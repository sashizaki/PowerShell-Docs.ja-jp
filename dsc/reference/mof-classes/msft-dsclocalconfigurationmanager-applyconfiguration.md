---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: ApplyConfiguration メソッド
ms.openlocfilehash: 0425b9a7db37e421830ba37da8f5c0a4877a1b72
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67727177"
---
# <a name="applyconfiguration-method"></a><span data-ttu-id="b5a36-103">ApplyConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="b5a36-103">ApplyConfiguration method</span></span>

<span data-ttu-id="b5a36-104">構成エージェントを使用して、保留中の構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="b5a36-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="b5a36-105">保留中の構成がない場合は、現在の構成を再適用します。</span><span class="sxs-lookup"><span data-stu-id="b5a36-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="b5a36-106">構文</span><span class="sxs-lookup"><span data-stu-id="b5a36-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="b5a36-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b5a36-107">Parameters</span></span>

<span data-ttu-id="b5a36-108">*force* \[in\] **true** の場合、保留中の構成があっても、現在の構成が再適用されます。</span><span class="sxs-lookup"><span data-stu-id="b5a36-108">*force* \[in\] If this is **true**, the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="b5a36-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="b5a36-109">Return value</span></span>

<span data-ttu-id="b5a36-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="b5a36-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5a36-111">コメント</span><span class="sxs-lookup"><span data-stu-id="b5a36-111">Remarks</span></span>

<span data-ttu-id="b5a36-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="b5a36-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b5a36-113">要件</span><span class="sxs-lookup"><span data-stu-id="b5a36-113">Requirements</span></span>

<span data-ttu-id="b5a36-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="b5a36-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="b5a36-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="b5a36-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="b5a36-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5a36-116">See also</span></span>

[<span data-ttu-id="b5a36-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="b5a36-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
