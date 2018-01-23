---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの ResourceSet メソッド"
ms.openlocfilehash: 7291641098578226449f8cbd360da0a3f9842598
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="resourceset-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="805f2-103">MSFT_DSCLocalConfigurationManager クラスの ResourceSet メソッド</span><span class="sxs-lookup"><span data-stu-id="805f2-103">ResourceSet method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="805f2-104">DSC リソースの **Set** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="805f2-104">Directly calls the **Set** method of a DSC resource.</span></span>

<a name="syntax"></a><span data-ttu-id="805f2-105">構文</span><span class="sxs-lookup"><span data-stu-id="805f2-105">Syntax</span></span>
------

```mof
uint32 ResourceSet(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean RebootRequired
);
```

<a name="parameters"></a><span data-ttu-id="805f2-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="805f2-106">Parameters</span></span>
----------

<span data-ttu-id="805f2-107">*ResourceType* \[in\]</span><span class="sxs-lookup"><span data-stu-id="805f2-107">*ResourceType* \[in\]</span></span>  
<span data-ttu-id="805f2-108">呼び出すリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="805f2-108">The name of the resource to call.</span></span>

<span data-ttu-id="805f2-109">*ModuleName* \[in\]</span><span class="sxs-lookup"><span data-stu-id="805f2-109">*ModuleName* \[in\]</span></span>  
<span data-ttu-id="805f2-110">呼び出すリソースを含むモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="805f2-110">The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="805f2-111">*resourceProperty* \[in\]</span><span class="sxs-lookup"><span data-stu-id="805f2-111">*resourceProperty* \[in\]</span></span>  
<span data-ttu-id="805f2-112">ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。</span><span class="sxs-lookup"><span data-stu-id="805f2-112">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="805f2-113">リソースのプロパティと種類を検出するには、[Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="805f2-113">Use the [Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="805f2-114">*RebootRequired* \[out\]</span><span class="sxs-lookup"><span data-stu-id="805f2-114">*RebootRequired* \[out\]</span></span>  
<span data-ttu-id="805f2-115">ターゲット ノードの再起動が必要な場合、制御が戻るときに、このプロパティは **true** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="805f2-115">On return, this property is set to **true** if the target node needs to be rebooted.</span></span>

## <a name="return-value"></a><span data-ttu-id="805f2-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="805f2-116">Return value</span></span>
------------

<span data-ttu-id="805f2-117">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="805f2-117">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="805f2-118">コメント</span><span class="sxs-lookup"><span data-stu-id="805f2-118">Remarks</span></span>

<span data-ttu-id="805f2-119">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="805f2-119">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="805f2-120">要件</span><span class="sxs-lookup"><span data-stu-id="805f2-120">Requirements</span></span>
------------
><span data-ttu-id="805f2-121">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="805f2-121">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="805f2-122">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="805f2-122">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="805f2-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="805f2-123">See also</span></span>


[<span data-ttu-id="805f2-124">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="805f2-124">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)

 

 



