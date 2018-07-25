# <a name="using-visual-studio-code-for-powershell-development"></a><span data-ttu-id="0a5b8-101">PowerShell 開発のための Visual Studio Code の使用</span><span class="sxs-lookup"><span data-stu-id="0a5b8-101">Using Visual Studio Code for PowerShell Development</span></span>

<span data-ttu-id="0a5b8-102">Visual Studio Code は、[PowerShell ISE] に加え[ise]、PowerShell でも十分にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-102">In addition to the [PowerShell ISE][ise], PowerShell is also well-supported in Visual Studio Code.</span></span>
<span data-ttu-id="0a5b8-103">さらに、PowerShell Core で ISE はサポートされていませんが、Visual Studio Code はすべてのプラットフォーム (Windows、macOS、および Linux) の PowerShell Core でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-103">Furthermore, the ISE is not supported with PowerShell Core, while Visual Studio Code is supported for PowerShell Core on all platforms (Windows, macOS, and Linux)</span></span>

<span data-ttu-id="0a5b8-104">Windows で Visual Studio Code を使用する場合、Windows 10 を使用して PowerShell バージョン 5 を使用するか、ダウンレベルの (Windows 8.1 などの) Windows OS に、[Windows Management Framework 5.0 RTM](https://www.microsoft.com/en-us/download/details.aspx?id=50395) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-104">You can use Visual Studio Code on Windows with PowerShell version 5 by using Windows 10 or by installing [Windows Management Framework 5.0 RTM](https://www.microsoft.com/en-us/download/details.aspx?id=50395) for down-level Windows OSs (e.g. Windows 8.1, etc.).</span></span>

<span data-ttu-id="0a5b8-105">開始する前に、システムに PowerShell があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-105">Before starting it, please make sure PowerShell exists on your system.</span></span>
<span data-ttu-id="0a5b8-106">Windows、macOS、および Linux 上の最近のワークロードに対しては、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-106">For modern workloads on Windows, macOS, and Linux, see:</span></span>

- <span data-ttu-id="0a5b8-107">[Linux への PowerShell Core のインストール][install-pscore-linux]</span><span class="sxs-lookup"><span data-stu-id="0a5b8-107">[Installing PowerShell Core on Linux][install-pscore-linux]</span></span>
- <span data-ttu-id="0a5b8-108">[macOS への PowerShell Core のインストール][install-pscore-macos]</span><span class="sxs-lookup"><span data-stu-id="0a5b8-108">[Installing PowerShell Core on macOS][install-pscore-macos]</span></span>
- <span data-ttu-id="0a5b8-109">[Windows への PowerShell Core のインストール][install-pscore-windows]</span><span class="sxs-lookup"><span data-stu-id="0a5b8-109">[Installing PowerShell Core on Windows][install-pscore-windows]</span></span>

<span data-ttu-id="0a5b8-110">従来の Windows PowerShell ワークロードに対しては、「[Windows PowerShell のインストール][install-winps]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-110">For traditional Windows PowerShell workloads, see [Installing Windows PowerShell][install-winps].</span></span>

## <a name="editing-with-visual-studio-code"></a><span data-ttu-id="0a5b8-111">Visual Studio Code を使用した編集</span><span class="sxs-lookup"><span data-stu-id="0a5b8-111">Editing with Visual Studio Code</span></span>

### <a name="1-installing-visual-studio-codehttpscodevisualstudiocomdocssetupsetup-overview"></a>[<span data-ttu-id="0a5b8-112">1.Visual Studio Code のインストール</span><span class="sxs-lookup"><span data-stu-id="0a5b8-112">1. Installing Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/setup/setup-overview)

- <span data-ttu-id="0a5b8-113">**Linux**: 「[Running VS Code on Linux](https://code.visualstudio.com/docs/setup/linux)」 (Linux 上での VS コードの実行) ページのインストール手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-113">**Linux**: follow the installation instructions on the [Running VS Code on Linux](https://code.visualstudio.com/docs/setup/linux) page</span></span>

- <span data-ttu-id="0a5b8-114">**macOS**: 「[Running VS Code on macOS](https://code.visualstudio.com/docs/setup/mac)」 (macOS 上での VS コードの実行) ページのインストール手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-114">**macOS**: follow the installation instructions on the [Running VS Code on macOS](https://code.visualstudio.com/docs/setup/mac) page</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="0a5b8-115">macOS で、PowerShell の拡張機能用が正常に動作するには、OpenSSL をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-115">On macOS, you must install OpenSSL for the PowerShell extension to work correctly.</span></span>
  > <span data-ttu-id="0a5b8-116">これには、[Homebrew](http://brew.sh/) をインストールして、`brew install openssl` を実行するのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-116">The easiest way to accomplish this is to install [Homebrew](http://brew.sh/) and then run `brew install openssl`.</span></span>
  > <span data-ttu-id="0a5b8-117">これで、VS Code を使用して PowerShell 拡張機能を正常に読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-117">VS Code can now load the the PowerShell extension successfully.</span></span>

- <span data-ttu-id="0a5b8-118">**Windows**: 「[Running VS Code on Windows](https://code.visualstudio.com/docs/setup/windows)」 (Windows 上での VS コードの実行) ページのインストール手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-118">**Windows**: follow the installation instructions on the [Running VS Code on Windows](https://code.visualstudio.com/docs/setup/windows) page</span></span>

### <a name="2-installing-powershell-extension"></a><span data-ttu-id="0a5b8-119">2.PowerShell 拡張機能のインストール</span><span class="sxs-lookup"><span data-stu-id="0a5b8-119">2. Installing PowerShell Extension</span></span>

- <span data-ttu-id="0a5b8-120">Visual Studio Code アプリを次のように起動します。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-120">Launch the Visual Studio Code app by:</span></span>
  - <span data-ttu-id="0a5b8-121">**Windows**: PowerShell セッションで `code` と入力します。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-121">**Windows**: typing `code` in your PowerShell session</span></span>
  - <span data-ttu-id="0a5b8-122">**Linux**: ターミナルで `code` と入力します。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-122">**Linux**: typing `code` in your terminal</span></span>
  - <span data-ttu-id="0a5b8-123">**macOS**: ターミナルで `code` と入力します。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-123">**macOS**: typing `code` in your terminal</span></span>

- <span data-ttu-id="0a5b8-124">**CTRL + P** (Mac 上では、**Cmd + P**) を押して、**Quick Open** を起動します。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-124">Launch **Quick Open** by pressing **Ctrl+P** (**Cmd+P** on Mac).</span></span>
- <span data-ttu-id="0a5b8-125">Quick Open で `ext install powershell` と入力し、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-125">In Quick Open, type `ext install powershell` and hit **Enter**.</span></span>
- <span data-ttu-id="0a5b8-126">サイド バーに **[拡張機能]** ビューが開きます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-126">The **Extensions** view opens on the Side Bar.</span></span> <span data-ttu-id="0a5b8-127">Microsoft の PowerShell の拡張機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-127">Select the PowerShell extension from Microsoft.</span></span>
  <span data-ttu-id="0a5b8-128">次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-128">You should see something like below:</span></span>

  ![VSCode](../../images/vscode.png)

- <span data-ttu-id="0a5b8-130">Microsoft の PowerShell 拡張機能の、**[インストール]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-130">Click the **Install** button on the PowerShell extension from Microsoft.</span></span>
- <span data-ttu-id="0a5b8-131">インストール後、**[インストール]** ボタンは **[再読み込み]** に変わります。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-131">After the install, you see the **Install** button turns to **Reload**.</span></span>
  <span data-ttu-id="0a5b8-132">**[再読み込み]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-132">Click on **Reload**.</span></span>
- <span data-ttu-id="0a5b8-133">Visual Studio Code が再読み込みされたら、編集が可能になります。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-133">After Visual Studio Code has reload, you are ready for editing.</span></span>

<span data-ttu-id="0a5b8-134">たとえば、新しいファイルを作成するには、**[ファイル]、[新規]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-134">For example, to create a new file, click **File->New**.</span></span>
<span data-ttu-id="0a5b8-135">保存するには、**[ファイル]、[保存]** の順にクリックし、`HelloWorld.ps1` などのファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-135">To save it, click **File->Save** and then provide a file name, let's say `HelloWorld.ps1`.</span></span>
<span data-ttu-id="0a5b8-136">ファイルを閉じるには、ファイル名の横の "x" をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-136">To close the file, click on "x" next to the file name.</span></span>
<span data-ttu-id="0a5b8-137">**[ファイル]、[終了]** の順にクリックし、Visual Studio Code を終了します。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-137">To exit Visual Studio Code, **File->Exit**.</span></span>

#### <a name="using-a-specific-installed-version-of-powershell"></a><span data-ttu-id="0a5b8-138">PowerShell の特定のインストール バージョンの使用</span><span class="sxs-lookup"><span data-stu-id="0a5b8-138">Using a specific installed version of PowerShell</span></span>

<span data-ttu-id="0a5b8-139">Visual Studio Code で PowerShell の特定のインストール バージョンを使用する場合、ユーザー設定ファイルに新しい変数を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-139">If you wish to use a specific installation of PowerShell with Visual Studio Code, you need to add a new variable to your user settings file.</span></span>

1. <span data-ttu-id="0a5b8-140">**[ファイル]、[基本設定]、[設定]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-140">Click **File -> Preferences -> Settings**</span></span>
1. <span data-ttu-id="0a5b8-141">2 つのエディター ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-141">Two editor panes appear.</span></span>
   <span data-ttu-id="0a5b8-142">一番右側のウィンドウの (`settings.json`)、2 つの中かっこ (`{` と `}`) の間のどこかに、OS に適した以下の設定を追加し、**\<バージョン\>** をインストール済みの PowerShell のバージョンに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-142">In the right-most pane (`settings.json`), insert the setting below appropriate for your OS somewhere between the two curly brackets (`{` and `}`) and replace **\<version\>** with the installed PowerShell version:</span></span>

   ```json
    // On Windows:
    "powershell.powerShellExePath": "c:/Program Files/PowerShell/<version>/pwsh.exe"

    // On Linux:
    "powershell.powerShellExePath": "/opt/microsoft/powershell/<version>/pwsh"

    // On macOS:
    "powershell.powerShellExePath": "/usr/local/microsoft/powershell/<version>/pwsh"
   ```

1. <span data-ttu-id="0a5b8-143">設定を希望の PowerShell の実行可能ファイルへのパスに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-143">Replace the setting with the path to the desired PowerShell executable</span></span>
1. <span data-ttu-id="0a5b8-144">設定ファイルを保存し、Visual Studio Code を再起動します。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-144">Save the settings file and restart Visual Studio Code</span></span>

#### <a name="configuration-settings-for-visual-studio-code"></a><span data-ttu-id="0a5b8-145">Visual Studio Code の構成設定</span><span class="sxs-lookup"><span data-stu-id="0a5b8-145">Configuration settings for Visual Studio Code</span></span>

<span data-ttu-id="0a5b8-146">前段の手順を使用して、`settings.json` に構成設定を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-146">By using the steps in the previous paragraph you can add configuration settings in `settings.json`.</span></span>

<span data-ttu-id="0a5b8-147">Visual Studio Code には、次の構成設定をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-147">We recommend the following configuration settings for Visual Studio Code:</span></span>

```json
{
    "csharp.suppressDotnetRestoreNotification": true,
    "editor.renderWhitespace": "all",
    "editor.renderControlCharacters": true,
    "omnisharp.projectLoadTimeout": 120,
    "files.trimTrailingWhitespace": true
}
```

## <a name="debugging-with-visual-studio-code"></a><span data-ttu-id="0a5b8-148">Visual Studio Code を使用したデバッグ</span><span class="sxs-lookup"><span data-stu-id="0a5b8-148">Debugging with Visual Studio Code</span></span>

### <a name="no-workspace-debugging"></a><span data-ttu-id="0a5b8-149">ワークスペースを使用しないデバッグ</span><span class="sxs-lookup"><span data-stu-id="0a5b8-149">No-workspace debugging</span></span>

<span data-ttu-id="0a5b8-150">Visual Studio Code バージョン 1.9 以降では、PowerShell スクリプトを含むフォルダーを開かずに PowerShell スクリプトをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-150">As of Visual Studio Code version 1.9 you can debug PowerShell scripts without having to open the folder containing the PowerShell script.</span></span>
<span data-ttu-id="0a5b8-151">単純に、**[ファイル]、[ファイルを開く]** の順にクリックして PowerShell スクリプト ファイルを開き、行にブレークポイントを設定し (F9 キーを押す)、F5 キーを押してデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-151">Simply open the PowerShell script file with **File->Open File...**, set a breakpoint on a line (press F9) and then press F5 to start debugging.</span></span>
<span data-ttu-id="0a5b8-152">[Debug actions]\(デバッグ アクション\) ウィンドウが表示されます。ここでは、デバッガーを中断したり、デバッグのステップ実行、再開、停止を行ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-152">You should see the Debug actions pane appear which allows you to break into the debugger, step, resume and stop debugging.</span></span>

### <a name="workspace-debugging"></a><span data-ttu-id="0a5b8-153">ワークスペースを使用したデバッグ</span><span class="sxs-lookup"><span data-stu-id="0a5b8-153">Workspace debugging</span></span>

<span data-ttu-id="0a5b8-154">ワークスペースを使用したデバッグとは、**[ファイル]** メニューの **[ファイルを開く]** を使用して Visual Studio Code で開いたフォルダーのコンテキストでデバッグを行うことを言います。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-154">Workspace debugging refers to debugging in the context of a folder that you have opened in Visual Studio Code using **Open Folder...** from the **File** menu.</span></span>
<span data-ttu-id="0a5b8-155">開いたフォルダーは、通常は PowerShell プロジェクトのフォルダーや Git リポジトリのルートです。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-155">The folder you open is typically your PowerShell project folder and/or the root of your Git repository.</span></span>

<span data-ttu-id="0a5b8-156">このモードの場合も、単純に F5 キーを押せば、現在選択されている PowerShell スクリプトのデバッグを開始できます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-156">Even in this mode, you can start debugging the currently selected PowerShell script by simply pressing F5.</span></span>
<span data-ttu-id="0a5b8-157">ただし、ワークスペースを使用したデバッグでは、現在開いているファイルをデバッグする以外に、複数のデバッグ構成を定義できます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-157">However, workspace debugging allows you to define multiple debug configurations other than just debugging the currently open file.</span></span>
<span data-ttu-id="0a5b8-158">たとえば、次に構成を追加できます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-158">For instance, you can add a configurations to:</span></span>

- <span data-ttu-id="0a5b8-159">デバッガーでの Pester テストの起動</span><span class="sxs-lookup"><span data-stu-id="0a5b8-159">Launch Pester tests in the debugger</span></span>
- <span data-ttu-id="0a5b8-160">デバッガーでの引数を使用した特定のファイルの起動</span><span class="sxs-lookup"><span data-stu-id="0a5b8-160">Launch a specific file with arguments in the debugger</span></span>
- <span data-ttu-id="0a5b8-161">デバッガーでの対話型セッションの起動</span><span class="sxs-lookup"><span data-stu-id="0a5b8-161">Launch an interactive session in the debugger</span></span>
- <span data-ttu-id="0a5b8-162">PowerShell ホスト手順へのデバッガーのアタッチ</span><span class="sxs-lookup"><span data-stu-id="0a5b8-162">Attach the debugger to a PowerShell host process</span></span>

  <span data-ttu-id="0a5b8-163">デバッグ用の構成ファイルを作成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-163">Follow these steps to create your debug configuration file:</span></span>

  1. <span data-ttu-id="0a5b8-164">**Ctrl + Shift + D** (Mac の場合は **Cmd + Shift + D**) と押して、**[デバッグ]** ビューを開きます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-164">Open the **Debug** view by pressing **Ctrl+Shift+D** (**Cmd+Shift+D** on Mac).</span></span>
  2. <span data-ttu-id="0a5b8-165">ツールバーの **[構成]** 歯車アイコンキーを押します。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-165">Press the **Configure** gear icon in the toolbar.</span></span>
  3. <span data-ttu-id="0a5b8-166">Visual Studio Code により、**[環境の選択]** が求められます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-166">Visual Studio Code prompts you to **Select Environment**.</span></span>
  <span data-ttu-id="0a5b8-167">**[PowerShell]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-167">Choose **PowerShell**.</span></span>

  <span data-ttu-id="0a5b8-168">これを行うときに、Visual Studio Code によってワークスペース フォルダーのルートに、".vscode\launch.json" のディレクトリとファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-168">When you do this, Visual Studio Code creates a directory and a file ".vscode\launch.json" in the root of your workspace folder.</span></span>
  <span data-ttu-id="0a5b8-169">ここにデバッグ構成が格納されます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-169">This is where your debug configuration is stored.</span></span> <span data-ttu-id="0a5b8-170">ファイルが Git リポジトリにある場合は、通常は launch.json ファイルをコミットしたいでしょう。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-170">If your files are in a Git repository, you typically want to commit the launch.json file.</span></span>
  <span data-ttu-id="0a5b8-171">launch.json ファイルの内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-171">The contents of the launch.json file are:</span></span>

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

  <span data-ttu-id="0a5b8-172">これが、一般的なデバッグ シナリオです。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-172">This represents the common debug scenarios.</span></span>
  <span data-ttu-id="0a5b8-173">ただし、エディターでこのファイルを開いた場合、**[構成の追加]** ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-173">However, when you open this file in the editor, you see an **Add Configuration...** button.</span></span>
  <span data-ttu-id="0a5b8-174">さらに PowerShell デバッグ構成を追加するには、このボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-174">You can press this button to add more PowerShell debug configurations.</span></span> <span data-ttu-id="0a5b8-175">**[PowerShell: Launch Script]\(PowerShell: スクリプトの起動\)** の構成を追加すると便利です。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-175">One handy configuration to add is **PowerShell: Launch Script**.</span></span>
  <span data-ttu-id="0a5b8-176">この構成では、エディターで現在どのファイルがアクティブであるかに関係なく、F5 キーを押すと起動される特定のファイルを、オプションの引数とともに指定できます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-176">With this configuration, you can specify a specific file with optional arguments that should be launched whenever you press F5 no matter which file is currently active in the editor.</span></span>

  <span data-ttu-id="0a5b8-177">デバッグ構成が確立されると、**[デバッグ]** ビューのツールバーのデバッグ構成ドロップダウンから、デバッグ セッションで使用する構成を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-177">Once the debug configuration is established, you can select which configuration you want to use during a debug session by selecting one from the debug configuration drop-down in the **Debug** view's toolbar.</span></span>

  <span data-ttu-id="0a5b8-178">Visual Studio Code 用の PowerShell の拡張機能を使用開始するのに便利なブログを、次にいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-178">There are a few blogs that may be helpful to get you started using PowerShell extension for Visual Studio Code</span></span>

<span data-ttu-id="0a5b8-179">Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="0a5b8-179">Visual Studio Code:</span></span>

- <span data-ttu-id="0a5b8-180">[PowerShell 拡張機能][ps-extension]</span><span class="sxs-lookup"><span data-stu-id="0a5b8-180">[PowerShell Extension][ps-extension]</span></span>
- <span data-ttu-id="0a5b8-181">[Visual Studio Code での PowerShell スクリプトの記述およびデバッグ][debug]</span><span class="sxs-lookup"><span data-stu-id="0a5b8-181">[Write and debug PowerShell scripts in Visual Studio Code][debug]</span></span>
- <span data-ttu-id="0a5b8-182">[Visual Studio Code でのデバッグのガイダンス][vscode-guide]</span><span class="sxs-lookup"><span data-stu-id="0a5b8-182">[Debugging Visual Studio Code Guidance][vscode-guide]</span></span>
- <span data-ttu-id="0a5b8-183">[Visual Studio Code での PowerShell のデバッグ][ps-vscode]</span><span class="sxs-lookup"><span data-stu-id="0a5b8-183">[Debugging PowerShell in Visual Studio Code][ps-vscode]</span></span>
- <span data-ttu-id="0a5b8-184">[Visual Studio Code での PowerShell 開発の概要][getting-started]</span><span class="sxs-lookup"><span data-stu-id="0a5b8-184">[Get started with PowerShell development in Visual Studio Code][getting-started]</span></span>
- <span data-ttu-id="0a5b8-185">[PowerShell 開発のための Visual Studio Code の編集機能 – パート 1][editing-part1]</span><span class="sxs-lookup"><span data-stu-id="0a5b8-185">[Visual Studio Code editing features for PowerShell development – Part 1][editing-part1]</span></span>
- <span data-ttu-id="0a5b8-186">[PowerShell 開発のための Visual Studio Code の編集機能 – パート 2][editing-part2]</span><span class="sxs-lookup"><span data-stu-id="0a5b8-186">[Visual Studio Code editing features for PowerShell development – Part 2][editing-part2]</span></span>
- <span data-ttu-id="0a5b8-187">[Visual Studio Code での PowerShell スクリプトのデバッグ – パート 1][debugging-part1]</span><span class="sxs-lookup"><span data-stu-id="0a5b8-187">[Debugging PowerShell script in Visual Studio Code – Part 1][debugging-part1]</span></span>
- <span data-ttu-id="0a5b8-188">[Visual Studio Code での PowerShell スクリプトのデバッグ – パート 2][debugging-part2]</span><span class="sxs-lookup"><span data-stu-id="0a5b8-188">[Debugging PowerShell script in Visual Studio Code – Part 2][debugging-part2]</span></span>

[ise]: ../ise-guide.md
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

## <a name="powershell-extension-for-visual-studio-code"></a><span data-ttu-id="0a5b8-189">Visual Studio Code 用の PowerShell Extension の拡張機能</span><span class="sxs-lookup"><span data-stu-id="0a5b8-189">PowerShell Extension for Visual Studio Code</span></span>

<span data-ttu-id="0a5b8-190">PowerShell の拡張機能のソース コードは、[GitHub](https://github.com/PowerShell/vscode-powershell) にあります。</span><span class="sxs-lookup"><span data-stu-id="0a5b8-190">The PowerShell extension's source code can be found on [GitHub](https://github.com/PowerShell/vscode-powershell).</span></span>