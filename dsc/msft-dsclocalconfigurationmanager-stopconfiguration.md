---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの StopConfiguration メソッド"
ms.openlocfilehash: 66d00cb40750e91e4b369a2e8cebb449697406d9
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="stopconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="af7dd-103">MSFT_DSCLocalConfigurationManager クラスの StopConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="af7dd-103">StopConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="af7dd-104">進行中の構成の変更を停止します。</span><span class="sxs-lookup"><span data-stu-id="af7dd-104">Stops the configuration change that is in progress.</span></span>

<a name="syntax"></a><span data-ttu-id="af7dd-105">構文</span><span class="sxs-lookup"><span data-stu-id="af7dd-105">Syntax</span></span>
------

```mof
uint32 StopConfiguration(
  [in] boolean force
);
```

<a name="parameters"></a><span data-ttu-id="af7dd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af7dd-106">Parameters</span></span>
----------

<span data-ttu-id="af7dd-107">*force* \[in\]</span><span class="sxs-lookup"><span data-stu-id="af7dd-107">*force* \[in\]</span></span>  
<span data-ttu-id="af7dd-108">**true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="af7dd-108">**true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="af7dd-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="af7dd-109">Return value</span></span>
------------

<span data-ttu-id="af7dd-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="af7dd-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="af7dd-111">コメント</span><span class="sxs-lookup"><span data-stu-id="af7dd-111">Remarks</span></span>

<span data-ttu-id="af7dd-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="af7dd-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="af7dd-113">要件</span><span class="sxs-lookup"><span data-stu-id="af7dd-113">Requirements</span></span>
------------
><span data-ttu-id="af7dd-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="af7dd-114">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="af7dd-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="af7dd-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="af7dd-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="af7dd-116">See also</span></span>


[<span data-ttu-id="af7dd-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="af7dd-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



