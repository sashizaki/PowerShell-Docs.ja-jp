---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの RollBack メソッド
ms.openlocfilehash: d2f9b7025d611912e119800408e25fcb66bc0228
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="rollback-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="5226f-103">MSFT_DSCLocalConfigurationManager クラスの RollBack メソッド</span><span class="sxs-lookup"><span data-stu-id="5226f-103">RollBack method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="5226f-104">構成を以前のバージョンにロールバックします。</span><span class="sxs-lookup"><span data-stu-id="5226f-104">Rolls back the configuration to a previous version.</span></span>

<a name="syntax"></a><span data-ttu-id="5226f-105">構文</span><span class="sxs-lookup"><span data-stu-id="5226f-105">Syntax</span></span>
------

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

<a name="parameters"></a><span data-ttu-id="5226f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5226f-106">Parameters</span></span>
----------

<span data-ttu-id="5226f-107">*configurationNumber* \[in\] 要求された構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="5226f-107">*configurationNumber* \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="5226f-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="5226f-108">Return value</span></span>
------------

<span data-ttu-id="5226f-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="5226f-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="5226f-110">コメント</span><span class="sxs-lookup"><span data-stu-id="5226f-110">Remarks</span></span>

<span data-ttu-id="5226f-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="5226f-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="5226f-112">要件</span><span class="sxs-lookup"><span data-stu-id="5226f-112">Requirements</span></span>
------------
><span data-ttu-id="5226f-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="5226f-113">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="5226f-114">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="5226f-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="5226f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5226f-115">See also</span></span>


[<span data-ttu-id="5226f-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="5226f-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)