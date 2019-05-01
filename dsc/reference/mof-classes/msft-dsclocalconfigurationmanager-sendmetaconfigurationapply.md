---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド
ms.openlocfilehash: b372a6c0ab9d4561dcf67026275e7d3ca6aa2584
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078314"
---
# <a name="sendmetaconfigurationapply-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="47db5-103">MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド</span><span class="sxs-lookup"><span data-stu-id="47db5-103">SendMetaConfigurationApply method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="47db5-104">構成エージェントを制御するために使用するローカル構成マネージャーの設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="47db5-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="47db5-105">構文</span><span class="sxs-lookup"><span data-stu-id="47db5-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="47db5-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="47db5-106">Parameters</span></span>

<span data-ttu-id="47db5-107">*ConfigurationData* \[in\] 構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="47db5-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="47db5-108">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="47db5-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="47db5-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="47db5-109">Return value</span></span>

<span data-ttu-id="47db5-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="47db5-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="47db5-111">コメント</span><span class="sxs-lookup"><span data-stu-id="47db5-111">Remarks</span></span>

<span data-ttu-id="47db5-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="47db5-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="47db5-113">要件</span><span class="sxs-lookup"><span data-stu-id="47db5-113">Requirements</span></span>

<span data-ttu-id="47db5-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="47db5-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="47db5-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="47db5-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="47db5-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="47db5-116">See also</span></span>

[<span data-ttu-id="47db5-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="47db5-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)