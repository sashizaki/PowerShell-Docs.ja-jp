---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: EnableDebugConfiguration メソッド
ms.openlocfilehash: f1290e4d898332361850ffc85aa0a8d79863c8f7
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953439"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="8a924-103">EnableDebugConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="8a924-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="8a924-104">DSC リソースのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8a924-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="8a924-105">構文</span><span class="sxs-lookup"><span data-stu-id="8a924-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="8a924-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a924-106">Parameters</span></span>

<span data-ttu-id="8a924-107">*BreakAll* \[in\] リソース スクリプトのすべての行にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="8a924-107">*BreakAll* \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="8a924-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="8a924-108">Return value</span></span>

<span data-ttu-id="8a924-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="8a924-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="8a924-110">解説</span><span class="sxs-lookup"><span data-stu-id="8a924-110">Remarks</span></span>

<span data-ttu-id="8a924-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="8a924-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8a924-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="8a924-112">Requirements</span></span>

<span data-ttu-id="8a924-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="8a924-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="8a924-114">**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="8a924-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="8a924-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a924-115">See also</span></span>

[<span data-ttu-id="8a924-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="8a924-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
