---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/18/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-timezone?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-TimeZone
ms.openlocfilehash: ddce638972aabb1afc1c8fe500df380dd01dff14
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603236"
---
# <span data-ttu-id="3e076-102">Set-TimeZone</span><span class="sxs-lookup"><span data-stu-id="3e076-102">Set-TimeZone</span></span>

## <span data-ttu-id="3e076-103">概要</span><span class="sxs-lookup"><span data-stu-id="3e076-103">SYNOPSIS</span></span>
<span data-ttu-id="3e076-104">システムのタイムゾーンを指定したタイムゾーンに設定します。</span><span class="sxs-lookup"><span data-stu-id="3e076-104">Sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="3e076-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3e076-105">SYNTAX</span></span>

### <span data-ttu-id="3e076-106">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="3e076-106">Name (Default)</span></span>

```
Set-TimeZone [-Name] <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3e076-107">Id</span><span class="sxs-lookup"><span data-stu-id="3e076-107">Id</span></span>

```
Set-TimeZone -Id <String> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3e076-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="3e076-108">InputObject</span></span>

```
Set-TimeZone [-InputObject] <TimeZoneInfo> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3e076-109">Description</span><span class="sxs-lookup"><span data-stu-id="3e076-109">DESCRIPTION</span></span>

<span data-ttu-id="3e076-110">コマンドレットでは、 `Set-TimeZone` システムのタイムゾーンを指定されたタイムゾーンに設定します。</span><span class="sxs-lookup"><span data-stu-id="3e076-110">The `Set-TimeZone` cmdlet sets the system time zone to a specified time zone.</span></span>

## <span data-ttu-id="3e076-111">例</span><span class="sxs-lookup"><span data-stu-id="3e076-111">EXAMPLES</span></span>

### <span data-ttu-id="3e076-112">例 1: タイムゾーンを Id で設定する</span><span class="sxs-lookup"><span data-stu-id="3e076-112">Example 1: Set the time zone by Id</span></span>

<span data-ttu-id="3e076-113">この例では、ローカルコンピューターのタイムゾーンをロシア標準時に設定します。</span><span class="sxs-lookup"><span data-stu-id="3e076-113">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

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

### <span data-ttu-id="3e076-114">例 2: タイムゾーンを名前で設定する</span><span class="sxs-lookup"><span data-stu-id="3e076-114">Example 2: Set the time zone by name</span></span>

<span data-ttu-id="3e076-115">この例では、ローカルコンピューターのタイムゾーンをロシア標準時に設定します。</span><span class="sxs-lookup"><span data-stu-id="3e076-115">This example sets the time zone on the local computer to Russian Standard Time.</span></span>

```powershell
Set-TimeZone -Name "Russia TZ 2 Standard Time"
```

<span data-ttu-id="3e076-116">前の例に示したように、タイムゾーンの **Id** と **名前** は必ずしも一致するとは限りません。</span><span class="sxs-lookup"><span data-stu-id="3e076-116">As we saw in the previous example, the **Id** and the **Name** of the Time Zone do not always match.</span></span>
<span data-ttu-id="3e076-117">**Name** パラメーターは、 **TimeZoneInfo** オブジェクトの **standardname** または **daylightname** プロパティと一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e076-117">The **Name** parameter must match the **StandardName** or **DaylightName** properties of the **TimeZoneInfo** object.</span></span>

## <span data-ttu-id="3e076-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3e076-118">PARAMETERS</span></span>

### <span data-ttu-id="3e076-119">-Id</span><span class="sxs-lookup"><span data-stu-id="3e076-119">-Id</span></span>

<span data-ttu-id="3e076-120">このコマンドレットが設定するタイムゾーンの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e076-120">Specifies the ID of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="3e076-121">次のコマンドを実行して、タイムゾーン Id の完全な一覧を取得でき `Get-TimeZone -ListAvailable` ます。</span><span class="sxs-lookup"><span data-stu-id="3e076-121">A full list of Time Zone IDs can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

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

### <span data-ttu-id="3e076-122">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3e076-122">-InputObject</span></span>

<span data-ttu-id="3e076-123">入力として使用する **TimeZoneInfo** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e076-123">Specifies a **TimeZoneInfo** object to use as input.</span></span>

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

### <span data-ttu-id="3e076-124">-Name</span><span class="sxs-lookup"><span data-stu-id="3e076-124">-Name</span></span>

<span data-ttu-id="3e076-125">このコマンドレットによって設定されるタイムゾーンの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3e076-125">Specifies the name of the time zone that this cmdlet sets.</span></span> <span data-ttu-id="3e076-126">タイムゾーン名の完全な一覧を取得するには、コマンドを実行し `Get-TimeZone -ListAvailable` ます。</span><span class="sxs-lookup"><span data-stu-id="3e076-126">A full list of Time Zone names can be obtained by running the following command: `Get-TimeZone -ListAvailable`.</span></span>

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

### <span data-ttu-id="3e076-127">-PassThru</span><span class="sxs-lookup"><span data-stu-id="3e076-127">-PassThru</span></span>

<span data-ttu-id="3e076-128">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="3e076-128">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="3e076-129">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="3e076-129">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="3e076-130">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3e076-130">-Confirm</span></span>

<span data-ttu-id="3e076-131">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e076-131">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3e076-132">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3e076-132">-WhatIf</span></span>

<span data-ttu-id="3e076-133">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="3e076-133">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="3e076-134">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="3e076-134">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3e076-135">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="3e076-135">CommonParameters</span></span>

<span data-ttu-id="3e076-136">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="3e076-136">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3e076-137">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e076-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3e076-138">入力</span><span class="sxs-lookup"><span data-stu-id="3e076-138">INPUTS</span></span>

### <span data-ttu-id="3e076-139">System.string, TimeZoneInfo, System.string, System.string</span><span class="sxs-lookup"><span data-stu-id="3e076-139">System.String, System.TimeZoneInfo, System.String</span></span>

## <span data-ttu-id="3e076-140">出力</span><span class="sxs-lookup"><span data-stu-id="3e076-140">OUTPUTS</span></span>

## <span data-ttu-id="3e076-141">注</span><span class="sxs-lookup"><span data-stu-id="3e076-141">NOTES</span></span>

<span data-ttu-id="3e076-142">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e076-142">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="3e076-143">関連リンク</span><span class="sxs-lookup"><span data-stu-id="3e076-143">RELATED LINKS</span></span>

[<span data-ttu-id="3e076-144">Get-TimeZone</span><span class="sxs-lookup"><span data-stu-id="3e076-144">Get-TimeZone</span></span>](Get-TimeZone.md)
