---
ms.date: 07/17/2020
ms.topic: reference
title: RollBack メソッド
description: RollBack メソッド
ms.openlocfilehash: 82ca54ed23a3a892b785f603be3b423def5ee636
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92650632"
---
# <a name="rollback-method"></a><span data-ttu-id="73cbc-103">RollBack メソッド</span><span class="sxs-lookup"><span data-stu-id="73cbc-103">RollBack method</span></span>

<span data-ttu-id="73cbc-104">構成を以前のバージョンにロールバックします。</span><span class="sxs-lookup"><span data-stu-id="73cbc-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="73cbc-105">構文</span><span class="sxs-lookup"><span data-stu-id="73cbc-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="73cbc-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="73cbc-106">Parameters</span></span>

<span data-ttu-id="73cbc-107">**configurationNumber** \[in\] 要求された構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="73cbc-107">**configurationNumber** \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="73cbc-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="73cbc-108">Return value</span></span>

<span data-ttu-id="73cbc-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="73cbc-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="73cbc-110">解説</span><span class="sxs-lookup"><span data-stu-id="73cbc-110">Remarks</span></span>

<span data-ttu-id="73cbc-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="73cbc-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="73cbc-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="73cbc-112">Requirements</span></span>

<span data-ttu-id="73cbc-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="73cbc-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="73cbc-114">**名前空間** :Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="73cbc-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="73cbc-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="73cbc-115">See also</span></span>

[<span data-ttu-id="73cbc-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="73cbc-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
