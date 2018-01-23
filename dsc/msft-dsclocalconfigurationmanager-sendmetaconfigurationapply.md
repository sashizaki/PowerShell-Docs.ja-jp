---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド"
ms.openlocfilehash: 350555220757b1939b1de34ab423e963635eb53c
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="sendmetaconfigurationapply-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="3212f-103">MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド</span><span class="sxs-lookup"><span data-stu-id="3212f-103">SendMetaConfigurationApply method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="3212f-104">構成エージェントを制御するために使用するローカル構成マネージャーの設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="3212f-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

<a name="syntax"></a><span data-ttu-id="3212f-105">構文</span><span class="sxs-lookup"><span data-stu-id="3212f-105">Syntax</span></span>
------

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

<a name="parameters"></a><span data-ttu-id="3212f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3212f-106">Parameters</span></span>
----------

<span data-ttu-id="3212f-107">*ConfigurationData* \[in\]</span><span class="sxs-lookup"><span data-stu-id="3212f-107">*ConfigurationData* \[in\]</span></span>  
<span data-ttu-id="3212f-108">構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="3212f-108">The environment data for the configuration.</span></span>

<span data-ttu-id="3212f-109">*force* \[in\]</span><span class="sxs-lookup"><span data-stu-id="3212f-109">*force* \[in\]</span></span>  
<span data-ttu-id="3212f-110">**true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="3212f-110">**true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="3212f-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="3212f-111">Return value</span></span>
------------

<span data-ttu-id="3212f-112">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="3212f-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="3212f-113">コメント</span><span class="sxs-lookup"><span data-stu-id="3212f-113">Remarks</span></span>

<span data-ttu-id="3212f-114">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="3212f-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3212f-115">要件</span><span class="sxs-lookup"><span data-stu-id="3212f-115">Requirements</span></span>
------------
><span data-ttu-id="3212f-116">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="3212f-116">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="3212f-117">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="3212f-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="3212f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="3212f-118">See also</span></span>


[<span data-ttu-id="3212f-119">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="3212f-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



