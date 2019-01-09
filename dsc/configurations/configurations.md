---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC 構成
ms.openlocfilehash: 6af27f442de3080facd65892c713c989d0e388c5
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402581"
---
# <a name="dsc-configurations"></a><span data-ttu-id="c79a5-103">DSC 構成</span><span class="sxs-lookup"><span data-stu-id="c79a5-103">DSC Configurations</span></span>

> <span data-ttu-id="c79a5-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="c79a5-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="c79a5-105">DSC 構成は、特殊な関数を定義する PowerShell スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="c79a5-105">DSC configurations are PowerShell scripts that define a special type of function.</span></span>
<span data-ttu-id="c79a5-106">構成を定義するには、PowerShell キーワード **Configuration** を使用します。</span><span class="sxs-lookup"><span data-stu-id="c79a5-106">To define a configuration, you use the PowerShell keyword **Configuration**.</span></span>

```powershell
Configuration MyDscConfiguration {
    Node "TEST-PC1" {
        WindowsFeature MyFeatureInstance {
            Ensure = 'Present'
            Name = 'RSAT'
        }
        WindowsFeature My2ndFeatureInstance {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}
MyDscConfiguration
```

<span data-ttu-id="c79a5-107">としてスクリプトを保存、`.ps1`ファイル。</span><span class="sxs-lookup"><span data-stu-id="c79a5-107">Save the script as a `.ps1` file.</span></span>

## <a name="configuration-syntax"></a><span data-ttu-id="c79a5-108">構成構文</span><span class="sxs-lookup"><span data-stu-id="c79a5-108">Configuration syntax</span></span>

<span data-ttu-id="c79a5-109">構成スクリプトは次の部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="c79a5-109">A configuration script consists of the following parts:</span></span>

- <span data-ttu-id="c79a5-110">**Configuration** ブロック。</span><span class="sxs-lookup"><span data-stu-id="c79a5-110">The **Configuration** block.</span></span> <span data-ttu-id="c79a5-111">これは、最も外側にあるスクリプト ブロックです。</span><span class="sxs-lookup"><span data-stu-id="c79a5-111">This is the outermost script block.</span></span> <span data-ttu-id="c79a5-112">このブロックを定義するには、**Configuration** キーワードを使用し、名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c79a5-112">You define it by using the **Configuration** keyword and providing a name.</span></span> <span data-ttu-id="c79a5-113">この場合、構成の名前は "MyDscConfiguration" です。</span><span class="sxs-lookup"><span data-stu-id="c79a5-113">In this case, the name of the configuration is "MyDscConfiguration".</span></span>
- <span data-ttu-id="c79a5-114">1 つまたは複数の **Node** ブロック。</span><span class="sxs-lookup"><span data-stu-id="c79a5-114">One or more **Node** blocks.</span></span> <span data-ttu-id="c79a5-115">これらは、構成するノード (コンピューターまたは VM) を定義します。</span><span class="sxs-lookup"><span data-stu-id="c79a5-115">These define the nodes (computers or VMs) that you are configuring.</span></span> <span data-ttu-id="c79a5-116">上記の構成には、"TEST-PC1" という名前のコンピューターを対象とする 1 つの **Node** ブロックがあります。</span><span class="sxs-lookup"><span data-stu-id="c79a5-116">In the above configuration, there is one **Node** block that targets a computer named "TEST-PC1".</span></span> <span data-ttu-id="c79a5-117">ノード ブロックには、複数のコンピューター名を受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="c79a5-117">The Node block can accept multiple computer names.</span></span>
- <span data-ttu-id="c79a5-118">1 つまたは複数のリソース ブロック。</span><span class="sxs-lookup"><span data-stu-id="c79a5-118">One or more resource blocks.</span></span> <span data-ttu-id="c79a5-119">ここでは、構成するリソースのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="c79a5-119">This is where the configuration sets the properties for the resources that it is configuring.</span></span> <span data-ttu-id="c79a5-120">この場合は、それぞれ "WindowsFeature" リソースを呼び出す 2 つのリソース ブロックがあります。</span><span class="sxs-lookup"><span data-stu-id="c79a5-120">In this case, there are two resource blocks, each of which call the "WindowsFeature" resource.</span></span>

<span data-ttu-id="c79a5-121">**Configuration** ブロック内では、通常 PowerShell 関数内で可能なすべてのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c79a5-121">Within a **Configuration** block, you can do anything that you normally could in a PowerShell function.</span></span> <span data-ttu-id="c79a5-122">たとえば、前の例では、ターゲット コンピューターの名前を構成内でハード コードしなかった場合、ノード名のパラメーターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="c79a5-122">For example, in the previous example, if you didn't want to hard code the name of the target computer in the configuration, you could add a parameter for the node name:</span></span>

<span data-ttu-id="c79a5-123">この例では、構成のコンパイル時にノードの名前を **ComputerName** パラメーターとして渡すことで、ノードの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c79a5-123">In this example, you specify the name of the node by passing it as the **ComputerName** parameter when you compile the configuration.</span></span> <span data-ttu-id="c79a5-124">名前の既定値は "localhost" です。</span><span class="sxs-lookup"><span data-stu-id="c79a5-124">The name defaults to "localhost".</span></span>

```powershell
Configuration MyDscConfiguration
{
    param
    (
        [string[]]$ComputerName='localhost'
    )

    Node $ComputerName
    {
        WindowsFeature MyFeatureInstance
        {
            Ensure = 'Present'
            Name = 'RSAT'
        }

        WindowsFeature My2ndFeatureInstance
        {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}

MyDscConfiguration
```

<span data-ttu-id="c79a5-125">**ノード**ブロックは、複数のコンピューター名にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="c79a5-125">The **Node** block can also accept multiple computer names.</span></span> <span data-ttu-id="c79a5-126">上記の例で使用するか、`-ComputerName`パラメーター、またはコンマで区切られたパスのリストを直接使用するコンピューターの**ノード**ブロックします。</span><span class="sxs-lookup"><span data-stu-id="c79a5-126">In the above example, you can either use the `-ComputerName` parameter, or pass a comma-separated list of computers directly to the **Node** block.</span></span>

```powershell
MyDscConfiguration -ComputerName "localhost", "Server01"
```

<span data-ttu-id="c79a5-127">コンピューターの一覧を指定するときに、**ノード**ブロック、構成では、内から配列表記を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c79a5-127">When specifying a list of computers to the **Node** block, from within a Configuration, you need to use array-notation.</span></span>

```powershell
Configuration MyDscConfiguration
{
    Node @('localhost', 'Server01')
    {
        WindowsFeature MyFeatureInstance
        {
            Ensure = 'Present'
            Name = 'RSAT'
        }

        WindowsFeature My2ndFeatureInstance
        {
            Ensure = 'Present'
            Name = 'Bitlocker'
        }
    }
}

MyDscConfiguration
```

## <a name="compiling-the-configuration"></a><span data-ttu-id="c79a5-128">構成のコンパイル</span><span class="sxs-lookup"><span data-stu-id="c79a5-128">Compiling the configuration</span></span>

<span data-ttu-id="c79a5-129">構成を適用する前に、MOF ドキュメントにコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c79a5-129">Before you can enact a configuration, you have to compile it into a MOF document.</span></span>
<span data-ttu-id="c79a5-130">そのためには、PowerShell 関数の場合と同じように構成を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c79a5-130">You do this by calling the configuration like you would call a PowerShell function.</span></span>
<span data-ttu-id="c79a5-131">例の最後の行には構成を呼び出すための構成の名前のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c79a5-131">The last line of the example containing only the name of the configuration, calls the configuration.</span></span>

> [!NOTE]
> <span data-ttu-id="c79a5-132">構成を呼び出すには、(他の PowerShell 関数と同様に) 関数がグローバル スコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="c79a5-132">To call a configuration, the function must be in global scope (as with any other PowerShell function).</span></span>
> <span data-ttu-id="c79a5-133">そのためには、スクリプトで "ドット ソース" を行うか、F5 キーを使用するか、または ISE で **[スクリプトの実行]** をクリックして、構成スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="c79a5-133">You can make this happen either by "dot-sourcing" the script, or by running the configuration script by using F5 or clicking on the **Run Script** button in the ISE.</span></span>
> <span data-ttu-id="c79a5-134">スクリプトでドット ソースを行うには、構成を含むスクリプト ファイルの名前が `myConfig.ps1` である場合、`. .\myConfig.ps1` でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c79a5-134">To dot-source the script, run the command `. .\myConfig.ps1` where `myConfig.ps1` is the name of the script file that contains your configuration.</span></span>

<span data-ttu-id="c79a5-135">構成を呼び出すと、結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c79a5-135">When you call the configuration, it:</span></span>

- <span data-ttu-id="c79a5-136">すべての変数が解決されます</span><span class="sxs-lookup"><span data-stu-id="c79a5-136">Resolves all variables</span></span>
- <span data-ttu-id="c79a5-137">構成と同じ名前のフォルダーが現在のディレクトリ内に作成されます。</span><span class="sxs-lookup"><span data-stu-id="c79a5-137">Creates a folder in the current directory with the same name as the configuration.</span></span>
- <span data-ttu-id="c79a5-138">_NodeName_.mof という名前のファイルが新しいディレクトリ内に作成されます。_NodeName_ は、構成のターゲット ノードの名前です。</span><span class="sxs-lookup"><span data-stu-id="c79a5-138">Creates a file named _NodeName_.mof in the new directory, where _NodeName_ is the name of the target node of the configuration.</span></span>
  <span data-ttu-id="c79a5-139">1 つ以上のノードがある場合、MOF ファイルがノードごとに作成されます。</span><span class="sxs-lookup"><span data-stu-id="c79a5-139">If there is more than one node, a MOF file will be created for each node.</span></span>

> [!NOTE]
> <span data-ttu-id="c79a5-140">MOF ファイルには、ターゲット ノードのすべての構成情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c79a5-140">The MOF file contains all of the configuration information for the target node.</span></span> <span data-ttu-id="c79a5-141">このため、このファイルをセキュリティ保護することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c79a5-141">Because of this, it’s important to keep it secure.</span></span>
> <span data-ttu-id="c79a5-142">詳細については、「[MOF ファイルのセキュリティ保護](../pull-server/secureMOF.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c79a5-142">For more information, see [Securing the MOF file](../pull-server/secureMOF.md).</span></span>

<span data-ttu-id="c79a5-143">上記の最初の構成をコンパイルすると、次のフォルダー構造となります。</span><span class="sxs-lookup"><span data-stu-id="c79a5-143">Compiling the first configuration above results in the following folder structure:</span></span>

```powershell
. .\MyDscConfiguration.ps1
MyDscConfiguration
```

```
    Directory: C:\users\default\Documents\DSC Configurations\MyDscConfiguration
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       10/23/2015   4:32 PM           2842 localhost.mof
```

<span data-ttu-id="c79a5-144">2 番目の例のように構成でパラメーターを受け取る場合は、コンパイル時に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c79a5-144">If the configuration takes a parameter, as in the second example, that has to be provided at compile time.</span></span> <span data-ttu-id="c79a5-145">その場合、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c79a5-145">Here's how that would look:</span></span>

```powershell
. .\MyDscConfiguration.ps1
MyDscConfiguration -ComputerName 'MyTestNode'
```

```
    Directory: C:\users\default\Documents\DSC Configurations\MyDscConfiguration
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----       10/23/2015   4:32 PM           2842 MyTestNode.mof
```

## <a name="using-new-resources-in-your-configuration"></a><span data-ttu-id="c79a5-146">構成での新しいリソースの使用</span><span class="sxs-lookup"><span data-stu-id="c79a5-146">Using new resources in Your configuration</span></span>

<span data-ttu-id="c79a5-147">前の例を実行した場合、リソースを明示的にインポートしないで使用することについて警告されることがあります。</span><span class="sxs-lookup"><span data-stu-id="c79a5-147">If you ran the previous examples, you might have noticed that you were warned that you were using a resource without explicitly importing it.</span></span>
<span data-ttu-id="c79a5-148">今日、DSC には PSDesiredStateConfiguration モジュールの一部として 12 のリソースが付属しています。</span><span class="sxs-lookup"><span data-stu-id="c79a5-148">Today, DSC ships with 12 resources as part of the PSDesiredStateConfiguration module.</span></span>

<span data-ttu-id="c79a5-149">コマンドレット [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) を使用して、どのリソースがシステムにインストールされ、LCM で使用できるかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="c79a5-149">The cmdlet, [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), can be used to determine what resources are installed on the system and available for use by the LCM.</span></span>
<span data-ttu-id="c79a5-150">これらのモジュールが `$env:PSModulePath` に配置され、[Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) によって正しく認識された後、構成内に読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="c79a5-150">Once these modules have been placed in `$env:PSModulePath` and are properly recognized by [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), they still need to be loaded within your configuration.</span></span>

<span data-ttu-id="c79a5-151">**Import-dscresource**内でのみ認識できる動的キーワードには、**構成**ブロック、コマンドレットではありません。</span><span class="sxs-lookup"><span data-stu-id="c79a5-151">**Import-DscResource** is a dynamic keyword that can only be recognized within a **Configuration** block, it is not a cmdlet.</span></span>
<span data-ttu-id="c79a5-152">**Import-DscResource** は、次の 2 つのパラメーターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c79a5-152">**Import-DscResource** supports two parameters:</span></span>

- <span data-ttu-id="c79a5-153">**ModuleName** は、**Import-DscResource** を使用する場合に推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="c79a5-153">**ModuleName** is the recommended way of using **Import-DscResource**.</span></span> <span data-ttu-id="c79a5-154">これは、インポートするリソースを含むモジュールの名前 (およびモジュール名の文字列配列) を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c79a5-154">It accepts the name of the module that contains the resources to be imported (as well as a string array of module names).</span></span>
- <span data-ttu-id="c79a5-155">**Name** は、インポートするリソースの名前です。</span><span class="sxs-lookup"><span data-stu-id="c79a5-155">**Name** is the name of the resource to import.</span></span> <span data-ttu-id="c79a5-156">これは、[Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) によって "Name" として返されるフレンドリ名ではありませんが、リソース スキーマを定義するときに使用されるクラス名です ([Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) によって **ResourceType** として返されます)。</span><span class="sxs-lookup"><span data-stu-id="c79a5-156">This is not the friendly name returned as "Name" by [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource), but the class name used when defining the resource schema (returned as **ResourceType** by [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)).</span></span>

<span data-ttu-id="c79a5-157">使用しての詳細については`Import-DSCResource`を参照してください[Import-dscresource を使用します。](import-dscresource.md)</span><span class="sxs-lookup"><span data-stu-id="c79a5-157">For more information on using `Import-DSCResource`, see [Using Import-DSCResource](import-dscresource.md)</span></span>

## <a name="powershell-v4-and-v5-differences"></a><span data-ttu-id="c79a5-158">PowerShell v4 および v5 の違い</span><span class="sxs-lookup"><span data-stu-id="c79a5-158">PowerShell v4 and v5 differences</span></span>

<span data-ttu-id="c79a5-159">PowerShell 4.0 に格納する必要がある DSC リソースの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="c79a5-159">There are differences in where DSC resources need to be stored in PowerShell 4.0.</span></span> <span data-ttu-id="c79a5-160">詳細については、次を参照してください。[リソースの場所](import-dscresource.md#resource-location)します。</span><span class="sxs-lookup"><span data-stu-id="c79a5-160">For more information, see [Resource location](import-dscresource.md#resource-location).</span></span>

## <a name="see-also"></a><span data-ttu-id="c79a5-161">参照</span><span class="sxs-lookup"><span data-stu-id="c79a5-161">See Also</span></span>

- [<span data-ttu-id="c79a5-162">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="c79a5-162">Windows PowerShell Desired State Configuration Overview</span></span>](../overview/overview.md)
- [<span data-ttu-id="c79a5-163">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="c79a5-163">DSC Resources</span></span>](../resources/resources.md)
- [<span data-ttu-id="c79a5-164">ローカル構成マネージャーの構成</span><span class="sxs-lookup"><span data-stu-id="c79a5-164">Configuring The Local Configuration Manager</span></span>](../managing-nodes/metaConfig.md)
