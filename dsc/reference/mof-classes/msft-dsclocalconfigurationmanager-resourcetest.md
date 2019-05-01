---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの ResourceTest メソッド
ms.openlocfilehash: e7645b0c6b93b96cb01f72c1c92d468f7642ea13
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62078556"
---
# <a name="resourcetest-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="48758-103">MSFT_DSCLocalConfigurationManager クラスの ResourceTest メソッド</span><span class="sxs-lookup"><span data-stu-id="48758-103">ResourceTest method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="48758-104">DSC リソースの **Test** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="48758-104">Directly calls the **Test** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="48758-105">構文</span><span class="sxs-lookup"><span data-stu-id="48758-105">Syntax</span></span>

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

## <a name="parameters"></a><span data-ttu-id="48758-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="48758-106">Parameters</span></span>

<span data-ttu-id="48758-107">*ResourceType* \[in\] 呼び出すリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="48758-107">*ResourceType* \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="48758-108">*ModuleName* \[in\] 呼び出すリソースを含むモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="48758-108">*ModuleName* \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="48758-109">*resourceProperty* \[in\] ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。</span><span class="sxs-lookup"><span data-stu-id="48758-109">*resourceProperty* \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="48758-110">リソースのプロパティと種類を検出するには、[Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="48758-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="48758-111">*InDesiredState* \[out\] ターゲット ノードが目的の状態にある場合、制御が戻るときに、このプロパティは **true** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="48758-111">*InDesiredState* \[out\] On return, this property is set to **true** if the target node is in the desired state.</span></span>

## <a name="return-value"></a><span data-ttu-id="48758-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="48758-112">Return value</span></span>

<span data-ttu-id="48758-113">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="48758-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="48758-114">コメント</span><span class="sxs-lookup"><span data-stu-id="48758-114">Remarks</span></span>

<span data-ttu-id="48758-115">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="48758-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="48758-116">要件</span><span class="sxs-lookup"><span data-stu-id="48758-116">Requirements</span></span>

<span data-ttu-id="48758-117">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="48758-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="48758-118">**名前空間**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="48758-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="48758-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="48758-119">See also</span></span>

[<span data-ttu-id="48758-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="48758-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)