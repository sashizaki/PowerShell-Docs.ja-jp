---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの GetConfiguration メソッド
ms.openlocfilehash: 46eec896df643996bea5f2c371a9294034caae6b
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="getconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="b9ec9-103">MSFT_DSCLocalConfigurationManager クラスの GetConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="b9ec9-103">GetConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="b9ec9-104">構成ドキュメントを管理ノードに送信し、構成エージェントの **Get** メソッドを使用して構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="b9ec9-104">Sends the configuration document to the managed node and uses the **Get** method of the Configuration Agent to apply the configuration.</span></span>

<a name="syntax"></a><span data-ttu-id="b9ec9-105">構文</span><span class="sxs-lookup"><span data-stu-id="b9ec9-105">Syntax</span></span>
------

```mof
uint32 GetConfiguration(
  [in]  uint8            configurationData[],
  [out] OMI_BaseResource configurations[]
);
```

<a name="parameters"></a><span data-ttu-id="b9ec9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b9ec9-106">Parameters</span></span>
----------

<span data-ttu-id="b9ec9-107">*configurationData* \[in\] 送信する構成データを指定します。</span><span class="sxs-lookup"><span data-stu-id="b9ec9-107">*configurationData* \[in\] Specifies the configuration data to send.</span></span>

<span data-ttu-id="b9ec9-108">*configurations* \[out\] 制御が戻ったとき、その構成の埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b9ec9-108">*configurations* \[out\] On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="b9ec9-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="b9ec9-109">Return value</span></span>
------------

<span data-ttu-id="b9ec9-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="b9ec9-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9ec9-111">コメント</span><span class="sxs-lookup"><span data-stu-id="b9ec9-111">Remarks</span></span>

<span data-ttu-id="b9ec9-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="b9ec9-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="b9ec9-113">要件</span><span class="sxs-lookup"><span data-stu-id="b9ec9-113">Requirements</span></span>
------------
><span data-ttu-id="b9ec9-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="b9ec9-114">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="b9ec9-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="b9ec9-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="b9ec9-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="b9ec9-116">See also</span></span>


[<span data-ttu-id="b9ec9-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="b9ec9-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)