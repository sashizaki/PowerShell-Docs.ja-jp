---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの ApplyConfiguration メソッド
ms.openlocfilehash: 559ff1793a18e28dad2f176bdb20eb53bc08630d
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37892614"
---
# <a name="applyconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="23774-103">MSFT_DSCLocalConfigurationManager クラスの ApplyConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="23774-103">ApplyConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="23774-104">構成エージェントを使用して、保留中の構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="23774-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="23774-105">保留中の構成がない場合は、現在の構成を再適用します。</span><span class="sxs-lookup"><span data-stu-id="23774-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="23774-106">構文</span><span class="sxs-lookup"><span data-stu-id="23774-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="23774-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="23774-107">Parameters</span></span>

<span data-ttu-id="23774-108">*force* \[in\] **true** の場合、保留中の構成があっても、現在の構成が再適用されます。</span><span class="sxs-lookup"><span data-stu-id="23774-108">*force* \[in\] If this is **true**, the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="23774-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="23774-109">Return value</span></span>

<span data-ttu-id="23774-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="23774-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="23774-111">コメント</span><span class="sxs-lookup"><span data-stu-id="23774-111">Remarks</span></span>

<span data-ttu-id="23774-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="23774-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="23774-113">要件</span><span class="sxs-lookup"><span data-stu-id="23774-113">Requirements</span></span>

<span data-ttu-id="23774-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="23774-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="23774-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="23774-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="23774-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="23774-116">See also</span></span>

[<span data-ttu-id="23774-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="23774-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)