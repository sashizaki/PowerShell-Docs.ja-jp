---
ms.date: 12/31/2019
keywords: powershell,コマンドレット
title: ISEEditor オブジェクト
ms.openlocfilehash: cb63acebc1a8bb9fa6cc07199088ae0d5441bc91
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809698"
---
# <a name="the-iseeditor-object"></a><span data-ttu-id="50dfc-103">ISEEditor オブジェクト</span><span class="sxs-lookup"><span data-stu-id="50dfc-103">The ISEEditor Object</span></span>

<span data-ttu-id="50dfc-104">**ISEEditor** オブジェクトは、Microsoft.PowerShell.Host.ISE.ISEEditor クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="50dfc-104">An **ISEEditor** object is an instance of the Microsoft.PowerShell.Host.ISE.ISEEditor class.</span></span> <span data-ttu-id="50dfc-105">コンソール ウィンドウは **ISEEditor** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="50dfc-105">The Console pane is an **ISEEditor** object.</span></span> <span data-ttu-id="50dfc-106">各 [ISEFile](The-ISEFile-Object.md) オブジェクトには、関連付けられている **ISEEditor** オブジェクトがあります。</span><span class="sxs-lookup"><span data-stu-id="50dfc-106">Each [ISEFile](The-ISEFile-Object.md) object has an associated **ISEEditor** object.</span></span> <span data-ttu-id="50dfc-107">次のセクションでは、**ISEEditor** オブジェクトのメソッドとプロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="50dfc-107">The following sections list the methods and properties of an **ISEEditor** object.</span></span>

## <a name="methods"></a><span data-ttu-id="50dfc-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="50dfc-108">Methods</span></span>

### <a name="clear"></a><span data-ttu-id="50dfc-109">Clear\(\)</span><span class="sxs-lookup"><span data-stu-id="50dfc-109">Clear\(\)</span></span>

<span data-ttu-id="50dfc-110">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="50dfc-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="50dfc-111">エディター内のテキストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="50dfc-111">Clears the text in the editor.</span></span>

```powershell
# Clears the text in the Console pane.
$psISE.CurrentPowerShellTab.ConsolePane.Clear()
```

### <a name="ensurevisibleint-linenumber"></a><span data-ttu-id="50dfc-112">EnsureVisible\(int lineNumber\)</span><span class="sxs-lookup"><span data-stu-id="50dfc-112">EnsureVisible\(int lineNumber\)</span></span>

<span data-ttu-id="50dfc-113">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="50dfc-113">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="50dfc-114">指定した **lineNumber** パラメーターの値に対応する行が表示されるようにエディターをスクロールします。</span><span class="sxs-lookup"><span data-stu-id="50dfc-114">Scrolls the editor so that the line that corresponds to the specified **lineNumber** parameter value is visible.</span></span> <span data-ttu-id="50dfc-115">指定した行番号が 1 から最後の行番号までの有効な行番号を定義する範囲を超えた場合、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="50dfc-115">It throws an exception if the specified line number is outside the range of 1,last line number, which defines the valid line numbers.</span></span>

<span data-ttu-id="50dfc-116">**lineNumber** 表示させる行の番号。</span><span class="sxs-lookup"><span data-stu-id="50dfc-116">**lineNumber** The number of the line that is to be made visible.</span></span>

```powershell
# Scrolls the text in the Script pane so that the fifth line is in view.
$psISE.CurrentFile.Editor.EnsureVisible(5)
```

### <a name="focus"></a><span data-ttu-id="50dfc-117">Focus\(\)</span><span class="sxs-lookup"><span data-stu-id="50dfc-117">Focus\(\)</span></span>

<span data-ttu-id="50dfc-118">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="50dfc-118">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="50dfc-119">エディターにフォーカスを設定します。</span><span class="sxs-lookup"><span data-stu-id="50dfc-119">Sets the focus to the editor.</span></span>

```powershell
# Sets focus to the Console pane.
$psISE.CurrentPowerShellTab.ConsolePane.Focus()
```

### <a name="getlinelengthint-linenumber-"></a><span data-ttu-id="50dfc-120">GetLineLength\(int lineNumber \)</span><span class="sxs-lookup"><span data-stu-id="50dfc-120">GetLineLength\(int lineNumber \)</span></span>

<span data-ttu-id="50dfc-121">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="50dfc-121">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="50dfc-122">行番号で指定される行の整数として行の長さを取得します。</span><span class="sxs-lookup"><span data-stu-id="50dfc-122">Gets the line length as an integer for the line that is specified by the line number.</span></span>

<span data-ttu-id="50dfc-123">**lineNumber** 長さを取得する対象の行の番号。</span><span class="sxs-lookup"><span data-stu-id="50dfc-123">**lineNumber** The number of the line of which to get the length.</span></span>

<span data-ttu-id="50dfc-124">**Returns** 指定した行番号にある行の長さ。</span><span class="sxs-lookup"><span data-stu-id="50dfc-124">**Returns** The line length for the line at the specified line number.</span></span>

```powershell
# Gets the length of the first line in the text of the Command pane.
$psISE.CurrentPowerShellTab.ConsolePane.GetLineLength(1)
```

### <a name="gotomatch"></a><span data-ttu-id="50dfc-125">GoToMatch\(\)</span><span class="sxs-lookup"><span data-stu-id="50dfc-125">GoToMatch\(\)</span></span>

<span data-ttu-id="50dfc-126">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="50dfc-126">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="50dfc-127">エディター オブジェクトの **CanGoToMatch** プロパティが `$true` の場合、一致する文字にカーソルを移動します。これは、カーソルが始めかっこ `(`、始め角かっこ `[`、始め波かっこ `{` の直前または終わりかっこ `)`、終わり角かっこ `]`、終わり波かっこ `}` の直後にある場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="50dfc-127">Moves the caret to the matching character if the **CanGoToMatch** property of the editor object is `$true`, which occurs when the caret is immediately before an opening parenthesis, bracket, or brace - `(`,`[`,`{` - or immediately after a closing parenthesis, bracket, or brace - `)`,`]`,`}`.</span></span> <span data-ttu-id="50dfc-128">カーソルは、開始文字の前または終了文字の後に配置されます。</span><span class="sxs-lookup"><span data-stu-id="50dfc-128">The caret is placed before an opening character or after a closing character.</span></span> <span data-ttu-id="50dfc-129">**CanGoToMatch** プロパティが `$false` の場合、このメソッドでは何も実行されません。</span><span class="sxs-lookup"><span data-stu-id="50dfc-129">If the **CanGoToMatch** property is `$false`, then this method does nothing.</span></span>

```powershell
# Goes to the matching character if CanGoToMatch() is $true
$psISE.CurrentPowerShellTab.ConsolePane.GoToMatch()
```

### <a name="inserttext-text-"></a><span data-ttu-id="50dfc-130">InsertText\( text \)</span><span class="sxs-lookup"><span data-stu-id="50dfc-130">InsertText\( text \)</span></span>

<span data-ttu-id="50dfc-131">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="50dfc-131">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="50dfc-132">選択範囲をテキストに置き換えるか、現在のカーソル位置でテキストを挿入します。</span><span class="sxs-lookup"><span data-stu-id="50dfc-132">Replaces the selection with text or inserts text at the current caret position.</span></span>

<span data-ttu-id="50dfc-133">**text** - 文字列。挿入するテキスト。</span><span class="sxs-lookup"><span data-stu-id="50dfc-133">**text** - String The text to insert.</span></span>

<span data-ttu-id="50dfc-134">後述の「[スクリプト例](#scripting-example)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50dfc-134">See the [Scripting Example](#scripting-example) later in this topic.</span></span>

### <a name="select-startline-startcolumn-endline-endcolumn-"></a><span data-ttu-id="50dfc-135">Select\( startLine, startColumn, endLine, endColumn \)</span><span class="sxs-lookup"><span data-stu-id="50dfc-135">Select\( startLine, startColumn, endLine, endColumn \)</span></span>

<span data-ttu-id="50dfc-136">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="50dfc-136">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="50dfc-137">**startLine**、**startColumn**、**endLine**、**endColumn** パラメーターからテキストを選択します。</span><span class="sxs-lookup"><span data-stu-id="50dfc-137">Selects the text from the **startLine**, **startColumn**, **endLine**, and **endColumn** parameters.</span></span>

<span data-ttu-id="50dfc-138">**startLine** - 整数。選択範囲が開始する行。</span><span class="sxs-lookup"><span data-stu-id="50dfc-138">**startLine** - Integer The line where the selection starts.</span></span>

<span data-ttu-id="50dfc-139">**startColumn** - 整数。選択範囲が開始する開始行内の列。</span><span class="sxs-lookup"><span data-stu-id="50dfc-139">**startColumn** - Integer The column within the start line where the selection starts.</span></span>

<span data-ttu-id="50dfc-140">**endLine** - 整数。選択範囲が終了する行。</span><span class="sxs-lookup"><span data-stu-id="50dfc-140">**endLine** - Integer The line where the selection ends.</span></span>

<span data-ttu-id="50dfc-141">**endColumn** - 整数。選択範囲が終了する終了行内の列。</span><span class="sxs-lookup"><span data-stu-id="50dfc-141">**endColumn** - Integer The column within the end line where the selection ends.</span></span>

<span data-ttu-id="50dfc-142">後述の「[スクリプト例](#scripting-example)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50dfc-142">See the  [Scripting Example](#scripting-example) later in this topic.</span></span>

### <a name="selectcaretline"></a><span data-ttu-id="50dfc-143">SelectCaretLine\(\)</span><span class="sxs-lookup"><span data-stu-id="50dfc-143">SelectCaretLine\(\)</span></span>

<span data-ttu-id="50dfc-144">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="50dfc-144">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="50dfc-145">現在カーソルがある行のテキスト全体を選択します。</span><span class="sxs-lookup"><span data-stu-id="50dfc-145">Selects the entire line of text that currently contains the caret.</span></span>

```powershell
# First, set the caret position on line 5.
$psISE.CurrentFile.Editor.SetCaretPosition(5,1)
# Now select that entire line of text
$psISE.CurrentFile.Editor.SelectCaretLine()
```

### <a name="setcaretposition-linenumber-columnnumber-"></a><span data-ttu-id="50dfc-146">SetCaretPosition\( lineNumber, columnNumber \)</span><span class="sxs-lookup"><span data-stu-id="50dfc-146">SetCaretPosition\( lineNumber, columnNumber \)</span></span>

<span data-ttu-id="50dfc-147">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="50dfc-147">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="50dfc-148">行番号および列番号でカーソル位置を設定します。</span><span class="sxs-lookup"><span data-stu-id="50dfc-148">Sets the caret position at the line number and the column number.</span></span> <span data-ttu-id="50dfc-149">カーソル行番号またはカーソル列番号のいずれかがそれぞれの有効な範囲外である場合、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="50dfc-149">It throws an exception if either the caret line number or the caret column number are out of their respective valid ranges.</span></span>

<span data-ttu-id="50dfc-150">**lineNumber** - 整数。カーソル行番号。</span><span class="sxs-lookup"><span data-stu-id="50dfc-150">**lineNumber** - Integer The caret line number.</span></span>

<span data-ttu-id="50dfc-151">**columnNumber** - 整数。カーソル列番号。</span><span class="sxs-lookup"><span data-stu-id="50dfc-151">**columnNumber** - Integer The caret column number.</span></span>

```powershell
# Set the CaretPosition.
$psISE.CurrentFile.Editor.SetCaretPosition(5,1)
```

### <a name="toggleoutliningexpansion"></a><span data-ttu-id="50dfc-152">ToggleOutliningExpansion\(\)</span><span class="sxs-lookup"><span data-stu-id="50dfc-152">ToggleOutliningExpansion\(\)</span></span>

<span data-ttu-id="50dfc-153">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="50dfc-153">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="50dfc-154">すべてのアウトライン セクションの展開または折りたたみが行われます。</span><span class="sxs-lookup"><span data-stu-id="50dfc-154">Causes all the outline sections to expand or collapse.</span></span>

```powershell
# Toggle the outlining expansion
$psISE.CurrentFile.Editor.ToggleOutliningExpansion()
```

## <a name="properties"></a><span data-ttu-id="50dfc-155">Properties</span><span class="sxs-lookup"><span data-stu-id="50dfc-155">Properties</span></span>

### <a name="cangotomatch"></a><span data-ttu-id="50dfc-156">CanGoToMatch</span><span class="sxs-lookup"><span data-stu-id="50dfc-156">CanGoToMatch</span></span>

<span data-ttu-id="50dfc-157">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="50dfc-157">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="50dfc-158">カーソルがかっこ `()`、角かっこ `[]`、または波かっこ `{}` の横にあるかどうかを示す読み取り専用のブール型プロパティ。</span><span class="sxs-lookup"><span data-stu-id="50dfc-158">The read-only Boolean property to indicate whether the caret is next to a parenthesis, bracket, or brace - `()`, `[]`, `{}`.</span></span> <span data-ttu-id="50dfc-159">カーソルがかっこの始め文字の直前またはかっこの終わり文字の直後にある場合、このプロパティの値は `$true` です。</span><span class="sxs-lookup"><span data-stu-id="50dfc-159">If the caret is immediately before the opening character or immediately after the closing character of a pair, then this property value is `$true`.</span></span> <span data-ttu-id="50dfc-160">それ以外の場合は、`$false` となります。</span><span class="sxs-lookup"><span data-stu-id="50dfc-160">Otherwise, it is `$false`.</span></span>

```powershell
# Test to see if the caret is next to a parenthesis, bracket, or brace
$psISE.CurrentFile.Editor.CanGoToMatch
```

### <a name="caretcolumn"></a><span data-ttu-id="50dfc-161">CaretColumn</span><span class="sxs-lookup"><span data-stu-id="50dfc-161">CaretColumn</span></span>

<span data-ttu-id="50dfc-162">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="50dfc-162">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="50dfc-163">カーソルの位置に対応する列番号を取得する読み取り専用プロパティ。</span><span class="sxs-lookup"><span data-stu-id="50dfc-163">The read-only property that gets the column number that corresponds to the position of the caret.</span></span>

```powershell
# Get the CaretColumn.
$psISE.CurrentFile.Editor.CaretColumn
```

### <a name="caretline"></a><span data-ttu-id="50dfc-164">CaretLine</span><span class="sxs-lookup"><span data-stu-id="50dfc-164">CaretLine</span></span>

<span data-ttu-id="50dfc-165">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="50dfc-165">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="50dfc-166">カーソルのある行の番号を取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="50dfc-166">The read-only property that gets the number of the line that contains the caret.</span></span>

```powershell
# Get the CaretLine.
$psISE.CurrentFile.Editor.CaretLine
```

### <a name="caretlinetext"></a><span data-ttu-id="50dfc-167">CaretLineText</span><span class="sxs-lookup"><span data-stu-id="50dfc-167">CaretLineText</span></span>

<span data-ttu-id="50dfc-168">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="50dfc-168">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="50dfc-169">カーソルのある行のテキスト全体を取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="50dfc-169">The read-only property that gets the complete line of text that contains the caret.</span></span>

```powershell
# Get all of the text on the line that contains the caret.
$psISE.CurrentFile.Editor.CaretLineText
```

### <a name="linecount"></a><span data-ttu-id="50dfc-170">LineCount</span><span class="sxs-lookup"><span data-stu-id="50dfc-170">LineCount</span></span>

<span data-ttu-id="50dfc-171">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="50dfc-171">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="50dfc-172">エディターから行数を取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="50dfc-172">The read-only property that gets the line count from the editor.</span></span>

```powershell
# Get the LineCount.
$psISE.CurrentFile.Editor.LineCount
```

### <a name="selectedtext"></a><span data-ttu-id="50dfc-173">SelectedText</span><span class="sxs-lookup"><span data-stu-id="50dfc-173">SelectedText</span></span>

<span data-ttu-id="50dfc-174">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="50dfc-174">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="50dfc-175">エディターから選択テキストを取得する読み取り専用のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="50dfc-175">The read-only property that gets the selected text from the editor.</span></span>

<span data-ttu-id="50dfc-176">後述の「[スクリプト例](#scripting-example)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50dfc-176">See the  [Scripting Example](#scripting-example) later in this topic.</span></span>

### <a name="text"></a><span data-ttu-id="50dfc-177">Text</span><span class="sxs-lookup"><span data-stu-id="50dfc-177">Text</span></span>

<span data-ttu-id="50dfc-178">Windows PowerShell ISE 2.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="50dfc-178">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="50dfc-179">エディターでテキストを取得または設定する読み取り/書き込みのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="50dfc-179">The read/write property that gets or sets the text in the editor.</span></span>

<span data-ttu-id="50dfc-180">後述の「[スクリプト例](#scripting-example)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50dfc-180">See the [Scripting Example](#scripting-example) later in this topic.</span></span>

## <a name="scripting-example"></a><span data-ttu-id="50dfc-181">スクリプトの例</span><span class="sxs-lookup"><span data-stu-id="50dfc-181">Scripting Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="50dfc-182">参照</span><span class="sxs-lookup"><span data-stu-id="50dfc-182">See Also</span></span>

- [<span data-ttu-id="50dfc-183">ISEFile オブジェクト</span><span class="sxs-lookup"><span data-stu-id="50dfc-183">The ISEFile Object</span></span>](The-ISEFile-Object.md)
- [<span data-ttu-id="50dfc-184">PowerShellTab オブジェクト</span><span class="sxs-lookup"><span data-stu-id="50dfc-184">The PowerShellTab Object</span></span>](The-PowerShellTab-Object.md)
- [<span data-ttu-id="50dfc-185">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="50dfc-185">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="50dfc-186">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="50dfc-186">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
