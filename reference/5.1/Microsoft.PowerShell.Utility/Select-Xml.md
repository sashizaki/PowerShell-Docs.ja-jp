---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/select-xml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Select-Xml
ms.openlocfilehash: eb5684ed281b3ba05629528bb12b44577f8c050a
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "93218152"
---
# <span data-ttu-id="8080d-103">Select-Xml</span><span class="sxs-lookup"><span data-stu-id="8080d-103">Select-Xml</span></span>

## <span data-ttu-id="8080d-104">概要</span><span class="sxs-lookup"><span data-stu-id="8080d-104">SYNOPSIS</span></span>
<span data-ttu-id="8080d-105">XML 文字列または XML ドキュメント内のテキストを検索します。</span><span class="sxs-lookup"><span data-stu-id="8080d-105">Finds text in an XML string or document.</span></span>

## <span data-ttu-id="8080d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8080d-106">SYNTAX</span></span>

### <span data-ttu-id="8080d-107">Xml (既定値)</span><span class="sxs-lookup"><span data-stu-id="8080d-107">Xml (Default)</span></span>

```
Select-Xml [-Xml] <XmlNode[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### <span data-ttu-id="8080d-108">Path</span><span class="sxs-lookup"><span data-stu-id="8080d-108">Path</span></span>

```
Select-Xml [-Path] <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### <span data-ttu-id="8080d-109">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8080d-109">LiteralPath</span></span>

```
Select-Xml -LiteralPath <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

### <span data-ttu-id="8080d-110">Content</span><span class="sxs-lookup"><span data-stu-id="8080d-110">Content</span></span>

```
Select-Xml -Content <String[]> [-XPath] <String> [-Namespace <Hashtable>] [<CommonParameters>]
```

## <span data-ttu-id="8080d-111">Description</span><span class="sxs-lookup"><span data-stu-id="8080d-111">DESCRIPTION</span></span>

<span data-ttu-id="8080d-112">Xml **コマンドレット** を使用すると、XPath クエリを使用して、Xml 文字列とドキュメント内のテキストを検索できます。</span><span class="sxs-lookup"><span data-stu-id="8080d-112">The **Select-Xml** cmdlet lets you use XPath queries to search for text in XML strings and documents.</span></span>
<span data-ttu-id="8080d-113">XPath クエリを入力し、 *Content* 、 *Path* 、または *xml* パラメーターを使用して、検索する xml を指定します。</span><span class="sxs-lookup"><span data-stu-id="8080d-113">Enter an XPath query, and use the *Content* , *Path* , or *Xml* parameter to specify the XML to be searched.</span></span>

## <span data-ttu-id="8080d-114">例</span><span class="sxs-lookup"><span data-stu-id="8080d-114">EXAMPLES</span></span>

### <span data-ttu-id="8080d-115">例 1: [エイリアス] プロパティノードを選択する</span><span class="sxs-lookup"><span data-stu-id="8080d-115">Example 1: Select AliasProperty nodes</span></span>

```
PS C:\> $Path = "$Pshome\Types.ps1xml"
PS C:\> $XPath = "/Types/Type/Members/AliasProperty"
PS C:\> Select-Xml -Path $Path -XPath $Xpath | Select-Object -ExpandProperty Node
Name                 ReferencedMemberName
----                 --------------------
Count                Length
Name                 Key
Name                 ServiceName
RequiredServices     ServicesDependedOn
ProcessName          Name
Handles              Handlecount
VM                   VirtualSize
WS                   WorkingSetSize
Name                 ProcessName
Handles              Handlecount
VM                   VirtualMemorySize
WS                   WorkingSet
PM                   PagedMemorySize
NPM                  NonpagedSystemMemorySize
Name                 __Class
Namespace            ModuleName
```

<span data-ttu-id="8080d-116">この例では、Types.ps1xml のエイリアス プロパティを取得します</span><span class="sxs-lookup"><span data-stu-id="8080d-116">This example gets the alias properties in the Types.ps1xml.</span></span>
<span data-ttu-id="8080d-117">(このファイルの詳細については、「about_Types.ps1xml」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="8080d-117">(For information about this file, see about_Types.ps1xml.)</span></span>

<span data-ttu-id="8080d-118">最初のコマンドは、Types.ps1xml ファイルのパスを $Path 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="8080d-118">The first command saves the path to the Types.ps1xml file in the $Path variable.</span></span>

<span data-ttu-id="8080d-119">2 番目のコマンドは、AliasProperty ノードの XML パスを $XPath 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="8080d-119">The second command saves the XML path to the AliasProperty node in the $XPath variable.</span></span>

<span data-ttu-id="8080d-120">3 番目のコマンドは、 **Select-Xml** コマンドレットを使用して、XPath ステートメントで特定された Types.ps1xml ファイルの AliasProperty ノードを取得します。</span><span class="sxs-lookup"><span data-stu-id="8080d-120">The third command uses the **Select-Xml** cmdlet to get the AliasProperty nodes that are identified by the XPath statement from the Types.ps1xml file.</span></span>
<span data-ttu-id="8080d-121">このコマンドは、パイプライン演算子を使用して、エイリアスプロパティノードを Select-Object コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="8080d-121">The command uses a pipeline operator to send the AliasProperty nodes to the Select-Object cmdlet.</span></span>
<span data-ttu-id="8080d-122">*Expandproperty* パラメーターを指定すると、 **Node** オブジェクトが展開され、Name プロパティと referencedmembername プロパティが返されます。</span><span class="sxs-lookup"><span data-stu-id="8080d-122">The *ExpandProperty* parameter expands the **Node** object and returns its Name and ReferencedMemberName properties.</span></span>

<span data-ttu-id="8080d-123">結果には、Types.ps1xml ファイルの各エイリアス プロパティの Name と ReferencedMemberName が示されています。</span><span class="sxs-lookup"><span data-stu-id="8080d-123">The result shows the Name and ReferencedMemberName of each alias property in the Types.ps1xml file.</span></span>
<span data-ttu-id="8080d-124">たとえば、 **Length** プロパティのエイリアスである **Count** プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="8080d-124">For example, there is a **Count** property that is an alias of the **Length** property.</span></span>

### <span data-ttu-id="8080d-125">例 2: XML ドキュメントを入力する</span><span class="sxs-lookup"><span data-stu-id="8080d-125">Example 2: Input an XML document</span></span>

```
PS C:\> [xml]$Types = Get-Content $Pshome\Types.ps1xml
PS C:\> Select-Xml -Xml $Types -XPath "//MethodName"
```

<span data-ttu-id="8080d-126">この *例では、xml パラメーターを* 使用して、xml ドキュメントを xml **コマンドレット** に提供する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8080d-126">This example shows how to use the *XML* parameter to provide an XML document to the **Select-Xml** cmdlet.</span></span>

<span data-ttu-id="8080d-127">最初のコマンドは、Get-Content コマンドレットを使用して Types.ps1xml ファイルの内容を取得し、$Types 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="8080d-127">The first command uses the Get-Content cmdlet to get the content of the Types.ps1xml file and save it in the $Types variable.</span></span>
<span data-ttu-id="8080d-128">Xml は、 \[ \] 変数を xml オブジェクトとしてキャストします。</span><span class="sxs-lookup"><span data-stu-id="8080d-128">The \[xml\] casts the variable as an XML object.</span></span>

<span data-ttu-id="8080d-129">2 番目のコマンドは、 **Select-Xml** コマンドレットを使用して、Types.ps1xml ファイルの MethodName ノードを取得します。</span><span class="sxs-lookup"><span data-stu-id="8080d-129">The second command uses the **Select-Xml** cmdlet to get the MethodName nodes in the Types.ps1xml file.</span></span>
<span data-ttu-id="8080d-130">このコマンドは、 *Xml* パラメーターを使用して $Types 変数内の XML コンテンツを指定し、 *XPath* パラメーターを使用して MethodName ノードのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="8080d-130">The command uses the *Xml* parameter to specify the XML content in the $Types variable and the *XPath* parameter to specify the path to the MethodName node.</span></span>

### <span data-ttu-id="8080d-131">例 3: PowerShell ヘルプファイルを検索する</span><span class="sxs-lookup"><span data-stu-id="8080d-131">Example 3: Search PowerShell Help files</span></span>

```
PS C:\> $Namespace = @{command = "http://schemas.microsoft.com/maml/dev/command/2004/10"; maml = "http://schemas.microsoft.com/maml/2004/10"; dev = "http://schemas.microsoft.com/maml/dev/2004/10"}

The second command saves the path to the help files in the $Path variable.If there are no help files in this path on your computer, use the Update-Help cmdlet to download the help files. For more information about Updatable Help, see about_Updatable_Help (https://go.microsoft.com/fwlink/?LinkId=235801).
PS C:\> $Path = "$Pshome\en-us\*dll-Help.xml"

The third command uses the **Select-Xml** cmdlet to search the XML for cmdlet names by finding Command:Name element anywhere in the files. It saves the results in the $Xml variable.**Select-Xml** returns a **SelectXmlInfo** object that has a Node property, which is a **System.Xml.XmlElement** object. The Node property has an InnerXML property, which contains the actual XML that is retrieved.
PS C:\> $Xml = Select-Xml -Path $Path -Namespace $Namespace -XPath "//command:name"

The fourth command sends the XML in the $Xml variable to the Format-Table cmdlet. The **Format-Table** command uses a calculated property to get the Node.InnerXML property of each object in the $Xml variable, trim the white space before and after the text, and display it in the table, along with the path to the source file.
PS C:\> $Xml | Format-Table @{Label="Name"; Expression= {($_.node.innerxml).trim()}}, Path -AutoSize

Name                    Path
----                    ----
Export-Counter          C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Get-Counter             C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Get-WinEvent            C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Import-Counter          C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Diagnostics.dll-Help.xml
Add-Computer            C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Management.dll-Help.xml
Add-Content             C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Management.dll-Help.xml
Checkpoint-Computer     C:\Windows\system32\WindowsPowerShell\v1.0\en-us\Microsoft.PowerShell.Commands.Management.dll-Help.xml
...
```

<span data-ttu-id="8080d-132">この **例では、xml コマンドレット** を使用して、POWERSHELL の xml ベースのコマンドレットヘルプファイルを検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8080d-132">This example shows how to use the **Select-Xml** cmdlet to search the PowerShell XML-based cmdlet help files.</span></span>
<span data-ttu-id="8080d-133">各ヘルプ ファイルのタイトルとなるコマンドレット名とヘルプ ファイルのパスを検索します。</span><span class="sxs-lookup"><span data-stu-id="8080d-133">In this example, we'll search for the cmdlet name that serves as a title for each help file and the path to the help file.</span></span>

<span data-ttu-id="8080d-134">最初のコマンドは、ヘルプ ファイルに使用されている XML 名前空間を表すハッシュ テーブルを作成し、$Namespace 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="8080d-134">The first command creates a hash table that represents the XML namespace that is used for the help files and saves it in the $Namespace variable.</span></span>

### <span data-ttu-id="8080d-135">例 4: XML を入力するさまざまな方法</span><span class="sxs-lookup"><span data-stu-id="8080d-135">Example 4: Different ways to input XML</span></span>

```
PS C:\> $Xml = @"
<?xml version="1.0" encoding="utf-8"?>
<Book>
  <projects>
    <project name="Book1" date="2009-01-20">
      <editions>
        <edition language="English">En.Book1.com</edition>
        <edition language="German">Ge.Book1.Com</edition>
        <edition language="French">Fr.Book1.com</edition>
        <edition language="Polish">Pl.Book1.com</edition>
      </editions>
    </project>
  </projects>
</Book>
"@

The second command uses the *Content* parameter of **Select-Xml** to specify the XML in the $Xml variable.
PS C:\> Select-Xml -Content $Xml -XPath "//edition" | foreach {$_.node.InnerXML}

En.Book1.com
Ge.Book1.Com
Fr.Book1.com
Pl.Book1.com

The third command is equivalent to the second. It uses a pipeline operator (|) to send the XML in the $Xml variable to the **Select-Xml** cmdlet.
PS C:\> $Xml | Select-Xml -XPath "//edition" | foreach {$_.node.InnerXML}

En.Book1.com
Ge.Book1.Com
Fr.Book1.com
Pl.Book1.com
```

<span data-ttu-id="8080d-136">この例では、2つの異なる方法で XML を **選択して xml** コマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="8080d-136">This example shows two different ways to send XML to the **Select-Xml** cmdlet.</span></span>

<span data-ttu-id="8080d-137">最初のコマンドは、XML を含む文字列を $Xml 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="8080d-137">The first command saves a here-string that contains XML in the $Xml variable.</span></span>
<span data-ttu-id="8080d-138">(ヒア文字列の詳細については、「about_Quoting_Rules」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="8080d-138">(For more information about here-strings, see about_Quoting_Rules.)</span></span>

### <span data-ttu-id="8080d-139">例 5: 既定の xmlns 名前空間を使用する</span><span class="sxs-lookup"><span data-stu-id="8080d-139">Example 5: Use the default xmlns namespace</span></span>

```
PS C:\> $SnippetNamespace = @{snip = "http://schemas.microsoft.com/PowerShell/Snippets"}

The second command uses the **Select-Xml** cmdlet to get the content of the Title element of each snippet. It uses the *Path* parameter to specify the Snippets directory and the *Namespace* parameter to specify the namespace in the $SnippetNamespace variable. The value of the *XPath* parameter is the "snip" namespace key, a colon (:), and the name of the Title element.The command uses a pipeline operator (|) to send each **Node** property that **Select-Xml** returns to the ForEach-Object cmdlet, which gets the title in the value of the **InnerXml** property of the node.
PS C:\> Select-Xml -Path $Home\Documents\WindowsPowerShell\Snippets -Namespace $SnippetNamespace -XPath "//snip:Title" | foreach {$_.Node.Innerxml}
```

<span data-ttu-id="8080d-140">この例では、既定の xmlns 名前空間を使用する XML ドキュメントで、 **xml** コマンドレットを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8080d-140">This example shows how to use the **Select-Xml** cmdlet with XML documents that use the default xmlns namespace.</span></span>
<span data-ttu-id="8080d-141">例として、ユーザーが作成した Windows PowerShell ISE のスニペット ファイルのタイトルを取得します。</span><span class="sxs-lookup"><span data-stu-id="8080d-141">The example gets the titles of Windows PowerShell ISE user-created snippet files.</span></span>
<span data-ttu-id="8080d-142">スニペットの詳細については、「New-IseSnippet」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8080d-142">For information about snippets, see New-IseSnippet.</span></span>

<span data-ttu-id="8080d-143">最初のコマンドは、スニペット XML ファイルが使用する既定の名前空間のハッシュテーブルを作成し、$SnippetNamespace 変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="8080d-143">The first command creates a hash table for the default namespace that snippet XML files use and assigns it to the $SnippetNamespace variable.</span></span>
<span data-ttu-id="8080d-144">ハッシュ テーブルの値は、スニペット XML の XMLNS スキーマ URI です。</span><span class="sxs-lookup"><span data-stu-id="8080d-144">The hash table value is the XMLNS schema URI in the snippet XML.</span></span>
<span data-ttu-id="8080d-145">ハッシュテーブルのキー名 (切り取り) は任意です。</span><span class="sxs-lookup"><span data-stu-id="8080d-145">The hash table key name, snip, is arbitrary.</span></span>
<span data-ttu-id="8080d-146">予約されていない任意の名前を使用できますが、xmlns は使用できません。</span><span class="sxs-lookup"><span data-stu-id="8080d-146">You can use any name that is not reserved, but you cannot use xmlns.</span></span>

## <span data-ttu-id="8080d-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8080d-147">PARAMETERS</span></span>

### <span data-ttu-id="8080d-148">-コンテンツ</span><span class="sxs-lookup"><span data-stu-id="8080d-148">-Content</span></span>

<span data-ttu-id="8080d-149">検索対象の XML を含む文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="8080d-149">Specifies a string that contains the XML to search.</span></span>
<span data-ttu-id="8080d-150">パイプを使用して文字列を **選択** することもできます。</span><span class="sxs-lookup"><span data-stu-id="8080d-150">You can also pipe strings to **Select-Xml**.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Content
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8080d-151">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="8080d-151">-LiteralPath</span></span>

<span data-ttu-id="8080d-152">検索対象の XML ファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8080d-152">Specifies the paths and file names of the XML files to search.</span></span>
<span data-ttu-id="8080d-153">*Path* と異なり、 *LiteralPath* パラメーターの値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="8080d-153">Unlike *Path* , the value of the *LiteralPath* parameter is used exactly as it is typed.</span></span>
<span data-ttu-id="8080d-154">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="8080d-154">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="8080d-155">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="8080d-155">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="8080d-156">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="8080d-156">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8080d-157">-Namespace</span><span class="sxs-lookup"><span data-stu-id="8080d-157">-Namespace</span></span>

<span data-ttu-id="8080d-158">XML で使用されている名前空間のハッシュ テーブルを指定します。</span><span class="sxs-lookup"><span data-stu-id="8080d-158">Specifies a hash table of the namespaces used in the XML.</span></span>
<span data-ttu-id="8080d-159">@ {} の形式を使用し \<namespaceName\>  =  \<namespaceValue\> ます。</span><span class="sxs-lookup"><span data-stu-id="8080d-159">Use the format @{\<namespaceName\> = \<namespaceValue\>}.</span></span>

<span data-ttu-id="8080d-160">XML で既定の名前空間 (xmlns で始まる) を使用する場合は、名前空間名に任意のキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="8080d-160">When the XML uses the default namespace, which begins with xmlns, use an arbitrary key for the namespace name.</span></span>
<span data-ttu-id="8080d-161">Xmlns は使用できません。</span><span class="sxs-lookup"><span data-stu-id="8080d-161">You cannot use xmlns.</span></span>
<span data-ttu-id="8080d-162">XPath ステートメントで、各ノード名の前に、名前空間の名前とコロン ((例: Node など) を付けます。</span><span class="sxs-lookup"><span data-stu-id="8080d-162">In the XPath statement, prefix each node name with the namespace name and a colon, such as //namespaceName:Node.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8080d-163">-Path</span><span class="sxs-lookup"><span data-stu-id="8080d-163">-Path</span></span>

<span data-ttu-id="8080d-164">検索対象の XML ファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="8080d-164">Specifies the path and file names of the XML files to search.</span></span>
<span data-ttu-id="8080d-165">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8080d-165">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="8080d-166">-Xml</span><span class="sxs-lookup"><span data-stu-id="8080d-166">-Xml</span></span>

<span data-ttu-id="8080d-167">1 つ以上の XML ノードを指定します。</span><span class="sxs-lookup"><span data-stu-id="8080d-167">Specifies one or more XML nodes.</span></span>

<span data-ttu-id="8080d-168">XML ドキュメントは、XML ノードのコレクションとして処理されます。</span><span class="sxs-lookup"><span data-stu-id="8080d-168">An XML document will be processed as a collection of XML nodes.</span></span>
<span data-ttu-id="8080d-169">パイプを使用 **し** て xml ドキュメントを xml にパイプする場合、各ドキュメントノードは、パイプラインを介して取得されるたびに個別に検索されます。</span><span class="sxs-lookup"><span data-stu-id="8080d-169">If you pipe an XML document to **Select-Xml** , each document node will be searched separately as it comes through the pipeline.</span></span>

```yaml
Type: System.Xml.XmlNode[]
Parameter Sets: Xml
Aliases: Node

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8080d-170">-XPath</span><span class="sxs-lookup"><span data-stu-id="8080d-170">-XPath</span></span>

<span data-ttu-id="8080d-171">XPath 検索クエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="8080d-171">Specifies an XPath search query.</span></span>
<span data-ttu-id="8080d-172">クエリ言語では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="8080d-172">The query language is case-sensitive.</span></span>
<span data-ttu-id="8080d-173">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="8080d-173">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8080d-174">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8080d-174">CommonParameters</span></span>

<span data-ttu-id="8080d-175">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8080d-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8080d-176">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8080d-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8080d-177">入力</span><span class="sxs-lookup"><span data-stu-id="8080d-177">INPUTS</span></span>

### <span data-ttu-id="8080d-178">System.string または System.Xml.Xmlノード</span><span class="sxs-lookup"><span data-stu-id="8080d-178">System.String or System.Xml.XmlNode</span></span>

<span data-ttu-id="8080d-179">パイプを使用してパスまたは XML ノードをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="8080d-179">You can pipe a path or XML node to this cmdlet.</span></span>

## <span data-ttu-id="8080d-180">出力</span><span class="sxs-lookup"><span data-stu-id="8080d-180">OUTPUTS</span></span>

### <span data-ttu-id="8080d-181">Microsoft. PowerShell. SelectXmlInfo</span><span class="sxs-lookup"><span data-stu-id="8080d-181">Microsoft.PowerShell.Commands.SelectXmlInfo</span></span>

## <span data-ttu-id="8080d-182">注</span><span class="sxs-lookup"><span data-stu-id="8080d-182">NOTES</span></span>

* <span data-ttu-id="8080d-183">XPath は、XML ドキュメントの一部分を特定するために設計された標準言語です。</span><span class="sxs-lookup"><span data-stu-id="8080d-183">XPath is a standard language that is designed to identify parts of an XML document.</span></span> <span data-ttu-id="8080d-184">XPath 言語の詳細については、MSDN ライブラリの[イベント選択](https://msdn.microsoft.com/library/aa385231)の「 [xpath リファレンス](https://msdn.microsoft.com/library/ms256115)」と「選択フィルター」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8080d-184">For more information about the XPath language, see [XPath Reference](https://msdn.microsoft.com/library/ms256115) and the Selection Filters section of the [Event Selection](https://msdn.microsoft.com/library/aa385231) in the MSDN library.</span></span>

## <span data-ttu-id="8080d-185">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8080d-185">RELATED LINKS</span></span>

[<span data-ttu-id="8080d-186">ConvertTo-Xml</span><span class="sxs-lookup"><span data-stu-id="8080d-186">ConvertTo-Xml</span></span>](ConvertTo-Xml.md)
