---
ms.date: 07/17/2020
ms.topic: reference
title: SendConfigurationApplyAsync メソッド
description: SendConfigurationApplyAsync メソッド
ms.openlocfilehash: 92c9d03a7653e72b1ff04084caea4a8b5aadb0e5
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644788"
---
# <a name="sendconfigurationapplyasync-method"></a><span data-ttu-id="9c24e-103">SendConfigurationApplyAsync メソッド</span><span class="sxs-lookup"><span data-stu-id="9c24e-103">SendConfigurationApplyAsync method</span></span>

<span data-ttu-id="9c24e-104">構成ドキュメントを管理ノードに非同期的に送信し、構成エージェントを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="9c24e-104">Sends the configuration document asynchronously to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="9c24e-105">構文</span><span class="sxs-lookup"><span data-stu-id="9c24e-105">Syntax</span></span>

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

## <a name="parameters"></a><span data-ttu-id="9c24e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9c24e-106">Parameters</span></span>

<span data-ttu-id="9c24e-107">**ConfigurationData** \[in\] 構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="9c24e-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="9c24e-108">**force** \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="9c24e-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

<span data-ttu-id="9c24e-109">**jobId** \[in\] 構成を送信するジョブの ID です。</span><span class="sxs-lookup"><span data-stu-id="9c24e-109">**jobId** \[in\] The ID of the job for which to send the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="9c24e-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="9c24e-110">Return value</span></span>

<span data-ttu-id="9c24e-111">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="9c24e-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c24e-112">解説</span><span class="sxs-lookup"><span data-stu-id="9c24e-112">Remarks</span></span>

<span data-ttu-id="9c24e-113">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="9c24e-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="9c24e-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="9c24e-114">Requirements</span></span>

<span data-ttu-id="9c24e-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="9c24e-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="9c24e-116">**名前空間** :Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="9c24e-116">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="9c24e-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="9c24e-117">See also</span></span>

[<span data-ttu-id="9c24e-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="9c24e-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
