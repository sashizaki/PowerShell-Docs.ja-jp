---
title: Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法
description: Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法
ms.date: 08/06/2018
ms.openlocfilehash: 193243dc2e3e921b22a6ee068370200ae84ce4ac
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78279260"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a>Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法

VSCode 用の PowerShell 拡張機能は PowerShell ISE と完全に同等の機能を求めるものではありませんが、ISE のユーザーにとって VSCode のエクスペリエンスをより自然にする機能があります。

このドキュメントでは、ISE と比較してなじみのあるユーザー エクスペリエンスになるように VSCode で構成できる設定の一覧を紹介します。

## <a name="ise-mode"></a>ISE モード

> [!NOTE]
> この機能は、バージョン 2019.12.0 以降の PowerShell Preview 拡張機能、および バージョン2020.3.0 以降の PowerShell 拡張機能で使用できます。

Visual Studio Code で ISE のエクスペリエンスを最も簡単にレプリケートするには、"ISE モード" を有効にします。
これを行うには、コマンド パレット (<kbd>F1</kbd> または <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> または <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (macOS の場合)) を開き、「ISE モード」と入力します。
一覧から "PowerShell: ISE モードの有効化" を選択します。

このコマンドを実行すると、このドキュメントに含まれる設定の多くが自動的に適用されます。
結果は次のようになります。

![ISE モード](media/How-To-Replicate-the-ISE-Experience-In-VSCode/3-ise-mode.png)

この記事の残りの部分では、ISE モードの設定に関する詳細情報と、追加の設定をいくつか取り上げて説明します。

## <a name="key-bindings"></a>キー バインド

| Function                              | ISE バインド                  | VSCode バインド                              |
| ----------------                      | -----------                  | --------------                              |
| デバッガーの割り込みと中断          | <kbd>Ctrl</kbd>+<kbd>B</kbd> | <kbd>F6</kbd>                               |
| 現在の行/強調表示されているテキストを実行する | <kbd>F8</kbd>                | <kbd>F8</kbd>                               |
| 使用できるスニペットを一覧表示する               | <kbd>Ctrl</kbd>+<kbd>J</kbd> | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd> |

### <a name="custom-key-bindings"></a>カスタム キー バインド

VSCode でも[独自のキー バインドを構成](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)できます。

## <a name="simplified-ise-like-ui"></a>簡素化された ISE のような UI

Visual Studio Code の UI を簡素化して ISE の UI により近づけたい場合は、次の 2 つの設定を適用します。

```json
"workbench.activityBar.visible": false,
"debug.openDebug": "neverOpen",
```

> [!NOTE]
> これらの設定は "[ISE モード](#ise-mode)" に含まれています。

これにより、次の赤いボックス内にある "アクティビティ バー" と "デバッグ サイド バー" のセクションが非表示になります。

![強調表示されたセクションにはアクティビティ バーとデバッグ サイド バーが含まれている](media/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

最終的な結果は次のようになります。

![VS Code の簡素化されたビュー](media/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

## <a name="tab-completion"></a>Tab 補完機能

さらに ISE に似たタブ補完を有効にするには、次の設定を追加します。

```json
"editor.tabCompletion": "on",
```

> [!NOTE]
> この設定は (拡張機能ではなく) VSCode に直接追加されました。 その動作は VSCode によって直接決定され、拡張機能から変更することはできません。

> [!NOTE]
> この設定は "[ISE モード](#ise-mode)" に含まれています。

## <a name="no-focus-on-console-when-executing"></a>実行時にコンソールにフォーカスなし

<kbd>F8</kbd> キーで実行したときにエディターのフォーカスを維持するには:

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

> [!NOTE]
> この設定は "[ISE モード](#ise-mode)" に含まれています。

アクセシビリティのため、既定値は `true` です。

## <a name="dont-start-integrated-console-on-startup"></a>スタートアップ時に統合コンソールを起動しない

スタートアップ時に統合コンソールを停止するには、次のように設定します。

```json
"powershell.integratedConsole.showOnStartup": false
```

> [!NOTE]
> バックグラウンドの PowerShell プロセスは、IntelliSense、スクリプト分析、シンボル ナビゲーションなどを提供しているため、起動します。ただし、コンソールは表示されません。

## <a name="assume-files-are-powershell-by-default"></a>既定でファイルが PowerShell であると想定する

新規/無題のファイルを作成するには、既定で PowerShell として登録します。

```json
"files.defaultLanguage": "powershell",
```

> [!NOTE]
> この設定は "[ISE モード](#ise-mode)" に含まれています。

## <a name="color-scheme"></a>配色

エディターの外観を ISE に似せるために、VSCode で使用できる ISE テーマがいくつかあります。

[コマンド パレット] に「`theme`」と入力して `Preferences: Color Theme` を取得し、<kbd>Enter</kbd> キーを押します。
ドロップダウン リストから `PowerShell ISE` を選択します。

このテーマは、次のように設定で指定できます。

```json
"workbench.colorTheme": "PowerShell ISE",
```

> [!NOTE]
> この設定は "[ISE モード](#ise-mode)" に含まれています。

## <a name="powershell-command-explorer"></a>PowerShell コマンド エクスプローラー

[@corbob](https://github.com/corbob) の機能により、PowerShell 拡張機能には独自のコマンド エクスプローラーの開始機能があります。

[コマンド パレット] に「`PowerShell Command Explorer`」と入力し、<kbd>Enter</kbd> キーを押します。

> [!NOTE]
> これは自動的に "[ISE モード](#ise-mode)" で表示されます。

## <a name="open-in-the-ise"></a>ISE で開く

どのような方法でも最終的には ISE でファイルを開く場合は、<kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd> キーを使用できます。

## <a name="other-resources"></a>その他のリソース

- 4sysops には、VSCode をより ISE に似せて構成する方法に関する[優れた記事](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/)が掲載されています。
- Mike F Robbins には VSCode の設定に関する[優れた投稿](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/)があります。
- Learn PowerShell には、PowerShell の VSCode の設定に関する[優れた記事](https://www.learnpwsh.com/setup-vs-code-for-powershell/)があります。

## <a name="more-settings"></a>詳細設定

ISE ユーザーにとって VSCode をより身近に感じられるその他の方法をご存じであれば、このドキュメントにご協力ください。探している互換性の構成があり、それを有効にする方法がわからない場合は、[問題を開いて](https://github.com/PowerShell/vscode-powershell/issues/new/choose)質問してください。

PR や寄付も常に歓迎しています。

## <a name="vscode-tips"></a>VSCode のヒント

### <a name="command-palette"></a>コマンド パレット

<kbd>F1</kbd> または <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (macOS 上では <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>)

VSCode でコマンドを実行する便利な方法です。
詳細については、[VSCode のドキュメント](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette)を参照してください。

[コマンド パレット]: #command-palette
