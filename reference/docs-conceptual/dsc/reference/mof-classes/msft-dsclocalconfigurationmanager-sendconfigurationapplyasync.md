---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: SendConfigurationApplyAsync メソッド
ms.openlocfilehash: c0e6dc9418757ee719e848fa8e7006dd73d91ad8
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953379"
---
# <a name="sendconfigurationapplyasync-method"></a><span data-ttu-id="6159d-103">SendConfigurationApplyAsync メソッド</span><span class="sxs-lookup"><span data-stu-id="6159d-103">SendConfigurationApplyAsync method</span></span>

<span data-ttu-id="6159d-104">構成ドキュメントを管理ノードに非同期的に送信し、構成エージェントを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="6159d-104">Sends the configuration document asynchronously to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="6159d-105">構文</span><span class="sxs-lookup"><span data-stu-id="6159d-105">Syntax</span></span>

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

## <a name="parameters"></a><span data-ttu-id="6159d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6159d-106">Parameters</span></span>

<span data-ttu-id="6159d-107">*ConfigurationData* \[in\] 構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="6159d-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="6159d-108">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="6159d-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

<span data-ttu-id="6159d-109">*jobId* \[in\] 構成を送信するジョブの ID です。</span><span class="sxs-lookup"><span data-stu-id="6159d-109">*jobId* \[in\] The ID of the job for which to send the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="6159d-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="6159d-110">Return value</span></span>

<span data-ttu-id="6159d-111">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="6159d-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="6159d-112">解説</span><span class="sxs-lookup"><span data-stu-id="6159d-112">Remarks</span></span>

<span data-ttu-id="6159d-113">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="6159d-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="6159d-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="6159d-114">Requirements</span></span>

<span data-ttu-id="6159d-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="6159d-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="6159d-116">**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="6159d-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="6159d-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6159d-117">See also</span></span>

[<span data-ttu-id="6159d-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="6159d-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
