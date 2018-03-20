---
ms.date: 2017-06-12
author: rpsqrd
ms.topic: conceptual
keywords: "JEA, PowerShell, セキュリティ"
title: "JEA セッションの構成"
ms.openlocfilehash: c475a90a59d91b074f954cfb656b00142444c052
ms.sourcegitcommit: 99227f62dcf827354770eb2c3e95c5cf6a3118b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="jea-session-configurations"></a><span data-ttu-id="b89d8-103">JEA セッションの構成</span><span class="sxs-lookup"><span data-stu-id="b89d8-103">JEA Session Configurations</span></span>

> <span data-ttu-id="b89d8-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="b89d8-104">Applies to: Windows PowerShell 5.0</span></span>

<span data-ttu-id="b89d8-105">JEA エンドポイントは、PowerShell セッション構成ファイルを特定の方法で作成して登録することにより、システムに登録されます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-105">A JEA endpoint is registered on a system by creating and registering a PowerShell session configuration file in a specific way.</span></span>
<span data-ttu-id="b89d8-106">セッションの構成によって、"*誰が*" JEA エンドポイントを使用でき、どのロールにアクセスできるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="b89d8-106">Session configurations determine *who* can use the JEA endpoint, and which role(s) they will have access to.</span></span>
<span data-ttu-id="b89d8-107">また、JEA セッション内の任意のロールのユーザーに適用されるグローバル設定も定義できます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-107">They also define global settings that apply to users of any role in the JEA session.</span></span>

<span data-ttu-id="b89d8-108">このトピックでは、PowerShell セッション構成ファイルを作成し、JEA エンドポイントを登録する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b89d8-108">This topic describes how to create a PowerShell session configuration file and register a JEA endpoint.</span></span>

## <a name="create-a-session-configuration-file"></a><span data-ttu-id="b89d8-109">セッション構成ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="b89d8-109">Create a session configuration file</span></span>

<span data-ttu-id="b89d8-110">JEA エンドポイントを登録するには、そのエンドポイントを構成する方法を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b89d8-110">In order to register a JEA endpoint, you need to specify how that endpoint should be configured.</span></span>
<span data-ttu-id="b89d8-111">ここでは多くのオプションについて考慮する必要がありますが、最も重要なものは、JEA エンドポイントにアクセスできる必要があるユーザー、そのユーザーに割り当てられるロール、JEA が内部で使用する ID、JEA エンドポイントの名前です。</span><span class="sxs-lookup"><span data-stu-id="b89d8-111">There are many options to consider here, the most important of which being who should have access to the JEA endpoint, which roles will they be assigned, which identity will JEA use under the covers, and what will be the name of the JEA endpoint.</span></span>
<span data-ttu-id="b89d8-112">これらはすべて PowerShell セッション構成ファイルで定義されており、これは .pssc 拡張子の付いた PowerShell データ ファイルです。</span><span class="sxs-lookup"><span data-stu-id="b89d8-112">These are all defined in a PowerShell session configuration file, which is a PowerShell data file ending with a .pssc extension.</span></span>

<span data-ttu-id="b89d8-113">JEA エンドポイントのスケルトン セッション構成ファイルを作成するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="b89d8-113">To create a skeleton session configuration file for JEA endpoints, run the following command.</span></span>

```powershell
New-PSSessionConfigurationFile -SessionType RestrictedRemoteServer -Path .\MyJEAEndpoint.pssc
```

> [!TIP]
> <span data-ttu-id="b89d8-114">既定では、スケルトン ファイルには、最も一般的な構成オプションのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-114">Only the most common configuration options are included in the skeleton file by default.</span></span>
> <span data-ttu-id="b89d8-115">適用できるすべての設定を生成される PSSC に含めるには、`-Full` スイッチを使います。</span><span class="sxs-lookup"><span data-stu-id="b89d8-115">Use the `-Full` switch to include all applicable settings in the generated PSSC.</span></span>

<span data-ttu-id="b89d8-116">セッション構成ファイルは、任意のテキスト エディターで開くことができます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-116">You can open the session configuration file in any text editor.</span></span>
<span data-ttu-id="b89d8-117">`-SessionType RestrictedRemoteServer` フィールドは、セッション構成がセキュリティ保護された管理のために JEA によって使われることを示します。</span><span class="sxs-lookup"><span data-stu-id="b89d8-117">The `-SessionType RestrictedRemoteServer` field indicates that the session configuration will be used by JEA for secure management.</span></span>
<span data-ttu-id="b89d8-118">このようにして構成されたセッションは、[NoLanguage モード](https://technet.microsoft.com/library/dn433292.aspx)で動作し、次の 8 つの既定のコマンド (およびエイリアス) のみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-118">Sessions configured this way will operate in [NoLanguage mode](https://technet.microsoft.com/library/dn433292.aspx) and only have the following 8 default commands (and aliases) available:</span></span>

- <span data-ttu-id="b89d8-119">Clear-Host (cls、clear)</span><span class="sxs-lookup"><span data-stu-id="b89d8-119">Clear-Host (cls, clear)</span></span>
- <span data-ttu-id="b89d8-120">Exit-PSSession (exsn、exit)</span><span class="sxs-lookup"><span data-stu-id="b89d8-120">Exit-PSSession (exsn, exit)</span></span>
- <span data-ttu-id="b89d8-121">Get-Command (gcm)</span><span class="sxs-lookup"><span data-stu-id="b89d8-121">Get-Command (gcm)</span></span>
- <span data-ttu-id="b89d8-122">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="b89d8-122">Get-FormatData</span></span>
- <span data-ttu-id="b89d8-123">Get-Help</span><span class="sxs-lookup"><span data-stu-id="b89d8-123">Get-Help</span></span>
- <span data-ttu-id="b89d8-124">Measure-Object (measure)</span><span class="sxs-lookup"><span data-stu-id="b89d8-124">Measure-Object (measure)</span></span>
- <span data-ttu-id="b89d8-125">Out-Default</span><span class="sxs-lookup"><span data-stu-id="b89d8-125">Out-Default</span></span>
- <span data-ttu-id="b89d8-126">Select-Object (select)</span><span class="sxs-lookup"><span data-stu-id="b89d8-126">Select-Object (select)</span></span>

<span data-ttu-id="b89d8-127">PowerShell プロバイダーおよび外部プログラム (実行可能ファイル、スクリプトなど) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="b89d8-127">No PowerShell providers are available, nor are any external programs (executables, scripts, etc.).</span></span>

<span data-ttu-id="b89d8-128">JEA セッションの構成には他にもいくつかフィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="b89d8-128">There are several other fields you will want to configure for the JEA session.</span></span>
<span data-ttu-id="b89d8-129">それについては以下のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="b89d8-129">They are covered in the following sections.</span></span>

### <a name="choose-the-jea-identity"></a><span data-ttu-id="b89d8-130">JEA ID を選択する</span><span class="sxs-lookup"><span data-stu-id="b89d8-130">Choose the JEA identity</span></span>

<span data-ttu-id="b89d8-131">バックグラウンドで、接続ユーザーのコマンドの実行中に、JEA は使用する ID (アカウント) が必要です。</span><span class="sxs-lookup"><span data-stu-id="b89d8-131">Behind the scenes, JEA needs an identity (account) to use when running a connected user's commands.</span></span>
<span data-ttu-id="b89d8-132">JEA が使う ID をセッション構成ファイルで決定します。</span><span class="sxs-lookup"><span data-stu-id="b89d8-132">You decide which identity JEA will use in the session configuration file.</span></span>

#### <a name="local-virtual-account"></a><span data-ttu-id="b89d8-133">ローカル仮想アカウント</span><span class="sxs-lookup"><span data-stu-id="b89d8-133">Local Virtual Account</span></span>

<span data-ttu-id="b89d8-134">この JEA エンドポイントによってサポートされるすべてのロールがローカル マシンの管理に使われ、ローカル管理者アカウントがコマンドを正常に実行するために十分である場合は、ローカル仮想アカウントを使うように JEA を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b89d8-134">If the roles supported by this JEA endpoint are all used to manage the local machine, and a local administrator account is sufficient to run the commands succesfully, you should configure JEA to use a local virtual account.</span></span>
<span data-ttu-id="b89d8-135">仮想アカウントは、特定のユーザーに固有の一時的なアカウントであり、PowerShell セッションの期間中にのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="b89d8-135">Virtual accounts are temporary accounts that are unique to a specific user and only last for the duration of their PowerShell session.</span></span>
<span data-ttu-id="b89d8-136">メンバー サーバーまたはワークステーションでは、仮想アカウントはローカル コンピューターの **Administrators** グループに属しており、最も多くのシステム リソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-136">On a member server or workstation, virtual accounts belong to the local computer's **Administrators** group, and have access to most system resources.</span></span>
<span data-ttu-id="b89d8-137">Active Directory ドメイン コントローラーでは、仮想アカウントはドメインの **Domain Admins** グループに属しています。</span><span class="sxs-lookup"><span data-stu-id="b89d8-137">On an Active Directory Domain Controller, virtual accounts belong to the domain's **Domain Admins** group.</span></span>

```powershell
# Setting the session to use a virtual account
RunAsVirtualAccount = $true
```

<span data-ttu-id="b89d8-138">セッション構成でサポートされているロールにこのような広範な権限が必要ない場合は、仮想アカウントが属するセキュリティ グループを必要に応じて指定できます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-138">If the roles supported by the session configuration do not require such broad privileges, you can optionally specify the security groups to which the virtual account will belong.</span></span>
<span data-ttu-id="b89d8-139">メンバー サーバーまたはワークステーションでは、ドメインのグループではなくローカル グループからセキュリティ グループを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b89d8-139">On a member server or workstation, the specified security groups must be local groups, not groups from a domain.</span></span>

<span data-ttu-id="b89d8-140">1 つまたは複数のセキュリティ グループを指定すると、仮想アカウントはローカル グループまたはドメイン管理者グループに属さなくなります。</span><span class="sxs-lookup"><span data-stu-id="b89d8-140">When one or more security groups is specified, the virtual account will no longer belong to the local or domain administrators group.</span></span>

```powershell
# Setting the session to use a virtual account that only belongs to the NetworkOperator and NetworkAuditor local groups
RunAsVirtualAccount = $true
RunAsVirtualAccountGroups = 'NetworkOperator', 'NetworkAuditor'
```

#### <a name="group-managed-service-account"></a><span data-ttu-id="b89d8-141">グループの管理されたサービス アカウント</span><span class="sxs-lookup"><span data-stu-id="b89d8-141">Group Managed Service Account</span></span>


<span data-ttu-id="b89d8-142">JEA ユーザーが他のコンピューターや Web サービスなどのネットワーク リソースにアクセスする必要があるシナリオでは、グループ管理サービス アカウント (gMSA) の方が使うのに適した ID です。</span><span class="sxs-lookup"><span data-stu-id="b89d8-142">For scenarios requiring the JEA user to access network resources such as other machines or web services, a group managed service account (gMSA) is a more appropriate identity to use.</span></span>
<span data-ttu-id="b89d8-143">gMSA アカウントで提供されるドメイン ID を使って、ドメイン内のコンピューター上のリソースに対する認証を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-143">gMSA accounts give you a domain identity which can be used to authenticate against resources on any machine within the domain.</span></span>
<span data-ttu-id="b89d8-144">gMSA アカウントによって提供される権限は、アクセスするリソースによって決まります。</span><span class="sxs-lookup"><span data-stu-id="b89d8-144">The rights the gMSA account gives you is determined by the resources you are accessing.</span></span>
<span data-ttu-id="b89d8-145">コンピューター/サービスの管理者が明示的に gMSA アカウントに管理者権限を付与しない限り、コンピューターまたはサービスに対する権限を自動的に持つことはありません。</span><span class="sxs-lookup"><span data-stu-id="b89d8-145">You will not automatically have admin rights on any machines or services unless the machine/service administrator has explicitly granted the gMSA account admin privileges.</span></span>

```powershell
# Configure JEA sessions to use the gMSA account in the local computer's domain with the sAMAccountName of 'MyJEAgMSA'
GroupManagedServiceAccount = 'Domain\MyJEAgMSA'
```

<span data-ttu-id="b89d8-146">いくつかの理由でネットワーク リソースへのアクセスが必要なときにのみ、gMSA アカウントを使う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b89d8-146">gMSA accounts should only be used when access to network resources are required for a few reasons:</span></span>

- <span data-ttu-id="b89d8-147">すべてのユーザーが同じ実行 ID を共有しているため、gMSA アカウントを使うと、操作をユーザーまでトレースするのが困難になります。</span><span class="sxs-lookup"><span data-stu-id="b89d8-147">It is harder to trace back actions to a user when using a gMSA account since every user shares the same run-as identity.</span></span> <span data-ttu-id="b89d8-148">PowerShell セッションのトランスクリプトとログを調べて、ユーザーと操作を関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="b89d8-148">You will need to consult PowerShell session transcripts and logs to correlate users with their actions.</span></span>

- <span data-ttu-id="b89d8-149">GMSA アカウントが、接続しているユーザーがアクセスする必要のない多くのネットワーク リソースへのアクセス権を持っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="b89d8-149">The gMSA account may have access to many network resources which the connecting user does not need access to.</span></span> <span data-ttu-id="b89d8-150">常に最小限の特権の原則に従って、JEA セッションで有効なアクセス許可を制限してください。</span><span class="sxs-lookup"><span data-stu-id="b89d8-150">Always try to limit effective permissions in a JEA session to follow the principle of least privilege.</span></span>

> [!NOTE]
> <span data-ttu-id="b89d8-151">グループ管理されたサービス アカウントは、ドメインに参加しているコンピューターにおいてのみ、Windows PowerShell 5.1 以降だけで使用できます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-151">Group managed service accounts are only available in Windows PowerShell 5.1 or newer and on domain-joined machines.</span></span>


#### <a name="more-information-about-run-as-users"></a><span data-ttu-id="b89d8-152">実行ユーザーに関する詳しい情報</span><span class="sxs-lookup"><span data-stu-id="b89d8-152">More information about run as users</span></span>

<span data-ttu-id="b89d8-153">実行 ID と、JEA セッションのセキュリティに対する実行 ID の関与の詳細については、「[security considerations](security-considerations.md)」 (JEA のセキュリティに関する考慮事項) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b89d8-153">Additional information about run as identities and how they factor into the security of a JEA session can be found in the [security considerations](security-considerations.md) article.</span></span>

### <a name="session-transcripts"></a><span data-ttu-id="b89d8-154">セッションのトランスクリプト</span><span class="sxs-lookup"><span data-stu-id="b89d8-154">Session transcripts</span></span>

<span data-ttu-id="b89d8-155">ユーザーのセッションのトランスクリプトを自動的に記録するように、JEA セッション構成ファイルを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b89d8-155">It is recommended that you configure a JEA session configuration file to automatically record transcripts of users' sessions.</span></span>
<span data-ttu-id="b89d8-156">PowerShell セッションのトランスクリプトには、接続しているユーザー、そのユーザーに割り当てられている実行 ID、そのユーザーによって実行されたコマンドに関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-156">PowerShell session transcripts contain information about the connecting user, the run as identity assigned to them, and the commands run by the user.</span></span>
<span data-ttu-id="b89d8-157">システムに対して特定の変更を実行したユーザーを把握する必要がある監査チームに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-157">They can be useful to an auditing team who needs to understand who performed a specific change to a system.</span></span>

<span data-ttu-id="b89d8-158">セッション構成ファイルで自動トランスクリプトを構成するには、トランスクリプトを保存するフォルダーへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b89d8-158">To configure automatic transcription in the session configuration file, provide a path to a folder where the transcripts should be stored.</span></span>

```powershell
TranscriptDirectory = 'C:\ProgramData\JEAConfiguration\Transcripts'
```

<span data-ttu-id="b89d8-159">指定するフォルダーは、その中のデータをユーザーが変更または削除できないように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b89d8-159">The specified folder should be configured to prevent users from modifying or deleting any data in it.</span></span>
<span data-ttu-id="b89d8-160">トランスクリプトはローカル システム アカウントによってフォルダーに書き込まれるので、アカウントにはこのディレクトリの読み取りと書き込みのアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="b89d8-160">Transcripts are written to the folder by the Local System account, which requires read and write access to the directory.</span></span>
<span data-ttu-id="b89d8-161">標準ユーザーがこのフォルダーにアクセスできてはならず、限られた少数のセキュリティ管理者だけがトランスクリプトを監査するためにフォルダーにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b89d8-161">Standard users should have no access to the folder, and a limited set of security administrators should have access to audit the transcripts.</span></span>

### <a name="user-drive"></a><span data-ttu-id="b89d8-162">ユーザー ドライブ</span><span class="sxs-lookup"><span data-stu-id="b89d8-162">User drive</span></span>

<span data-ttu-id="b89d8-163">接続しているユーザーが、コマンドを実行するために、JEA エンドポイントとの間で双方向にファイルをコピーする必要がある場合は、セッション構成ファイルでユーザー ドライブを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-163">If your connecting users will need to copy files to/from the JEA endpoint in order to run a command, you can enable the user drive in the session configuration file.</span></span>
<span data-ttu-id="b89d8-164">ユーザー ドライブは、接続しているユーザーごとに固有のフォルダーにマップされた [PSDrive](https://msdn.microsoft.com/powershell/scripting/getting-started/cookbooks/managing-windows-powershell-drives) です。</span><span class="sxs-lookup"><span data-stu-id="b89d8-164">The user drive is a [PSDrive](https://msdn.microsoft.com/powershell/scripting/getting-started/cookbooks/managing-windows-powershell-drives) that is mapped to a unique folder for each connecting user.</span></span>
<span data-ttu-id="b89d8-165">このフォルダーは、ユーザーがシステムとの間でファイルをコピーするための場所として機能します。完全なファイル システムへのアクセス権は与えられず、FileSystem プロバイダーは公開されません。</span><span class="sxs-lookup"><span data-stu-id="b89d8-165">This folder serves as a space for them to copy files to/from the system, without giving them access to the full file system or exposing the FileSystem provider.</span></span>
<span data-ttu-id="b89d8-166">ユーザー ドライブの内容は、ネットワーク接続が中断される場合に備えて、セッションの間は保持されます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-166">The user drive contents are persistent across sessions to accommodate situations where network connectivity may be interrupted.</span></span>

```powershell
MountUserDrive = $true
```

<span data-ttu-id="b89d8-167">既定では、ユーザー ドライブを使用することで、ユーザーごとに最大 50 MB のデータを格納できます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-167">By default, the user drive allows you to store a maximum of 50MB of data per user.</span></span>
<span data-ttu-id="b89d8-168">*UserDriveMaximumSize* フィールドで、ユーザーが使用できるデータの量を制限できます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-168">You can limit the amount of data a user can consume with the *UserDriveMaximumSize* field.</span></span>

```powershell
# Enables the user drive with a per-user limit of 500MB (524288000 bytes)
MountUserDrive = $true
UserDriveMaximumSize = 524288000
```

<span data-ttu-id="b89d8-169">ユーザー ドライブにデータを永続的に保持しないようにする場合は、システムにスケジュールされたタスクを構成して、毎晩フォルダーを自動的にクリーンアップできます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-169">If you do not want data in the user drive to be persistent, you can configure a scheduled task on the system to automatically clean up the folder every night.</span></span>

> [!NOTE]
> <span data-ttu-id="b89d8-170">ユーザー ドライブを使用できるのは、Windows PowerShell 5.1 以降のみです。</span><span class="sxs-lookup"><span data-stu-id="b89d8-170">The user drive is only available in Windows PowerShell 5.1 or newer.</span></span>

### <a name="role-definitions"></a><span data-ttu-id="b89d8-171">ロールの定義</span><span class="sxs-lookup"><span data-stu-id="b89d8-171">Role definitions</span></span>

<span data-ttu-id="b89d8-172">セッション構成ファイルのロールの定義では、*ロール*への*ユーザー*のマッピングを定義します。</span><span class="sxs-lookup"><span data-stu-id="b89d8-172">Role definitions in a session configuration file define the mapping of *users* to *roles*.</span></span>
<span data-ttu-id="b89d8-173">このフィールドに含まれるすべてのユーザーまたはグループには、登録時に JEA エンドポイントへのアクセス許可を自動的に付与されます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-173">Every user or group included in this field will automatically be granted permission to the JEA endpoint when it is registered.</span></span>
<span data-ttu-id="b89d8-174">各ユーザーまたはグループは、ハッシュ テーブルのキーとして含まれるのは 1 回だけですが、複数のロールを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-174">Each user or group can be included as a key in the hashtable only once, but can be assigned multiple roles.</span></span>
<span data-ttu-id="b89d8-175">ロール機能の名前は、ロール機能ファイルの名前から .psrc 拡張子を除いたものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b89d8-175">The name of the role capability should be the name of the role capability file, without the .psrc extension.</span></span>

```powershell
RoleDefinitions = @{
    'CONTOSO\JEA_DNS_ADMINS'    = @{ RoleCapabilities = 'DnsAdmin', 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_OPERATORS' = @{ RoleCapabilities = 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_AUDITORS'  = @{ RoleCapabilities = 'DnsAuditor' }
}
```

<span data-ttu-id="b89d8-176">ユーザーがロール定義の複数のグループに所属している場合、それぞれのロールのアクセス許可を付与されます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-176">If a user belongs to more than one group in the role definition, they will get access to the roles of each.</span></span>
<span data-ttu-id="b89d8-177">2 つのロールで同じコマンドレットへのアクセスが許可されている場合、最も制限の少ないパラメーター セットがユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-177">If two roles grant access to the same cmdlets, the most permissive parameter set will be granted to the user.</span></span>

<span data-ttu-id="b89d8-178">ロール定義フィールドでローカル ユーザーまたはグループを指定する場合は、円記号の前に必ず (*localhost* や *.* ではなく) コンピューター名を指定してください。</span><span class="sxs-lookup"><span data-stu-id="b89d8-178">When specifying local users or groups in the role definitions field, be sure to use the computer name (not *localhost* or *.*) before the backslash.</span></span>
<span data-ttu-id="b89d8-179">コンピューター名を確認するには、`$env:computername` 変数を調べます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-179">You can check the computer name by inspecting the `$env:computername` variable.</span></span>

```powershell
RoleDefinitions = @{
    'MyComputerName\MyLocalGroup' = @{ RoleCapabilities = 'DnsAuditor' }
}
```

### <a name="role-capability-search-order"></a><span data-ttu-id="b89d8-180">ロール機能の検索順序</span><span class="sxs-lookup"><span data-stu-id="b89d8-180">Role capability search order</span></span>
<span data-ttu-id="b89d8-181">上の例で示されているように、ロール機能はロール機能ファイルのフラット名 (拡張子を除いたファイル名) によって参照されます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-181">As shown in the example above, role capabilities are referenced by the flat name (filename without the extension) of the role capability file.</span></span>
<span data-ttu-id="b89d8-182">システムにおいて同じフラット名で複数のロール機能を使用できる場合、PowerShell は暗黙的な検索順序を使って有効なロール機能ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-182">If multiple role capabilities are available on the system with the same flat name, PowerShell will use its implicit search order to select the effective role capability file.</span></span>
<span data-ttu-id="b89d8-183">同じ名前のすべてのロール機能ファイルにアクセスできるようには**なりません**。</span><span class="sxs-lookup"><span data-stu-id="b89d8-183">It will **not** give access to all role capability files with the same name.</span></span>

<span data-ttu-id="b89d8-184">JEA は `$env:PSModulePath` 環境変数を使用して、ロール機能ファイルをスキャンするパスを決定します。</span><span class="sxs-lookup"><span data-stu-id="b89d8-184">JEA uses the `$env:PSModulePath` environment variable to determine which paths to scan for role capability files.</span></span>
<span data-ttu-id="b89d8-185">各パス内で、JEA は「RoleCapabilities」サブフォルダを含む有効な PowerShell モジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="b89d8-185">Within each of those paths, JEA will look for valid PowerShell modules that contain a "RoleCapabilities" subfolder.</span></span>
<span data-ttu-id="b89d8-186">モジュールのインポートと同様に、JEA は同じ名前のカスタム ロール機能よりも Windows に同梱されているロール機能を優先します。</span><span class="sxs-lookup"><span data-stu-id="b89d8-186">As with importing modules, JEA prefers role capabilities that are shipped with Windows to custom role capabilities with the same name.</span></span>
<span data-ttu-id="b89d8-187">他のすべての名前付け競合の優先順位は、Windows がディレクトリ内のファイルを列挙する順序 (アルファベット順とは限りません) によって決まります。</span><span class="sxs-lookup"><span data-stu-id="b89d8-187">For all other naming conflicts, precedence is determined by the order in which Windows enumerates the files in the directory (not guaranteed to be alphabetically).</span></span>
<span data-ttu-id="b89d8-188">希望するファイル名と一致している、最初に検出されたロール機能ファイルが接続ユーザーに対して使われます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-188">The first role capability file found that matches the desired name will be used for the connecting user.</span></span>

<span data-ttu-id="b89d8-189">2 つ以上のロール機能が同じ名前を共有していると、ロール機能の検索順序は確定的ではないため、コンピューター上のロール機能が固有の名前を持っているか確認することを**強くお勧め**します。</span><span class="sxs-lookup"><span data-stu-id="b89d8-189">Since the role capability search order is not deterministic when two or more role capabilities share the same name, it is **strongly recommended** that you ensure role capabilities have unique names on your machine.</span></span>

### <a name="conditional-access-rules"></a><span data-ttu-id="b89d8-190">条件付きアクセス規則</span><span class="sxs-lookup"><span data-stu-id="b89d8-190">Conditional access rules</span></span>

<span data-ttu-id="b89d8-191">RoleDefinitions フィールドに含まれるすべてのユーザーとグループは、JEA エンドポイントへのアクセスを自動的に許可されます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-191">All users and groups included in the RoleDefinitions field are automatically granted access to JEA endpoints.</span></span>
<span data-ttu-id="b89d8-192">条件付きアクセス規則を使うと、このアクセスを調整して、ユーザーが割り当てられているロールに影響を与えない別のセキュリティ グループにユーザーが属していることを要求できます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-192">Conditional access rules allow you to refine this access and require users to belong to additional security groups which do not impact the roles which they are assigned.</span></span>
<span data-ttu-id="b89d8-193">これは、"ジャスト イン タイム" 特権アクセス管理ソリューション、スマート カード認証、またはその他の多要素認証ソリューションを JEA と統合する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-193">This can be useful if you want to integrate a "just in time" privileged access management solution, smartcard authentication, or other multifactor authentication solution with JEA.</span></span>

<span data-ttu-id="b89d8-194">条件付きアクセス規則は、セッション構成ファイルの RequiredGroups フィールドで定義します。</span><span class="sxs-lookup"><span data-stu-id="b89d8-194">Conditional access rules are defined in the RequiredGroups field in a session configuration file.</span></span>
<span data-ttu-id="b89d8-195">そこでは、"And" キーと "Or" キーを使って規則を作成するハッシュ テーブル (必要に応じて入れ子になっている) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-195">There, you can provide a hashtable (optionally nested) that uses 'And' and 'Or' keys to construct your rules.</span></span>
<span data-ttu-id="b89d8-196">このフィールドの活用方法について、次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b89d8-196">Here are some examples of how to leverage this field:</span></span>

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
> <span data-ttu-id="b89d8-197">条件付きアクセス規則を使用できるのは、Windows PowerShell 5.1 以降のみです。</span><span class="sxs-lookup"><span data-stu-id="b89d8-197">Conditional access rules are only available in Windows PowerShell 5.1 or newer.</span></span>

### <a name="other-properties"></a><span data-ttu-id="b89d8-198">他のプロパティ</span><span class="sxs-lookup"><span data-stu-id="b89d8-198">Other properties</span></span>
<span data-ttu-id="b89d8-199">セッション構成ファイルではロール機能ファイルで実行できるすべてのことを実行できますが、接続しているユーザーが別のコマンドにアクセスできるようにする機能だけはありません。</span><span class="sxs-lookup"><span data-stu-id="b89d8-199">Session configuration files can also do everything a role capability file can do, just without the ability to give connecting users access to different commands.</span></span>
<span data-ttu-id="b89d8-200">すべてのユーザーに特定のコマンドレット、関数、またはプロバイダーへのアクセスを許可する場合は、セッション構成ファイルで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-200">If you want to allow all users access to specific cmdlets, functions, or providers, you can do so right in the session configuration file.</span></span>
<span data-ttu-id="b89d8-201">セッション構成ファイルでサポートされているプロパティの一覧については、`Get-Help New-PSSessionConfigurationFile -Full` を実行してください。</span><span class="sxs-lookup"><span data-stu-id="b89d8-201">For a full list of supported properties in the session configuration file, run `Get-Help New-PSSessionConfigurationFile -Full`.</span></span>

## <a name="testing-a-session-configuration-file"></a><span data-ttu-id="b89d8-202">セッション構成ファイルのテスト</span><span class="sxs-lookup"><span data-stu-id="b89d8-202">Testing a session configuration file</span></span>

<span data-ttu-id="b89d8-203">[Test-PSSessionConfigurationFile](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/test-pssessionconfigurationfile) コマンドレットを使って、セッション構成をテストできます。</span><span class="sxs-lookup"><span data-stu-id="b89d8-203">You can test a session configuration using the [Test-PSSessionConfigurationFile](https://msdn.microsoft.com/en-us/powershell/reference/5.1/microsoft.powershell.core/test-pssessionconfigurationfile) cmdlet.</span></span>
<span data-ttu-id="b89d8-204">テキスト エディターを使って手動で pssc ファイルを編集した場合は、セッション構成ファイルをテストして構文が正しいことを確認することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b89d8-204">It is strongly recommended that you test your session configuration file if you have edited the pssc file manually using a text editor to ensure the syntax is correct.</span></span>
<span data-ttu-id="b89d8-205">セッション構成ファイルがこのテストに合格しない場合、システムに正しく登録することはできません。</span><span class="sxs-lookup"><span data-stu-id="b89d8-205">If a session configuration file does not pass this test, it will not be able to be successfully registered on the system.</span></span>

## <a name="sample-session-configuration-file"></a><span data-ttu-id="b89d8-206">セッション構成ファイルのサンプル</span><span class="sxs-lookup"><span data-stu-id="b89d8-206">Sample session configuration file</span></span>

<span data-ttu-id="b89d8-207">JEA のセッション構成を作成して検証する方法を示す完全な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b89d8-207">Below is a complete example showing how to create and validate a session configuration for JEA.</span></span>
<span data-ttu-id="b89d8-208">使いやすさと読みやすさのため、作成したロール定義を `$roles` 変数に保存していることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b89d8-208">Note that the role definitions are created and stored in the `$roles` variable for convenience and readability.</span></span>
<span data-ttu-id="b89d8-209">ただし、必ずこのようにする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b89d8-209">It is not a requirement to do so.</span></span>

```powershell
$roles = @{
    'CONTOSO\JEA_DNS_ADMINS'    = @{ RoleCapabilities = 'DnsAdmin', 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_OPERATORS' = @{ RoleCapabilities = 'DnsOperator', 'DnsAuditor' }
    'CONTOSO\JEA_DNS_AUDITORS'  = @{ RoleCapabilities = 'DnsAuditor' }
}

New-PSSessionConfigurationFile -SessionType RestrictedRemoteServer -Path .\JEAConfig.pssc -RunAsVirtualAccount -TranscriptDirectory 'C:\ProgramData\JEAConfiguration\Transcripts' -RoleDefinitions $roles -RequiredGroups @{ Or = '2FA-logon', 'smartcard-logon' }
Test-PSSessionConfigurationFile -Path .\JEAConfig.pssc # should yield True
```

## <a name="updating-session-configuration-files"></a><span data-ttu-id="b89d8-210">セッション構成ファイルの更新</span><span class="sxs-lookup"><span data-stu-id="b89d8-210">Updating session configuration files</span></span>

<span data-ttu-id="b89d8-211">ロールへのユーザーのマッピングなど、JEA セッション構成のプロパティを変更する必要がある場合は、JEA セッション構成を[登録解除](register-jea.md#unregistering-jea-configurations)してから[再登録](register-jea.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b89d8-211">If you need to change properties of a JEA session configuration, including the mapping of users to roles, you must [unregister](register-jea.md#unregistering-jea-configurations) and [re-register](register-jea.md) the JEA session configuration.</span></span>
<span data-ttu-id="b89d8-212">JEA セッション構成を再登録するときは、必要な変更を含む更新された PowerShell セッション構成ファイルを使います。</span><span class="sxs-lookup"><span data-stu-id="b89d8-212">When you re-register the JEA session configuration, use an updated PowerShell session configuration file that includes your desired changes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b89d8-213">次の手順</span><span class="sxs-lookup"><span data-stu-id="b89d8-213">Next steps</span></span>

- [<span data-ttu-id="b89d8-214">JEA 構成を登録する</span><span class="sxs-lookup"><span data-stu-id="b89d8-214">Register a JEA configuration</span></span>](register-jea.md)
- [<span data-ttu-id="b89d8-215">ロール機能</span><span class="sxs-lookup"><span data-stu-id="b89d8-215">Author JEA roles</span></span>](role-capabilities.md)

