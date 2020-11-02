---
ms.date: 07/15/2020
ms.topic: reference
title: DSC の PackageManagementSource リソース
description: DSC の PackageManagementSource リソース
ms.openlocfilehash: 495b6548ef86f639e93b914ec8bd8ea7818ff8dd
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142856"
---
# <a name="dsc-packagemanagementsource-resource"></a><span data-ttu-id="0c3e4-103">DSC の PackageManagementSource リソース</span><span class="sxs-lookup"><span data-stu-id="0c3e4-103">DSC PackageManagementSource Resource</span></span>

> <span data-ttu-id="0c3e4-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="0c3e4-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="0c3e4-105">Windows PowerShell Desired State Configuration (DSC) の **PackageManagementSource** リソースは、ターゲット ノードで Package Management ソースを登録または登録解除するメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-105">The **PackageManagementSource** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to register or unregister Package Management sources on a target node.</span></span>
<span data-ttu-id="0c3e4-106">**この方法で登録された Package Management ソースは System コンテキストで登録されるため、System アカウントまたは DSC エンジンで使用することができます。**</span><span class="sxs-lookup"><span data-stu-id="0c3e4-106">**Package Management sources registered in this way are registered under the System context, usable by the System account or by the DSC engine.**</span></span> <span data-ttu-id="0c3e4-107">このリソースには **PackageManagement** モジュールが必要です。これは、 [PowerShell Gallery](https://PowerShellGallery.com) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-107">This resource requires the **PackageManagement** module, available from the [PowerShell Gallery](https://PowerShellGallery.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c3e4-108">**PackageManagement** モジュールは、次のプロパティ情報が適切であるようにバージョン 1.1.7.0 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-108">The **PackageManagement** module should be at least version 1.1.7.0 for the following property information to be correct.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="0c3e4-109">構文</span><span class="sxs-lookup"><span data-stu-id="0c3e4-109">Syntax</span></span>

```Syntax
PackageManagementSource [String] #ResourceName
{
    Name = [string]
    ProviderName = [string]
    SourceLocation = [string]
    [ InstallationPolicy = [string]{ Trusted | Untrusted } ]
    [ SourceCredential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string]{ Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="0c3e4-110">Properties</span><span class="sxs-lookup"><span data-stu-id="0c3e4-110">Properties</span></span>

|<span data-ttu-id="0c3e4-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0c3e4-111">Property</span></span> |<span data-ttu-id="0c3e4-112">説明</span><span class="sxs-lookup"><span data-stu-id="0c3e4-112">Description</span></span> |
|---|---|
|<span data-ttu-id="0c3e4-113">名前</span><span class="sxs-lookup"><span data-stu-id="0c3e4-113">Name</span></span> |<span data-ttu-id="0c3e4-114">システムで登録または登録解除するパッケージ ソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-114">Specifies the name of the package source to be registered or unregistered on your system.</span></span> |
|<span data-ttu-id="0c3e4-115">ProviderName</span><span class="sxs-lookup"><span data-stu-id="0c3e4-115">ProviderName</span></span> |<span data-ttu-id="0c3e4-116">パッケージ ソースとの相互運用に使用できる OneGet プロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-116">Specifies the name of the OneGet provider through which you can interop with the package source.</span></span> |
|<span data-ttu-id="0c3e4-117">SourceLocation</span><span class="sxs-lookup"><span data-stu-id="0c3e4-117">SourceLocation</span></span> |<span data-ttu-id="0c3e4-118">パッケージ ソースの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-118">Specifies the URI of the package source.</span></span> |
|<span data-ttu-id="0c3e4-119">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="0c3e4-119">InstallationPolicy</span></span> |<span data-ttu-id="0c3e4-120">組み込みの Nuget プロバイダーなどのプロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-120">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="0c3e4-121">パッケージのソースを信頼するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-121">Determines whether you trust the package's source.</span></span> <span data-ttu-id="0c3e4-122">つぎのいずれかです。 **Untrusted** または **Trusted** 。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-122">One of: **Untrusted** or **Trusted** .</span></span> |
|<span data-ttu-id="0c3e4-123">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="0c3e4-123">SourceCredential</span></span> |<span data-ttu-id="0c3e4-124">リモート ソースのパッケージへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-124">Provides access to the package on a remote source.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="0c3e4-125">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="0c3e4-125">Common properties</span></span>

|<span data-ttu-id="0c3e4-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0c3e4-126">Property</span></span> |<span data-ttu-id="0c3e4-127">説明</span><span class="sxs-lookup"><span data-stu-id="0c3e4-127">Description</span></span> |
|---|---|
|<span data-ttu-id="0c3e4-128">DependsOn</span><span class="sxs-lookup"><span data-stu-id="0c3e4-128">DependsOn</span></span> |<span data-ttu-id="0c3e4-129">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-129">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="0c3e4-130">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-130">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="0c3e4-131">Ensure</span><span class="sxs-lookup"><span data-stu-id="0c3e4-131">Ensure</span></span> |<span data-ttu-id="0c3e4-132">パッケージ ソースを登録または登録解除するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-132">Determines whether the package source is to be registered or unregistered.</span></span> <span data-ttu-id="0c3e4-133">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-133">The default value is **Present** .</span></span> |
|<span data-ttu-id="0c3e4-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="0c3e4-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="0c3e4-135">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="0c3e4-136">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="0c3e4-137">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="0c3e4-138">例</span><span class="sxs-lookup"><span data-stu-id="0c3e4-138">Example</span></span>

<span data-ttu-id="0c3e4-139">この例では、 **PackageManagementSource** DSC リソースを使用して `https://nuget.org` パッケージ ソースを登録しています。</span><span class="sxs-lookup"><span data-stu-id="0c3e4-139">This example registers the `https://nuget.org` package source using the **PackageManagementSource** DSC resource.</span></span>

```powershell
Configuration PackageManagementSourceTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceLocation   = "https://api.nuget.org/api/v3/"
        InstallationPolicy ="Trusted"
    }
}
```
