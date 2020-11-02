---
ms.date: 07/17/2020
ms.topic: reference
title: EnableDebugConfiguration メソッド
description: EnableDebugConfiguration メソッド
ms.openlocfilehash: 536366e6e1627a249f3bc2dc19bfd8ff3de42117
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644776"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="a8634-103">EnableDebugConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="a8634-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="a8634-104">DSC リソースのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a8634-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="a8634-105">構文</span><span class="sxs-lookup"><span data-stu-id="a8634-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="a8634-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a8634-106">Parameters</span></span>

<span data-ttu-id="a8634-107">**BreakAll** \[in\] リソース スクリプトのすべての行にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="a8634-107">**BreakAll** \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="a8634-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="a8634-108">Return value</span></span>

<span data-ttu-id="a8634-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="a8634-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8634-110">解説</span><span class="sxs-lookup"><span data-stu-id="a8634-110">Remarks</span></span>

<span data-ttu-id="a8634-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="a8634-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a8634-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a8634-112">Requirements</span></span>

<span data-ttu-id="a8634-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="a8634-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="a8634-114">**名前空間** :Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="a8634-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="a8634-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8634-115">See also</span></span>

[<span data-ttu-id="a8634-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="a8634-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
