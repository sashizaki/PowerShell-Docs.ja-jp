---
title: Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法
description: Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法
ms.date: 08/06/2018
ms.openlocfilehash: 983da850c13d72bcdc7b2d33970c6e9e06b3d869
ms.sourcegitcommit: 9df29dfc637191b62ca591893c251c1e02d4eb4c
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54012485"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a>Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法

VSCode の PowerShell の拡張機能は、PowerShell ISE での完全な機能パリティをシークは、中には、ISE のユーザーを VSCode エクスペリエンスをより自然な機能があります。

このドキュメントは、VSCode にユーザーの操作をもう少し詳しく理解するいると比較して、ISE で構成できる一覧の設定を試みます。

## <a name="key-bindings"></a>キー バインド

| 機能                              | ISE のバインド                  | VSCode のバインド                              |
| ----------------                      | -----------                  | --------------                              |
| 中断し、デバッガーを中断          | <kbd>Ctrl キーを押し</kbd>+<kbd>B</kbd> | <kbd>F6</kbd>                               |
| 現在の行/強調表示されているテキストを実行します。 | <kbd>F8</kbd>                | <kbd>F8</kbd>                               |
| 使用可能なスニペットの一覧               | <kbd>Ctrl</kbd>+<kbd>J</kbd> | <kbd>Ctrl キーを押し</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd> |

### <a name="custom-key-bindings"></a>カスタムのキー バインド

できます[独自のキー バインドを構成する](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)vscode もします。

## <a name="tab-completion"></a>Tab 補完機能

ISE のようなタブ補完よりを有効にするには、この設定を追加します。

```json
"editor.tabCompletion": "on"
```

> [!NOTE]
> この設定は、VSCode に直接 (ではなく、拡張機能) に追加されました。 その動作は、直接 VSCode によって決定され、拡張機能では変更できません。

## <a name="no-focus-on-console-when-executing"></a>コンソールを実行するときに対象なし

実行するときに、エディターで、フォーカスを保持する<kbd>F8</kbd>:

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

既定値は`true`アクセシビリティのためにします。

## <a name="dont-start-integrated-console-on-startup"></a>起動時に統合されたコンソールを起動しません。

起動時に、統合されたコンソールを停止するには、次のように設定します。

```json
"powershell.integratedConsole.showOnStartup": false
```

> [!NOTE]
> スクリプトの分析、シンボル ナビゲーションなど、IntelliSense を提供するためにも、バック グラウンドの PowerShell プロセスが開始されます。ただし、コンソールに表示されません。

## <a name="assume-files-are-powershell-by-default"></a>ファイルは、既定で PowerShell を前提としています

新しい/無題のファイルを作成するには、既定で PowerShell として登録します。

```json
"files.defaultLanguage": "powershell"
```

## <a name="color-scheme"></a>色スキーム

ISE のテーマは for VSCode の ISE ようになります、エディターを使用できます。

[コマンド パレット]型`theme`を取得する`Preferences: Color Theme`キーを押します<kbd>Enter</kbd>します。
ドロップダウン リストで選択`PowerShell ISE`します。

使用して、設定では、このテーマを設定できます。

```json
"workbench.colorTheme": "PowerShell ISE"
```

## <a name="powershell-command-explorer"></a>PowerShell コマンドのエクスプ ローラー

作業に協力してくれた[ @corbob ](https://github.com/corbob)PowerShell の拡張機能が、独自のコマンドのエクスプ ローラーの始点。

[コマンド パレット]、入力`PowerShell Command Explorer`キーを押します<kbd>Enter</kbd>します。

## <a name="open-in-the-ise"></a>ISE で開く

使用することができる場合は、ISE でファイルを開きますかしようとしている最終的には、 <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>。

## <a name="other-resources"></a>その他のリソース

- 4sysops が[すばらしい記事](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/)VSCode に ISE のような詳細を構成します。
- Mike F Robbins が[の優れた投稿](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/)VSCode の設定。
- PowerShell を調べる[上位の優れた書き込み](https://www.learnpwsh.com/setup-vs-code-for-powershell/)VSCode を取得するのには、PowerShell のセットアップします。

## <a name="more-settings"></a>詳細設定

ISE のユーザーのより親しみ VSCode にする方法のわかっている場合は、このドキュメントに貢献します。かどうかは探している、互換性の構成が有効にする方法を見つけることができません[issue](https://github.com/PowerShell/vscode-powershell/issues/new/choose)遠慮なくご質問および!

私たちは常に Pr と投稿も歓迎します。

## <a name="vscode-tips"></a>VSCode のヒント

### <a name="command-palette"></a>コマンド パレット

<kbd>F1</kbd>または<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd> + <kbd>シフト</kbd>+<kbd>P</kbd> macos)

VSCode でコマンドを実行する便利な方法です。
詳細については、次を参照してください。 [VSCode docs](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette)します。

[コマンド パレット]: #command-palette
