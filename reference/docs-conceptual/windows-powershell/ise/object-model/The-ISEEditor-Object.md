---
ms.date: 12/31/2019
title: ISEEditor オブジェクト
description: ISEEditor オブジェクトは、Microsoft.PowerShell.Host.ISE.ISEEditor クラスのインスタンスです。 コンソール ウィンドウは ISEEditor オブジェクトです。
ms.openlocfilehash: ffcb6e35e1160beab6efb29cc84847fa9ffd012b
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92654062"
---
# <a name="the-iseeditor-object"></a><span data-ttu-id="e6e60-104">ISEEditor オブジェクト</span><span class="sxs-lookup"><span data-stu-id="e6e60-104">The ISEEditor Object</span></span>

<span data-ttu-id="e6e60-105">**ISEEditor** オブジェクトは、Microsoft.PowerShell.Host.ISE.ISEEditor クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="e6e60-105">An **ISEEditor** object is an instance of the Microsoft.PowerShell.Host.ISE.ISEEditor class.</span></span> <span data-ttu-id="e6e60-106">コンソール ウィンドウは **ISEEditor** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="e6e60-106">The Console pane is an **ISEEditor** object.</span></span> <span data-ttu-id="e6e60-107">各 [ISEFile](The-ISEFile-Object.md) オブジェクトには、関連付けられている **ISEEditor** オブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="e6e60-107">Each [ISEFile](The-ISEFile-Object.md) object has an associated **ISEEditor** object.</span></span> <span data-ttu-id="e6e60-108">次のセクションでは、 **ISEEditor** オブジェクトのメソッドとプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e6e60-108">The following sections list the methods and properties of an **ISEEditor** object.</span></span>

## <a name="methods"></a><span data-ttu-id="e6e60-109">メソッド</span><span class="sxs-lookup"><span data-stu-id="e6e60-109">Methods</span></span>

### <a name="clear"></a><span data-ttu-id="e6e60-110">Clear\(\)</span><span class="sxs-lookup"><span data-stu-id="e6e60-110">Clear\(\)</span></span>

<span data-ttu-id="e6e60-111">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e6e60-111">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="e6e60-112">エディター内のテキストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="e6e60-112">Clears the text in the editor.</span></span>

```powershell
# Clears the text in the Console pane.
$psISE.CurrentPowerShellTab.ConsolePane.Clear()
```

### <a name="ensurevisibleint-linenumber"></a><span data-ttu-id="e6e60-113">EnsureVisible\(int lineNumber\)</span><span class="sxs-lookup"><span data-stu-id="e6e60-113">EnsureVisible\(int lineNumber\)</span></span>

<span data-ttu-id="e6e60-114">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e6e60-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="e6e60-115">指定した **lineNumber** パラメーターの値に対応する行が表示されるようにエディターをスクロールします。</span><span class="sxs-lookup"><span data-stu-id="e6e60-115">Scrolls the editor so that the line that corresponds to the specified **lineNumber** parameter value is visible.</span></span> <span data-ttu-id="e6e60-116">指定した行番号が 1 から最後の行番号までの有効な行番号を定義する範囲を超えた場合、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="e6e60-116">It throws an exception if the specified line number is outside the range of 1,last line number, which defines the valid line numbers.</span></span>

<span data-ttu-id="e6e60-117">**lineNumber** 表示させる行の番号。</span><span class="sxs-lookup"><span data-stu-id="e6e60-117">**lineNumber** The number of the line that is to be made visible.</span></span>

```powershell
# Scrolls the text in the Script pane so that the fifth line is in view.
$psISE.CurrentFile.Editor.EnsureVisible(5)
```

### <a name="focus"></a><span data-ttu-id="e6e60-118">Focus\(\)</span><span class="sxs-lookup"><span data-stu-id="e6e60-118">Focus\(\)</span></span>

<span data-ttu-id="e6e60-119">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e6e60-119">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="e6e60-120">エディターにフォーカスを設定します。</span><span class="sxs-lookup"><span data-stu-id="e6e60-120">Sets the focus to the editor.</span></span>

```powershell
# Sets focus to the Console pane.
$psISE.CurrentPowerShellTab.ConsolePane.Focus()
```

### <a name="getlinelengthint-linenumber-"></a><span data-ttu-id="e6e60-121">GetLineLength\(int lineNumber \)</span><span class="sxs-lookup"><span data-stu-id="e6e60-121">GetLineLength\(int lineNumber \)</span></span>

<span data-ttu-id="e6e60-122">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e6e60-122">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="e6e60-123">行番号で指定される行の整数として行の長さを取得します。</span><span class="sxs-lookup"><span data-stu-id="e6e60-123">Gets the line length as an integer for the line that is specified by the line number.</span></span>

<span data-ttu-id="e6e60-124">**lineNumber** 長さを取得する対象の行の番号。</span><span class="sxs-lookup"><span data-stu-id="e6e60-124">**lineNumber** The number of the line of which to get the length.</span></span>

<span data-ttu-id="e6e60-125">**Returns** 指定した行番号にある行の長さ。</span><span class="sxs-lookup"><span data-stu-id="e6e60-125">**Returns** The line length for the line at the specified line number.</span></span>

```powershell
# Gets the length of the first line in the text of the Command pane.
$psISE.CurrentPowerShellTab.ConsolePane.GetLineLength(1)
```

### <a name="gotomatch"></a><span data-ttu-id="e6e60-126">GoToMatch\(\)</span><span class="sxs-lookup"><span data-stu-id="e6e60-126">GoToMatch\(\)</span></span>

<span data-ttu-id="e6e60-127">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="e6e60-127">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="e6e60-128">エディター オブジェクトの **CanGoToMatch** プロパティが `$true` の場合、一致する文字にカーソルを移動します。これは、カーソルが始めかっこ `(`、始め角かっこ `[`、始め波かっこ `{` の直前または終わりかっこ `)`、終わり角かっこ `]`、終わり波かっこ `}` の直後にある場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="e6e60-128">Moves the caret to the matching character if the **CanGoToMatch** property of the editor object is `$true`, which occurs when the caret is immediately before an opening parenthesis, bracket, or brace - `(`,`[`,`{` - or immediately after a closing parenthesis, bracket, or brace - `)`,`]`,`}`.</span></span> <span data-ttu-id="e6e60-129">カーソルは、開始文字の前または終了文字の後に配置されます。</span><span class="sxs-lookup"><span data-stu-id="e6e60-129">The caret is placed before an opening character or after a closing character.</span></span> <span data-ttu-id="e6e60-130">**CanGoToMatch** プロパティが `$false` の場合、このメソッドでは何も実行されません。</span><span class="sxs-lookup"><span data-stu-id="e6e60-130">If the **CanGoToMatch** property is `$false`, then this method does nothing.</span></span>

```powershell
# Goes to the matching character if CanGoToMatch() is $true
$psISE.CurrentPowerShellTab.ConsolePane.GoToMatch()
```

### <a name="inserttext-text-"></a><span data-ttu-id="e6e60-131">InsertText\( text \)</span><span class="sxs-lookup"><span data-stu-id="e6e60-131">InsertText\( text \)</span></span>

<span data-ttu-id="e6e60-132">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e6e60-132">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="e6e60-133">選択範囲をテキストに置き換えるか、現在のカーソル位置でテキストを挿入します。</span><span class="sxs-lookup"><span data-stu-id="e6e60-133">Replaces the selection with text or inserts text at the current caret position.</span></span>

<span data-ttu-id="e6e60-134">**text** - 文字列。挿入するテキスト。</span><span class="sxs-lookup"><span data-stu-id="e6e60-134">**text** - String The text to insert.</span></span>

<span data-ttu-id="e6e60-135">後述の「[スクリプト例](#scripting-example)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6e60-135">See the [Scripting Example](#scripting-example) later in this topic.</span></span>

### <a name="select-startline-startcolumn-endline-endcolumn-"></a><span data-ttu-id="e6e60-136">Select\( startLine, startColumn, endLine, endColumn \)</span><span class="sxs-lookup"><span data-stu-id="e6e60-136">Select\( startLine, startColumn, endLine, endColumn \)</span></span>

<span data-ttu-id="e6e60-137">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e6e60-137">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="e6e60-138">**startLine** 、 **startColumn** 、 **endLine** 、 **endColumn** パラメーターからテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6e60-138">Selects the text from the **startLine** , **startColumn** , **endLine** , and **endColumn** parameters.</span></span>

<span data-ttu-id="e6e60-139">**startLine** - 整数。選択範囲が開始する行。</span><span class="sxs-lookup"><span data-stu-id="e6e60-139">**startLine** - Integer The line where the selection starts.</span></span>

<span data-ttu-id="e6e60-140">**startColumn** - 整数。選択範囲が開始する開始行内の列。</span><span class="sxs-lookup"><span data-stu-id="e6e60-140">**startColumn** - Integer The column within the start line where the selection starts.</span></span>

<span data-ttu-id="e6e60-141">**endLine** - 整数。選択範囲が終了する行。</span><span class="sxs-lookup"><span data-stu-id="e6e60-141">**endLine** - Integer The line where the selection ends.</span></span>

<span data-ttu-id="e6e60-142">**endColumn** - 整数。選択範囲が終了する終了行内の列。</span><span class="sxs-lookup"><span data-stu-id="e6e60-142">**endColumn** - Integer The column within the end line where the selection ends.</span></span>

<span data-ttu-id="e6e60-143">後述の「[スクリプト例](#scripting-example)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6e60-143">See the  [Scripting Example](#scripting-example) later in this topic.</span></span>

### <a name="selectcaretline"></a><span data-ttu-id="e6e60-144">SelectCaretLine\(\)</span><span class="sxs-lookup"><span data-stu-id="e6e60-144">SelectCaretLine\(\)</span></span>

<span data-ttu-id="e6e60-145">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e6e60-145">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="e6e60-146">現在カーソルがある行のテキスト全体を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6e60-146">Selects the entire line of text that currently contains the caret.</span></span>

```powershell
# First, set the caret position on line 5.
$psISE.CurrentFile.Editor.SetCaretPosition(5,1)
# Now select that entire line of text
$psISE.CurrentFile.Editor.SelectCaretLine()
```

### <a name="setcaretposition-linenumber-columnnumber-"></a><span data-ttu-id="e6e60-147">SetCaretPosition\( lineNumber, columnNumber \)</span><span class="sxs-lookup"><span data-stu-id="e6e60-147">SetCaretPosition\( lineNumber, columnNumber \)</span></span>

<span data-ttu-id="e6e60-148">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e6e60-148">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="e6e60-149">行番号および列番号でカーソル位置を設定します。</span><span class="sxs-lookup"><span data-stu-id="e6e60-149">Sets the caret position at the line number and the column number.</span></span> <span data-ttu-id="e6e60-150">カーソル行番号またはカーソル列番号のいずれかがそれぞれの有効な範囲外である場合、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="e6e60-150">It throws an exception if either the caret line number or the caret column number are out of their respective valid ranges.</span></span>

<span data-ttu-id="e6e60-151">**lineNumber** - 整数。カーソル行番号。</span><span class="sxs-lookup"><span data-stu-id="e6e60-151">**lineNumber** - Integer The caret line number.</span></span>

<span data-ttu-id="e6e60-152">**columnNumber** - 整数。カーソル列番号。</span><span class="sxs-lookup"><span data-stu-id="e6e60-152">**columnNumber** - Integer The caret column number.</span></span>

```powershell
# Set the CaretPosition.
$psISE.CurrentFile.Editor.SetCaretPosition(5,1)
```

### <a name="toggleoutliningexpansion"></a><span data-ttu-id="e6e60-153">ToggleOutliningExpansion\(\)</span><span class="sxs-lookup"><span data-stu-id="e6e60-153">ToggleOutliningExpansion\(\)</span></span>

<span data-ttu-id="e6e60-154">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="e6e60-154">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="e6e60-155">すべてのアウトライン セクションの展開または折りたたみが行われます。</span><span class="sxs-lookup"><span data-stu-id="e6e60-155">Causes all the outline sections to expand or collapse.</span></span>

```powershell
# Toggle the outlining expansion
$psISE.CurrentFile.Editor.ToggleOutliningExpansion()
```

## <a name="properties"></a><span data-ttu-id="e6e60-156">Properties</span><span class="sxs-lookup"><span data-stu-id="e6e60-156">Properties</span></span>

### <a name="cangotomatch"></a><span data-ttu-id="e6e60-157">CanGoToMatch</span><span class="sxs-lookup"><span data-stu-id="e6e60-157">CanGoToMatch</span></span>

<span data-ttu-id="e6e60-158">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="e6e60-158">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="e6e60-159">カーソルがかっこ `()`、角かっこ `[]`、または波かっこ `{}` の横にあるかどうかを示す読み取り専用のブール型プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e6e60-159">The read-only Boolean property to indicate whether the caret is next to a parenthesis, bracket, or brace - `()`, `[]`, `{}`.</span></span> <span data-ttu-id="e6e60-160">カーソルがかっこの始め文字の直前またはかっこの終わり文字の直後にある場合、このプロパティの値は `$true` です。</span><span class="sxs-lookup"><span data-stu-id="e6e60-160">If the caret is immediately before the opening character or immediately after the closing character of a pair, then this property value is `$true`.</span></span> <span data-ttu-id="e6e60-161">それ以外の場合は、`$false` となります。</span><span class="sxs-lookup"><span data-stu-id="e6e60-161">Otherwise, it is `$false`.</span></span>

```powershell
# Test to see if the caret is next to a parenthesis, bracket, or brace
$psISE.CurrentFile.Editor.CanGoToMatch
```

### <a name="caretcolumn"></a><span data-ttu-id="e6e60-162">CaretColumn</span><span class="sxs-lookup"><span data-stu-id="e6e60-162">CaretColumn</span></span>

<span data-ttu-id="e6e60-163">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e6e60-163">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="e6e60-164">カーソルの位置に対応する列番号を取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e6e60-164">The read-only property that gets the column number that corresponds to the position of the caret.</span></span>

```powershell
# Get the CaretColumn.
$psISE.CurrentFile.Editor.CaretColumn
```

### <a name="caretline"></a><span data-ttu-id="e6e60-165">CaretLine</span><span class="sxs-lookup"><span data-stu-id="e6e60-165">CaretLine</span></span>

<span data-ttu-id="e6e60-166">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e6e60-166">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="e6e60-167">カーソルのある行の番号を取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="e6e60-167">The read-only property that gets the number of the line that contains the caret.</span></span>

```powershell
# Get the CaretLine.
$psISE.CurrentFile.Editor.CaretLine
```

### <a name="caretlinetext"></a><span data-ttu-id="e6e60-168">CaretLineText</span><span class="sxs-lookup"><span data-stu-id="e6e60-168">CaretLineText</span></span>

<span data-ttu-id="e6e60-169">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e6e60-169">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="e6e60-170">カーソルのある行のテキスト全体を取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="e6e60-170">The read-only property that gets the complete line of text that contains the caret.</span></span>

```powershell
# Get all of the text on the line that contains the caret.
$psISE.CurrentFile.Editor.CaretLineText
```

### <a name="linecount"></a><span data-ttu-id="e6e60-171">LineCount</span><span class="sxs-lookup"><span data-stu-id="e6e60-171">LineCount</span></span>

<span data-ttu-id="e6e60-172">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e6e60-172">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="e6e60-173">エディターから行数を取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="e6e60-173">The read-only property that gets the line count from the editor.</span></span>

```powershell
# Get the LineCount.
$psISE.CurrentFile.Editor.LineCount
```

### <a name="selectedtext"></a><span data-ttu-id="e6e60-174">SelectedText</span><span class="sxs-lookup"><span data-stu-id="e6e60-174">SelectedText</span></span>

<span data-ttu-id="e6e60-175">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e6e60-175">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="e6e60-176">エディターから選択テキストを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="e6e60-176">The read-only property that gets the selected text from the editor.</span></span>

<span data-ttu-id="e6e60-177">後述の「[スクリプト例](#scripting-example)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6e60-177">See the  [Scripting Example](#scripting-example) later in this topic.</span></span>

### <a name="text"></a><span data-ttu-id="e6e60-178">Text</span><span class="sxs-lookup"><span data-stu-id="e6e60-178">Text</span></span>

<span data-ttu-id="e6e60-179">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e6e60-179">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="e6e60-180">エディターでテキストを取得または設定する読み取り/書き込みのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="e6e60-180">The read/write property that gets or sets the text in the editor.</span></span>

<span data-ttu-id="e6e60-181">後述の「[スクリプト例](#scripting-example)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6e60-181">See the [Scripting Example](#scripting-example) later in this topic.</span></span>

## <a name="scripting-example"></a><span data-ttu-id="e6e60-182">スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="e6e60-182">Scripting Example</span></span>

```powershell
# This illustrates how you can use the length of a line to
# select the entire line and shows how you can make it lowercase.
# You must run this in the Console pane. It will not run in the Script pane.
# Begin by getting a variable that points to the editor.
$myEditor = $psISE.CurrentFile.Editor
# Clear the text in the current file editor.
$myEditor.Clear()

# Make sure the file has five lines of text.
$myEditor.InsertText("LINE1 `n")
$myEditor.InsertText("LINE2 `n")
$myEditor.InsertText("LINE3 `n")
$myEditor.InsertText("LINE4 `n")
$myEditor.InsertText("LINE5 `n")

# Use the GetLineLength method to get the length of the third line.
$endColumn = $myEditor.GetLineLength(3)
# Select the text in the first three lines.
$myEditor.Select(1, 1, 3, $endColumn + 1)
$selection = $myEditor.SelectedText
# Clear all the text in the editor.
$myEditor.Clear()
# Add the selected text back, but in lower case.
$myEditor.InsertText($selection.ToLower())
```

## <a name="see-also"></a><span data-ttu-id="e6e60-183">参照</span><span class="sxs-lookup"><span data-stu-id="e6e60-183">See Also</span></span>

- [<span data-ttu-id="e6e60-184">ISEFile オブジェクト</span><span class="sxs-lookup"><span data-stu-id="e6e60-184">The ISEFile Object</span></span>](The-ISEFile-Object.md)
- [<span data-ttu-id="e6e60-185">PowerShellTab オブジェクト</span><span class="sxs-lookup"><span data-stu-id="e6e60-185">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md)
- [<span data-ttu-id="e6e60-186">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="e6e60-186">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="e6e60-187">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="e6e60-187">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
