---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド
ms.openlocfilehash: b372a6c0ab9d4561dcf67026275e7d3ca6aa2584
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37892959"
---
# <a name="sendmetaconfigurationapply-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="8a992-103">MSFT_DSCLocalConfigurationManager クラスの SendMetaConfigurationApply メソッド</span><span class="sxs-lookup"><span data-stu-id="8a992-103">SendMetaConfigurationApply method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="8a992-104">構成エージェントを制御するために使用するローカル構成マネージャーの設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="8a992-104">Sets the Local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

## <a name="syntax"></a><span data-ttu-id="8a992-105">構文</span><span class="sxs-lookup"><span data-stu-id="8a992-105">Syntax</span></span>

```mof
uint32 SendMetaConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="8a992-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a992-106">Parameters</span></span>

<span data-ttu-id="8a992-107">*ConfigurationData* \[in\] 構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="8a992-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="8a992-108">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="8a992-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="8a992-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="8a992-109">Return value</span></span>

<span data-ttu-id="8a992-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="8a992-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="8a992-111">コメント</span><span class="sxs-lookup"><span data-stu-id="8a992-111">Remarks</span></span>

<span data-ttu-id="8a992-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="8a992-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="8a992-113">要件</span><span class="sxs-lookup"><span data-stu-id="8a992-113">Requirements</span></span>

<span data-ttu-id="8a992-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="8a992-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="8a992-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="8a992-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="8a992-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a992-116">See also</span></span>

[<span data-ttu-id="8a992-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="8a992-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)