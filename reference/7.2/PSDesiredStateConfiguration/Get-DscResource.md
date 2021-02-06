---
external help file: PSDesiredStateConfiguration-help.xml
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 07/23/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscresource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscResource
ms.openlocfilehash: dbc036562da0172dc4406f169891d2cd1c5e4098
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602402"
---
# <span data-ttu-id="a7a2e-102">Get-DscResource</span><span class="sxs-lookup"><span data-stu-id="a7a2e-102">Get-DscResource</span></span>

## <span data-ttu-id="a7a2e-103">概要</span><span class="sxs-lookup"><span data-stu-id="a7a2e-103">SYNOPSIS</span></span>
<span data-ttu-id="a7a2e-104">コンピューターに存在する Desired State Configuration (DSC) リソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-104">Gets Desired State Configuration (DSC) resources present on the computer.</span></span>

## <span data-ttu-id="a7a2e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a7a2e-105">SYNTAX</span></span>

```
Get-DscResource [[-Name] <String[]>] [[-Module] <Object>] [-Syntax] [<CommonParameters>]
```

## <span data-ttu-id="a7a2e-106">Description</span><span class="sxs-lookup"><span data-stu-id="a7a2e-106">DESCRIPTION</span></span>

<span data-ttu-id="a7a2e-107">この `Get-DscResource` コマンドレットは、コンピューター上に存在する POWERSHELL DSC リソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-107">The `Get-DscResource` cmdlet retrieves the PowerShell DSC resources present on the computer.</span></span> <span data-ttu-id="a7a2e-108">このコマンドレットは、PSModulePath にインストールされているリソースのみを検出します。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-108">This cmdlet discovers only the resources installed in the PSModulePath.</span></span> <span data-ttu-id="a7a2e-109">これには、ユーザーが作成した組み込みプロバイダーとカスタムプロバイダーの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-109">It shows the details about built-in and custom providers, which are created by the user.</span></span> <span data-ttu-id="a7a2e-110">このコマンドレットは、モジュールとしてパッケージ化されているか、セッションで実行時に作成された他の構成である複合リソースの詳細も表示します。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-110">This cmdlet also shows details about composite resources, which are other configurations that are packaged as module or created at run time in the session.</span></span>

## <span data-ttu-id="a7a2e-111">例</span><span class="sxs-lookup"><span data-stu-id="a7a2e-111">EXAMPLES</span></span>

### <span data-ttu-id="a7a2e-112">例 1: ローカルコンピューター上のすべてのリソースを取得する</span><span class="sxs-lookup"><span data-stu-id="a7a2e-112">Example 1: Get all resources on the local computer</span></span>

```powershell
Get-DscResource
```

<span data-ttu-id="a7a2e-113">以下のコマンドは、ローカル コンピューター上のすべてのリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-113">This command gets all the resources on the local computer.</span></span>

### <span data-ttu-id="a7a2e-114">例 2: 名前を指定してリソースを取得する</span><span class="sxs-lookup"><span data-stu-id="a7a2e-114">Example 2: Get a resource by specifying the name</span></span>

```powershell
Get-DscResource -Name "WindowsFeature"
```

<span data-ttu-id="a7a2e-115">以下のコマンドは、WindowsFeature リソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-115">This command gets the WindowsFeature resource.</span></span>

### <span data-ttu-id="a7a2e-116">例 3: モジュールからすべてのリソースを取得する</span><span class="sxs-lookup"><span data-stu-id="a7a2e-116">Example 3: Get all the resources from a module</span></span>

```powershell
Get-DscResource -Module "xHyper-V"
```

<span data-ttu-id="a7a2e-117">このコマンドは、xHyper モジュールからすべてのリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-117">This command gets all the resources from the xHyper-V module.</span></span>

### <span data-ttu-id="a7a2e-118">例 4: ワイルドカード文字を使用してリソースを取得する</span><span class="sxs-lookup"><span data-stu-id="a7a2e-118">Example 4: Get a resource by using wildcard characters</span></span>

```powershell
Get-DscResource -Name P*,r*
```

<span data-ttu-id="a7a2e-119">このコマンドは、 **Name** パラメーターで指定されたワイルドカードパターンに一致するすべてのリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-119">This command gets all resources that match the wildcard pattern specified by the **Name** parameter.</span></span>

### <span data-ttu-id="a7a2e-120">例 5: リソースの構文を取得する</span><span class="sxs-lookup"><span data-stu-id="a7a2e-120">Example 5: Get a resource syntax</span></span>

```powershell
Get-DscResource -Name "WindowsFeature" -Syntax
```

<span data-ttu-id="a7a2e-121">以下のコマンドは、WindowsFeature リソースを取得し、リソースの構文を表示します。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-121">This command gets the WindowsFeature resource, and shows the syntax for the resource.</span></span>

### <span data-ttu-id="a7a2e-122">例 6: リソースのすべてのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="a7a2e-122">Example 6: Get all the properties for a resource</span></span>

```powershell
Get-DscResource -Name "User" | Select-Object -ExpandProperty Properties
```

<span data-ttu-id="a7a2e-123">以下のコマンドは、User リソースを取得し、次にパイプライン演算子を使用して User リソースのすべてのプロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-123">This command gets the User resource, and then uses the pipeline operator to return all the properties for the User resource.</span></span>

### <span data-ttu-id="a7a2e-124">例 7: 指定したバージョンの指定したモジュールからすべてのリソースを取得する</span><span class="sxs-lookup"><span data-stu-id="a7a2e-124">Example 7: Get all the resources from a specified module with a specified version</span></span>

```powershell
Get-DscResource -Module @{ModuleName='xHyper-V';RequiredVersion='3.0.0.0'}
```

<span data-ttu-id="a7a2e-125">このコマンドは、xHyper モジュールのバージョン3.0.0.0 ですべてのリソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-125">This command gets all the resources from xHyper-V module with version 3.0.0.0.</span></span>

## <span data-ttu-id="a7a2e-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a7a2e-126">PARAMETERS</span></span>

### <span data-ttu-id="a7a2e-127">-モジュール</span><span class="sxs-lookup"><span data-stu-id="a7a2e-127">-Module</span></span>

<span data-ttu-id="a7a2e-128">DSC リソースを表示するモジュールの名前または完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-128">Specifies the name or fully qualified name of the module for which to view the DSC resource.</span></span>

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

### <span data-ttu-id="a7a2e-129">-Name</span><span class="sxs-lookup"><span data-stu-id="a7a2e-129">-Name</span></span>

<span data-ttu-id="a7a2e-130">表示する DSC リソースの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-130">Specifies an array of names of the DSC resource to view.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a7a2e-131">-構文</span><span class="sxs-lookup"><span data-stu-id="a7a2e-131">-Syntax</span></span>

<span data-ttu-id="a7a2e-132">コマンドレットが、指定された DSC リソースの構文ビューを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-132">Indicates that the cmdlet returns the syntax view of the specified DSC resources.</span></span> <span data-ttu-id="a7a2e-133">返された構文は、PowerShell スクリプトでリソースを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-133">The returned syntax shows how to use the resources in a PowerShell script.</span></span>

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

### <span data-ttu-id="a7a2e-134">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a7a2e-134">CommonParameters</span></span>

<span data-ttu-id="a7a2e-135">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a7a2e-136">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7a2e-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a7a2e-137">入力</span><span class="sxs-lookup"><span data-stu-id="a7a2e-137">INPUTS</span></span>

### <span data-ttu-id="a7a2e-138">System.String[]</span><span class="sxs-lookup"><span data-stu-id="a7a2e-138">System.String[]</span></span>

### <span data-ttu-id="a7a2e-139">System.Object</span><span class="sxs-lookup"><span data-stu-id="a7a2e-139">System.Object</span></span>

## <span data-ttu-id="a7a2e-140">出力</span><span class="sxs-lookup"><span data-stu-id="a7a2e-140">OUTPUTS</span></span>

### <span data-ttu-id="a7a2e-141">DesiredStateConfiguration []. DscResourceInfo []</span><span class="sxs-lookup"><span data-stu-id="a7a2e-141">Microsoft.PowerShell.DesiredStateConfiguration.DscResourceInfo[]</span></span>

### <span data-ttu-id="a7a2e-142">string[]</span><span class="sxs-lookup"><span data-stu-id="a7a2e-142">string[]</span></span>

## <span data-ttu-id="a7a2e-143">注</span><span class="sxs-lookup"><span data-stu-id="a7a2e-143">NOTES</span></span>

## <span data-ttu-id="a7a2e-144">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a7a2e-144">RELATED LINKS</span></span>

[<span data-ttu-id="a7a2e-145">PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="a7a2e-145">PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="a7a2e-146">Invoke-DscResource</span><span class="sxs-lookup"><span data-stu-id="a7a2e-146">Invoke-DscResource</span></span>](/powershell/module/PSDesiredStateConfiguration/Invoke-DscResource)

