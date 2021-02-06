---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-formatdata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-FormatData
ms.openlocfilehash: 28eab1709de12ec5d391009aacccfd4e973a8b9b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600981"
---
# <span data-ttu-id="a5684-102">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="a5684-102">Get-FormatData</span></span>

## <span data-ttu-id="a5684-103">概要</span><span class="sxs-lookup"><span data-stu-id="a5684-103">SYNOPSIS</span></span>
<span data-ttu-id="a5684-104">現在のセッションの書式設定データを取得します。</span><span class="sxs-lookup"><span data-stu-id="a5684-104">Gets the formatting data in the current session.</span></span>

## <span data-ttu-id="a5684-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a5684-105">SYNTAX</span></span>

```
Get-FormatData [[-TypeName] <String[]>] [-PowerShellVersion <Version>] [<CommonParameters>]
```

## <span data-ttu-id="a5684-106">Description</span><span class="sxs-lookup"><span data-stu-id="a5684-106">DESCRIPTION</span></span>

<span data-ttu-id="a5684-107">`Get-FormatData`コマンドレットでは、現在のセッションの書式設定データを取得します。</span><span class="sxs-lookup"><span data-stu-id="a5684-107">The `Get-FormatData` cmdlet gets the formatting data in the current session.</span></span>

<span data-ttu-id="a5684-108">セッションの書式設定データには、ディレクトリ内のファイルなどの書式設定ファイルからの書式設定データ、 `Format.ps1xml` `$PSHOME` セッションにインポートするモジュールのデータの書式設定、コマンドレットを使用してセッションにインポートするコマンドのデータの書式設定などがあり `Import-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="a5684-108">The formatting data in the session includes formatting data from `Format.ps1xml` formatting files, such as those in the `$PSHOME` directory, formatting data for modules that you import into the session, and formatting data for commands that you import into your session by using the `Import-PSSession` cmdlet.</span></span>

<span data-ttu-id="a5684-109">このコマンドレットを使用すると、書式設定データを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a5684-109">You can use this cmdlet to examine the formatting data.</span></span> <span data-ttu-id="a5684-110">次に、コマンドレットを使用して `Export-FormatData` オブジェクトをシリアル化し、XML に変換して、ファイルに保存し `Format.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="a5684-110">Then, you can use the `Export-FormatData` cmdlet to serialize the objects, convert them to XML, and save them in `Format.ps1xml` files.</span></span>

<span data-ttu-id="a5684-111">PowerShell でのファイルの書式設定の詳細については、「 [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5684-111">For more information about formatting files in PowerShell, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

## <span data-ttu-id="a5684-112">例</span><span class="sxs-lookup"><span data-stu-id="a5684-112">EXAMPLES</span></span>

### <span data-ttu-id="a5684-113">例 1: すべての書式設定データを取得する</span><span class="sxs-lookup"><span data-stu-id="a5684-113">Example 1: Get all formatting data</span></span>

<span data-ttu-id="a5684-114">この例では、セッションのすべての書式設定データを取得します。</span><span class="sxs-lookup"><span data-stu-id="a5684-114">This example gets all the formatting data in the session.</span></span>

```powershell
Get-FormatData
```

### <span data-ttu-id="a5684-115">例 2: 型名で書式設定データを取得する</span><span class="sxs-lookup"><span data-stu-id="a5684-115">Example 2: Get formatting data by type name</span></span>

<span data-ttu-id="a5684-116">この例では、名前がで始まる書式設定データ項目を取得し `System.Management.Automation.Cmd` ます。</span><span class="sxs-lookup"><span data-stu-id="a5684-116">This example gets the formatting data items whose names begin with `System.Management.Automation.Cmd`.</span></span>

```powershell
Get-FormatData -TypeName 'System.Management.Automation.Cmd*'
```

### <span data-ttu-id="a5684-117">例 3: 書式設定データオブジェクトを確認する</span><span class="sxs-lookup"><span data-stu-id="a5684-117">Example 3: Examine a formatting data object</span></span>

<span data-ttu-id="a5684-118">この例では、書式設定データ オブジェクトを取得し、そのプロパティを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a5684-118">This example shows how to get a formatting data object and examine its properties.</span></span>

```powershell
$F = Get-FormatData -TypeName 'System.Management.Automation.Cmd*'
$F
```

```Output
TypeName        FormatViewDefinition
--------        --------------------
HelpInfoShort   {help , TableControl}
```

```powershell
$F.FormatViewDefinition[0].control
```

```Output
Headers          : {System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader,
                   System.Management.Automation.TableControlColumnHeader}
Rows             : {System.Management.Automation.TableControlRow}
AutoSize         : False
HideTableHeaders : False
GroupBy          :
OutOfBand        : False
```

```powershell
$F.FormatViewDefinition[0].control.Headers
```

```Output
Label       Alignment Width
-----       --------- -----
CommandType Undefined    15
Name        Undefined    50
Version     Undefined    10
Source      Undefined     0
```

### <span data-ttu-id="a5684-119">例 4: 書式設定データを取得してエクスポートする</span><span class="sxs-lookup"><span data-stu-id="a5684-119">Example 4: Get formatting data and export it</span></span>

<span data-ttu-id="a5684-120">この例では、およびを使用し `Get-FormatData` `Export-FormatData` て、モジュールによって追加された書式設定データをエクスポートする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a5684-120">This example shows how to use `Get-FormatData` and `Export-FormatData` to export the formatting data that is added by a module.</span></span>

```powershell
$A = Get-FormatData
Import-Module bitstransfer
$B = Get-FormatData
Compare-Object $A $B
```

```Output
InputObject                                                SideIndicator
-----------                                                -------------
Microsoft.BackgroundIntelligentTransfer.Management.BitsJob =>
```

```powershell
Get-FormatData *bits* | Export-FormatData -FilePath c:\test\bits.format.ps1xml
Get-Content c:\test\bits.format.ps1xml
```

```Output
<?xml version="1.0" encoding="utf-8"?><Configuration><ViewDefinitions>
<View><Name>Microsoft.BackgroundIntelligentTransfer.Management.BitsJob</Name>
...
```

<span data-ttu-id="a5684-121">最初の4つのコマンドは `Get-FormatData` 、、、およびコマンドレットを使用して、 `Import-Module` `Compare-Object` **BitsTransfer** モジュールがセッションに追加するフォーマットの種類を識別します。</span><span class="sxs-lookup"><span data-stu-id="a5684-121">The first four commands use the `Get-FormatData`, `Import-Module`, and `Compare-Object` cmdlets to identify the format type that the **BitsTransfer** module adds to the session.</span></span>

<span data-ttu-id="a5684-122">5番目のコマンドは、コマンドレットを使用して、 `Get-FormatData` **BitsTransfer** モジュールによって追加される形式の種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="a5684-122">The fifth command uses the `Get-FormatData` cmdlet to get the format type that the **BitsTransfer** module adds.</span></span> <span data-ttu-id="a5684-123">パイプライン演算子 () を使用して、 `|` format type オブジェクトをコマンドレットに送信します。これにより、 `Export-FormatData` XML に変換され、指定したファイルに保存され `format.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="a5684-123">It uses a pipeline operator (`|`) to send the format type object to the `Export-FormatData` cmdlet, which converts it back to XML and saves it in the specified `format.ps1xml` file.</span></span>

<span data-ttu-id="a5684-124">最後のコマンドは、ファイルの内容の抜粋を示し `format.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="a5684-124">The final command shows an excerpt of the `format.ps1xml` file content.</span></span>

### <span data-ttu-id="a5684-125">例 5: PowerShell の指定したバージョンに基づいて書式設定データを取得する</span><span class="sxs-lookup"><span data-stu-id="a5684-125">Example 5: Get formatting data based on the specified version of PowerShell</span></span>

<span data-ttu-id="a5684-126">この例では、を使用して `Get-FormatData` 、指定した **TypeName** と PowerShell バージョンの書式データを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a5684-126">This example shows how to use `Get-FormatData` to get format data for a specified **TypeName** and PowerShell version.</span></span>

```powershell
Get-FormatData -TypeName 'Microsoft.Powershell.Utility.FileHash' -PowerShellVersion $PSVersionTable.PSVersion

TypeNames                               FormatViewDefinition
---------                               --------------------
{Microsoft.Powershell.Utility.FileHash} {Microsoft.Powershell.Utility.FileHash}
```

## <span data-ttu-id="a5684-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a5684-127">PARAMETERS</span></span>

### <span data-ttu-id="a5684-128">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="a5684-128">-PowerShellVersion</span></span>

<span data-ttu-id="a5684-129">このコマンドレットによって書式設定データに対して取得される PowerShell のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5684-129">Specify the version of PowerShell this cmdlet gets for the formatting data.</span></span> <span data-ttu-id="a5684-130">ピリオドで区切られた2桁の数字を入力してください。</span><span class="sxs-lookup"><span data-stu-id="a5684-130">Enter a two digit number separated by a period.</span></span>

<span data-ttu-id="a5684-131">Powershell 5.1 では、旧バージョンの PowerShell を実行しているリモート処理コンピューターの互換性を向上させるために、このパラメーターが追加されました。</span><span class="sxs-lookup"><span data-stu-id="a5684-131">This parameter was added in PowerShell 5.1 to improve compatibility when remoting computers running older versions of PowerShell.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a5684-132">-TypeName</span><span class="sxs-lookup"><span data-stu-id="a5684-132">-TypeName</span></span>

<span data-ttu-id="a5684-133">このコマンドレットが書式設定データに対して取得する型名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5684-133">Specifies the type names that this cmdlet gets for the formatting data.</span></span>
<span data-ttu-id="a5684-134">型名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a5684-134">Enter the type names.</span></span>
<span data-ttu-id="a5684-135">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a5684-135">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="a5684-136">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5684-136">CommonParameters</span></span>

<span data-ttu-id="a5684-137">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a5684-137">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a5684-138">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5684-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a5684-139">入力</span><span class="sxs-lookup"><span data-stu-id="a5684-139">INPUTS</span></span>

### <span data-ttu-id="a5684-140">なし</span><span class="sxs-lookup"><span data-stu-id="a5684-140">None</span></span>

<span data-ttu-id="a5684-141">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="a5684-141">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="a5684-142">出力</span><span class="sxs-lookup"><span data-stu-id="a5684-142">OUTPUTS</span></span>

### <span data-ttu-id="a5684-143">システムの管理. ExtendedTypeDefinition</span><span class="sxs-lookup"><span data-stu-id="a5684-143">System.Management.Automation.ExtendedTypeDefinition</span></span>

## <span data-ttu-id="a5684-144">注</span><span class="sxs-lookup"><span data-stu-id="a5684-144">NOTES</span></span>

## <span data-ttu-id="a5684-145">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a5684-145">RELATED LINKS</span></span>

[<span data-ttu-id="a5684-146">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="a5684-146">Export-FormatData</span></span>](Export-FormatData.md)

[<span data-ttu-id="a5684-147">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="a5684-147">Update-FormatData</span></span>](Update-FormatData.md)
