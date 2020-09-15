---
ms.date: 07/17/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: GetConfiguration メソッド
ms.openlocfilehash: 989aeef4cd9aa5d55741b48c8565c657c4b6512c
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463824"
---
# <a name="getconfiguration-method"></a><span data-ttu-id="e974b-103">GetConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="e974b-103">GetConfiguration method</span></span>

<span data-ttu-id="e974b-104">構成ドキュメントを管理ノードに送信し、構成エージェントの **Get** メソッドを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="e974b-104">Sends the configuration document to the managed node and uses the **Get** method of the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="e974b-105">構文</span><span class="sxs-lookup"><span data-stu-id="e974b-105">Syntax</span></span>

```mof
uint32 GetConfiguration(
  [in]  uint8            configurationData[],
  [out] OMI_BaseResource configurations[]
);
```

## <a name="parameters"></a><span data-ttu-id="e974b-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e974b-106">Parameters</span></span>

<span data-ttu-id="e974b-107">**configurationData** \[in\] 送信する構成データを指定します。</span><span class="sxs-lookup"><span data-stu-id="e974b-107">**configurationData** \[in\] Specifies the configuration data to send.</span></span>

<span data-ttu-id="e974b-108">**configurations** \[out\] 制御が戻ったとき、その構成の埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e974b-108">**configurations** \[out\] On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="e974b-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="e974b-109">Return value</span></span>

<span data-ttu-id="e974b-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="e974b-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="e974b-111">解説</span><span class="sxs-lookup"><span data-stu-id="e974b-111">Remarks</span></span>

<span data-ttu-id="e974b-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="e974b-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e974b-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="e974b-113">Requirements</span></span>

<span data-ttu-id="e974b-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="e974b-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="e974b-115">**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="e974b-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="e974b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e974b-116">See also</span></span>

[<span data-ttu-id="e974b-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="e974b-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
