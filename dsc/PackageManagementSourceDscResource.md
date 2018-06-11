---
ms.date: 06/20/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC の PackageManagementSource リソース
ms.openlocfilehash: 5d049b05c387cafe27edb202d569852b10852dce
ms.sourcegitcommit: 01d6985ed190a222e9da1da41596f524f607a5bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753772"
---
# <a name="dsc-packagemanagementsource-resource"></a><span data-ttu-id="6eab8-103">DSC の PackageManagementSource リソース</span><span class="sxs-lookup"><span data-stu-id="6eab8-103">DSC PackageManagementSource Resource</span></span>

> <span data-ttu-id="6eab8-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0、Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="6eab8-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="6eab8-105">Windows PowerShell Desired State Configuration (DSC) の **PackageManagementSource** リソースは、ターゲット ノードで Package Management ソースを登録または登録解除するメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="6eab8-105">The **PackageManagementSource** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to register or unregister Package Management sources on a target node.</span></span> <span data-ttu-id="6eab8-106">**この方法で登録された Package Management ソースは System コンテキストで登録されるため、System アカウントまたは DSC エンジンで使用することができます。**</span><span class="sxs-lookup"><span data-stu-id="6eab8-106">**Package Management sources registered in this way are registered under the System context, usable by the System account or by the DSC engine.**</span></span> <span data-ttu-id="6eab8-107">このリソースには **PackageManagement** モジュールが必要です。これは、http://PowerShellGallery.com から入手できます。</span><span class="sxs-lookup"><span data-stu-id="6eab8-107">This resource requires the **PackageManagement** module, available from http://PowerShellGallery.com.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6eab8-108">**PackageManagement** モジュールは、次のプロパティ情報が適切であるようにバージョン 1.1.7.0 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6eab8-108">The **PackageManagement** module should be at least version 1.1.7.0 for the following property information to be correct.</span></span>

## <a name="syntax"></a><span data-ttu-id="6eab8-109">構文</span><span class="sxs-lookup"><span data-stu-id="6eab8-109">Syntax</span></span>

```
PackageManagementSource [String] #ResourceName
{
    Name = [string]
    ProviderName = [string]
    SourceLocation = [string]
    [DependsOn = [string[]]]
    [Ensure = [string]{ Absent | Present }]
    [InstallationPolicy = [string]{ Trusted | Untrusted }]
    [PsDscRunAsCredential = [PSCredential]]
    [SourceCredential = [PSCredential]]
}
```

## <a name="properties"></a><span data-ttu-id="6eab8-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6eab8-110">Properties</span></span>

|  <span data-ttu-id="6eab8-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6eab8-111">Property</span></span>  |  <span data-ttu-id="6eab8-112">説明</span><span class="sxs-lookup"><span data-stu-id="6eab8-112">Description</span></span>   |
|---|---|
| <span data-ttu-id="6eab8-113">名前</span><span class="sxs-lookup"><span data-stu-id="6eab8-113">Name</span></span>| <span data-ttu-id="6eab8-114">システムで登録または登録解除するパッケージ ソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6eab8-114">Specifies the name of the package source to be registered or unregistered on your system.</span></span>|
| <span data-ttu-id="6eab8-115">ProviderName</span><span class="sxs-lookup"><span data-stu-id="6eab8-115">ProviderName</span></span>| <span data-ttu-id="6eab8-116">パッケージ ソースとの相互運用に使用できる OneGet プロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6eab8-116">Specifies the name of the OneGet provider through which you can interop with the package source.</span></span>|
| <span data-ttu-id="6eab8-117">SourceLocation</span><span class="sxs-lookup"><span data-stu-id="6eab8-117">SourceLocation</span></span>| <span data-ttu-id="6eab8-118">パッケージ ソースの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="6eab8-118">Specifies the URI of the package source.</span></span>|
| <span data-ttu-id="6eab8-119">Ensure</span><span class="sxs-lookup"><span data-stu-id="6eab8-119">Ensure</span></span>| <span data-ttu-id="6eab8-120">パッケージ ソースを登録または登録解除するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="6eab8-120">Determines whether the package source is to be registered or unregistered.</span></span>|
| <span data-ttu-id="6eab8-121">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="6eab8-121">InstallationPolicy</span></span>| <span data-ttu-id="6eab8-122">組み込みの Nuget プロバイダーなどのプロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="6eab8-122">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="6eab8-123">パッケージのソースを信頼するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="6eab8-123">Determines whether you trust the package's source.</span></span> <span data-ttu-id="6eab8-124">"Untrusted" または "Trusted" のどちらかです。</span><span class="sxs-lookup"><span data-stu-id="6eab8-124">One of: "Untrusted", "Trusted".</span></span>|
| <span data-ttu-id="6eab8-125">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="6eab8-125">SourceCredential</span></span>| <span data-ttu-id="6eab8-126">リモート ソースのパッケージへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6eab8-126">Provides access to the package on a remote source.</span></span>|

## <a name="example"></a><span data-ttu-id="6eab8-127">例</span><span class="sxs-lookup"><span data-stu-id="6eab8-127">Example</span></span>

<span data-ttu-id="6eab8-128">この例では、**PackageManagementSource** DSC リソースを使用して http://nuget.org パッケージ ソースを登録しています。</span><span class="sxs-lookup"><span data-stu-id="6eab8-128">This example registers the http://nuget.org package source using the **PackageManagementSource** DSC resource.</span></span>

```powershell
Configuration PackageManagementSourceTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceLocation   = "http://nuget.org/api/v2/"
        InstallationPolicy ="Trusted"
    }
}
```