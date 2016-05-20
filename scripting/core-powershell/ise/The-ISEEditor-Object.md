---
title: ISEEditor オブジェクト
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0101daf8-4e31-4e4c-ab89-01d95dcb8f46
---
# ISEEditor オブジェクト
  **ISEEditor** オブジェクトは、Microsoft.PowerShell.Host.ISE.ISEEditor クラスのインスタンスです。 コンソール ウィンドウは **ISEEditor** オブジェクトです。 各 [ISEFile](The-ISEFile-Object.md) オブジェクトには、関連付けられている **ISEEditor** オブジェクトがあります。 次のセクションでは、**ISEEditor** オブジェクトのメソッドとプロパティについて説明します。

## メソッド

### Clear\(\)
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 エディター内のテキストをクリアします。

```
# Clears the text in the Console pane.
$psIse.CurrentPowerShellTab.ConsolePane.Clear()

```

### EnsureVisible\(int lineNumber\)
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 指定した **lineNumber** パラメーターの値に対応する行が表示されるようにエディターをスクロールします。 指定した行番号が 1 から最後の行番号までの有効な行番号を定義する範囲を超えた場合、例外がスローされます。

 **lineNumber**
 表示するようにする行の番号。

```
# Scrolls the text in the Script pane so that the fifth line is in view. 
$psIse.CurrentFile.Editor.EnsureVisible(5)

```

### Focus\(\)
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 エディターにフォーカスを設定します。

```
# Sets focus to the Console pane. 
$psISE.CurrentPowerShellTab.ConsolePane.Focus()
```

### GetLineLength\(int lineNumber \)
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 行番号で指定される行の整数として行の長さを取得します。

 **lineNumber**
 長さを取得する対象の行の番号。

 **戻り値**
 指定した行番号にある行の長さ。

```
# Gets the length of the first line in the text of the Command pane. 
$psIse.CurrentPowerShellTab.ConsolePane.GetLineLength(1)
```

### GoToMatch\(\)
  Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。 

 エディター オブジェクトの **CanGoToMatch** プロパティが **$true** の場合、一致する文字にカーソルを移動します。これは、カーソルが始めかっこ、始め角かっこ、または始め波かっこ (\(、\[、{) の直前または終わりかっこ、終わり角かっこ、または終わり波かっこ (\)、\]、}) の直後にある場合に発生します。  カーソルは、開始文字の前または終了文字の後に配置されます。 **CanGoToMatch** プロパティが **$false** の場合、このメソッドでは何も実行されません。 [CanGoToMatch](#cangotomatch) を参照してください。.

```
# Test to see if the caret is next to a parenthesis, bracket, or brace.
```

### InsertText\( text \)
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 選択範囲をテキストに置き換えるか、現在のカーソル位置でテキストを挿入します。

 **text** \- 文字列
 挿入するテキスト。

 後述の「[スクリプト例](#example)」を参照してください。

### Select\( startLine, startColumn, endLine, endColumn \)
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 **startLine**、**startColumn**、**endLine**、**endColumn** パラメーターからテキストを選択します。

 **startLine** \- 整数
 選択範囲が開始する行。

 **startColumn** \- 整数
 選択範囲が開始する開始行内の列。

 **endLine** \- 整数
 選択範囲が終了する行。

 **endColumn** \- 整数
 選択範囲が終了する終了行内の列。

 後述の「[スクリプト例](#example)」を参照してください。

### SelectCaretLine\(\)
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 現在カーソルがある行のテキスト全体を選択します。

```
# First, set the caret position on line 5.
$psIse.CurrentFile.Editor.SetCaretPosition(5,1) 
# Now select that entire line of text
$psIse.CurrentFile.Editor.SelectCaretLine()

```

### SetCaretPosition\( lineNumber, columnNumber \)
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 行番号および列番号でカーソル位置を設定します。 カーソル行番号またはカーソル列番号のいずれかがそれぞれの有効な範囲外である場合、例外をスローします。

 **lineNumber** \- 整数
 カーソル行番号。

 **columnNumber** \- 整数
 カーソル列番号。

```
# Set the CaretPosition.
$psIse.CurrentFile.Editor.SetCaretPosition(5,1)
```

### ToggleOutliningExpansion\(\)
  Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。 

 すべてのアウトライン セクションの展開または折りたたみが行われます。

```
# Toggle the outlining expansion
$psIse.CurrentFile.Editor.ToggleOutliningExpansion()

```

## プロパティ

###  <a name="CanGoToMatch"></a> CanGoToMatch
  Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。 

 カーソルがかっこ、角かっこ、または波かっこ (\(\)、\[\]、{}) の横にあるかどうかを示す読み取り専用のブール型プロパティ。 カーソルがかっこの始め文字の直前またはかっこの終わり文字の直後にある場合、このプロパティの値は **$true** です。 それ以外の場合は **$false** です。.

```
# Test to see if the caret is next to a parenthesis, bracket, or brace
$psIse.CurrentFile.Editor.CanGoToMatch

```

###  <a name="CaretColumn"></a> CaretColumn
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 カーソルの位置に対応する列番号を取得する読み取り専用プロパティ。

```
# Get the CaretColumn.
$psIse.CurrentFile.Editor.CaretColumn

```

###  <a name="CaretLine"></a> CaretLine
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 カーソルのある行の番号を取得する読み取り専用のプロパティ。

```
# Get the CaretLine.
$psIse.CurrentFile.Editor.CaretLine

```

###  <a name="caretlinetext"></a> CaretLineText
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 カーソルのある行のテキスト全体を取得する読み取り専用のプロパティ。

```
# Get all of the text on the line that contains the caret.
$psIse.CurrentFile.Editor.CaretLineText

```

###  <a name="LineCount"></a> LineCount
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 エディターから行数を取得する読み取り専用のプロパティ。

```
# Get the LineCount.
$psIse.CurrentFile.Editor.LineCount

```

###  <a name="SelectedText"></a> SelectedText
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 エディターから選択テキストを取得する読み取り専用のプロパティ。

 後述の「[スクリプト例](#example)」を参照してください。

###  <a name="Text"></a> テキスト
  Windows PowerShell ISE 2.0 以降でサポートされています。 

 エディターでテキストを取得または設定する読み取り\/書き込みのプロパティ。

 後述の「[スクリプト例](#example)」を参照してください。

##  <a name="example"></a> スクリプトの例

```

# This illustrates how you can use the length of a line to
# select the entire line and shows how you can make it lowercase. 
# You must run this in the Console pane. It will not run in the Script pane.
# Begin by getting a variable that points to the editor.
$myEditor=$psIse.CurrentFile.Editor
# Clear the text in the current file editor.
$myEditor.Clear()

# Make sure the file has five lines of text.
$myEditor.InsertText("LINE1 `n")
$myEditor.InsertText("LINE2 `n")
$myEditor.InsertText("LINE3 `n")
$myEditor.InsertText("LINE4 `n")
$myEditor.InsertText("LINE5 `n")

# Use the GetLineLength method to get the length of the third line. 
$endColumn= $myEditor.GetLineLength(3)
# Select the text in the first three lines.
$myEditor.Select(1,1,3,$endColumn + 1)
$selection = $myEditor.SelectedText
# Clear all the text in the editor.
$myEditor.Clear()
# Add the selected text back, but in lower case.
$myEditor.InsertText($selection.ToLower())
```

## 参照
 [ISEFile オブジェクト](The-ISEFile-Object.md) 
 [PowerShellTab オブジェクト](The-PowerShellTab-Object.md) 
 [Windows PowerShell ISE スクリプト オブジェクト モデル](The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
 [Windows PowerShell ISE オブジェクト モデル リファレンス](Windows-PowerShell-ISE-Object-Model-Reference.md) 
 [ISE オブジェクト モデルの階層](The-ISE-Object-Model-Hierarchy.md)

  


<!--HONumber=May16_HO2-->


