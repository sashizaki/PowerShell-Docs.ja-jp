---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApplyAsync メソッド
ms.openlocfilehash: b028079cf826719967858f50e357b441ba8f9d79
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047673"
---
# <a name="sendconfigurationapplyasync-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="11888-103">MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApplyAsync メソッド</span><span class="sxs-lookup"><span data-stu-id="11888-103">SendConfigurationApplyAsync method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="11888-104">構成ドキュメントを管理ノードに非同期的に送信し、構成エージェントを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="11888-104">Sends the configuration document asynchronously to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="11888-105">構文</span><span class="sxs-lookup"><span data-stu-id="11888-105">Syntax</span></span>

```mof
uint32 SendConfigurationApplyAsync(
  [in] uint8   ConfigurationData[],
  [in] boolean force,
  [in] string  jobId
);
```

## <a name="parameters"></a><span data-ttu-id="11888-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="11888-106">Parameters</span></span>

<span data-ttu-id="11888-107">*ConfigurationData* \[in\] 構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="11888-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="11888-108">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="11888-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

<span data-ttu-id="11888-109">*jobId* \[in\] 構成を送信するジョブの ID です。</span><span class="sxs-lookup"><span data-stu-id="11888-109">*jobId* \[in\] The ID of the job for which to send the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="11888-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="11888-110">Return value</span></span>

<span data-ttu-id="11888-111">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="11888-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="11888-112">コメント</span><span class="sxs-lookup"><span data-stu-id="11888-112">Remarks</span></span>

<span data-ttu-id="11888-113">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="11888-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="11888-114">要件</span><span class="sxs-lookup"><span data-stu-id="11888-114">Requirements</span></span>

<span data-ttu-id="11888-115">MOF\*\*DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="11888-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="11888-116">\*\*［名前空間］:Root \microsoft\windows\desiredstateconfiguration</span><span class="sxs-lookup"><span data-stu-id="11888-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="11888-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="11888-117">See also</span></span>

[<span data-ttu-id="11888-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="11888-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)