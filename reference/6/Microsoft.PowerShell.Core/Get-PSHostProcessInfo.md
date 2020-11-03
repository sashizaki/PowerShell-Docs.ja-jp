---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-pshostprocessinfo?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSHostProcessInfo
ms.openlocfilehash: 24ebb507b2f9544115d6309b0a91d8b19b0745ec
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216112"
---
# <span data-ttu-id="15762-103">Get-PSHostProcessInfo</span><span class="sxs-lookup"><span data-stu-id="15762-103">Get-PSHostProcessInfo</span></span>

## <span data-ttu-id="15762-104">概要</span><span class="sxs-lookup"><span data-stu-id="15762-104">SYNOPSIS</span></span>
<span data-ttu-id="15762-105">PowerShell ホストに関するプロセス情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="15762-105">Gets process information about the PowerShell host.</span></span>

## <span data-ttu-id="15762-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="15762-106">SYNTAX</span></span>

### <span data-ttu-id="15762-107">ProcessNameParameterSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="15762-107">ProcessNameParameterSet (Default)</span></span>

```
Get-PSHostProcessInfo [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="15762-108">ProcessParameterSet</span><span class="sxs-lookup"><span data-stu-id="15762-108">ProcessParameterSet</span></span>

```
Get-PSHostProcessInfo [-Process] <Process[]> [<CommonParameters>]
```

### <span data-ttu-id="15762-109">ProcessIdParameterSet</span><span class="sxs-lookup"><span data-stu-id="15762-109">ProcessIdParameterSet</span></span>

```
Get-PSHostProcessInfo [-Id] <Int32[]> [<CommonParameters>]
```

## <span data-ttu-id="15762-110">Description</span><span class="sxs-lookup"><span data-stu-id="15762-110">DESCRIPTION</span></span>

<span data-ttu-id="15762-111">`Get-PSHostProcessInfo`コマンドレットは、ローカルコンピューター上で実行されている PowerShell ホストプロセスに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="15762-111">The `Get-PSHostProcessInfo` cmdlet gets information about PowerShell host processes running on the local computer.</span></span>

<span data-ttu-id="15762-112">PowerShell 6.2 以降では、このコマンドレットは Windows 以外のプラットフォームでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="15762-112">Beginning in PowerShell 6.2, this cmdlet is supported on non-Windows platforms.</span></span>

## <span data-ttu-id="15762-113">例</span><span class="sxs-lookup"><span data-stu-id="15762-113">EXAMPLES</span></span>

### <span data-ttu-id="15762-114">1: システムで実行されている PowerShell ホストの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="15762-114">1: Get a list of PowerShell hosts running on the system</span></span>

```powershell
Get-PSHostProcessInfo
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
powershell      11204 DefaultAppDomain
pwsh            13912 DefaultAppDomain
```

### <span data-ttu-id="15762-115">2: 特定のプロセス名の PowerShell ホスト情報を取得する</span><span class="sxs-lookup"><span data-stu-id="15762-115">2: Get PowerShell host information for a specific process name</span></span>

```powershell
Get-PSHostProcessInfo -Name pwsh
```

```Output
ProcessName ProcessId AppDomainName
----------- --------- -------------
pwsh            13912 DefaultAppDomain
```

## <span data-ttu-id="15762-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="15762-116">PARAMETERS</span></span>

### <span data-ttu-id="15762-117">-Id</span><span class="sxs-lookup"><span data-stu-id="15762-117">-Id</span></span>

<span data-ttu-id="15762-118">プロセス ID を指定してプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="15762-118">Specifies a process by the process ID.</span></span> <span data-ttu-id="15762-119">プロセス ID を取得するには、 `Get-Process` コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="15762-119">To get a process ID, run the `Get-Process` cmdlet.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: ProcessIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="15762-120">-Name</span><span class="sxs-lookup"><span data-stu-id="15762-120">-Name</span></span>

<span data-ttu-id="15762-121">プロセス名でプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="15762-121">Specifies a process by the process name.</span></span> <span data-ttu-id="15762-122">プロセス名を取得するには、 `Get-Process` コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="15762-122">To get a process name, run the `Get-Process` cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ProcessNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="15762-123">-Process</span><span class="sxs-lookup"><span data-stu-id="15762-123">-Process</span></span>

<span data-ttu-id="15762-124">プロセスオブジェクトによってプロセスを指定します。</span><span class="sxs-lookup"><span data-stu-id="15762-124">Specifies a process by the process object.</span></span> <span data-ttu-id="15762-125">このパラメーターを使用する最も簡単な方法は、 `Get-Process` 変数に入力するプロセスを返すコマンドの結果を保存し、その変数をこのパラメーターの値として指定することです。</span><span class="sxs-lookup"><span data-stu-id="15762-125">The simplest way to use this parameter is to save the results of a `Get-Process` command that returns process that you want to enter in a variable, and then specify the variable as the value of this parameter.</span></span>

```yaml
Type: System.Diagnostics.Process[]
Parameter Sets: ProcessParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="15762-126">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="15762-126">CommonParameters</span></span>

<span data-ttu-id="15762-127">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="15762-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="15762-128">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="15762-128">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="15762-129">入力</span><span class="sxs-lookup"><span data-stu-id="15762-129">INPUTS</span></span>

### <span data-ttu-id="15762-130">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="15762-130">System.Diagnostics.Process</span></span>

<span data-ttu-id="15762-131">パイプを使用して、 **プロセス** オブジェクトをから `Get-Process` このコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="15762-131">You can pipe a **Process** object from `Get-Process` to this cmdlet.</span></span>

## <span data-ttu-id="15762-132">出力</span><span class="sxs-lookup"><span data-stu-id="15762-132">OUTPUTS</span></span>

### <span data-ttu-id="15762-133">Get-pshostprocessinfo です。</span><span class="sxs-lookup"><span data-stu-id="15762-133">Microsoft.PowerShell.Commands.PSHostProcessInfo</span></span>

## <span data-ttu-id="15762-134">注</span><span class="sxs-lookup"><span data-stu-id="15762-134">NOTES</span></span>

## <span data-ttu-id="15762-135">関連リンク</span><span class="sxs-lookup"><span data-stu-id="15762-135">RELATED LINKS</span></span>

[<span data-ttu-id="15762-136">Get-Process</span><span class="sxs-lookup"><span data-stu-id="15762-136">Get-Process</span></span>](../Microsoft.PowerShell.Management/get-process.md)