---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの RemoveConfiguration メソッド"
ms.openlocfilehash: faa113c442b80eea3ac474220b098b7d80ec50a8
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="removeconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="902d2-103">MSFT_DSCLocalConfigurationManager クラスの RemoveConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="902d2-103">RemoveConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="902d2-104">構成ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="902d2-104">Removes the configuration files.</span></span>

<a name="syntax"></a><span data-ttu-id="902d2-105">構文</span><span class="sxs-lookup"><span data-stu-id="902d2-105">Syntax</span></span>
------

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

<a name="parameters"></a><span data-ttu-id="902d2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="902d2-106">Parameters</span></span>
----------

<span data-ttu-id="902d2-107">*Stage* \[in\]</span><span class="sxs-lookup"><span data-stu-id="902d2-107">*Stage* \[in\]</span></span>  
<span data-ttu-id="902d2-108">削除する構成ドキュメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="902d2-108">Specifies which configuration document to remove.</span></span> <span data-ttu-id="902d2-109">次の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="902d2-109">The following values are valid:</span></span>

|<span data-ttu-id="902d2-110">値</span><span class="sxs-lookup"><span data-stu-id="902d2-110">Value</span></span> |<span data-ttu-id="902d2-111">説明</span><span class="sxs-lookup"><span data-stu-id="902d2-111">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="902d2-112">**1**</span><span class="sxs-lookup"><span data-stu-id="902d2-112">**1**</span></span> | <span data-ttu-id="902d2-113">**現在**の構成ドキュメント (current.mof)。</span><span class="sxs-lookup"><span data-stu-id="902d2-113">The **Current** configuration document (current.mof).</span></span> |
|<span data-ttu-id="902d2-114">**2**</span><span class="sxs-lookup"><span data-stu-id="902d2-114">**2**</span></span> | <span data-ttu-id="902d2-115">**保留中**の構成ドキュメント (pending.mof)。</span><span class="sxs-lookup"><span data-stu-id="902d2-115">The **Pending** configuration document (pending.mof).</span></span>  |
|<span data-ttu-id="902d2-116">**4**</span><span class="sxs-lookup"><span data-stu-id="902d2-116">**4**</span></span> | <span data-ttu-id="902d2-117">**以前**の構成ドキュメント (previous.mof)。</span><span class="sxs-lookup"><span data-stu-id="902d2-117">The **Previous** configuration document (previous.mof).</span></span> |

<span data-ttu-id="902d2-118">*Force* \[in\]</span><span class="sxs-lookup"><span data-stu-id="902d2-118">*Force* \[in\]</span></span>  
<span data-ttu-id="902d2-119">**true** の場合、構成を強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="902d2-119">**true** to force the removal of the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="902d2-120">戻り値</span><span class="sxs-lookup"><span data-stu-id="902d2-120">Return value</span></span>
------------

<span data-ttu-id="902d2-121">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="902d2-121">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="902d2-122">コメント</span><span class="sxs-lookup"><span data-stu-id="902d2-122">Remarks</span></span>

<span data-ttu-id="902d2-123">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="902d2-123">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="902d2-124">要件</span><span class="sxs-lookup"><span data-stu-id="902d2-124">Requirements</span></span>
------------
><span data-ttu-id="902d2-125">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="902d2-125">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="902d2-126">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="902d2-126">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="902d2-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="902d2-127">See also</span></span>


[<span data-ttu-id="902d2-128">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="902d2-128">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



