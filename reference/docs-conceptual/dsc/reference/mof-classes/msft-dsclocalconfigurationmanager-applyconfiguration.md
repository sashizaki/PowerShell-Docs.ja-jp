---
ms.date: 07/14/2020
ms.topic: reference
title: ApplyConfiguration メソッド
description: ApplyConfiguration メソッド
ms.openlocfilehash: aa99221b33d39c3ecc70156a11eaee10b540e2dc
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92664283"
---
# <a name="applyconfiguration-method"></a><span data-ttu-id="0d57b-103">ApplyConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="0d57b-103">ApplyConfiguration method</span></span>

<span data-ttu-id="0d57b-104">構成エージェントを使用して、保留中の構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="0d57b-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="0d57b-105">保留中の構成がない場合は、現在の構成を再適用します。</span><span class="sxs-lookup"><span data-stu-id="0d57b-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="0d57b-106">構文</span><span class="sxs-lookup"><span data-stu-id="0d57b-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="0d57b-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0d57b-107">Parameters</span></span>

### <a name="force"></a><span data-ttu-id="0d57b-108">force</span><span class="sxs-lookup"><span data-stu-id="0d57b-108">force</span></span>

<span data-ttu-id="0d57b-109">**true** の場合、保留中の構成があっても、現在の構成が再適用されます。</span><span class="sxs-lookup"><span data-stu-id="0d57b-109">If this is **true** , the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="0d57b-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="0d57b-110">Return value</span></span>

<span data-ttu-id="0d57b-111">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="0d57b-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="0d57b-112">解説</span><span class="sxs-lookup"><span data-stu-id="0d57b-112">Remarks</span></span>

<span data-ttu-id="0d57b-113">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="0d57b-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="0d57b-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="0d57b-114">Requirements</span></span>

<span data-ttu-id="0d57b-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="0d57b-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="0d57b-116">**名前空間** :Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="0d57b-116">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="0d57b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d57b-117">See also</span></span>

[<span data-ttu-id="0d57b-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="0d57b-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
