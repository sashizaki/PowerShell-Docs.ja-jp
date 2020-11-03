---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedscript?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledScript
ms.openlocfilehash: 6a69108694d5ba614bb7f195004d2d37ac6de092
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215992"
---
# <span data-ttu-id="fe128-103">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="fe128-103">Get-InstalledScript</span></span>

## <span data-ttu-id="fe128-104">概要</span><span class="sxs-lookup"><span data-stu-id="fe128-104">SYNOPSIS</span></span>
<span data-ttu-id="fe128-105">インストールされているスクリプトを取得します。</span><span class="sxs-lookup"><span data-stu-id="fe128-105">Gets an installed script.</span></span>

## <span data-ttu-id="fe128-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fe128-106">SYNTAX</span></span>

```
Get-InstalledScript [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="fe128-107">Description</span><span class="sxs-lookup"><span data-stu-id="fe128-107">DESCRIPTION</span></span>

<span data-ttu-id="fe128-108">**Get-help** コマンドレットは、CurrentUser および AllUsers スコープ用にインストールされているスクリプトを取得します。</span><span class="sxs-lookup"><span data-stu-id="fe128-108">The **Get-InstalledScript** cmdlet gets installed scripts for CurrentUser and AllUsers scopes.</span></span>

## <span data-ttu-id="fe128-109">例</span><span class="sxs-lookup"><span data-stu-id="fe128-109">EXAMPLES</span></span>

### <span data-ttu-id="fe128-110">例 1: インストールされているすべてのスクリプトを取得する</span><span class="sxs-lookup"><span data-stu-id="fe128-110">Example 1: Get all installed scripts</span></span>

```
PS C:\> Get-InstalledScript
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
2.0        Script-WithDependencies1            Script     local1               Description for the Script-WithDependencies1 script
```

<span data-ttu-id="fe128-111">このコマンドは、インストールされているすべてのスクリプトを取得します。</span><span class="sxs-lookup"><span data-stu-id="fe128-111">This command gets all installed scripts.</span></span>

### <span data-ttu-id="fe128-112">例 2: 名前を指定してインストール済みのスクリプトを取得する</span><span class="sxs-lookup"><span data-stu-id="fe128-112">Example 2: Get installed scripts by name</span></span>

```
PS C:\> Get-InstalledScript -Name "Required-Scri*"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="fe128-113">このコマンドは、名前がスクリプト化で始まるスクリプトを取得します。</span><span class="sxs-lookup"><span data-stu-id="fe128-113">This command gets scripts where the name begins with Required-Scri.</span></span>

## <span data-ttu-id="fe128-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fe128-114">PARAMETERS</span></span>

### <span data-ttu-id="fe128-115">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="fe128-115">-AllowPrerelease</span></span>

<span data-ttu-id="fe128-116">プレリリースとしてマークされた結果スクリプトにを含めます。</span><span class="sxs-lookup"><span data-stu-id="fe128-116">Includes in the results scripts marked as a prerelease.</span></span>

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

### <span data-ttu-id="fe128-117">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="fe128-117">-MaximumVersion</span></span>

<span data-ttu-id="fe128-118">取得するスクリプトの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe128-118">Specifies the maximum, or latest, version of a script to get.</span></span>
<span data-ttu-id="fe128-119">*MaximumVersion* および *RequiredVersion* パラメーターは相互に排他的です。両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fe128-119">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fe128-120">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="fe128-120">-MinimumVersion</span></span>

<span data-ttu-id="fe128-121">取得するスクリプトの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe128-121">Specifies the minimum version of a script to get.</span></span>
<span data-ttu-id="fe128-122">*MinimumVersion* および *RequiredVersion* パラメーターは相互に排他的です。両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fe128-122">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fe128-123">-Name</span><span class="sxs-lookup"><span data-stu-id="fe128-123">-Name</span></span>

<span data-ttu-id="fe128-124">取得するスクリプトの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="fe128-124">Specifies an array of names of scripts to get.</span></span>
<span data-ttu-id="fe128-125">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe128-125">Wildcards are accepted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="fe128-126">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="fe128-126">-RequiredVersion</span></span>

<span data-ttu-id="fe128-127">取得するスクリプトの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="fe128-127">Specifies the exact version of a script to get.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fe128-128">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fe128-128">CommonParameters</span></span>

<span data-ttu-id="fe128-129">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="fe128-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fe128-130">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe128-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fe128-131">入力</span><span class="sxs-lookup"><span data-stu-id="fe128-131">INPUTS</span></span>

### <span data-ttu-id="fe128-132">System.String[]</span><span class="sxs-lookup"><span data-stu-id="fe128-132">System.String[]</span></span>

### <span data-ttu-id="fe128-133">System.String</span><span class="sxs-lookup"><span data-stu-id="fe128-133">System.String</span></span>

## <span data-ttu-id="fe128-134">出力</span><span class="sxs-lookup"><span data-stu-id="fe128-134">OUTPUTS</span></span>

### <span data-ttu-id="fe128-135">System.Object</span><span class="sxs-lookup"><span data-stu-id="fe128-135">System.Object</span></span>

## <span data-ttu-id="fe128-136">注</span><span class="sxs-lookup"><span data-stu-id="fe128-136">NOTES</span></span>

## <span data-ttu-id="fe128-137">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fe128-137">RELATED LINKS</span></span>

[<span data-ttu-id="fe128-138">Install-Script</span><span class="sxs-lookup"><span data-stu-id="fe128-138">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="fe128-139">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="fe128-139">Uninstall-Script</span></span>](Uninstall-Script.md)