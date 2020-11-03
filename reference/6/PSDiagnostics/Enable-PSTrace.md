---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: d5008d5105b18b5a3d0423cab4282735e3d382d8
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212483"
---
# <span data-ttu-id="8a2dd-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="8a2dd-102">Enable-PSTrace</span></span>

## <span data-ttu-id="8a2dd-103">概要</span><span class="sxs-lookup"><span data-stu-id="8a2dd-103">SYNOPSIS</span></span>
<span data-ttu-id="8a2dd-104">Microsoft Windows PowerShell イベントプロバイダーのログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8a2dd-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="8a2dd-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8a2dd-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="8a2dd-106">Description</span><span class="sxs-lookup"><span data-stu-id="8a2dd-106">DESCRIPTION</span></span>

<span data-ttu-id="8a2dd-107">このコマンドレットは、Microsoft Windows PowerShell イベントプロバイダーの操作および分析イベントログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8a2dd-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="8a2dd-108">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a2dd-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="8a2dd-109">例</span><span class="sxs-lookup"><span data-stu-id="8a2dd-109">EXAMPLES</span></span>

### <span data-ttu-id="8a2dd-110">例 1: PowerShell の分析イベントログを有効にする</span><span class="sxs-lookup"><span data-stu-id="8a2dd-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="8a2dd-111">次の例では、Microsoft Windows PowerShell プロバイダーの分析イベントログのみを有効にします。</span><span class="sxs-lookup"><span data-stu-id="8a2dd-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="8a2dd-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8a2dd-112">PARAMETERS</span></span>

### <span data-ttu-id="8a2dd-113">-分析のみ</span><span class="sxs-lookup"><span data-stu-id="8a2dd-113">-AnalyticOnly</span></span>

<span data-ttu-id="8a2dd-114">このパラメーターを使用すると、コマンドレットによって、Microsoft Windows PowerShell プロバイダーの分析イベントログが有効になります。</span><span class="sxs-lookup"><span data-stu-id="8a2dd-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="8a2dd-115">操作イベントログは変更されません。</span><span class="sxs-lookup"><span data-stu-id="8a2dd-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="8a2dd-116">-Force</span><span class="sxs-lookup"><span data-stu-id="8a2dd-116">-Force</span></span>

<span data-ttu-id="8a2dd-117">プロンプトを表示せずに変更を強制するために使用します。</span><span class="sxs-lookup"><span data-stu-id="8a2dd-117">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="8a2dd-118">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a2dd-118">CommonParameters</span></span>
<span data-ttu-id="8a2dd-119">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8a2dd-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8a2dd-120">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a2dd-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8a2dd-121">入力</span><span class="sxs-lookup"><span data-stu-id="8a2dd-121">INPUTS</span></span>

### <span data-ttu-id="8a2dd-122">なし</span><span class="sxs-lookup"><span data-stu-id="8a2dd-122">None</span></span>

## <span data-ttu-id="8a2dd-123">出力</span><span class="sxs-lookup"><span data-stu-id="8a2dd-123">OUTPUTS</span></span>

### <span data-ttu-id="8a2dd-124">なし</span><span class="sxs-lookup"><span data-stu-id="8a2dd-124">None</span></span>

## <span data-ttu-id="8a2dd-125">注</span><span class="sxs-lookup"><span data-stu-id="8a2dd-125">NOTES</span></span>

<span data-ttu-id="8a2dd-126">このコマンドレットは `Get-LogProperties` 、 `Set-LogProperties` コマンドレットとコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8a2dd-126">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="8a2dd-127">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a2dd-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="8a2dd-128">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8a2dd-128">RELATED LINKS</span></span>

[<span data-ttu-id="8a2dd-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="8a2dd-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="8a2dd-130">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="8a2dd-130">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="8a2dd-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="8a2dd-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)
