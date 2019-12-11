---
ms.date: 08/14/2018
keywords: PowerShell, コマンドレット
title: Windows PowerShell ISE でスクリプトを記述および実行する方法
ms.openlocfilehash: be54e26965a6d2f1472059820080a6a06c47dd26
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74117556"
---
# <a name="how-to-write-and-run-scripts-in-the-windows-powershell-ise"></a>Windows PowerShell ISE でスクリプトを記述および実行する方法

この記事では、スクリプト ウィンドウでスクリプトを作成、編集、実行、保存する方法について説明します。

## <a name="how-to-create-and-run-scripts"></a>スクリプトを作成して実行する方法

Windows PowerShell ファイルは、スクリプト ウィンドウで開いたり、編集したりできます。 Windows PowerShell で対象となるファイルの種類は、スクリプト ファイル (.ps1)、スクリプト データ ファイル (.psd1)、スクリプト モジュール ファイル (.psm1) です。 これらのファイルの種類は、スクリプト ウィンドウのエディターで構文が色分けされます。 スクリプト ウィンドウで開くことのできる他の一般的なファイルの種類には、構成ファイル (.ps1xml)、XML ファイル、テキスト ファイルがあります。

> [!NOTE]
> Windows PowerShell の実行ポリシーによって、スクリプトの実行や、Windows PowerShell のプロファイルと構成ファイルの読み込みを実行できるかどうかが決まります。 既定の実行ポリシー Restricted では、すべてのスクリプトの実行とプロファイルの読み込みが防止されます。 プロファイルの、読み込みと使用を許可するように実行ポリシーを変更する方法については、「[Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy)」と「[about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)」をご覧ください。

### <a name="to-create-a-new-script-file"></a>新しいスクリプト ファイルを作成するには

ツール バーの **[新規作成]** 、または **[ファイル]** メニューの **[新規作成]** をクリックします。 作成されたファイルは、現在の PowerShell タブの下に新しいファイル タブとして表示されます。PowerShell のタブは、少なくとも 1 つのタブが存在する場合にのみ表示されることにご注意ください。 既定では種類のスクリプトのファイル (.ps1) が作成されますが、そのファイルに新しい名前や拡張子を指定して保存できます。 同じ PowerShell タブ内に複数のスクリプト ファイルを作成できます。

### <a name="to-open-an-existing-script"></a>既存のスクリプトを開くには

ツール バーの **[開く]** 、または **[ファイル]** メニューの **[開く]** をクリックします。 **[開く]** ダイアログ ボックスで、開くファイルを選びます。 開いたファイルが新しいタブに表示されます。

### <a name="to-close-a-script-tab"></a>スクリプト タブを閉じるには

閉じたいファイル タブの **[閉じる]** アイコン (X) をクリックするか、または **[ファイル]** メニューを選択して **[閉じる]** をクリックします。

ファイルが最後に保存されてから変更された場合は、ファイルを保存するか破棄するかを選ぶメッセージが表示されます。

### <a name="to-display-the-file-path"></a>ファイル パスを表示するには

ファイル タブのファイル名をポイントします。 スクリプト ファイルへの完全修飾パスがヒントに表示されます。

### <a name="to-run-a-script"></a>スクリプトを実行するには

ツール バーの **[スクリプトを実行]** 、または **[ファイル]** メニューの **[実行]** をクリックします。

### <a name="to-run-a-portion-of-a-script"></a>スクリプトの一部を実行するには

1. スクリプト ウィンドウで、スクリプトの一部を選択します。
2. **[ファイル]** メニューの **[選択項目を実行]** 、またはツール バーの **[選択項目を実行]** をクリックします。

### <a name="to-stop-a-running-script"></a>スクリプトの実行を停止するには

実行中のスクリプトを停止するには、いくつかの方法があります。

- ツールバーの **[操作の停止]** をクリックする
- CTRL + BREAK キーを押す
- **[ファイル]** メニューを選択して、 **[操作の停止]** をクリックする

テキストが選択されていない場合は、**CTRL + C** キーを押すと、実行が停止します。テキストが選択されている場合は、**CTRL + C** キーは、選択したテキストのコピー機能にマップされます。

## <a name="how-to-write-and-edit-text-in-the-script-pane"></a>スクリプト ウィンドウでテキストを記述して編集する方法

スクリプト ペインで、テキストのコピー、切り取り、貼り付け、検索、および置換を実行できます。 最後に実行した操作を元に戻したり、再実行したりできます。 これらのアクションのキーボード ショートカットは、すべての Windows アプリケーションで使われているショートカットと同じです。

### <a name="to-enter-text-in-the-script-pane"></a>スクリプト ウィンドウにテキストを入力するには

1. カーソルをスクリプト ウィンドウに移すには、スクリプト ウィンドウ内の任意の場所をクリックするか、または **[表示]** メニューの **[スクリプト ウィンドウに移動]** をクリックします。
2. スクリプトを作成します。 Windows PowerShell ISE では、編集しやすいように、構文の色分けやタブ補完の機能が提供されます。
3. 入力中にタブ補完機能を使う方法について詳しくは、「[スクリプト ウィンドウとコンソール ウィンドウでタブ補完を使用する方法](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md)」をご覧ください。

### <a name="to-find-text-in-the-script-pane"></a>スクリプト ウィンドウでテキストを検索するには

1. 任意の場所にあるテキストを検索するには、**CTRL + F** キーを押すか、または **[編集]** メニューの **[スクリプト内を検索]** をクリックします。
2. カーソルより後の場所にあるテキストを検索するには、**F3** キーを押すか、または **[編集]** メニューの **[スクリプト内で次を検索]** をクリックします。
3. カーソルより前の場所にあるテキストを検索するには、**SHIFT + F3** キーを押すか、または **[編集]** メニューの **[スクリプト内で前を検索]** をクリックします。

### <a name="to-find-and-replace-text-in-the-script-pane"></a>スクリプト ウィンドウでテキストを検索して置換するには

**Ctrl キーを押しながら H キー**を押すか、または **[編集]** メニューの **[スクリプト内で置換]** をクリックします。 検索するテキストと置換後のテキストを入力して、**ENTER** キーを押します。

### <a name="to-go-to-a-particular-line-of-text-in-the-script-pane"></a>スクリプト ウィンドウ内のテキストの特定の行に移動するには

1. スクリプト ウィンドウで **CTRL + G** キーを押すか、または **[編集]** メニューの **[指定の行に移動]** をクリックします。

2. 行番号を入力します。

### <a name="to-copy-text-in-the-script-pane"></a>スクリプト ウィンドウでテキストをコピーするには

1. スクリプト ウィンドウで、コピーするテキストを選択します。

2. **CTRL + C** キーを押すか、ツール バーで **[コピー]** アイコンをクリックするか、または **[編集]** メニューの **[コピー]** をクリックします。

### <a name="to-cut-text-in-the-script-pane"></a>スクリプト ウィンドウでテキストを切り取るには

1. スクリプト ウィンドウで、切り取るテキストを選択します。
2. **CTRL + X** キーを押すか、ツール バーで **[切り取り]** アイコンをクリックするか、または **[編集]** メニューの **[切り取り]** をクリックします。

### <a name="to-paste-text-into-the-script-pane"></a>スクリプト ウィンドウにテキストを貼り付けるには

**CTRL + V** キーを押すか、ツール バーで **[貼り付け]** アイコンをクリックするか、または **[編集]** メニューの **[貼り付け]** をクリックします。

### <a name="to-undo-an-action-in-the-script-pane"></a>スクリプト ウィンドウ内のアクションを元に戻すには

**CTRL + Z** キーを押すか、ツール バーで **[元に戻す]** アイコンをクリックするか、または **[編集]** メニューの **[元に戻す]** をクリックします。

### <a name="to-redo-an-action-in-the-script-pane"></a>スクリプト ウィンドウ内のアクションをやり直すには

**CTRL + Y** キーを押すか、ツール バーで **[やり直し]** アイコンをクリックするか、または **[編集]** メニューの **[やり直し]** をクリックします。

## <a name="how-to-save-a-script"></a>スクリプトを保存する方法

変更されてから保存されていないファイルには、スクリプト名の横にアスタリスクが表示されます。 ファイルを保存すると、アスタリスクは消えます。

### <a name="to-save-a-script"></a>スクリプトを保存するには

**CTRL + S** キーを押すか、ツール バーで **[保存]** アイコンをクリックするか、または **[ファイル]** メニューの **[保存]** をクリックします。

### <a name="to-save-and-name-a-script"></a>スクリプトに名前を付けて保存するには

1. **[ファイル]** メニューの **[名前を付けて保存]** をクリックします。 **[名前を付けて保存]** ダイアログ ボックスが表示されます。
2. **[ファイル名]** ボックスに、ファイルの名前を入力します。
3. **[ファイルの種類]** ボックスで、ファイルの種類を選びます。 たとえば、 **[ファイルの種類]** ボックスで、[PowerShell スクリプト (\*.ps1)] を選びます。
4. **[保存]** をクリックします。

### <a name="to-save-a-script-in-ascii-encoding"></a>ASCII エンコードでスクリプトを保存するには

既定では、Windows PowerShell ISE は新しいスクリプト ファイル (.ps1)、スクリプト データ ファイル (.psd1)、スクリプト モジュール ファイル (.psm1) を Unicode (BigEndianUnicode) として保存します。ASCII (ANSI) など、別のエンコードでスクリプトを保存するには、[$psISE.CurrentFile](object-model/the-ise-object-model-hierarchy.md) オブジェクトの **Save** または **SaveAs** メソッドを使用します。

次のコマンドでは、新しいスクリプトを MyScript.ps1 という名前の ASCII エンコードで保存します。

```powershell
$psISE.CurrentFile.SaveAs("MyScript.ps1", [System.Text.Encoding]::ASCII)
```

次のコマンドでは、現在のスクリプト ファイルと同じ名前の ASCII エンコードのファイルに置き換えます。

```powershell
$psISE.CurrentFile.Save([System.Text.Encoding]::ASCII)
```

次のコマンドでは、現在のファイルのエンコードを取得します。

```powershell
$psISE.CurrentFile.encoding
```

Windows PowerShell ISE では、次のエンコード オプションがサポートされています: ASCII、BigEndianUnicode、Unicode、UTF32、UTF7、UTF8、Default。 既定値オプションの値は、システムによって異なります。

Save または Save As コマンドを使用した場合、Windows PowerShell ISE ではスクリプト ファイルのエンコードを変更しません。

## <a name="see-also"></a>参照

- [Windows PowerShell ISE の操作](exploring-the-windows-powershell-ise.md)
