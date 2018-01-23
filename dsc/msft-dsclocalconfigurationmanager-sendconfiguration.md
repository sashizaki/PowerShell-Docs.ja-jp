---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの SendConfiguration メソッド"
ms.openlocfilehash: 72c59b5aad293fa561146e5ad6822f27f40f321f
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="sendconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="6fdd9-103">MSFT_DSCLocalConfigurationManager クラスの SendConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="6fdd9-103">SendConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="6fdd9-104">構成ドキュメントを管理ノードに送信し、保留中の変更として保存します。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

<a name="syntax"></a><span data-ttu-id="6fdd9-105">構文</span><span class="sxs-lookup"><span data-stu-id="6fdd9-105">Syntax</span></span>
------

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

<a name="parameters"></a><span data-ttu-id="6fdd9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6fdd9-106">Parameters</span></span>
----------

<span data-ttu-id="6fdd9-107">*ConfigurationData* \[in\]</span><span class="sxs-lookup"><span data-stu-id="6fdd9-107">*ConfigurationData* \[in\]</span></span>  
<span data-ttu-id="6fdd9-108">構成用の環境データ。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-108">The environment data for the configuration.</span></span>

<span data-ttu-id="6fdd9-109">*force* \[in\]</span><span class="sxs-lookup"><span data-stu-id="6fdd9-109">*force* \[in\]</span></span>  
<span data-ttu-id="6fdd9-110">**true** の場合、構成を強制的に中止します。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-110">**true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="6fdd9-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="6fdd9-111">Return value</span></span>
------------

<span data-ttu-id="6fdd9-112">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="6fdd9-113">コメント</span><span class="sxs-lookup"><span data-stu-id="6fdd9-113">Remarks</span></span>

<span data-ttu-id="6fdd9-114">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="6fdd9-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="6fdd9-115">要件</span><span class="sxs-lookup"><span data-stu-id="6fdd9-115">Requirements</span></span>
------------
><span data-ttu-id="6fdd9-116">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="6fdd9-116">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="6fdd9-117">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="6fdd9-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="6fdd9-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="6fdd9-118">See also</span></span>


[<span data-ttu-id="6fdd9-119">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="6fdd9-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



