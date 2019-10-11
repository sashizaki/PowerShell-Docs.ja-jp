---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC の PackageManagementSource リソース
ms.openlocfilehash: 20b7851e44751d4bd0add718d2f7294d5215ab70
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954789"
---
# <a name="dsc-packagemanagementsource-resource"></a><span data-ttu-id="1eb6c-103">DSC の PackageManagementSource リソース</span><span class="sxs-lookup"><span data-stu-id="1eb6c-103">DSC PackageManagementSource Resource</span></span>

> <span data-ttu-id="1eb6c-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="1eb6c-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="1eb6c-105">Windows PowerShell Desired State Configuration (DSC) の **PackageManagementSource** リソースは、ターゲット ノードで Package Management ソースを登録または登録解除するメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-105">The **PackageManagementSource** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to register or unregister Package Management sources on a target node.</span></span>
<span data-ttu-id="1eb6c-106">**この方法で登録された Package Management ソースは System コンテキストで登録されるため、System アカウントまたは DSC エンジンで使用することができます。**</span><span class="sxs-lookup"><span data-stu-id="1eb6c-106">**Package Management sources registered in this way are registered under the System context, usable by the System account or by the DSC engine.**</span></span> <span data-ttu-id="1eb6c-107">このリソースには **PackageManagement** モジュールが必要です。これは、[PowerShell Gallery](https://PowerShellGallery.com) から入手できます。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-107">This resource requires the **PackageManagement** module, available from the [PowerShell Gallery](https://PowerShellGallery.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1eb6c-108">**PackageManagement** モジュールは、次のプロパティ情報が適切であるようにバージョン 1.1.7.0 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-108">The **PackageManagement** module should be at least version 1.1.7.0 for the following property information to be correct.</span></span>

## <a name="syntax"></a><span data-ttu-id="1eb6c-109">構文</span><span class="sxs-lookup"><span data-stu-id="1eb6c-109">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="1eb6c-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1eb6c-110">Properties</span></span>

|<span data-ttu-id="1eb6c-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1eb6c-111">Property</span></span> |<span data-ttu-id="1eb6c-112">説明</span><span class="sxs-lookup"><span data-stu-id="1eb6c-112">Description</span></span> |
|---|---|
|<span data-ttu-id="1eb6c-113">名前</span><span class="sxs-lookup"><span data-stu-id="1eb6c-113">Name</span></span> |<span data-ttu-id="1eb6c-114">システムで登録または登録解除するパッケージ ソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-114">Specifies the name of the package source to be registered or unregistered on your system.</span></span> |
|<span data-ttu-id="1eb6c-115">ProviderName</span><span class="sxs-lookup"><span data-stu-id="1eb6c-115">ProviderName</span></span> |<span data-ttu-id="1eb6c-116">パッケージ ソースとの相互運用に使用できる OneGet プロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-116">Specifies the name of the OneGet provider through which you can interop with the package source.</span></span> |
|<span data-ttu-id="1eb6c-117">SourceLocation</span><span class="sxs-lookup"><span data-stu-id="1eb6c-117">SourceLocation</span></span> |<span data-ttu-id="1eb6c-118">パッケージ ソースの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-118">Specifies the URI of the package source.</span></span> |
|<span data-ttu-id="1eb6c-119">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="1eb6c-119">InstallationPolicy</span></span> |<span data-ttu-id="1eb6c-120">組み込みの Nuget プロバイダーなどのプロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-120">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="1eb6c-121">パッケージのソースを信頼するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-121">Determines whether you trust the package's source.</span></span> <span data-ttu-id="1eb6c-122">つぎのいずれかです。**Untrusted** または **Trusted**。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-122">One of: **Untrusted** or **Trusted**.</span></span> |
|<span data-ttu-id="1eb6c-123">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="1eb6c-123">SourceCredential</span></span> |<span data-ttu-id="1eb6c-124">リモート ソースのパッケージへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-124">Provides access to the package on a remote source.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="1eb6c-125">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="1eb6c-125">Common properties</span></span>

|<span data-ttu-id="1eb6c-126">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1eb6c-126">Property</span></span> |<span data-ttu-id="1eb6c-127">説明</span><span class="sxs-lookup"><span data-stu-id="1eb6c-127">Description</span></span> |
|---|---|
|<span data-ttu-id="1eb6c-128">DependsOn</span><span class="sxs-lookup"><span data-stu-id="1eb6c-128">DependsOn</span></span> |<span data-ttu-id="1eb6c-129">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-129">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="1eb6c-130">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-130">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="1eb6c-131">Ensure</span><span class="sxs-lookup"><span data-stu-id="1eb6c-131">Ensure</span></span> |<span data-ttu-id="1eb6c-132">パッケージ ソースを登録または登録解除するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-132">Determines whether the package source is to be registered or unregistered.</span></span> <span data-ttu-id="1eb6c-133">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-133">The default value is **Present**.</span></span> |
|<span data-ttu-id="1eb6c-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="1eb6c-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="1eb6c-135">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="1eb6c-136">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="1eb6c-137">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="1eb6c-138">例</span><span class="sxs-lookup"><span data-stu-id="1eb6c-138">Example</span></span>

<span data-ttu-id="1eb6c-139">この例では、**PackageManagementSource** DSC リソースを使用して `https://nuget.org` パッケージ ソースを登録しています。</span><span class="sxs-lookup"><span data-stu-id="1eb6c-139">This example registers the `https://nuget.org` package source using the **PackageManagementSource** DSC resource.</span></span>

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