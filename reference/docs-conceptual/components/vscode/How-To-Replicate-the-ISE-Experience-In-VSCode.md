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
# <a name="how-to-replicate-the-ise-experience-in-visual-studio-code"></a><span data-ttu-id="e47cb-103">Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法</span><span class="sxs-lookup"><span data-stu-id="e47cb-103">How to replicate the ISE experience in Visual Studio Code</span></span>

<span data-ttu-id="e47cb-104">VSCode の PowerShell の拡張機能は、PowerShell ISE での完全な機能パリティをシークは、中には、ISE のユーザーを VSCode エクスペリエンスをより自然な機能があります。</span><span class="sxs-lookup"><span data-stu-id="e47cb-104">While the PowerShell extension for VSCode doesn't seek complete feature parity with the PowerShell ISE, there are features in place to make the VSCode experience more natural for users of the ISE.</span></span>

<span data-ttu-id="e47cb-105">このドキュメントは、VSCode にユーザーの操作をもう少し詳しく理解するいると比較して、ISE で構成できる一覧の設定を試みます。</span><span class="sxs-lookup"><span data-stu-id="e47cb-105">This document tries to list settings you can configure in VSCode to make the user experience a bit more familiar compared to the ISE.</span></span>

## <a name="key-bindings"></a><span data-ttu-id="e47cb-106">キー バインド</span><span class="sxs-lookup"><span data-stu-id="e47cb-106">Key bindings</span></span>

| <span data-ttu-id="e47cb-107">機能</span><span class="sxs-lookup"><span data-stu-id="e47cb-107">Function</span></span>                              | <span data-ttu-id="e47cb-108">ISE のバインド</span><span class="sxs-lookup"><span data-stu-id="e47cb-108">ISE Binding</span></span>                  | <span data-ttu-id="e47cb-109">VSCode のバインド</span><span class="sxs-lookup"><span data-stu-id="e47cb-109">VSCode Binding</span></span>                              |
| ----------------                      | -----------                  | --------------                              |
| <span data-ttu-id="e47cb-110">中断し、デバッガーを中断</span><span class="sxs-lookup"><span data-stu-id="e47cb-110">Interrupt and break debugger</span></span>          | <span data-ttu-id="e47cb-111"><kbd>Ctrl キーを押し</kbd>+<kbd>B</kbd></span><span class="sxs-lookup"><span data-stu-id="e47cb-111"><kbd>Ctrl</kbd>+<kbd>B</kbd></span></span> | <span data-ttu-id="e47cb-112"><kbd>F6</kbd></span><span class="sxs-lookup"><span data-stu-id="e47cb-112"><kbd>F6</kbd></span></span>                               |
| <span data-ttu-id="e47cb-113">現在の行/強調表示されているテキストを実行します。</span><span class="sxs-lookup"><span data-stu-id="e47cb-113">Execute current line/highlighted text</span></span> | <span data-ttu-id="e47cb-114"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="e47cb-114"><kbd>F8</kbd></span></span>                | <span data-ttu-id="e47cb-115"><kbd>F8</kbd></span><span class="sxs-lookup"><span data-stu-id="e47cb-115"><kbd>F8</kbd></span></span>                               |
| <span data-ttu-id="e47cb-116">使用可能なスニペットの一覧</span><span class="sxs-lookup"><span data-stu-id="e47cb-116">List available snippets</span></span>               | <span data-ttu-id="e47cb-117"><kbd>Ctrl</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="e47cb-117"><kbd>Ctrl</kbd>+<kbd>J</kbd></span></span> | <span data-ttu-id="e47cb-118"><kbd>Ctrl キーを押し</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span><span class="sxs-lookup"><span data-stu-id="e47cb-118"><kbd>Ctrl</kbd>+<kbd>Alt</kbd>+<kbd>J</kbd></span></span> |

### <a name="custom-key-bindings"></a><span data-ttu-id="e47cb-119">カスタムのキー バインド</span><span class="sxs-lookup"><span data-stu-id="e47cb-119">Custom Key bindings</span></span>

<span data-ttu-id="e47cb-120">できます[独自のキー バインドを構成する](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings)vscode もします。</span><span class="sxs-lookup"><span data-stu-id="e47cb-120">You can [configure your own key bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_custom-keybindings-for-refactorings) in VSCode as well.</span></span>

## <a name="tab-completion"></a><span data-ttu-id="e47cb-121">Tab 補完機能</span><span class="sxs-lookup"><span data-stu-id="e47cb-121">Tab completion</span></span>

<span data-ttu-id="e47cb-122">ISE のようなタブ補完よりを有効にするには、この設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="e47cb-122">To enable more ISE-like tab completion, add this setting:</span></span>

```json
"editor.tabCompletion": "on"
```

> [!NOTE]
> <span data-ttu-id="e47cb-123">この設定は、VSCode に直接 (ではなく、拡張機能) に追加されました。</span><span class="sxs-lookup"><span data-stu-id="e47cb-123">This setting was added directly to VSCode (rather than in the extension).</span></span> <span data-ttu-id="e47cb-124">その動作は、直接 VSCode によって決定され、拡張機能では変更できません。</span><span class="sxs-lookup"><span data-stu-id="e47cb-124">Its behavior is determined by VSCode directly and cannot be changed by the extension.</span></span>

## <a name="no-focus-on-console-when-executing"></a><span data-ttu-id="e47cb-125">コンソールを実行するときに対象なし</span><span class="sxs-lookup"><span data-stu-id="e47cb-125">No focus on console when executing</span></span>

<span data-ttu-id="e47cb-126">実行するときに、エディターで、フォーカスを保持する<kbd>F8</kbd>:</span><span class="sxs-lookup"><span data-stu-id="e47cb-126">To keep the focus in the editor when you execute with <kbd>F8</kbd>:</span></span>

```json
"powershell.integratedConsole.focusConsoleOnExecute": false
```

<span data-ttu-id="e47cb-127">既定値は`true`アクセシビリティのためにします。</span><span class="sxs-lookup"><span data-stu-id="e47cb-127">The default is `true` for accessibility purposes.</span></span>

## <a name="dont-start-integrated-console-on-startup"></a><span data-ttu-id="e47cb-128">起動時に統合されたコンソールを起動しません。</span><span class="sxs-lookup"><span data-stu-id="e47cb-128">Don't start integrated console on startup</span></span>

<span data-ttu-id="e47cb-129">起動時に、統合されたコンソールを停止するには、次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="e47cb-129">To stop the integrated console on startup, set:</span></span>

```json
"powershell.integratedConsole.showOnStartup": false
```

> [!NOTE]
> <span data-ttu-id="e47cb-130">スクリプトの分析、シンボル ナビゲーションなど、IntelliSense を提供するためにも、バック グラウンドの PowerShell プロセスが開始されます。ただし、コンソールに表示されません。</span><span class="sxs-lookup"><span data-stu-id="e47cb-130">The background PowerShell process will still start since that provides IntelliSense, script analysis, symbol navigation, etc. But the console won't be shown.</span></span>

## <a name="assume-files-are-powershell-by-default"></a><span data-ttu-id="e47cb-131">ファイルは、既定で PowerShell を前提としています</span><span class="sxs-lookup"><span data-stu-id="e47cb-131">Assume files are PowerShell by default</span></span>

<span data-ttu-id="e47cb-132">新しい/無題のファイルを作成するには、既定で PowerShell として登録します。</span><span class="sxs-lookup"><span data-stu-id="e47cb-132">To make new/untitled files, register as PowerShell by default:</span></span>

```json
"files.defaultLanguage": "powershell"
```

## <a name="color-scheme"></a><span data-ttu-id="e47cb-133">色スキーム</span><span class="sxs-lookup"><span data-stu-id="e47cb-133">Color scheme</span></span>

<span data-ttu-id="e47cb-134">ISE のテーマは for VSCode の ISE ようになります、エディターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e47cb-134">There are a number of ISE themes available for VSCode to make the editor look much more like the ISE.</span></span>

<span data-ttu-id="e47cb-135">[コマンド パレット]型`theme`を取得する`Preferences: Color Theme`キーを押します<kbd>Enter</kbd>します。</span><span class="sxs-lookup"><span data-stu-id="e47cb-135">In the [Command Palette] type `theme` to get `Preferences: Color Theme` and press <kbd>Enter</kbd>.</span></span>
<span data-ttu-id="e47cb-136">ドロップダウン リストで選択`PowerShell ISE`します。</span><span class="sxs-lookup"><span data-stu-id="e47cb-136">In the drop-down list, select `PowerShell ISE`.</span></span>

<span data-ttu-id="e47cb-137">使用して、設定では、このテーマを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e47cb-137">You can set this theme in the settings with:</span></span>

```json
"workbench.colorTheme": "PowerShell ISE"
```

## <a name="powershell-command-explorer"></a><span data-ttu-id="e47cb-138">PowerShell コマンドのエクスプ ローラー</span><span class="sxs-lookup"><span data-stu-id="e47cb-138">PowerShell Command Explorer</span></span>

<span data-ttu-id="e47cb-139">作業に協力してくれた[ @corbob ](https://github.com/corbob)PowerShell の拡張機能が、独自のコマンドのエクスプ ローラーの始点。</span><span class="sxs-lookup"><span data-stu-id="e47cb-139">Thanks to the work of [@corbob](https://github.com/corbob), the PowerShell extension has the beginnings of its own command explorer.</span></span>

<span data-ttu-id="e47cb-140">[コマンド パレット]、入力`PowerShell Command Explorer`キーを押します<kbd>Enter</kbd>します。</span><span class="sxs-lookup"><span data-stu-id="e47cb-140">In the [Command Palette], enter `PowerShell Command Explorer` and press <kbd>Enter</kbd>.</span></span>

## <a name="open-in-the-ise"></a><span data-ttu-id="e47cb-141">ISE で開く</span><span class="sxs-lookup"><span data-stu-id="e47cb-141">Open in the ISE</span></span>

<span data-ttu-id="e47cb-142">使用することができる場合は、ISE でファイルを開きますかしようとしている最終的には、 <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>。</span><span class="sxs-lookup"><span data-stu-id="e47cb-142">If you end up wanting to open a file in the ISE anyway, you can use <kbd>Shift</kbd>+<kbd>Alt</kbd>+<kbd>P</kbd>.</span></span>

## <a name="other-resources"></a><span data-ttu-id="e47cb-143">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="e47cb-143">Other resources</span></span>

- <span data-ttu-id="e47cb-144">4sysops が[すばらしい記事](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/)VSCode に ISE のような詳細を構成します。</span><span class="sxs-lookup"><span data-stu-id="e47cb-144">4sysops has [a great article](https://4sysops.com/archives/make-visual-studio-code-look-and-behave-like-powershell-ise/) on configuring VSCode to be more like the ISE.</span></span>
- <span data-ttu-id="e47cb-145">Mike F Robbins が[の優れた投稿](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/)VSCode の設定。</span><span class="sxs-lookup"><span data-stu-id="e47cb-145">Mike F Robbins has [a great post](https://mikefrobbins.com/2017/08/24/how-to-install-visual-studio-code-and-configure-it-as-a-replacement-for-the-powershell-ise/) on setting up VSCode.</span></span>
- <span data-ttu-id="e47cb-146">PowerShell を調べる[上位の優れた書き込み](https://www.learnpwsh.com/setup-vs-code-for-powershell/)VSCode を取得するのには、PowerShell のセットアップします。</span><span class="sxs-lookup"><span data-stu-id="e47cb-146">Learn PowerShell has [an excellent write up](https://www.learnpwsh.com/setup-vs-code-for-powershell/) on getting VSCode setup for PowerShell.</span></span>

## <a name="more-settings"></a><span data-ttu-id="e47cb-147">詳細設定</span><span class="sxs-lookup"><span data-stu-id="e47cb-147">More settings</span></span>

<span data-ttu-id="e47cb-148">ISE のユーザーのより親しみ VSCode にする方法のわかっている場合は、このドキュメントに貢献します。かどうかは探している、互換性の構成が有効にする方法を見つけることができません[issue](https://github.com/PowerShell/vscode-powershell/issues/new/choose)遠慮なくご質問および!</span><span class="sxs-lookup"><span data-stu-id="e47cb-148">If you know of more ways to make VSCode feel more familiar for ISE users, contribute to this doc. If there's a compatibility configuration you're looking for, but you can't find any way to enable it, [open an issue](https://github.com/PowerShell/vscode-powershell/issues/new/choose) and ask away!</span></span>

<span data-ttu-id="e47cb-149">私たちは常に Pr と投稿も歓迎します。</span><span class="sxs-lookup"><span data-stu-id="e47cb-149">We're always happy to accept PRs and contributions as well!</span></span>

## <a name="vscode-tips"></a><span data-ttu-id="e47cb-150">VSCode のヒント</span><span class="sxs-lookup"><span data-stu-id="e47cb-150">VSCode Tips</span></span>

### <a name="command-palette"></a><span data-ttu-id="e47cb-151">コマンド パレット</span><span class="sxs-lookup"><span data-stu-id="e47cb-151">Command Palette</span></span>

<span data-ttu-id="e47cb-152"><kbd>F1</kbd>または<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd> + <kbd>シフト</kbd>+<kbd>P</kbd> macos)</span><span class="sxs-lookup"><span data-stu-id="e47cb-152"><kbd>F1</kbd> OR <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS)</span></span>

<span data-ttu-id="e47cb-153">VSCode でコマンドを実行する便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="e47cb-153">A handy way of executing commands in VSCode.</span></span>
<span data-ttu-id="e47cb-154">詳細については、次を参照してください。 [VSCode docs](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette)します。</span><span class="sxs-lookup"><span data-stu-id="e47cb-154">For more information, see [the VSCode docs](https://code.visualstudio.com/docs/getstarted/userinterface#_command-palette).</span></span>

[コマンド パレット]: #command-palette
[Command Palette]: #command-palette
