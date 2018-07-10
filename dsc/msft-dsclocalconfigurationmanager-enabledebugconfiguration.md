---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの EnableDebugConfiguration メソッド
ms.openlocfilehash: b2eaebfa901cb5d93fd0183287073e6b31f975d1
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37892401"
---
# <a name="enabledebugconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="33ba8-103">MSFT_DSCLocalConfigurationManager クラスの EnableDebugConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="33ba8-103">EnableDebugConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="33ba8-104">DSC リソースのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="33ba8-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="33ba8-105">構文</span><span class="sxs-lookup"><span data-stu-id="33ba8-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="33ba8-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="33ba8-106">Parameters</span></span>

<span data-ttu-id="33ba8-107">*BreakAll* \[in\] リソース スクリプトのすべての行にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="33ba8-107">*BreakAll* \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="33ba8-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="33ba8-108">Return value</span></span>

<span data-ttu-id="33ba8-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="33ba8-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="33ba8-110">コメント</span><span class="sxs-lookup"><span data-stu-id="33ba8-110">Remarks</span></span>

<span data-ttu-id="33ba8-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="33ba8-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="33ba8-112">要件</span><span class="sxs-lookup"><span data-stu-id="33ba8-112">Requirements</span></span>

<span data-ttu-id="33ba8-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="33ba8-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="33ba8-114">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="33ba8-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="33ba8-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="33ba8-115">See also</span></span>

[<span data-ttu-id="33ba8-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="33ba8-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)