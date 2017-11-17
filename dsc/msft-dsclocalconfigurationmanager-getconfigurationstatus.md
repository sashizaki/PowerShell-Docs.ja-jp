---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの GetConfigurationStatus メソッド"
ms.openlocfilehash: e02ed81a7b8436323bc68aaa2587a445e6a5adf9
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="getconfigurationstatus-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="da810-103">MSFT_DSCLocalConfigurationManager クラスの GetConfigurationStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="da810-103">GetConfigurationStatus method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="da810-104">構成状態の履歴を取得します。</span><span class="sxs-lookup"><span data-stu-id="da810-104">Get the configuration status history.</span></span>

<a name="syntax"></a><span data-ttu-id="da810-105">構文</span><span class="sxs-lookup"><span data-stu-id="da810-105">Syntax</span></span>
------

```mof
uint32 GetConfigurationStatus(
  [in]  boolean                     All,
  [out] MSFT_DSCConfigurationStatus configurationStatus[]
);
```

<a name="parameters"></a><span data-ttu-id="da810-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da810-106">Parameters</span></span>
----------

<span data-ttu-id="da810-107">*All* \[in\]</span><span class="sxs-lookup"><span data-stu-id="da810-107">*All* \[in\]</span></span>  
<span data-ttu-id="da810-108">**true** の場合、コンピューターで実行中のすべての構成 (構成の適用や整合性チェックも含む) についての情報が返されます</span><span class="sxs-lookup"><span data-stu-id="da810-108">**true** if this method should return information about all the configuration runs on the machine, including the configuration application and the consistency check.</span></span>

<span data-ttu-id="da810-109">*configurationStatus* \[out\]</span><span class="sxs-lookup"><span data-stu-id="da810-109">*configurationStatus* \[out\]</span></span>  
<span data-ttu-id="da810-110">制御が戻ったとき、設定を定義する **MSFT_DSCConfigurationStatus** クラスの埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="da810-110">On return, contains an embedded instance of the **MSFT_DSCConfigurationStatus** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="da810-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="da810-111">Return value</span></span>
------------

<span data-ttu-id="da810-112">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="da810-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="da810-113">コメント</span><span class="sxs-lookup"><span data-stu-id="da810-113">Remarks</span></span>

<span data-ttu-id="da810-114">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="da810-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="da810-115">要件</span><span class="sxs-lookup"><span data-stu-id="da810-115">Requirements</span></span>
------------
><span data-ttu-id="da810-116">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="da810-116">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="da810-117">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="da810-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="da810-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="da810-118">See also</span></span>


[<span data-ttu-id="da810-119">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="da810-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



