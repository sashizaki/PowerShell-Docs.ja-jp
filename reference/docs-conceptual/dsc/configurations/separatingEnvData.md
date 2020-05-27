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
# <a name="separating-configuration-and-environment-data"></a><span data-ttu-id="54017-103">構成データと環境データの分離</span><span class="sxs-lookup"><span data-stu-id="54017-103">Separating configuration and environment data</span></span>

><span data-ttu-id="54017-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="54017-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="54017-105">構成データを使用して、DSC 構成で使用するデータを構成自体と切り離しておくと便利です。</span><span class="sxs-lookup"><span data-stu-id="54017-105">It can be useful to separate the data used in a DSC configuration from the configuration itself by using configuration data.</span></span>
<span data-ttu-id="54017-106">そうすることにより、複数の環境に 1 つの構成を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="54017-106">By doing this, you can use a single configuration for multiple environments.</span></span>

<span data-ttu-id="54017-107">たとえば、アプリケーションを開発している場合は、開発環境と運用環境の両方に 1 つの構成を使用し、構成データを使用して各環境のデータを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="54017-107">For example, if you are developing an application, you can use one configuration for both development and production environments, and use configuration data to specify data for each environment.</span></span>

## <a name="what-is-configuration-data"></a><span data-ttu-id="54017-108">構成データとは</span><span class="sxs-lookup"><span data-stu-id="54017-108">What is configuration data?</span></span>

<span data-ttu-id="54017-109">構成データはハッシュ テーブルで定義されるデータで、その構成をコンパイルするときに DSC 構成に渡されます。</span><span class="sxs-lookup"><span data-stu-id="54017-109">Configuration data is data that is defined in a hashtable and passed to a DSC configuration when you compile that configuration.</span></span>

<span data-ttu-id="54017-110">**ConfigurationData** ハッシュ テーブルの詳細については、[構成データの使用](configData.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="54017-110">For a detailed description of the **ConfigurationData** hashtable, see [Using configuration data](configData.md).</span></span>

## <a name="a-simple-example"></a><span data-ttu-id="54017-111">簡単な例</span><span class="sxs-lookup"><span data-stu-id="54017-111">A simple example</span></span>

<span data-ttu-id="54017-112">簡単な例で仕組みを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="54017-112">Let's look at a very simple example to see how this works.</span></span>
<span data-ttu-id="54017-113">一部のノードには **IIS** を、他のノードには **Hyper-V** を存在させる 1 つの構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="54017-113">We'll create a single configuration that ensures that **IIS** is present on some nodes, and that **Hyper-V** is present on others:</span></span>

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

<span data-ttu-id="54017-114">このスクリプトの最後の行は、`$MyData`ConfigurationData**パラメーターの値として** を渡して、構成をコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="54017-114">The last line in this script compiles the configuration, passing `$MyData` as the value **ConfigurationData** parameter.</span></span>

<span data-ttu-id="54017-115">その結果、2 つの MOF ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="54017-115">The result is that two MOF files are created:</span></span>

```
    Directory: C:\DscTests\MyDscConfiguration


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/31/2017   5:09 PM           1968 VM-1.mof
-a----        3/31/2017   5:09 PM           1970 VM-2.mof
```

<span data-ttu-id="54017-116">`$MyData` が、それぞれ独自の `NodeName` と `Role` を持つ、2 つの異なるノードを指定します。</span><span class="sxs-lookup"><span data-stu-id="54017-116">`$MyData` specifies two different nodes, each with its own `NodeName` and `Role`.</span></span> <span data-ttu-id="54017-117">構成は、 **(具体的には**) から取得したノードのコレクションを集めることで動的に`$MyData`ノード`$AllNodes` ブロックを作成し、そのコレクションを `Role` プロパティと突き合わせてフィルタ―処理します。</span><span class="sxs-lookup"><span data-stu-id="54017-117">The configuration dynamically creates **Node** blocks by taking the collection of nodes it gets from `$MyData` (specifically, `$AllNodes`) and filters that collection against the `Role` property..</span></span>

## <a name="using-configuration-data-to-define-development-and-production-environments"></a><span data-ttu-id="54017-118">構成データを使用して、開発および運用環境を定義する</span><span class="sxs-lookup"><span data-stu-id="54017-118">Using configuration data to define development and production environments</span></span>

<span data-ttu-id="54017-119">1 つの構成を使用して Web サイトの開発環境と運用環境の両方を設定する完全な例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="54017-119">Let's look at a complete example that uses a single configuration to set up both development and production environments of a website.</span></span> <span data-ttu-id="54017-120">開発環境では、IIS と SQL Server の両方が 1 つのノードにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="54017-120">In the development environment, both IIS and SQL Server are installed on a single nodes.</span></span> <span data-ttu-id="54017-121">運用環境では、IIS と SQL は別々のノードにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="54017-121">In the production environment, IIS and SQL Server are installed on separate nodes.</span></span> <span data-ttu-id="54017-122">.psd1 構成データ ファイルを使用して、この 2 つの異なる環境のデータを指定します。</span><span class="sxs-lookup"><span data-stu-id="54017-122">We'll use a configuration data .psd1 file to specify the data for the two different environments.</span></span>

### <a name="configuration-data-file"></a><span data-ttu-id="54017-123">構成データ ファイル</span><span class="sxs-lookup"><span data-stu-id="54017-123">Configuration data file</span></span>

<span data-ttu-id="54017-124">開発環境と運用環境のデータを、`DevProdEnvData.psd1` という名前のファイルに次のように定義します。</span><span class="sxs-lookup"><span data-stu-id="54017-124">We'll define the development and production environment data in a file named `DevProdEnvData.psd1` as follows:</span></span>

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

### <a name="configuration-script-file"></a><span data-ttu-id="54017-125">構成スクリプト ファイル</span><span class="sxs-lookup"><span data-stu-id="54017-125">Configuration script file</span></span>

<span data-ttu-id="54017-126">次に、`.ps1` で定義されている構成において、`DevProdEnvData.psd1` に定義したノードを役割別 (`MSSQL`、`Dev`、またはその両方) にフィルター処理し、役割に応じて構成します。</span><span class="sxs-lookup"><span data-stu-id="54017-126">Now, in the configuration, which is defined in a `.ps1` file, we filter the nodes we defined in `DevProdEnvData.psd1` by their role (`MSSQL`, `Dev`, or both), and configure them accordingly.</span></span>
<span data-ttu-id="54017-127">開発環境では 1 つのノードに SQL Server と IIS の両方がありますが、運用環境では、SQL Server と IIS はそれぞれ 2 つの異なるノードにあります。</span><span class="sxs-lookup"><span data-stu-id="54017-127">The development environment has both the SQL Server and IIS on one node, while the production environment has them on two different nodes.</span></span>
<span data-ttu-id="54017-128">`SiteContents` プロパティで指定したように、サイトのコンテンツも異なります。</span><span class="sxs-lookup"><span data-stu-id="54017-128">The site contents is also different, as specified by the `SiteContents` properties.</span></span>

<span data-ttu-id="54017-129">構成スクリプトの最後の行で、`DevProdEnvData.psd1` を `$ConfigurationData` パラメーターとして渡して、構成を呼び出し (MOF ドキュメントに構成をコンパイルし) ます。</span><span class="sxs-lookup"><span data-stu-id="54017-129">At the end of the configuration script, we call the configuration (compile it into a MOF document), passing `DevProdEnvData.psd1` as the `$ConfigurationData` parameter.</span></span>

><span data-ttu-id="54017-130">**注:** この構成には、ターゲット ノードにインストールされるモジュール `xSqlPs` と `xWebAdministration` が必要です。</span><span class="sxs-lookup"><span data-stu-id="54017-130">**Note:** This configuration requires the modules `xSqlPs` and `xWebAdministration` to be installed on the target node.</span></span>

<span data-ttu-id="54017-131">`MyWebApp.ps1` という名前のファイルで構成を定義しましょう。</span><span class="sxs-lookup"><span data-stu-id="54017-131">Let's define the configuration in a file named `MyWebApp.ps1`:</span></span>

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

<span data-ttu-id="54017-132">この構成を実行すると、3 つの MOF ファイルが作成されます (**AllNodes** 配列内の名付けられたエントリごとに 1 つ)。</span><span class="sxs-lookup"><span data-stu-id="54017-132">When you run this configuration, three MOF files are created (one for each named entry in the **AllNodes** array):</span></span>

```
    Directory: C:\DscTests\MyWebApp


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/31/2017   5:47 PM           2944 Prod-SQL.mof
-a----        3/31/2017   5:47 PM           6994 Dev.mof
-a----        3/31/2017   5:47 PM           5338 Prod-IIS.mof
```

## <a name="using-non-node-data"></a><span data-ttu-id="54017-133">ノード外のデータを使用する</span><span class="sxs-lookup"><span data-stu-id="54017-133">Using non-node data</span></span>

<span data-ttu-id="54017-134">ノードに固有ではないデータの **ConfigurationData** ハッシュ テーブルに追加キーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="54017-134">You can add additional keys to the **ConfigurationData** hashtable for data that is not specific to a node.</span></span>
<span data-ttu-id="54017-135">次の構成では、2 つの Web サイトが存在するようにします。</span><span class="sxs-lookup"><span data-stu-id="54017-135">The following configuration ensures the presence of two websites.</span></span>
<span data-ttu-id="54017-136">それぞれの Web サイトのデータは **AllNodes** 配列に定義されています。</span><span class="sxs-lookup"><span data-stu-id="54017-136">Data for each website are defined in the **AllNodes** array.</span></span>
<span data-ttu-id="54017-137">ファイル `Config.xml` は両方の Web サイトに使用されるので、それを追加キーで `NonNodeData` という名前で定義します。</span><span class="sxs-lookup"><span data-stu-id="54017-137">The file `Config.xml` is used for both websites, so we define it in an additional key with the name `NonNodeData`.</span></span>
<span data-ttu-id="54017-138">追加キーは必要な数だけ設定でき、名前の付け方も自由です。</span><span class="sxs-lookup"><span data-stu-id="54017-138">Note that you can have as many additional keys as you want, and you can name them anything you want.</span></span>
<span data-ttu-id="54017-139">`NonNodeData` は予約語ではなく、ここでの追加キーにこのように名前を付けただけです。</span><span class="sxs-lookup"><span data-stu-id="54017-139">`NonNodeData` is not a reserved word, it is just what we decided to name the additional key.</span></span>

<span data-ttu-id="54017-140">追加キーへのアクセスには、特殊な変数 **$ConfigurationData** を使用します。</span><span class="sxs-lookup"><span data-stu-id="54017-140">You access additional keys by using the special variable **$ConfigurationData**.</span></span>
<span data-ttu-id="54017-141">この例では `ConfigFileContents` は、次の行を使用してアクセスします。</span><span class="sxs-lookup"><span data-stu-id="54017-141">In this example, `ConfigFileContents` is accessed with the line:</span></span>

```powershell
 Contents = $ConfigurationData.NonNodeData.ConfigFileContents
 ```

 <span data-ttu-id="54017-142">これは `File` リソース ブロック内です。</span><span class="sxs-lookup"><span data-stu-id="54017-142">in the `File` resource block.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="54017-143">参照</span><span class="sxs-lookup"><span data-stu-id="54017-143">See Also</span></span>

- [<span data-ttu-id="54017-144">構成データの使用</span><span class="sxs-lookup"><span data-stu-id="54017-144">Using configuration data</span></span>](configData.md)
- [<span data-ttu-id="54017-145">構成データでの資格情報オプション</span><span class="sxs-lookup"><span data-stu-id="54017-145">Credentials Options in Configuration Data</span></span>](configDataCredentials.md)
- [<span data-ttu-id="54017-146">DSC 構成</span><span class="sxs-lookup"><span data-stu-id="54017-146">DSC Configurations</span></span>](configurations.md)
