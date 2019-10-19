---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: ResourceTest メソッド
ms.openlocfilehash: ff06fd645a94055e79aa0f8d20f2f06e16483720
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954949"
---
# <a name="resourcetest-method"></a><span data-ttu-id="04ab4-103">ResourceTest メソッド</span><span class="sxs-lookup"><span data-stu-id="04ab4-103">ResourceTest method</span></span>

<span data-ttu-id="04ab4-104">DSC リソースの **Test** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="04ab4-104">Directly calls the **Test** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="04ab4-105">構文</span><span class="sxs-lookup"><span data-stu-id="04ab4-105">Syntax</span></span>

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

## <a name="parameters"></a><span data-ttu-id="04ab4-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="04ab4-106">Parameters</span></span>

<span data-ttu-id="04ab4-107">*ResourceType* \[in\] 呼び出すリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="04ab4-107">*ResourceType* \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="04ab4-108">*ModuleName* \[in\] 呼び出すリソースを含むモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="04ab4-108">*ModuleName* \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="04ab4-109">*resourceProperty* \[in\] ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。</span><span class="sxs-lookup"><span data-stu-id="04ab4-109">*resourceProperty* \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="04ab4-110">リソースのプロパティと種類を検出するには、[Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="04ab4-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="04ab4-111">*InDesiredState* \[out\] ターゲット ノードが目的の状態にある場合、制御が戻るときに、このプロパティは **true** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="04ab4-111">*InDesiredState* \[out\] On return, this property is set to **true** if the target node is in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="04ab4-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="04ab4-112">Return value</span></span>

<span data-ttu-id="04ab4-113">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="04ab4-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="04ab4-114">コメント</span><span class="sxs-lookup"><span data-stu-id="04ab4-114">Remarks</span></span>

<span data-ttu-id="04ab4-115">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="04ab4-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="04ab4-116">要件</span><span class="sxs-lookup"><span data-stu-id="04ab4-116">Requirements</span></span>

<span data-ttu-id="04ab4-117">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="04ab4-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="04ab4-118">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="04ab4-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="04ab4-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="04ab4-119">See also</span></span>

[<span data-ttu-id="04ab4-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="04ab4-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)