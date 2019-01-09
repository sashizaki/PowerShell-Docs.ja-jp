---
ms.date: 12/12/2018
keywords: dsc, powershell, 構成、サービス, セットアップ
title: 構成の作成、コンパイル、適用
ms.openlocfilehash: fa4d98fd12202439ba7025fd8af3fa398653ca05
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402349"
---
> <span data-ttu-id="fad13-103">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="fad13-103">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

# <a name="write-compile-and-apply-a-configuration"></a><span data-ttu-id="fad13-104">構成の作成、コンパイル、適用</span><span class="sxs-lookup"><span data-stu-id="fad13-104">Write, Compile, and Apply a Configuration</span></span>

<span data-ttu-id="fad13-105">この演習では、Desired State Configuration (DSC) の構成の作成と適用について最初から最後まで説明します。</span><span class="sxs-lookup"><span data-stu-id="fad13-105">This exercise walks through creating and applying a Desired State Configuration (DSC) configuration from start to finish.</span></span>
<span data-ttu-id="fad13-106">次の例では、書き込みし、非常に単純な構成を適用する方法を学びます。</span><span class="sxs-lookup"><span data-stu-id="fad13-106">In the following example, you will learn how to write and apply a very simple Configuration.</span></span> <span data-ttu-id="fad13-107">構成が"HelloWorld.txt"ファイルがローカル コンピューターに存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="fad13-107">The Configuration will ensure a "HelloWorld.txt" file exists on your local machine.</span></span> <span data-ttu-id="fad13-108">ファイルを削除する場合は、DSC ことに、次回の更新は再作成します。</span><span class="sxs-lookup"><span data-stu-id="fad13-108">If you delete the file, DSC will recreate it the next time it updates.</span></span>

<span data-ttu-id="fad13-109">DSC とそのしくみの概要については、次を参照してください。 [Desired State Configuration の概要開発者向け](../overview/overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="fad13-109">For an overview of what DSC is and how it works, see [Desired State Configuration Overview for Developers](../overview/overview.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="fad13-110">要件</span><span class="sxs-lookup"><span data-stu-id="fad13-110">Requirements</span></span>

<span data-ttu-id="fad13-111">この例を実行するには、PowerShell 4.0 またはそれ以降を実行しているコンピューターが必要です。</span><span class="sxs-lookup"><span data-stu-id="fad13-111">To run this example, you will need a computer running PowerShell 4.0 or later.</span></span>

## <a name="write-the-configuration"></a><span data-ttu-id="fad13-112">構成を記述する</span><span class="sxs-lookup"><span data-stu-id="fad13-112">Write the configuration</span></span>

<span data-ttu-id="fad13-113">DSC [構成](configurations.md)は、1 つ以上のターゲット コンピューター (ノード) を構成する方法を定義する特別な PowerShell 関数です。</span><span class="sxs-lookup"><span data-stu-id="fad13-113">A DSC [Configuration](configurations.md) is a special PowerShell function that defines how you want to configure one or more target computers (Nodes).</span></span>

<span data-ttu-id="fad13-114">PowerShell ISE で、またはその他の PowerShell エディターで、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="fad13-114">In the PowerShell ISE, or other PowerShell editor, type the following:</span></span>

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

<span data-ttu-id="fad13-115">"HelloWorld.ps1"として保存します。</span><span class="sxs-lookup"><span data-stu-id="fad13-115">Save the file as "HelloWorld.ps1".</span></span>

<span data-ttu-id="fad13-116">関数を定義するようには、構成の定義です。</span><span class="sxs-lookup"><span data-stu-id="fad13-116">Defining a Configuration is like defining a Function.</span></span> <span data-ttu-id="fad13-117">`localhost` 場合、**ノード**ブロックは構成するターゲット ノードを指定します。</span><span class="sxs-lookup"><span data-stu-id="fad13-117">The **Node** block specifies the target node to be configured, in this case `localhost`.</span></span>

<span data-ttu-id="fad13-118">構成では、1 つを呼び出す[リソース](../resources/resources.md)、`File`リソース。</span><span class="sxs-lookup"><span data-stu-id="fad13-118">The configuration calls one [resources](../resources/resources.md), the `File` resource.</span></span> <span data-ttu-id="fad13-119">リソースは、ターゲット ノードが構成によって定義された状態になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="fad13-119">Resources do the work of ensuring that the target node is in the state defined by the configuration.</span></span>

## <a name="compile-the-configuration"></a><span data-ttu-id="fad13-120">構成をコンパイルする</span><span class="sxs-lookup"><span data-stu-id="fad13-120">Compile the configuration</span></span>

<span data-ttu-id="fad13-121">DSC 構成をノードに適用するには、最初にコンパイルを行い、MOF ファイルを出力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fad13-121">For a DSC configuration to be applied to a node, it must first be compiled into a MOF file.</span></span>
<span data-ttu-id="fad13-122">によって定義されたすべてのノードの 1 つの".mof"ファイルをコンパイルは、関数のように、構成を実行している、`Node`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="fad13-122">Running the configuration, like a function, will compile one ".mof" file for every Node defined by the `Node` block.</span></span>
<span data-ttu-id="fad13-123">構成を実行するのには、する必要があります*ドット ソース*現在のスコープに"HelloWorld.ps1"スクリプト。</span><span class="sxs-lookup"><span data-stu-id="fad13-123">In order to run the configuration, you need to *dot source* your "HelloWorld.ps1" script into the current scope.</span></span>
<span data-ttu-id="fad13-124">詳細については、次を参照してください。 [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-6#script-scope-and-dot-sourcing)します。</span><span class="sxs-lookup"><span data-stu-id="fad13-124">For more information, see [about_Scripts](/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-6#script-scope-and-dot-sourcing).</span></span>

<span data-ttu-id="fad13-125">*ドット ソース*"HelloWorld.ps1"スクリプトの後のそれを格納場所のパスを入力して、 `. ` (ドット、領域)。</span><span class="sxs-lookup"><span data-stu-id="fad13-125">*Dot source* your "HelloWorld.ps1" script by typing in the path where you stored it, after the `. ` (dot, space).</span></span> <span data-ttu-id="fad13-126">次に、可能性があります関数のように呼び出して、構成を実行します。</span><span class="sxs-lookup"><span data-stu-id="fad13-126">You may then, run your configuration by calling it like a Function.</span></span>

```powershell
. C:\Scripts\WebsiteTest.ps1
HelloWolrd
```

<span data-ttu-id="fad13-127">これにより、次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="fad13-127">This generates the following output:</span></span>

```output
Directory: C:\Scripts\HelloWorld


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

## <a name="apply-the-configuration"></a><span data-ttu-id="fad13-128">構成を適用する</span><span class="sxs-lookup"><span data-stu-id="fad13-128">Apply the configuration</span></span>

<span data-ttu-id="fad13-129">コンパイル済みの MOF があるため、[Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットを呼び出すことで、ターゲット ノード (今回の場合はローカル コンピューター) に構成を適用できます。</span><span class="sxs-lookup"><span data-stu-id="fad13-129">Now that you have the compiled MOF, you can apply the configuration to the target node (in this case, the local computer) by calling the [Start-DscConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span>

<span data-ttu-id="fad13-130">`Start-DscConfiguration`コマンドレットの指示、[ローカル構成マネージャー (LCM)](../managing-nodes/metaConfig.md)構成を適用する、DSC のエンジンです。</span><span class="sxs-lookup"><span data-stu-id="fad13-130">The `Start-DscConfiguration` cmdlet tells the [Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md), the engine of DSC, to apply the configuration.</span></span>
<span data-ttu-id="fad13-131">LCM はDSC リソースを呼び出し、構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="fad13-131">The LCM does the work of calling the DSC resources to apply the configuration.</span></span>

<span data-ttu-id="fad13-132">次のコードを使用して実行する、`Start-DSCConfiguration`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="fad13-132">Use the code below to execute the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="fad13-133">"Localhost.mof"を格納する場所のディレクトリ パスを指定、`-Path`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="fad13-133">Specify the directory path where your "localhost.mof" is stored to the `-Path` parameter.</span></span> <span data-ttu-id="fad13-134">`Start-DSCConfiguration`コマンドレットは、いずれかに指定されたディレクトリを検索"\<computername\>.mof"ファイル。</span><span class="sxs-lookup"><span data-stu-id="fad13-134">The `Start-DSCConfiguration` cmdlet looks through the directory specified for any "\<computername\>.mof" files.</span></span> <span data-ttu-id="fad13-135">`Start-DSCConfiguration`コマンドレットはファイル名 ("localhost"、"server01"、「dc 02」など) で指定されたコンピューター名に見つけた各".mof"ファイルを適用しようとしています。</span><span class="sxs-lookup"><span data-stu-id="fad13-135">The `Start-DSCConfiguration` cmdlet attempts to apply each ".mof" file it finds to the computername specified by the filename ("localhost", "server01", "dc-02", etc.).</span></span>

> [!NOTE]
> <span data-ttu-id="fad13-136">場合、`-Wait`パラメーターが指定されていない`Start-DSCConfiguration`操作を実行するバック グラウンド ジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="fad13-136">If the `-Wait` parameter is not specified, `Start-DSCConfiguration` creates a background job to perform the operation.</span></span> <span data-ttu-id="fad13-137">指定する、`-Verbose`パラメーターを使用すると、ウォッチ、 **Verbose**が操作の出力。</span><span class="sxs-lookup"><span data-stu-id="fad13-137">Specifying the `-Verbose` parameter allows you to watch the **Verbose** output of the operation.</span></span> <span data-ttu-id="fad13-138">`-Wait`、および`-Verbose`は両方の省略可能なパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="fad13-138">`-Wait`, and `-Verbose` are both optional parameters.</span></span>

```powershell
Start-DscConfiguration -Path C:\Scripts\HelloWorld -Verbose -Wait
```

## <a name="test-the-configuration"></a><span data-ttu-id="fad13-139">構成をテストする</span><span class="sxs-lookup"><span data-stu-id="fad13-139">Test the configuration</span></span>

<span data-ttu-id="fad13-140">1 回、`Start-DSCConfiguration`コマンドレットが完了したら、指定した場所にある"HelloWorld.txt"ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fad13-140">Once the `Start-DSCConfiguration` cmdlet is complete, you should see a "HelloWorld.txt" file in the location you specified.</span></span> <span data-ttu-id="fad13-141">内容を確認することができます、 [Get-content](/powershell/module/microsoft.powershell.management/get-content)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="fad13-141">You can verify the contents with the [Get-Content](/powershell/module/microsoft.powershell.management/get-content) cmdlet.</span></span>

<span data-ttu-id="fad13-142">できます*テスト*を使用して現在の状態[Test-dscconfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)します。</span><span class="sxs-lookup"><span data-stu-id="fad13-142">You can also *test* the current status using [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span></span>

<span data-ttu-id="fad13-143">出力は、ノードが現在適用されている構成で準拠している場合は、"True"にすることがあります。</span><span class="sxs-lookup"><span data-stu-id="fad13-143">The output should be "True" if the Node is currently compliant with the applied Configuration.</span></span>

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

## <a name="re-applying-the-configuration"></a><span data-ttu-id="fad13-144">構成を再適用します。</span><span class="sxs-lookup"><span data-stu-id="fad13-144">Re-applying the configuration</span></span>

<span data-ttu-id="fad13-145">もう一度適用される構成を表示するには、構成で作成されたテキスト ファイルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="fad13-145">To see your configuration get applied again, you can remove the text file created by your Configuration.</span></span> <span data-ttu-id="fad13-146">使用して、`Start-DSCConfiguration`コマンドレットと、`-UseExisting`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="fad13-146">The use the `Start-DSCConfiguration` cmdlet with the `-UseExisting` parameter.</span></span> <span data-ttu-id="fad13-147">`-UseExisting`パラメーター `Start-DSCConfiguration` "current.mof"ファイルを再適用するを表す最も最近正常に構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="fad13-147">The `-UseExisting` parameter instructs `Start-DSCConfiguration` to re-apply the "current.mof" file, which represents the most recently successfully applied configuration.</span></span>

```powershell
Remove-Item -Path C:\Temp\HelloWorld.txt
```

## <a name="next-steps"></a><span data-ttu-id="fad13-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="fad13-148">Next steps</span></span>

- <span data-ttu-id="fad13-149">「[DSC 構成](configurations.md)」で DSC 構成の詳細を確認する。</span><span class="sxs-lookup"><span data-stu-id="fad13-149">Find out more about DSC configurations at [DSC configurations](configurations.md).</span></span>
- <span data-ttu-id="fad13-150">「[DSC リソース](../resources/resources.md)」で利用可能な DSC リソースとカスタム DSC リソースの作成方法を確認する。</span><span class="sxs-lookup"><span data-stu-id="fad13-150">See what DSC resources are available, and how to create custom DSC resources at [DSC resources](../resources/resources.md).</span></span>
- <span data-ttu-id="fad13-151">「[PowerShell ギャラリー](https://www.powershellgallery.com/)」で DSC の構成とリソースを検索する。</span><span class="sxs-lookup"><span data-stu-id="fad13-151">Find DSC configurations and resources in the [PowerShell Gallery](https://www.powershellgallery.com/).</span></span>
