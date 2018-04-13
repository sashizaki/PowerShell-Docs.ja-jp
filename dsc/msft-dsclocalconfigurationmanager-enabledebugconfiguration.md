---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの EnableDebugConfiguration メソッド
ms.openlocfilehash: 9fe41fa806a6abff1d36dadd0c041a5cf0e78caf
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="enabledebugconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="54563-103">MSFT_DSCLocalConfigurationManager クラスの EnableDebugConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="54563-103">EnableDebugConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="54563-104">DSC リソースのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="54563-104">Enables DSC resource debugging.</span></span>

<a name="syntax"></a><span data-ttu-id="54563-105">構文</span><span class="sxs-lookup"><span data-stu-id="54563-105">Syntax</span></span>
------

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

<a name="parameters"></a><span data-ttu-id="54563-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="54563-106">Parameters</span></span>
----------

<span data-ttu-id="54563-107">*BreakAll* \[in\] リソース スクリプトのすべての行にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="54563-107">*BreakAll* \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="54563-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="54563-108">Return value</span></span>
------------

<span data-ttu-id="54563-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="54563-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="54563-110">コメント</span><span class="sxs-lookup"><span data-stu-id="54563-110">Remarks</span></span>

<span data-ttu-id="54563-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="54563-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="54563-112">要件</span><span class="sxs-lookup"><span data-stu-id="54563-112">Requirements</span></span>
------------
><span data-ttu-id="54563-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="54563-113">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="54563-114">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="54563-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="54563-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="54563-115">See also</span></span>


[<span data-ttu-id="54563-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="54563-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)