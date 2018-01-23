---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの TestConfiguration メソッド"
ms.openlocfilehash: 04f0f3146473dc71f492086449d9dce5467c55db
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="testconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="82eac-103">MSFT_DSCLocalConfigurationManager クラスの TestConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="82eac-103">TestConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="82eac-104">構成ドキュメントを管理ノードに送信し、そのドキュメントに対して現在の構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="82eac-104">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>

<a name="syntax"></a><span data-ttu-id="82eac-105">構文</span><span class="sxs-lookup"><span data-stu-id="82eac-105">Syntax</span></span>
------

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

<a name="parameters"></a><span data-ttu-id="82eac-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="82eac-106">Parameters</span></span>
----------

<span data-ttu-id="82eac-107">*configurationData* \[in\]</span><span class="sxs-lookup"><span data-stu-id="82eac-107">*configurationData* \[in\]</span></span>  
<span data-ttu-id="82eac-108">構成のための環境データ。</span><span class="sxs-lookup"><span data-stu-id="82eac-108">Environment data for the confuguration.</span></span>

<span data-ttu-id="82eac-109">*InDesiredState* \[out\]</span><span class="sxs-lookup"><span data-stu-id="82eac-109">*InDesiredState* \[out\]</span></span>  
<span data-ttu-id="82eac-110">制御が戻ったとき、管理ノードが構成ドキュメントで指定された状態であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="82eac-110">On return, specifies whether the managed node is in the state specified by the configuration document.</span></span>

<span data-ttu-id="82eac-111">*ResourcesInDesiredState* \[out\]</span><span class="sxs-lookup"><span data-stu-id="82eac-111">*ResourcesInDesiredState* \[out\]</span></span>  
<span data-ttu-id="82eac-112">制御が戻ったとき、目的の状態にあるリソースを指定する、**MSFT_ResourceInDesiredState** クラスの埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="82eac-112">On return, contains an embedded instance of the **MSFT_ResourceInDesiredState** class that specifies resources that are in the desired state.</span></span>

<span data-ttu-id="82eac-113">*ResourcesNotInDesiredState* \[out\]</span><span class="sxs-lookup"><span data-stu-id="82eac-113">*ResourcesNotInDesiredState* \[out\]</span></span>  
<span data-ttu-id="82eac-114">制御が戻ったとき、目的の状態ではないリソースを指定する、**MSFT_ResourceNotInDesiredState** クラスの埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="82eac-114">On return, contains an embedded instance of the **MSFT_ResourceNotInDesiredState** class that specifies resources that are not in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="82eac-115">戻り値</span><span class="sxs-lookup"><span data-stu-id="82eac-115">Return value</span></span>
------------

<span data-ttu-id="82eac-116">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="82eac-116">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="82eac-117">コメント</span><span class="sxs-lookup"><span data-stu-id="82eac-117">Remarks</span></span>

<span data-ttu-id="82eac-118">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="82eac-118">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="82eac-119">要件</span><span class="sxs-lookup"><span data-stu-id="82eac-119">Requirements</span></span>
------------
><span data-ttu-id="82eac-120">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="82eac-120">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="82eac-121">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="82eac-121">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="82eac-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="82eac-122">See also</span></span>


[<span data-ttu-id="82eac-123">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="82eac-123">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



