---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの GetConfigurationResultOutput メソッド
ms.openlocfilehash: f4c2ddaa37cdafeff1a442f3f1fa656788a1c6c8
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="getconfigurationresultoutput-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="efa01-103">MSFT_DSCLocalConfigurationManager クラスの GetConfigurationResultOutput メソッド</span><span class="sxs-lookup"><span data-stu-id="efa01-103">GetConfigurationResultOutput method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="efa01-104">特定のジョブに関連する構成エージェントの出力を取得します。</span><span class="sxs-lookup"><span data-stu-id="efa01-104">Gets the Configuration Agent output associated with a specific job.</span></span>

<a name="syntax"></a><span data-ttu-id="efa01-105">構文</span><span class="sxs-lookup"><span data-stu-id="efa01-105">Syntax</span></span>
------

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

<a name="parameters"></a><span data-ttu-id="efa01-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="efa01-106">Parameters</span></span>
----------

<span data-ttu-id="efa01-107">*jobId* \[in\] 出力データを取得するジョブの ID です。</span><span class="sxs-lookup"><span data-stu-id="efa01-107">*jobId* \[in\] The ID of the job for which to get output data.</span></span>

<span data-ttu-id="efa01-108">*resumeOutputBookmark* \[in\] 出力が前のブックマークからの続きとなるように指定します。</span><span class="sxs-lookup"><span data-stu-id="efa01-108">*resumeOutputBookmark* \[in\] Specifies that the output should be a continuation from a previous bookmark.</span></span>

<span data-ttu-id="efa01-109">*output* \[out\] 指定されたジョブの出力です。</span><span class="sxs-lookup"><span data-stu-id="efa01-109">*output* \[out\] The output for the specified job.</span></span>

## <a name="return-value"></a><span data-ttu-id="efa01-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="efa01-110">Return value</span></span>
------------

<span data-ttu-id="efa01-111">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="efa01-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="efa01-112">コメント</span><span class="sxs-lookup"><span data-stu-id="efa01-112">Remarks</span></span>

<span data-ttu-id="efa01-113">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="efa01-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="efa01-114">要件</span><span class="sxs-lookup"><span data-stu-id="efa01-114">Requirements</span></span>
------------
><span data-ttu-id="efa01-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="efa01-115">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="efa01-116">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="efa01-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="efa01-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="efa01-117">See also</span></span>


[<span data-ttu-id="efa01-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="efa01-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)