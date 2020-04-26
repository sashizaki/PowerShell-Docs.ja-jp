---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: GetMetaConfiguration メソッド
ms.openlocfilehash: bd280cb8ebd7b0522e4e01cbd24bd9bdcfddf4c2
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953409"
---
# <a name="getmetaconfiguration-method"></a><span data-ttu-id="fcece-103">GetMetaConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="fcece-103">GetMetaConfiguration method</span></span>

<span data-ttu-id="fcece-104">構成エージェントを制御するために使用するローカル構成マネージャーの設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="fcece-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="fcece-105">構文</span><span class="sxs-lookup"><span data-stu-id="fcece-105">Syntax</span></span>

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

## <a name="parameters"></a><span data-ttu-id="fcece-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="fcece-106">Parameters</span></span>

<span data-ttu-id="fcece-107">*MetaConfiguration* \[out\] 制御が戻ったとき、設定を定義する **MSFT_DSCMetaConfiguration** クラスの埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fcece-107">*MetaConfiguration* \[out\] On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="fcece-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="fcece-108">Return value</span></span>

<span data-ttu-id="fcece-109">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="fcece-109">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="fcece-110">解説</span><span class="sxs-lookup"><span data-stu-id="fcece-110">Remarks</span></span>

<span data-ttu-id="fcece-111">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="fcece-111">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="fcece-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="fcece-112">Requirements</span></span>

<span data-ttu-id="fcece-113">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="fcece-113">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="fcece-114">**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="fcece-114">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="fcece-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcece-115">See also</span></span>

[<span data-ttu-id="fcece-116">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="fcece-116">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
