---
ms.date: 07/17/2020
ms.topic: reference
title: GetConfigurationResultOutput メソッド
description: GetConfigurationResultOutput メソッド
ms.openlocfilehash: 7c885109b3078189b7ac653733a5fb24db66312e
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644713"
---
# <a name="getconfigurationresultoutput-method"></a><span data-ttu-id="abb56-103">GetConfigurationResultOutput メソッド</span><span class="sxs-lookup"><span data-stu-id="abb56-103">GetConfigurationResultOutput method</span></span>

<span data-ttu-id="abb56-104">特定のジョブに関連する構成エージェントの出力を取得します。</span><span class="sxs-lookup"><span data-stu-id="abb56-104">Gets the Configuration Agent output associated with a specific job.</span></span>

## <a name="syntax"></a><span data-ttu-id="abb56-105">構文</span><span class="sxs-lookup"><span data-stu-id="abb56-105">Syntax</span></span>

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

## <a name="parameters"></a><span data-ttu-id="abb56-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="abb56-106">Parameters</span></span>

<span data-ttu-id="abb56-107">**jobId** \[in\] 出力データを取得するジョブの ID です。</span><span class="sxs-lookup"><span data-stu-id="abb56-107">**jobId** \[in\] The ID of the job for which to get output data.</span></span>

<span data-ttu-id="abb56-108">**resumeOutputBookmark** \[in\] 出力が前のブックマークからの続きとなるように指定します。</span><span class="sxs-lookup"><span data-stu-id="abb56-108">**resumeOutputBookmark** \[in\] Specifies that the output should be a continuation from a previous bookmark.</span></span>

<span data-ttu-id="abb56-109">**output** \[out\] 指定されたジョブの出力です。</span><span class="sxs-lookup"><span data-stu-id="abb56-109">**output** \[out\] The output for the specified job.</span></span>

## <a name="return-value"></a><span data-ttu-id="abb56-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="abb56-110">Return value</span></span>

<span data-ttu-id="abb56-111">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="abb56-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="abb56-112">解説</span><span class="sxs-lookup"><span data-stu-id="abb56-112">Remarks</span></span>

<span data-ttu-id="abb56-113">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="abb56-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="abb56-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="abb56-114">Requirements</span></span>

<span data-ttu-id="abb56-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="abb56-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="abb56-116">**名前空間** :Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="abb56-116">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="abb56-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="abb56-117">See also</span></span>

[<span data-ttu-id="abb56-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="abb56-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
