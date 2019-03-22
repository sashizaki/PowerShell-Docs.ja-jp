---
ms.date: 08/24/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Script リソース
ms.openlocfilehash: 86dfb74bf52d8907686bb955fd722f4fb8b9131b
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2019
ms.locfileid: "58054758"
---
# <a name="dsc-script-resource"></a><span data-ttu-id="85860-103">DSC Script リソース</span><span class="sxs-lookup"><span data-stu-id="85860-103">DSC Script Resource</span></span>

> <span data-ttu-id="85860-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="85860-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="85860-105">Windows PowerShell Desired State Configuration (DSC) の **Script** リソースは、ターゲット ノードで Windows PowerShell スクリプトのブロックを実行するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="85860-105">The **Script** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to run Windows PowerShell script blocks on target nodes.</span></span> <span data-ttu-id="85860-106">**Script** リソースでは、該当の DSC 状態の操作を実行するために定義したスクリプト ブロックを含む `GetScript`、`SetScript`、および `TestScript` プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="85860-106">The **Script** resource uses `GetScript`, `SetScript`, and `TestScript` properties that contain script blocks you define to perform the corresponding DSC state operations.</span></span>

## <a name="syntax"></a><span data-ttu-id="85860-107">構文</span><span class="sxs-lookup"><span data-stu-id="85860-107">Syntax</span></span>

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

> [!NOTE]
> <span data-ttu-id="85860-108">`GetScript`、`TestScript`、および `SetScript` ブロックは、文字列として格納されます。</span><span class="sxs-lookup"><span data-stu-id="85860-108">The `GetScript`, `TestScript`, and `SetScript` blocks are stored as strings.</span></span>

## <a name="properties"></a><span data-ttu-id="85860-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="85860-109">Properties</span></span>

|<span data-ttu-id="85860-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="85860-110">Property</span></span>|<span data-ttu-id="85860-111">説明</span><span class="sxs-lookup"><span data-stu-id="85860-111">Description</span></span>|
|--------|-----------|
|<span data-ttu-id="85860-112">GetScript</span><span class="sxs-lookup"><span data-stu-id="85860-112">GetScript</span></span>|<span data-ttu-id="85860-113">ノードの現在の状態を返すスクリプト ブロック。</span><span class="sxs-lookup"><span data-stu-id="85860-113">A script block that returns the current state of the Node.</span></span>|
|<span data-ttu-id="85860-114">SetScript</span><span class="sxs-lookup"><span data-stu-id="85860-114">SetScript</span></span>|<span data-ttu-id="85860-115">ノードが目的の状態になっていない場合に、コンプライアンスを適用するために DSC が使用するスクリプト ブロック。</span><span class="sxs-lookup"><span data-stu-id="85860-115">A script block that DSC uses to enforce compliance when the Node is not in the desired state.</span></span>|
|<span data-ttu-id="85860-116">TestScript</span><span class="sxs-lookup"><span data-stu-id="85860-116">TestScript</span></span>|<span data-ttu-id="85860-117">ノードが目的の状態になっているかどうかを判定するスクリプト ブロック。</span><span class="sxs-lookup"><span data-stu-id="85860-117">A script block that determines if the Node is in the desired state.</span></span>|
|<span data-ttu-id="85860-118">Credential</span><span class="sxs-lookup"><span data-stu-id="85860-118">Credential</span></span>| <span data-ttu-id="85860-119">資格情報が必要な場合、このスクリプトの実行に使用する資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="85860-119">Indicates the credentials to use for running this script, if credentials are required.</span></span>|
|<span data-ttu-id="85860-120">DependsOn</span><span class="sxs-lookup"><span data-stu-id="85860-120">DependsOn</span></span>| <span data-ttu-id="85860-121">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="85860-121">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="85860-122">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="85860-122">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>

### <a name="getscript"></a><span data-ttu-id="85860-123">GetScript</span><span class="sxs-lookup"><span data-stu-id="85860-123">GetScript</span></span>

<span data-ttu-id="85860-124">DSC は `GetScript` からの出力を使用しません。</span><span class="sxs-lookup"><span data-stu-id="85860-124">DSC does not use the output from `GetScript`.</span></span> <span data-ttu-id="85860-125">[Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) コマンドレットは `GetScript` を実行して、ノードの現在の状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="85860-125">The [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet executes the `GetScript` to retrieve a node's current state.</span></span> <span data-ttu-id="85860-126">戻り値は `GetScript` からは必要とされません。</span><span class="sxs-lookup"><span data-stu-id="85860-126">A return value is not required from `GetScript`.</span></span> <span data-ttu-id="85860-127">戻り値を指定した場合は、値が `String` の **Result** キーを含む `hashtable` になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="85860-127">If you specify a return value, it must be a `hashtable` containing a **Result** key whose value is a `String`.</span></span>

### <a name="testscript"></a><span data-ttu-id="85860-128">TestScript</span><span class="sxs-lookup"><span data-stu-id="85860-128">TestScript</span></span>

<span data-ttu-id="85860-129">`TestScript` は、`SetScript` が実行される必要があるかどうかを判定するために、DSC によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="85860-129">The `TestScript` is executed by DSC to determine if the `SetScript` should be run.</span></span> <span data-ttu-id="85860-130">`TestScript` から `$false` が返された場合、DSC は `SetScript` を実行して、ノードを目的の状態に戻します。</span><span class="sxs-lookup"><span data-stu-id="85860-130">If the `TestScript` returns `$false`, DSC executes the `SetScript` to bring the node back to the desired state.</span></span> <span data-ttu-id="85860-131">`boolean` 値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="85860-131">It must return a `boolean` value.</span></span> <span data-ttu-id="85860-132">結果が `$true` の場合、ノードが準拠しており `SetScript` が実行されるべきではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="85860-132">A result of `$true` indicates that the node is compliant and `SetScript` should not executed.</span></span>

<span data-ttu-id="85860-133">[Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) コマンドレットでは、`TestScript` を実行して、**Script** リソースに準拠しているノードを取得します。</span><span class="sxs-lookup"><span data-stu-id="85860-133">The [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) cmdlet, executes the `TestScript` to retrieve the nodes compliance with the  **Script** resources.</span></span> <span data-ttu-id="85860-134">ただし、この場合は、`TestScript` ブロックによって返される値に関わらず、`SetScript` は実行されません。</span><span class="sxs-lookup"><span data-stu-id="85860-134">However, in this case, the `SetScript` does not run, no matter what the `TestScript` block returns.</span></span>

> [!NOTE]
> <span data-ttu-id="85860-135">`TestScript` からの出力はすべて、戻り値の一部です。</span><span class="sxs-lookup"><span data-stu-id="85860-135">All output from your `TestScript` is part of its return value.</span></span> <span data-ttu-id="85860-136">PowerShell は、抑制されていない出力を非ゼロとして解釈します。これは、ノードの状態に関係なく、`TestScript` は `$true` を返すことを意味します。</span><span class="sxs-lookup"><span data-stu-id="85860-136">PowerShell interprets unsuppressed output as non-zero, which means that your `TestScript` will return `$true` regardless of your node's state.</span></span>
> <span data-ttu-id="85860-137">これにより、誤検知という予期しない結果となり、トラブルシューティングの際に困難が生じます。</span><span class="sxs-lookup"><span data-stu-id="85860-137">This results in unpredictable results, false positives, and causes difficulty during troubleshooting.</span></span>

### <a name="setscript"></a><span data-ttu-id="85860-138">SetScript</span><span class="sxs-lookup"><span data-stu-id="85860-138">SetScript</span></span>

<span data-ttu-id="85860-139">`SetScript` はノードを変更して、目的の状態を適用します。</span><span class="sxs-lookup"><span data-stu-id="85860-139">The `SetScript` modifies the node to enforce the desired state.</span></span> <span data-ttu-id="85860-140">これは、`TestScript` スクリプト ブロックから `$false` が返された場合に、DSC によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="85860-140">It is called by DSC if the `TestScript` script block returns `$false`.</span></span> <span data-ttu-id="85860-141">`SetScript` には、戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="85860-141">The `SetScript` should have no return value.</span></span>

## <a name="examples"></a><span data-ttu-id="85860-142">例</span><span class="sxs-lookup"><span data-stu-id="85860-142">Examples</span></span>

### <a name="example-1-write-sample-text-using-a-script-resource"></a><span data-ttu-id="85860-143">例 1:Script リソースを使用して、サンプル テキストを作成する</span><span class="sxs-lookup"><span data-stu-id="85860-143">Example 1: Write sample text using a Script resource</span></span>

<span data-ttu-id="85860-144">この例では、各ノード上の `C:\TempFolder\TestFile.txt` の有無についてテストします。</span><span class="sxs-lookup"><span data-stu-id="85860-144">This example tests for the existence of `C:\TempFolder\TestFile.txt` on each node.</span></span> <span data-ttu-id="85860-145">このファイルがない場合は、`SetScript` を使用してファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="85860-145">If it does not exist, it creates it using the `SetScript`.</span></span> <span data-ttu-id="85860-146">`GetScript` はファイルのコンテンツを返し、その戻り値は使用されません。</span><span class="sxs-lookup"><span data-stu-id="85860-146">The `GetScript` returns the contents of the file, and its return value is not used.</span></span>

```powershell
Configuration ScriptTest
{
    Import-DscResource –ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script ScriptExample
        {
            SetScript = {
                $sw = New-Object System.IO.StreamWriter("C:\TempFolder\TestFile.txt")
                $sw.WriteLine("Some sample string")
                $sw.Close()
            }
            TestScript = { Test-Path "C:\TempFolder\TestFile.txt" }
            GetScript = { @{ Result = (Get-Content C:\TempFolder\TestFile.txt) } }
        }
    }
}
```

### <a name="example-2-compare-version-information-using-a-script-resource"></a><span data-ttu-id="85860-147">例 2: Script リソースを使用してバージョン情報を比較する</span><span class="sxs-lookup"><span data-stu-id="85860-147">Example 2: Compare version information using a Script resource</span></span>

<span data-ttu-id="85860-148">この例は、オーサリング コンピューター上のテキスト ファイルから *compliant* バージョン情報を取得して、これを `$version` 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="85860-148">This example retrieves the *compliant* version information from a text file on the authoring computer and stores it in the `$version` variable.</span></span> <span data-ttu-id="85860-149">ノードの MOF ファイルを生成するときに、各スクリプト ブロックの `$using:version` 変数は、DSC によって `$version` 変数の値に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="85860-149">When generating the node's MOF file, DSC replaces the `$using:version` variables in each script block with the value of the `$version` variable.</span></span> <span data-ttu-id="85860-150">実行時に *compliant* バージョンが各ノード上のテキスト ファイルに格納され、以降の実行で比較され更新されます。</span><span class="sxs-lookup"><span data-stu-id="85860-150">During execution, the *compliant* version is stored in a text file on each Node and compared and updated on subsequent executions.</span></span>

```powershell
$version = Get-Content 'version.txt'

Configuration ScriptTest
{
    Import-DscResource –ModuleName 'PSDesiredStateConfiguration'

    Node localhost
    {
        Script UpdateConfigurationVersion
        {
            GetScript = {
                $currentVersion = Get-Content (Join-Path -Path $env:SYSTEMDRIVE -ChildPath 'version.txt')
                return @{ 'Result' = "$currentVersion" }
            }
            TestScript = {
                # Create and invoke a scriptblock using the $GetScript automatic variable, which contains a string representation of the GetScript.
                $state = [scriptblock]::Create($GetScript).Invoke()

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
}
```