---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-pscallstack?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSCallStack
ms.openlocfilehash: 315965d3103fc7064f522ca84c8aae77e90ceeb0
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209223"
---
# <span data-ttu-id="07431-103">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="07431-103">Get-PSCallStack</span></span>

## <span data-ttu-id="07431-104">概要</span><span class="sxs-lookup"><span data-stu-id="07431-104">SYNOPSIS</span></span>
<span data-ttu-id="07431-105">現在の呼び出し履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="07431-105">Displays the current call stack.</span></span>

## <span data-ttu-id="07431-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="07431-106">SYNTAX</span></span>

```
Get-PSCallStack [<CommonParameters>]
```

## <span data-ttu-id="07431-107">Description</span><span class="sxs-lookup"><span data-stu-id="07431-107">DESCRIPTION</span></span>

<span data-ttu-id="07431-108">**Get PSCallStack** コマンドレットは、現在の呼び出し履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="07431-108">The **Get-PSCallStack** cmdlet displays the current call stack.</span></span>

<span data-ttu-id="07431-109">PowerShell デバッガーで使用するように設計されていますが、このコマンドレットを使用すると、デバッガーの外部にあるスクリプトまたは関数で呼び出し履歴を表示できます。</span><span class="sxs-lookup"><span data-stu-id="07431-109">Although it is designed to be used with the PowerShell debugger, you can use this cmdlet to display the call stack in a script or function outside of the debugger.</span></span>

<span data-ttu-id="07431-110">デバッガーで **Get PSCallStack** コマンドを実行するには、またはを入力し `k` `Get-PSCallStack` ます。</span><span class="sxs-lookup"><span data-stu-id="07431-110">To run a **Get-PSCallStack** command while in the debugger, type `k` or `Get-PSCallStack`.</span></span>

## <span data-ttu-id="07431-111">例</span><span class="sxs-lookup"><span data-stu-id="07431-111">EXAMPLES</span></span>

### <span data-ttu-id="07431-112">例 1: 関数の呼び出し履歴を取得する</span><span class="sxs-lookup"><span data-stu-id="07431-112">Example 1: Get the call stack for a function</span></span>

```
PS C:\> function my-alias {
$p = $args[0]
Get-Alias | where {$_.definition -like "*$p"} | format-table definition, name -auto
}
PS C:\ps-test> Set-PSBreakpoint -Command my-alias
Command    : my-alias
Action     :
Enabled    : True
HitCount   : 0
Id         : 0
Script     : prompt PS C:\> my-alias Get-Content

Entering debug mode. Use h or ? for help.
Hit Command breakpoint on 'prompt:my-alias'
my-alias get-content
[DBG]: PS C:\ps-test> s
$p = $args[0]
DEBUG: Stepped to ':    $p = $args[0]    '
[DBG]: PS C:\ps-test> s
get-alias | Where {$_.Definition -like "*$p*"} | format-table Definition,
[DBG]: PS C:\ps-test>get-pscallstack

Name        CommandLineParameters         UnboundArguments              Location
----        ---------------------         ----------------              --------
prompt      {}                            {}                            prompt
my-alias    {}                            {get-content}                 prompt
prompt      {}                            {}                            prompt PS C:\> [DBG]: PS C:\ps-test> o
Definition  Name
----------  ----
Get-Content gc
Get-Content cat
Get-Content type
```

<span data-ttu-id="07431-113">このコマンドは、 **Get PSCallStack** コマンドレットを使用して、My エイリアスの呼び出し履歴を表示します。これは、コマンドレット名のエイリアスを取得する単純な関数です。</span><span class="sxs-lookup"><span data-stu-id="07431-113">This command uses the **Get-PSCallStack** cmdlet to display the call stack for My-Alias, a simple function that gets the aliases for a cmdlet name.</span></span>

<span data-ttu-id="07431-114">最初のコマンドは、PowerShell プロンプトで関数を入力します。</span><span class="sxs-lookup"><span data-stu-id="07431-114">The first command enters the function at the PowerShell prompt.</span></span>
<span data-ttu-id="07431-115">2 番目のコマンドは、Set-PSBreakpoint コマンドレットを使用して、My-Alias 関数にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="07431-115">The second command uses the Set-PSBreakpoint cmdlet to set a breakpoint on the My-Alias function.</span></span>
<span data-ttu-id="07431-116">3 番目のコマンドは、My-Alias 関数を使用して、Get-Content コマンドレットに対して現在のセッションのすべてのエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="07431-116">The third command uses the My-Alias function to get all of the aliases in the current session for the Get-Content cmdlet.</span></span>

<span data-ttu-id="07431-117">デバッガーは関数呼び出しに割り込みます。</span><span class="sxs-lookup"><span data-stu-id="07431-117">The debugger breaks in at the function call.</span></span>
<span data-ttu-id="07431-118">2 つの連続するステップイン (s) コマンドは、行ごとに関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="07431-118">Two consecutive step-into (s) commands begin executing the function line by line.</span></span>
<span data-ttu-id="07431-119">次に、 **Get PSCallStack** コマンドを使用して、呼び出し履歴を取得します。</span><span class="sxs-lookup"><span data-stu-id="07431-119">Then, a **Get-PSCallStack** command is used to retrieve the call stack.</span></span>

<span data-ttu-id="07431-120">最後のコマンドは、デバッガーを終了し、完了まで実行を継続する Step-Out コマンド (o) です。</span><span class="sxs-lookup"><span data-stu-id="07431-120">The final command is a Step-Out command (o) that exits the debugger and continues executing the script to completion.</span></span>

## <span data-ttu-id="07431-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="07431-121">PARAMETERS</span></span>

### <span data-ttu-id="07431-122">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="07431-122">CommonParameters</span></span>

<span data-ttu-id="07431-123">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="07431-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="07431-124">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07431-124">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="07431-125">入力</span><span class="sxs-lookup"><span data-stu-id="07431-125">INPUTS</span></span>

### <span data-ttu-id="07431-126">なし</span><span class="sxs-lookup"><span data-stu-id="07431-126">None</span></span>

<span data-ttu-id="07431-127">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="07431-127">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="07431-128">出力</span><span class="sxs-lookup"><span data-stu-id="07431-128">OUTPUTS</span></span>

### <span data-ttu-id="07431-129">CallStackFrame (システム管理)</span><span class="sxs-lookup"><span data-stu-id="07431-129">System.Management.Automation.CallStackFrame</span></span>

<span data-ttu-id="07431-130">**Get-PSCallStack** は、呼び出し履歴内の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="07431-130">**Get-PSCallStack** returns an object that represents the items in the call stack.</span></span>

## <span data-ttu-id="07431-131">注</span><span class="sxs-lookup"><span data-stu-id="07431-131">NOTES</span></span>

## <span data-ttu-id="07431-132">関連リンク</span><span class="sxs-lookup"><span data-stu-id="07431-132">RELATED LINKS</span></span>

[<span data-ttu-id="07431-133">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="07431-133">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="07431-134">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="07431-134">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="07431-135">Format-Table</span><span class="sxs-lookup"><span data-stu-id="07431-135">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="07431-136">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="07431-136">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="07431-137">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="07431-137">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="07431-138">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="07431-138">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)
