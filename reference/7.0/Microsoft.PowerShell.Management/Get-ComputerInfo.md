---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: 876ce5ff32863281ba9bc1ae94ece8b0a12c9efd
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210371"
---
# <span data-ttu-id="47c8f-103">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="47c8f-103">Get-ComputerInfo</span></span>

## <span data-ttu-id="47c8f-104">概要</span><span class="sxs-lookup"><span data-stu-id="47c8f-104">SYNOPSIS</span></span>
<span data-ttu-id="47c8f-105">システムおよびオペレーティングシステムのプロパティの統合オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="47c8f-105">Gets a consolidated object of system and operating system properties.</span></span>

## <span data-ttu-id="47c8f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="47c8f-106">SYNTAX</span></span>

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="47c8f-107">Description</span><span class="sxs-lookup"><span data-stu-id="47c8f-107">DESCRIPTION</span></span>

<span data-ttu-id="47c8f-108">`Get-ComputerInfo`コマンドレットは、システムとオペレーティングシステムのプロパティの統合オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="47c8f-108">The `Get-ComputerInfo` cmdlet gets a consolidated object of system and operating system properties.</span></span>
<span data-ttu-id="47c8f-109">このコマンドレットは、Windows PowerShell 5.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="47c8f-109">This cmdlet was introduced in Windows PowerShell 5.1.</span></span>

## <span data-ttu-id="47c8f-110">例</span><span class="sxs-lookup"><span data-stu-id="47c8f-110">EXAMPLES</span></span>

### <span data-ttu-id="47c8f-111">例 1: すべてのコンピューターのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="47c8f-111">Example 1: Get all computer properties</span></span>

```powershell
Get-ComputerInfo
```

<span data-ttu-id="47c8f-112">このコマンドは、すべてのシステムおよびオペレーティングシステムのプロパティをコンピューターから取得します。</span><span class="sxs-lookup"><span data-stu-id="47c8f-112">This command gets all system and operating system properties from the computer.</span></span>

### <span data-ttu-id="47c8f-113">例 2: すべてのコンピューターのオペレーティングシステムのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="47c8f-113">Example 2: Get all computer operating system properties</span></span>

```powershell
Get-ComputerInfo -Property "os*"
```

<span data-ttu-id="47c8f-114">このコマンドは、すべてのオペレーティングシステムのプロパティをコンピューターから取得します。</span><span class="sxs-lookup"><span data-stu-id="47c8f-114">This command gets all operating system properties from the computer.</span></span>

## <span data-ttu-id="47c8f-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="47c8f-115">PARAMETERS</span></span>

### <span data-ttu-id="47c8f-116">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="47c8f-116">-Property</span></span>

<span data-ttu-id="47c8f-117">このコマンドレットによって表示されるコンピュータープロパティを文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="47c8f-117">Specifies, as a string array, the computer properties in which this cmdlet displays.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="47c8f-118">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="47c8f-118">CommonParameters</span></span>

<span data-ttu-id="47c8f-119">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="47c8f-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="47c8f-120">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47c8f-120">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="47c8f-121">入力</span><span class="sxs-lookup"><span data-stu-id="47c8f-121">INPUTS</span></span>

### <span data-ttu-id="47c8f-122">System.String[]</span><span class="sxs-lookup"><span data-stu-id="47c8f-122">System.String[]</span></span>

## <span data-ttu-id="47c8f-123">出力</span><span class="sxs-lookup"><span data-stu-id="47c8f-123">OUTPUTS</span></span>

### <span data-ttu-id="47c8f-124">Microsoft. PowerShell. 管理. ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="47c8f-124">Microsoft.PowerShell.Management.ComputerInfo</span></span>

## <span data-ttu-id="47c8f-125">注</span><span class="sxs-lookup"><span data-stu-id="47c8f-125">NOTES</span></span>

## <span data-ttu-id="47c8f-126">関連リンク</span><span class="sxs-lookup"><span data-stu-id="47c8f-126">RELATED LINKS</span></span>
