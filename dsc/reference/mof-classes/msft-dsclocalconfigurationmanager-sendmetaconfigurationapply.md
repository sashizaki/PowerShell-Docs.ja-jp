---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: SendMetaConfigurationApply メソッド
ms.openlocfilehash: b2e420bafb8ea22aea43800f6e429d3ed785d1e8
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67727047"
---
# <a name="sendmetaconfigurationapply-method"></a><span data-ttu-id="35946-103">SendMetaConfigurationApply メソッド</span><span class="sxs-lookup"><span data-stu-id="35946-103">SendMetaConfigurationApply method</span></span>

<span data-ttu-id="35946-104">構成エージェントを制御するために使用するローカル構成マネージャーの設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="35946-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="35946-105">構文</span><span class="sxs-lookup"><span data-stu-id="35946-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="35946-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="35946-106">Parameters</span></span>

<span data-ttu-id="35946-107">*ConfigurationData* \[in\] 構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="35946-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="35946-108">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="35946-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="35946-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="35946-109">Return value</span></span>

<span data-ttu-id="35946-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="35946-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="35946-111">コメント</span><span class="sxs-lookup"><span data-stu-id="35946-111">Remarks</span></span>

<span data-ttu-id="35946-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="35946-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="35946-113">要件</span><span class="sxs-lookup"><span data-stu-id="35946-113">Requirements</span></span>

<span data-ttu-id="35946-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="35946-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="35946-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="35946-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="35946-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="35946-116">See also</span></span>

[<span data-ttu-id="35946-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="35946-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
