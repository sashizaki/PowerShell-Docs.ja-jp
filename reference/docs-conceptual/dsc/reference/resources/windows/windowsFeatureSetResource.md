---
ms.date: 07/16/2020
ms.topic: reference
title: DSC WindowsFeatureSet リソース
description: DSC WindowsFeatureSet リソース
ms.openlocfilehash: 327c5e907e9b100f42b6a15684f8b131c1f20a41
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2020
ms.locfileid: "93143077"
---
# <a name="dsc-windowsfeatureset-resource"></a><span data-ttu-id="a3448-103">DSC WindowsFeatureSet リソース</span><span class="sxs-lookup"><span data-stu-id="a3448-103">DSC WindowsFeatureSet Resource</span></span>

> <span data-ttu-id="a3448-104">適用先:Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="a3448-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="a3448-105">Windows PowerShell Desired State Configuration (DSC) の **WindowsFeatureSet** リソースは、役割と機能がターゲット ノードで追加または削除されることを保証するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="a3448-105">The **WindowsFeatureSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that roles and features are added or removed on a target node.</span></span> <span data-ttu-id="a3448-106">このリソースは [複合リソース](../../../resources/authoringResourceComposite.md)であり、 **Name** プロパティに指定されている機能ごとに [WindowsFeature リソース](windowsfeatureResource.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a3448-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [WindowsFeature resource](windowsfeatureResource.md) for each feature specified in the **Name** property.</span></span>

<span data-ttu-id="a3448-107">Windows 機能の数を同じ状態に構成するときにこのリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3448-107">Use this resource when you want to configure a number of Windows Features to the same state.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="a3448-108">構文</span><span class="sxs-lookup"><span data-stu-id="a3448-108">Syntax</span></span>

```Syntax
WindowsFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ Source = [string] ]
    [ IncludeAllSubFeature = [Boolean] ]
    [ Credential = [PSCredential] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="a3448-109">Properties</span><span class="sxs-lookup"><span data-stu-id="a3448-109">Properties</span></span>

|  <span data-ttu-id="a3448-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a3448-110">Property</span></span>  |  <span data-ttu-id="a3448-111">説明</span><span class="sxs-lookup"><span data-stu-id="a3448-111">Description</span></span>   |
|---|---|
|<span data-ttu-id="a3448-112">名前</span><span class="sxs-lookup"><span data-stu-id="a3448-112">Name</span></span> |<span data-ttu-id="a3448-113">追加または削除する役割または機能の名前。</span><span class="sxs-lookup"><span data-stu-id="a3448-113">The names of the roles or features that you want to ensure are added or removed.</span></span> <span data-ttu-id="a3448-114">これは [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) コマンドレットの **Name** プロパティと同じものであり、役割または機能の表示名ではありません。</span><span class="sxs-lookup"><span data-stu-id="a3448-114">This is the same as the **Name** property of the [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) cmdlet, and not the display name of the roles or features.</span></span> |
|<span data-ttu-id="a3448-115">source</span><span class="sxs-lookup"><span data-stu-id="a3448-115">Source</span></span> |<span data-ttu-id="a3448-116">必要に応じて、インストールに使用するソース ファイルの場所を示します。</span><span class="sxs-lookup"><span data-stu-id="a3448-116">Indicates the location of the source file to use for installation, if necessary.</span></span> |
|<span data-ttu-id="a3448-117">IncludeAllSubFeature</span><span class="sxs-lookup"><span data-stu-id="a3448-117">IncludeAllSubFeature</span></span> |<span data-ttu-id="a3448-118">**Name** プロパティで指定した機能を使用して必要なすべてのサブ機能を含めるには、このプロパティを `$true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="a3448-118">Set this property to `$true` to include all required subfeatures with of the features you specify with the **Name** property.</span></span> |
|<span data-ttu-id="a3448-119">資格情報</span><span class="sxs-lookup"><span data-stu-id="a3448-119">Credential</span></span> |<span data-ttu-id="a3448-120">役割または機能の追加や削除に使用する資格情報。</span><span class="sxs-lookup"><span data-stu-id="a3448-120">The credentials to use to add or remove the roles or features.</span></span> |
|<span data-ttu-id="a3448-121">LogPath</span><span class="sxs-lookup"><span data-stu-id="a3448-121">LogPath</span></span> |<span data-ttu-id="a3448-122">リソース プロバイダーの操作を記録するログ ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="a3448-122">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="a3448-123">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="a3448-123">Common properties</span></span>

|<span data-ttu-id="a3448-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a3448-124">Property</span></span> |<span data-ttu-id="a3448-125">説明</span><span class="sxs-lookup"><span data-stu-id="a3448-125">Description</span></span> |
|---|---|
|<span data-ttu-id="a3448-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="a3448-126">DependsOn</span></span> |<span data-ttu-id="a3448-127">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="a3448-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="a3448-128">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="a3448-128">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="a3448-129">Ensure</span><span class="sxs-lookup"><span data-stu-id="a3448-129">Ensure</span></span> |<span data-ttu-id="a3448-130">役割または機能を追加するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a3448-130">Indicates whether the roles or features are added.</span></span> <span data-ttu-id="a3448-131">役割または機能を確実に追加するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="a3448-131">To ensure that the roles or features are added, set this property to **Present** .</span></span> <span data-ttu-id="a3448-132">役割または機能を確実に削除するには、このプロパティを **Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="a3448-132">To ensure that the roles or features are removed, set the property to **Absent** .</span></span> <span data-ttu-id="a3448-133">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="a3448-133">The default value is **Present** .</span></span> |
|<span data-ttu-id="a3448-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="a3448-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="a3448-135">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="a3448-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="a3448-136">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="a3448-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="a3448-137">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3448-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="a3448-138">例</span><span class="sxs-lookup"><span data-stu-id="a3448-138">Example</span></span>

<span data-ttu-id="a3448-139">次の構成では、 **Web-Server** (IIS) 機能、 **SMTP Server** 機能、各機能のすべてのサブ機能がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a3448-139">The following configuration ensures that the **Web-Server** (IIS) and **SMTP Server** features, and all subfeatures of each, are installed.</span></span>

```powershell
configuration FeatureSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        WindowsFeatureSet WindowsFeatureSetExample
        {
            Name                    = @("SMTP-Server", "Web-Server")
            Ensure                  = 'Present'
            IncludeAllSubFeature    = $true
        }
    }
}
```
