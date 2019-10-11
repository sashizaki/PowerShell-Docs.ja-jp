---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WindowsFeatureSet リソース
ms.openlocfilehash: 1758d248dde4fdee57bd01c157a3f9a8340d6194
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71952959"
---
# <a name="dsc-windowsfeatureset-resource"></a><span data-ttu-id="4f235-103">DSC WindowsFeatureSet リソース</span><span class="sxs-lookup"><span data-stu-id="4f235-103">DSC WindowsFeatureSet Resource</span></span>

> <span data-ttu-id="4f235-104">適用先:Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="4f235-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="4f235-105">Windows PowerShell Desired State Configuration (DSC) の **WindowsFeatureSet** リソースは、役割と機能がターゲット ノードで追加または削除されることを保証するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="4f235-105">The **WindowsFeatureSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that roles and features are added or removed on a target node.</span></span> <span data-ttu-id="4f235-106">このリソースは[複合リソース](../../../resources/authoringResourceComposite.md)であり、**Name** プロパティに指定されている機能ごとに [WindowsFeature リソース](windowsfeatureResource.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4f235-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [WindowsFeature resource](windowsfeatureResource.md) for each feature specified in the **Name** property.</span></span>

<span data-ttu-id="4f235-107">Windows 機能の数を同じ状態に構成するときにこのリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f235-107">Use this resource when you want to configure a number of Windows Features to the same state.</span></span>

## <a name="syntax"></a><span data-ttu-id="4f235-108">構文</span><span class="sxs-lookup"><span data-stu-id="4f235-108">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="4f235-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4f235-109">Properties</span></span>

|  <span data-ttu-id="4f235-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4f235-110">Property</span></span>  |  <span data-ttu-id="4f235-111">説明</span><span class="sxs-lookup"><span data-stu-id="4f235-111">Description</span></span>   |
|---|---|
|<span data-ttu-id="4f235-112">名前</span><span class="sxs-lookup"><span data-stu-id="4f235-112">Name</span></span> |<span data-ttu-id="4f235-113">追加または削除する役割または機能の名前。</span><span class="sxs-lookup"><span data-stu-id="4f235-113">The names of the roles or features that you want to ensure are added or removed.</span></span> <span data-ttu-id="4f235-114">これは [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature?view=winserver2012r2-ps) コマンドレットの **Name** プロパティと同じものであり、役割または機能の表示名ではありません。</span><span class="sxs-lookup"><span data-stu-id="4f235-114">This is the same as the **Name** property of the [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature?view=winserver2012r2-ps) cmdlet, and not the display name of the roles or features.</span></span> |
|<span data-ttu-id="4f235-115">ソース</span><span class="sxs-lookup"><span data-stu-id="4f235-115">Source</span></span> |<span data-ttu-id="4f235-116">必要に応じて、インストールに使用するソース ファイルの場所を示します。</span><span class="sxs-lookup"><span data-stu-id="4f235-116">Indicates the location of the source file to use for installation, if necessary.</span></span> |
|<span data-ttu-id="4f235-117">IncludeAllSubFeature</span><span class="sxs-lookup"><span data-stu-id="4f235-117">IncludeAllSubFeature</span></span> |<span data-ttu-id="4f235-118">**Name** プロパティで指定した機能を使用して必要なすべてのサブ機能を含めるには、このプロパティを `$true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="4f235-118">Set this property to `$true` to include all required subfeatures with of the features you specify with the **Name** property.</span></span> |
|<span data-ttu-id="4f235-119">Credential</span><span class="sxs-lookup"><span data-stu-id="4f235-119">Credential</span></span> |<span data-ttu-id="4f235-120">役割または機能の追加や削除に使用する資格情報。</span><span class="sxs-lookup"><span data-stu-id="4f235-120">The credentials to use to add or remove the roles or features.</span></span> |
|<span data-ttu-id="4f235-121">LogPath</span><span class="sxs-lookup"><span data-stu-id="4f235-121">LogPath</span></span> |<span data-ttu-id="4f235-122">リソース プロバイダーの操作を記録するログ ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="4f235-122">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="4f235-123">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="4f235-123">Common properties</span></span>

|<span data-ttu-id="4f235-124">プロパティ</span><span class="sxs-lookup"><span data-stu-id="4f235-124">Property</span></span> |<span data-ttu-id="4f235-125">説明</span><span class="sxs-lookup"><span data-stu-id="4f235-125">Description</span></span> |
|---|---|
|<span data-ttu-id="4f235-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="4f235-126">DependsOn</span></span> |<span data-ttu-id="4f235-127">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="4f235-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="4f235-128">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="4f235-128">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="4f235-129">Ensure</span><span class="sxs-lookup"><span data-stu-id="4f235-129">Ensure</span></span> |<span data-ttu-id="4f235-130">役割または機能を追加するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="4f235-130">Indicates whether the roles or features are added.</span></span> <span data-ttu-id="4f235-131">役割または機能を確実に追加するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="4f235-131">To ensure that the roles or features are added, set this property to **Present**.</span></span> <span data-ttu-id="4f235-132">役割または機能を確実に削除するには、このプロパティを **Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="4f235-132">To ensure that the roles or features are removed, set the property to **Absent**.</span></span> <span data-ttu-id="4f235-133">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="4f235-133">The default value is **Present**.</span></span> |
|<span data-ttu-id="4f235-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="4f235-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="4f235-135">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="4f235-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="4f235-136">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="4f235-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="4f235-137">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f235-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="4f235-138">例</span><span class="sxs-lookup"><span data-stu-id="4f235-138">Example</span></span>

<span data-ttu-id="4f235-139">次の構成では、**Web-Server** (IIS) 機能、**SMTP Server** 機能、各機能のすべてのサブ機能がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4f235-139">The following configuration ensures that the **Web-Server** (IIS) and **SMTP Server** features, and all subfeatures of each, are installed.</span></span>

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