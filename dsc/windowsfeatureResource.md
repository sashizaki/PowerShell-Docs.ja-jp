---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC WindowsFeature リソース"
ms.openlocfilehash: a3433577a122f6c7e31360e094a089f6ceef77c2
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="dsc-windowsfeature-resource"></a><span data-ttu-id="0a471-103">DSC WindowsFeature リソース</span><span class="sxs-lookup"><span data-stu-id="0a471-103">DSC WindowsFeature Resource</span></span>

> <span data-ttu-id="0a471-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="0a471-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="0a471-105">Windows PowerShell Desired State Configuration (DSC) の **WindowsFeature** リソースは、役割と機能がターゲット ノードで追加または削除されることを保証するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="0a471-105">The **WindowsFeature** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that roles and features are added or removed on a target node.</span></span>

## <a name="syntax"></a><span data-ttu-id="0a471-106">構文</span><span class="sxs-lookup"><span data-stu-id="0a471-106">Syntax</span></span>

```
WindowsFeature [string] #ResourceName
{
    Name = [string]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ IncludeAllSubFeature = [bool] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Source = [string] ]
}
```

## <a name="properties"></a><span data-ttu-id="0a471-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0a471-107">Properties</span></span>

|  <span data-ttu-id="0a471-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0a471-108">Property</span></span>  |  <span data-ttu-id="0a471-109">説明</span><span class="sxs-lookup"><span data-stu-id="0a471-109">Description</span></span>   | 
|---|---| 
| <span data-ttu-id="0a471-110">名前</span><span class="sxs-lookup"><span data-stu-id="0a471-110">Name</span></span>| <span data-ttu-id="0a471-111">追加または削除されることを保証する役割または機能の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="0a471-111">Indicates the name of the role or feature that you want to ensure is added or removed.</span></span> <span data-ttu-id="0a471-112">これは、[Get-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205469.aspx) コマンドレットからの __Name__ プロパティと同じものであり、役割または機能の表示名ではありません。</span><span class="sxs-lookup"><span data-stu-id="0a471-112">This is the same as the __Name__ property from the [Get-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205469.aspx) cmdlet, and not the display name of the role or feature.</span></span>| 
| <span data-ttu-id="0a471-113">Credential</span><span class="sxs-lookup"><span data-stu-id="0a471-113">Credential</span></span>| <span data-ttu-id="0a471-114">役割または機能の追加や削除に使用する資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="0a471-114">Indicates the credentials to use to add or remove the role or feature.</span></span>| 
| <span data-ttu-id="0a471-115">Ensure</span><span class="sxs-lookup"><span data-stu-id="0a471-115">Ensure</span></span>| <span data-ttu-id="0a471-116">役割または機能が追加されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0a471-116">Indicates if the role or feature is added.</span></span> <span data-ttu-id="0a471-117">役割または機能が追加されることを保証するには、このプロパティを "Present" に設定します。役割または機能が削除されることを保証するには、このプロパティを "Absent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="0a471-117">To ensure that the role or feature is added, set this property to "Present" To ensure that the role or feature is removed, set the property to "Absent".</span></span>| 
| <span data-ttu-id="0a471-118">IncludeAllSubFeature</span><span class="sxs-lookup"><span data-stu-id="0a471-118">IncludeAllSubFeature</span></span>| <span data-ttu-id="0a471-119">__Name__ プロパティで指定した機能の状態を使用して必要なすべてのサブ機能の状態を保証するには、このプロパティを __$true__ に設定します。</span><span class="sxs-lookup"><span data-stu-id="0a471-119">Set this property to __$true__ to ensure the state of all required subfeatures with the state of the feature you specify with the __Name__ property.</span></span>| 
| <span data-ttu-id="0a471-120">LogPath</span><span class="sxs-lookup"><span data-stu-id="0a471-120">LogPath</span></span>| <span data-ttu-id="0a471-121">リソース プロバイダーの操作を記録するログ ファイルへのパスを示します。</span><span class="sxs-lookup"><span data-stu-id="0a471-121">Indicates the path to a log file where you want the resource provider to log the operation.</span></span>| 
| <span data-ttu-id="0a471-122">DependsOn</span><span class="sxs-lookup"><span data-stu-id="0a471-122">DependsOn</span></span>| <span data-ttu-id="0a471-123">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="0a471-123">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="0a471-124">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="0a471-124">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>| 
| <span data-ttu-id="0a471-125">ソース</span><span class="sxs-lookup"><span data-stu-id="0a471-125">Source</span></span>| <span data-ttu-id="0a471-126">必要に応じて、インストールに使用するソース ファイルの場所を示します。</span><span class="sxs-lookup"><span data-stu-id="0a471-126">Indicates the location of the source file to use for installation, if necessary.</span></span>| 

## <a name="example"></a><span data-ttu-id="0a471-127">例</span><span class="sxs-lookup"><span data-stu-id="0a471-127">Example</span></span>
```powershell
WindowsFeature RoleExample
{
    Ensure = "Present" 
    # Alternatively, to ensure the role is uninstalled, set Ensure to "Absent"
    Name = "Web-Server" # Use the Name property from Get-WindowsFeature  
}
```

