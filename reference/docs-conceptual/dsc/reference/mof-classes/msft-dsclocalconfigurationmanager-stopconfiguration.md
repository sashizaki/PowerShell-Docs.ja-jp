---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: StopConfiguration メソッド
ms.openlocfilehash: e1de175032a3bddf11af218bc4a15bdbe554a9d5
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953359"
---
# <a name="stopconfiguration-method"></a><span data-ttu-id="1edae-103">StopConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="1edae-103">StopConfiguration method</span></span>

<span data-ttu-id="1edae-104">進行中の構成の変更を停止します。</span><span class="sxs-lookup"><span data-stu-id="1edae-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="1edae-105">構文</span><span class="sxs-lookup"><span data-stu-id="1edae-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="1edae-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="1edae-106">Parameters</span></span>

<span data-ttu-id="1edae-107">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="1edae-107">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="1edae-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="1edae-108">Return value</span></span>

<span data-ttu-id="1edae-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="1edae-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="1edae-110">コメント</span><span class="sxs-lookup"><span data-stu-id="1edae-110">Remarks</span></span>

<span data-ttu-id="1edae-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="1edae-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1edae-112">要件</span><span class="sxs-lookup"><span data-stu-id="1edae-112">Requirements</span></span>

<span data-ttu-id="1edae-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="1edae-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="1edae-114">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="1edae-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="1edae-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="1edae-115">See also</span></span>

[<span data-ttu-id="1edae-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="1edae-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)