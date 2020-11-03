---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSReadline
ms.date: 06/30/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/get-psreadlineoption?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSReadLineOption
ms.openlocfilehash: 7f731014e5a240e0c756640144ff7cae5e48f051
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224731"
---
# <span data-ttu-id="21049-103">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="21049-103">Get-PSReadLineOption</span></span>

## <span data-ttu-id="21049-104">概要</span><span class="sxs-lookup"><span data-stu-id="21049-104">SYNOPSIS</span></span>
<span data-ttu-id="21049-105">構成可能なオプションの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="21049-105">Gets values for the options that can be configured.</span></span>

## <span data-ttu-id="21049-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="21049-106">SYNTAX</span></span>

```
Get-PSReadLineOption [<CommonParameters>]
```

## <span data-ttu-id="21049-107">Description</span><span class="sxs-lookup"><span data-stu-id="21049-107">DESCRIPTION</span></span>

<span data-ttu-id="21049-108">`Get-PSReadLineOption`コマンドレットは、コマンドレットを使用して構成できる設定の現在の状態を返し `Set-PSReadLineOption` ます。</span><span class="sxs-lookup"><span data-stu-id="21049-108">The `Get-PSReadLineOption` cmdlet returns the current state of the settings that can be configured by using the `Set-PSReadLineOption` cmdlet.</span></span> <span data-ttu-id="21049-109">返されたオブジェクトを使用して **Psreadline** オプションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="21049-109">You can use the returned object to change **PSReadLine** options.</span></span> <span data-ttu-id="21049-110">これにより、複数の種類のトークンの構文の色分け表示オプションを少し簡単に設定できるようになります。</span><span class="sxs-lookup"><span data-stu-id="21049-110">This provides a slightly simpler way to set syntax coloring options for multiple kinds of tokens.</span></span>

## <span data-ttu-id="21049-111">例</span><span class="sxs-lookup"><span data-stu-id="21049-111">EXAMPLES</span></span>

### <span data-ttu-id="21049-112">例 1: オプションとその値を取得する</span><span class="sxs-lookup"><span data-stu-id="21049-112">Example 1: Get options and their values</span></span>

```powershell
Get-PSReadLineOption
```

```Output
EditMode                               : Windows
AddToHistoryHandler                    : System.Func`2[System.String,System.Object]
HistoryNoDuplicates                    : True
HistorySavePath                        : C:\Users\username\AppData\Roaming\Microsoft\Windows\
                                         PowerShell\PSReadLine\ConsoleHost_history.txt
HistorySaveStyle                       : SaveIncrementally
HistorySearchCaseSensitive             : False
HistorySearchCursorMovesToEnd          : False
MaximumHistoryCount                    : 4096
ContinuationPrompt                     : >>
ExtraPromptLineCount                   : 0
PromptText                             : {> }
BellStyle                              : Audible
DingDuration                           : 50
DingTone                               : 1221
CommandsToValidateScriptBlockArguments : {ForEach-Object, %, Invoke-Command, icm...}
CommandValidationHandler               :
CompletionQueryItems                   : 100
MaximumKillRingCount                   : 10
ShowToolTips                           : True
ViModeIndicator                        : None
WordDelimiters                         : ;:,.[]{}()/\|^&*-=+'"---
AnsiEscapeTimeout                      : 100
CommandColor                           : "$([char]0x1b)[93m"
CommentColor                           : "$([char]0x1b)[32m"
ContinuationPromptColor                : "$([char]0x1b)[37m"
DefaultTokenColor                      : "$([char]0x1b)[37m"
EmphasisColor                          : "$([char]0x1b)[96m"
ErrorColor                             : "$([char]0x1b)[91m"
KeywordColor                           : "$([char]0x1b)[92m"
MemberColor                            : "$([char]0x1b)[97m"
NumberColor                            : "$([char]0x1b)[97m"
OperatorColor                          : "$([char]0x1b)[90m"
ParameterColor                         : "$([char]0x1b)[90m"
SelectionColor                         : "$([char]0x1b)[30;47m"
StringColor                            : "$([char]0x1b)[36m"
TypeColor                              : "$([char]0x1b)[37m"
VariableColor                          : "$([char]0x1b)[92m"
```

<span data-ttu-id="21049-113">このコマンドは、使用可能な PSReadLine オプションとその現在の値の一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="21049-113">This command returns the list of available PSReadLine options and their current values.</span></span>

## <span data-ttu-id="21049-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="21049-114">PARAMETERS</span></span>

### <span data-ttu-id="21049-115">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="21049-115">CommonParameters</span></span>

<span data-ttu-id="21049-116">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="21049-116">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="21049-117">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21049-117">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="21049-118">入力</span><span class="sxs-lookup"><span data-stu-id="21049-118">INPUTS</span></span>

### <span data-ttu-id="21049-119">なし</span><span class="sxs-lookup"><span data-stu-id="21049-119">None</span></span>

<span data-ttu-id="21049-120">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="21049-120">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="21049-121">出力</span><span class="sxs-lookup"><span data-stu-id="21049-121">OUTPUTS</span></span>

### <span data-ttu-id="21049-122">PSConsoleReadLineOptions</span><span class="sxs-lookup"><span data-stu-id="21049-122">Microsoft.PowerShell.PSConsoleReadLineOptions</span></span>

<span data-ttu-id="21049-123">現在のオプションのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="21049-123">An instance of the current options.</span></span> <span data-ttu-id="21049-124">このオブジェクトのプロパティ値を変更すると、を呼び出さずに直接 PSReadLine の設定が更新され `Set-PSReadLineOption` ます。</span><span class="sxs-lookup"><span data-stu-id="21049-124">Changing the property values of this object updates the settings in PSReadLine directly without invoking `Set-PSReadLineOption`.</span></span>

## <span data-ttu-id="21049-125">注</span><span class="sxs-lookup"><span data-stu-id="21049-125">NOTES</span></span>

## <span data-ttu-id="21049-126">関連リンク</span><span class="sxs-lookup"><span data-stu-id="21049-126">RELATED LINKS</span></span>

[<span data-ttu-id="21049-127">-PSReadLineKeyHandler を削除します。</span><span class="sxs-lookup"><span data-stu-id="21049-127">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="21049-128">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="21049-128">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="21049-129">設定-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="21049-129">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="21049-130">設定-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="21049-130">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
