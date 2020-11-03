---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-runspacedebug?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-RunspaceDebug
ms.openlocfilehash: dc33195db1ddfb0c2b3e87aaab44845e9f6580a7
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211491"
---
# <span data-ttu-id="6bea7-103">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="6bea7-103">Enable-RunspaceDebug</span></span>

## <span data-ttu-id="6bea7-104">概要</span><span class="sxs-lookup"><span data-stu-id="6bea7-104">SYNOPSIS</span></span>
<span data-ttu-id="6bea7-105">デバッガーがアタッチされるまでブレークポイントが保持される実行空間でのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6bea7-105">Enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="6bea7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6bea7-106">SYNTAX</span></span>

### <span data-ttu-id="6bea7-107">RunspaceNameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="6bea7-107">RunspaceNameParameterSet (Default)</span></span>

```
Enable-RunspaceDebug [-BreakAll] [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="6bea7-108">RunspaceParameterSet</span><span class="sxs-lookup"><span data-stu-id="6bea7-108">RunspaceParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="6bea7-109">RunspaceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="6bea7-109">RunspaceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="6bea7-110">RunspaceInstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="6bea7-110">RunspaceInstanceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="6bea7-111">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="6bea7-111">ProcessNameParameterSet</span></span>

```
Enable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="6bea7-112">Description</span><span class="sxs-lookup"><span data-stu-id="6bea7-112">DESCRIPTION</span></span>

<span data-ttu-id="6bea7-113">`Enable-RunspaceDebug`コマンドレットは、デバッガーがアタッチされるまでブレークポイントが保持される実行空間でのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6bea7-113">The `Enable-RunspaceDebug` cmdlet enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="6bea7-114">例</span><span class="sxs-lookup"><span data-stu-id="6bea7-114">EXAMPLES</span></span>

### <span data-ttu-id="6bea7-115">1: 既定の実行空間デバッガーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6bea7-115">1: Enable the default runspace debugger</span></span>

```powershell
Enable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            True       False
```

## <span data-ttu-id="6bea7-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6bea7-116">PARAMETERS</span></span>

### <span data-ttu-id="6bea7-117">-AppDomainName</span><span class="sxs-lookup"><span data-stu-id="6bea7-117">-AppDomainName</span></span>

<span data-ttu-id="6bea7-118">PowerShell 実行空間をホストするアプリケーションドメインの名前。</span><span class="sxs-lookup"><span data-stu-id="6bea7-118">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="6bea7-119">-BreakAll</span><span class="sxs-lookup"><span data-stu-id="6bea7-119">-BreakAll</span></span>

<span data-ttu-id="6bea7-120">デバッガーが現在アタッチされているかどうかに関係なく、実行空間内の実行中のコマンドまたはスクリプトをステップモードで停止します。</span><span class="sxs-lookup"><span data-stu-id="6bea7-120">Causes any running command or script in the Runspace to stop in step mode, regardless of whether a debugger is currently attached.</span></span> <span data-ttu-id="6bea7-121">現在の停止ポイントをデバッグするためにデバッガーがアタッチされるまで、スクリプトまたはコマンドは停止したままになります。</span><span class="sxs-lookup"><span data-stu-id="6bea7-121">The script or command will remain stopped until a debugger is attached to debug the current stop point.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RunspaceNameParameterSet, RunspaceParameterSet, RunspaceIdParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6bea7-122">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="6bea7-122">-ProcessName</span></span>

<span data-ttu-id="6bea7-123">PowerShell 実行空間をホストするプロセスの名前。</span><span class="sxs-lookup"><span data-stu-id="6bea7-123">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="6bea7-124">-実行空間</span><span class="sxs-lookup"><span data-stu-id="6bea7-124">-Runspace</span></span>

<span data-ttu-id="6bea7-125">無効にする1つ以上の実行 **空間** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6bea7-125">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="6bea7-126">-RunspaceId</span><span class="sxs-lookup"><span data-stu-id="6bea7-126">-RunspaceId</span></span>

<span data-ttu-id="6bea7-127">無効にする1つ以上の実行 **空間** Id 番号。</span><span class="sxs-lookup"><span data-stu-id="6bea7-127">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="6bea7-128">-RunspaceInstanceId</span><span class="sxs-lookup"><span data-stu-id="6bea7-128">-RunspaceInstanceId</span></span>

<span data-ttu-id="6bea7-129">無効にする1つ以上の実行 **空間** guid。</span><span class="sxs-lookup"><span data-stu-id="6bea7-129">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="6bea7-130">-RunspaceName</span><span class="sxs-lookup"><span data-stu-id="6bea7-130">-RunspaceName</span></span>

<span data-ttu-id="6bea7-131">無効にする1つ以上の実行 **空間** 名。</span><span class="sxs-lookup"><span data-stu-id="6bea7-131">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="6bea7-132">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6bea7-132">CommonParameters</span></span>

<span data-ttu-id="6bea7-133">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6bea7-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6bea7-134">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6bea7-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6bea7-135">入力</span><span class="sxs-lookup"><span data-stu-id="6bea7-135">INPUTS</span></span>

## <span data-ttu-id="6bea7-136">出力</span><span class="sxs-lookup"><span data-stu-id="6bea7-136">OUTPUTS</span></span>

## <span data-ttu-id="6bea7-137">注</span><span class="sxs-lookup"><span data-stu-id="6bea7-137">NOTES</span></span>

## <span data-ttu-id="6bea7-138">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6bea7-138">RELATED LINKS</span></span>

[<span data-ttu-id="6bea7-139">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="6bea7-139">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="6bea7-140">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="6bea7-140">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)
