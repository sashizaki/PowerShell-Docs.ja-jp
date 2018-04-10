---
ms.date: 06/12/2017
author: rpsqrd
ms.topic: conceptual
keywords: JEA, PowerShell, セキュリティ
title: JEA セキュリティの考慮事項
ms.openlocfilehash: 1b83a73c047b056a4cc094d7e4b0bbf31f75f53a
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="jea-security-considerations"></a><span data-ttu-id="b10af-103">JEA セキュリティの考慮事項</span><span class="sxs-lookup"><span data-stu-id="b10af-103">JEA Security Considerations</span></span>

> <span data-ttu-id="b10af-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="b10af-104">Applies to: Windows PowerShell 5.0</span></span>

<span data-ttu-id="b10af-105">JEA はコンピューターの常駐管理者の数を減らし、セキュリティに対する姿勢を改善します。</span><span class="sxs-lookup"><span data-stu-id="b10af-105">JEA helps you improve your security posture by reducing the number of permanent administrators on your machines.</span></span>
<span data-ttu-id="b10af-106">ユーザーがシステムを管理するための新しい入口を作成し (PowerShell セッション構成)、それを既定で厳しく施錠し、誤用を防止します。</span><span class="sxs-lookup"><span data-stu-id="b10af-106">It does so by creating a new entry point for users to manage the system (a PowerShell session configuration) which is tightly locked down by default to prevent misuse.</span></span>
<span data-ttu-id="b10af-107">管理タスクを実行するために、無制限ではない、一部のアクセス許可を必要とするユーザーに JEA エンドポイントのアクセス許可を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="b10af-107">Users who need some, but not unlimited, access to the machine to perform administrative tasks can be granted access to the JEA endpoint.</span></span>
<span data-ttu-id="b10af-108">JEA では管理アクセス許可を直接持たなくても管理コマンドを実行できるため、高い特権を与えるセキュリティ グループからユーザーを削除できます (標準ユーザーにします)。</span><span class="sxs-lookup"><span data-stu-id="b10af-108">Because JEA allows them to run admin commands without directly having admin access, you can then remove those users from highly privileged security groups (make them standard users).</span></span>

<span data-ttu-id="b10af-109">このトピックでは、JEA セキュリティ モデルとベスト プラクティスについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="b10af-109">This topic describes the JEA security model and best practices in more detail.</span></span>

## <a name="run-as-account"></a><span data-ttu-id="b10af-110">実行アカウント</span><span class="sxs-lookup"><span data-stu-id="b10af-110">Run As account</span></span>

<span data-ttu-id="b10af-111">各 JEA エンドポイントには、指定の "実行" アカウントが与えられます。このアカウントの下で、接続するユーザーのアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="b10af-111">Each JEA endpoint has a designated "run as" account, which is the account under which the connecting user's actions are performed.</span></span>
<span data-ttu-id="b10af-112">このアカウントは[セッション構成ファイル](session-configurations.md)で構成できます。選択したアカウントは、エンドポイントのセキュリティに大きく関係します。</span><span class="sxs-lookup"><span data-stu-id="b10af-112">This account is configurable in the [session configuration file](session-configurations.md), and the account you choose has a significant bearing on the security of your endpoint.</span></span>

<span data-ttu-id="b10af-113">**仮想アカウント**は、実行アカウントを構成するときに推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="b10af-113">**Virtual accounts** are the recommended way of configuring the run as account.</span></span>
<span data-ttu-id="b10af-114">仮想アカウントは 1 回限りの一時的なローカル アカウントです。JEA セッションの間、接続ユーザーが使用するために作成されます。</span><span class="sxs-lookup"><span data-stu-id="b10af-114">Virtual accounts are one-time, temporary local accounts that are created for the connecting user to use during the duration of their JEA session.</span></span>
<span data-ttu-id="b10af-115">セッションが終了すると同時に仮想アカウントは破棄され、その後は使用できません。</span><span class="sxs-lookup"><span data-stu-id="b10af-115">As soon as their session is terminated, the virtual account will be destroyed and cannot be used anymore.</span></span>
<span data-ttu-id="b10af-116">接続ユーザーは仮想アカウントの資格情報を知らず、仮想アカウントを使用してその他の手段 (リモート デスクトップや制約のない PowerShell エンドポイントなど) を介してシステムにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b10af-116">The connecting user does not know the credentials for the virtual account and cannot use the virtual account to access the system via other means, such as Remote Desktop or an unconstrained PowerShell endpoint.</span></span>

<span data-ttu-id="b10af-117">既定では、仮想アカウントは、コンピューターのローカル管理者グループに属します。</span><span class="sxs-lookup"><span data-stu-id="b10af-117">By default, virtual accounts belong to the local administrators group on the machine.</span></span>
<span data-ttu-id="b10af-118">それにより、システム上のあらゆるものを管理する完全な権限が与えられますが、ネットワーク上のリソースを管理する権限は与えられません。</span><span class="sxs-lookup"><span data-stu-id="b10af-118">This gives them full rights to manage anything on the system, but no rights to manage resources on the network.</span></span>
<span data-ttu-id="b10af-119">他のコンピューターで認証を行うと、ユーザー コンテキストは、仮想アカウントではなく、ローカル コンピューター アカウントになります。</span><span class="sxs-lookup"><span data-stu-id="b10af-119">When authenticating with other machines, the user context will be that of the local computer account, not the virtual account.</span></span>

<span data-ttu-id="b10af-120">ドメイン コント ローラーにはローカルの管理者グループの概念がないために、特別なケースです。</span><span class="sxs-lookup"><span data-stu-id="b10af-120">Domain controllers are a special case since there is no concept of a local administrators group.</span></span>
<span data-ttu-id="b10af-121">代わりに、仮想アカウントは Domain Admins に属しており、ドメイン コントローラー上のディレクトリ サービスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="b10af-121">Instead, virtual accounts belong to Domain Admins instead and can manage the directory services on the domain controller.</span></span>
<span data-ttu-id="b10af-122">ドメイン ID は JEA セッションがインスタンス化されたドメイン コントローラー上での使用に制限されており、すべてのネットワーク アクセスは代わりにドメイン コントローラー コンピューター オブジェクトから来ているように見えます。</span><span class="sxs-lookup"><span data-stu-id="b10af-122">The domain identity is still restricted to use on the domain controller where the JEA session was instantiated, and any network access will appear to come from the domain controller computer object instead.</span></span>

<span data-ttu-id="b10af-123">いずれの場合でも、仮想アカウントが属するセキュリティ グループを明示的に定義できます。</span><span class="sxs-lookup"><span data-stu-id="b10af-123">In both cases, you can also explicitly define which security groups the virtual account should belong to.</span></span>
<span data-ttu-id="b10af-124">ローカル/ドメイン管理者特権なしでタスクを実行できるとき、明示的に定義することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b10af-124">This is a good practice when the task you are performing can be done without local/domain admin privileges.</span></span>
<span data-ttu-id="b10af-125">管理者にセキュリティ グループを既に定義している場合、そのグループに仮想アカウントのメンバーシップを与えることで必要なアクセス許可を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="b10af-125">If you already have a security group defined for your admins, you can simply grant the virtual account membership to that group to give it the permissions it needs.</span></span>
<span data-ttu-id="b10af-126">仮想アカウント グループ メンバーシップはワークステーションとメンバー サーバーのローカル セキュリティ グループに限定されますが、ドメイン コントローラーでは、ドメイン セキュリティ グループのメンバーだけになることができます。</span><span class="sxs-lookup"><span data-stu-id="b10af-126">Virtual account group membership is limited to local security groups on workstation and member servers, but on a domain controller they can only be members of domain security groups.</span></span>
<span data-ttu-id="b10af-127">仮想アカウントにそれが属する 1 つ以上のセキュリティ グループを指定すると、既定のグループ (ローカル管理またはドメイン管理) から削除されます。</span><span class="sxs-lookup"><span data-stu-id="b10af-127">Once you specify one or more security groups for the virtual account to belong to, it will no longer belong to the default groups (local admin or domain admin).</span></span>

<span data-ttu-id="b10af-128">次の表は、仮想アカウントに対して構成できるオプションとその結果として与えられるアクセス許可をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="b10af-128">The table below summarizes the possible configuration options and resulting permissions for virtual accounts</span></span>

<span data-ttu-id="b10af-129">コンピューターの種類</span><span class="sxs-lookup"><span data-stu-id="b10af-129">Computer type</span></span>                | <span data-ttu-id="b10af-130">仮想アカウント グループ構成</span><span class="sxs-lookup"><span data-stu-id="b10af-130">Virtual account group configuration</span></span> | <span data-ttu-id="b10af-131">ローカル ユーザー コンテキスト</span><span class="sxs-lookup"><span data-stu-id="b10af-131">Local user context</span></span>                                      | <span data-ttu-id="b10af-132">ネットワーク ユーザー コンテキスト</span><span class="sxs-lookup"><span data-stu-id="b10af-132">Network user context</span></span>
-----------------------------|-------------------------------------|---------------------------------------------------------|--------------------------------------------------
<span data-ttu-id="b10af-133">ドメイン コントローラー</span><span class="sxs-lookup"><span data-stu-id="b10af-133">Domain controller</span></span>            | <span data-ttu-id="b10af-134">既定</span><span class="sxs-lookup"><span data-stu-id="b10af-134">Default</span></span>                             | <span data-ttu-id="b10af-135">ドメイン ユーザー、'*DOMAIN*\Domain Admins' のメンバー</span><span class="sxs-lookup"><span data-stu-id="b10af-135">Domain user, member of '*DOMAIN*\Domain Admins'</span></span>         | <span data-ttu-id="b10af-136">コンピューター アカウント</span><span class="sxs-lookup"><span data-stu-id="b10af-136">Computer account</span></span>
<span data-ttu-id="b10af-137">ドメイン コントローラー</span><span class="sxs-lookup"><span data-stu-id="b10af-137">Domain controller</span></span>            | <span data-ttu-id="b10af-138">ドメイン グループ A と B</span><span class="sxs-lookup"><span data-stu-id="b10af-138">Domain groups A and B</span></span>               | <span data-ttu-id="b10af-139">ドメイン ユーザー、'*DOMAIN*\A'、'*DOMAIN*\B' のメンバー</span><span class="sxs-lookup"><span data-stu-id="b10af-139">Domain user, member of '*DOMAIN*\A', '*DOMAIN*\B'</span></span>       | <span data-ttu-id="b10af-140">コンピューター アカウント</span><span class="sxs-lookup"><span data-stu-id="b10af-140">Computer account</span></span>
<span data-ttu-id="b10af-141">メンバー サーバーまたはワークステーション</span><span class="sxs-lookup"><span data-stu-id="b10af-141">Member server or workstation</span></span> | <span data-ttu-id="b10af-142">既定</span><span class="sxs-lookup"><span data-stu-id="b10af-142">Default</span></span>                             | <span data-ttu-id="b10af-143">ローカル ユーザー、'*BUILTIN*\Administrators' のメンバー</span><span class="sxs-lookup"><span data-stu-id="b10af-143">Local user, member of '*BUILTIN*\Administrators'</span></span>        | <span data-ttu-id="b10af-144">コンピューター アカウント</span><span class="sxs-lookup"><span data-stu-id="b10af-144">Computer account</span></span>
<span data-ttu-id="b10af-145">メンバー サーバーまたはワークステーション</span><span class="sxs-lookup"><span data-stu-id="b10af-145">Member server or workstation</span></span> | <span data-ttu-id="b10af-146">ローカル グループ C と D</span><span class="sxs-lookup"><span data-stu-id="b10af-146">Local groups C and D</span></span>                | <span data-ttu-id="b10af-147">ローカル ユーザー、'*COMPUTER*\C' と '*COMPUTER*\D' のメンバー</span><span class="sxs-lookup"><span data-stu-id="b10af-147">Local user, member of '*COMPUTER*\C' and '*COMPUTER*\D'</span></span> | <span data-ttu-id="b10af-148">コンピューター アカウント</span><span class="sxs-lookup"><span data-stu-id="b10af-148">Computer account</span></span>

<span data-ttu-id="b10af-149">セキュリティ監査イベントとアプリケーション イベントのログを見ると、各 JEA ユーザー セッションに一意の仮想アカウントが与えられていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="b10af-149">When you look at security audit events and application event logs, you will see that each JEA user session has a unique virtual account.</span></span>
<span data-ttu-id="b10af-150">JEA エンドポイントのユーザー アクションを、コマンドを実行した元のユーザーまでさかのぼって追跡できます。</span><span class="sxs-lookup"><span data-stu-id="b10af-150">This helps you track user actions in a JEA endpoint back to the original user who ran the command.</span></span>
<span data-ttu-id="b10af-151">仮想アカウントの名前の形式は、"WinRM Virtual Users\\WinRM\_VA\_*ACCOUNTNUMBER*\_*DOMAIN*\_*sAMAccountName*" になります。たとえば、ドメイン "Contoso" のユーザー "Alice" が JEA エンドポイントでサービスを再開した場合、サービス コントロール マネージャー イベントに関連付けられているユーザー名は "WinRM Virtual Users\\WinRM\_VA\_1\_contoso\_alice" になります。</span><span class="sxs-lookup"><span data-stu-id="b10af-151">Virtual account names follow the format "WinRM Virtual Users\\WinRM\_VA\_*ACCOUNTNUMBER*\_*DOMAIN*\_*sAMAccountName*" For example, if user "Alice" in domain "Contoso" restarts a service in a JEA endpoint, the username associated with any service control manager events would be "WinRM Virtual Users\\WinRM\_VA\_1\_contoso\_alice".</span></span>


<span data-ttu-id="b10af-152">**グループの管理されたサービス アカウント (gMSAs)** は、メンバー サーバーに JEA セッションのネットワーク リソースのアクセス許可を与える必要があるときに便利です。</span><span class="sxs-lookup"><span data-stu-id="b10af-152">**Group managed service accounts (gMSAs)** are useful when a member server needs to have access to network resources in the JEA session.</span></span>
<span data-ttu-id="b10af-153">たとえば、JEA エンドポイントを利用し、異なるコンピューターでホストされている REST API のアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="b10af-153">An example use case for this is a JEA endpoint that is used to control access to a REST API hosted on a different machine.</span></span>
<span data-ttu-id="b10af-154">REST API で必要な呼び出しを行う関数を記述することは簡単ですが、API で認証するために、ネットワーク ID が必要になります。</span><span class="sxs-lookup"><span data-stu-id="b10af-154">It is easy to write functions to make the desired invocations on the REST API, but in order to authenticate with the API you need a network identity.</span></span>
<span data-ttu-id="b10af-155">グループの管理されたサービス アカウントを利用すると、アカウントを使用できるコンピューターを制御しながら、"次ホップ" が可能になります。</span><span class="sxs-lookup"><span data-stu-id="b10af-155">Using a group managed service account makes the "second hop" possible while still having control over which computers can use the account.</span></span>
<span data-ttu-id="b10af-156">gMSA の効果的なアクセス許可が、gMSA アカウントが属するセキュリティ グループ (ローカルまたはドメイン) により定義されます。</span><span class="sxs-lookup"><span data-stu-id="b10af-156">The effective permissions of the gMSA are defined by the security groups (local or domain) to which the gMSA account belongs.</span></span>

<span data-ttu-id="b10af-157">gMSA アカウントを使用するように JEA エンドポイントを構成すると、あらゆる JEA ユーザーのアクションが同じグループの管理されたサービス アカウントから行われたように表示されます。</span><span class="sxs-lookup"><span data-stu-id="b10af-157">When a JEA endpoint is configured to use a gMSA account, the actions of all JEA users will appear to come from the same group managed service account.</span></span>
<span data-ttu-id="b10af-158">アクションを特定のユーザーまでさかのぼって追跡する唯一の方法は、PowerShell セッション トランスクリプトで実行されたコマンド セットを特定することです。</span><span class="sxs-lookup"><span data-stu-id="b10af-158">The only way you can trace actions back to a specific user is to identify the set of commands run in a PowerShell session transcript.</span></span>

<span data-ttu-id="b10af-159">実行アカウントを指定せずに、PowerShell で接続ユーザーの資格情報を利用してリモート サーバー上でコマンドを実行する場合、**パススルー資格情報**が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b10af-159">**Pass-thru credentials** are used when you do not specify a run as account and want PowerShell to use the connecting user's credential to run commands on the remote server.</span></span>
<span data-ttu-id="b10af-160">この構成は JEA には推奨*されません*。特権のある管理グループの直接アクセス許可を接続ユーザーに与える必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="b10af-160">This configuration is *not* recommended for JEA as it would require you to grant the connecting user direct access to privileged management groups.</span></span>
<span data-ttu-id="b10af-161">接続ユーザーに管理者特権が既に与えられている場合、JEA を完全に回避し、制約のない他の手法でシステムを管理できます。</span><span class="sxs-lookup"><span data-stu-id="b10af-161">If the connecting user already has admin privileges, they can avoid JEA altogether and manage the system via other, unconstrained means.</span></span>
<span data-ttu-id="b10af-162">詳細については、[JEA で管理者に対する防御がない](#jea-does-not-protect-against-admins)ことに関する下のセクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b10af-162">See the section below on how [JEA does not protect against admins](#jea-does-not-protect-against-admins) for more information.</span></span>

<span data-ttu-id="b10af-163">**標準の実行アカウント**では、PowerShell セッション全体を実行するユーザー アカウントを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b10af-163">**Standard run as accounts** allow you to specify any user account under which the entire PowerShell session will run.</span></span>
<span data-ttu-id="b10af-164">これは重要な特徴です。(`-RunAsCredential` パラメーターで) 固定の実行アカウントを使用するように設定されているセッション構成は JEA に対応していないためです。</span><span class="sxs-lookup"><span data-stu-id="b10af-164">This is an important distinction, because a session configuration set to use a fixed run as account (with the `-RunAsCredential` parameter) is not JEA-aware.</span></span>
<span data-ttu-id="b10af-165">つまり、ロールの定義が予想どおり機能することがなくなり、エンドポイントにアクセスする許可が与えられているすべてのユーザーに同じロールが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="b10af-165">That means that role definitions no longer function as expected, and every user authorized to access the endpoint will be assigned the same role.</span></span>

<span data-ttu-id="b10af-166">JEA エンドポイントでは RunAsCredential を使用しないでください。特定のユーザーまでさかのぼって追跡することが難しく、ユーザーをロールにマッピングできないためです。</span><span class="sxs-lookup"><span data-stu-id="b10af-166">You should not use a RunAsCredential on a JEA endpoint because of the difficulty in tracing actions back to specific users and the lack of support for mapping users to roles.</span></span>

## <a name="winrm-endpoint-acl"></a><span data-ttu-id="b10af-167">WinRM エンドポイント ACL</span><span class="sxs-lookup"><span data-stu-id="b10af-167">WinRM Endpoint ACL</span></span>

<span data-ttu-id="b10af-168">通常の PowerShell リモート処理エンドポイントと同様に、各 JEA エンドポイントに個別のアクセス制御リスト (ACL) が与えられ、WinRM 構成に設定されます。そのリストにより、JEA エンドポイントで認証できるユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="b10af-168">As with regular PowerShell remoting endpoints, each JEA endpoint has a separate access control list (ACL) set in the WinRM configuration that controls who can authenticate with the JEA endpoint.</span></span>
<span data-ttu-id="b10af-169">構成が不適切な場合、信頼されているユーザーが JEA エンドポイントにアクセスできなかったり、信頼されていないユーザーがアクセスできたりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="b10af-169">If improperly configured, trusted users may not be able to access the JEA endpoint and/or untrusted users may gain access.</span></span>
<span data-ttu-id="b10af-170">ただし、WinRM ACL は JEA ロールへのユーザーのマッピングに影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="b10af-170">The WinRM ACL does not, however, affect the mapping of users to JEA roles.</span></span>
<span data-ttu-id="b10af-171">それは、システムに登録されたセッション構成ファイルの *RoleDefinitions* フィールドで制御されます。</span><span class="sxs-lookup"><span data-stu-id="b10af-171">That is controlled by the *RoleDefinitions* field in the session configuration file that was registered on the system.</span></span>

<span data-ttu-id="b10af-172">既定では、セッション構成ファイルと 1 つ以上のロール機能を利用して JEA エンドポイントを登録するとき、WinRM ACL は、1 つ以上のロールにマッピングするすべてのユーザーにエンドポイントのアクセスを許可するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="b10af-172">By default, when you register a JEA endpoint using a session configuration file and one or more role capabilities, the WinRM ACL will be configured to allow all users mapping to one or more roles access to the endpoint.</span></span>
<span data-ttu-id="b10af-173">たとえば、次のコマンドで構成された JEA セッションには *CONTOSO\JEA\_Lev1* と *CONTOSO\JEA\_Lev2* への完全アクセス許可が与えられます。</span><span class="sxs-lookup"><span data-stu-id="b10af-173">For example, a JEA session configured using the following commands will grant full access to *CONTOSO\JEA\_Lev1* and *CONTOSO\JEA\_Lev2*.</span></span>

```powershell
$roles = @{ 'CONTOSO\JEA_Lev1' = 'Lev1Role'; 'CONTOSO\JEA_Lev2' = 'Lev2Role' }
New-PSSessionConfigurationFile -Path '.\jea.pssc' -SessionType RestrictedRemoteServer -RoleDefinitions $roles -RunAsVirtualAccount
Register-PSSessionConfiguration -Path '.\jea.pssc' -Name 'MyJEAEndpoint'
```

<span data-ttu-id="b10af-174">[Get-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/get-pssessionconfiguration) コマンドレットでユーザー アクセス許可を監査できます。</span><span class="sxs-lookup"><span data-stu-id="b10af-174">You can audit user permissions with the [Get-PSSessionConfiguration](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/get-pssessionconfiguration) cmdlet.</span></span>

```powershell
PS C:\> Get-PSSessionConfiguration -Name 'MyJEAEndpoint' | Select-Object Permission

Permission
----------
CONTOSO\JEA_Lev1 AccessAllowed
CONTOSO\JEA_Lev2 AccessAllowed
```

<span data-ttu-id="b10af-175">アクセスを与えるユーザーを変更するには、対話的プロンプトの `Set-PSSessionConfiguration -Name 'MyJEAEndpoint' -ShowSecurityDescriptorUI` を実行するか、`Set-PSSessionConfiguration -Name 'MyJEAEndpoint' -SecurityDescriptorSddl <SDDL string>` を実行してアクセス許可を更新します。</span><span class="sxs-lookup"><span data-stu-id="b10af-175">To change which users have access, run either `Set-PSSessionConfiguration -Name 'MyJEAEndpoint' -ShowSecurityDescriptorUI` for an interactive prompt or `Set-PSSessionConfiguration -Name 'MyJEAEndpoint' -SecurityDescriptorSddl <SDDL string>` to update the permissions.</span></span>
<span data-ttu-id="b10af-176">ユーザーが JEA エンドポイントにアクセスするには、少なくとも*呼び出し*権限が必要になります。</span><span class="sxs-lookup"><span data-stu-id="b10af-176">Users need at least *Invoke* rights to access the JEA endpoint.</span></span>

<span data-ttu-id="b10af-177">追加ユーザーに JEA エンドポイントのアクセスを与えるが、セッション構成ファイルに定義されているロールには分類されない場合、JEA セッションを開始できますが、既定のコマンドレットへのアクセスのみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="b10af-177">If additional users are granted access to the JEA endpoint but do not fall into any of the roles defined in the session configuration file, they will be able to start a JEA session but only have access to the default cmdlets.</span></span>
<span data-ttu-id="b10af-178">`Get-PSSessionCapability` を実行し、JEA エンドポイントのユーザー アクセス許可を監査できます。</span><span class="sxs-lookup"><span data-stu-id="b10af-178">You can audit user permissions in a JEA endpoint by running `Get-PSSessionCapability`.</span></span>
<span data-ttu-id="b10af-179">JEA エンドポイントでユーザーにアクセスを与えるコマンドを監査する方法については、[JEA の監査とレポート](audit-and-report.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b10af-179">Check out the [Auditing and Reporting on JEA](audit-and-report.md) article for more information about auditing which commands a user has access to in a JEA endpoint.</span></span>

## <a name="least-privilege-roles"></a><span data-ttu-id="b10af-180">最小特権ロール</span><span class="sxs-lookup"><span data-stu-id="b10af-180">Least privilege roles</span></span>

<span data-ttu-id="b10af-181">JEA ロールを設計するとき、バックグラウンドで実行されている仮想アカウントまたはグループの管理されたサービス アカウントに、多くの場合、ローカル コンピューターを管理するためのアクセスが無制限で与えられることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b10af-181">When designing JEA roles, it is important to remember that the virtual or group managed service account running behind the scenes often has unrestricted access to manage the local machine.</span></span>
<span data-ttu-id="b10af-182">JEA ロール機能を利用すれば、特権コンテキストを利用して実行できるコマンドとアプリケーションを制限することで、アカウントの用途を制限できます。</span><span class="sxs-lookup"><span data-stu-id="b10af-182">JEA role capabilities help restrict what that account can be used for by limiting the commands and applications that can be run using that privileged context.</span></span>
<span data-ttu-id="b10af-183">ロールが不適切に設計されると、危険なコマンドの実行が許可され、ユーザーが JEA の境界から抜けたり、機密情報にアクセスできたりすることがあります。</span><span class="sxs-lookup"><span data-stu-id="b10af-183">Improperly designed roles can allow dangerous commands to run that may allow a user to break out of the JEA boundaries or obtain access to sensitive information.</span></span>

<span data-ttu-id="b10af-184">たとえば、次のロール機能エントリを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="b10af-184">For example, consider the following role capability entry:</span></span>

```powershell
@{
    VisibleCmdlets = 'Microsoft.PowerShell.Management\*-Process'
}
```

<span data-ttu-id="b10af-185">このロール機能では、Microsoft.PowerShell.Management モジュールから名詞 "Process" であらゆる PowerShell コマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b10af-185">This role capability allows users to run any PowerShell cmdlet with the noun "Process" from the Microsoft.PowerShell.Management module.</span></span>
<span data-ttu-id="b10af-186">システムで実行中のアプリケーションを確認するための `Get-Process` や応答していないアプリケーションを強制終了するための `Stop-Process` のようなコマンドレットが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="b10af-186">Users may need to access cmdlets like `Get-Process` to understand what applications are running on the system and `Stop-Process` to kill any hung applications.</span></span>
<span data-ttu-id="b10af-187">ただし、このエントリでは `Start-Process` も許可されます。これを利用すれば、完全な管理者権限で任意のプログラムを起動できます。</span><span class="sxs-lookup"><span data-stu-id="b10af-187">However, this entry also allows `Start-Process`, which can be used to start up an arbitrary program with full administrator permissions.</span></span>
<span data-ttu-id="b10af-188">プログラムをシステムにローカル インストールする必要がないため、悪意のあるユーザーがファイル共有でプログラムを起動するだけで接続ユーザーにローカル管理者特権が与えられ、マルウェアが実行されるなどの事態がありえます。</span><span class="sxs-lookup"><span data-stu-id="b10af-188">The program doesn't need to be installed locally on the system, so an adversary could simply start a program on a file share that gives the connecting user local admin privileges, runs malware, and more.'</span></span>

<span data-ttu-id="b10af-189">次は、同じロール機能をより安全にしたものです。</span><span class="sxs-lookup"><span data-stu-id="b10af-189">A more secure version of this same role capability would look like:</span></span>

```powershell
@{
    VisibleCmdlets = 'Microsoft.PowerShell.Management\Get-Process', 'Microsoft.PowerShell.Management\Stop-Process'
}
```

<span data-ttu-id="b10af-190">ロール機能ではワイルドカードを使用しないでください。[有効なユーザー アクセス許可を定期的に監査](audit-and-report.md#check-effective-rights-for-a-specific-user)し、ユーザーがアクセスできるコマンドを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b10af-190">Avoid using wildcards in role capabilities, and be sure to [audit effective user permissions](audit-and-report.md#check-effective-rights-for-a-specific-user) regularly to understand which commands a user has access to.</span></span>

## <a name="jea-does-not-protect-against-admins"></a><span data-ttu-id="b10af-191">JEA で管理者に対する防御がない</span><span class="sxs-lookup"><span data-stu-id="b10af-191">JEA does not protect against admins</span></span>

<span data-ttu-id="b10af-192">JEA の中心的原則の 1 つは、管理者以外のユーザーに*一部*の管理タスクを許可するというものです。</span><span class="sxs-lookup"><span data-stu-id="b10af-192">One of the core principles of JEA is that it allows non-admins to perform *some* admin tasks.</span></span>
<span data-ttu-id="b10af-193">JEA には、管理者特権が既に与えられているユーザーに対する防御がありません。</span><span class="sxs-lookup"><span data-stu-id="b10af-193">JEA does not protect against those who already have administrator privileges.</span></span>
<span data-ttu-id="b10af-194">環境で "ドメイン管理者"、"ローカル管理者"、その他の高い特権を持つグループに属するユーザーは、別の手段でコンピューターにサインインし、JEA の防御を避けることができます。</span><span class="sxs-lookup"><span data-stu-id="b10af-194">Users who belong "domain admins," "local admins," or other highly privileged groups in your environment will still be able to get around JEA's protections by signing into the machine via another means.</span></span>
<span data-ttu-id="b10af-195">たとえば、RDP でサインインし、リモート MMC コンソールを利用するか、制約のない PowerShell エンドポイントに接続できます。</span><span class="sxs-lookup"><span data-stu-id="b10af-195">They could, for example, sign in with RDP, use remote MMC consoles, or connect to unconstrained PowerShell endpoints.</span></span>
<span data-ttu-id="b10af-196">また、システムのローカル管理者は JEA 構成を変更し、追加ユーザーにシステムの管理を許可したり、ロール機能を変更し、JEA セッションでユーザーに許可する範囲を拡大することを許可したりできます。</span><span class="sxs-lookup"><span data-stu-id="b10af-196">Local admins on the system can also modify JEA configurations to allow additional users to manage the system or change a role capability to extend the scope of what a user can do in their JEA session.</span></span>
<span data-ttu-id="b10af-197">そのため、JEA ユーザーのアクセス権の拡大状況を見て、システムの特権アクセスを得る他の手法がないか調べることが重要です。</span><span class="sxs-lookup"><span data-stu-id="b10af-197">It is therefore important to evaluate your JEA users' extended permissions to see if there are other ways they could gain privileged access to the system.</span></span>

<span data-ttu-id="b10af-198">一般的な慣行としては、日常的な保守管理に JEA を利用し、"just in time " (必要なときに必要な許可だけを与える) の特権アクセス管理ソリューションを用意して緊急の場合にのみ一時的にローカル管理者になることをユーザーに許可します。</span><span class="sxs-lookup"><span data-stu-id="b10af-198">A common practice is to use JEA for regular day-to-day maintenance and have a "just in time" privileged access management solution allow users to temporarily become local admins in emergency situations.</span></span>
<span data-ttu-id="b10af-199">ユーザーはシステムの常駐管理者ではなくなるが、必要なときにのみ、管理者特権が与えられます。ワークフローを完了すると、アクセス許可の使用が記録されます。</span><span class="sxs-lookup"><span data-stu-id="b10af-199">This helps ensure users are not permanent admins on the system, but can get those rights if, and only when, they complete a workflow that documents their use of those permissions.</span></span>