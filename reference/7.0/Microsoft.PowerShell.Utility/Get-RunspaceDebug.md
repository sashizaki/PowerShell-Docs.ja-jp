---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspacedebug?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RunspaceDebug
ms.openlocfilehash: 627b1446f37b951eb5455ca1d9b41ec5453e2cc7
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210752"
---
# <span data-ttu-id="bf861-103">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="bf861-103">Get-RunspaceDebug</span></span>

## <span data-ttu-id="bf861-104">概要</span><span class="sxs-lookup"><span data-stu-id="bf861-104">SYNOPSIS</span></span>
<span data-ttu-id="bf861-105">実行空間のデバッグオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="bf861-105">Shows runspace debugging options.</span></span>

## <span data-ttu-id="bf861-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bf861-106">SYNTAX</span></span>

### <span data-ttu-id="bf861-107">RunspaceNameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="bf861-107">RunspaceNameParameterSet (Default)</span></span>

```
Get-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="bf861-108">RunspaceParameterSet</span><span class="sxs-lookup"><span data-stu-id="bf861-108">RunspaceParameterSet</span></span>

```
Get-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="bf861-109">RunspaceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="bf861-109">RunspaceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="bf861-110">RunspaceInstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="bf861-110">RunspaceInstanceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="bf861-111">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="bf861-111">ProcessNameParameterSet</span></span>

```
Get-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="bf861-112">Description</span><span class="sxs-lookup"><span data-stu-id="bf861-112">DESCRIPTION</span></span>

<span data-ttu-id="bf861-113">コマンドレットには、実行 `Get-RunspaceDebug` 空間デバッグオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf861-113">The `Get-RunspaceDebug` cmdlet shows runspace debugging options.</span></span>

## <span data-ttu-id="bf861-114">例</span><span class="sxs-lookup"><span data-stu-id="bf861-114">EXAMPLES</span></span>

### <span data-ttu-id="bf861-115">1: 既定の実行空間デバッガーの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="bf861-115">1: Show the state of the default runspace debugger</span></span>

```powershell
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="bf861-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bf861-116">PARAMETERS</span></span>

### <span data-ttu-id="bf861-117">-AppDomainName</span><span class="sxs-lookup"><span data-stu-id="bf861-117">-AppDomainName</span></span>

<span data-ttu-id="bf861-118">PowerShell 実行空間をホストするアプリケーションドメインの名前。</span><span class="sxs-lookup"><span data-stu-id="bf861-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bf861-119">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="bf861-119">-ProcessName</span></span>

<span data-ttu-id="bf861-120">PowerShell 実行空間をホストするプロセスの名前。</span><span class="sxs-lookup"><span data-stu-id="bf861-120">The name of the process that hosts the PowerShell runspace.</span></span>

```yaml
Type: System.String
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bf861-121">-実行空間</span><span class="sxs-lookup"><span data-stu-id="bf861-121">-Runspace</span></span>

<span data-ttu-id="bf861-122">無効にする1つ以上の実行 **空間** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bf861-122">One or more **Runspace** objects to be disabled.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.Runspace[]
Parameter Sets: RunspaceParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="bf861-123">-RunspaceId</span><span class="sxs-lookup"><span data-stu-id="bf861-123">-RunspaceId</span></span>

<span data-ttu-id="bf861-124">無効にする1つ以上の実行 **空間** Id 番号。</span><span class="sxs-lookup"><span data-stu-id="bf861-124">One or more **Runspace** Id numbers to be disabled.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: RunspaceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bf861-125">-RunspaceInstanceId</span><span class="sxs-lookup"><span data-stu-id="bf861-125">-RunspaceInstanceId</span></span>

<span data-ttu-id="bf861-126">無効にする1つ以上の実行 **空間** guid。</span><span class="sxs-lookup"><span data-stu-id="bf861-126">One or more **Runspace** GUIDs to be disabled.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: RunspaceInstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bf861-127">-RunspaceName</span><span class="sxs-lookup"><span data-stu-id="bf861-127">-RunspaceName</span></span>

<span data-ttu-id="bf861-128">無効にする1つ以上の実行 **空間** 名。</span><span class="sxs-lookup"><span data-stu-id="bf861-128">One or more **Runspace** names to be disabled.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RunspaceNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bf861-129">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="bf861-129">CommonParameters</span></span>

<span data-ttu-id="bf861-130">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="bf861-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bf861-131">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf861-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bf861-132">入力</span><span class="sxs-lookup"><span data-stu-id="bf861-132">INPUTS</span></span>

## <span data-ttu-id="bf861-133">出力</span><span class="sxs-lookup"><span data-stu-id="bf861-133">OUTPUTS</span></span>

## <span data-ttu-id="bf861-134">注</span><span class="sxs-lookup"><span data-stu-id="bf861-134">NOTES</span></span>

## <span data-ttu-id="bf861-135">関連リンク</span><span class="sxs-lookup"><span data-stu-id="bf861-135">RELATED LINKS</span></span>

[<span data-ttu-id="bf861-136">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="bf861-136">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="bf861-137">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="bf861-137">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)
