---
ms.date: 06/12/2017
contributor: manikb
ms.topic: reference
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: Find-RoleCapability
ms.openlocfilehash: 89aacd604d54f6a5e9752790be65cc3bcc77c8e1
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="find-rolecapability"></a><span data-ttu-id="37534-103">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="37534-103">Find-RoleCapability</span></span>

<span data-ttu-id="37534-104">モジュール内のロール機能を検索します。</span><span class="sxs-lookup"><span data-stu-id="37534-104">Finds role capabilities in modules.</span></span>

## <a name="description"></a><span data-ttu-id="37534-105">説明</span><span class="sxs-lookup"><span data-stu-id="37534-105">Description</span></span>
<span data-ttu-id="37534-106">Find-RoleCapability コマンドレットは、モジュール内の PowerShell ロール機能を検索します。</span><span class="sxs-lookup"><span data-stu-id="37534-106">The Find-RoleCapability cmdlet finds PowerShell role capabilities in modules.</span></span> <span data-ttu-id="37534-107">Find-RoleCapability は、登録されているリポジトリ内のモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="37534-107">Find-RoleCapability searches modules in registered repositories.</span></span>
<span data-ttu-id="37534-108">このコマンドレットが検索するロール機能ごとに、PSGetRoleCapabilityInfo オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="37534-108">For each role capability that this cmdlet finds, it returns a PSGetRoleCapabilityInfo object.</span></span> <span data-ttu-id="37534-109">PSGetRoleCapabilityInfo オブジェクトを Install-Module コマンドレットに渡して、ロール機能を含むモジュールをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="37534-109">You can pass a PSGetRoleCapabilityInfo object to the Install-Module cmdlet to install the module that contains the role capability.</span></span>
<span data-ttu-id="37534-110">PowerShell ロール機能は、Just Enough Administration (JEA) エンドポイントでユーザーが利用できるコマンド、アプリケーションなどを定義します。</span><span class="sxs-lookup"><span data-stu-id="37534-110">PowerShell role capabilities define which commands, applications, and so on are available to a user at a Just Enough Administration (JEA) endpoint.</span></span> <span data-ttu-id="37534-111">ロール機能は、拡張子が .psrc のファイルによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="37534-111">Role capabilities are defined by files with a .psrc extension.</span></span>

- <span data-ttu-id="37534-112">Find-RoleCapability は、次のバージョン パラメーターでフィルター処理できます。MinimumVersion、RequiredVersion、AllVersions。</span><span class="sxs-lookup"><span data-stu-id="37534-112">Find-RoleCapability can filter with version parameters: MinimumVersion, RequiredVersion, AllVersions.</span></span>
  - <span data-ttu-id="37534-113">これらのパラメーターは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="37534-113">These parameters are mutually exclusive.</span></span>
  - <span data-ttu-id="37534-114">これらのバージョン パラメーターは、ワイルドカードを含まない 1 つのモジュール名が指定されている場合にのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="37534-114">These version parameters are allowed only with the single module name without any wildcards.</span></span>
  - <span data-ttu-id="37534-115">RequiredVersion パラメーターが指定されていない場合、Find-RoleCapability は指定された最小バージョン以上の最新バージョンのモジュールを返すか、または最新バージョンのモジュールを返します (最小バージョンが指定されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="37534-115">If the RequiredVersion parameter is not specified, Find-RoleCapability returns the latest version of the module that is equal to or greater than the minimum version specified or the latest version of the module if no minimum version is specified.</span></span>
  - <span data-ttu-id="37534-116">RequiredVersion パラメーターが指定されている場合、Find-RoleCapability は指定したバージョンに完全に一致するバージョンのモジュールのみを返します。</span><span class="sxs-lookup"><span data-stu-id="37534-116">If the RequiredVersion parameter is specified, Find-RoleCapability only returns the version of the module that exactly matches the specified version.</span></span>
- <span data-ttu-id="37534-117">Find-RoleCapability では、-Tag パラメーターを使用してモジュールのメタデータをフィルター処理できます</span><span class="sxs-lookup"><span data-stu-id="37534-117">Find-RoleCapability can filter on module metadata with the -Tag parameter</span></span>
- <span data-ttu-id="37534-118">Find-RoleCapability では、-Filter パラメーターを使用してリポジトリ固有の検索言語をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="37534-118">Find-RoleCapability can filter on repository-specific search language with the -Filter parameter.</span></span>
- <span data-ttu-id="37534-119">Find-RoleCapability では、登録されているリポジトリのすべてまたは一部からモジュール上でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="37534-119">Find-RoleCapability can filter on modules from all or few of the registered repositories.</span></span>

## <a name="cmdlet-syntax"></a><span data-ttu-id="37534-120">コマンドレット構文</span><span class="sxs-lookup"><span data-stu-id="37534-120">Cmdlet syntax</span></span>
```powershell
Get-Command -Name Find-RoleCapability -Module PowerShellGet -Syntax
```

## <a name="cmdlet-online-help-reference"></a><span data-ttu-id="37534-121">コマンドレット オンライン ヘルプ リファレンス</span><span class="sxs-lookup"><span data-stu-id="37534-121">Cmdlet online help reference</span></span>

[<span data-ttu-id="37534-122">Find-RoleCapability</span><span class="sxs-lookup"><span data-stu-id="37534-122">Find-RoleCapability</span></span>](http://go.microsoft.com/fwlink/?LinkId=718029)

## <a name="example-commands"></a><span data-ttu-id="37534-123">コマンド例</span><span class="sxs-lookup"><span data-stu-id="37534-123">Example commands</span></span>
```powershell

# Find a specific role capability
Find-RoleCapability -Name Maintenance

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
Maintenance                         1.5.0      RoleCapModule                       PrivatePSGallery

# Find multiple role capabilities
Find-RoleCapability -Name MyJeaRole, Maintenance

# Find all available role capabilities from all registered repositories
Find-RoleCapability

# Find available role capabilities from few registered repositories
Find-RoleCapability -Repository PSGallery,PrivatePSGallery

# Find all role capabilities in a specified repository
Find-RoleCapability -Repository PSGallery

# Find a role capability defined in a specific module
Find-RoleCapability -Name Maintenance -ModuleName RoleCapModule

# Find role capabilities from all versions of a module
Find-RoleCapability -ModuleName RoleCapModule -AllVersions

# Find role capabilities with module name and MinimumVersion.
Find-RoleCapability -ModuleName RoleCapModule -MinimumVersion 1.1

# Find role capabilities with module name and exact version
Find-RoleCapability -ModuleName RoleCapModule -RequiredVersion 1.4.0

# Find role capabilities defined modules with -Filter based search. -Filter searches in description and module names
Find-RoleCapability -Filter Cookbook
Find-RoleCapability -Filter RBAC

# Find all role capabilities with tags Azure or DSC in module metadata
Find-RoleCapability -Tag Azure, DSC

```