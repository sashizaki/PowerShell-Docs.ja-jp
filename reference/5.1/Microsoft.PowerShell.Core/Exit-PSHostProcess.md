---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: 6b6d95484ee2aec6fba60f5528a6ef6089d888a0
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342316"
---
# <span data-ttu-id="e30b0-103">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="e30b0-103">Exit-PSHostProcess</span></span>

## <span data-ttu-id="e30b0-104">概要</span><span class="sxs-lookup"><span data-stu-id="e30b0-104">SYNOPSIS</span></span>
<span data-ttu-id="e30b0-105">ローカルプロセスで対話型セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="e30b0-105">Closes an interactive session with a local process.</span></span>

## <span data-ttu-id="e30b0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e30b0-106">SYNTAX</span></span>

```
Exit-PSHostProcess [<CommonParameters>]
```

## <span data-ttu-id="e30b0-107">Description</span><span class="sxs-lookup"><span data-stu-id="e30b0-107">DESCRIPTION</span></span>

<span data-ttu-id="e30b0-108">コマンドレットでは、 `Exit-PSHostProcess` コマンドレットを実行して、開いたローカルプロセスとの対話型セッションを閉じ `Enter-PSHostProcess` ます。</span><span class="sxs-lookup"><span data-stu-id="e30b0-108">The `Exit-PSHostProcess` cmdlet closes an interactive session with a local process that you have opened by running the `Enter-PSHostProcess` cmdlet.</span></span> <span data-ttu-id="e30b0-109">プロセス内で `Exit-PSHostProcess` 実行されているスクリプトのデバッグまたはトラブルシューティングが完了したら、プロセス内からこのコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e30b0-109">You run the `Exit-PSHostProcess` cmdlet from within the process, when you are finished debugging or troubleshooting a script that is running within a process.</span></span> <span data-ttu-id="e30b0-110">PowerShell 6.2 以降では、このコマンドレットは Windows 以外のプラットフォームでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e30b0-110">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="e30b0-111">例</span><span class="sxs-lookup"><span data-stu-id="e30b0-111">EXAMPLES</span></span>

### <span data-ttu-id="e30b0-112">例 1: プロセスを終了する</span><span class="sxs-lookup"><span data-stu-id="e30b0-112">Example 1: Exit a process</span></span>

```
PS C:\> [Process:1520]: PS C:\>  Exit-PSHostProcess
PS C:\>
```

<span data-ttu-id="e30b0-113">この例では、「」で説明されているように、プロセス内の実行空間で実行されているスクリプトをデバッグするために、アクティブなプロセスで作業してい `Enter-PSHostProcess` ます。</span><span class="sxs-lookup"><span data-stu-id="e30b0-113">In this example, you have been working in an active process to debug a script running in a runspace in the process, as described in `Enter-PSHostProcess`.</span></span> <span data-ttu-id="e30b0-114">デバッガーを終了するコマンドを入力した後 `exit` 、コマンドレットを実行して `Exit-PSHostProcess` 、プロセスとの対話型セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="e30b0-114">After you type the `exit` command to exit the debugger, run the `Exit-PSHostProcess` cmdlet to close your interactive session with the process.</span></span>
<span data-ttu-id="e30b0-115">コマンドレットでは、プロセス内のセッションを閉じ、プロンプトに戻り `PS C:\>` ます。</span><span class="sxs-lookup"><span data-stu-id="e30b0-115">The cmdlet closes your session in the process, and returns you to the `PS C:\>` prompt.</span></span>

## <span data-ttu-id="e30b0-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e30b0-116">PARAMETERS</span></span>

### <span data-ttu-id="e30b0-117">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e30b0-117">CommonParameters</span></span>

<span data-ttu-id="e30b0-118">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e30b0-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e30b0-119">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e30b0-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e30b0-120">入力</span><span class="sxs-lookup"><span data-stu-id="e30b0-120">INPUTS</span></span>

## <span data-ttu-id="e30b0-121">出力</span><span class="sxs-lookup"><span data-stu-id="e30b0-121">OUTPUTS</span></span>

## <span data-ttu-id="e30b0-122">注</span><span class="sxs-lookup"><span data-stu-id="e30b0-122">NOTES</span></span>

## <span data-ttu-id="e30b0-123">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e30b0-123">RELATED LINKS</span></span>

[<span data-ttu-id="e30b0-124">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="e30b0-124">Enter-PSHostProcess</span></span>](Enter-PSHostProcess.md)
