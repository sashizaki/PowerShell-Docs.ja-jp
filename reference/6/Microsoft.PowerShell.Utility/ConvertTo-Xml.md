---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-xml?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Xml
ms.openlocfilehash: 09e962d96bffc1c890a4532502e1f3461180caae
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216779"
---
# <span data-ttu-id="5f5e5-103">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="5f5e5-103">ConvertTo-Xml</span></span>

## <span data-ttu-id="5f5e5-104">概要</span><span class="sxs-lookup"><span data-stu-id="5f5e5-104">SYNOPSIS</span></span>
<span data-ttu-id="5f5e5-105">オブジェクトの XML ベースの表現を作成します。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-105">Creates an XML-based representation of an object.</span></span>

## <span data-ttu-id="5f5e5-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5f5e5-106">SYNTAX</span></span>

```
ConvertTo-Xml [-Depth <Int32>] [-InputObject] <PSObject> [-NoTypeInformation] [-As <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="5f5e5-107">Description</span><span class="sxs-lookup"><span data-stu-id="5f5e5-107">DESCRIPTION</span></span>

<span data-ttu-id="5f5e5-108">`ConvertTo-Xml`コマンドレットでは、1つ以上の .net オブジェクトの[XML ベース](/dotnet/api/system.xml.xmldocument)の表現を作成します。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-108">The `ConvertTo-Xml` cmdlet creates an [XML-based](/dotnet/api/system.xml.xmldocument) representation of one or more more .NET objects.</span></span> <span data-ttu-id="5f5e5-109">このコマンドレットを使用するには、1つまたは複数のオブジェクトをコマンドレットにパイプするか、 **InputObject** パラメーターを使用してオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-109">To use this cmdlet, pipe one or more objects to the cmdlet, or use the **InputObject** parameter to specify the object.</span></span>

<span data-ttu-id="5f5e5-110">複数のオブジェクトをにパイプする場合 `ConvertTo-Xml` 、または **InputObject** パラメーターを使用して複数のオブジェクトを送信する場合、は、 `ConvertTo-Xml` すべてのオブジェクトの表現を含む単一のメモリ内 XML ドキュメントを返します。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-110">When you pipe multiple objects to `ConvertTo-Xml` or use the **InputObject** parameter to submit multiple objects, `ConvertTo-Xml` returns a single, in-memory XML document that includes representations of all of the objects.</span></span>

<span data-ttu-id="5f5e5-111">このコマンドレットは [export-clixml](./Export-Clixml.md) に似ていますが、では `Export-Clixml` 、結果の XML が [共通言語基盤 (CLI) の xml](https://www.ecma-international.org/publications/standards/Ecma-335.htm) ファイルに格納されます。これは、 [export-clixml](./Import-Clixml.md)を使用してオブジェクトとして再インポートできます。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-111">This cmdlet is similar to [Export-Clixml](./Export-Clixml.md) except that `Export-Clixml` stores the resulting XML in a [Common Language Infrastructure(CLI) XML](https://www.ecma-international.org/publications/standards/Ecma-335.htm) file that can be reimported as objects with [Import-Clixml](./Import-Clixml.md).</span></span> <span data-ttu-id="5f5e5-112">`ConvertTo-Xml` は、XML ドキュメントのメモリ内表現を返します。そのため、PowerShell で処理を続行できます。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-112">`ConvertTo-Xml` returns an in-memory representation of an XML document, so you can continue to process it in PowerShell.</span></span> <span data-ttu-id="5f5e5-113">`ConvertTo-Xml` には、オブジェクトを CLI XML に変換するオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-113">`ConvertTo-Xml` does not have an option to convert objects to CLI XML.</span></span>

## <span data-ttu-id="5f5e5-114">例</span><span class="sxs-lookup"><span data-stu-id="5f5e5-114">EXAMPLES</span></span>

### <span data-ttu-id="5f5e5-115">例 1: 日付を XML に変換する</span><span class="sxs-lookup"><span data-stu-id="5f5e5-115">Example 1: Convert a date to XML</span></span>

```
PS C:\> Get-Date | ConvertTo-Xml
```

<span data-ttu-id="5f5e5-116">このコマンドは、現在の日付 ( **DateTime** オブジェクト) を XML に変換します。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-116">This command converts the current date (a **DateTime** object) to XML.</span></span>

### <span data-ttu-id="5f5e5-117">例 2: プロセスを XML に変換する</span><span class="sxs-lookup"><span data-stu-id="5f5e5-117">Example 2: Convert processes to XML</span></span>

```
PS C:\> ConvertTo-Xml -As "Document" -InputObject (Get-Process) -Depth 3
```

<span data-ttu-id="5f5e5-118">このコマンドは、コンピューター上のすべてのプロセスを表すプロセス オブジェクトを XML ドキュメントに変換します。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-118">This command converts the process objects that represent all of the processes on the computer into an XML document.</span></span> <span data-ttu-id="5f5e5-119">オブジェクトは、3 レベルの深さに拡張されます。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-119">The objects are expanded to a depth of three levels.</span></span>

## <span data-ttu-id="5f5e5-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5f5e5-120">PARAMETERS</span></span>

### <span data-ttu-id="5f5e5-121">-As</span><span class="sxs-lookup"><span data-stu-id="5f5e5-121">-As</span></span>

<span data-ttu-id="5f5e5-122">出力形式を決定します。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-122">Determines the output format.</span></span>
<span data-ttu-id="5f5e5-123">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-123">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5f5e5-124">文字列 をオンにします。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-124">String.</span></span>
<span data-ttu-id="5f5e5-125">1 つの文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-125">Returns a single string.</span></span>
- <span data-ttu-id="5f5e5-126">ストリーム。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-126">Stream.</span></span>
<span data-ttu-id="5f5e5-127">文字列の配列を返します。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-127">Returns an array of strings.</span></span>
- <span data-ttu-id="5f5e5-128">ドキュメントです。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-128">Document.</span></span>
<span data-ttu-id="5f5e5-129">**XmlDocument** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-129">Returns an **XmlDocument** object.</span></span>

<span data-ttu-id="5f5e5-130">既定値は Document です。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-130">The default value is Document.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Stream, String, Document

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5f5e5-131">-深さ</span><span class="sxs-lookup"><span data-stu-id="5f5e5-131">-Depth</span></span>

<span data-ttu-id="5f5e5-132">XML 表現に含める子オブジェクトのレベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-132">Specifies how many levels of contained objects are included in the XML representation.</span></span> <span data-ttu-id="5f5e5-133">既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-133">The default value is 1.</span></span>

<span data-ttu-id="5f5e5-134">たとえば、オブジェクトのプロパティにオブジェクトが含まれる場合、子オブジェクトのプロパティの XML 表現を保存するには、深さのレベルとして 2 を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-134">For example, if the object's properties also contain objects, to save an XML representation of the properties of the contained objects, you must specify a depth of 2.</span></span>

<span data-ttu-id="5f5e5-135">既定値は、Types.ps1xml ファイル内のオブジェクトの型に対してオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-135">The default value can be overridden for the object type in the Types.ps1xml files.</span></span> <span data-ttu-id="5f5e5-136">詳細については、「about_Types.ps1xml」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-136">For more information, see about_Types.ps1xml.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5f5e5-137">-InputObject</span><span class="sxs-lookup"><span data-stu-id="5f5e5-137">-InputObject</span></span>

<span data-ttu-id="5f5e5-138">変換するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-138">Specifies the object to be converted.</span></span> <span data-ttu-id="5f5e5-139">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-139">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="5f5e5-140">パイプを使用してオブジェクトを **convertto-html** にパイプすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-140">You can also pipe objects to **ConvertTo-XML** .</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5f5e5-141">-NoTypeInformation</span><span class="sxs-lookup"><span data-stu-id="5f5e5-141">-NoTypeInformation</span></span>

<span data-ttu-id="5f5e5-142">オブジェクト ノードから Type 属性を削除します。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-142">Omits the Type attribute from the object nodes.</span></span>

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

### <span data-ttu-id="5f5e5-143">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5f5e5-143">CommonParameters</span></span>

<span data-ttu-id="5f5e5-144">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5f5e5-145">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5f5e5-146">入力</span><span class="sxs-lookup"><span data-stu-id="5f5e5-146">INPUTS</span></span>

### <span data-ttu-id="5f5e5-147">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="5f5e5-147">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="5f5e5-148">パイプを使用して任意のオブジェクトを **convertto-html** に送ることができます。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-148">You can pipe any object to **ConvertTo-XML** .</span></span>

## <span data-ttu-id="5f5e5-149">出力</span><span class="sxs-lookup"><span data-stu-id="5f5e5-149">OUTPUTS</span></span>

### <span data-ttu-id="5f5e5-150">System.string または System.Xml.Xmlドキュメント</span><span class="sxs-lookup"><span data-stu-id="5f5e5-150">System.String or System.Xml.XmlDocument</span></span>

<span data-ttu-id="5f5e5-151">As パラメーターの値によっ *て* 、 **convertto-html** が返すオブジェクトの型が決まります。</span><span class="sxs-lookup"><span data-stu-id="5f5e5-151">The value of the *As* parameter determines the type of object that **ConvertTo-XML** returns.</span></span>

## <span data-ttu-id="5f5e5-152">注</span><span class="sxs-lookup"><span data-stu-id="5f5e5-152">NOTES</span></span>

## <span data-ttu-id="5f5e5-153">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5f5e5-153">RELATED LINKS</span></span>

[<span data-ttu-id="5f5e5-154">ConvertTo-Csv</span><span class="sxs-lookup"><span data-stu-id="5f5e5-154">ConvertTo-Csv</span></span>](ConvertTo-Csv.md)

[<span data-ttu-id="5f5e5-155">ConvertTo-Html</span><span class="sxs-lookup"><span data-stu-id="5f5e5-155">ConvertTo-Html</span></span>](ConvertTo-Html.md)

[<span data-ttu-id="5f5e5-156">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="5f5e5-156">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="5f5e5-157">Get-Date</span><span class="sxs-lookup"><span data-stu-id="5f5e5-157">Get-Date</span></span>](Get-Date.md)

[<span data-ttu-id="5f5e5-158">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="5f5e5-158">Import-Clixml</span></span>](Import-Clixml.md)
