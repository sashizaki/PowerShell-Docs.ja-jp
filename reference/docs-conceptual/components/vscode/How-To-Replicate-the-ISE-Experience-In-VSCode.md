---
title: Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法
description: Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法
ms.date: 08/06/2018
ms.openlocfilehash: 983da850c13d72bcdc7b2d33970c6e9e06b3d869
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058524"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a>Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法

VSCode 用の PowerShell 拡張機能は PowerShell ISE と完全に同等の機能を求めるものではありませんが、ISE のユーザーにとって VSCode のエクスペリエンスをより自然にする機能があります。

このドキュメントでは、ISE と比較してなじみのあるユーザー エクスペリエンスになるように VSCode で構成できる設定の一覧を紹介します。

## <a name="key-bindings"></a>キー バインド

| 機能                              | ISE バインド                  | VSCode バインド                              |
| ----------------                      | -----------                  | --------------                              |
| デバッガーの割り込みと中断          | <kbd>Ctrl</kbd>+<kbd>B</kbd> | <kbd>F6</kbd>                               |
| 現在の行/強調表示されているテキストを実行する | <kbd>F8</kbd>                | <kbd>F8</kbd>                               |
| 使用できるスニペットを一覧表示する               | <kbd>Ctrl</kbd>+<kbd>J</kbd> | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd> |

### <a name="custom-key-bindings"></a>カスタム キー バインド

VSCode でも[独自のキー バインドを構成](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)できます。

## <a name="tab-completion"></a>Tab 補完機能

さらに ISE に似たタブ補完を有効にするには、次の設定を追加します。

```json
"editor.tabCompletion": "on"
```

> [!NOTE]
> この設定は (拡張機能ではなく) VSCode に直接追加されました。 その動作は VSCode によって直接決定され、拡張機能から変更することはできません。

## <a name="no-focus-on-console-when-executing"></a>実行時のコンソールへのフォーカスなし

<kbd>F8</kbd> キーで実行したときにエディターのフォーカスを維持するには:

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

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
"files.defaultLanguage": "powershell"
```

## <a name="color-scheme"></a>配色

エディターの外観を ISE に似せるために、VSCode で使用できる ISE テーマがいくつかあります。

[コマンド パレット] に「`theme`」と入力して `Preferences: Color Theme` を取得し、<kbd>Enter</kbd> キーを押します。
ドロップダウン リストから `PowerShell ISE` を選択します。

このテーマは、次のように設定で指定できます。

```json
"workbench.colorTheme": "PowerShell ISE"
```

## <a name="powershell-command-explorer"></a>PowerShell コマンド エクスプローラー

[@corbob](https://github.com/corbob) の機能により、PowerShell 拡張機能には独自のコマンド エクスプローラーの開始機能があります。

[コマンド パレット] に「`PowerShell Command Explorer`」と入力し、<kbd>Enter</kbd> キーを押します。

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
