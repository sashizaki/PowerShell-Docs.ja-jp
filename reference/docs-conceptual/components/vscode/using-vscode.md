---
title: PowerShell 開発のための Visual Studio Code の使用
description: PowerShell 開発のための Visual Studio Code の使用
ms.date: 11/07/2019
ms.openlocfilehash: 16ae228c0d169261b783366a730fd2d5d77d32d6
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78279072"
---
# <a name="using-visual-studio-code-for-powershell-development"></a><span data-ttu-id="f9ec8-103">PowerShell 開発のための Visual Studio Code の使用</span><span class="sxs-lookup"><span data-stu-id="f9ec8-103">Using Visual Studio Code for PowerShell Development</span></span>

<span data-ttu-id="f9ec8-104">[PowerShell ISE][ise] だけでなく、PowerShell も Visual Studio Code (VSCode) で問題なくサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-104">In addition to the [PowerShell ISE][ise], PowerShell is also well-supported in Visual Studio Code (VSCode).</span></span> <span data-ttu-id="f9ec8-105">PowerShell Core では ISE はサポートされていませんが、VSCode はすべてのプラットフォーム (Windows、macOS、Linux) の PowerShell Core でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-105">The ISE isn't supported with PowerShell Core, but VSCode is supported for PowerShell Core on all platforms: Windows, macOS, and Linux.</span></span>

<span data-ttu-id="f9ec8-106">PowerShell バージョンが 5 の Windows で VSCode を使用する場合、Windows 10 を使用するか、ダウンレベルの Windows OS (Windows 8.1 など) 向けの Windows Management Framework 5.1 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-106">You can use VSCode on Windows with PowerShell version 5 by using Windows 10 or by installing Windows Management Framework 5.1 for down-level Windows OSs such as Windows 8.1.</span></span> <span data-ttu-id="f9ec8-107">詳細については、「[WMF 5.1 のインストールと構成](/powershell/scripting/wmf/setup/install-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-107">For more information, see [Install and Configure WMF 5.1](/powershell/scripting/wmf/setup/install-configure).</span></span>

<span data-ttu-id="f9ec8-108">開始する前に、システムに PowerShell があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-108">Before you begin, make sure PowerShell exists on your system.</span></span> <span data-ttu-id="f9ec8-109">Windows、macOS、Linux 上の最近のワークロードに対しては、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-109">For modern workloads on Windows, macOS, and Linux, see the following links:</span></span>

- <span data-ttu-id="f9ec8-110">[Linux に PowerShell Core をインストールする][install-pscore-linux]</span><span class="sxs-lookup"><span data-stu-id="f9ec8-110">[Installing PowerShell Core on Linux][install-pscore-linux]</span></span>
- <span data-ttu-id="f9ec8-111">[macOS に PowerShell Core をインストールする][install-pscore-macos]</span><span class="sxs-lookup"><span data-stu-id="f9ec8-111">[Installing PowerShell Core on macOS][install-pscore-macos]</span></span>
- <span data-ttu-id="f9ec8-112">[Windows に PowerShell Core をインストールする][install-pscore-windows]</span><span class="sxs-lookup"><span data-stu-id="f9ec8-112">[Installing PowerShell Core on Windows][install-pscore-windows]</span></span>

<span data-ttu-id="f9ec8-113">従来の Windows PowerShell ワークロードについては、「[Windows PowerShell のインストール][install-winps]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-113">For traditional Windows PowerShell workloads, see [Installing Windows PowerShell][install-winps].</span></span>

## <a name="editing-with-vscode"></a><span data-ttu-id="f9ec8-114">VSCode による編集</span><span class="sxs-lookup"><span data-stu-id="f9ec8-114">Editing with VSCode</span></span>

1. <span data-ttu-id="f9ec8-115">VSCode をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-115">Install VSCode.</span></span> <span data-ttu-id="f9ec8-116">詳細については、「[Visual Studio Code の設定](https://code.visualstudio.com/Docs/setup/setup-overview)」という概要ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-116">For more information, see the overview [Setting up Visual Studio Code](https://code.visualstudio.com/Docs/setup/setup-overview).</span></span>

   <span data-ttu-id="f9ec8-117">プラットフォーム別のインストール手順があります。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-117">There are installation instructions for each platform:</span></span>

   - <span data-ttu-id="f9ec8-118">**Linux**: [Linux 上で VS コードを実行する](https://code.visualstudio.com/docs/setup/linux)方法に関するページのインストール手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-118">**Linux**: follow the installation instructions on the [Running VSCode on Linux](https://code.visualstudio.com/docs/setup/linux) page.</span></span>
   - <span data-ttu-id="f9ec8-119">**macOS**: [macOS 上で VS コードを実行する](https://code.visualstudio.com/docs/setup/mac)方法に関するページのインストール手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-119">**macOS**: follow the installation instructions on the [Running VSCode on macOS](https://code.visualstudio.com/docs/setup/mac) page.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="f9ec8-120">macOS で、PowerShell の拡張機能用が正常に動作するには、OpenSSL をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-120">On macOS, you must install OpenSSL for the PowerShell extension to work correctly.</span></span> <span data-ttu-id="f9ec8-121">これには、[Homebrew](https://brew.sh/) をインストールして、`brew install openssl` を実行するのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-121">The easiest way to accomplish this is to install [Homebrew](https://brew.sh/) and then run `brew install openssl`.</span></span> <span data-ttu-id="f9ec8-122">これで、VSCode を使用して PowerShell 拡張機能を正常に読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-122">VSCode can now load the PowerShell extension successfully.</span></span>

   - <span data-ttu-id="f9ec8-123">**Windows**: [Windows 上で VS コードを実行する](https://code.visualstudio.com/docs/setup/windows)方法に関するページのインストール手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-123">**Windows**: follow the installation instructions on the [Running VSCode on Windows](https://code.visualstudio.com/docs/setup/windows) page.</span></span>

1. <span data-ttu-id="f9ec8-124">PowerShell 拡張機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-124">Install the PowerShell Extension.</span></span>

   1. <span data-ttu-id="f9ec8-125">次の方法で VSCode アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-125">Launch the VSCode app by:</span></span>
      - <span data-ttu-id="f9ec8-126">**Windows**: PowerShell セッションで `code` と入力します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-126">**Windows**: typing `code` in your PowerShell session</span></span>
      - <span data-ttu-id="f9ec8-127">**Linux**: ターミナルで `code` と入力します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-127">**Linux**: typing `code` in your terminal</span></span>
      - <span data-ttu-id="f9ec8-128">**macOS**: ターミナルで `code` と入力します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-128">**macOS**: typing `code` in your terminal</span></span>
   1. <span data-ttu-id="f9ec8-129">Windows または Linux の場合、<kbd>Ctrl</kbd>+<kbd>P</kbd> を押し、**Quick Open** を起動します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-129">Launch **Quick Open** on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="f9ec8-130">macOS の場合、<kbd>Cmd</kbd>+<kbd>P</kbd> を押します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-130">On macOS, press <kbd>Cmd</kbd>+<kbd>P</kbd>.</span></span>
   1. <span data-ttu-id="f9ec8-131">Quick Open を開き、「`ext install powershell`」と入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-131">In Quick Open, type `ext install powershell` and press **Enter**.</span></span>
   1. <span data-ttu-id="f9ec8-132">サイド バーに **[拡張機能]** ビューが開きます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-132">The **Extensions** view opens on the Side Bar.</span></span> <span data-ttu-id="f9ec8-133">Microsoft の PowerShell の拡張機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-133">Select the PowerShell extension from Microsoft.</span></span>
      <span data-ttu-id="f9ec8-134">次の画像のような VSCode 画面が表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-134">You should see a VSCode screen similar to the following image:</span></span>

      ![VS Code](media/using-vscode/vscode.png)

   1. <span data-ttu-id="f9ec8-136">Microsoft の PowerShell 拡張機能の、 **[インストール]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-136">Click the **Install** button on the PowerShell extension from Microsoft.</span></span>
   1. <span data-ttu-id="f9ec8-137">インストール後、 **[インストール]** ボタンは **[再読み込み]** に変わります。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-137">After the install, you see the **Install** button turns to **Reload**.</span></span> <span data-ttu-id="f9ec8-138">**[再読み込み]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-138">Click on **Reload**.</span></span>
   1. <span data-ttu-id="f9ec8-139">VSCode が再読み込みされたら、編集が可能になります。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-139">After VSCode has reloaded, you're ready for editing.</span></span>

<span data-ttu-id="f9ec8-140">たとえば、新しいファイルを作成するには、 **[ファイル]、[新規]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-140">For example, to create a new file, click **File > New**.</span></span> <span data-ttu-id="f9ec8-141">保存するには、 **[ファイル]、[保存]** の順にクリックし、`HelloWorld.ps1` のようなファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-141">To save it, click **File > Save** and then provide a file name, such as `HelloWorld.ps1`.</span></span> <span data-ttu-id="f9ec8-142">ファイルを閉じるには、ファイル名の横の `X` をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-142">To close the file, click the `X` next to the file name.</span></span> <span data-ttu-id="f9ec8-143">VSCode を終了するには、 **[ファイル]、[終了]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-143">To exit VSCode, **File > Exit**.</span></span>

### <a name="installing-the-powershell-extension-on-restricted-systems"></a><span data-ttu-id="f9ec8-144">制限されているシステムへの PowerShell 拡張機能のインストール</span><span class="sxs-lookup"><span data-stu-id="f9ec8-144">Installing the PowerShell Extension on Restricted Systems</span></span>

<span data-ttu-id="f9ec8-145">一部のシステムはすべてのコード署名をチェックする必要があるように設定されているため、PowerShell エディター サービスをシステムで実行することを手動で承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-145">Some systems are set up in a way that requires all code signatures to be checked and requires PowerShell Editor Services to be manually approved to run on the system.</span></span> <span data-ttu-id="f9ec8-146">PowerShell 拡張機能をインストールしたが次のようなエラーが表示される場合、考えられる原因は実行ポリシーを変更するグループ ポリシーの更新です。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-146">A Group Policy update that changes execution policy is a likely cause if you've installed the PowerShell extension but are receiving an error such as:</span></span>

```
Language server startup failed.
```

<span data-ttu-id="f9ec8-147">PowerShell エディター サービスおよび VSCode 用 PowerShell 拡張機能を手動で承認するには、PowerShell プロンプトを開いて次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-147">To manually approve PowerShell Editor Services and the PowerShell extension for VSCode, open a PowerShell prompt and run the following command:</span></span>

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

<span data-ttu-id="f9ec8-148">"**この信頼されていない発行元からのソフトウェアを実行しますか?** " というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-148">You're prompted with **Do you want to run software from this untrusted publisher?**</span></span> <span data-ttu-id="f9ec8-149">`A` キーを押してファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-149">Type `A` to run the file.</span></span> <span data-ttu-id="f9ec8-150">次に、VSCode を開き、PowerShell 拡張機能が正しく機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-150">Then, open VSCode and check that the PowerShell extension is functioning properly.</span></span> <span data-ttu-id="f9ec8-151">まだ問題がある場合は、[GitHub](https://github.com/PowerShell/vscode-powershell/issues) で問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-151">If you still have issues getting started, let us know on [GitHub](https://github.com/PowerShell/vscode-powershell/issues).</span></span>

### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a><span data-ttu-id="f9ec8-152">拡張機能で使用する PowerShell のバージョンを選択</span><span class="sxs-lookup"><span data-stu-id="f9ec8-152">Choosing a version of PowerShell to use with the extension</span></span>

<span data-ttu-id="f9ec8-153">Windows PowerShell と PowerShell Core がインストールされている場合、PowerShell の特定のバージョンを PowerShell の拡張機能で使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-153">With PowerShell Core installing side-by-side with Windows PowerShell, it's now possible to use a particular version of PowerShell with the PowerShell extension.</span></span> <span data-ttu-id="f9ec8-154">バージョンは次の手順で選択します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-154">Use the following steps to choose the version:</span></span>

1. <span data-ttu-id="f9ec8-155">Windows または Linux の場合、<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> を使用して**コマンド パレット**を開きます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-155">Open the **Command Palette** on Windows or Linux with <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="f9ec8-156">macOS の場合、<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> を使用します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-156">On macOS, use <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span>
1. <span data-ttu-id="f9ec8-157">"**セッション**" を検索します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-157">Search for **Session**.</span></span>
1. <span data-ttu-id="f9ec8-158">**[PowerShell: Show Session Menu]\(PowerShell: セッション メニューを表示\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-158">Click on **PowerShell: Show Session Menu**.</span></span>
1. <span data-ttu-id="f9ec8-159">一覧から、"**PowerShell Core**" など、使用する PowerShell のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-159">Choose the version of PowerShell you want to use from the list, for example: **PowerShell Core**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9ec8-160">この機能では、異なるオペレーティング システム上のいくつかのよく知られているパスを検索し、PowerShell のインストール場所を検出します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-160">This feature looks at a few well-known paths on different operating systems to discover install locations of PowerShell.</span></span> <span data-ttu-id="f9ec8-161">PowerShell を一般的ではない場所にインストールしている場合、最初にそれがセッション メニューに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-161">If you installed PowerShell to a non-typical location, it might not show up initially in the Session Menu.</span></span> <span data-ttu-id="f9ec8-162">次のように、[独自のカスタム パスを追加して](#adding-your-own-powershell-paths-to-the-session-menu)、セッション メニューを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-162">You can extend the session menu by [adding your own custom paths](#adding-your-own-powershell-paths-to-the-session-menu) as described below.</span></span>

>[!NOTE]
> <span data-ttu-id="f9ec8-163">次のようにセッション メニューに進むこともできます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-163">There's another way to get to the session menu.</span></span> <span data-ttu-id="f9ec8-164">エディターで PowerShell ファイルを開いているときに、右下に緑のバージョン番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-164">When a PowerShell file is open in your editor, you see a green version number in the bottom right.</span></span> <span data-ttu-id="f9ec8-165">このバージョン番号をクリックすると、セッション メニューに移動できます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-165">Clicking this version number will bring you to the session menu.</span></span>

### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a><span data-ttu-id="f9ec8-166">セッション メニューへの独自の PowerShell のパスの追加</span><span class="sxs-lookup"><span data-stu-id="f9ec8-166">Adding your own PowerShell paths to the session menu</span></span>

<span data-ttu-id="f9ec8-167">VSCode 設定を利用し、セッション メニューに他の PowerShell の実行可能パスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-167">You can add other PowerShell executable paths to the session menu through a VSCode setting.</span></span>

<span data-ttu-id="f9ec8-168">次のように `powershell.powerShellAdditionalExePaths` のリストに項目を追加するか、`settings.json` にない場合はリストを作成します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-168">Add an item to the list `powershell.powerShellAdditionalExePaths` or create the list if it doesn't exist in your `settings.json`:</span></span>

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

<span data-ttu-id="f9ec8-169">各項目には次が必要です。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-169">Each item must have:</span></span>

* <span data-ttu-id="f9ec8-170">`exePath`:`pwsh` または `powershell` 実行可能ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-170">`exePath`: The path to the `pwsh` or `powershell` executable.</span></span>
* <span data-ttu-id="f9ec8-171">`versionName`:セッション メニューに表示されるテキスト。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-171">`versionName`: The text that will show up in the session menu.</span></span>

<span data-ttu-id="f9ec8-172">`powershell.powerShellDefaultVersion` の設定を使用して、これをセッション メニューに表示されるテキストに設定して、使用する既定の PowerShell のバージョンを設定できます (前の設定での `versionName`)。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-172">You can set the default PowerShell version to use the `powershell.powerShellDefaultVersion` setting by setting this to the text displayed in the session menu (also known as the `versionName` in the last setting):</span></span>

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

<span data-ttu-id="f9ec8-173">この設定を構成したら、VSCode を再起動します。あるいは**コマンド パレット**から現在の VSCode ウィンドウを再度読み込むには、「**Developer: Reload Window**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-173">After you've configured this setting, restart VSCode or to reload the current VSCode window from the **Command Palette**, type **Developer: Reload Window**.</span></span>

<span data-ttu-id="f9ec8-174">これでセッション メニューを開くと、追加した PowerShell バージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-174">If you open the session menu, you now see your additional PowerShell versions!</span></span>

> [!NOTE]
> <span data-ttu-id="f9ec8-175">これは、ソースから PowerShell をビルドした場合、PowerShell のローカル ビルドをテストする優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-175">If you build PowerShell from source, this is a great way to test out your local build of PowerShell.</span></span>

### <a name="configuration-settings-for-vscode"></a><span data-ttu-id="f9ec8-176">VSCode の構成設定</span><span class="sxs-lookup"><span data-stu-id="f9ec8-176">Configuration settings for VSCode</span></span>

<span data-ttu-id="f9ec8-177">前段の手順を使用して、`settings.json` に構成設定を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-177">By using the steps in the previous paragraph, you can add configuration settings in `settings.json`.</span></span>

<span data-ttu-id="f9ec8-178">VSCode には、次の構成設定をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-178">We recommend the following configuration settings for VSCode:</span></span>

```json
{
    "csharp.suppressDotnetRestoreNotification": true,
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "omnisharp.projectLoadTimeout": 120,
    "files.trimTrailingWhitespace": true,
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="f9ec8-179">これらの設定がすべてのファイルの種類に影響しないようにする場合、VSCode では言語ごとに構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-179">If you don't want these settings to affect all files types, VSCode also allows per-language configurations.</span></span> <span data-ttu-id="f9ec8-180">`[<language-name>]` フィールドに設定を指定して、言語固有の設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-180">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="f9ec8-181">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-181">For example:</span></span>

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="f9ec8-182">VSCode でのファイル エンコードについて詳しくは、[ファイルのエンコードの理解](understanding-file-encoding.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-182">For more information about file encoding in VSCode, see [Understanding file encoding](understanding-file-encoding.md).</span></span>

## <a name="debugging-with-vscode"></a><span data-ttu-id="f9ec8-183">VSCode によるデバッグ</span><span class="sxs-lookup"><span data-stu-id="f9ec8-183">Debugging with VSCode</span></span>

### <a name="no-workspace-debugging"></a><span data-ttu-id="f9ec8-184">ワークスペースを使用しないデバッグ</span><span class="sxs-lookup"><span data-stu-id="f9ec8-184">No-workspace debugging</span></span>

<span data-ttu-id="f9ec8-185">VSCode バージョン 1.9 以降では、PowerShell スクリプトを含むフォルダーを開かずに PowerShell スクリプトをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-185">As of VSCode version 1.9 you can debug PowerShell scripts without opening the folder that contains the PowerShell script.</span></span> <span data-ttu-id="f9ec8-186">**[ファイル] > [ファイルを開く]** の順にクリックして PowerShell スクリプト ファイルを開き、行にブレークポイントを設定し、<kbd>F9</kbd> キーを押し、<kbd>F5</kbd> キーを押してデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-186">Open the PowerShell script file with **File > Open File...**, set a breakpoint on a line, press <kbd>F9</kbd>, and then press <kbd>F5</kbd> to start debugging.</span></span> <span data-ttu-id="f9ec8-187">[Debug actions]\(デバッグ アクション\) ウィンドウが表示されます。ここでは、デバッガーを中断したり、デバッグをステップ実行、再開、停止したりできます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-187">You should see the Debug actions pane appear which allows you to break into the debugger, step, resume, and stop debugging.</span></span>

### <a name="workspace-debugging"></a><span data-ttu-id="f9ec8-188">ワークスペースを使用したデバッグ</span><span class="sxs-lookup"><span data-stu-id="f9ec8-188">Workspace debugging</span></span>

<span data-ttu-id="f9ec8-189">ワークスペースを使用したデバッグとは、 **[ファイル]** メニューの **[フォルダーを開く]** を使用して Visual Studio Code で開いたフォルダーのコンテキストでデバッグを行うことを言います。開いたフォルダーは、通常は PowerShell プロジェクトのフォルダーや Git リポジトリのルートです。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-189">Workspace debugging refers to debugging in the context of a folder that you've opened in Visual Studio Code from the **File** menu using **Open Folder...**. The folder you open is typically your PowerShell project folder and/or the root of your Git repository.</span></span>

<span data-ttu-id="f9ec8-190">このモードの場合も、<kbd>F5</kbd> キーを押せば、現在選択されている PowerShell スクリプトのデバッグを開始できます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-190">Even in this mode, you can start debugging the currently selected PowerShell script by pressing <kbd>F5</kbd>.</span></span> <span data-ttu-id="f9ec8-191">ただし、ワークスペースを使用したデバッグでは、現在開いているファイルをデバッグする以外に、複数のデバッグ構成を定義できます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-191">However, workspace debugging allows you to define multiple debug configurations other than just debugging the currently open file.</span></span> <span data-ttu-id="f9ec8-192">たとえば、次の目的で構成を追加できます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-192">For instance, you can add a configuration to:</span></span>

- <span data-ttu-id="f9ec8-193">デバッガーで Pester テストを起動します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-193">Launch Pester tests in the debugger.</span></span>
- <span data-ttu-id="f9ec8-194">デバッガーで引数を使用して特定のファイルを起動します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-194">Launch a specific file with arguments in the debugger.</span></span>
- <span data-ttu-id="f9ec8-195">デバッガーで対話型セッションを起動します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-195">Launch an interactive session in the debugger.</span></span>
- <span data-ttu-id="f9ec8-196">PowerShell ホスト手順にデバッガーをアタッチします。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-196">Attach the debugger to a PowerShell host process.</span></span>

<span data-ttu-id="f9ec8-197">デバッグ用の構成ファイルを作成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-197">Follow these steps to create your debug configuration file:</span></span>

  1. <span data-ttu-id="f9ec8-198">Windows または Linux の場合、<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> を押し、 **[デバッグ]** ビューを開きます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-198">Open the **Debug** view on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span> <span data-ttu-id="f9ec8-199">macOS の場合、<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> を押します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-199">On macOS, press <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span>
  1. <span data-ttu-id="f9ec8-200">ツールバーの **[構成]** 歯車アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-200">Click the **Configure** gear icon in the toolbar.</span></span>
  1. <span data-ttu-id="f9ec8-201">VSCode により、 **[環境の選択]** が求められます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-201">VSCode prompts you to **Select Environment**.</span></span> <span data-ttu-id="f9ec8-202">**[PowerShell]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-202">Choose **PowerShell**.</span></span>

<span data-ttu-id="f9ec8-203">結果的に、VSCode によってワークスペース フォルダーのルートにディレクトリとファイル `.vscode\launch.json` が作成されます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-203">The result is that VSCode creates a directory and a file `.vscode\launch.json` in the root of your workspace folder.</span></span> <span data-ttu-id="f9ec8-204">この場所にデバッグ構成が格納されます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-204">This location is where your debug configuration is stored.</span></span> <span data-ttu-id="f9ec8-205">ファイルが Git リポジトリにある場合は、通常、`launch.json` ファイルをコミットすることになるでしょう。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-205">If your files are in a Git repository, you typically want to commit the `launch.json` file.</span></span> <span data-ttu-id="f9ec8-206">`launch.json` ファイルの内容:</span><span class="sxs-lookup"><span data-stu-id="f9ec8-206">The contents of the `launch.json` file are:</span></span>

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

<span data-ttu-id="f9ec8-207">このファイルは一般的なデバッグ シナリオです。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-207">This file represents the common debug scenarios.</span></span> <span data-ttu-id="f9ec8-208">エディターでこのファイルを開いた場合、 **[構成の追加]** ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-208">When you open this file in the editor, you see an **Add Configuration...** button.</span></span> <span data-ttu-id="f9ec8-209">このボタンをクリックすることで、PowerShell デバッグ構成をさらに追加できます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-209">You can click this button to add more PowerShell debug configurations.</span></span> <span data-ttu-id="f9ec8-210">追加すると便利な構成の 1 つは、 **[PowerShell: Launch Script]\(PowerShell: 起動スクリプト\)** です。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-210">One useful configuration to add is **PowerShell: Launch Script**.</span></span> <span data-ttu-id="f9ec8-211">この構成では、エディターで現在どのファイルがアクティブであるかに関係なく、<kbd>F5</kbd> キーを押すと起動されるファイルを、オプションの引数と共に指定できます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-211">With this configuration, you can specify a file with optional arguments that should be launched whenever you press <kbd>F5</kbd> no matter which file is currently active in the editor.</span></span>

<span data-ttu-id="f9ec8-212">デバッグ構成が確立されたら、デバッグ セッション中に使用する構成を選択できます。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-212">After the debug configuration is established, you can select which configuration you want to use during a debug session.</span></span> <span data-ttu-id="f9ec8-213">**[デバッグ]** ビューのツール バーでデバッグ構成ドロップダウンから構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-213">Select a configuration from the debug configuration drop-down in the **Debug** view's toolbar.</span></span>

<span data-ttu-id="f9ec8-214">Visual Studio Code 用の PowerShell の拡張機能を使用開始するのに便利なブログを、次にいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-214">There are a few blogs that may be helpful to get you started using PowerShell extension for Visual Studio Code:</span></span>

- <span data-ttu-id="f9ec8-215">[PowerShell の拡張機能][ps-extension]</span><span class="sxs-lookup"><span data-stu-id="f9ec8-215">[PowerShell Extension][ps-extension]</span></span>
- <span data-ttu-id="f9ec8-216">[Visual Studio Code での PowerShell スクリプトの記述およびデバッグ][debug]</span><span class="sxs-lookup"><span data-stu-id="f9ec8-216">[Write and debug PowerShell scripts in Visual Studio Code][debug]</span></span>
- <span data-ttu-id="f9ec8-217">[Visual Studio Code でのデバッグのガイダンス][vscode-guide]</span><span class="sxs-lookup"><span data-stu-id="f9ec8-217">[Debugging Visual Studio Code Guidance][vscode-guide]</span></span>
- <span data-ttu-id="f9ec8-218">[Visual Studio Code での PowerShell のデバッグ][ps-vscode]</span><span class="sxs-lookup"><span data-stu-id="f9ec8-218">[Debugging PowerShell in Visual Studio Code][ps-vscode]</span></span>
- <span data-ttu-id="f9ec8-219">[Visual Studio Code での PowerShell 開発の概要][getting-started]</span><span class="sxs-lookup"><span data-stu-id="f9ec8-219">[Get started with PowerShell development in Visual Studio Code][getting-started]</span></span>
- <span data-ttu-id="f9ec8-220">[PowerShell 開発のための Visual Studio Code の編集機能 – パート 1][editing-part1]</span><span class="sxs-lookup"><span data-stu-id="f9ec8-220">[Visual Studio Code editing features for PowerShell development – Part 1][editing-part1]</span></span>
- <span data-ttu-id="f9ec8-221">[PowerShell 開発のための Visual Studio Code の編集機能 – パート 2][editing-part2]</span><span class="sxs-lookup"><span data-stu-id="f9ec8-221">[Visual Studio Code editing features for PowerShell development – Part 2][editing-part2]</span></span>
- <span data-ttu-id="f9ec8-222">[Visual Studio Code での PowerShell スクリプトのデバッグ – パート 1][debugging-part1]</span><span class="sxs-lookup"><span data-stu-id="f9ec8-222">[Debugging PowerShell script in Visual Studio Code – Part 1][debugging-part1]</span></span>
- <span data-ttu-id="f9ec8-223">[Visual Studio Code での PowerShell スクリプトのデバッグ – パート 2][debugging-part2]</span><span class="sxs-lookup"><span data-stu-id="f9ec8-223">[Debugging PowerShell script in Visual Studio Code – Part 2][debugging-part2]</span></span>

[ise]: ../ise/Introducing-the-Windows-PowerShell-ISE.md
[install-pscore-linux]:  ../../install/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:  ../../install/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../install/Installing-PowerShell-Core-on-Windows.md
[install-winps]: ../../install/Installing-Windows-PowerShell.md
[ps-extension]: https://blogs.msdn.microsoft.com/cdndevs/2015/12/11/visual-studio-code-powershell-extension/
[debug]: https://devblogs.microsoft.com/powershell/announcing-powershell-language-support-for-visual-studio-code-and-more/
[vscode-guide]: https://johnpapa.net/debugging-with-visual-studio-code/
[ps-vscode]: https://github.com/PowerShell/vscode-powershell/tree/master/examples
[getting-started]: https://devblogs.microsoft.com/scripting/get-started-with-powershell-development-in-visual-studio-code/
[editing-part1]: https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]: https://devblogs.microsoft.com/scripting/visual-studio-code-editing-features-for-powershell-development-part-2/
[debugging-part1]: https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]: https://devblogs.microsoft.com/scripting/debugging-powershell-script-in-visual-studio-code-part-2/

## <a name="powershell-extension-for-vscode"></a><span data-ttu-id="f9ec8-224">VSCode 用 PowerShell 拡張機能</span><span class="sxs-lookup"><span data-stu-id="f9ec8-224">PowerShell Extension for VSCode</span></span>

<span data-ttu-id="f9ec8-225">PowerShell の拡張機能のソース コードは、[GitHub](https://github.com/PowerShell/vscode-powershell) にあります。</span><span class="sxs-lookup"><span data-stu-id="f9ec8-225">The PowerShell extension's source code can be found on [GitHub](https://github.com/PowerShell/vscode-powershell).</span></span>
