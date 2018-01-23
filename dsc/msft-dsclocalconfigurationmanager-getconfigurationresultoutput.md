---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの GetConfigurationResultOutput メソッド"
ms.openlocfilehash: f6106bb28dc20004b5bbb6df2d8e719cf0c453f0
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="getconfigurationresultoutput-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="c244b-103">MSFT_DSCLocalConfigurationManager クラスの GetConfigurationResultOutput メソッド</span><span class="sxs-lookup"><span data-stu-id="c244b-103">GetConfigurationResultOutput method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="c244b-104">特定のジョブに関連する構成エージェントの出力を取得します。</span><span class="sxs-lookup"><span data-stu-id="c244b-104">Gets the Configuration Agent output associated with a specific job.</span></span>

<a name="syntax"></a><span data-ttu-id="c244b-105">構文</span><span class="sxs-lookup"><span data-stu-id="c244b-105">Syntax</span></span>
------

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

<a name="parameters"></a><span data-ttu-id="c244b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c244b-106">Parameters</span></span>
----------

<span data-ttu-id="c244b-107">*jobId* \[in\]</span><span class="sxs-lookup"><span data-stu-id="c244b-107">*jobId* \[in\]</span></span>  
<span data-ttu-id="c244b-108">出力データを取得するジョブの ID です。</span><span class="sxs-lookup"><span data-stu-id="c244b-108">The ID of the job for which to get output data.</span></span>

<span data-ttu-id="c244b-109">*resumeOutputBookmark* \[in\]</span><span class="sxs-lookup"><span data-stu-id="c244b-109">*resumeOutputBookmark* \[in\]</span></span>  
<span data-ttu-id="c244b-110">出力が前のブックマークからの続きとなるように指定します。</span><span class="sxs-lookup"><span data-stu-id="c244b-110">Specifies that the output should be a continuation from a previous bookmark.</span></span>

<span data-ttu-id="c244b-111">*output* \[out\]</span><span class="sxs-lookup"><span data-stu-id="c244b-111">*output* \[out\]</span></span>  
<span data-ttu-id="c244b-112">指定されたジョブの出力です。</span><span class="sxs-lookup"><span data-stu-id="c244b-112">The output for the specified job.</span></span>

## <a name="return-value"></a><span data-ttu-id="c244b-113">戻り値</span><span class="sxs-lookup"><span data-stu-id="c244b-113">Return value</span></span>
------------

<span data-ttu-id="c244b-114">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="c244b-114">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="c244b-115">コメント</span><span class="sxs-lookup"><span data-stu-id="c244b-115">Remarks</span></span>

<span data-ttu-id="c244b-116">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="c244b-116">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c244b-117">要件</span><span class="sxs-lookup"><span data-stu-id="c244b-117">Requirements</span></span>
------------
><span data-ttu-id="c244b-118">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="c244b-118">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="c244b-119">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="c244b-119">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="c244b-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c244b-120">See also</span></span>


[<span data-ttu-id="c244b-121">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="c244b-121">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)

 

 



