---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: d0bf17b4bdc169661cf4cde878739287d8be668b
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94343991"
---
# <span data-ttu-id="b3ddf-103">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="b3ddf-103">Get-ComputerInfo</span></span>

## <span data-ttu-id="b3ddf-104">概要</span><span class="sxs-lookup"><span data-stu-id="b3ddf-104">SYNOPSIS</span></span>
<span data-ttu-id="b3ddf-105">システムおよびオペレーティングシステムのプロパティの統合オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="b3ddf-105">Gets a consolidated object of system and operating system properties.</span></span>

## <span data-ttu-id="b3ddf-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b3ddf-106">SYNTAX</span></span>

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="b3ddf-107">Description</span><span class="sxs-lookup"><span data-stu-id="b3ddf-107">DESCRIPTION</span></span>

<span data-ttu-id="b3ddf-108">`Get-ComputerInfo`コマンドレットは、システムとオペレーティングシステムのプロパティの統合オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="b3ddf-108">The `Get-ComputerInfo` cmdlet gets a consolidated object of system and operating system properties.</span></span>
<span data-ttu-id="b3ddf-109">このコマンドレットは、Windows PowerShell 5.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b3ddf-109">This cmdlet was introduced in Windows PowerShell 5.1.</span></span>

## <span data-ttu-id="b3ddf-110">例</span><span class="sxs-lookup"><span data-stu-id="b3ddf-110">EXAMPLES</span></span>

### <span data-ttu-id="b3ddf-111">例 1: すべてのコンピューターのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="b3ddf-111">Example 1: Get all computer properties</span></span>

```powershell
Get-ComputerInfo
```

<span data-ttu-id="b3ddf-112">このコマンドは、すべてのシステムおよびオペレーティングシステムのプロパティをコンピューターから取得します。</span><span class="sxs-lookup"><span data-stu-id="b3ddf-112">This command gets all system and operating system properties from the computer.</span></span>

### <span data-ttu-id="b3ddf-113">例 2: すべてのコンピューターのオペレーティングシステムのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="b3ddf-113">Example 2: Get all computer operating system properties</span></span>

```powershell
Get-ComputerInfo -Property "os*"
```

<span data-ttu-id="b3ddf-114">このコマンドは、すべてのオペレーティングシステムのプロパティをコンピューターから取得します。</span><span class="sxs-lookup"><span data-stu-id="b3ddf-114">This command gets all operating system properties from the computer.</span></span>

## <span data-ttu-id="b3ddf-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b3ddf-115">PARAMETERS</span></span>

### <span data-ttu-id="b3ddf-116">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="b3ddf-116">-Property</span></span>

<span data-ttu-id="b3ddf-117">このコマンドレットによって表示されるコンピュータープロパティを文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="b3ddf-117">Specifies, as a string array, the computer properties in which this cmdlet displays.</span></span>

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

### <span data-ttu-id="b3ddf-118">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b3ddf-118">CommonParameters</span></span>

<span data-ttu-id="b3ddf-119">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b3ddf-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b3ddf-120">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3ddf-120">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="b3ddf-121">入力</span><span class="sxs-lookup"><span data-stu-id="b3ddf-121">INPUTS</span></span>

### <span data-ttu-id="b3ddf-122">System.String[]</span><span class="sxs-lookup"><span data-stu-id="b3ddf-122">System.String[]</span></span>

## <span data-ttu-id="b3ddf-123">出力</span><span class="sxs-lookup"><span data-stu-id="b3ddf-123">OUTPUTS</span></span>

### <span data-ttu-id="b3ddf-124">Microsoft. PowerShell. 管理. ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="b3ddf-124">Microsoft.PowerShell.Management.ComputerInfo</span></span>

## <span data-ttu-id="b3ddf-125">注</span><span class="sxs-lookup"><span data-stu-id="b3ddf-125">NOTES</span></span>

<span data-ttu-id="b3ddf-126">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b3ddf-126">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="b3ddf-127">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b3ddf-127">RELATED LINKS</span></span>
