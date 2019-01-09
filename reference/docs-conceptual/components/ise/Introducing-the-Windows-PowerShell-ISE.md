---
ms.date: 08/14/2018
keywords: PowerShell, コマンドレット
title: Windows PowerShell ISE の紹介
ms.openlocfilehash: 09a28b295855fd2a3c62bba8a681399dae3454f8
ms.sourcegitcommit: 3402a478cf118c11a5642038eb117bc76553e3ab
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53411584"
---
# <a name="the-windows-powershell-ise"></a>Windows PowerShell ISE

Windows PowerShell Integrated Scripting Environment (ISE) は、Windows PowerShell のホスト アプリケーションです。 ISE で、コマンドと作成、テストを実行し、1 つの Windows ベースのグラフィック ユーザー インターフェイスでスクリプトをデバッグできます。 ISE は、右から左の言語の複数行の編集、タブ補完、構文の色分け、選択的な実行、状況依存のヘルプとサポートを提供します。 メニュー項目とキーボード ショートカットは、Windows PowerShell コンソールで実行する多数の同じタスクにマッピングされます。 たとえば、ISE でスクリプトをデバッグするときに、行のブレークポイントを設定する編集ウィンドウでコードを右クリックできます。

## <a name="support"></a>サポート

ISE は、Windows PowerShell V2 で初めて導入されたおよび PowerShell V3 を再設計されています。 ISE に Windows PowerShell となどの Windows PowerShell V5.1 のサポートされているすべてのバージョンでサポートされます。 ISE がただしは maintennce モードであり、新機能を追加する可能性はありません。
さらに、ISE で PowerShell v6 や他の製品のサポートはありません。 PowerShell スクリプトなどを管理するためのグラフィカル ツールとしているユーザーを考慮する必要があります[Visual Studio Code](https://code.visualstudio.com/)します。

## <a name="key-features"></a>主な機能

Windows PowerShell ISE の主要な機能は次のとおりです。

- 複数行の編集:[コマンド] ウィンドウで現在の行の下に空白行を挿入するには、SHIFT キーを押しながら ENTER キーを押します。
- 選択して実行する場合:スクリプトの一部を実行するには、実行するテキストを選択して、**[スクリプトの実行]** ボタンをクリックします。 または、F5 キーを押します。
- 状況依存ヘルプ:**Invoke-Item** と入力し、F1 キーを押します。 ヘルプ ファイルの **Invoke-Item** コマンドレットに関する記事が開きます。

Windows PowerShell ISE では、外観の一部をカスタマイズすることができます。 また、独自の Windows PowerShell プロファイル スクリプトもあります。

## <a name="to-start-the-windows-powershell-ise"></a>Windows PowerShell ISE を開始するには

**[スタート]** をクリックし、**[Windows PowerShell]** を選択して、**[Windows PowerShell ISE]** をクリックします。
代わりに、任意のコマンド シェルまたは [実行] ボックスに `powershell_ise.exe` を入力することも可能です。

## <a name="to-get-help-in-the-windows-powershell-ise"></a>Windows PowerShell ISE のヘルプを利用するには

**[ヘルプ]** メニューで、**[Windows PowerShell ヘルプ]** をクリックします。 または、F1 キーを押します。 開いたファイルは、Get-Help コマンドレットから利用できるすべてのヘルプを含む、Windows PowerShell ISE と Windows PowerShell について説明しています。
