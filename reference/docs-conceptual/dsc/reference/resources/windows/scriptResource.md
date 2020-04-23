---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Script リソース
ms.openlocfilehash: e09e86011fa7dbb2a4d7f28b5032b4328b6f6ec2
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953069"
---
# <a name="dsc-script-resource"></a><span data-ttu-id="387b6-103">DSC Script リソース</span><span class="sxs-lookup"><span data-stu-id="387b6-103">DSC Script Resource</span></span>

> <span data-ttu-id="387b6-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="387b6-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="387b6-105">Windows PowerShell Desired State Configuration (DSC) の **Script** リソースは、ターゲット ノードで Windows PowerShell スクリプトのブロックを実行するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="387b6-105">The **Script** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to run Windows PowerShell script blocks on target nodes.</span></span> <span data-ttu-id="387b6-106">**Script** リソースでは、対応する DSC 状態操作を実行するために、定義するスクリプト ブロックを含む **GetScript**、**SetScript**、および **TestScript** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="387b6-106">The **Script** resource uses **GetScript**, **SetScript**, and **TestScript** properties that contain script blocks you define to perform the corresponding DSC state operations.</span></span>

## <a name="syntax"></a><span data-ttu-id="387b6-107">構文</span><span class="sxs-lookup"><span data-stu-id="387b6-107">Syntax</span></span>

```Syntax
Script [string] #ResourceName
{
    GetScript = [string]
    SetScript = [string]
    TestScript = [string]
    [ Credential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

> [!NOTE]
> <span data-ttu-id="387b6-108">**GetScript**、**TestScript**、および **SetScript** ブロックは文字列として格納されます。</span><span class="sxs-lookup"><span data-stu-id="387b6-108">**GetScript**, **TestScript**, and **SetScript** blocks are stored as strings.</span></span>

## <a name="properties"></a><span data-ttu-id="387b6-109">Properties</span><span class="sxs-lookup"><span data-stu-id="387b6-109">Properties</span></span>

|<span data-ttu-id="387b6-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="387b6-110">Property</span></span> |<span data-ttu-id="387b6-111">説明</span><span class="sxs-lookup"><span data-stu-id="387b6-111">Description</span></span> |
|---|---|
|<span data-ttu-id="387b6-112">GetScript</span><span class="sxs-lookup"><span data-stu-id="387b6-112">GetScript</span></span> |<span data-ttu-id="387b6-113">ノードの現在の状態を返すスクリプト ブロック。</span><span class="sxs-lookup"><span data-stu-id="387b6-113">A script block that returns the current state of the Node.</span></span> |
|<span data-ttu-id="387b6-114">SetScript</span><span class="sxs-lookup"><span data-stu-id="387b6-114">SetScript</span></span> |<span data-ttu-id="387b6-115">ノードが目的の状態になっていない場合に、コンプライアンスを適用するために DSC が使用するスクリプト ブロック。</span><span class="sxs-lookup"><span data-stu-id="387b6-115">A script block that DSC uses to enforce compliance when the Node is not in the desired state.</span></span> |
|<span data-ttu-id="387b6-116">TestScript</span><span class="sxs-lookup"><span data-stu-id="387b6-116">TestScript</span></span> |<span data-ttu-id="387b6-117">ノードが目的の状態になっているかどうかを判定するスクリプト ブロック。</span><span class="sxs-lookup"><span data-stu-id="387b6-117">A script block that determines if the Node is in the desired state.</span></span> |
|<span data-ttu-id="387b6-118">資格情報</span><span class="sxs-lookup"><span data-stu-id="387b6-118">Credential</span></span> |<span data-ttu-id="387b6-119">資格情報が必要な場合、このスクリプトの実行に使用する資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="387b6-119">Indicates the credentials to use for running this script, if credentials are required.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="387b6-120">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="387b6-120">Common properties</span></span>

|<span data-ttu-id="387b6-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="387b6-121">Property</span></span> |<span data-ttu-id="387b6-122">説明</span><span class="sxs-lookup"><span data-stu-id="387b6-122">Description</span></span> |
|---|---|
|<span data-ttu-id="387b6-123">DependsOn</span><span class="sxs-lookup"><span data-stu-id="387b6-123">DependsOn</span></span> |<span data-ttu-id="387b6-124">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="387b6-124">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="387b6-125">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="387b6-125">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="387b6-126">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="387b6-126">PsDscRunAsCredential</span></span> |<span data-ttu-id="387b6-127">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="387b6-127">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="387b6-128">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="387b6-128">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="387b6-129">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="387b6-129">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

### <a name="additional-information"></a><span data-ttu-id="387b6-130">関連情報</span><span class="sxs-lookup"><span data-stu-id="387b6-130">Additional information</span></span>

#### <a name="getscript"></a><span data-ttu-id="387b6-131">GetScript</span><span class="sxs-lookup"><span data-stu-id="387b6-131">GetScript</span></span>

<span data-ttu-id="387b6-132">DSC では **GetScript** からの出力が使用されません。</span><span class="sxs-lookup"><span data-stu-id="387b6-132">DSC does not use the output from **GetScript**.</span></span> <span data-ttu-id="387b6-133">[Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) コマンドレットでは **GetScript** を実行してノードの現在の状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="387b6-133">The [Get-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet executes **GetScript** to retrieve a node's current state.</span></span> <span data-ttu-id="387b6-134">**GetScript** からの戻り値は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="387b6-134">A return value is not required from **GetScript**.</span></span> <span data-ttu-id="387b6-135">戻り値を指定する場合は、値が String の **Result** キーを含むハッシュテーブルにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="387b6-135">If you specify a return value, it must be a hashtable containing a **Result** key whose value is a String.</span></span>

#### <a name="testscript"></a><span data-ttu-id="387b6-136">TestScript</span><span class="sxs-lookup"><span data-stu-id="387b6-136">TestScript</span></span>

<span data-ttu-id="387b6-137">**TestScript** は DSC によって実行され、**SetScript** を実行する必要があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="387b6-137">**TestScript** is executed by DSC to determine if **SetScript** should be run.</span></span> <span data-ttu-id="387b6-138">**TestScript** から `$false` が返される場合、DSC では **SetScript** を実行してノードを目的の状態に戻します。</span><span class="sxs-lookup"><span data-stu-id="387b6-138">If **TestScript** returns `$false`, DSC executes **SetScript** to bring the node back to the desired state.</span></span> <span data-ttu-id="387b6-139">ブール値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="387b6-139">It must return a boolean value.</span></span> <span data-ttu-id="387b6-140">結果が `$true` の場合、ノードが準拠しており **SetScript** が実行されるべきではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="387b6-140">A result of `$true` indicates that the node is compliant and **SetScript** should not executed.</span></span>

<span data-ttu-id="387b6-141">[Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) コマンドレットでは、**TestScript** を実行して、**Script** リソースに準拠しているノードを取得します。</span><span class="sxs-lookup"><span data-stu-id="387b6-141">The [Test-DscConfiguration](/powershell/module/PSDesiredStateConfiguration/Test-DscConfiguration) cmdlet, executes **TestScript** to retrieve the nodes compliance with the **Script** resources.</span></span>
<span data-ttu-id="387b6-142">ただし、この場合、**TestScript** がどのように返されるかに関係なく、**SetScript** は実行されません。</span><span class="sxs-lookup"><span data-stu-id="387b6-142">However, in this case, **SetScript** does not run, no matter what **TestScript** block returns.</span></span>

> [!NOTE]
> <span data-ttu-id="387b6-143">**TestScript** のすべての出力が戻り値の一部になります。</span><span class="sxs-lookup"><span data-stu-id="387b6-143">All output from your **TestScript** is part of its return value.</span></span> <span data-ttu-id="387b6-144">PowerShell は、抑制されていない出力を非ゼロとして解釈します。これは、ノードの状態に関係なく、**TestScript** から `$true` が返されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="387b6-144">PowerShell interprets unsuppressed output as non-zero, which means that your **TestScript** will return `$true` regardless of your node's state.</span></span> <span data-ttu-id="387b6-145">これにより、誤検知という予期しない結果となり、トラブルシューティングの際に困難が生じます。</span><span class="sxs-lookup"><span data-stu-id="387b6-145">This results in unpredictable results, false positives, and causes difficulty during troubleshooting.</span></span>

#### <a name="setscript"></a><span data-ttu-id="387b6-146">SetScript</span><span class="sxs-lookup"><span data-stu-id="387b6-146">SetScript</span></span>

<span data-ttu-id="387b6-147">**SetScript** ではノードを変更して、目的の状態を適用します。</span><span class="sxs-lookup"><span data-stu-id="387b6-147">**SetScript** modifies the node to enforce the desired state.</span></span> <span data-ttu-id="387b6-148">**TestScript** スクリプト ブロックから `$false` が返される場合、これが DSC によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="387b6-148">It is called by DSC if the **TestScript** script block returns `$false`.</span></span> <span data-ttu-id="387b6-149">**SetScript** には戻り値がありません。</span><span class="sxs-lookup"><span data-stu-id="387b6-149">The **SetScript** should have no return value.</span></span>

## <a name="examples"></a><span data-ttu-id="387b6-150">例</span><span class="sxs-lookup"><span data-stu-id="387b6-150">Examples</span></span>

### <a name="example-1-write-sample-text-using-a-script-resource"></a><span data-ttu-id="387b6-151">例 1: Script リソースを使用して、サンプル テキストを作成する</span><span class="sxs-lookup"><span data-stu-id="387b6-151">Example 1: Write sample text using a Script resource</span></span>

<span data-ttu-id="387b6-152">この例では、各ノード上の `C:\TempFolder\TestFile.txt` の有無についてテストします。</span><span class="sxs-lookup"><span data-stu-id="387b6-152">This example tests for the existence of `C:\TempFolder\TestFile.txt` on each node.</span></span> <span data-ttu-id="387b6-153">このファイルがない場合は、`SetScript` を使用してファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="387b6-153">If it does not exist, it creates it using the `SetScript`.</span></span> <span data-ttu-id="387b6-154">`GetScript` はファイルのコンテンツを返し、その戻り値は使用されません。</span><span class="sxs-lookup"><span data-stu-id="387b6-154">The `GetScript` returns the contents of the file, and its return value is not used.</span></span>

```powershell
Configuration ScriptTest
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

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

### <a name="example-2-compare-version-information-using-a-script-resource"></a><span data-ttu-id="387b6-155">例 2: Script リソースを使用してバージョン情報を比較する</span><span class="sxs-lookup"><span data-stu-id="387b6-155">Example 2: Compare version information using a Script resource</span></span>

<span data-ttu-id="387b6-156">この例は、オーサリング コンピューター上のテキスト ファイルから *compliant* バージョン情報を取得して、これを `$version` 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="387b6-156">This example retrieves the *compliant* version information from a text file on the authoring computer and stores it in the `$version` variable.</span></span> <span data-ttu-id="387b6-157">ノードの MOF ファイルを生成するときに、各スクリプト ブロックの `$using:version` 変数は、DSC によって `$version` 変数の値に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="387b6-157">When generating the node's MOF file, DSC replaces the `$using:version` variables in each script block with the value of the `$version` variable.</span></span>
<span data-ttu-id="387b6-158">実行時に *compliant* バージョンが各ノード上のテキスト ファイルに格納され、以降の実行で比較され更新されます。</span><span class="sxs-lookup"><span data-stu-id="387b6-158">During execution, the *compliant* version is stored in a text file on each Node and compared and updated on subsequent executions.</span></span>

```powershell
$version = Get-Content 'version.txt'

Configuration ScriptTest
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

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