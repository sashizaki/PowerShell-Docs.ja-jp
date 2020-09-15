---
ms.date: 07/14/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: ApplyConfiguration メソッド
ms.openlocfilehash: bec74ccd6f75448484adfd26bf8a4af4e224eb3f
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463841"
---
# <a name="applyconfiguration-method"></a><span data-ttu-id="f8437-103">ApplyConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="f8437-103">ApplyConfiguration method</span></span>

<span data-ttu-id="f8437-104">構成エージェントを使用して、保留中の構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="f8437-104">Uses the Configuration Agent to apply the configuration that is pending.</span></span>

<span data-ttu-id="f8437-105">保留中の構成がない場合は、現在の構成を再適用します。</span><span class="sxs-lookup"><span data-stu-id="f8437-105">If there is no configuration pending, this method reapplies the current configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="f8437-106">構文</span><span class="sxs-lookup"><span data-stu-id="f8437-106">Syntax</span></span>

```mof
uint32 ApplyConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="f8437-107">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f8437-107">Parameters</span></span>

### <a name="force"></a><span data-ttu-id="f8437-108">force</span><span class="sxs-lookup"><span data-stu-id="f8437-108">force</span></span>

<span data-ttu-id="f8437-109">**true** の場合、保留中の構成があっても、現在の構成が再適用されます。</span><span class="sxs-lookup"><span data-stu-id="f8437-109">If this is **true**, the current configuration is reapplied, even if there is a configuration pending.</span></span>

## <a name="return-value"></a><span data-ttu-id="f8437-110">戻り値</span><span class="sxs-lookup"><span data-stu-id="f8437-110">Return value</span></span>

<span data-ttu-id="f8437-111">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="f8437-111">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="f8437-112">解説</span><span class="sxs-lookup"><span data-stu-id="f8437-112">Remarks</span></span>

<span data-ttu-id="f8437-113">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="f8437-113">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f8437-114">必要条件</span><span class="sxs-lookup"><span data-stu-id="f8437-114">Requirements</span></span>

<span data-ttu-id="f8437-115">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="f8437-115">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="f8437-116">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="f8437-116">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="f8437-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8437-117">See also</span></span>

[<span data-ttu-id="f8437-118">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="f8437-118">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
