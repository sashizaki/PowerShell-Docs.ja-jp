---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/18/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-timezone?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TimeZone
ms.openlocfilehash: 9f442e4423eb9695776733e7938cc2cf861e2fae
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212251"
---
# <span data-ttu-id="6e031-103">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="6e031-103">Set-TimeZone</span></span>

## <span data-ttu-id="6e031-104">概要</span><span class="sxs-lookup"><span data-stu-id="6e031-104">SYNOPSIS</span></span>
<span data-ttu-id="6e031-105">システムのタイムゾーンを指定したタイムゾーンに設定します。</span><span class="sxs-lookup"><span data-stu-id="6e031-105">Sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="6e031-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6e031-106">SYNTAX</span></span>

### <span data-ttu-id="6e031-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="6e031-107">Name (Default)</span></span>

```
Set-TimeZone [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6e031-108">Id</span><span class="sxs-lookup"><span data-stu-id="6e031-108">Id</span></span>

```
Set-TimeZone -Id <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6e031-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="6e031-109">InputObject</span></span>

```
Set-TimeZone [-InputObject] <TimeZoneInfo> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6e031-110">Description</span><span class="sxs-lookup"><span data-stu-id="6e031-110">DESCRIPTION</span></span>

<span data-ttu-id="6e031-111">コマンドレットでは、 `Set-TimeZone` システムのタイムゾーンを指定されたタイムゾーンに設定します。</span><span class="sxs-lookup"><span data-stu-id="6e031-111">The `Set-TimeZone` cmdlet sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="6e031-112">例</span><span class="sxs-lookup"><span data-stu-id="6e031-112">EXAMPLES</span></span>

### <span data-ttu-id="6e031-113">例 1: タイムゾーンを Id で設定する</span><span class="sxs-lookup"><span data-stu-id="6e031-113">Example 1: Set the time zone by Id</span></span>

<span data-ttu-id="6e031-114">この例では、ローカルコンピューターのタイムゾーンをロシア標準時に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e031-114">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

```powershell
Set-TimeZone -Id "Russian Standard Time" -PassThru
```

```Output
Id                         : Russian Standard Time
DisplayName                : (UTC+03:00) Moscow, St. Petersburg
StandardName               : Russia TZ 2 Standard Time
DaylightName               : Russia TZ 2 Daylight Time
BaseUtcOffset              : 03:00:00
SupportsDaylightSavingTime : True
```

### <span data-ttu-id="6e031-115">例 2: タイムゾーンを名前で設定する</span><span class="sxs-lookup"><span data-stu-id="6e031-115">Example 2: Set the time zone by name</span></span>

<span data-ttu-id="6e031-116">この例では、ローカルコンピューターのタイムゾーンをロシア標準時に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e031-116">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

```powershell
Set-TimeZone -Name "Russia TZ 2 Standard Time"
```

<span data-ttu-id="6e031-117">前の例に示したように、タイムゾーンの **Id** と **名前** は必ずしも一致するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="6e031-117">As we saw in the previous example, the **Id** and the **Name** of the Time Zone do not always match.</span></span>
<span data-ttu-id="6e031-118">**Name** パラメーターは、 **TimeZoneInfo** オブジェクトの **standardname** または **daylightname** プロパティと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e031-118">The **Name** parameter must match the **StandardName** or **DaylightName** properties of the **TimeZoneInfo** object.</span></span>

## <span data-ttu-id="6e031-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6e031-119">PARAMETERS</span></span>

### <span data-ttu-id="6e031-120">-Id</span><span class="sxs-lookup"><span data-stu-id="6e031-120">-Id</span></span>

<span data-ttu-id="6e031-121">このコマンドレットが設定するタイムゾーンの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e031-121">Specifies the ID of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="6e031-122">次のコマンドを実行して、タイムゾーン Id の完全な一覧を取得でき `Get-TimeZone -ListAvailable` ます。</span><span class="sxs-lookup"><span data-stu-id="6e031-122">A full list of Time Zone IDs can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

```yaml
Type: System.String
Parameter Sets: Id
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="6e031-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6e031-123">-InputObject</span></span>

<span data-ttu-id="6e031-124">入力として使用する **TimeZoneInfo** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e031-124">Specifies a **TimeZoneInfo** object to use as input.</span></span>

```yaml
Type: System.TimeZoneInfo
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6e031-125">-Name</span><span class="sxs-lookup"><span data-stu-id="6e031-125">-Name</span></span>

<span data-ttu-id="6e031-126">このコマンドレットによって設定されるタイムゾーンの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e031-126">Specifies the name of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="6e031-127">タイムゾーン名の完全な一覧を取得するには、コマンドを実行し `Get-TimeZone -ListAvailable` ます。</span><span class="sxs-lookup"><span data-stu-id="6e031-127">A full list of Time Zone names can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6e031-128">-PassThru</span><span class="sxs-lookup"><span data-stu-id="6e031-128">-PassThru</span></span>

<span data-ttu-id="6e031-129">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="6e031-129">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="6e031-130">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="6e031-130">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="6e031-131">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6e031-131">-Confirm</span></span>

<span data-ttu-id="6e031-132">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e031-132">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6e031-133">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6e031-133">-WhatIf</span></span>

<span data-ttu-id="6e031-134">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="6e031-134">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6e031-135">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="6e031-135">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6e031-136">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6e031-136">CommonParameters</span></span>

<span data-ttu-id="6e031-137">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6e031-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6e031-138">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e031-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6e031-139">入力</span><span class="sxs-lookup"><span data-stu-id="6e031-139">INPUTS</span></span>

### <span data-ttu-id="6e031-140">System.string, TimeZoneInfo, System.string, System.string</span><span class="sxs-lookup"><span data-stu-id="6e031-140">System.String, System.TimeZoneInfo, System.String</span></span>

## <span data-ttu-id="6e031-141">出力</span><span class="sxs-lookup"><span data-stu-id="6e031-141">OUTPUTS</span></span>

## <span data-ttu-id="6e031-142">注</span><span class="sxs-lookup"><span data-stu-id="6e031-142">NOTES</span></span>

## <span data-ttu-id="6e031-143">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6e031-143">RELATED LINKS</span></span>

[<span data-ttu-id="6e031-144">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="6e031-144">Get-TimeZone</span></span>](Get-TimeZone.md)
