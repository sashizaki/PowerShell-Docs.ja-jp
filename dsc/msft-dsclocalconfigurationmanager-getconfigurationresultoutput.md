---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの GetConfigurationResultOutput メソッド"
ms.openlocfilehash: 09862fd3c19e1e517c9bf5df878113ba3f10d8a6
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="getconfigurationresultoutput-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="39690-103">MSFT_DSCLocalConfigurationManager クラスの GetConfigurationResultOutput メソッド</span><span class="sxs-lookup"><span data-stu-id="39690-103">GetConfigurationResultOutput method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="39690-104">特定のジョブに関連する構成エージェントの出力を取得します。</span><span class="sxs-lookup"><span data-stu-id="39690-104">Gets the Configuration Agent output associated with a specific job.</span></span>

<a name="syntax"></a><span data-ttu-id="39690-105">構文</span><span class="sxs-lookup"><span data-stu-id="39690-105">Syntax</span></span>
------

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

<a name="parameters"></a><span data-ttu-id="39690-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="39690-106">Parameters</span></span>
----------

<span data-ttu-id="39690-107">*jobId* \[in\]</span><span class="sxs-lookup"><span data-stu-id="39690-107">*jobId* \[in\]</span></span>  
<span data-ttu-id="39690-108">出力データを取得するジョブの ID です。</span><span class="sxs-lookup"><span data-stu-id="39690-108">The ID of the job for which to get output data.</span></span>

<span data-ttu-id="39690-109">*resumeOutputBookmark* \[in\]</span><span class="sxs-lookup"><span data-stu-id="39690-109">*resumeOutputBookmark* \[in\]</span></span>  
<span data-ttu-id="39690-110">出力が前のブックマークからの続きとなるように指定します。</span><span class="sxs-lookup"><span data-stu-id="39690-110">Specifies that the output should be a continuation from a previous bookmark.</span></span>

<span data-ttu-id="39690-111">*output* \[out\]</span><span class="sxs-lookup"><span data-stu-id="39690-111">*output* \[out\]</span></span>  
<span data-ttu-id="39690-112">指定されたジョブの出力です。</span><span class="sxs-lookup"><span data-stu-id="39690-112">The output for the specified job.</span></span>

## <a name="return-value"></a><span data-ttu-id="39690-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="39690-113">Return value</span></span>
------------

<span data-ttu-id="39690-114">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="39690-114">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="39690-115">コメント</span><span class="sxs-lookup"><span data-stu-id="39690-115">Remarks</span></span>

<span data-ttu-id="39690-116">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="39690-116">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="39690-117">要件</span><span class="sxs-lookup"><span data-stu-id="39690-117">Requirements</span></span>
------------
><span data-ttu-id="39690-118">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="39690-118">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="39690-119">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="39690-119">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="39690-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="39690-120">See also</span></span>


[<span data-ttu-id="39690-121">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="39690-121">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)

 

 



