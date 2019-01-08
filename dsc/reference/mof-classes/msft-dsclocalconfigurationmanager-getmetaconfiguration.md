---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの GetMetaConfiguration メソッド
ms.openlocfilehash: e14237ef68b95d68e2f14071aa1fa6ba0717f39f
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047808"
---
# <a name="getmetaconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="c7799-103">MSFT_DSCLocalConfigurationManager クラスの GetMetaConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="c7799-103">GetMetaConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="c7799-104">構成エージェントを制御するために使用するローカル構成マネージャーの設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="c7799-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="c7799-105">構文</span><span class="sxs-lookup"><span data-stu-id="c7799-105">Syntax</span></span>

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

## <a name="parameters"></a><span data-ttu-id="c7799-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c7799-106">Parameters</span></span>

<span data-ttu-id="c7799-107">*MetaConfiguration* \[out\] 制御が戻ったとき、設定を定義する **MSFT_DSCMetaConfiguration** クラスの埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c7799-107">*MetaConfiguration* \[out\] On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="c7799-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="c7799-108">Return value</span></span>

<span data-ttu-id="c7799-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="c7799-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="c7799-110">コメント</span><span class="sxs-lookup"><span data-stu-id="c7799-110">Remarks</span></span>

<span data-ttu-id="c7799-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="c7799-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c7799-112">要件</span><span class="sxs-lookup"><span data-stu-id="c7799-112">Requirements</span></span>

<span data-ttu-id="c7799-113">MOF\*\*DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="c7799-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="c7799-114">\*\*［名前空間］:Root \microsoft\windows\desiredstateconfiguration</span><span class="sxs-lookup"><span data-stu-id="c7799-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="c7799-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7799-115">See also</span></span>

[<span data-ttu-id="c7799-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="c7799-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)