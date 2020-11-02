---
ms.date: 07/17/2020
ms.topic: reference
title: SendMetaConfigurationApply メソッド
description: SendMetaConfigurationApply メソッド
ms.openlocfilehash: 27c58819c0249ace011c475e500e565e5daed9bb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92648960"
---
# <a name="sendmetaconfigurationapply-method"></a><span data-ttu-id="96a51-103">SendMetaConfigurationApply メソッド</span><span class="sxs-lookup"><span data-stu-id="96a51-103">SendMetaConfigurationApply method</span></span>

<span data-ttu-id="96a51-104">構成エージェントを制御するために使用するローカル構成マネージャーの設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="96a51-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="96a51-105">構文</span><span class="sxs-lookup"><span data-stu-id="96a51-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="96a51-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="96a51-106">Parameters</span></span>

<span data-ttu-id="96a51-107">**ConfigurationData** \[in\] 構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="96a51-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="96a51-108">**force** \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="96a51-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="96a51-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="96a51-109">Return value</span></span>

<span data-ttu-id="96a51-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="96a51-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="96a51-111">解説</span><span class="sxs-lookup"><span data-stu-id="96a51-111">Remarks</span></span>

<span data-ttu-id="96a51-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="96a51-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="96a51-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="96a51-113">Requirements</span></span>

<span data-ttu-id="96a51-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="96a51-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="96a51-115">**名前空間** :Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="96a51-115">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="96a51-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="96a51-116">See also</span></span>

[<span data-ttu-id="96a51-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="96a51-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
