---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApply メソッド
ms.openlocfilehash: c578f4f52d3ea70e7bcf683ac204d6e484d4630d
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34222158"
---
# <a name="sendconfigurationapply-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="134c9-103">MSFT_DSCLocalConfigurationManager クラスの SendConfigurationApply メソッド</span><span class="sxs-lookup"><span data-stu-id="134c9-103">SendConfigurationApply method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="134c9-104">構成ドキュメントを管理ノードに送信し、構成エージェントを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="134c9-104">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

<a name="syntax"></a><span data-ttu-id="134c9-105">構文</span><span class="sxs-lookup"><span data-stu-id="134c9-105">Syntax</span></span>
------

```mof
uint32 SendConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

<a name="parameters"></a><span data-ttu-id="134c9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="134c9-106">Parameters</span></span>
----------

<span data-ttu-id="134c9-107">*ConfigurationData* \[in\] 構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="134c9-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="134c9-108">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="134c9-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="134c9-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="134c9-109">Return value</span></span>
------------

<span data-ttu-id="134c9-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="134c9-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="134c9-111">コメント</span><span class="sxs-lookup"><span data-stu-id="134c9-111">Remarks</span></span>

<span data-ttu-id="134c9-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="134c9-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="134c9-113">要件</span><span class="sxs-lookup"><span data-stu-id="134c9-113">Requirements</span></span>
------------
><span data-ttu-id="134c9-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="134c9-114">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="134c9-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="134c9-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="134c9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="134c9-116">See also</span></span>


[<span data-ttu-id="134c9-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="134c9-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)