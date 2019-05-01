---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの GetMetaConfiguration メソッド
ms.openlocfilehash: e14237ef68b95d68e2f14071aa1fa6ba0717f39f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078522"
---
# <a name="getmetaconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="aa2b4-103">MSFT_DSCLocalConfigurationManager クラスの GetMetaConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="aa2b4-103">GetMetaConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="aa2b4-104">構成エージェントを制御するために使用するローカル構成マネージャーの設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="aa2b4-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="aa2b4-105">構文</span><span class="sxs-lookup"><span data-stu-id="aa2b4-105">Syntax</span></span>

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

## <a name="parameters"></a><span data-ttu-id="aa2b4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aa2b4-106">Parameters</span></span>

<span data-ttu-id="aa2b4-107">*MetaConfiguration* \[out\] 制御が戻ったとき、設定を定義する **MSFT_DSCMetaConfiguration** クラスの埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="aa2b4-107">*MetaConfiguration* \[out\] On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="aa2b4-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="aa2b4-108">Return value</span></span>

<span data-ttu-id="aa2b4-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="aa2b4-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="aa2b4-110">コメント</span><span class="sxs-lookup"><span data-stu-id="aa2b4-110">Remarks</span></span>

<span data-ttu-id="aa2b4-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="aa2b4-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="aa2b4-112">要件</span><span class="sxs-lookup"><span data-stu-id="aa2b4-112">Requirements</span></span>

<span data-ttu-id="aa2b4-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="aa2b4-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="aa2b4-114">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="aa2b4-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="aa2b4-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa2b4-115">See also</span></span>

[<span data-ttu-id="aa2b4-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="aa2b4-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)