---
ms.date: 06/20/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC の PackageManagementSource リソース
ms.openlocfilehash: e51b5318288bef458567dd4b58d17caaea3ed69b
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047526"
---
# <a name="dsc-packagemanagementsource-resource"></a><span data-ttu-id="cb691-103">DSC の PackageManagementSource リソース</span><span class="sxs-lookup"><span data-stu-id="cb691-103">DSC PackageManagementSource Resource</span></span>

> <span data-ttu-id="cb691-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0、Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="cb691-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0, Windows PowerShell 5.1</span></span>

<span data-ttu-id="cb691-105">Windows PowerShell Desired State Configuration (DSC) の **PackageManagementSource** リソースは、ターゲット ノードで Package Management ソースを登録または登録解除するメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="cb691-105">The **PackageManagementSource** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to register or unregister Package Management sources on a target node.</span></span> <span data-ttu-id="cb691-106">**この方法で登録された Package Management ソースは System コンテキストで登録されるため、System アカウントまたは DSC エンジンで使用することができます。**</span><span class="sxs-lookup"><span data-stu-id="cb691-106">**Package Management sources registered in this way are registered under the System context, usable by the System account or by the DSC engine.**</span></span> <span data-ttu-id="cb691-107">このリソースには **PackageManagement** モジュールが必要です。これは、 http://PowerShellGallery.com から入手できます。</span><span class="sxs-lookup"><span data-stu-id="cb691-107">This resource requires the **PackageManagement** module, available from http://PowerShellGallery.com.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb691-108">**PackageManagement** モジュールは、次のプロパティ情報が適切であるようにバージョン 1.1.7.0 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb691-108">The **PackageManagement** module should be at least version 1.1.7.0 for the following property information to be correct.</span></span>

## <a name="syntax"></a><span data-ttu-id="cb691-109">構文</span><span class="sxs-lookup"><span data-stu-id="cb691-109">Syntax</span></span>

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

## <a name="properties"></a><span data-ttu-id="cb691-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="cb691-110">Properties</span></span>

|  <span data-ttu-id="cb691-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="cb691-111">Property</span></span>  |  <span data-ttu-id="cb691-112">説明</span><span class="sxs-lookup"><span data-stu-id="cb691-112">Description</span></span>   |
|---|---|
| <span data-ttu-id="cb691-113">名前</span><span class="sxs-lookup"><span data-stu-id="cb691-113">Name</span></span>| <span data-ttu-id="cb691-114">システムで登録または登録解除するパッケージ ソースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb691-114">Specifies the name of the package source to be registered or unregistered on your system.</span></span>|
| <span data-ttu-id="cb691-115">ProviderName</span><span class="sxs-lookup"><span data-stu-id="cb691-115">ProviderName</span></span>| <span data-ttu-id="cb691-116">パッケージ ソースとの相互運用に使用できる OneGet プロバイダーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb691-116">Specifies the name of the OneGet provider through which you can interop with the package source.</span></span>|
| <span data-ttu-id="cb691-117">SourceLocation</span><span class="sxs-lookup"><span data-stu-id="cb691-117">SourceLocation</span></span>| <span data-ttu-id="cb691-118">パッケージ ソースの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb691-118">Specifies the URI of the package source.</span></span>|
| <span data-ttu-id="cb691-119">Ensure</span><span class="sxs-lookup"><span data-stu-id="cb691-119">Ensure</span></span>| <span data-ttu-id="cb691-120">パッケージ ソースを登録または登録解除するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="cb691-120">Determines whether the package source is to be registered or unregistered.</span></span>|
| <span data-ttu-id="cb691-121">InstallationPolicy</span><span class="sxs-lookup"><span data-stu-id="cb691-121">InstallationPolicy</span></span>| <span data-ttu-id="cb691-122">組み込みの Nuget プロバイダーなどのプロバイダーによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="cb691-122">Used by providers such as the built-in Nuget Provider.</span></span> <span data-ttu-id="cb691-123">パッケージのソースを信頼するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="cb691-123">Determines whether you trust the package's source.</span></span> <span data-ttu-id="cb691-124"> または  のどちらかです。「信頼されていない」、「信頼済み」です。</span><span class="sxs-lookup"><span data-stu-id="cb691-124">One of: "Untrusted", "Trusted".</span></span>|
| <span data-ttu-id="cb691-125">SourceCredential</span><span class="sxs-lookup"><span data-stu-id="cb691-125">SourceCredential</span></span>| <span data-ttu-id="cb691-126">リモート ソースのパッケージへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="cb691-126">Provides access to the package on a remote source.</span></span>|

## <a name="example"></a><span data-ttu-id="cb691-127">例</span><span class="sxs-lookup"><span data-stu-id="cb691-127">Example</span></span>

<span data-ttu-id="cb691-128">この例では、**PackageManagementSource** DSC リソースを使用して http://nuget.org パッケージ ソースを登録しています。</span><span class="sxs-lookup"><span data-stu-id="cb691-128">This example registers the http://nuget.org package source using the **PackageManagementSource** DSC resource.</span></span>

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