---
ms.date: 08/14/2018
keywords: PowerShell, コマンドレット
title: Windows PowerShell ISE の紹介
ms.openlocfilehash: d27a0eb594d7271121cee59f38d096995cc98648
ms.sourcegitcommit: 56b9be8503a5a1342c0b85b36f5ba6f57c281b63
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "43133134"
---
# <a name="introducing-the-windows-powershell-ise"></a>Windows PowerShell ISE の紹介

Windows PowerShell Integrated Scripting Environment (ISE) は、Windows PowerShell のホスト アプリケーションです。 Windows PowerShell ISE でコマンドを実行して、単一の Windows ベースのグラフィカル ユーザー インターフェイスでスクリプトの書き込み、テスト、およびデバッグを行うことが可能です。 インターフェイスでは、複数行の編集、タブ補完、構文の色分け、選択的な実行、状況依存のヘルプ、および右から左方向の言語のサポートを提供します。 メニュー項目とキーボード ショートカットは、Windows PowerShell コンソールで実行する多数の同じタスクにマッピングされます。 たとえば、Windows PowerShell ISE でスクリプトをデバッグするとき、コード行を右クリックするとブレークポイントを設定できます。

Windows PowerShell ISE の新機能をお試しください。

- 複数行の編集: [コマンド] ウィンドウで現在の行の下に空白行を挿入するには、SHIFT キーを押しながら ENTER キーを押します。
- 選択的な実行: スクリプトの一部を実行するには、実行するテキストを選んで、**[スクリプトの実行]** ボタンをクリックします。 または、F5 キーを押します。
- 状況依存ヘルプ: **Invoke-Item** と入力し、F1 キーを押します。 ヘルプ ファイルの **Invoke-Item** コマンドレットに関する記事が開きます。

Windows PowerShell ISE では、外観の一部をカスタマイズすることができます。 また、独自の Windows PowerShell プロファイル スクリプトもあります。

## <a name="to-start-the-windows-powershell-ise"></a>Windows PowerShell ISE を開始するには

**[スタート]** をクリックし、**[Windows PowerShell]** を選択して、**[Windows PowerShell ISE]** をクリックします。
代わりに、任意のコマンド シェルまたは [実行] ボックスに `powershell_ise.exe` を入力することも可能です。

## <a name="to-get-help-in-the-windows-powershell-ise"></a>Windows PowerShell ISE のヘルプを利用するには

**[ヘルプ]** メニューで、**[Windows PowerShell ヘルプ]** をクリックします。 または、F1 キーを押します。 開いたファイルは、Get-Help コマンドレットから利用できるすべてのヘルプを含む、Windows PowerShell ISE と Windows PowerShell について説明しています。