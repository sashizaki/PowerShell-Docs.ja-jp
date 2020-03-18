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
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a><span data-ttu-id="6b167-103">Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法</span><span class="sxs-lookup"><span data-stu-id="6b167-103">How to replicate the ISE experience in Visual Studio Code</span></span>

<span data-ttu-id="6b167-104">VSCode 用の PowerShell 拡張機能は PowerShell ISE と完全に同等の機能を求めるものではありませんが、ISE のユーザーにとって VSCode のエクスペリエンスをより自然にする機能があります。</span><span class="sxs-lookup"><span data-stu-id="6b167-104">While the PowerShell extension for VSCode doesn't seek complete feature parity with the PowerShell ISE, there are features in place to make the VSCode experience more natural for users of the ISE.</span></span>

<span data-ttu-id="6b167-105">このドキュメントでは、ISE と比較してなじみのあるユーザー エクスペリエンスになるように VSCode で構成できる設定の一覧を紹介します。</span><span class="sxs-lookup"><span data-stu-id="6b167-105">This document tries to list settings you can configure in VSCode to make the user experience a bit more familiar compared to the ISE.</span></span>

## <a name="ise-mode"></a><span data-ttu-id="6b167-106">ISE モード</span><span class="sxs-lookup"><span data-stu-id="6b167-106">ISE Mode</span></span>

> [!NOTE]
> <span data-ttu-id="6b167-107">この機能は、バージョン 2019.12.0 以降の PowerShell Preview 拡張機能、および バージョン2020.3.0 以降の PowerShell 拡張機能で使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b167-107">This feature is available in the PowerShell Preview extension since version 2019.12.0 and in the PowerShell extension since version 2020.3.0.</span></span>

<span data-ttu-id="6b167-108">Visual Studio Code で ISE のエクスペリエンスを最も簡単にレプリケートするには、"ISE モード" を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6b167-108">The easiest way to replicate the ISE experience in Visual Studio Code is by turning on "ISE Mode".</span></span>
<span data-ttu-id="6b167-109">これを行うには、コマンド パレット (<kbd>F1</kbd> または <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> または <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (macOS の場合)) を開き、「ISE モード」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6b167-109">To do this, open the command pallet (<kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> OR <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS) and type in "ISE Mode".</span></span>
<span data-ttu-id="6b167-110">一覧から "PowerShell: ISE モードの有効化" を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b167-110">Select "PowerShell: Enable ISE Mode" from the list.</span></span>

<span data-ttu-id="6b167-111">このコマンドを実行すると、このドキュメントに含まれる設定の多くが自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6b167-111">This command will apply a lot of the settings found in this document automatically.</span></span>
<span data-ttu-id="6b167-112">結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6b167-112">The result looks like this:</span></span>

![ISE モード](media/How-To-Replicate-the-ISE-Experience-In-VSCode/3-ise-mode.png)

<span data-ttu-id="6b167-114">この記事の残りの部分では、ISE モードの設定に関する詳細情報と、追加の設定をいくつか取り上げて説明します。</span><span class="sxs-lookup"><span data-stu-id="6b167-114">The rest of this article includes more detailed information on settings in ISE Mode and some additional settings.</span></span>

## <a name="key-bindings"></a><span data-ttu-id="6b167-115">キー バインド</span><span class="sxs-lookup"><span data-stu-id="6b167-115">Key bindings</span></span>

| <span data-ttu-id="6b167-116">Function</span><span class="sxs-lookup"><span data-stu-id="6b167-116">Function</span></span>                              | <span data-ttu-id="6b167-117">ISE バインド</span><span class="sxs-lookup"><span data-stu-id="6b167-117">ISE Binding</span></span>                  | <span data-ttu-id="6b167-118">VSCode バインド</span><span class="sxs-lookup"><span data-stu-id="6b167-118">VSCode Binding</span></span>                              |
| ----------------                      | -----------                  | --------------                              |
| <span data-ttu-id="6b167-119">デバッガーの割り込みと中断</span><span class="sxs-lookup"><span data-stu-id="6b167-119">Interrupt and break debugger</span></span>          | <span data-ttu-id="6b167-120"><kbd>Ctrl</kbd>+<kbd>B</kbd></span><span class="sxs-lookup"><span data-stu-id="6b167-120"><kbd>Ctrl</kbd>+<kbd>B</kbd></span></span> | <span data-ttu-id="6b167-121"><kbd>F6</kbd></span><span class="sxs-lookup"><span data-stu-id="6b167-121"><kbd>F6</kbd></span></span>                               |
| <span data-ttu-id="6b167-122">現在の行/強調表示されているテキストを実行する</span><span class="sxs-lookup"><span data-stu-id="6b167-122">Execute current line/highlighted text</span></span> | <span data-ttu-id="6b167-123"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="6b167-123"><kbd>F8</kbd></span></span>                | <span data-ttu-id="6b167-124"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="6b167-124"><kbd>F8</kbd></span></span>                               |
| <span data-ttu-id="6b167-125">使用できるスニペットを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="6b167-125">List available snippets</span></span>               | <span data-ttu-id="6b167-126"><kbd>Ctrl</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="6b167-126"><kbd>Ctrl</kbd>+<kbd>J</kbd></span></span> | <span data-ttu-id="6b167-127"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="6b167-127"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span></span> |

### <a name="custom-key-bindings"></a><span data-ttu-id="6b167-128">カスタム キー バインド</span><span class="sxs-lookup"><span data-stu-id="6b167-128">Custom Key bindings</span></span>

<span data-ttu-id="6b167-129">VSCode でも[独自のキー バインドを構成](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)できます。</span><span class="sxs-lookup"><span data-stu-id="6b167-129">You can [configure your own key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) in VSCode as well.</span></span>

## <a name="simplified-ise-like-ui"></a><span data-ttu-id="6b167-130">簡素化された ISE のような UI</span><span class="sxs-lookup"><span data-stu-id="6b167-130">Simplified ISE-like UI</span></span>

<span data-ttu-id="6b167-131">Visual Studio Code の UI を簡素化して ISE の UI により近づけたい場合は、次の 2 つの設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="6b167-131">If you're looking to simplify the Visual Studio Code UI to look more closely to the UI of the ISE, apply these two settings:</span></span>

```json
"workbench.activityBar.visible": false,
"debug.openDebug": "neverOpen",
```

> [!NOTE]
> <span data-ttu-id="6b167-132">これらの設定は "[ISE モード](#ise-mode)" に含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b167-132">These settings are included in ["ISE Mode"](#ise-mode).</span></span>

<span data-ttu-id="6b167-133">これにより、次の赤いボックス内にある "アクティビティ バー" と "デバッグ サイド バー" のセクションが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="6b167-133">This will hide the "Activity Bar" and the "Debug Side Bar" sections below inside of the red box:</span></span>

![強調表示されたセクションにはアクティビティ バーとデバッグ サイド バーが含まれている](media/How-To-Replicate-the-ISE-Experience-In-VSCode/1-highlighted-sidebar.png)

<span data-ttu-id="6b167-135">最終的な結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="6b167-135">The end result looks like this:</span></span>

![VS Code の簡素化されたビュー](media/How-To-Replicate-the-ISE-Experience-In-VSCode/2-simplified-ui.png)

## <a name="tab-completion"></a><span data-ttu-id="6b167-137">Tab 補完機能</span><span class="sxs-lookup"><span data-stu-id="6b167-137">Tab completion</span></span>

<span data-ttu-id="6b167-138">さらに ISE に似たタブ補完を有効にするには、次の設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="6b167-138">To enable more ISE-like tab completion, add this setting:</span></span>

```json
"editor.tabCompletion": "on",
```

> [!NOTE]
> <span data-ttu-id="6b167-139">この設定は (拡張機能ではなく) VSCode に直接追加されました。</span><span class="sxs-lookup"><span data-stu-id="6b167-139">This setting was added directly to VSCode (rather than in the extension).</span></span> <span data-ttu-id="6b167-140">その動作は VSCode によって直接決定され、拡張機能から変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6b167-140">Its behavior is determined by VSCode directly and cannot be changed by the extension.</span></span>

> [!NOTE]
> <span data-ttu-id="6b167-141">この設定は "[ISE モード](#ise-mode)" に含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b167-141">This setting is included in ["ISE Mode"](#ise-mode).</span></span>

## <a name="no-focus-on-console-when-executing"></a><span data-ttu-id="6b167-142">実行時にコンソールにフォーカスなし</span><span class="sxs-lookup"><span data-stu-id="6b167-142">No focus on console when executing</span></span>

<span data-ttu-id="6b167-143"><kbd>F8</kbd> キーで実行したときにエディターのフォーカスを維持するには:</span><span class="sxs-lookup"><span data-stu-id="6b167-143">To keep the focus in the editor when you execute with <kbd>F8</kbd>:</span></span>

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

> [!NOTE]
> <span data-ttu-id="6b167-144">この設定は "[ISE モード](#ise-mode)" に含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b167-144">This setting is included in ["ISE Mode"](#ise-mode).</span></span>

<span data-ttu-id="6b167-145">アクセシビリティのため、既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="6b167-145">The default is `true` for accessibility purposes.</span></span>

## <a name="dont-start-integrated-console-on-startup"></a><span data-ttu-id="6b167-146">スタートアップ時に統合コンソールを起動しない</span><span class="sxs-lookup"><span data-stu-id="6b167-146">Don't start integrated console on startup</span></span>

<span data-ttu-id="6b167-147">スタートアップ時に統合コンソールを停止するには、次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="6b167-147">To stop the integrated console on startup, set:</span></span>

```json
"powershell.integratedConsole.showOnStartup": false
```

> [!NOTE]
> <span data-ttu-id="6b167-148">バックグラウンドの PowerShell プロセスは、IntelliSense、スクリプト分析、シンボル ナビゲーションなどを提供しているため、起動します。ただし、コンソールは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6b167-148">The background PowerShell process will still start since that provides IntelliSense, script analysis, symbol navigation, etc. But the console won't be shown.</span></span>

## <a name="assume-files-are-powershell-by-default"></a><span data-ttu-id="6b167-149">既定でファイルが PowerShell であると想定する</span><span class="sxs-lookup"><span data-stu-id="6b167-149">Assume files are PowerShell by default</span></span>

<span data-ttu-id="6b167-150">新規/無題のファイルを作成するには、既定で PowerShell として登録します。</span><span class="sxs-lookup"><span data-stu-id="6b167-150">To make new/untitled files, register as PowerShell by default:</span></span>

```json
"files.defaultLanguage": "powershell",
```

> [!NOTE]
> <span data-ttu-id="6b167-151">この設定は "[ISE モード](#ise-mode)" に含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b167-151">This setting is included in ["ISE Mode"](#ise-mode).</span></span>

## <a name="color-scheme"></a><span data-ttu-id="6b167-152">配色</span><span class="sxs-lookup"><span data-stu-id="6b167-152">Color scheme</span></span>

<span data-ttu-id="6b167-153">エディターの外観を ISE に似せるために、VSCode で使用できる ISE テーマがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="6b167-153">There are a number of ISE themes available for VSCode to make the editor look much more like the ISE.</span></span>

<span data-ttu-id="6b167-154">[コマンド パレット] に「`theme`」と入力して `Preferences: Color Theme` を取得し、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6b167-154">In the [Command Palette] type `theme` to get `Preferences: Color Theme` and press <kbd>Enter</kbd>.</span></span>
<span data-ttu-id="6b167-155">ドロップダウン リストから `PowerShell ISE` を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b167-155">In the drop-down list, select `PowerShell ISE`.</span></span>

<span data-ttu-id="6b167-156">このテーマは、次のように設定で指定できます。</span><span class="sxs-lookup"><span data-stu-id="6b167-156">You can set this theme in the settings with:</span></span>

```json
"workbench.colorTheme": "PowerShell ISE",
```

> [!NOTE]
> <span data-ttu-id="6b167-157">この設定は "[ISE モード](#ise-mode)" に含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b167-157">This setting is included in ["ISE Mode"](#ise-mode).</span></span>

## <a name="powershell-command-explorer"></a><span data-ttu-id="6b167-158">PowerShell コマンド エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="6b167-158">PowerShell Command Explorer</span></span>

<span data-ttu-id="6b167-159">[@corbob](https://github.com/corbob) の機能により、PowerShell 拡張機能には独自のコマンド エクスプローラーの開始機能があります。</span><span class="sxs-lookup"><span data-stu-id="6b167-159">Thanks to the work of [@corbob](https://github.com/corbob), the PowerShell extension has the beginnings of its own command explorer.</span></span>

<span data-ttu-id="6b167-160">[コマンド パレット] に「`PowerShell Command Explorer`」と入力し、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6b167-160">In the [Command Palette], enter `PowerShell Command Explorer` and press <kbd>Enter</kbd>.</span></span>

> [!NOTE]
> <span data-ttu-id="6b167-161">これは自動的に "[ISE モード](#ise-mode)" で表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b167-161">This is shown automatically in ["ISE Mode"](#ise-mode).</span></span>

## <a name="open-in-the-ise"></a><span data-ttu-id="6b167-162">ISE で開く</span><span class="sxs-lookup"><span data-stu-id="6b167-162">Open in the ISE</span></span>

<span data-ttu-id="6b167-163">どのような方法でも最終的には ISE でファイルを開く場合は、<kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd> キーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b167-163">If you end up wanting to open a file in the ISE anyway, you can use <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>.</span></span>

## <a name="other-resources"></a><span data-ttu-id="6b167-164">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="6b167-164">Other resources</span></span>

- <span data-ttu-id="6b167-165">4sysops には、VSCode をより ISE に似せて構成する方法に関する[優れた記事](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/)が掲載されています。</span><span class="sxs-lookup"><span data-stu-id="6b167-165">4sysops has [a great article](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) on configuring VSCode to be more like the ISE.</span></span>
- <span data-ttu-id="6b167-166">Mike F Robbins には VSCode の設定に関する[優れた投稿](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/)があります。</span><span class="sxs-lookup"><span data-stu-id="6b167-166">Mike F Robbins has [a great post](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) on setting up VSCode.</span></span>
- <span data-ttu-id="6b167-167">Learn PowerShell には、PowerShell の VSCode の設定に関する[優れた記事](https://www.learnpwsh.com/setup-vs-code-for-powershell/)があります。</span><span class="sxs-lookup"><span data-stu-id="6b167-167">Learn PowerShell has [an excellent write up](https://www.learnpwsh.com/setup-vs-code-for-powershell/) on getting VSCode setup for PowerShell.</span></span>

## <a name="more-settings"></a><span data-ttu-id="6b167-168">詳細設定</span><span class="sxs-lookup"><span data-stu-id="6b167-168">More settings</span></span>

<span data-ttu-id="6b167-169">ISE ユーザーにとって VSCode をより身近に感じられるその他の方法をご存じであれば、このドキュメントにご協力ください。探している互換性の構成があり、それを有効にする方法がわからない場合は、[問題を開いて](https://github.com/PowerShell/vscode-powershell/issues/new/choose)質問してください。</span><span class="sxs-lookup"><span data-stu-id="6b167-169">If you know of more ways to make VSCode feel more familiar for ISE users, contribute to this doc. If there's a compatibility configuration you're looking for, but you can't find any way to enable it, [open an issue](https://github.com/PowerShell/vscode-powershell/issues/new/choose) and ask away!</span></span>

<span data-ttu-id="6b167-170">PR や寄付も常に歓迎しています。</span><span class="sxs-lookup"><span data-stu-id="6b167-170">We're always happy to accept PRs and contributions as well!</span></span>

## <a name="vscode-tips"></a><span data-ttu-id="6b167-171">VSCode のヒント</span><span class="sxs-lookup"><span data-stu-id="6b167-171">VSCode Tips</span></span>

### <a name="command-palette"></a><span data-ttu-id="6b167-172">コマンド パレット</span><span class="sxs-lookup"><span data-stu-id="6b167-172">Command Palette</span></span>

<span data-ttu-id="6b167-173"><kbd>F1</kbd> または <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (macOS 上では <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>)</span><span class="sxs-lookup"><span data-stu-id="6b167-173"><kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS)</span></span>

<span data-ttu-id="6b167-174">VSCode でコマンドを実行する便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="6b167-174">A handy way of executing commands in VSCode.</span></span>
<span data-ttu-id="6b167-175">詳細については、[VSCode のドキュメント](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b167-175">For more information, see [the VSCode docs](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).</span></span>

[コマンド パレット]: #command-palette
[Command Palette]: #command-palette
