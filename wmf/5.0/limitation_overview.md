---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 306241bc5ec854c0e2ed835009a79b21fc249f14
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="known-issues-and-limitations"></a><span data-ttu-id="c29e3-102">既知の問題と制限事項</span><span class="sxs-lookup"><span data-stu-id="c29e3-102">Known Issues and Limitations</span></span>

<a name="powershell-shortcuts-are-broken-when-used-for-the-first-time"></a><span data-ttu-id="c29e3-103">初回使用時に PowerShell のショートカットが壊れている</span><span class="sxs-lookup"><span data-stu-id="c29e3-103">PowerShell Shortcuts are broken when used for the first time</span></span>
------------------------------------------------------------

<span data-ttu-id="c29e3-104">**解決策:** 次の操作のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="c29e3-104">**Resolution:** Perform one of the following actions:</span></span>

1.  <span data-ttu-id="c29e3-105">PowerShell のショートカットを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="c29e3-105">Right click on the PowerShell shortcut.</span></span> <span data-ttu-id="c29e3-106">[Windows PowerShell] を選択し、管理者特権以外のモードで起動します。</span><span class="sxs-lookup"><span data-stu-id="c29e3-106">Select “Windows PowerShell” to launch in a non-elevated mode.</span></span>
2.  <span data-ttu-id="c29e3-107">PowerShell のショートカットを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="c29e3-107">Right click on the PowerShell shortcut.</span></span> <span data-ttu-id="c29e3-108">[Windows PowerShell] を右クリックし、[管理者として実行] を選択して管理者特権モードで起動します。</span><span class="sxs-lookup"><span data-stu-id="c29e3-108">Right click on “Windows PowerShell” and select “Run As Administrator” to launch in an elevated mode.</span></span>

<span data-ttu-id="c29e3-109">上記の操作のいずれかを実行すると、PowerShell のショートカットが機能します。</span><span class="sxs-lookup"><span data-stu-id="c29e3-109">Once you have performed either of the above actions, the PowerShell shortcuts will work.</span></span> <span data-ttu-id="c29e3-110">これらの操作は、一度だけ実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c29e3-110">These actions need to be performed only once.</span></span>


<a name="powershell-modules-and-dsc-resources-report-errors-about-executionpolicy-on-windows-7"></a><span data-ttu-id="c29e3-111">Windows 7 で PowerShell モジュールと DSC リソースにより ExecutionPolicy についてエラーがレポートされる</span><span class="sxs-lookup"><span data-stu-id="c29e3-111">PowerShell Modules and DSC Resources report errors about ExecutionPolicy on Windows 7</span></span>
-------------------------------------------------------------------------------------
<span data-ttu-id="c29e3-112">Windows 7 で PowerShell モジュールと DSC リソースを使用すると、ExecutionPolicy についてレポートされるエラーとなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c29e3-112">On Windows 7, the use of PowerShell modules and DSC resources may result in errors reported about ExecutionPolicy.</span></span>

<span data-ttu-id="c29e3-113">**解決策:** 管理者特権の PowerShell セッション (管理者として実行) で、次のコマンドを実行して ExecutionPolicy を RemoteSigned に設定します。</span><span class="sxs-lookup"><span data-stu-id="c29e3-113">**Resolution:** Set the ExecutionPolicy to RemoteSigned by running the following command in an elevated PowerShell session (Run as Administrator):</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

<a name="connecting-to-an-old-remote-exchange-endpoint-causes-a-crash"></a><span data-ttu-id="c29e3-114">古いリモート Exchange のエンドポイントに接続するとクラッシュが発生する</span><span class="sxs-lookup"><span data-stu-id="c29e3-114">Connecting to an old remote Exchange endpoint causes a crash</span></span>
------------------------------------------------------------

<span data-ttu-id="c29e3-115">古い Exchange のエンドポイントは、新しいエンドポイントにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="c29e3-115">The old Exchange endpoint redirects to a new endpoint.</span></span> <span data-ttu-id="c29e3-116">リダイレクト ロジックに含まれたバグにより、クラッシュが発生します。</span><span class="sxs-lookup"><span data-stu-id="c29e3-116">There is a bug in the redirection logic that results in a crash.</span></span>

<span data-ttu-id="c29e3-117">**解決策:** 新しいエンドポイントに直接接続します。</span><span class="sxs-lookup"><span data-stu-id="c29e3-117">**Resolution:** Connect directly to the new endpoint.</span></span>


<a name="software-inventory-logging-feature-is-erroneously-stopped-after-wmf-50-installation-on-windows-server-2012-r2"></a><span data-ttu-id="c29e3-118">Windows Server 2012 R2 に WMF 5.0 をインストールした後、ソフトウェア インベントリ ログ機能が誤って停止される</span><span class="sxs-lookup"><span data-stu-id="c29e3-118">Software Inventory Logging feature is erroneously stopped after WMF 5.0 installation on Windows Server 2012 R2</span></span>
-------------------------------------------------------------------------------------------------------------

<span data-ttu-id="c29e3-119">SIL を既に実行している Windows Server 2012 R2 に WMF 5.0 をインストールする場合、インストール後ソフトウェア インベントリ ログ機能が誤って停止されます。</span><span class="sxs-lookup"><span data-stu-id="c29e3-119">When installing WMF 5.0 on a Windows Server 2012 R2 that is already running SIL, the Software Inventory Logging feature is erroneously stopped after installation.</span></span>

<span data-ttu-id="c29e3-120">**解決策:** インストール プロセスでソフトウェア インベントリ ログ機能が誤って停止されるため、WMF のインストール後に Start-SilLogging コマンドレットを 1 回実行します。</span><span class="sxs-lookup"><span data-stu-id="c29e3-120">**Resolution:** Run the Start-SilLogging cmdlet once after the WMF installation, as the installation process will errantly stop the Software Inventory Logging feature.</span></span>

<a name="get-childitem-does-not-work-if--literalpath-and--recurse-are-used-together"></a><span data-ttu-id="c29e3-121">-LiteralPath と -Recurse を一緒に使用すると Get-ChildItem が機能しない</span><span class="sxs-lookup"><span data-stu-id="c29e3-121">Get-ChildItem does not work if -LiteralPath and -Recurse are used together</span></span>
--------------------------------------------------------------------------

<span data-ttu-id="c29e3-122">ディレクトリ名に無効なワイルドカードが含まれている場合、-LiteralPath と -Recurse を一緒に使用すると、Get-ChildItem によって期待どおりの結果が生成されません。</span><span class="sxs-lookup"><span data-stu-id="c29e3-122">If a directory name contains an invalid wildcard character, then Get-ChildItem will not produce expected results when both -LiteralPath and -Recurse are used together.</span></span>

<span data-ttu-id="c29e3-123">**解決策:** 理想的ではありませんが、現在の対応策では、コマンドレットに依存するのではなく、スクリプトに再帰を実装します。</span><span class="sxs-lookup"><span data-stu-id="c29e3-123">**Resolution:** Not ideal, but current workaround is to implement recursion in the script rather than rely on the cmdlet.</span></span>


<a name="sysprep-fails-after-wmf-50-installation"></a><span data-ttu-id="c29e3-124">WMF 5.0 のインストール後に Sysprep が失敗する</span><span class="sxs-lookup"><span data-stu-id="c29e3-124">Sysprep fails after WMF 5.0 installation</span></span>
----------------------------------------

<span data-ttu-id="c29e3-125">実行中の Windows Server のバージョンによって、この問題の解決策は 2 つあります。</span><span class="sxs-lookup"><span data-stu-id="c29e3-125">There are two workarounds for this issue depending on the version of Windows Server you are running.</span></span>

<span data-ttu-id="c29e3-126">**解決策:**</span><span class="sxs-lookup"><span data-stu-id="c29e3-126">**Resolution:**</span></span>
- <span data-ttu-id="c29e3-127">**Windows Server 2008 R2** を実行するシステムの場合</span><span class="sxs-lookup"><span data-stu-id="c29e3-127">For systems running **Windows Server 2008 R2**</span></span>
  1. <span data-ttu-id="c29e3-128">管理者として PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="c29e3-128">Open Powershell as an administrator</span></span>
  2. <span data-ttu-id="c29e3-129">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c29e3-129">Run the following command</span></span>

  ```powershell
    Set-SilLogging –TargetUri https://BlankTarget –CertificateThumbprint 0123456789
  ```
  3. <span data-ttu-id="c29e3-130">予想されるとおりにコマンドを実行してエラーを無視します。</span><span class="sxs-lookup"><span data-stu-id="c29e3-130">Run the command and ignore the error, as they are expected.</span></span>

  ```powershell
    Publish-SilData
   ```
  4. <span data-ttu-id="c29e3-131">\Windows\System32\Logfiles\SIL\ ディレクトリ内のファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="c29e3-131">Delete the files in  \Windows\System32\Logfiles\SIL\ directory</span></span>

  ```powershell
    Remove-Item -Recurse $env:SystemRoot\System32\Logfiles\SIL\
  ```
  5. <span data-ttu-id="c29e3-132">使用可能な重要な Windows 更新プログラムをすべてをインストールし、通常どおりに Sysyprep の操作を開始します。</span><span class="sxs-lookup"><span data-stu-id="c29e3-132">Install all available important Windows Updates, and begin Sysyprep operation normally.</span></span>

- <span data-ttu-id="c29e3-133">**Windows Server 2012** を実行するシステムの場合</span><span class="sxs-lookup"><span data-stu-id="c29e3-133">For systems running **Windows Server 2012**</span></span>
  1.    <span data-ttu-id="c29e3-134">Sysprep を取得するサーバーに WMF 5.0 をインストールした後、管理者としてログインします。</span><span class="sxs-lookup"><span data-stu-id="c29e3-134">After installing WMF 5.0 on the server to be Sysprep’d, login as administrator.</span></span>
  2.    <span data-ttu-id="c29e3-135">\Windows\System32\Sysprep\ActionFiles\ ディレクトリから Windows ディレクトリ以外の場所 (例: C:\) に Generize.xml をコピーします。</span><span class="sxs-lookup"><span data-stu-id="c29e3-135">Copy Generize.xml from directory \Windows\System32\Sysprep\ActionFiles\ to a location outside of the Windows directory, C:\ for example.</span></span>
  3.    <span data-ttu-id="c29e3-136">メモ帳で Generalize.xml のコピーを開きます。</span><span class="sxs-lookup"><span data-stu-id="c29e3-136">Open your Generalize.xml copy with notepad.</span></span>
  4.    <span data-ttu-id="c29e3-137">次のテキストを検索して削除します。テキストごとに 1 つのインスタンスを削除する必要があります (これらはドキュメントの末尾付近にあります)。</span><span class="sxs-lookup"><span data-stu-id="c29e3-137">Find and remove the following text, one instance of each needs to be deleted (they will be near the end of the document).</span></span>

    ```
    <sysprepOrder order="0x3200"></sysprepOrder>
    <sysprepOrder order="0x3300"></sysprepOrder>
    ```

  5.    <span data-ttu-id="c29e3-138">編集した Generalize.xml のコピーを保存してファイルを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c29e3-138">Save the edited copy of Generalize.xml and close the file.</span></span>
  6.    <span data-ttu-id="c29e3-139">管理者としてコマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="c29e3-139">Open a command prompt as administrator</span></span>
  7.    <span data-ttu-id="c29e3-140">次のコマンドを実行し、System32 フォルダーで Generalize.xml ファイルの所有権を取得します。</span><span class="sxs-lookup"><span data-stu-id="c29e3-140">Run the following command to take ownership of the Generalize.xml file in system32 folder:</span></span>

    ```
    Takeown /f C:\Windows\System32\Sysprep\ActionFiles\Generalize.xml
    ```

  8.    <span data-ttu-id="c29e3-141">次のコマンドを実行し、ファイルの適切なアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="c29e3-141">Run the following command to set appropriate permission on the file:</span></span>

    ```
    Cacls C:\Windows\System32\ Sysprep\ActionFiles\Generalize.xml /G `<AdministratorUserName>`:F
    ```
      * <span data-ttu-id="c29e3-142">確認のプロンプトで [はい] と回答します。</span><span class="sxs-lookup"><span data-stu-id="c29e3-142">Answer Yes at the prompt for confirmation.</span></span>
      * <span data-ttu-id="c29e3-143">なお `<AdministratorUserName>` をコンピューター管理者のユーザー名に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="c29e3-143">Note that `<AdministratorUserName>` should be replaced by the username who is administrator on the machine.</span></span> <span data-ttu-id="c29e3-144">たとえば、"Administrator" にします。</span><span class="sxs-lookup"><span data-stu-id="c29e3-144">For example, "Administrator".</span></span>

  9.    <span data-ttu-id="c29e3-145">次のコマンドを使用して、Sysprep ディレクトリに保存した編集済みファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="c29e3-145">Copy the file you edited and saved over to the Sysprep directory using the following command:</span></span>

    ```
    xcopy C:\Generalize.xml C:\Windows\System32\Sysprep\ActionFiles\Generalize.xml
    ```
      * <span data-ttu-id="c29e3-146">[はい] と回答して上書きします (上書きの確認メッセージが表示されない場合は、入力されたパスを再確認してください)。</span><span class="sxs-lookup"><span data-stu-id="c29e3-146">Answer Yes to overwrite (note that if there is no prompt to overwrite, double check the path entered).</span></span>
      * <span data-ttu-id="c29e3-147">編集した Generalize.xml のコピーは C:\ にコピーされたことを想定しています。</span><span class="sxs-lookup"><span data-stu-id="c29e3-147">Assumes your edited copy of Generalize.xml was copied to C:\ .</span></span>

  10.   <span data-ttu-id="c29e3-148">この解決策により Generalize.xml が更新されます。</span><span class="sxs-lookup"><span data-stu-id="c29e3-148">Generalize.xml is now updated with the workaround.</span></span> <span data-ttu-id="c29e3-149">Sysprep を実行して汎用化オプションを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="c29e3-149">Please run Sysprep with the generalize option enabled.</span></span>