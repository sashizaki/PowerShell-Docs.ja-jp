---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-timezone?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TimeZone
ms.openlocfilehash: ae937a7e72b2b1f2d5f455358a0034717e3e4634
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215395"
---
# <span data-ttu-id="d9000-103">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="d9000-103">Get-TimeZone</span></span>

## <span data-ttu-id="d9000-104">概要</span><span class="sxs-lookup"><span data-stu-id="d9000-104">SYNOPSIS</span></span>
<span data-ttu-id="d9000-105">現在のタイムゾーンまたは使用可能なタイムゾーンの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="d9000-105">Gets the current time zone or a list of available time zones.</span></span>

## <span data-ttu-id="d9000-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d9000-106">SYNTAX</span></span>

### <span data-ttu-id="d9000-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="d9000-107">Name (Default)</span></span>

```
Get-TimeZone [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="d9000-108">Id</span><span class="sxs-lookup"><span data-stu-id="d9000-108">Id</span></span>

```
Get-TimeZone -Id <String[]> [<CommonParameters>]
```

### <span data-ttu-id="d9000-109">ListAvailable</span><span class="sxs-lookup"><span data-stu-id="d9000-109">ListAvailable</span></span>

```
Get-TimeZone [-ListAvailable] [<CommonParameters>]
```

## <span data-ttu-id="d9000-110">Description</span><span class="sxs-lookup"><span data-stu-id="d9000-110">DESCRIPTION</span></span>

<span data-ttu-id="d9000-111">**Get TimeZone** コマンドレットは、現在のタイムゾーンまたは使用可能なタイムゾーンの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="d9000-111">The **Get-TimeZone** cmdlet gets the current time zone or a list of available time zones.</span></span>

## <span data-ttu-id="d9000-112">例</span><span class="sxs-lookup"><span data-stu-id="d9000-112">EXAMPLES</span></span>

### <span data-ttu-id="d9000-113">例 1: 現在のタイムゾーンを取得する</span><span class="sxs-lookup"><span data-stu-id="d9000-113">Example 1: Get the current time zone</span></span>

```
PS C:\> Get-TimeZone
Pacific Standard Time
```

<span data-ttu-id="d9000-114">このコマンドは、現在のタイムゾーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="d9000-114">This command gets the current time zone.</span></span>

### <span data-ttu-id="d9000-115">例 2: 指定した文字列に一致するタイムゾーンを取得する</span><span class="sxs-lookup"><span data-stu-id="d9000-115">Example 2: Get time zones that match a specified string</span></span>

```
PS C:\> Get-TimeZone -Name "*pac*"
Pacific Standard Time (Mexico)

(UTC-08:00) Pacific Time (US &amp; Canada)

Pacific Standard Time

SA Pacific Standard Time

Pacific SA Standard Time

West Pacific Standard Time

Central Pacific Standard Time
```

<span data-ttu-id="d9000-116">このコマンドは、指定されたワイルドカードと一致するすべてのタイムゾーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="d9000-116">This command gets all time zones that match the specified wildcard.</span></span>

### <span data-ttu-id="d9000-117">例 3: 使用可能なすべてのタイムゾーンを取得する</span><span class="sxs-lookup"><span data-stu-id="d9000-117">Example 3: Get all available time zones</span></span>

```
PS C:\> Get-TimeZone -ListAvailable
```

<span data-ttu-id="d9000-118">このコマンドは、使用可能なすべてのタイムゾーンを取得します。</span><span class="sxs-lookup"><span data-stu-id="d9000-118">This command gets all available time zones.</span></span>

## <span data-ttu-id="d9000-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d9000-119">PARAMETERS</span></span>

### <span data-ttu-id="d9000-120">-Id</span><span class="sxs-lookup"><span data-stu-id="d9000-120">-Id</span></span>

<span data-ttu-id="d9000-121">文字列配列として、このコマンドレットが取得するタイムゾーンの ID または id を指定します。</span><span class="sxs-lookup"><span data-stu-id="d9000-121">Specifies, as a string array, the ID or IDs of the time zones that this cmdlet gets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d9000-122">-ListAvailable</span><span class="sxs-lookup"><span data-stu-id="d9000-122">-ListAvailable</span></span>

<span data-ttu-id="d9000-123">このコマンドレットがすべての使用可能なタイムゾーンを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="d9000-123">Indicates that this cmdlet gets all available time zones.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListAvailable
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d9000-124">-Name</span><span class="sxs-lookup"><span data-stu-id="d9000-124">-Name</span></span>

<span data-ttu-id="d9000-125">文字列配列として、このコマンドレットが取得するタイムゾーンの名前または名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d9000-125">Specifies, as a string array, the name or names of the time zones that this cmdlet gets.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="d9000-126">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d9000-126">CommonParameters</span></span>

<span data-ttu-id="d9000-127">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d9000-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d9000-128">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9000-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d9000-129">入力</span><span class="sxs-lookup"><span data-stu-id="d9000-129">INPUTS</span></span>

### <span data-ttu-id="d9000-130">System.String[]</span><span class="sxs-lookup"><span data-stu-id="d9000-130">System.String[]</span></span>

## <span data-ttu-id="d9000-131">出力</span><span class="sxs-lookup"><span data-stu-id="d9000-131">OUTPUTS</span></span>

### <span data-ttu-id="d9000-132">TimeZoneInfo []</span><span class="sxs-lookup"><span data-stu-id="d9000-132">System.TimeZoneInfo[]</span></span>

## <span data-ttu-id="d9000-133">注</span><span class="sxs-lookup"><span data-stu-id="d9000-133">NOTES</span></span>

## <span data-ttu-id="d9000-134">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d9000-134">RELATED LINKS</span></span>

[<span data-ttu-id="d9000-135">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="d9000-135">Set-TimeZone</span></span>](Set-TimeZone.md)
