---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: SendConfigurationApply メソッド
ms.openlocfilehash: 11b9d435bbaac1600d25ff074b6c55b236a8378b
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954889"
---
# <a name="sendconfigurationapply-method"></a><span data-ttu-id="c23bf-103">SendConfigurationApply メソッド</span><span class="sxs-lookup"><span data-stu-id="c23bf-103">SendConfigurationApply method</span></span>

<span data-ttu-id="c23bf-104">構成ドキュメントを管理ノードに送信し、構成エージェントを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="c23bf-104">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="c23bf-105">構文</span><span class="sxs-lookup"><span data-stu-id="c23bf-105">Syntax</span></span>

```mof
uint32 SendConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="c23bf-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c23bf-106">Parameters</span></span>

<span data-ttu-id="c23bf-107">*ConfigurationData* \[in\] 構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="c23bf-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="c23bf-108">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="c23bf-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="c23bf-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="c23bf-109">Return value</span></span>

<span data-ttu-id="c23bf-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="c23bf-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="c23bf-111">コメント</span><span class="sxs-lookup"><span data-stu-id="c23bf-111">Remarks</span></span>

<span data-ttu-id="c23bf-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="c23bf-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c23bf-113">要件</span><span class="sxs-lookup"><span data-stu-id="c23bf-113">Requirements</span></span>

<span data-ttu-id="c23bf-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="c23bf-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="c23bf-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="c23bf-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="c23bf-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c23bf-116">See also</span></span>

[<span data-ttu-id="c23bf-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="c23bf-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
