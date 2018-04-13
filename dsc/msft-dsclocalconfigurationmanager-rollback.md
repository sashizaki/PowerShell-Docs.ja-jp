---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの RollBack メソッド
ms.openlocfilehash: c0a801c4037921e700e447d1434e246df0a63a4f
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="rollback-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="e8640-103">MSFT_DSCLocalConfigurationManager クラスの RollBack メソッド</span><span class="sxs-lookup"><span data-stu-id="e8640-103">RollBack method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="e8640-104">構成を以前のバージョンにロールバックします。</span><span class="sxs-lookup"><span data-stu-id="e8640-104">Rolls back the configuration to a previous version.</span></span>

<a name="syntax"></a><span data-ttu-id="e8640-105">構文</span><span class="sxs-lookup"><span data-stu-id="e8640-105">Syntax</span></span>
------

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

<a name="parameters"></a><span data-ttu-id="e8640-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e8640-106">Parameters</span></span>
----------

<span data-ttu-id="e8640-107">*configurationNumber* \[in\] 要求された構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="e8640-107">*configurationNumber* \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="e8640-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="e8640-108">Return value</span></span>
------------

<span data-ttu-id="e8640-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="e8640-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8640-110">コメント</span><span class="sxs-lookup"><span data-stu-id="e8640-110">Remarks</span></span>

<span data-ttu-id="e8640-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="e8640-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e8640-112">要件</span><span class="sxs-lookup"><span data-stu-id="e8640-112">Requirements</span></span>
------------
><span data-ttu-id="e8640-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="e8640-113">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="e8640-114">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="e8640-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="e8640-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8640-115">See also</span></span>


[<span data-ttu-id="e8640-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="e8640-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)