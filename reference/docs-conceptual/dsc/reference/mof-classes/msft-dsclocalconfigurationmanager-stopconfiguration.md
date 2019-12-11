---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: StopConfiguration メソッド
ms.openlocfilehash: e1de175032a3bddf11af218bc4a15bdbe554a9d5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953359"
---
# <a name="stopconfiguration-method"></a><span data-ttu-id="21cb9-103">StopConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="21cb9-103">StopConfiguration method</span></span>

<span data-ttu-id="21cb9-104">進行中の構成の変更を停止します。</span><span class="sxs-lookup"><span data-stu-id="21cb9-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="21cb9-105">構文</span><span class="sxs-lookup"><span data-stu-id="21cb9-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="21cb9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="21cb9-106">Parameters</span></span>

<span data-ttu-id="21cb9-107">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="21cb9-107">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="21cb9-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="21cb9-108">Return value</span></span>

<span data-ttu-id="21cb9-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="21cb9-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="21cb9-110">コメント</span><span class="sxs-lookup"><span data-stu-id="21cb9-110">Remarks</span></span>

<span data-ttu-id="21cb9-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="21cb9-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="21cb9-112">要件</span><span class="sxs-lookup"><span data-stu-id="21cb9-112">Requirements</span></span>

<span data-ttu-id="21cb9-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="21cb9-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="21cb9-114">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="21cb9-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="21cb9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="21cb9-115">See also</span></span>

[<span data-ttu-id="21cb9-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="21cb9-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
