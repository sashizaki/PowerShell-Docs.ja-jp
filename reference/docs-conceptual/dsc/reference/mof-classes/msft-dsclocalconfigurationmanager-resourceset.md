---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: ResourceSet メソッド
ms.openlocfilehash: 18364027b249e502e1f0b8802d9f3e031c7b07ce
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71954959"
---
# <a name="resourceset-method"></a><span data-ttu-id="66439-103">ResourceSet メソッド</span><span class="sxs-lookup"><span data-stu-id="66439-103">ResourceSet method</span></span>

<span data-ttu-id="66439-104">DSC リソースの **Set** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="66439-104">Directly calls the **Set** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="66439-105">構文</span><span class="sxs-lookup"><span data-stu-id="66439-105">Syntax</span></span>

```mof
uint32 ResourceSet(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean RebootRequired
);
```

## <a name="parameters"></a><span data-ttu-id="66439-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="66439-106">Parameters</span></span>

<span data-ttu-id="66439-107">*ResourceType* \[in\] 呼び出すリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="66439-107">*ResourceType* \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="66439-108">*ModuleName* \[in\] 呼び出すリソースを含むモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="66439-108">*ModuleName* \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="66439-109">*resourceProperty* \[in\] ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。</span><span class="sxs-lookup"><span data-stu-id="66439-109">*resourceProperty* \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="66439-110">リソースのプロパティと種類を検出するには、[Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="66439-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="66439-111">*RebootRequired* \[out\] ターゲット ノードの再起動が必要な場合、制御が戻るときに、このプロパティは **true** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="66439-111">*RebootRequired* \[out\] On return, this property is set to **true** if the target node needs to be rebooted.</span></span>

## <a name="return-value"></a><span data-ttu-id="66439-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="66439-112">Return value</span></span>

<span data-ttu-id="66439-113">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="66439-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="66439-114">解説</span><span class="sxs-lookup"><span data-stu-id="66439-114">Remarks</span></span>

<span data-ttu-id="66439-115">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="66439-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="66439-116">必要条件</span><span class="sxs-lookup"><span data-stu-id="66439-116">Requirements</span></span>

<span data-ttu-id="66439-117">**MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="66439-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="66439-118">**名前空間**:Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="66439-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="66439-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="66439-119">See also</span></span>

[<span data-ttu-id="66439-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="66439-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)
