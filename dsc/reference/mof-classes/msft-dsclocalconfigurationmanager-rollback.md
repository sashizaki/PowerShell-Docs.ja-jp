---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの RollBack メソッド
ms.openlocfilehash: 4956900ecd2c9cb7f2e2b5bcab94616f9f5d5565
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078369"
---
# <a name="rollback-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="9a5d4-103">MSFT_DSCLocalConfigurationManager クラスの RollBack メソッド</span><span class="sxs-lookup"><span data-stu-id="9a5d4-103">RollBack method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="9a5d4-104">構成を以前のバージョンにロールバックします。</span><span class="sxs-lookup"><span data-stu-id="9a5d4-104">Rolls back the configuration to a previous version.</span></span>

## <a name="syntax"></a><span data-ttu-id="9a5d4-105">構文</span><span class="sxs-lookup"><span data-stu-id="9a5d4-105">Syntax</span></span>

```mof
uint32 RollBack(
  [in] uint8 configurationNumber
);
```

## <a name="parameters"></a><span data-ttu-id="9a5d4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="9a5d4-106">Parameters</span></span>

<span data-ttu-id="9a5d4-107">*configurationNumber* \[in\] 要求された構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="9a5d4-107">*configurationNumber* \[in\] Specifies the requested configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="9a5d4-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="9a5d4-108">Return value</span></span>

<span data-ttu-id="9a5d4-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="9a5d4-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="9a5d4-110">コメント</span><span class="sxs-lookup"><span data-stu-id="9a5d4-110">Remarks</span></span>

<span data-ttu-id="9a5d4-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="9a5d4-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="9a5d4-112">要件</span><span class="sxs-lookup"><span data-stu-id="9a5d4-112">Requirements</span></span>

<span data-ttu-id="9a5d4-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="9a5d4-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="9a5d4-114">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="9a5d4-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="9a5d4-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="9a5d4-115">See also</span></span>

[<span data-ttu-id="9a5d4-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="9a5d4-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)