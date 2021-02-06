---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-pscallstack?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSCallStack
ms.openlocfilehash: 607e3999a1dbe9a4f22a751f11ac93ee3f9d9409
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599910"
---
# <span data-ttu-id="044ad-102">Get-PSCallStack</span><span class="sxs-lookup"><span data-stu-id="044ad-102">Get-PSCallStack</span></span>

## <span data-ttu-id="044ad-103">概要</span><span class="sxs-lookup"><span data-stu-id="044ad-103">SYNOPSIS</span></span>
<span data-ttu-id="044ad-104">現在の呼び出し履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="044ad-104">Displays the current call stack.</span></span>

## <span data-ttu-id="044ad-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="044ad-105">SYNTAX</span></span>

```
Get-PSCallStack [<CommonParameters>]
```

## <span data-ttu-id="044ad-106">Description</span><span class="sxs-lookup"><span data-stu-id="044ad-106">DESCRIPTION</span></span>

<span data-ttu-id="044ad-107">**Get PSCallStack** コマンドレットは、現在の呼び出し履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="044ad-107">The **Get-PSCallStack** cmdlet displays the current call stack.</span></span>

<span data-ttu-id="044ad-108">PowerShell デバッガーで使用するように設計されていますが、このコマンドレットを使用すると、デバッガーの外部にあるスクリプトまたは関数で呼び出し履歴を表示できます。</span><span class="sxs-lookup"><span data-stu-id="044ad-108">Although it is designed to be used with the PowerShell debugger, you can use this cmdlet to display the call stack in a script or function outside of the debugger.</span></span>

<span data-ttu-id="044ad-109">デバッガーで **Get PSCallStack** コマンドを実行するには、またはを入力し `k` `Get-PSCallStack` ます。</span><span class="sxs-lookup"><span data-stu-id="044ad-109">To run a **Get-PSCallStack** command while in the debugger, type `k` or `Get-PSCallStack`.</span></span>

## <span data-ttu-id="044ad-110">例</span><span class="sxs-lookup"><span data-stu-id="044ad-110">EXAMPLES</span></span>

### <span data-ttu-id="044ad-111">例 1: 関数の呼び出し履歴を取得する</span><span class="sxs-lookup"><span data-stu-id="044ad-111">Example 1: Get the call stack for a function</span></span>

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

<span data-ttu-id="044ad-112">このコマンドは、 **Get PSCallStack** コマンドレットを使用して、My エイリアスの呼び出し履歴を表示します。これは、コマンドレット名のエイリアスを取得する単純な関数です。</span><span class="sxs-lookup"><span data-stu-id="044ad-112">This command uses the **Get-PSCallStack** cmdlet to display the call stack for My-Alias, a simple function that gets the aliases for a cmdlet name.</span></span>

<span data-ttu-id="044ad-113">最初のコマンドは、PowerShell プロンプトで関数を入力します。</span><span class="sxs-lookup"><span data-stu-id="044ad-113">The first command enters the function at the PowerShell prompt.</span></span>
<span data-ttu-id="044ad-114">2 番目のコマンドは、Set-PSBreakpoint コマンドレットを使用して、My-Alias 関数にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="044ad-114">The second command uses the Set-PSBreakpoint cmdlet to set a breakpoint on the My-Alias function.</span></span>
<span data-ttu-id="044ad-115">3 番目のコマンドは、My-Alias 関数を使用して、Get-Content コマンドレットに対して現在のセッションのすべてのエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="044ad-115">The third command uses the My-Alias function to get all of the aliases in the current session for the Get-Content cmdlet.</span></span>

<span data-ttu-id="044ad-116">デバッガーは関数呼び出しに割り込みます。</span><span class="sxs-lookup"><span data-stu-id="044ad-116">The debugger breaks in at the function call.</span></span>
<span data-ttu-id="044ad-117">2 つの連続するステップイン (s) コマンドは、行ごとに関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="044ad-117">Two consecutive step-into (s) commands begin executing the function line by line.</span></span>
<span data-ttu-id="044ad-118">次に、 **Get PSCallStack** コマンドを使用して、呼び出し履歴を取得します。</span><span class="sxs-lookup"><span data-stu-id="044ad-118">Then, a **Get-PSCallStack** command is used to retrieve the call stack.</span></span>

<span data-ttu-id="044ad-119">最後のコマンドは、デバッガーを終了し、完了まで実行を継続する Step-Out コマンド (o) です。</span><span class="sxs-lookup"><span data-stu-id="044ad-119">The final command is a Step-Out command (o) that exits the debugger and continues executing the script to completion.</span></span>

## <span data-ttu-id="044ad-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="044ad-120">PARAMETERS</span></span>

### <span data-ttu-id="044ad-121">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="044ad-121">CommonParameters</span></span>

<span data-ttu-id="044ad-122">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="044ad-122">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="044ad-123">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="044ad-123">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="044ad-124">入力</span><span class="sxs-lookup"><span data-stu-id="044ad-124">INPUTS</span></span>

### <span data-ttu-id="044ad-125">なし</span><span class="sxs-lookup"><span data-stu-id="044ad-125">None</span></span>

<span data-ttu-id="044ad-126">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="044ad-126">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="044ad-127">出力</span><span class="sxs-lookup"><span data-stu-id="044ad-127">OUTPUTS</span></span>

### <span data-ttu-id="044ad-128">CallStackFrame (システム管理)</span><span class="sxs-lookup"><span data-stu-id="044ad-128">System.Management.Automation.CallStackFrame</span></span>

<span data-ttu-id="044ad-129">**Get-PSCallStack** は、呼び出し履歴内の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="044ad-129">**Get-PSCallStack** returns an object that represents the items in the call stack.</span></span>

## <span data-ttu-id="044ad-130">注</span><span class="sxs-lookup"><span data-stu-id="044ad-130">NOTES</span></span>

## <span data-ttu-id="044ad-131">関連リンク</span><span class="sxs-lookup"><span data-stu-id="044ad-131">RELATED LINKS</span></span>

[<span data-ttu-id="044ad-132">Disable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="044ad-132">Disable-PSBreakpoint</span></span>](Disable-PSBreakpoint.md)

[<span data-ttu-id="044ad-133">Enable-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="044ad-133">Enable-PSBreakpoint</span></span>](Enable-PSBreakpoint.md)

[<span data-ttu-id="044ad-134">Format-Table</span><span class="sxs-lookup"><span data-stu-id="044ad-134">Format-Table</span></span>](Format-Table.md)

[<span data-ttu-id="044ad-135">Get-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="044ad-135">Get-PSBreakpoint</span></span>](Get-PSBreakpoint.md)

[<span data-ttu-id="044ad-136">Remove-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="044ad-136">Remove-PSBreakpoint</span></span>](Remove-PSBreakpoint.md)

[<span data-ttu-id="044ad-137">Set-PSBreakpoint</span><span class="sxs-lookup"><span data-stu-id="044ad-137">Set-PSBreakpoint</span></span>](Set-PSBreakpoint.md)

