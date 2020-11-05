---
ms.date: 06/22/2020
keywords: dsc, powershell, 構成, サービス, セットアップ
title: 構成の作成、コンパイル、適用
description: この演習では、DSC の構成の作成と適用について最初から最後まで説明します。 次の例では、非常に単純な構成を作成して適用する方法について学習します
ms.openlocfilehash: f173fe0dc6cd73e2b49bb8c44a9ee1a53eab475f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92645025"
---
# <a name="write-compile-and-apply-a-configuration"></a><span data-ttu-id="c0aec-105">構成の作成、コンパイル、適用</span><span class="sxs-lookup"><span data-stu-id="c0aec-105">Write, Compile, and Apply a Configuration</span></span>

> <span data-ttu-id="c0aec-106">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="c0aec-106">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="c0aec-107">この演習では、Desired State Configuration (DSC) の構成の作成と適用について最初から最後まで説明します。</span><span class="sxs-lookup"><span data-stu-id="c0aec-107">This exercise walks through creating and applying a Desired State Configuration (DSC) configuration from start to finish.</span></span> <span data-ttu-id="c0aec-108">次の例では、非常に単純な構成を作成して適用する方法について学習します。</span><span class="sxs-lookup"><span data-stu-id="c0aec-108">In the following example, you will learn how to write and apply a very simple Configuration.</span></span> <span data-ttu-id="c0aec-109">この構成により、"HelloWorld.txt" ファイルがローカル コンピューターに存在していることが確保されます。</span><span class="sxs-lookup"><span data-stu-id="c0aec-109">The Configuration will ensure a "HelloWorld.txt" file exists on your local machine.</span></span>
<span data-ttu-id="c0aec-110">ファイルを削除する場合は、次に更新されるときに DSC によってファイルが再作成されます。</span><span class="sxs-lookup"><span data-stu-id="c0aec-110">If you delete the file, DSC will recreate it the next time it updates.</span></span>

<span data-ttu-id="c0aec-111">DSC の概要としくみついては、[開発者向けの Desired State Configuration の概要](../overview/overview.md)に関するページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c0aec-111">For an overview of what DSC is and how it works, see [Desired State Configuration Overview for Developers](../overview/overview.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="c0aec-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="c0aec-112">Requirements</span></span>

<span data-ttu-id="c0aec-113">このサンプルを実行するには、PowerShell 4.0 以降が動作しているコンピューターが必要です。</span><span class="sxs-lookup"><span data-stu-id="c0aec-113">To run this example, you will need a computer running PowerShell 4.0 or later.</span></span>

## <a name="write-the-configuration"></a><span data-ttu-id="c0aec-114">構成を記述する</span><span class="sxs-lookup"><span data-stu-id="c0aec-114">Write the configuration</span></span>

<span data-ttu-id="c0aec-115">DSC [構成](configurations.md)は、1 つ以上のターゲット コンピューター (ノード) を構成する方法を定義する特別な PowerShell 関数です。</span><span class="sxs-lookup"><span data-stu-id="c0aec-115">A DSC [Configuration](configurations.md) is a special PowerShell function that defines how you want to configure one or more target computers (Nodes).</span></span>

<span data-ttu-id="c0aec-116">PowerShell ISE、またはその他の PowerShell エディターで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c0aec-116">In the PowerShell ISE, or other PowerShell editor, type the following:</span></span>

```powershell
Configuration HelloWorld {

    # Import the module that contains the File resource.
    Import-DscResource -ModuleName PsDesiredStateConfiguration

    # The Node statement specifies which targets to compile MOF files for, when
    # this configuration is executed.
    Node 'localhost' {

        # The File resource can ensure the state of files, or copy them from a
        # source to a destination with persistent updates.
        File HelloWorld {
            DestinationPath = "C:\Temp\HelloWorld.txt"
            Ensure = "Present"
            Contents   = "Hello World from DSC!"
        }
    }
}
```

> [!IMPORTANT]
> <span data-ttu-id="c0aec-117">多くの DSC リソースを同じ構成で操作できるように複数のモジュールをインポートすることが必要な、より高度なシナリオの場合は、`Import-DscResource` を使って各モジュールを別々の行に配置するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="c0aec-117">In more advanced scenarios where multiple modules need to be imported so you can work with many DSC Resources in the same configuration, make sure to put each module in a separate line using `Import-DscResource`.</span></span> <span data-ttu-id="c0aec-118">こちらの方がソース管理で管理しやすく、また Azure State Configuration の DSC を使用する場合に必要になります。</span><span class="sxs-lookup"><span data-stu-id="c0aec-118">This is easier to maintain in source control and required when working with DSC in Azure State Configuration.</span></span>
>
> ```powershell
>  Configuration HelloWorld {
>
>   # Import the module that contains the File resource.
>   Import-DscResource -ModuleName PsDesiredStateConfiguration
>   Import-DscResource -ModuleName xWebAdministration
>
> ```

<span data-ttu-id="c0aec-119">ファイルを "HelloWorld.ps1" という名前で保存します。</span><span class="sxs-lookup"><span data-stu-id="c0aec-119">Save the file as "HelloWorld.ps1".</span></span>

<span data-ttu-id="c0aec-120">構成を定義するのは、関数の定義と似ています。</span><span class="sxs-lookup"><span data-stu-id="c0aec-120">Defining a Configuration is like defining a Function.</span></span> <span data-ttu-id="c0aec-121">`localhost` 場合、 **ノード** ブロックは構成するターゲット ノードを指定します。</span><span class="sxs-lookup"><span data-stu-id="c0aec-121">The **Node** block specifies the target node to be configured, in this case `localhost`.</span></span>

<span data-ttu-id="c0aec-122">構成では、1 つの[リソース](../resources/resources.md) (`File` リソース) を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c0aec-122">The configuration calls one [resources](../resources/resources.md), the `File` resource.</span></span> <span data-ttu-id="c0aec-123">リソースは、ターゲット ノードが構成によって定義された状態になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="c0aec-123">Resources do the work of ensuring that the target node is in the state defined by the configuration.</span></span>

## <a name="compile-the-configuration"></a><span data-ttu-id="c0aec-124">構成のコンパイル</span><span class="sxs-lookup"><span data-stu-id="c0aec-124">Compile the configuration</span></span>

<span data-ttu-id="c0aec-125">DSC 構成をノードに適用するには、最初にコンパイルを行い、MOF ファイルを出力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0aec-125">For a DSC configuration to be applied to a node, it must first be compiled into a MOF file.</span></span> <span data-ttu-id="c0aec-126">関数のように構成を実行すると、`Node` ブロックで定義されたノードごとに、`.mof` ファイルが 1 つコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="c0aec-126">Running the configuration, like a function, will compile one `.mof` file for every Node defined by the `Node` block.</span></span> <span data-ttu-id="c0aec-127">構成を実行するには、現在の範囲で `HelloWorld.ps1` スクリプトを " _ドット ソース_ " で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0aec-127">In order to run the configuration, you need to _dot source_ your `HelloWorld.ps1` script into the current scope.</span></span> <span data-ttu-id="c0aec-128">詳細については、[スクリプト](/powershell/module/microsoft.powershell.core/about/about_scripts#script-scope-and-dot-sourcing)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0aec-128">For more information, see [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts#script-scope-and-dot-sourcing).</span></span>

<!-- markdownlint-disable MD038 -->
<span data-ttu-id="c0aec-129">`HelloWorld.ps1` スクリプトを " _ドット ソース_ " で実行するには、`. ` (ドット、スペース) の後で、それを保存した場所のパス内に入力します。</span><span class="sxs-lookup"><span data-stu-id="c0aec-129">_Dot source_ your `HelloWorld.ps1` script by typing in the path where you stored it, after the `. ` (dot, space).</span></span> <span data-ttu-id="c0aec-130">その後、関数のように呼び出すことで、構成を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="c0aec-130">You may then, run your configuration by calling it like a function.</span></span> <span data-ttu-id="c0aec-131">また、スクリプトの一番下にある構成関数を呼び出すと、ドット ソースで実行する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="c0aec-131">You could also invoke the configuration function at the bottom of the script so that you don't need to dot-source.</span></span>
<!-- markdownlint-enable MD038 -->

```powershell
. C:\Scripts\HelloWorld.ps1
HelloWorld
```

<span data-ttu-id="c0aec-132">これにより、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c0aec-132">This generates the following output:</span></span>

```Output
Directory: C:\Scripts\HelloWorld


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

## <a name="apply-the-configuration"></a><span data-ttu-id="c0aec-133">構成を適用する</span><span class="sxs-lookup"><span data-stu-id="c0aec-133">Apply the configuration</span></span>

<span data-ttu-id="c0aec-134">コンパイル済みの MOF があるため、[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットを呼び出すことで、ターゲット ノード (今回の場合はローカル コンピューター) に構成を適用できます。</span><span class="sxs-lookup"><span data-stu-id="c0aec-134">Now that you have the compiled MOF, you can apply the configuration to the target node (in this case, the local computer) by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

<span data-ttu-id="c0aec-135">`Start-DscConfiguration` コマンドレットから[ローカル構成マネージャー (LCM)](../managing-nodes/metaConfig.md) (DSC のエンジン) に対して構成の適用を指示します。</span><span class="sxs-lookup"><span data-stu-id="c0aec-135">The `Start-DscConfiguration` cmdlet tells the [Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md), the engine of DSC, to apply the configuration.</span></span> <span data-ttu-id="c0aec-136">LCM はDSC リソースを呼び出し、構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="c0aec-136">The LCM does the work of calling the DSC resources to apply the configuration.</span></span>

<span data-ttu-id="c0aec-137">以下のコードを使用して、`Start-DSCConfiguration` コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="c0aec-137">Use the code below to execute the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="c0aec-138">`localhost.mof` が保存されているディレクトリ パスを **Path** パラメーターに指定します。</span><span class="sxs-lookup"><span data-stu-id="c0aec-138">Specify the directory path where your `localhost.mof` is stored to the **Path** parameter.</span></span> <span data-ttu-id="c0aec-139">`Start-DSCConfiguration` コマンドレットは、任意の `<computername>.mof` ファイルに対して指定されたディレクトリが対象になります。</span><span class="sxs-lookup"><span data-stu-id="c0aec-139">The `Start-DSCConfiguration` cmdlet looks through the directory specified for any `<computername>.mof` files.</span></span> <span data-ttu-id="c0aec-140">`Start-DSCConfiguration` コマンドレットでは、見つかった各 `.mof` ファイルを、ファイル名 ("localhost"、"server01"、"dc-02" など) で指定された `computername` に適用する試みが行われます。</span><span class="sxs-lookup"><span data-stu-id="c0aec-140">The `Start-DSCConfiguration` cmdlet attempts to apply each `.mof` file it finds to the `computername` specified by the filename ("localhost", "server01", "dc-02", etc.).</span></span>

> [!NOTE]
> <span data-ttu-id="c0aec-141">`-Wait` パラメーターが指定されていない場合、`Start-DSCConfiguration` では操作を実行するためにバックグラウンド ジョブが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c0aec-141">If the `-Wait` parameter is not specified, `Start-DSCConfiguration` creates a background job to perform the operation.</span></span> <span data-ttu-id="c0aec-142">`-Verbose` パラメーターを指定すると、操作の **詳細** 出力を確認できます。</span><span class="sxs-lookup"><span data-stu-id="c0aec-142">Specifying the `-Verbose` parameter allows you to watch the **Verbose** output of the operation.</span></span> <span data-ttu-id="c0aec-143">`-Wait` および `-Verbose` は、どちらも省略可能なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="c0aec-143">`-Wait`, and `-Verbose` are both optional parameters.</span></span>

```powershell
Start-DscConfiguration -Path C:\Scripts\HelloWorld -Verbose -Wait
```

## <a name="test-the-configuration"></a><span data-ttu-id="c0aec-144">構成をテストする</span><span class="sxs-lookup"><span data-stu-id="c0aec-144">Test the configuration</span></span>

<span data-ttu-id="c0aec-145">`Start-DSCConfiguration` コマンドレットが完了すると、指定した場所に `HelloWorld.txt` ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c0aec-145">Once the `Start-DSCConfiguration` cmdlet is complete, you should see a `HelloWorld.txt` file in the location you specified.</span></span> <span data-ttu-id="c0aec-146">[Get-Content](/powershell/module/microsoft.powershell.management/get-content) コマンドレットを使用して、コンテンツを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c0aec-146">You can verify the contents with the [Get-Content](/powershell/module/microsoft.powershell.management/get-content) cmdlet.</span></span>

<span data-ttu-id="c0aec-147">[Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) を使用して、現在の状態を _テスト_ することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0aec-147">You can also _test_ the current status using [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span></span>

<span data-ttu-id="c0aec-148">現在、ノードが適用された構成に準拠している場合、出力は `True` になります。</span><span class="sxs-lookup"><span data-stu-id="c0aec-148">The output should be `True` if the Node is currently compliant with the applied Configuration.</span></span>

```powershell
Test-DSCConfiguration
```

```Output
True
```

```powershell
Get-Content -Path C:\Temp\HelloWorld.txt
```

```Output
Hello World from DSC!
```

## <a name="re-applying-the-configuration"></a><span data-ttu-id="c0aec-149">構成を再適用する</span><span class="sxs-lookup"><span data-stu-id="c0aec-149">Re-applying the configuration</span></span>

<span data-ttu-id="c0aec-150">もう一度構成が適用されることを確認するには、自分の構成で作成されたテキスト ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="c0aec-150">To see your configuration get applied again, you can remove the text file created by your Configuration.</span></span> <span data-ttu-id="c0aec-151">`Start-DSCConfiguration` コマンドレットを `-UseExisting` パラメーターを指定して使用します。</span><span class="sxs-lookup"><span data-stu-id="c0aec-151">The use the `Start-DSCConfiguration` cmdlet with the `-UseExisting` parameter.</span></span> <span data-ttu-id="c0aec-152">`-UseExisting` パラメーターによって、`Start-DSCConfiguration` に対して、最後に正常に適用された構成を表す、"current.mof" を再適用するように指示されます。</span><span class="sxs-lookup"><span data-stu-id="c0aec-152">The `-UseExisting` parameter instructs `Start-DSCConfiguration` to re-apply the "current.mof" file, which represents the most recently successfully applied configuration.</span></span>

```powershell
Remove-Item -Path C:\Temp\HelloWorld.txt
```

## <a name="next-steps"></a><span data-ttu-id="c0aec-153">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c0aec-153">Next steps</span></span>

- <span data-ttu-id="c0aec-154">「[DSC 構成](configurations.md)」で DSC 構成の詳細を確認する。</span><span class="sxs-lookup"><span data-stu-id="c0aec-154">Find out more about DSC configurations at [DSC configurations](configurations.md).</span></span>
- <span data-ttu-id="c0aec-155">「[DSC リソース](../resources/resources.md)」で利用可能な DSC リソースとカスタム DSC リソースの作成方法を確認する。</span><span class="sxs-lookup"><span data-stu-id="c0aec-155">See what DSC resources are available, and how to create custom DSC resources at [DSC resources](../resources/resources.md).</span></span>
- <span data-ttu-id="c0aec-156">「[PowerShell ギャラリー](https://www.powershellgallery.com/)」で DSC の構成とリソースを検索する。</span><span class="sxs-lookup"><span data-stu-id="c0aec-156">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>
