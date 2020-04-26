---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: RollBack メソッド
ms.openlocfilehash: 6452bdffd5160d9956576fb59c98e2f9ff7ddbbb
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71954939"
---
# <a name="rollback-method"></a><span data-ttu-id="a1d70-103">RollBack メソッド</span><span class="sxs-lookup"><span data-stu-id="a1d70-103">RollBack method</span></span>

<span data-ttu-id="a1d70-104">構成を以前のバージョンにロールバックします。</span><span class="sxs-lookup"><span data-stu-id="a1d70-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="a1d70-105">構文</span><span class="sxs-lookup"><span data-stu-id="a1d70-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="a1d70-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1d70-106">Parameters</span></span>

<span data-ttu-id="a1d70-107">*configurationNumber* \[in\] 要求された構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1d70-107">*configurationNumber* \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="a1d70-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="a1d70-108">Return value</span></span>

<span data-ttu-id="a1d70-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="a1d70-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1d70-110">解説</span><span class="sxs-lookup"><span data-stu-id="a1d70-110">Remarks</span></span>

<span data-ttu-id="a1d70-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="a1d70-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a1d70-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="a1d70-112">Requirements</span></span>

<span data-ttu-id="a1d70-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="a1d70-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="a1d70-114">**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="a1d70-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="a1d70-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1d70-115">See also</span></span>

[<span data-ttu-id="a1d70-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="a1d70-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
