---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
title: 情報ストリーム
ms.openlocfilehash: c54603cf0dd4f0b69f8147620130f9f29bc3e5ec
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71147612"
---
# <a name="information-stream"></a><span data-ttu-id="0bf84-103">情報ストリーム</span><span class="sxs-lookup"><span data-stu-id="0bf84-103">Information Stream</span></span>

<span data-ttu-id="0bf84-104">PowerShell 5.0 に、スクリプトとそのホストの間で構造化データを転送する新しい構造化された**情報**ストリームが追加されました。</span><span class="sxs-lookup"><span data-stu-id="0bf84-104">PowerShell 5.0 adds a new structured **Information** stream to transmit structured data between a script and its host.</span></span> <span data-ttu-id="0bf84-105">`Write-Host` も更新され、**情報**ストリームに送った出力をキャプチャしたり、サイレント状態にしたりできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0bf84-105">`Write-Host` has also been updated to emit its output to the **Information** stream where you can now capture or silence it.</span></span> <span data-ttu-id="0bf84-106">新しい `Write-Information` コマンドレットを **InformationVariable** および **InformationAction** 共通パラメーターと一緒に使うと、柔軟性と機能が向上します。</span><span class="sxs-lookup"><span data-stu-id="0bf84-106">The new `Write-Information` cmdlet used with **InformationVariable** and **InformationAction** common parameters enables more flexibility and capability.</span></span>

<span data-ttu-id="0bf84-107">次の関数では、新しい**情報**ストリームを利用するコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="0bf84-107">The following function uses cmdlets that take advantage of the new **Information** stream.</span></span>

```powershell
function OutputGusher {
  [CmdletBinding()]
  param()
  Write-Host -ForegroundColor Green 'Preparing to give you output!'
  Write-Host '============================='
  Write-Host 'I ' -ForegroundColor White -NoNewline
  Write-Host '<3 ' -ForegroundColor Red -NoNewline
  Write-Host 'Output' -ForegroundColor White
  Write-Host '============================='

  $p = Get-Process -id $pid
  $p

  Write-Information $p -Tag Process
  Write-Information 'Some spammy logging information' -Tag LogLow
  Write-Information 'Some important logging information' -Tag LogHigh

  Write-Host
  Write-Host -ForegroundColor Green 'SCRIPT COMPLETE!!'
}
```

<span data-ttu-id="0bf84-108">この関数の実行結果は、次の例のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0bf84-108">The following examples show the results of running this function.</span></span>

```powershell
$r = c:\temp\OutputGusher
```

```Output
Preparing to give you output!
=============================
I <3 Output
=============================

SCRIPT COMPLETE!!
```

<span data-ttu-id="0bf84-109">`$r` 変数がスクリプト変数 `$p` の処理情報をキャプチャしました。</span><span class="sxs-lookup"><span data-stu-id="0bf84-109">The `$r` variable has captured the process information in the script variable `$p`.</span></span>

```powershell
$r.Id
4008
```

<span data-ttu-id="0bf84-110">`Write-Host` の **InformationVariable** パラメーターを使用すると、`Write-Information` コマンドレットとは異なり、出力を変数にキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="0bf84-110">Unlike the `Write-Host` cmdlet, using the **InformationVariable** parameter of `Write-Information` allows you to capture the output in a variable.</span></span> <span data-ttu-id="0bf84-111">**タグ**を使用すると、**情報**ストリームに送信されたメッセージのチャネルを分けることができます。</span><span class="sxs-lookup"><span data-stu-id="0bf84-111">Using the **Tag**, you can create separate channels for message sent to the **Information** stream.</span></span>

```powershell
$r = OutputGusher -InformationVariable iv
$ivOutput = $iv | Group-Object -AsHash { $_.Tags[0] } -AsString
$ivOutput
```

```Output
Preparing to give you output!
=============================
I <3 Output
=============================
SCRIPT COMPLETE!!

Name                 Value
----                 -----
LogLow               {Some spammy logging information}
LogHigh              {Some important logging information}
Process              {System.Diagnostics.Process (powershell)}
PSHOST               {Preparing to give you output!, =============================, I , <3 ...}
```

<span data-ttu-id="0bf84-112">タグを使用して**情報**ストリームにメッセージを送ると、そのメッセージはホスト アプリケーションには表示されず、タグ名を使用して取得されるようになります。</span><span class="sxs-lookup"><span data-stu-id="0bf84-112">When you send a message to the **Information** stream with a tag, that message is not displayed in the host application but can be retrieved using the tag name.</span></span> <span data-ttu-id="0bf84-113">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0bf84-113">For example:</span></span>

```powershell
$iv | where Tags -eq 'LogHigh'
```

```Output
Some important logging information
```