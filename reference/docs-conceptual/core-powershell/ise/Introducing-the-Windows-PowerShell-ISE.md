---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: Windows PowerShell ISE の紹介
ms.openlocfilehash: b09e64d0258d11f1f16f96b319ef232ebdfa0c49
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="introducing-the-windows-powershell-ise"></a>Windows PowerShell ISE の紹介

Windows PowerShell Integrated Scripting Environment (ISE) は、Windows PowerShell のホスト アプリケーションです。 Windows PowerShell ISE では、複数行の編集、タブ補完、構文の色分け、選択的な実行、状況依存ヘルプ、右から左へ記述する言語のサポートが可能な単一の Windows ベースのグラフィック ユーザー インターフェイス内で、コマンドの実行や、スクリプトの作成、テスト、およびデバッグを実行することができます。 メニュー項目とキーボード ショートカットを使用して、Windows PowerShell コンソールで実行するタスクの多くを実行できます。 たとえば、Windows PowerShell ISE 内のスクリプトをデバッグする場合に、スクリプト内の行のブレークポイントを設定するために、コードの行を右クリックして、**[ブレークポイントの設定/解除]** をクリックします。

Windows PowerShell ISE の新機能をお試しください。

- 複数行の編集: [コマンド] ウィンドウで現在の行の下に空白行を挿入するには、SHIFT キーを押しながら ENTER キーを押します。
- 選択的な実行: スクリプトの一部を実行するには、実行するテキストを選んで、**[スクリプトの実行]** ボタンをクリックします。 または、F5 キーを押します。
- 状況依存ヘルプ: **Invoke-Item** と入力し、F1 キーを押します。 ヘルプ ファイルの **Invoke-Item** コマンドレットに関するヘルプ トピックが開きます。

Windows PowerShell ISE では、外観の一部をカスタマイズすることができます。 また、独自の Windows PowerShell プロファイルも持ち、Windows PowerShell ISE で使用する関数、エイリアス、変数、およびコマンドを格納できます。

## <a name="to-start-the-windows-powershell-ise"></a>Windows PowerShell ISE を開始するには

次のいずれかの操作を行います。

- **[スタート]** をクリックして **[すべてのプログラム]** をポイントし、**[Windows PowerShell V2]** をポイントして **[Windows PowerShell ISE]** をクリックします。
- Windows PowerShell コンソール (Cmd.exe)、または [コマンド名を指定して実行] ボックスで、「**powershell_ise.exe**」と入力します。

## <a name="to-get-help-in-the-windows-powershell-ise"></a>Windows PowerShell ISE のヘルプを利用するには

**[ヘルプ]** メニューで、**[Windows PowerShell ヘルプ]** をクリックします。 または、F1 キーを押します。 開いたファイルは、Get-Help コマンドレットから利用できるすべてのヘルプを含む、Windows PowerShell ISE と Windows PowerShell について説明しています。