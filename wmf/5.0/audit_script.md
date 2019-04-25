---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 28cd186ab3a08a0da4ff81f5a21514f239770d13
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058082"
---
# <a name="script-tracing-and-logging"></a><span data-ttu-id="cd208-102">スクリプトのトレースとログ</span><span class="sxs-lookup"><span data-stu-id="cd208-102">Script Tracing and Logging</span></span>

<span data-ttu-id="cd208-103">Windows PowerShell には、コマンドレットの呼び出しをログに記録する **LogPipelineExecutionDetails** グループ ポリシー設定が既に備えられていますが、PowerShell のスクリプト言語には、ログへの記録や監査の対象とする可能性がある機能が数多く含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd208-103">While Windows PowerShell already has the **LogPipelineExecutionDetails** Group Policy setting to log the invocation of cmdlets, PowerShell’s scripting language has plenty of features that you might want to log and/or audit.</span></span> <span data-ttu-id="cd208-104">新しい詳細スクリプト トレース機能では、システムで使用される Windows PowerShell スクリプトの詳細な追跡や分析を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cd208-104">The new Detailed Script Tracing feature lets you enable detailed tracking and analysis of Windows PowerShell scripting use on a system.</span></span> <span data-ttu-id="cd208-105">詳細なスクリプト トレースを有効にすると、Windows PowerShell はすべてのスクリプト ブロックを ETW イベント ログ **Microsoft-Windows-PowerShell/Operational** に記録します。</span><span class="sxs-lookup"><span data-stu-id="cd208-105">After you enable detailed script tracing, Windows PowerShell logs all script blocks to the ETW event log, **Microsoft-Windows-PowerShell/Operational**.</span></span> <span data-ttu-id="cd208-106">スクリプト ブロックによって別のスクリプト ブロックが作成される場合 (たとえば、文字列で Invoke-Expression コマンドレットを呼び出すスクリプト)、その結果として得られるスクリプト ブロックも記録されます。</span><span class="sxs-lookup"><span data-stu-id="cd208-106">If a script block creates another script block (for example, a script that calls the Invoke-Expression cmdlet on a string), that resulting script block is logged as well.</span></span>

<span data-ttu-id="cd208-107">これらのイベントのログ記録は、**[PowerShell スクリプト ブロックのログ記録を有効にする]** グループ ポリシー設定 ([管理用テンプレート] -> [Windows コンポーネント] -> [Windows PowerShell]) で有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cd208-107">Logging of these events can be enabled through the **Turn on PowerShell Script Block Logging** Group Policy setting (in Administrative Templates -> Windows Components -> Windows PowerShell).</span></span>

<span data-ttu-id="cd208-108">イベントは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cd208-108">The events are:</span></span>

| <span data-ttu-id="cd208-109">［チャネル］</span><span class="sxs-lookup"><span data-stu-id="cd208-109">Channel</span></span> | <span data-ttu-id="cd208-110">Operational</span><span class="sxs-lookup"><span data-stu-id="cd208-110">Operational</span></span>                                 |
|---------|---------------------------------------------|
| <span data-ttu-id="cd208-111">レベル</span><span class="sxs-lookup"><span data-stu-id="cd208-111">Level</span></span>   | <span data-ttu-id="cd208-112">Verbose</span><span class="sxs-lookup"><span data-stu-id="cd208-112">Verbose</span></span>                                     |
| <span data-ttu-id="cd208-113">オペコード</span><span class="sxs-lookup"><span data-stu-id="cd208-113">Opcode</span></span>  | <span data-ttu-id="cd208-114">作成</span><span class="sxs-lookup"><span data-stu-id="cd208-114">Create</span></span>                                      |
| <span data-ttu-id="cd208-115">タスク</span><span class="sxs-lookup"><span data-stu-id="cd208-115">Task</span></span>    | <span data-ttu-id="cd208-116">CommandStart</span><span class="sxs-lookup"><span data-stu-id="cd208-116">CommandStart</span></span>                                |
| <span data-ttu-id="cd208-117">キーワード</span><span class="sxs-lookup"><span data-stu-id="cd208-117">Keyword</span></span> | <span data-ttu-id="cd208-118">Runspace</span><span class="sxs-lookup"><span data-stu-id="cd208-118">Runspace</span></span>                                    |
| <span data-ttu-id="cd208-119">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cd208-119">EventId</span></span> | <span data-ttu-id="cd208-120">Engine_ScriptBlockCompiled (0x1008 = 4104)</span><span class="sxs-lookup"><span data-stu-id="cd208-120">Engine_ScriptBlockCompiled (0x1008 = 4104)</span></span>  |
| <span data-ttu-id="cd208-121">メッセージ</span><span class="sxs-lookup"><span data-stu-id="cd208-121">Message</span></span> | <span data-ttu-id="cd208-122">Creating Scriptblock text (%1 of %2):</span><span class="sxs-lookup"><span data-stu-id="cd208-122">Creating Scriptblock text (%1 of %2):</span></span> </br> <span data-ttu-id="cd208-123">%3</span><span class="sxs-lookup"><span data-stu-id="cd208-123">%3</span></span> </br> <span data-ttu-id="cd208-124">ScriptBlock ID: %4</span><span class="sxs-lookup"><span data-stu-id="cd208-124">ScriptBlock ID: %4</span></span> |


<span data-ttu-id="cd208-125">メッセージに埋め込まれたテキストは、コンパイルされたスクリプト ブロックの範囲です。</span><span class="sxs-lookup"><span data-stu-id="cd208-125">The text embedded in the message is the extent of the script block compiled.</span></span> <span data-ttu-id="cd208-126">ID は、スクリプト ブロックの有効期間に保持される GUID です。</span><span class="sxs-lookup"><span data-stu-id="cd208-126">The ID is a GUID that is retained for the life of the script block.</span></span>

<span data-ttu-id="cd208-127">詳細ログ記録の機能を有効にすると、次のように開始マーカーと終了マーカーが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="cd208-127">When you enable verbose logging, the feature writes begin and end markers:</span></span>

| <span data-ttu-id="cd208-128">［チャネル］</span><span class="sxs-lookup"><span data-stu-id="cd208-128">Channel</span></span> | <span data-ttu-id="cd208-129">Operational</span><span class="sxs-lookup"><span data-stu-id="cd208-129">Operational</span></span>                                            |
|---------|--------------------------------------------------------|
| <span data-ttu-id="cd208-130">レベル</span><span class="sxs-lookup"><span data-stu-id="cd208-130">Level</span></span>   | <span data-ttu-id="cd208-131">Verbose</span><span class="sxs-lookup"><span data-stu-id="cd208-131">Verbose</span></span>                                                |
| <span data-ttu-id="cd208-132">オペコード</span><span class="sxs-lookup"><span data-stu-id="cd208-132">Opcode</span></span>  | <span data-ttu-id="cd208-133">Open (/ Close)</span><span class="sxs-lookup"><span data-stu-id="cd208-133">Open (/ Close)</span></span>                                         |
| <span data-ttu-id="cd208-134">タスク</span><span class="sxs-lookup"><span data-stu-id="cd208-134">Task</span></span>    | <span data-ttu-id="cd208-135">CommandStart (/ CommandStop)</span><span class="sxs-lookup"><span data-stu-id="cd208-135">CommandStart (/ CommandStop)</span></span>                           |
| <span data-ttu-id="cd208-136">キーワード</span><span class="sxs-lookup"><span data-stu-id="cd208-136">Keyword</span></span> | <span data-ttu-id="cd208-137">Runspace</span><span class="sxs-lookup"><span data-stu-id="cd208-137">Runspace</span></span>                                               |
| <span data-ttu-id="cd208-138">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cd208-138">EventId</span></span> | <span data-ttu-id="cd208-139">ScriptBlock\_Invoke\_Start\_Detail (0x1009 = 4105) /</span><span class="sxs-lookup"><span data-stu-id="cd208-139">ScriptBlock\_Invoke\_Start\_Detail (0x1009 = 4105) /</span></span> </br> <span data-ttu-id="cd208-140">ScriptBlock\_Invoke\_Complete\_Detail (0x100A = 4106)</span><span class="sxs-lookup"><span data-stu-id="cd208-140">ScriptBlock\_Invoke\_Complete\_Detail (0x100A = 4106)</span></span> |
| <span data-ttu-id="cd208-141">メッセージ</span><span class="sxs-lookup"><span data-stu-id="cd208-141">Message</span></span> | <span data-ttu-id="cd208-142">Started (/ Completed) invocation of ScriptBlock ID: %1</span><span class="sxs-lookup"><span data-stu-id="cd208-142">Started (/ Completed) invocation of ScriptBlock ID: %1</span></span> </br> <span data-ttu-id="cd208-143">Runspace ID: %2</span><span class="sxs-lookup"><span data-stu-id="cd208-143">Runspace ID: %2</span></span> |

<span data-ttu-id="cd208-144">ID は (イベント ID 0x1008 に関連付けることができる) スクリプト ブロックを表す GUIDで、Runspace ID はこのスクリプト ブロックが実行された実行空間を表します。</span><span class="sxs-lookup"><span data-stu-id="cd208-144">The ID is the GUID representing the script block (that can be correlated with event ID 0x1008), and the Runspace ID represents the runspace in which this script block was run.</span></span>

<span data-ttu-id="cd208-145">呼び出しメッセージ内のパーセント記号は、構造化 ETW プロパティを表します。</span><span class="sxs-lookup"><span data-stu-id="cd208-145">Percent signs in the invocation message represent structured ETW properties.</span></span> <span data-ttu-id="cd208-146">これらはメッセージ テキストで実際の値に置き換えられますが、Get-WinEvent コマンドレットを使用してメッセージを取得し、メッセージの **Properties** 配列を使用すると、より信頼性の高い方法でそれらにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cd208-146">While they are replaced with the actual values in the message text, a more robust way to access them is to retrieve the message with the Get-WinEvent cmdlet, and then use the **Properties** array of the message.</span></span>

<span data-ttu-id="cd208-147">この機能を利用して、スクリプトを暗号化および難読化する悪意のある試みをラップ解除する方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cd208-147">Here's an example of how this functionality can help unwrap a malicious attempt to encrypt and obfuscate a script:</span></span>

```powershell
## Malware
function SuperDecrypt
{
    param($script)
    $bytes = [Convert]::FromBase64String($script)

    ## XOR “encryption”
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

<span data-ttu-id="cd208-148">このことを実行すると、次のログ エントリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="cd208-148">Running this generates the following log entries:</span></span>

```
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

スクリプト ブロックの長さが、ETW で単一のイベントに格納できる長さを超えた場合、Windows PowerShell はスクリプトを複数の部分に分割します。 <span data-ttu-id="cd208-150">ログ メッセージからスクリプトを再結合するサンプル コードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="cd208-150">Here is sample code to recombine a script from its log messages:</span></span>

```powershell
$created = Get-WinEvent -FilterHashtable @{ ProviderName="Microsoft-Windows-PowerShell"; Id = 4104 } | Where-Object { $_.<...> }
$sortedScripts = $created | sort { $_.Properties[0].Value }
$mergedScript = -join ($sortedScripts | % { $_.Properties[2].Value })
```

<span data-ttu-id="cd208-151">保持するバッファーが限られているすべてのログ システム (ETW ログなど) の場合と同様、このインフラストラクチャに対して、正しくないイベントでログを溢れさせて以前の証拠を隠す攻撃が行われる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd208-151">As with all logging systems that have a limited retention buffer (i.e. ETW logs), one attack against this infrastructure is to flood the log with spurious events to hide earlier evidence.</span></span> <span data-ttu-id="cd208-152">この攻撃から保護するには、何らかの形式のイベント ログ収集が設定されていることを確認し (つまり、Windows イベント転送、「[Spotting the Adversary with Windows Event Log Monitoring (Windows イベント ログ監視による敵対者の偵察)](https://www.iad.gov/iad/library/reports/spotting-the-adversary-with-windows-event-log-monitoring.cfm)」)、できるだけ早くコンピューターからイベント ログを移動します。</span><span class="sxs-lookup"><span data-stu-id="cd208-152">To protect yourself from this attack, ensure that you have some form of event log collection set up (i.e., Windows Event Forwarding, [Spotting the Adversary with Windows Event Log Monitoring](https://www.iad.gov/iad/library/reports/spotting-the-adversary-with-windows-event-log-monitoring.cfm)) to move event logs off of the computer as soon as possible.</span></span>
