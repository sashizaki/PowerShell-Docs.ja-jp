---
ms.date: 07/17/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: StopConfiguration メソッド
ms.openlocfilehash: 76e50c98b09dca86983320918c6899082580672a
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463705"
---
# <a name="stopconfiguration-method"></a><span data-ttu-id="50483-103">StopConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="50483-103">StopConfiguration method</span></span>

<span data-ttu-id="50483-104">進行中の構成の変更を停止します。</span><span class="sxs-lookup"><span data-stu-id="50483-104">Stops the configuration change that is in progress.</span></span>

## <a name="syntax"></a><span data-ttu-id="50483-105">構文</span><span class="sxs-lookup"><span data-stu-id="50483-105">Syntax</span></span>

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="50483-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="50483-106">Parameters</span></span>

<span data-ttu-id="50483-107">**force** \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="50483-107">**force** \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="50483-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="50483-108">Return value</span></span>

<span data-ttu-id="50483-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="50483-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="50483-110">解説</span><span class="sxs-lookup"><span data-stu-id="50483-110">Remarks</span></span>

<span data-ttu-id="50483-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="50483-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="50483-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="50483-112">Requirements</span></span>

<span data-ttu-id="50483-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="50483-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="50483-114">**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="50483-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="50483-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="50483-115">See also</span></span>

[<span data-ttu-id="50483-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="50483-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
