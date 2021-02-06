---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/19/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/enable-runspacedebug?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-RunspaceDebug
ms.openlocfilehash: 26ab9b9135eedafa0238eab5c07aa7abb7880ed4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605183"
---
# <span data-ttu-id="11944-102">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="11944-102">Enable-RunspaceDebug</span></span>

## <span data-ttu-id="11944-103">概要</span><span class="sxs-lookup"><span data-stu-id="11944-103">SYNOPSIS</span></span>
<span data-ttu-id="11944-104">デバッガーがアタッチされるまでブレークポイントが保持される実行空間でのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="11944-104">Enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="11944-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="11944-105">SYNTAX</span></span>

### <span data-ttu-id="11944-106">RunspaceNameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="11944-106">RunspaceNameParameterSet (Default)</span></span>

```
Enable-RunspaceDebug [-BreakAll] [[-RunspaceName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="11944-107">RunspaceParameterSet</span><span class="sxs-lookup"><span data-stu-id="11944-107">RunspaceParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-Runspace] <Runspace[]> [<CommonParameters>]
```

### <span data-ttu-id="11944-108">RunspaceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="11944-108">RunspaceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-BreakAll] [-RunspaceId] <Int32[]> [<CommonParameters>]
```

### <span data-ttu-id="11944-109">RunspaceInstanceIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="11944-109">RunspaceInstanceIdParameterSet</span></span>

```
Enable-RunspaceDebug [-RunspaceInstanceId] <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="11944-110">ProcessNameParameterSet</span><span class="sxs-lookup"><span data-stu-id="11944-110">ProcessNameParameterSet</span></span>

```
Enable-RunspaceDebug [[-ProcessName] <String>] [[-AppDomainName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="11944-111">Description</span><span class="sxs-lookup"><span data-stu-id="11944-111">DESCRIPTION</span></span>

<span data-ttu-id="11944-112">`Enable-RunspaceDebug`コマンドレットは、デバッガーがアタッチされるまでブレークポイントが保持される実行空間でのデバッグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="11944-112">The `Enable-RunspaceDebug` cmdlet enables debugging on runspaces where any breakpoint is preserved until a debugger is attached.</span></span>

## <span data-ttu-id="11944-113">例</span><span class="sxs-lookup"><span data-stu-id="11944-113">EXAMPLES</span></span>

### <span data-ttu-id="11944-114">1: 既定の実行空間デバッガーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="11944-114">1: Enable the default runspace debugger</span></span>

```powershell
Enable-RunspaceDebug
Get-RunspaceDebug
```

```Output
 Id Name                 Enabled    BreakAll
 -- ----                 -------    --------
  1 Runspace1            True       False
```

## <span data-ttu-id="11944-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="11944-115">PARAMETERS</span></span>

### <span data-ttu-id="11944-116">-AppDomainName</span><span class="sxs-lookup"><span data-stu-id="11944-116">-AppDomainName</span></span>

<span data-ttu-id="11944-117">PowerShell 実行空間をホストするアプリケーションドメインの名前。</span><span class="sxs-lookup"><span data-stu-id="11944-117">The name of the application domain that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="11944-118">-BreakAll</span><span class="sxs-lookup"><span data-stu-id="11944-118">-BreakAll</span></span>

<span data-ttu-id="11944-119">デバッガーが現在アタッチされているかどうかに関係なく、実行空間内の実行中のコマンドまたはスクリプトをステップモードで停止します。</span><span class="sxs-lookup"><span data-stu-id="11944-119">Causes any running command or script in the Runspace to stop in step mode, regardless of whether a debugger is currently attached.</span></span> <span data-ttu-id="11944-120">現在の停止ポイントをデバッグするためにデバッガーがアタッチされるまで、スクリプトまたはコマンドは停止したままになります。</span><span class="sxs-lookup"><span data-stu-id="11944-120">The script or command will remain stopped until a debugger is attached to debug the current stop point.</span></span>

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

### <span data-ttu-id="11944-121">-ProcessName</span><span class="sxs-lookup"><span data-stu-id="11944-121">-ProcessName</span></span>

<span data-ttu-id="11944-122">PowerShell 実行空間をホストするプロセスの名前。</span><span class="sxs-lookup"><span data-stu-id="11944-122">The name of the process that hosts the PowerShell runspace.</span></span>

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

### <span data-ttu-id="11944-123">-実行空間</span><span class="sxs-lookup"><span data-stu-id="11944-123">-Runspace</span></span>

<span data-ttu-id="11944-124">無効にする1つ以上の実行 **空間** オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="11944-124">One or more **Runspace** objects to be disabled.</span></span>

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

### <span data-ttu-id="11944-125">-RunspaceId</span><span class="sxs-lookup"><span data-stu-id="11944-125">-RunspaceId</span></span>

<span data-ttu-id="11944-126">無効にする1つ以上の実行 **空間** Id 番号。</span><span class="sxs-lookup"><span data-stu-id="11944-126">One or more **Runspace** Id numbers to be disabled.</span></span>

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

### <span data-ttu-id="11944-127">-RunspaceInstanceId</span><span class="sxs-lookup"><span data-stu-id="11944-127">-RunspaceInstanceId</span></span>

<span data-ttu-id="11944-128">無効にする1つ以上の実行 **空間** guid。</span><span class="sxs-lookup"><span data-stu-id="11944-128">One or more **Runspace** GUIDs to be disabled.</span></span>

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

### <span data-ttu-id="11944-129">-RunspaceName</span><span class="sxs-lookup"><span data-stu-id="11944-129">-RunspaceName</span></span>

<span data-ttu-id="11944-130">無効にする1つ以上の実行 **空間** 名。</span><span class="sxs-lookup"><span data-stu-id="11944-130">One or more **Runspace** names to be disabled.</span></span>

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

### <span data-ttu-id="11944-131">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="11944-131">CommonParameters</span></span>

<span data-ttu-id="11944-132">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="11944-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="11944-133">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11944-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="11944-134">入力</span><span class="sxs-lookup"><span data-stu-id="11944-134">INPUTS</span></span>

## <span data-ttu-id="11944-135">出力</span><span class="sxs-lookup"><span data-stu-id="11944-135">OUTPUTS</span></span>

## <span data-ttu-id="11944-136">注</span><span class="sxs-lookup"><span data-stu-id="11944-136">NOTES</span></span>

## <span data-ttu-id="11944-137">関連リンク</span><span class="sxs-lookup"><span data-stu-id="11944-137">RELATED LINKS</span></span>

[<span data-ttu-id="11944-138">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="11944-138">Disable-RunspaceDebug</span></span>](Disable-RunspaceDebug.md)

[<span data-ttu-id="11944-139">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="11944-139">Get-RunspaceDebug</span></span>](Get-RunspaceDebug.md)

