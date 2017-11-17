---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: "ギャラリー, PowerShell, コマンドレット, PSGet"
title: Find-Command
ms.openlocfilehash: f867f12b1c6efad30a04581c6f36c5a77a2fb2ae
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="find-command"></a><span data-ttu-id="bc689-103">Find-Command</span><span class="sxs-lookup"><span data-stu-id="bc689-103">Find-Command</span></span>

<span data-ttu-id="bc689-104">モジュール内の PowerShell コマンドを検索します。</span><span class="sxs-lookup"><span data-stu-id="bc689-104">Finds PowerShell commands in modules.</span></span>

## <a name="description"></a><span data-ttu-id="bc689-105">説明</span><span class="sxs-lookup"><span data-stu-id="bc689-105">Description</span></span>
<span data-ttu-id="bc689-106">Find-Command コマンドレットは、コマンドレット、エイリアス、関数、ワークフローなどの PowerShell コマンドを検索します。</span><span class="sxs-lookup"><span data-stu-id="bc689-106">The Find-Command cmdlet finds PowerShell commands such as cmdlets, aliases, functions, and workflows.</span></span> <span data-ttu-id="bc689-107">Find-Command は、登録されているリポジトリ内のモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="bc689-107">Find-Command searches modules in registered repositories.</span></span>
<span data-ttu-id="bc689-108">このコマンドレットが検索するコマンドごとに、PSGetCommandInfo オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="bc689-108">For each command that this cmdlet finds, it returns a PSGetCommandInfo object.</span></span> <span data-ttu-id="bc689-109">PSGetCommandInfo オブジェクトを Install-Module コマンドレットに渡して、コマンドを含むモジュールをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bc689-109">You can pass a PSGetCommandInfo object to the Install-Module cmdlet to install the module that contains the command.</span></span>

- <span data-ttu-id="bc689-110">Find-Command は、次のバージョン パラメーターでフィルター処理できます。MinimumVersion、RequiredVersion、AllVersions。</span><span class="sxs-lookup"><span data-stu-id="bc689-110">Find-Command can filter with version parameters: MinimumVersion, RequiredVersion, AllVersions.</span></span>
  - <span data-ttu-id="bc689-111">これらのパラメーターは同時に指定できません。</span><span class="sxs-lookup"><span data-stu-id="bc689-111">These parameters are mutually exclusive.</span></span>
  - <span data-ttu-id="bc689-112">これらのバージョン パラメーターは、ワイルドカードを含まない 1 つのモジュール名が指定されている場合にのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="bc689-112">These version parameters are allowed only with the single module name without any wildcards.</span></span>
  - <span data-ttu-id="bc689-113">RequiredVersion パラメーターが指定されていない場合、Find-Command は指定された最小バージョン以上の最新バージョンのモジュールを返すか、または最新バージョンのモジュールを返します (最小バージョンが指定されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="bc689-113">If the RequiredVersion parameter is not specified, Find-Command returns the latest version of the module that is equal to or greater than the minimum version specified or the latest version of the module if no minimum version is specified.</span></span>
  - <span data-ttu-id="bc689-114">RequiredVersion パラメーターが指定されている場合、Find-Command は指定したバージョンに完全に一致するバージョンのモジュールのみを返します。</span><span class="sxs-lookup"><span data-stu-id="bc689-114">If the RequiredVersion parameter is specified, Find-Command only returns the version of the module that exactly matches the specified version.</span></span>
- <span data-ttu-id="bc689-115">Find-Command では、-Tag パラメーターを使用してモジュールのメタデータをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="bc689-115">Find-Command can filter on module metadata with the -Tag parameter</span></span>
- <span data-ttu-id="bc689-116">Find-Command では、-Filter パラメーターを使用してリポジトリ固有の検索言語をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="bc689-116">Find-Command can filter on repository-specific search language with the -Filter parameter.</span></span>
- <span data-ttu-id="bc689-117">Find-Command では、登録されているリポジトリのすべてまたは一部からモジュール上でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="bc689-117">Find-Command can filter on modules from all or few of the registered repositories.</span></span>

## <a name="cmdlet-syntax"></a><span data-ttu-id="bc689-118">コマンドレット構文</span><span class="sxs-lookup"><span data-stu-id="bc689-118">Cmdlet syntax</span></span>
```powershell
Get-Command -Name Find-Command -Module PowerShellGet -Syntax
```

## <a name="cmdlet-online-help-reference"></a><span data-ttu-id="bc689-119">コマンドレット オンライン ヘルプ リファレンス</span><span class="sxs-lookup"><span data-stu-id="bc689-119">Cmdlet online help reference</span></span>

[<span data-ttu-id="bc689-120">Find-Command</span><span class="sxs-lookup"><span data-stu-id="bc689-120">Find-Command</span></span>](http://go.microsoft.com/fwlink/?LinkId=733636)

## <a name="example-commands"></a><span data-ttu-id="bc689-121">コマンド例</span><span class="sxs-lookup"><span data-stu-id="bc689-121">Example commands</span></span>
```powershell

# Find a specific command
Find-Command -Name Get-ScriptAnalyzerRule

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
Get-ScriptAnalyzerRule              1.5.0      PSScriptAnalyzer                    PSGallery

# Find multiple commands
Find-Command -Name Get-ScriptAnalyzerRule, Invoke-ScriptAnalyzer

# Find all available commands from all registered repositories
Find-Command

# Find available commands from few registered repositories
Find-Command -Repository PSGallery,PrivatePSGallery

# Find all commands in a specified repository
Find-Command -Repository PSGallery

# Find a command defined in a specific module
Find-Command -Name Get-ScriptAnalyzerRule -Module PSScriptAnalyzer

# Find commands from all versions of a module
Find-Command -ModuleName PSReadline -AllVersions

# Find commands with module name and MinimumVersion.
Find-Command -ModuleName PSReadline -MinimumVersion 1.1

# Find commands with module name and exact version
Find-Command -ModuleName AzureRM -RequiredVersion 1.4.0

# Find commands defined modules with -Filter based search. -Filter searches in description and module names
Find-Command -Filter Cookbook
Find-Command -Filter RBAC

# Find all commands with tags Azure or DSC in module metadata
Find-Command -Tag Azure, DSC

```

