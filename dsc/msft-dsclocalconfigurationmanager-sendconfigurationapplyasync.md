---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApplyAsync メソッド"
ms.openlocfilehash: e680d510aaac097f4f0de80660274230e028ed45
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="sendconfigurationapplyasync-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="fd262-103">MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApplyAsync メソッド</span><span class="sxs-lookup"><span data-stu-id="fd262-103">SendConfigurationApplyAsync method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="fd262-104">構成ドキュメントを管理ノードに非同期的に送信し、構成エージェントを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="fd262-104">Sends the configuration document asynchronously to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

<a name="syntax"></a><span data-ttu-id="fd262-105">構文</span><span class="sxs-lookup"><span data-stu-id="fd262-105">Syntax</span></span>
------

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

<a name="parameters"></a><span data-ttu-id="fd262-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fd262-106">Parameters</span></span>
----------

<span data-ttu-id="fd262-107">*ConfigurationData* \[in\]</span><span class="sxs-lookup"><span data-stu-id="fd262-107">*ConfigurationData* \[in\]</span></span>  
<span data-ttu-id="fd262-108">構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="fd262-108">The environment data for the configuration.</span></span>

<span data-ttu-id="fd262-109">*force* \[in\]</span><span class="sxs-lookup"><span data-stu-id="fd262-109">*force* \[in\]</span></span>  
<span data-ttu-id="fd262-110">**true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="fd262-110">**true** to force the configuration to stop.</span></span>

<span data-ttu-id="fd262-111">*jobId* \[in\]</span><span class="sxs-lookup"><span data-stu-id="fd262-111">*jobId* \[in\]</span></span>  
<span data-ttu-id="fd262-112">構成を送信するジョブの ID です。</span><span class="sxs-lookup"><span data-stu-id="fd262-112">The ID of the job for which to send the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="fd262-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="fd262-113">Return value</span></span>
------------

<span data-ttu-id="fd262-114">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="fd262-114">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="fd262-115">コメント</span><span class="sxs-lookup"><span data-stu-id="fd262-115">Remarks</span></span>

<span data-ttu-id="fd262-116">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="fd262-116">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="fd262-117">要件</span><span class="sxs-lookup"><span data-stu-id="fd262-117">Requirements</span></span>
------------
><span data-ttu-id="fd262-118">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="fd262-118">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="fd262-119">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="fd262-119">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="fd262-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd262-120">See also</span></span>


[<span data-ttu-id="fd262-121">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="fd262-121">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



