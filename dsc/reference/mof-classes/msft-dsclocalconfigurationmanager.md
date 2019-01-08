---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラス
ms.openlocfilehash: 7f6aaf209601e99b0120407eb301d32fcfda9eb8
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047710"
---
# <a name="msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="703c3-103">MSFT_DSCLocalConfigurationManager クラス</span><span class="sxs-lookup"><span data-stu-id="703c3-103">MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="703c3-104">構成ファイルの状態を制御し、構成エージェントを使用してその構成を適用するローカル構成マネージャー (LCM)。</span><span class="sxs-lookup"><span data-stu-id="703c3-104">The Local Configuration Manager (LCM) that controls the states of configuration files and uses Configuration Agent to apply the configurations.</span></span>

<span data-ttu-id="703c3-105">次の構文はマネージド オブジェクト フォーマット (MOF) のコードを単純化したもので、すべての継承されたプロパティを含みます。</span><span class="sxs-lookup"><span data-stu-id="703c3-105">The following syntax is simplified from Managed Object Format (MOF) code and includes all of the inherited properties.</span></span>

## <a name="syntax"></a><span data-ttu-id="703c3-106">構文</span><span class="sxs-lookup"><span data-stu-id="703c3-106">Syntax</span></span>

```
[ClassVersion("1.0.0"), dynamic, provider("dsccore"), AMENDMENT]
class MSFT_DSCLocalConfigurationManager
{
};
```

## <a name="members"></a><span data-ttu-id="703c3-107">[メンバー]</span><span class="sxs-lookup"><span data-stu-id="703c3-107">Members</span></span>

<span data-ttu-id="703c3-108">**MSFT_DSCLocalConfigurationManager** クラスには次のメンバーがあります。</span><span class="sxs-lookup"><span data-stu-id="703c3-108">The **MSFT_DSCLocalConfigurationManager** class has the following members:</span></span>

- <span data-ttu-id="703c3-109">[メソッド][]</span><span class="sxs-lookup"><span data-stu-id="703c3-109">[Methods][]</span></span>

### <a name="methods"></a><span data-ttu-id="703c3-110">メソッド</span><span class="sxs-lookup"><span data-stu-id="703c3-110">Methods</span></span>

<span data-ttu-id="703c3-111">**MSFT_DSCLocalConfigurationManager** クラスでは、次のメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="703c3-111">The **MSFT_DSCLocalConfigurationManager** class has these methods.</span></span>

|<span data-ttu-id="703c3-112">方法</span><span class="sxs-lookup"><span data-stu-id="703c3-112">Method</span></span> |<span data-ttu-id="703c3-113">説明</span><span class="sxs-lookup"><span data-stu-id="703c3-113">Description</span></span> |
|:--- |:---|
| [<span data-ttu-id="703c3-114">ApplyConfiguration</span><span class="sxs-lookup"><span data-stu-id="703c3-114">ApplyConfiguration</span></span>](msft-dsclocalconfigurationmanager-applyconfiguration.md)| <span data-ttu-id="703c3-115">構成エージェントを使用して、保留中の構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="703c3-115">Uses the Configuration Agent to apply the configuration that is pending.</span></span>|
| [<span data-ttu-id="703c3-116">DisableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="703c3-116">DisableDebugConfiguration</span></span>](msft-dsclocalconfigurationmanager-disabledebugconfiguration.md)| <span data-ttu-id="703c3-117">DSC リソースのデバッグを無効にします。</span><span class="sxs-lookup"><span data-stu-id="703c3-117">Disables DSC resource debugging.</span></span>|
| [<span data-ttu-id="703c3-118">EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="703c3-118">EnableDebugConfiguration</span></span>](msft-dsclocalconfigurationmanager-enabledebugconfiguration.md)| <span data-ttu-id="703c3-119">DSC リソースのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="703c3-119">Enables DSC resource debugging.</span></span>|
| [<span data-ttu-id="703c3-120">GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="703c3-120">GetConfiguration</span></span>](msft-dsclocalconfigurationmanager-getconfiguration.md)| <span data-ttu-id="703c3-121">構成ドキュメントを管理ノードに送信し、構成エージェントの **Get** メソッドを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="703c3-121">Sends the configuration document to the managed node and uses the **Get** method of the Configuration Agent to apply the configuration.</span></span>|
| [<span data-ttu-id="703c3-122">GetConfigurationResultOutput</span><span class="sxs-lookup"><span data-stu-id="703c3-122">GetConfigurationResultOutput</span></span>](msft-dsclocalconfigurationmanager-getconfigurationresultoutput.md)| <span data-ttu-id="703c3-123">特定のジョブに関連する構成エージェントの出力を取得します。</span><span class="sxs-lookup"><span data-stu-id="703c3-123">Gets the Configuration Agent output relating to a specific job.</span></span>|
| [<span data-ttu-id="703c3-124">GetConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="703c3-124">GetConfigurationStatus</span></span>](msft-dsclocalconfigurationmanager-getconfigurationstatus.md)| <span data-ttu-id="703c3-125">構成状態の履歴を取得します。</span><span class="sxs-lookup"><span data-stu-id="703c3-125">Get the configuration status history.</span></span>|
| [<span data-ttu-id="703c3-126">GetMetaConfiguration</span><span class="sxs-lookup"><span data-stu-id="703c3-126">GetMetaConfiguration</span></span>](msft-dsclocalconfigurationmanager-getmetaconfiguration.md)| <span data-ttu-id="703c3-127">構成エージェントを制御するために使用する LCM 設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="703c3-127">Gets the LCM settings that are used to control Configuration Agent.</span></span>|
| [<span data-ttu-id="703c3-128">PerformRequiredConfigurationChecks</span><span class="sxs-lookup"><span data-stu-id="703c3-128">PerformRequiredConfigurationChecks</span></span>](msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks.md)| <span data-ttu-id="703c3-129">整合性チェックを開始します。</span><span class="sxs-lookup"><span data-stu-id="703c3-129">Starts the consistency check.</span></span>|
| [<span data-ttu-id="703c3-130">RemoveConfiguration</span><span class="sxs-lookup"><span data-stu-id="703c3-130">RemoveConfiguration</span></span>](msft-dsclocalconfigurationmanager-removeconfiguration.md)| <span data-ttu-id="703c3-131">構成ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="703c3-131">Removes the configuration files.</span></span>|
| [<span data-ttu-id="703c3-132">ResourceGet</span><span class="sxs-lookup"><span data-stu-id="703c3-132">ResourceGet</span></span>](msft-dsclocalconfigurationmanager-resourceget.md)| <span data-ttu-id="703c3-133">DSC リソースの **Get** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="703c3-133">Directly calls the **Get** method of a DSC resource.</span></span>|
| [<span data-ttu-id="703c3-134">ResourceSet</span><span class="sxs-lookup"><span data-stu-id="703c3-134">ResourceSet</span></span>](msft-dsclocalconfigurationmanager-resourceset.md)| <span data-ttu-id="703c3-135">DSC リソースの **Set** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="703c3-135">Directly calls the **Set** method of a DSC resource.</span></span>|
| [<span data-ttu-id="703c3-136">ResourceTest</span><span class="sxs-lookup"><span data-stu-id="703c3-136">ResourceTest</span></span>](msft-dsclocalconfigurationmanager-resourcetest.md)| <span data-ttu-id="703c3-137">DSC リソースの **Test** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="703c3-137">Directly calls the **Test** method of a DSC resource.</span></span>|
| [<span data-ttu-id="703c3-138">RollBack</span><span class="sxs-lookup"><span data-stu-id="703c3-138">RollBack</span></span>](msft-dsclocalconfigurationmanager-rollback.md)| <span data-ttu-id="703c3-139">以前の構成にロールバックします。</span><span class="sxs-lookup"><span data-stu-id="703c3-139">Rolls back to a previous configuration.</span></span>|
| [<span data-ttu-id="703c3-140">SendConfiguration</span><span class="sxs-lookup"><span data-stu-id="703c3-140">SendConfiguration</span></span>](msft-dsclocalconfigurationmanager-sendconfiguration.md)| <span data-ttu-id="703c3-141">構成ドキュメントを管理ノードに送信し、保留中の変更として保存します。</span><span class="sxs-lookup"><span data-stu-id="703c3-141">Sends the configuration document to the managed node and saves it as a pending change.</span></span>|
| [<span data-ttu-id="703c3-142">SendConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="703c3-142">SendConfigurationApply</span></span>](msft-dsclocalconfigurationmanager-sendconfigurationapply.md)| <span data-ttu-id="703c3-143">構成ドキュメントを管理ノードに送信し、構成エージェントを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="703c3-143">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>|
| [<span data-ttu-id="703c3-144">SendConfigurationApplyAsync</span><span class="sxs-lookup"><span data-stu-id="703c3-144">SendConfigurationApplyAsync</span></span>](msft-dsclocalconfigurationmanager-sendconfigurationapplyasync.md)| <span data-ttu-id="703c3-145">構成ドキュメントを管理ノードに送信し、構成エージェントの使用を開始して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="703c3-145">Send the configuration document to the managed node and start using the Configuration Agent to apply the configuration.</span></span> <span data-ttu-id="703c3-146">GetConfigurationResultOutput を使用して、結果の出力を取得します。</span><span class="sxs-lookup"><span data-stu-id="703c3-146">Use GetConfigurationResultOutput to retrieve result output.</span></span>|
| [<span data-ttu-id="703c3-147">SendMetaConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="703c3-147">SendMetaConfigurationApply</span></span>](msft-dsclocalconfigurationmanager-sendmetaconfigurationapply.md)| <span data-ttu-id="703c3-148">構成エージェントを制御するために使用する LCM の設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="703c3-148">Sets the LCM settings that are used to control the Configuration Agent.</span></span>|
| [<span data-ttu-id="703c3-149">StopConfiguration</span><span class="sxs-lookup"><span data-stu-id="703c3-149">StopConfiguration</span></span>](msft-dsclocalconfigurationmanager-stopconfiguration.md)| <span data-ttu-id="703c3-150">進行中の構成を停止します。</span><span class="sxs-lookup"><span data-stu-id="703c3-150">Stops the configuration that is in progress.</span></span>|
| [<span data-ttu-id="703c3-151">TestConfiguration</span><span class="sxs-lookup"><span data-stu-id="703c3-151">TestConfiguration</span></span>](msft-dsclocalconfigurationmanager-testconfiguration.md)| <span data-ttu-id="703c3-152">構成ドキュメントを管理ノードに送信し、そのドキュメントに対して現在の構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="703c3-152">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>|

## <a name="requirements"></a><span data-ttu-id="703c3-153">要件</span><span class="sxs-lookup"><span data-stu-id="703c3-153">Requirements</span></span>

<span data-ttu-id="703c3-154">MOF\*\*DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="703c3-154">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="703c3-155">\*\*［名前空間］:Root \microsoft\windows\desiredstateconfiguration</span><span class="sxs-lookup"><span data-stu-id="703c3-155">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>