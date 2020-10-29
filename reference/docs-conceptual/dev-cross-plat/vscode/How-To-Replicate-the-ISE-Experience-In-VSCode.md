---
title: Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法
description: Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法
ms.date: 08/06/2018
ms.openlocfilehash: 6b0b8ce054695d6cc0fc578290c554e2dc1472bc
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784624"
---
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a>Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法

VS Code 用の PowerShell 拡張機能は PowerShell ISE と完全に同等の機能を求めるものではありませんが、ISE のユーザーにとって VS Code のエクスペリエンスをより自然にする機能があります。

このドキュメントでは、ISE と比較してなじみのあるユーザー エクスペリエンスになるように VS Code で構成できる設定の一覧を紹介します。

## <a name="ise-mode"></a>ISE モード

> [!NOTE]
> この機能は、バージョン 2019.12.0 以降の PowerShell Preview 拡張機能、および バージョン2020.3.0 以降の PowerShell 拡張機能で使用できます。

Visual Studio Code で ISE のエクスペリエンスを最も簡単にレプリケートするには、"ISE モード" を有効にします。
これを行うには、コマンド パレット (<kbd>F1</kbd> または <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> または <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (macOS の場合)) を開き、「ISE モード」と入力します。 一覧から "PowerShell: ISE モードの有効化" を選択します。

このコマンドでは、下に説明する設定が自動的に適用されます。結果は次のようになります。

![ISE モードでの Visual Studio Code](media/How-To-Replicate-the-ISE-Experience-In-VSCode/3-ise-mode.png)

## <a name="ise-mode-configuration-settings"></a>ISE モードの構成設定

ISE モードでは VS Code 設定に対して次の変更が行われます。

- キー バインド

  |               機能                |         ISE バインド          |              VS Code バインド                |
  | ------------------------------------- | ---------------------------- | ------------------------------------------- |
  | デバッガーの割り込みと中断          | <kbd>Ctrl</kbd>+<kbd>B</kbd> | <kbd>F6</kbd>                               |
  | 現在の行/強調表示されているテキストを実行する | <kbd>F8</kbd>                | <kbd>F8</kbd>                               |
  | 使用できるスニペットを一覧表示する               | <kbd>Ctrl</kbd>+<kbd>J</kbd> | <kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd> |

  > [!NOTE]
  > VS Code でも[独自のキー バインドを構成](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)できます。

- 簡素化された ISE のような UI

  Visual Studio Code の UI を簡素化して ISE の UI により近づけたい場合は、次の 2 つの設定を適用します。

  ```json
  "workbench.activityBar.visible": false,
  "debug.openDebug": "neverOpen",
  ```

  これらの設定により、次の赤いボックス内に表示されている "アクティビティ バー" と "デバッグ サイド バー" のセクションが非表示になります。

  ![強調表示されたセクションにアクティビティ バーとデバッグ サイド バーが含まれています](media/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

  最終的な結果は次のようになります。

  ![VS Code の簡素化されたビュー](media/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

- Tab 補完機能

  さらに ISE に似たタブ補完を有効にするには、次の設定を追加します。

  ```json
  "editor.tabCompletion": "on",
  ```

- 実行時にコンソールにフォーカスなし

  <kbd>F8</kbd> キーで実行したときにエディターのフォーカスを維持するには:

  ```json
  "powershell.integratedConsole.focusConsoleOnExecute": false
  ```

  アクセシビリティのため、既定値は `true` です。

- スタートアップ時に統合コンソールを起動しない

  スタートアップ時に統合コンソールを停止するには、次のように設定します。

  ```json
  "powershell.integratedConsole.showOnStartup": false
  ```

  > [!NOTE]
  > バックグラウンドの PowerShell プロセスでは、IntelliSense、スクリプト分析、シンボル ナビゲーションなどの提供が引き続き開始されますが、コンソールは表示されません。

- 既定でファイルが PowerShell であると想定する

  新規/無題のファイルを作成するには、既定で PowerShell として登録します。

  ```json
  "files.defaultLanguage": "powershell",
  ```

- 配色

  エディターの外観を ISE に似せるために、VS Code で使用できる ISE テーマがいくつかあります。

  [[コマンド パレット]][] に「`theme`」と入力して `Preferences: Color Theme` を取得し、<kbd>Enter</kbd> キーを押します。 ドロップダウン リストから `PowerShell ISE` を選択します。

  このテーマは、次のように設定で指定できます。

  ```json
  "workbench.colorTheme": "PowerShell ISE",
  ```

- PowerShell コマンド エクスプローラー

  [@corbob](https://github.com/corbob) の機能により、PowerShell 拡張機能には独自のコマンド エクスプローラーの開始機能があります。

  [[コマンド パレット]][] に「`PowerShell Command Explorer`」と入力し、<kbd>Enter</kbd> キーを押します。

- ISE で開く

  Windows PowerShell ISE でファイルを開く場合は、 [[コマンド パレット]][] を開き、"ISE で開く" を検索して、 **[PowerShell: Open Current File in PowerShell ISE]\(PowerShell: PowerShell ISE で現在のファイルを開く\)** を選択します。

## <a name="other-resources"></a>その他のリソース

- 4sysops には、VS Code をより ISE に似せて構成する方法に関する[優れた記事][4sysops]が掲載されています。
- Mike F Robbins には VS Code の設定に関する[優れた投稿][mikefrobbins]があります。
<!-- - Learn PowerShell has [an excellent write up][learnpwsh] setup for PowerShell. -->

## <a name="vs-code-tips"></a>VS Code のヒント

- コマンド パレット

  コマンド パレットは、VS Code でコマンドを実行する便利な方法です。 コマンド パレットを開くには、<kbd>F1</kbd> または <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> または <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (macOS の場合) を使用します。

  詳細については、[VS Code のドキュメント][vsc-docs]を参照してください。

- デバッグ コンソールを無効にする

  PowerShell スクリプト用に VS Code のみを使用する計画である場合は、 **デバッグ コンソール** を非表示にすることができます。これは PowerShell 拡張機能では使用されないからです。 これを行うには、 **[デバッグ コンソール]** を右クリックしてから、それを非表示するためのチェック マークをオンにします。

## <a name="more-settings"></a>詳細設定

ISE ユーザーにとって VS Code をより身近に感じられるその他の方法をご存じであれば、このドキュメントにご協力ください。探している互換性の構成があり、それを有効にする方法がわからない場合は、[問題を開いて][]質問してください。

PR や寄付も常に歓迎しています。

<!-- link references -->
[vsc-docs]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette
[コマンド パレット]: #vs-code-tips
[問題を開いて]: https://github.com/PowerShell/VSCode-powershell/issues/new/choose

[4sysops]: https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/
[mikefrobbins]: https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/
[learnpwsh]: https://www.learnpwsh.com/setup-vs-code-for-powershell/
