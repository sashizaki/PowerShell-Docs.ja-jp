---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: 29a72bac55dd4aabca52673a192b13f75b88f308
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209031"
---
# <span data-ttu-id="e3787-103">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="e3787-103">Exit-PSHostProcess</span></span>

## <span data-ttu-id="e3787-104">概要</span><span class="sxs-lookup"><span data-stu-id="e3787-104">SYNOPSIS</span></span>
<span data-ttu-id="e3787-105">ローカルプロセスで対話型セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="e3787-105">Closes an interactive session with a local process.</span></span>

## <span data-ttu-id="e3787-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e3787-106">SYNTAX</span></span>

```
Exit-PSHostProcess [<CommonParameters>]
```

## <span data-ttu-id="e3787-107">Description</span><span class="sxs-lookup"><span data-stu-id="e3787-107">DESCRIPTION</span></span>
<span data-ttu-id="e3787-108">**Enter-pshostprocess** コマンドレットは、Enter-PSHostProcess コマンドレットを実行して、開いたローカルプロセスとの対話型セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="e3787-108">The **Exit-PSHostProcess** cmdlet closes an interactive session with a local process that you have opened by running the Enter-PSHostProcess cmdlet.</span></span>
<span data-ttu-id="e3787-109">プロセス内で実行されているスクリプトのデバッグまたはトラブルシューティングが完了したら、プロセス内から **enter-pshostprocess** コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e3787-109">You run the **Exit-PSHostProcess** cmdlet from within the process, when you are finished debugging or troubleshooting a script that is running within a process.</span></span>

## <span data-ttu-id="e3787-110">例</span><span class="sxs-lookup"><span data-stu-id="e3787-110">EXAMPLES</span></span>

### <span data-ttu-id="e3787-111">例 1: プロセスを終了する</span><span class="sxs-lookup"><span data-stu-id="e3787-111">Example 1: Exit a process</span></span>

```
PS C:\> [Process:1520]: PS C:\>  Exit-PSHostProcess
PS C:\>
```

<span data-ttu-id="e3787-112">この例では、「Enter-pshostprocess」で説明されているように、プロセス内の実行空間で実行されているスクリプトをデバッグするために、アクティブプロセスで作業しています。</span><span class="sxs-lookup"><span data-stu-id="e3787-112">In this example, you have been working in an active process to debug a script running in a runspace in the process, as described in Enter-PSHostProcess.</span></span>
<span data-ttu-id="e3787-113">デバッガーを終了する **終了** コマンドを入力した後、 **enter-pshostprocess** コマンドレットを実行して、プロセスとの対話型セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="e3787-113">After you type the **exit** command to exit the debugger, run the **Exit-PSHostProcess** cmdlet to close your interactive session with the process.</span></span>
<span data-ttu-id="e3787-114">このコマンドレットは、プロセス内のセッションを閉じ、PS C: プロンプトに戻り \\ \> ます。</span><span class="sxs-lookup"><span data-stu-id="e3787-114">The cmdlet closes your session in the process, and returns you to the PS C:\\\> prompt.</span></span>

## <span data-ttu-id="e3787-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e3787-115">PARAMETERS</span></span>

### <span data-ttu-id="e3787-116">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e3787-116">CommonParameters</span></span>
<span data-ttu-id="e3787-117">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e3787-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e3787-118">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3787-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e3787-119">入力</span><span class="sxs-lookup"><span data-stu-id="e3787-119">INPUTS</span></span>

## <span data-ttu-id="e3787-120">出力</span><span class="sxs-lookup"><span data-stu-id="e3787-120">OUTPUTS</span></span>

## <span data-ttu-id="e3787-121">注</span><span class="sxs-lookup"><span data-stu-id="e3787-121">NOTES</span></span>

## <span data-ttu-id="e3787-122">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e3787-122">RELATED LINKS</span></span>

[<span data-ttu-id="e3787-123">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="e3787-123">Enter-PSHostProcess</span></span>](Enter-PSHostProcess.md)
