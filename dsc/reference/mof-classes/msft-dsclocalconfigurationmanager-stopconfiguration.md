---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの StopConfiguration メソッド
ms.openlocfilehash: 1cd887d205967c3d282143df4e6199027639230e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078244"
---
# <a name="stopconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="8afd3-103">MSFT_DSCLocalConfigurationManager クラスの StopConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="8afd3-103">StopConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="8afd3-104">進行中の構成の変更を停止します。</span><span class="sxs-lookup"><span data-stu-id="8afd3-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="8afd3-105">構文</span><span class="sxs-lookup"><span data-stu-id="8afd3-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="8afd3-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8afd3-106">Parameters</span></span>

<span data-ttu-id="8afd3-107">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="8afd3-107">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="8afd3-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="8afd3-108">Return value</span></span>

<span data-ttu-id="8afd3-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="8afd3-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="8afd3-110">コメント</span><span class="sxs-lookup"><span data-stu-id="8afd3-110">Remarks</span></span>

<span data-ttu-id="8afd3-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="8afd3-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8afd3-112">要件</span><span class="sxs-lookup"><span data-stu-id="8afd3-112">Requirements</span></span>

<span data-ttu-id="8afd3-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="8afd3-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="8afd3-114">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="8afd3-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="8afd3-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="8afd3-115">See also</span></span>

[<span data-ttu-id="8afd3-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="8afd3-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)