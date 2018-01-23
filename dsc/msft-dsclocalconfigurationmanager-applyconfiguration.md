---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの ApplyConfiguration メソッド"
ms.openlocfilehash: 72fbedf30e5058d8003ed620400d6b443d50dff6
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="applyconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="883da-103">MSFT_DSCLocalConfigurationManager クラスの ApplyConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="883da-103">ApplyConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="883da-104">構成エージェントを使用して、保留中の構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="883da-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span> 

<span data-ttu-id="883da-105">保留中の構成がない場合は、現在の構成を再適用します。</span><span class="sxs-lookup"><span data-stu-id="883da-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>


## <a name="syntax"></a><span data-ttu-id="883da-106">構文</span><span class="sxs-lookup"><span data-stu-id="883da-106">Syntax</span></span>
------

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="883da-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="883da-107">Parameters</span></span>
----------

<span data-ttu-id="883da-108">*force* \[in\]</span><span class="sxs-lookup"><span data-stu-id="883da-108">*force* \[in\]</span></span>  
<span data-ttu-id="883da-109">**true** の場合、保留中の構成があっても、現在の構成が再適用されます。</span><span class="sxs-lookup"><span data-stu-id="883da-109">If this is **true**, the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="883da-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="883da-110">Return value</span></span>
------------

<span data-ttu-id="883da-111">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="883da-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="883da-112">コメント</span><span class="sxs-lookup"><span data-stu-id="883da-112">Remarks</span></span>

<span data-ttu-id="883da-113">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="883da-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="883da-114">要件</span><span class="sxs-lookup"><span data-stu-id="883da-114">Requirements</span></span>
------------
><span data-ttu-id="883da-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="883da-115">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="883da-116">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="883da-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="883da-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="883da-117">See also</span></span>


[<span data-ttu-id="883da-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="883da-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)

 

 



