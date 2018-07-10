---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの GetConfigurationStatus メソッド
ms.openlocfilehash: c66ccc4eefaef2d0c3a68fa8a96c5abb9bda6e4c
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37893061"
---
# <a name="getconfigurationstatus-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="bee2b-103">MSFT_DSCLocalConfigurationManager クラスの GetConfigurationStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="bee2b-103">GetConfigurationStatus method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="bee2b-104">構成状態の履歴を取得します。</span><span class="sxs-lookup"><span data-stu-id="bee2b-104">Get the configuration status history.</span></span>

## <a name="syntax"></a><span data-ttu-id="bee2b-105">構文</span><span class="sxs-lookup"><span data-stu-id="bee2b-105">Syntax</span></span>

```mof
uint32 GetConfigurationStatus(
  [in]  boolean                     All,
  [out] MSFT_DSCConfigurationStatus configurationStatus[]
);
```

## <a name="parameters"></a><span data-ttu-id="bee2b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="bee2b-106">Parameters</span></span>

<span data-ttu-id="bee2b-107">*All* \[in\] **true** の場合、コンピューターで実行中のすべての構成 (構成の適用や整合性チェックも含む) についての情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="bee2b-107">*All* \[in\] **true** if this method should return information about all the configuration runs on the machine, including the configuration application and the consistency check.</span></span>

<span data-ttu-id="bee2b-108">*configurationStatus* \[out\] 制御が戻ったとき、設定を定義する **MSFT_DSCConfigurationStatus** クラスの埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bee2b-108">*configurationStatus* \[out\] On return, contains an embedded instance of the **MSFT_DSCConfigurationStatus** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="bee2b-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="bee2b-109">Return value</span></span>

<span data-ttu-id="bee2b-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="bee2b-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="bee2b-111">コメント</span><span class="sxs-lookup"><span data-stu-id="bee2b-111">Remarks</span></span>

<span data-ttu-id="bee2b-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="bee2b-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="bee2b-113">要件</span><span class="sxs-lookup"><span data-stu-id="bee2b-113">Requirements</span></span>

<span data-ttu-id="bee2b-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="bee2b-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="bee2b-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="bee2b-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="bee2b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="bee2b-116">See also</span></span>

[<span data-ttu-id="bee2b-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="bee2b-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)