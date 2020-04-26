---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: SendConfiguration メソッド
ms.openlocfilehash: 4feba090bc58844659c2329a304dd9805255564f
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71953389"
---
# <a name="sendconfiguration-method"></a><span data-ttu-id="0c1c3-103">SendConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="0c1c3-103">SendConfiguration method</span></span>

<span data-ttu-id="0c1c3-104">構成ドキュメントを管理ノードに送信し、保留中の変更として保存します。</span><span class="sxs-lookup"><span data-stu-id="0c1c3-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

## <a name="syntax"></a><span data-ttu-id="0c1c3-105">構文</span><span class="sxs-lookup"><span data-stu-id="0c1c3-105">Syntax</span></span>

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="0c1c3-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c1c3-106">Parameters</span></span>

<span data-ttu-id="0c1c3-107">*ConfigurationData* \[in\] 構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="0c1c3-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="0c1c3-108">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="0c1c3-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="0c1c3-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="0c1c3-109">Return value</span></span>

<span data-ttu-id="0c1c3-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="0c1c3-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="0c1c3-111">解説</span><span class="sxs-lookup"><span data-stu-id="0c1c3-111">Remarks</span></span>

<span data-ttu-id="0c1c3-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="0c1c3-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="0c1c3-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="0c1c3-113">Requirements</span></span>

<span data-ttu-id="0c1c3-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="0c1c3-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="0c1c3-115">**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="0c1c3-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="0c1c3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c1c3-116">See also</span></span>

[<span data-ttu-id="0c1c3-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="0c1c3-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
