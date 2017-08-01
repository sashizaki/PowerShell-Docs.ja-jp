---
description: 
manager: dongill
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット, JEA"
ms.date: 2016-06-22
title: "このガイドで使用される主要概念"
ms.technology: powershell
ms.openlocfilehash: 873ab19fdf43ec4ac41cc546aa94b64fbc607984
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
ms.translationtype: HT
ms.contentlocale: ja-JP
---
# <a name="key-concepts-used-throughout-this-guide"></a><span data-ttu-id="f961e-103">このガイドで使用される主要概念</span><span class="sxs-lookup"><span data-stu-id="f961e-103">Key Concepts Used Throughout This Guide</span></span>
<span data-ttu-id="f961e-104">**JEA とは**</span><span class="sxs-lookup"><span data-stu-id="f961e-104">**What exactly is JEA?**</span></span>

<span data-ttu-id="f961e-105">JEA は PowerShell の[制約付きエンドポイント](http://blogs.technet.com/b/heyscriptingguy/archive/2014/03/31/introduction-to-powershell-endpoints.aspx)の拡張機能で、ロール定義、仮想アカウントなどのいくつかの機能強化を追加することで、管理エンドポイントをさらに簡単に保護できます。</span><span class="sxs-lookup"><span data-stu-id="f961e-105">JEA is an extension of PowerShell [constrained endpoints](http://blogs.technet.com/b/heyscriptingguy/archive/2014/03/31/introduction-to-powershell-endpoints.aspx) that adds in role definitions, virtual accounts, and several other improvements to make it even easier to lock down your management endpoints.</span></span>
<span data-ttu-id="f961e-106">JEA エンドポイントは、1 つの PowerShell セッション構成ファイルと 1 つ以上のロール機能ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f961e-106">A JEA endpoint consists of a PowerShell Session Configuration file and one or more Role Capability files.</span></span>

<span data-ttu-id="f961e-107">**セッション構成ファイルおよびロール機能ファイルとは**</span><span class="sxs-lookup"><span data-stu-id="f961e-107">**What are Session Configuration and Role Capability files?**</span></span>

<span data-ttu-id="f961e-108">PowerShell セッション構成ファイル (.pssc) は、PowerShell エンドポイントに接続できる*ユーザー*とその構成*方法*を定義します。</span><span class="sxs-lookup"><span data-stu-id="f961e-108">PowerShell Session Configuration files (.pssc) define *who* can connect to a PowerShell endpoint and *how* it is configured.</span></span>
<span data-ttu-id="f961e-109">ここで、ユーザーとセキュリティ グループを特定の管理ロールにマップし、仮想アカウント、トランスクリプション ポリシーなどのグローバル設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="f961e-109">This is where you would map users and security groups to specific management roles and configure global settings like virtual accounts and transcription policies.</span></span>
<span data-ttu-id="f961e-110">セッション構成ファイルは各コンピューターに固有で、これを使用して、必要に応じて、コンピューターごとにアクセス権を制御できます。</span><span class="sxs-lookup"><span data-stu-id="f961e-110">Session configuration files are specific to each machine, which allows you to control access on a per-machine basis if desired.</span></span>

<span data-ttu-id="f961e-111">PowerShell ロール機能ファイル (.psrc) は、特定のロールに属する*どの*ユーザーがシステム上で操作を行えるかを定義します。</span><span class="sxs-lookup"><span data-stu-id="f961e-111">PowerShell Role Capability files (.psrc) define *what* users belonging to a role are able to do on the system.</span></span>
<span data-ttu-id="f961e-112">ここでは、ユーザーが JEA セッションで使用できるコマンドレット、関数、プロバイダー、および外部プログラムを制限できます。</span><span class="sxs-lookup"><span data-stu-id="f961e-112">Here, you can restrict which cmdlets, functions, providers, and external programs a user may use in their JEA session.</span></span>
<span data-ttu-id="f961e-113">ロール機能ファイルは、提供中のロール (DNS 管理者、レベル 1 のヘルプデスク、読み取り専用のインベントリの監査など) には一般的で、PowerShell モジュールに属し、環境全体で、また他のユーザーと簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="f961e-113">Role Capability files are often generic for the role being served (DNS admin, level 1 helpdesk, read-only inventory auditing, etc.) and belong to PowerShell modules, making it easy to share them across your environment and with others.</span></span>

<span data-ttu-id="f961e-114">**JEA による仮想アカウントの使用**</span><span class="sxs-lookup"><span data-stu-id="f961e-114">**How does JEA leverage virtual accounts?**</span></span>

<span data-ttu-id="f961e-115">PowerShell セッション構成ファイルでは、仮想 "実行" アカウントを使用するように JEA セッションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="f961e-115">In the PowerShell Session Configuration file, you can configure JEA sessions to use virtual "run as" accounts.</span></span>
<span data-ttu-id="f961e-116">仮想アカウントは、その特定のセッションで特定の接続しているユーザーに作成され、ユーザーのコマンドを実行する、1 回限りの特権アカウントです。</span><span class="sxs-lookup"><span data-stu-id="f961e-116">Virtual accounts are one-time privileged accounts spun up for the specific connecting user in that specific session under which context the user's commands are executed.</span></span>
<span data-ttu-id="f961e-117">既定では、仮想アカウントはローカルの "管理者" セキュリティ グループに属しますが、指定したセキュリティ グループにのみ属するように構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f961e-117">Virtual accounts belong to the local "Administrators" security group by default, but can optionally be configured to only belong to security groups you specify.</span></span>

<span data-ttu-id="f961e-118">**PowerShell リモート処理**: PowerShell リモート処理では、リモート コンピューターに対して PowerShell コマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f961e-118">**PowerShell Remoting**: PowerShell remoting allows you to run PowerShell commands against remote machines.</span></span>
<span data-ttu-id="f961e-119">1 つまたは複数のコンピューターを操作し、一時的または永続的な接続を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f961e-119">You can operate against one or many computers, and use either temporary or persistent connections.</span></span>
<span data-ttu-id="f961e-120">このデモでは、対話型セッションによりローカル コンピューターにリモート接続します。</span><span class="sxs-lookup"><span data-stu-id="f961e-120">In this demo, you remoted into your local machine with an interactive session.</span></span>
<span data-ttu-id="f961e-121">JEA では、PowerShell リモート処理で使用できる機能に制限があります。</span><span class="sxs-lookup"><span data-stu-id="f961e-121">JEA restricts the functionality available through PowerShell remoting.</span></span>
<span data-ttu-id="f961e-122">PowerShell リモート処理について詳しくは、`Get-Help about_Remote` を実行してください。</span><span class="sxs-lookup"><span data-stu-id="f961e-122">For more information about PowerShell remoting, run `Get-Help about_Remote`.</span></span>

<span data-ttu-id="f961e-123">**RunAs ユーザー**: JEA を使用すると、管理者以外のユーザーが、特権 "仮想アカウント" として実行されます。</span><span class="sxs-lookup"><span data-stu-id="f961e-123">**"RunAs" User**: When using JEA, a non-administrator "runs as" a privileged "Virtual Account."</span></span>
<span data-ttu-id="f961e-124">仮想アカウントは、リモート セッションの間だけ持続します。</span><span class="sxs-lookup"><span data-stu-id="f961e-124">The Virtual Account only lasts the duration of the remote session.</span></span>
<span data-ttu-id="f961e-125">つまり、これは、ユーザーがエンドポイントに接続したときに作成され、ユーザーがセッションを終了したときに破棄されます。</span><span class="sxs-lookup"><span data-stu-id="f961e-125">That is to say, it is created when a user connects to the endpoint, and destroyed when the user ends the session.</span></span>
<span data-ttu-id="f961e-126">既定では、仮想アカウントは、ローカル管理者グループのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="f961e-126">By default, the Virtual Account is a member of the local Administrators group.</span></span>
<span data-ttu-id="f961e-127">ドメイン コントローラーでは、Domain Admins のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="f961e-127">On a domain controller, it is a member of Domain Admins.</span></span>
<span data-ttu-id="f961e-128">仮想アカウントはこれらが作成されるコンピューターに対してローカルで、そのコンピューターの外では効力を持ちません。</span><span class="sxs-lookup"><span data-stu-id="f961e-128">Virtual Accounts are local to the machine on which they are created, and do not have permissions outside of that machine.</span></span>
<span data-ttu-id="f961e-129">これは、これらが Active Directory に登録されない (RID が割り当てられない) ことを意味します。</span><span class="sxs-lookup"><span data-stu-id="f961e-129">This means that they are not registered in Active Directory (no RID is assigned).</span></span>
<span data-ttu-id="f961e-130">さらに、許可されたコマンド/スクリプトがローカル コンピューターの外のリソースへのアクセスを試行する場合、これは、仮想アカウント ID ではなく、コンピューターの ID を使ってこれらのリソースにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="f961e-130">Additionally, if an allowed command/script tries to access resources outside of the local machine, it will be accessing those resources under the machine's identity, not the Virtual Account identity.</span></span>

<span data-ttu-id="f961e-131">**"接続されている" ユーザー**: JEA エンドポイントに接続し、ロールが割り当てられる管理者以外のユーザー。</span><span class="sxs-lookup"><span data-stu-id="f961e-131">**"Connected" User**: The non-administrator user who connects to the JEA endpoint and to whom roles are assigned.</span></span>
<span data-ttu-id="f961e-132">このユーザーが実行するすべてのユーザーは、RunAs または仮想アカウントのコンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="f961e-132">Any commands this user runs are run under the context of the RunAs User or virtual account.</span></span>

