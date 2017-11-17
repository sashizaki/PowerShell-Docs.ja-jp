---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの GetConfiguration メソッド"
ms.openlocfilehash: 96676a76a0302543e5e4a214c82ed952d7f52a71
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="getconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="c3e23-103">MSFT_DSCLocalConfigurationManager クラスの GetConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="c3e23-103">GetConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="c3e23-104">構成ドキュメントを管理ノードに送信し、構成エージェントの **Get** メソッドを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="c3e23-104">Sends the configuration document to the managed node and uses the **Get** method of the Configuration Agent to apply the configuration.</span></span>

<a name="syntax"></a><span data-ttu-id="c3e23-105">構文</span><span class="sxs-lookup"><span data-stu-id="c3e23-105">Syntax</span></span>
------

```mof
uint32 GetConfiguration(
  [in]  uint8            configurationData[],
  [out] OMI_BaseResource configurations[]
);
```

<a name="parameters"></a><span data-ttu-id="c3e23-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3e23-106">Parameters</span></span>
----------

<span data-ttu-id="c3e23-107">*configurationData* \[in\]</span><span class="sxs-lookup"><span data-stu-id="c3e23-107">*configurationData* \[in\]</span></span>  
<span data-ttu-id="c3e23-108">送信する構成データを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3e23-108">Specifies the configuration data to send.</span></span>

<span data-ttu-id="c3e23-109">*configurations* \[out\]</span><span class="sxs-lookup"><span data-stu-id="c3e23-109">*configurations* \[out\]</span></span>  
<span data-ttu-id="c3e23-110">制御が戻ったとき、その構成の埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c3e23-110">On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="c3e23-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="c3e23-111">Return value</span></span>
------------

<span data-ttu-id="c3e23-112">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="c3e23-112">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="c3e23-113">コメント</span><span class="sxs-lookup"><span data-stu-id="c3e23-113">Remarks</span></span>

<span data-ttu-id="c3e23-114">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="c3e23-114">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c3e23-115">要件</span><span class="sxs-lookup"><span data-stu-id="c3e23-115">Requirements</span></span>
------------
><span data-ttu-id="c3e23-116">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="c3e23-116">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="c3e23-117">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="c3e23-117">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="c3e23-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="c3e23-118">See also</span></span>


[<span data-ttu-id="c3e23-119">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="c3e23-119">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
 

 



