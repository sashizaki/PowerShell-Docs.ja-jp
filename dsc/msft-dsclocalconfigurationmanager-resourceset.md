---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの ResourceSet メソッド"
ms.openlocfilehash: 9cd9c1b3f58a5862db6c4eea0488423b8dfe7310
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="resourceset-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="bb2dd-103">MSFT_DSCLocalConfigurationManager クラスの ResourceSet メソッド</span><span class="sxs-lookup"><span data-stu-id="bb2dd-103">ResourceSet method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="bb2dd-104">DSC リソースの **Set** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="bb2dd-104">Directly calls the **Set** method of a DSC resource.</span></span>

<a name="syntax"></a><span data-ttu-id="bb2dd-105">構文</span><span class="sxs-lookup"><span data-stu-id="bb2dd-105">Syntax</span></span>
------

```mof
uint32 ResourceSet(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean RebootRequired
);
```

<a name="parameters"></a><span data-ttu-id="bb2dd-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bb2dd-106">Parameters</span></span>
----------

<span data-ttu-id="bb2dd-107">*ResourceType* \[in\]</span><span class="sxs-lookup"><span data-stu-id="bb2dd-107">*ResourceType* \[in\]</span></span>  
<span data-ttu-id="bb2dd-108">呼び出すリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="bb2dd-108">The name of the resource to call.</span></span>

<span data-ttu-id="bb2dd-109">*ModuleName* \[in\]</span><span class="sxs-lookup"><span data-stu-id="bb2dd-109">*ModuleName* \[in\]</span></span>  
<span data-ttu-id="bb2dd-110">呼び出すリソースを含むモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="bb2dd-110">The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="bb2dd-111">*resourceProperty* \[in\]</span><span class="sxs-lookup"><span data-stu-id="bb2dd-111">*resourceProperty* \[in\]</span></span>  
<span data-ttu-id="bb2dd-112">ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。</span><span class="sxs-lookup"><span data-stu-id="bb2dd-112">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="bb2dd-113">リソースのプロパティと種類を検出するには、[Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb2dd-113">Use the [Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="bb2dd-114">*RebootRequired* \[out\]</span><span class="sxs-lookup"><span data-stu-id="bb2dd-114">*RebootRequired* \[out\]</span></span>  
<span data-ttu-id="bb2dd-115">ターゲット ノードの再起動が必要な場合、制御が戻るときに、このプロパティは **true** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="bb2dd-115">On return, this property is set to **true** if the target node needs to be rebooted.</span></span>

## <a name="return-value"></a><span data-ttu-id="bb2dd-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="bb2dd-116">Return value</span></span>
------------

<span data-ttu-id="bb2dd-117">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="bb2dd-117">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="bb2dd-118">コメント</span><span class="sxs-lookup"><span data-stu-id="bb2dd-118">Remarks</span></span>

<span data-ttu-id="bb2dd-119">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="bb2dd-119">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="bb2dd-120">要件</span><span class="sxs-lookup"><span data-stu-id="bb2dd-120">Requirements</span></span>
------------
><span data-ttu-id="bb2dd-121">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="bb2dd-121">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="bb2dd-122">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="bb2dd-122">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="bb2dd-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb2dd-123">See also</span></span>


[<span data-ttu-id="bb2dd-124">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="bb2dd-124">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)

 

 



