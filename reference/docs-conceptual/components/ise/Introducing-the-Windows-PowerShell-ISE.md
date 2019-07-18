---
ms.date: 08/14/2018
keywords: PowerShell, コマンドレット
title: Windows PowerShell ISE の紹介
ms.openlocfilehash: 729c8535dbcfcd2c51070b8beac5d328375f36ae
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057425"
---
# <a name="the-windows-powershell-ise"></a>Windows PowerShell ISE

Windows PowerShell Integrated Scripting Environment (ISE) は、Windows PowerShell のホスト アプリケーションです。 ISE では、コマンドを実行して、単一の Windows ベースのグラフィカル ユーザー インターフェイスでスクリプトの書き込み、テスト、およびデバッグを行うことが可能です。 ISE では、複数行の編集、タブ補完、構文の色分け、選択的な実行、状況依存のヘルプ、および右から左方向の言語のサポートを提供します。 メニュー項目とキーボード ショートカットは、Windows PowerShell コンソールで実行する多数の同じタスクにマッピングされます。 たとえば、ISE でスクリプトをデバッグするとき、編集ウィンドウでコード行を右クリックするとブレークポイントを設定できます。

## <a name="support"></a>サポート

ISE は、Windows PowerShell V2 で初めて導入され、PowerShell V3 で再設計されました。 ISE は、Windows PowerShell V5.1 までのすべてのサポートされているバージョンの Windows PowerShell でサポートされています。 ただし、ISE はメンテナンス モードであり、新しい機能は追加されない可能性があります。
また、PowerShell v6 以降では ISE はサポートされません。 PowerShell スクリプトなどを管理するためのグラフィカル ツールを利用するには、[Visual Studio Code](https://code.visualstudio.com/) を検討することをお勧めします。

## <a name="key-features"></a>主な機能

Windows PowerShell ISE の主な機能:

- 複数行の編集:[コマンド] ウィンドウで現在の行の下に空白行を挿入するには、Shift キーを押しながら Enter キーを押します。
- 選択して実行:スクリプトの一部を実行するには、実行するテキストを選択して、**[スクリプトの実行]** ボタンをクリックします。 または、F5 キーを押します。
- 状況依存ヘルプ:**Invoke-Item** と入力し、F1 キーを押します。 ヘルプ ファイルの **Invoke-Item** コマンドレットに関する記事が開きます。

Windows PowerShell ISE では、外観の一部をカスタマイズすることができます。 また、独自の Windows PowerShell プロファイル スクリプトもあります。

## <a name="to-start-the-windows-powershell-ise"></a>Windows PowerShell ISE を開始するには

**[スタート]** をクリックし、**[Windows PowerShell]** を選択して、**[Windows PowerShell ISE]** をクリックします。
代わりに、任意のコマンド シェルまたは [実行] ボックスに `powershell_ise.exe` を入力することも可能です。

## <a name="to-get-help-in-the-windows-powershell-ise"></a>Windows PowerShell ISE のヘルプを利用するには

**[ヘルプ]** メニューで、**[Windows PowerShell ヘルプ]** をクリックします。 または、F1 キーを押します。 開いたファイルは、Get-Help コマンドレットから利用できるすべてのヘルプを含む、Windows PowerShell ISE と Windows PowerShell について説明しています。
