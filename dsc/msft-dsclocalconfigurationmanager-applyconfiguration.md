---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの ApplyConfiguration メソッド
ms.openlocfilehash: ef8488246b2c8614452d32009e45535f0ff2e184
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34222141"
---
# <a name="applyconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="7949e-103">MSFT_DSCLocalConfigurationManager クラスの ApplyConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="7949e-103">ApplyConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="7949e-104">構成エージェントを使用して、保留中の構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="7949e-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="7949e-105">保留中の構成がない場合は、現在の構成を再適用します。</span><span class="sxs-lookup"><span data-stu-id="7949e-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>


## <a name="syntax"></a><span data-ttu-id="7949e-106">構文</span><span class="sxs-lookup"><span data-stu-id="7949e-106">Syntax</span></span>
------

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="7949e-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="7949e-107">Parameters</span></span>
----------

<span data-ttu-id="7949e-108">*force* \[in\] **true** の場合、保留中の構成があっても、現在の構成が再適用されます。</span><span class="sxs-lookup"><span data-stu-id="7949e-108">*force* \[in\] If this is **true**, the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="7949e-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="7949e-109">Return value</span></span>
------------

<span data-ttu-id="7949e-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="7949e-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="7949e-111">コメント</span><span class="sxs-lookup"><span data-stu-id="7949e-111">Remarks</span></span>

<span data-ttu-id="7949e-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="7949e-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="7949e-113">要件</span><span class="sxs-lookup"><span data-stu-id="7949e-113">Requirements</span></span>
------------
><span data-ttu-id="7949e-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="7949e-114">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="7949e-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="7949e-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="7949e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="7949e-116">See also</span></span>


[<span data-ttu-id="7949e-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="7949e-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)