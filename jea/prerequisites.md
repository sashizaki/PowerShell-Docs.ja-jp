---
ms.date: 06/12/2017
author: rpsqrd
ms.topic: conceptual
keywords: JEA, PowerShell, セキュリティ
title: JEA の前提条件
ms.openlocfilehash: 92a74d89a0e982e9f45e69d92b261756de33c038
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="prerequisites"></a><span data-ttu-id="ec7a2-103">前提条件</span><span class="sxs-lookup"><span data-stu-id="ec7a2-103">Prerequisites</span></span>

> <span data-ttu-id="ec7a2-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="ec7a2-104">Applies to: Windows PowerShell 5.0</span></span>

<span data-ttu-id="ec7a2-105">Just Enough Administration は、Windows PowerShell 5.0 以降に含まれる機能です。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-105">Just Enough Administration is a feature included with Windows PowerShell 5.0 and higher.</span></span>
<span data-ttu-id="ec7a2-106">このトピックでは、JEA の使用を開始するために満たす必要のある前提条件について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-106">This topic describes the prerequisites that must be satisfied in order to start using JEA.</span></span>

## <a name="install-jea"></a><span data-ttu-id="ec7a2-107">JEA のインストール</span><span class="sxs-lookup"><span data-stu-id="ec7a2-107">Install JEA</span></span>

<span data-ttu-id="ec7a2-108">JEA は Windows PowerShell 5.0 以降で利用できますが、完全な機能のためには、システムで使用できる最新バージョンの PowerShell をインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-108">JEA is available with Windows PowerShell 5.0 and higher, but for full functionality it is recommended that you install the latest version of PowerShell available for your system.</span></span>
<span data-ttu-id="ec7a2-109">次の表は、Windows Server での JEA の可用性を示します。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-109">The following table describes JEA's availability on Windows Server:</span></span>

<span data-ttu-id="ec7a2-110">サーバーのオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="ec7a2-110">Server Operating System</span></span>   | <span data-ttu-id="ec7a2-111">JEA の可用性</span><span class="sxs-lookup"><span data-stu-id="ec7a2-111">JEA Availability</span></span>
--------------------------|--------------------------------
<span data-ttu-id="ec7a2-112">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="ec7a2-112">Windows Server 2016</span></span>       | <span data-ttu-id="ec7a2-113">プレインストール済み</span><span class="sxs-lookup"><span data-stu-id="ec7a2-113">Preinstalled</span></span>
<span data-ttu-id="ec7a2-114">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ec7a2-114">Windows Server 2012 R2</span></span>    | <span data-ttu-id="ec7a2-115">WMF 5.1 のすべての機能</span><span class="sxs-lookup"><span data-stu-id="ec7a2-115">Full functionality with WMF 5.1</span></span>
<span data-ttu-id="ec7a2-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ec7a2-116">Windows Server 2012</span></span>       | <span data-ttu-id="ec7a2-117">WMF 5.1 のすべての機能</span><span class="sxs-lookup"><span data-stu-id="ec7a2-117">Full functionality with WMF 5.1</span></span>
<span data-ttu-id="ec7a2-118">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="ec7a2-118">Windows Server 2008 R2</span></span>    | <span data-ttu-id="ec7a2-119">WMF 5.1 の制限された機能<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ec7a2-119">Reduced functionality<sup>1</sup> with WMF 5.1</span></span>

<span data-ttu-id="ec7a2-120">JEA は、自宅または会社のコンピューターでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-120">You can also use JEA on your home or work computer:</span></span>

<span data-ttu-id="ec7a2-121">クライアントのオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="ec7a2-121">Client Operating System</span></span>   | <span data-ttu-id="ec7a2-122">JEA の可用性</span><span class="sxs-lookup"><span data-stu-id="ec7a2-122">JEA Availability</span></span>
--------------------------|-----------------------------------------------------
<span data-ttu-id="ec7a2-123">Windows 10 1607 以降</span><span class="sxs-lookup"><span data-stu-id="ec7a2-123">Windows 10 1607+</span></span>          | <span data-ttu-id="ec7a2-124">プレインストール済み</span><span class="sxs-lookup"><span data-stu-id="ec7a2-124">Preinstalled</span></span>
<span data-ttu-id="ec7a2-125">Windows 10 1603、1511</span><span class="sxs-lookup"><span data-stu-id="ec7a2-125">Windows 10 1603, 1511</span></span>     | <span data-ttu-id="ec7a2-126">制限された機能でプレインストール済み<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ec7a2-126">Preinstalled, with reduced functionality<sup>2</sup></span></span>
<span data-ttu-id="ec7a2-127">Windows 10 1507</span><span class="sxs-lookup"><span data-stu-id="ec7a2-127">Windows 10 1507</span></span>           | <span data-ttu-id="ec7a2-128">不可</span><span class="sxs-lookup"><span data-stu-id="ec7a2-128">Not available</span></span>
<span data-ttu-id="ec7a2-129">Windows 8、8.1</span><span class="sxs-lookup"><span data-stu-id="ec7a2-129">Windows 8, 8.1</span></span>            | <span data-ttu-id="ec7a2-130">WMF 5.1 のすべての機能</span><span class="sxs-lookup"><span data-stu-id="ec7a2-130">Full functionality with WMF 5.1</span></span>
<span data-ttu-id="ec7a2-131">Windows 7</span><span class="sxs-lookup"><span data-stu-id="ec7a2-131">Windows 7</span></span>                 | <span data-ttu-id="ec7a2-132">WMF 5.1 の制限された機能<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ec7a2-132">Reduced functionality<sup>1</sup> with WMF 5.1</span></span>

<span data-ttu-id="ec7a2-133"><sup>1</sup> Windows Server 2008 R2 または Windows 7 で、グループが管理するサービス アカウントを使用するように JEA を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-133"><sup>1</sup> JEA cannot be configured to use group managed service accounts on Windows Server 2008 R2 or Windows 7.</span></span>
<span data-ttu-id="ec7a2-134">仮想アカウントと他の JEA 機能はサポートされています*。*</span><span class="sxs-lookup"><span data-stu-id="ec7a2-134">Virtual accounts and other JEA features *are* supported.</span></span>

<span data-ttu-id="ec7a2-135"><sup>2</sup> Windows 10 のバージョン 1511 と 1603 では、JEA の次の機能はサポートされません。グループ管理されたサービス アカウントとしての実行、セッション構成での条件付きアクセス規則、ユーザー ドライブ、ローカル ユーザー アカウントへのアクセスの許可。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-135"><sup>2</sup> Windows 10 versions 1511 and 1603 do not support the following JEA features: running as a group managed service account, conditional access rules in session configurations, the user drive, and granting access to local user accounts.</span></span>
<span data-ttu-id="ec7a2-136">これらの機能を使うには、Windows をバージョン 1607 (Anniversary Update) 以降に更新します。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-136">To get support for these features, update Windows to version 1607 (Anniversary Update) or higher.</span></span>

### <a name="check-which-version-of-powershell-is-installed"></a><span data-ttu-id="ec7a2-137">インストールされている PowerShell のバージョンを確認する</span><span class="sxs-lookup"><span data-stu-id="ec7a2-137">Check which version of PowerShell is installed</span></span>

<span data-ttu-id="ec7a2-138">システムにインストールされている PowerShell のバージョンを確認するには、Windows PowerShell プロンプトで `$PSVersionTable` 変数を調べます。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-138">To check which version of PowerShell is installed on your system, check the `$PSVersionTable` variable in a Windows PowerShell prompt.</span></span>

```powershell
PS C:\> $PSVersionTable.PSVersion

Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  1000
```

<span data-ttu-id="ec7a2-139">*メジャー* バージョンが **5** 以上の場合、JEA を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-139">You are ready to use JEA if the *Major* version is equal to or greater than **5**.</span></span>
<span data-ttu-id="ec7a2-140">エクスペリエンスを最善にし、すべての最新機能にアクセスするには、可能な場合は PowerShell バージョン **5.1** にアップグレードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-140">For the best experience, and to have access to all the latest features, it is recommended that you upgrade to PowerShell version **5.1** when possible.</span></span>

### <a name="install-windows-management-framework"></a><span data-ttu-id="ec7a2-141">Windows Management Framework をインストールする</span><span class="sxs-lookup"><span data-stu-id="ec7a2-141">Install Windows Management Framework</span></span>

<span data-ttu-id="ec7a2-142">古いバージョンの PowerShell を実行している場合、最新の Windows Management Framework (WMF) 更新プログラムにシステムを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-142">If you are running an older version of PowerShell, you will need to update your system with the latest Windows Management Framework (WMF) update.</span></span>
<span data-ttu-id="ec7a2-143">更新パッケージおよび最新の WMF リリース ノートへのリンクは、[ダウンロード センター](https://aka.ms/WMF5)にあります。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-143">Update packages and a link to the latest WMF release notes are available in the [Download Center](https://aka.ms/WMF5).</span></span>

<span data-ttu-id="ec7a2-144">すべてのサーバーをアップグレードする前に、WMF とのワークロードの互換性をテストすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-144">It is strongly recommended that you test your workload's compatibility with WMF before upgrading all of your servers.</span></span>

<span data-ttu-id="ec7a2-145">Windows 10 のユーザーは、現在のバージョンの Windows PowerShell を取得するには、最新の機能更新をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-145">Windows 10 users should install the latest feature updates to obtain the current version of Windows PowerShell.</span></span>

## <a name="enable-powershell-remoting"></a><span data-ttu-id="ec7a2-146">PowerShell リモート処理を有効にする</span><span class="sxs-lookup"><span data-stu-id="ec7a2-146">Enable PowerShell Remoting</span></span>

<span data-ttu-id="ec7a2-147">PowerShell リモート処理は、JEA 構築の基盤を提供します。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-147">PowerShell Remoting provides the foundation on which JEA is built.</span></span>
<span data-ttu-id="ec7a2-148">したがって、JEA を使用する前に、システムで PowerShell リモート処理を有効にし、[適切にセキュリティ保護する](https://msdn.microsoft.com/powershell/scripting/setup/winrmsecurity)必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-148">It is therefore necessary to ensure PowerShell Remoting is enabled and [properly secured](https://msdn.microsoft.com/powershell/scripting/setup/winrmsecurity) on your system before you can use JEA.</span></span>

<span data-ttu-id="ec7a2-149">Windows Server 2012、2012 R2、2016 では、PowerShell リモート処理は既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-149">PowerShell Remoting is enabled by default on Windows Server 2012, 2012 R2, and 2016.</span></span>
<span data-ttu-id="ec7a2-150">管理者特権の PowerShell ウィンドウで次のコマンドを実行することにより、PowerShell リモート処理を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-150">You can enable PowerShell Remoting by running the following command in an elevated PowerShell window.</span></span>

```powershell
Enable-PSRemoting
```

## <a name="enable-powershell-module-and-script-block-logging-optional"></a><span data-ttu-id="ec7a2-151">PowerShell モジュールおよびスクリプト ブロック ログを有効にする (省略可能)</span><span class="sxs-lookup"><span data-stu-id="ec7a2-151">Enable PowerShell module and script block logging (optional)</span></span>

<span data-ttu-id="ec7a2-152">次の手順で、システム上のすべての PowerShell 操作のログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-152">The following steps enable logging for all PowerShell actions on your system.</span></span>
<span data-ttu-id="ec7a2-153">PowerShell モジュール ログは JEA には必要ありませんが、ユーザーが実行するコマンドが中央の場所に記録されるように有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-153">PowerShell Module Logging is not required for JEA, however it is strongly recommended that you turn it on to ensure the commands users run are logged in a central location.</span></span>

<span data-ttu-id="ec7a2-154">グループ ポリシーを使って、PowerShell モジュール ログ ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-154">You can configure the PowerShell Module Logging policy using Group Policy.</span></span>

1. <span data-ttu-id="ec7a2-155">ワークステーションでローカル グループ ポリシー エディターを開くか、Active Directory ドメイン コントローラーのグループ ポリシー管理コンソールでグループ ポリシー オブジェクトを開きます</span><span class="sxs-lookup"><span data-stu-id="ec7a2-155">Open the Local Group Policy Editor on a workstation or a Group Policy Object in the Group Policy Management Console on an Active Directory Domain Controller</span></span>
2. <span data-ttu-id="ec7a2-156">**[コンピューターの構成]\\[管理用テンプレート]\\[Windows コンポーネント]\\[Windows PowerShell]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-156">Navigate to **Computer Configuration\\Administrative Templates\\Windows Components\\Windows PowerShell**</span></span>
3. <span data-ttu-id="ec7a2-157">**[モジュール ログを有効にする]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-157">Double click on **Turn on Module Logging**</span></span>
4. <span data-ttu-id="ec7a2-158">**[有効]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-158">Click **Enabled**</span></span>
5. <span data-ttu-id="ec7a2-159">[オプション] セクションで、モジュール名の横にある **[表示]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-159">In the Options section, click on **Show** next to Module Names</span></span>
6. <span data-ttu-id="ec7a2-160">ポップアップ ウィンドウに「**\***」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-160">Type "**\***" in the pop up window.</span></span> <span data-ttu-id="ec7a2-161">これは、すべてのモジュールのコマンドを記録するよう PowerShell に指示します。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-161">This instructs PowerShell to log commands from all modules.</span></span>
7. <span data-ttu-id="ec7a2-162">**[OK]** をクリックしてポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-162">Click **OK** to set the policy</span></span>
8. <span data-ttu-id="ec7a2-163">**[PowerShell スクリプト ブロックのログ記録を有効にする]** をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-163">Double click on **Turn on PowerShell Script Block Logging**</span></span>
9. <span data-ttu-id="ec7a2-164">**[有効]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-164">Click **Enabled**</span></span>
10. <span data-ttu-id="ec7a2-165">**[OK]** をクリックしてポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-165">Click **OK** to set the policy</span></span>
11. <span data-ttu-id="ec7a2-166">(ドメインに参加しているコンピューターのみ) **gpupdate** を実行するか、グループ ポリシーが更新されたポリシーを処理して設定を適用するのを待ちます</span><span class="sxs-lookup"><span data-stu-id="ec7a2-166">(On domain-joined machines only) Run **gpupdate** or wait for Group Policy to process the updated policy and apply the settings</span></span>

<span data-ttu-id="ec7a2-167">グループ ポリシーを通してシステム全体の PowerShell トランスクリプトを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ec7a2-167">You can also enable system-wide PowerShell transcription through Group Policy.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ec7a2-168">次の手順</span><span class="sxs-lookup"><span data-stu-id="ec7a2-168">Next steps</span></span>

- [<span data-ttu-id="ec7a2-169">ロール機能ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="ec7a2-169">Create a role capability file</span></span>](role-capabilities.md)
- [<span data-ttu-id="ec7a2-170">セッション構成ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="ec7a2-170">Create a session configuration file</span></span>](session-configurations.md)

## <a name="see-also"></a><span data-ttu-id="ec7a2-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec7a2-171">See also</span></span>

- [<span data-ttu-id="ec7a2-172">PowerShell リモート処理と WinRM セキュリティに関する追加情報</span><span class="sxs-lookup"><span data-stu-id="ec7a2-172">Additional information about PowerShell Remoting and WinRM security</span></span>](https://msdn.microsoft.com/powershell/scripting/setup/winrmsecurity)
- [<span data-ttu-id="ec7a2-173">*PowerShell ♥ the Blue Team* のセキュリティに関するブログ投稿</span><span class="sxs-lookup"><span data-stu-id="ec7a2-173">*PowerShell ♥ the Blue Team* blog post on security</span></span>](https://blogs.msdn.microsoft.com/powershell/2015/06/09/powershell-the-blue-team/)