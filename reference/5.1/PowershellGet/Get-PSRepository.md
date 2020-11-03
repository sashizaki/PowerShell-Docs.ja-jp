---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-psrepository?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSRepository
ms.openlocfilehash: e86f06b5e2ebbf51431e362af87b22ba4bd9c30d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215248"
---
# <span data-ttu-id="470fe-103">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="470fe-103">Get-PSRepository</span></span>

## <span data-ttu-id="470fe-104">概要</span><span class="sxs-lookup"><span data-stu-id="470fe-104">SYNOPSIS</span></span>
<span data-ttu-id="470fe-105">PowerShell リポジトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="470fe-105">Gets PowerShell repositories.</span></span>

## <span data-ttu-id="470fe-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="470fe-106">SYNTAX</span></span>

```
Get-PSRepository [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="470fe-107">Description</span><span class="sxs-lookup"><span data-stu-id="470fe-107">DESCRIPTION</span></span>
<span data-ttu-id="470fe-108">**Register-psrepository** コマンドレットは、現在のユーザーに登録されている PowerShell モジュールリポジトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="470fe-108">The **Get-PSRepository** cmdlet gets PowerShell module repositories that are registered for the current user.</span></span>

## <span data-ttu-id="470fe-109">例</span><span class="sxs-lookup"><span data-stu-id="470fe-109">EXAMPLES</span></span>

### <span data-ttu-id="470fe-110">例 1: すべてのモジュールリポジトリを取得する</span><span class="sxs-lookup"><span data-stu-id="470fe-110">Example 1: Get all module repositories</span></span>

```
PS C:\> Get-PSRepository
Name                                     SourceLocation                                     OneGetProvider       InstallationPolicy
----                                     --------------                                     --------------       ------------------
PSGallery                                http://go.micro...                                 NuGet                Untrusted
myNuGetSource                            https://myget.c...                                 NuGet                Trusted
```

<span data-ttu-id="470fe-111">このコマンドは、現在のユーザーに対して登録されているすべてのモジュールリポジトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="470fe-111">This command gets all module repositories registered for the current user.</span></span>

### <span data-ttu-id="470fe-112">例 2: 名前を指定してモジュールリポジトリを取得する</span><span class="sxs-lookup"><span data-stu-id="470fe-112">Example 2: Get module repositories by name</span></span>

```
PS C:\> Get-PSRepository -Name "*NuGet*"
```

<span data-ttu-id="470fe-113">このコマンドは、名前に NuGet を含むすべてのモジュールリポジトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="470fe-113">This command gets all module repositories that include NuGet in their names.</span></span>

### <span data-ttu-id="470fe-114">例 3: モジュールリポジトリを取得し、出力を書式設定する</span><span class="sxs-lookup"><span data-stu-id="470fe-114">Example 3: Get a module repository and format the output</span></span>

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

<span data-ttu-id="470fe-115">このコマンドは、Local01 という名前のリポジトリを取得し、パイプライン演算子を使用してそのオブジェクトを Format-List コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="470fe-115">This command gets the repository named Local01 and uses the pipeline operator to pass that object to the Format-List cmdlet.</span></span>

## <span data-ttu-id="470fe-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="470fe-116">PARAMETERS</span></span>

### <span data-ttu-id="470fe-117">-Name</span><span class="sxs-lookup"><span data-stu-id="470fe-117">-Name</span></span>
<span data-ttu-id="470fe-118">取得するリポジトリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="470fe-118">Specifies the names of the repositories to get.</span></span>

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

### <span data-ttu-id="470fe-119">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="470fe-119">CommonParameters</span></span>
<span data-ttu-id="470fe-120">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="470fe-120">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="470fe-121">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="470fe-121">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="470fe-122">入力</span><span class="sxs-lookup"><span data-stu-id="470fe-122">INPUTS</span></span>

## <span data-ttu-id="470fe-123">出力</span><span class="sxs-lookup"><span data-stu-id="470fe-123">OUTPUTS</span></span>

## <span data-ttu-id="470fe-124">注</span><span class="sxs-lookup"><span data-stu-id="470fe-124">NOTES</span></span>

## <span data-ttu-id="470fe-125">関連リンク</span><span class="sxs-lookup"><span data-stu-id="470fe-125">RELATED LINKS</span></span>

[<span data-ttu-id="470fe-126">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="470fe-126">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="470fe-127">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="470fe-127">Set-PSRepository</span></span>](Set-PSRepository.md)

[<span data-ttu-id="470fe-128">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="470fe-128">Unregister-PSRepository</span></span>](Unregister-PSRepository.md)
