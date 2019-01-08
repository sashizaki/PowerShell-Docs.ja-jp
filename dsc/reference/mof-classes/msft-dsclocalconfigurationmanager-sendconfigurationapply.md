---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApply メソッド
ms.openlocfilehash: da3a08307122ab38ee4a6fd5d4a9b97579a988f7
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047506"
---
# <a name="sendconfigurationapply-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="b581c-103">MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApply メソッド</span><span class="sxs-lookup"><span data-stu-id="b581c-103">SendConfigurationApply method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="b581c-104">構成ドキュメントを管理ノードに送信し、構成エージェントを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="b581c-104">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="b581c-105">構文</span><span class="sxs-lookup"><span data-stu-id="b581c-105">Syntax</span></span>

```mof
uint32 SendConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="b581c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b581c-106">Parameters</span></span>

<span data-ttu-id="b581c-107">*ConfigurationData* \[in\] 構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="b581c-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="b581c-108">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="b581c-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="b581c-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="b581c-109">Return value</span></span>

<span data-ttu-id="b581c-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="b581c-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b581c-111">コメント</span><span class="sxs-lookup"><span data-stu-id="b581c-111">Remarks</span></span>

<span data-ttu-id="b581c-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="b581c-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b581c-113">要件</span><span class="sxs-lookup"><span data-stu-id="b581c-113">Requirements</span></span>

<span data-ttu-id="b581c-114">MOF\*\*DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="b581c-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="b581c-115">\*\*［名前空間］:Root \microsoft\windows\desiredstateconfiguration</span><span class="sxs-lookup"><span data-stu-id="b581c-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="b581c-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b581c-116">See also</span></span>

[<span data-ttu-id="b581c-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="b581c-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)