---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC Script リソース"
ms.openlocfilehash: 22213b74986b45b3a8205f1584b3b0d89a92f211
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="dsc-script-resource"></a><span data-ttu-id="4ed36-103">DSC Script リソース</span><span class="sxs-lookup"><span data-stu-id="4ed36-103">DSC Script Resource</span></span>

 
> <span data-ttu-id="4ed36-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="4ed36-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="4ed36-105">Windows PowerShell Desired State Configuration (DSC) の **Script** リソースは、ターゲット ノードで Windows PowerShell スクリプトのブロックを実行するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="4ed36-105">The **Script** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to run Windows PowerShell script blocks on target nodes.</span></span> <span data-ttu-id="4ed36-106">`Script` リソースには、`GetScript`、`SetScript`、`TestScript` プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="4ed36-106">The `Script` resource has `GetScript`, `SetScript`, and `TestScript` properties.</span></span> <span data-ttu-id="4ed36-107">このプロパティは、各ターゲット ノードに対して実行されるスクリプト ブロックに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ed36-107">These properties should be set to script blocks that will run on each target node.</span></span> 

<span data-ttu-id="4ed36-108">`GetScript` スクリプト ブロックは、現在のノードの状態を表すハッシュ テーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="4ed36-108">The `GetScript` script block should return a hashtable representing the state of the current node.</span></span> <span data-ttu-id="4ed36-109">ハッシュ テーブルに入るキーは 1 つだけです (`Result`)。値の型は `String` になります。</span><span class="sxs-lookup"><span data-stu-id="4ed36-109">The hashtable must only contain one key `Result` and the value must be of type `String`.</span></span> <span data-ttu-id="4ed36-110">何も返す必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4ed36-110">It is not required to return anything.</span></span> <span data-ttu-id="4ed36-111">DSC は、このスクリプト ブロックの出力を処理しません。</span><span class="sxs-lookup"><span data-stu-id="4ed36-111">DSC doesn't do anything with the output of this script block.</span></span>

<span data-ttu-id="4ed36-112">`TestScript` スクリプト ブロックは、現在のノードを変更する必要があるかどうかを判定します。</span><span class="sxs-lookup"><span data-stu-id="4ed36-112">The `TestScript` script block should determine if the current node needs to be modified.</span></span> <span data-ttu-id="4ed36-113">ノードが最新の場合は `$true` を返します。</span><span class="sxs-lookup"><span data-stu-id="4ed36-113">It should return `$true` if the node is up-to-date.</span></span> <span data-ttu-id="4ed36-114">ノードの構成が最新ではなく、`SetScript` スクリプト ブロックで更新する必要がある場合は、`$false` が返されます。</span><span class="sxs-lookup"><span data-stu-id="4ed36-114">It should return `$false` if the node's configuration is out-of-date and should be updated by the `SetScript` script block.</span></span> <span data-ttu-id="4ed36-115">`TestScript` スクリプト ブロックは DSC によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4ed36-115">The `TestScript` script block is called by DSC.</span></span>

<span data-ttu-id="4ed36-116">`SetScript` スクリプト ブロックはノードを変更します。</span><span class="sxs-lookup"><span data-stu-id="4ed36-116">The `SetScript` script block should modify the node.</span></span> <span data-ttu-id="4ed36-117">これは、`TestScript` ブロックから `$false` が返された場合に DSC によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="4ed36-117">It is called by DSC if the `TestScript` block return `$false`.</span></span>

<span data-ttu-id="4ed36-118">`GetScript`、`TestScript`、または `SetScript` スクリプト ブロックで構成スクリプトの変数を使用する必要がある場合は、`$using:` スコープを使用します (例については、以下を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="4ed36-118">If you need to use variables from your configuration script in the `GetScript`, `TestScript`, or `SetScript` script blocks, use the `$using:` scope (see below for an example).</span></span>


## <a name="syntax"></a><span data-ttu-id="4ed36-119">構文</span><span class="sxs-lookup"><span data-stu-id="4ed36-119">Syntax</span></span>

```
Script [string] #ResourceName
{
    GetScript = [string]
    SetScript = [string]
    TestScript = [string]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a><span data-ttu-id="4ed36-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4ed36-120">Properties</span></span>

|  <span data-ttu-id="4ed36-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4ed36-121">Property</span></span>  |  <span data-ttu-id="4ed36-122">説明</span><span class="sxs-lookup"><span data-stu-id="4ed36-122">Description</span></span>   | 
|---|---| 
| <span data-ttu-id="4ed36-123">GetScript</span><span class="sxs-lookup"><span data-stu-id="4ed36-123">GetScript</span></span>| <span data-ttu-id="4ed36-124">[Get-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407379.aspx) コマンドレットを呼び出すと実行される Windows PowerShell スクリプトのブロックを提供します。</span><span class="sxs-lookup"><span data-stu-id="4ed36-124">Provides a block of Windows PowerShell script that runs when you invoke the [Get-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407379.aspx) cmdlet.</span></span> <span data-ttu-id="4ed36-125">このブロックでは、ハッシュ テーブルを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ed36-125">This block must return a hashtable.</span></span> <span data-ttu-id="4ed36-126">ハッシュ テーブルに入るキーは 1 つだけです (**結果**)。値の型は**文字列**になります。</span><span class="sxs-lookup"><span data-stu-id="4ed36-126">The hashtable must only contain one key **Result** and the value must be of type **String**.</span></span>| 
| <span data-ttu-id="4ed36-127">SetScript</span><span class="sxs-lookup"><span data-stu-id="4ed36-127">SetScript</span></span>| <span data-ttu-id="4ed36-128">Windows PowerShell スクリプトのブロックを提供します。</span><span class="sxs-lookup"><span data-stu-id="4ed36-128">Provides a block of Windows PowerShell script.</span></span> <span data-ttu-id="4ed36-129">[Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) コマンドレットを呼び出すと、**TestScript** ブロックが最初に実行されます。</span><span class="sxs-lookup"><span data-stu-id="4ed36-129">When you invoke the [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) cmdlet, the **TestScript** block runs first.</span></span> <span data-ttu-id="4ed36-130">**TestScript** ブロックが **$false** を返した場合は、**SetScript** ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="4ed36-130">If the **TestScript** block returns **$false**, the **SetScript** block will run.</span></span> <span data-ttu-id="4ed36-131">**TestScript** ブロックが **$true** を返した場合は、**SetScript** ブロックが実行されません。</span><span class="sxs-lookup"><span data-stu-id="4ed36-131">If the **TestScript** block returns **$true**, the **SetScript** block will not run.</span></span>| 
| <span data-ttu-id="4ed36-132">TestScript</span><span class="sxs-lookup"><span data-stu-id="4ed36-132">TestScript</span></span>| <span data-ttu-id="4ed36-133">Windows PowerShell スクリプトのブロックを提供します。</span><span class="sxs-lookup"><span data-stu-id="4ed36-133">Provides a block of Windows PowerShell script.</span></span> <span data-ttu-id="4ed36-134">[Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) コマンドレットを呼び出すと、このブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="4ed36-134">When you invoke the [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) cmdlet, this block runs.</span></span> <span data-ttu-id="4ed36-135">これが **$false** を返した場合は、SetScript ブロックが実行されます。</span><span class="sxs-lookup"><span data-stu-id="4ed36-135">If it returns **$false**, the SetScript block will run.</span></span> <span data-ttu-id="4ed36-136">これが **$true** を返した場合は、SetScript ブロックが実行されません。</span><span class="sxs-lookup"><span data-stu-id="4ed36-136">If it returns **$true**, the SetScript block will not run.</span></span> <span data-ttu-id="4ed36-137">[Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) コマンドレットを呼び出すと、**TestScript** ブロックも実行されます。</span><span class="sxs-lookup"><span data-stu-id="4ed36-137">The **TestScript** block also runs when you invoke the [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) cmdlet.</span></span> <span data-ttu-id="4ed36-138">ただし、この場合、TestScript ブロックがどのような値を返すかに関係なく、**SetScript** ブロックは実行されません。</span><span class="sxs-lookup"><span data-stu-id="4ed36-138">However, in this case, the **SetScript** block will not run, no matter what value the TestScript block returns.</span></span> <span data-ttu-id="4ed36-139">**TestScript** ブロックは、実際の構成が現在の Desired State Configuration と一致する場合には True を返す必要があり、一致しない場合には False を返す必要があります </span><span class="sxs-lookup"><span data-stu-id="4ed36-139">The **TestScript** block must return True if the actual configuration matches the current desired state configuration, and False if it does not match.</span></span> <span data-ttu-id="4ed36-140">(現在の Desired State Configuration は DSC を使用しているノードに適用された最後の構成です)。</span><span class="sxs-lookup"><span data-stu-id="4ed36-140">(The current desired state configuration is the last configuration enacted on the node that is using DSC.)</span></span>| 
| <span data-ttu-id="4ed36-141">Credential</span><span class="sxs-lookup"><span data-stu-id="4ed36-141">Credential</span></span>| <span data-ttu-id="4ed36-142">資格情報が必要な場合、このスクリプトの実行に使用する資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="4ed36-142">Indicates the credentials to use for running this script, if credentials are required.</span></span>| 
| <span data-ttu-id="4ed36-143">DependsOn</span><span class="sxs-lookup"><span data-stu-id="4ed36-143">DependsOn</span></span>| <span data-ttu-id="4ed36-144">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="4ed36-144">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="4ed36-145">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="4ed36-145">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>

## <a name="example-1"></a><span data-ttu-id="4ed36-146">例 1</span><span class="sxs-lookup"><span data-stu-id="4ed36-146">Example 1</span></span>
```powershell
Configuration ScriptTest
{
    Import-DscResource –ModuleName 'PSDesiredStateConfiguration'

    Script ScriptExample
    {
        SetScript = 
        { 
            $sw = New-Object System.IO.StreamWriter("C:\TempFolder\TestFile.txt")
            $sw.WriteLine("Some sample string")
            $sw.Close()
        }
        TestScript = { Test-Path "C:\TempFolder\TestFile.txt" }
        GetScript = { @{ Result = (Get-Content C:\TempFolder\TestFile.txt) } }          
    }
}
```

## <a name="example-2"></a><span data-ttu-id="4ed36-147">例 2</span><span class="sxs-lookup"><span data-stu-id="4ed36-147">Example 2</span></span>
```powershell
$version = Get-Content 'version.txt'

Configuration ScriptTest
{
    Import-DscResource –ModuleName 'PSDesiredStateConfiguration'

    Script UpdateConfigurationVersion
    {
        GetScript = { 
            $currentVersion = Get-Content (Join-Path -Path $env:SYSTEMDRIVE -ChildPath 'version.txt')
            return @{ 'Result' = "$currentVersion" }
        }          
        TestScript = { 
            $state = $GetScript
            if( $state['Result'] -eq $using:version )
            {
                Write-Verbose -Message ('{0} -eq {1}' -f $state['Result'],$using:version)
                return $true
            }
            Write-Verbose -Message ('Version up-to-date: {0}' -f $using:version)
            return $false
        }
        SetScript = { 
            $using:version | Set-Content -Path (Join-Path -Path $env:SYSTEMDRIVE -ChildPath 'version.txt')
        }
    }
}
```

<span data-ttu-id="4ed36-148">このリソースは、構成のバージョンをテキスト ファイルに書き込んでいます。</span><span class="sxs-lookup"><span data-stu-id="4ed36-148">This resource is writing the configuration's version to a text file.</span></span> <span data-ttu-id="4ed36-149">このバージョンはクライアント コンピューターで利用できますが、いずれのノードでも使用できないため、PowerShell の `using` スコープを指定して、`Script` リソースのスクリプト ブロックそれぞれに渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ed36-149">This version is available on the client computer, but isn't on any of the nodes, so it has to be passed to each of the `Script` resource's script blocks with PowerShell's `using` scope.</span></span> <span data-ttu-id="4ed36-150">ノードの MOF ファイルを生成すると、`$version` 変数の値は、クライアント コンピューター上のテキスト ファイルから読み取られます。</span><span class="sxs-lookup"><span data-stu-id="4ed36-150">When generating the node's MOF file, the value of the `$version` variable is read from a text file on the client computer.</span></span> <span data-ttu-id="4ed36-151">各スクリプト ブロックの `$using:version` 変数は、DSC によって `$version` 変数の値に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="4ed36-151">DSC replaces the `$using:version` variables in each script block with the value of the `$version` variable.</span></span>

