---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの RollBack メソッド"
ms.openlocfilehash: a219703389405c0dd457d0b2e0b1c54b9c28f559
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="rollback-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="dac3d-103">MSFT_DSCLocalConfigurationManager クラスの RollBack メソッド</span><span class="sxs-lookup"><span data-stu-id="dac3d-103">RollBack method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="dac3d-104">構成を以前のバージョンにロールバックします。</span><span class="sxs-lookup"><span data-stu-id="dac3d-104">Rolls back the configuration to a previous version.</span></span>

<a name="syntax"></a><span data-ttu-id="dac3d-105">構文</span><span class="sxs-lookup"><span data-stu-id="dac3d-105">Syntax</span></span>
------

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

<a name="parameters"></a><span data-ttu-id="dac3d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="dac3d-106">Parameters</span></span>
----------

<span data-ttu-id="dac3d-107">*configurationNumber* \[in\]</span><span class="sxs-lookup"><span data-stu-id="dac3d-107">*configurationNumber* \[in\]</span></span>  
<span data-ttu-id="dac3d-108">要求された構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="dac3d-108">Specifies the requested configuration.</span></span> 

## <a name="return-value"></a><span data-ttu-id="dac3d-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="dac3d-109">Return value</span></span>
------------

<span data-ttu-id="dac3d-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="dac3d-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="dac3d-111">コメント</span><span class="sxs-lookup"><span data-stu-id="dac3d-111">Remarks</span></span>

<span data-ttu-id="dac3d-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="dac3d-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="dac3d-113">要件</span><span class="sxs-lookup"><span data-stu-id="dac3d-113">Requirements</span></span>
------------
><span data-ttu-id="dac3d-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="dac3d-114">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="dac3d-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="dac3d-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="dac3d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="dac3d-116">See also</span></span>


[<span data-ttu-id="dac3d-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="dac3d-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



