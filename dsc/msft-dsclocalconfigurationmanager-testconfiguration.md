---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの TestConfiguration メソッド
ms.openlocfilehash: 2df04d317bd5e7a5c2a713d92be57c5c9a9f5e8c
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34219013"
---
# <a name="testconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="be321-103">MSFT_DSCLocalConfigurationManager クラスの TestConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="be321-103">TestConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="be321-104">構成ドキュメントを管理ノードに送信し、そのドキュメントに対して現在の構成を検証します。</span><span class="sxs-lookup"><span data-stu-id="be321-104">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>

<a name="syntax"></a><span data-ttu-id="be321-105">構文</span><span class="sxs-lookup"><span data-stu-id="be321-105">Syntax</span></span>
------

```mof
uint32 TestConfiguration(
  [in]  uint8                          configurationData[],
  [out] boolean                        InDesiredState,
  [out] MSFT_ResourceInDesiredState    ResourcesInDesiredState[],
  [out] MSFT_ResourceNotInDesiredState ResourcesNotInDesiredState[]
);
```

<a name="parameters"></a><span data-ttu-id="be321-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="be321-106">Parameters</span></span>
----------

<span data-ttu-id="be321-107">*configurationData* \[in\] 構成のための環境データ。</span><span class="sxs-lookup"><span data-stu-id="be321-107">*configurationData* \[in\] Environment data for the confuguration.</span></span>

<span data-ttu-id="be321-108">*InDesiredState* \[out\] 制御が戻ったとき、管理ノードが構成ドキュメントで指定された状態であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="be321-108">*InDesiredState* \[out\] On return, specifies whether the managed node is in the state specified by the configuration document.</span></span>

<span data-ttu-id="be321-109">*ResourcesInDesiredState* \[out\] 制御が戻ったとき、目的の状態にあるリソースを指定する、**MSFT_ResourceInDesiredState** クラスの埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="be321-109">*ResourcesInDesiredState* \[out\] On return, contains an embedded instance of the **MSFT_ResourceInDesiredState** class that specifies resources that are in the desired state.</span></span>

<span data-ttu-id="be321-110">*ResourcesNotInDesiredState* \[out\] 制御が戻ったとき、目的の状態ではないリソースを指定する、**MSFT_ResourceNotInDesiredState** クラスの埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="be321-110">*ResourcesNotInDesiredState* \[out\] On return, contains an embedded instance of the **MSFT_ResourceNotInDesiredState** class that specifies resources that are not in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="be321-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="be321-111">Return value</span></span>
------------

<span data-ttu-id="be321-112">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="be321-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="be321-113">コメント</span><span class="sxs-lookup"><span data-stu-id="be321-113">Remarks</span></span>

<span data-ttu-id="be321-114">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="be321-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="be321-115">要件</span><span class="sxs-lookup"><span data-stu-id="be321-115">Requirements</span></span>
------------
><span data-ttu-id="be321-116">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="be321-116">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="be321-117">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="be321-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="be321-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="be321-118">See also</span></span>


[<span data-ttu-id="be321-119">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="be321-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)