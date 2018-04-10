---
ms.date: 06/12/2017
author: rpsqrd
ms.topic: conceptual
keywords: JEA, PowerShell, セキュリティ
title: Just Enough Administration の概要
ms.openlocfilehash: fd5b97b7a483908f10cec6460d4e803740f064a8
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="just-enough-administration"></a><span data-ttu-id="88a4b-103">Just Enough Administration</span><span class="sxs-lookup"><span data-stu-id="88a4b-103">Just Enough Administration</span></span>

<span data-ttu-id="88a4b-104">Just Enough Administration (JEA) は、PowerShell で管理できるものすべてに対する委任された管理を有効にするセキュリティ テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="88a4b-104">Just Enough Administration (JEA) is a security technology that enables delegated administration for anything that can be managed with PowerShell.</span></span>
<span data-ttu-id="88a4b-105">JEA を使用すると、以下のことを実行できます。</span><span class="sxs-lookup"><span data-stu-id="88a4b-105">With JEA, you can:</span></span>

- <span data-ttu-id="88a4b-106">通常のユーザーに代わって特権の必要な操作を実行する仮想アカウントまたはグループの管理されたサービス アカウントを活用することによって、**お使いのコンピューター上の管理者の数を減らします。**</span><span class="sxs-lookup"><span data-stu-id="88a4b-106">**Reduce the number of administrators on your machines** by leveraging virtual accounts or group managed service accounts that perform privileged actions on behalf of regular users.</span></span>
- <span data-ttu-id="88a4b-107">**ユーザーが実行できる操作を制限します**。ここでは、ユーザーが実行できるコマンドレット、関数、および外部コマンドを指定できます。</span><span class="sxs-lookup"><span data-stu-id="88a4b-107">**Limit what users can do** by specifying which cmdlets, functions, and external commands they can run.</span></span>
- <span data-ttu-id="88a4b-108">トランスクリプションとログを使用して、**ユーザーの操作を把握します**。このトランスクリプションとログは、ユーザーがセッション中にどんなコマンドを実行したかを正確に示します。</span><span class="sxs-lookup"><span data-stu-id="88a4b-108">**Better understand what your users are doing** with transcripts and logs that show you exactly which commands a user executed during their session.</span></span>

<span data-ttu-id="88a4b-109">**これが重要な理由:**</span><span class="sxs-lookup"><span data-stu-id="88a4b-109">**Why is this important?**</span></span>

<span data-ttu-id="88a4b-110">サーバーの管理に使用される高い特権を持つアカウントには、深刻なセキュリティ リスクがあります。</span><span class="sxs-lookup"><span data-stu-id="88a4b-110">Highly privileged accounts used to administer your servers pose a serious security risk.</span></span>
<span data-ttu-id="88a4b-111">そのようなアカウントが攻撃者に狙われた場合、組織全体に[横展開の攻撃](http://aka.ms/pth)が始まります。</span><span class="sxs-lookup"><span data-stu-id="88a4b-111">Should an attacker compromise one of these accounts, they could launch [lateral attacks](http://aka.ms/pth) across your organization.</span></span>
<span data-ttu-id="88a4b-112">侵害されたアカウントがさらに多くのアカウントやリソースへのアクセスを与え、会社の機密情報の盗難に一歩近づき、サービス拒否攻撃などが始まります。</span><span class="sxs-lookup"><span data-stu-id="88a4b-112">Each account they compromise can give them access to even more accounts and resources, putting them one step closer to stealing company secrets, launching a denial-of-service attack, and more.</span></span>

<span data-ttu-id="88a4b-113">しかしながら、管理者特権を削除することは簡単なことではありません。</span><span class="sxs-lookup"><span data-stu-id="88a4b-113">It is not always easy to remove administrative privileges, either.</span></span>
<span data-ttu-id="88a4b-114">DNS ロールが Active Directory ドメイン コントローラーと同じコンピューターにインストールされるという一般的なシナリオについて考えてみてください。</span><span class="sxs-lookup"><span data-stu-id="88a4b-114">Consider the common scenario where the DNS role is installed on the same machine as your Active Directory Domain Controller.</span></span>
<span data-ttu-id="88a4b-115">DNS 管理者は、DNS サーバーでの問題を解決するためにローカル管理者特権が必要ですが、そのためには、これらの管理者を高い特権を持つ "Domain Admins" セキュリティ グループのメンバーにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="88a4b-115">Your DNS administrators require local administrator privileges to fix issues with the DNS server, but in order to do so you have to make them members of the highly privileged "Domain Admins" security group.</span></span>
<span data-ttu-id="88a4b-116">この方法は、ドメイン全体への制御や、そのコンピューター上のすべてのリソースへのアクセス権を DNS 管理者に効果的に付与します。</span><span class="sxs-lookup"><span data-stu-id="88a4b-116">This approach effectively gives DNS Administrators control over your whole domain and access to all resources on that machine.</span></span>

<span data-ttu-id="88a4b-117">JEA は*最小限の特権*の原則の導入を支援し、この問題の対処に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="88a4b-117">JEA helps address this problem by helping you adopt the principle of *Least Privilege*.</span></span>
<span data-ttu-id="88a4b-118">JEA を利用すると、DNS 管理者に管理エンドポイントを構成して、これらの管理者が作業を行うのに必要なすべての PowerShell コマンドにアクセスできるように、またそれ以外のことを実行できないように指定できます。</span><span class="sxs-lookup"><span data-stu-id="88a4b-118">With JEA, you can configure a management endpoint for DNS administrators that gives them access to all the PowerShell commands they need to get their job done, but nothing more.</span></span>
<span data-ttu-id="88a4b-119">つまり、DNS 管理者に Active Directory への権限を付与しなくても、侵害された DNS キャッシュを修復したり、DNS サーバーを再起動したり、またはファイル システムを参照したり、潜在的に危険性なスクリプトを実行したりできる適切なアクセスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="88a4b-119">This means you can provide the appropriate access to repair a poisoned DNS cache or restart the DNS server without unintentionally giving them rights to Active Directory, or to browse the file system, or run potentially dangerous scripts.</span></span>
<span data-ttu-id="88a4b-120">さらに、JEA セッションが一時的な特権仮想アカウントを使用するように構成されている場合、DNS 管理者は*管理者以外の*資格情報を使用してサーバーに接続できる一方で、一般的には管理者特権を必要とするコマンドも実行できます。</span><span class="sxs-lookup"><span data-stu-id="88a4b-120">Better yet, when the JEA session is configured to use temporary privileged virtual accounts, your DNS administrators can connect to the server using *non-admin* credentials and still be able to run commands which typically require admin privileges.</span></span>
<span data-ttu-id="88a4b-121">この機能により、幅広い特権が与えられたローカル/ドメイン管理者ロールからユーザーを削除し、代わりに、各コンピューターでユーザーに許可する操作を慎重に制御できます。</span><span class="sxs-lookup"><span data-stu-id="88a4b-121">This capability enables you to remove users from widely-privileged local/domain administrator roles and instead carefully control what they are able to do on each machine.</span></span>

## <a name="get-started-with-jea"></a><span data-ttu-id="88a4b-122">JEA の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="88a4b-122">Get Started with JEA</span></span>

<span data-ttu-id="88a4b-123">現在、Windows Server 2016 か Windows 10 を実行しているあらゆるコンピューターで JEA の使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="88a4b-123">You can start using JEA today on any machine running Windows Server 2016 or Windows 10.</span></span>
<span data-ttu-id="88a4b-124">JEA は、Windows Management Framework の更新プログラムがインストールしてある以前のオペレーティング システムでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="88a4b-124">You can also run JEA on older operating systems with a Windows Management Framework update.</span></span>
<span data-ttu-id="88a4b-125">JEA の使用要件、JEA エンドポイントの作成、使用、監査方法については、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="88a4b-125">To learn more about the requirements to use JEA and to learn how to create, use, and audit a JEA endpoint, check out the following topics:</span></span>

- <span data-ttu-id="88a4b-126">[前提条件](prerequisites.md) - JEA を使用するための環境の設定方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="88a4b-126">[Prerequisites](prerequisites.md) - explains how to set up your environment to use JEA.</span></span>
- <span data-ttu-id="88a4b-127">[ロール機能](role-capabilities.md) - JEA セッションでユーザーに許可する操作を決定するロールの作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="88a4b-127">[Role Capabilities](role-capabilities.md) - explains how to create roles which determine what a user is allowed to do in a JEA session.</span></span>
- <span data-ttu-id="88a4b-128">[セッション構成](session-configurations.md) - ユーザーをロールにマッピングし、JEA ID を設定する JEA エンドポイントの構成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="88a4b-128">[Session Configurations](session-configurations.md) - explains how to configure JEA endpoints that map users to roles and set the JEA identity</span></span>
- <span data-ttu-id="88a4b-129">[JEA の登録](register-jea.md) - JEA エンドポイントを作成し、ユーザーがそれに接続できるようにします。</span><span class="sxs-lookup"><span data-stu-id="88a4b-129">[Registering JEA](register-jea.md) - create a JEA endpoint and make it available for users to connect to.</span></span>
- <span data-ttu-id="88a4b-130">[JEA の使用](using-jea.md) - JEA のさまざまな使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="88a4b-130">[Using JEA](using-jea.md) - learn the various ways you can use JEA.</span></span>
- <span data-ttu-id="88a4b-131">[セキュリティの考慮事項](security-considerations.md) - JEA 構成オプションのセキュリティ ベスト プラクティスとその意味について確認します。</span><span class="sxs-lookup"><span data-stu-id="88a4b-131">[Security Considerations](security-considerations.md) - review security best practices and implications of JEA configuration options.</span></span>
- <span data-ttu-id="88a4b-132">[JEA の監査とレポート](audit-and-report.md) - JEA エンドポイントの監査とレポートの方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="88a4b-132">[Audit and Report on JEA](audit-and-report.md) - learn how to audit and report on JEA endpoints.</span></span>

## <a name="samples-and-dsc-resource"></a><span data-ttu-id="88a4b-133">サンプルと DSC のリソース</span><span class="sxs-lookup"><span data-stu-id="88a4b-133">Samples and DSC resource</span></span>

<span data-ttu-id="88a4b-134">JEA 構成の例と JEA DSC リソースは [JEA GitHub リポジトリ](https://github.com/PowerShell/JEA)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="88a4b-134">Sample JEA configurations and the JEA DSC resource can be found in the [JEA GitHub repository](https://github.com/PowerShell/JEA).</span></span>