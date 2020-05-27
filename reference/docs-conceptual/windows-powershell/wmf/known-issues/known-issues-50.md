---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
title: WMF 5.0 の既知の問題
ms.openlocfilehash: 1db656884736c742ef78354b7452879e319d4a0a
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809088"
---
# <a name="known-issues-in-wmf-50"></a><span data-ttu-id="7b8d8-103">WMF 5.0 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="7b8d8-103">Known Issues in WMF 5.0</span></span>

## <a name="powershell-shortcuts-are-broken-when-used-for-the-first-time"></a><span data-ttu-id="7b8d8-104">初回使用時に PowerShell のショートカットが壊れている</span><span class="sxs-lookup"><span data-stu-id="7b8d8-104">PowerShell Shortcuts are broken when used for the first time</span></span>

<span data-ttu-id="7b8d8-105">**解決策:** 次の操作のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-105">**Resolution:** Perform one of the following actions:</span></span>

1. <span data-ttu-id="7b8d8-106">PowerShell のショートカットを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-106">Right click on the PowerShell shortcut.</span></span> <span data-ttu-id="7b8d8-107">[Windows PowerShell] を選択し、管理者特権以外のモードで起動します。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-107">Select "Windows PowerShell" to launch in a non-elevated mode.</span></span>
2. <span data-ttu-id="7b8d8-108">PowerShell のショートカットを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-108">Right click on the PowerShell shortcut.</span></span> <span data-ttu-id="7b8d8-109">[Windows PowerShell] を右クリックし、[管理者として実行] を選択して管理者特権モードで起動します。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-109">Right click on "Windows PowerShell" and select "Run As Administrator" to launch in an elevated mode.</span></span>

<span data-ttu-id="7b8d8-110">上記の操作のいずれかを実行すると、PowerShell のショートカットが機能します。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-110">Once you have performed either of the above actions, the PowerShell shortcuts will work.</span></span> <span data-ttu-id="7b8d8-111">これらの操作は、一度だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-111">These actions need to be performed only once.</span></span>

## <a name="powershell-modules-and-dsc-resources-report-errors-about-executionpolicy-on-windows-7"></a><span data-ttu-id="7b8d8-112">Windows 7 で PowerShell モジュールと DSC リソースにより ExecutionPolicy についてエラーがレポートされる</span><span class="sxs-lookup"><span data-stu-id="7b8d8-112">PowerShell Modules and DSC Resources report errors about ExecutionPolicy on Windows 7</span></span>

<span data-ttu-id="7b8d8-113">Windows 7 で PowerShell モジュールと DSC リソースを使用すると、ExecutionPolicy のエラーが通知される場合があります。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-113">On Windows 7, using PowerShell modules and DSC resources may result in errors reported about ExecutionPolicy.</span></span>

<span data-ttu-id="7b8d8-114">**解決策:** 管理者特権の PowerShell セッション (管理者として実行) で、次のコマンドを実行して ExecutionPolicy を **RemoteSigned** に設定します。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-114">**Resolution:** Set the ExecutionPolicy to **RemoteSigned** by running the following command in an elevated PowerShell session (Run as Administrator):</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="connecting-to-an-old-remote-exchange-endpoint-causes-a-crash"></a><span data-ttu-id="7b8d8-115">古いリモート Exchange のエンドポイントに接続するとクラッシュが発生する</span><span class="sxs-lookup"><span data-stu-id="7b8d8-115">Connecting to an old remote Exchange endpoint causes a crash</span></span>

<span data-ttu-id="7b8d8-116">古い Exchange のエンドポイントは、新しいエンドポイントにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-116">The old Exchange endpoint redirects to a new endpoint.</span></span> <span data-ttu-id="7b8d8-117">リダイレクト ロジックに含まれたバグにより、クラッシュが発生します。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-117">There is a bug in the redirection logic that results in a crash.</span></span>

<span data-ttu-id="7b8d8-118">**解決策:** 新しいエンドポイントに直接接続します。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-118">**Resolution:** Connect directly to the new endpoint.</span></span>

## <a name="software-inventory-logging-feature-is-erroneously-stopped-after-wmf-50-installation-on-windows-server-2012-r2"></a><span data-ttu-id="7b8d8-119">Windows Server 2012 R2 に WMF 5.0 をインストールした後、ソフトウェア インベントリ ログ機能が誤って停止される</span><span class="sxs-lookup"><span data-stu-id="7b8d8-119">Software Inventory Logging feature is erroneously stopped after WMF 5.0 installation on Windows Server 2012 R2</span></span>

<span data-ttu-id="7b8d8-120">SIL を既に実行している Windows Server 2012 R2 に WMF 5.0 をインストールする場合、インストール後ソフトウェア インベントリ ログ機能が誤って停止されます。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-120">When installing WMF 5.0 on a Windows Server 2012 R2 that is already running SIL, the Software Inventory Logging feature is erroneously stopped after installation.</span></span>

<span data-ttu-id="7b8d8-121">**解決策:** インストール プロセスでソフトウェア インベントリ ログ機能が誤って停止されるため、WMF のインストール後に `Start-SilLogging` コマンドレットを 1 回実行します。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-121">**Resolution:** Run the `Start-SilLogging` cmdlet once after the WMF installation, as the installation process will errantly stop the Software Inventory Logging feature.</span></span>

## <a name="get-childitem-does-not-work-if--literalpath-and--recurse-are-used-together"></a><span data-ttu-id="7b8d8-122">-LiteralPath と -Recurse を一緒に使用すると `Get-ChildItem` が機能しない</span><span class="sxs-lookup"><span data-stu-id="7b8d8-122">`Get-ChildItem` does not work if -LiteralPath and -Recurse are used together</span></span>

<span data-ttu-id="7b8d8-123">ディレクトリ名に無効なワイルドカードが含まれている場合、-LiteralPath と -Recurse を一緒に使用すると、`Get-ChildItem` によって期待どおりの結果が生成されません。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-123">If a directory name contains an invalid wildcard character, then `Get-ChildItem` will not produce expected results when both -LiteralPath and -Recurse are used together.</span></span>

<span data-ttu-id="7b8d8-124">**解決策:** 理想的ではありませんが、現在の対応策では、コマンドレットに依存するのではなく、スクリプトに再帰を実装します。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-124">**Resolution:** Not ideal, but current workaround is to implement recursion in the script rather than rely on the cmdlet.</span></span>

## <a name="sysprep-fails-after-wmf-50-installation"></a><span data-ttu-id="7b8d8-125">WMF 5.0 のインストール後に Sysprep が失敗する</span><span class="sxs-lookup"><span data-stu-id="7b8d8-125">Sysprep fails after WMF 5.0 installation</span></span>

<span data-ttu-id="7b8d8-126">実行中の Windows Server のバージョンによって、この問題の解決策は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-126">There are two workarounds for this issue depending on the version of Windows Server you are running.</span></span>

<span data-ttu-id="7b8d8-127">**解決策:**</span><span class="sxs-lookup"><span data-stu-id="7b8d8-127">**Resolution:**</span></span>

- <span data-ttu-id="7b8d8-128">**Windows Server 2008 R2** を実行するシステムの場合</span><span class="sxs-lookup"><span data-stu-id="7b8d8-128">For systems running **Windows Server 2008 R2**</span></span>
  1. <span data-ttu-id="7b8d8-129">管理者として PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-129">Open PowerShell as an administrator</span></span>
  2. <span data-ttu-id="7b8d8-130">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-130">Run the following command</span></span>

     ```powershell
     Set-SilLogging -TargetUri https://BlankTarget -CertificateThumbprint 0123456789
     ```

  3. <span data-ttu-id="7b8d8-131">予想されるとおりにコマンドを実行してエラーを無視します。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-131">Run the command and ignore the error, as they are expected.</span></span>

     ```powershell
     Publish-SilData
     ```

  4. <span data-ttu-id="7b8d8-132">\Windows\System32\Logfiles\SIL\ ディレクトリ内のファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-132">Delete the files in  \Windows\System32\Logfiles\SIL\ directory</span></span>

     ```powershell
     Remove-Item -Recurse $env:SystemRoot\System32\Logfiles\SIL\
     ```

  5. <span data-ttu-id="7b8d8-133">使用可能な重要な Windows 更新プログラムをすべてをインストールし、通常どおりに Sysyprep の操作を開始します。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-133">Install all available important Windows Updates, and begin Sysyprep operation normally.</span></span>

- <span data-ttu-id="7b8d8-134">**Windows Server 2012** を実行するシステムの場合</span><span class="sxs-lookup"><span data-stu-id="7b8d8-134">For systems running **Windows Server 2012**</span></span>
  1. <span data-ttu-id="7b8d8-135">Sysprep されるようにサーバーに WMF 5.0 をインストールした後、管理者としてログインします。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-135">After installing WMF 5.0 on the server to be Sysprep'd, login as administrator.</span></span>
  2. <span data-ttu-id="7b8d8-136">`\Windows\System32\Sysprep\ActionFiles\` ディレクトリから Windows ディレクトリ以外の場所 (例: `C:\`) に Generize.xml をコピーします。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-136">Copy Generize.xml from directory `\Windows\System32\Sysprep\ActionFiles\` to a location outside of the Windows directory, `C:\` for example.</span></span>
  3. <span data-ttu-id="7b8d8-137">メモ帳で Generalize.xml のコピーを開きます。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-137">Open your Generalize.xml copy with notepad.</span></span>
  4. <span data-ttu-id="7b8d8-138">次のテキストを検索して削除します。テキストごとに 1 つのインスタンスを削除する必要があります (これらはドキュメントの末尾付近にあります)。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-138">Find and remove the following text, one instance of each needs to be deleted (they will be near the end of the document).</span></span>

     ```xml
     <sysprepOrder order="0x3200"></sysprepOrder>
     <sysprepOrder order="0x3300"></sysprepOrder>
     ```

  5. <span data-ttu-id="7b8d8-139">編集した Generalize.xml のコピーを保存してファイルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-139">Save the edited copy of Generalize.xml and close the file.</span></span>
  6. <span data-ttu-id="7b8d8-140">管理者としてコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-140">Open a command prompt as administrator</span></span>
  7. <span data-ttu-id="7b8d8-141">次のコマンドを実行し、System32 フォルダーで Generalize.xml ファイルの所有権を取得します。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-141">Run the following command to take ownership of the Generalize.xml file in system32 folder:</span></span>

     ```powershell
     Takeown /f C:\Windows\System32\Sysprep\ActionFiles\Generalize.xml
     ```

  8. <span data-ttu-id="7b8d8-142">次のコマンドを実行し、ファイルの適切なアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-142">Run the following command to set appropriate permission on the file:</span></span>

     ```powershell
     Cacls C:\Windows\System32\ Sysprep\ActionFiles\Generalize.xml /G `<AdministratorUserName>`:F
     ```

     - <span data-ttu-id="7b8d8-143">確認のプロンプトで [はい] と回答します。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-143">Answer Yes at the prompt for confirmation.</span></span>
     - <span data-ttu-id="7b8d8-144">なお `<AdministratorUserName>` をコンピューター管理者のユーザー名に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-144">Note that `<AdministratorUserName>` should be replaced by the username who is administrator on the machine.</span></span> <span data-ttu-id="7b8d8-145">たとえば、"Administrator" にします。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-145">For example, "Administrator".</span></span>

  9. <span data-ttu-id="7b8d8-146">次のコマンドを使用して、Sysprep ディレクトリに保存した編集済みファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-146">Copy the file you edited and saved over to the Sysprep directory using the following command:</span></span>

     ```powershell
     xcopy C:\Generalize.xml C:\Windows\System32\Sysprep\ActionFiles\Generalize.xml
     ```

     - <span data-ttu-id="7b8d8-147">[はい] と回答して上書きします (上書きの確認メッセージが表示されない場合は、入力されたパスを再確認してください)。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-147">Answer Yes to overwrite (note that if there is no prompt to overwrite, double check the path entered).</span></span>
     - <span data-ttu-id="7b8d8-148">編集した Generalize.xml のコピーは C:\ にコピーされたことを想定しています。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-148">Assumes your edited copy of Generalize.xml was copied to C:\ .</span></span>

  10. <span data-ttu-id="7b8d8-149">この解決策により Generalize.xml が更新されます。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-149">Generalize.xml is now updated with the workaround.</span></span> <span data-ttu-id="7b8d8-150">Sysprep を実行して汎用化オプションを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="7b8d8-150">Please run Sysprep with the generalize option enabled.</span></span>
