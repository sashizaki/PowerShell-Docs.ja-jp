---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WindowsOptionalFeatureSet リソース
ms.openlocfilehash: f378006a6c362ee9890d70dd76fb552dd262a544
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "71952869"
---
# <a name="dsc-windowsoptionalfeatureset-resource"></a><span data-ttu-id="c648a-103">DSC WindowsOptionalFeatureSet リソース</span><span class="sxs-lookup"><span data-stu-id="c648a-103">DSC WindowsOptionalFeatureSet Resource</span></span>

> <span data-ttu-id="c648a-104">適用先:Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="c648a-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="c648a-105">Windows PowerShell Desired State Configuration (DSC) の **WindowsOptionalFeatureSet** リソースは、オプション機能をターゲット ノードで有効にするためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="c648a-105">The **WindowsOptionalFeatureSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that optional features are enabled on a target node.</span></span> <span data-ttu-id="c648a-106">このリソースは[複合リソース](../../../resources/authoringResourceComposite.md)であり、**Name** プロパティに指定されている機能ごとに [WindowsOptionalFeature リソース](windowsOptionalFeatureResource.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c648a-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [WindowsOptionalFeature resource](windowsOptionalFeatureResource.md) for each feature specified in the **Name** property.</span></span>

<span data-ttu-id="c648a-107">Windows のオプション機能の数を同じ状態に構成するときにこのリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="c648a-107">Use this resource when you want to configure a number of Windows optional features to the same state.</span></span>

## <a name="syntax"></a><span data-ttu-id="c648a-108">構文</span><span class="sxs-lookup"><span data-stu-id="c648a-108">Syntax</span></span>

```Syntax
WindowsOptionalFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ Source = [string] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogPath = [string] ]
    [ NoWindowsUpdateCheck = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="c648a-109">Properties</span><span class="sxs-lookup"><span data-stu-id="c648a-109">Properties</span></span>

|<span data-ttu-id="c648a-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c648a-110">Property</span></span> |<span data-ttu-id="c648a-111">説明</span><span class="sxs-lookup"><span data-stu-id="c648a-111">Description</span></span> |
|---|---|
|<span data-ttu-id="c648a-112">名前</span><span class="sxs-lookup"><span data-stu-id="c648a-112">Name</span></span> |<span data-ttu-id="c648a-113">有効または無効にする機能の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="c648a-113">Indicates the name of the features that you want to ensure are enabled or disabled.</span></span> |
|<span data-ttu-id="c648a-114">source</span><span class="sxs-lookup"><span data-stu-id="c648a-114">Source</span></span> |<span data-ttu-id="c648a-115">実装されていません。</span><span class="sxs-lookup"><span data-stu-id="c648a-115">Not implemented.</span></span> |
|<span data-ttu-id="c648a-116">NoWindowsUpdateCheck</span><span class="sxs-lookup"><span data-stu-id="c648a-116">NoWindowsUpdateCheck</span></span> |<span data-ttu-id="c648a-117">機能を有効にするソース ファイルを検索するとき、DISM が Windows Update (WU) を確認するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c648a-117">Specifies whether DISM contacts Windows Update (WU) when searching for the source files to enable features.</span></span> <span data-ttu-id="c648a-118">`$true` の場合、DISM は WU に接続しません。</span><span class="sxs-lookup"><span data-stu-id="c648a-118">If `$true`, DISM does not contact WU.</span></span> |
|<span data-ttu-id="c648a-119">RemoveFilesOnDisable</span><span class="sxs-lookup"><span data-stu-id="c648a-119">RemoveFilesOnDisable</span></span> |<span data-ttu-id="c648a-120">**Ensure** が **Absent** に設定されているときに、`$true` に設定すると、その機能に関連付けられているすべてのファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c648a-120">Set to `$true` to remove all files associated with the features when **Ensure** is set to **Absent**.</span></span> |
|<span data-ttu-id="c648a-121">LogLevel</span><span class="sxs-lookup"><span data-stu-id="c648a-121">LogLevel</span></span> |<span data-ttu-id="c648a-122">ログに表示される最大の出力レベル。</span><span class="sxs-lookup"><span data-stu-id="c648a-122">The maximum output level shown in the logs.</span></span> <span data-ttu-id="c648a-123">有効な値は**ErrorsOnly**、**ErrorsAndWarning**、**ErrorsAndWarningAndInformation** です。</span><span class="sxs-lookup"><span data-stu-id="c648a-123">The accepted values are: **ErrorsOnly**, **ErrorsAndWarning**, and **ErrorsAndWarningAndInformation**.</span></span> |
|<span data-ttu-id="c648a-124">LogPath</span><span class="sxs-lookup"><span data-stu-id="c648a-124">LogPath</span></span> |<span data-ttu-id="c648a-125">リソース プロバイダーの操作を記録するログ ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="c648a-125">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="c648a-126">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="c648a-126">Common properties</span></span>

|<span data-ttu-id="c648a-127">プロパティ</span><span class="sxs-lookup"><span data-stu-id="c648a-127">Property</span></span> |<span data-ttu-id="c648a-128">説明</span><span class="sxs-lookup"><span data-stu-id="c648a-128">Description</span></span> |
|---|---|
|<span data-ttu-id="c648a-129">DependsOn</span><span class="sxs-lookup"><span data-stu-id="c648a-129">DependsOn</span></span> |<span data-ttu-id="c648a-130">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="c648a-130">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="c648a-131">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="c648a-131">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="c648a-132">Ensure</span><span class="sxs-lookup"><span data-stu-id="c648a-132">Ensure</span></span> |<span data-ttu-id="c648a-133">機能が有効化かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="c648a-133">Specifies whether the features are enabled.</span></span> <span data-ttu-id="c648a-134">機能を確実に有効にするには、このプロパティを **Enable** に設定します。</span><span class="sxs-lookup"><span data-stu-id="c648a-134">To ensure that the features are enabled, set this property to **Enable**.</span></span> <span data-ttu-id="c648a-135">機能を確実に無効にするには、このプロパティを **Disable** に設定します。</span><span class="sxs-lookup"><span data-stu-id="c648a-135">To ensure that the features are disabled, set the property to **Disable**.</span></span> <span data-ttu-id="c648a-136">既定値は **Enable** です。</span><span class="sxs-lookup"><span data-stu-id="c648a-136">The default value is **Enable**.</span></span> |
|<span data-ttu-id="c648a-137">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="c648a-137">PsDscRunAsCredential</span></span> |<span data-ttu-id="c648a-138">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="c648a-138">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="c648a-139">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="c648a-139">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="c648a-140">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c648a-140">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>