---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラス
ms.openlocfilehash: 615f2998b11a0a927d3868d852e0d408f500c86d
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="bfd13-103">MSFT_DSCLocalConfigurationManager クラス</span><span class="sxs-lookup"><span data-stu-id="bfd13-103">MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="bfd13-104">構成ファイルの状態を制御し、構成エージェントを使用してその構成を適用するローカル構成マネージャー (LCM)。</span><span class="sxs-lookup"><span data-stu-id="bfd13-104">The Local Configuration Manager (LCM) that controls the states of configuration files and uses Configuration Agent to apply the configurations.</span></span>

<span data-ttu-id="bfd13-105">次の構文は管理オブジェクト フォーマット (MOF) のコードを単純化したもので、すべての継承されたプロパティを含みます。</span><span class="sxs-lookup"><span data-stu-id="bfd13-105">The following syntax is simplified from Managed Object Format (MOF) code and includes all of the inherited properties.</span></span>

## <a name="syntax"></a><span data-ttu-id="bfd13-106">構文</span><span class="sxs-lookup"><span data-stu-id="bfd13-106">Syntax</span></span>
------

``` syntax
[ClassVersion("1.0.0"), dynamic, provider("dsccore"), AMENDMENT]
class MSFT_DSCLocalConfigurationManager
{
};
```

## <a name="members"></a><span data-ttu-id="bfd13-107">[メンバー]</span><span class="sxs-lookup"><span data-stu-id="bfd13-107">Members</span></span>
-------

<span data-ttu-id="bfd13-108">**MSFT_DSCLocalConfigurationManager** クラスには次のメンバーがあります。</span><span class="sxs-lookup"><span data-stu-id="bfd13-108">The **MSFT_DSCLocalConfigurationManager** class has the following members:</span></span>

-   <span data-ttu-id="bfd13-109">[メソッド][]</span><span class="sxs-lookup"><span data-stu-id="bfd13-109">[Methods][]</span></span>

### <a name="methods"></a><span data-ttu-id="bfd13-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="bfd13-110">Methods</span></span>

<span data-ttu-id="bfd13-111">**MSFT_DSCLocalConfigurationManager** クラスでは、次のメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bfd13-111">The **MSFT_DSCLocalConfigurationManager** class has these methods.</span></span>

|<span data-ttu-id="bfd13-112">方法</span><span class="sxs-lookup"><span data-stu-id="bfd13-112">Method</span></span> |<span data-ttu-id="bfd13-113">説明</span><span class="sxs-lookup"><span data-stu-id="bfd13-113">Description</span></span> |
|:--- |:---|
| [<span data-ttu-id="bfd13-114">ApplyConfiguration</span><span class="sxs-lookup"><span data-stu-id="bfd13-114">ApplyConfiguration</span></span>](msft-dsclocalconfigurationmanager-applyconfiguration.md)| <span data-ttu-id="bfd13-115">構成エージェントを使用して、保留中の構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-115">Uses the Configuration Agent to apply the configuration that is pending.</span></span>|
| [<span data-ttu-id="bfd13-116">DisableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="bfd13-116">DisableDebugConfiguration</span></span>](msft-dsclocalconfigurationmanager-disabledebugconfiguration.md)| <span data-ttu-id="bfd13-117">DSC リソースのデバッグを無効にします。</span><span class="sxs-lookup"><span data-stu-id="bfd13-117">Disables DSC resource debugging.</span></span>|
| [<span data-ttu-id="bfd13-118">EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="bfd13-118">EnableDebugConfiguration</span></span>](msft-dsclocalconfigurationmanager-enabledebugconfiguration.md)| <span data-ttu-id="bfd13-119">DSC リソースのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bfd13-119">Enables DSC resource debugging.</span></span>|
| [<span data-ttu-id="bfd13-120">GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="bfd13-120">GetConfiguration</span></span>](msft-dsclocalconfigurationmanager-getconfiguration.md)| <span data-ttu-id="bfd13-121">構成ドキュメントを管理ノードに送信し、構成エージェントの **Get** メソッドを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-121">Sends the configuration document to the managed node and uses the **Get** method of the Configuration Agent to apply the configuration.</span></span>|
| [<span data-ttu-id="bfd13-122">GetConfigurationResultOutput</span><span class="sxs-lookup"><span data-stu-id="bfd13-122">GetConfigurationResultOutput</span></span>](msft-dsclocalconfigurationmanager-getconfigurationresultoutput.md)| <span data-ttu-id="bfd13-123">特定のジョブに関連する構成エージェントの出力を取得します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-123">Gets the Configuration Agent output relating to a specific job.</span></span>|
| [<span data-ttu-id="bfd13-124">GetConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="bfd13-124">GetConfigurationStatus</span></span>](msft-dsclocalconfigurationmanager-getconfigurationstatus.md)| <span data-ttu-id="bfd13-125">構成状態の履歴を取得します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-125">Get the configuration status history.</span></span>|
| [<span data-ttu-id="bfd13-126">GetMetaConfiguration</span><span class="sxs-lookup"><span data-stu-id="bfd13-126">GetMetaConfiguration</span></span>](msft-dsclocalconfigurationmanager-getmetaconfiguration.md)| <span data-ttu-id="bfd13-127">構成エージェントを制御するために使用する LCM 設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-127">Gets the LCM settings that are used to control Configuration Agent.</span></span>|
| [<span data-ttu-id="bfd13-128">PerformRequiredConfigurationChecks</span><span class="sxs-lookup"><span data-stu-id="bfd13-128">PerformRequiredConfigurationChecks</span></span>](msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks.md)| <span data-ttu-id="bfd13-129">整合性チェックを開始します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-129">Starts the consistency check.</span></span>|
| [<span data-ttu-id="bfd13-130">RemoveConfiguration</span><span class="sxs-lookup"><span data-stu-id="bfd13-130">RemoveConfiguration</span></span>](msft-dsclocalconfigurationmanager-removeconfiguration.md)| <span data-ttu-id="bfd13-131">構成ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-131">Removes the configuration files.</span></span>|
| [<span data-ttu-id="bfd13-132">ResourceGet</span><span class="sxs-lookup"><span data-stu-id="bfd13-132">ResourceGet</span></span>](msft-dsclocalconfigurationmanager-resourceget.md)| <span data-ttu-id="bfd13-133">DSC リソースの **Get** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-133">Directly calls the **Get** method of a DSC resource.</span></span>|
| [<span data-ttu-id="bfd13-134">ResourceSet</span><span class="sxs-lookup"><span data-stu-id="bfd13-134">ResourceSet</span></span>](msft-dsclocalconfigurationmanager-resourceset.md)| <span data-ttu-id="bfd13-135">DSC リソースの **Set** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-135">Directly calls the **Set** method of a DSC resource.</span></span>|
| [<span data-ttu-id="bfd13-136">ResourceTest</span><span class="sxs-lookup"><span data-stu-id="bfd13-136">ResourceTest</span></span>](msft-dsclocalconfigurationmanager-resourcetest.md)| <span data-ttu-id="bfd13-137">DSC リソースの **Test** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-137">Directly calls the **Test** method of a DSC resource.</span></span>|
| [<span data-ttu-id="bfd13-138">RollBack</span><span class="sxs-lookup"><span data-stu-id="bfd13-138">RollBack</span></span>](msft-dsclocalconfigurationmanager-rollback.md)| <span data-ttu-id="bfd13-139">以前の構成にロールバックします。</span><span class="sxs-lookup"><span data-stu-id="bfd13-139">Rolls back to a previous configuration.</span></span>|
| [<span data-ttu-id="bfd13-140">SendConfiguration</span><span class="sxs-lookup"><span data-stu-id="bfd13-140">SendConfiguration</span></span>](msft-dsclocalconfigurationmanager-sendconfiguration.md)| <span data-ttu-id="bfd13-141">構成ドキュメントを管理ノードに送信し、保留中の変更として保存します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-141">Sends the configuration document to the managed node and saves it as a pending change.</span></span>|
| [<span data-ttu-id="bfd13-142">SendConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="bfd13-142">SendConfigurationApply</span></span>](msft-dsclocalconfigurationmanager-sendconfigurationapply.md)| <span data-ttu-id="bfd13-143">構成ドキュメントを管理ノードに送信し、構成エージェントを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-143">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>|
| [<span data-ttu-id="bfd13-144">SendConfigurationApplyAsync</span><span class="sxs-lookup"><span data-stu-id="bfd13-144">SendConfigurationApplyAsync</span></span>](msft-dsclocalconfigurationmanager-sendconfigurationapplyasync.md)| <span data-ttu-id="bfd13-145">構成ドキュメントを管理ノードに送信し、構成エージェントの使用を開始して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-145">Send the configuration document to the managed node and start using the Configuration Agent to apply the configuration.</span></span> <span data-ttu-id="bfd13-146">GetConfigurationResultOutput を使用して、結果の出力を取得します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-146">Use GetConfigurationResultOutput to retrieve result output.</span></span>|
| [<span data-ttu-id="bfd13-147">SendMetaConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="bfd13-147">SendMetaConfigurationApply</span></span>](msft-dsclocalconfigurationmanager-sendmetaconfigurationapply.md)| <span data-ttu-id="bfd13-148">構成エージェントを制御するために使用する LCM の設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-148">Sets the LCM settings that are used to control the Configuration Agent.</span></span>|
| [<span data-ttu-id="bfd13-149">StopConfiguration</span><span class="sxs-lookup"><span data-stu-id="bfd13-149">StopConfiguration</span></span>](msft-dsclocalconfigurationmanager-stopconfiguration.md)| <span data-ttu-id="bfd13-150">進行中の構成を停止します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-150">Stops the configuration that is in progress.</span></span>|
| [<span data-ttu-id="bfd13-151">TestConfiguration</span><span class="sxs-lookup"><span data-stu-id="bfd13-151">TestConfiguration</span></span>](msft-dsclocalconfigurationmanager-testconfiguration.md)| <span data-ttu-id="bfd13-152">構成ドキュメントを管理ノードに送信し、そのドキュメントに対して現在の構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="bfd13-152">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>|





## <a name="requirements"></a><span data-ttu-id="bfd13-153">要件</span><span class="sxs-lookup"><span data-stu-id="bfd13-153">Requirements</span></span>
------------
><span data-ttu-id="bfd13-154">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="bfd13-154">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="bfd13-155">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="bfd13-155">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>