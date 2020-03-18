---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: CI/CD パイプラインでの DSC のロールについて
ms.openlocfilehash: 79740225c030974546035b67e0f873fa00aa690a
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78279371"
---
# <a name="understanding-dscs-role-in-a-cicd-pipeline"></a><span data-ttu-id="0853e-103">CI/CD パイプラインでの DSC のロールについて</span><span class="sxs-lookup"><span data-stu-id="0853e-103">Understanding DSC's role in a CI/CD pipeline</span></span>

<span data-ttu-id="0853e-104">この記事では、構成とリソースを結合するために使用できるアプローチの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="0853e-104">This article describes the types of approaches available for combining configurations and resources.</span></span>
<span data-ttu-id="0853e-105">各シナリオの目標は同じで、サーバーの展開の終了状態に到達するために複数の構成を選択する場合の複雑さを軽減することです。</span><span class="sxs-lookup"><span data-stu-id="0853e-105">The goal for each scenario is the same, to reduce complexity when multiple configurations are preferred to reach a server deployment end state.</span></span> <span data-ttu-id="0853e-106">この例には、アプリケーションの状態を維持するアプリケーション所有者や、セキュリティ ベースラインへの変更をリリースする中央の管理チームなど、サーバーの展開の結果に貢献する複数のチームが考えられます。</span><span class="sxs-lookup"><span data-stu-id="0853e-106">An example of this would be multiple teams contributing to the outcome of a server deployment, such as an application owner maintaining the application state and a central team releasing changes to security baselines.</span></span> <span data-ttu-id="0853e-107">ここでは、各アプローチのメリットとリスクなどを含む、微妙な差異について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="0853e-107">The nuances of each approach including the benefits and risks are detailed here.</span></span>

![パイプライン](media/authoringAdvanced/Pipeline.jpg)

## <a name="types-of-collaborative-authoring-techniques"></a><span data-ttu-id="0853e-109">コラボレーションの作成方法の種類</span><span class="sxs-lookup"><span data-stu-id="0853e-109">Types of Collaborative Authoring Techniques</span></span>

<span data-ttu-id="0853e-110">この概念を有効にするために 2 つのソリューションがローカルの Configuration Manager に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="0853e-110">There are two solutions built in to Local Configuration Manager to enable this concept:</span></span>

|        <span data-ttu-id="0853e-111">概念</span><span class="sxs-lookup"><span data-stu-id="0853e-111">Concept</span></span>         |                    <span data-ttu-id="0853e-112">詳細情報</span><span class="sxs-lookup"><span data-stu-id="0853e-112">Detailed Information</span></span>                     |
| ---------------------- | ----------------------------------------------------------- |
| <span data-ttu-id="0853e-113">部分構成</span><span class="sxs-lookup"><span data-stu-id="0853e-113">Partial Configurations</span></span> | [<span data-ttu-id="0853e-114">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="0853e-114">Documentation</span></span>](../pull-server/partialConfigs.md)           |
| <span data-ttu-id="0853e-115">複合リソース</span><span class="sxs-lookup"><span data-stu-id="0853e-115">Composite Resources</span></span>    | [<span data-ttu-id="0853e-116">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="0853e-116">Documentation</span></span>](../resources/authoringResourceComposite.md) |

## <a name="understanding-the-impact-of-each-approach"></a><span data-ttu-id="0853e-117">各アプローチの影響を理解する</span><span class="sxs-lookup"><span data-stu-id="0853e-117">Understanding The Impact of Each Approach</span></span>

<span data-ttu-id="0853e-118">これらのいずれかのソリューションを使用して、サーバーの展開の結果を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="0853e-118">Either of these solutions can be used to manage the outcome of a server deployment.</span></span> <span data-ttu-id="0853e-119">ただし、各アプローチの使用による影響には、大きな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="0853e-119">However, there is significant difference in the impact of using each approach.</span></span>

## <a name="partial-configurations"></a><span data-ttu-id="0853e-120">部分構成</span><span class="sxs-lookup"><span data-stu-id="0853e-120">Partial Configurations</span></span>

<span data-ttu-id="0853e-121">部分構成を使用する場合、ローカルの Configuration Manager は複数の構成を個別に管理するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="0853e-121">When using Partial Configurations, Local Configuration Manager is configured to manage multiple configurations independently.</span></span> <span data-ttu-id="0853e-122">構成は個別にコンパイルされてから、ノードに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="0853e-122">Configurations are compiled independently and then assigned to the node.</span></span> <span data-ttu-id="0853e-123">これには、各構成の名前を使用して、LCM を事前に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0853e-123">This requires LCM to be configured in advance with the name of each configuration.</span></span>

![PartialConfiguration](media/authoringAdvanced/PartialConfiguration.jpg)

<span data-ttu-id="0853e-125">部分構成では、2 つ以上のチームにサーバーの構成に対する完全な制御を提供します。多くの場合、コミュニケーションやコラボレーションの利点はありません。</span><span class="sxs-lookup"><span data-stu-id="0853e-125">Partial Configurations provide two, or more, teams complete control over configuration of a server, often without the benefit of communication or collaboration.</span></span>

<span data-ttu-id="0853e-126">これにより、リソースの競合や意図しないオーバーライドが発生したり、最終的には、資産の真の構成の制御を失う可能性があることが、お客様からのフィードバックで報告されております。</span><span class="sxs-lookup"><span data-stu-id="0853e-126">Customers have provided feedback that this can lead to resource conflicts, unintentional overrides, and ultimately loss of true configuration control of the asset.</span></span>

<span data-ttu-id="0853e-127">さらに、お客様からは、このモデルを使用したときに、各制御チームの構成変更がリリース パイプラインを通じて完全にテストされているとは思えず、実稼働環境で予期しない結果につながるというフィードバックもいただいております。</span><span class="sxs-lookup"><span data-stu-id="0853e-127">Additionally, customers have provided feedback that when using this model, each controlling teams configuration changes are unlikely to be fully tested through a release pipeline, leading to unexpected results in production.</span></span>

<span data-ttu-id="0853e-128">**サーバーにリリースするすべての変更を 1 つのパイプラインを使用して評価することが重要です。**</span><span class="sxs-lookup"><span data-stu-id="0853e-128">**It is critical that a single pipeline be used to evaluate all changes release to servers.**</span></span>

<span data-ttu-id="0853e-129">次の図では、チーム B はチーム A に部分構成をリリースします。そしてチーム A は両方の構成が適用されたサーバーに対してテストを実行します。</span><span class="sxs-lookup"><span data-stu-id="0853e-129">In the illustration below, Team B releases their partial configuration to Team A. Team A then runs their tests against a server with both configurations applied.</span></span> <span data-ttu-id="0853e-130">このモデルでは、1 つの機関だけが実稼働環境で変更を行う権限を持っています。</span><span class="sxs-lookup"><span data-stu-id="0853e-130">In this model, only one authority has permission to make changes in production.</span></span>

![PartialSinglePipeline](media/authoringAdvanced/PartialSinglePipeline.jpg)

<span data-ttu-id="0853e-132">チーム B から変更が必要な場合は、チーム A のソース管理環境に対して Pull Request を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0853e-132">When changes are required from Team B, they should submit a Pull Request against Team A's source control environment.</span></span> <span data-ttu-id="0853e-133">次に、チーム A がテスト自動化を使用して変更を確認し、その変更によってサーバーでホストされているアプリケーションやサービスでエラーが発生しないことが確認できたら、運用環境にリリースします。</span><span class="sxs-lookup"><span data-stu-id="0853e-133">Team A would then review the changes using test automation and release to production when there is confidence that the changes will not cause errors in the applications or services hosted by the server.</span></span>

## <a name="composite-resources"></a><span data-ttu-id="0853e-134">複合リソース</span><span class="sxs-lookup"><span data-stu-id="0853e-134">Composite Resources</span></span>

<span data-ttu-id="0853e-135">複合リソースは、リソースとしてパッケージ化された単なる DSC 構成です。</span><span class="sxs-lookup"><span data-stu-id="0853e-135">A composite resource is simply a DSC Configuration packaged as a resource.</span></span> <span data-ttu-id="0853e-136">複合リソースを受け入れるように LCM を構成するための特別な要件はありません。</span><span class="sxs-lookup"><span data-stu-id="0853e-136">There are no special requirements for configuring LCM to accept composite resources.</span></span> <span data-ttu-id="0853e-137">リソースは新しい構成内で使用され、1 つのコンパイル結果が 1 つの MOF ファイルになります。</span><span class="sxs-lookup"><span data-stu-id="0853e-137">The resources are used within a new configuration and a single compilation results in one MOF file.</span></span>

![CompositeResource](media/authoringAdvanced/CompositeResource.jpg)

<span data-ttu-id="0853e-139">複合リソースには、2 つの一般的なシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="0853e-139">There are two common scenarios for composite resources.</span></span> <span data-ttu-id="0853e-140">1 つ目は、複雑さを軽減し、独自の概念を抽象化することです。</span><span class="sxs-lookup"><span data-stu-id="0853e-140">The first is to reduce complexity and abstract unique concepts.</span></span> <span data-ttu-id="0853e-141">2 つ目は、すべてのテストが成功した後で、アプリケーション チームがリリース パイプラインを通じて運用環境に安全に展開するために、ベースラインのパッケージ化を許可することです。</span><span class="sxs-lookup"><span data-stu-id="0853e-141">The second is to allow baselines to be packaged for an application team to safely deploy through their release pipeline to production after all tests have passed.</span></span>

```PowerShell
Configuration Name
{
  File 1
  {
    Ensure = "Present"
    Path = "c:\inetpub\file1.zip"
    Source = "http://uri/file1.zip"
  }
  Service A
  {
    Ensure = "Present"
    Name = "ServiceA"
    Status = "Running"
  }
  SecurityBaseline Settings
  {
    Ensure = "Present"
    Datacenter = "NorthAmerica"
  }
}
```

<span data-ttu-id="0853e-142">複合リソースは、パイプラインを使用して合成とコラボレーション両方を促進させつつ、運用の成熟度を高めます。</span><span class="sxs-lookup"><span data-stu-id="0853e-142">Composite resources promote both composition and collaboration using a pipeline while building operational maturity.</span></span>

<span data-ttu-id="0853e-143">気付かないうちに、既に複合リソースを使用している場合があります。</span><span class="sxs-lookup"><span data-stu-id="0853e-143">You might be already using composite resources without realizing it.</span></span> <span data-ttu-id="0853e-144">**ServiceSet** はその一例です。</span><span class="sxs-lookup"><span data-stu-id="0853e-144">An example is **ServiceSet**.</span></span>
<span data-ttu-id="0853e-145">このリソースは、複数の Windows サービスの状態を個別にリストすることなく、管理します。</span><span class="sxs-lookup"><span data-stu-id="0853e-145">This resource manages the state of multiple Windows Services without listing them individually.</span></span> <span data-ttu-id="0853e-146">Name プロパティは、各サービスの名前を指定する文字列の配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="0853e-146">The Name property accepts an array of strings to provide the name of each service.</span></span> <span data-ttu-id="0853e-147">構成のコンパイル時に、MOF には ServiceSet に渡される名前ごとに一意の Service セクションが格納されます。</span><span class="sxs-lookup"><span data-stu-id="0853e-147">When the configuration is compiled, the MOF will contain a unique Service section for each of the Names passed to ServiceSet.</span></span>

<span data-ttu-id="0853e-148">組織には、すべてのサーバーにインストールする必要がある "エージェント" または "ミドルウェア" がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="0853e-148">Organizations might have "agents" or "middleware" that should be installed on every server.</span></span> <span data-ttu-id="0853e-149">このようなツールとユーティリティの依存関係、セットアップ、および構成を管理するには、複合リソースが最善の答えです。</span><span class="sxs-lookup"><span data-stu-id="0853e-149">A composite resource is the best answer to managing the dependencies, setup, and configuration of any such tools and utilities.</span></span>

<span data-ttu-id="0853e-150">複数のサーバーにまたがるソリューションを担当する人またはチームが、自身の要件を含む構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="0853e-150">The person or team responsible for solutions that span multiple servers authors a configuration containing their requirements.</span></span> <span data-ttu-id="0853e-151">次に、複合リソースのドキュメントで説明する手順を使用して、構成を複合リソースとしてパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="0853e-151">Next, the configuration would be packaged as a composite resource using instructions provided in the composite resource documentation.</span></span> <span data-ttu-id="0853e-152">最後に、新しい複合リソースを、ファイル共有や NuGet フィードなど、アプリケーション チームが構成で使用できる場所に発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0853e-152">Finally, the new composite resource should be published to a location such as a file share or NuGet feed where application teams can consume it in their configurations.</span></span>

<span data-ttu-id="0853e-153">チームは、新しいバージョンをリリースするたびに、その複合リソースのモジュール マニフェストでバージョン番号をインクリメントする場合があります。</span><span class="sxs-lookup"><span data-stu-id="0853e-153">Each time the team releases a new version, they would increment the version number in the module manifest for their composite resource.</span></span> <span data-ttu-id="0853e-154">アプリケーション チームは、アプリケーションの依存関係を管理するために作成する構成に複合リソースを含めます。</span><span class="sxs-lookup"><span data-stu-id="0853e-154">The application teams include the composite resource in the configuration they author for managing application dependencies.</span></span> <span data-ttu-id="0853e-155">運用/セキュリティ チームは、リソースの新しいバージョンをリリースするときに、アプリケーション チームに新しい変更を通知します。</span><span class="sxs-lookup"><span data-stu-id="0853e-155">When the Operations/Security teams release a new version of their resource, they notify the application teams of a new change.</span></span>

<span data-ttu-id="0853e-156">アプリケーション チームは、変更がベースラインに対してのみの場合は、実稼働環境へのリリースをトリガーすることがあります。</span><span class="sxs-lookup"><span data-stu-id="0853e-156">The application teams might trigger a release to production where the only change is to baselines.</span></span>
<span data-ttu-id="0853e-157">ただし、これにより、サービス停止のリスクの前にアプリケーションへの影響を評価する機会が与えられます。</span><span class="sxs-lookup"><span data-stu-id="0853e-157">However, this provides an opportunity to evaluate impact to applications before risk of a service outage.</span></span>

> [!NOTE]
> <span data-ttu-id="0853e-158">複合リソースの使用についてのフィードバックには、変更するには新しい MOF をコンパイルしてリリースする必要があるというご指摘がありました。</span><span class="sxs-lookup"><span data-stu-id="0853e-158">Feedback regarding the use of composite resources has included criticism that making changes requires compiling and releasing a new MOF.</span></span> <span data-ttu-id="0853e-159">これは仕様です。</span><span class="sxs-lookup"><span data-stu-id="0853e-159">This is by design.</span></span> <span data-ttu-id="0853e-160">新しい構成リリースにはそれぞれ、各リソースの特定のバージョンへの静的参照を含める必要があります。また、実稼働サーバー ノードに到達する前にテストして検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0853e-160">Each new configuration release should include a static reference to a specific version of each resource, and should be validated by tests before reaching production server nodes.</span></span> <span data-ttu-id="0853e-161">ソース管理からの変更のテストとリリースのプロセスにより、小さくても頻繁なバッチで変更をリリースするための安全な環境が作成されます。</span><span class="sxs-lookup"><span data-stu-id="0853e-161">The process of testing and releasing changes from source control creates a safe environment for releasing change in small but frequent batches.</span></span>

<span data-ttu-id="0853e-162">リリース パイプラインを使用して、コア インフラストラクチャを管理する方法の詳細については、次のホワイト ペーパーをご覧ください: 「[The Release Pipeline Model (リリース パイプライン モデル)](../further-reading/whitepapers.md)」。</span><span class="sxs-lookup"><span data-stu-id="0853e-162">For more information about using release pipelines to manage core infrastructure, see the whitepaper: [The Release Pipeline Model](../further-reading/whitepapers.md).</span></span>
