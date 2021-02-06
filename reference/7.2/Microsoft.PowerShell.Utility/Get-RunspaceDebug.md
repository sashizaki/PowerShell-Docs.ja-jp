---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-runspacedebug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RunspaceDebug
ms.openlocfilehash: a77695fe32345fda8e6a0284cd29becb432a4273
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599723"
---
# <span data-ttu-id="ba75f-102">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="ba75f-102">Get-RunspaceDebug</span></span>

## <span data-ttu-id="ba75f-103">概要</span><span class="sxs-lookup"><span data-stu-id="ba75f-103">SYNOPSIS</span></span>
<span data-ttu-id="ba75f-104">実行空間のデバッグオプションを示します。</span><span class="sxs-lookup"><span data-stu-id="ba75f-104">Shows runspace debugging options.</span></span>

## <span data-ttu-id="ba75f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ba75f-105">SYNTAX</span></span>

### <span data-ttu-id="ba75f-106">RunspaceNameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="ba75f-106">RunspaceNameParameterSet (Default)</span></span>

```
Get-RunspaceDebug [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="ba75f-107">RunspaceParameterSet</span><span class="sxs-lookup"><span data-stu-id="ba75f-107">RunspaceParameterSet</span></span>

```
Get-RunspaceDebug [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="ba75f-108">RunspaceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="ba75f-108">RunspaceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="ba75f-109">RunspaceInstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="ba75f-109">RunspaceInstanceIdParameterSet</span></span>

```
Get-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="ba75f-110">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="ba75f-110">ProcessNameParameterSet</span></span>

```
Get-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="ba75f-111">Description</span><span class="sxs-lookup"><span data-stu-id="ba75f-111">DESCRIPTION</span></span>

<span data-ttu-id="ba75f-112">コマンドレットには、実行 `Get-RunspaceDebug` 空間デバッグオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba75f-112">The `Get-RunspaceDebug` cmdlet shows runspace debugging options.</span></span>

## <span data-ttu-id="ba75f-113">例</span><span class="sxs-lookup"><span data-stu-id="ba75f-113">EXAMPLES</span></span>

### <span data-ttu-id="ba75f-114">1: 既定の実行空間デバッガーの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="ba75f-114">1: Show the state of the default runspace debugger</span></span>

```powershell
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            False      False
```

## <span data-ttu-id="ba75f-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ba75f-115">PARAMETERS</span></span>

### <span data-ttu-id="ba75f-116">-AppDomainName</span><span class="sxs-lookup"><span data-stu-id="ba75f-116">-AppDomainName</span></span>

<span data-ttu-id="ba75f-117">PowerShell 実行空間をホストするアプリケーションドメインの名前。</span><span class="sxs-lookup"><span data-stu-id="ba75f-117">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="ba75f-118">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="ba75f-118">-ProcessName</span></span>

<span data-ttu-id="ba75f-119">PowerShell 実行空間をホストするプロセスの名前。</span><span class="sxs-lookup"><span data-stu-id="ba75f-119">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="ba75f-120">-実行空間</span><span class="sxs-lookup"><span data-stu-id="ba75f-120">-Runspace</span></span>

<span data-ttu-id="ba75f-121">無効にする1つ以上の実行 **空間** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="ba75f-121">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="ba75f-122">-RunspaceId</span><span class="sxs-lookup"><span data-stu-id="ba75f-122">-RunspaceId</span></span>

<span data-ttu-id="ba75f-123">無効にする1つ以上の実行 **空間** Id 番号。</span><span class="sxs-lookup"><span data-stu-id="ba75f-123">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="ba75f-124">-RunspaceInstanceId</span><span class="sxs-lookup"><span data-stu-id="ba75f-124">-RunspaceInstanceId</span></span>

<span data-ttu-id="ba75f-125">無効にする1つ以上の実行 **空間** guid。</span><span class="sxs-lookup"><span data-stu-id="ba75f-125">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="ba75f-126">-RunspaceName</span><span class="sxs-lookup"><span data-stu-id="ba75f-126">-RunspaceName</span></span>

<span data-ttu-id="ba75f-127">無効にする1つ以上の実行 **空間** 名。</span><span class="sxs-lookup"><span data-stu-id="ba75f-127">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="ba75f-128">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ba75f-128">CommonParameters</span></span>

<span data-ttu-id="ba75f-129">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ba75f-129">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ba75f-130">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba75f-130">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ba75f-131">入力</span><span class="sxs-lookup"><span data-stu-id="ba75f-131">INPUTS</span></span>

## <span data-ttu-id="ba75f-132">出力</span><span class="sxs-lookup"><span data-stu-id="ba75f-132">OUTPUTS</span></span>

## <span data-ttu-id="ba75f-133">注</span><span class="sxs-lookup"><span data-stu-id="ba75f-133">NOTES</span></span>

## <span data-ttu-id="ba75f-134">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ba75f-134">RELATED LINKS</span></span>

[<span data-ttu-id="ba75f-135">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="ba75f-135">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="ba75f-136">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="ba75f-136">Enable-RunspaceDebug</span></span>](Enable-RunspaceDebug.md)

