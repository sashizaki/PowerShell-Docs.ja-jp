---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの ResourceGet メソッド"
ms.openlocfilehash: df90cb6859413c94be992c8cbc30171e9bd3d6de
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="resourceget-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="8a08c-103">MSFT_DSCLocalConfigurationManager クラスの ResourceGet メソッド</span><span class="sxs-lookup"><span data-stu-id="8a08c-103">ResourceGet method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="8a08c-104">DSC リソースの **Get** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8a08c-104">Directly calls the **Get** method of a DSC resource.</span></span>

<a name="syntax"></a><span data-ttu-id="8a08c-105">構文</span><span class="sxs-lookup"><span data-stu-id="8a08c-105">Syntax</span></span>
------

```mof
uint32 ResourceGet(
  [in]  string           ResourceType,
  [in]  string           ModuleName,
  [in]  uint8            resourceProperty[],
  [out] OMI_BaseResource configurations
);
```

<a name="parameters"></a><span data-ttu-id="8a08c-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a08c-106">Parameters</span></span>
----------

<span data-ttu-id="8a08c-107">*ResourceType* \[in\]</span><span class="sxs-lookup"><span data-stu-id="8a08c-107">*ResourceType* \[in\]</span></span>  
<span data-ttu-id="8a08c-108">呼び出すリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="8a08c-108">The name of the resource to call.</span></span>

<span data-ttu-id="8a08c-109">*ModuleName* \[in\]</span><span class="sxs-lookup"><span data-stu-id="8a08c-109">*ModuleName* \[in\]</span></span>  
<span data-ttu-id="8a08c-110">呼び出すリソースを含むモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="8a08c-110">The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="8a08c-111">*resourceProperty* \[in\]</span><span class="sxs-lookup"><span data-stu-id="8a08c-111">*resourceProperty* \[in\]</span></span>  
<span data-ttu-id="8a08c-112">ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。</span><span class="sxs-lookup"><span data-stu-id="8a08c-112">Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="8a08c-113">リソースのプロパティと種類を検出するには、[Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8a08c-113">Use the [Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="8a08c-114">*configurations* \[out\]</span><span class="sxs-lookup"><span data-stu-id="8a08c-114">*configurations* \[out\]</span></span>  
<span data-ttu-id="8a08c-115">制御が戻ったとき、その構成の埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8a08c-115">On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="8a08c-116">戻り値</span><span class="sxs-lookup"><span data-stu-id="8a08c-116">Return value</span></span>
------------

<span data-ttu-id="8a08c-117">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="8a08c-117">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="8a08c-118">コメント</span><span class="sxs-lookup"><span data-stu-id="8a08c-118">Remarks</span></span>

<span data-ttu-id="8a08c-119">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="8a08c-119">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8a08c-120">要件</span><span class="sxs-lookup"><span data-stu-id="8a08c-120">Requirements</span></span>
------------
><span data-ttu-id="8a08c-121">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="8a08c-121">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="8a08c-122">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="8a08c-122">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="8a08c-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a08c-123">See also</span></span>


[<span data-ttu-id="8a08c-124">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="8a08c-124">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



