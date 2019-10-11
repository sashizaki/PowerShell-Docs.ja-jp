---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: SendConfiguration メソッド
ms.openlocfilehash: 4feba090bc58844659c2329a304dd9805255564f
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71953389"
---
# <a name="sendconfiguration-method"></a><span data-ttu-id="2fb33-103">SendConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="2fb33-103">SendConfiguration method</span></span>

<span data-ttu-id="2fb33-104">構成ドキュメントを管理ノードに送信し、保留中の変更として保存します。</span><span class="sxs-lookup"><span data-stu-id="2fb33-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

## <a name="syntax"></a><span data-ttu-id="2fb33-105">構文</span><span class="sxs-lookup"><span data-stu-id="2fb33-105">Syntax</span></span>

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="2fb33-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fb33-106">Parameters</span></span>

<span data-ttu-id="2fb33-107">*ConfigurationData* \[in\] 構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="2fb33-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="2fb33-108">*force* \[in\] **true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="2fb33-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="2fb33-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="2fb33-109">Return value</span></span>

<span data-ttu-id="2fb33-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="2fb33-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="2fb33-111">コメント</span><span class="sxs-lookup"><span data-stu-id="2fb33-111">Remarks</span></span>

<span data-ttu-id="2fb33-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="2fb33-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="2fb33-113">要件</span><span class="sxs-lookup"><span data-stu-id="2fb33-113">Requirements</span></span>

<span data-ttu-id="2fb33-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="2fb33-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="2fb33-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="2fb33-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="2fb33-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fb33-116">See also</span></span>

[<span data-ttu-id="2fb33-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="2fb33-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
