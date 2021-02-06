---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-installedscript?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-InstalledScript
ms.openlocfilehash: fe5fc0feb34fda87dab987f33140992a346017a1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599550"
---
# <span data-ttu-id="bb90f-102">Get-InstalledScript</span><span class="sxs-lookup"><span data-stu-id="bb90f-102">Get-InstalledScript</span></span>

## <span data-ttu-id="bb90f-103">概要</span><span class="sxs-lookup"><span data-stu-id="bb90f-103">SYNOPSIS</span></span>
<span data-ttu-id="bb90f-104">インストールされているスクリプトを取得します。</span><span class="sxs-lookup"><span data-stu-id="bb90f-104">Gets an installed script.</span></span>

## <span data-ttu-id="bb90f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bb90f-105">SYNTAX</span></span>

```
Get-InstalledScript [[-Name] <String[]>] [-MinimumVersion <String>] [-RequiredVersion <String>]
 [-MaximumVersion <String>] [-AllowPrerelease] [<CommonParameters>]
```

## <span data-ttu-id="bb90f-106">Description</span><span class="sxs-lookup"><span data-stu-id="bb90f-106">DESCRIPTION</span></span>

<span data-ttu-id="bb90f-107">**Get-help** コマンドレットは、CurrentUser および AllUsers スコープ用にインストールされているスクリプトを取得します。</span><span class="sxs-lookup"><span data-stu-id="bb90f-107">The **Get-InstalledScript** cmdlet gets installed scripts for CurrentUser and AllUsers scopes.</span></span>

## <span data-ttu-id="bb90f-108">例</span><span class="sxs-lookup"><span data-stu-id="bb90f-108">EXAMPLES</span></span>

### <span data-ttu-id="bb90f-109">例 1: インストールされているすべてのスクリプトを取得する</span><span class="sxs-lookup"><span data-stu-id="bb90f-109">Example 1: Get all installed scripts</span></span>

```
PS C:\> Get-InstalledScript
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
2.0        Script-WithDependencies1            Script     local1               Description for the Script-WithDependencies1 script
```

<span data-ttu-id="bb90f-110">このコマンドは、インストールされているすべてのスクリプトを取得します。</span><span class="sxs-lookup"><span data-stu-id="bb90f-110">This command gets all installed scripts.</span></span>

### <span data-ttu-id="bb90f-111">例 2: 名前を指定してインストール済みのスクリプトを取得する</span><span class="sxs-lookup"><span data-stu-id="bb90f-111">Example 2: Get installed scripts by name</span></span>

```
PS C:\> Get-InstalledScript -Name "Required-Scri*"
Version    Name                                Type       Repository           Description
-------    ----                                ----       ----------           -----------
2.5        Required-Script1                    Script     local1               Description for the Required-Script1 script
2.5        Required-Script2                    Script     local1               Description for the Required-Script2 script
2.5        Required-Script3                    Script     local1               Description for the Required-Script3 script
```

<span data-ttu-id="bb90f-112">このコマンドは、名前がスクリプト化で始まるスクリプトを取得します。</span><span class="sxs-lookup"><span data-stu-id="bb90f-112">This command gets scripts where the name begins with Required-Scri.</span></span>

## <span data-ttu-id="bb90f-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bb90f-113">PARAMETERS</span></span>

### <span data-ttu-id="bb90f-114">-AllowPrerelease リリース</span><span class="sxs-lookup"><span data-stu-id="bb90f-114">-AllowPrerelease</span></span>

<span data-ttu-id="bb90f-115">プレリリースとしてマークされた結果スクリプトにを含めます。</span><span class="sxs-lookup"><span data-stu-id="bb90f-115">Includes in the results scripts marked as a prerelease.</span></span>

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

### <span data-ttu-id="bb90f-116">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="bb90f-116">-MaximumVersion</span></span>

<span data-ttu-id="bb90f-117">取得するスクリプトの最大バージョンまたは最新バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="bb90f-117">Specifies the maximum, or latest, version of a script to get.</span></span>
<span data-ttu-id="bb90f-118">*MaximumVersion* および *RequiredVersion* パラメーターは相互に排他的です。両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bb90f-118">The *MaximumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="bb90f-119">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="bb90f-119">-MinimumVersion</span></span>

<span data-ttu-id="bb90f-120">取得するスクリプトの最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="bb90f-120">Specifies the minimum version of a script to get.</span></span>
<span data-ttu-id="bb90f-121">*MinimumVersion* および *RequiredVersion* パラメーターは相互に排他的です。両方のパラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bb90f-121">The *MinimumVersion* and *RequiredVersion* parameters are mutually exclusive; you cannot use both parameters in the same command.</span></span>

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

### <span data-ttu-id="bb90f-122">-Name</span><span class="sxs-lookup"><span data-stu-id="bb90f-122">-Name</span></span>

<span data-ttu-id="bb90f-123">取得するスクリプトの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="bb90f-123">Specifies an array of names of scripts to get.</span></span>
<span data-ttu-id="bb90f-124">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb90f-124">Wildcards are accepted.</span></span>

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

### <span data-ttu-id="bb90f-125">-RequiredVersion</span><span class="sxs-lookup"><span data-stu-id="bb90f-125">-RequiredVersion</span></span>

<span data-ttu-id="bb90f-126">取得するスクリプトの正確なバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="bb90f-126">Specifies the exact version of a script to get.</span></span>

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

### <span data-ttu-id="bb90f-127">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="bb90f-127">CommonParameters</span></span>

<span data-ttu-id="bb90f-128">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="bb90f-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bb90f-129">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb90f-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bb90f-130">入力</span><span class="sxs-lookup"><span data-stu-id="bb90f-130">INPUTS</span></span>

### <span data-ttu-id="bb90f-131">System.String[]</span><span class="sxs-lookup"><span data-stu-id="bb90f-131">System.String[]</span></span>

### <span data-ttu-id="bb90f-132">System.String</span><span class="sxs-lookup"><span data-stu-id="bb90f-132">System.String</span></span>

## <span data-ttu-id="bb90f-133">出力</span><span class="sxs-lookup"><span data-stu-id="bb90f-133">OUTPUTS</span></span>

### <span data-ttu-id="bb90f-134">System.Object</span><span class="sxs-lookup"><span data-stu-id="bb90f-134">System.Object</span></span>

## <span data-ttu-id="bb90f-135">注</span><span class="sxs-lookup"><span data-stu-id="bb90f-135">NOTES</span></span>

## <span data-ttu-id="bb90f-136">関連リンク</span><span class="sxs-lookup"><span data-stu-id="bb90f-136">RELATED LINKS</span></span>

[<span data-ttu-id="bb90f-137">Install-Script</span><span class="sxs-lookup"><span data-stu-id="bb90f-137">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="bb90f-138">アンインストール-スクリプト</span><span class="sxs-lookup"><span data-stu-id="bb90f-138">Uninstall-Script</span></span>](Uninstall-Script.md)

