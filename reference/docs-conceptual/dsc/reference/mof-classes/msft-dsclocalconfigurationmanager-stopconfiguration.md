---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: StopConfiguration メソッド
ms.openlocfilehash: e1de175032a3bddf11af218bc4a15bdbe554a9d5
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953359"
---
# <a name="stopconfiguration-method"></a><span data-ttu-id="74120-103">StopConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="74120-103">StopConfiguration method</span></span>

<span data-ttu-id="74120-104">進行中の構成の変更を停止します。</span><span class="sxs-lookup"><span data-stu-id="74120-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="74120-105">構文</span><span class="sxs-lookup"><span data-stu-id="74120-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="74120-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="74120-106">Parameters</span></span>

<span data-ttu-id="74120-107">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="74120-107">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="74120-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="74120-108">Return value</span></span>

<span data-ttu-id="74120-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="74120-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="74120-110">解説</span><span class="sxs-lookup"><span data-stu-id="74120-110">Remarks</span></span>

<span data-ttu-id="74120-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="74120-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="74120-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="74120-112">Requirements</span></span>

<span data-ttu-id="74120-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="74120-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="74120-114">**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="74120-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="74120-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="74120-115">See also</span></span>

[<span data-ttu-id="74120-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="74120-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
