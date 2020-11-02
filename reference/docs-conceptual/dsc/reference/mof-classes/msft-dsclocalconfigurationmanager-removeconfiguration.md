---
ms.date: 07/17/2020
ms.topic: reference
title: RemoveConfiguration メソッド
description: RemoveConfiguration メソッド
ms.openlocfilehash: d5988ac014c457407c56a097c9a376427376eb3f
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650727"
---
# <a name="removeconfiguration-method"></a><span data-ttu-id="cac52-103">RemoveConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="cac52-103">RemoveConfiguration method</span></span>

<span data-ttu-id="cac52-104">構成ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="cac52-104">Removes the configuration files.</span></span>

## <a name="syntax"></a><span data-ttu-id="cac52-105">構文</span><span class="sxs-lookup"><span data-stu-id="cac52-105">Syntax</span></span>

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a><span data-ttu-id="cac52-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cac52-106">Parameters</span></span>

<span data-ttu-id="cac52-107">**Stage** \[in\] 削除する構成ドキュメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="cac52-107">**Stage** \[in\] Specifies which configuration document to remove.</span></span> <span data-ttu-id="cac52-108">有効な値は、</span><span class="sxs-lookup"><span data-stu-id="cac52-108">The following values are valid:</span></span>

|<span data-ttu-id="cac52-109">値</span><span class="sxs-lookup"><span data-stu-id="cac52-109">Value</span></span> |<span data-ttu-id="cac52-110">説明</span><span class="sxs-lookup"><span data-stu-id="cac52-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="cac52-111">**1**</span><span class="sxs-lookup"><span data-stu-id="cac52-111">**1**</span></span> | <span data-ttu-id="cac52-112">**現在** の構成ドキュメント (current.mof)。</span><span class="sxs-lookup"><span data-stu-id="cac52-112">The **Current** configuration document (current.mof).</span></span> |
|<span data-ttu-id="cac52-113">**2**</span><span class="sxs-lookup"><span data-stu-id="cac52-113">**2**</span></span> | <span data-ttu-id="cac52-114">**保留中** の構成ドキュメント (pending.mof)。</span><span class="sxs-lookup"><span data-stu-id="cac52-114">The **Pending** configuration document (pending.mof).</span></span>  |
|<span data-ttu-id="cac52-115">**4**</span><span class="sxs-lookup"><span data-stu-id="cac52-115">**4**</span></span> | <span data-ttu-id="cac52-116">**以前** の構成ドキュメント (previous.mof)。</span><span class="sxs-lookup"><span data-stu-id="cac52-116">The **Previous** configuration document (previous.mof).</span></span> |

<span data-ttu-id="cac52-117">*Force* \[in\] **true** の場合、構成を強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="cac52-117">*Force* \[in\] **true** to force the removal of the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="cac52-118">戻り値</span><span class="sxs-lookup"><span data-stu-id="cac52-118">Return value</span></span>

<span data-ttu-id="cac52-119">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="cac52-119">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="cac52-120">解説</span><span class="sxs-lookup"><span data-stu-id="cac52-120">Remarks</span></span>

<span data-ttu-id="cac52-121">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="cac52-121">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="cac52-122">必要条件</span><span class="sxs-lookup"><span data-stu-id="cac52-122">Requirements</span></span>

<span data-ttu-id="cac52-123">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="cac52-123">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="cac52-124">**名前空間** :Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="cac52-124">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="cac52-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="cac52-125">See also</span></span>

[<span data-ttu-id="cac52-126">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="cac52-126">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
