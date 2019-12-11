---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: EnableDebugConfiguration メソッド
ms.openlocfilehash: f1290e4d898332361850ffc85aa0a8d79863c8f7
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71953439"
---
# <a name="enabledebugconfiguration-method"></a><span data-ttu-id="95dfd-103">EnableDebugConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="95dfd-103">EnableDebugConfiguration method</span></span>

<span data-ttu-id="95dfd-104">DSC リソースのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="95dfd-104">Enables DSC resource debugging.</span></span>

## <a name="syntax"></a><span data-ttu-id="95dfd-105">構文</span><span class="sxs-lookup"><span data-stu-id="95dfd-105">Syntax</span></span>

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

## <a name="parameters"></a><span data-ttu-id="95dfd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="95dfd-106">Parameters</span></span>

<span data-ttu-id="95dfd-107">*BreakAll* \[in\] リソース スクリプトのすべての行にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="95dfd-107">*BreakAll* \[in\] Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="95dfd-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="95dfd-108">Return value</span></span>

<span data-ttu-id="95dfd-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="95dfd-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="95dfd-110">コメント</span><span class="sxs-lookup"><span data-stu-id="95dfd-110">Remarks</span></span>

<span data-ttu-id="95dfd-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="95dfd-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="95dfd-112">要件</span><span class="sxs-lookup"><span data-stu-id="95dfd-112">Requirements</span></span>

<span data-ttu-id="95dfd-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="95dfd-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="95dfd-114">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="95dfd-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="95dfd-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="95dfd-115">See also</span></span>

[<span data-ttu-id="95dfd-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="95dfd-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
