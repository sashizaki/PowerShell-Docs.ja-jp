---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの EnableDebugConfiguration メソッド"
ms.openlocfilehash: 7220c972b3f43b4697cf71df54d2d43881938367
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="enabledebugconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="0345e-103">MSFT_DSCLocalConfigurationManager クラスの EnableDebugConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="0345e-103">EnableDebugConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="0345e-104">DSC リソースのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0345e-104">Enables DSC resource debugging.</span></span>

<a name="syntax"></a><span data-ttu-id="0345e-105">構文</span><span class="sxs-lookup"><span data-stu-id="0345e-105">Syntax</span></span>
------

```mof
uint32 EnableDebugConfiguration(
  [in] boolean BreakAll
);
```

<a name="parameters"></a><span data-ttu-id="0345e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0345e-106">Parameters</span></span>
----------

<span data-ttu-id="0345e-107">*BreakAll* \[in\]</span><span class="sxs-lookup"><span data-stu-id="0345e-107">*BreakAll* \[in\]</span></span>  
<span data-ttu-id="0345e-108">リソース スクリプトのすべての行にブレークポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="0345e-108">Sets a breakpoint at every line in the resource script.</span></span>

## <a name="return-value"></a><span data-ttu-id="0345e-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="0345e-109">Return value</span></span>
------------

<span data-ttu-id="0345e-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="0345e-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="0345e-111">コメント</span><span class="sxs-lookup"><span data-stu-id="0345e-111">Remarks</span></span>

<span data-ttu-id="0345e-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="0345e-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="0345e-113">要件</span><span class="sxs-lookup"><span data-stu-id="0345e-113">Requirements</span></span>
------------
><span data-ttu-id="0345e-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="0345e-114">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="0345e-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="0345e-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="0345e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0345e-116">See also</span></span>


[<span data-ttu-id="0345e-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="0345e-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
 

 



