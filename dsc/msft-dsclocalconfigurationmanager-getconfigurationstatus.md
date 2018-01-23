---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの GetConfigurationStatus メソッド"
ms.openlocfilehash: a41e7a15fc935c2cd5fd4cb66d0ab13509d5d4e0
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="getconfigurationstatus-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="3636d-103">MSFT_DSCLocalConfigurationManager クラスの GetConfigurationStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="3636d-103">GetConfigurationStatus method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="3636d-104">構成状態の履歴を取得します。</span><span class="sxs-lookup"><span data-stu-id="3636d-104">Get the configuration status history.</span></span>

<a name="syntax"></a><span data-ttu-id="3636d-105">構文</span><span class="sxs-lookup"><span data-stu-id="3636d-105">Syntax</span></span>
------

```mof
uint32 GetConfigurationStatus(
  [in]  boolean                     All,
  [out] MSFT_DSCConfigurationStatus configurationStatus[]
);
```

<a name="parameters"></a><span data-ttu-id="3636d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3636d-106">Parameters</span></span>
----------

<span data-ttu-id="3636d-107">*All* \[in\]</span><span class="sxs-lookup"><span data-stu-id="3636d-107">*All* \[in\]</span></span>  
<span data-ttu-id="3636d-108">**true** の場合、コンピューターで実行中のすべての構成 (構成の適用や整合性チェックも含む) についての情報が返されます</span><span class="sxs-lookup"><span data-stu-id="3636d-108">**true** if this method should return information about all the configuration runs on the machine, including the configuration application and the consistency check.</span></span>

<span data-ttu-id="3636d-109">*configurationStatus* \[out\]</span><span class="sxs-lookup"><span data-stu-id="3636d-109">*configurationStatus* \[out\]</span></span>  
<span data-ttu-id="3636d-110">制御が戻ったとき、設定を定義する **MSFT_DSCConfigurationStatus** クラスの埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3636d-110">On return, contains an embedded instance of the **MSFT_DSCConfigurationStatus** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="3636d-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="3636d-111">Return value</span></span>
------------

<span data-ttu-id="3636d-112">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="3636d-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="3636d-113">コメント</span><span class="sxs-lookup"><span data-stu-id="3636d-113">Remarks</span></span>

<span data-ttu-id="3636d-114">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="3636d-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3636d-115">要件</span><span class="sxs-lookup"><span data-stu-id="3636d-115">Requirements</span></span>
------------
><span data-ttu-id="3636d-116">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="3636d-116">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="3636d-117">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="3636d-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="3636d-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="3636d-118">See also</span></span>


[<span data-ttu-id="3636d-119">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="3636d-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



