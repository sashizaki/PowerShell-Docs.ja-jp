---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApplyAsync メソッド"
ms.openlocfilehash: e680bfd1c5b39d364c90cf5ef6b43d0a568af23a
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="sendconfigurationapplyasync-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="ea079-103">MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApplyAsync メソッド</span><span class="sxs-lookup"><span data-stu-id="ea079-103">SendConfigurationApplyAsync method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="ea079-104">構成ドキュメントを管理ノードに非同期的に送信し、構成エージェントを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="ea079-104">Sends the configuration document asynchronously to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

<a name="syntax"></a><span data-ttu-id="ea079-105">構文</span><span class="sxs-lookup"><span data-stu-id="ea079-105">Syntax</span></span>
------

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

<a name="parameters"></a><span data-ttu-id="ea079-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ea079-106">Parameters</span></span>
----------

<span data-ttu-id="ea079-107">*ConfigurationData* \[in\]</span><span class="sxs-lookup"><span data-stu-id="ea079-107">*ConfigurationData* \[in\]</span></span>  
<span data-ttu-id="ea079-108">構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="ea079-108">The environment data for the configuration.</span></span>

<span data-ttu-id="ea079-109">*force* \[in\]</span><span class="sxs-lookup"><span data-stu-id="ea079-109">*force* \[in\]</span></span>  
<span data-ttu-id="ea079-110">**true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="ea079-110">**true** to force the configuration to stop.</span></span>

<span data-ttu-id="ea079-111">*jobId* \[in\]</span><span class="sxs-lookup"><span data-stu-id="ea079-111">*jobId* \[in\]</span></span>  
<span data-ttu-id="ea079-112">構成を送信するジョブの ID です。</span><span class="sxs-lookup"><span data-stu-id="ea079-112">The ID of the job for which to send the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="ea079-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="ea079-113">Return value</span></span>
------------

<span data-ttu-id="ea079-114">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="ea079-114">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="ea079-115">コメント</span><span class="sxs-lookup"><span data-stu-id="ea079-115">Remarks</span></span>

<span data-ttu-id="ea079-116">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="ea079-116">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ea079-117">要件</span><span class="sxs-lookup"><span data-stu-id="ea079-117">Requirements</span></span>
------------
><span data-ttu-id="ea079-118">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="ea079-118">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="ea079-119">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="ea079-119">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="ea079-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea079-120">See also</span></span>


[<span data-ttu-id="ea079-121">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="ea079-121">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



