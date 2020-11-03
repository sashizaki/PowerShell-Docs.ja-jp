---
description: PowerShell がコンソールプロンプトで入力を読み取る方法をカスタマイズする方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_psconsolehostreadline?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSConsoleHostReadLine
ms.openlocfilehash: 143fa763c109b5645f992c3bb0a3097a8b2d9e90
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220872"
---
# <a name="about_psconsolehostreadline"></a><span data-ttu-id="188a5-104">about_PSConsoleHostReadLine</span><span class="sxs-lookup"><span data-stu-id="188a5-104">about_PSConsoleHostReadLine</span></span>

## <a name="short-description"></a><span data-ttu-id="188a5-105">概要</span><span class="sxs-lookup"><span data-stu-id="188a5-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="188a5-106">PowerShell がコンソールプロンプトで入力を読み取る方法をカスタマイズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="188a5-106">Explains how to create a customize how PowerShell reads input at the console prompt.</span></span>

## <a name="long-description"></a><span data-ttu-id="188a5-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="188a5-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="188a5-108">Windows PowerShell 3.0 以降では、PSConsoleHostReadLine という名前の関数を記述できます。この関数は、コンソールの入力の既定の処理方法をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="188a5-108">Starting in Windows PowerShell 3.0, you can write a function named PSConsoleHostReadLine that overrides the default way that console input is processed.</span></span>

### <a name="examples"></a><span data-ttu-id="188a5-109">例</span><span class="sxs-lookup"><span data-stu-id="188a5-109">EXAMPLES</span></span>

<span data-ttu-id="188a5-110">次の例では、メモ帳を起動し、ユーザーが作成したテキストファイルから入力を取得します。</span><span class="sxs-lookup"><span data-stu-id="188a5-110">The following example launches Notepad and gets input from a text File that the user creates:</span></span>

```powershell
function PSConsoleHostReadLine
{
  $inputFile = Join-Path $env:TEMP PSConsoleHostReadLine
  Set-Content $inputFile "PS > "

  # Notepad opens. Enter your command in it, save the file, and then exit.
  notepad $inputFile | Out-Null
  $userInput = Get-Content $inputFile
  $resultingCommand = $userInput.Replace("PS >", "")
  $resultingCommand
}
```

### <a name="remarks"></a><span data-ttu-id="188a5-111">REMARKS</span><span class="sxs-lookup"><span data-stu-id="188a5-111">REMARKS</span></span>

<span data-ttu-id="188a5-112">既定では、PowerShell はコンソールから入力を読み取ります。このモードでは、Windows コンソールサブシステムがすべての keypresses、F7 メニュー、およびその他の入力を処理します。</span><span class="sxs-lookup"><span data-stu-id="188a5-112">By default, PowerShell reads input from the console in what is known as "Cooked Mode" -- in which the Windows console subsystem handles all the keypresses, F7 menus, and other input.</span></span> <span data-ttu-id="188a5-113">Enter キーまたは Tab キーを押すと、その時点までに入力したテキストが PowerShell によって取得されます。</span><span class="sxs-lookup"><span data-stu-id="188a5-113">When you press Enter or Tab, PowerShell gets the text that you have typed up to that point.</span></span> <span data-ttu-id="188a5-114">Ctrl + R、Ctrl + A、Ctrl + E、またはその他のキーを押したことを、Enter キーまたは Tab キーを押す前に確認することはできません。Windows PowerShell 3.0 では、PSConsoleHostReadLine 関数によってこの問題が解決されます。</span><span class="sxs-lookup"><span data-stu-id="188a5-114">There is no way for it to know that you pressed Ctrl-R, Ctrl-A, Ctrl-E, or any other keys before pressing Enter or Tab. In Windows PowerShell 3.0, the PSConsoleHostReadLine function solves this issue.</span></span> <span data-ttu-id="188a5-115">PowerShell コンソールホストで PSConsoleHostReadline という名前の関数を定義すると、PowerShell は "調理モード" 入力機構ではなく、その関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="188a5-115">When you define a function named PSConsoleHostReadline in the PowerShell console host, PowerShell calls that function instead of the "Cooked Mode" input mechanism.</span></span>

### <a name="see-also"></a><span data-ttu-id="188a5-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="188a5-116">SEE ALSO</span></span>

[<span data-ttu-id="188a5-117">about_Prompts</span><span class="sxs-lookup"><span data-stu-id="188a5-117">about_Prompts</span></span>](about_Prompts.md)

