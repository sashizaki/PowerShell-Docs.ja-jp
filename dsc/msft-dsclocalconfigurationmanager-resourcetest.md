---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの ResourceTest メソッド"
ms.openlocfilehash: 3c88f74c5f623502e8cbe0d7aa7390fca75569a9
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="resourcetest-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="a9705-103">MSFT_DSCLocalConfigurationManager クラスの ResourceTest メソッド</span><span class="sxs-lookup"><span data-stu-id="a9705-103">ResourceTest method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="a9705-104">DSC リソースの **Test** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a9705-104">Directly calls the **Test** method of a DSC resource.</span></span>

<a name="syntax"></a><span data-ttu-id="a9705-105">構文</span><span class="sxs-lookup"><span data-stu-id="a9705-105">Syntax</span></span>
------

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

<a name="parameters"></a><span data-ttu-id="a9705-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a9705-106">Parameters</span></span>
----------

<span data-ttu-id="a9705-107">*ResourceType* \[in\]</span><span class="sxs-lookup"><span data-stu-id="a9705-107">*ResourceType* \[in\]</span></span>  
<span data-ttu-id="a9705-108">呼び出すリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="a9705-108">The name of the resource to call.</span></span>

<span data-ttu-id="a9705-109">*ModuleName* \[in\]</span><span class="sxs-lookup"><span data-stu-id="a9705-109">*ModuleName* \[in\]</span></span>  
<span data-ttu-id="a9705-110">呼び出すリソースを含むモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="a9705-110">The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="a9705-111">*resourceProperty* \[in\]</span><span class="sxs-lookup"><span data-stu-id="a9705-111">*resourceProperty* \[in\]</span></span>  
<span data-ttu-id="a9705-112">ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。</span><span class="sxs-lookup"><span data-stu-id="a9705-112">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="a9705-113">リソースのプロパティと種類を検出するには、[Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9705-113">Use the [Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="a9705-114">*InDesiredState* \[out\]</span><span class="sxs-lookup"><span data-stu-id="a9705-114">*InDesiredState* \[out\]</span></span>  
<span data-ttu-id="a9705-115">ターゲット ノードが目的の状態にある場合、制御が戻るときに、このプロパティは **true** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a9705-115">On return, this property is set to **true** if the target node is in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="a9705-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="a9705-116">Return value</span></span>
------------

<span data-ttu-id="a9705-117">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="a9705-117">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a9705-118">コメント</span><span class="sxs-lookup"><span data-stu-id="a9705-118">Remarks</span></span>

<span data-ttu-id="a9705-119">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="a9705-119">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a9705-120">要件</span><span class="sxs-lookup"><span data-stu-id="a9705-120">Requirements</span></span>
------------
><span data-ttu-id="a9705-121">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="a9705-121">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="a9705-122">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="a9705-122">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="a9705-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9705-123">See also</span></span>


[<span data-ttu-id="a9705-124">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="a9705-124">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



