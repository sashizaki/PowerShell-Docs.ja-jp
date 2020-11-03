---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-printer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Printer
ms.openlocfilehash: ec8d080da133310270d022b00f7f92d08ea3ca41
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213779"
---
# <span data-ttu-id="40b54-103">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="40b54-103">Out-Printer</span></span>

## <span data-ttu-id="40b54-104">概要</span><span class="sxs-lookup"><span data-stu-id="40b54-104">SYNOPSIS</span></span>
<span data-ttu-id="40b54-105">プリンターに出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="40b54-105">Sends output to a printer.</span></span>

## <span data-ttu-id="40b54-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="40b54-106">SYNTAX</span></span>

```
Out-Printer [[-Name] <String>] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="40b54-107">Description</span><span class="sxs-lookup"><span data-stu-id="40b54-107">DESCRIPTION</span></span>

<span data-ttu-id="40b54-108">`Out-Printer`コマンドレットは、出力を既定のプリンターまたは代替プリンター (指定されている場合) に送信します。</span><span class="sxs-lookup"><span data-stu-id="40b54-108">The `Out-Printer` cmdlet sends output to the default printer or to an alternate printer, if one is specified.</span></span>

> [!NOTE]
> <span data-ttu-id="40b54-109">このコマンドレットは、PowerShell 7 で再導入されました。</span><span class="sxs-lookup"><span data-stu-id="40b54-109">This cmdlet was reintroduced in PowerShell 7.</span></span> <span data-ttu-id="40b54-110">このコマンドレットは、Windows デスクトップをサポートする Windows システムでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="40b54-110">This cmdlet is only available on Windows systems that support the Windows Desktop.</span></span>

## <span data-ttu-id="40b54-111">例</span><span class="sxs-lookup"><span data-stu-id="40b54-111">EXAMPLES</span></span>

### <span data-ttu-id="40b54-112">例 1-既定のプリンターに印刷するファイルを送信する</span><span class="sxs-lookup"><span data-stu-id="40b54-112">Example 1 - Send a file to be printed on the default printer</span></span>

<span data-ttu-id="40b54-113">この例では、に Path パラメーターがない場合でも、ファイルを印刷する方法を示し `Out-Printer` ます。 **Path**</span><span class="sxs-lookup"><span data-stu-id="40b54-113">This example shows how to print a file, even though `Out-Printer` does not have a **Path** parameter.</span></span>

```powershell
Get-Content -Path ./readme.txt | Out-Printer
```

<span data-ttu-id="40b54-114">`Get-Content`現在のディレクトリ内のファイルの内容を取得 `readme.txt` し、その内容をにパイプして `Out-Printer` 、既定のプリンターに送信します。</span><span class="sxs-lookup"><span data-stu-id="40b54-114">`Get-Content`gets the contents of the `readme.txt` file in the current directory and pipes it to `Out-Printer`, which sends it to the default printer.</span></span>

### <span data-ttu-id="40b54-115">例 2: リモートプリンターに文字列を出力する</span><span class="sxs-lookup"><span data-stu-id="40b54-115">Example 2: Print a string to a remote printer</span></span>

<span data-ttu-id="40b54-116">この例 `Hello, World` では、Server01 上の **Prt-6b カラー** プリンターに出力します。</span><span class="sxs-lookup"><span data-stu-id="40b54-116">This example prints `Hello, World` to the **Prt-6B Color** printer on Server01.</span></span>

```powershell
"Hello, World" | Out-Printer -Name "\\Server01\Prt-6B Color"
```

<span data-ttu-id="40b54-117">**Name** パラメーターは、既定値ではなく、特定のプリンターを選択します。</span><span class="sxs-lookup"><span data-stu-id="40b54-117">The **Name** parameter selects a specific printer, rather than the default.</span></span>

### <span data-ttu-id="40b54-118">例 3-既定のプリンターにヘルプトピックを印刷する</span><span class="sxs-lookup"><span data-stu-id="40b54-118">Example 3 - Print a help topic to the default printer</span></span>

<span data-ttu-id="40b54-119">この例では、のヘルプトピックの完全バージョンを出力し `Get-CimInstance` ます。</span><span class="sxs-lookup"><span data-stu-id="40b54-119">This example prints the full version of the Help topic for `Get-CimInstance`.</span></span>

```powershell
$H = Get-Help -Full Get-CimInstance
Out-Printer -InputObject $H
```

<span data-ttu-id="40b54-120">`Get-Help` のヘルプトピックの完全バージョンを取得 `Get-CimInstance` し、変数に格納し `$H` ます。</span><span class="sxs-lookup"><span data-stu-id="40b54-120">`Get-Help` gets the full version of the Help topic for `Get-CimInstance` and stores it in the `$H` variable.</span></span> <span data-ttu-id="40b54-121">**InputObject** パラメーターは、の値 `$H` をに渡し `Out-Printer` ます。</span><span class="sxs-lookup"><span data-stu-id="40b54-121">The **InputObject** parameter passes the value of `$H` to `Out-Printer`.</span></span>

## <span data-ttu-id="40b54-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="40b54-122">PARAMETERS</span></span>

### <span data-ttu-id="40b54-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="40b54-123">-InputObject</span></span>

<span data-ttu-id="40b54-124">プリンターに送信するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="40b54-124">Specifies the objects to be sent to the printer.</span></span> <span data-ttu-id="40b54-125">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="40b54-125">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="40b54-126">-Name</span><span class="sxs-lookup"><span data-stu-id="40b54-126">-Name</span></span>

<span data-ttu-id="40b54-127">指定されたプリンターに出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="40b54-127">Sends the output to the specified printer.</span></span> <span data-ttu-id="40b54-128">パラメーター **名は省略可能です。**</span><span class="sxs-lookup"><span data-stu-id="40b54-128">The parameter name **Name** is optional.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PrinterName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="40b54-129">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="40b54-129">CommonParameters</span></span>

<span data-ttu-id="40b54-130">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="40b54-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="40b54-131">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40b54-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="40b54-132">入力</span><span class="sxs-lookup"><span data-stu-id="40b54-132">INPUTS</span></span>

### <span data-ttu-id="40b54-133">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="40b54-133">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="40b54-134">パイプを使用して任意のオブジェクトをにパイプすることができ `Out-Printer` ます。</span><span class="sxs-lookup"><span data-stu-id="40b54-134">You can pipe any object to `Out-Printer`.</span></span>

## <span data-ttu-id="40b54-135">出力</span><span class="sxs-lookup"><span data-stu-id="40b54-135">OUTPUTS</span></span>

### <span data-ttu-id="40b54-136">なし</span><span class="sxs-lookup"><span data-stu-id="40b54-136">None</span></span>

<span data-ttu-id="40b54-137">`Out-Printer` はオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="40b54-137">`Out-Printer` does not return any objects.</span></span>

## <span data-ttu-id="40b54-138">注</span><span class="sxs-lookup"><span data-stu-id="40b54-138">NOTES</span></span>

<span data-ttu-id="40b54-139">動詞を含むコマンドレットは、 `Out` オブジェクトを書式設定しません。</span><span class="sxs-lookup"><span data-stu-id="40b54-139">The cmdlets that contain the `Out` verb do not format objects.</span></span> <span data-ttu-id="40b54-140">それらをレンダリングして、指定された表示先に送信するだけです。</span><span class="sxs-lookup"><span data-stu-id="40b54-140">They just render them and send them to the specified display destination.</span></span> <span data-ttu-id="40b54-141">書式設定されていないオブジェクトをコマンドレットに送信すると、コマンドレットによって、 `Out` レンダリングされる前に書式設定コマンドレットに送信されます。</span><span class="sxs-lookup"><span data-stu-id="40b54-141">If you send an unformatted object to an `Out` cmdlet, the cmdlet sends it to a formatting cmdlet before rendering it.</span></span>

<span data-ttu-id="40b54-142">`Out-Printer` プリンターにデータを送信しますが、パイプラインに出力オブジェクトを生成しません。</span><span class="sxs-lookup"><span data-stu-id="40b54-142">`Out-Printer` sends data to the printer, but does not emit any output objects to the pipeline.</span></span> <span data-ttu-id="40b54-143">パイプを使用しての出力をに渡した場合 `Out-Printer` `Get-Member` 、は `Get-Member` オブジェクトが指定されていないことを報告します。</span><span class="sxs-lookup"><span data-stu-id="40b54-143">If you pipe the output of `Out-Printer` to `Get-Member`, `Get-Member` reports that no objects have been specified.</span></span>

## <span data-ttu-id="40b54-144">関連リンク</span><span class="sxs-lookup"><span data-stu-id="40b54-144">RELATED LINKS</span></span>

[<span data-ttu-id="40b54-145">Out-File</span><span class="sxs-lookup"><span data-stu-id="40b54-145">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="40b54-146">Out-String</span><span class="sxs-lookup"><span data-stu-id="40b54-146">Out-String</span></span>](Out-String.md)
