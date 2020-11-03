---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: fea84d9ae83eae88f9a665e8a49aaf2e6743127d
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211360"
---
# <span data-ttu-id="d429f-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="d429f-102">Enable-PSTrace</span></span>

## <span data-ttu-id="d429f-103">概要</span><span class="sxs-lookup"><span data-stu-id="d429f-103">SYNOPSIS</span></span>
<span data-ttu-id="d429f-104">Microsoft Windows PowerShell イベントプロバイダーのログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d429f-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="d429f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d429f-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="d429f-106">Description</span><span class="sxs-lookup"><span data-stu-id="d429f-106">DESCRIPTION</span></span>

<span data-ttu-id="d429f-107">このコマンドレットは、Microsoft Windows PowerShell イベントプロバイダーの操作および分析イベントログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d429f-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="d429f-108">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d429f-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="d429f-109">例</span><span class="sxs-lookup"><span data-stu-id="d429f-109">EXAMPLES</span></span>

### <span data-ttu-id="d429f-110">例 1: PowerShell の分析イベントログを有効にする</span><span class="sxs-lookup"><span data-stu-id="d429f-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="d429f-111">次の例では、Microsoft Windows PowerShell プロバイダーの分析イベントログのみを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d429f-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="d429f-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d429f-112">PARAMETERS</span></span>

### <span data-ttu-id="d429f-113">-分析のみ</span><span class="sxs-lookup"><span data-stu-id="d429f-113">-AnalyticOnly</span></span>

<span data-ttu-id="d429f-114">このパラメーターを使用すると、コマンドレットによって、Microsoft Windows PowerShell プロバイダーの分析イベントログが有効になります。</span><span class="sxs-lookup"><span data-stu-id="d429f-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="d429f-115">操作イベントログは変更されません。</span><span class="sxs-lookup"><span data-stu-id="d429f-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="d429f-116">-Force</span><span class="sxs-lookup"><span data-stu-id="d429f-116">-Force</span></span>

<span data-ttu-id="d429f-117">プロンプトを表示せずに変更を強制するために使用します。</span><span class="sxs-lookup"><span data-stu-id="d429f-117">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="d429f-118">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d429f-118">CommonParameters</span></span>
<span data-ttu-id="d429f-119">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d429f-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d429f-120">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d429f-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d429f-121">入力</span><span class="sxs-lookup"><span data-stu-id="d429f-121">INPUTS</span></span>

### <span data-ttu-id="d429f-122">なし</span><span class="sxs-lookup"><span data-stu-id="d429f-122">None</span></span>

## <span data-ttu-id="d429f-123">出力</span><span class="sxs-lookup"><span data-stu-id="d429f-123">OUTPUTS</span></span>

### <span data-ttu-id="d429f-124">なし</span><span class="sxs-lookup"><span data-stu-id="d429f-124">None</span></span>

## <span data-ttu-id="d429f-125">注</span><span class="sxs-lookup"><span data-stu-id="d429f-125">NOTES</span></span>

<span data-ttu-id="d429f-126">このコマンドレットは `Get-LogProperties` 、 `Set-LogProperties` コマンドレットとコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d429f-126">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="d429f-127">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d429f-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="d429f-128">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d429f-128">RELATED LINKS</span></span>

[<span data-ttu-id="d429f-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="d429f-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="d429f-130">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="d429f-130">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="d429f-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="d429f-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)