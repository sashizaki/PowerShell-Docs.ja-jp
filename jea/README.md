---
description: 
manager: dongill
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット, JEA"
ms.date: 2016-06-22
title: README
ms.technology: powershell
ms.openlocfilehash: b0ef4ff685b82e1a4e9ab83a45736720df7b39a2
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
ms.translationtype: HT
ms.contentlocale: ja-JP
---
# <a name="just-enough-administration"></a><span data-ttu-id="07199-103">Just Enough Administration</span><span class="sxs-lookup"><span data-stu-id="07199-103">Just Enough Administration</span></span>
<span data-ttu-id="07199-104">Just Enough Administration (JEA) は、PowerShell で管理できるものすべてに対する委任された管理を有効にするセキュリティ テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="07199-104">Just Enough Administration (JEA) is a security technology that enables delegated administration for anything that can be managed with PowerShell.</span></span>
<span data-ttu-id="07199-105">JEA を使用すると、以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="07199-105">With JEA, you can:</span></span>
- <span data-ttu-id="07199-106">**お使いのコンピューター上の管理者の数を減らします**。このためには、通常のユーザーに代わって特権の必要な操作を実行する仮想アカウントを活用します。</span><span class="sxs-lookup"><span data-stu-id="07199-106">**Reduce the number of administrators on your machines** by leveraging virtual accounts that perform privileged actions on behalf of regular users.</span></span>
- <span data-ttu-id="07199-107">**ユーザーが実行できる操作を制限します**。ここでは、ユーザーが実行できるコマンドレット、関数、および外部コマンドを指定できます。</span><span class="sxs-lookup"><span data-stu-id="07199-107">**Limit what users can do** by specifying which cmdlets, functions, and external commands they can run.</span></span>
- <span data-ttu-id="07199-108">"覗き見" トランスクリプションを使用して、**ユーザーの操作を把握します**。このトランスクリプションは、ユーザーがセッション中にどんなコマンドを実行したかを正確に示します。</span><span class="sxs-lookup"><span data-stu-id="07199-108">**Better understand what your users are doing** with "over the shoulder" transcriptions that show you exactly what commands a user executed during a session.</span></span>

<span data-ttu-id="07199-109">**これが重要な理由:**</span><span class="sxs-lookup"><span data-stu-id="07199-109">**Why is this important?**</span></span>  
<span data-ttu-id="07199-110">DNS サーバーが Active Directory ドメイン コントローラーと併置された一般的なシナリオについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="07199-110">Consider the common scenario where your DNS servers are co-located with your Active Directory Domain Controllers.</span></span>
<span data-ttu-id="07199-111">DNS 管理者は、DNS サーバーでの問題を解決するためにローカル管理者特権が必要ですが、そのためには、これらの管理者を高い特権を持つ "Domain Admins" セキュリティ グループのメンバーにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="07199-111">Your DNS administrators need to have local administrator privileges to fix issues with the DNS server, but in order to do so you have to make them members of the highly privileged "Domain Admins" security group.</span></span>
<span data-ttu-id="07199-112">この方法は、ドメイン全体への制御や、そのコンピューター上のすべてのリソースへのアクセス権を DNS 管理者に効果的に付与します。</span><span class="sxs-lookup"><span data-stu-id="07199-112">This approach effectively gives DNS Administrators control over your whole domain and access to all resources on that machine.</span></span>

<span data-ttu-id="07199-113">JEA を配置し、DNS 管理者にロールを構成して、これらの管理者が作業を行うのに必要なすべてのコマンドにアクセスできるように、またそれ以外のことを実行できないように指定できます。</span><span class="sxs-lookup"><span data-stu-id="07199-113">With JEA in place, you can configure a role for your DNS administrators that gives them access to all the commands they need to get their job done, but nothing more.</span></span>
<span data-ttu-id="07199-114">つまり、DNS 管理者に Active Directory への権限を付与しなくても、侵害された DNS キャッシュを修復したり、ファイル システムを参照したり、潜在的に危険性なスクリプトを実行したりできる適切なアクセスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="07199-114">This means you can provide the appropriate access to repair a poisoned DNS cache without unintentionally giving them rights to Active Directory, or to browse the file system, or run potentially dangerous scripts.</span></span>
<span data-ttu-id="07199-115">さらに、JEA セッションが 1 回限りの特権仮想アカウントを使用するように構成されている場合、DNS 管理者は*特権のない*資格情報を使用してサーバーに接続できる一方で、特権のあるコマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="07199-115">Better yet, when the JEA session is configured to use one-time privileged virtual accounts, your DNS administrators can connect to the server using *unprivileged* credentials and still be able to run privileged commands.</span></span>

## <a name="availability"></a><span data-ttu-id="07199-116">可用性</span><span class="sxs-lookup"><span data-stu-id="07199-116">Availability</span></span>
<span data-ttu-id="07199-117">JEA は今後の Windows Server 2016 と並行して開発中であり、Windows Management Framework 更新プログラムを通じて以前のバージョンの Windows で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="07199-117">JEA is being developed in parallel to Windows Server 2016, and is available on older versions of Windows through Windows Management Framework updates.</span></span>
<span data-ttu-id="07199-118">JEA の現在のリリースは、次のプラットフォームで使用できます。</span><span class="sxs-lookup"><span data-stu-id="07199-118">The current release of JEA is available on the following platforms:</span></span>

<span data-ttu-id="07199-119">**Windows Server**</span><span class="sxs-lookup"><span data-stu-id="07199-119">**Windows Server**</span></span>
- <span data-ttu-id="07199-120">Windows Server 2016 Technical Preview 4 以降</span><span class="sxs-lookup"><span data-stu-id="07199-120">Windows Server 2016 Technical Preview 4 and higher</span></span>
- <span data-ttu-id="07199-121">[Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) がインストールされた Windows Server 2012 R2、2012、および 2008 R2\*</span><span class="sxs-lookup"><span data-stu-id="07199-121">Windows Server 2012 R2, 2012, and 2008 R2\* with [Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) installed</span></span>

<span data-ttu-id="07199-122">**Windows クライアント**</span><span class="sxs-lookup"><span data-stu-id="07199-122">**Windows Client**</span></span>
- <span data-ttu-id="07199-123">11 月の更新プログラム (1511) がインストールされた Windows 10</span><span class="sxs-lookup"><span data-stu-id="07199-123">Windows 10 with the November Update (1511) installed</span></span>
- <span data-ttu-id="07199-124">[Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) がインストールされた Windows 8.1、8、および 7\*</span><span class="sxs-lookup"><span data-stu-id="07199-124">Windows 8.1, 8, and 7\* with [Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) installed</span></span>

<span data-ttu-id="07199-125">\* JEA セッションの仮想アカウントのサポートは、現在 Windows Server 2008 R2 または Windows 7 では利用できません。</span><span class="sxs-lookup"><span data-stu-id="07199-125">\* Support for virtual accounts in JEA sessions is currently not available on Windows Server 2008 R2 or Windows 7.</span></span>


## <a name="explore-the-experience-guide"></a><span data-ttu-id="07199-126">エクスペリエンス ガイドの利用</span><span class="sxs-lookup"><span data-stu-id="07199-126">Explore the experience guide</span></span>
<span data-ttu-id="07199-127">ここでは、独自の JEA エンドポイントを作成、展開、使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="07199-127">Ready to learn how to author, deploy, and use your own JEA endpoint?</span></span>

<span data-ttu-id="07199-128">このガイドでは、事前構築された JEA エンドポイントを使用してエンドユーザー エクスペリエンスとはどのようなものかを知ることですばやく作業を開始できます。また、セッション構成やロール機能などの概念の実証に役立つように、エンドポイントを最初から再作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="07199-128">This guide gets you started quickly with a pre-built JEA endpoint to get an idea of what the end-user experience is like, then walks you through recreating an endpoint from scratch to help demonstrate concepts like session configurations and Role Capabilities.</span></span>

1.  <span data-ttu-id="07199-129">[はじめに](introduction.md) </span><span class="sxs-lookup"><span data-stu-id="07199-129">[Introduction](introduction.md) </span></span>  
<span data-ttu-id="07199-130">JEA を検討する必要がある理由を簡単に説明します</span><span class="sxs-lookup"><span data-stu-id="07199-130">Briefly review why you should care about JEA</span></span>

2.  [<span data-ttu-id="07199-131">前提条件</span><span class="sxs-lookup"><span data-stu-id="07199-131">Prerequisites</span></span>](prerequisites.md)  
<span data-ttu-id="07199-132">環境の設定方法を説明します</span><span class="sxs-lookup"><span data-stu-id="07199-132">Explains how to set up your environment</span></span>

3.  [<span data-ttu-id="07199-133">JEA の使用</span><span class="sxs-lookup"><span data-stu-id="07199-133">Using JEA</span></span>](using-jea.md)  
<span data-ttu-id="07199-134">JEA を使用するオペレーターのエクスペリエンスを理解することから始めます</span><span class="sxs-lookup"><span data-stu-id="07199-134">Helps you start by understanding the operator experience of using JEA</span></span>

4.  [<span data-ttu-id="07199-135">デモを作り直す</span><span class="sxs-lookup"><span data-stu-id="07199-135">Remake the Demo</span></span>](remake-the-demo-endpoint.md)  
<span data-ttu-id="07199-136">JEA セッション構成を最初から作成します</span><span class="sxs-lookup"><span data-stu-id="07199-136">Create a JEA Session Configuration from scratch</span></span>

5.  [<span data-ttu-id="07199-137">ロール機能</span><span class="sxs-lookup"><span data-stu-id="07199-137">Role Capabilities</span></span>](role-capabilities.md)  
<span data-ttu-id="07199-138">ロール機能ファイルを使用して JEA の機能をカスタマイズする方法について説明します</span><span class="sxs-lookup"><span data-stu-id="07199-138">Learn about how to customize JEA capabilities with Role Capability Files</span></span>

6.  [<span data-ttu-id="07199-139">エンド ツー エンド - Active Directory</span><span class="sxs-lookup"><span data-stu-id="07199-139">End to End - Active Directory</span></span>](end-to-end---active-directory.md)  
<span data-ttu-id="07199-140">Active Directory を管理するためのまったく新しいエンドポイントを作成します</span><span class="sxs-lookup"><span data-stu-id="07199-140">Make a whole new endpoint for managing Active Directory</span></span>

7.  [<span data-ttu-id="07199-141">複数のコンピューターの展開と保守</span><span class="sxs-lookup"><span data-stu-id="07199-141">Multi-machine Deployment and Maintenance</span></span>](multi-machine-deployment-and-maintenance.md)  
<span data-ttu-id="07199-142">規模によって展開と作成がどのように変化するかを理解します</span><span class="sxs-lookup"><span data-stu-id="07199-142">Discover how deployment and authoring changes with scale</span></span>

8.  [<span data-ttu-id="07199-143">JEA のレポート</span><span class="sxs-lookup"><span data-stu-id="07199-143">Reporting on JEA</span></span>](reporting-on-jea.md)  
<span data-ttu-id="07199-144">JEA のすべての操作とインフラストラクチャの監査とレポート方法を理解します</span><span class="sxs-lookup"><span data-stu-id="07199-144">Discover how to audit and report on all JEA actions and infrastructure</span></span>

9.  <span data-ttu-id="07199-145">付録</span><span class="sxs-lookup"><span data-stu-id="07199-145">Appendixes</span></span>
  - [<span data-ttu-id="07199-146">このガイドで使用される主要概念</span><span class="sxs-lookup"><span data-stu-id="07199-146">Key Concepts Used Throughout This Guide</span></span>](key-concepts-used-throughout-this-guide.md)  
  -  [<span data-ttu-id="07199-147">ドメイン コントローラーの作成</span><span class="sxs-lookup"><span data-stu-id="07199-147">Creating a Domain Controller</span></span>](creating-a-domain-controller.md)  
  -  [<span data-ttu-id="07199-148">ブラックリストへの登録</span><span class="sxs-lookup"><span data-stu-id="07199-148">On Blacklisting</span></span>](on-blacklisting.md)  
  -  [<span data-ttu-id="07199-149">コマンドの制限時の考慮事項</span><span class="sxs-lookup"><span data-stu-id="07199-149">Considerations When Limiting Commands</span></span>](considerations-when-limiting-commands.md)  
  -  [<span data-ttu-id="07199-150">ロール機能のよくある落とし穴</span><span class="sxs-lookup"><span data-stu-id="07199-150">Common Role Capability Pitfalls</span></span>](common-role-capability-pitfalls.md)

## <a name="start-authoring-your-own-jea-endpoints"></a><span data-ttu-id="07199-151">独自の JEA エンドポイントの作成を開始する</span><span class="sxs-lookup"><span data-stu-id="07199-151">Start authoring your own JEA endpoints</span></span>
<span data-ttu-id="07199-152">JEA エンドポイントの作成は簡単です。必要なのは、JEA 対応のシステムとテキスト エディター (PowerShell ISE など) だけです。</span><span class="sxs-lookup"><span data-stu-id="07199-152">It's easy to author a JEA endpoint -- all you need is a JEA-enabled system and a text editor (like PowerShell ISE).</span></span>
<span data-ttu-id="07199-153">作業開始に役立つヒントは、[`New-PSRoleCapabilityFile -Path <path>`](https://technet.microsoft.com/library/mt631422.aspx) および [`New-PSSessionConfigurationFile -Path <Path>`](https://technet.microsoft.com/library/mt631422.aspx) を使用して、他の引数は使用せずにスケルトン ファイルを作成することです。</span><span class="sxs-lookup"><span data-stu-id="07199-153">One helpful tip to get started is to create skeleton files using [`New-PSRoleCapabilityFile -Path <path>`](https://technet.microsoft.com/library/mt631422.aspx) and [`New-PSSessionConfigurationFile -Path <Path>`](https://technet.microsoft.com/library/mt631422.aspx) without any other arguments.</span></span>
<span data-ttu-id="07199-154">これらのスケルトン ファイルには、すべての適用可能な構成フィールドと、各フィールドの使用目的を説明するコメントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="07199-154">These skeleton files contain all of the applicable configuration fields along with helpful comments to explain what each field can be used for.</span></span>

<span data-ttu-id="07199-155">JEA エンドポイントのさらに簡単な作成方法については、[JEA ツールキット ヘルパー](http://blogs.technet.com/b/privatecloud/archive/2015/12/20/introducing-the-updated-jea-helper-tool.aspx)を参照してください。ここに用意された GUI を使用して、セッション構成およびロール機能ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="07199-155">To make authoring JEA endpoints even easier, check out the [JEA Toolkit Helper](http://blogs.technet.com/b/privatecloud/archive/2015/12/20/introducing-the-updated-jea-helper-tool.aspx) which provides a GUI with which you can author Session Configuration and Role Capability files.</span></span>
<span data-ttu-id="07199-156">また、PowerShell ログに基づいたロール機能の生成もサポートされており、ユーザーが業務で通常実行するコマンドで作業を開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="07199-156">It even supports generating Role Capabilities based on PowerShell logs to start you off with the commands your users regularly run to get their jobs done.</span></span>

