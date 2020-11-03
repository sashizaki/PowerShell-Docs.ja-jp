---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/get-psreadlinekeyhandler?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSReadLineKeyHandler
ms.openlocfilehash: 7cebb2a601714992759a310b6012deee5157e322
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224736"
---
# <span data-ttu-id="26b56-103">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="26b56-103">Get-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="26b56-104">概要</span><span class="sxs-lookup"><span data-stu-id="26b56-104">SYNOPSIS</span></span>
<span data-ttu-id="26b56-105">PSReadLine モジュールのキーバインドを取得します。</span><span class="sxs-lookup"><span data-stu-id="26b56-105">Gets the key bindings for the PSReadLine module.</span></span>

## <span data-ttu-id="26b56-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="26b56-106">SYNTAX</span></span>

```
Get-PSReadLineKeyHandler [-Bound] [-Unbound] [<CommonParameters>]
```

## <span data-ttu-id="26b56-107">Description</span><span class="sxs-lookup"><span data-stu-id="26b56-107">DESCRIPTION</span></span>

<span data-ttu-id="26b56-108">**Get PSReadLineKeyHandler** コマンドレットは、現在バインドされているキーバインドを返します。</span><span class="sxs-lookup"><span data-stu-id="26b56-108">The **Get-PSReadLineKeyHandler** cmdlet returns the currently bound key bindings.</span></span>

## <span data-ttu-id="26b56-109">例</span><span class="sxs-lookup"><span data-stu-id="26b56-109">EXAMPLES</span></span>

### <span data-ttu-id="26b56-110">例 1: すべてのキーマッピングを取得する</span><span class="sxs-lookup"><span data-stu-id="26b56-110">Example 1: Get all key mappings</span></span>

<span data-ttu-id="26b56-111">このコマンドは、バインドおよびバインド解除されているすべてのキーマッピングを返します。</span><span class="sxs-lookup"><span data-stu-id="26b56-111">This command returns all key mappings, bound and unbound.</span></span>

```powershell
Get-PSReadLineKeyHandler -Bound -Unbound
```

```Output
Key                   Function                Description
---                   --------                -----------
Enter                 AcceptLine              Accept the input or move to the next line if input is missing a closing token.
Shift+Enter           AddLine                 Move the cursor to the next line without attempting to execute the input
Escape                RevertLine              Equivalent to undo all edits (clears the line except lines imported from history)
LeftArrow             BackwardChar            Move the cursor back one character
RightArrow            ForwardChar             Move the cursor forward one character
Ctrl+LeftArrow        BackwardWord            Move the cursor to the beginning of the current or previous word
Ctrl+RightArrow       NextWord                Move the cursor forward to the start of the next word
Shift+LeftArrow       SelectBackwardChar      Adjust the current selection to include the previous character
Shift+RightArrow      SelectForwardChar       Adjust the current selection to include the next character
Ctrl+Shift+LeftArrow  SelectBackwardWord      Adjust the current selection to include the previous word
Ctrl+Shift+RightArrow SelectNextWord          Adjust the current selection to include the next word
UpArrow               PreviousHistory         Replace the input with the previous item in the history
DownArrow             NextHistory             Replace the input with the next item in the history
Home                  BeginningOfLine         Move the cursor to the beginning of the line
End                   EndOfLine               Move the cursor to the end of the line
Shift+Home            SelectBackwardsLine     Adjust the current selection to include from the cursor to the end of the line
Shift+End             SelectLine              Adjust the current selection to include from the cursor to the start of the line
Delete                DeleteChar              Delete the character under the cursor
Backspace             BackwardDeleteChar      Delete the character before the cursor
Ctrl+Spacebar         MenuComplete            Complete the input if there is a single completion, otherwise complete the input by selecting from a menu o...
Tab                   TabCompleteNext         Complete the input using the next completion
Shift+Tab             TabCompletePrevious     Complete the input using the previous completion
Ctrl+a                SelectAll               Select the entire line. Moves the cursor to the end of the line
Ctrl+c                CopyOrCancelLine        Either copy selected text to the clipboard, or if no text is selected, cancel editing the line with Cancel...
Ctrl+C                Copy                    Copy selected region to the system clipboard.  If no region is selected, copy the whole line
Ctrl+l                ClearScreen             Clear the screen and redraw the current line at the top of the screen
Ctrl+r                ReverseSearchHistory    Search history backwards interactively
...
```

### <span data-ttu-id="26b56-112">例 2: バインドされたキーを取得する</span><span class="sxs-lookup"><span data-stu-id="26b56-112">Example 2: Get bound keys</span></span>

<span data-ttu-id="26b56-113">このコマンドは、バインドされたキーとキーの組み合わせのみを返します。</span><span class="sxs-lookup"><span data-stu-id="26b56-113">This command returns only bound keys and key combinations.</span></span>

```powershell
Get-PSReadLineKeyHandler
```

```Output
Key                   Function                Description
---                   --------                -----------
Enter                 AcceptLine              Accept the input or move to the next line if input is missing a closing token.
Shift+Enter           AddLine                 Move the cursor to the next line without attempting to execute the input
Escape                RevertLine              Equivalent to undo all edits (clears the line except lines imported from history)
LeftArrow             BackwardChar            Move the cursor back one character
RightArrow            ForwardChar             Move the cursor forward one character
Ctrl+LeftArrow        BackwardWord            Move the cursor to the beginning of the current or previous word
Ctrl+RightArrow       NextWord                Move the cursor forward to the start of the next word
Shift+LeftArrow       SelectBackwardChar      Adjust the current selection to include the previous character
Shift+RightArrow      SelectForwardChar       Adjust the current selection to include the next character
Ctrl+Shift+LeftArrow  SelectBackwardWord      Adjust the current selection to include the previous word
Ctrl+Shift+RightArrow SelectNextWord          Adjust the current selection to include the next word
UpArrow               PreviousHistory         Replace the input with the previous item in the history
DownArrow             NextHistory             Replace the input with the next item in the history
Home                  BeginningOfLine         Move the cursor to the beginning of the line
End                   EndOfLine               Move the cursor to the end of the line
Shift+Home            SelectBackwardsLine     Adjust the current selection to include from the cursor to the end of the line
Shift+End             SelectLine              Adjust the current selection to include from the cursor to the start of the line
Delete                DeleteChar              Delete the character under the cursor
Backspace             BackwardDeleteChar      Delete the character before the cursor
Ctrl+Spacebar         MenuComplete            Complete the input if there is a single completion, otherwise complete the input by selecting from a menu o...
Tab                   TabCompleteNext         Complete the input using the next completion
...
```

## <span data-ttu-id="26b56-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="26b56-114">PARAMETERS</span></span>

### <span data-ttu-id="26b56-115">-バインド</span><span class="sxs-lookup"><span data-stu-id="26b56-115">-Bound</span></span>

<span data-ttu-id="26b56-116">このコマンドレットが、バインドされている関数を返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="26b56-116">Indicates that this cmdlet returns functions that are bound.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26b56-117">-バインド解除</span><span class="sxs-lookup"><span data-stu-id="26b56-117">-Unbound</span></span>

<span data-ttu-id="26b56-118">このコマンドレットが、バインドされていない関数を返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="26b56-118">Indicates that this cmdlet returns functions that are unbound.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="26b56-119">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="26b56-119">CommonParameters</span></span>

<span data-ttu-id="26b56-120">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="26b56-120">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="26b56-121">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="26b56-121">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="26b56-122">入力</span><span class="sxs-lookup"><span data-stu-id="26b56-122">INPUTS</span></span>

### <span data-ttu-id="26b56-123">なし</span><span class="sxs-lookup"><span data-stu-id="26b56-123">None</span></span>

<span data-ttu-id="26b56-124">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="26b56-124">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="26b56-125">出力</span><span class="sxs-lookup"><span data-stu-id="26b56-125">OUTPUTS</span></span>

### <span data-ttu-id="26b56-126">Microsoft. PowerShell. KeyHandler</span><span class="sxs-lookup"><span data-stu-id="26b56-126">Microsoft.PowerShell.KeyHandler</span></span>

## <span data-ttu-id="26b56-127">注</span><span class="sxs-lookup"><span data-stu-id="26b56-127">NOTES</span></span>

## <span data-ttu-id="26b56-128">関連リンク</span><span class="sxs-lookup"><span data-stu-id="26b56-128">RELATED LINKS</span></span>

[<span data-ttu-id="26b56-129">-PSReadLineKeyHandler を削除します。</span><span class="sxs-lookup"><span data-stu-id="26b56-129">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="26b56-130">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="26b56-130">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="26b56-131">設定-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="26b56-131">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="26b56-132">設定-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="26b56-132">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
