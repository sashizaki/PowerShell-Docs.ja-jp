---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: クイック スタート - DSC を使用して Web サイトを作成する
ms.openlocfilehash: d98607939ccd3cc5e660936d8c0a6d54fce7d65f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71955069"
---
> <span data-ttu-id="9857f-103">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="9857f-103">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

# <a name="quickstart---create-a-website-with-dsc"></a><span data-ttu-id="9857f-104">クイック スタート - DSC を使用して Web サイトを作成する</span><span class="sxs-lookup"><span data-stu-id="9857f-104">Quickstart - Create a website with DSC</span></span>

<span data-ttu-id="9857f-105">この演習では、Desired State Configuration (DSC) の構成の作成と適用について最初から最後まで説明します。</span><span class="sxs-lookup"><span data-stu-id="9857f-105">This exercise walks through creating and applying a Desired State Configuration (DSC) configuration from start to finish.</span></span>
<span data-ttu-id="9857f-106">これから使用するサンプルでは、サーバーの `Web-Server` (IIS) 機能が有効になっており、そのサーバのディレクトリ `inetpub\wwwroot` に「Hello World」サンプルのコンテンツが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="9857f-106">The example we'll use ensures that a server has the `Web-Server` (IIS) feature enabled, and that the content for a simple "Hello World" website is present in the `inetpub\wwwroot` directory of that server.</span></span>

<span data-ttu-id="9857f-107">DSC の概要としくみついては、「[意思決定者向け Desired State Configuration の概要](../overview/decisionMaker.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9857f-107">For an overview of what DSC is and how it works, see [Desired State Configuration Overview for Decision Makers](../overview/decisionMaker.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="9857f-108">要件</span><span class="sxs-lookup"><span data-stu-id="9857f-108">Requirements</span></span>

<span data-ttu-id="9857f-109">このサンプルを実行するには、Windows Server 2012 以降と PowerShell 4.0 以降が動作しているコンピューターが必要です。</span><span class="sxs-lookup"><span data-stu-id="9857f-109">To run this example, you will need a computer running Windows Server 2012 or later and PowerShell 4.0 or later.</span></span>

## <a name="write-and-place-the-indexhtm-file"></a><span data-ttu-id="9857f-110">index.htm ファイルを記述し、配置する</span><span class="sxs-lookup"><span data-stu-id="9857f-110">Write and place the index.htm file</span></span>

<span data-ttu-id="9857f-111">最初に、Web サイトのコンテンツとして使用する HTML ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9857f-111">First, we'll create the HTML file that we will use as the website content.</span></span>

<span data-ttu-id="9857f-112">ルート フォルダーに `test` という名前のフォルダを作成します。</span><span class="sxs-lookup"><span data-stu-id="9857f-112">In your root folder, create a folder named `test`.</span></span>

<span data-ttu-id="9857f-113">テキスト エディターで、次のテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="9857f-113">In a text editor, type the following text:</span></span>

```html
<head></head>
<body>
<p>Hello World!</p>
</body>
```

<span data-ttu-id="9857f-114">これを先ほど作成した `test` フォルダに `index.htm` というファイル名でこのファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="9857f-114">Save this as `index.htm` in the `test` folder you created earlier.</span></span>

## <a name="write-the-configuration"></a><span data-ttu-id="9857f-115">構成を記述する</span><span class="sxs-lookup"><span data-stu-id="9857f-115">Write the configuration</span></span>

<span data-ttu-id="9857f-116">[DSC 構成](../configurations/configurations.md)は 1 つまたは複数のターゲット コンピューター (ノード) を構成する方法を定義する特別な PowerShell 関数です。</span><span class="sxs-lookup"><span data-stu-id="9857f-116">A [DSC configuration](../configurations/configurations.md) is a special PowerShell function that defines how you want to configure one or more target computers (nodes).</span></span>

<span data-ttu-id="9857f-117">PowerShell ISE で、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9857f-117">In the PowerShell ISE, type the following:</span></span>

```powershell
Configuration WebsiteTest {

    # Import the module that contains the resources we're using.
    Import-DscResource -ModuleName PsDesiredStateConfiguration

    # The Node statement specifies which targets this configuration will be applied to.
    Node 'localhost' {

        # The first resource block ensures that the Web-Server (IIS) feature is enabled.
        WindowsFeature WebServer {
            Ensure = "Present"
            Name   = "Web-Server"
        }

        # The second resource block ensures that the website content copied to the website root folder.
        File WebsiteContent {
            Ensure = 'Present'
            SourcePath = 'c:\test\index.htm'
            DestinationPath = 'c:\inetpub\wwwroot'
        }
    }
}
```

<span data-ttu-id="9857f-118">このファイルを `WebsiteTest.ps1` として保存します。</span><span class="sxs-lookup"><span data-stu-id="9857f-118">Save the file as `WebsiteTest.ps1`.</span></span>

<span data-ttu-id="9857f-119">関数名の前に **Configuration** というキーワードを追加することで、PowerShell の関数のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="9857f-119">You can see that it looks like a PowerShell function, with the addition of the keyword **Configuration** used before the name of the function.</span></span>

<span data-ttu-id="9857f-120">`localhost` 場合、**ノード**ブロックは構成するターゲット ノードを指定します。</span><span class="sxs-lookup"><span data-stu-id="9857f-120">The **Node** block specifies the target node to be configured, in this case `localhost`.</span></span>

<span data-ttu-id="9857f-121">構成は 2 つの[リソース](../resources/resources.md) (**WindowsFeature** と**ファイル**) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9857f-121">The configuration calls two [resources](../resources/resources.md), **WindowsFeature** and **File**.</span></span>
<span data-ttu-id="9857f-122">リソースは、ターゲット ノードが構成によって定義された状態になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="9857f-122">Resources do the work of ensuring that the target node is in the state defined by the configuration.</span></span>

## <a name="compile-the-configuration"></a><span data-ttu-id="9857f-123">構成をコンパイルする</span><span class="sxs-lookup"><span data-stu-id="9857f-123">Compile the configuration</span></span>

<span data-ttu-id="9857f-124">DSC 構成をノードに適用するには、最初にコンパイルを行い、MOF ファイルを出力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9857f-124">For a DSC configuration to be applied to a node, it must first be compiled into a MOF file.</span></span>
<span data-ttu-id="9857f-125">これを行うには、構成を関数のように実行します。</span><span class="sxs-lookup"><span data-stu-id="9857f-125">To do this, you run the configuration like a function.</span></span>
<span data-ttu-id="9857f-126">PowerShell コンソールで構成が保存されているフォルダーに移動し、次のコマンドを実行して構成のコンパイルを行い、MOF ファイルを出力します。</span><span class="sxs-lookup"><span data-stu-id="9857f-126">In a PowerShell console, navigate to the same folder where you saved your configuration and run the following commands to compile the configuration into a MOF file:</span></span>

```powershell
. .\WebsiteTest.ps1
WebsiteTest
```

<span data-ttu-id="9857f-127">これにより、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="9857f-127">This generates the following output:</span></span>

```
Directory: C:\ConfigurationTest\WebsiteTest


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

<span data-ttu-id="9857f-128">最初の行では、コンソールで利用可能な構成関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="9857f-128">The first line makes the configuration function available in the console.</span></span>
<span data-ttu-id="9857f-129">2 行目では構成を実行します。</span><span class="sxs-lookup"><span data-stu-id="9857f-129">The second line runs the configuration.</span></span>
<span data-ttu-id="9857f-130">その結果、現在のフォルダのサブ フォルダとして `WebsiteTest` という名前の新しいフォルダが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9857f-130">The result is that a new folder, named `WebsiteTest` is created as a subfolder of the current folder.</span></span>
<span data-ttu-id="9857f-131">`WebsiteTest` フォルダーには、`localhost.mof` という名前のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9857f-131">The `WebsiteTest` folder contains a file named `localhost.mof`.</span></span>
<span data-ttu-id="9857f-132">これは後にターゲット ノードに適用できるファイルです。</span><span class="sxs-lookup"><span data-stu-id="9857f-132">It is this file that can then be applied to the target node.</span></span>

## <a name="apply-the-configuration"></a><span data-ttu-id="9857f-133">構成を適用する</span><span class="sxs-lookup"><span data-stu-id="9857f-133">Apply the configuration</span></span>

<span data-ttu-id="9857f-134">コンパイル済みの MOF があるため、[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットを呼び出すことで、ターゲット ノード (今回の場合はローカル コンピューター) に構成を適用できます。</span><span class="sxs-lookup"><span data-stu-id="9857f-134">Now that you have the compiled MOF, you can apply the configuration to the target node (in this case, the local computer) by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

<span data-ttu-id="9857f-135">`Start-DscConfiguration` コマンドレットから DSC のエンジンである [Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md) に対して構成の適用を指示します。</span><span class="sxs-lookup"><span data-stu-id="9857f-135">The `Start-DscConfiguration` cmdlet tells the [Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md), which is the engine of DSC, to apply the configuration.</span></span>
<span data-ttu-id="9857f-136">LCM はDSC リソースを呼び出し、構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="9857f-136">The LCM does the work of calling the DSC resources to apply the configuration.</span></span>

<span data-ttu-id="9857f-137">PowerShell コンソールで構成が保存されているフォルダーに移動し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9857f-137">In a PowerShell console, navigate to the same folder where you saved your configuration and run the following command:</span></span>

```powershell
Start-DscConfiguration .\WebsiteTest
```

## <a name="test-the-configuration"></a><span data-ttu-id="9857f-138">構成をテストする</span><span class="sxs-lookup"><span data-stu-id="9857f-138">Test the configuration</span></span>

<span data-ttu-id="9857f-139">[Get-DscConfigurationStatus](/powershell/module/psdesiredstateconfiguration/get-dscconfigurationstatus) コマンドレットを呼び出すことで、構成の適用が正しく行われたか確認できます。</span><span class="sxs-lookup"><span data-stu-id="9857f-139">You can call the [Get-DscConfigurationStatus](/powershell/module/psdesiredstateconfiguration/get-dscconfigurationstatus) cmdlet to see whether the configuration succeeded.</span></span>

<span data-ttu-id="9857f-140">今回の場合は、Web ブラウザーで `http://localhost/` を参照することで、結果を直接テストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9857f-140">You can also test the results directly, in this case by browsing to `http://localhost/` in a web browser.</span></span>
<span data-ttu-id="9857f-141">この例の最初の手順として、作成した「Hello World」 HTML ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9857f-141">You should see the "Hello World" HTML page you created as the first step in this example.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9857f-142">次の手順</span><span class="sxs-lookup"><span data-stu-id="9857f-142">Next steps</span></span>

- <span data-ttu-id="9857f-143">「[DSC 構成](../configurations/configurations.md)」で DSC 構成の詳細を確認する。</span><span class="sxs-lookup"><span data-stu-id="9857f-143">Find out more about DSC configurations at [DSC configurations](../configurations/configurations.md).</span></span>
- <span data-ttu-id="9857f-144">「[DSC リソース](../resources/resources.md)」で利用可能な DSC リソースとカスタム DSC リソースの作成方法を確認する。</span><span class="sxs-lookup"><span data-stu-id="9857f-144">See what DSC resources are available, and how to create custom DSC resources at [DSC resources](../resources/resources.md).</span></span>
- <span data-ttu-id="9857f-145">「[PowerShell ギャラリー](https://www.powershellgallery.com/)」で DSC の構成とリソースを検索する。</span><span class="sxs-lookup"><span data-stu-id="9857f-145">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>
