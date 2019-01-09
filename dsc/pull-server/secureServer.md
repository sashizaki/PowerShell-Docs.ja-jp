---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: プル サーバーのベスト プラクティス
ms.openlocfilehash: da67f8fd793878b097ffb260afad0fcf5c69bb04
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402974"
---
# <a name="pull-server-best-practices"></a><span data-ttu-id="913f8-103">プル サーバーのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="913f8-103">Pull server best practices</span></span>

<span data-ttu-id="913f8-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="913f8-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="913f8-105">プル サーバー (Windows Feature *DSC-Service*) は、Windows Server のサポート対象のコンポーネントですが、新機能がオファーされる予定はありません。</span><span class="sxs-lookup"><span data-stu-id="913f8-105">The Pull Server (Windows Feature *DSC-Service*) is a supported component of Windows Server however there are no plans to offer new features or capabilities.</span></span> <span data-ttu-id="913f8-106">管理対象のクライアントは、(Windows Server のプル サーバー以降の機能が含まれる) [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) または、[こちら](pullserver.md#community-solutions-for-pull-service)に列挙されているコミュニティ ソリューションのいずれかに切り替えを開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="913f8-106">It is recommended to begin transitioning managed clients to [Azure Automation DSC](/azure/automation/automation-dsc-getting-started) (includes features beyond Pull Server on Windows Server) or one of the community solutions listed [here](pullserver.md#community-solutions-for-pull-service).</span></span>

<span data-ttu-id="913f8-107">要約:このドキュメントは、プロセスと、ソリューション用に準備するエンジニアを支援するために拡張機能を対象としています。</span><span class="sxs-lookup"><span data-stu-id="913f8-107">Summary: This document is intended to include process and extensibility to assist engineers who are preparing for the solution.</span></span> <span data-ttu-id="913f8-108">ベスト プラクティスに関する推奨事項は、将来を見据えた安定したものにするために、お客様によって確認され、製品チームによって検証されたベスト プラクティスの詳細を示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="913f8-108">Details should provide best practices as identified by customers and then validated by the product team to ensure recommendations are future facing and considered stable.</span></span>

| |<span data-ttu-id="913f8-109">ドキュメント情報</span><span class="sxs-lookup"><span data-stu-id="913f8-109">Doc Info</span></span>|
|:---|:---|
<span data-ttu-id="913f8-110">作成者</span><span class="sxs-lookup"><span data-stu-id="913f8-110">Author</span></span> | <span data-ttu-id="913f8-111">Michael Greene</span><span class="sxs-lookup"><span data-stu-id="913f8-111">Michael Greene</span></span>
<span data-ttu-id="913f8-112">校閲者</span><span class="sxs-lookup"><span data-stu-id="913f8-112">Reviewers</span></span> | <span data-ttu-id="913f8-113">Ben Gelens、Ravikanth Chaganti、Aleksandar Nikolic</span><span class="sxs-lookup"><span data-stu-id="913f8-113">Ben Gelens, Ravikanth Chaganti, Aleksandar Nikolic</span></span>
<span data-ttu-id="913f8-114">公開済み</span><span class="sxs-lookup"><span data-stu-id="913f8-114">Published</span></span> | <span data-ttu-id="913f8-115">2015 年 4 月</span><span class="sxs-lookup"><span data-stu-id="913f8-115">April, 2015</span></span>

## <a name="abstract"></a><span data-ttu-id="913f8-116">概要</span><span class="sxs-lookup"><span data-stu-id="913f8-116">Abstract</span></span>

<span data-ttu-id="913f8-117">このドキュメントは、Windows PowerShell Desired State Configuration プル サーバーの実装を計画しているすべてのユーザー向けの公式なガイダンスを提供するためのものです。</span><span class="sxs-lookup"><span data-stu-id="913f8-117">This document is designed to provide official guidance for anyone planning for a Windows PowerShell Desired State Configuration pull server implementation.</span></span> <span data-ttu-id="913f8-118">プル サーバーは単純なサービスで、数分で展開できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="913f8-118">A pull server is a simple service that should take only minutes to deploy.</span></span> <span data-ttu-id="913f8-119">このドキュメントは展開で使用できる技術的な操作方法に関するガイダンスを提供するものですが、ベスト プラクティスと、展開の前に考慮すべきことを参照する場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="913f8-119">Although this document will offer technical how-to guidance that can be used in a deployment, the value of this document is as a reference for best practices and what to think about before deploying.</span></span>
<span data-ttu-id="913f8-120">読者は DSC と、DSC 展開に含まれるコンポーネントの説明で使用される用語の基礎をよく理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="913f8-120">Readers should have basic familiarity with DSC, and the terms used to describe the components that are included in a DSC deployment.</span></span> <span data-ttu-id="913f8-121">詳細については、「[Windows PowerShell Desired State Configuration の概要](/powershell/dsc/overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="913f8-121">For more information, see the [Windows PowerShell Desired State Configuration Overview](/powershell/dsc/overview)  topic.</span></span>
<span data-ttu-id="913f8-122">DSC はクラウドと共に進化することを想定しているため、プル サーバーを含む基礎技術にも進化と、新機能の導入が求められます。</span><span class="sxs-lookup"><span data-stu-id="913f8-122">As DSC is expected to evolve at cloud cadence, the underlying technology including pull server is also expected to evolve and to introduce new capabilities.</span></span> <span data-ttu-id="913f8-123">このドキュメントには、以前のリリースへの参照と、先進的な設計を促進する将来を見据えたソリューションへの参照を提供する付録にバージョン テーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="913f8-123">This document includes a version table in the appendix that provides references to previous releases and references to future looking solutions to encourage forward-looking designs.</span></span>

<span data-ttu-id="913f8-124">このドキュメントの主な 2 つのセクションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="913f8-124">The two major sections of this document:</span></span>

- <span data-ttu-id="913f8-125">構成計画</span><span class="sxs-lookup"><span data-stu-id="913f8-125">Configuration Planning</span></span>
- <span data-ttu-id="913f8-126">インストール ガイド</span><span class="sxs-lookup"><span data-stu-id="913f8-126">Installation Guide</span></span>

### <a name="versions-of-the-windows-management-framework"></a><span data-ttu-id="913f8-127">Windows Management Framework のバージョン</span><span class="sxs-lookup"><span data-stu-id="913f8-127">Versions of the Windows Management Framework</span></span>

<span data-ttu-id="913f8-128">このドキュメントの情報は、Windows Management Framework 5.0 に適用するためのものです。</span><span class="sxs-lookup"><span data-stu-id="913f8-128">The information in this document is intended to apply to Windows Management Framework 5.0.</span></span> <span data-ttu-id="913f8-129">プル サーバーの展開と操作で WMF 5.0 は必要ありませんが、このドキュメントではバージョン 5.0 に焦点を合わせています。</span><span class="sxs-lookup"><span data-stu-id="913f8-129">While WMF 5.0 is not required for deploying and operating a pull server, version 5.0 is the focus of this document.</span></span>

### <a name="windows-powershell-desired-state-configuration"></a><span data-ttu-id="913f8-130">Windows PowerShell の必要な状態の構成</span><span class="sxs-lookup"><span data-stu-id="913f8-130">Windows PowerShell Desired State Configuration</span></span>

<span data-ttu-id="913f8-131">Desired State Configuration (DSC) は、Common Information Model (CIM) を記述するためにマネージド オブジェクト フォーマット (MOF) という業界構文を使用して、構成データの展開と管理を可能にする管理プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="913f8-131">Desired State Configuration (DSC) is a management platform that enables deploying and managing configuration data by using an industry syntax named the Managed Object Format (MOF) to describe the Common Information Model (CIM).</span></span> <span data-ttu-id="913f8-132">オープン ソース プロジェクトの Open Management Infrastructure (OMI) は、Linux とネットワーク ハードウェア オペレーティング システムを含むプラットフォーム全体でこれらの標準をさらに開発するために存在します。</span><span class="sxs-lookup"><span data-stu-id="913f8-132">An open source project, Open Management Infrastructure (OMI), exists to further development of these standards across platforms including Linux and network hardware operating systems.</span></span> <span data-ttu-id="913f8-133">詳細については、[MOF 仕様にリンクされている DMTF ページ](https://www.dmtf.org/standards/cim)、および [OMI のドキュメントとソース](https://collaboration.opengroup.org/omi/documents.php)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="913f8-133">For more information, see the [DMTF page linking to MOF specifications](https://www.dmtf.org/standards/cim), and [OMI Documents and Source](https://collaboration.opengroup.org/omi/documents.php).</span></span>

<span data-ttu-id="913f8-134">Windows PowerShell には、宣言構成を作成および管理するために使用できる Desired State Configuration の一連の言語拡張が用意されています。</span><span class="sxs-lookup"><span data-stu-id="913f8-134">Windows PowerShell provides a set of language extensions for Desired State Configuration that you can use to create and manage declarative configurations.</span></span>

### <a name="pull-server-role"></a><span data-ttu-id="913f8-135">プル サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="913f8-135">Pull server role</span></span>

<span data-ttu-id="913f8-136">プル サーバーでは、ターゲット ノードにアクセス可能な構成を格納する中央サービスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="913f8-136">A pull server provides a centralized service to store configurations that will be accessible to target nodes.</span></span>

<span data-ttu-id="913f8-137">プル サーバーの役割は、Web サーバー インスタンスまたは SMB ファイル共有のいずれかとして展開することができます。</span><span class="sxs-lookup"><span data-stu-id="913f8-137">The pull server role can be deployed as either a Web Server instance or an SMB file share.</span></span> <span data-ttu-id="913f8-138">Web サーバー機能には OData インターフェイスが含まれており、構成の適用時に成功または失敗の確認を報告するターゲット ノードの機能もオプションで含めることができます。</span><span class="sxs-lookup"><span data-stu-id="913f8-138">The web server capability includes an OData interface and can optionally include capabilities for target nodes to report back confirmation of success or failure as configurations are applied.</span></span> <span data-ttu-id="913f8-139">この機能は、多数のターゲット ノードが存在する環境で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="913f8-139">This functionality is useful in environments where there are a large number of target nodes.</span></span>
<span data-ttu-id="913f8-140">プル サーバーをポイントするようにターゲット ノード (クライアントとも呼ばれる) を構成した後で、最新の構成データと必要なすべてのスクリプトがダウンロードされ、適用されます。</span><span class="sxs-lookup"><span data-stu-id="913f8-140">After configuring a target node (also referred to as a client) to point to the pull server the latest configuration data and any required scripts are downloaded and applied.</span></span> <span data-ttu-id="913f8-141">これは、1 回限りの展開として、またはプル サーバーを大規模な変更を管理するための重要な資産とする再発ジョブとして行われる場合があります。</span><span class="sxs-lookup"><span data-stu-id="913f8-141">This can happen as a one-time deployment or as a re-occurring job which also makes the pull server an important asset for managing change at scale.</span></span> <span data-ttu-id="913f8-142">詳細については、「[Windows PowerShell Desired State Configuration プル サーバー](/powershell/dsc/pullServer)」および</span><span class="sxs-lookup"><span data-stu-id="913f8-142">For more information, see [Windows PowerShell Desired State Configuration Pull Servers](/powershell/dsc/pullServer) and</span></span>

<span data-ttu-id="913f8-143">「[Push and Pull Configuration Modes](/powershell/dsc/pullServer)」(構成モードのプッシュとプル) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="913f8-143">[Push and Pull Configuration Modes](/powershell/dsc/pullServer).</span></span>

## <a name="configuration-planning"></a><span data-ttu-id="913f8-144">構成計画</span><span class="sxs-lookup"><span data-stu-id="913f8-144">Configuration planning</span></span>

<span data-ttu-id="913f8-145">エンタープライズ ソフトウェアの展開の場合、事前に収集できる情報があります。この情報は、適切なアーキテクチャの計画と、展開を完了するために必要な手順を準備に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="913f8-145">For any enterprise software deployment there is information that can be collected in advance to help plan for the correct architecture and to be prepared for the steps required to complete the deployment.</span></span> <span data-ttu-id="913f8-146">次のセクションでは、準備方法と、事前に必要となる可能性がある組織的な接続に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="913f8-146">The following sections provide information regarding how to prepare and the organizational connections that will likely need to happen in advance.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="913f8-147">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="913f8-147">Software requirements</span></span>

<span data-ttu-id="913f8-148">プル サーバーの展開には、Windows Server の DSC サービス機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="913f8-148">Deployment of a pull server requires the DSC Service feature of Windows Server.</span></span> <span data-ttu-id="913f8-149">この機能は、Windows Server 2012 で導入されたもので、Windows 管理フレームワーク (WMF) の継続的なリリースを通じて更新されています。</span><span class="sxs-lookup"><span data-stu-id="913f8-149">This feature was introduced in Windows Server 2012, and has been updated through ongoing releases of Windows Management Framework (WMF).</span></span>

### <a name="software-downloads"></a><span data-ttu-id="913f8-150">ソフトウェアのダウンロード</span><span class="sxs-lookup"><span data-stu-id="913f8-150">Software downloads</span></span>

<span data-ttu-id="913f8-151">Windows Update から最新のコンテンツをインストールすることに加えて、ベスト プラクティスとして、DSC プル サーバーの展開と見なされる 2 つのダウンロードがあります。プル サーバーのプロビジョニングを自動化するには、Windows Management Framework と DSC モジュールの最新バージョン。</span><span class="sxs-lookup"><span data-stu-id="913f8-151">In addition to installing the latest content from Windows Update, there are two downloads considered best practice to deploy a DSC pull server: The latest version of Windows Management Framework, and a DSC module to automate pull server provisioning.</span></span>

### <a name="wmf"></a><span data-ttu-id="913f8-152">WMF</span><span class="sxs-lookup"><span data-stu-id="913f8-152">WMF</span></span>

<span data-ttu-id="913f8-153">Windows Server 2012 R2 には、DSC サービスという機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="913f8-153">Windows Server 2012 R2 includes a feature named the DSC Service.</span></span> <span data-ttu-id="913f8-154">DSC サービス機能では、OData エンドポイントをサポートするバイナリを含む、プル サーバー機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="913f8-154">The DSC Service feature provides the pull server functionality, including the binaries that support the OData endpoint.</span></span>
<span data-ttu-id="913f8-155">WMF は Windows Server に含まれており、Windows Server のリリースに応じて迅速に更新されます。</span><span class="sxs-lookup"><span data-stu-id="913f8-155">WMF is included in Windows Server and is updated on an agile cadence between Windows Server releases.</span></span> <span data-ttu-id="913f8-156">[新しいバージョンの WMF 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=54616) には、DSC サービス機能の更新プログラムが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="913f8-156">[New versions of WMF 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=54616)  can include updates to the DSC Service feature.</span></span> <span data-ttu-id="913f8-157">そのため、WMF の最新リリースをダウンロードし、リリース ノートを確認し、リリースに DSC サービス機能の更新プログラムが含まれるかどうか判断することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="913f8-157">For this reason, it is a best practice to download the latest release of WMF and to review the release notes to determine if the release includes an update to the DSC service feature.</span></span> <span data-ttu-id="913f8-158">さらに、更新プログラムまたはシナリオの設計が安定状態であるか実験状態であるかを示すリリース ノートのセクションを確認する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="913f8-158">You should also review the section of the release notes that indicates whether the design status for an update or scenario is listed as stable or experimental.</span></span>
<span data-ttu-id="913f8-159">アジャイル リリース サイクルを可能にするために、個々の機能を安定したものとして宣言することができます。これにより、WMF がプレビューでリリースされている間でも、機能は運用環境で使用する準備ができていることが示されます。</span><span class="sxs-lookup"><span data-stu-id="913f8-159">To allow for an agile release cycle, individual features can be declared stable, which indicates the feature is ready to be used in a production environment even while WMF is released in preview.</span></span>
<span data-ttu-id="913f8-160">WMF リリースで既に更新されている他の機能は、次のとおりです (詳細については、WMF リリース ノートを参照)。</span><span class="sxs-lookup"><span data-stu-id="913f8-160">Other features that have historically been updated by WMF releases (see the WMF Release Notes for further detail):</span></span>

- <span data-ttu-id="913f8-161">Windows PowerShell、Windows PowerShell Integrated Scripting Environment (ISE)</span><span class="sxs-lookup"><span data-stu-id="913f8-161">Windows PowerShell Windows PowerShell Integrated Scripting</span></span>
- <span data-ttu-id="913f8-162">Windows PowerShell Web サービス (Management OData IIS 拡張機能)</span><span class="sxs-lookup"><span data-stu-id="913f8-162">Environment (ISE) Windows PowerShell Web Services (Management OData</span></span>
- <span data-ttu-id="913f8-163">Windows PowerShell Desired State Configuration (DSC)</span><span class="sxs-lookup"><span data-stu-id="913f8-163">IIS Extension)  Windows PowerShell Desired State Configuration (DSC)</span></span>
- <span data-ttu-id="913f8-164">Windows Remote Management (WinRM)、Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="913f8-164">Windows Remote Management (WinRM) Windows Management Instrumentation (WMI)</span></span>

### <a name="dsc-resource"></a><span data-ttu-id="913f8-165">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="913f8-165">DSC resource</span></span>

<span data-ttu-id="913f8-166">プル サーバーの展開は、DSC 構成スクリプトを使用してサービスをプロビジョニングすることで簡略化できます。</span><span class="sxs-lookup"><span data-stu-id="913f8-166">A pull server deployment can be simplified by provisioning the service using a DSC configuration script.</span></span> <span data-ttu-id="913f8-167">このドキュメントには、運用準備ができているサーバー ノードの展開で使用できる構成スクリプトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="913f8-167">This document includes configuration scripts that can be used to deploy a production ready server node.</span></span> <span data-ttu-id="913f8-168">構成スクリプトを使用するには、Windows Server に含まれていない DSC モジュールが必要になります。</span><span class="sxs-lookup"><span data-stu-id="913f8-168">To use the configuration scripts, a DSC module is required that is not included in Windows Server.</span></span> <span data-ttu-id="913f8-169">必要なモジュール名は**xPSDesiredStateConfiguration** で、DSC リソースの **xDscWebService** が含まれます。</span><span class="sxs-lookup"><span data-stu-id="913f8-169">The required module name is **xPSDesiredStateConfiguration**, which includes the DSC resource **xDscWebService**.</span></span> <span data-ttu-id="913f8-170">xPSDesiredStateConfiguration モジュールは[こちら](https://gallery.technet.microsoft.com/xPSDesiredStateConfiguratio-417dc71d)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="913f8-170">The xPSDesiredStateConfiguration module can be downloaded [here](https://gallery.technet.microsoft.com/xPSDesiredStateConfiguratio-417dc71d).</span></span>

<span data-ttu-id="913f8-171">**PowerShellGet** モジュールから `Install-Module` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="913f8-171">Use the `Install-Module` cmdlet from the **PowerShellGet** module.</span></span>

```powershell
Install-Module xPSDesiredStateConfiguration
```

<span data-ttu-id="913f8-172">**PowerShellGet** モジュールの場合、次の場所にモジュールがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="913f8-172">The **PowerShellGet** module will download the module to:</span></span>

`C:\Program Files\Windows PowerShell\Modules`

<span data-ttu-id="913f8-173">計画タスク</span><span class="sxs-lookup"><span data-stu-id="913f8-173">Planning task</span></span>|
---|
<span data-ttu-id="913f8-174">Windows Server 2012 R2 のインストール ファイルにアクセスできますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-174">Do you have access to the installation files for Windows Server 2012 R2?</span></span>|
<span data-ttu-id="913f8-175">展開環境からインターネットにアクセスし、オンライン ギャラリーから WMF とモジュールをダウンロードできますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-175">Will the deployment environment have Internet access to download WMF and the module from the online gallery?</span></span>|
<span data-ttu-id="913f8-176">オペレーティング システムをインストールした後、最新のセキュリティ更新プログラムはどのようにインストールできますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-176">How will you install the latest security updates after installing the operating system?</span></span>|
<span data-ttu-id="913f8-177">使用環境からインターネットにアクセスし、更新プログラムを取得できますか? あるいは、環境内にローカル Windows Server Update Services (WSUS) サーバーはありますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-177">Will the environment have Internet access to obtain updates, or will it have a local Windows Server Update Services (WSUS) server?</span></span>|
<span data-ttu-id="913f8-178">オフライン導入により更新プログラムが既に含まれている Windows Server インストール ファイルにアクセスできますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-178">Do you have access to Windows Server installation files that already include updates through offline injection?</span></span>|

### <a name="hardware-requirements"></a><span data-ttu-id="913f8-179">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="913f8-179">Hardware requirements</span></span>

<span data-ttu-id="913f8-180">物理サーバーと仮想サーバーの両方でプル サーバーの展開がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="913f8-180">Pull server deployments are supported on both physical and virtual servers.</span></span> <span data-ttu-id="913f8-181">プル サーバーのサイズ要件は、Windows Server 2012 R2 の要件と一致します。</span><span class="sxs-lookup"><span data-stu-id="913f8-181">The sizing requirements for pull server align with the requirements for Windows Server 2012 R2.</span></span>

<span data-ttu-id="913f8-182">CPU:1.4 GHz 64 ビット プロセッサ、メモリ:50 MB のディスク領域32 GB のネットワーク:ギガビット イーサネット アダプター</span><span class="sxs-lookup"><span data-stu-id="913f8-182">CPU: 1.4 GHz 64-bit processor Memory: 512 MB Disk Space: 32 GB Network: Gigabit Ethernet Adapter</span></span>

<span data-ttu-id="913f8-183">計画タスク</span><span class="sxs-lookup"><span data-stu-id="913f8-183">Planning task</span></span>|
---|
<span data-ttu-id="913f8-184">物理ハードウェアまたは仮想化プラットフォームに展開する予定ですか?</span><span class="sxs-lookup"><span data-stu-id="913f8-184">Will you deploy on physical hardware or on a virtualization platform?</span></span>|
<span data-ttu-id="913f8-185">ターゲット環境のために新しいサーバーを要求するプロセスは何ですか?</span><span class="sxs-lookup"><span data-stu-id="913f8-185">What is the process to request a new server for your target environment?</span></span>|
<span data-ttu-id="913f8-186">サーバーが使用可能になるまでの平均所要時間はどれくらいですか?</span><span class="sxs-lookup"><span data-stu-id="913f8-186">What is the average turnaround time for a server to become available?</span></span>|
<span data-ttu-id="913f8-187">どのようなサイズのサーバーを要求しますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-187">What size server will you request?</span></span>|

### <a name="accounts"></a><span data-ttu-id="913f8-188">[アカウント]</span><span class="sxs-lookup"><span data-stu-id="913f8-188">Accounts</span></span>

<span data-ttu-id="913f8-189">プル サーバー インスタンスを展開する場合、サービス アカウントの要件はありません。</span><span class="sxs-lookup"><span data-stu-id="913f8-189">There are no service account requirements to deploy a pull server instance.</span></span>
<span data-ttu-id="913f8-190">ただし、ローカル ユーザー アカウントのコンテキストで Web サイトを実行できるシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="913f8-190">However, there are scenarios where the website could run in the context of a local user account.</span></span>
<span data-ttu-id="913f8-191">たとえば、Web サイト コンテンツの記憶域共有にアクセスする必要があり、記憶域共有をホストしているデバイスまたは Windows Server がドメインに参加していない場合などです。</span><span class="sxs-lookup"><span data-stu-id="913f8-191">For example, if there is a need to access a storage share for website content and either the Windows Server or the device hosting the storage share are not domain joined.</span></span>

### <a name="dns-records"></a><span data-ttu-id="913f8-192">DNS レコード</span><span class="sxs-lookup"><span data-stu-id="913f8-192">DNS records</span></span>

<span data-ttu-id="913f8-193">プル サーバー環境で動作するようにクライアントを構成する際に使用するサーバー名が必要になります。</span><span class="sxs-lookup"><span data-stu-id="913f8-193">You will need a server name to use when configuring clients to work with a pull server environment.</span></span>
<span data-ttu-id="913f8-194">テスト環境では、通常、サーバーのホスト名が使用されます。DNS 名前解決が使用できない場合には、サーバーの IP アドレスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="913f8-194">In test environments, typically the server hostname is used, or the IP address for the server can be used if DNS name resolution is not available.</span></span>
<span data-ttu-id="913f8-195">運用環境、または運用環境の展開を表すためのラボ環境では、DNS CNAME レコードを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="913f8-195">In production environments or in a lab environment that is intended to represent a production deployment, the best practice is to create a DNS CNAME record.</span></span>

<span data-ttu-id="913f8-196">DNS CNAME では、ホスト (A) レコードを参照する別名を作成できます。</span><span class="sxs-lookup"><span data-stu-id="913f8-196">A DNS CNAME allows you to create an alias to refer to your host (A) record.</span></span>
<span data-ttu-id="913f8-197">追加の名前レコードの目的は、後で変更が必要になった場合に備えて柔軟性を高めることです。</span><span class="sxs-lookup"><span data-stu-id="913f8-197">The intent of the additional name record is to increase flexibility should a change be required in the future.</span></span>
<span data-ttu-id="913f8-198">CNAME はクライアント構成の分離に役立ちます。したがって、プル サーバーの置換や追加などの、サーバー環境の変更に合わせて、クライアント構成を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="913f8-198">A CNAME can help to isolate the client configuration so that changes to the server environment, such as replacing a pull server or adding additional pull servers, will not require a corresponding change to the client configuration.</span></span>

<span data-ttu-id="913f8-199">DNS レコードの名前を選択する場合は、ソリューションのアーキテクチャに注意してください。</span><span class="sxs-lookup"><span data-stu-id="913f8-199">When choosing a name for the DNS record, keep the solution architecture in mind.</span></span>
<span data-ttu-id="913f8-200">負荷分散を使用する場合、HTTPS 経由でトラフィックを保護するために使用される証明書で DNS レコードと同じ名前を共有する必要があります。</span><span class="sxs-lookup"><span data-stu-id="913f8-200">If using load balancing, the certificate used to secure traffic over HTTPS will need to share the same name as the DNS record.</span></span>

<span data-ttu-id="913f8-201">シナリオ</span><span class="sxs-lookup"><span data-stu-id="913f8-201">Scenario</span></span> |<span data-ttu-id="913f8-202">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="913f8-202">Best Practice</span></span>
:---|:---
<span data-ttu-id="913f8-203">テスト環境</span><span class="sxs-lookup"><span data-stu-id="913f8-203">Test Environment</span></span> |<span data-ttu-id="913f8-204">可能であれば、計画された運用環境を再現します。</span><span class="sxs-lookup"><span data-stu-id="913f8-204">Reproduce the planned production environment, if possible.</span></span> <span data-ttu-id="913f8-205">サーバーのホスト名は簡単な構成に適しています。</span><span class="sxs-lookup"><span data-stu-id="913f8-205">A server hostname is suitable for simple configurations.</span></span> <span data-ttu-id="913f8-206">DNS が利用できない場合は、ホスト名の代わりに IP アドレスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="913f8-206">If DNS is not available, an IP address may be used in lieu of a hostname.</span></span>|
<span data-ttu-id="913f8-207">単一ノードの展開</span><span class="sxs-lookup"><span data-stu-id="913f8-207">Single Node Deployment</span></span> |<span data-ttu-id="913f8-208">サーバーのホスト名をポイントする DNS CNAME レコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="913f8-208">Create a DNS CNAME record that points to the server hostname.</span></span>|

<span data-ttu-id="913f8-209">詳細については、[Windows Server での DNS ラウンド ロビンの構成](/previous-versions/windows/it-pro/windows-server-2003/cc787484(v=ws.10))に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="913f8-209">For more information, see [Configuring DNS Round Robin in Windows Server](/previous-versions/windows/it-pro/windows-server-2003/cc787484(v=ws.10)).</span></span>

<span data-ttu-id="913f8-210">計画タスク</span><span class="sxs-lookup"><span data-stu-id="913f8-210">Planning task</span></span>|
---|
<span data-ttu-id="913f8-211">DNS レコードの作成や変更に関する問い合わせはどこにすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="913f8-211">Do you know who to contact to have DNS records created and changed?</span></span>|
<span data-ttu-id="913f8-212">DNS レコードの要求の平均所要時間はどれくらいですか?</span><span class="sxs-lookup"><span data-stu-id="913f8-212">What is the average turnaround for a request for a DNS record?</span></span>|
<span data-ttu-id="913f8-213">サーバーの静的なホスト名 (A) レコードを要求する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-213">Do you need to request static Hostname (A) records for servers?</span></span>|
<span data-ttu-id="913f8-214">CNAME レコードとして何を要求しますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-214">What will you request as a CNAME?</span></span>|
<span data-ttu-id="913f8-215">必要な場合に、どのような種類の負荷分散ソリューションを利用しますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-215">If needed, what type of Load Balancing solution will you utilize?</span></span> <span data-ttu-id="913f8-216">(詳細については、「負荷分散」というタイトルのセクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="913f8-216">(see section titled Load Balancing for details)</span></span>|

### <a name="public-key-infrastructure"></a><span data-ttu-id="913f8-217">公開キー基盤</span><span class="sxs-lookup"><span data-stu-id="913f8-217">Public Key Infrastructure</span></span>

<span data-ttu-id="913f8-218">今日では、ほとんどの組織で、転送時にネットワーク トラフィック (特に、サーバーの構成方法などの機密データを含むトラフィック) を検証および/または暗号化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="913f8-218">Most organizations today require that network traffic, especially traffic that includes such sensitive data as how servers are configured, must be validated and/or encrypted during transit.</span></span>
<span data-ttu-id="913f8-219">クリア テキストでのクライアント要求を容易にする HTTP を使用してプル サーバーを展開できますが、HTTPS を使用してトラフィックをセキュリティで保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="913f8-219">While it is possible to deploy a pull server using HTTP which facilitates client requests in clear text, it is a best practice to secure traffic using HTTPS.</span></span> <span data-ttu-id="913f8-220">DSC リソースの **xPSDesiredStateConfiguration** で一連のパラメーターを指定して、HTTPS を使用するようにサービスを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="913f8-220">The service can be configured to use HTTPS using a set of parameters in the DSC resource **xPSDesiredStateConfiguration**.</span></span>

<span data-ttu-id="913f8-221">プル サーバーの HTTPS トラフィックをセキュリティで保護する証明書の要件は、その他の HTTPS Web サイトのセキュリティ保護と違いはありません。</span><span class="sxs-lookup"><span data-stu-id="913f8-221">The certificate requirements to secure HTTPS traffic for pull server are not different than securing any other HTTPS web site.</span></span> <span data-ttu-id="913f8-222">Windows Server 証明書サービスの **Web サーバー** テンプレートには必要な機能が揃っています。</span><span class="sxs-lookup"><span data-stu-id="913f8-222">The **Web Server** template in a Windows Server Certificate Services satisfies the required capabilities.</span></span>

<span data-ttu-id="913f8-223">計画タスク</span><span class="sxs-lookup"><span data-stu-id="913f8-223">Planning task</span></span>|
---|
<span data-ttu-id="913f8-224">証明書要求が自動化されていない場合、証明書を要求する際に誰に連絡する必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-224">If certificate requests are not automated, who will you need to contact to requests a certificate?</span></span>|
<span data-ttu-id="913f8-225">要求の平均所要時間はどれくらいですか?</span><span class="sxs-lookup"><span data-stu-id="913f8-225">What is the average turnaround for the request?</span></span>|
<span data-ttu-id="913f8-226">証明書ファイルはどのように転送されますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-226">How will the certificate file be transferred to you?</span></span>|
<span data-ttu-id="913f8-227">証明書の秘密キーはどのように転送されますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-227">How will the certificate private key be transferred to you?</span></span>|
<span data-ttu-id="913f8-228">既定の有効期限はどれくらいですか?</span><span class="sxs-lookup"><span data-stu-id="913f8-228">How long is the default expiration time?</span></span>|
<span data-ttu-id="913f8-229">証明書名として使用できる、プル サーバー環境用の DNS 名はどのように決めましたか?</span><span class="sxs-lookup"><span data-stu-id="913f8-229">Have you settled on a DNS name for the pull server environment, that you can use for the certificate name?</span></span>|

### <a name="choosing-an-architecture"></a><span data-ttu-id="913f8-230">アーキテクチャの選択</span><span class="sxs-lookup"><span data-stu-id="913f8-230">Choosing an architecture</span></span>

<span data-ttu-id="913f8-231">プル サーバーは、IIS でホストされている Web サービス、または SMB ファイル共有を使用して展開できます。</span><span class="sxs-lookup"><span data-stu-id="913f8-231">A pull server can be deployed using either a web service hosted on IIS, or an SMB file share.</span></span> <span data-ttu-id="913f8-232">ほとんどの場合、提供される Web サービス オプションを使用することで、柔軟性が増します。</span><span class="sxs-lookup"><span data-stu-id="913f8-232">In most situations, the web service option will provide greater flexibility.</span></span> <span data-ttu-id="913f8-233">HTTPS トラフィックではネットワーク境界をスキャンすることは珍しいことではありませんが、ネットワーク間の SMB トラフィックは多くの場合、フィルター処理されるか、ブロックされます。</span><span class="sxs-lookup"><span data-stu-id="913f8-233">It is not uncommon for HTTPS traffic to traverse network boundaries, whereas SMB traffic is often filtered or blocked between networks.</span></span> <span data-ttu-id="913f8-234">Web サービスでは、一元的に確認できるようにクライアントがサーバーに状態をレポートするメカニズムを提供する Conformance Server または Web Reporting Manager (このドキュメントの今後のバージョンに両方のトピックが含まれる予定) を含めるオプションも提供されます。</span><span class="sxs-lookup"><span data-stu-id="913f8-234">The web service also offers the option to include a Conformance Server or Web Reporting Manager (both topics to be addressed in a future version of this document) that provide a mechanism for clients to report status back to a server for centralized visibility.</span></span>
<span data-ttu-id="913f8-235">SMB では、ポリシーで Web サーバーを利用しないように指示されている環境や、Web サーバー役割は好ましくないとする他の環境要件に対するオプションを提供します。</span><span class="sxs-lookup"><span data-stu-id="913f8-235">SMB provides an option for environments where policy dictates that a web server should not be utilized, and for other environmental requirements that make a web server role undesirable.</span></span>
<span data-ttu-id="913f8-236">いずれの場合も、必ず、トラフィックの署名と暗号化に関する要件を評価してください。</span><span class="sxs-lookup"><span data-stu-id="913f8-236">In either case, remember to evaluate the requirements for signing and encrypting traffic.</span></span> <span data-ttu-id="913f8-237">HTTPS、SMB 署名、および IPSEC ポリシーはすべて、考慮に値するオプションです。</span><span class="sxs-lookup"><span data-stu-id="913f8-237">HTTPS, SMB signing, and IPSEC policies are all options worth considering.</span></span>

#### <a name="load-balancing"></a><span data-ttu-id="913f8-238">負荷分散</span><span class="sxs-lookup"><span data-stu-id="913f8-238">Load balancing</span></span>

<span data-ttu-id="913f8-239">Web サービスと対話するクライアントは、単一の応答で返される情報を要求します。</span><span class="sxs-lookup"><span data-stu-id="913f8-239">Clients interacting with the web service make a request for information that is returned in a single response.</span></span> <span data-ttu-id="913f8-240">順次要求は必要ありません。したがって、負荷分散プラットフォームで任意の時点で単一サーバーでのセッションが維持されるようにする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="913f8-240">No sequential requests are required, so it is not necessary for the load balancing platform to ensure sessions are maintained on a single server at any point in time.</span></span>

<span data-ttu-id="913f8-241">計画タスク</span><span class="sxs-lookup"><span data-stu-id="913f8-241">Planning task</span></span>|
---|
<span data-ttu-id="913f8-242">複数サーバーでの負荷分散トラフィックではどのようなソリューションが使用されますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-242">What solution will be used for load balancing traffic across servers?</span></span>|
<span data-ttu-id="913f8-243">ロード バランサー機器を使用する場合、デバイスへの新しい構成の追加要求は誰が受けますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-243">If using a hardware load balancer, who will take a request to add a new configuration to the device?</span></span>|
<span data-ttu-id="913f8-244">新しい負荷分散 Web サービスの構成要求に要する平均時間はどれくらいですか?</span><span class="sxs-lookup"><span data-stu-id="913f8-244">What is the average turnaround for a request to configure a new load balanced web service?</span></span>|
<span data-ttu-id="913f8-245">要求にはどのような情報が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="913f8-245">What information will be required for the request?</span></span>|
<span data-ttu-id="913f8-246">追加 IP を要求する必要はありますか? あるいは、負荷分散の担当チームが対応するのですか?</span><span class="sxs-lookup"><span data-stu-id="913f8-246">Will you need to request an additional IP or will the team responsible for load balancing handle that?</span></span>|
<span data-ttu-id="913f8-247">必要な DNS レコードはありますか? また、負荷分散ソリューションの構成担当チームでその DNS レコードが必要になりますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-247">Do you have the DNS records needed, and will this be required by the team responsible for configuring the load balancing solution?</span></span>|
<span data-ttu-id="913f8-248">負荷分散ソリューションでは、PKI をデバイスで処理する必要がありますか? あるいは、セッション要件がない限り、HTTPS トラフィックの負荷分散は可能ですか?</span><span class="sxs-lookup"><span data-stu-id="913f8-248">Does the load balancing solution require that PKI be handled by the device or can it load balance HTTPS traffic as long as there are no session requirements?</span></span>|

### <a name="staging-configurations-and-modules-on-the-pull-server"></a><span data-ttu-id="913f8-249">プル サーバーのステージング構成およびモジュール</span><span class="sxs-lookup"><span data-stu-id="913f8-249">Staging configurations and modules on the pull server</span></span>

<span data-ttu-id="913f8-250">構成計画の一環として、プル サーバーでホストされる DSC モジュールと構成について考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="913f8-250">As part of configuration planning, you will need to think about which DSC modules and configurations will be hosted by the pull server.</span></span> <span data-ttu-id="913f8-251">構成計画のために、コンテンツを準備し、プル サーバーに展開する方法について、基本的に理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="913f8-251">For the purpose of configuration planning it is important to have a basic understanding of how to prepare and deploy content to a pull server.</span></span>

<span data-ttu-id="913f8-252">今後、このセクションは追加され、DSC プル サーバー用の運用ガイドに含まれる予定です。</span><span class="sxs-lookup"><span data-stu-id="913f8-252">In the future, this section will be expanded and included in an Operations Guide for DSC Pull Server.</span></span>  <span data-ttu-id="913f8-253">このガイドでは、時間の経過と共に自動的にモジュールと構成を管理する日常的なプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="913f8-253">The guide will discuss the day to day process for managing modules and configurations over time with automation.</span></span>

#### <a name="dsc-modules"></a><span data-ttu-id="913f8-254">DSC モジュール</span><span class="sxs-lookup"><span data-stu-id="913f8-254">DSC modules</span></span>

<span data-ttu-id="913f8-255">構成を要求するクライアントには、必須の DSC モジュールが必要になります。</span><span class="sxs-lookup"><span data-stu-id="913f8-255">Clients that request a configuration will need the required DSC modules.</span></span> <span data-ttu-id="913f8-256">プル サーバーの機能は、クライアントへの DSC モジュールのオンデマンド配布を自動化するものです。</span><span class="sxs-lookup"><span data-stu-id="913f8-256">A functionality of the pull server is to automate distribution on demand of DSC modules to clients.</span></span> <span data-ttu-id="913f8-257">初めてプル サーバーを展開する場合 (おそらく、ラボまたは概念実証として)、PowerShell ギャラリーや DSC モジュールの PowerShell.org GitHub リポジトリなどのパブリック リポジトリから使用可能な DSC モジュールに依存する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="913f8-257">If you are deploying a pull server for the first time, perhaps as a lab or proof of concept, you are likely going to depend on DSC modules that are available from public repositories such as the PowerShell Gallery or the PowerShell.org GitHub repositories for DSC modules.</span></span>

<span data-ttu-id="913f8-258">PowerShell ギャラリーなどの信頼できるオンライン リソースの場合でも、パブリック リポジトリからダウンロードされるすべてのモジュールを、PowerShell の使用経験があり、運用環境で使用する前にモジュールを使用する環境に関する知識がある担当者が確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="913f8-258">It is critical to remember that even for trusted online sources such as the PowerShell Gallery, any module that is downloaded from a public repository should be reviewed by someone with PowerShell experience and knowledge of the environment where the modules will be used prior to being used in production.</span></span> <span data-ttu-id="913f8-259">このタスクの実行時に、ドキュメントやスクリプト例などの削除可能な追加ペイロードをモジュールで確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="913f8-259">While completing this task it is a good time to check for any additional payload in the module that can be removed such as documentation and example scripts.</span></span> <span data-ttu-id="913f8-260">これにより、サーバーからクライアントへのネットワークを介したモジュールのダウンロード時に、最初の要求でのクライアントごとのネットワーク帯域幅を減らせます。</span><span class="sxs-lookup"><span data-stu-id="913f8-260">This will reduce the network bandwidth per client in their first request, when modules will be downloaded over the network from server to client.</span></span>

<span data-ttu-id="913f8-261">各モジュールは、モジュール ペイロードを含む、ModuleName_Version.zip という名前の特定の形式の ZIP ファイルにパッケージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="913f8-261">Each module must be packaged in a specific format, a ZIP file named ModuleName_Version.zip that contains the module payload.</span></span> <span data-ttu-id="913f8-262">ファイルをサーバーにコピーしたら、チェックサム ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="913f8-262">After the file is copied to the server a checksum file must be created.</span></span> <span data-ttu-id="913f8-263">クライアントがサーバーに接続されると、DSC モジュールのコンテンツが公開後に変更されていないことを確認するためにチェックサムが使用されます。</span><span class="sxs-lookup"><span data-stu-id="913f8-263">When clients connect to the server, the checksum is used to verify the content of the DSC module has not changed since it was published.</span></span>

```powershell
New-DscChecksum -ConfigurationPath .\ -OutPath .\
```

<span data-ttu-id="913f8-264">計画タスク</span><span class="sxs-lookup"><span data-stu-id="913f8-264">Planning task</span></span>|
---|
<span data-ttu-id="913f8-265">テストまたはラボ環境を計画する場合に、検証を行うために重要なシナリオはどれですか?</span><span class="sxs-lookup"><span data-stu-id="913f8-265">If you are planning a test or lab environment which scenarios are key to validate?</span></span>|
<span data-ttu-id="913f8-266">必要なものすべてをカバーするリソースを含む一般公開されているモジュールはありますか?あるいは、独自のリソースを作成する必要はありますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-266">Are there publicly available modules that contain resources to cover everything you need or will you need to author your own resources?</span></span>|
<span data-ttu-id="913f8-267">使用環境からインターネットにアクセスして、公開モジュールを取得できますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-267">Will your environment have Internet access to retrieve public modules?</span></span>|
<span data-ttu-id="913f8-268">DSC モジュールの確認担当者は誰ですか?</span><span class="sxs-lookup"><span data-stu-id="913f8-268">Who will be responsible for reviewing DSC modules?</span></span>|
<span data-ttu-id="913f8-269">運用環境を計画する場合に、DSC モジュールを格納するためのローカル リポジトリとして何を使用しますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-269">If you are planning a production environment what will you use as a local repository for storing DSC modules?</span></span>|
<span data-ttu-id="913f8-270">中央の管理チームはアプリケーション チームからの DSC モジュールを受け入れますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-270">Will a central team accept DSC modules from application teams?</span></span> <span data-ttu-id="913f8-271">プロセスはどのようになりますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-271">What will the process be?</span></span>|
<span data-ttu-id="913f8-272">ソース リポジトリから、サーバーに対する運用準備済み DSC モジュールのチェックサムのパッケージ化、コピー、および作成を自動化しますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-272">Will you automate packaging, copying, and creating a checksum for production-ready DSC modules to the server, from your source repo?</span></span>|
<span data-ttu-id="913f8-273">チームで自動プラットフォームの管理も担当しますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-273">Will your team be responsible for managing the automation platform as well?</span></span>|

#### <a name="dsc-configurations"></a><span data-ttu-id="913f8-274">DSC 構成</span><span class="sxs-lookup"><span data-stu-id="913f8-274">DSC configurations</span></span>

<span data-ttu-id="913f8-275">プル サーバーの目的は、クライアント ノードに DSC 構成を配布するための一元的なメカニズムを提供することです。</span><span class="sxs-lookup"><span data-stu-id="913f8-275">The purpose of a pull server is to provide a centralized mechanism for distributing DSC configurations to client nodes.</span></span> <span data-ttu-id="913f8-276">構成は、MOF ドキュメントとしてサーバーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="913f8-276">The configurations are stored on the server as MOF documents.</span></span>
<span data-ttu-id="913f8-277">各ドキュメントは、一意の **GUID** で名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="913f8-277">Each document will be named with a unique **Guid**.</span></span> <span data-ttu-id="913f8-278">クライアントは、プル サーバーに接続するように構成されている場合、要求する必要がある構成用の **GUID** も付与されます。</span><span class="sxs-lookup"><span data-stu-id="913f8-278">When clients are configured to connect with a pull server, they are also given the **Guid** for the configuration they should request.</span></span> <span data-ttu-id="913f8-279">**GUID** で構成を参照するこのシステムは、グローバルな一意性を保証します。また、ノードごとに細かく構成を適用できたり、構成が同じである多くのサーバーにまたがる役割で構成を適用できるため、柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="913f8-279">This system of referencing configurations by **Guid** guarantees global uniqueness and is flexible such that a configuration can be applied with granularity per node, or as a role configuration that spans many servers that should have identical configurations.</span></span>

#### <a name="guids"></a><span data-ttu-id="913f8-280">GUID</span><span class="sxs-lookup"><span data-stu-id="913f8-280">Guids</span></span>

<span data-ttu-id="913f8-281">構成 **GUID** の計画についても、プル サーバー展開を検討する際に考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="913f8-281">Planning for configuration **Guids** is worth additional attention when thinking through a pull server deployment.</span></span> <span data-ttu-id="913f8-282">**GUID** の処理方法に関する特定の要件はありませんが、プロセスは環境ごとに一意である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="913f8-282">There is no specific requirement for how to handle **Guids** and the process is likely to be unique for each environment.</span></span> <span data-ttu-id="913f8-283">プロセスは、単純なものから複雑なものまでさまざまです。たとえば、セントラルに格納されている CSV ファイル、単純な SQL テーブル、CMDB、別のツールまたはソフトウェア ソリューションとの統合が必要な複雑なソリューションなどです。</span><span class="sxs-lookup"><span data-stu-id="913f8-283">The process can range from simple to complex: a centrally stored CSV file, a simple SQL table, a CMDB, or a complex solution requiring integration with another tool or software solution.</span></span> <span data-ttu-id="913f8-284">2 つの一般的な方法を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="913f8-284">There are two general approaches:</span></span>

- <span data-ttu-id="913f8-285">**サーバーごとに GUID を割り当てる** — 確実にすべてのサーバー構成が個別に制御されるようにします。</span><span class="sxs-lookup"><span data-stu-id="913f8-285">**Assigning Guids per server** — Provides a measure of assurance that every server configuration is controlled individually.</span></span> <span data-ttu-id="913f8-286">これにより、正確に更新が行われ、少数のサーバーを含む環境で適切に機能します。</span><span class="sxs-lookup"><span data-stu-id="913f8-286">This provides a level of precision around updates and can work well in environments with few servers.</span></span>
- <span data-ttu-id="913f8-287">**サーバーの役割ごとに GUID を割り当てる** — Web サーバーなど、同じ機能を実行するすべてのサーバーに同じ GUID を使用し、必要な構成データが参照されるようにします。</span><span class="sxs-lookup"><span data-stu-id="913f8-287">**Assigning Guids per server role** — All servers that perform the same function, such as web servers, use the same GUID to reference the required configuration data.</span></span>  <span data-ttu-id="913f8-288">多くのサーバーで同じ GUID を共有している場合、それらすべてのサーバーは、構成の変更と同時に更新されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="913f8-288">Be aware that if many servers share the same GUID, all of them would be updated simultaneously when the configuration changes.</span></span>

  <span data-ttu-id="913f8-289">GUID は、使用環境でのサーバーの展開と構成方法に関する情報を得るために悪意のあるユーザーによって利用される可能性があるため、機密データとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="913f8-289">The GUID is something that should be considered sensitive data because it could be leveraged by someone with malicious intent to gain intelligence about how servers are deployed and configured in your environment.</span></span> <span data-ttu-id="913f8-290">詳細については、「[Securely allocating GUIDs in PowerShell Desired State Configuration Pull Mode](https://blogs.msdn.microsoft.com/powershell/2014/12/31/securely-allocating-guids-in-powershell-desired-state-configuration-pull-mode/)」 (PowerShell Desired State Configuration プル モードでの安全な GUID の割り当て) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="913f8-290">For more information, see [Securely allocating Guids in PowerShell Desired State Configuration Pull Mode](https://blogs.msdn.microsoft.com/powershell/2014/12/31/securely-allocating-guids-in-powershell-desired-state-configuration-pull-mode/).</span></span>

<span data-ttu-id="913f8-291">計画タスク</span><span class="sxs-lookup"><span data-stu-id="913f8-291">Planning task</span></span>|
---|
<span data-ttu-id="913f8-292">構成の準備ができた場合に、プル サーバー フォルダーに構成をコピーする担当者は誰ですか?</span><span class="sxs-lookup"><span data-stu-id="913f8-292">Who will be responsible for copying configurations in to the pull server folder when they are ready?</span></span>|
<span data-ttu-id="913f8-293">アプリケーション チームによって構成が作成されている場合、引き継ぎプロセスはどのようになっていますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-293">If Configurations are authored by an application team, what will the process be to hand them off?</span></span>|
<span data-ttu-id="913f8-294">構成を作成時に格納するリポジトリはチーム全体で利用しますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-294">Will you leverage a repository to store configurations as they are being authored, across teams?</span></span>|
<span data-ttu-id="913f8-295">構成をサーバーにコピーし、準備ができたときにチェックサムを作成するプロセスを自動化しますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-295">Will you automate the process of copying configurations to the server and creating a checksum when they are ready?</span></span>|
<span data-ttu-id="913f8-296">GUID をサーバーまたは役割にどのようにマップしますか? また、どこに格納しますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-296">How will you map Guids to servers or roles, and where will this be stored?</span></span>|
<span data-ttu-id="913f8-297">クライアント コンピューターの構成プロセスとして何を使用しますか? また、構成 GUID の作成および格納プロセスとどのように統合しますか?</span><span class="sxs-lookup"><span data-stu-id="913f8-297">What will you use as a process to configure client machines, and how will it integrate with your process for creating and storing Configuration Guids?</span></span>|

## <a name="installation-guide"></a><span data-ttu-id="913f8-298">インストール ガイド</span><span class="sxs-lookup"><span data-stu-id="913f8-298">Installation Guide</span></span>

<span data-ttu-id="913f8-299">*このドキュメントには、安定したスクリプトが示されています。スクリプトは、運用環境で実行する前に、必ず慎重に確認してください。*</span><span class="sxs-lookup"><span data-stu-id="913f8-299">*Scripts given in this document are stable examples. Always review scripts carefully before executing them in a production environment.*</span></span>

### <a name="prerequisites"></a><span data-ttu-id="913f8-300">前提条件</span><span class="sxs-lookup"><span data-stu-id="913f8-300">Prerequisites</span></span>

<span data-ttu-id="913f8-301">サーバー上の PowerShell のバージョンを確認するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="913f8-301">To verify the version of PowerShell on your server use the following command.</span></span>

```powershell
$PSVersionTable.PSVersion
```

<span data-ttu-id="913f8-302">可能であれば、Windows Management Framework を最新バージョンにアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="913f8-302">If possible, upgrade to the latest version of Windows Management Framework.</span></span>
<span data-ttu-id="913f8-303">次に、以下のコマンドを使用して、`xPsDesiredStateConfiguration` モジュールをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="913f8-303">Next, download the `xPsDesiredStateConfiguration` module using the following command.</span></span>

```powershell
Install-Module xPSDesiredStateConfiguration
```

<span data-ttu-id="913f8-304">モジュールをダウンロードする前に、コマンドによって承認が求められます。</span><span class="sxs-lookup"><span data-stu-id="913f8-304">The command will ask for your approval before downloading the module.</span></span>

### <a name="installation-and-configuration-scripts"></a><span data-ttu-id="913f8-305">インストールおよび構成スクリプト</span><span class="sxs-lookup"><span data-stu-id="913f8-305">Installation and configuration scripts</span></span>

<span data-ttu-id="913f8-306">DSC プル サーバーを展開する最適な方法は、DSC 構成スクリプトを使用することです。</span><span class="sxs-lookup"><span data-stu-id="913f8-306">The best method to deploy a DSC pull server is to use a DSC configuration script.</span></span> <span data-ttu-id="913f8-307">このドキュメントでは、DSC Web サービスのみを構成する基本設定と、DSC Web サービスを含む Windows Server エンド ツー エンドを構成する詳細設定の両方を含むスクリプトを示します。</span><span class="sxs-lookup"><span data-stu-id="913f8-307">This document will present scripts including both basic settings that would configure only the DSC web service and advanced settings that would configure a Windows Server end-to-end including DSC web service.</span></span>

<span data-ttu-id="913f8-308">注: 現在、 `xPSDesiredStateConfiguation` DSC モジュールには、EN-US ロケールを使用するサーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="913f8-308">Note:  Currently the `xPSDesiredStateConfiguation` DSC module requires the server to be EN-US locale.</span></span>

### <a name="basic-configuration-for-windows-server-2012"></a><span data-ttu-id="913f8-309">Windows Server 2012 の基本構成</span><span class="sxs-lookup"><span data-stu-id="913f8-309">Basic configuration for Windows Server 2012</span></span>

```powershell
# This is a very basic Configuration to deploy a pull server instance in a lab environment on Windows Server 2012.

Configuration PullServer {
Import-DscResource -ModuleName xPSDesiredStateConfiguration

        # Load the Windows Server DSC Service feature
        WindowsFeature DSCServiceFeature
        {
          Ensure = 'Present'
          Name = 'DSC-Service'
        }

        # Use the DSC Resource to simplify deployment of the web service
        xDSCWebService PSDSCPullServer
        {
          Ensure = 'Present'
          EndpointName = 'PSDSCPullServer'
          Port = 8080
          PhysicalPath = "$env:SYSTEMDRIVE\inetpub\wwwroot\PSDSCPullServer"
          CertificateThumbPrint = 'AllowUnencryptedTraffic'
          ModulePath = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules"
          ConfigurationPath = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"
          State = 'Started'
          DependsOn = '[WindowsFeature]DSCServiceFeature'
        }
}
PullServer -OutputPath 'C:\PullServerConfig\'
Start-DscConfiguration -Wait -Force -Verbose -Path 'C:\PullServerConfig\'
```

### <a name="advanced-configuration-for-windows-server-2012-r2"></a><span data-ttu-id="913f8-310">Windows Server 2012 R2 の詳細構成</span><span class="sxs-lookup"><span data-stu-id="913f8-310">Advanced configuration for Windows Server 2012 R2</span></span>

```powershell
# This is an advanced Configuration example for Pull Server production deployments on Windows Server 2012 R2.
# Many of the features demonstrated are optional and provided to demonstrate how to adapt the Configuration for multiple scenarios
# Select the needed resources based on the requirements for each environment.
# Optional scenarios include:
#      * Reduce footprint to Server Core
#      * Rename server and join domain
#      * Switch from SSL to TLS for HTTPS
#      * Automatically load certificate from Certificate Authority
#      * Locate Modules and Configuration data on remote SMB share
#      * Manage state of default websites in IIS

param (
        [Parameter(Mandatory=$true)]
        [ValidateNotNullorEmpty()]
        [System.String] $ServerName,
        [System.String] $DomainName,
        [System.String] $CARootName,
        [System.String] $CAServerFQDN,
        [System.String] $CertSubject,
        [System.String] $SMBShare,
        [Parameter(Mandatory=$true)]
        [ValidateNotNullorEmpty()]
        [PsCredential] $Credential
    )

Configuration PullServer {
    Import-DscResource -ModuleName xPSDesiredStateConfiguration, xWebAdministration, xCertificate, xComputerManagement
    Node localhost
    {

        # Configure the server to automatically corret configuration drift including reboots if needed.
        LocalConfigurationManager
        {
            ConfigurationMode = 'ApplyAndAutoCorrect'
            RebootNodeifNeeded = $node.RebootNodeifNeeded
            CertificateId = $node.Thumbprint
        }

        # Remove all GUI interfaces so the server has minimum running footprint.
        WindowsFeature ServerCore
        {
            Ensure = 'Absent'
            Name = 'User-Interfaces-Infra'
        }

        # Set the server name and if needed, join a domain. If not joining a domain, remove the DomainName parameter.
        xComputer DomainJoin
        {
            Name = $Node.ServerName
            DomainName = $Node.DomainName
            Credential = $Node.Credential
        }

        # The next series of settings disable SSL and enable TLS, for environments where that is required by policy.
        Registry TLS1_2ServerEnabled
        {
            Ensure = 'Present'
            Key = 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server'
            ValueName = 'Enabled'
            ValueData = 1
            ValueType = 'Dword'
        }

        Registry TLS1_2ServerDisabledByDefault
        {
            Ensure = 'Present'
            Key = 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Server'
            ValueName = 'DisabledByDefault'
            ValueData = 0
            ValueType = 'Dword'
        }

        Registry TLS1_2ClientEnabled
        {
            Ensure = 'Present'
            Key = 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client'
            ValueName = 'Enabled'
            ValueData = 1
            ValueType = 'Dword'
        }

        Registry TLS1_2ClientDisabledByDefault
        {
            Ensure = 'Present'
            Key = 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\TLS 1.2\Client'
            ValueName = 'DisabledByDefault'
            ValueData = 0
            ValueType = 'Dword'
        }

        Registry SSL2ServerDisabled
        {
            Ensure = 'Present'
            Key = 'HKLM:\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols\SSL 2.0\Server'
            ValueName = 'Enabled'
            ValueData = 0
            ValueType = 'Dword'
        }

        # Install the Windows Server DSC Service feature
        WindowsFeature DSCServiceFeature
        {
            Ensure = 'Present'
            Name = 'DSC-Service'
        }

        # If using a certificate from a local Active Directory Enterprise Root Certificate Authority, complete a request and install the certificate
        xCertReq SSLCert
        {
            CARootName = $Node.CARootName
            CAServerFQDN = $Node.CAServerFQDN
            Subject = $Node.CertSubject
            AutoRenew = $Node.AutoRenew
            Credential = $Node.Credential
        }

        # Use the DSC resource to simplify deployment of the web service.  You might also consider modifying the default port, possibly leveraging port 443 in environments where that is enforced as a standard.
        xDSCWebService PSDSCPullServer
        {
            Ensure = 'Present'
            EndpointName = 'PSDSCPullServer'
            Port = 8080
            PhysicalPath = "$env:SYSTEMDRIVE\inetpub\wwwroot\PSDSCPullServer"
            CertificateThumbPrint = 'CertificateSubject'
            CertificateSubject = $Node.CertSubject
            ModulePath = "$($Node.SMBShare)\DscService\Modules"
            ConfigurationPath = "$($Node.SMBShare)\DscService\Configuration"
            State = 'Started'
            DependsOn = '[WindowsFeature]DSCServiceFeature'
        }

        # Validate web config file contains current DB settings
        xWebConfigKeyValue CorrectDBProvider
        {
            ConfigSection = 'AppSettings'
            Key = 'dbprovider'
            Value = 'System.Data.OleDb'
            WebsitePath = 'IIS:\sites\PSDSCPullServer'
            DependsOn = '[xDSCWebService]PSDSCPullServer'
        }
        xWebConfigKeyValue CorrectDBConnectionStr
        {
            ConfigSection = 'AppSettings'
            Key = 'dbconnectionstr'
            Value = 'Provider=Microsoft.Jet.OLEDB.4.0;Data Source=C:\Program Files\WindowsPowerShell\DscService\Devices.mdb;'
            WebsitePath = 'IIS:\sites\PSDSCPullServer'
            DependsOn = '[xDSCWebService]PSDSCPullServer'
        }

        # Stop the default website
        xWebsite StopDefaultSite
        {
            Ensure = 'Present'
            Name = 'Default Web Site'
            State = 'Stopped'
            PhysicalPath = 'C:\inetpub\wwwroot'
            DependsOn = '[WindowsFeature]DSCServiceFeature'
        }
    }
}

$configData = @{
    AllNodes = @(
        @{
            NodeName = 'localhost'
            ServerName = $ServerName
            DomainName = $DomainName
            CARootName = $CARootName
            CAServerFQDN = $CAServerFQDN
            CertSubject = $CertSubject
            AutoRenew = $true
            SMBShare = $SMBShare
            Credential = $Credential
            RebootNodeifNeeded = $true
            CertificateFile = 'c:\PullServerConfig\Cert.cer'
            Thumbprint = 'B9A39921918B466EB1ADF2509E00F5DECB2EFDA9'
            }
        )
    }

PullServer -ConfigurationData $configData -OutputPath 'C:\PullServerConfig\'
Set-DscLocalConfigurationManager -ComputerName localhost -Path 'C:\PullServerConfig\'
Start-DscConfiguration -Wait -Force -Verbose -Path 'C:\PullServerConfig\'

# .\Script.ps1 -ServerName web1 -domainname 'test.pha' -carootname 'test-dc01-ca' -caserverfqdn 'dc01.test.pha' -certsubject 'CN=service.test.pha' -smbshare '\\sofs1.test.pha\share'
```

### <a name="verify-pull-server-functionality"></a><span data-ttu-id="913f8-311">プル サーバーの機能を確認する</span><span class="sxs-lookup"><span data-stu-id="913f8-311">Verify pull server functionality</span></span>

```powershell
# This function is meant to simplify a check against a DSC pull server. If you do not use the default service URL, you will need to adjust accordingly.
function Verify-DSCPullServer ($fqdn) {
    ([xml](Invoke-WebRequest "https://$($fqdn):8080/psdscpullserver.svc" | % Content)).service.workspace.collection.href
}

Verify-DSCPullServer 'INSERT SERVER FQDN'
```

```output
Expected Result:
Action
Module
StatusReport
Node
```

### <a name="configure-clients"></a><span data-ttu-id="913f8-312">クライアントを構成する</span><span class="sxs-lookup"><span data-stu-id="913f8-312">Configure clients</span></span>

```powershell
Configuration PullClient {
    param(
    $ID,
    $Server
    )
        LocalConfigurationManager
                {
                    ConfigurationID = $ID;
                    RefreshMode = 'PULL';
                    DownloadManagerName = 'WebDownloadManager';
                    RebootNodeIfNeeded = $true;
                    RefreshFrequencyMins = 30;
                    ConfigurationModeFrequencyMins = 15;
                    ConfigurationMode = 'ApplyAndAutoCorrect';
                    DownloadManagerCustomData = @{ServerUrl = "http://"+$Server+":8080/PSDSCPullServer.svc"; AllowUnsecureConnection = $true}
                }
}

PullClient -ID 'INSERTGUID' -Server 'INSERTSERVER' -Output 'C:\DSCConfig\'
Set-DscLocalConfigurationManager -ComputerName 'Localhost' -Path 'C:\DSCConfig\' -Verbose
```

## <a name="additional-references-snippets-and-examples"></a><span data-ttu-id="913f8-313">その他の参照情報、スニペット、および例</span><span class="sxs-lookup"><span data-stu-id="913f8-313">Additional references, snippets, and examples</span></span>

<span data-ttu-id="913f8-314">この例では、テストのためにクライアント接続 (WMF5 が必要) を手動で開始する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="913f8-314">This example shows how to manually initiate a client connection (requires WMF5) for testing.</span></span>

```powershell
Update-DscConfiguration –Wait -Verbose
```

<span data-ttu-id="913f8-315">CNAME レコードを DNS ゾーンに追加する場合は、[Add-DnsServerResourceRecordName](http://bit.ly/1G1H31L) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="913f8-315">The [Add-DnsServerResourceRecordName](http://bit.ly/1G1H31L) cmdlet is used to add a type CNAME record to a DNS zone.</span></span>

<span data-ttu-id="913f8-316">[チェックサムを作成し、SMB プル サーバーに DSC MOF を公開する](https://gallery.technet.microsoft.com/scriptcenter/PowerShell-Function-to-3bc4b7f0) PowerShell 関数では必要なチェックサムが自動的に生成されてから、MOF 構成とチェックサムの両方のファイルが SMB プル サーバーにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="913f8-316">The PowerShell Function to [Create a Checksum and Publish DSC MOF to SMB Pull Server](https://gallery.technet.microsoft.com/scriptcenter/PowerShell-Function-to-3bc4b7f0) automatically generates the required checksum, and then copies both the MOF configuration and checksum files to the SMB pull server.</span></span>

## <a name="appendix---understanding-odata-service-data-file-types"></a><span data-ttu-id="913f8-317">付録 - ODATA サービス データ ファイルの種類の理解</span><span class="sxs-lookup"><span data-stu-id="913f8-317">Appendix - Understanding ODATA service data file types</span></span>

<span data-ttu-id="913f8-318">データ ファイルは、OData Web サービスを含む、プル サーバーの展開時に情報を作成するために格納されます。</span><span class="sxs-lookup"><span data-stu-id="913f8-318">A data file is stored to create information during deployment of a pull server that includes the OData web service.</span></span> <span data-ttu-id="913f8-319">ファイルの種類は、以下の説明のとおり、オペレーティング システムによって異なります。</span><span class="sxs-lookup"><span data-stu-id="913f8-319">The type of file depends on the operating system, as described below.</span></span>

- <span data-ttu-id="913f8-320">**Windows Server 2012** ファイルの種類は常に .mdb になります。</span><span class="sxs-lookup"><span data-stu-id="913f8-320">**Windows Server 2012** The file type will always be   .mdb</span></span>
- <span data-ttu-id="913f8-321">**Windows Server 2012 R2** 構成で .mdb が指定されていない限り、ファイルの種類は既定で .edb になります。</span><span class="sxs-lookup"><span data-stu-id="913f8-321">**Windows Server 2012 R2** The file type will default to .edb unless a .mdb is specified in the configuration</span></span>

<span data-ttu-id="913f8-322">プル サーバーをインストールするための[スクリプトの詳細な例](https://github.com/mgreenegit/Whitepapers/blob/Dev/PullServerCPIG.md#installation-and-configuration-scripts)では、ファイルの種類によって発生する可能性のあるエラーを防ぐために web.config ファイル設定を自動的に制御する方法の例も示されます。</span><span class="sxs-lookup"><span data-stu-id="913f8-322">In the [Advanced example script](https://github.com/mgreenegit/Whitepapers/blob/Dev/PullServerCPIG.md#installation-and-configuration-scripts) for installing a Pull Server, you will also find an example of how to automatically control the web.config file settings to prevent any chance of error caused by file type.</span></span>
