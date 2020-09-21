---
ms.date: 07/17/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: TestConfiguration メソッド
ms.openlocfilehash: 0611c4d5543c49b879bef9b60cafdd0b055c9b86
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464300"
---
# <a name="testconfiguration-method"></a><span data-ttu-id="69e7e-103">TestConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="69e7e-103">TestConfiguration method</span></span>

<span data-ttu-id="69e7e-104">構成ドキュメントを管理ノードに送信し、そのドキュメントに対して現在の構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="69e7e-104">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>

## <a name="syntax"></a><span data-ttu-id="69e7e-105">構文</span><span class="sxs-lookup"><span data-stu-id="69e7e-105">Syntax</span></span>

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

## <a name="parameters"></a><span data-ttu-id="69e7e-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="69e7e-106">Parameters</span></span>

<span data-ttu-id="69e7e-107">**configurationData** \[in\] 構成のための環境データです。</span><span class="sxs-lookup"><span data-stu-id="69e7e-107">**configurationData** \[in\] Environment data for the configuration.</span></span>

<span data-ttu-id="69e7e-108">**InDesiredState** \[out\] 制御が戻ったとき、マネージド ノードが構成ドキュメントで指定された状態であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="69e7e-108">**InDesiredState** \[out\] On return, specifies whether the managed node is in the state specified by the configuration document.</span></span>

<span data-ttu-id="69e7e-109">**ResourcesInDesiredState** \[out\] 制御が戻ったとき、目的の状態にあるリソースを指定する、**MSFT_ResourceInDesiredState** クラスの埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="69e7e-109">**ResourcesInDesiredState** \[out\] On return, contains an embedded instance of the **MSFT_ResourceInDesiredState** class that specifies resources that are in the desired state.</span></span>

<span data-ttu-id="69e7e-110">**ResourcesNotInDesiredState** \[out\] 制御が戻ったとき、目的の状態ではないリソースを指定する、**MSFT_ResourceNotInDesiredState** クラスの埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="69e7e-110">**ResourcesNotInDesiredState** \[out\] On return, contains an embedded instance of the **MSFT_ResourceNotInDesiredState** class that specifies resources that are not in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="69e7e-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="69e7e-111">Return value</span></span>

<span data-ttu-id="69e7e-112">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="69e7e-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="69e7e-113">解説</span><span class="sxs-lookup"><span data-stu-id="69e7e-113">Remarks</span></span>

<span data-ttu-id="69e7e-114">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="69e7e-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="69e7e-115">必要条件</span><span class="sxs-lookup"><span data-stu-id="69e7e-115">Requirements</span></span>

<span data-ttu-id="69e7e-116">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="69e7e-116">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="69e7e-117">**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="69e7e-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="69e7e-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="69e7e-118">See also</span></span>

[<span data-ttu-id="69e7e-119">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="69e7e-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
