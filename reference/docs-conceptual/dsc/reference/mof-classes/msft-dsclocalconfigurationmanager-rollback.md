---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: RollBack メソッド
ms.openlocfilehash: 6452bdffd5160d9956576fb59c98e2f9ff7ddbbb
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954939"
---
# <a name="rollback-method"></a><span data-ttu-id="ff61f-103">RollBack メソッド</span><span class="sxs-lookup"><span data-stu-id="ff61f-103">RollBack method</span></span>

<span data-ttu-id="ff61f-104">構成を以前のバージョンにロールバックします。</span><span class="sxs-lookup"><span data-stu-id="ff61f-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="ff61f-105">構文</span><span class="sxs-lookup"><span data-stu-id="ff61f-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="ff61f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ff61f-106">Parameters</span></span>

<span data-ttu-id="ff61f-107">*configurationNumber* \[in\] 要求された構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff61f-107">*configurationNumber* \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="ff61f-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="ff61f-108">Return value</span></span>

<span data-ttu-id="ff61f-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="ff61f-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff61f-110">コメント</span><span class="sxs-lookup"><span data-stu-id="ff61f-110">Remarks</span></span>

<span data-ttu-id="ff61f-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="ff61f-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ff61f-112">要件</span><span class="sxs-lookup"><span data-stu-id="ff61f-112">Requirements</span></span>

<span data-ttu-id="ff61f-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="ff61f-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="ff61f-114">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="ff61f-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="ff61f-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="ff61f-115">See also</span></span>

[<span data-ttu-id="ff61f-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="ff61f-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
