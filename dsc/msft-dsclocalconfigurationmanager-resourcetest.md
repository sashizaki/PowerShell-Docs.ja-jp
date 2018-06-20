---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの ResourceTest メソッド
ms.openlocfilehash: 714bbb286ebbe4ed0f1faa15e03ac4b51a3ee87f
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34218860"
---
# <a name="resourcetest-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="cb0c1-103">MSFT_DSCLocalConfigurationManager クラスの ResourceTest メソッド</span><span class="sxs-lookup"><span data-stu-id="cb0c1-103">ResourceTest method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="cb0c1-104">DSC リソースの **Test** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cb0c1-104">Directly calls the **Test** method of a DSC resource.</span></span>

<a name="syntax"></a><span data-ttu-id="cb0c1-105">構文</span><span class="sxs-lookup"><span data-stu-id="cb0c1-105">Syntax</span></span>
------

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

<a name="parameters"></a><span data-ttu-id="cb0c1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="cb0c1-106">Parameters</span></span>
----------

<span data-ttu-id="cb0c1-107">*ResourceType* \[in\] 呼び出すリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="cb0c1-107">*ResourceType* \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="cb0c1-108">*ModuleName* \[in\] 呼び出すリソースを含むモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="cb0c1-108">*ModuleName* \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="cb0c1-109">*resourceProperty* \[in\] ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。</span><span class="sxs-lookup"><span data-stu-id="cb0c1-109">*resourceProperty* \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="cb0c1-110">リソースのプロパティと種類を検出するには、[Get-DscResource](https://technet.microsoft.com/library/dn521625.aspx) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb0c1-110">Use the [Get-DscResource](https://technet.microsoft.com/library/dn521625.aspx) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="cb0c1-111">*InDesiredState* \[out\] ターゲット ノードが目的の状態にある場合、制御が戻るときに、このプロパティは **true** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="cb0c1-111">*InDesiredState* \[out\] On return, this property is set to **true** if the target node is in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="cb0c1-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="cb0c1-112">Return value</span></span>
------------

<span data-ttu-id="cb0c1-113">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="cb0c1-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb0c1-114">コメント</span><span class="sxs-lookup"><span data-stu-id="cb0c1-114">Remarks</span></span>

<span data-ttu-id="cb0c1-115">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="cb0c1-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="cb0c1-116">要件</span><span class="sxs-lookup"><span data-stu-id="cb0c1-116">Requirements</span></span>
------------
><span data-ttu-id="cb0c1-117">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="cb0c1-117">**MOF:** DscCore.mof</span></span>

><span data-ttu-id="cb0c1-118">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="cb0c1-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>


## <a name="see-also"></a><span data-ttu-id="cb0c1-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="cb0c1-119">See also</span></span>


[<span data-ttu-id="cb0c1-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="cb0c1-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)