---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uptime?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Uptime
ms.openlocfilehash: d06dbc66d9674b59df4d75f8ae333d4fe24aa7eb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213016"
---
# <span data-ttu-id="776c4-102">Get-Uptime</span><span class="sxs-lookup"><span data-stu-id="776c4-102">Get-Uptime</span></span>

## <span data-ttu-id="776c4-103">概要</span><span class="sxs-lookup"><span data-stu-id="776c4-103">SYNOPSIS</span></span>
<span data-ttu-id="776c4-104">前回の起動時からの **TimeSpan** を取得します。</span><span class="sxs-lookup"><span data-stu-id="776c4-104">Get the **TimeSpan** since last boot.</span></span>

## <span data-ttu-id="776c4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="776c4-105">SYNTAX</span></span>

### <span data-ttu-id="776c4-106">Timespan (既定値)</span><span class="sxs-lookup"><span data-stu-id="776c4-106">Timespan (Default)</span></span>

```
Get-Uptime [<CommonParameters>]
```

### <span data-ttu-id="776c4-107">カウンター</span><span class="sxs-lookup"><span data-stu-id="776c4-107">Since</span></span>

```
Get-Uptime [-Since] [<CommonParameters>]
```

## <span data-ttu-id="776c4-108">Description</span><span class="sxs-lookup"><span data-stu-id="776c4-108">DESCRIPTION</span></span>

<span data-ttu-id="776c4-109">このコマンドレットは、オペレーティングシステムを最後に起動してから経過した時間を返します。</span><span class="sxs-lookup"><span data-stu-id="776c4-109">This cmdlet returns the time elapsed since the last boot of the operating system.</span></span>

<span data-ttu-id="776c4-110">`Get-Uptime`コマンドレットは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="776c4-110">The `Get-Uptime` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="776c4-111">例</span><span class="sxs-lookup"><span data-stu-id="776c4-111">EXAMPLES</span></span>

### <span data-ttu-id="776c4-112">例 1-前回の起動時からの時間を表示する</span><span class="sxs-lookup"><span data-stu-id="776c4-112">Example 1 - Show time since last boot</span></span>

```powershell
Get-Uptime
```

```Output
Days              : 9
Hours             : 0
Minutes           : 9
Seconds           : 45
Milliseconds      : 0
Ticks             : 7781850000000
TotalDays         : 9.00677083333333
TotalHours        : 216.1625
TotalMinutes      : 12969.75
TotalSeconds      : 778185
TotalMilliseconds : 778185000
```

### <span data-ttu-id="776c4-113">例 2-最後に起動した時刻を表示する</span><span class="sxs-lookup"><span data-stu-id="776c4-113">Example 2 - Show the time of the last boot</span></span>

```powershell
Get-Uptime -Since
```

```Output
Tuesday, June 18, 2019 2:34:56 PM
```

## <span data-ttu-id="776c4-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="776c4-114">PARAMETERS</span></span>

### <span data-ttu-id="776c4-115">-以降</span><span class="sxs-lookup"><span data-stu-id="776c4-115">-Since</span></span>

<span data-ttu-id="776c4-116">コマンドレットが、オペレーティングシステムが最後に起動された時刻を表す **DateTime** オブジェクトを返すようにします。</span><span class="sxs-lookup"><span data-stu-id="776c4-116">Cause the cmdlet to return a **DateTime** object representing the last time that the operating system was booted.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Since
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="776c4-117">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="776c4-117">CommonParameters</span></span>

<span data-ttu-id="776c4-118">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="776c4-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="776c4-119">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="776c4-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="776c4-120">入力</span><span class="sxs-lookup"><span data-stu-id="776c4-120">INPUTS</span></span>

### <span data-ttu-id="776c4-121">なし</span><span class="sxs-lookup"><span data-stu-id="776c4-121">None</span></span>

## <span data-ttu-id="776c4-122">出力</span><span class="sxs-lookup"><span data-stu-id="776c4-122">OUTPUTS</span></span>

### <span data-ttu-id="776c4-123">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="776c4-123">System.TimeSpan</span></span>

<span data-ttu-id="776c4-124">これは、パラメーターが使用されていない場合の既定の戻り値の型です。</span><span class="sxs-lookup"><span data-stu-id="776c4-124">This is the default return type when no parameters are used.</span></span>

### <span data-ttu-id="776c4-125">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="776c4-125">System.DateTime</span></span>

<span data-ttu-id="776c4-126">この型は、 **以降** のパラメーターを使用したときに返されます。</span><span class="sxs-lookup"><span data-stu-id="776c4-126">This type is returned when using the **Since** parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="776c4-127">Windows の高速起動が有効になっている場合、 **Lastbootuptime タイム** に格納されている値は更新されません。</span><span class="sxs-lookup"><span data-stu-id="776c4-127">If Windows fast startup is enabled, Windows does not update the value stored in **LastBootUpTime** .</span></span> <span data-ttu-id="776c4-128">高速スタートアップを無効にするには、コマンドを実行し `Powercfg -h off` ます。</span><span class="sxs-lookup"><span data-stu-id="776c4-128">To disable fast startup, run the following command: `Powercfg -h off`.</span></span>
>
> <span data-ttu-id="776c4-129">Windows fast スタートアップの詳細については、「 [ウェイクアップからの高速スタートアップの区別](/windows-hardware/drivers/kernel/distinguishing-fast-startup-from-wake-from-hibernation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="776c4-129">For more information about Windows fast startup, see [Distinguishing Fast Startup from Wake-from-Hibernation](/windows-hardware/drivers/kernel/distinguishing-fast-startup-from-wake-from-hibernation).</span></span>

## <span data-ttu-id="776c4-130">注</span><span class="sxs-lookup"><span data-stu-id="776c4-130">NOTES</span></span>

<span data-ttu-id="776c4-131">Windows では、返される値は WMI の **Win32_OperatingSystem** クラスの **lastbootuptime** プロパティと同じです。</span><span class="sxs-lookup"><span data-stu-id="776c4-131">On Windows, the value returned is the same as the **LastBootUpTime** property of the **Win32_OperatingSystem** class in WMI.</span></span>

## <span data-ttu-id="776c4-132">関連リンク</span><span class="sxs-lookup"><span data-stu-id="776c4-132">RELATED LINKS</span></span>

[<span data-ttu-id="776c4-133">Win32_OperatingSystem</span><span class="sxs-lookup"><span data-stu-id="776c4-133">Win32_OperatingSystem</span></span>](/windows/win32/cimwin32prov/win32-operatingsystem#properties)

