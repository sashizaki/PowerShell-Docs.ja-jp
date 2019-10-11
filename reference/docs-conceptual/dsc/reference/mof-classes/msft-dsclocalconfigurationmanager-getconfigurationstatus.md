---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: GetConfigurationStatus メソッド
ms.openlocfilehash: 83b30ba2612d962fcf2fa658d07d18fb2d91ccc7
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71955019"
---
# <a name="getconfigurationstatus-method"></a><span data-ttu-id="30a5f-103">GetConfigurationStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="30a5f-103">GetConfigurationStatus method</span></span>

<span data-ttu-id="30a5f-104">構成状態の履歴を取得します。</span><span class="sxs-lookup"><span data-stu-id="30a5f-104">Get the configuration status history.</span></span>

## <a name="syntax"></a><span data-ttu-id="30a5f-105">構文</span><span class="sxs-lookup"><span data-stu-id="30a5f-105">Syntax</span></span>

```mof
uint32 GetConfigurationStatus(
  [in]  boolean                     All,
  [out] MSFT_DSCConfigurationStatus configurationStatus[]
);
```

## <a name="parameters"></a><span data-ttu-id="30a5f-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="30a5f-106">Parameters</span></span>

<span data-ttu-id="30a5f-107">*All* \[in\] **true** の場合、コンピューターで実行中のすべての構成 (構成の適用や整合性チェックも含む) についての情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="30a5f-107">*All* \[in\] **true** if this method should return information about all the configuration runs on the machine, including the configuration application and the consistency check.</span></span>

<span data-ttu-id="30a5f-108">*configurationStatus* \[out\] 制御が戻ったとき、設定を定義する **MSFT_DSCConfigurationStatus** クラスの埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="30a5f-108">*configurationStatus* \[out\] On return, contains an embedded instance of the **MSFT_DSCConfigurationStatus** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="30a5f-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="30a5f-109">Return value</span></span>

<span data-ttu-id="30a5f-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="30a5f-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="30a5f-111">コメント</span><span class="sxs-lookup"><span data-stu-id="30a5f-111">Remarks</span></span>

<span data-ttu-id="30a5f-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="30a5f-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="30a5f-113">要件</span><span class="sxs-lookup"><span data-stu-id="30a5f-113">Requirements</span></span>

<span data-ttu-id="30a5f-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="30a5f-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="30a5f-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="30a5f-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="30a5f-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="30a5f-116">See also</span></span>

[<span data-ttu-id="30a5f-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="30a5f-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
