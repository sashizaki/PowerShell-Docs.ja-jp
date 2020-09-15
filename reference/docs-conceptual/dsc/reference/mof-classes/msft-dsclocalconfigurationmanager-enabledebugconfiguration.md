---
ms.date: 07/17/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: EnableDebugConfiguration メソッド
ms.openlocfilehash: be75b1012f49db79eb75a68c6912ffd5772bf16f
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464096"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="a1eca-103">EnableDebugConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="a1eca-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="a1eca-104">DSC リソースのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a1eca-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="a1eca-105">構文</span><span class="sxs-lookup"><span data-stu-id="a1eca-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="a1eca-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1eca-106">Parameters</span></span>

<span data-ttu-id="a1eca-107">**BreakAll** \[in\] リソース スクリプトのすべての行にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="a1eca-107">**BreakAll** \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="a1eca-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="a1eca-108">Return value</span></span>

<span data-ttu-id="a1eca-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="a1eca-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1eca-110">解説</span><span class="sxs-lookup"><span data-stu-id="a1eca-110">Remarks</span></span>

<span data-ttu-id="a1eca-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="a1eca-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a1eca-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a1eca-112">Requirements</span></span>

<span data-ttu-id="a1eca-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="a1eca-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="a1eca-114">**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="a1eca-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="a1eca-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1eca-115">See also</span></span>

[<span data-ttu-id="a1eca-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="a1eca-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
