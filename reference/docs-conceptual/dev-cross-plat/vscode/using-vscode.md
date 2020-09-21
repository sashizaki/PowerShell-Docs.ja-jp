---
title: PowerShell 開発のための Visual Studio Code の使用
description: PowerShell 開発のための Visual Studio Code の使用
ms.date: 11/07/2019
ms.openlocfilehash: 181746e7d3df2880223d1f15a0c8b99b324f5b98
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782533"
---
# <a name="using-visual-studio-code-for-powershell-development"></a><span data-ttu-id="d36ee-103">PowerShell 開発のための Visual Studio Code の使用</span><span class="sxs-lookup"><span data-stu-id="d36ee-103">Using Visual Studio Code for PowerShell Development</span></span>

<span data-ttu-id="d36ee-104">[Visual Studio Code][vscode] は、Microsoft によるクロスプラットフォームのスクリプト エディターです。</span><span class="sxs-lookup"><span data-stu-id="d36ee-104">[Visual Studio Code][vscode] is a cross-platform script editor by Microsoft.</span></span> <span data-ttu-id="d36ee-105">[PowerShell 拡張機能][psext]と共に使用すると、充実した対話型のスクリプト編集エクスペリエンスがもたらされ、信頼性の高い PowerShell スクリプトを簡単に記述できます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-105">Together with the [PowerShell extension][psext], it provides a rich and interactive script editing experience, making it easier to write reliable PowerShell scripts.</span></span> <span data-ttu-id="d36ee-106">PowerShell スクリプトの記述に使用するエディターとしては、PowerShell 拡張機能を備えた Visual Studio Code をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d36ee-106">Visual Studio Code with the PowerShell extension is the recommended editor for writing PowerShell scripts.</span></span>

<span data-ttu-id="d36ee-107">次の PowerShell バージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d36ee-107">It supports the following PowerShell versions:</span></span>

- <span data-ttu-id="d36ee-108">PowerShell 7 以上 (Windows、macOS、および Linux)</span><span class="sxs-lookup"><span data-stu-id="d36ee-108">PowerShell 7 and up (Windows, macOS, and Linux)</span></span>
- <span data-ttu-id="d36ee-109">PowerShell Core 6 (Windows、macOS、および Linux)</span><span class="sxs-lookup"><span data-stu-id="d36ee-109">PowerShell Core 6 (Windows, macOS, and Linux)</span></span>
- <span data-ttu-id="d36ee-110">Windows PowerShell 5.1 (Windows のみ)</span><span class="sxs-lookup"><span data-stu-id="d36ee-110">Windows PowerShell 5.1 (Windows-only)</span></span>

> [!NOTE]
> <span data-ttu-id="d36ee-111">Visual Studio Code は、[Visual Studio][] と同じものではありません。</span><span class="sxs-lookup"><span data-stu-id="d36ee-111">Visual Studio Code is not the same as [Visual Studio][].</span></span>

## <a name="getting-started"></a><span data-ttu-id="d36ee-112">作業の開始</span><span class="sxs-lookup"><span data-stu-id="d36ee-112">Getting started</span></span>

<span data-ttu-id="d36ee-113">開始する前に、システムに PowerShell があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-113">Before you begin, make sure PowerShell exists on your system.</span></span> <span data-ttu-id="d36ee-114">Windows、macOS、Linux 上の最近のワークロードに対しては、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d36ee-114">For modern workloads on Windows, macOS, and Linux, see the following links:</span></span>

- <span data-ttu-id="d36ee-115">[Linux への PowerShell のインストール][install-pscore-linux]</span><span class="sxs-lookup"><span data-stu-id="d36ee-115">[Installing PowerShell on Linux][install-pscore-linux]</span></span>
- <span data-ttu-id="d36ee-116">[macOS への PowerShell のインストール][install-pscore-macos]</span><span class="sxs-lookup"><span data-stu-id="d36ee-116">[Installing PowerShell on macOS][install-pscore-macos]</span></span>
- <span data-ttu-id="d36ee-117">[Windows への PowerShell のインストール][install-pscore-windows]</span><span class="sxs-lookup"><span data-stu-id="d36ee-117">[Installing PowerShell on Windows][install-pscore-windows]</span></span>

<span data-ttu-id="d36ee-118">従来の Windows PowerShell ワークロードについては、「[Windows PowerShell のインストール][install-winps]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d36ee-118">For traditional Windows PowerShell workloads, see [Installing Windows PowerShell][install-winps].</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d36ee-119">[Windows PowerShell ISE][ise] は引き続き Windows で使用できます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-119">The [Windows PowerShell ISE][ise] is still available for Windows.</span></span> <span data-ttu-id="d36ee-120">ただし、アクティブな機能開発の対象ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d36ee-120">However, it is no longer in active feature development.</span></span> <span data-ttu-id="d36ee-121">ISE は、PowerShell 6 以降では機能しません。</span><span class="sxs-lookup"><span data-stu-id="d36ee-121">The ISE does not work with PowerShell 6 and higher.</span></span> <span data-ttu-id="d36ee-122">Windows のコンポーネントとして、セキュリティや優先順位の高いサービスに関する修正プログラムが引き続き公式でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-122">As a component of Windows, it continues to be officially supported for security and high-priority servicing fixes.</span></span>
> <span data-ttu-id="d36ee-123">Windows から ISE が削除される予定はありません。</span><span class="sxs-lookup"><span data-stu-id="d36ee-123">We have no plans to remove the ISE from Windows.</span></span>

## <a name="editing-with-visual-studio-code"></a><span data-ttu-id="d36ee-124">Visual Studio Code を使用した編集</span><span class="sxs-lookup"><span data-stu-id="d36ee-124">Editing with Visual Studio Code</span></span>

1. <span data-ttu-id="d36ee-125">Visual Studio Code をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d36ee-125">Install Visual Studio Code.</span></span> <span data-ttu-id="d36ee-126">詳細については、「[Visual Studio Code の設定][vsc-setup]」という概要ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d36ee-126">For more information, see the overview [Setting up Visual Studio Code][vsc-setup].</span></span>

   <span data-ttu-id="d36ee-127">プラットフォーム別のインストール手順があります。</span><span class="sxs-lookup"><span data-stu-id="d36ee-127">There are installation instructions for each platform:</span></span>

   - <span data-ttu-id="d36ee-128">**Windows**: [Windows 上での Visual Studio Code の実行][vsc-setup-win]に関するページに記載されているインストール手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d36ee-128">**Windows**: follow the installation instructions on the [Running Visual Studio Code on Windows][vsc-setup-win] page.</span></span>
   - <span data-ttu-id="d36ee-129">**macOS**: [macOS 上での Visual Studio Code の実行][vsc-setup-macOS]に関するページに記載されているインストール手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d36ee-129">**macOS**: follow the installation instructions on the [Running Visual Studio Code on macOS][vsc-setup-macOS] page.</span></span>
   - <span data-ttu-id="d36ee-130">**Linux**: [Linux 上での Visual Studio Code の実行][vsc-setup-linux]に関するページに記載されているインストール手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="d36ee-130">**Linux**: follow the installation instructions on the [Running Visual Studio Code on Linux][vsc-setup-linux] page.</span></span>

1. <span data-ttu-id="d36ee-131">PowerShell 拡張機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d36ee-131">Install the PowerShell Extension.</span></span>

   1. <span data-ttu-id="d36ee-132">コンソールで「`code`」と入力するか、Visual Studio Code Insiders をインストールした場合は「`code-insiders`」と入力して、Visual Studio Code アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-132">Launch the Visual Studio Code app by typing `code` in a console or `code-insiders` if you installed Visual Studio Code Insiders.</span></span>
   1. <span data-ttu-id="d36ee-133">Windows または Linux の場合、<kbd>Ctrl</kbd>+<kbd>P</kbd> を押し、**Quick Open** を起動します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-133">Launch **Quick Open** on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="d36ee-134">macOS の場合、<kbd>Cmd</kbd>+<kbd>P</kbd> を押します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-134">On macOS, press <kbd>Cmd</kbd>+<kbd>P</kbd>.</span></span>
   1. <span data-ttu-id="d36ee-135">Quick Open を開き、「`ext install powershell`」と入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-135">In Quick Open, type `ext install powershell` and press **Enter**.</span></span>
   1. <span data-ttu-id="d36ee-136">サイド バーに **[拡張機能]** ビューが開きます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-136">The **Extensions** view opens on the Side Bar.</span></span> <span data-ttu-id="d36ee-137">Microsoft の PowerShell の拡張機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-137">Select the PowerShell extension from Microsoft.</span></span>
      <span data-ttu-id="d36ee-138">次の画像のような Visual Studio Code の画面が表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="d36ee-138">You should see a Visual Studio Code screen similar to the following image:</span></span>

      ![Visual Studio Code - PowerShell 拡張機能の表示](media/using-vscode/vscode.png)

   1. <span data-ttu-id="d36ee-140">Microsoft の PowerShell 拡張機能の、 **[インストール]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d36ee-140">Click the **Install** button on the PowerShell extension from Microsoft.</span></span>
   1. <span data-ttu-id="d36ee-141">インストール後、 **[インストール]** ボタンが **[再読み込み]** に変わった場合は、 **[再読み込み]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d36ee-141">After the install, if you see the **Install** button turn into **Reload**, Click on **Reload**.</span></span>
   1. <span data-ttu-id="d36ee-142">Visual Studio Code が再読み込みされたら、編集が可能になります。</span><span class="sxs-lookup"><span data-stu-id="d36ee-142">After Visual Studio Code has reloaded, you're ready for editing.</span></span>

<span data-ttu-id="d36ee-143">たとえば、新しいファイルを作成するには、 **[ファイル]、[新規]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d36ee-143">For example, to create a new file, click **File > New**.</span></span> <span data-ttu-id="d36ee-144">保存するには、 **[ファイル]、[保存]** の順にクリックし、`HelloWorld.ps1` のようなファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-144">To save it, click **File > Save** and then provide a file name, such as `HelloWorld.ps1`.</span></span> <span data-ttu-id="d36ee-145">ファイルを閉じるには、ファイル名の横の `X` をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d36ee-145">To close the file, click the `X` next to the file name.</span></span> <span data-ttu-id="d36ee-146">Visual Studio Code を終了するには、 **[ファイル] > [終了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-146">To exit Visual Studio Code, **File > Exit**.</span></span>

### <a name="installing-the-powershell-extension-on-restricted-systems"></a><span data-ttu-id="d36ee-147">制限されているシステムへの PowerShell 拡張機能のインストール</span><span class="sxs-lookup"><span data-stu-id="d36ee-147">Installing the PowerShell Extension on Restricted Systems</span></span>

<span data-ttu-id="d36ee-148">一部のシステムは、すべてのコード署名の検証を要求するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="d36ee-148">Some systems are set up to require validation of all code signatures.</span></span> <span data-ttu-id="d36ee-149">次のエラーが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d36ee-149">You may receive the following error:</span></span>

```
Language server startup failed.
```

<span data-ttu-id="d36ee-150">この問題は、PowerShell の実行ポリシーが Windows グループ ポリシーによって設定されている場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d36ee-150">This problem can occur when PowerShell's execution policy is set by Windows Group Policy.</span></span> <span data-ttu-id="d36ee-151">PowerShell エディター サービスおよび Visual Studio Code 用 PowerShell 拡張機能を手動で承認するには、PowerShell プロンプトを開いて次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-151">To manually approve PowerShell Editor Services and the PowerShell extension for Visual Studio Code, open a PowerShell prompt and run the following command:</span></span>

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

<span data-ttu-id="d36ee-152">"**この信頼されていない発行元からのソフトウェアを実行しますか?** " というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-152">You're prompted with **Do you want to run software from this untrusted publisher?**</span></span> <span data-ttu-id="d36ee-153">`A` キーを押してファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-153">Type `A` to run the file.</span></span> <span data-ttu-id="d36ee-154">次に、Visual Studio Code を開き、PowerShell 拡張機能が正しく機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-154">Then, open Visual Studio Code and check that the PowerShell extension is functioning properly.</span></span> <span data-ttu-id="d36ee-155">まだ問題が解決しない場合は、[GitHub の問題][]でお知らせください。</span><span class="sxs-lookup"><span data-stu-id="d36ee-155">If you still have problems getting started, let us know on [GitHub issues][].</span></span>

> [!NOTE]
> <span data-ttu-id="d36ee-156">Visual Studio Code 用 PowerShell 拡張機能では、制約付き言語モードでの実行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d36ee-156">The PowerShell extension for Visual Studio Code does not support running in constrained language mode.</span></span> <span data-ttu-id="d36ee-157">詳細については、[GitHub の問題 #606][i606] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d36ee-157">For more information, see [GitHub issue #606][i606].</span></span>

### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a><span data-ttu-id="d36ee-158">拡張機能で使用する PowerShell のバージョンを選択</span><span class="sxs-lookup"><span data-stu-id="d36ee-158">Choosing a version of PowerShell to use with the extension</span></span>

<span data-ttu-id="d36ee-159">Windows PowerShell と PowerShell Core がインストールされている場合、PowerShell の特定のバージョンを PowerShell の拡張機能で使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d36ee-159">With PowerShell Core installing side-by-side with Windows PowerShell, it's now possible to use a specific version of PowerShell with the PowerShell extension.</span></span> <span data-ttu-id="d36ee-160">この機能では、異なるオペレーティング システム上のいくつかのよく知られているパスを検索して、PowerShell のインストールが検出されます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-160">This feature looks at a few well-known paths on different operating systems to discover installations of PowerShell.</span></span>

<span data-ttu-id="d36ee-161">バージョンは次の手順で選択します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-161">Use the following steps to choose the version:</span></span>

1. <span data-ttu-id="d36ee-162">Windows または Linux の場合、<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> を使用して**コマンド パレット**を開きます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-162">Open the **Command Palette** on Windows or Linux with <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="d36ee-163">macOS の場合、<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> を使用します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-163">On macOS, use <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span>
1. <span data-ttu-id="d36ee-164">"**セッション**" を検索します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-164">Search for **Session**.</span></span>
1. <span data-ttu-id="d36ee-165">**[PowerShell: Show Session Menu]\(PowerShell: セッション メニューを表示\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d36ee-165">Click on **PowerShell: Show Session Menu**.</span></span>
1. <span data-ttu-id="d36ee-166">一覧から、"**PowerShell Core**" など、使用する PowerShell のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-166">Choose the version of PowerShell you want to use from the list, for example: **PowerShell Core**.</span></span>

<span data-ttu-id="d36ee-167">PowerShell を一般的ではない場所にインストールしている場合、最初にそれがセッション メニューに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="d36ee-167">If you installed PowerShell to a non-typical location, it might not show up initially in the Session Menu.</span></span> <span data-ttu-id="d36ee-168">次のように、[独自のカスタム パスを追加して](#adding-your-own-powershell-paths-to-the-session-menu)、セッション メニューを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-168">You can extend the session menu by [adding your own custom paths](#adding-your-own-powershell-paths-to-the-session-menu) as described below.</span></span>

> [!NOTE]
> <span data-ttu-id="d36ee-169">PowerShell セッション メニューには、ステータス バーの右下隅にある緑のバージョン番号からアクセスすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-169">The PowerShell session menu can also be accessed from the green version number in the bottom right corner of status bar.</span></span> <span data-ttu-id="d36ee-170">このバージョン番号をクリックすると、セッション メニューが開かれます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-170">Clicking this version number opens the session menu.</span></span>

## <a name="configuration-settings-for-visual-studio-code"></a><span data-ttu-id="d36ee-171">Visual Studio Code の構成設定</span><span class="sxs-lookup"><span data-stu-id="d36ee-171">Configuration settings for Visual Studio Code</span></span>

<span data-ttu-id="d36ee-172">まず、Visual Studio Code の設定を変更する方法に慣れていない場合は、[Visual Studio Code の設定に関するドキュメント][vsc-settings]を読むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d36ee-172">First, if you're not familiar with how to change settings in Visual Studio Code, we recommend reading [Visual Studio Code's settings][vsc-settings] documentation.</span></span>

<span data-ttu-id="d36ee-173">ドキュメントを読み終えたら、`settings.json` で構成設定を追加できます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-173">After reading the documentation, you can add configuration settings in `settings.json`.</span></span>

```json
{
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "files.trimTrailingWhitespace": true,
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="d36ee-174">これらの設定がすべてのファイルの種類に影響しないようにする場合、Visual Studio Code では言語ごとに構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-174">If you don't want these settings to affect all files types, Visual Studio Code also allows per-language configurations.</span></span> <span data-ttu-id="d36ee-175">`[<language-name>]` フィールドに設定を指定して、言語固有の設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-175">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="d36ee-176">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-176">For example:</span></span>

```json
{
    "[powershell]": {
        "files.encoding": "utf8bom",
        "files.autoGuessEncoding": true
    }
}
```

> [!TIP]
> <span data-ttu-id="d36ee-177">Visual Studio Code でのファイル エンコードについて詳しくは、[ファイル エンコードの概要][file-encoding]に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d36ee-177">For more information about file encoding in Visual Studio Code, see [Understanding file encoding][file-encoding].</span></span>
>
> <span data-ttu-id="d36ee-178">また、PowerShell 編集用に Visual Studio Code を構成する方法に関するその他のヒントについては、「[Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法][vsc-ise]」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d36ee-178">Also, check out [How to replicate the ISE experience in Visual Studio Code][vsc-ise] for other tips on how to configure Visual Studio Code for PowerShell editing.</span></span>

### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a><span data-ttu-id="d36ee-179">セッション メニューへの独自の PowerShell のパスの追加</span><span class="sxs-lookup"><span data-stu-id="d36ee-179">Adding your own PowerShell paths to the session menu</span></span>

<span data-ttu-id="d36ee-180">[Visual Studio Code 設定](https://code.visualstudio.com/docs/getstarted/settings): `powershell.powerShellAdditionalExePaths` を使用して、セッション メニューに他の PowerShell の実行パスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-180">You can add other PowerShell executable paths to the session menu through the [Visual Studio Code setting](https://code.visualstudio.com/docs/getstarted/settings): `powershell.powerShellAdditionalExePaths`.</span></span>

<span data-ttu-id="d36ee-181">次のように `powershell.powerShellAdditionalExePaths` のリストに項目を追加するか、`settings.json` にない場合はリストを作成します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-181">Add an item to the list `powershell.powerShellAdditionalExePaths` or create the list if it doesn't exist in your `settings.json`:</span></span>

```json
{
    // other settings...

    "powershell.powerShellAdditionalExePaths": [
        {
            "exePath": "C:\\Users\\tyler\\Downloads\\PowerShell\\pwsh.exe",
            "versionName": "Downloaded PowerShell"
        }
    ],

    // other settings...
}
```

<span data-ttu-id="d36ee-182">各項目には次が必要です。</span><span class="sxs-lookup"><span data-stu-id="d36ee-182">Each item must have:</span></span>

- <span data-ttu-id="d36ee-183">`exePath`:`pwsh` または `powershell` 実行可能ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="d36ee-183">`exePath`: The path to the `pwsh` or `powershell` executable.</span></span>
- <span data-ttu-id="d36ee-184">`versionName`:セッション メニューに表示されるテキスト。</span><span class="sxs-lookup"><span data-stu-id="d36ee-184">`versionName`: The text that will show up in the session menu.</span></span>

<span data-ttu-id="d36ee-185">PowerShell の既定のバージョンを設定するには、セッション メニューに表示されるテキストに値 `powershell.powerShellDefaultVersion` を設定します (`versionName` とも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="d36ee-185">To set the default PowerShell version, set the value `powershell.powerShellDefaultVersion` to the text displayed in the session menu (also known as the `versionName`):</span></span>

```json
{
    // other settings...

    "powershell.powerShellAdditionalExePaths": [
        {
            "exePath": "C:\\Users\\tyler\\Downloads\\PowerShell\\pwsh.exe",
            "versionName": "Downloaded PowerShell"
        }
    ],

    "powershell.powerShellDefaultVersion": "Downloaded PowerShell",

    // other settings...
}
```

<span data-ttu-id="d36ee-186">この設定を構成したら、Visual Studio Code を再起動します。または、**コマンド パレット**から現在の Visual Studio Code ウィンドウを再度読み込むには、「**Developer: Reload Window**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-186">After you've configured this setting, restart Visual Studio Code or to reload the current Visual Studio Code window from the **Command Palette**, type **Developer: Reload Window**.</span></span>

<span data-ttu-id="d36ee-187">これでセッション メニューを開くと、追加した PowerShell バージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-187">If you open the session menu, you now see your additional PowerShell versions!</span></span>

> [!NOTE]
> <span data-ttu-id="d36ee-188">これは、ソースから PowerShell をビルドした場合、PowerShell のローカル ビルドをテストする優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="d36ee-188">If you build PowerShell from source, this is a great way to test out your local build of PowerShell.</span></span>

### <a name="using-an-older-version-of-the-powershell-extension-for-windows-powershell-v3-and-v4"></a><span data-ttu-id="d36ee-189">Windows PowerShell v3 および v4 用の古いバージョンの PowerShell 拡張機能を使用する</span><span class="sxs-lookup"><span data-stu-id="d36ee-189">Using an older version of the PowerShell Extension for Windows PowerShell v3 and v4</span></span>

<span data-ttu-id="d36ee-190">現在の PowerShell 拡張機能では [PowerShell v3 と v4][i1310] はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d36ee-190">The current PowerShell extension doesn't support [PowerShell v3 and v4][i1310].</span></span> <span data-ttu-id="d36ee-191">ただし、PowerShell v3 と v4 をサポートする最新バージョンの拡張機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-191">However, you can use the last version of the extension that supports PowerShell v3 and v4.</span></span>

> [!CAUTION]
> <span data-ttu-id="d36ee-192">この古いバージョンの拡張機能に修正プログラムが追加されることはありません。</span><span class="sxs-lookup"><span data-stu-id="d36ee-192">There will be no additional fixes to this older version of the extension.</span></span> <span data-ttu-id="d36ee-193">これは "そのままの状態で" 提供されますが、Windows PowerShell v3 と Windows PowerShell v4 を引き続き使用している場合に利用できます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-193">It's provided "AS IS" but is available for you if you are still using Windows PowerShell v3 and Windows PowerShell v4.</span></span>

<span data-ttu-id="d36ee-194">まず、[拡張機能] ペインを開いて「`PowerShell`」を検索します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-194">First, open the Extension pane and search for `PowerShell`.</span></span> <span data-ttu-id="d36ee-195">次に、歯車をクリックして、 **[Install another version...]\(別のバージョンをインストール...\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-195">Then click the gear and select **Install another version...**.</span></span>

![メニュー項目 - 別のバージョンをインストール...](media/using-vscode/install-another-version.png)

<span data-ttu-id="d36ee-197">次に、バージョン **2020.1.0** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-197">Then select the **2020.1.0** version.</span></span> <span data-ttu-id="d36ee-198">このバージョンの拡張機能は、v3 と v4 がサポートされている最後のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="d36ee-198">This version of the extension was the last version to support v3 and v4.</span></span> <span data-ttu-id="d36ee-199">拡張機能のバージョンが自動的に更新されないように、必ず次の設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-199">Be sure to add the following setting so that your extension version doesn't update automatically:</span></span>

```json
{
    "extensions.autoUpdate": false
}
```

<span data-ttu-id="d36ee-200">バージョン **2020.1.0** は、近い将来有効になります。</span><span class="sxs-lookup"><span data-stu-id="d36ee-200">Version **2020.1.0** will work for the foreseeable future.</span></span> <span data-ttu-id="d36ee-201">ただし、このバージョンの拡張機能が動作しなくなるような変更が Visual Studio Code で実装される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d36ee-201">However, Visual Studio Code could implement a change that breaks this version of the extension.</span></span> <span data-ttu-id="d36ee-202">このことと、サポートがないことから、次のいずれかを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d36ee-202">Because of this, and lack of support, we recommend:</span></span>

- <span data-ttu-id="d36ee-203">Windows PowerShell 5.1 にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="d36ee-203">Upgrading to Windows PowerShell 5.1</span></span>
- <span data-ttu-id="d36ee-204">PowerShell 7 をインストールする。これは Windows PowerShell とのサイド バイ サイド インストールであり、PowerShell 拡張機能と最適に連携します</span><span class="sxs-lookup"><span data-stu-id="d36ee-204">Install PowerShell 7, which is a side-by-side install to Windows PowerShell and works the best with the PowerShell extension</span></span>

## <a name="debugging-with-visual-studio-code"></a><span data-ttu-id="d36ee-205">Visual Studio Code を使用したデバッグ</span><span class="sxs-lookup"><span data-stu-id="d36ee-205">Debugging with Visual Studio Code</span></span>

### <a name="no-workspace-debugging"></a><span data-ttu-id="d36ee-206">ワークスペースを使用しないデバッグ</span><span class="sxs-lookup"><span data-stu-id="d36ee-206">No-workspace debugging</span></span>

<span data-ttu-id="d36ee-207">Visual Studio Code バージョン 1.9 (以降) では、PowerShell スクリプトを含むフォルダーを開かずに PowerShell スクリプトをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-207">In Visual Studio Code version 1.9 (or higher), you can debug PowerShell scripts without opening the folder that contains the PowerShell script.</span></span>

1. <span data-ttu-id="d36ee-208">**[ファイル] > [ファイルを開く]** の順に選択して、PowerShell スクリプト ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-208">Open the PowerShell script file with **File > Open File...**</span></span>
1. <span data-ttu-id="d36ee-209">ブレークポイントの設定 - 行を選択して、<kbd>F9</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-209">Set a breakpoint - select a line then press <kbd>F9</kbd></span></span>
1. <span data-ttu-id="d36ee-210"><kbd>F5</kbd> キーを押してデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-210">Press <kbd>F5</kbd> to start debugging</span></span>

<span data-ttu-id="d36ee-211">[Debug actions]\(デバッグ アクション\) ウィンドウが表示されます。ここでは、デバッガーを中断したり、デバッグをステップ実行、再開、停止したりできます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-211">You should see the Debug actions pane appear which allows you to break into the debugger, step, resume, and stop debugging.</span></span>

### <a name="workspace-debugging"></a><span data-ttu-id="d36ee-212">ワークスペースを使用したデバッグ</span><span class="sxs-lookup"><span data-stu-id="d36ee-212">Workspace debugging</span></span>

<span data-ttu-id="d36ee-213">ワークスペースを使用したデバッグとは、 **[ファイル]** メニューの **[フォルダーを開く]** を使用して開いたフォルダーのコンテキストでデバッグを行うことを言います。開いたフォルダーは、通常は PowerShell プロジェクトのフォルダーまたは Git リポジトリのルートです。</span><span class="sxs-lookup"><span data-stu-id="d36ee-213">Workspace debugging refers to debugging in the context of a folder that you've opened from the **File** menu using **Open Folder...**. The folder you open is typically your PowerShell project folder or the root of your Git repository.</span></span> <span data-ttu-id="d36ee-214">ワークスペースを使用したデバッグでは、現在開いているファイルをデバッグする以外に、複数のデバッグ構成を定義できます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-214">Workspace debugging allows you to define multiple debug configurations other than just debugging the currently open file.</span></span>

<span data-ttu-id="d36ee-215">デバッグ用の構成ファイルを作成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d36ee-215">Follow these steps to create a debug configuration file:</span></span>

1. <span data-ttu-id="d36ee-216">Windows または Linux の場合、<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> を押し、 **[デバッグ]** ビューを開きます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-216">Open the **Debug** view on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span> <span data-ttu-id="d36ee-217">macOS の場合、<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> を押します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-217">On macOS, press <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span>
1. <span data-ttu-id="d36ee-218">**launch.json ファイルの作成**リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d36ee-218">Click the **create a launch.json file** link.</span></span>
1. <span data-ttu-id="d36ee-219">**[環境を選択]** プロンプトで、 **[PowerShell]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-219">From the **Select Environment** prompt, choose **PowerShell**.</span></span>
1. <span data-ttu-id="d36ee-220">使用するデバッグの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-220">Choose the type of debugging you'd like to use:</span></span>

   - <span data-ttu-id="d36ee-221">**現在のファイルを起動** - 現在アクティブなエディター ウィンドウのファイルを起動してデバッグします</span><span class="sxs-lookup"><span data-stu-id="d36ee-221">**Launch Current File** - Launch and debug the file in the currently active editor window</span></span>
   - <span data-ttu-id="d36ee-222">**スクリプトを起動** - 指定したファイルまたはコマンドを起動してデバッグします</span><span class="sxs-lookup"><span data-stu-id="d36ee-222">**Launch Script** - Launch and debug the specified file or command</span></span>
   - <span data-ttu-id="d36ee-223">**対話型セッション** - 統合コンソールから実行されたコマンドをデバッグします</span><span class="sxs-lookup"><span data-stu-id="d36ee-223">**Interactive Session** - Debug commands executed from the Integrated Console</span></span>
   - <span data-ttu-id="d36ee-224">**アタッチ** - 実行中の PowerShell ホスト プロセスにデバッガーをアタッチします</span><span class="sxs-lookup"><span data-stu-id="d36ee-224">**Attach** - Attach the debugger to a running PowerShell Host Process</span></span>

<span data-ttu-id="d36ee-225">デバッグ構成を格納する自分のワークスペース フォルダーのルートにディレクトリとファイル `.vscode\launch.json` が Visual Studio Code によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-225">Visual Studio Code creates a directory and a file `.vscode\launch.json` in the root of your workspace folder to store the debug configuration.</span></span> <span data-ttu-id="d36ee-226">ファイルが Git リポジトリにある場合は、通常、`launch.json` ファイルをコミットすることになるでしょう。</span><span class="sxs-lookup"><span data-stu-id="d36ee-226">If your files are in a Git repository, you typically want to commit the `launch.json` file.</span></span> <span data-ttu-id="d36ee-227">`launch.json` ファイルの内容:</span><span class="sxs-lookup"><span data-stu-id="d36ee-227">The contents of the `launch.json` file are:</span></span>

```json
{
  "version": "0.2.0",
  "configurations": [
      {
          "type": "PowerShell",
          "request": "launch",
          "name": "PowerShell Launch (current file)",
          "script": "${file}",
          "args": [],
          "cwd": "${file}"
      },
      {
          "type": "PowerShell",
          "request": "attach",
          "name": "PowerShell Attach to Host Process",
          "processId": "${command.PickPSHostProcess}",
          "runspaceId": 1
      },
      {
          "type": "PowerShell",
          "request": "launch",
          "name": "PowerShell Interactive Session",
          "cwd": "${workspaceRoot}"
      }
  ]
}
```

<span data-ttu-id="d36ee-228">このファイルは一般的なデバッグ シナリオです。</span><span class="sxs-lookup"><span data-stu-id="d36ee-228">This file represents the common debug scenarios.</span></span> <span data-ttu-id="d36ee-229">エディターでこのファイルを開いた場合、 **[構成の追加]** ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-229">When you open this file in the editor, you see an **Add Configuration...** button.</span></span> <span data-ttu-id="d36ee-230">このボタンをクリックすることで、PowerShell デバッグ構成をさらに追加できます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-230">You can click this button to add more PowerShell debug configurations.</span></span> <span data-ttu-id="d36ee-231">追加すると便利な構成の 1 つは、 **[PowerShell: Launch Script]\(PowerShell: 起動スクリプト\)** です。</span><span class="sxs-lookup"><span data-stu-id="d36ee-231">One useful configuration to add is **PowerShell: Launch Script**.</span></span> <span data-ttu-id="d36ee-232">この構成では、エディターでどのファイルがアクティブであるかに関係なく、<kbd>F5</kbd> キーを押すたびに使用される省略可能な引数を含むファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-232">With this configuration, you can specify a file containing optional arguments that are used whenever you press <kbd>F5</kbd> no matter which file is active in the editor.</span></span>

<span data-ttu-id="d36ee-233">デバッグ構成が確立されたら、デバッグ セッション中に使用する構成を選択できます。</span><span class="sxs-lookup"><span data-stu-id="d36ee-233">After the debug configuration is established, you can select which configuration you want to use during a debug session.</span></span> <span data-ttu-id="d36ee-234">**[デバッグ]** ビューのツール バーでデバッグ構成ドロップダウンから構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-234">Select a configuration from the debug configuration drop-down in the **Debug** view's toolbar.</span></span>

## <a name="troubleshooting-the-powershell-extension-for-visual-studio-code"></a><span data-ttu-id="d36ee-235">Visual Studio Code 用 PowerShell 拡張機能のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d36ee-235">Troubleshooting the PowerShell extension for Visual Studio Code</span></span>

<span data-ttu-id="d36ee-236">PowerShell スクリプト開発のための Visual Studio Code の使用に関して問題が発生した場合は、GitHub 上の[トラブルシューティング ガイド][troubleshooting]を参照してください</span><span class="sxs-lookup"><span data-stu-id="d36ee-236">If you experience any issues using Visual Studio Code for PowerShell script development, see the [troubleshooting guide][troubleshooting] on GitHub.</span></span>

## <a name="useful-resources"></a><span data-ttu-id="d36ee-237">有用なリソース</span><span class="sxs-lookup"><span data-stu-id="d36ee-237">Useful resources</span></span>

<span data-ttu-id="d36ee-238">Visual Studio Code 用の PowerShell 拡張機能の使用を開始するのに役立つビデオとブログ記事を、次にいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="d36ee-238">There are a few videos and blog posts that may be helpful to get you started using the PowerShell extension for Visual Studio Code:</span></span>

### <a name="videos"></a><span data-ttu-id="d36ee-239">ビデオ</span><span class="sxs-lookup"><span data-stu-id="d36ee-239">Videos</span></span>

- [<span data-ttu-id="d36ee-240">既定の PowerShell エディターとして Visual Studio Code を使用する</span><span class="sxs-lookup"><span data-stu-id="d36ee-240">Using Visual Studio Code as Your Default PowerShell Editor</span></span>](https://youtu.be/bGn45vIeAMM)
- [<span data-ttu-id="d36ee-241">Visual Studio Code: PowerShell スクリプトのデバッグの詳細</span><span class="sxs-lookup"><span data-stu-id="d36ee-241">Visual Studio Code: deep dive into debugging your PowerShell scripts</span></span>](https://youtu.be/cSbIXmlkr8o)

### <a name="blog-posts"></a><span data-ttu-id="d36ee-242">ブログ記事</span><span class="sxs-lookup"><span data-stu-id="d36ee-242">Blog posts</span></span>

- <span data-ttu-id="d36ee-243">[PowerShell の拡張機能][pscdn]</span><span class="sxs-lookup"><span data-stu-id="d36ee-243">[PowerShell Extension][pscdn]</span></span>
- <span data-ttu-id="d36ee-244">[Visual Studio Code での PowerShell スクリプトの記述およびデバッグ][debug]</span><span class="sxs-lookup"><span data-stu-id="d36ee-244">[Write and debug PowerShell scripts in Visual Studio Code][debug]</span></span>
- <span data-ttu-id="d36ee-245">[Visual Studio Code でのデバッグのガイダンス][psdbgblog]</span><span class="sxs-lookup"><span data-stu-id="d36ee-245">[Debugging Visual Studio Code Guidance][psdbgblog]</span></span>
- <span data-ttu-id="d36ee-246">[Visual Studio Code での PowerShell のデバッグ][psdbg-gh]</span><span class="sxs-lookup"><span data-stu-id="d36ee-246">[Debugging PowerShell in Visual Studio Code][psdbg-gh]</span></span>
- <span data-ttu-id="d36ee-247">[Visual Studio Code での PowerShell 開発の概要][getting-started]</span><span class="sxs-lookup"><span data-stu-id="d36ee-247">[Get started with PowerShell development in Visual Studio Code][getting-started]</span></span>
- <span data-ttu-id="d36ee-248">[PowerShell 開発のための Visual Studio Code の編集機能 – パート 1][editing-part1]</span><span class="sxs-lookup"><span data-stu-id="d36ee-248">[Visual Studio Code editing features for PowerShell development – Part 1][editing-part1]</span></span>
- <span data-ttu-id="d36ee-249">[PowerShell 開発のための Visual Studio Code の編集機能 – パート 2][editing-part2]</span><span class="sxs-lookup"><span data-stu-id="d36ee-249">[Visual Studio Code editing features for PowerShell development – Part 2][editing-part2]</span></span>
- <span data-ttu-id="d36ee-250">[Visual Studio Code での PowerShell スクリプトのデバッグ – パート 1][debugging-part1]</span><span class="sxs-lookup"><span data-stu-id="d36ee-250">[Debugging PowerShell script in Visual Studio Code – Part 1][debugging-part1]</span></span>
- <span data-ttu-id="d36ee-251">[Visual Studio Code での PowerShell スクリプトのデバッグ – パート 2][debugging-part2]</span><span class="sxs-lookup"><span data-stu-id="d36ee-251">[Debugging PowerShell script in Visual Studio Code – Part 2][debugging-part2]</span></span>

## <a name="powershell-extension-project-source-code"></a><span data-ttu-id="d36ee-252">PowerShell 拡張機能プロジェクトのソース コード</span><span class="sxs-lookup"><span data-stu-id="d36ee-252">PowerShell extension project source code</span></span>

<span data-ttu-id="d36ee-253">PowerShell の拡張機能のソース コードは、[GitHub][psext-src] にあります。</span><span class="sxs-lookup"><span data-stu-id="d36ee-253">The PowerShell extension's source code can be found on [GitHub][psext-src].</span></span>

<span data-ttu-id="d36ee-254">共同作成に関心がある場合は、ぜひ pull request をご活用ください。</span><span class="sxs-lookup"><span data-stu-id="d36ee-254">If you're interested in contributing, Pull Requests are greatly appreciated.</span></span> <span data-ttu-id="d36ee-255">[GitHub 上の開発者向けドキュメント][dev-docs]を参照して、作業を開始してください。</span><span class="sxs-lookup"><span data-stu-id="d36ee-255">Follow along with the [developer documentation][dev-docs] on GitHub to get started.</span></span>

<!-- related articles -->
[ise]:                    ../../windows-powershell/ise/Introducing-the-Windows-PowerShell-ISE.md
[install-pscore-linux]:   ../../install/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:   ../../install/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../install/Installing-PowerShell-Core-on-Windows.md
[install-winps]:          ../../install/Installing-Windows-PowerShell.md
[file-encoding]:          understanding-file-encoding.md
[vsc-ise]:                How-To-Replicate-the-ISE-Experience-In-VSCode.md

<!-- blogs -->
[debug]:                  https://devblogs.microsoft.com/powershell/announcing-powershell-language-support-for-visual-studio-code-and-more/
[debugging-part1]:        https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]:        https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-2/
[editing-part1]:          https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]:          https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-2/
[getting-started]:        https://devblogs.microsoft.com/scripting/get-started-with-powershell-development-in-visual-studio-code/
[psdbgblog]:              https://johnpapa.net/debugging-with-visual-studio-code/
[psdbg-gh]:               https://github.com/PowerShell/vscode-powershell/tree/master/examples
[pscdn]:                  https://blogs.msdn.microsoft.com/cdndevs/2015/12/11/visual-studio-code-powershell-extension/

<!-- issues -->
[GitHub の問題]:          https://github.com/PowerShell/vscode-powershell/issues
[GitHub issues]:          https://github.com/PowerShell/vscode-powershell/issues
[i1310]:                  https://github.com/PowerShell/vscode-powershell/issues/1310
[i606]:                   https://github.com/PowerShell/vscode-powershell/issues/606

<!-- product links -->
[Visual Studio]:          https://visualstudio.microsoft.com/
[vscode]:                 https://code.visualstudio.com/
[psext]:                  https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell
[vsc-settings]:           https://code.visualstudio.com/docs/getstarted/settings
[vsc-setup]:              https://code.visualstudio.com/Docs/setup/setup-overview
[vsc-setup-win]:          https://code.visualstudio.com/docs/setup/windows
[vsc-setup-macos]:        https://code.visualstudio.com/docs/setup/mac
[vsc-setup-linux]:        https://code.visualstudio.com/docs/setup/linux
[psext-src]:              https://github.com/PowerShell/vscode-powershell
[troubleshooting]:        https://github.com/PowerShell/vscode-powershell/blob/master/docs/troubleshooting.md
[dev-docs]:               https://github.com/PowerShell/vscode-powershell/blob/master/docs/development.md
