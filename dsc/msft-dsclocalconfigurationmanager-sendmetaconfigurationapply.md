---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド"
ms.openlocfilehash: d8ddc9d99f0d74ad907a6e39ae0e8ac14159be16
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="sendmetaconfigurationapply-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="d07a2-103">MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド</span><span class="sxs-lookup"><span data-stu-id="d07a2-103">SendMetaConfigurationApply method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="d07a2-104">構成エージェントを制御するために使用するローカル構成マネージャーの設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="d07a2-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

<a name="syntax"></a><span data-ttu-id="d07a2-105">構文</span><span class="sxs-lookup"><span data-stu-id="d07a2-105">Syntax</span></span>
------

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

<a name="parameters"></a><span data-ttu-id="d07a2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="d07a2-106">Parameters</span></span>
----------

<span data-ttu-id="d07a2-107">*ConfigurationData* \[in\]</span><span class="sxs-lookup"><span data-stu-id="d07a2-107">*ConfigurationData* \[in\]</span></span>  
<span data-ttu-id="d07a2-108">構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="d07a2-108">The environment data for the configuration.</span></span>

<span data-ttu-id="d07a2-109">*force* \[in\]</span><span class="sxs-lookup"><span data-stu-id="d07a2-109">*force* \[in\]</span></span>  
<span data-ttu-id="d07a2-110">**true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="d07a2-110">**true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="d07a2-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="d07a2-111">Return value</span></span>
------------

<span data-ttu-id="d07a2-112">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="d07a2-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="d07a2-113">コメント</span><span class="sxs-lookup"><span data-stu-id="d07a2-113">Remarks</span></span>

<span data-ttu-id="d07a2-114">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="d07a2-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="d07a2-115">要件</span><span class="sxs-lookup"><span data-stu-id="d07a2-115">Requirements</span></span>
------------
><span data-ttu-id="d07a2-116">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="d07a2-116">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="d07a2-117">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="d07a2-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="d07a2-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d07a2-118">See also</span></span>


[<span data-ttu-id="d07a2-119">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="d07a2-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



