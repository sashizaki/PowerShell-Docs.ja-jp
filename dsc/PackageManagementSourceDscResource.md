---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC の PackageManagementSource リソース
ms.openlocfilehash: 3e67cec9058ecb0e43f882f98f5ec8b92e261a09
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="dsc-packagemanagementsource-resource"></a><span data-ttu-id="40c01-103">DSC の PackageManagementSource リソース</span><span class="sxs-lookup"><span data-stu-id="40c01-103">DSC PackageManagementSource Resource</span></span>

> <span data-ttu-id="40c01-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="40c01-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="40c01-105">Windows PowerShell Desired State Configuration (DSC) の **PackageManagementSource** リソースは、ターゲット ノードで Package Management ソースを登録または登録解除するメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="40c01-105">The **PackageManagementSource** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to register or unregister Package Management sources on a target node.</span></span> <span data-ttu-id="40c01-106">**この方法で登録された Package Management ソースは System コンテキストで登録されるため、System アカウントまたは DSC エンジンで使用することができます。**</span><span class="sxs-lookup"><span data-stu-id="40c01-106">**Package Management sources registered in this way are registered under the System context, usable by the System account or by the DSC engine.**</span></span> <span data-ttu-id="40c01-107">このリソースには **PackageManagement** モジュールが必要です。これは、http://PowerShellGallery.com から入手できます。</span><span class="sxs-lookup"><span data-stu-id="40c01-107">This resource requires the **PackageManagement** module, available from http://PowerShellGallery.com.</span></span>

## <a name="syntax"></a><span data-ttu-id="40c01-108">構文</span><span class="sxs-lookup"><span data-stu-id="40c01-108">Syntax</span></span>

```
PSModule [string] #ResourceName
{
    Name = [string]
    [ Ensure = [string] { Absent | Present }  ]
    [ InstallationPolicy = [string] ]
    [ ProviderName = [string] ]
    [ SourceUri = [string] ]
    [ SourceCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="40c01-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40c01-109">Properties</span></span>
|  <span data-ttu-id="40c01-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="40c01-110">Property</span></span>  |  <span data-ttu-id="40c01-111">説明</span><span class="sxs-lookup"><span data-stu-id="40c01-111">Description</span></span>   |
|---|---|
| <span data-ttu-id="40c01-112">名前</span><span class="sxs-lookup"><span data-stu-id="40c01-112">Name</span></span>| <span data-ttu-id="40c01-113">システムで登録または登録解除するパッケージ ソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="40c01-113">Specifies the name of the package source to be registered or unregistered on your system.</span></span>|
| <span data-ttu-id="40c01-114">Ensure</span><span class="sxs-lookup"><span data-stu-id="40c01-114">Ensure</span></span>| <span data-ttu-id="40c01-115">パッケージ ソースを登録または登録解除するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="40c01-115">Determines whether the package source is to be registered or unregistered.</span></span>|
| <span data-ttu-id="40c01-116">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="40c01-116">InstallationPolicy</span></span>| <span data-ttu-id="40c01-117">パッケージ ソースを信頼するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="40c01-117">Determines whether you trust the package source.</span></span> <span data-ttu-id="40c01-118">"Untrusted" または "Trusted" のどちらかです。</span><span class="sxs-lookup"><span data-stu-id="40c01-118">One of: "Untrusted", "Trusted".</span></span>|
| <span data-ttu-id="40c01-119">ProviderName</span><span class="sxs-lookup"><span data-stu-id="40c01-119">ProviderName</span></span>| <span data-ttu-id="40c01-120">パッケージ ソースとの相互運用に使用できる OneGet プロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="40c01-120">Specifies the name of the OneGet provider through which you can interop with the package source.</span></span>|
| <span data-ttu-id="40c01-121">SourceUri</span><span class="sxs-lookup"><span data-stu-id="40c01-121">SourceUri</span></span>| <span data-ttu-id="40c01-122">パッケージ ソースの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="40c01-122">Specifies the URI of the package source.</span></span>|
| <span data-ttu-id="40c01-123">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="40c01-123">SourceCredential</span></span>| <span data-ttu-id="40c01-124">リモート ソースのパッケージへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="40c01-124">Provides access to the package on a remote source.</span></span>|

## <a name="example"></a><span data-ttu-id="40c01-125">例</span><span class="sxs-lookup"><span data-stu-id="40c01-125">Example</span></span>

<span data-ttu-id="40c01-126">この例では、**PackageManagementSource** DSC リソースを使用して http://nuget.org パッケージ ソースを登録しています。</span><span class="sxs-lookup"><span data-stu-id="40c01-126">This example registers the http://nuget.org package source using the **PackageManagementSource** DSC resource.</span></span>

```powershell
Configuration PackageManagementSourceTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceUri   = "http://nuget.org/api/v2/"
        InstallationPolicy ="Trusted"
    }
}
```