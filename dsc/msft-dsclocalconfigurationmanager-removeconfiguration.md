---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの RemoveConfiguration メソッド
ms.openlocfilehash: e0ae8a50212b70841d210d7b2d666a2855218d1a
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="removeconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="b06fa-103">MSFT_DSCLocalConfigurationManager クラスの RemoveConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="b06fa-103">RemoveConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="b06fa-104">構成ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="b06fa-104">Removes the configuration files.</span></span>

<a name="syntax"></a><span data-ttu-id="b06fa-105">構文</span><span class="sxs-lookup"><span data-stu-id="b06fa-105">Syntax</span></span>
------

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

<a name="parameters"></a><span data-ttu-id="b06fa-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b06fa-106">Parameters</span></span>
----------

<span data-ttu-id="b06fa-107">*Stage* \[in\] 削除する構成ドキュメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="b06fa-107">*Stage* \[in\] Specifies which configuration document to remove.</span></span> <span data-ttu-id="b06fa-108">次の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="b06fa-108">The following values are valid:</span></span>

|<span data-ttu-id="b06fa-109">値</span><span class="sxs-lookup"><span data-stu-id="b06fa-109">Value</span></span> |<span data-ttu-id="b06fa-110">説明</span><span class="sxs-lookup"><span data-stu-id="b06fa-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="b06fa-111">**1**</span><span class="sxs-lookup"><span data-stu-id="b06fa-111">**1**</span></span> | <span data-ttu-id="b06fa-112">**現在**の構成ドキュメント (current.mof)。</span><span class="sxs-lookup"><span data-stu-id="b06fa-112">The **Current** configuration document (current.mof).</span></span> |
|<span data-ttu-id="b06fa-113">**2**</span><span class="sxs-lookup"><span data-stu-id="b06fa-113">**2**</span></span> | <span data-ttu-id="b06fa-114">**保留中**の構成ドキュメント (pending.mof)。</span><span class="sxs-lookup"><span data-stu-id="b06fa-114">The **Pending** configuration document (pending.mof).</span></span>  |
|<span data-ttu-id="b06fa-115">**4**</span><span class="sxs-lookup"><span data-stu-id="b06fa-115">**4**</span></span> | <span data-ttu-id="b06fa-116">**以前**の構成ドキュメント (previous.mof)。</span><span class="sxs-lookup"><span data-stu-id="b06fa-116">The **Previous** configuration document (previous.mof).</span></span> |

<span data-ttu-id="b06fa-117">*Force* \[in\] **true** の場合、構成を強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="b06fa-117">*Force* \[in\] **true** to force the removal of the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="b06fa-118">戻り値</span><span class="sxs-lookup"><span data-stu-id="b06fa-118">Return value</span></span>
------------

<span data-ttu-id="b06fa-119">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="b06fa-119">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b06fa-120">コメント</span><span class="sxs-lookup"><span data-stu-id="b06fa-120">Remarks</span></span>

<span data-ttu-id="b06fa-121">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="b06fa-121">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b06fa-122">要件</span><span class="sxs-lookup"><span data-stu-id="b06fa-122">Requirements</span></span>
------------
><span data-ttu-id="b06fa-123">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="b06fa-123">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="b06fa-124">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="b06fa-124">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="b06fa-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="b06fa-125">See also</span></span>


[<span data-ttu-id="b06fa-126">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="b06fa-126">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)