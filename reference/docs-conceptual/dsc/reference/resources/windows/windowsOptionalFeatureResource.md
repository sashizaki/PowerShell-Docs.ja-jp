---
ms.date: 08/28/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WindowsOptionalFeature リソース
ms.openlocfilehash: f24173c1a9ed605bac43767a9da2d4dbded78883
ms.sourcegitcommit: 06b6f4012e4eca71d414733cdba23ef75535223c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2020
ms.locfileid: "89093252"
---
# <a name="dsc-windowsoptionalfeature-resource"></a><span data-ttu-id="7188c-103">DSC WindowsOptionalFeature リソース</span><span class="sxs-lookup"><span data-stu-id="7188c-103">DSC WindowsOptionalFeature Resource</span></span>

> <span data-ttu-id="7188c-104">適用先:Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="7188c-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="7188c-105">Windows PowerShell Desired State Configuration (DSC) の **WindowsOptionalFeature** リソースは、オプション機能をターゲット ノードで有効にするためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="7188c-105">The **WindowsOptionalFeature** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that optional features are enabled on a target node.</span></span>

> [!NOTE]
> <span data-ttu-id="7188c-106">**WindowsOptionalFeature** は、Windows 10 などの Windows クライアント コンピューターでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="7188c-106">**WindowsOptionalFeature** only works on Windows client machines like Windows 10.</span></span>

## <a name="syntax"></a><span data-ttu-id="7188c-107">構文</span><span class="sxs-lookup"><span data-stu-id="7188c-107">Syntax</span></span>

```Syntax
WindowsOptionalFeature [string] #ResourceName
{
    Name = [string]
    [ NoWindowsUpdateCheck = [bool] ]
    [ RemoveFilesOnDisable = [bool] ]
    [ LogLevel = [string] { ErrorsOnly | ErrorsAndWarning | ErrorsAndWarningAndInformation }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Enable | Disable }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="7188c-108">Properties</span><span class="sxs-lookup"><span data-stu-id="7188c-108">Properties</span></span>

|<span data-ttu-id="7188c-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7188c-109">Property</span></span> |<span data-ttu-id="7188c-110">説明</span><span class="sxs-lookup"><span data-stu-id="7188c-110">Description</span></span> |
|---|---|
|<span data-ttu-id="7188c-111">名前</span><span class="sxs-lookup"><span data-stu-id="7188c-111">Name</span></span> |<span data-ttu-id="7188c-112">有効または無効にする機能の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="7188c-112">Indicates the name of the feature that you want to ensure is enabled or disabled.</span></span> |
|<span data-ttu-id="7188c-113">NoWindowsUpdateCheck</span><span class="sxs-lookup"><span data-stu-id="7188c-113">NoWindowsUpdateCheck</span></span> |<span data-ttu-id="7188c-114">機能を有効にするソース ファイルを検索するとき、DISM が Windows Update (WU) を確認するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="7188c-114">Specifies whether DISM contacts Windows Update (WU) when searching for the source files to enable a feature.</span></span> <span data-ttu-id="7188c-115">`$true` の場合、DISM は WU に接続しません。</span><span class="sxs-lookup"><span data-stu-id="7188c-115">If `$true`, DISM does not contact WU.</span></span> |
|<span data-ttu-id="7188c-116">RemoveFilesOnDisable</span><span class="sxs-lookup"><span data-stu-id="7188c-116">RemoveFilesOnDisable</span></span> |<span data-ttu-id="7188c-117">**Ensure** が **Absent** に設定されているときに、`$true` に設定すると、その機能に関連付けられているすべてのファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="7188c-117">Set to `$true` to remove all files associated with the feature when **Ensure** is set to **Absent**.</span></span> |
|<span data-ttu-id="7188c-118">LogLevel</span><span class="sxs-lookup"><span data-stu-id="7188c-118">LogLevel</span></span> |<span data-ttu-id="7188c-119">ログに表示される最大の出力レベル。</span><span class="sxs-lookup"><span data-stu-id="7188c-119">The maximum output level shown in the logs.</span></span> <span data-ttu-id="7188c-120">有効な値は**ErrorsOnly**、**ErrorsAndWarning**、**ErrorsAndWarningAndInformation** です。</span><span class="sxs-lookup"><span data-stu-id="7188c-120">The accepted values are: **ErrorsOnly**, **ErrorsAndWarning**, and **ErrorsAndWarningAndInformation**.</span></span> |
|<span data-ttu-id="7188c-121">LogPath</span><span class="sxs-lookup"><span data-stu-id="7188c-121">LogPath</span></span> |<span data-ttu-id="7188c-122">リソース プロバイダーの操作を記録するログ ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="7188c-122">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="7188c-123">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="7188c-123">Common properties</span></span>

|<span data-ttu-id="7188c-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="7188c-124">Property</span></span> |<span data-ttu-id="7188c-125">説明</span><span class="sxs-lookup"><span data-stu-id="7188c-125">Description</span></span> |
|---|---|
|<span data-ttu-id="7188c-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="7188c-126">DependsOn</span></span> |<span data-ttu-id="7188c-127">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="7188c-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="7188c-128">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="7188c-128">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="7188c-129">Ensure</span><span class="sxs-lookup"><span data-stu-id="7188c-129">Ensure</span></span> |<span data-ttu-id="7188c-130">機能が有効かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="7188c-130">Specifies whether the feature is enabled.</span></span> <span data-ttu-id="7188c-131">機能を確実に有効にするには、このプロパティを _Enable_ に設定します。</span><span class="sxs-lookup"><span data-stu-id="7188c-131">To ensure that the feature is enabled, set this property to _Enable_.</span></span> <span data-ttu-id="7188c-132">機能を確実に無効にするには、このプロパティを _Disable_ に設定します。</span><span class="sxs-lookup"><span data-stu-id="7188c-132">To ensure that the feature is disabled, set the property to _Disable_.</span></span> <span data-ttu-id="7188c-133">既定値は _Enable_ です。</span><span class="sxs-lookup"><span data-stu-id="7188c-133">The default value is _Enable_.</span></span> |
|<span data-ttu-id="7188c-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="7188c-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="7188c-135">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="7188c-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="7188c-136">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="7188c-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="7188c-137">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7188c-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>
