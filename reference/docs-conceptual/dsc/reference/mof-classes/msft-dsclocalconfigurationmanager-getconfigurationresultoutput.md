---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: GetConfigurationResultOutput メソッド
ms.openlocfilehash: 480e710ce1a208253f0e664474c3e9bab296066a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953419"
---
# <a name="getconfigurationresultoutput-method"></a><span data-ttu-id="f6ca9-103">GetConfigurationResultOutput メソッド</span><span class="sxs-lookup"><span data-stu-id="f6ca9-103">GetConfigurationResultOutput method</span></span>

<span data-ttu-id="f6ca9-104">特定のジョブに関連する構成エージェントの出力を取得します。</span><span class="sxs-lookup"><span data-stu-id="f6ca9-104">Gets the Configuration Agent output associated with a specific job.</span></span>

## <a name="syntax"></a><span data-ttu-id="f6ca9-105">構文</span><span class="sxs-lookup"><span data-stu-id="f6ca9-105">Syntax</span></span>

```mof
uint32 GetConfigurationResultOutput(
  [in]  string                      jobId,
  [in]  uint8                       resumeOutputBookmark[],
  [out] MSFT_DSCConfigurationOutput output[]
);
```

## <a name="parameters"></a><span data-ttu-id="f6ca9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f6ca9-106">Parameters</span></span>

<span data-ttu-id="f6ca9-107">*jobId* \[in\] 出力データを取得するジョブの ID です。</span><span class="sxs-lookup"><span data-stu-id="f6ca9-107">*jobId* \[in\] The ID of the job for which to get output data.</span></span>

<span data-ttu-id="f6ca9-108">*resumeOutputBookmark* \[in\] 出力が前のブックマークからの続きとなるように指定します。</span><span class="sxs-lookup"><span data-stu-id="f6ca9-108">*resumeOutputBookmark* \[in\] Specifies that the output should be a continuation from a previous bookmark.</span></span>

<span data-ttu-id="f6ca9-109">*output* \[out\] 指定されたジョブの出力です。</span><span class="sxs-lookup"><span data-stu-id="f6ca9-109">*output* \[out\] The output for the specified job.</span></span>

## <a name="return-value"></a><span data-ttu-id="f6ca9-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="f6ca9-110">Return value</span></span>

<span data-ttu-id="f6ca9-111">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="f6ca9-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6ca9-112">コメント</span><span class="sxs-lookup"><span data-stu-id="f6ca9-112">Remarks</span></span>

<span data-ttu-id="f6ca9-113">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="f6ca9-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f6ca9-114">要件</span><span class="sxs-lookup"><span data-stu-id="f6ca9-114">Requirements</span></span>

<span data-ttu-id="f6ca9-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="f6ca9-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="f6ca9-116">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="f6ca9-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="f6ca9-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6ca9-117">See also</span></span>

[<span data-ttu-id="f6ca9-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="f6ca9-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
