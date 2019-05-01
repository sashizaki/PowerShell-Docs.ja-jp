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
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a><span data-ttu-id="cde8e-103">Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法</span><span class="sxs-lookup"><span data-stu-id="cde8e-103">How to replicate the ISE experience in Visual Studio Code</span></span>

<span data-ttu-id="cde8e-104">VSCode 用の PowerShell 拡張機能は PowerShell ISE と完全に同等の機能を求めるものではありませんが、ISE のユーザーにとって VSCode のエクスペリエンスをより自然にする機能があります。</span><span class="sxs-lookup"><span data-stu-id="cde8e-104">While the PowerShell extension for VSCode doesn't seek complete feature parity with the PowerShell ISE, there are features in place to make the VSCode experience more natural for users of the ISE.</span></span>

<span data-ttu-id="cde8e-105">このドキュメントでは、ISE と比較してなじみのあるユーザー エクスペリエンスになるように VSCode で構成できる設定の一覧を紹介します。</span><span class="sxs-lookup"><span data-stu-id="cde8e-105">This document tries to list settings you can configure in VSCode to make the user experience a bit more familiar compared to the ISE.</span></span>

## <a name="key-bindings"></a><span data-ttu-id="cde8e-106">キー バインド</span><span class="sxs-lookup"><span data-stu-id="cde8e-106">Key bindings</span></span>

| <span data-ttu-id="cde8e-107">機能</span><span class="sxs-lookup"><span data-stu-id="cde8e-107">Function</span></span>                              | <span data-ttu-id="cde8e-108">ISE バインド</span><span class="sxs-lookup"><span data-stu-id="cde8e-108">ISE Binding</span></span>                  | <span data-ttu-id="cde8e-109">VSCode バインド</span><span class="sxs-lookup"><span data-stu-id="cde8e-109">VSCode Binding</span></span>                              |
| ----------------                      | -----------                  | --------------                              |
| <span data-ttu-id="cde8e-110">デバッガーの割り込みと中断</span><span class="sxs-lookup"><span data-stu-id="cde8e-110">Interrupt and break debugger</span></span>          | <span data-ttu-id="cde8e-111"><kbd>Ctrl</kbd>+<kbd>B</kbd></span><span class="sxs-lookup"><span data-stu-id="cde8e-111"><kbd>Ctrl</kbd>+<kbd>B</kbd></span></span> | <span data-ttu-id="cde8e-112"><kbd>F6</kbd></span><span class="sxs-lookup"><span data-stu-id="cde8e-112"><kbd>F6</kbd></span></span>                               |
| <span data-ttu-id="cde8e-113">現在の行/強調表示されているテキストを実行する</span><span class="sxs-lookup"><span data-stu-id="cde8e-113">Execute current line/highlighted text</span></span> | <span data-ttu-id="cde8e-114"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="cde8e-114"><kbd>F8</kbd></span></span>                | <span data-ttu-id="cde8e-115"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="cde8e-115"><kbd>F8</kbd></span></span>                               |
| <span data-ttu-id="cde8e-116">使用できるスニペットを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="cde8e-116">List available snippets</span></span>               | <span data-ttu-id="cde8e-117"><kbd>Ctrl</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="cde8e-117"><kbd>Ctrl</kbd>+<kbd>J</kbd></span></span> | <span data-ttu-id="cde8e-118"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="cde8e-118"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span></span> |

### <a name="custom-key-bindings"></a><span data-ttu-id="cde8e-119">カスタム キー バインド</span><span class="sxs-lookup"><span data-stu-id="cde8e-119">Custom Key bindings</span></span>

<span data-ttu-id="cde8e-120">VSCode でも[独自のキー バインドを構成](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)できます。</span><span class="sxs-lookup"><span data-stu-id="cde8e-120">You can [configure your own key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) in VSCode as well.</span></span>

## <a name="tab-completion"></a><span data-ttu-id="cde8e-121">Tab 補完機能</span><span class="sxs-lookup"><span data-stu-id="cde8e-121">Tab completion</span></span>

<span data-ttu-id="cde8e-122">さらに ISE に似たタブ補完を有効にするには、次の設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="cde8e-122">To enable more ISE-like tab completion, add this setting:</span></span>

```json
"editor.tabCompletion": "on"
```

> [!NOTE]
> <span data-ttu-id="cde8e-123">この設定は (拡張機能ではなく) VSCode に直接追加されました。</span><span class="sxs-lookup"><span data-stu-id="cde8e-123">This setting was added directly to VSCode (rather than in the extension).</span></span> <span data-ttu-id="cde8e-124">その動作は VSCode によって直接決定され、拡張機能から変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="cde8e-124">Its behavior is determined by VSCode directly and cannot be changed by the extension.</span></span>

## <a name="no-focus-on-console-when-executing"></a><span data-ttu-id="cde8e-125">実行時のコンソールへのフォーカスなし</span><span class="sxs-lookup"><span data-stu-id="cde8e-125">No focus on console when executing</span></span>

<span data-ttu-id="cde8e-126"><kbd>F8</kbd> キーで実行したときにエディターのフォーカスを維持するには:</span><span class="sxs-lookup"><span data-stu-id="cde8e-126">To keep the focus in the editor when you execute with <kbd>F8</kbd>:</span></span>

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

<span data-ttu-id="cde8e-127">アクセシビリティのため、既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="cde8e-127">The default is `true` for accessibility purposes.</span></span>

## <a name="dont-start-integrated-console-on-startup"></a><span data-ttu-id="cde8e-128">スタートアップ時に統合コンソールを起動しない</span><span class="sxs-lookup"><span data-stu-id="cde8e-128">Don't start integrated console on startup</span></span>

<span data-ttu-id="cde8e-129">スタートアップ時に統合コンソールを停止するには、次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="cde8e-129">To stop the integrated console on startup, set:</span></span>

```json
"powershell.integratedConsole.showOnStartup": false
```

> [!NOTE]
> <span data-ttu-id="cde8e-130">バックグラウンドの PowerShell プロセスは、IntelliSense、スクリプト分析、シンボル ナビゲーションなどを提供しているため、起動します。ただし、コンソールは表示されません。</span><span class="sxs-lookup"><span data-stu-id="cde8e-130">The background PowerShell process will still start since that provides IntelliSense, script analysis, symbol navigation, etc. But the console won't be shown.</span></span>

## <a name="assume-files-are-powershell-by-default"></a><span data-ttu-id="cde8e-131">既定でファイルが PowerShell であると想定する</span><span class="sxs-lookup"><span data-stu-id="cde8e-131">Assume files are PowerShell by default</span></span>

<span data-ttu-id="cde8e-132">新規/無題のファイルを作成するには、既定で PowerShell として登録します。</span><span class="sxs-lookup"><span data-stu-id="cde8e-132">To make new/untitled files, register as PowerShell by default:</span></span>

```json
"files.defaultLanguage": "powershell"
```

## <a name="color-scheme"></a><span data-ttu-id="cde8e-133">配色</span><span class="sxs-lookup"><span data-stu-id="cde8e-133">Color scheme</span></span>

<span data-ttu-id="cde8e-134">エディターの外観を ISE に似せるために、VSCode で使用できる ISE テーマがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="cde8e-134">There are a number of ISE themes available for VSCode to make the editor look much more like the ISE.</span></span>

<span data-ttu-id="cde8e-135">[[コマンド パレット]] に「`theme`」と入力して `Preferences: Color Theme` を取得し、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cde8e-135">In the [Command Palette] type `theme` to get `Preferences: Color Theme` and press <kbd>Enter</kbd>.</span></span>
<span data-ttu-id="cde8e-136">ドロップダウン リストから `PowerShell ISE` を選択します。</span><span class="sxs-lookup"><span data-stu-id="cde8e-136">In the drop-down list, select `PowerShell ISE`.</span></span>

<span data-ttu-id="cde8e-137">このテーマは、次のように設定で指定できます。</span><span class="sxs-lookup"><span data-stu-id="cde8e-137">You can set this theme in the settings with:</span></span>

```json
"workbench.colorTheme": "PowerShell ISE"
```

## <a name="powershell-command-explorer"></a><span data-ttu-id="cde8e-138">PowerShell コマンド エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="cde8e-138">PowerShell Command Explorer</span></span>

<span data-ttu-id="cde8e-139">[@corbob](https://github.com/corbob) の機能により、PowerShell 拡張機能には独自のコマンド エクスプローラーの開始機能があります。</span><span class="sxs-lookup"><span data-stu-id="cde8e-139">Thanks to the work of [@corbob](https://github.com/corbob), the PowerShell extension has the beginnings of its own command explorer.</span></span>

<span data-ttu-id="cde8e-140">[[コマンド パレット]] に「`PowerShell Command Explorer`」と入力し、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cde8e-140">In the [Command Palette], enter `PowerShell Command Explorer` and press <kbd>Enter</kbd>.</span></span>

## <a name="open-in-the-ise"></a><span data-ttu-id="cde8e-141">ISE で開く</span><span class="sxs-lookup"><span data-stu-id="cde8e-141">Open in the ISE</span></span>

<span data-ttu-id="cde8e-142">どのような方法でも最終的には ISE でファイルを開く場合は、<kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd> キーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cde8e-142">If you end up wanting to open a file in the ISE anyway, you can use <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>.</span></span>

## <a name="other-resources"></a><span data-ttu-id="cde8e-143">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="cde8e-143">Other resources</span></span>

- <span data-ttu-id="cde8e-144">4sysops には、VSCode をより ISE に似せて構成する方法に関する[優れた記事](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/)が掲載されています。</span><span class="sxs-lookup"><span data-stu-id="cde8e-144">4sysops has [a great article](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) on configuring VSCode to be more like the ISE.</span></span>
- <span data-ttu-id="cde8e-145">Mike F Robbins には VSCode の設定に関する[優れた投稿](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/)があります。</span><span class="sxs-lookup"><span data-stu-id="cde8e-145">Mike F Robbins has [a great post](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) on setting up VSCode.</span></span>
- <span data-ttu-id="cde8e-146">Learn PowerShell には、PowerShell の VSCode の設定に関する[優れた記事](https://www.learnpwsh.com/setup-vs-code-for-powershell/)があります。</span><span class="sxs-lookup"><span data-stu-id="cde8e-146">Learn PowerShell has [an excellent write up](https://www.learnpwsh.com/setup-vs-code-for-powershell/) on getting VSCode setup for PowerShell.</span></span>

## <a name="more-settings"></a><span data-ttu-id="cde8e-147">詳細設定</span><span class="sxs-lookup"><span data-stu-id="cde8e-147">More settings</span></span>

<span data-ttu-id="cde8e-148">ISE ユーザーにとって VSCode をより身近に感じられるその他の方法をご存じであれば、このドキュメントにご協力ください。探している互換性の構成があり、それを有効にする方法がわからない場合は、[問題を開いて](https://github.com/PowerShell/vscode-powershell/issues/new/choose)質問してください。</span><span class="sxs-lookup"><span data-stu-id="cde8e-148">If you know of more ways to make VSCode feel more familiar for ISE users, contribute to this doc. If there's a compatibility configuration you're looking for, but you can't find any way to enable it, [open an issue](https://github.com/PowerShell/vscode-powershell/issues/new/choose) and ask away!</span></span>

<span data-ttu-id="cde8e-149">PR や寄付も常に歓迎しています。</span><span class="sxs-lookup"><span data-stu-id="cde8e-149">We're always happy to accept PRs and contributions as well!</span></span>

## <a name="vscode-tips"></a><span data-ttu-id="cde8e-150">VSCode のヒント</span><span class="sxs-lookup"><span data-stu-id="cde8e-150">VSCode Tips</span></span>

### <a name="command-palette"></a><span data-ttu-id="cde8e-151">コマンド パレット</span><span class="sxs-lookup"><span data-stu-id="cde8e-151">Command Palette</span></span>

<span data-ttu-id="cde8e-152"><kbd>F1</kbd> または <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (macOS 上では <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>)</span><span class="sxs-lookup"><span data-stu-id="cde8e-152"><kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS)</span></span>

<span data-ttu-id="cde8e-153">VSCode でコマンドを実行する便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="cde8e-153">A handy way of executing commands in VSCode.</span></span>
<span data-ttu-id="cde8e-154">詳細については、[VSCode のドキュメント](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cde8e-154">For more information, see [the VSCode docs](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).</span></span>

<span data-ttu-id="cde8e-155">[[コマンド パレット]]: #command-palette</span><span class="sxs-lookup"><span data-stu-id="cde8e-155">[Command Palette]: #command-palette</span></span>
