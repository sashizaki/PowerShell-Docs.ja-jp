---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: SendConfigurationApplyAsync メソッド
ms.openlocfilehash: c0e6dc9418757ee719e848fa8e7006dd73d91ad8
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953379"
---
# <a name="sendconfigurationapplyasync-method"></a><span data-ttu-id="b8a1f-103">SendConfigurationApplyAsync メソッド</span><span class="sxs-lookup"><span data-stu-id="b8a1f-103">SendConfigurationApplyAsync method</span></span>

<span data-ttu-id="b8a1f-104">構成ドキュメントを管理ノードに非同期的に送信し、構成エージェントを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="b8a1f-104">Sends the configuration document asynchronously to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="b8a1f-105">構文</span><span class="sxs-lookup"><span data-stu-id="b8a1f-105">Syntax</span></span>

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

## <a name="parameters"></a><span data-ttu-id="b8a1f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b8a1f-106">Parameters</span></span>

<span data-ttu-id="b8a1f-107">*ConfigurationData* \[in\] 構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="b8a1f-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="b8a1f-108">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="b8a1f-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

<span data-ttu-id="b8a1f-109">*jobId* \[in\] 構成を送信するジョブの ID です。</span><span class="sxs-lookup"><span data-stu-id="b8a1f-109">*jobId* \[in\] The ID of the job for which to send the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="b8a1f-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="b8a1f-110">Return value</span></span>

<span data-ttu-id="b8a1f-111">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="b8a1f-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b8a1f-112">コメント</span><span class="sxs-lookup"><span data-stu-id="b8a1f-112">Remarks</span></span>

<span data-ttu-id="b8a1f-113">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="b8a1f-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b8a1f-114">要件</span><span class="sxs-lookup"><span data-stu-id="b8a1f-114">Requirements</span></span>

<span data-ttu-id="b8a1f-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="b8a1f-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="b8a1f-116">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="b8a1f-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="b8a1f-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8a1f-117">See also</span></span>

[<span data-ttu-id="b8a1f-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="b8a1f-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)