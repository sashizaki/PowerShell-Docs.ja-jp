---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApplyAsync メソッド
ms.openlocfilehash: 7ff821a277a548869862741551ee9897e417ea45
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="sendconfigurationapplyasync-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="af19d-103">MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApplyAsync メソッド</span><span class="sxs-lookup"><span data-stu-id="af19d-103">SendConfigurationApplyAsync method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="af19d-104">構成ドキュメントを管理ノードに非同期的に送信し、構成エージェントを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="af19d-104">Sends the configuration document asynchronously to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

<a name="syntax"></a><span data-ttu-id="af19d-105">構文</span><span class="sxs-lookup"><span data-stu-id="af19d-105">Syntax</span></span>
------

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

<a name="parameters"></a><span data-ttu-id="af19d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af19d-106">Parameters</span></span>
----------

<span data-ttu-id="af19d-107">*ConfigurationData* \[in\] 構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="af19d-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="af19d-108">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="af19d-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

<span data-ttu-id="af19d-109">*jobId* \[in\] 構成を送信するジョブの ID です。</span><span class="sxs-lookup"><span data-stu-id="af19d-109">*jobId* \[in\] The ID of the job for which to send the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="af19d-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="af19d-110">Return value</span></span>
------------

<span data-ttu-id="af19d-111">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="af19d-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="af19d-112">コメント</span><span class="sxs-lookup"><span data-stu-id="af19d-112">Remarks</span></span>

<span data-ttu-id="af19d-113">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="af19d-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="af19d-114">要件</span><span class="sxs-lookup"><span data-stu-id="af19d-114">Requirements</span></span>
------------
><span data-ttu-id="af19d-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="af19d-115">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="af19d-116">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="af19d-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="af19d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="af19d-117">See also</span></span>


[<span data-ttu-id="af19d-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="af19d-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)