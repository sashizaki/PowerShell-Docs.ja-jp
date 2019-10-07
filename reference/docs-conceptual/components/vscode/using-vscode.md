---
title: PowerShell 開発のための Visual Studio Code の使用
description: PowerShell 開発のための Visual Studio Code の使用
ms.date: 08/06/2018
ms.openlocfilehash: 0e082b74f99d214749f10224fb5aaf41e2ef8951
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71325241"
---
# <a name="using-visual-studio-code-for-powershell-development"></a><span data-ttu-id="cfade-103">PowerShell 開発のための Visual Studio Code の使用</span><span class="sxs-lookup"><span data-stu-id="cfade-103">Using Visual Studio Code for PowerShell Development</span></span>

<span data-ttu-id="cfade-104">[PowerShell ISE][ise] だけでなく、PowerShell も Visual Studio Code (VSCode) で問題なくサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cfade-104">In addition to the [PowerShell ISE][ise], PowerShell is also well-supported in Visual Studio Code (VSCode).</span></span> <span data-ttu-id="cfade-105">さらに、PowerShell Core で ISE はサポートされていませんが、VSCode はすべてのプラットフォーム (Windows、macOS、Linux) の PowerShell Core でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cfade-105">Furthermore, the ISE is not supported with PowerShell Core, while VSCode is supported for PowerShell Core on all platforms (Windows, macOS, and Linux)</span></span>

<span data-ttu-id="cfade-106">PowerShell バージョンが 5 の Windows で VSCode を使用する場合、Windows 10 を使用するか、ダウンレベルの Windows OS (Windows 8.1 などの) 向けの [Windows Management Framework 5.0 RTM](https://devblogs.microsoft.com/powershell/windows-management-framework-wmf-5-0-rtm-is-now-available-via-the-microsoft-update-catalog/) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="cfade-106">You can use VSCode on Windows with PowerShell version 5 by using Windows 10 or by installing [Windows Management Framework 5.0 RTM](https://devblogs.microsoft.com/powershell/windows-management-framework-wmf-5-0-rtm-is-now-available-via-the-microsoft-update-catalog/) for down-level Windows OSs (e.g. Windows 8.1, etc.).</span></span>

<span data-ttu-id="cfade-107">開始する前に、システムに PowerShell があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cfade-107">Before starting it, please make sure PowerShell exists on your system.</span></span> <span data-ttu-id="cfade-108">Windows、macOS、および Linux 上の最近のワークロードに対しては、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfade-108">For modern workloads on Windows, macOS, and Linux, see:</span></span>

- <span data-ttu-id="cfade-109">[Linux への PowerShell Core のインストール][install-pscore-linux]</span><span class="sxs-lookup"><span data-stu-id="cfade-109">[Installing PowerShell Core on Linux][install-pscore-linux]</span></span>
- <span data-ttu-id="cfade-110">[macOS への PowerShell Core のインストール][install-pscore-macos]</span><span class="sxs-lookup"><span data-stu-id="cfade-110">[Installing PowerShell Core on macOS][install-pscore-macos]</span></span>
- <span data-ttu-id="cfade-111">[Windows への PowerShell Core のインストール][install-pscore-windows]</span><span class="sxs-lookup"><span data-stu-id="cfade-111">[Installing PowerShell Core on Windows][install-pscore-windows]</span></span>

<span data-ttu-id="cfade-112">従来の Windows PowerShell ワークロードについては、「[Windows PowerShell のインストール][install-winps]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfade-112">For traditional Windows PowerShell workloads, see [Installing Windows PowerShell][install-winps].</span></span>

## <a name="editing-with-vscode"></a><span data-ttu-id="cfade-113">VSCode による編集</span><span class="sxs-lookup"><span data-stu-id="cfade-113">Editing with VSCode</span></span>

1. [<span data-ttu-id="cfade-114">VSCode のインストール</span><span class="sxs-lookup"><span data-stu-id="cfade-114">Installing VSCode</span></span>](https://code.visualstudio.com/Docs/setup/setup-overview)

   - <span data-ttu-id="cfade-115">**Linux**: [Linux 上で VS コードを実行する](https://code.visualstudio.com/docs/setup/linux)方法に関するページのインストール手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cfade-115">**Linux**: follow the installation instructions on the [Running VSCode on Linux](https://code.visualstudio.com/docs/setup/linux) page</span></span>
   - <span data-ttu-id="cfade-116">**macOS**: [macOS 上で VS コードを実行する](https://code.visualstudio.com/docs/setup/mac)方法に関するページのインストール手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cfade-116">**macOS**: follow the installation instructions on the [Running VSCode on macOS](https://code.visualstudio.com/docs/setup/mac) page</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="cfade-117">macOS で、PowerShell の拡張機能用が正常に動作するには、OpenSSL をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfade-117">On macOS, you must install OpenSSL for the PowerShell extension to work correctly.</span></span> <span data-ttu-id="cfade-118">これには、[Homebrew](https://brew.sh/) をインストールして、`brew install openssl` を実行するのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="cfade-118">The easiest way to accomplish this is to install [Homebrew](https://brew.sh/) and then run `brew install openssl`.</span></span> <span data-ttu-id="cfade-119">これで、VSCode を使用して PowerShell 拡張機能を正常に読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="cfade-119">VSCode can now load the PowerShell extension successfully.</span></span>

   - <span data-ttu-id="cfade-120">**Windows**: [Windows 上で VS コードを実行する](https://code.visualstudio.com/docs/setup/windows)方法に関するページのインストール手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cfade-120">**Windows**: follow the installation instructions on the [Running VSCode on Windows](https://code.visualstudio.com/docs/setup/windows) page</span></span>

2. <span data-ttu-id="cfade-121">PowerShell 拡張機能のインストール</span><span class="sxs-lookup"><span data-stu-id="cfade-121">Installing PowerShell Extension</span></span>

   - <span data-ttu-id="cfade-122">次の方法で VSCode アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="cfade-122">Launch the VSCode app by:</span></span>
     - <span data-ttu-id="cfade-123">**Windows**: PowerShell セッションで `code` と入力します。</span><span class="sxs-lookup"><span data-stu-id="cfade-123">**Windows**: typing `code` in your PowerShell session</span></span>
     - <span data-ttu-id="cfade-124">**Linux**: ターミナルで `code` と入力します。</span><span class="sxs-lookup"><span data-stu-id="cfade-124">**Linux**: typing `code` in your terminal</span></span>
     - <span data-ttu-id="cfade-125">**macOS**: ターミナルで `code` と入力します。</span><span class="sxs-lookup"><span data-stu-id="cfade-125">**macOS**: typing `code` in your terminal</span></span>
   - <span data-ttu-id="cfade-126"><kbd>Ctrl</kbd>+<kbd>P</kbd> (Mac 上では、<kbd>Cmd</kbd>+<kbd>P</kbd>) を押して、**Quick Open** を起動します。</span><span class="sxs-lookup"><span data-stu-id="cfade-126">Launch **Quick Open** by pressing <kbd>Ctrl</kbd>+<kbd>P</kbd> (<kbd>Cmd</kbd>+<kbd>P</kbd> on Mac).</span></span>
   - <span data-ttu-id="cfade-127">Quick Open で `ext install powershell` と入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cfade-127">In Quick Open, type `ext install powershell` and hit **Enter**.</span></span>
   - <span data-ttu-id="cfade-128">サイド バーに **[拡張機能]** ビューが開きます。</span><span class="sxs-lookup"><span data-stu-id="cfade-128">The **Extensions** view opens on the Side Bar.</span></span> <span data-ttu-id="cfade-129">Microsoft の PowerShell の拡張機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfade-129">Select the PowerShell extension from Microsoft.</span></span>
     <span data-ttu-id="cfade-130">次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfade-130">You should see something like below:</span></span>

     ![VSCode](../../images/using-vscode/vscode.png)

   - <span data-ttu-id="cfade-132">Microsoft の PowerShell 拡張機能の、 **[インストール]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfade-132">Click the **Install** button on the PowerShell extension from Microsoft.</span></span>
   - <span data-ttu-id="cfade-133">インストール後、 **[インストール]** ボタンは **[再読み込み]** に変わります。</span><span class="sxs-lookup"><span data-stu-id="cfade-133">After the install, you see the **Install** button turns to **Reload**.</span></span> <span data-ttu-id="cfade-134">**[再読み込み]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfade-134">Click on **Reload**.</span></span>
   - <span data-ttu-id="cfade-135">VSCode が再読み込みされたら、編集が可能になります。</span><span class="sxs-lookup"><span data-stu-id="cfade-135">After VSCode has reload, you are ready for editing.</span></span>

<span data-ttu-id="cfade-136">たとえば、新しいファイルを作成するには、 **[ファイル]、[新規]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfade-136">For example, to create a new file, click **File->New**.</span></span> <span data-ttu-id="cfade-137">保存するには、 **[ファイル]、[保存]** の順にクリックし、`HelloWorld.ps1` などのファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="cfade-137">To save it, click **File->Save** and then provide a file name, let's say `HelloWorld.ps1`.</span></span> <span data-ttu-id="cfade-138">ファイルを閉じるには、ファイル名の横の "x" をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfade-138">To close the file, click on "x" next to the file name.</span></span> <span data-ttu-id="cfade-139">VSCode を終了するには、 **[ファイル]、[終了]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfade-139">To exit VSCode, **File->Exit**.</span></span>

### <a name="installing-the-powershell-extension-on-restricted-systems"></a><span data-ttu-id="cfade-140">制限されているシステムへの PowerShell 拡張機能のインストール</span><span class="sxs-lookup"><span data-stu-id="cfade-140">Installing the PowerShell Extension on Restricted Systems</span></span>

<span data-ttu-id="cfade-141">一部のシステムはすべてのコード署名をチェックする必要があるように設定されているため、PowerShell エディター サービスをシステムで実行することを手動で承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfade-141">Some systems are set up in a way that requires all code signatures to be checked and thus requires PowerShell Editor Services to be manually approved to run on the system.</span></span> <span data-ttu-id="cfade-142">PowerShell 拡張機能をインストールしたが次のようなエラーが表示される場合、考えられる原因は実行ポリシーを変更するグループ ポリシーの更新です。</span><span class="sxs-lookup"><span data-stu-id="cfade-142">A Group Policy update that changes execution policy is a likely cause if you have installed the PowerShell extension but are reaching an error like:</span></span>

```
Language server startup failed.
```

<span data-ttu-id="cfade-143">PowerShell エディター サービスおよび VSCode 用 PowerShell 拡張機能を手動で承認するには、PowerShell プロンプトを開いて以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="cfade-143">To manually approve PowerShell Editor Services and thus the PowerShell extension for VSCode open a PowerShell prompt and run:</span></span>

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

<span data-ttu-id="cfade-144">"この信頼されていない発行元からのソフトウェアを実行しますか?" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfade-144">You are prompted with "Do you want to run software from this untrusted publisher?"</span></span> <span data-ttu-id="cfade-145">`R` キーを押してファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="cfade-145">Type `R` to run the file.</span></span> <span data-ttu-id="cfade-146">次に、VSCode を開き、PowerShell 拡張機能が正しく機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cfade-146">Then, open VSCode and check that the PowerShell extension is functioning properly.</span></span> <span data-ttu-id="cfade-147">まだ問題がある場合は、[GitHub](https://github.com/PowerShell/vscode-powershell/issues) で問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="cfade-147">If you still have issues getting started, let us know on [GitHub](https://github.com/PowerShell/vscode-powershell/issues).</span></span>

#### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a><span data-ttu-id="cfade-148">拡張機能で使用する PowerShell のバージョンを選択</span><span class="sxs-lookup"><span data-stu-id="cfade-148">Choosing a version of PowerShell to use with the extension</span></span>

<span data-ttu-id="cfade-149">Windows PowerShell と PowerShell Core がインストールされている場合、PowerShell の特定のバージョンを PowerShell の拡張機能で使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="cfade-149">With PowerShell Core installing side-by-side with Windows PowerShell, is it now possible to use a particular version of PowerShell with the PowerShell extension.</span></span> <span data-ttu-id="cfade-150">バージョンを選択するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cfade-150">Use the following these steps to choose the version:</span></span>

1. <span data-ttu-id="cfade-151">コマンド パレットを開きます (Windows と Linux では、<kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd>、macOS では、<kbd>Cmd</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd>)。</span><span class="sxs-lookup"><span data-stu-id="cfade-151">Open the command pallet (<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on Windows & Linux, <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> on macOS).</span></span>
1. <span data-ttu-id="cfade-152">"セッション" を検索します。</span><span class="sxs-lookup"><span data-stu-id="cfade-152">Search for "Session".</span></span>
1. <span data-ttu-id="cfade-153">[PowerShell:Show Session Menu]\(PowerShell: セッション メニューを表示\) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfade-153">Click on "PowerShell: Show Session Menu".</span></span>
1. <span data-ttu-id="cfade-154">一覧から、"PowerShell Core" など、使用する PowerShell のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="cfade-154">Choose the version of PowerShell you want to use from the list - for example, "PowerShell Core".</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cfade-155">この機能では、異なるオペレーティング システム上のいくつかのよく知られているパスを検索し、PowerShell のインストール場所を検出します。</span><span class="sxs-lookup"><span data-stu-id="cfade-155">This feature looks at a few well-known paths on different operating systems to discover install locations of PowerShell.</span></span> <span data-ttu-id="cfade-156">PowerShell を一般的ではない場所にインストールしている場合、最初にそれがセッション メニューに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="cfade-156">If you installed PowerShell to a non-typical location, it might not show up initially in the Session Menu.</span></span> <span data-ttu-id="cfade-157">次のように、[独自のカスタム パスを追加して](#adding-your-own-powershell-paths-to-the-session-menu)、セッション メニューを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="cfade-157">You can extend the session menu by [adding your own custom paths](#adding-your-own-powershell-paths-to-the-session-menu) as described below.</span></span>

>[!NOTE]
> <span data-ttu-id="cfade-158">次のようにセッション メニューに進むこともできます。</span><span class="sxs-lookup"><span data-stu-id="cfade-158">There is another way to get to the session menu.</span></span> <span data-ttu-id="cfade-159">エディターで PowerShell ファイルを開いているときに、右下に緑のバージョン番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfade-159">When a PowerShell file is open in your editor, you see a green version number in the bottom right.</span></span> <span data-ttu-id="cfade-160">このバージョン番号をクリックすると、セッション メニューに移動できます。</span><span class="sxs-lookup"><span data-stu-id="cfade-160">Clicking this version number will bring you to the session menu.</span></span>

##### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a><span data-ttu-id="cfade-161">セッション メニューへの独自の PowerShell のパスの追加</span><span class="sxs-lookup"><span data-stu-id="cfade-161">Adding your own PowerShell paths to the session menu</span></span>

<span data-ttu-id="cfade-162">VSCode 設定を利用し、セッション メニューに他の PowerShell の実行可能パスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="cfade-162">You can add other PowerShell executable paths to the session menu through a VSCode setting.</span></span>

<span data-ttu-id="cfade-163">次のように `powershell.powerShellAdditionalExePaths` のリストに項目を追加するか、`settings.json` にない場合はリストを作成します。</span><span class="sxs-lookup"><span data-stu-id="cfade-163">Add an item to the list `powershell.powerShellAdditionalExePaths` or create the list if it doesn't exist in your `settings.json`:</span></span>

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

<span data-ttu-id="cfade-164">各項目には次が必要です。</span><span class="sxs-lookup"><span data-stu-id="cfade-164">Each item must have:</span></span>

* <span data-ttu-id="cfade-165">`exePath`:`pwsh` または `powershell` 実行可能ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="cfade-165">`exePath`: The path to the `pwsh` or `powershell` executable.</span></span>
* <span data-ttu-id="cfade-166">`versionName`:セッション メニューに表示されるテキスト。</span><span class="sxs-lookup"><span data-stu-id="cfade-166">`versionName`: The text that will show up in the session menu.</span></span>

<span data-ttu-id="cfade-167">`powershell.powerShellDefaultVersion` の設定を使用して、これをセッション メニューに表示されるテキストに設定して、使用する既定の PowerShell のバージョンを設定できます (前の設定での `versionName`)。</span><span class="sxs-lookup"><span data-stu-id="cfade-167">You can set the default PowerShell version to use using the `powershell.powerShellDefaultVersion` setting by setting this to the text displayed in the session menu (aka the `versionName` in the last setting):</span></span>

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

<span data-ttu-id="cfade-168">この設定を設定したら、VSCode を再開するか [Developer:Reload Window]\(Developer: ウィンドウの再読み込み\) のコマンド パレットアクションを使用して、現在の VSCode ウィンドウを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="cfade-168">Once you've set this setting, restart VSCode or use the the "Developer: Reload Window" command pallet action to reload the current VSCode window.</span></span>

<span data-ttu-id="cfade-169">これでセッション メニューを開くと、追加した PowerShell バージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfade-169">If you open the session menu, you now see your additional PowerShell versions!</span></span>

> [!NOTE]
> <span data-ttu-id="cfade-170">これは、ソースから PowerShell をビルドした場合、PowerShell のローカル ビルドをテストする優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="cfade-170">If you build PowerShell from source, this is a great way to test out your local build of PowerShell.</span></span>

#### <a name="configuration-settings-for-vscode"></a><span data-ttu-id="cfade-171">VSCode の構成設定</span><span class="sxs-lookup"><span data-stu-id="cfade-171">Configuration settings for VSCode</span></span>

<span data-ttu-id="cfade-172">前段の手順を使用して、`settings.json` に構成設定を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="cfade-172">By using the steps in the previous paragraph you can add configuration settings in `settings.json`.</span></span>

<span data-ttu-id="cfade-173">VSCode には、次の構成設定をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cfade-173">We recommend the following configuration settings for VSCode:</span></span>

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

<span data-ttu-id="cfade-174">これらの設定がすべてのファイルの種類に影響しないようにする場合、VSCode では言語ごとに構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="cfade-174">If you don't want these settings to affect all files types, VSCode also allows per-language configurations.</span></span> <span data-ttu-id="cfade-175">`[<language-name>]` フィールドに設定を指定して、言語固有の設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="cfade-175">Create a language specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="cfade-176">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="cfade-176">For example:</span></span>

```json
"[powershell]": {
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="cfade-177">VSCode でのファイル エンコードについて詳しくは、[ファイルのエンコードの理解](understanding-file-encoding.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="cfade-177">For more information about file encoding in VSCode, see [Understanding file encoding](understanding-file-encoding.md).</span></span>

## <a name="debugging-with-vscode"></a><span data-ttu-id="cfade-178">VSCode によるデバッグ</span><span class="sxs-lookup"><span data-stu-id="cfade-178">Debugging with VSCode</span></span>

### <a name="no-workspace-debugging"></a><span data-ttu-id="cfade-179">ワークスペースを使用しないデバッグ</span><span class="sxs-lookup"><span data-stu-id="cfade-179">No-workspace debugging</span></span>

<span data-ttu-id="cfade-180">VSCode バージョン 1.9 以降では、PowerShell スクリプトを含むフォルダーを開かずに PowerShell スクリプトをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="cfade-180">As of VSCode version 1.9 you can debug PowerShell scripts without having to open the folder containing the PowerShell script.</span></span> <span data-ttu-id="cfade-181">**[ファイル] > [ファイルを開く]** の順にクリックして PowerShell スクリプト ファイルを開き、行にブレークポイントを設定し (<kbd>F9</kbd> キーを押す)、<kbd>F5</kbd> キーを押してデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="cfade-181">Open the PowerShell script file with **File->Open File...**, set a breakpoint on a line (press <kbd>F9</kbd>) and then press <kbd>F5</kbd> to start debugging.</span></span> <span data-ttu-id="cfade-182">[Debug actions]\(デバッグ アクション\) ウィンドウが表示されます。ここでは、デバッガーを中断したり、デバッグのステップ実行、再開、停止を行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="cfade-182">You should see the Debug actions pane appear which allows you to break into the debugger, step, resume and stop debugging.</span></span>

### <a name="workspace-debugging"></a><span data-ttu-id="cfade-183">ワークスペースを使用したデバッグ</span><span class="sxs-lookup"><span data-stu-id="cfade-183">Workspace debugging</span></span>

<span data-ttu-id="cfade-184">ワークスペースを使用したデバッグとは、 **[ファイル]** メニューの **[ファイルを開く]** を使用して Visual Studio Code で開いたフォルダーのコンテキストでデバッグを行うことを言います。</span><span class="sxs-lookup"><span data-stu-id="cfade-184">Workspace debugging refers to debugging in the context of a folder that you have opened in Visual Studio Code using **Open Folder...** from the **File** menu.</span></span> <span data-ttu-id="cfade-185">開いたフォルダーは、通常は PowerShell プロジェクトのフォルダーや Git リポジトリのルートです。</span><span class="sxs-lookup"><span data-stu-id="cfade-185">The folder you open is typically your PowerShell project folder and/or the root of your Git repository.</span></span>

<span data-ttu-id="cfade-186">このモードの場合も、単純に <kbd>F5</kbd> キーを押せば、現在選択されている PowerShell スクリプトのデバッグを開始できます。</span><span class="sxs-lookup"><span data-stu-id="cfade-186">Even in this mode, you can start debugging the currently selected PowerShell script by simply pressing <kbd>F5</kbd>.</span></span> <span data-ttu-id="cfade-187">ただし、ワークスペースを使用したデバッグでは、現在開いているファイルをデバッグする以外に、複数のデバッグ構成を定義できます。</span><span class="sxs-lookup"><span data-stu-id="cfade-187">However, workspace debugging allows you to define multiple debug configurations other than just debugging the currently open file.</span></span> <span data-ttu-id="cfade-188">たとえば、次に構成を追加できます。</span><span class="sxs-lookup"><span data-stu-id="cfade-188">For instance, you can add a configurations to:</span></span>

- <span data-ttu-id="cfade-189">デバッガーでの Pester テストの起動</span><span class="sxs-lookup"><span data-stu-id="cfade-189">Launch Pester tests in the debugger</span></span>
- <span data-ttu-id="cfade-190">デバッガーでの引数を使用した特定のファイルの起動</span><span class="sxs-lookup"><span data-stu-id="cfade-190">Launch a specific file with arguments in the debugger</span></span>
- <span data-ttu-id="cfade-191">デバッガーでの対話型セッションの起動</span><span class="sxs-lookup"><span data-stu-id="cfade-191">Launch an interactive session in the debugger</span></span>
- <span data-ttu-id="cfade-192">PowerShell ホスト手順へのデバッガーのアタッチ</span><span class="sxs-lookup"><span data-stu-id="cfade-192">Attach the debugger to a PowerShell host process</span></span>

<span data-ttu-id="cfade-193">デバッグ用の構成ファイルを作成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="cfade-193">Follow these steps to create your debug configuration file:</span></span>

  1. <span data-ttu-id="cfade-194"><kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> (Mac の場合は <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>) と押して、 **[デバッグ]** ビューを開きます。</span><span class="sxs-lookup"><span data-stu-id="cfade-194">Open the **Debug** view by pressing <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> (<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> on Mac).</span></span>
  2. <span data-ttu-id="cfade-195">ツールバーの **[構成]** 歯車アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="cfade-195">Click the **Configure** gear icon in the toolbar.</span></span>
  3. <span data-ttu-id="cfade-196">VSCode により、 **[環境の選択]** が求められます。</span><span class="sxs-lookup"><span data-stu-id="cfade-196">VSCode prompts you to **Select Environment**.</span></span> <span data-ttu-id="cfade-197">**[PowerShell]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cfade-197">Choose **PowerShell**.</span></span>

  <span data-ttu-id="cfade-198">これを行うときに、VSCode によってワークスペース フォルダーのルートに、".vscode\launch.json" のディレクトリとファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cfade-198">When you do this, VSCode creates a directory and a file ".vscode\launch.json" in the root of your workspace folder.</span></span> <span data-ttu-id="cfade-199">ここにデバッグ構成が格納されます。</span><span class="sxs-lookup"><span data-stu-id="cfade-199">This is where your debug configuration is stored.</span></span> <span data-ttu-id="cfade-200">ファイルが Git リポジトリにある場合は、通常は launch.json ファイルをコミットしたいでしょう。</span><span class="sxs-lookup"><span data-stu-id="cfade-200">If your files are in a Git repository, you typically want to commit the launch.json file.</span></span> <span data-ttu-id="cfade-201">launch.json ファイルの内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cfade-201">The contents of the launch.json file are:</span></span>

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

  <span data-ttu-id="cfade-202">これが、一般的なデバッグ シナリオです。</span><span class="sxs-lookup"><span data-stu-id="cfade-202">This represents the common debug scenarios.</span></span> <span data-ttu-id="cfade-203">ただし、エディターでこのファイルを開いた場合、 **[構成の追加]** ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfade-203">However, when you open this file in the editor, you see an **Add Configuration...** button.</span></span> <span data-ttu-id="cfade-204">このボタンをクリックすることで、PowerShell デバッグ構成をさらに追加できます。</span><span class="sxs-lookup"><span data-stu-id="cfade-204">You can click this button to add more PowerShell debug configurations.</span></span> <span data-ttu-id="cfade-205">追加すると便利な構成の 1 つは、 **[PowerShell: Launch Script]\(PowerShell: 起動スクリプト\)** です。</span><span class="sxs-lookup"><span data-stu-id="cfade-205">One handy configuration to add is **PowerShell: Launch Script**.</span></span> <span data-ttu-id="cfade-206">この構成では、エディターで現在どのファイルがアクティブであるかに関係なく、<kbd>F5</kbd> キーを押すと起動される特定のファイルを、オプションの引数とともに指定できます。</span><span class="sxs-lookup"><span data-stu-id="cfade-206">With this configuration, you can specify a specific file with optional arguments that should be launched whenever you press <kbd>F5</kbd> no matter which file is currently active in the editor.</span></span>

  <span data-ttu-id="cfade-207">デバッグ構成が確立されると、 **[デバッグ]** ビューのツールバーのデバッグ構成ドロップダウンから、デバッグ セッションで使用する構成を選択できます。</span><span class="sxs-lookup"><span data-stu-id="cfade-207">Once the debug configuration is established, you can select which configuration you want to use during a debug session by selecting one from the debug configuration drop-down in the **Debug** view's toolbar.</span></span>

<span data-ttu-id="cfade-208">Visual Studio Code 用の PowerShell の拡張機能を使用開始するのに便利なブログを、次にいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="cfade-208">There are a few blogs that may be helpful to get you started using PowerShell extension for Visual Studio Code:</span></span>

- <span data-ttu-id="cfade-209">[PowerShell の拡張機能][ps-extension]</span><span class="sxs-lookup"><span data-stu-id="cfade-209">[PowerShell Extension][ps-extension]</span></span>
- <span data-ttu-id="cfade-210">[Visual Studio Code での PowerShell スクリプトの記述およびデバッグ][debug]</span><span class="sxs-lookup"><span data-stu-id="cfade-210">[Write and debug PowerShell scripts in Visual Studio Code][debug]</span></span>
- <span data-ttu-id="cfade-211">[Visual Studio Code でのデバッグのガイダンス][vscode-guide]</span><span class="sxs-lookup"><span data-stu-id="cfade-211">[Debugging Visual Studio Code Guidance][vscode-guide]</span></span>
- <span data-ttu-id="cfade-212">[Visual Studio Code での PowerShell のデバッグ][ps-vscode]</span><span class="sxs-lookup"><span data-stu-id="cfade-212">[Debugging PowerShell in Visual Studio Code][ps-vscode]</span></span>
- <span data-ttu-id="cfade-213">[Visual Studio Code での PowerShell 開発の概要][getting-started]</span><span class="sxs-lookup"><span data-stu-id="cfade-213">[Get started with PowerShell development in Visual Studio Code][getting-started]</span></span>
- <span data-ttu-id="cfade-214">[PowerShell 開発のための Visual Studio Code の編集機能 – パート 1][editing-part1]</span><span class="sxs-lookup"><span data-stu-id="cfade-214">[Visual Studio Code editing features for PowerShell development – Part 1][editing-part1]</span></span>
- <span data-ttu-id="cfade-215">[PowerShell 開発のための Visual Studio Code の編集機能 – パート 2][editing-part2]</span><span class="sxs-lookup"><span data-stu-id="cfade-215">[Visual Studio Code editing features for PowerShell development – Part 2][editing-part2]</span></span>
- <span data-ttu-id="cfade-216">[Visual Studio Code での PowerShell スクリプトのデバッグ – パート 1][debugging-part1]</span><span class="sxs-lookup"><span data-stu-id="cfade-216">[Debugging PowerShell script in Visual Studio Code – Part 1][debugging-part1]</span></span>
- <span data-ttu-id="cfade-217">[Visual Studio Code での PowerShell スクリプトのデバッグ – パート 2][debugging-part2]</span><span class="sxs-lookup"><span data-stu-id="cfade-217">[Debugging PowerShell script in Visual Studio Code – Part 2][debugging-part2]</span></span>

[ise]: ../ise/Introducing-the-Windows-PowerShell-ISE.md
[install-pscore-linux]:  ../../setup/Installing-PowerShell-Core-on-Linux.md
[install-pscore-macos]:  ../../setup/Installing-PowerShell-Core-on-macOS.md
[install-pscore-windows]: ../../setup/Installing-PowerShell-Core-on-Windows.md
[install-winps]: ../../setup/Installing-Windows-PowerShell.md
[ps-extension]: https://blogs.msdn.microsoft.com/cdndevs/2015/12/11/visual-studio-code-powershell-extension/
[debug]: https://blogs.msdn.microsoft.com/powershell/2015/11/16/announcing-powershell-language-support-for-visual-studio-code-and-more/
[vscode-guide]: https://johnpapa.net/debugging-with-visual-studio-code/
[ps-vscode]: https://github.com/PowerShell/vscode-powershell/tree/master/examples
[getting-started]: https://blogs.technet.microsoft.com/heyscriptingguy/2016/12/05/get-started-with-powershell-development-in-visual-studio-code/
[editing-part1]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/01/11/visual-studio-code-editing-features-for-powershell-development-part-1/
[editing-part2]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/01/12/visual-studio-code-editing-features-for-powershell-development-part-2/
[debugging-part1]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/02/06/debugging-powershell-script-in-visual-studio-code-part-1/
[debugging-part2]: https://blogs.technet.microsoft.com/heyscriptingguy/2017/02/13/debugging-powershell-script-in-visual-studio-code-part-2/

## <a name="powershell-extension-for-vscode"></a><span data-ttu-id="cfade-218">VSCode 用 PowerShell 拡張機能</span><span class="sxs-lookup"><span data-stu-id="cfade-218">PowerShell Extension for VSCode</span></span>

<span data-ttu-id="cfade-219">PowerShell の拡張機能のソース コードは、[GitHub](https://github.com/PowerShell/vscode-powershell) にあります。</span><span class="sxs-lookup"><span data-stu-id="cfade-219">The PowerShell extension's source code can be found on [GitHub](https://github.com/PowerShell/vscode-powershell).</span></span>
