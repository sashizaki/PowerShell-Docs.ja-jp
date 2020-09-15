---
ms.date: 07/16/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WindowsFeature リソース
ms.openlocfilehash: b15b267c6898697816b386a381e5a6d59acd492a
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "86464113"
---
# <a name="dsc-windowsfeature-resource"></a><span data-ttu-id="338ad-103">DSC WindowsFeature リソース</span><span class="sxs-lookup"><span data-stu-id="338ad-103">DSC WindowsFeature Resource</span></span>

> <span data-ttu-id="338ad-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="338ad-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="338ad-105">Windows PowerShell Desired State Configuration (DSC) の **WindowsFeature** リソースは、役割と機能がターゲット ノードで追加または削除されることを保証するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="338ad-105">The **WindowsFeature** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that roles and features are added or removed on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="338ad-106">構文</span><span class="sxs-lookup"><span data-stu-id="338ad-106">Syntax</span></span>

```Syntax
WindowsFeature [string] #ResourceName
{
    Name = [string]
    [ Credential = [PSCredential] ]
    [ IncludeAllSubFeature = [bool] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="338ad-107">Properties</span><span class="sxs-lookup"><span data-stu-id="338ad-107">Properties</span></span>

|<span data-ttu-id="338ad-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="338ad-108">Property</span></span> |<span data-ttu-id="338ad-109">説明</span><span class="sxs-lookup"><span data-stu-id="338ad-109">Description</span></span> |
|---|---|
|<span data-ttu-id="338ad-110">名前</span><span class="sxs-lookup"><span data-stu-id="338ad-110">Name</span></span> |<span data-ttu-id="338ad-111">追加または削除されることを保証する役割または機能の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="338ad-111">Indicates the name of the role or feature that you want to ensure is added or removed.</span></span> <span data-ttu-id="338ad-112">これは、[Get-WindowsFeature](/powershell/module/servermanager/Get-WindowsFeature) コマンドレットからの **Name** プロパティと同じものであり、役割または機能の表示名ではありません。</span><span class="sxs-lookup"><span data-stu-id="338ad-112">This is the same as the **Name** property from the [Get-WindowsFeature](/powershell/module/servermanager/Get-WindowsFeature) cmdlet, and not the display name of the role or feature.</span></span> |
|<span data-ttu-id="338ad-113">資格情報</span><span class="sxs-lookup"><span data-stu-id="338ad-113">Credential</span></span> |<span data-ttu-id="338ad-114">役割または機能の追加や削除に使用する資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="338ad-114">Indicates the credentials to use to add or remove the role or feature.</span></span> |
|<span data-ttu-id="338ad-115">IncludeAllSubFeature</span><span class="sxs-lookup"><span data-stu-id="338ad-115">IncludeAllSubFeature</span></span> |<span data-ttu-id="338ad-116">**Name** プロパティで指定した機能の状態を使用して必要なすべてのサブ機能の状態を保証するには、このプロパティを `$true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="338ad-116">Set this property to `$true` to ensure the state of all required subfeatures with the state of the feature you specify with the **Name** property.</span></span> |
|<span data-ttu-id="338ad-117">LogPath</span><span class="sxs-lookup"><span data-stu-id="338ad-117">LogPath</span></span> |<span data-ttu-id="338ad-118">リソース プロバイダーの操作を記録するログ ファイルへのパスを示します。</span><span class="sxs-lookup"><span data-stu-id="338ad-118">Indicates the path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="338ad-119">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="338ad-119">Common properties</span></span>

|<span data-ttu-id="338ad-120">プロパティ</span><span class="sxs-lookup"><span data-stu-id="338ad-120">Property</span></span> |<span data-ttu-id="338ad-121">説明</span><span class="sxs-lookup"><span data-stu-id="338ad-121">Description</span></span> |
|---|---|
|<span data-ttu-id="338ad-122">DependsOn</span><span class="sxs-lookup"><span data-stu-id="338ad-122">DependsOn</span></span> |<span data-ttu-id="338ad-123">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="338ad-123">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="338ad-124">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="338ad-124">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="338ad-125">Ensure</span><span class="sxs-lookup"><span data-stu-id="338ad-125">Ensure</span></span> |<span data-ttu-id="338ad-126">役割または機能が追加されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="338ad-126">Indicates if the role or feature is added.</span></span> <span data-ttu-id="338ad-127">役割または機能を確実に追加するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="338ad-127">To ensure that the role or feature is added, set this property to **Present**.</span></span> <span data-ttu-id="338ad-128">役割または機能を確実に削除するには、このプロパティを **Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="338ad-128">To ensure that the role or feature is removed, set the property to **Absent**.</span></span> <span data-ttu-id="338ad-129">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="338ad-129">The default value is **Present**.</span></span> |
|<span data-ttu-id="338ad-130">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="338ad-130">PsDscRunAsCredential</span></span> |<span data-ttu-id="338ad-131">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="338ad-131">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="338ad-132">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="338ad-132">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="338ad-133">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="338ad-133">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="338ad-134">例</span><span class="sxs-lookup"><span data-stu-id="338ad-134">Example</span></span>

```powershell
WindowsFeature RoleExample
{
    Ensure = "Present"
    # Alternatively, to ensure the role is uninstalled, set Ensure to "Absent"
    Name = "Web-Server" # Use the Name property from Get-WindowsFeature
}
```
