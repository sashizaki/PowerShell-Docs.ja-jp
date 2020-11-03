---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscresource?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscResource
ms.openlocfilehash: d710881f4444a35bd1dca7950292660889a3e38c
ms.sourcegitcommit: 9dddf1d2e91ebcd347fcfb7bf6ef670d49a12ab7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "93218984"
---
# <span data-ttu-id="32cf3-103">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="32cf3-103">Get-DscResource</span></span>

## <span data-ttu-id="32cf3-104">概要</span><span class="sxs-lookup"><span data-stu-id="32cf3-104">SYNOPSIS</span></span>
<span data-ttu-id="32cf3-105">コンピューターに存在する Desired State Configuration (DSC) リソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="32cf3-105">Gets Desired State Configuration (DSC) resources present on the computer.</span></span>

## <span data-ttu-id="32cf3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="32cf3-106">SYNTAX</span></span>

```
Get-DscResource [[-Name] <String[]>] [[-Module] <Object>] [-Syntax] [<CommonParameters>]
```

## <span data-ttu-id="32cf3-107">Description</span><span class="sxs-lookup"><span data-stu-id="32cf3-107">DESCRIPTION</span></span>

<span data-ttu-id="32cf3-108">この `Get-DscResource` コマンドレットは、コンピューター上に存在する POWERSHELL DSC リソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="32cf3-108">The `Get-DscResource` cmdlet retrieves the PowerShell DSC resources present on the computer.</span></span> <span data-ttu-id="32cf3-109">このコマンドレットは、PSModulePath にインストールされているリソースのみを検出します。</span><span class="sxs-lookup"><span data-stu-id="32cf3-109">This cmdlet discovers only the resources installed in the PSModulePath.</span></span> <span data-ttu-id="32cf3-110">これには、ユーザーが作成した組み込みプロバイダーとカスタムプロバイダーの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="32cf3-110">It shows the details about built-in and custom providers, which are created by the user.</span></span> <span data-ttu-id="32cf3-111">このコマンドレットは、モジュールとしてパッケージ化されているか、セッションで実行時に作成された他の構成である複合リソースの詳細も表示します。</span><span class="sxs-lookup"><span data-stu-id="32cf3-111">This cmdlet also shows details about composite resources, which are other configurations that are packaged as module or created at run time in the session.</span></span>

## <span data-ttu-id="32cf3-112">例</span><span class="sxs-lookup"><span data-stu-id="32cf3-112">EXAMPLES</span></span>

### <span data-ttu-id="32cf3-113">例 1: ローカルコンピューター上のすべてのリソースを取得する</span><span class="sxs-lookup"><span data-stu-id="32cf3-113">Example 1: Get all resources on the local computer</span></span>

```powershell
 Get-DscResource
```

<span data-ttu-id="32cf3-114">以下のコマンドは、ローカル コンピューター上のすべてのリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="32cf3-114">This command gets all the resources on the local computer.</span></span>

### <span data-ttu-id="32cf3-115">例 2: 名前を指定してリソースを取得する</span><span class="sxs-lookup"><span data-stu-id="32cf3-115">Example 2: Get a resource by specifying the name</span></span>

```powershell
Get-DscResource -Name "WindowsFeature"
```

<span data-ttu-id="32cf3-116">以下のコマンドは、WindowsFeature リソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="32cf3-116">This command gets the WindowsFeature resource.</span></span>

### <span data-ttu-id="32cf3-117">例 3: モジュールからすべてのリソースを取得する</span><span class="sxs-lookup"><span data-stu-id="32cf3-117">Example 3: Get all the resources from a module</span></span>

```powershell
Get-DscResource -Module "xHyper-V"
```

<span data-ttu-id="32cf3-118">このコマンドは、xHyper モジュールからすべてのリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="32cf3-118">This command gets all the resources from the xHyper-V module.</span></span>

### <span data-ttu-id="32cf3-119">例 4: ワイルドカード文字を使用してリソースを取得する</span><span class="sxs-lookup"><span data-stu-id="32cf3-119">Example 4: Get a resource by using wildcard characters</span></span>

```powershell
Get-DscResource -Name P*,r*
```

<span data-ttu-id="32cf3-120">このコマンドは、 **Name** パラメーターで指定されたワイルドカードパターンに一致するすべてのリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="32cf3-120">This command gets all resources that match the wildcard pattern specified by the **Name** parameter.</span></span>

### <span data-ttu-id="32cf3-121">例 5: リソースの構文を取得する</span><span class="sxs-lookup"><span data-stu-id="32cf3-121">Example 5: Get a resource syntax</span></span>

```powershell
Get-DscResource -Name "WindowsFeature" -Syntax
```

<span data-ttu-id="32cf3-122">以下のコマンドは、WindowsFeature リソースを取得し、リソースの構文を表示します。</span><span class="sxs-lookup"><span data-stu-id="32cf3-122">This command gets the WindowsFeature resource, and shows the syntax for the resource.</span></span>

### <span data-ttu-id="32cf3-123">例 6: リソースのすべてのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="32cf3-123">Example 6: Get all the properties for a resource</span></span>

```powershell
Get-DscResource -Name "User" | Select-Object -ExpandProperty Properties
```

<span data-ttu-id="32cf3-124">以下のコマンドは、User リソースを取得し、次にパイプライン演算子を使用して User リソースのすべてのプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="32cf3-124">This command gets the User resource, and then uses the pipeline operator to return all the properties for the User resource.</span></span>

### <span data-ttu-id="32cf3-125">例 7: 指定したバージョンの指定したモジュールからすべてのリソースを取得する</span><span class="sxs-lookup"><span data-stu-id="32cf3-125">Example 7: Get all the resources from a specified module with a specified version</span></span>

```powershell
Get-DscResource -Module @{ModuleName='xHyper-V';RequiredVersion='3.0.0.0'}
```

<span data-ttu-id="32cf3-126">このコマンドは、xHyper モジュールのバージョン3.0.0.0 ですべてのリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="32cf3-126">This command gets all the resources from xHyper-V module with version 3.0.0.0.</span></span>

## <span data-ttu-id="32cf3-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="32cf3-127">PARAMETERS</span></span>

### <span data-ttu-id="32cf3-128">-モジュール</span><span class="sxs-lookup"><span data-stu-id="32cf3-128">-Module</span></span>

<span data-ttu-id="32cf3-129">DSC リソースを表示するモジュールの名前または完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="32cf3-129">Specifies the name or fully qualified name of the module for which to view the DSC resource.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="32cf3-130">-Name</span><span class="sxs-lookup"><span data-stu-id="32cf3-130">-Name</span></span>

<span data-ttu-id="32cf3-131">表示する DSC リソースの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="32cf3-131">Specifies an array of names of the DSC resource to view.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="32cf3-132">-構文</span><span class="sxs-lookup"><span data-stu-id="32cf3-132">-Syntax</span></span>

<span data-ttu-id="32cf3-133">コマンドレットが、指定された DSC リソースの構文ビューを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="32cf3-133">Indicates that the cmdlet returns the syntax view of the specified DSC resources.</span></span> <span data-ttu-id="32cf3-134">返された構文は、PowerShell スクリプトでリソースを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="32cf3-134">The returned syntax shows how to use the resources in a PowerShell script.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="32cf3-135">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="32cf3-135">CommonParameters</span></span>

<span data-ttu-id="32cf3-136">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="32cf3-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="32cf3-137">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32cf3-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="32cf3-138">入力</span><span class="sxs-lookup"><span data-stu-id="32cf3-138">INPUTS</span></span>

### <span data-ttu-id="32cf3-139">System.String[]</span><span class="sxs-lookup"><span data-stu-id="32cf3-139">System.String[]</span></span>

### <span data-ttu-id="32cf3-140">System.Object</span><span class="sxs-lookup"><span data-stu-id="32cf3-140">System.Object</span></span>

## <span data-ttu-id="32cf3-141">出力</span><span class="sxs-lookup"><span data-stu-id="32cf3-141">OUTPUTS</span></span>

### <span data-ttu-id="32cf3-142">DesiredStateConfiguration []. DscResourceInfo []</span><span class="sxs-lookup"><span data-stu-id="32cf3-142">Microsoft.PowerShell.DesiredStateConfiguration.DscResourceInfo[]</span></span>

### <span data-ttu-id="32cf3-143">string[]</span><span class="sxs-lookup"><span data-stu-id="32cf3-143">string[]</span></span>

## <span data-ttu-id="32cf3-144">注</span><span class="sxs-lookup"><span data-stu-id="32cf3-144">NOTES</span></span>

## <span data-ttu-id="32cf3-145">関連リンク</span><span class="sxs-lookup"><span data-stu-id="32cf3-145">RELATED LINKS</span></span>

[<span data-ttu-id="32cf3-146">PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="32cf3-146">PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="32cf3-147">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="32cf3-147">Invoke-DscResource</span></span>](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource)