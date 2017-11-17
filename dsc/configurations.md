---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC 構成"
ms.openlocfilehash: 3fdee72d5701433a3903697c5a0a32b112136592
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="dsc-configurations"></a><span data-ttu-id="8be5b-103">DSC 構成</span><span class="sxs-lookup"><span data-stu-id="8be5b-103">DSC Configurations</span></span>

><span data-ttu-id="8be5b-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="8be5b-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="8be5b-105">DSC 構成は、特殊な関数を定義する PowerShell スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="8be5b-105">DSC configurations are PowerShell scripts that define a special type of function.</span></span> <span data-ttu-id="8be5b-106">構成を定義するには、PowerShell キーワード **Configuration** を使用します。</span><span class="sxs-lookup"><span data-stu-id="8be5b-106">To define a configuration, you use the PowerShell keyword **Configuration**.</span></span>

```powershell
Configuration MyDscConfiguration {

    Node "TEST-PC1" {
        WindowsFeature MyFeatureInstance {
            Ensure = "Present"
            Name =  "RSAT"
        }
        WindowsFeature My2ndFeatureInstance {
            Ensure = "Present"
            Name = "Bitlocker"
        }
    }
} 

MyDscConfiguration 
```

<span data-ttu-id="8be5b-107">スクリプトを .ps1 ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="8be5b-107">Save the script as a .ps1 file.</span></span>

## <a name="configuration-syntax"></a><span data-ttu-id="8be5b-108">構成構文</span><span class="sxs-lookup"><span data-stu-id="8be5b-108">Configuration syntax</span></span>

<span data-ttu-id="8be5b-109">構成スクリプトは次の部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="8be5b-109">A configuration script consists of the following parts:</span></span>

- <span data-ttu-id="8be5b-110">**Configuration** ブロック。</span><span class="sxs-lookup"><span data-stu-id="8be5b-110">The **Configuration** block.</span></span> <span data-ttu-id="8be5b-111">これは、最も外側にあるスクリプト ブロックです。</span><span class="sxs-lookup"><span data-stu-id="8be5b-111">This is the outermost script block.</span></span> <span data-ttu-id="8be5b-112">このブロックを定義するには、**Configuration** キーワードを使用し、名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8be5b-112">You define it by using the **Configuration** keyword and providing a name.</span></span> <span data-ttu-id="8be5b-113">この場合、構成の名前は "MyDscConfiguration" です。</span><span class="sxs-lookup"><span data-stu-id="8be5b-113">In this case, the name of the configuration is "MyDscConfiguration".</span></span>
- <span data-ttu-id="8be5b-114">1 つまたは複数の **Node** ブロック。</span><span class="sxs-lookup"><span data-stu-id="8be5b-114">One or more **Node** blocks.</span></span> <span data-ttu-id="8be5b-115">これらは、構成するノード (コンピューターまたは VM) を定義します。</span><span class="sxs-lookup"><span data-stu-id="8be5b-115">These define the nodes (computers or VMs) that you are configuring.</span></span> <span data-ttu-id="8be5b-116">上記の構成には、"TEST-PC1" という名前のコンピューターを対象とする 1 つの **Node** ブロックがあります。</span><span class="sxs-lookup"><span data-stu-id="8be5b-116">In the above configuration, there is one **Node** block that targets a computer named "TEST-PC1".</span></span>
- <span data-ttu-id="8be5b-117">1 つまたは複数のリソース ブロック。</span><span class="sxs-lookup"><span data-stu-id="8be5b-117">One or more resource blocks.</span></span> <span data-ttu-id="8be5b-118">ここでは、構成するリソースのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="8be5b-118">This is where the configuration sets the properties for the resources that it is configuring.</span></span> <span data-ttu-id="8be5b-119">この場合は、それぞれ "WindowsFeature" リソースを呼び出す 2 つのリソース ブロックがあります。</span><span class="sxs-lookup"><span data-stu-id="8be5b-119">In this case, there are two resource blocks, each of which call the "WindowsFeature" resource.</span></span>

<span data-ttu-id="8be5b-120">**Configuration** ブロック内では、通常 PowerShell 関数内で可能なすべてのことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8be5b-120">Within a **Configuration** block, you can do anything that you normally could in a PowerShell function.</span></span> <span data-ttu-id="8be5b-121">たとえば、前の例では、ターゲット コンピューターの名前を構成内でハード コードしなかった場合、ノード名のパラメーターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="8be5b-121">For example, in the previous example, if you didn't want to hard code the name of the target computer in the configuration, you could add a parameter for the node name:</span></span>

```powershell
Configuration MyDscConfiguration {

    param(
        [string[]]$ComputerName="localhost"
    )
    Node $ComputerName {
        WindowsFeature MyFeatureInstance {
            Ensure = "Present"
            Name =  "RSAT"
        }
        WindowsFeature My2ndFeatureInstance {
            Ensure = "Present"
            Name = "Bitlocker"
        }
    }
}

MyDscConfiguration 
```

<span data-ttu-id="8be5b-122">この例では、構成のコンパイル時にノードの名前を **ComputerName** パラメーターとして渡すことで、ノードの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8be5b-122">In this example, you specify the name of the node by passing it as the **ComputerName** parameter when you compile the configuraton.</span></span> <span data-ttu-id="8be5b-123">名前の既定値は "localhost" です。</span><span class="sxs-lookup"><span data-stu-id="8be5b-123">The name defaults to "localhost".</span></span>

## <a name="compiling-the-configuration"></a><span data-ttu-id="8be5b-124">構成のコンパイル</span><span class="sxs-lookup"><span data-stu-id="8be5b-124">Compiling the configuration</span></span>

<span data-ttu-id="8be5b-125">構成を適用する前に、MOF ドキュメントにコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8be5b-125">Before you can enact a configuration, you have to compile it into a MOF document.</span></span> <span data-ttu-id="8be5b-126">そのためには、PowerShell 関数の場合と同じように構成を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8be5b-126">You do this by calling the configuration like you would a PowerShell function.</span></span>  
<span data-ttu-id="8be5b-127">例の最後の行には構成を呼び出すための構成の名前のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8be5b-127">The last line of the example containing only the name of the configuration, calls the configuration.</span></span>

><span data-ttu-id="8be5b-128">**注:** 構成を呼び出すには、(他の PowerShell 関数と同様に) 関数がグローバル スコープ内にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="8be5b-128">**Note:** To call a configuration, the function must be in global scope (as with any other PowerShell function).</span></span> 
><span data-ttu-id="8be5b-129">そのためには、スクリプトで "ドット ソース" を行うか、F5 キーを使用するか、または ISE で **[スクリプトの実行]** をクリックして、構成スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="8be5b-129">You can make this happen either by "dot-sourcing" the script, or by running the configuration script by using F5 or clicking on the **Run Script** button in the ISE.</span></span> 
><span data-ttu-id="8be5b-130">スクリプトでドット ソースを行うには、構成を含むスクリプト ファイルの名前が `myConfig.ps1` である場合、`. .\myConfig.ps1` でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8be5b-130">To dot-source the script, run the command `. .\myConfig.ps1` where `myConfig.ps1` is the name of the script file that contains your configuration.</span></span>

<span data-ttu-id="8be5b-131">構成を呼び出すと、結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8be5b-131">When you call the configuration, it:</span></span>

- <span data-ttu-id="8be5b-132">すべての変数が解決されます</span><span class="sxs-lookup"><span data-stu-id="8be5b-132">Resolves all variables</span></span> 
- <span data-ttu-id="8be5b-133">構成と同じ名前のフォルダーが現在のディレクトリ内に作成されます。</span><span class="sxs-lookup"><span data-stu-id="8be5b-133">Creates a folder in the current directory with the same name as the configuration.</span></span>
- <span data-ttu-id="8be5b-134">_NodeName_.mof という名前のファイルが新しいディレクトリ内に作成されます。_NodeName_ は、構成のターゲット ノードの名前です。</span><span class="sxs-lookup"><span data-stu-id="8be5b-134">Creates a file named _NodeName_.mof in the new directory, where _NodeName_ is the name of the target node of the configuration.</span></span> 
    <span data-ttu-id="8be5b-135">複数のノードがある場合は、ノードごとに MOF ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8be5b-135">If there are more than one nodes, a MOF file will be created for each node.</span></span>

><span data-ttu-id="8be5b-136">**注**: MOF ファイルには、ターゲット ノードのすべての構成情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8be5b-136">**Note**: The MOF file contains all of the configuration information for the target node.</span></span> <span data-ttu-id="8be5b-137">このため、このファイルをセキュリティ保護することが重要です。</span><span class="sxs-lookup"><span data-stu-id="8be5b-137">Because of this, it’s important to keep it secure.</span></span> 
><span data-ttu-id="8be5b-138">詳細については、「[MOF ファイルのセキュリティ保護](secureMOF.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8be5b-138">For more information, see [Securing the MOF file](secureMOF.md).</span></span>

<span data-ttu-id="8be5b-139">上記の最初の構成をコンパイルすると、次のフォルダー構造となります。</span><span class="sxs-lookup"><span data-stu-id="8be5b-139">Compiling the first configuration above results in the following folder structure:</span></span>

```powershell
. .\MyDscConfiguration.ps1
MyDscConfiguration
```

```
    Directory: C:\users\default\Documents\DSC Configurations\MyDscConfiguration
Mode                LastWriteTime         Length Name                                                                                              
----                -------------         ------ ----                                                                                         
-a----       10/23/2015   4:32 PM           2842 TEST-PC1.mof
```  

<span data-ttu-id="8be5b-140">2 番目の例のように構成でパラメーターを受け取る場合は、コンパイル時に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8be5b-140">If the configuration takes a parameter, as in the second example, that has to be provided at compile time.</span></span> <span data-ttu-id="8be5b-141">その場合、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8be5b-141">Here's how that would look:</span></span>

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

## <a name="using-dependson"></a><span data-ttu-id="8be5b-142">DependsOn の使用</span><span class="sxs-lookup"><span data-stu-id="8be5b-142">Using DependsOn</span></span>

<span data-ttu-id="8be5b-143">**DependsOn** は便利な DSC キーワードです。</span><span class="sxs-lookup"><span data-stu-id="8be5b-143">A useful DSC keyword is **DependsOn**.</span></span> <span data-ttu-id="8be5b-144">通常 (必ずしも常にではありませんが)、DSC では、構成内で出現する順序でリソースが適用されます。</span><span class="sxs-lookup"><span data-stu-id="8be5b-144">Typically (though not necessarily always), DSC applies the resources in the order that they appear within the configuration.</span></span> <span data-ttu-id="8be5b-145">ただし、**DependsOn** でどのリソースが他のリソースに依存するかを指定すると、リソース インスタンスが定義されている順序に関係なく、LCM によってリソースが正しい順序で適用されます。</span><span class="sxs-lookup"><span data-stu-id="8be5b-145">However, **DependsOn** specifies which resources depend on other resources, and the LCM ensures that they are applied in the correct order, regardless of the order in which resource instances are defined.</span></span> <span data-ttu-id="8be5b-146">たとえば、構成で、**User** リソースのインスタンスが **Group** インスタンスの存在に依存することを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8be5b-146">For example, a configuration might specify that an instance of the **User** resource depends on the existence of a **Group** instance:</span></span>

```powershell
Configuration DependsOnExample {
    Node Test-PC1 {
        Group GroupExample {
            Ensure = "Present"
            GroupName = "TestGroup"
        }

        User UserExample {
            Ensure = "Present"
            UserName = "TestUser"
            FullName = "TestUser"
            DependsOn = "[Group]GroupExample"
        }
    }
}

DependsOnExample
```

## <a name="using-new-resources-in-your-configuration"></a><span data-ttu-id="8be5b-147">構成での新しいリソースの使用</span><span class="sxs-lookup"><span data-stu-id="8be5b-147">Using new resources in Your configuration</span></span>

<span data-ttu-id="8be5b-148">前の例を実行した場合、リソースを明示的にインポートしないで使用することについて警告されることがあります。</span><span class="sxs-lookup"><span data-stu-id="8be5b-148">If you ran the previous examples, you might have noticed that you were warned that you were using a resource without explicitly importing it.</span></span>
<span data-ttu-id="8be5b-149">今日、DSC には PSDesiredStateConfiguration モジュールの一部として 12 のリソースが付属しています。</span><span class="sxs-lookup"><span data-stu-id="8be5b-149">Today, DSC ships with 12 resources as part of the PSDesiredStateConfiguration module.</span></span> <span data-ttu-id="8be5b-150">外部モジュールの他のリソースが LCM によって認識されるためには、`$env:PSModulePath` に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8be5b-150">Other resources in external modules must be placed in `$env:PSModulePath` in order to be recognized by the LCM.</span></span> <span data-ttu-id="8be5b-151">新しいコマンドレット [Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx) を使用して、どのリソースがシステムにインストールされ、LCM で使用できるかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="8be5b-151">A new cmdlet, [Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx), can be used to determine what resources are installed on the system and available for use by the LCM.</span></span> <span data-ttu-id="8be5b-152">これらのモジュールが `$env:PSModulePath` に配置され、[Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx) によって正しく認識された後、構成内に読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="8be5b-152">Once these modules have been placed in `$env:PSModulePath` and are properly recognized by [Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx), they still need to be loaded within your configuration.</span></span> 
<span data-ttu-id="8be5b-153">**Import-DscResource** は、**Configuration** ブロック内でのみ認識される動的なキーワードです (つまり、コマンドレットではありません)。</span><span class="sxs-lookup"><span data-stu-id="8be5b-153">**Import-DscResource** is a dynamic keyword that can only be recognized within a **Configuration** block (i.e. it is not a cmdlet).</span></span> 
<span data-ttu-id="8be5b-154">**Import-DscResource** は、次の 2 つのパラメーターをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8be5b-154">**Import-DscResource** supports two parameters:</span></span>
- <span data-ttu-id="8be5b-155">**ModuleName** は、**Import-DscResource** を使用する場合に推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="8be5b-155">**ModuleName** is the recommended way of using **Import-DscResource**.</span></span> <span data-ttu-id="8be5b-156">これは、インポートするリソースを含むモジュールの名前 (およびモジュール名の文字列配列) を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8be5b-156">It accepts the name of the module that contains the resources to be imported (as well as a string array of module names).</span></span> 
- <span data-ttu-id="8be5b-157">**Name** は、インポートするリソースの名前です。</span><span class="sxs-lookup"><span data-stu-id="8be5b-157">**Name** is the name of the resource to import.</span></span> <span data-ttu-id="8be5b-158">これは、[Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx) によって "Name" として返されるフレンドリ名ではありませんが、リソース スキーマを定義するときに使用されるクラス名です ([Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx) によって **ResourceType** として返されます)。</span><span class="sxs-lookup"><span data-stu-id="8be5b-158">This is not the friendly name returned as "Name" by [Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx), but the class name used when defining the resource schema (returned as **ResourceType** by [Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx)).</span></span> 

## <a name="see-also"></a><span data-ttu-id="8be5b-159">参照</span><span class="sxs-lookup"><span data-stu-id="8be5b-159">See Also</span></span>
* [<span data-ttu-id="8be5b-160">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="8be5b-160">Windows PowerShell Desired State Configuration Overview</span></span>](overview.md)
* [<span data-ttu-id="8be5b-161">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="8be5b-161">DSC Resources</span></span>](resources.md)
* [<span data-ttu-id="8be5b-162">ローカル構成マネージャーの構成</span><span class="sxs-lookup"><span data-stu-id="8be5b-162">Configuring The Local Configuration Manager</span></span>](metaConfig.md)

