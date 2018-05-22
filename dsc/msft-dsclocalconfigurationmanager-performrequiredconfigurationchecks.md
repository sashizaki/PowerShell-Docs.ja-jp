---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの PerformRequiredConfigurationChecks メソッド
ms.openlocfilehash: c3fdaa23875815b1cf5cbf0b6e21c633e00664aa
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="performrequiredconfigurationchecks-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="af106-103">MSFT_DSCLocalConfigurationManager クラスの PerformRequiredConfigurationChecks メソッド</span><span class="sxs-lookup"><span data-stu-id="af106-103">PerformRequiredConfigurationChecks method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="af106-104">タスク スケジューラを使用して、整合性チェックを開始します。</span><span class="sxs-lookup"><span data-stu-id="af106-104">Starts a consistency check by using the Task Scheduler.</span></span>

<a name="syntax"></a><span data-ttu-id="af106-105">構文</span><span class="sxs-lookup"><span data-stu-id="af106-105">Syntax</span></span>
------

```mof
uint32 PerformRequiredConfigurationChecks(
  [in] uint32 Flags
);
```

<a name="parameters"></a><span data-ttu-id="af106-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="af106-106">Parameters</span></span>
----------

<span data-ttu-id="af106-107">*Flags* \[in\] 実行する整合性チェックの種類を指定するビットマスク。</span><span class="sxs-lookup"><span data-stu-id="af106-107">*Flags* \[in\] A bitmask that specifies the type of consistency check to run.</span></span> <span data-ttu-id="af106-108">次の値が有効です。これらの値はビット単位の **OR** 演算で組み合わせることもできます。</span><span class="sxs-lookup"><span data-stu-id="af106-108">The following values are valid, and can be combined by using a bitwise **OR** operation:</span></span>

|<span data-ttu-id="af106-109">値</span><span class="sxs-lookup"><span data-stu-id="af106-109">Value</span></span> |<span data-ttu-id="af106-110">説明</span><span class="sxs-lookup"><span data-stu-id="af106-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="af106-111">**1**</span><span class="sxs-lookup"><span data-stu-id="af106-111">**1**</span></span> | <span data-ttu-id="af106-112">通常の整合性チェックです。</span><span class="sxs-lookup"><span data-stu-id="af106-112">A normal consistency check.</span></span> |
|<span data-ttu-id="af106-113">**2**</span><span class="sxs-lookup"><span data-stu-id="af106-113">**2**</span></span> | <span data-ttu-id="af106-114">再起動後に、整合性チェックを続行します。</span><span class="sxs-lookup"><span data-stu-id="af106-114">A continuation of a consistency check after a reboot.</span></span> <span data-ttu-id="af106-115">この値は、他の値と組み合わせないでください。</span><span class="sxs-lookup"><span data-stu-id="af106-115">This value should not be combined with other values.</span></span> |
|<span data-ttu-id="af106-116">**4**</span><span class="sxs-lookup"><span data-stu-id="af106-116">**4**</span></span> | <span data-ttu-id="af106-117">構成は、ノード用のメタ構成で指定されたプル サーバーからプルされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="af106-117">The configuration should be pulled from the pull server specified in the metaconfiguration for the node.</span></span> <span data-ttu-id="af106-118">値を **5** にするには、常に **1** と組み合わせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="af106-118">This value should always be combined with **1**, for a value of **5**.</span></span> |
|<span data-ttu-id="af106-119">**8**</span><span class="sxs-lookup"><span data-stu-id="af106-119">**8**</span></span> | <span data-ttu-id="af106-120">レポート サーバーにステータスを送信します。</span><span class="sxs-lookup"><span data-stu-id="af106-120">Send status to the report server.</span></span> |

## <a name="return-value"></a><span data-ttu-id="af106-121">戻り値</span><span class="sxs-lookup"><span data-stu-id="af106-121">Return value</span></span>
------------

<span data-ttu-id="af106-122">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="af106-122">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="af106-123">コメント</span><span class="sxs-lookup"><span data-stu-id="af106-123">Remarks</span></span>

<span data-ttu-id="af106-124">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="af106-124">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="af106-125">要件</span><span class="sxs-lookup"><span data-stu-id="af106-125">Requirements</span></span>
------------
><span data-ttu-id="af106-126">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="af106-126">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="af106-127">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="af106-127">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="af106-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="af106-128">See also</span></span>


[<span data-ttu-id="af106-129">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="af106-129">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)