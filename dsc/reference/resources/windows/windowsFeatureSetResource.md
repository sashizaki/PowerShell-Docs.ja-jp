---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC WindowsFeatureSet リソース
ms.openlocfilehash: 8b7c7e72dd58459bd19cb723e5790a82841515c0
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047539"
---
# <a name="dsc-windowsfeatureset-resource"></a><span data-ttu-id="42ed3-103">DSC WindowsFeatureSet リソース</span><span class="sxs-lookup"><span data-stu-id="42ed3-103">DSC WindowsFeatureSet Resource</span></span>

> <span data-ttu-id="42ed3-104">適用先:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="42ed3-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="42ed3-105">Windows PowerShell Desired State Configuration (DSC) の **WindowsFeatureSet** リソースは、役割と機能がターゲット ノードで追加または削除されることを保証するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="42ed3-105">The **WindowsFeatureSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that roles and features are added or removed on a target node.</span></span>
<span data-ttu-id="42ed3-106">このリソースは[複合リソース](../../../resources/authoringResourceComposite.md)であり、`Name` プロパティに指定されている機能ごとに [WindowsFeature リソース](windowsfeatureResource.md)を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="42ed3-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [WindowsFeature resource](windowsfeatureResource.md) for each feature specified in the `Name` property.</span></span>

<span data-ttu-id="42ed3-107">Windows 機能の数を同じ状態に構成するときにこのリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="42ed3-107">Use this resource when you want to configure a number of Windows Features to the same state.</span></span>

## <a name="syntax"></a><span data-ttu-id="42ed3-108">構文</span><span class="sxs-lookup"><span data-stu-id="42ed3-108">Syntax</span></span>

```
WindowsFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ Ensure = [string] { Absent | Present }  ]
    [ Source = [string] ]
    [ IncludeAllSubFeature = [bool] ]
    [ Credential = [PSCredential] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]

}
```

## <a name="properties"></a><span data-ttu-id="42ed3-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="42ed3-109">Properties</span></span>

|  <span data-ttu-id="42ed3-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="42ed3-110">Property</span></span>  |  <span data-ttu-id="42ed3-111">説明</span><span class="sxs-lookup"><span data-stu-id="42ed3-111">Description</span></span>   |
|---|---|
| <span data-ttu-id="42ed3-112">名前</span><span class="sxs-lookup"><span data-stu-id="42ed3-112">Name</span></span>| <span data-ttu-id="42ed3-113">追加または削除する役割または機能の名前。</span><span class="sxs-lookup"><span data-stu-id="42ed3-113">The names of the roles or features that you want to ensure are added or removed.</span></span> <span data-ttu-id="42ed3-114">これは [Get-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205469.aspx) コマンドレットの **Name** プロパティと同じものであり、役割または機能の表示名ではありません。</span><span class="sxs-lookup"><span data-stu-id="42ed3-114">This is the same as the **Name** property of the [Get-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205469.aspx) cmdlet, and not the display name of the roles or features.</span></span>|
| <span data-ttu-id="42ed3-115">Credential</span><span class="sxs-lookup"><span data-stu-id="42ed3-115">Credential</span></span>| <span data-ttu-id="42ed3-116">役割または機能の追加や削除に使用する資格情報。</span><span class="sxs-lookup"><span data-stu-id="42ed3-116">The credentials to use to add or remove the roles or features.</span></span>|
| <span data-ttu-id="42ed3-117">Ensure</span><span class="sxs-lookup"><span data-stu-id="42ed3-117">Ensure</span></span>| <span data-ttu-id="42ed3-118">役割または機能を追加するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="42ed3-118">Indicates whether the roles or features are added.</span></span> <span data-ttu-id="42ed3-119">役割または機能を追加するには、このプロパティを "Present" に設定します。役割または機能を削除するには、このプロパティを "Absent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="42ed3-119">To ensure that the roles or features are added, set this property to "Present" To ensure that the roles or features are removed, set the property to "Absent".</span></span>|
| <span data-ttu-id="42ed3-120">IncludeAllSubFeature</span><span class="sxs-lookup"><span data-stu-id="42ed3-120">IncludeAllSubFeature</span></span>| <span data-ttu-id="42ed3-121">**Name** プロパティで指定した機能を使用して必要なすべてのサブ機能を含めるには、このプロパティを **$true** に設定します。</span><span class="sxs-lookup"><span data-stu-id="42ed3-121">Set this property to **$true** to include all required subfeatures with of the features you specify with the **Name** property.</span></span>|
| <span data-ttu-id="42ed3-122">LogPath</span><span class="sxs-lookup"><span data-stu-id="42ed3-122">LogPath</span></span>| <span data-ttu-id="42ed3-123">リソース プロバイダーの操作を記録するログ ファイルへのパス。</span><span class="sxs-lookup"><span data-stu-id="42ed3-123">The path to a log file where you want the resource provider to log the operation.</span></span>|
| <span data-ttu-id="42ed3-124">DependsOn</span><span class="sxs-lookup"><span data-stu-id="42ed3-124">DependsOn</span></span>| <span data-ttu-id="42ed3-125">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="42ed3-125">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="42ed3-126">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="42ed3-126">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="42ed3-127">ソース</span><span class="sxs-lookup"><span data-stu-id="42ed3-127">Source</span></span>| <span data-ttu-id="42ed3-128">必要に応じて、インストールに使用するソース ファイルの場所を示します。</span><span class="sxs-lookup"><span data-stu-id="42ed3-128">Indicates the location of the source file to use for installation, if necessary.</span></span>|

## <a name="example"></a><span data-ttu-id="42ed3-129">例</span><span class="sxs-lookup"><span data-stu-id="42ed3-129">Example</span></span>

<span data-ttu-id="42ed3-130">次の構成では、**Web-Server** (IIS) 機能、**SMTP Server** 機能、各機能のすべてのサブ機能がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="42ed3-130">The following configuration ensures that the **Web-Server** (IIS) and **SMTP Server** features, and all subfeatures of each, are installed.</span></span>

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
