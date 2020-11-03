---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: cc94d85e48849d47531ac0a83527f3c68c21377e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217331"
---
# <span data-ttu-id="94e86-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="94e86-102">Enable-PSTrace</span></span>

## <span data-ttu-id="94e86-103">概要</span><span class="sxs-lookup"><span data-stu-id="94e86-103">SYNOPSIS</span></span>
<span data-ttu-id="94e86-104">Microsoft Windows PowerShell イベントプロバイダーのログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="94e86-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="94e86-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="94e86-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="94e86-106">Description</span><span class="sxs-lookup"><span data-stu-id="94e86-106">DESCRIPTION</span></span>

<span data-ttu-id="94e86-107">このコマンドレットは、Microsoft Windows PowerShell イベントプロバイダーの操作および分析イベントログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="94e86-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="94e86-108">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94e86-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="94e86-109">例</span><span class="sxs-lookup"><span data-stu-id="94e86-109">EXAMPLES</span></span>

### <span data-ttu-id="94e86-110">例 1: PowerShell の分析イベントログを有効にする</span><span class="sxs-lookup"><span data-stu-id="94e86-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="94e86-111">次の例では、Microsoft Windows PowerShell プロバイダーの分析イベントログのみを有効にします。</span><span class="sxs-lookup"><span data-stu-id="94e86-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="94e86-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="94e86-112">PARAMETERS</span></span>

### <span data-ttu-id="94e86-113">-分析のみ</span><span class="sxs-lookup"><span data-stu-id="94e86-113">-AnalyticOnly</span></span>

<span data-ttu-id="94e86-114">このパラメーターを使用すると、コマンドレットによって、Microsoft Windows PowerShell プロバイダーの分析イベントログが有効になります。</span><span class="sxs-lookup"><span data-stu-id="94e86-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="94e86-115">操作イベントログは変更されません。</span><span class="sxs-lookup"><span data-stu-id="94e86-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="94e86-116">-Force</span><span class="sxs-lookup"><span data-stu-id="94e86-116">-Force</span></span>

<span data-ttu-id="94e86-117">プロンプトを表示せずに変更を強制するために使用します。</span><span class="sxs-lookup"><span data-stu-id="94e86-117">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="94e86-118">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="94e86-118">CommonParameters</span></span>
<span data-ttu-id="94e86-119">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="94e86-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="94e86-120">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94e86-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="94e86-121">入力</span><span class="sxs-lookup"><span data-stu-id="94e86-121">INPUTS</span></span>

### <span data-ttu-id="94e86-122">なし</span><span class="sxs-lookup"><span data-stu-id="94e86-122">None</span></span>

## <span data-ttu-id="94e86-123">出力</span><span class="sxs-lookup"><span data-stu-id="94e86-123">OUTPUTS</span></span>

### <span data-ttu-id="94e86-124">なし</span><span class="sxs-lookup"><span data-stu-id="94e86-124">None</span></span>

## <span data-ttu-id="94e86-125">注</span><span class="sxs-lookup"><span data-stu-id="94e86-125">NOTES</span></span>

<span data-ttu-id="94e86-126">このコマンドレットは `Get-LogProperties` 、 `Set-LogProperties` コマンドレットとコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="94e86-126">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="94e86-127">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94e86-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="94e86-128">関連リンク</span><span class="sxs-lookup"><span data-stu-id="94e86-128">RELATED LINKS</span></span>

[<span data-ttu-id="94e86-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="94e86-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="94e86-130">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="94e86-130">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="94e86-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="94e86-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)

