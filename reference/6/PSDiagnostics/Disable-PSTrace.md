---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: 3f99869825b2255d3f5487c48b6eaa90a4ae901f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212464"
---
# <span data-ttu-id="501ac-102">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="501ac-102">Disable-PSTrace</span></span>

## <span data-ttu-id="501ac-103">概要</span><span class="sxs-lookup"><span data-stu-id="501ac-103">SYNOPSIS</span></span>
<span data-ttu-id="501ac-104">Microsoft Windows PowerShell イベントプロバイダーのログを無効にします。</span><span class="sxs-lookup"><span data-stu-id="501ac-104">Disables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="501ac-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="501ac-105">SYNTAX</span></span>

```
Disable-PSTrace [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="501ac-106">Description</span><span class="sxs-lookup"><span data-stu-id="501ac-106">DESCRIPTION</span></span>

<span data-ttu-id="501ac-107">このコマンドレットは、Microsoft Windows PowerShell イベントプロバイダーの操作および分析イベントログを無効にします。</span><span class="sxs-lookup"><span data-stu-id="501ac-107">This cmdlet disables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="501ac-108">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="501ac-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="501ac-109">例</span><span class="sxs-lookup"><span data-stu-id="501ac-109">EXAMPLES</span></span>

### <span data-ttu-id="501ac-110">例 1: PowerShell の分析イベントログを無効にする</span><span class="sxs-lookup"><span data-stu-id="501ac-110">Example 1: Disable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="501ac-111">次の例では、Microsoft Windows PowerShell プロバイダーの分析イベントログのみを無効にします。</span><span class="sxs-lookup"><span data-stu-id="501ac-111">The following example disables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Disable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="501ac-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="501ac-112">PARAMETERS</span></span>

### <span data-ttu-id="501ac-113">-分析のみ</span><span class="sxs-lookup"><span data-stu-id="501ac-113">-AnalyticOnly</span></span>

<span data-ttu-id="501ac-114">このパラメーターを使用すると、コマンドレットは、Microsoft Windows PowerShell プロバイダーの分析イベントログを無効にします。</span><span class="sxs-lookup"><span data-stu-id="501ac-114">When this parameter is used, the cmdlet disables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="501ac-115">操作イベントログは変更されません。</span><span class="sxs-lookup"><span data-stu-id="501ac-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="501ac-116">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="501ac-116">CommonParameters</span></span>
<span data-ttu-id="501ac-117">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="501ac-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="501ac-118">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="501ac-118">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="501ac-119">入力</span><span class="sxs-lookup"><span data-stu-id="501ac-119">INPUTS</span></span>

### <span data-ttu-id="501ac-120">なし</span><span class="sxs-lookup"><span data-stu-id="501ac-120">None</span></span>

## <span data-ttu-id="501ac-121">出力</span><span class="sxs-lookup"><span data-stu-id="501ac-121">OUTPUTS</span></span>

### <span data-ttu-id="501ac-122">なし</span><span class="sxs-lookup"><span data-stu-id="501ac-122">None</span></span>

## <span data-ttu-id="501ac-123">注</span><span class="sxs-lookup"><span data-stu-id="501ac-123">NOTES</span></span>

<span data-ttu-id="501ac-124">このコマンドレットは `Get-LogProperties` 、 `Set-LogProperties` コマンドレットとコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="501ac-124">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="501ac-125">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="501ac-125">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="501ac-126">関連リンク</span><span class="sxs-lookup"><span data-stu-id="501ac-126">RELATED LINKS</span></span>

[<span data-ttu-id="501ac-127">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="501ac-127">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="501ac-128">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="501ac-128">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="501ac-129">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="501ac-129">Enable-PSTrace</span></span>](Enable-PSTrace.md)
