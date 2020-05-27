---
ms.date: 12/12/2018
keywords: dsc, powershell, 構成, サービス, セットアップ
title: 構成の作成、コンパイル、適用
ms.openlocfilehash: 11de1d4552bc9c438adf9e3dea2059834e11e10c
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808301"
---
# <a name="write-compile-and-apply-a-configuration"></a><span data-ttu-id="6b750-103">構成の作成、コンパイル、適用</span><span class="sxs-lookup"><span data-stu-id="6b750-103">Write, Compile, and Apply a Configuration</span></span>

> <span data-ttu-id="6b750-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="6b750-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="6b750-105">この演習では、Desired State Configuration (DSC) の構成の作成と適用について最初から最後まで説明します。</span><span class="sxs-lookup"><span data-stu-id="6b750-105">This exercise walks through creating and applying a Desired State Configuration (DSC) configuration from start to finish.</span></span>
<span data-ttu-id="6b750-106">次の例では、非常に単純な構成を作成して適用する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="6b750-106">In the following example, you will learn how to write and apply a very simple Configuration.</span></span> <span data-ttu-id="6b750-107">この構成により、"HelloWorld.txt" ファイルがローカル コンピューターに存在していることが確保されます。</span><span class="sxs-lookup"><span data-stu-id="6b750-107">The Configuration will ensure a "HelloWorld.txt" file exists on your local machine.</span></span> <span data-ttu-id="6b750-108">ファイルを削除する場合は、次に更新されるときに DSC によってファイルが再作成されます。</span><span class="sxs-lookup"><span data-stu-id="6b750-108">If you delete the file, DSC will recreate it the next time it updates.</span></span>

<span data-ttu-id="6b750-109">DSC の概要としくみついては、[開発者向けの Desired State Configuration の概要](../overview/overview.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6b750-109">For an overview of what DSC is and how it works, see [Desired State Configuration Overview for Developers](../overview/overview.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="6b750-110">必要条件</span><span class="sxs-lookup"><span data-stu-id="6b750-110">Requirements</span></span>

<span data-ttu-id="6b750-111">このサンプルを実行するには、PowerShell 4.0 以降が動作しているコンピューターが必要です。</span><span class="sxs-lookup"><span data-stu-id="6b750-111">To run this example, you will need a computer running PowerShell 4.0 or later.</span></span>

## <a name="write-the-configuration"></a><span data-ttu-id="6b750-112">構成を記述する</span><span class="sxs-lookup"><span data-stu-id="6b750-112">Write the configuration</span></span>

<span data-ttu-id="6b750-113">DSC [構成](configurations.md)は、1 つ以上のターゲット コンピューター (ノード) を構成する方法を定義する特別な PowerShell 関数です。</span><span class="sxs-lookup"><span data-stu-id="6b750-113">A DSC [Configuration](configurations.md) is a special PowerShell function that defines how you want to configure one or more target computers (Nodes).</span></span>

<span data-ttu-id="6b750-114">PowerShell ISE、またはその他の PowerShell エディターで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6b750-114">In the PowerShell ISE, or other PowerShell editor, type the following:</span></span>

```powershell
Configuration HelloWorld {

    # Import the module that contains the File resource.
    Import-DscResource -ModuleName PsDesiredStateConfiguration

    # The Node statement specifies which targets to compile MOF files for, when this configuration is executed.
    Node 'localhost' {

        # The File resource can ensure the state of files, or copy them from a source to a destination with persistent updates.
        File HelloWorld {
            DestinationPath = "C:\Temp\HelloWorld.txt"
            Ensure = "Present"
            Contents   = "Hello World from DSC!"
        }
    }
}
```

> <span data-ttu-id="6b750-115">[重要] 多くの DSC リソースを同じ構成で操作できるように複数のモジュールをインポートすることが必要な、より高度なシナリオの場合は、`Import-DscResource` を使って各モジュールを別々の行に配置するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="6b750-115">!Important In more advanced scenarios where multiple modules need to be imported so you can work with many DSC Resources in the same configuration, make sure to put each module in a separate line using `Import-DscResource`.</span></span>
> <span data-ttu-id="6b750-116">こちらの方がソース管理で管理しやすく、また Azure State Configuration の DSC を使用する場合に必要になります。</span><span class="sxs-lookup"><span data-stu-id="6b750-116">This is easier to maintain in source control and required when working with DSC in Azure State Configuration.</span></span>
>
> ```powershell
>  Configuration HelloWorld {
>
>   # Import the module that contains the File resource.
>   Import-DscResource -ModuleName PsDesiredStateConfiguration
>   Import-DscResource -ModuleName xWebAdministration
>
> ```

<span data-ttu-id="6b750-117">ファイルを "HelloWorld.ps1" という名前で保存します。</span><span class="sxs-lookup"><span data-stu-id="6b750-117">Save the file as "HelloWorld.ps1".</span></span>

<span data-ttu-id="6b750-118">構成を定義するのは、関数の定義と似ています。</span><span class="sxs-lookup"><span data-stu-id="6b750-118">Defining a Configuration is like defining a Function.</span></span> <span data-ttu-id="6b750-119">`localhost` 場合、**ノード**ブロックは構成するターゲット ノードを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b750-119">The **Node** block specifies the target node to be configured, in this case `localhost`.</span></span>

<span data-ttu-id="6b750-120">構成では、1 つの[リソース](../resources/resources.md) (`File` リソース) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="6b750-120">The configuration calls one [resources](../resources/resources.md), the `File` resource.</span></span> <span data-ttu-id="6b750-121">リソースは、ターゲット ノードが構成によって定義された状態になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="6b750-121">Resources do the work of ensuring that the target node is in the state defined by the configuration.</span></span>

## <a name="compile-the-configuration"></a><span data-ttu-id="6b750-122">構成のコンパイル</span><span class="sxs-lookup"><span data-stu-id="6b750-122">Compile the configuration</span></span>

<span data-ttu-id="6b750-123">DSC 構成をノードに適用するには、最初にコンパイルを行い、MOF ファイルを出力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b750-123">For a DSC configuration to be applied to a node, it must first be compiled into a MOF file.</span></span>
<span data-ttu-id="6b750-124">関数のように構成を実行すると、`Node` ブロックで定義されたノードごとに、".mof" ファイルを 1 つコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="6b750-124">Running the configuration, like a function, will compile one ".mof" file for every Node defined by the `Node` block.</span></span>
<span data-ttu-id="6b750-125">構成を実行するために、"HelloWorld.ps1" スクリプトを現在の範囲に*ドット ソース*で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b750-125">In order to run the configuration, you need to *dot source* your "HelloWorld.ps1" script into the current scope.</span></span>
<span data-ttu-id="6b750-126">詳細については、[スクリプト](/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-6#script-scope-and-dot-sourcing)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b750-126">For more information, see [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-6#script-scope-and-dot-sourcing).</span></span>

<!-- markdownlint-disable MD038 -->
<span data-ttu-id="6b750-127">`. ` (ドット、スペース) の後に保存した場所のパスを入力することで、"HelloWorld.ps1" スクリプトを "*ドット ソース*" で使用します。</span><span class="sxs-lookup"><span data-stu-id="6b750-127">*Dot source* your "HelloWorld.ps1" script by typing in the path where you stored it, after the `. ` (dot, space).</span></span> <span data-ttu-id="6b750-128">その後、関数のように呼び出すことで、構成を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="6b750-128">You may then, run your configuration by calling it like a Function.</span></span>
<!-- markdownlint-enable MD038 -->

```powershell
. C:\Scripts\HelloWorld.ps1
HelloWorld
```

<span data-ttu-id="6b750-129">これにより、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="6b750-129">This generates the following output:</span></span>

```output
Directory: C:\Scripts\HelloWorld


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

## <a name="apply-the-configuration"></a><span data-ttu-id="6b750-130">構成を適用する</span><span class="sxs-lookup"><span data-stu-id="6b750-130">Apply the configuration</span></span>

<span data-ttu-id="6b750-131">コンパイル済みの MOF があるため、[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットを呼び出すことで、ターゲット ノード (今回の場合はローカル コンピューター) に構成を適用できます。</span><span class="sxs-lookup"><span data-stu-id="6b750-131">Now that you have the compiled MOF, you can apply the configuration to the target node (in this case, the local computer) by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

<span data-ttu-id="6b750-132">`Start-DscConfiguration` コマンドレットから[ローカル構成マネージャー (LCM)](../managing-nodes/metaConfig.md) (DSC のエンジン) に対して構成の適用を指示します。</span><span class="sxs-lookup"><span data-stu-id="6b750-132">The `Start-DscConfiguration` cmdlet tells the [Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md), the engine of DSC, to apply the configuration.</span></span>
<span data-ttu-id="6b750-133">LCM はDSC リソースを呼び出し、構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="6b750-133">The LCM does the work of calling the DSC resources to apply the configuration.</span></span>

<span data-ttu-id="6b750-134">以下のコードを使用して、`Start-DSCConfiguration` コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="6b750-134">Use the code below to execute the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="6b750-135">"localhost.mof" が保存されているディレクトリ パスを `-Path` パラメーターに指定します。</span><span class="sxs-lookup"><span data-stu-id="6b750-135">Specify the directory path where your "localhost.mof" is stored to the `-Path` parameter.</span></span> <span data-ttu-id="6b750-136">`Start-DSCConfiguration` コマンドレットは、任意の "\<computername\>.mof" ファイルに対して指定されたディレクトリが対象になります。</span><span class="sxs-lookup"><span data-stu-id="6b750-136">The `Start-DSCConfiguration` cmdlet looks through the directory specified for any "\<computername\>.mof" files.</span></span> <span data-ttu-id="6b750-137">`Start-DSCConfiguration` コマンドレットでは、見つかった各 ".mof" ファイルを、ファイル名 ("localhost"、"server01"、"dc-02" など) で指定されたコンピューター名に適用しようとします。</span><span class="sxs-lookup"><span data-stu-id="6b750-137">The `Start-DSCConfiguration` cmdlet attempts to apply each ".mof" file it finds to the computername specified by the filename ("localhost", "server01", "dc-02", etc.).</span></span>

> [!NOTE]
> <span data-ttu-id="6b750-138">`-Wait` パラメーターが指定されていない場合、`Start-DSCConfiguration` では操作を実行するためにバックグラウンド ジョブが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6b750-138">If the `-Wait` parameter is not specified, `Start-DSCConfiguration` creates a background job to perform the operation.</span></span> <span data-ttu-id="6b750-139">`-Verbose` パラメーターを指定すると、操作の**詳細**出力を確認できます。</span><span class="sxs-lookup"><span data-stu-id="6b750-139">Specifying the `-Verbose` parameter allows you to watch the **Verbose** output of the operation.</span></span> <span data-ttu-id="6b750-140">`-Wait` および `-Verbose` は、どちらも省略可能なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="6b750-140">`-Wait`, and `-Verbose` are both optional parameters.</span></span>

```powershell
Start-DscConfiguration -Path C:\Scripts\HelloWorld -Verbose -Wait
```

## <a name="test-the-configuration"></a><span data-ttu-id="6b750-141">構成をテストする</span><span class="sxs-lookup"><span data-stu-id="6b750-141">Test the configuration</span></span>

<span data-ttu-id="6b750-142">`Start-DSCConfiguration` コマンドレットが完了すると、指定した場所に "HelloWorld.txt" ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b750-142">Once the `Start-DSCConfiguration` cmdlet is complete, you should see a "HelloWorld.txt" file in the location you specified.</span></span> <span data-ttu-id="6b750-143">[Get-Content](/powershell/module/microsoft.powershell.management/get-content) コマンドレットを使用して、コンテンツを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6b750-143">You can verify the contents with the [Get-Content](/powershell/module/microsoft.powershell.management/get-content) cmdlet.</span></span>

<span data-ttu-id="6b750-144">[Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) を使用して、現在の状態を*テスト*することもできます。</span><span class="sxs-lookup"><span data-stu-id="6b750-144">You can also *test* the current status using [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span></span>

<span data-ttu-id="6b750-145">現在、ノードが適用された構成に準拠している場合、出力は "True" になります。</span><span class="sxs-lookup"><span data-stu-id="6b750-145">The output should be "True" if the Node is currently compliant with the applied Configuration.</span></span>

```powershell
Test-DSCConfiguration
```

```output
True
```

```powershell
Get-Content -Path C:\Temp\HelloWorld.txt
```

```output
Hello World from DSC!
```

## <a name="re-applying-the-configuration"></a><span data-ttu-id="6b750-146">構成を再適用する</span><span class="sxs-lookup"><span data-stu-id="6b750-146">Re-applying the configuration</span></span>

<span data-ttu-id="6b750-147">もう一度構成が適用されることを確認するには、自分の構成で作成されたテキスト ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b750-147">To see your configuration get applied again, you can remove the text file created by your Configuration.</span></span> <span data-ttu-id="6b750-148">`Start-DSCConfiguration` コマンドレットを `-UseExisting` パラメーターを指定して使用します。</span><span class="sxs-lookup"><span data-stu-id="6b750-148">The use the `Start-DSCConfiguration` cmdlet with the `-UseExisting` parameter.</span></span> <span data-ttu-id="6b750-149">`-UseExisting` パラメーターによって、`Start-DSCConfiguration` に対して、最後に正常に適用された構成を表す、"current.mof" を再適用するように指示されます。</span><span class="sxs-lookup"><span data-stu-id="6b750-149">The `-UseExisting` parameter instructs `Start-DSCConfiguration` to re-apply the "current.mof" file, which represents the most recently successfully applied configuration.</span></span>

```powershell
Remove-Item -Path C:\Temp\HelloWorld.txt
```

## <a name="next-steps"></a><span data-ttu-id="6b750-150">次のステップ</span><span class="sxs-lookup"><span data-stu-id="6b750-150">Next steps</span></span>

- <span data-ttu-id="6b750-151">「[DSC 構成](configurations.md)」で DSC 構成の詳細を確認する。</span><span class="sxs-lookup"><span data-stu-id="6b750-151">Find out more about DSC configurations at [DSC configurations](configurations.md).</span></span>
- <span data-ttu-id="6b750-152">「[DSC リソース](../resources/resources.md)」で利用可能な DSC リソースとカスタム DSC リソースの作成方法を確認する。</span><span class="sxs-lookup"><span data-stu-id="6b750-152">See what DSC resources are available, and how to create custom DSC resources at [DSC resources](../resources/resources.md).</span></span>
- <span data-ttu-id="6b750-153">「[PowerShell ギャラリー](https://www.powershellgallery.com/)」で DSC の構成とリソースを検索する。</span><span class="sxs-lookup"><span data-stu-id="6b750-153">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>
