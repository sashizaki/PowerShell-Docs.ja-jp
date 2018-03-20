---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの ResourceTest メソッド"
ms.openlocfilehash: 799b1cd91dfacf25c0e5e734ca96d20a776103f0
ms.sourcegitcommit: 99227f62dcf827354770eb2c3e95c5cf6a3118b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="resourcetest-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="345f3-103">MSFT_DSCLocalConfigurationManager クラスの ResourceTest メソッド</span><span class="sxs-lookup"><span data-stu-id="345f3-103">ResourceTest method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="345f3-104">DSC リソースの **Test** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="345f3-104">Directly calls the **Test** method of a DSC resource.</span></span>

<a name="syntax"></a><span data-ttu-id="345f3-105">構文</span><span class="sxs-lookup"><span data-stu-id="345f3-105">Syntax</span></span>
------

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

<a name="parameters"></a><span data-ttu-id="345f3-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="345f3-106">Parameters</span></span>
----------

<span data-ttu-id="345f3-107">*ResourceType* \[in\]</span><span class="sxs-lookup"><span data-stu-id="345f3-107">*ResourceType* \[in\]</span></span>  
<span data-ttu-id="345f3-108">呼び出すリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="345f3-108">The name of the resource to call.</span></span>

<span data-ttu-id="345f3-109">*ModuleName* \[in\]</span><span class="sxs-lookup"><span data-stu-id="345f3-109">*ModuleName* \[in\]</span></span>  
<span data-ttu-id="345f3-110">呼び出すリソースを含むモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="345f3-110">The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="345f3-111">*resourceProperty* \[in\]</span><span class="sxs-lookup"><span data-stu-id="345f3-111">*resourceProperty* \[in\]</span></span>  
<span data-ttu-id="345f3-112">ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。</span><span class="sxs-lookup"><span data-stu-id="345f3-112">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="345f3-113">リソースのプロパティと種類を検出するには、[Get-DscResource](https://technet.microsoft.com/library/dn521625.aspx) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="345f3-113">Use the [Get-DscResource](https://technet.microsoft.com/library/dn521625.aspx) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="345f3-114">*InDesiredState* \[out\]</span><span class="sxs-lookup"><span data-stu-id="345f3-114">*InDesiredState* \[out\]</span></span>  
<span data-ttu-id="345f3-115">ターゲット ノードが目的の状態にある場合、制御が戻るときに、このプロパティは **true** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="345f3-115">On return, this property is set to **true** if the target node is in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="345f3-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="345f3-116">Return value</span></span>
------------

<span data-ttu-id="345f3-117">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="345f3-117">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="345f3-118">コメント</span><span class="sxs-lookup"><span data-stu-id="345f3-118">Remarks</span></span>

<span data-ttu-id="345f3-119">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="345f3-119">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="345f3-120">要件</span><span class="sxs-lookup"><span data-stu-id="345f3-120">Requirements</span></span>
------------
><span data-ttu-id="345f3-121">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="345f3-121">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="345f3-122">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="345f3-122">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="345f3-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="345f3-123">See also</span></span>


[<span data-ttu-id="345f3-124">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="345f3-124">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



