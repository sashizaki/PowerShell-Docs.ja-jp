---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-psrepository?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSRepository
ms.openlocfilehash: 66f840d99b107da22b6771e6327ab68d33a1b368
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599540"
---
# <span data-ttu-id="b3aff-102">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b3aff-102">Get-PSRepository</span></span>

## <span data-ttu-id="b3aff-103">概要</span><span class="sxs-lookup"><span data-stu-id="b3aff-103">SYNOPSIS</span></span>
<span data-ttu-id="b3aff-104">PowerShell リポジトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="b3aff-104">Gets PowerShell repositories.</span></span>

## <span data-ttu-id="b3aff-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b3aff-105">SYNTAX</span></span>

```
Get-PSRepository [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="b3aff-106">Description</span><span class="sxs-lookup"><span data-stu-id="b3aff-106">DESCRIPTION</span></span>

<span data-ttu-id="b3aff-107">**Register-psrepository** コマンドレットは、現在のユーザーに登録されている PowerShell モジュールリポジトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="b3aff-107">The **Get-PSRepository** cmdlet gets PowerShell module repositories that are registered for the current user.</span></span>

## <span data-ttu-id="b3aff-108">例</span><span class="sxs-lookup"><span data-stu-id="b3aff-108">EXAMPLES</span></span>

### <span data-ttu-id="b3aff-109">例 1: すべてのモジュールリポジトリを取得する</span><span class="sxs-lookup"><span data-stu-id="b3aff-109">Example 1: Get all module repositories</span></span>

```
PS C:\> Get-PSRepository
Name                                     SourceLocation                                     OneGetProvider       InstallationPolicy
----                                     --------------                                     --------------       ------------------
PSGallery                                http://go.micro...                                 NuGet                Untrusted
myNuGetSource                            https://myget.c...                                 NuGet                Trusted
```

<span data-ttu-id="b3aff-110">このコマンドは、現在のユーザーに対して登録されているすべてのモジュールリポジトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="b3aff-110">This command gets all module repositories registered for the current user.</span></span>

### <span data-ttu-id="b3aff-111">例 2: 名前を指定してモジュールリポジトリを取得する</span><span class="sxs-lookup"><span data-stu-id="b3aff-111">Example 2: Get module repositories by name</span></span>

```
PS C:\> Get-PSRepository -Name "*NuGet*"
```

<span data-ttu-id="b3aff-112">このコマンドは、名前に NuGet を含むすべてのモジュールリポジトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="b3aff-112">This command gets all module repositories that include NuGet in their names.</span></span>

### <span data-ttu-id="b3aff-113">例 3: モジュールリポジトリを取得し、出力を書式設定する</span><span class="sxs-lookup"><span data-stu-id="b3aff-113">Example 3: Get a module repository and format the output</span></span>

```
PS C:\> Get-PSRepository -Name "Local01" | Format-List * -Force
Name                      : local01
SourceLocation            : http://manikb-dev:8765/api/v2/
Trusted                   : True
Registered                : True
InstallationPolicy        : Trusted
PackageManagementProvider : NuGet
PublishLocation           : http://pattif-dev:8765/api/v2/package/
ScriptSourceLocation      : http://pattif-dev:8765/api/v2/artifacts/psscript
ScriptPublishLocation     : http://pattif-dev:8765/api/v2/package/
ProviderOptions           : {}
```

<span data-ttu-id="b3aff-114">このコマンドは、Local01 という名前のリポジトリを取得し、パイプライン演算子を使用してそのオブジェクトを Format-List コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="b3aff-114">This command gets the repository named Local01 and uses the pipeline operator to pass that object to the Format-List cmdlet.</span></span>

## <span data-ttu-id="b3aff-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b3aff-115">PARAMETERS</span></span>

### <span data-ttu-id="b3aff-116">-Name</span><span class="sxs-lookup"><span data-stu-id="b3aff-116">-Name</span></span>

<span data-ttu-id="b3aff-117">取得するリポジトリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b3aff-117">Specifies the names of the repositories to get.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b3aff-118">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b3aff-118">CommonParameters</span></span>

<span data-ttu-id="b3aff-119">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b3aff-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b3aff-120">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3aff-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b3aff-121">入力</span><span class="sxs-lookup"><span data-stu-id="b3aff-121">INPUTS</span></span>

### <span data-ttu-id="b3aff-122">System.String[]</span><span class="sxs-lookup"><span data-stu-id="b3aff-122">System.String[]</span></span>

## <span data-ttu-id="b3aff-123">出力</span><span class="sxs-lookup"><span data-stu-id="b3aff-123">OUTPUTS</span></span>

### <span data-ttu-id="b3aff-124">System.Object</span><span class="sxs-lookup"><span data-stu-id="b3aff-124">System.Object</span></span>

## <span data-ttu-id="b3aff-125">注</span><span class="sxs-lookup"><span data-stu-id="b3aff-125">NOTES</span></span>

## <span data-ttu-id="b3aff-126">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b3aff-126">RELATED LINKS</span></span>

[<span data-ttu-id="b3aff-127">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b3aff-127">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="b3aff-128">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b3aff-128">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="b3aff-129">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b3aff-129">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)

