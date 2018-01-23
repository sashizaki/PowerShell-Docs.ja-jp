---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの RemoveConfiguration メソッド"
ms.openlocfilehash: fed45836293adedbce18f01cfe53cdfa1a474975
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="removeconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="24de0-103">MSFT_DSCLocalConfigurationManager クラスの RemoveConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="24de0-103">RemoveConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="24de0-104">構成ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="24de0-104">Removes the configuration files.</span></span>

<a name="syntax"></a><span data-ttu-id="24de0-105">構文</span><span class="sxs-lookup"><span data-stu-id="24de0-105">Syntax</span></span>
------

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

<a name="parameters"></a><span data-ttu-id="24de0-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="24de0-106">Parameters</span></span>
----------

<span data-ttu-id="24de0-107">*Stage* \[in\]</span><span class="sxs-lookup"><span data-stu-id="24de0-107">*Stage* \[in\]</span></span>  
<span data-ttu-id="24de0-108">削除する構成ドキュメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="24de0-108">Specifies which configuration document to remove.</span></span> <span data-ttu-id="24de0-109">次の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="24de0-109">The following values are valid:</span></span>

|<span data-ttu-id="24de0-110">値</span><span class="sxs-lookup"><span data-stu-id="24de0-110">Value</span></span> |<span data-ttu-id="24de0-111">説明</span><span class="sxs-lookup"><span data-stu-id="24de0-111">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="24de0-112">**1**</span><span class="sxs-lookup"><span data-stu-id="24de0-112">**1**</span></span> | <span data-ttu-id="24de0-113">**現在**の構成ドキュメント (current.mof)。</span><span class="sxs-lookup"><span data-stu-id="24de0-113">The **Current** configuration document (current.mof).</span></span> |
|<span data-ttu-id="24de0-114">**2**</span><span class="sxs-lookup"><span data-stu-id="24de0-114">**2**</span></span> | <span data-ttu-id="24de0-115">**保留中**の構成ドキュメント (pending.mof)。</span><span class="sxs-lookup"><span data-stu-id="24de0-115">The **Pending** configuration document (pending.mof).</span></span>  |
|<span data-ttu-id="24de0-116">**4**</span><span class="sxs-lookup"><span data-stu-id="24de0-116">**4**</span></span> | <span data-ttu-id="24de0-117">**以前**の構成ドキュメント (previous.mof)。</span><span class="sxs-lookup"><span data-stu-id="24de0-117">The **Previous** configuration document (previous.mof).</span></span> |

<span data-ttu-id="24de0-118">*Force* \[in\]</span><span class="sxs-lookup"><span data-stu-id="24de0-118">*Force* \[in\]</span></span>  
<span data-ttu-id="24de0-119">**true** の場合、構成を強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="24de0-119">**true** to force the removal of the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="24de0-120">戻り値</span><span class="sxs-lookup"><span data-stu-id="24de0-120">Return value</span></span>
------------

<span data-ttu-id="24de0-121">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="24de0-121">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="24de0-122">コメント</span><span class="sxs-lookup"><span data-stu-id="24de0-122">Remarks</span></span>

<span data-ttu-id="24de0-123">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="24de0-123">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="24de0-124">要件</span><span class="sxs-lookup"><span data-stu-id="24de0-124">Requirements</span></span>
------------
><span data-ttu-id="24de0-125">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="24de0-125">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="24de0-126">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="24de0-126">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="24de0-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="24de0-127">See also</span></span>


[<span data-ttu-id="24de0-128">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="24de0-128">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



