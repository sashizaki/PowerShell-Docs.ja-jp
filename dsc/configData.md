---
title: "構成データと環境データの分離"
ms.date: 2016-05-16
keywords: PowerShell, DSC
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
ms.openlocfilehash: f8f8ef06cd79af294bad7bb8cf3d6676ab9a69bc
ms.sourcegitcommit: f06ef671c0a646bdd277634da89cc11bc2a78a41
translationtype: HT
---
# <a name="separating-configuration-and-environment-data"></a>構成データと環境データの分離

>適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

組み込みの DSC **ConfigurationData** パラメーターを使用して、構成内で使用可能なデータを定義することができます。 これにより、複数のノードや異なる環境で使用可能な 1 つの構成を作成できます。 たとえば、アプリケーションを開発している場合は、開発環境と運用環境の両方に 1 つの構成を使用し、構成データを使用して各環境のデータを指定することができます。

簡単な例で仕組みを見てみましょう。 一部のノードには **IIS** を、他のノードには **Hyper-V** を存在させる 1 つの構成を作成します。 

```powershell
Configuration MyDscConfiguration {
    
    Node $AllNodes.Where{$_.Role -eq "WebServer"}.NodeName
    {
        WindowsFeature IISInstall {
            Ensure = 'Present'
            Name   = 'Web-Server'
        }
        
    }
    Node $AllNodes.Where($_.Role -eq "VMHost").NodeName
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
        }

        @{
            NodeName    = 'VM-2'
            Role = 'VMHost'
        }
    )
}

MyDscConfiguration -ConfigurationData $MyData
```

このスクリプトの最後の行は、**ConfigurationData** パラメーターの値として `$MyData` を渡し、MOF ドキュメントに構成をコンパイルします。 `$MyData` が、それぞれ独自の `NodeName` と `Role` を持つ、2 つの異なるノードを指定します。 構成は、`$MyData` (具体的には `$AllNodes`) から取得したノードのコレクションを集めることで動的に**ノード** ブロックを作成し、そのコレクションを `Role` プロパティと突き合わせてフィルタ―処理します。

さらに詳しく仕組みを見てみましょう。

## <a name="the-configurationdata-parameter"></a>ConfigurationData パラメーター

DSC 構成は、構成のコンパイル時に指定した **ConfigurationData** という名前のパラメーターを受け取ります。 構成をコンパイルする方法の詳細については、「[DSC 構成](configurations.md)」を参照してください。

**ConfigurationData** パラメーターはハッシュテーブルであり、**AllNodes** という名前のキーが少なくとも 1 つ必要です。 その他のキーを含めることもできます。

```powershell
$MyData = 
@{
    AllNodes = @()
    NonNodeData = ""   
}
```

**AllNodes** キーの値は配列です。 この配列の各要素もハッシュ テーブルであり、**NodeName** という名前のキーが少なくとも 1 つ必要です。

```powershell
$MyData = 
@{
    AllNodes = 
    @(
        @{
            NodeName = "VM-1"
        },

 
        @{
            NodeName = "VM-2"
        },

 
        @{
            NodeName = "VM-3"
        }
    );

    NonNodeData = ""   
}
```

各ハッシュテーブルには他のキーを追加することもできます。

```powershell
$MyData = 
@{
    AllNodes = 
    @(
        @{
            NodeName = "VM-1"
            Role     = "WebServer"
        },

 
        @{
            NodeName = "VM-2"
            Role     = "SQLServer"
        },

 
        @{
            NodeName = "VM-3"
            Role     = "WebServer"
        }
    );

    NonNodeData = ""   
}
```

すべてのノードにプロパティを適用するには、**AllNodes** 配列に **NodeName** が `*` のメンバーを作成します。 たとえば、すべてのノードに `LogPath` プロパティを適用するには、次のように入力します。

```powershell
$MyData = 
@{
    AllNodes = 
    @(
        @{
            NodeName     = "*"
            LogPath      = "C:\Logs"
        },

 
        @{
            NodeName     = "VM-1"
            Role         = "WebServer"
            SiteContents = "C:\Site1"
            SiteName     = "Website1"
        },

 
        @{
            NodeName     = "VM-2"
            Role         = "SQLServer"
        },

 
        @{
            NodeName     = "VM-3"
            Role         = "WebServer"
            SiteContents = "C:\Site2"
            SiteName     = "Website3"
        }
    );
}
```

これは、名前が `LogPath` で `"C:\Logs"` の値を持つプロパティを、その他のブロック (`VM-1`、`VM-2`、および `VM-3`) にそれぞれ追加するのと同じことです。

## <a name="defining-the-configurationdata-hashtable"></a>ConfigurationData ハッシュテーブルの定義

**ConfigurationData** は、(これまでの例のように) 構成として同じスクリプト ファイル内に変数として定義するか、または別の .psd1 ファイルに定義することができます。 **ConfigurationData** を .psd1 ファイルで定義するには、構成データを表すハッシュテーブルのみが含まれるファイルを作成します。

たとえば、次の内容を含む `MyData.psd1` という名前のファイルを作成します。

```powershell
@{
    AllNodes =
    @(
        @{
            NodeName    = 'VM-1'
            FeatureName = 'Web-Server'
        }

        @{
            NodeName    = 'VM-2'
            FeatureName = 'Hyper-V'
        }
    )
}
```

.psd1 ファイルに定義された構成データを使用するには、構成のコンパイル時に、そのファイルのパスと名前を **ConfigurationData** パラメーターの値として渡します。

```powershell
MyDscConfiguration -ConfigurationData .\MyData.psd1
```

## <a name="using-configurationdata-variables-in-a-configuration"></a>構成での ConfigurationData 変数の使用

DSC には、構成スクリプトで使用できる 3 つの特殊な変数 **$AllNodes**、**$Node**、および**$ConfigurationData** が用意されています。

- **$AllNodes** は、**ConfigurationData** で定義されたノードのコレクション全体を参照します。 **.Where()** と **.ForEach()** を使用すると、**AllNodes** コレクションをフィルター処理できます。
- **Node** は、**.Where()** または **.ForEach()** を使用してフィルター処理された後の **AllNodes** コレクション内にある特定のエントリを参照します。
- **ConfigurationData** は、構成のコンパイル時にパラメーターとして渡されるハッシュ テーブル全体を参照します。

## <a name="devops-example"></a>DevOps の例

1 つの構成を使用して Web サイトの開発環境と運用環境の両方を設定する完全な例を見てみましょう。 開発環境では、IIS と SQL Server の両方が 1 つのノードにインストールされています。 運用環境では、IIS と SQL は別々のノードにインストールされています。 .psd1 構成データ ファイルを使用して、この 2 つの異なる環境のデータを指定します。

### <a name="configuration-data-file"></a>構成データ ファイル

開発環境と運用環境を、`DevProdEnvData.psd1` という名前のファイルに次のように定義します。

```powershell
@{

    AllNodes = @(

        @{
            NodeName        = "*"
            SQLServerName   = "MySQLServer"
            SqlSource       = "C:\Software\Sql"
            DotNetSrc       = "C:\Software\sxs"
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
        }

        @{
            NodeName         = "Dev"
            Role             = "MSSQL", "Web"
            SiteContents     = "C:\Website\Dev\SiteContents\"
            SitePath         = "\\Dev\Website\"

        }

    )

}

    )

}
```

### <a name="configuration-file"></a>［構成ファイル］

次に、構成において、`DevProdEnvData.psd1` に定義したノードを役割別 (`MSSQL`、`Dev`、またはその両方) にフィルター処理し、役割に応じて構成します。 開発環境では 1 つのノードに SQL Server と IIS の両方がありますが、運用環境では、SQL Server と IIS はそれぞれ 2 つの異なるノードにあります。 `SiteContents` プロパティで指定したように、サイトのコンテンツも異なります。

構成スクリプトの最後の行で、`DevProdEnvData.psd1` を `$ConfigurationData` パラメーターとして渡して、構成を呼び出し (MOF ドキュメントに構成をコンパイルし) ます。

```powershell
Configuration MyWebApp
{
    Import-DscResource -Module PSDesiredStateConfiguration
    Import-DscResource -Module xSqlPs

    Node $AllNodes.Where{$_.Role -contains "MSSQL"}.Nodename
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

   Node $AllNodes.Where($_.Role -contains "Web")
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
            Name            = $WebSiteName
            State           = 'Started'
            PhysicalPath    = $Node.SitePath
            DependsOn       = '[File]WebContent'
        }

    }

}

MyWebApp -ConfigurationData DevProdEnvData.psd1
```

## <a name="see-also"></a>参照
- [構成データでの資格情報オプション](configDataCredentials.md)
- [DSC 構成](configurations.md)
