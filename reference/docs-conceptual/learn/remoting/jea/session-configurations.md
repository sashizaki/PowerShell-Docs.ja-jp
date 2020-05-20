---
ms.date: 07/10/2019
keywords: JEA, PowerShell, セキュリティ
title: JEA セッションの構成
ms.openlocfilehash: 650d0d11ef13605847d0822249e29e3491180629
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "70017733"
---
# <a name="jea-session-configurations"></a><span data-ttu-id="2c837-103">JEA セッションの構成</span><span class="sxs-lookup"><span data-stu-id="2c837-103">JEA Session Configurations</span></span>

<span data-ttu-id="2c837-104">JEA エンドポイントは、PowerShell セッション構成ファイルを作成して登録することにより、システムに登録されます。</span><span class="sxs-lookup"><span data-stu-id="2c837-104">A JEA endpoint is registered on a system by creating and registering a PowerShell session configuration file.</span></span> <span data-ttu-id="2c837-105">セッションの構成によって、誰が JEA エンドポイントを使用でき、どのロールにアクセスできるかが定義されます。</span><span class="sxs-lookup"><span data-stu-id="2c837-105">Session configurations define who can use the JEA endpoint and which roles they have access to.</span></span> <span data-ttu-id="2c837-106">また、JEA セッション内のすべてのユーザーに適用されるグローバル設定も定義されます。</span><span class="sxs-lookup"><span data-stu-id="2c837-106">They also define global settings that apply to all users of the JEA session.</span></span>

## <a name="create-a-session-configuration-file"></a><span data-ttu-id="2c837-107">セッション構成ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="2c837-107">Create a session configuration file</span></span>

<span data-ttu-id="2c837-108">JEA エンドポイントを登録するには、そのエンドポイントの構成方法を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c837-108">To register a JEA endpoint, you must specify how that endpoint is configured.</span></span> <span data-ttu-id="2c837-109">考慮すべきオプションは多数あります。</span><span class="sxs-lookup"><span data-stu-id="2c837-109">There are many options to consider.</span></span> <span data-ttu-id="2c837-110">最も重要なオプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2c837-110">The most important options are:</span></span>

- <span data-ttu-id="2c837-111">誰が JEA エンドポイントにアクセスできるか</span><span class="sxs-lookup"><span data-stu-id="2c837-111">Who has access to the JEA endpoint</span></span>
- <span data-ttu-id="2c837-112">どのようなロールが彼らに割り当てられるか</span><span class="sxs-lookup"><span data-stu-id="2c837-112">Which roles they be assigned</span></span>
- <span data-ttu-id="2c837-113">JEA は内部でどの ID を使用するか</span><span class="sxs-lookup"><span data-stu-id="2c837-113">Which identity JEA uses under the covers</span></span>
- <span data-ttu-id="2c837-114">JEA エンドポイントの名前</span><span class="sxs-lookup"><span data-stu-id="2c837-114">The name of the JEA endpoint</span></span>

<span data-ttu-id="2c837-115">これらのオプションは、PowerShell セッションの構成ファイルである `.pssc` 拡張子の付いた PowerShell データ ファイルに定義されています。</span><span class="sxs-lookup"><span data-stu-id="2c837-115">These options are defined in a PowerShell data file with a `.pssc` extension known as a PowerShell session configuration file.</span></span> <span data-ttu-id="2c837-116">このセッション構成ファイルは、任意のテキスト エディターで編集できます。</span><span class="sxs-lookup"><span data-stu-id="2c837-116">The session configuration file can be edited using any text editor.</span></span>

<span data-ttu-id="2c837-117">空のテンプレート構成ファイルを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2c837-117">Run the following command to create a blank template configuration file.</span></span>

```powershell
New-PSSessionConfigurationFile -SessionType RestrictedRemoteServer -Path .\MyJEAEndpoint.pssc
```

> [!TIP]
> <span data-ttu-id="2c837-118">テンプレート ファイルには、既定で最も一般的な構成オプションのみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c837-118">Only the most common configuration options are included in the template file by default.</span></span> <span data-ttu-id="2c837-119">適用できるすべての設定を生成される PSSC に含めるには、`-Full` スイッチを使います。</span><span class="sxs-lookup"><span data-stu-id="2c837-119">Use the `-Full` switch to include all applicable settings in the generated PSSC.</span></span>

<span data-ttu-id="2c837-120">`-SessionType RestrictedRemoteServer` フィールドは、セキュリティ管理のためにセッション構成が JEA によって使われることを示します。</span><span class="sxs-lookup"><span data-stu-id="2c837-120">The `-SessionType RestrictedRemoteServer` field indicates that the session configuration is used by JEA for secure management.</span></span> <span data-ttu-id="2c837-121">このような種類のセッションは、**NoLanguage** モードで動作し、次の既定のコマンド (およびエイリアス) のみにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2c837-121">Sessions of this type operate in **NoLanguage** mode and only have access to the following default commands (and aliases):</span></span>

- <span data-ttu-id="2c837-122">Clear-Host (cls、clear)</span><span class="sxs-lookup"><span data-stu-id="2c837-122">Clear-Host (cls, clear)</span></span>
- <span data-ttu-id="2c837-123">Exit-PSSession (exsn、exit)</span><span class="sxs-lookup"><span data-stu-id="2c837-123">Exit-PSSession (exsn, exit)</span></span>
- <span data-ttu-id="2c837-124">Get-Command (gcm)</span><span class="sxs-lookup"><span data-stu-id="2c837-124">Get-Command (gcm)</span></span>
- <span data-ttu-id="2c837-125">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="2c837-125">Get-FormatData</span></span>
- <span data-ttu-id="2c837-126">Get-Help</span><span class="sxs-lookup"><span data-stu-id="2c837-126">Get-Help</span></span>
- <span data-ttu-id="2c837-127">Measure-Object (measure)</span><span class="sxs-lookup"><span data-stu-id="2c837-127">Measure-Object (measure)</span></span>
- <span data-ttu-id="2c837-128">Out-Default</span><span class="sxs-lookup"><span data-stu-id="2c837-128">Out-Default</span></span>
- <span data-ttu-id="2c837-129">Select-Object (select)</span><span class="sxs-lookup"><span data-stu-id="2c837-129">Select-Object (select)</span></span>

<span data-ttu-id="2c837-130">PowerShell プロバイダーおよび外部プログラム (実行可能ファイルまたはスクリプト) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="2c837-130">No PowerShell providers are available, nor are any external programs (executables or scripts).</span></span>

<span data-ttu-id="2c837-131">言語モードの詳細については、「[about_Language_modes](/powershell/module/microsoft.powershell.core/about/about_language_modes)」(言語モードについて) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c837-131">For more information about language modes, see [about_Language_modes](/powershell/module/microsoft.powershell.core/about/about_language_modes).</span></span>

### <a name="choose-the-jea-identity"></a><span data-ttu-id="2c837-132">JEA ID を選択する</span><span class="sxs-lookup"><span data-stu-id="2c837-132">Choose the JEA identity</span></span>

<span data-ttu-id="2c837-133">バックグラウンドで、接続ユーザーのコマンドの実行中に、JEA は使用する ID (アカウント) が必要です。</span><span class="sxs-lookup"><span data-stu-id="2c837-133">Behind the scenes, JEA needs an identity (account) to use when running a connected user's commands.</span></span>
<span data-ttu-id="2c837-134">セッション構成ファイルには、JEA が使う ID を定義します。</span><span class="sxs-lookup"><span data-stu-id="2c837-134">You define which identity JEA uses in the session configuration file.</span></span>

#### <a name="local-virtual-account"></a><span data-ttu-id="2c837-135">ローカル仮想アカウント</span><span class="sxs-lookup"><span data-stu-id="2c837-135">Local Virtual Account</span></span>

<span data-ttu-id="2c837-136">ローカル仮想アカウントは、JEA エンドポイント用に定義されているすべてのロールがローカル マシンの管理に使われ、ローカル管理者アカウントがコマンドを正常に実行するために十分である場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="2c837-136">Local virtual accounts are useful when all roles defined for the JEA endpoint are used to manage the local machine and a local administrator account is sufficient to run the commands successfully.</span></span>
<span data-ttu-id="2c837-137">仮想アカウントは、特定のユーザーに固有の一時的なアカウントであり、PowerShell セッションの期間中にのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="2c837-137">Virtual accounts are temporary accounts that are unique to a specific user and only last for the duration of their PowerShell session.</span></span> <span data-ttu-id="2c837-138">メンバー サーバーまたはワークステーションでは、仮想アカウントはローカル コンピューターの **Administrators** グループに属しています。</span><span class="sxs-lookup"><span data-stu-id="2c837-138">On a member server or workstation, virtual accounts belong to the local computer's **Administrators** group.</span></span> <span data-ttu-id="2c837-139">Active Directory ドメイン コントローラーでは、仮想アカウントはドメインの **Domain Admins** グループに属しています。</span><span class="sxs-lookup"><span data-stu-id="2c837-139">On an Active Directory Domain Controller, virtual accounts belong to the domain's **Domain Admins** group.</span></span>

```powershell
# Setting the session to use a virtual account
RunAsVirtualAccount = $true
```

<span data-ttu-id="2c837-140">セッション構成で定義されているロールに完全な管理権限が必要ない場合は、仮想アカウントが属するセキュリティ グループを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c837-140">If the roles defined by the session configuration don't require full administrative privilege, you can specify the security groups to which the virtual account will belong.</span></span> <span data-ttu-id="2c837-141">メンバー サーバーまたはワークステーションでは、ドメインのグループではなくローカル グループからセキュリティ グループを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c837-141">On a member server or workstation, the specified security groups must be local groups, not groups from a domain.</span></span>

<span data-ttu-id="2c837-142">1 つ以上のセキュリティ グループを指定すると、その仮想アカウントはローカル グループまたはドメイン管理者グループには割り当てられません。</span><span class="sxs-lookup"><span data-stu-id="2c837-142">When one or more security groups are specified, the virtual account isn't assigned to the local or domain administrators group.</span></span>

```powershell
# Setting the session to use a virtual account that only belongs to the NetworkOperator and NetworkAuditor local groups
RunAsVirtualAccount = $true
RunAsVirtualAccountGroups = 'NetworkOperator', 'NetworkAuditor'
```

> [!NOTE]
> <span data-ttu-id="2c837-143">仮想アカウントには、ローカル サーバーのセキュリティ ポリシーで、サービスとしてログオンが一時的に付与されます。</span><span class="sxs-lookup"><span data-stu-id="2c837-143">Virtual accounts are temporarily granted the Logon as a service right in the local server security policy.</span></span> <span data-ttu-id="2c837-144">指定されている VirtualAccountGroups の 1 つにポリシーでこれが既に付与されている場合、個別の仮想アカウントがポリシーに追加されたり、ポリシーから削除されたりすることがなくなります。</span><span class="sxs-lookup"><span data-stu-id="2c837-144">If one of the VirtualAccountGroups specified has already been granted this right in the policy, the individual virtual account will no longer be added and removed from the policy.</span></span> <span data-ttu-id="2c837-145">セキュリティ ポリシーの改訂が念入りに監査されるドメイン コントローラーのようなシナリオで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2c837-145">This can be useful in scenarios such as domain controllers where revisions to the domain controller security policy are closely audited.</span></span> <span data-ttu-id="2c837-146">これは、2018 年 11 月以降のロールアップが適用された Windows Server 2016 と、2019 年 1 月以降のロールアップが適用された Windows Server 2019 でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="2c837-146">This is only available in Windows Server 2016 with the November 2018 or later rollup and Windows Server 2019 with the January 2019 or later rollup.</span></span>

#### <a name="group-managed-service-account"></a><span data-ttu-id="2c837-147">グループ管理サービス アカウント</span><span class="sxs-lookup"><span data-stu-id="2c837-147">Group-managed service account</span></span>

<span data-ttu-id="2c837-148">グループ管理サービス アカウント (GMSA) とは、JEA ユーザーがファイル共有や Web サービスなどのネットワーク リソースにアクセスする必要がある場合の使用に適した ID です。</span><span class="sxs-lookup"><span data-stu-id="2c837-148">A group-managed service account (GMSA) is the appropriate identity to use when JEA users need to access network resources such as file shares and web services.</span></span> <span data-ttu-id="2c837-149">GMSA では、ドメイン内の任意のコンピューター上のリソースに対する認証に使用するドメイン ID を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="2c837-149">GMSAs give you a domain identity that is used to authenticate with resources on any machine within the domain.</span></span> <span data-ttu-id="2c837-150">GMSA によって提供される権限は、ユーザーがアクセスするリソースによって決まります。</span><span class="sxs-lookup"><span data-stu-id="2c837-150">The rights that a GMSA provides are determined by the resources you're accessing.</span></span> <span data-ttu-id="2c837-151">コンピューターまたはサービスの管理者が明示的に GMSA に管理者権限を付与しない限り、ユーザーにはコンピューターまたはサービスに対する管理者権限は付与されません。</span><span class="sxs-lookup"><span data-stu-id="2c837-151">You don't have admin rights on any machines or services unless the machine or service administrator has explicitly granted those rights to the GMSA.</span></span>

```powershell
# Configure JEA sessions to use the GMSA in the local computer's domain
# with the sAMAccountName of 'MyJEAGMSA'
GroupManagedServiceAccount = 'Domain\MyJEAGMSA'
```

<span data-ttu-id="2c837-152">GMSA は必要な場合のみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c837-152">GMSAs should only be used when necessary:</span></span>

- <span data-ttu-id="2c837-153">GMSA を使用した場合、アクションをユーザーまでたどることは困難です。</span><span class="sxs-lookup"><span data-stu-id="2c837-153">It's difficult to trace back actions to a user when using a GMSA.</span></span> <span data-ttu-id="2c837-154">どのユーザーにも、同じ実行者 ID が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c837-154">Every user shares the same run-as identity.</span></span> <span data-ttu-id="2c837-155">個々のユーザーとそのアクションの関連付けを確認するには、PowerShell セッションのトランスクリプトとログを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c837-155">You must review PowerShell session transcripts and logs to correlate individual users with their actions.</span></span>

- <span data-ttu-id="2c837-156">GMSA は、接続しているユーザーがアクセスする必要のない、多くのネットワーク リソースにアクセスできる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2c837-156">The GMSA may have access to many network resources that the connecting user doesn't need access to.</span></span> <span data-ttu-id="2c837-157">常に最小限の特権の原則に従って、JEA セッションで有効なアクセス許可を制限してください。</span><span class="sxs-lookup"><span data-stu-id="2c837-157">Always try to limit effective permissions in a JEA session to follow the principle of least privilege.</span></span>

> [!NOTE]
> <span data-ttu-id="2c837-158">グループ管理サービス アカウントは、PowerShell 5.1 以降を使用した、ドメインに参加しているコンピューターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2c837-158">Group managed service accounts are only available on domain-joined machines using PowerShell 5.1 or newer.</span></span>

<span data-ttu-id="2c837-159">JEA セッションのセキュリティ保護の詳細については、[セキュリティに関する考慮事項](security-considerations.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c837-159">For more information about securing a JEA session, see the [security considerations](security-considerations.md) article.</span></span>

### <a name="session-transcripts"></a><span data-ttu-id="2c837-160">セッションのトランスクリプト</span><span class="sxs-lookup"><span data-stu-id="2c837-160">Session transcripts</span></span>

<span data-ttu-id="2c837-161">ユーザー セッションのトランスクリプトを自動的に記録するには、JEA エンドポイントを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2c837-161">It's recommended that you configure a JEA endpoint to automatically record transcripts of users' sessions.</span></span> <span data-ttu-id="2c837-162">PowerShell セッションのトランスクリプトには、接続しているユーザー、そのユーザーに割り当てられている実行 ID、そのユーザーによって実行されたコマンドに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2c837-162">PowerShell session transcripts contain information about the connecting user, the run as identity assigned to them, and the commands run by the user.</span></span> <span data-ttu-id="2c837-163">これは、システムに特定の変更を行ったユーザーを把握する必要がある監査チームに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="2c837-163">They can be useful to an auditing team who needs to understand who made a specific change to a system.</span></span>

<span data-ttu-id="2c837-164">セッション構成ファイルで自動トランスクリプトを構成するには、トランスクリプトを保存するフォルダーへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c837-164">To configure automatic transcription in the session configuration file, provide a path to a folder where the transcripts should be stored.</span></span>

```powershell
TranscriptDirectory = 'C:\ProgramData\JEAConfiguration\Transcripts'
```

<span data-ttu-id="2c837-165">トランスクリプトは、**ローカル システム** アカウントによってフォルダーに書き込まれるので、このアカウントにはこのディレクトリに対する読み書きのアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="2c837-165">Transcripts are written to the folder by the **Local System** account, which requires read and write access to the directory.</span></span> <span data-ttu-id="2c837-166">標準ユーザーは、このフォルダーにアクセスできないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c837-166">Standard users should have no access to the folder.</span></span> <span data-ttu-id="2c837-167">トランスクリプトを監査できるセキュリティ管理者の数は制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c837-167">Limit the number of security administrators that have access to audit the transcripts.</span></span>

### <a name="user-drive"></a><span data-ttu-id="2c837-168">ユーザー ドライブ</span><span class="sxs-lookup"><span data-stu-id="2c837-168">User drive</span></span>

<span data-ttu-id="2c837-169">接続しているユーザーが、JEA エンドポイントにファイルをコピーしたり、そこからコピーする必要がある場合、セッション構成ファイルでユーザー ドライブを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2c837-169">If your connecting users need to copy files to or from the JEA endpoint, you can enable the user drive in the session configuration file.</span></span> <span data-ttu-id="2c837-170">ユーザー ドライブは、接続しているユーザーごとに固有のフォルダーにマップされた **PSDrive** です。</span><span class="sxs-lookup"><span data-stu-id="2c837-170">The user drive is a **PSDrive** that is mapped to a unique folder for each connecting user.</span></span> <span data-ttu-id="2c837-171">このフォルダーでは、ユーザーにファイル システム全体へのアクセス権を与えたり、FileSystem プロバイダーを公開したりせずに、ユーザーはシステムからファイルをコピーしたり、システムにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="2c837-171">This folder allows users to copy files to or from the system without giving them access to the full file system or exposing the FileSystem provider.</span></span> <span data-ttu-id="2c837-172">ユーザー ドライブの内容は、ネットワーク接続が中断される場合に備えて、セッションの間は保持されます。</span><span class="sxs-lookup"><span data-stu-id="2c837-172">The user drive contents are persistent across sessions to accommodate situations where network connectivity may be interrupted.</span></span>

```powershell
MountUserDrive = $true
```

<span data-ttu-id="2c837-173">既定では、ユーザー ドライブを使用することで、ユーザーごとに最大 50 MB のデータを格納できます。</span><span class="sxs-lookup"><span data-stu-id="2c837-173">By default, the user drive allows you to store a maximum of 50MB of data per user.</span></span> <span data-ttu-id="2c837-174">*UserDriveMaximumSize* フィールドで、ユーザーが使用できるデータの量を制限できます。</span><span class="sxs-lookup"><span data-stu-id="2c837-174">You can limit the amount of data a user can consume with the *UserDriveMaximumSize* field.</span></span>

```powershell
# Enables the user drive with a per-user limit of 500MB (524288000 bytes)
MountUserDrive = $true
UserDriveMaximumSize = 524288000
```

<span data-ttu-id="2c837-175">ユーザー ドライブにデータを永続的に保持しない場合は、システムにタスクをスケジュールして、毎晩フォルダーを自動的にクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="2c837-175">If you don't want data in the user drive to be persistent, you can configure a scheduled task on the system to automatically clean up the folder every night.</span></span>

> [!NOTE]
> <span data-ttu-id="2c837-176">ユーザー ドライブを使用できるのは、PowerShell 5.1 以降のみです。</span><span class="sxs-lookup"><span data-stu-id="2c837-176">The user drive is only available in PowerShell 5.1 or newer.</span></span>

<span data-ttu-id="2c837-177">PSDrives の詳細については、[PowerShell ドライブの管理](/powershell/scripting/samples/managing-windows-powershell-drives)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c837-177">For more information about PSDrives, see [Managing PowerShell drives](/powershell/scripting/samples/managing-windows-powershell-drives).</span></span>

### <a name="role-definitions"></a><span data-ttu-id="2c837-178">ロールの定義</span><span class="sxs-lookup"><span data-stu-id="2c837-178">Role definitions</span></span>

<span data-ttu-id="2c837-179">セッション構成ファイルのロールの定義では、**ロール**への**ユーザー**のマッピングを定義します。</span><span class="sxs-lookup"><span data-stu-id="2c837-179">Role definitions in a session configuration file define the mapping of **users** to **roles**.</span></span> <span data-ttu-id="2c837-180">このフィールドに含まれるすべてのユーザーまたはグループには、登録時に JEA エンドポイントへのアクセス許可が自動的に付与されます。</span><span class="sxs-lookup"><span data-stu-id="2c837-180">Every user or group included in this field is granted permission to the JEA endpoint when it's registered.</span></span>
<span data-ttu-id="2c837-181">各ユーザーまたはグループは、ハッシュ テーブルのキーとして含まれるのは 1 回だけですが、複数のロールを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="2c837-181">Each user or group can be included as a key in the hashtable only once, but can be assigned multiple roles.</span></span> <span data-ttu-id="2c837-182">ロール機能の名前は、ロール機能ファイルの名前から `.psrc` 拡張子を除いたものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c837-182">The name of the role capability should be the name of the role capability file, without the `.psrc` extension.</span></span>

```powershell
RoleDefinitions = @{
    'CONTOSO\JEA_DNS_ADMINS'    = @{ RoleCapabilities = 'DnsAdmin', 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_OPERATORS' = @{ RoleCapabilities = 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_AUDITORS'  = @{ RoleCapabilities = 'DnsAuditor' }
}
```

<span data-ttu-id="2c837-183">ユーザーがロール定義の複数のグループに所属している場合、それぞれのロールのアクセス許可を付与されます。</span><span class="sxs-lookup"><span data-stu-id="2c837-183">If a user belongs to more than one group in the role definition, they get access to the roles of each.</span></span> <span data-ttu-id="2c837-184">2 つのロールに同じコマンドレットへのアクセスが許可されている場合、最も制限の少ないパラメーター セットがユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="2c837-184">When two roles grant access to the same cmdlets, the most permissive parameter set is granted to the user.</span></span>

<span data-ttu-id="2c837-185">ロール定義フィールドでローカル ユーザーまたはグループを指定する場合は、必ず (**localhost** やワイルドカードではなく) コンピューター名を指定してください。</span><span class="sxs-lookup"><span data-stu-id="2c837-185">When specifying local users or groups in the role definitions field, be sure to use the computer name, not **localhost** or wildcards.</span></span> <span data-ttu-id="2c837-186">コンピューター名を確認するには、`$env:COMPUTERNAME` 変数を調べます。</span><span class="sxs-lookup"><span data-stu-id="2c837-186">You can check the computer name by inspecting the `$env:COMPUTERNAME` variable.</span></span>

```powershell
RoleDefinitions = @{
    'MyComputerName\MyLocalGroup' = @{ RoleCapabilities = 'DnsAuditor' }
}
```

### <a name="role-capability-search-order"></a><span data-ttu-id="2c837-187">ロール機能の検索順序</span><span class="sxs-lookup"><span data-stu-id="2c837-187">Role capability search order</span></span>

<span data-ttu-id="2c837-188">上の例で示されているように、ロール機能はロール機能ファイルのベース名によって参照されます。</span><span class="sxs-lookup"><span data-stu-id="2c837-188">As shown in the example above, role capabilities are referenced by the base name of the role capability file.</span></span> <span data-ttu-id="2c837-189">ファイルのベース名とは、拡張子を除いたファイル名です。</span><span class="sxs-lookup"><span data-stu-id="2c837-189">The base name of a file is the filename without the extension.</span></span> <span data-ttu-id="2c837-190">システムに同じ名前のロール機能が複数ある場合、PowerShell は暗黙的な検索順序を使って有効なロール機能ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="2c837-190">If multiple role capabilities are available on the system with the same name, PowerShell uses its implicit search order to select the effective role capability file.</span></span> <span data-ttu-id="2c837-191">JEA は、同じ名前のすべてのロール機能ファイルにはアクセスを付与**しません**。</span><span class="sxs-lookup"><span data-stu-id="2c837-191">JEA does **not** give access to all role capability files with the same name.</span></span>

<span data-ttu-id="2c837-192">JEA は `$env:PSModulePath` 環境変数を使用して、ロール機能ファイルをスキャンするパスを決定します。</span><span class="sxs-lookup"><span data-stu-id="2c837-192">JEA uses the `$env:PSModulePath` environment variable to determine which paths to scan for role capability files.</span></span> <span data-ttu-id="2c837-193">それらのパス内では、JEA は "RoleCapabilities" サブフォルダを含む有効な PowerShell モジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c837-193">Within each of those paths, JEA looks for valid PowerShell modules that contain a "RoleCapabilities" subfolder.</span></span> <span data-ttu-id="2c837-194">モジュールのインポートと同様に、JEA は同じ名前のカスタム ロール機能よりも Windows に同梱されているロール機能を優先します。</span><span class="sxs-lookup"><span data-stu-id="2c837-194">As with importing modules, JEA prefers role capabilities that are shipped with Windows to custom role capabilities with the same name.</span></span>

<span data-ttu-id="2c837-195">競合する他のすべての名前の優先順位は、Windows によってファイルがディレクトリ内で列挙される順序によって決まります。</span><span class="sxs-lookup"><span data-stu-id="2c837-195">For all other naming conflicts, precedence is determined by the order in which Windows enumerates the files in the directory.</span></span> <span data-ttu-id="2c837-196">この順序は、アルファベット順であるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="2c837-196">The order isn't guaranteed to be alphabetical.</span></span> <span data-ttu-id="2c837-197">指定した名前と一致する最初に検出されたロール機能ファイルは、接続ユーザーに対して使われます。</span><span class="sxs-lookup"><span data-stu-id="2c837-197">The first role capability file found that matches the specified name is used for the connecting user.</span></span> <span data-ttu-id="2c837-198">ロール機能の検索順序は決定論的ではないので、ロール機能のファイル名を一意にすることを**強くお勧め**します。</span><span class="sxs-lookup"><span data-stu-id="2c837-198">Since the role capability search order isn't deterministic, it's **strongly recommended** that role capabilities have unique filenames.</span></span>

### <a name="conditional-access-rules"></a><span data-ttu-id="2c837-199">条件付きアクセス規則</span><span class="sxs-lookup"><span data-stu-id="2c837-199">Conditional access rules</span></span>

<span data-ttu-id="2c837-200">**RoleDefinitions** フィールドに含まれるすべてのユーザーとグループは、JEA エンドポイントへのアクセスが自動的に許可されます。</span><span class="sxs-lookup"><span data-stu-id="2c837-200">All users and groups included in the **RoleDefinitions** field are automatically granted access to JEA endpoints.</span></span> <span data-ttu-id="2c837-201">条件付きアクセス規則を使うと、このアクセスを調整して、ユーザーに割り当て済みのロールに影響を与えない別のセキュリティ グループに、ユーザーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2c837-201">Conditional access rules allow you to refine this access and require users to belong to additional security groups that don't impact the roles to which they're assigned.</span></span> <span data-ttu-id="2c837-202">これは、Just-In-Time 特権アクセスの管理ソリューション、スマート カード認証、またはその他の多要素認証ソリューションを JEA と統合する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2c837-202">This is useful when you want to integrate a just-in-time privileged access management solution, smartcard authentication, or other multifactor authentication solution with JEA.</span></span>

<span data-ttu-id="2c837-203">条件付きアクセス規則は、セッション構成ファイルの RequiredGroups フィールドで定義します。</span><span class="sxs-lookup"><span data-stu-id="2c837-203">Conditional access rules are defined in the RequiredGroups field in a session configuration file.</span></span>
<span data-ttu-id="2c837-204">そこでは、"And" キーと "Or" キーを使って規則を作成するハッシュ テーブル (必要に応じて入れ子になっている) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2c837-204">There, you can provide a hashtable (optionally nested) that uses 'And' and 'Or' keys to construct your rules.</span></span> <span data-ttu-id="2c837-205">このフィールドの使用方法について、次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="2c837-205">Here are some examples of how to use this field:</span></span>

```powershell
# Example 1: Connecting users must belong to a security group called "elevated-jea"
RequiredGroups = @{ And = 'elevated-jea' }

# Example 2: Connecting users must have signed on with 2 factor authentication or a smart card
# The 2 factor authentication group name is "2FA-logon" and the smart card group name is "smartcard-logon"
RequiredGroups = @{ Or = '2FA-logon', 'smartcard-logon' }

# Example 3: Connecting users must elevate into "elevated-jea" with their JIT system and have logged on with 2FA or a smart card
RequiredGroups = @{ And = 'elevated-jea', @{ Or = '2FA-logon', 'smartcard-logon' }}
```

> [!NOTE]
> <span data-ttu-id="2c837-206">条件付きアクセス規則を使用できるのは、PowerShell 5.1 以降のみです。</span><span class="sxs-lookup"><span data-stu-id="2c837-206">Conditional access rules are only available in PowerShell 5.1 or newer.</span></span>

### <a name="other-properties"></a><span data-ttu-id="2c837-207">他のプロパティ</span><span class="sxs-lookup"><span data-stu-id="2c837-207">Other properties</span></span>

<span data-ttu-id="2c837-208">セッション構成ファイルではロール機能ファイルで実行できるすべてのことを実行できますが、接続しているユーザーが別のコマンドにアクセスできるようにする機能だけはありません。</span><span class="sxs-lookup"><span data-stu-id="2c837-208">Session configuration files can also do everything a role capability file can do, just without the ability to give connecting users access to different commands.</span></span> <span data-ttu-id="2c837-209">すべてのユーザーに特定のコマンドレット、関数、またはプロバイダーへのアクセスを許可する場合は、セッション構成ファイルで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2c837-209">If you want to allow all users access to specific cmdlets, functions, or providers, you can do so right in the session configuration file.</span></span>
<span data-ttu-id="2c837-210">セッション構成ファイルでサポートされているプロパティの一覧については、`Get-Help New-PSSessionConfigurationFile -Full` を実行してください。</span><span class="sxs-lookup"><span data-stu-id="2c837-210">For a full list of supported properties in the session configuration file, run `Get-Help New-PSSessionConfigurationFile -Full`.</span></span>

## <a name="testing-a-session-configuration-file"></a><span data-ttu-id="2c837-211">セッション構成ファイルのテスト</span><span class="sxs-lookup"><span data-stu-id="2c837-211">Testing a session configuration file</span></span>

<span data-ttu-id="2c837-212">[Test-PSSessionConfigurationFile](/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile) コマンドレットを使って、セッション構成をテストできます。</span><span class="sxs-lookup"><span data-stu-id="2c837-212">You can test a session configuration using the [Test-PSSessionConfigurationFile](/powershell/module/microsoft.powershell.core/test-pssessionconfigurationfile) cmdlet.</span></span> <span data-ttu-id="2c837-213">`.pssc` ファイルを手動で編集した場合は、セッション構成ファイルをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2c837-213">It's recommended that you test your session configuration file if you've manually edited the `.pssc` file.</span></span> <span data-ttu-id="2c837-214">テストすることにより、構文が正しいことが確認されます。</span><span class="sxs-lookup"><span data-stu-id="2c837-214">Testing ensures the syntax is correct.</span></span> <span data-ttu-id="2c837-215">このテストが失敗するセッション構成ファイルは、システムに登録できません。</span><span class="sxs-lookup"><span data-stu-id="2c837-215">If a session configuration file fails this test, it can't be registered on the system.</span></span>

## <a name="sample-session-configuration-file"></a><span data-ttu-id="2c837-216">セッション構成ファイルのサンプル</span><span class="sxs-lookup"><span data-stu-id="2c837-216">Sample session configuration file</span></span>

<span data-ttu-id="2c837-217">JEA のセッション構成を作成して検証する方法を、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="2c837-217">The following example shows how to create and validate a session configuration for JEA.</span></span> <span data-ttu-id="2c837-218">作成したロール定義は、使いやすくまた読みやすくするため、`$roles` 変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="2c837-218">The role definitions are created and stored in the `$roles` variable for convenience and readability.</span></span> <span data-ttu-id="2c837-219">ただし、必ずこのようにする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2c837-219">It isn't a requirement to do so.</span></span>

```powershell
$roles = @{
    'CONTOSO\JEA_DNS_ADMINS'    = @{ RoleCapabilities = 'DnsAdmin', 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_OPERATORS' = @{ RoleCapabilities = 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_AUDITORS'  = @{ RoleCapabilities = 'DnsAuditor' }
}

New-PSSessionConfigurationFile -SessionType RestrictedRemoteServer -Path .\JEAConfig.pssc -RunAsVirtualAccount -TranscriptDirectory 'C:\ProgramData\JEAConfiguration\Transcripts' -RoleDefinitions $roles -RequiredGroups @{ Or = '2FA-logon', 'smartcard-logon' }
Test-PSSessionConfigurationFile -Path .\JEAConfig.pssc # should yield True
```

## <a name="updating-session-configuration-files"></a><span data-ttu-id="2c837-220">セッション構成ファイルの更新</span><span class="sxs-lookup"><span data-stu-id="2c837-220">Updating session configuration files</span></span>

<span data-ttu-id="2c837-221">JEA セッション構成で、ロールへのユーザーのマッピングなどのプロパティを変更するには、[登録解除](register-jea.md#unregistering-jea-configurations)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c837-221">To change the properties of a JEA session configuration, including the mapping of users to roles, you must [unregister](register-jea.md#unregistering-jea-configurations).</span></span> <span data-ttu-id="2c837-222">その後、更新されたセッション構成ファイルを使用して JEA セッション構成を[再登録](register-jea.md)します。</span><span class="sxs-lookup"><span data-stu-id="2c837-222">Then, [re-register](register-jea.md) the JEA session configuration using an updated session configuration file.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2c837-223">次のステップ</span><span class="sxs-lookup"><span data-stu-id="2c837-223">Next steps</span></span>

- [<span data-ttu-id="2c837-224">JEA 構成を登録する</span><span class="sxs-lookup"><span data-stu-id="2c837-224">Register a JEA configuration</span></span>](register-jea.md)
- [<span data-ttu-id="2c837-225">ロール機能</span><span class="sxs-lookup"><span data-stu-id="2c837-225">Author JEA roles</span></span>](role-capabilities.md)
