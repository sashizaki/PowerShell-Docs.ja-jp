---
ms.date: 07/17/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: SendMetaConfigurationApply メソッド
ms.openlocfilehash: 896afe2f3370e108b48583aafb33ee7b0eb1301b
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463722"
---
# <a name="sendmetaconfigurationapply-method"></a><span data-ttu-id="bdd41-103">SendMetaConfigurationApply メソッド</span><span class="sxs-lookup"><span data-stu-id="bdd41-103">SendMetaConfigurationApply method</span></span>

<span data-ttu-id="bdd41-104">構成エージェントを制御するために使用するローカル構成マネージャーの設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="bdd41-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="bdd41-105">構文</span><span class="sxs-lookup"><span data-stu-id="bdd41-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="bdd41-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bdd41-106">Parameters</span></span>

<span data-ttu-id="bdd41-107">**ConfigurationData** \[in\] 構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="bdd41-107">**ConfigurationData** \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="bdd41-108">**force** \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="bdd41-108">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="bdd41-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="bdd41-109">Return value</span></span>

<span data-ttu-id="bdd41-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="bdd41-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="bdd41-111">解説</span><span class="sxs-lookup"><span data-stu-id="bdd41-111">Remarks</span></span>

<span data-ttu-id="bdd41-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="bdd41-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="bdd41-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="bdd41-113">Requirements</span></span>

<span data-ttu-id="bdd41-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="bdd41-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="bdd41-115">**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="bdd41-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="bdd41-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdd41-116">See also</span></span>

[<span data-ttu-id="bdd41-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="bdd41-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
