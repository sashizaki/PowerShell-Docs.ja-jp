---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
title: スクリプトのトレースとログ
ms.openlocfilehash: 6b7e5022cb4c974da5ddb3d670b5808dc9fb7bdc
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71147802"
---
# <a name="script-tracing-and-logging"></a><span data-ttu-id="599ab-103">スクリプトのトレースとログ</span><span class="sxs-lookup"><span data-stu-id="599ab-103">Script Tracing and Logging</span></span>

<span data-ttu-id="599ab-104">PowerShell には、コマンドレットの呼び出しをログに記録する **LogPipelineExecutionDetails** グループ ポリシーの設定が既にありますが、PowerShell のスクリプト言語には、ログ記録や監査の対象にしたい場合がある機能がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="599ab-104">While PowerShell already has the **LogPipelineExecutionDetails** Group Policy setting to log the invocation of cmdlets, PowerShell's scripting language has several features that you might want to log and audit.</span></span> <span data-ttu-id="599ab-105">新しい詳細スクリプト トレース機能では、システムでの PowerShell スクリプト アクティビティの詳細な追跡や分析が提供されます。</span><span class="sxs-lookup"><span data-stu-id="599ab-105">The new Detailed Script Tracing feature provides detailed tracking and analysis of PowerShell script activity on a system.</span></span> <span data-ttu-id="599ab-106">詳細なスクリプト トレースを有効にすると、PowerShell ではすべてのスクリプト ブロックが ETW イベント ログ **Microsoft-Windows-PowerShell/Operational** に記録されます。</span><span class="sxs-lookup"><span data-stu-id="599ab-106">After enabling detailed script tracing, PowerShell logs all script blocks to the ETW event log, **Microsoft-Windows-PowerShell/Operational**.</span></span> <span data-ttu-id="599ab-107">スクリプト ブロックで別のスクリプト ブロックが作成された場合 (たとえば、`Invoke-Expression` を呼び出すことによって)、呼び出されたスクリプト ブロックも記録されます。</span><span class="sxs-lookup"><span data-stu-id="599ab-107">If a script block creates another script block, for example, by calling `Invoke-Expression`, the invoked script block also logged.</span></span>

<span data-ttu-id="599ab-108">ログ記録は、 **[管理用テンプレート]**  ->  **[Windows コンポーネント]**  ->  **[Windows PowerShell]** の **[PowerShell スクリプト ブロックのログ記録を有効にする]** グループ ポリシー設定で有効にします。</span><span class="sxs-lookup"><span data-stu-id="599ab-108">Logging is enabled through the **Turn on PowerShell Script Block Logging** Group Policy setting in **Administrative Templates** -> **Windows Components** -> **Windows PowerShell**.</span></span>

<span data-ttu-id="599ab-109">イベントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="599ab-109">The events are:</span></span>

| <span data-ttu-id="599ab-110">チャネル</span><span class="sxs-lookup"><span data-stu-id="599ab-110">Channel</span></span> |                               <span data-ttu-id="599ab-111">運用時</span><span class="sxs-lookup"><span data-stu-id="599ab-111">Operational</span></span>                               |
| ------- | ----------------------------------------------------------------------- |
| <span data-ttu-id="599ab-112">Level</span><span class="sxs-lookup"><span data-stu-id="599ab-112">Level</span></span>   | <span data-ttu-id="599ab-113">"詳細"</span><span class="sxs-lookup"><span data-stu-id="599ab-113">Verbose</span></span>                                                                 |
| <span data-ttu-id="599ab-114">オペコード</span><span class="sxs-lookup"><span data-stu-id="599ab-114">Opcode</span></span>  | <span data-ttu-id="599ab-115">作成</span><span class="sxs-lookup"><span data-stu-id="599ab-115">Create</span></span>                                                                  |
| <span data-ttu-id="599ab-116">タスク</span><span class="sxs-lookup"><span data-stu-id="599ab-116">Task</span></span>    | <span data-ttu-id="599ab-117">CommandStart</span><span class="sxs-lookup"><span data-stu-id="599ab-117">CommandStart</span></span>                                                            |
| <span data-ttu-id="599ab-118">Keyword</span><span class="sxs-lookup"><span data-stu-id="599ab-118">Keyword</span></span> | <span data-ttu-id="599ab-119">Runspace</span><span class="sxs-lookup"><span data-stu-id="599ab-119">Runspace</span></span>                                                                |
| <span data-ttu-id="599ab-120">EventId</span><span class="sxs-lookup"><span data-stu-id="599ab-120">EventId</span></span> | <span data-ttu-id="599ab-121">Engine_ScriptBlockCompiled (0x1008 = 4104)</span><span class="sxs-lookup"><span data-stu-id="599ab-121">Engine_ScriptBlockCompiled (0x1008 = 4104)</span></span>                              |
| <span data-ttu-id="599ab-122">Message</span><span class="sxs-lookup"><span data-stu-id="599ab-122">Message</span></span> | <span data-ttu-id="599ab-123">Creating Scriptblock text (%1 of %2):</span><span class="sxs-lookup"><span data-stu-id="599ab-123">Creating Scriptblock text (%1 of %2):</span></span> </br> <span data-ttu-id="599ab-124">%3</span><span class="sxs-lookup"><span data-stu-id="599ab-124">%3</span></span> </br> <span data-ttu-id="599ab-125">ScriptBlock ID: %4</span><span class="sxs-lookup"><span data-stu-id="599ab-125">ScriptBlock ID: %4</span></span> |


<span data-ttu-id="599ab-126">メッセージに埋め込まれたテキストは、コンパイルされたスクリプト ブロックの範囲です。</span><span class="sxs-lookup"><span data-stu-id="599ab-126">The text embedded in the message is the extent of the script block compiled.</span></span> <span data-ttu-id="599ab-127">ID は、スクリプト ブロックの有効期間に保持される GUID です。</span><span class="sxs-lookup"><span data-stu-id="599ab-127">The ID is a GUID that is retained for the life of the script block.</span></span>

<span data-ttu-id="599ab-128">詳細ログ記録の機能を有効にすると、次のように開始マーカーと終了マーカーが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="599ab-128">When you enable verbose logging, the feature writes begin and end markers:</span></span>

| <span data-ttu-id="599ab-129">チャネル</span><span class="sxs-lookup"><span data-stu-id="599ab-129">Channel</span></span> |                                 <span data-ttu-id="599ab-130">運用時</span><span class="sxs-lookup"><span data-stu-id="599ab-130">Operational</span></span>                                |
| ------- | -------------------------------------------------------------------------- |
| <span data-ttu-id="599ab-131">Level</span><span class="sxs-lookup"><span data-stu-id="599ab-131">Level</span></span>   | <span data-ttu-id="599ab-132">"詳細"</span><span class="sxs-lookup"><span data-stu-id="599ab-132">Verbose</span></span>                                                                    |
| <span data-ttu-id="599ab-133">オペコード</span><span class="sxs-lookup"><span data-stu-id="599ab-133">Opcode</span></span>  | <span data-ttu-id="599ab-134">Open / Close</span><span class="sxs-lookup"><span data-stu-id="599ab-134">Open / Close</span></span>                                                               |
| <span data-ttu-id="599ab-135">タスク</span><span class="sxs-lookup"><span data-stu-id="599ab-135">Task</span></span>    | <span data-ttu-id="599ab-136">CommandStart / CommandStop</span><span class="sxs-lookup"><span data-stu-id="599ab-136">CommandStart / CommandStop</span></span>                                                 |
| <span data-ttu-id="599ab-137">Keyword</span><span class="sxs-lookup"><span data-stu-id="599ab-137">Keyword</span></span> | <span data-ttu-id="599ab-138">Runspace</span><span class="sxs-lookup"><span data-stu-id="599ab-138">Runspace</span></span>                                                                   |
| <span data-ttu-id="599ab-139">EventId</span><span class="sxs-lookup"><span data-stu-id="599ab-139">EventId</span></span> | <span data-ttu-id="599ab-140">ScriptBlock\_Invoke\_Start\_Detail (0x1009 = 4105) /</span><span class="sxs-lookup"><span data-stu-id="599ab-140">ScriptBlock\_Invoke\_Start\_Detail (0x1009 = 4105) /</span></span> </br> <span data-ttu-id="599ab-141">ScriptBlock\_Invoke\_Complete\_Detail (0x100A = 4106)</span><span class="sxs-lookup"><span data-stu-id="599ab-141">ScriptBlock\_Invoke\_Complete\_Detail (0x100A = 4106)</span></span> |
| <span data-ttu-id="599ab-142">Message</span><span class="sxs-lookup"><span data-stu-id="599ab-142">Message</span></span> | <span data-ttu-id="599ab-143">Started / Completed invocation of ScriptBlock ID: %1</span><span class="sxs-lookup"><span data-stu-id="599ab-143">Started / Completed invocation of ScriptBlock ID: %1</span></span> </br> <span data-ttu-id="599ab-144">Runspace ID: %2</span><span class="sxs-lookup"><span data-stu-id="599ab-144">Runspace ID: %2</span></span> |

<span data-ttu-id="599ab-145">ID は (イベント ID 0x1008 に関連付けることができる) スクリプト ブロックを表す GUIDで、Runspace ID はこのスクリプト ブロックが実行された実行空間を表します。</span><span class="sxs-lookup"><span data-stu-id="599ab-145">The ID is the GUID representing the script block (that can be correlated with event ID 0x1008), and the Runspace ID represents the runspace in which this script block was run.</span></span>

<span data-ttu-id="599ab-146">呼び出しメッセージ内のパーセント記号は、構造化 ETW プロパティを表します。</span><span class="sxs-lookup"><span data-stu-id="599ab-146">Percent signs in the invocation message represent structured ETW properties.</span></span> <span data-ttu-id="599ab-147">これらはメッセージ テキストで実際の値に置き換えられますが、Get-WinEvent コマンドレットを使用してメッセージを取得し、メッセージの **Properties** 配列を使用すると、より信頼性の高い方法でそれらにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="599ab-147">While they are replaced with the actual values in the message text, a more robust way to access them is to retrieve the message with the Get-WinEvent cmdlet, and then use the **Properties** array of the message.</span></span>

<span data-ttu-id="599ab-148">この機能を利用して、スクリプトを暗号化および難読化する悪意のある試みをラップ解除する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="599ab-148">Here's an example of how this functionality can help unwrap a malicious attempt to encrypt and obfuscate a script:</span></span>

```powershell
## Malware
function SuperDecrypt
{
    param($script)
    $bytes = [Convert]::FromBase64String($script)

    ## XOR "encryption"
    $xorKey = 0x42
    for($counter = 0; $counter -lt $bytes.Length; $counter++)
    {
        $bytes[$counter] = $bytes[$counter] -bxor $xorKey
    }
    [System.Text.Encoding]::Unicode.GetString($bytes)
}

$decrypted = SuperDecrypt "FUIwQitCNkInQm9CCkItQjFCNkJiQmVCEkI1QixCJkJlQg=="
Invoke-Expression $decrypted
```

<span data-ttu-id="599ab-149">このことを実行すると、次のログ エントリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="599ab-149">Running this generates the following log entries:</span></span>

```Output
Compiling Scriptblock text (1 of 1):
function SuperDecrypt
{
    param($script)
    $bytes = [Convert]::FromBase64String($script)
    ## XOR "encryption"
    $xorKey = 0x42
    for($counter = 0; $counter -lt $bytes.Length; $counter++)
    {
        $bytes[$counter] = $bytes[$counter] -bxor $xorKey
    }
    [System.Text.Encoding]::Unicode.GetString($bytes)

}
ScriptBlock ID: ad8ae740-1f33-42aa-8dfc-1314411877e3

Compiling Scriptblock text (1 of 1):
$decrypted = SuperDecrypt "FUIwQitCNkInQm9CCkItQjFCNkJiQmVCEkI1QixCJkJlQg=="
ScriptBlock ID: ba11c155-d34c-4004-88e3-6502ecb50f52

Compiling Scriptblock text (1 of 1):
Invoke-Expression $decrypted
ScriptBlock ID: 856c01ca-85d7-4989-b47f-e6a09ee4eeb3

Compiling Scriptblock text (1 of 1):
Write-Host 'Pwnd'
ScriptBlock ID: 5e618414-4e77-48e3-8f65-9a863f54b4c8
```

スクリプト ブロックの長さが単一のイベントの容量を超える場合、PowerShell ではスクリプトが複数の部分に分割されます。 <span data-ttu-id="599ab-151">ログ メッセージからスクリプトを再結合するサンプル コードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="599ab-151">Here is sample code to recombine a script from its log messages:</span></span>

```powershell
$created = Get-WinEvent -FilterHashtable @{ ProviderName="Microsoft-Windows-PowerShell"; Id = 4104 } |
  Where-Object { $_.<...> }
$sortedScripts = $created | sort { $_.Properties[0].Value }
$mergedScript = -join ($sortedScripts | % { $_.Properties[2].Value })
```

<span data-ttu-id="599ab-152">保持するバッファーが限られているすべてのログ システムと同様、このインフラストラクチャを攻撃する 1 つの方法は、正しくないイベントでログを溢れさせて以前の証拠を隠すことです。</span><span class="sxs-lookup"><span data-stu-id="599ab-152">As with all logging systems that have a limited retention buffer, one way to attack this infrastructure is to flood the log with spurious events to hide earlier evidence.</span></span> <span data-ttu-id="599ab-153">この攻撃を防ぐには、Windows イベント転送に何らかの形式のイベント ログ コレクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="599ab-153">To protect yourself from this attack, ensure that you have some form of event log collection set up Windows Event Forwarding.</span></span> <span data-ttu-id="599ab-154">詳細については、「[Spotting the Adversary with Windows Event Log Monitoring](https://apps.nsa.gov/iaarchive/library/reports/spotting-the-adversary-with-windows-event-log-monitoring.cfm)」 (Windows イベント ログ監視による敵対者の偵察) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="599ab-154">For more information, see [Spotting the Adversary with Windows Event Log Monitoring](https://apps.nsa.gov/iaarchive/library/reports/spotting-the-adversary-with-windows-event-log-monitoring.cfm).</span></span>