---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの RollBack メソッド"
ms.openlocfilehash: b8597e3eb7872d9894863fb02d927c9f475da44c
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="rollback-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="382a2-103">MSFT_DSCLocalConfigurationManager クラスの RollBack メソッド</span><span class="sxs-lookup"><span data-stu-id="382a2-103">RollBack method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="382a2-104">構成を以前のバージョンにロールバックします。</span><span class="sxs-lookup"><span data-stu-id="382a2-104">Rolls back the configuration to a previous version.</span></span>

<a name="syntax"></a><span data-ttu-id="382a2-105">構文</span><span class="sxs-lookup"><span data-stu-id="382a2-105">Syntax</span></span>
------

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

<a name="parameters"></a><span data-ttu-id="382a2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="382a2-106">Parameters</span></span>
----------

<span data-ttu-id="382a2-107">*configurationNumber* \[in\]</span><span class="sxs-lookup"><span data-stu-id="382a2-107">*configurationNumber* \[in\]</span></span>  
<span data-ttu-id="382a2-108">要求された構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="382a2-108">Specifies the requested configuration.</span></span> 

## <a name="return-value"></a><span data-ttu-id="382a2-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="382a2-109">Return value</span></span>
------------

<span data-ttu-id="382a2-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="382a2-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="382a2-111">コメント</span><span class="sxs-lookup"><span data-stu-id="382a2-111">Remarks</span></span>

<span data-ttu-id="382a2-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="382a2-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="382a2-113">要件</span><span class="sxs-lookup"><span data-stu-id="382a2-113">Requirements</span></span>
------------
><span data-ttu-id="382a2-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="382a2-114">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="382a2-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="382a2-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="382a2-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="382a2-116">See also</span></span>


[<span data-ttu-id="382a2-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="382a2-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



