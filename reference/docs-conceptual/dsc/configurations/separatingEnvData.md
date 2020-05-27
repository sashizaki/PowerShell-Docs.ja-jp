---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成データと環境データの分離
ms.openlocfilehash: 076e17054cfa20fad5ca925df126e239a77268db
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692427"
---
# <a name="separating-configuration-and-environment-data"></a>構成データと環境データの分離

>適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

構成データを使用して、DSC 構成で使用するデータを構成自体と切り離しておくと便利です。
そうすることにより、複数の環境に 1 つの構成を使用することができます。

たとえば、アプリケーションを開発している場合は、開発環境と運用環境の両方に 1 つの構成を使用し、構成データを使用して各環境のデータを指定することができます。

## <a name="what-is-configuration-data"></a>構成データとは

構成データはハッシュ テーブルで定義されるデータで、その構成をコンパイルするときに DSC 構成に渡されます。

**ConfigurationData** ハッシュ テーブルの詳細については、[構成データの使用](configData.md)に関するページを参照してください。

## <a name="a-simple-example"></a>簡単な例

簡単な例で仕組みを見てみましょう。
一部のノードには **IIS** を、他のノードには **Hyper-V** を存在させる 1 つの構成を作成します。

```powershell
Configuration MyDscConfiguration {

  Node $AllNodes.Where{$_.Role -eq "WebServer"}.NodeName
    {
  WindowsFeature IISInstall {
    Ensure = 'Present'
    Name   = 'Web-Server'
  }

 }
    Node $AllNodes.Where{$_.Role -eq "VMHost"}.NodeName
    {
        WindowsFeature HyperVInstall {
            Ensure = 'Present'
            Name   = 'Hyper-V'
        }
    }
}

$MyData =
@{
    AllNodes =
    @(
        @{
            NodeName    = 'VM-1'
            Role = 'WebServer'
        },

        @{
            NodeName    = 'VM-2'
            Role = 'VMHost'
        }
    )
}

MyDscConfiguration -ConfigurationData $MyData
```

このスクリプトの最後の行は、`$MyData`ConfigurationData**パラメーターの値として** を渡して、構成をコンパイルします。

その結果、2 つの MOF ファイルが作成されます。

```
    Directory: C:\DscTests\MyDscConfiguration


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/31/2017   5:09 PM           1968 VM-1.mof
-a----        3/31/2017   5:09 PM           1970 VM-2.mof
```

`$MyData` が、それぞれ独自の `NodeName` と `Role` を持つ、2 つの異なるノードを指定します。 構成は、 **(具体的には**) から取得したノードのコレクションを集めることで動的に`$MyData`ノード`$AllNodes` ブロックを作成し、そのコレクションを `Role` プロパティと突き合わせてフィルタ―処理します。

## <a name="using-configuration-data-to-define-development-and-production-environments"></a>構成データを使用して、開発および運用環境を定義する

1 つの構成を使用して Web サイトの開発環境と運用環境の両方を設定する完全な例を見てみましょう。 開発環境では、IIS と SQL Server の両方が 1 つのノードにインストールされています。 運用環境では、IIS と SQL は別々のノードにインストールされています。 .psd1 構成データ ファイルを使用して、この 2 つの異なる環境のデータを指定します。

### <a name="configuration-data-file"></a>構成データ ファイル

開発環境と運用環境のデータを、`DevProdEnvData.psd1` という名前のファイルに次のように定義します。

```powershell
@{

    AllNodes = @(

        @{
            NodeName        = "*"
            SQLServerName   = "MySQLServer"
            SqlSource       = "C:\Software\Sql"
            DotNetSrc       = "C:\Software\sxs"
            WebSiteName     = "New website"
        },

        @{
            NodeName        = "Prod-SQL"
            Role            = "MSSQL"
        },

        @{
            NodeName        = "Prod-IIS"
            Role            = "Web"
            SiteContents    = "C:\Website\Prod\SiteContents\"
            SitePath        = "\\Prod-IIS\Website\"
        },

        @{
            NodeName         = "Dev"
            Role             = "MSSQL", "Web"
            SiteContents     = "C:\Website\Dev\SiteContents\"
            SitePath         = "\\Dev\Website\"
        }
    )
}
```

### <a name="configuration-script-file"></a>構成スクリプト ファイル

次に、`.ps1` で定義されている構成において、`DevProdEnvData.psd1` に定義したノードを役割別 (`MSSQL`、`Dev`、またはその両方) にフィルター処理し、役割に応じて構成します。
開発環境では 1 つのノードに SQL Server と IIS の両方がありますが、運用環境では、SQL Server と IIS はそれぞれ 2 つの異なるノードにあります。
`SiteContents` プロパティで指定したように、サイトのコンテンツも異なります。

構成スクリプトの最後の行で、`DevProdEnvData.psd1` を `$ConfigurationData` パラメーターとして渡して、構成を呼び出し (MOF ドキュメントに構成をコンパイルし) ます。

>**注:** この構成には、ターゲット ノードにインストールされるモジュール `xSqlPs` と `xWebAdministration` が必要です。

`MyWebApp.ps1` という名前のファイルで構成を定義しましょう。

```powershell
Configuration MyWebApp
{
    Import-DscResource -Module PSDesiredStateConfiguration
    Import-DscResource -Module xSqlPs
    Import-DscResource -Module xWebAdministration

    Node $AllNodes.Where{$_.Role -contains "MSSQL"}.NodeName
   {
        # Install prerequisites
        WindowsFeature installdotNet35
        {
            Ensure      = "Present"
            Name        = "Net-Framework-Core"
            Source      = "c:\software\sxs"
        }

        # Install SQL Server
        xSqlServerInstall InstallSqlServer
        {
            InstanceName = $Node.SQLServerName
            SourcePath   = $Node.SqlSource
            Features     = "SQLEngine,SSMS"
            DependsOn    = "[WindowsFeature]installdotNet35"

        }
   }

   Node $AllNodes.Where{$_.Role -contains "Web"}.NodeName
   {
        # Install the IIS role
        WindowsFeature IIS
        {
            Ensure       = 'Present'
            Name         = 'Web-Server'
        }

        # Install the ASP .NET 4.5 role
        WindowsFeature AspNet45
        {
            Ensure       = 'Present'
            Name         = 'Web-Asp-Net45'

        }

        # Stop the default website
        xWebsite DefaultSite
        {
            Ensure       = 'Present'
            Name         = 'Default Web Site'
            State        = 'Stopped'
            PhysicalPath = 'C:\inetpub\wwwroot'
            DependsOn    = '[WindowsFeature]IIS'

        }

        # Copy the website content
        File WebContent

        {
            Ensure          = 'Present'
            SourcePath      = $Node.SiteContents
            DestinationPath = $Node.SitePath
            Recurse         = $true
            Type            = 'Directory'
            DependsOn       = '[WindowsFeature]AspNet45'

        }


        # Create the new Website

        xWebsite NewWebsite

        {

            Ensure          = 'Present'
            Name            = $Node.WebSiteName
            State           = 'Started'
            PhysicalPath    = $Node.SitePath
            DependsOn       = '[File]WebContent'
        }

    }

}

MyWebApp -ConfigurationData DevProdEnvData.psd1
```

この構成を実行すると、3 つの MOF ファイルが作成されます (**AllNodes** 配列内の名付けられたエントリごとに 1 つ)。

```
    Directory: C:\DscTests\MyWebApp


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/31/2017   5:47 PM           2944 Prod-SQL.mof
-a----        3/31/2017   5:47 PM           6994 Dev.mof
-a----        3/31/2017   5:47 PM           5338 Prod-IIS.mof
```

## <a name="using-non-node-data"></a>ノード外のデータを使用する

ノードに固有ではないデータの **ConfigurationData** ハッシュ テーブルに追加キーを追加できます。
次の構成では、2 つの Web サイトが存在するようにします。
それぞれの Web サイトのデータは **AllNodes** 配列に定義されています。
ファイル `Config.xml` は両方の Web サイトに使用されるので、それを追加キーで `NonNodeData` という名前で定義します。
追加キーは必要な数だけ設定でき、名前の付け方も自由です。
`NonNodeData` は予約語ではなく、ここでの追加キーにこのように名前を付けただけです。

追加キーへのアクセスには、特殊な変数 **$ConfigurationData** を使用します。
この例では `ConfigFileContents` は、次の行を使用してアクセスします。

```powershell
 Contents = $ConfigurationData.NonNodeData.ConfigFileContents
 ```

 これは `File` リソース ブロック内です。

```powershell
$MyData =
@{
    AllNodes =
    @(
        @{
            NodeName           = "*"
            LogPath            = "C:\Logs"
        },

        @{
            NodeName = "VM-1"
            SiteContents = "C:\Site1"
            SiteName = "Website1"
        },


        @{
            NodeName = "VM-2"
            SiteContents = "C:\Site2"
            SiteName = "Website2"
        }
    );

    NonNodeData =
    @{
        ConfigFileContents = (Get-Content C:\Template\Config.xml)
     }
}

configuration WebsiteConfig
{
    Import-DscResource -ModuleName xWebAdministration -Name MSFT_xWebsite

    node $AllNodes.NodeName
    {
        xWebsite Site
        {
            Name         = $Node.SiteName
            PhysicalPath = $Node.SiteContents
            Ensure       = "Present"
        }

        File ConfigFile
        {
            DestinationPath = $Node.SiteContents + "\\config.xml"
            Contents = $ConfigurationData.NonNodeData.ConfigFileContents
        }
    }
}
```

## <a name="see-also"></a>参照

- [構成データの使用](configData.md)
- [構成データでの資格情報オプション](configDataCredentials.md)
- [DSC 構成](configurations.md)
