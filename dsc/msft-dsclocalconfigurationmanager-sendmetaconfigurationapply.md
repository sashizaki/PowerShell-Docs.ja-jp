---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド
ms.openlocfilehash: ab82b239ddfdb4075d9440cd66343266b3c08eda
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="sendmetaconfigurationapply-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="7e63b-103">MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド</span><span class="sxs-lookup"><span data-stu-id="7e63b-103">SendMetaConfigurationApply method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="7e63b-104">構成エージェントを制御するために使用するローカル構成マネージャーの設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="7e63b-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

<a name="syntax"></a><span data-ttu-id="7e63b-105">構文</span><span class="sxs-lookup"><span data-stu-id="7e63b-105">Syntax</span></span>
------

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

<a name="parameters"></a><span data-ttu-id="7e63b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7e63b-106">Parameters</span></span>
----------

<span data-ttu-id="7e63b-107">*ConfigurationData* \[in\] 構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="7e63b-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="7e63b-108">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="7e63b-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="7e63b-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="7e63b-109">Return value</span></span>
------------

<span data-ttu-id="7e63b-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="7e63b-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e63b-111">コメント</span><span class="sxs-lookup"><span data-stu-id="7e63b-111">Remarks</span></span>

<span data-ttu-id="7e63b-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="7e63b-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="7e63b-113">要件</span><span class="sxs-lookup"><span data-stu-id="7e63b-113">Requirements</span></span>
------------
><span data-ttu-id="7e63b-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="7e63b-114">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="7e63b-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="7e63b-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="7e63b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7e63b-116">See also</span></span>


[<span data-ttu-id="7e63b-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="7e63b-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)