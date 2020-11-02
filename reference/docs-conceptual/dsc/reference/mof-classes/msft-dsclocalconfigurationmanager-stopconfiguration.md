---
ms.date: 07/17/2020
ms.topic: reference
title: StopConfiguration メソッド
description: StopConfiguration メソッド
ms.openlocfilehash: 854c0dbe8554c08413735a5a7bc872776e0b0a6c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644616"
---
# <a name="stopconfiguration-method"></a><span data-ttu-id="790ec-103">StopConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="790ec-103">StopConfiguration method</span></span>

<span data-ttu-id="790ec-104">進行中の構成の変更を停止します。</span><span class="sxs-lookup"><span data-stu-id="790ec-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="790ec-105">構文</span><span class="sxs-lookup"><span data-stu-id="790ec-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="790ec-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="790ec-106">Parameters</span></span>

<span data-ttu-id="790ec-107">**force** \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="790ec-107">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="790ec-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="790ec-108">Return value</span></span>

<span data-ttu-id="790ec-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="790ec-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="790ec-110">解説</span><span class="sxs-lookup"><span data-stu-id="790ec-110">Remarks</span></span>

<span data-ttu-id="790ec-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="790ec-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="790ec-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="790ec-112">Requirements</span></span>

<span data-ttu-id="790ec-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="790ec-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="790ec-114">**名前空間** :Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="790ec-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="790ec-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="790ec-115">See also</span></span>

[<span data-ttu-id="790ec-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="790ec-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
