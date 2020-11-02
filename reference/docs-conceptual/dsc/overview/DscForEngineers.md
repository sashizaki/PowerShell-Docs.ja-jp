---
ms.date: 10/13/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: エンジニア向けの Desired State Configuration の概要
description: このドキュメントは、開発および運用チームに対して PowerShell Desired State Configuration (DSC) の利点を説明するためのものです。
ms.openlocfilehash: c98295d0e78f4dc89e5df429e3c1de9a0c024054
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646929"
---
# <a name="desired-state-configuration-overview-for-engineers"></a><span data-ttu-id="ae2e4-104">エンジニア向けの Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="ae2e4-104">Desired State Configuration Overview for Engineers</span></span>

<span data-ttu-id="ae2e4-105">このドキュメントは、開発および運用チームに対して PowerShell Desired State Configuration (DSC) の利点を説明するためのものです。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-105">This document is intended for developer and operations teams to understand the benefits of PowerShell Desired State Configuration (DSC).</span></span> <span data-ttu-id="ae2e4-106">より大まかな DSC のメリットについては、「[意思決定者向け Desired State Configuration の概要](decisionMaker.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-106">For a higher level view of the value DSC provides, please see [Desired State Configuration Overview for Decision Makers](decisionMaker.md)</span></span>

## <a name="benefits-of-desired-state-configuration"></a><span data-ttu-id="ae2e4-107">Desired State Configuration の利点</span><span class="sxs-lookup"><span data-stu-id="ae2e4-107">Benefits of Desired State Configuration</span></span>

<span data-ttu-id="ae2e4-108">DSC の存在理由は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-108">DSC exists to:</span></span>

- <span data-ttu-id="ae2e4-109">Windows でのスクリプト作成の複雑さを軽減する</span><span class="sxs-lookup"><span data-stu-id="ae2e4-109">Decrease the complexity of scripting in Windows</span></span>
- <span data-ttu-id="ae2e4-110">イテレーションの速度を上げる</span><span class="sxs-lookup"><span data-stu-id="ae2e4-110">Increase the speed of iteration</span></span>

<span data-ttu-id="ae2e4-111">"継続的展開" という概念の重要性が高まりつつあります。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-111">The concept of "continuous deployment" is becoming more important.</span></span> <span data-ttu-id="ae2e4-112">継続的展開とは、展開を頻繁に、場合によっては 1 日に何回もできることを指します。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-112">Continuous deployment means the ability to deploy frequently, potentially many times per day.</span></span> <span data-ttu-id="ae2e4-113">こうした展開の目的は修正ではなく、公開されたものを迅速に取得することにあります。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-113">The purpose of these deployments are not to fix something but to get something published quickly.</span></span> <span data-ttu-id="ae2e4-114">できる限りスムーズかつ確実に、新機能を開発から運用に移行することで、新しいビジネス ロジックの価値実現にかかる時間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-114">By getting new features through development into operation as smoothly and reliably as possible, you reduce time-to-value of new business logic.</span></span>

<span data-ttu-id="ae2e4-115">クラウド コンピューティングへの移行に伴い、最終状態の環境をテキストとして宣言し展開エンジンに公開する、"宣言" テンプレート モデルを活用した展開ソリューションが必要とされています。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-115">The move towards cloud computing implies a deployment solution that utilizes a "declarative" template model, where an end state environment is declared as text and published to a deployment engine.</span></span> <span data-ttu-id="ae2e4-116">この展開方法では、展開をいつでも継続的に繰り返して最終状態を確保できるため、エラーの脅威に対する復元性を持ちながら急速な変更を大規模に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-116">This deployment technique allows for rapid change, at scale, with resilience against threat of failure because at any time the deployment can be consistently repeated to guarantee an end state.</span></span> <span data-ttu-id="ae2e4-117">こうした変化への対応として、このような作業のスタイルを自動化によりサポートするツールやサービスが作成されました。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-117">The creation of tools and services that support this style of operations through automation is a response to these changes.</span></span>

<span data-ttu-id="ae2e4-118">DSC は、宣言的かつべき等的 (反復可能) な展開、構成、適合を実現するプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-118">DSC is a platform that provides declarative and idempotent (repeatable) deployment, configuration and conformance.</span></span> <span data-ttu-id="ae2e4-119">DSC プラットフォームを使用することで、データ センターの各コンポーネントの構成を適切に保ち、エラーを回避するとともに配置の失敗による費用の損失を抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-119">The DSC platform enables you to ensure that the components of your data center have the correct configuration, which avoids errors and prevents costly deployment failures.</span></span> <span data-ttu-id="ae2e4-120">DSC では、アプリケーション コードの一部として DSC 構成を処理することで継続的配置を可能にします。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-120">By treating DSC configurations as part of application code, DSC enables continuous deployment.</span></span> <span data-ttu-id="ae2e4-121">DSC 構成はアプリケーションの一部として更新し、アプリケーションの展開に必要な知識をいつでも使用可能な最新の状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-121">The DSC configuration should be updated as a part of the application, ensuring that the knowledge needed to deploy the application is always up-to-date and ready to be used.</span></span>

## <a name="i-have-powershell-why-do-i-need-desired-state-configuration"></a><span data-ttu-id="ae2e4-122">"PowerShell はありますが、なぜ Desired State Configuration が必要なのですか?"</span><span class="sxs-lookup"><span data-stu-id="ae2e4-122">"I have PowerShell, why do I need Desired State Configuration?"</span></span>

<span data-ttu-id="ae2e4-123">DSC 構成では、意図 ("何をやりたいか") と実行 ("どのようにやりたいか") が切り離されます。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-123">DSC configurations separate intent, or "what I want to do", from execution, or "how I want to do it."</span></span> <span data-ttu-id="ae2e4-124">つまり、実行のロジックはリソースに含まれるということです。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-124">This means the logic of execution is contained within the resources.</span></span> <span data-ttu-id="ae2e4-125">ある機能の DSC リソースが用意されていれば、ユーザーがその機能を実装または配置する方法を知る必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-125">Users do not have to know how to implement or deploy a feature when a DSC resource for that feature is available.</span></span> <span data-ttu-id="ae2e4-126">これにより、ユーザーは配置の構造に集中できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-126">This allows the user to focus on the structure of their deployment.</span></span>

<span data-ttu-id="ae2e4-127">たとえば、次のような PowerShell スクリプトがあるとします。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-127">As an example, PowerShell scripts should look like this:</span></span>

```powershell
# Create a share in Windows Server 8
New-SmbShare -Name MyShare -Path C:\Demo\Temp -FullAccess Alice -ReadAccess Bob
```

<span data-ttu-id="ae2e4-128">このスクリプトはシンプルでわかりやすく、直線的です。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-128">This script is simple, comprehensible, and straightforward.</span></span> <span data-ttu-id="ae2e4-129">しかし、このスクリプトを運用環境に移そうとすると、いくつかの問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-129">However, if you try putting that script into production, you will run into several issues.</span></span> <span data-ttu-id="ae2e4-130">このスクリプトを続けて 2 回実行したらどうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-130">What happens if that script is run twice in a row?</span></span> <span data-ttu-id="ae2e4-131">また、Bob がこの共有へのフル アクセスをすでに所有していた場合にはどうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-131">What happens if Bob previously had Full Access to the share?</span></span>

<span data-ttu-id="ae2e4-132">こうした問題に対処するため、"実際の" バージョンのスクリプトは次のようなものになります。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-132">To compensate for these issues, a "real" version of the script will look closer to something like:</span></span>

```powershell
# But actually creating a share in an idempotent way would be

$shareExists = $false
$smbShare = Get-SmbShare -Name $Name -ErrorAction SilentlyContinue
if($smbShare -ne $null)
{
    Write-Verbose -Message "Share with name $Name exists"
    $shareExists = $true
}

if ($shareExists -eq $false)
{
    Write-Verbose "Creating share $Name to ensure it is Present"
    New-SmbShare @PSBoundParameters
}
else
{
    # Need to call either Set-SmbShare or *ShareAccess cmdlets
    if ($PSBoundParameters.ContainsKey("ChangeAccess"))
    {
       #...etc, etc, etc
    }
}
```

<span data-ttu-id="ae2e4-133">ロジックやエラー処理が増えたため、スクリプトが複雑になっています。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-133">This script is more complex, with plenty of logic and error handling.</span></span> <span data-ttu-id="ae2e4-134">このスクリプトがわかりにくくなった理由は、目的ではなく _実行方法_ を記載したためです。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-134">The script is more complex because you are no longer stating what you want done, but _how to do it_ .</span></span>

<span data-ttu-id="ae2e4-135">DSC ではやりたいことを記載し、基になるロジックを抽象化することができます。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-135">DSC allows you to say what you want done, and the underlying logic is abstracted away.</span></span>

```powershell
# A configuration is a special kind of PowerShell function
Configuration Sample_Share
{
   Import-DscResource -Module xSmbShare
   # Nodes are the endpoint we wish to configure
   # A Configuration block can have zero or more Node blocks
   Node $NodeName
   {
      # Next, specify one or more resource blocks
      # Resources are simply PowerShell modules that
      # implement the logic of "how" to execute a task
      xSmbShare MySMBShare
      {
          Ensure      = "Present"
          Name        = "MyShare"
          Path        = "C:\Demo\Temp"
          ReadAccess  = "Bob"
          FullAccess  = "Alice"
          Description = "This is an updated description for this share"
      }
   }
}
#Run the function to compile the configuration
Sample_Share
#Pass the configuration to the nodes we defined and configure them
Start-DscConfiguration Sample_Share
```

<span data-ttu-id="ae2e4-136">このスクリプトの書式は整えられており、読みやすくなっています。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-136">This script is cleanly formatted and straightforward to read.</span></span>
<span data-ttu-id="ae2e4-137">ロジックのパスとエラー処理は[リソース](../resources/resources.md)実装の部分にまだ残されていますが、スクリプト作成者が気づくことはありません。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-137">The logic paths and error handling are still present in the [resource](../resources/resources.md) implementation, but invisible to the script author.</span></span>

## <a name="separating-environment-from-structure"></a><span data-ttu-id="ae2e4-138">構造からの環境の分離</span><span class="sxs-lookup"><span data-stu-id="ae2e4-138">Separating Environment from Structure</span></span>

<span data-ttu-id="ae2e4-139">DevOps の一般的なパターンでは、展開用の環境を複数用意します。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-139">A common pattern in DevOps is to have multiple environments for deployment.</span></span> <span data-ttu-id="ae2e4-140">たとえば、新しいコードを素早く試作するための "開発" 環境があるとします。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-140">For example, there might be a "dev" environment used to quickly prototype new code.</span></span> <span data-ttu-id="ae2e4-141">"開発" 環境のコードは "テスト" 環境に移されて、別のユーザーが新機能の検証を行います。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-141">The code from the "dev" environment goes into a "test" environment, where other people verify the new functionality.</span></span> <span data-ttu-id="ae2e4-142">最後に、コードは "運用"、つまり実際のサイト運用環境に移されます。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-142">Finally, the code goes into "prod", or the live site production environment.</span></span>

<span data-ttu-id="ae2e4-143">DSC 構成では、[構成データ](../configurations/configData.md)を使用することでこのような開発 - テスト - 運用のパイプラインに対応します。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-143">DSC configurations accommodate this dev-test-prod pipeline through the use of [configuration data](../configurations/configData.md).</span></span>
<span data-ttu-id="ae2e4-144">これにより、構成の構造と管理対象ノードとの差異がさらに抽象化されます。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-144">This further abstracts the difference between the structure of the configuration from the nodes that are managed.</span></span> <span data-ttu-id="ae2e4-145">たとえば、SQL サーバー、IIS サーバー、中間層サーバーが必要な構成を定義するとします。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-145">For example, you can define a configuration that requires a SQL server, an IIS server, and a middle-tier server.</span></span> <span data-ttu-id="ae2e4-146">この構成の各部分をどのようなノードに収容するかにかかわらず、これら 3 つの要素は常に存在します。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-146">Regardless of what nodes receive the different pieces of this configuration, those three elements will always be present.</span></span> <span data-ttu-id="ae2e4-147">構成データを使用することで、開発環境では 3 つの要素すべてを同一のマシンにポイントし、テスト環境では 3 つの異なるマシンに分離して、最終的に運用環境ですべての運用サーバーにポイントすることができます。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-147">You can use configuration data to point all three elements towards the same machine for a dev environment, separate out the three elements to three different machines for a test environment, and finally towards all your production servers for the prod environment.</span></span> <span data-ttu-id="ae2e4-148">複数の環境に展開するには、対象となる環境用の適切な構成データを指定して `Start-DscConfiguration` を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ae2e4-148">To deploy to the different environments, you can invoke `Start-DscConfiguration` with the correct configuration data for the environment you want to target.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae2e4-149">参照</span><span class="sxs-lookup"><span data-stu-id="ae2e4-149">See Also</span></span>

[<span data-ttu-id="ae2e4-150">構成</span><span class="sxs-lookup"><span data-stu-id="ae2e4-150">Configurations</span></span>](../configurations/configurations.md)

[<span data-ttu-id="ae2e4-151">構成データ</span><span class="sxs-lookup"><span data-stu-id="ae2e4-151">Configuration Data</span></span>](../configurations/configData.md)

[<span data-ttu-id="ae2e4-152">リソース</span><span class="sxs-lookup"><span data-stu-id="ae2e4-152">Resources</span></span>](../resources/resources.md)
