---
ms.date: 07/10/2019
keywords: JEA, PowerShell, セキュリティ
title: JEA の前提条件
ms.openlocfilehash: 1833bacf49eebcccefc10f7c85a39732559c1a97
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74416732"
---
# <a name="prerequisites"></a><span data-ttu-id="d1ad5-103">前提条件</span><span class="sxs-lookup"><span data-stu-id="d1ad5-103">Prerequisites</span></span>

<span data-ttu-id="d1ad5-104">Just Enough Administration は、PowerShell 5.0 以降に含まれる機能です。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-104">Just Enough Administration is a feature included in PowerShell 5.0 and higher.</span></span> <span data-ttu-id="d1ad5-105">この記事では、JEA の使用を開始するために満たす必要のある前提条件について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-105">This article describes the prerequisites that must be satisfied to start using JEA.</span></span>


## <a name="check-which-version-of-powershell-is-installed"></a><span data-ttu-id="d1ad5-106">インストールされている PowerShell のバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="d1ad5-106">Check which version of PowerShell is installed</span></span>

<span data-ttu-id="d1ad5-107">システムにインストールされている PowerShell のバージョンを確認するには、Windows PowerShell プロンプトで `$PSVersionTable` 変数を調べます。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-107">To check which version of PowerShell is installed on your system, check the `$PSVersionTable` variable in a Windows PowerShell prompt.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  1000
```

<span data-ttu-id="d1ad5-108">JEA は PowerShell 5.0 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-108">JEA is available with PowerShell 5.0 and higher.</span></span> <span data-ttu-id="d1ad5-109">完全な機能のためには、システムで使用できる最新バージョンの PowerShell をインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-109">For full functionality, it's recommended that you install the latest version of PowerShell available for your system.</span></span> <span data-ttu-id="d1ad5-110">次の表は、Windows Server での JEA の可用性を示します。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-110">The following table describes JEA's availability on Windows Server:</span></span>

| <span data-ttu-id="d1ad5-111">サーバーのオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="d1ad5-111">Server Operating System</span></span> |                <span data-ttu-id="d1ad5-112">JEA の可用性</span><span class="sxs-lookup"><span data-stu-id="d1ad5-112">JEA Availability</span></span>                |
| ----------------------- | ---------------------------------------------- |
| <span data-ttu-id="d1ad5-113">Windows Server 2016 以降</span><span class="sxs-lookup"><span data-stu-id="d1ad5-113">Windows Server 2016+</span></span>    | <span data-ttu-id="d1ad5-114">プレインストール済み</span><span class="sxs-lookup"><span data-stu-id="d1ad5-114">Preinstalled</span></span>                                   |
| <span data-ttu-id="d1ad5-115">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d1ad5-115">Windows Server 2012 R2</span></span>  | <span data-ttu-id="d1ad5-116">WMF 5.1 のすべての機能</span><span class="sxs-lookup"><span data-stu-id="d1ad5-116">Full functionality with WMF 5.1</span></span>                |
| <span data-ttu-id="d1ad5-117">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="d1ad5-117">Windows Server 2012</span></span>     | <span data-ttu-id="d1ad5-118">WMF 5.1 のすべての機能</span><span class="sxs-lookup"><span data-stu-id="d1ad5-118">Full functionality with WMF 5.1</span></span>                |
| <span data-ttu-id="d1ad5-119">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d1ad5-119">Windows Server 2008 R2</span></span>  | <span data-ttu-id="d1ad5-120">WMF 5.1 の制限された機能<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d1ad5-120">Reduced functionality<sup>1</sup> with WMF 5.1</span></span> |

<span data-ttu-id="d1ad5-121">JEA は、自宅または会社のコンピューターでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-121">You can also use JEA on your home or work computer:</span></span>

| <span data-ttu-id="d1ad5-122">クライアントのオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="d1ad5-122">Client Operating System</span></span> |                   <span data-ttu-id="d1ad5-123">JEA の可用性</span><span class="sxs-lookup"><span data-stu-id="d1ad5-123">JEA Availability</span></span>                   |
| ----------------------- | ---------------------------------------------------- |
| <span data-ttu-id="d1ad5-124">Windows 10 1607 以降</span><span class="sxs-lookup"><span data-stu-id="d1ad5-124">Windows 10 1607+</span></span>        | <span data-ttu-id="d1ad5-125">プレインストール済み</span><span class="sxs-lookup"><span data-stu-id="d1ad5-125">Preinstalled</span></span>                                         |
| <span data-ttu-id="d1ad5-126">Windows 10 1603、1511</span><span class="sxs-lookup"><span data-stu-id="d1ad5-126">Windows 10 1603, 1511</span></span>   | <span data-ttu-id="d1ad5-127">制限された機能でプレインストール済み<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="d1ad5-127">Preinstalled, with reduced functionality<sup>2</sup></span></span> |
| <span data-ttu-id="d1ad5-128">Windows 10 1507</span><span class="sxs-lookup"><span data-stu-id="d1ad5-128">Windows 10 1507</span></span>         | <span data-ttu-id="d1ad5-129">不可</span><span class="sxs-lookup"><span data-stu-id="d1ad5-129">Not available</span></span>                                        |
| <span data-ttu-id="d1ad5-130">Windows 8、8.1</span><span class="sxs-lookup"><span data-stu-id="d1ad5-130">Windows 8, 8.1</span></span>          | <span data-ttu-id="d1ad5-131">WMF 5.1 のすべての機能</span><span class="sxs-lookup"><span data-stu-id="d1ad5-131">Full functionality with WMF 5.1</span></span>                      |
| <span data-ttu-id="d1ad5-132">Windows 7</span><span class="sxs-lookup"><span data-stu-id="d1ad5-132">Windows 7</span></span>               | <span data-ttu-id="d1ad5-133">WMF 5.1 の制限された機能<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d1ad5-133">Reduced functionality<sup>1</sup> with WMF 5.1</span></span>       |

- <span data-ttu-id="d1ad5-134"><sup>1</sup> Windows Server 2008 R2 または Windows 7 で、グループが管理するサービス アカウントを使用するように JEA を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-134"><sup>1</sup> JEA can't be configured to use group-managed service accounts on Windows Server 2008 R2 or Windows 7.</span></span> <span data-ttu-id="d1ad5-135">仮想アカウントと他の JEA 機能はサポートされています *。*</span><span class="sxs-lookup"><span data-stu-id="d1ad5-135">Virtual accounts and other JEA features *are* supported.</span></span>

- <span data-ttu-id="d1ad5-136"><sup>2</sup> 次の JEA 機能は、Windows 10 バージョン 1511 と 1603 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-136"><sup>2</sup> The following JEA features aren't supported on Windows 10 versions 1511 and 1603:</span></span>

  - <span data-ttu-id="d1ad5-137">グループ管理されたサービス アカウントとして実行する</span><span class="sxs-lookup"><span data-stu-id="d1ad5-137">Running as a group-managed service account</span></span>
  - <span data-ttu-id="d1ad5-138">セッション構成での条件付きアクセス規則</span><span class="sxs-lookup"><span data-stu-id="d1ad5-138">Conditional access rules in session configurations</span></span>
  - <span data-ttu-id="d1ad5-139">ユーザー ドライブ</span><span class="sxs-lookup"><span data-stu-id="d1ad5-139">The user drive</span></span>
  - <span data-ttu-id="d1ad5-140">ローカル ユーザー アカウントにアクセス許可を付与する</span><span class="sxs-lookup"><span data-stu-id="d1ad5-140">Granting access to local user accounts</span></span>

  <span data-ttu-id="d1ad5-141">これらの機能を使うには、Windows をバージョン 1607 (Anniversary Update) 以降に更新します。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-141">To get support for these features, update Windows to version 1607 (Anniversary Update) or higher.</span></span>

### <a name="install-windows-management-framework"></a><span data-ttu-id="d1ad5-142">Windows Management Framework をインストールする</span><span class="sxs-lookup"><span data-stu-id="d1ad5-142">Install Windows Management Framework</span></span>

<span data-ttu-id="d1ad5-143">より古いバージョンの PowerShell を実行している場合、最新の Windows Management Framework (WMF) 更新プログラムでご利用のシステムを更新する必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-143">If you're running an older version of PowerShell, you may need to update your system with the latest Windows Management Framework (WMF) update.</span></span> <span data-ttu-id="d1ad5-144">詳細については、[WMF のドキュメント](/powershell/scripting/wmf/overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-144">For more information, see the [WMF documentation](/powershell/scripting/wmf/overview).</span></span>

<span data-ttu-id="d1ad5-145">ご利用のすべてのサーバーをアップグレードする前に、WMF とのワークロードの互換性をテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-145">It's recommended that you test your workload's compatibility with WMF before upgrading all of your servers.</span></span>

<span data-ttu-id="d1ad5-146">Windows 10 のユーザーは、現在のバージョンの Windows PowerShell を取得するには、最新の機能更新をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-146">Windows 10 users should install the latest feature updates to obtain the current version of Windows PowerShell.</span></span>

## <a name="enable-powershell-remoting"></a><span data-ttu-id="d1ad5-147">PowerShell リモート処理を有効にする</span><span class="sxs-lookup"><span data-stu-id="d1ad5-147">Enable PowerShell Remoting</span></span>

<span data-ttu-id="d1ad5-148">PowerShell リモート処理は、JEA 構築の基盤を提供します。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-148">PowerShell Remoting provides the foundation on which JEA is built.</span></span> <span data-ttu-id="d1ad5-149">JEA を使用する前に、PowerShell リモート処理を有効にし、適切にセキュリティで保護されていることを確実にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-149">It's necessary to ensure PowerShell Remoting is enabled and properly secured before you can use JEA.</span></span> <span data-ttu-id="d1ad5-150">詳細については、[WinRM セキュリティ](/powershell/scripting/learn/remoting/winrmsecurity)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-150">For more information, see [WinRM Security](/powershell/scripting/learn/remoting/winrmsecurity).</span></span>

<span data-ttu-id="d1ad5-151">Windows Server 2012、2012 R2、2016 では、PowerShell リモート処理は既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-151">PowerShell Remoting is enabled by default on Windows Server 2012, 2012 R2, and 2016.</span></span> <span data-ttu-id="d1ad5-152">管理者特権の PowerShell ウィンドウで次のコマンドを実行することにより、PowerShell リモート処理を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-152">You can enable PowerShell Remoting by running the following command in an elevated PowerShell window.</span></span>

```powershell
Enable-PSRemoting
```

## <a name="enable-powershell-module-and-script-block-logging-optional"></a><span data-ttu-id="d1ad5-153">PowerShell モジュールおよびスクリプト ブロック ログを有効にする (省略可能)</span><span class="sxs-lookup"><span data-stu-id="d1ad5-153">Enable PowerShell module and script block logging (optional)</span></span>

<span data-ttu-id="d1ad5-154">次の手順で、システム上のすべての PowerShell 操作のログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-154">The following steps enable logging for all PowerShell actions on your system.</span></span> <span data-ttu-id="d1ad5-155">PowerShell モジュール ログは JEA には必要ありませんが、ユーザーが実行するコマンドが確実に中央の場所にログ記録されるように、有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-155">PowerShell Module Logging isn't required for JEA, however it's recommended you turn on logging to ensure the commands users run are logged in a central location.</span></span>

<span data-ttu-id="d1ad5-156">グループ ポリシーを使って、PowerShell モジュール ログ ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-156">You can configure the PowerShell Module Logging policy using Group Policy.</span></span>

1. <span data-ttu-id="d1ad5-157">ワークステーションでローカル グループ ポリシー エディターを開くか、Active Directory ドメイン コントローラーのグループ ポリシー管理コンソールでグループ ポリシー オブジェクトを開きます</span><span class="sxs-lookup"><span data-stu-id="d1ad5-157">Open the Local Group Policy Editor on a workstation or a Group Policy Object in the Group Policy Management Console on an Active Directory Domain Controller</span></span>
2. <span data-ttu-id="d1ad5-158">**[コンピューターの構成]\\[管理用テンプレート]\\[Windows コンポーネント]\\[Windows PowerShell]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-158">Navigate to **Computer Configuration\\Administrative Templates\\Windows Components\\Windows PowerShell**</span></span>
3. <span data-ttu-id="d1ad5-159">**[モジュール ログを有効にする]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-159">Double-click on **Turn on Module Logging**</span></span>
4. <span data-ttu-id="d1ad5-160">**[有効]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-160">Click **Enabled**</span></span>
5. <span data-ttu-id="d1ad5-161">[オプション] セクションで、モジュール名の横にある **[表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-161">In the Options section, click on **Show** next to Module Names</span></span>
6. <span data-ttu-id="d1ad5-162">ポップアップ ウィンドウに「`*`」を入力して、すべてのモジュールからのコマンドをログ記録します。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-162">Type `*` in the pop-up window to log commands from all modules.</span></span>
7. <span data-ttu-id="d1ad5-163">**[OK]** をクリックしてポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-163">Click **OK** to set the policy</span></span>
8. <span data-ttu-id="d1ad5-164">**[PowerShell スクリプト ブロックのログ記録を有効にする]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-164">Double-click on **Turn on PowerShell Script Block Logging**</span></span>
9. <span data-ttu-id="d1ad5-165">**[有効]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-165">Click **Enabled**</span></span>
10. <span data-ttu-id="d1ad5-166">**[OK]** をクリックしてポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-166">Click **OK** to set the policy</span></span>
11. <span data-ttu-id="d1ad5-167">(ドメインに参加しているコンピューターのみ) `gpupdate` を実行するか、グループ ポリシーが更新されたポリシーを処理して設定を適用するのを待ちます</span><span class="sxs-lookup"><span data-stu-id="d1ad5-167">(On domain-joined machines only) Run `gpupdate` or wait for Group Policy to process the updated policy and apply the settings</span></span>

<span data-ttu-id="d1ad5-168">グループ ポリシーを通してシステム全体の PowerShell トランスクリプトを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d1ad5-168">You can also enable system-wide PowerShell transcription through Group Policy.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d1ad5-169">次の手順</span><span class="sxs-lookup"><span data-stu-id="d1ad5-169">Next steps</span></span>

[<span data-ttu-id="d1ad5-170">ロール機能ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="d1ad5-170">Create a role capability file</span></span>](role-capabilities.md)

[<span data-ttu-id="d1ad5-171">セッション構成ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="d1ad5-171">Create a session configuration file</span></span>](session-configurations.md)

## <a name="see-also"></a><span data-ttu-id="d1ad5-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1ad5-172">See also</span></span>

[<span data-ttu-id="d1ad5-173">WinRM セキュリティ</span><span class="sxs-lookup"><span data-stu-id="d1ad5-173">WinRM Security</span></span>](/powershell/scripting/learn/remoting/winrmsecurity)

[<span data-ttu-id="d1ad5-174">ブルー チームを支援する PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1ad5-174">PowerShell ♥ the Blue Team</span></span>](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)
