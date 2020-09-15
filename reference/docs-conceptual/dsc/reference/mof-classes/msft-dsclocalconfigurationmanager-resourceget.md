---
ms.date: 07/17/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: ResourceGet メソッド
ms.openlocfilehash: aa7671989db6f4a98d879fd449d09503eddbeda3
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463960"
---
# <a name="resourceget-method"></a><span data-ttu-id="247d1-103">ResourceGet メソッド</span><span class="sxs-lookup"><span data-stu-id="247d1-103">ResourceGet method</span></span>

<span data-ttu-id="247d1-104">DSC リソースの **Get** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="247d1-104">Directly calls the **Get** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="247d1-105">構文</span><span class="sxs-lookup"><span data-stu-id="247d1-105">Syntax</span></span>

```mof
uint32 ResourceGet(
  [in]  string           ResourceType,
  [in]  string           ModuleName,
  [in]  uint8            resourceProperty[],
  [out] OMI_BaseResource configurations
);
```

## <a name="parameters"></a><span data-ttu-id="247d1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="247d1-106">Parameters</span></span>

<span data-ttu-id="247d1-107">**ResourceType** \[in\] 呼び出すリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="247d1-107">**ResourceType** \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="247d1-108">**ModuleName** \[in\] 呼び出すリソースを含むモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="247d1-108">**ModuleName** \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="247d1-109">**resourceProperty** \[in\] ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。</span><span class="sxs-lookup"><span data-stu-id="247d1-109">**resourceProperty** \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="247d1-110">リソースのプロパティと種類を検出するには、[Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="247d1-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="247d1-111">**configurations** \[out\] 制御が戻ったとき、その構成の埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="247d1-111">**configurations** \[out\] On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="247d1-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="247d1-112">Return value</span></span>

<span data-ttu-id="247d1-113">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="247d1-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="247d1-114">解説</span><span class="sxs-lookup"><span data-stu-id="247d1-114">Remarks</span></span>

<span data-ttu-id="247d1-115">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="247d1-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="247d1-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="247d1-116">Requirements</span></span>

<span data-ttu-id="247d1-117">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="247d1-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="247d1-118">**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="247d1-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="247d1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="247d1-119">See also</span></span>

[<span data-ttu-id="247d1-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="247d1-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
