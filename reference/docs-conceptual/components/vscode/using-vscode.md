---
title: PowerShell 開発のための Visual Studio Code の使用
description: PowerShell 開発のための Visual Studio Code の使用
ms.date: 11/07/2019
ms.openlocfilehash: 8644aa7c648d649651ca679238e0b79ff35ac579
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500904"
---
# <a name="using-visual-studio-code-for-powershell-development"></a><span data-ttu-id="8ef87-103">PowerShell 開発のための Visual Studio Code の使用</span><span class="sxs-lookup"><span data-stu-id="8ef87-103">Using Visual Studio Code for PowerShell Development</span></span>

<span data-ttu-id="8ef87-104">[Visual Studio Code](https://code.visualstudio.com/) は、Microsoft によるクロスプラットフォーム (Windows、macOS、Linux) のスクリプト エディターです。</span><span class="sxs-lookup"><span data-stu-id="8ef87-104">[Visual Studio Code](https://code.visualstudio.com/) is a cross-platform (Windows, macOS, and Linux) script editor by Microsoft.</span></span> <span data-ttu-id="8ef87-105">[PowerShell 拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell)と共に使用すると、充実した対話型のスクリプト編集エクスペリエンスがもたらされ、信頼性の高い PowerShell スクリプトを簡単に記述できます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-105">Together with the [the PowerShell extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell), it provides a rich and interactive script editing experience, making it easier to write reliable PowerShell scripts.</span></span>

<span data-ttu-id="8ef87-106">PowerShell スクリプトの記述に使用するエディターとしては、PowerShell 拡張機能を備えた Visual Studio Code をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ef87-106">Visual Studio Code with the PowerShell extension is the recommended editor for writing PowerShell scripts.</span></span>
<span data-ttu-id="8ef87-107">次の PowerShell バージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8ef87-107">It supports the following PowerShell versions:</span></span>

- <span data-ttu-id="8ef87-108">PowerShell 7 以上</span><span class="sxs-lookup"><span data-stu-id="8ef87-108">PowerShell 7 and up</span></span>
- <span data-ttu-id="8ef87-109">PowerShell Core 6</span><span class="sxs-lookup"><span data-stu-id="8ef87-109">PowerShell Core 6</span></span>
- <span data-ttu-id="8ef87-110">Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="8ef87-110">Windows PowerShell 5.1</span></span>

<span data-ttu-id="8ef87-111">開始する前に、システムに PowerShell があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-111">Before you begin, make sure PowerShell exists on your system.</span></span> <span data-ttu-id="8ef87-112">Windows、macOS、Linux 上の最近のワークロードに対しては、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ef87-112">For modern workloads on Windows, macOS, and Linux, see the following links:</span></span>

- <span data-ttu-id="8ef87-113">[Linux への PowerShell のインストール][install-pscore-linux]</span><span class="sxs-lookup"><span data-stu-id="8ef87-113">[Installing PowerShell on Linux][install-pscore-linux]</span></span>
- <span data-ttu-id="8ef87-114">[macOS への PowerShell のインストール][install-pscore-macos]</span><span class="sxs-lookup"><span data-stu-id="8ef87-114">[Installing PowerShell on macOS][install-pscore-macos]</span></span>
- <span data-ttu-id="8ef87-115">[Windows への PowerShell のインストール][install-pscore-windows]</span><span class="sxs-lookup"><span data-stu-id="8ef87-115">[Installing PowerShell on Windows][install-pscore-windows]</span></span>

<span data-ttu-id="8ef87-116">従来の Windows PowerShell ワークロードについては、「[Windows PowerShell のインストール][install-winps]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ef87-116">For traditional Windows PowerShell workloads, see [Installing Windows PowerShell][install-winps].</span></span>

> [!NOTE]
> <span data-ttu-id="8ef87-117">Visual Studio Code は、[Visual Studio](https://visualstudio.microsoft.com/) と同じものではありません。</span><span class="sxs-lookup"><span data-stu-id="8ef87-117">Visual Studio Code is not the same as [Visual Studio](https://visualstudio.microsoft.com/).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ef87-118">Windows では [Windows PowerShell ISE][ise] も引き続き使用できますが、これはアクティブな機能開発の対象ではなくなっており、PowerShell 7 以降および PowerShell Core 6 は使用できません。</span><span class="sxs-lookup"><span data-stu-id="8ef87-118">The [Windows PowerShell ISE][ise] is also still available for Windows, however, it is no longer in active feature development and does not work with PowerShell 7 and up or PowerShell Core 6.</span></span>
> <span data-ttu-id="8ef87-119">Windows に付属するコンポーネントとして、セキュリティや優先順位の高いサービスに関する修正プログラムが引き続き公式でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-119">As a shipping component of Windows, it continues to be officially supported for security and high-priority servicing fixes.</span></span> <span data-ttu-id="8ef87-120">現在、Windows から ISE が削除される予定はありません。</span><span class="sxs-lookup"><span data-stu-id="8ef87-120">We currently have no plans to remove the ISE from Windows.</span></span>

## <a name="editing-with-visual-studio-code"></a><span data-ttu-id="8ef87-121">Visual Studio Code を使用した編集</span><span class="sxs-lookup"><span data-stu-id="8ef87-121">Editing with Visual Studio Code</span></span>

1. <span data-ttu-id="8ef87-122">Visual Studio Code をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ef87-122">Install Visual Studio Code.</span></span> <span data-ttu-id="8ef87-123">詳細については、「[Visual Studio Code の設定](https://code.visualstudio.com/Docs/setup/setup-overview)」という概要ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ef87-123">For more information, see the overview [Setting up Visual Studio Code](https://code.visualstudio.com/Docs/setup/setup-overview).</span></span>

    <span data-ttu-id="8ef87-124">プラットフォーム別のインストール手順があります。</span><span class="sxs-lookup"><span data-stu-id="8ef87-124">There are installation instructions for each platform:</span></span>

    - <span data-ttu-id="8ef87-125">**Windows**: [Windows 上での Visual Studio Code の実行](https://code.visualstudio.com/docs/setup/windows)に関するページに記載されているインストール手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="8ef87-125">**Windows**: follow the installation instructions on the [Running Visual Studio Code on Windows](https://code.visualstudio.com/docs/setup/windows) page.</span></span>
    - <span data-ttu-id="8ef87-126">**macOS**: [macOS 上での Visual Studio Code の実行](https://code.visualstudio.com/docs/setup/mac)に関するページに記載されているインストール手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="8ef87-126">**macOS**: follow the installation instructions on the [Running Visual Studio Code on macOS](https://code.visualstudio.com/docs/setup/mac) page.</span></span>
    - <span data-ttu-id="8ef87-127">**Linux**: [Linux 上での Visual Studio Code の実行](https://code.visualstudio.com/docs/setup/linux)に関するページに記載されているインストール手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="8ef87-127">**Linux**: follow the installation instructions on the [Running Visual Studio Code on Linux](https://code.visualstudio.com/docs/setup/linux) page.</span></span>

1. <span data-ttu-id="8ef87-128">PowerShell 拡張機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ef87-128">Install the PowerShell Extension.</span></span>

   1. <span data-ttu-id="8ef87-129">コンソールで「`code`」と入力するか、Visual Studio Code Insiders をインストールした場合は「`code-insiders`」と入力して、Visual Studio Code アプリを起動します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-129">Launch the Visual Studio Code app by typing `code` in a console or `code-insiders` if you installed Visual Studio Code Insiders.</span></span>
   1. <span data-ttu-id="8ef87-130">Windows または Linux の場合、<kbd>Ctrl</kbd>+<kbd>P</kbd> を押し、**Quick Open** を起動します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-130">Launch **Quick Open** on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="8ef87-131">macOS の場合、<kbd>Cmd</kbd>+<kbd>P</kbd> を押します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-131">On macOS, press <kbd>Cmd</kbd>+<kbd>P</kbd>.</span></span>
   1. <span data-ttu-id="8ef87-132">Quick Open を開き、「`ext install powershell`」と入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-132">In Quick Open, type `ext install powershell` and press **Enter**.</span></span>
   1. <span data-ttu-id="8ef87-133">サイド バーに **[拡張機能]** ビューが開きます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-133">The **Extensions** view opens on the Side Bar.</span></span> <span data-ttu-id="8ef87-134">Microsoft の PowerShell の拡張機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-134">Select the PowerShell extension from Microsoft.</span></span>
      <span data-ttu-id="8ef87-135">次の画像のような Visual Studio Code の画面が表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="8ef87-135">You should see a Visual Studio Code screen similar to the following image:</span></span>

      ![Visual Studio Code](media/using-vscode/vscode.png)

   1. <span data-ttu-id="8ef87-137">Microsoft の PowerShell 拡張機能の、 **[インストール]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ef87-137">Click the **Install** button on the PowerShell extension from Microsoft.</span></span>
   1. <span data-ttu-id="8ef87-138">インストール後、 **[インストール]** ボタンが **[再読み込み]** に変わった場合は、 **[再読み込み]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ef87-138">After the install, if you see the **Install** button turn into **Reload**, Click on **Reload**.</span></span>
   1. <span data-ttu-id="8ef87-139">Visual Studio Code が再読み込みされたら、編集が可能になります。</span><span class="sxs-lookup"><span data-stu-id="8ef87-139">After Visual Studio Code has reloaded, you're ready for editing.</span></span>

<span data-ttu-id="8ef87-140">たとえば、新しいファイルを作成するには、 **[ファイル]、[新規]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ef87-140">For example, to create a new file, click **File > New**.</span></span> <span data-ttu-id="8ef87-141">保存するには、 **[ファイル]、[保存]** の順にクリックし、`HelloWorld.ps1` のようなファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-141">To save it, click **File > Save** and then provide a file name, such as `HelloWorld.ps1`.</span></span> <span data-ttu-id="8ef87-142">ファイルを閉じるには、ファイル名の横の `X` をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ef87-142">To close the file, click the `X` next to the file name.</span></span> <span data-ttu-id="8ef87-143">Visual Studio Code を終了するには、 **[ファイル] > [終了]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-143">To exit Visual Studio Code, **File > Exit**.</span></span>

### <a name="installing-the-powershell-extension-on-restricted-systems"></a><span data-ttu-id="8ef87-144">制限されているシステムへの PowerShell 拡張機能のインストール</span><span class="sxs-lookup"><span data-stu-id="8ef87-144">Installing the PowerShell Extension on Restricted Systems</span></span>

<span data-ttu-id="8ef87-145">一部のシステムはすべてのコード署名をチェックする必要があるように設定されているため、PowerShell エディター サービスをシステムで実行することを手動で承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ef87-145">Some systems are set up in a way that requires all code signatures to be checked and requires PowerShell Editor Services to be manually approved to run on the system.</span></span> <span data-ttu-id="8ef87-146">PowerShell 拡張機能をインストールしたが次のようなエラーが表示される場合、考えられる原因は実行ポリシーを変更するグループ ポリシーの更新です。</span><span class="sxs-lookup"><span data-stu-id="8ef87-146">A Group Policy update that changes execution policy is a likely cause if you've installed the PowerShell extension but are receiving an error such as:</span></span>

```
Language server startup failed.
```

<span data-ttu-id="8ef87-147">PowerShell エディター サービスおよび Visual Studio Code 用 PowerShell 拡張機能を手動で承認するには、PowerShell プロンプトを開いて次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-147">To manually approve PowerShell Editor Services and the PowerShell extension for Visual Studio Code, open a PowerShell prompt and run the following command:</span></span>

```powershell
Import-Module $HOME\.vscode\extensions\ms-vscode.powershell*\modules\PowerShellEditorServices\PowerShellEditorServices.psd1
```

<span data-ttu-id="8ef87-148">"**この信頼されていない発行元からのソフトウェアを実行しますか?** " というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-148">You're prompted with **Do you want to run software from this untrusted publisher?**</span></span>
<span data-ttu-id="8ef87-149">`A` キーを押してファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-149">Type `A` to run the file.</span></span> <span data-ttu-id="8ef87-150">次に、Visual Studio Code を開き、PowerShell 拡張機能が正しく機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-150">Then, open Visual Studio Code and check that the PowerShell extension is functioning properly.</span></span> <span data-ttu-id="8ef87-151">まだ問題がある場合は、[GitHub](https://github.com/PowerShell/vscode-powershell/issues) で問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="8ef87-151">If you still have issues getting started, let us know on [GitHub](https://github.com/PowerShell/vscode-powershell/issues).</span></span>

> [!NOTE]
> <span data-ttu-id="8ef87-152">Visual Studio Code 用 PowerShell 拡張機能では、制約付き言語モードでの実行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8ef87-152">The PowerShell extension for Visual Studio Code does not support running in constrained language mode.</span></span> <span data-ttu-id="8ef87-153">詳細については、[そのサポートを追跡する GitHub イシュー](https://github.com/PowerShell/vscode-powershell/issues/606)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ef87-153">Please see the [GitHub issue tracking that support](https://github.com/PowerShell/vscode-powershell/issues/606) for more information.</span></span>

### <a name="using-an-older-version-of-the-powershell-extension-for-windows-powershell-v3-and-v4"></a><span data-ttu-id="8ef87-154">Windows PowerShell v3 および v4 用の古いバージョンの PowerShell 拡張機能を使用する</span><span class="sxs-lookup"><span data-stu-id="8ef87-154">Using an older version of the PowerShell Extension for Windows PowerShell v3 and v4</span></span>

<span data-ttu-id="8ef87-155">現在の PowerShell 拡張機能では [v3 と v4 のサポートが停止されています](https://github.com/PowerShell/vscode-powershell/issues/1310)が、サポートされていた最終バージョンの拡張機能を引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-155">Although the current PowerShell extension [stopped supporting v3 and v4](https://github.com/PowerShell/vscode-powershell/issues/1310), you can still use the last version of the extension that did.</span></span>

> [!NOTE]
> <span data-ttu-id="8ef87-156">この古いバージョンの拡張機能に修正プログラムが追加されることはありません。</span><span class="sxs-lookup"><span data-stu-id="8ef87-156">There will be no additional fixes to this older version of the extension.</span></span> <span data-ttu-id="8ef87-157">これは "そのままの状態で" 提供されますが、Windows PowerShell v3 と Windows PowerShell v4 を引き続き使用している場合に利用できます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-157">It's provided "AS IS" but is available for you if you are still using Windows PowerShell v3 and Windows PowerShell v4.</span></span>

<span data-ttu-id="8ef87-158">まず、[拡張機能] ペインを開いて「`PowerShell`」を検索します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-158">First, open the Extension pane and search for `PowerShell`.</span></span> <span data-ttu-id="8ef87-159">次に、歯車をクリックして、 **[Install another version...]\(別のバージョンをインストール...\)** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-159">Then click the gear and select **Install another version...**.</span></span>

![別のバージョンをインストール...](media/using-vscode/install-another-version.png)

<span data-ttu-id="8ef87-161">次に、 **`2020.1.0`** バージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-161">Then select the **`2020.1.0`** version.</span></span> <span data-ttu-id="8ef87-162">このバージョンの拡張機能は、v3 と v4 がサポートされている最後のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="8ef87-162">This version of the extension was the last version to support v3 and v4.</span></span>

<span data-ttu-id="8ef87-163">また、拡張機能のバージョンが自動的に更新されないように、次の設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-163">Also, add the following setting so that your extension version doesn't update automatically:</span></span>

```json
{
    "extensions.autoUpdate": false
}
```

<span data-ttu-id="8ef87-164">これはしばらくの間は動作しますが、このバージョンの拡張機能が動作しなくなるような変更が Visual Studio Code で実装される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8ef87-164">Although this will work in the forseeable future, Visual Studio Code could implement a change that breaks this version of the extension.</span></span>
<span data-ttu-id="8ef87-165">このことと、サポートがないことにより、次のいずれかを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ef87-165">Because of this, and lack of support, we highly recommend either:</span></span>

- <span data-ttu-id="8ef87-166">PowerShell 7 をダウンロードする - これは Windows PowerShell とのサイド バイ サイド インストールであり、PowerShell 拡張機能と最適に連携します</span><span class="sxs-lookup"><span data-stu-id="8ef87-166">Downloading PowerShell 7 - which is a side-by-side install to Windows PowerShell and works the best with the PowerShell extension</span></span>
- <span data-ttu-id="8ef87-167">Windows PowerShell 5.1 にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="8ef87-167">Upgrading to Windows PowerShell 5.1</span></span>

<span data-ttu-id="8ef87-168">この記事の「[Visual Studio Code を使用した編集](#editing-with-visual-studio-code)」セクションに、これらをインストールする場所へのリンクが記載されています。</span><span class="sxs-lookup"><span data-stu-id="8ef87-168">The [Editing with Visual Studio Code](#editing-with-visual-studio-code) section in this article links to where to install these.</span></span>

### <a name="choosing-a-version-of-powershell-to-use-with-the-extension"></a><span data-ttu-id="8ef87-169">拡張機能で使用する PowerShell のバージョンを選択</span><span class="sxs-lookup"><span data-stu-id="8ef87-169">Choosing a version of PowerShell to use with the extension</span></span>

<span data-ttu-id="8ef87-170">Windows PowerShell と PowerShell Core がインストールされている場合、PowerShell の特定のバージョンを PowerShell の拡張機能で使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8ef87-170">With PowerShell Core installing side-by-side with Windows PowerShell, it's now possible to use a particular version of PowerShell with the PowerShell extension.</span></span> <span data-ttu-id="8ef87-171">バージョンは次の手順で選択します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-171">Use the following steps to choose the version:</span></span>

1. <span data-ttu-id="8ef87-172">Windows または Linux の場合、<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> を使用して**コマンド パレット**を開きます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-172">Open the **Command Palette** on Windows or Linux with <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span> <span data-ttu-id="8ef87-173">macOS の場合、<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd> を使用します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-173">On macOS, use <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>P</kbd>.</span></span>
1. <span data-ttu-id="8ef87-174">"**セッション**" を検索します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-174">Search for **Session**.</span></span>
1. <span data-ttu-id="8ef87-175">**[PowerShell: Show Session Menu]\(PowerShell: セッション メニューを表示\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ef87-175">Click on **PowerShell: Show Session Menu**.</span></span>
1. <span data-ttu-id="8ef87-176">一覧から、"**PowerShell Core**" など、使用する PowerShell のバージョンを選択します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-176">Choose the version of PowerShell you want to use from the list, for example: **PowerShell Core**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ef87-177">この機能では、異なるオペレーティング システム上のいくつかのよく知られているパスを検索し、PowerShell のインストール場所を検出します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-177">This feature looks at a few well-known paths on different operating systems to discover install locations of PowerShell.</span></span> <span data-ttu-id="8ef87-178">PowerShell を一般的ではない場所にインストールしている場合、最初にそれがセッション メニューに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ef87-178">If you installed PowerShell to a non-typical location, it might not show up initially in the Session Menu.</span></span> <span data-ttu-id="8ef87-179">次のように、[独自のカスタム パスを追加して](#adding-your-own-powershell-paths-to-the-session-menu)、セッション メニューを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-179">You can extend the session menu by [adding your own custom paths](#adding-your-own-powershell-paths-to-the-session-menu) as described below.</span></span>

>[!NOTE]
> <span data-ttu-id="8ef87-180">次のようにセッション メニューに進むこともできます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-180">There's another way to get to the session menu.</span></span> <span data-ttu-id="8ef87-181">エディターで PowerShell ファイルを開いているときに、右下に緑のバージョン番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-181">When a PowerShell file is open in your editor, you see a green version number in the bottom right.</span></span> <span data-ttu-id="8ef87-182">このバージョン番号をクリックすると、セッション メニューに移動できます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-182">Clicking this version number will bring you to the session menu.</span></span>

### <a name="adding-your-own-powershell-paths-to-the-session-menu"></a><span data-ttu-id="8ef87-183">セッション メニューへの独自の PowerShell のパスの追加</span><span class="sxs-lookup"><span data-stu-id="8ef87-183">Adding your own PowerShell paths to the session menu</span></span>

<span data-ttu-id="8ef87-184">[Visual Studio Code 設定](https://code.visualstudio.com/docs/getstarted/settings): `powershell.powerShellAdditionalExePaths` を使用して、セッション メニューに他の PowerShell の実行パスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-184">You can add other PowerShell executable paths to the session menu through the [Visual Studio Code setting](https://code.visualstudio.com/docs/getstarted/settings): `powershell.powerShellAdditionalExePaths`.</span></span>

<span data-ttu-id="8ef87-185">次のように `powershell.powerShellAdditionalExePaths` のリストに項目を追加するか、`settings.json` にない場合はリストを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-185">Add an item to the list `powershell.powerShellAdditionalExePaths` or create the list if it doesn't exist in your `settings.json`:</span></span>

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

<span data-ttu-id="8ef87-186">各項目には次が必要です。</span><span class="sxs-lookup"><span data-stu-id="8ef87-186">Each item must have:</span></span>

- <span data-ttu-id="8ef87-187">`exePath`:`pwsh` または `powershell` 実行可能ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="8ef87-187">`exePath`: The path to the `pwsh` or `powershell` executable.</span></span>
- <span data-ttu-id="8ef87-188">`versionName`:セッション メニューに表示されるテキスト。</span><span class="sxs-lookup"><span data-stu-id="8ef87-188">`versionName`: The text that will show up in the session menu.</span></span>

<span data-ttu-id="8ef87-189">`powershell.powerShellDefaultVersion` の設定を使用して、これをセッション メニューに表示されるテキストに設定して、使用する既定の PowerShell のバージョンを設定できます (前の設定での `versionName`)。</span><span class="sxs-lookup"><span data-stu-id="8ef87-189">You can set the default PowerShell version to use the `powershell.powerShellDefaultVersion` setting by setting this to the text displayed in the session menu (also known as the `versionName` in the last setting):</span></span>

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

<span data-ttu-id="8ef87-190">この設定を構成したら、Visual Studio Code を再起動します。または、**コマンド パレット**から現在の Visual Studio Code ウィンドウを再度読み込むには、「**Developer: Reload Window**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-190">After you've configured this setting, restart Visual Studio Code or to reload the current Visual Studio Code window from the **Command Palette**, type **Developer: Reload Window**.</span></span>

<span data-ttu-id="8ef87-191">これでセッション メニューを開くと、追加した PowerShell バージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-191">If you open the session menu, you now see your additional PowerShell versions!</span></span>

> [!NOTE]
> <span data-ttu-id="8ef87-192">これは、ソースから PowerShell をビルドした場合、PowerShell のローカル ビルドをテストする優れた方法です。</span><span class="sxs-lookup"><span data-stu-id="8ef87-192">If you build PowerShell from source, this is a great way to test out your local build of PowerShell.</span></span>

### <a name="configuration-settings-for-visual-studio-code"></a><span data-ttu-id="8ef87-193">Visual Studio Code の構成設定</span><span class="sxs-lookup"><span data-stu-id="8ef87-193">Configuration settings for Visual Studio Code</span></span>

<span data-ttu-id="8ef87-194">まず、Visual Studio Code の設定を変更する方法に慣れていない場合は、[Visual Studio Code の設定に関するドキュメント](https://code.visualstudio.com/docs/getstarted/settings)を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ef87-194">First, if you're not familiar with how to change settings in Visual Studio Code, we recommend looking at [Visual Studio Code's settings documentation](https://code.visualstudio.com/docs/getstarted/settings).</span></span>

<span data-ttu-id="8ef87-195">前段の手順を使用して、`settings.json` に構成設定を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-195">By using the steps in the previous paragraph, you can add configuration settings in `settings.json`.</span></span>

```json
{
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "files.trimTrailingWhitespace": true,
    "files.encoding": "utf8bom",
    "files.autoGuessEncoding": true
}
```

<span data-ttu-id="8ef87-196">これらの設定がすべてのファイルの種類に影響しないようにする場合、Visual Studio Code では言語ごとに構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-196">If you don't want these settings to affect all files types, Visual Studio Code also allows per-language configurations.</span></span> <span data-ttu-id="8ef87-197">`[<language-name>]` フィールドに設定を指定して、言語固有の設定を作成します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-197">Create a language-specific setting by putting settings in a `[<language-name>]` field.</span></span> <span data-ttu-id="8ef87-198">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-198">For example:</span></span>

```json
{
    "[powershell]": {
        "files.encoding": "utf8bom",
        "files.autoGuessEncoding": true
    }
}
```

> [!TIP]
> <span data-ttu-id="8ef87-199">Visual Studio Code でのファイル エンコードについて詳しくは、[ファイル エンコードの概要](understanding-file-encoding.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8ef87-199">For more information about file encoding in Visual Studio Code, see [Understanding file encoding](understanding-file-encoding.md).</span></span>
>
> <span data-ttu-id="8ef87-200">また、PowerShell 編集用に Visual Studio Code を構成する方法に関するその他のヒントについては、「[Visual Studio Code で ISE のエクスペリエンスをレプリケートする方法](How-To-Replicate-the-ISE-Experience-In-VSCode.md)」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8ef87-200">Also check out the [How to replicate the ISE experience in Visual Studio Code](How-To-Replicate-the-ISE-Experience-In-VSCode.md) for other tips on how to configure Visual Studio Code for PowerShell editing.</span></span>

## <a name="debugging-with-visual-studio-code"></a><span data-ttu-id="8ef87-201">Visual Studio Code を使用したデバッグ</span><span class="sxs-lookup"><span data-stu-id="8ef87-201">Debugging with Visual Studio Code</span></span>

### <a name="no-workspace-debugging"></a><span data-ttu-id="8ef87-202">ワークスペースを使用しないデバッグ</span><span class="sxs-lookup"><span data-stu-id="8ef87-202">No-workspace debugging</span></span>

<span data-ttu-id="8ef87-203">Visual Studio Code バージョン 1.9 以降では、PowerShell スクリプトを含むフォルダーを開かずに PowerShell スクリプトをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-203">As of Visual Studio Code version 1.9 you can debug PowerShell scripts without opening the folder that contains the PowerShell script.</span></span> <span data-ttu-id="8ef87-204">**[ファイル] > [ファイルを開く]** の順にクリックして PowerShell スクリプト ファイルを開き、行にブレークポイントを設定し、<kbd>F9</kbd> キーを押し、<kbd>F5</kbd> キーを押してデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-204">Open the PowerShell script file with **File > Open File...**, set a breakpoint on a line, press <kbd>F9</kbd>, and then press <kbd>F5</kbd> to start debugging.</span></span> <span data-ttu-id="8ef87-205">[Debug actions]\(デバッグ アクション\) ウィンドウが表示されます。ここでは、デバッガーを中断したり、デバッグをステップ実行、再開、停止したりできます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-205">You should see the Debug actions pane appear which allows you to break into the debugger, step, resume, and stop debugging.</span></span>

### <a name="workspace-debugging"></a><span data-ttu-id="8ef87-206">ワークスペースを使用したデバッグ</span><span class="sxs-lookup"><span data-stu-id="8ef87-206">Workspace debugging</span></span>

<span data-ttu-id="8ef87-207">ワークスペースを使用したデバッグとは、 **[ファイル]** メニューの **[フォルダーを開く]** を使用して Visual Studio Code で開いたフォルダーのコンテキストでデバッグを行うことを言います。開いたフォルダーは、通常は PowerShell プロジェクトのフォルダーや Git リポジトリのルートです。</span><span class="sxs-lookup"><span data-stu-id="8ef87-207">Workspace debugging refers to debugging in the context of a folder that you've opened in Visual Studio Code from the **File** menu using **Open Folder...**. The folder you open is typically your PowerShell project folder and/or the root of your Git repository.</span></span>

<span data-ttu-id="8ef87-208">このモードの場合も、<kbd>F5</kbd> キーを押せば、現在選択されている PowerShell スクリプトのデバッグを開始できます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-208">Even in this mode, you can start debugging the currently selected PowerShell script by pressing <kbd>F5</kbd>.</span></span> <span data-ttu-id="8ef87-209">ただし、ワークスペースを使用したデバッグでは、現在開いているファイルをデバッグする以外に、複数のデバッグ構成を定義できます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-209">However, workspace debugging allows you to define multiple debug configurations other than just debugging the currently open file.</span></span> <span data-ttu-id="8ef87-210">これらについては、この後すぐに説明します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-210">We'll get to those in a moment.</span></span>

<span data-ttu-id="8ef87-211">デバッグ用の構成ファイルを作成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8ef87-211">Follow these steps to create your debug configuration file:</span></span>

  1. <span data-ttu-id="8ef87-212">Windows または Linux の場合、<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> を押し、 **[デバッグ]** ビューを開きます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-212">Open the **Debug** view on Windows or Linux by pressing <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span> <span data-ttu-id="8ef87-213">macOS の場合、<kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd> を押します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-213">On macOS, press <kbd>Cmd</kbd>+<kbd>Shift</kbd>+<kbd>D</kbd>.</span></span>
  1. <span data-ttu-id="8ef87-214">"launch.json ファイルの作成" リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ef87-214">Click the "create a launch.json file" link.</span></span>
  1. <span data-ttu-id="8ef87-215">Visual Studio Code により、 **[環境の選択]** が求められます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-215">Visual Studio Code prompts you to **Select Environment**.</span></span> <span data-ttu-id="8ef87-216">**[PowerShell]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-216">Choose **PowerShell**.</span></span>
  1. <span data-ttu-id="8ef87-217">最後に、使用するデバッグの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-217">Lastly, choose the type of debugging you'd like to use:</span></span>

- <span data-ttu-id="8ef87-218">**現在のファイルを起動** - 現在アクティブなエディター ウィンドウのファイルを起動してデバッグします</span><span class="sxs-lookup"><span data-stu-id="8ef87-218">**Launch Current File** - Launch and debug the file in the currently active editor window</span></span>
- <span data-ttu-id="8ef87-219">**スクリプトを起動** - 指定したファイルまたはコマンドを起動してデバッグします</span><span class="sxs-lookup"><span data-stu-id="8ef87-219">**Launch Script** - Launch and debug the specified file or command</span></span>
- <span data-ttu-id="8ef87-220">**対話型セッション** - 統合コンソールから実行されたコマンドをデバッグします</span><span class="sxs-lookup"><span data-stu-id="8ef87-220">**Interactive Session** - Debug commands executed from the Integrated Console</span></span>
- <span data-ttu-id="8ef87-221">**アタッチ** - 実行中の PowerShell ホスト プロセスにデバッガーをアタッチします</span><span class="sxs-lookup"><span data-stu-id="8ef87-221">**Attach** - Attach the debugger to a running PowerShell Host Process</span></span>

<span data-ttu-id="8ef87-222">結果として、Visual Studio Code によってワークスペース フォルダーのルートにディレクトリとファイル `.vscode\launch.json` が作成されます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-222">The result is that Visual Studio Code creates a directory and a file `.vscode\launch.json` in the root of your workspace folder.</span></span> <span data-ttu-id="8ef87-223">この場所にデバッグ構成が格納されます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-223">This location is where your debug configuration is stored.</span></span> <span data-ttu-id="8ef87-224">ファイルが Git リポジトリにある場合は、通常、`launch.json` ファイルをコミットすることになるでしょう。</span><span class="sxs-lookup"><span data-stu-id="8ef87-224">If your files are in a Git repository, you typically want to commit the `launch.json` file.</span></span> <span data-ttu-id="8ef87-225">`launch.json` ファイルの内容:</span><span class="sxs-lookup"><span data-stu-id="8ef87-225">The contents of the `launch.json` file are:</span></span>

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

<span data-ttu-id="8ef87-226">このファイルは一般的なデバッグ シナリオです。</span><span class="sxs-lookup"><span data-stu-id="8ef87-226">This file represents the common debug scenarios.</span></span> <span data-ttu-id="8ef87-227">エディターでこのファイルを開いた場合、 **[構成の追加]** ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-227">When you open this file in the editor, you see an **Add Configuration...** button.</span></span> <span data-ttu-id="8ef87-228">このボタンをクリックすることで、PowerShell デバッグ構成をさらに追加できます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-228">You can click this button to add more PowerShell debug configurations.</span></span> <span data-ttu-id="8ef87-229">追加すると便利な構成の 1 つは、 **[PowerShell: Launch Script]\(PowerShell: 起動スクリプト\)** です。</span><span class="sxs-lookup"><span data-stu-id="8ef87-229">One useful configuration to add is **PowerShell: Launch Script**.</span></span> <span data-ttu-id="8ef87-230">この構成では、エディターで現在どのファイルがアクティブであるかに関係なく、<kbd>F5</kbd> キーを押すと起動されるファイルを、オプションの引数と共に指定できます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-230">With this configuration, you can specify a file with optional arguments that should be launched whenever you press <kbd>F5</kbd> no matter which file is currently active in the editor.</span></span>

<span data-ttu-id="8ef87-231">デバッグ構成が確立されたら、デバッグ セッション中に使用する構成を選択できます。</span><span class="sxs-lookup"><span data-stu-id="8ef87-231">After the debug configuration is established, you can select which configuration you want to use during a debug session.</span></span> <span data-ttu-id="8ef87-232">**[デバッグ]** ビューのツール バーでデバッグ構成ドロップダウンから構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-232">Select a configuration from the debug configuration drop-down in the **Debug** view's toolbar.</span></span>

## <a name="useful-resources"></a><span data-ttu-id="8ef87-233">有用なリソース</span><span class="sxs-lookup"><span data-stu-id="8ef87-233">Useful resources</span></span>

<span data-ttu-id="8ef87-234">Visual Studio Code 用の PowerShell 拡張機能の使用を開始するのに役立つビデオとブログ記事を、次にいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="8ef87-234">There are a few videos and blog posts that may be helpful to get you started using the PowerShell extension for Visual Studio Code:</span></span>

### <a name="videos"></a><span data-ttu-id="8ef87-235">ビデオ</span><span class="sxs-lookup"><span data-stu-id="8ef87-235">Videos</span></span>

- [<span data-ttu-id="8ef87-236">既定の PowerShell エディターとして Visual Studio Code を使用する</span><span class="sxs-lookup"><span data-stu-id="8ef87-236">Using Visual Studio Code as Your Default PowerShell Editor</span></span>](https://youtu.be/bGn45vIeAMM)
- [<span data-ttu-id="8ef87-237">Visual Studio Code: PowerShell スクリプトのデバッグの詳細</span><span class="sxs-lookup"><span data-stu-id="8ef87-237">Visual Studio Code: deep dive into debugging your PowerShell scripts</span></span>](https://youtu.be/cSbIXmlkr8o)

### <a name="blog-posts"></a><span data-ttu-id="8ef87-238">ブログ記事</span><span class="sxs-lookup"><span data-stu-id="8ef87-238">Blog posts</span></span>

- <span data-ttu-id="8ef87-239">[PowerShell の拡張機能][ps-extension]</span><span class="sxs-lookup"><span data-stu-id="8ef87-239">[PowerShell Extension][ps-extension]</span></span>
- <span data-ttu-id="8ef87-240">[Visual Studio Code での PowerShell スクリプトの記述およびデバッグ][debug]</span><span class="sxs-lookup"><span data-stu-id="8ef87-240">[Write and debug PowerShell scripts in Visual Studio Code][debug]</span></span>
- <span data-ttu-id="8ef87-241">[Visual Studio Code でのデバッグのガイダンス][vscode-guide]</span><span class="sxs-lookup"><span data-stu-id="8ef87-241">[Debugging Visual Studio Code Guidance][vscode-guide]</span></span>
- <span data-ttu-id="8ef87-242">[Visual Studio Code での PowerShell のデバッグ][ps-vscode]</span><span class="sxs-lookup"><span data-stu-id="8ef87-242">[Debugging PowerShell in Visual Studio Code][ps-vscode]</span></span>
- <span data-ttu-id="8ef87-243">[Visual Studio Code での PowerShell 開発の概要][getting-started]</span><span class="sxs-lookup"><span data-stu-id="8ef87-243">[Get started with PowerShell development in Visual Studio Code][getting-started]</span></span>
- <span data-ttu-id="8ef87-244">[PowerShell 開発のための Visual Studio Code の編集機能 – パート 1][editing-part1]</span><span class="sxs-lookup"><span data-stu-id="8ef87-244">[Visual Studio Code editing features for PowerShell development – Part 1][editing-part1]</span></span>
- <span data-ttu-id="8ef87-245">[PowerShell 開発のための Visual Studio Code の編集機能 – パート 2][editing-part2]</span><span class="sxs-lookup"><span data-stu-id="8ef87-245">[Visual Studio Code editing features for PowerShell development – Part 2][editing-part2]</span></span>
- <span data-ttu-id="8ef87-246">[Visual Studio Code での PowerShell スクリプトのデバッグ – パート 1][debugging-part1]</span><span class="sxs-lookup"><span data-stu-id="8ef87-246">[Debugging PowerShell script in Visual Studio Code – Part 1][debugging-part1]</span></span>
- <span data-ttu-id="8ef87-247">[Visual Studio Code での PowerShell スクリプトのデバッグ – パート 2][debugging-part2]</span><span class="sxs-lookup"><span data-stu-id="8ef87-247">[Debugging PowerShell script in Visual Studio Code – Part 2][debugging-part2]</span></span>

## <a name="powershell-extension-for-visual-studio-code"></a><span data-ttu-id="8ef87-248">Visual Studio Code 用 PowerShell 拡張機能</span><span class="sxs-lookup"><span data-stu-id="8ef87-248">PowerShell extension for Visual Studio Code</span></span>

<span data-ttu-id="8ef87-249">PowerShell の拡張機能のソース コードは、[GitHub](https://github.com/PowerShell/vscode-powershell) にあります。</span><span class="sxs-lookup"><span data-stu-id="8ef87-249">The PowerShell extension's source code can be found on [GitHub](https://github.com/PowerShell/vscode-powershell).</span></span>

<span data-ttu-id="8ef87-250">共同作成に興味をお持ちの場合は、ぜひ pull request をご活用ください。</span><span class="sxs-lookup"><span data-stu-id="8ef87-250">If you're interested in contributing, Pull Request are greatly appreciated.</span></span> <span data-ttu-id="8ef87-251">[GitHub 上の 開発者向けドキュメント](https://github.com/PowerShell/vscode-powershell/blob/master/docs/development.md)を参照して、作業を開始してください。</span><span class="sxs-lookup"><span data-stu-id="8ef87-251">Follow along with the [developer documentation on GitHub](https://github.com/PowerShell/vscode-powershell/blob/master/docs/development.md) to get started.</span></span>

## <a name="troubleshooting-the-powershell-extension-for-visual-studio-code"></a><span data-ttu-id="8ef87-252">Visual Studio Code 用 PowerShell 拡張機能のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="8ef87-252">Troubleshooting the PowerShell extension for Visual Studio Code</span></span>

<span data-ttu-id="8ef87-253">PowerShell スクリプト開発のための Visual Studio Code の使用に関して問題が発生した場合は、[GitHub 上のトラブルシューティング ガイド](https://github.com/PowerShell/vscode-powershell/blob/master/docs/troubleshooting.md)を参照してください</span><span class="sxs-lookup"><span data-stu-id="8ef87-253">If you experience any issues using Visual Studio Code for PowerShell script development, please take a look at the [troubleshooting guide on GitHub](https://github.com/PowerShell/vscode-powershell/blob/master/docs/troubleshooting.md)</span></span>

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
