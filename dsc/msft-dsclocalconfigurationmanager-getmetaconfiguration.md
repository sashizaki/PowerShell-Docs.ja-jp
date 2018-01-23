---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "MSFT_DSCLocalConfigurationManager クラスの GetMetaConfiguration メソッド"
ms.openlocfilehash: 695be4ee6490567295fda0cc44635870362d24b8
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="getmetaconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="a1982-103">MSFT_DSCLocalConfigurationManager クラスの GetMetaConfiguration メソッド</span><span class="sxs-lookup"><span data-stu-id="a1982-103">GetMetaConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="a1982-104">構成エージェントを制御するために使用するローカル構成マネージャーの設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="a1982-104">Gets the local Configuration Manager settings that are used to control the Configuration Agent.</span></span>

<a name="syntax"></a><span data-ttu-id="a1982-105">構文</span><span class="sxs-lookup"><span data-stu-id="a1982-105">Syntax</span></span>
------

```mof
uint32 GetMetaConfiguration(
  [out] MSFT_DSCMetaConfiguration MetaConfiguration
);
```

<a name="parameters"></a><span data-ttu-id="a1982-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a1982-106">Parameters</span></span>
----------

<span data-ttu-id="a1982-107">*MetaConfiguration* \[out\]</span><span class="sxs-lookup"><span data-stu-id="a1982-107">*MetaConfiguration* \[out\]</span></span>  
<span data-ttu-id="a1982-108">制御が戻ったとき、設定を定義する **MSFT_DSCMetaConfiguration** クラスの埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a1982-108">On return, contains an embedded instance of the **MSFT_DSCMetaConfiguration** class that defines the settings.</span></span>

## <a name="return-value"></a><span data-ttu-id="a1982-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="a1982-109">Return value</span></span>
------------

<span data-ttu-id="a1982-110">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="a1982-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1982-111">コメント</span><span class="sxs-lookup"><span data-stu-id="a1982-111">Remarks</span></span>

<span data-ttu-id="a1982-112">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="a1982-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a1982-113">要件</span><span class="sxs-lookup"><span data-stu-id="a1982-113">Requirements</span></span>
------------
><span data-ttu-id="a1982-114">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="a1982-114">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="a1982-115">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="a1982-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="a1982-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1982-116">See also</span></span>


[<span data-ttu-id="a1982-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="a1982-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)


 

 



