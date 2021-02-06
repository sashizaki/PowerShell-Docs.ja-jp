---
ms.date: 07/10/2019
keywords: JEA, PowerShell, セキュリティ
title: JEA の前提条件
description: この記事では、JEA の使用を開始するために満たす必要のある前提条件について説明します。
ms.openlocfilehash: 5cc70a06887a2d0a840cc83117f865d3148056e1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92501730"
---
# <a name="prerequisites"></a><span data-ttu-id="bab35-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="bab35-104">Prerequisites</span></span>

<span data-ttu-id="bab35-105">Just Enough Administration は、PowerShell 5.0 以降に含まれる機能です。</span><span class="sxs-lookup"><span data-stu-id="bab35-105">Just Enough Administration is a feature included in PowerShell 5.0 and higher.</span></span> <span data-ttu-id="bab35-106">この記事では、JEA の使用を開始するために満たす必要のある前提条件について説明します。</span><span class="sxs-lookup"><span data-stu-id="bab35-106">This article describes the prerequisites that must be satisfied to start using JEA.</span></span>

## <a name="check-which-version-of-powershell-is-installed"></a><span data-ttu-id="bab35-107">インストールされている PowerShell のバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="bab35-107">Check which version of PowerShell is installed</span></span>

<span data-ttu-id="bab35-108">システムにインストールされている PowerShell のバージョンを確認するには、Windows PowerShell プロンプトで `$PSVersionTable` 変数を調べます。</span><span class="sxs-lookup"><span data-stu-id="bab35-108">To check which version of PowerShell is installed on your system, check the `$PSVersionTable` variable in a Windows PowerShell prompt.</span></span>

```powershell
$PSVersionTable.PSVersion
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  1000
```

<span data-ttu-id="bab35-109">JEA は PowerShell 5.0 以降で利用できます。</span><span class="sxs-lookup"><span data-stu-id="bab35-109">JEA is available with PowerShell 5.0 and higher.</span></span> <span data-ttu-id="bab35-110">完全な機能のためには、システムで使用できる最新バージョンの PowerShell をインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bab35-110">For full functionality, it's recommended that you install the latest version of PowerShell available for your system.</span></span> <span data-ttu-id="bab35-111">次の表は、Windows Server での JEA の可用性を示します。</span><span class="sxs-lookup"><span data-stu-id="bab35-111">The following table describes JEA's availability on Windows Server:</span></span>

| <span data-ttu-id="bab35-112">サーバーのオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="bab35-112">Server Operating System</span></span> |                <span data-ttu-id="bab35-113">JEA の可用性</span><span class="sxs-lookup"><span data-stu-id="bab35-113">JEA Availability</span></span>                |
| ----------------------- | ---------------------------------------------- |
| <span data-ttu-id="bab35-114">Windows Server 2016 以降</span><span class="sxs-lookup"><span data-stu-id="bab35-114">Windows Server 2016+</span></span>    | <span data-ttu-id="bab35-115">プレインストール済み</span><span class="sxs-lookup"><span data-stu-id="bab35-115">Preinstalled</span></span>                                   |
| <span data-ttu-id="bab35-116">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="bab35-116">Windows Server 2012 R2</span></span>  | <span data-ttu-id="bab35-117">WMF 5.1 のすべての機能</span><span class="sxs-lookup"><span data-stu-id="bab35-117">Full functionality with WMF 5.1</span></span>                |
| <span data-ttu-id="bab35-118">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="bab35-118">Windows Server 2012</span></span>     | <span data-ttu-id="bab35-119">WMF 5.1 のすべての機能</span><span class="sxs-lookup"><span data-stu-id="bab35-119">Full functionality with WMF 5.1</span></span>                |
| <span data-ttu-id="bab35-120">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="bab35-120">Windows Server 2008 R2</span></span>  | <span data-ttu-id="bab35-121">WMF 5.1 の制限された機能<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bab35-121">Reduced functionality<sup>1</sup> with WMF 5.1</span></span> |

<span data-ttu-id="bab35-122">JEA は、自宅または会社のコンピューターでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="bab35-122">You can also use JEA on your home or work computer:</span></span>

| <span data-ttu-id="bab35-123">クライアントのオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="bab35-123">Client Operating System</span></span> |                   <span data-ttu-id="bab35-124">JEA の可用性</span><span class="sxs-lookup"><span data-stu-id="bab35-124">JEA Availability</span></span>                   |
| ----------------------- | ---------------------------------------------------- |
| <span data-ttu-id="bab35-125">Windows 10 1607 以降</span><span class="sxs-lookup"><span data-stu-id="bab35-125">Windows 10 1607+</span></span>        | <span data-ttu-id="bab35-126">プレインストール済み</span><span class="sxs-lookup"><span data-stu-id="bab35-126">Preinstalled</span></span>                                         |
| <span data-ttu-id="bab35-127">Windows 10 1603、1511</span><span class="sxs-lookup"><span data-stu-id="bab35-127">Windows 10 1603, 1511</span></span>   | <span data-ttu-id="bab35-128">制限された機能でプレインストール済み<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="bab35-128">Preinstalled, with reduced functionality<sup>2</sup></span></span> |
| <span data-ttu-id="bab35-129">Windows 10 1507</span><span class="sxs-lookup"><span data-stu-id="bab35-129">Windows 10 1507</span></span>         | <span data-ttu-id="bab35-130">使用不可</span><span class="sxs-lookup"><span data-stu-id="bab35-130">Not available</span></span>                                        |
| <span data-ttu-id="bab35-131">Windows 8、8.1</span><span class="sxs-lookup"><span data-stu-id="bab35-131">Windows 8, 8.1</span></span>          | <span data-ttu-id="bab35-132">WMF 5.1 のすべての機能</span><span class="sxs-lookup"><span data-stu-id="bab35-132">Full functionality with WMF 5.1</span></span>                      |
| <span data-ttu-id="bab35-133">Windows 7</span><span class="sxs-lookup"><span data-stu-id="bab35-133">Windows 7</span></span>               | <span data-ttu-id="bab35-134">WMF 5.1 の制限された機能<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bab35-134">Reduced functionality<sup>1</sup> with WMF 5.1</span></span>       |

- <span data-ttu-id="bab35-135"><sup>1</sup> Windows Server 2008 R2 または Windows 7 で、グループが管理するサービス アカウントを使用するように JEA を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="bab35-135"><sup>1</sup> JEA can't be configured to use group-managed service accounts on Windows Server 2008 R2 or Windows 7.</span></span> <span data-ttu-id="bab35-136">仮想アカウントと他の JEA 機能はサポートされています *。*</span><span class="sxs-lookup"><span data-stu-id="bab35-136">Virtual accounts and other JEA features *are* supported.</span></span>

- <span data-ttu-id="bab35-137"><sup>2</sup> 次の JEA 機能は、Windows 10 バージョン 1511 と 1603 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bab35-137"><sup>2</sup> The following JEA features aren't supported on Windows 10 versions 1511 and 1603:</span></span>

  - <span data-ttu-id="bab35-138">グループ管理されたサービス アカウントとして実行する</span><span class="sxs-lookup"><span data-stu-id="bab35-138">Running as a group-managed service account</span></span>
  - <span data-ttu-id="bab35-139">セッション構成での条件付きアクセス規則</span><span class="sxs-lookup"><span data-stu-id="bab35-139">Conditional access rules in session configurations</span></span>
  - <span data-ttu-id="bab35-140">ユーザー ドライブ</span><span class="sxs-lookup"><span data-stu-id="bab35-140">The user drive</span></span>
  - <span data-ttu-id="bab35-141">ローカル ユーザー アカウントにアクセス許可を付与する</span><span class="sxs-lookup"><span data-stu-id="bab35-141">Granting access to local user accounts</span></span>

  <span data-ttu-id="bab35-142">これらの機能を使うには、Windows をバージョン 1607 (Anniversary Update) 以降に更新します。</span><span class="sxs-lookup"><span data-stu-id="bab35-142">To get support for these features, update Windows to version 1607 (Anniversary Update) or higher.</span></span>

### <a name="install-windows-management-framework"></a><span data-ttu-id="bab35-143">Windows Management Framework をインストールする</span><span class="sxs-lookup"><span data-stu-id="bab35-143">Install Windows Management Framework</span></span>

<span data-ttu-id="bab35-144">より古いバージョンの PowerShell を実行している場合、最新の Windows Management Framework (WMF) 更新プログラムでご利用のシステムを更新する必要がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bab35-144">If you're running an older version of PowerShell, you may need to update your system with the latest Windows Management Framework (WMF) update.</span></span> <span data-ttu-id="bab35-145">詳細については、[WMF のドキュメント](/powershell/scripting/wmf/overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bab35-145">For more information, see the [WMF documentation](/powershell/scripting/wmf/overview).</span></span>

<span data-ttu-id="bab35-146">ご利用のすべてのサーバーをアップグレードする前に、WMF とのワークロードの互換性をテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bab35-146">It's recommended that you test your workload's compatibility with WMF before upgrading all of your servers.</span></span>

<span data-ttu-id="bab35-147">Windows 10 のユーザーは、現在のバージョンの Windows PowerShell を取得するには、最新の機能更新をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bab35-147">Windows 10 users should install the latest feature updates to obtain the current version of Windows PowerShell.</span></span>

## <a name="enable-powershell-remoting"></a><span data-ttu-id="bab35-148">PowerShell リモート処理を有効にする</span><span class="sxs-lookup"><span data-stu-id="bab35-148">Enable PowerShell Remoting</span></span>

<span data-ttu-id="bab35-149">PowerShell リモート処理は、JEA 構築の基盤を提供します。</span><span class="sxs-lookup"><span data-stu-id="bab35-149">PowerShell Remoting provides the foundation on which JEA is built.</span></span> <span data-ttu-id="bab35-150">JEA を使用する前に、PowerShell リモート処理を有効にし、適切にセキュリティで保護されていることを確実にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bab35-150">It's necessary to ensure PowerShell Remoting is enabled and properly secured before you can use JEA.</span></span> <span data-ttu-id="bab35-151">詳細については、[WinRM セキュリティ](/powershell/scripting/learn/remoting/winrmsecurity)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bab35-151">For more information, see [WinRM Security](/powershell/scripting/learn/remoting/winrmsecurity).</span></span>

<span data-ttu-id="bab35-152">Windows Server 2012、2012 R2、2016 では、PowerShell リモート処理は既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="bab35-152">PowerShell Remoting is enabled by default on Windows Server 2012, 2012 R2, and 2016.</span></span> <span data-ttu-id="bab35-153">管理者特権の PowerShell ウィンドウで次のコマンドを実行することにより、PowerShell リモート処理を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="bab35-153">You can enable PowerShell Remoting by running the following command in an elevated PowerShell window.</span></span>

```powershell
Enable-PSRemoting
```

## <a name="enable-powershell-module-and-script-block-logging-optional"></a><span data-ttu-id="bab35-154">PowerShell モジュールおよびスクリプト ブロック ログを有効にする (省略可能)</span><span class="sxs-lookup"><span data-stu-id="bab35-154">Enable PowerShell module and script block logging (optional)</span></span>

<span data-ttu-id="bab35-155">次の手順で、システム上のすべての PowerShell 操作のログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bab35-155">The following steps enable logging for all PowerShell actions on your system.</span></span> <span data-ttu-id="bab35-156">PowerShell モジュール ログは JEA には必要ありませんが、ユーザーが実行するコマンドが確実に中央の場所にログ記録されるように、有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bab35-156">PowerShell Module Logging isn't required for JEA, however it's recommended you turn on logging to ensure the commands users run are logged in a central location.</span></span>

<span data-ttu-id="bab35-157">グループ ポリシーを使って、PowerShell モジュール ログ ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="bab35-157">You can configure the PowerShell Module Logging policy using Group Policy.</span></span>

1. <span data-ttu-id="bab35-158">ワークステーションでローカル グループ ポリシー エディターを開くか、Active Directory ドメイン コントローラーのグループ ポリシー管理コンソールでグループ ポリシー オブジェクトを開きます</span><span class="sxs-lookup"><span data-stu-id="bab35-158">Open the Local Group Policy Editor on a workstation or a Group Policy Object in the Group Policy Management Console on an Active Directory Domain Controller</span></span>
2. <span data-ttu-id="bab35-159">**[コンピューターの構成]\\[管理用テンプレート]\\[Windows コンポーネント]\\[Windows PowerShell]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="bab35-159">Navigate to **Computer Configuration\\Administrative Templates\\Windows Components\\Windows PowerShell**</span></span>
3. <span data-ttu-id="bab35-160">**[モジュール ログを有効にする]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="bab35-160">Double-click on **Turn on Module Logging**</span></span>
4. <span data-ttu-id="bab35-161">**[有効]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bab35-161">Click **Enabled**</span></span>
5. <span data-ttu-id="bab35-162">[オプション] セクションで、モジュール名の横にある **[表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bab35-162">In the Options section, click on **Show** next to Module Names</span></span>
6. <span data-ttu-id="bab35-163">ポップアップ ウィンドウに「`*`」を入力して、すべてのモジュールからのコマンドをログ記録します。</span><span class="sxs-lookup"><span data-stu-id="bab35-163">Type `*` in the pop-up window to log commands from all modules.</span></span>
7. <span data-ttu-id="bab35-164">**[OK]** をクリックしてポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="bab35-164">Click **OK** to set the policy</span></span>
8. <span data-ttu-id="bab35-165">**[PowerShell スクリプト ブロックのログ記録を有効にする]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="bab35-165">Double-click on **Turn on PowerShell Script Block Logging**</span></span>
9. <span data-ttu-id="bab35-166">**[有効]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bab35-166">Click **Enabled**</span></span>
10. <span data-ttu-id="bab35-167">**[OK]** をクリックしてポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="bab35-167">Click **OK** to set the policy</span></span>
11. <span data-ttu-id="bab35-168">(ドメインに参加しているコンピューターのみ) `gpupdate` を実行するか、グループ ポリシーが更新されたポリシーを処理して設定を適用するのを待ちます</span><span class="sxs-lookup"><span data-stu-id="bab35-168">(On domain-joined machines only) Run `gpupdate` or wait for Group Policy to process the updated policy and apply the settings</span></span>

<span data-ttu-id="bab35-169">グループ ポリシーを通してシステム全体の PowerShell トランスクリプトを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bab35-169">You can also enable system-wide PowerShell transcription through Group Policy.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bab35-170">次のステップ</span><span class="sxs-lookup"><span data-stu-id="bab35-170">Next steps</span></span>

[<span data-ttu-id="bab35-171">ロール機能ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="bab35-171">Create a role capability file</span></span>](role-capabilities.md)

[<span data-ttu-id="bab35-172">セッション構成ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="bab35-172">Create a session configuration file</span></span>](session-configurations.md)

## <a name="see-also"></a><span data-ttu-id="bab35-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="bab35-173">See also</span></span>

[<span data-ttu-id="bab35-174">WinRM セキュリティ</span><span class="sxs-lookup"><span data-stu-id="bab35-174">WinRM Security</span></span>](/powershell/scripting/learn/remoting/winrmsecurity)

[<span data-ttu-id="bab35-175">ブルー チームを支援する PowerShell</span><span class="sxs-lookup"><span data-stu-id="bab35-175">PowerShell ♥ the Blue Team</span></span>](https://devblogs.microsoft.com/powershell/powershell-the-blue-team/)
