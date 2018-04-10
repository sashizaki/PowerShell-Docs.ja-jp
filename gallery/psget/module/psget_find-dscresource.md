---
ms.date: 06/12/2017
contributor: manikb
ms.topic: reference
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: Find-DscResource
ms.openlocfilehash: 522a44e25c57a7dd75a098a1f34e53e74d96f4a6
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="find-dscresource"></a><span data-ttu-id="1a728-103">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="1a728-103">Find-DscResource</span></span>

<span data-ttu-id="1a728-104">モジュール内の DSC リソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="1a728-104">Finds DSC Resources in modules.</span></span>

## <a name="description"></a><span data-ttu-id="1a728-105">説明</span><span class="sxs-lookup"><span data-stu-id="1a728-105">Description</span></span>

<span data-ttu-id="1a728-106">Find-DscResource コマンドレットは、登録したリポジトリから、指定した条件と一致するモジュールに含まれている [Desired State Configuration (DSC)](https://msdn.microsoft.com/PowerShell/dsc/overview) リソースを検索します。</span><span class="sxs-lookup"><span data-stu-id="1a728-106">The Find-DscResource cmdlet finds [Desired State Configuration (DSC)](https://msdn.microsoft.com/PowerShell/dsc/overview) resources contained in modules that match the specified criteria from registered repositories.</span></span>
<span data-ttu-id="1a728-107">Find-DscResource は、このコマンドレットが検出した各モジュールに対して PSGetDscResourceInfo オブジェクトを返します。このオブジェクトを Install-Module にパイプすると、このコマンドレットから返されたリソースを含むモジュールをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="1a728-107">For each module that this cmdlet finds, Find-DscResource returns a PSGetDscResourceInfo object that you can pipe to Install-Module to install the modules containing the resources that this cmdlet returns.</span></span>

<span data-ttu-id="1a728-108">DSC は、ソフトウェア サービスの構成データを展開および管理し、これらのサービスの実行環境を管理できる、Windows PowerShell の新しい管理プラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="1a728-108">DSC is a new management platform in Windows PowerShell that enables deploying and managing configuration data for software services and managing the environment in which these services run.</span></span>

<span data-ttu-id="1a728-109">Desired State Configuration (DSC) リソースは、DSC 構成の構成要素を提供します。</span><span class="sxs-lookup"><span data-stu-id="1a728-109">Desired State Configuration (DSC) Resources provide the building blocks for a DSC configuration.</span></span> <span data-ttu-id="1a728-110">リソースは、構成 (スキーマ) 可能なプロパティを公開し、また、指定されたことを実現するためにローカル構成マネージャー (LCM) が呼び出す PowerShell スクリプト関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a728-110">A resource exposes properties that can be configured (schema) and contains the PowerShell script functions that the Local Configuration Manager (LCM) calls to "make it so".</span></span>

<span data-ttu-id="1a728-111">リソースでは、ファイルのように汎用的なものをモデル化したり、IIS サーバー設定のように具体的なものをモデル化したりできます。</span><span class="sxs-lookup"><span data-stu-id="1a728-111">A resource can model something as generic as a file or as specific as an IIS server setting.</span></span> <span data-ttu-id="1a728-112">リソースなどのグループは、DSC モジュールに結合されます。DSC モジュールでは、リソースの使用目的を識別するためのメタデータが含まれている移植可能な構造にすべての必須ファイルが編成されます。</span><span class="sxs-lookup"><span data-stu-id="1a728-112">Groups of like resources are combined in to a DSC Module, which organizes all the required files in to a structure that is portable and includes metadata to identify how the resources are intended to be used.</span></span>

- <span data-ttu-id="1a728-113">Find-DscResource は、次のバージョン パラメーターでフィルター処理できます。MinimumVersion、RequiredVersion、AllVersions。</span><span class="sxs-lookup"><span data-stu-id="1a728-113">Find-DscResource can filter with version parameters: MinimumVersion, RequiredVersion, AllVersions.</span></span>
  - <span data-ttu-id="1a728-114">これらのパラメーターは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="1a728-114">These parameters are mutually exclusive.</span></span>
  - <span data-ttu-id="1a728-115">これらのバージョン パラメーターは、ワイルドカードを含まない 1 つのモジュール名が指定されている場合にのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="1a728-115">These version parameters are allowed only with the single module name without any wildcards.</span></span>
  - <span data-ttu-id="1a728-116">RequiredVersion パラメーターが指定されていない場合、Find-DscResource は指定された最小バージョン以上の最新バージョンのモジュールを返すか、または最新バージョンのモジュールを返します (最小バージョンが指定されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="1a728-116">If the RequiredVersion parameter is not specified, Find-DscResource returns the latest version of the module that is equal to or greater than the minimum version specified or the latest version of the module if no minimum version is specified.</span></span>
  - <span data-ttu-id="1a728-117">RequiredVersion パラメーターが指定されている場合、Find-DscResource は指定したバージョンに完全に一致するバージョンのモジュールのみを返します。</span><span class="sxs-lookup"><span data-stu-id="1a728-117">If the RequiredVersion parameter is specified, Find-DscResource only returns the version of the module that exactly matches the specified version.</span></span>
- <span data-ttu-id="1a728-118">Find-DscResource では、-Tag パラメーターを使用してモジュールのメタデータをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="1a728-118">Find-DscResource can filter on module metadata with the -Tag parameter</span></span>
- <span data-ttu-id="1a728-119">Find-DscResource では、-Filter パラメーターを使用してリポジトリ固有の検索言語をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="1a728-119">Find-DscResource can filter on repository-specific search language with the -Filter parameter.</span></span>
- <span data-ttu-id="1a728-120">Find-DscResource では、登録されているリポジトリのすべてまたは一部からモジュール上でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="1a728-120">Find-DscResource can filter on modules from all or few of the registered repositories.</span></span>

## <a name="cmdlet-syntax"></a><span data-ttu-id="1a728-121">コマンドレット構文</span><span class="sxs-lookup"><span data-stu-id="1a728-121">Cmdlet syntax</span></span>
```powershell
Get-Command -Name Find-DscResource -Module PowerShellGet -Syntax
```

## <a name="cmdlet-online-help-reference"></a><span data-ttu-id="1a728-122">コマンドレット オンライン ヘルプ リファレンス</span><span class="sxs-lookup"><span data-stu-id="1a728-122">Cmdlet online help reference</span></span>

[<span data-ttu-id="1a728-123">Find-DscResource</span><span class="sxs-lookup"><span data-stu-id="1a728-123">Find-DscResource</span></span>](http://go.microsoft.com/fwlink/?LinkId=517196)

## <a name="example-commands"></a><span data-ttu-id="1a728-124">コマンド例</span><span class="sxs-lookup"><span data-stu-id="1a728-124">Example commands</span></span>
```powershell

# Find a specific DSC Resource
Find-DscResource -Name xIisFeatureDelegation

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
xIisFeatureDelegation               1.10.0.0   xWebAdministration                  PSGallery

# Find all available DSC Resources from all registered repositories
Find-DscResource

# Find a DSC resource by name
Find-DscResource -Name xWebsite

# Find multiple DSC Resources
Find-DscResource -Name xIisHandler, xFirewall

# Find all DSC resources contained within a specific module
Find-DscResource -ModuleName xNetworking
Find-DscResource -ModuleName xWebAdministration

# Find all DSC resources in modules with DSCResourceKit or DesiredStateConfiguration
Find-DscResource -Tag DesiredStateConfiguration, DSCResourceKit

# Find available DSC Resources from few registered repositories
Find-DscResource -Repository PSGallery,PrivatePSGallery

# Find all DSC Resources in a specified repository
Find-DscResource -Repository PSGallery

# Find DSC Resources from all versions of a module
Find-DscResource -ModuleName xNetworking -AllVersions

# Find DSC Resources with module name and MinimumVersion.
Find-DscResource -ModuleName xNetworking -MinimumVersion 1.1

# Find DSC Resources with module name and exact version
Find-DscResource -ModuleName xNetworking -RequiredVersion 2.1.1

# Find DSC Resources defined modules with -Filter based search. -Filter searches in description and module names
Find-DscResource -Filter Domain

# Find all DSC Resources with tags Azure or DSC in module metadata
Find-DscResource -Tag Azure, DSC

```