---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: MSFT_DSCLocalConfigurationManager クラスの ResourceGet メソッド
ms.openlocfilehash: 1b74adf2327af2e0f9416f1d00eac4e3b75e9013
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047566"
---
# <a name="resourceget-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="00772-103">MSFT_DSCLocalConfigurationManager クラスの ResourceGet メソッド</span><span class="sxs-lookup"><span data-stu-id="00772-103">ResourceGet method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="00772-104">DSC リソースの **Get** メソッドを直接呼び出します。</span><span class="sxs-lookup"><span data-stu-id="00772-104">Directly calls the **Get** method of a DSC resource.</span></span>

## <a name="syntax"></a><span data-ttu-id="00772-105">構文</span><span class="sxs-lookup"><span data-stu-id="00772-105">Syntax</span></span>

```mof
uint32 ResourceGet(
  [in]  string           ResourceType,
  [in]  string           ModuleName,
  [in]  uint8            resourceProperty[],
  [out] OMI_BaseResource configurations
);
```

## <a name="parameters"></a><span data-ttu-id="00772-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="00772-106">Parameters</span></span>

<span data-ttu-id="00772-107">*ResourceType* \[in\] 呼び出すリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="00772-107">*ResourceType* \[in\] The name of the resource to call.</span></span>

<span data-ttu-id="00772-108">*ModuleName* \[in\] 呼び出すリソースを含むモジュールの名前。</span><span class="sxs-lookup"><span data-stu-id="00772-108">*ModuleName* \[in\] The name of the module that contains the resource to call.</span></span>

<span data-ttu-id="00772-109">*resourceProperty* \[in\] ハッシュ テーブルで、リソースのプロパティ名と値を、それぞれキーと値として指定します。</span><span class="sxs-lookup"><span data-stu-id="00772-109">*resourceProperty* \[in\] Specifies the resource property name and its value in a hash table as key and value, respectively.</span></span> <span data-ttu-id="00772-110">リソースのプロパティと種類を検出するには、[Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="00772-110">Use the [Get-DscResource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource) cmdlet to discover resource properties and their types.</span></span>

<span data-ttu-id="00772-111">*configurations* \[out\] 制御が戻ったとき、その構成の埋め込みインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="00772-111">*configurations* \[out\] On return, contains an embedded instance of the configurations.</span></span>

## <a name="return-value"></a><span data-ttu-id="00772-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="00772-112">Return value</span></span>

<span data-ttu-id="00772-113">成功した場合は 0 を返します。それ以外の場合はエラー コードを返します。</span><span class="sxs-lookup"><span data-stu-id="00772-113">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="00772-114">コメント</span><span class="sxs-lookup"><span data-stu-id="00772-114">Remarks</span></span>

<span data-ttu-id="00772-115">これは静的メソッドです。</span><span class="sxs-lookup"><span data-stu-id="00772-115">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="00772-116">要件</span><span class="sxs-lookup"><span data-stu-id="00772-116">Requirements</span></span>

<span data-ttu-id="00772-117">MOF\*\*DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="00772-117">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="00772-118">\*\*［名前空間］:Root \microsoft\windows\desiredstateconfiguration</span><span class="sxs-lookup"><span data-stu-id="00772-118">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="00772-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="00772-119">See also</span></span>

[<span data-ttu-id="00772-120">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="00772-120">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)