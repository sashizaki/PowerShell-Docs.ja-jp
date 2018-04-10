---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: ISEEditor オブジェクト
ms.openlocfilehash: 2d4c3d941035384c591ca57e809c0e3a9b852f5c
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="the-iseeditor-object"></a>ISEEditor オブジェクト

**ISEEditor** オブジェクトは、Microsoft.PowerShell.Host.ISE.ISEEditor クラスのインスタンスです。 コンソール ウィンドウは **ISEEditor** オブジェクトです。 各 [ISEFile](The-ISEFile-Object.md) オブジェクトには、関連付けられている **ISEEditor** オブジェクトがあります。 次のセクションでは、**ISEEditor** オブジェクトのメソッドとプロパティについて説明します。

## <a name="methods"></a>メソッド

### <a name="clear"></a>Clear\(\)

Windows PowerShell ISE 2.0 以降でサポートされています。

エディター内のテキストをクリアします。

```powershell
# Clears the text in the Console pane.
$psISE.CurrentPowerShellTab.ConsolePane.Clear()
```

### <a name="ensurevisibleint-linenumber"></a>EnsureVisible\(int lineNumber\)

Windows PowerShell ISE 2.0 以降でサポートされています。

指定した **lineNumber** パラメーターの値に対応する行が表示されるようにエディターをスクロールします。 指定した行番号が 1 から最後の行番号までの有効な行番号を定義する範囲を超えた場合、例外がスローされます。

**lineNumber** 表示させる行の番号。

```powershell
# Scrolls the text in the Script pane so that the fifth line is in view.
$psISE.CurrentFile.Editor.EnsureVisible(5)
```

### <a name="focus"></a>Focus\(\)

Windows PowerShell ISE 2.0 以降でサポートされています。

エディターにフォーカスを設定します。

```powershell
# Sets focus to the Console pane.
$psISE.CurrentPowerShellTab.ConsolePane.Focus()
```

### <a name="getlinelengthint-linenumber-"></a>GetLineLength\(int lineNumber \)

Windows PowerShell ISE 2.0 以降でサポートされています。

行番号で指定される行の整数として行の長さを取得します。

**lineNumber** 長さを取得する対象の行の番号。

**Returns** 指定した行番号にある行の長さ。

```powershell
# Gets the length of the first line in the text of the Command pane.
$psISE.CurrentPowerShellTab.ConsolePane.GetLineLength(1)
```

### <a name="gotomatch"></a>GoToMatch\(\)

Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。

エディター オブジェクトの **CanGoToMatch** プロパティが **$true** の場合、一致する文字にカーソルを移動します。これは、カーソルが始めかっこ \(、始め角かっこ \[、始め波かっこ { の直前または終わりかっこ \)、終わり角かっこ \]、終わり波かっこ } の直後にある場合に発生します。  カーソルは、開始文字の前または終了文字の後に配置されます。 **CanGoToMatch** プロパティが **$false** の場合、このメソッドでは何も実行されません。

```powershell
# Goes to the matching character if CanGoToMatch() is $true
$psISE.CurrentPowerShellTab.ConsolePane.GoToMatch()
```

### <a name="inserttext-text-"></a>InsertText\( text \)

Windows PowerShell ISE 2.0 以降でサポートされています。

選択範囲をテキストに置き換えるか、現在のカーソル位置でテキストを挿入します。

**text** - 文字列。挿入するテキスト。

後述の「[スクリプト例](#scripting-example)」を参照してください。

### <a name="select-startline-startcolumn-endline-endcolumn-"></a>Select\( startLine, startColumn, endLine, endColumn \)

Windows PowerShell ISE 2.0 以降でサポートされています。

**startLine**、**startColumn**、**endLine**、**endColumn** パラメーターからテキストを選択します。

**startLine** - 整数。選択範囲が開始する行。

**startColumn** - 整数。選択範囲が開始する開始行内の列。

**endLine** - 整数。選択範囲が終了する行。

**endColumn** - 整数。選択範囲が終了する終了行内の列。

後述の「[スクリプト例](#scripting-example)」を参照してください。

### <a name="selectcaretline"></a>SelectCaretLine\(\)

Windows PowerShell ISE 2.0 以降でサポートされています。

現在カーソルがある行のテキスト全体を選択します。

```powershell
# First, set the caret position on line 5.
$psISE.CurrentFile.Editor.SetCaretPosition(5,1)
# Now select that entire line of text
$psISE.CurrentFile.Editor.SelectCaretLine()
```

### <a name="setcaretposition-linenumber-columnnumber-"></a>SetCaretPosition\( lineNumber, columnNumber \)

Windows PowerShell ISE 2.0 以降でサポートされています。

行番号および列番号でカーソル位置を設定します。 カーソル行番号またはカーソル列番号のいずれかがそれぞれの有効な範囲外である場合、例外をスローします。

**lineNumber** - 整数。カーソル行番号。

**columnNumber** - 整数。カーソル列番号。

```powershell
# Set the CaretPosition.
$psISE.CurrentFile.Editor.SetCaretPosition(5,1)
```

### <a name="toggleoutliningexpansion"></a>ToggleOutliningExpansion\(\)

Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。

すべてのアウトライン セクションの展開または折りたたみが行われます。

```powershell
# Toggle the outlining expansion
$psISE.CurrentFile.Editor.ToggleOutliningExpansion()
```

## <a name="properties"></a>プロパティ

### <a name="cangotomatch"></a>CanGoToMatch

Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。

カーソルがかっこ、角かっこ、または波かっこ (\(\)、\[\]、{}) の横にあるかどうかを示す読み取り専用のブール型プロパティ。 カーソルがかっこの始め文字の直前またはかっこの終わり文字の直後にある場合、このプロパティの値は **$true** です。 それ以外の場合は **$false** です。

```powershell
# Test to see if the caret is next to a parenthesis, bracket, or brace
$psISE.CurrentFile.Editor.CanGoToMatch
```

### <a name="caretcolumn"></a>CaretColumn

Windows PowerShell ISE 2.0 以降でサポートされています。

カーソルの位置に対応する列番号を取得する読み取り専用プロパティ。

```powershell
# Get the CaretColumn.
$psISE.CurrentFile.Editor.CaretColumn
```

### <a name="caretline"></a>CaretLine

Windows PowerShell ISE 2.0 以降でサポートされています。

カーソルのある行の番号を取得する読み取り専用のプロパティ。

```powershell
# Get the CaretLine.
$psISE.CurrentFile.Editor.CaretLine
```

### <a name="caretlinetext"></a>CaretLineText

Windows PowerShell ISE 2.0 以降でサポートされています。

カーソルのある行のテキスト全体を取得する読み取り専用のプロパティ。

```powershell
# Get all of the text on the line that contains the caret.
$psISE.CurrentFile.Editor.CaretLineText
```

### <a name="linecount"></a>LineCount

Windows PowerShell ISE 2.0 以降でサポートされています。

エディターから行数を取得する読み取り専用のプロパティ。

```powershell
# Get the LineCount.
$psISE.CurrentFile.Editor.LineCount
```

### <a name="selectedtext"></a>SelectedText

Windows PowerShell ISE 2.0 以降でサポートされています。

エディターから選択テキストを取得する読み取り専用のプロパティ。

後述の「[スクリプト例](#scripting-example)」を参照してください。

### <a name="text"></a>テキスト

Windows PowerShell ISE 2.0 以降でサポートされています。

エディターでテキストを取得または設定する読み取り/書き込みのプロパティ。

後述の「[スクリプト例](#scripting-example)」を参照してください。

## <a name="scripting-example"></a>スクリプトの例

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

## <a name="see-also"></a>参照

- [ISEFile オブジェクト](The-ISEFile-Object.md)
- [PowerShellTab オブジェクト](The-PowerShellTab-Object.md)
- [Windows PowerShell ISE スクリプト オブジェクト モデルの目的](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)