---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 11/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/exit-pshostprocess?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Exit-PSHostProcess
ms.openlocfilehash: a1a8c6fcc16bcddc3bfcdade56cd75aadd179b74
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600996"
---
# <span data-ttu-id="24a56-102">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="24a56-102">Exit-PSHostProcess</span></span>

## <span data-ttu-id="24a56-103">概要</span><span class="sxs-lookup"><span data-stu-id="24a56-103">SYNOPSIS</span></span>
<span data-ttu-id="24a56-104">ローカルプロセスで対話型セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="24a56-104">Closes an interactive session with a local process.</span></span>

## <span data-ttu-id="24a56-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="24a56-105">SYNTAX</span></span>

```
Exit-PSHostProcess [<CommonParameters>]
```

## <span data-ttu-id="24a56-106">Description</span><span class="sxs-lookup"><span data-stu-id="24a56-106">DESCRIPTION</span></span>

<span data-ttu-id="24a56-107">コマンドレットでは、 `Exit-PSHostProcess` コマンドレットを実行して、開いたローカルプロセスとの対話型セッションを閉じ `Enter-PSHostProcess` ます。</span><span class="sxs-lookup"><span data-stu-id="24a56-107">The `Exit-PSHostProcess` cmdlet closes an interactive session with a local process that you have opened by running the `Enter-PSHostProcess` cmdlet.</span></span> <span data-ttu-id="24a56-108">プロセス内で `Exit-PSHostProcess` 実行されているスクリプトのデバッグまたはトラブルシューティングが完了したら、プロセス内からこのコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="24a56-108">You run the `Exit-PSHostProcess` cmdlet from within the process, when you are finished debugging or troubleshooting a script that is running within a process.</span></span> <span data-ttu-id="24a56-109">PowerShell 6.2 以降では、このコマンドレットは Windows 以外のプラットフォームでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="24a56-109">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="24a56-110">例</span><span class="sxs-lookup"><span data-stu-id="24a56-110">EXAMPLES</span></span>

### <span data-ttu-id="24a56-111">例 1: プロセスを終了する</span><span class="sxs-lookup"><span data-stu-id="24a56-111">Example 1: Exit a process</span></span>

```
[Process:1520]: PS>  Exit-PSHostProcess
PS>
```

<span data-ttu-id="24a56-112">この例では、「」で説明されているように、プロセス内の実行空間で実行されているスクリプトをデバッグするために、アクティブなプロセスで作業してい `Enter-PSHostProcess` ます。</span><span class="sxs-lookup"><span data-stu-id="24a56-112">In this example, you have been working in an active process to debug a script running in a runspace in the process, as described in `Enter-PSHostProcess`.</span></span> <span data-ttu-id="24a56-113">デバッガーを終了するコマンドを入力した後 `exit` 、コマンドレットを実行して `Exit-PSHostProcess` 、プロセスとの対話型セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="24a56-113">After you type the `exit` command to exit the debugger, run the `Exit-PSHostProcess` cmdlet to close your interactive session with the process.</span></span>
<span data-ttu-id="24a56-114">コマンドレットでは、プロセス内のセッションを閉じ、プロンプトに戻り `PS C:\>` ます。</span><span class="sxs-lookup"><span data-stu-id="24a56-114">The cmdlet closes your session in the process, and returns you to the `PS C:\>` prompt.</span></span>

## <span data-ttu-id="24a56-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="24a56-115">PARAMETERS</span></span>

### <span data-ttu-id="24a56-116">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="24a56-116">CommonParameters</span></span>

<span data-ttu-id="24a56-117">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="24a56-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="24a56-118">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24a56-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="24a56-119">入力</span><span class="sxs-lookup"><span data-stu-id="24a56-119">INPUTS</span></span>

## <span data-ttu-id="24a56-120">出力</span><span class="sxs-lookup"><span data-stu-id="24a56-120">OUTPUTS</span></span>

## <span data-ttu-id="24a56-121">注</span><span class="sxs-lookup"><span data-stu-id="24a56-121">NOTES</span></span>

## <span data-ttu-id="24a56-122">関連リンク</span><span class="sxs-lookup"><span data-stu-id="24a56-122">RELATED LINKS</span></span>

[<span data-ttu-id="24a56-123">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="24a56-123">Enter-PSHostProcess</span></span>](Enter-PSHostProcess.md)

