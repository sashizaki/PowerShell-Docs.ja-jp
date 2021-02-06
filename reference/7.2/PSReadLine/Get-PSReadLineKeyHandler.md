---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/get-psreadlinekeyhandler?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSReadLineKeyHandler
ms.openlocfilehash: bb1e92a8f4bca96dc369b5b799c7e89245e432be
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601208"
---
# <span data-ttu-id="87c3b-102">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="87c3b-102">Get-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="87c3b-103">概要</span><span class="sxs-lookup"><span data-stu-id="87c3b-103">SYNOPSIS</span></span>
<span data-ttu-id="87c3b-104">PSReadLine モジュールのバインドされたキー関数を取得します。</span><span class="sxs-lookup"><span data-stu-id="87c3b-104">Gets the bound key functions for the PSReadLine module.</span></span>

## <span data-ttu-id="87c3b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="87c3b-105">SYNTAX</span></span>

### <span data-ttu-id="87c3b-106">FullListing (既定値)</span><span class="sxs-lookup"><span data-stu-id="87c3b-106">FullListing (default)</span></span>

```
Get-PSReadLineKeyHandler [-Bound] [-Unbound] [<CommonParameters>]
```

### <span data-ttu-id="87c3b-107">固有のバインド</span><span class="sxs-lookup"><span data-stu-id="87c3b-107">SpecificBindings</span></span>

```
Get-PSReadLineKeyHandler [-Chord] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="87c3b-108">Description</span><span class="sxs-lookup"><span data-stu-id="87c3b-108">DESCRIPTION</span></span>

<span data-ttu-id="87c3b-109">パラメーターが指定されていない場合は、PSReadLine モジュールの現在バインドされているキー関数を返します。</span><span class="sxs-lookup"><span data-stu-id="87c3b-109">If no parameter is specified, returns the currently bound key functions for the PSReadLine module.</span></span>

<span data-ttu-id="87c3b-110">**コード** パラメーターが指定されている場合、コマンドレットは、特定のバインドされたキーを返します。</span><span class="sxs-lookup"><span data-stu-id="87c3b-110">If **Chord** parameter is specified, the cmdlet returns the specific bound keys.</span></span>

## <span data-ttu-id="87c3b-111">例</span><span class="sxs-lookup"><span data-stu-id="87c3b-111">EXAMPLES</span></span>

### <span data-ttu-id="87c3b-112">例 1: すべてのキーマッピングを取得する</span><span class="sxs-lookup"><span data-stu-id="87c3b-112">Example 1: Get all key mappings</span></span>

<span data-ttu-id="87c3b-113">このコマンドは、バインドおよびバインド解除されているすべてのキーマッピングを返します。</span><span class="sxs-lookup"><span data-stu-id="87c3b-113">This command returns all key mappings, bound and unbound.</span></span>

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

### <span data-ttu-id="87c3b-114">例 2: バインドされたキーを取得する</span><span class="sxs-lookup"><span data-stu-id="87c3b-114">Example 2: Get bound keys</span></span>

<span data-ttu-id="87c3b-115">このコマンドは、バインドされたキーとキーの組み合わせのみを返します。</span><span class="sxs-lookup"><span data-stu-id="87c3b-115">This command returns only bound keys and key combinations.</span></span>

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

### <span data-ttu-id="87c3b-116">例 3: 特定のキーバインドを取得する</span><span class="sxs-lookup"><span data-stu-id="87c3b-116">Example 3: Get specific key bindings</span></span>

<span data-ttu-id="87c3b-117">このコマンドは、指定されたキーのバインドのみを返します。</span><span class="sxs-lookup"><span data-stu-id="87c3b-117">This command returns only the bindings for the specified keys.</span></span>

```powershell
Get-PSReadLineKeyHandler -Chord Enter, Shift+Enter
```

```Output
Key         Function   Description
---         --------   -----------
Enter       AcceptLine Accept the input or move to the next line if input is missing a closing token.
Shift+Enter AddLine    Move the cursor to the next line without attempting to execute the input
...
```

## <span data-ttu-id="87c3b-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="87c3b-118">PARAMETERS</span></span>

### <span data-ttu-id="87c3b-119">-バインド</span><span class="sxs-lookup"><span data-stu-id="87c3b-119">-Bound</span></span>

<span data-ttu-id="87c3b-120">このコマンドレットが、バインドされている関数を返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="87c3b-120">Indicates that this cmdlet returns functions that are bound.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FullListing
Aliases:

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87c3b-121">-バインド解除</span><span class="sxs-lookup"><span data-stu-id="87c3b-121">-Unbound</span></span>

<span data-ttu-id="87c3b-122">このコマンドレットが、バインドされていない関数を返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="87c3b-122">Indicates that this cmdlet returns functions that are unbound.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FullListing
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87c3b-123">-コード</span><span class="sxs-lookup"><span data-stu-id="87c3b-123">-Chord</span></span>

<span data-ttu-id="87c3b-124">特定のキーまたはシーケンスにバインドされた関数のみを返します。</span><span class="sxs-lookup"><span data-stu-id="87c3b-124">Return only functions bound to specific keys or sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: SpecificBindings
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="87c3b-125">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="87c3b-125">CommonParameters</span></span>

<span data-ttu-id="87c3b-126">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="87c3b-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="87c3b-127">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87c3b-127">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="87c3b-128">入力</span><span class="sxs-lookup"><span data-stu-id="87c3b-128">INPUTS</span></span>

### <span data-ttu-id="87c3b-129">なし</span><span class="sxs-lookup"><span data-stu-id="87c3b-129">None</span></span>

<span data-ttu-id="87c3b-130">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="87c3b-130">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="87c3b-131">出力</span><span class="sxs-lookup"><span data-stu-id="87c3b-131">OUTPUTS</span></span>

### <span data-ttu-id="87c3b-132">Microsoft. PowerShell. KeyHandler</span><span class="sxs-lookup"><span data-stu-id="87c3b-132">Microsoft.PowerShell.KeyHandler</span></span>

## <span data-ttu-id="87c3b-133">注</span><span class="sxs-lookup"><span data-stu-id="87c3b-133">NOTES</span></span>

## <span data-ttu-id="87c3b-134">関連リンク</span><span class="sxs-lookup"><span data-stu-id="87c3b-134">RELATED LINKS</span></span>

[<span data-ttu-id="87c3b-135">-PSReadLineKeyHandler を削除します。</span><span class="sxs-lookup"><span data-stu-id="87c3b-135">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="87c3b-136">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="87c3b-136">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="87c3b-137">設定-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="87c3b-137">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="87c3b-138">設定-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="87c3b-138">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)

