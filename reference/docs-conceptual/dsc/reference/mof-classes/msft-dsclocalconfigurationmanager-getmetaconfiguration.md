---
ms.date: 07/17/2020
ms.topic: reference
title: GetMetaConfiguration メソッド
description: GetMetaConfiguration メソッド
ms.openlocfilehash: deca6b8ec342a34543bbe0e1fabbc2a740a88feb
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92644731"
---
# <a name="getmetaconfiguration-method"></a><span data-ttu-id="f2fb7-103">GetMetaConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="f2fb7-103">GetMetaConfiguration method</span></span>

<span data-ttu-id="f2fb7-104">構成エージェントを制御するために使用するローカル構成マネージャーの設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="f2fb7-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="f2fb7-105">構文</span><span class="sxs-lookup"><span data-stu-id="f2fb7-105">Syntax</span></span>

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

## <a name="parameters"></a><span data-ttu-id="f2fb7-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="f2fb7-106">Parameters</span></span>

<span data-ttu-id="f2fb7-107">**MetaConfiguration** \[out\] 制御が戻ったとき、設定を定義する **MSFT_DSCMetaConfiguration** クラスの埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2fb7-107">**MetaConfiguration** \[out\] On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="f2fb7-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="f2fb7-108">Return value</span></span>

<span data-ttu-id="f2fb7-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="f2fb7-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="f2fb7-110">解説</span><span class="sxs-lookup"><span data-stu-id="f2fb7-110">Remarks</span></span>

<span data-ttu-id="f2fb7-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="f2fb7-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="f2fb7-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="f2fb7-112">Requirements</span></span>

<span data-ttu-id="f2fb7-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="f2fb7-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="f2fb7-114">**名前空間** :Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="f2fb7-114">**Namespace** : Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="f2fb7-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2fb7-115">See also</span></span>

[<span data-ttu-id="f2fb7-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="f2fb7-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
