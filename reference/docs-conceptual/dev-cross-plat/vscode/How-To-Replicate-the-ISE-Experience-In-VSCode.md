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
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a><span data-ttu-id="9ef66-103">Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法</span><span class="sxs-lookup"><span data-stu-id="9ef66-103">How to replicate the ISE experience in Visual Studio Code</span></span>

<span data-ttu-id="9ef66-104">VS Code 用の PowerShell 拡張機能は PowerShell ISE と完全に同等の機能を求めるものではありませんが、ISE のユーザーにとって VS Code のエクスペリエンスをより自然にする機能があります。</span><span class="sxs-lookup"><span data-stu-id="9ef66-104">While the PowerShell extension for VS Code doesn't seek complete feature parity with the PowerShell ISE, there are features in place to make the VS Code experience more natural for users of the ISE.</span></span>

<span data-ttu-id="9ef66-105">このドキュメントでは、ISE と比較してなじみのあるユーザー エクスペリエンスになるように VS Code で構成できる設定の一覧を紹介します。</span><span class="sxs-lookup"><span data-stu-id="9ef66-105">This document tries to list settings you can configure in VS Code to make the user experience a bit more familiar compared to the ISE.</span></span>

## <a name="ise-mode"></a><span data-ttu-id="9ef66-106">ISE モード</span><span class="sxs-lookup"><span data-stu-id="9ef66-106">ISE Mode</span></span>

> [!NOTE]
> <span data-ttu-id="9ef66-107">この機能は、バージョン 2019.12.0 以降の PowerShell Preview 拡張機能、および バージョン2020.3.0 以降の PowerShell 拡張機能で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9ef66-107">This feature is available in the PowerShell Preview extension since version 2019.12.0 and in the PowerShell extension since version 2020.3.0.</span></span>

<span data-ttu-id="9ef66-108">Visual Studio Code で ISE のエクスペリエンスを最も簡単にレプリケートするには、"ISE モード" を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9ef66-108">The easiest way to replicate the ISE experience in Visual Studio Code is by turning on "ISE Mode".</span></span>
<span data-ttu-id="9ef66-109">これを行うには、コマンド パレット (<kbd>F1</kbd> または <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> または <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (macOS の場合)) を開き、「ISE モード」と入力します。</span><span class="sxs-lookup"><span data-stu-id="9ef66-109">To do this, open the command palette (<kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OR <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS) and type in "ISE Mode".</span></span> <span data-ttu-id="9ef66-110">一覧から "PowerShell: ISE モードの有効化" を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ef66-110">Select "PowerShell: Enable ISE Mode" from the list.</span></span>

<span data-ttu-id="9ef66-111">このコマンドでは、下に説明する設定が自動的に適用されます。結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9ef66-111">This command automatically applies the settings described below The result looks like this:</span></span>

![ISE モードでの Visual Studio Code](media/How-To-Replicate-the-ISE-Experience-In-VSCode/3-ise-mode.png)

## <a name="ise-mode-configuration-settings"></a><span data-ttu-id="9ef66-113">ISE モードの構成設定</span><span class="sxs-lookup"><span data-stu-id="9ef66-113">ISE Mode configuration settings</span></span>

<span data-ttu-id="9ef66-114">ISE モードでは VS Code 設定に対して次の変更が行われます。</span><span class="sxs-lookup"><span data-stu-id="9ef66-114">ISE Mode makes the following changes to VS Code settings.</span></span>

- <span data-ttu-id="9ef66-115">キー バインド</span><span class="sxs-lookup"><span data-stu-id="9ef66-115">Key bindings</span></span>

  |               <span data-ttu-id="9ef66-116">機能</span><span class="sxs-lookup"><span data-stu-id="9ef66-116">Function</span></span>                |         <span data-ttu-id="9ef66-117">ISE バインド</span><span class="sxs-lookup"><span data-stu-id="9ef66-117">ISE Binding</span></span>          |              <span data-ttu-id="9ef66-118">VS Code バインド</span><span class="sxs-lookup"><span data-stu-id="9ef66-118">VS Code Binding</span></span>                |
  | ------------------------------------- | ---------------------------- | ------------------------------------------- |
  | <span data-ttu-id="9ef66-119">デバッガーの割り込みと中断</span><span class="sxs-lookup"><span data-stu-id="9ef66-119">Interrupt and break debugger</span></span>          | <span data-ttu-id="9ef66-120"><kbd>Ctrl</kbd>+<kbd>B</kbd></span><span class="sxs-lookup"><span data-stu-id="9ef66-120"><kbd>Ctrl</kbd>+<kbd>B</kbd></span></span> | <span data-ttu-id="9ef66-121"><kbd>F6</kbd></span><span class="sxs-lookup"><span data-stu-id="9ef66-121"><kbd>F6</kbd></span></span>                               |
  | <span data-ttu-id="9ef66-122">現在の行/強調表示されているテキストを実行する</span><span class="sxs-lookup"><span data-stu-id="9ef66-122">Execute current line/highlighted text</span></span> | <span data-ttu-id="9ef66-123"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="9ef66-123"><kbd>F8</kbd></span></span>                | <span data-ttu-id="9ef66-124"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="9ef66-124"><kbd>F8</kbd></span></span>                               |
  | <span data-ttu-id="9ef66-125">使用できるスニペットを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="9ef66-125">List available snippets</span></span>               | <span data-ttu-id="9ef66-126"><kbd>Ctrl</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="9ef66-126"><kbd>Ctrl</kbd>+<kbd>J</kbd></span></span> | <span data-ttu-id="9ef66-127"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="9ef66-127"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span></span> |

  > [!NOTE]
  > <span data-ttu-id="9ef66-128">VS Code でも[独自のキー バインドを構成](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)できます。</span><span class="sxs-lookup"><span data-stu-id="9ef66-128">You can [configure your own key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) in VS Code as well.</span></span>

- <span data-ttu-id="9ef66-129">簡素化された ISE のような UI</span><span class="sxs-lookup"><span data-stu-id="9ef66-129">Simplified ISE-like UI</span></span>

  <span data-ttu-id="9ef66-130">Visual Studio Code の UI を簡素化して ISE の UI により近づけたい場合は、次の 2 つの設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="9ef66-130">If you're looking to simplify the Visual Studio Code UI to look more closely to the UI of the ISE, apply these two settings:</span></span>

  ```json
  "workbench.activityBar.visible": false,
  "debug.openDebug": "neverOpen",
  ```

  <span data-ttu-id="9ef66-131">これらの設定により、次の赤いボックス内に表示されている "アクティビティ バー" と "デバッグ サイド バー" のセクションが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="9ef66-131">These settings hide the "Activity Bar" and the "Debug Side Bar" sections shown inside the red box below:</span></span>

  ![強調表示されたセクションにアクティビティ バーとデバッグ サイド バーが含まれています](media/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

  <span data-ttu-id="9ef66-133">最終的な結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9ef66-133">The end result looks like this:</span></span>

  ![VS Code の簡素化されたビュー](media/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

- <span data-ttu-id="9ef66-135">Tab 補完機能</span><span class="sxs-lookup"><span data-stu-id="9ef66-135">Tab completion</span></span>

  <span data-ttu-id="9ef66-136">さらに ISE に似たタブ補完を有効にするには、次の設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="9ef66-136">To enable more ISE-like tab completion, add this setting:</span></span>

  ```json
  "editor.tabCompletion": "on",
  ```

- <span data-ttu-id="9ef66-137">実行時にコンソールにフォーカスなし</span><span class="sxs-lookup"><span data-stu-id="9ef66-137">No focus on console when executing</span></span>

  <span data-ttu-id="9ef66-138"><kbd>F8</kbd> キーで実行したときにエディターのフォーカスを維持するには:</span><span class="sxs-lookup"><span data-stu-id="9ef66-138">To keep the focus in the editor when you execute with <kbd>F8</kbd>:</span></span>

  ```json
  "powershell.integratedConsole.focusConsoleOnExecute": false
  ```

  <span data-ttu-id="9ef66-139">アクセシビリティのため、既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="9ef66-139">The default is `true` for accessibility purposes.</span></span>

- <span data-ttu-id="9ef66-140">スタートアップ時に統合コンソールを起動しない</span><span class="sxs-lookup"><span data-stu-id="9ef66-140">Don't start integrated console on startup</span></span>

  <span data-ttu-id="9ef66-141">スタートアップ時に統合コンソールを停止するには、次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="9ef66-141">To stop the integrated console on startup, set:</span></span>

  ```json
  "powershell.integratedConsole.showOnStartup": false
  ```

  > [!NOTE]
  > <span data-ttu-id="9ef66-142">バックグラウンドの PowerShell プロセスでは、IntelliSense、スクリプト分析、シンボル ナビゲーションなどの提供が引き続き開始されますが、コンソールは表示されません。</span><span class="sxs-lookup"><span data-stu-id="9ef66-142">The background PowerShell process still starts to provide IntelliSense, script analysis, symbol navigation, etc., but the console won't be shown.</span></span>

- <span data-ttu-id="9ef66-143">既定でファイルが PowerShell であると想定する</span><span class="sxs-lookup"><span data-stu-id="9ef66-143">Assume files are PowerShell by default</span></span>

  <span data-ttu-id="9ef66-144">新規/無題のファイルを作成するには、既定で PowerShell として登録します。</span><span class="sxs-lookup"><span data-stu-id="9ef66-144">To make new/untitled files, register as PowerShell by default:</span></span>

  ```json
  "files.defaultLanguage": "powershell",
  ```

- <span data-ttu-id="9ef66-145">配色</span><span class="sxs-lookup"><span data-stu-id="9ef66-145">Color scheme</span></span>

  <span data-ttu-id="9ef66-146">エディターの外観を ISE に似せるために、VS Code で使用できる ISE テーマがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="9ef66-146">There are a number of ISE themes available for VS Code to make the editor look much more like the ISE.</span></span>

  <span data-ttu-id="9ef66-147">[[コマンド パレット]][] に「`theme`」と入力して `Preferences: Color Theme` を取得し、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9ef66-147">In the [Command Palette][] type `theme` to get `Preferences: Color Theme` and press <kbd>Enter</kbd>.</span></span> <span data-ttu-id="9ef66-148">ドロップダウン リストから `PowerShell ISE` を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ef66-148">In the drop-down list, select `PowerShell ISE`.</span></span>

  <span data-ttu-id="9ef66-149">このテーマは、次のように設定で指定できます。</span><span class="sxs-lookup"><span data-stu-id="9ef66-149">You can set this theme in the settings with:</span></span>

  ```json
  "workbench.colorTheme": "PowerShell ISE",
  ```

- <span data-ttu-id="9ef66-150">PowerShell コマンド エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="9ef66-150">PowerShell Command Explorer</span></span>

  <span data-ttu-id="9ef66-151">[@corbob](https://github.com/corbob) の機能により、PowerShell 拡張機能には独自のコマンド エクスプローラーの開始機能があります。</span><span class="sxs-lookup"><span data-stu-id="9ef66-151">Thanks to the work of [@corbob](https://github.com/corbob), the PowerShell extension has the beginnings of its own command explorer.</span></span>

  <span data-ttu-id="9ef66-152">[[コマンド パレット]][] に「`PowerShell Command Explorer`」と入力し、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9ef66-152">In the [Command Palette][], enter `PowerShell Command Explorer` and press <kbd>Enter</kbd>.</span></span>

- <span data-ttu-id="9ef66-153">ISE で開く</span><span class="sxs-lookup"><span data-stu-id="9ef66-153">Open in the ISE</span></span>

  <span data-ttu-id="9ef66-154">Windows PowerShell ISE でファイルを開く場合は、 [[コマンド パレット]][] を開き、"ISE で開く" を検索して、 **[PowerShell: Open Current File in PowerShell ISE]\(PowerShell: PowerShell ISE で現在のファイルを開く\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9ef66-154">If you want to open a file in the Windows PowerShell ISE anyway, open the [Command Palette][], search for "open in ise", then select **PowerShell: Open Current File in PowerShell ISE** .</span></span>

## <a name="other-resources"></a><span data-ttu-id="9ef66-155">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="9ef66-155">Other resources</span></span>

- <span data-ttu-id="9ef66-156">4sysops には、VS Code をより ISE に似せて構成する方法に関する[優れた記事][4sysops]が掲載されています。</span><span class="sxs-lookup"><span data-stu-id="9ef66-156">4sysops has [a great article][4sysops] on configuring VS Code to be more like the ISE.</span></span>
- <span data-ttu-id="9ef66-157">Mike F Robbins には VS Code の設定に関する[優れた投稿][mikefrobbins]があります。</span><span class="sxs-lookup"><span data-stu-id="9ef66-157">Mike F Robbins has [a great post][mikefrobbins] on setting up VS Code.</span></span>
<!-- - Learn PowerShell has [an excellent write up][learnpwsh] setup for PowerShell. -->

## <a name="vs-code-tips"></a><span data-ttu-id="9ef66-158">VS Code のヒント</span><span class="sxs-lookup"><span data-stu-id="9ef66-158">VS Code Tips</span></span>

- <span data-ttu-id="9ef66-159">コマンド パレット</span><span class="sxs-lookup"><span data-stu-id="9ef66-159">Command Palette</span></span>

  <span data-ttu-id="9ef66-160">コマンド パレットは、VS Code でコマンドを実行する便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="9ef66-160">The Command Palette is handy way of executing commands in VS Code.</span></span> <span data-ttu-id="9ef66-161">コマンド パレットを開くには、<kbd>F1</kbd> または <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> または <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (macOS の場合) を使用します。</span><span class="sxs-lookup"><span data-stu-id="9ef66-161">Open the command palette using <kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OR <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS.</span></span>

  <span data-ttu-id="9ef66-162">詳細については、[VS Code のドキュメント][vsc-docs]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ef66-162">For more information, see [the VS Code documentation][vsc-docs].</span></span>

- <span data-ttu-id="9ef66-163">デバッグ コンソールを無効にする</span><span class="sxs-lookup"><span data-stu-id="9ef66-163">Disable the Debug Console</span></span>

  <span data-ttu-id="9ef66-164">PowerShell スクリプト用に VS Code のみを使用する計画である場合は、 **デバッグ コンソール** を非表示にすることができます。これは PowerShell 拡張機能では使用されないからです。</span><span class="sxs-lookup"><span data-stu-id="9ef66-164">If you only plan on using VS Code for PowerShell scripting, you can hide the **Debug Console** since it is not used by the PowerShell extension.</span></span> <span data-ttu-id="9ef66-165">これを行うには、 **[デバッグ コンソール]** を右クリックしてから、それを非表示するためのチェック マークをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9ef66-165">To do so, right click on **Debug Console** then click on the check mark to hide it.</span></span>

## <a name="more-settings"></a><span data-ttu-id="9ef66-166">詳細設定</span><span class="sxs-lookup"><span data-stu-id="9ef66-166">More settings</span></span>

<span data-ttu-id="9ef66-167">ISE ユーザーにとって VS Code をより身近に感じられるその他の方法をご存じであれば、このドキュメントにご協力ください。探している互換性の構成があり、それを有効にする方法がわからない場合は、[問題を開いて][]質問してください。</span><span class="sxs-lookup"><span data-stu-id="9ef66-167">If you know of more ways to make VS Code feel more familiar for ISE users, contribute to this doc. If there's a compatibility configuration you're looking for, but you can't find any way to enable it, [open an issue][] and ask away!</span></span>

<span data-ttu-id="9ef66-168">PR や寄付も常に歓迎しています。</span><span class="sxs-lookup"><span data-stu-id="9ef66-168">We're always happy to accept PRs and contributions as well!</span></span>

<!-- link references -->
[vsc-docs]: https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette
[コマンド パレット]: #vs-code-tips
[Command Palette]: #vs-code-tips
[問題を開いて]: https://github.com/PowerShell/VSCode-powershell/issues/new/choose
[open an issue]: https://github.com/PowerShell/VSCode-powershell/issues/new/choose

[4sysops]: https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/
[mikefrobbins]: https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/
[learnpwsh]: https://www.learnpwsh.com/setup-vs-code-for-powershell/
