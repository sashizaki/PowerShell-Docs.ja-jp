---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの GetConfigurationStatus メソッド
ms.openlocfilehash: c66ccc4eefaef2d0c3a68fa8a96c5abb9bda6e4c
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047742"
---
# <a name="getconfigurationstatus-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="b024d-103">MSFT_DSCLocalConfigurationManager クラスの GetConfigurationStatus メソッド</span><span class="sxs-lookup"><span data-stu-id="b024d-103">GetConfigurationStatus method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="b024d-104">構成状態の履歴を取得します。</span><span class="sxs-lookup"><span data-stu-id="b024d-104">Get the configuration status history.</span></span>

## <a name="syntax"></a><span data-ttu-id="b024d-105">構文</span><span class="sxs-lookup"><span data-stu-id="b024d-105">Syntax</span></span>

```mof
uint32 GetConfigurationStatus(
  [in]  boolean                     All,
  [out] MSFT_DSCConfigurationStatus configurationStatus[]
);
```

## <a name="parameters"></a><span data-ttu-id="b024d-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b024d-106">Parameters</span></span>

<span data-ttu-id="b024d-107">*All* \[in\] **true** の場合、コンピューターで実行中のすべての構成 (構成の適用や整合性チェックも含む) についての情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="b024d-107">*All* \[in\] **true** if this method should return information about all the configuration runs on the machine, including the configuration application and the consistency check.</span></span>

<span data-ttu-id="b024d-108">*configurationStatus* \[out\] 制御が戻ったとき、設定を定義する **MSFT_DSCConfigurationStatus** クラスの埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b024d-108">*configurationStatus* \[out\] On return, contains an embedded instance of the **MSFT_DSCConfigurationStatus** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="b024d-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="b024d-109">Return value</span></span>

<span data-ttu-id="b024d-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="b024d-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b024d-111">コメント</span><span class="sxs-lookup"><span data-stu-id="b024d-111">Remarks</span></span>

<span data-ttu-id="b024d-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="b024d-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b024d-113">要件</span><span class="sxs-lookup"><span data-stu-id="b024d-113">Requirements</span></span>

<span data-ttu-id="b024d-114">MOF\*\*DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="b024d-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="b024d-115">\*\*［名前空間］:Root \microsoft\windows\desiredstateconfiguration</span><span class="sxs-lookup"><span data-stu-id="b024d-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="b024d-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b024d-116">See also</span></span>

[<span data-ttu-id="b024d-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="b024d-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)