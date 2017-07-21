---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの PerformRequiredConfigurationChecks メソッド"
ms.openlocfilehash: 26110b3920104da7343b8d55cf63440c12accbbc
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="performrequiredconfigurationchecks-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="b78b5-103">MSFT_DSCLocalConfigurationManager クラスの PerformRequiredConfigurationChecks メソッド</span><span class="sxs-lookup"><span data-stu-id="b78b5-103">PerformRequiredConfigurationChecks method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="b78b5-104">タスク スケジューラを使用して、整合性チェックを開始します。</span><span class="sxs-lookup"><span data-stu-id="b78b5-104">Starts a consistency check by using the Task Scheduler.</span></span>

<a name="syntax"></a><span data-ttu-id="b78b5-105">構文</span><span class="sxs-lookup"><span data-stu-id="b78b5-105">Syntax</span></span>
------

```mof
uint32 PerformRequiredConfigurationChecks(
  [in] uint32 Flags
);
```

<a name="parameters"></a><span data-ttu-id="b78b5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b78b5-106">Parameters</span></span>
----------

<span data-ttu-id="b78b5-107">*Flags* \[in\]</span><span class="sxs-lookup"><span data-stu-id="b78b5-107">*Flags* \[in\]</span></span>  
<span data-ttu-id="b78b5-108">実行する整合性チェックの種類を指定するビットマスク。</span><span class="sxs-lookup"><span data-stu-id="b78b5-108">A bitmask that specifies the type of consistency check to run.</span></span> <span data-ttu-id="b78b5-109">次の値が有効です。これらの値はビット単位の **OR** 演算で組み合わせることもできます。</span><span class="sxs-lookup"><span data-stu-id="b78b5-109">The following values are valid, and can be combined by using a bitwise **OR** operation:</span></span>

|<span data-ttu-id="b78b5-110">値</span><span class="sxs-lookup"><span data-stu-id="b78b5-110">Value</span></span> |<span data-ttu-id="b78b5-111">説明</span><span class="sxs-lookup"><span data-stu-id="b78b5-111">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="b78b5-112">**1**</span><span class="sxs-lookup"><span data-stu-id="b78b5-112">**1**</span></span> | <span data-ttu-id="b78b5-113">通常の整合性チェックです。</span><span class="sxs-lookup"><span data-stu-id="b78b5-113">A normal consistency check.</span></span> |
|<span data-ttu-id="b78b5-114">**2**</span><span class="sxs-lookup"><span data-stu-id="b78b5-114">**2**</span></span> | <span data-ttu-id="b78b5-115">再起動後に、整合性チェックを続行します。</span><span class="sxs-lookup"><span data-stu-id="b78b5-115">A continuation of a consistency check after a reboot.</span></span> <span data-ttu-id="b78b5-116">この値は、他の値と組み合わせないでください。</span><span class="sxs-lookup"><span data-stu-id="b78b5-116">This value should not be combined with other values.</span></span> |
|<span data-ttu-id="b78b5-117">**4**</span><span class="sxs-lookup"><span data-stu-id="b78b5-117">**4**</span></span> | <span data-ttu-id="b78b5-118">構成は、ノード用のメタ構成で指定されたプル サーバーからプルされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b78b5-118">The configuration should be pulled from the pull server specified in the metaconfiguration for the node.</span></span> <span data-ttu-id="b78b5-119">値を **5** にするには、常に **1** と組み合わせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b78b5-119">This value should always be combined with **1**, for a value of **5**.</span></span> |
|<span data-ttu-id="b78b5-120">**8**</span><span class="sxs-lookup"><span data-stu-id="b78b5-120">**8**</span></span> | <span data-ttu-id="b78b5-121">レポート サーバーにステータスを送信します。</span><span class="sxs-lookup"><span data-stu-id="b78b5-121">Send status to the report server.</span></span> |

## <a name="return-value"></a><span data-ttu-id="b78b5-122">戻り値</span><span class="sxs-lookup"><span data-stu-id="b78b5-122">Return value</span></span>
------------

<span data-ttu-id="b78b5-123">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="b78b5-123">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b78b5-124">コメント</span><span class="sxs-lookup"><span data-stu-id="b78b5-124">Remarks</span></span>

<span data-ttu-id="b78b5-125">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="b78b5-125">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b78b5-126">要件</span><span class="sxs-lookup"><span data-stu-id="b78b5-126">Requirements</span></span>
------------
><span data-ttu-id="b78b5-127">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="b78b5-127">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="b78b5-128">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="b78b5-128">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="b78b5-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="b78b5-129">See also</span></span>


[<span data-ttu-id="b78b5-130">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="b78b5-130">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



