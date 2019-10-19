---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: RemoveConfiguration メソッド
ms.openlocfilehash: aacbed96beb960d7e0d449423a4de9a27f0a287e
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953399"
---
# <a name="removeconfiguration-method"></a><span data-ttu-id="da896-103">RemoveConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="da896-103">RemoveConfiguration method</span></span>

<span data-ttu-id="da896-104">構成ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="da896-104">Removes the configuration files.</span></span>

## <a name="syntax"></a><span data-ttu-id="da896-105">構文</span><span class="sxs-lookup"><span data-stu-id="da896-105">Syntax</span></span>

```mof
uint32 RemoveConfiguration(
  [in] uint32  Stage,
  [in] boolean Force
);
```

## <a name="parameters"></a><span data-ttu-id="da896-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="da896-106">Parameters</span></span>

<span data-ttu-id="da896-107">*Stage* \[in\] 削除する構成ドキュメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="da896-107">*Stage* \[in\] Specifies which configuration document to remove.</span></span> <span data-ttu-id="da896-108">次の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="da896-108">The following values are valid:</span></span>

|<span data-ttu-id="da896-109">値</span><span class="sxs-lookup"><span data-stu-id="da896-109">Value</span></span> |<span data-ttu-id="da896-110">説明</span><span class="sxs-lookup"><span data-stu-id="da896-110">Description</span></span> |
|:--- |:---|
|<span data-ttu-id="da896-111">**1**</span><span class="sxs-lookup"><span data-stu-id="da896-111">**1**</span></span> | <span data-ttu-id="da896-112">**現在**の構成ドキュメント (current.mof)。</span><span class="sxs-lookup"><span data-stu-id="da896-112">The **Current** configuration document (current.mof).</span></span> |
|<span data-ttu-id="da896-113">**2**</span><span class="sxs-lookup"><span data-stu-id="da896-113">**2**</span></span> | <span data-ttu-id="da896-114">**保留中**の構成ドキュメント (pending.mof)。</span><span class="sxs-lookup"><span data-stu-id="da896-114">The **Pending** configuration document (pending.mof).</span></span>  |
|<span data-ttu-id="da896-115">**4**</span><span class="sxs-lookup"><span data-stu-id="da896-115">**4**</span></span> | <span data-ttu-id="da896-116">**以前**の構成ドキュメント (previous.mof)。</span><span class="sxs-lookup"><span data-stu-id="da896-116">The **Previous** configuration document (previous.mof).</span></span> |

<span data-ttu-id="da896-117">*Force* \[in\] **true** の場合、構成を強制的に削除します。</span><span class="sxs-lookup"><span data-stu-id="da896-117">*Force* \[in\] **true** to force the removal of the configuration.</span></span>

## <a name="return-value"></a><span data-ttu-id="da896-118">戻り値</span><span class="sxs-lookup"><span data-stu-id="da896-118">Return value</span></span>

<span data-ttu-id="da896-119">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="da896-119">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="da896-120">コメント</span><span class="sxs-lookup"><span data-stu-id="da896-120">Remarks</span></span>

<span data-ttu-id="da896-121">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="da896-121">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="da896-122">要件</span><span class="sxs-lookup"><span data-stu-id="da896-122">Requirements</span></span>

<span data-ttu-id="da896-123">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="da896-123">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="da896-124">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="da896-124">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="da896-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="da896-125">See also</span></span>

[<span data-ttu-id="da896-126">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="da896-126">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)