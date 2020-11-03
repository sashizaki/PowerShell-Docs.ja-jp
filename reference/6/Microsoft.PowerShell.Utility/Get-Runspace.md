---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Runspace
ms.openlocfilehash: 12530b9cf30b34598dfc3a049f5553920abecc4f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216643"
---
# <span data-ttu-id="0e188-103">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="0e188-103">Get-Runspace</span></span>

## <span data-ttu-id="0e188-104">概要</span><span class="sxs-lookup"><span data-stu-id="0e188-104">SYNOPSIS</span></span>
<span data-ttu-id="0e188-105">PowerShell ホストプロセス内のアクティブな実行空間を取得します。</span><span class="sxs-lookup"><span data-stu-id="0e188-105">Gets active runspaces within a PowerShell host process.</span></span>

## <span data-ttu-id="0e188-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0e188-106">SYNTAX</span></span>

### <span data-ttu-id="0e188-107">NameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="0e188-107">NameParameterSet (Default)</span></span>

```
Get-Runspace [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="0e188-108">IdParameterSet</span><span class="sxs-lookup"><span data-stu-id="0e188-108">IdParameterSet</span></span>

```
Get-Runspace [-Id] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="0e188-109">InstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="0e188-109">InstanceIdParameterSet</span></span>

```
Get-Runspace [-InstanceId] <Guid[]> [<CommonParameters>]
```

## <span data-ttu-id="0e188-110">Description</span><span class="sxs-lookup"><span data-stu-id="0e188-110">DESCRIPTION</span></span>

<span data-ttu-id="0e188-111">`Get-Runspace`コマンドレットは、PowerShell ホストプロセス内のアクティブな実行空間を取得します。</span><span class="sxs-lookup"><span data-stu-id="0e188-111">The `Get-Runspace` cmdlet gets active runspaces in a PowerShell host process.</span></span>

## <span data-ttu-id="0e188-112">例</span><span class="sxs-lookup"><span data-stu-id="0e188-112">EXAMPLES</span></span>

### <span data-ttu-id="0e188-113">例 1: 実行空間を取得する</span><span class="sxs-lookup"><span data-stu-id="0e188-113">Example 1: Get runspaces</span></span>

```powershell
Get-Runspace
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
  2 Runspace2       localhost       Local         Opened        Available
  3 Runspace3       localhost       Local         Opened        Available
```

### <span data-ttu-id="0e188-114">例 2: Id で実行空間を取得する</span><span class="sxs-lookup"><span data-stu-id="0e188-114">Example 2: Get runspace by Id</span></span>

```powershell
Get-Runspace -Id 2
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  2 Runspace2       localhost       Local         Opened        Available
```

### <span data-ttu-id="0e188-115">例 3: 名前を使用して実行空間を取得する</span><span class="sxs-lookup"><span data-stu-id="0e188-115">Example 3: Get runspace by Name</span></span>

```powershell
Get-Runspace -Name Runspace1
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

### <span data-ttu-id="0e188-116">例 4: InstanceId によって実行空間を取得する</span><span class="sxs-lookup"><span data-stu-id="0e188-116">Example 4: Get runspace by InstanceId</span></span>

<span data-ttu-id="0e188-117">この例では、パラメーターを使用して使用可能な実行空間を特定 `Name` し、戻り値のオブジェクトを変数に格納し `$activeRunspace` ます。</span><span class="sxs-lookup"><span data-stu-id="0e188-117">In this example, we identify an available runspace using the `Name` parameter and store the return object to the variable `$activeRunspace`.</span></span> <span data-ttu-id="0e188-118">これにより、の後続の実行で実行 **空間** のプロパティを使用できるように `Get-Runspace` なります。</span><span class="sxs-lookup"><span data-stu-id="0e188-118">This allows you to use the properties of the **Runspace** in subsequent runs of `Get-Runspace`.</span></span>

```powershell
$activeRunspace = Get-Runspace -Name Runspace1
Get-Runspace -InstanceId $activeRunspace.InstanceId
```

```Output
Id Name            ComputerName    Type          State         Availability
 -- ----            ------------    ----          -----         ------------
  1 Runspace1       localhost       Local         Opened        Busy
```

## <span data-ttu-id="0e188-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0e188-119">PARAMETERS</span></span>

### <span data-ttu-id="0e188-120">-Id</span><span class="sxs-lookup"><span data-stu-id="0e188-120">-Id</span></span>

<span data-ttu-id="0e188-121">実行空間の Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e188-121">Specifies the Id of a runspace</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: IdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e188-122">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="0e188-122">-InstanceId</span></span>

<span data-ttu-id="0e188-123">実行中のジョブのインスタンス ID GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e188-123">Specifies the instance ID GUID of a running job.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e188-124">-Name</span><span class="sxs-lookup"><span data-stu-id="0e188-124">-Name</span></span>

<span data-ttu-id="0e188-125">実行空間の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e188-125">Specifies the Name of a runspace</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0e188-126">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="0e188-126">CommonParameters</span></span>

<span data-ttu-id="0e188-127">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="0e188-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0e188-128">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e188-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0e188-129">入力</span><span class="sxs-lookup"><span data-stu-id="0e188-129">INPUTS</span></span>

## <span data-ttu-id="0e188-130">出力</span><span class="sxs-lookup"><span data-stu-id="0e188-130">OUTPUTS</span></span>

### <span data-ttu-id="0e188-131">システム管理. 実行空間</span><span class="sxs-lookup"><span data-stu-id="0e188-131">System.Management.Automation.Runspaces.Runspace</span></span>

<span data-ttu-id="0e188-132">パイプを使用してコマンドの結果をにパイプすることができ `Get-Runspace` `Debug-Runspace` ます。</span><span class="sxs-lookup"><span data-stu-id="0e188-132">You can pipe the results of a `Get-Runspace` command to `Debug-Runspace`.</span></span>

## <span data-ttu-id="0e188-133">注</span><span class="sxs-lookup"><span data-stu-id="0e188-133">NOTES</span></span>

## <span data-ttu-id="0e188-134">関連リンク</span><span class="sxs-lookup"><span data-stu-id="0e188-134">RELATED LINKS</span></span>

[<span data-ttu-id="0e188-135">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="0e188-135">Debug-Runspace</span></span>](Debug-Runspace.md)
