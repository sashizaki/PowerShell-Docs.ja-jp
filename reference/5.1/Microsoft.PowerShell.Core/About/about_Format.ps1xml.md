---
description: '`Format.ps1xml`Powershell のファイルには、powershell コンソールでのオブジェクトの既定の表示が定義されています。 独自 `Format.ps1xml` のファイルを作成して、オブジェクトの表示を変更したり、PowerShell で作成した新しいオブジェクトの種類の既定の表示を定義したりすることができます。'
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 11/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_format.ps1xml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Format.ps1xml
ms.openlocfilehash: be88007d23ab98b9c2f707b77f9c43578ba9887b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222760"
---
# <a name="about-formatps1xml"></a><span data-ttu-id="5e2c3-105">Format.ps1xml について</span><span class="sxs-lookup"><span data-stu-id="5e2c3-105">About Format.ps1xml</span></span>

## <a name="short-description"></a><span data-ttu-id="5e2c3-106">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="5e2c3-106">Short description</span></span>

<span data-ttu-id="5e2c3-107">`Format.ps1xml`Powershell のファイルには、powershell コンソールでのオブジェクトの既定の表示が定義されています。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-107">The `Format.ps1xml` files in PowerShell define the default display of objects in the PowerShell console.</span></span> <span data-ttu-id="5e2c3-108">独自 `Format.ps1xml` のファイルを作成して、オブジェクトの表示を変更したり、PowerShell で作成した新しいオブジェクトの種類の既定の表示を定義したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-108">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="5e2c3-109">長い説明</span><span class="sxs-lookup"><span data-stu-id="5e2c3-109">Long description</span></span>

<span data-ttu-id="5e2c3-110">PowerShell のファイルには、 `Format.ps1xml` powershell でのオブジェクトの既定の表示が定義されています。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-110">The `Format.ps1xml` files in PowerShell define the default display of objects in PowerShell.</span></span> <span data-ttu-id="5e2c3-111">独自 `Format.ps1xml` のファイルを作成して、オブジェクトの表示を変更したり、PowerShell で作成した新しいオブジェクトの種類の既定の表示を定義したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-111">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

<span data-ttu-id="5e2c3-112">PowerShell がオブジェクトを表示すると、構造化された書式設定ファイルのデータを使用して、オブジェクトの既定の表示を決定します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-112">When PowerShell displays an object, it uses the data in structured formatting files to determine the default display of the object.</span></span> <span data-ttu-id="5e2c3-113">書式設定ファイルのデータは、オブジェクトがテーブルとリストのどちらで表示されるかを決定し、既定で表示されるプロパティを決定します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-113">The data in the formatting files determines whether the object is rendered in a table or in a list, and it determines which properties are displayed by default.</span></span>

<span data-ttu-id="5e2c3-114">書式設定は、表示のみに影響します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-114">The formatting affects the display only.</span></span> <span data-ttu-id="5e2c3-115">パイプラインで渡されるオブジェクトのプロパティや、パイプラインが渡される方法には影響しません。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-115">It doesn't affect which object properties are passed down the pipeline or how they're passed.</span></span> <span data-ttu-id="5e2c3-116">`Format.ps1xml` ファイルを使用して、ハッシュテーブルの出力形式をカスタマイズすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-116">`Format.ps1xml` files can't be used to customize the output format for hash tables.</span></span>

<span data-ttu-id="5e2c3-117">PowerShell には、7つのフォーマットファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-117">PowerShell includes seven formatting files.</span></span> <span data-ttu-id="5e2c3-118">これらのファイルは、インストールディレクトリ () にあり `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-118">These files are located in the installation directory (`$PSHOME`).</span></span> <span data-ttu-id="5e2c3-119">各ファイルは、Microsoft .NET Framework オブジェクトのグループの表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-119">Each file defines the display of a group of Microsoft .NET Framework objects:</span></span>

1. `Certificate.Format.ps1xml`

   <span data-ttu-id="5e2c3-120">証明書ストア内のオブジェクト (x.509 証明書や証明書ストアなど)。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-120">Objects in the Certificate store, such as X.509 certificates and certificate stores.</span></span>

1. `DotNetTypes.Format.ps1xml`

   <span data-ttu-id="5e2c3-121">CultureInfo、FileVersionInfo、EventLogEntry などの他の .NET Framework 型。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-121">Other .NET Framework types, such as CultureInfo, FileVersionInfo, and EventLogEntry objects.</span></span>

1. `FileSystem.Format.ps1xml`

   <span data-ttu-id="5e2c3-122">ファイルやディレクトリなどのファイルシステムオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-122">File system objects, such as files and directories.</span></span>

1. `Help.Format.ps1xml`

   <span data-ttu-id="5e2c3-123">詳細ビュー、完全ビュー、パラメーター、例などのヘルプビュー。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-123">Help views, such as detailed and full views, parameters, and examples.</span></span>

1. `PowerShellCore.Format.ps1xml`

   <span data-ttu-id="5e2c3-124">やなどの PowerShell コアコマンドレットによって生成されるオブジェクト `Get-Member` `Get-History` 。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-124">Objects generated by PowerShell core cmdlets, such as `Get-Member` and `Get-History`.</span></span>

1. `PowerShellTrace.Format.ps1xml`

   <span data-ttu-id="5e2c3-125">コマンドレットによって生成されるトレースオブジェクトなど `Trace-Command` 。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-125">Trace objects, such as those generated by the `Trace-Command` cmdlet.</span></span>

1. `Registry.Format.ps1xml`

   <span data-ttu-id="5e2c3-126">レジストリオブジェクト (キーやエントリなど)。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-126">Registry objects, such as keys and entries.</span></span>

<span data-ttu-id="5e2c3-127">フォーマットファイルでは、各オブジェクトの4つの異なるビューを定義できます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-127">A formatting file can define four different views of each object:</span></span>

- <span data-ttu-id="5e2c3-128">テーブル</span><span class="sxs-lookup"><span data-stu-id="5e2c3-128">Table</span></span>
- <span data-ttu-id="5e2c3-129">List</span><span class="sxs-lookup"><span data-stu-id="5e2c3-129">List</span></span>
- <span data-ttu-id="5e2c3-130">Wide</span><span class="sxs-lookup"><span data-stu-id="5e2c3-130">Wide</span></span>
- <span data-ttu-id="5e2c3-131">Custom</span><span class="sxs-lookup"><span data-stu-id="5e2c3-131">Custom</span></span>

<span data-ttu-id="5e2c3-132">たとえば、コマンドの出力を `Get-ChildItem` コマンドにパイプすると、は `Format-List` `Format-List` ファイル内のビューを使用し `FileSystem.Format.ps1xml` て、ファイルおよびフォルダーオブジェクトを一覧として表示する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-132">For example, when the output of a `Get-ChildItem` command is piped to a `Format-List` command, `Format-List` uses the view in the `FileSystem.Format.ps1xml` file to determine how to display the file and folder objects as a list.</span></span>

<span data-ttu-id="5e2c3-133">フォーマットファイルにオブジェクトの複数のビューが含まれている場合、PowerShell では、最初に見つかったビューが適用されます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-133">When a formatting file includes more than one view of an object, PowerShell applies the first view that it finds.</span></span>

<span data-ttu-id="5e2c3-134">ファイルで `Format.ps1xml` は、ビューの名前、適用先のオブジェクトの種類、列のヘッダー、およびビューの本文に表示されるプロパティを記述する XML タグのセットによって、ビューが定義されます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-134">In a `Format.ps1xml` file, a view is defined by a set of XML tags that describe the name of the view, the type of object to which it can be applied, the column headers, and the properties that are displayed in the body of the view.</span></span> <span data-ttu-id="5e2c3-135">ファイルの形式は、 `Format.ps1xml` データがユーザーに表示される直前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-135">The format in `Format.ps1xml` files is applied just before the data is presented to the user.</span></span>

## <a name="creating-new-formatps1xml-files"></a><span data-ttu-id="5e2c3-136">新しい Format.ps1xml ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="5e2c3-136">Creating new Format.ps1xml files</span></span>

<span data-ttu-id="5e2c3-137">`.ps1xml`PowerShell を使用してインストールされるファイルは、書式設定にスクリプトブロックを含めることができるため、改ざんを防ぐためにデジタル署名されています。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-137">The `.ps1xml` files that are installed with PowerShell are digitally signed to prevent tampering because the formatting can include script blocks.</span></span> <span data-ttu-id="5e2c3-138">既存のオブジェクトビューの表示形式を変更する、または新しいオブジェクトのビューを追加するには、独自の `Format.ps1xml` ファイルを作成して、PowerShell セッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-138">To change the display format of an existing object view, or to add views for new objects, create your own `Format.ps1xml` files, and then add them to your PowerShell session.</span></span>

<span data-ttu-id="5e2c3-139">新しいファイルを作成するには、既存のファイルをコピー `Format.ps1xml` します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-139">To create a new file, copy an existing `Format.ps1xml` file.</span></span> <span data-ttu-id="5e2c3-140">新しいファイルには任意の名前を付けることができますが、ファイル名拡張子を持つ必要があり `.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-140">The new file can have any name, but it must have a `.ps1xml` file name extension.</span></span> <span data-ttu-id="5e2c3-141">PowerShell にアクセスできる任意のディレクトリに新しいファイルを配置できますが、ファイルを PowerShell インストールディレクトリ ( `$PSHOME` ) またはインストールディレクトリのサブディレクトリに配置すると便利です。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-141">You can place the new file in any directory that is accessible to PowerShell, but it's useful to place the files in the PowerShell installation directory (`$PSHOME`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="5e2c3-142">現在のビューの書式を変更するには、書式設定ファイルでビューを探し、タグを使用してビューを変更します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-142">To change the formatting of a current view, locate the view in the formatting file, and then use the tags to change the view.</span></span> <span data-ttu-id="5e2c3-143">新しいオブジェクトの種類のビューを作成するには、新しいビューを作成するか、既存のビューをモデルとして使用します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-143">To create a view for a new object type, create a new view, or use an existing view as a model.</span></span> <span data-ttu-id="5e2c3-144">これらのタグについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-144">The tags are described in the next section.</span></span> <span data-ttu-id="5e2c3-145">その後、ファイル内の他のすべてのビューを削除して、ファイルを調べるすべてのユーザーに対して変更が明らかになるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-145">You can then delete all the other views in the file so that the changes are obvious to anyone examining the file.</span></span>

<span data-ttu-id="5e2c3-146">変更を保存したら、コマンドレットを使用し `Update-FormatData` て PowerShell セッションに新しいファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-146">After you save the changes, use the `Update-FormatData` cmdlet to add the new file to your PowerShell session.</span></span> <span data-ttu-id="5e2c3-147">組み込みファイルで定義されているビューよりもビューを優先する場合は、 **PrependPath** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-147">If you want your view to take precedence over a view defined in the built-in files, use the **PrependPath** parameter.</span></span>
<span data-ttu-id="5e2c3-148">`Update-FormatData` 現在のセッションのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-148">`Update-FormatData` affects only the current session.</span></span> <span data-ttu-id="5e2c3-149">今後のすべてのセッションに変更を加えるには、 `Update-FormatData` PowerShell プロファイルにコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-149">To make the change to all future sessions, add the `Update-FormatData` command to your PowerShell profile.</span></span>

### <a name="example-adding-calendar-data-to-culture-objects"></a><span data-ttu-id="5e2c3-150">例: カルチャオブジェクトへのカレンダーデータの追加</span><span class="sxs-lookup"><span data-stu-id="5e2c3-150">Example: Adding calendar data to culture objects</span></span>

<span data-ttu-id="5e2c3-151">この例では、現在の PowerShell セッションで、コマンドレットによって生成 **さ** れるカルチャオブジェクトの書式設定を変更する方法を示し `Get-Culture` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-151">This example shows how to change the formatting of the culture objects **System.Globalization.CultureInfo** generated by the `Get-Culture` cmdlet in the current PowerShell session.</span></span> <span data-ttu-id="5e2c3-152">この例のコマンドでは、カルチャオブジェクトの既定のテーブルビュー表示に **Calendar** プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-152">The commands in the example add the **Calendar** property to the default table view display of culture objects.</span></span>

<span data-ttu-id="5e2c3-153">最初の手順では、 `Format.ps1xml` カルチャオブジェクトの現在のビューが含まれているファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-153">The first step is to find the `Format.ps1xml` file that contains the current view of the culture objects.</span></span> <span data-ttu-id="5e2c3-154">次の `Select-String` コマンドは、ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-154">The following `Select-String` command finds the file:</span></span>

```powershell
$Parms = @{
  Path = "$PSHOME\*Format.ps1xml"
  Pattern = "System.Globalization.CultureInfo"
}

Select-String @Parms
```

```Output
C:\Windows\System32\WindowsPowerShell\v1.0\DotNetTypes.format.ps1xml:113:
     <Name>System.Globalization.CultureInfo</Name>
C:\Windows\System32\WindowsPowerShell\v1.0\DotNetTypes.format.ps1xml:115:
<TypeName>System.Globalization.CultureInfo</TypeName>
```

<span data-ttu-id="5e2c3-155">このコマンドは、定義がファイル内にあることを示し `DotNetTypes.Format.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-155">This command reveals that the definition is in the `DotNetTypes.Format.ps1xml` file.</span></span>

<span data-ttu-id="5e2c3-156">次のコマンドは、ファイルの内容を新しいファイルにコピーし `MyDotNetTypes.Format.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-156">The next command copies the file contents to a new file, `MyDotNetTypes.Format.ps1xml`.</span></span>

```powershell
Copy-Item $PSHome\DotNetTypes.format.ps1xml MyDotNetTypes.Format.ps1xml
```

<span data-ttu-id="5e2c3-157">`MyDotNetTypes.Format.ps1xml`Visual Studio Code など、任意の XML エディターまたはテキストエディターでファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-157">Open the `MyDotNetTypes.Format.ps1xml` file in any XML or text editor, such as Visual Studio Code.</span></span> <span data-ttu-id="5e2c3-158">「System.servicemodel **オブジェクト」** セクションを検索します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-158">Find the **System.Globalization.CultureInfo** object section.</span></span> <span data-ttu-id="5e2c3-159">次の XML は、 **CultureInfo** オブジェクトのビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-159">The following XML defines the views of the **CultureInfo** object.</span></span> <span data-ttu-id="5e2c3-160">オブジェクトには **Tablecontrol** ビューのみがあります。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-160">The object has only a **TableControl** view.</span></span>

```xml
<View>
  <Name>System.Globalization.CultureInfo</Name>
  <ViewSelectedBy>
    <TypeName>Deserialized.System.Globalization.CultureInfo</TypeName>
    <TypeName>System.Globalization.CultureInfo</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>
      <TableColumnHeader>
        <Width>16</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>16</Width>
      </TableColumnHeader>
    </TableHeaders>
    <TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
            <PropertyName>LCID</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>Name</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>DisplayName</PropertyName>
          </TableColumnItem>
        </TableColumnItems>
      </TableRowEntry>
    </TableRowEntries>
  </TableControl>
</View>
```

<span data-ttu-id="5e2c3-161">ファイルの残りの部分を削除します。ただし、開いているタグ、タグ、タグ、および終了タグとタグは除き `<?xml>` `<Configuration>` `<ViewDefinitions>` `<ViewDefinitions>` `<Configuration>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-161">Delete the remainder of the file, except for the opening `<?xml>`, `<Configuration>`, and `<ViewDefinitions>` tags and the closing `<ViewDefinitions>` and `<Configuration>` tags.</span></span> <span data-ttu-id="5e2c3-162">デジタル署名がある場合は、カスタムファイルから削除 `Format.ps1xml` します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-162">If there is a digital signature, delete it from your custom `Format.ps1xml`file.</span></span>

<span data-ttu-id="5e2c3-163">`MyDotNetTypes.Format.ps1xml`ファイルは次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-163">The `MyDotNetTypes.Format.ps1xml` file should now look like the following sample:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Configuration>
<ViewDefinitions>
<View>
  <Name>System.Globalization.CultureInfo</Name>
  <ViewSelectedBy>
    <TypeName>Deserialized.System.Globalization.CultureInfo</TypeName>
    <TypeName>System.Globalization.CultureInfo</TypeName>
  </ViewSelectedBy>
  <TableControl>
    <TableHeaders>
      <TableColumnHeader>
        <Width>16</Width>
      </TableColumnHeader>
      <TableColumnHeader>
        <Width>16</Width>
      </TableColumnHeader>
      <TableColumnHeader/>
    </TableHeaders>
    <TableRowEntries>
      <TableRowEntry>
        <TableColumnItems>
          <TableColumnItem>
            <PropertyName>LCID</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>Name</PropertyName>
          </TableColumnItem>
          <TableColumnItem>
            <PropertyName>DisplayName</PropertyName>
          </TableColumnItem>
        </TableColumnItems>
      </TableRowEntry>
    </TableRowEntries>
  </TableControl>
</View>
</ViewDefinitions>
</Configuration>
```

<span data-ttu-id="5e2c3-164">新しいタグのセットを追加して、 **Calendar** プロパティの新しい列を作成し `<TableColumnHeader>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-164">Create a new column for the **Calendar** property by adding a new set of `<TableColumnHeader>` tags.</span></span> <span data-ttu-id="5e2c3-165">**Calendar** プロパティの値は long であるため、45文字の値をとして指定し `<Width>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-165">The value of the **Calendar** property can be long, so specify a value of 45 characters as the `<Width>`.</span></span>

```xml
<TableHeaders>
  <TableColumnHeader>
    <Width>16</Width>
  </TableColumnHeader>
  <TableColumnHeader>
    <Width>16</Width>
  </TableColumnHeader>
  <TableColumnHeader>
    <Width>45</Width>
  </TableColumnHeader>
  <TableColumnHeader/>
</TableHeaders>
```

<span data-ttu-id="5e2c3-166">タグとタグを使用して、テーブルの行に **Calendar** の新しい列項目を追加し `<TableColumnItem>` `<PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-166">Add a new column item for **Calendar** in the table rows using the `<TableColumnItem>` and `<PropertyName` tags:</span></span>

```xml
<TableRowEntries>
  <TableRowEntry>
    <TableColumnItems>
      <TableColumnItem>
        <PropertyName>LCID</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>Name</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>Calendar</PropertyName>
      </TableColumnItem>
      <TableColumnItem>
        <PropertyName>DisplayName</PropertyName>
      </TableColumnItem>
    </TableColumnItems>
  </TableRowEntry>
</TableRowEntries>
```

<span data-ttu-id="5e2c3-167">ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-167">Save and close the file.</span></span> <span data-ttu-id="5e2c3-168">`Update-FormatData`新しいフォーマットファイルを現在の PowerShell セッションに追加するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-168">Use `Update-FormatData` to add the new format file to the current PowerShell session.</span></span>

<span data-ttu-id="5e2c3-169">この例では、 **PrependPath** パラメーターを使用して、新しいファイルを元のファイルよりも優先順位の高い順に配置します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-169">This example uses the **PrependPath** parameter to place the new file in a higher precedence order than the original file.</span></span> <span data-ttu-id="5e2c3-170">詳細については、「 [更新-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-170">For more information, see [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData).</span></span>

```powershell
Update-FormatData -PrependPath $PSHOME\MyDotNetTypes.Format.ps1xml
```

<span data-ttu-id="5e2c3-171">変更をテストするには、 `Get-Culture` **Calendar** プロパティを含む出力を入力して確認します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-171">To test the change, type `Get-Culture` and review the output that includes the **Calendar** property.</span></span>

```powershell
Get-Culture
```

```Output
LCID Name  Calendar                               DisplayName
---- ----  --------                               -----------
1033 en-US System.Globalization.GregorianCalendar English (United States)
```

## <a name="the-xml-in-formatps1xml-files"></a><span data-ttu-id="5e2c3-172">Format.ps1xml ファイル内の XML</span><span class="sxs-lookup"><span data-stu-id="5e2c3-172">The XML in Format.ps1xml files</span></span>

<span data-ttu-id="5e2c3-173">完全なスキーマ定義は、GitHub の PowerShell ソースコードリポジトリの [.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) にあります。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-173">The full schema definition can be found in [Format.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) in the PowerShell source code repository on GitHub.</span></span>

<span data-ttu-id="5e2c3-174">各ファイルの **Viewdefinitions** セクションには `Format.ps1xml` 、 `<View>` 各ビューを定義するタグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-174">The **ViewDefinitions** section of each `Format.ps1xml` file contains the `<View>` tags that define each view.</span></span> <span data-ttu-id="5e2c3-175">一般的な `<View>` タグには、次のタグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-175">A typical `<View>` tag includes the following tags:</span></span>

- <span data-ttu-id="5e2c3-176">`<Name>` ビューの名前を識別します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-176">`<Name>` identifies the name of the view.</span></span>
- <span data-ttu-id="5e2c3-177">`<ViewSelectedBy>` ビューが適用されるオブジェクトの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-177">`<ViewSelectedBy>` specifies the object type or types to which the view applies.</span></span>
- <span data-ttu-id="5e2c3-178">`<GroupBy>` ビュー内の項目をグループにまとめる方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-178">`<GroupBy>` specifies how items in the view will be combined in groups.</span></span>
- <span data-ttu-id="5e2c3-179">`<TableControl>`、、、およびには、 `<ListControl>` `<WideControl>` `<CustomControl>` 各項目の表示方法を指定するタグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-179">`<TableControl>`, `<ListControl>`, `<WideControl>`, and `<CustomControl>` contain the tags that specify how each item will be displayed.</span></span>

### <a name="viewselectedby-tag"></a><span data-ttu-id="5e2c3-180">タグで viewselected</span><span class="sxs-lookup"><span data-stu-id="5e2c3-180">ViewSelectedBy tag</span></span>

<span data-ttu-id="5e2c3-181">タグには `<ViewSelectedBy>` `<TypeName>` 、ビューが適用されるオブジェクトの種類ごとにタグを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-181">The `<ViewSelectedBy>` tag can contain a `<TypeName>` tag for each object type to which the view applies.</span></span> <span data-ttu-id="5e2c3-182">または、タグを使用して、他の場所で定義されている `<SelectionSetName>` 選択セットを参照するタグを含めることもでき `<SelectionSet>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-182">Or, it can contain a `<SelectionSetName>` tag that references a selection set that is defined elsewhere by using a `<SelectionSet>` tag.</span></span>

### <a name="groupby-tag"></a><span data-ttu-id="5e2c3-183">GroupBy タグ</span><span class="sxs-lookup"><span data-stu-id="5e2c3-183">GroupBy tag</span></span>

<span data-ttu-id="5e2c3-184">タグには、アイテムをグループ化するために使用する `<GroupBy>` オブジェクトプロパティを指定するタグが含まれてい `<PropertyName>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-184">The `<GroupBy>` tag contains a `<PropertyName>` tag that specifies the object property by which items are to be grouped.</span></span> <span data-ttu-id="5e2c3-185">また、 `<Label>` 各グループのラベルとして使用する文字列を指定するタグ、またはタグを `<CustomControlName>` 使用して他の場所で定義されたカスタムコントロールを参照するタグのいずれかも含まれ `<Control>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-185">It also contains either a `<Label>` tag that specifies a string to be used as a label for each group or a `<CustomControlName>` tag that references a custom control defined elsewhere using a `<Control>` tag.</span></span> <span data-ttu-id="5e2c3-186">タグにはタグ `<Control>` とタグが含まれてい `<Name>` `<CustomControl>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-186">The `<Control>` tag contains a `<Name>` tag and a `<CustomControl>` tag.</span></span>

### <a name="tablecontroltag"></a><span data-ttu-id="5e2c3-187">TableControlTag</span><span class="sxs-lookup"><span data-stu-id="5e2c3-187">TableControlTag</span></span>

<span data-ttu-id="5e2c3-188">`<TableControl>`タグには、通常、 `<TableHeaders>` `<TableRowEntries>` テーブルのヘッドと行の書式を定義するタグとタグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-188">The `<TableControl>` tag typically contains `<TableHeaders>` and `<TableRowEntries>` tags that define the formatting for the table's heads and rows.</span></span> <span data-ttu-id="5e2c3-189">`<TableHeaders>`タグには `<TableColumnHeader>` 、通常 `<Label>` 、、、タグを含むタグが含まれてい `<Width>` `<Alignment>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-189">The `<TableHeaders>` tag typically contains `<TableColumnHeader>` tags that contain `<Label>`, `<Width>`, and `<Alignment>` tags.</span></span> <span data-ttu-id="5e2c3-190">`<TableRowEntries>`タグには `<TableRowEntry>` 、テーブルの各行のタグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-190">The `<TableRowEntries>` tag contains `<TableRowEntry>` tags for each row in the table.</span></span> <span data-ttu-id="5e2c3-191">タグには、 `<TableRowEntry>` `<TableColumnItems>` 行の `<TableColumnItem>` 各列のタグを含むタグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-191">The `<TableRowEntry>` tag contains a `<TableColumnItems>` tag that contains a `<TableColumnItem>` tag for each column in the row.</span></span> <span data-ttu-id="5e2c3-192">通常、タグには、定義された `<TableColumnItem>` `<PropertyName>` 場所に表示されるオブジェクトプロパティを識別するタグ、または `<ScriptBlock>` 場所に表示される結果を計算するスクリプトコードを含むタグのいずれかが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-192">Typically, the `<TableColumnItem>` tag contains either a `<PropertyName>` tag that identifies the object property to be displayed in the defined location, or a `<ScriptBlock>` tag that contains script code that calculates a result that is to be displayed in the location.</span></span>

> [!NOTE]
> <span data-ttu-id="5e2c3-193">スクリプトブロックは、計算された結果が役に立つ場所の他の場所でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-193">Script blocks can also be used elsewhere in locations where calculated results can be useful.</span></span>

<span data-ttu-id="5e2c3-194">タグには、 `<TableColumnItem>` `<FormatString>` プロパティまたは計算された結果の表示方法を指定するタグを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-194">The `<TableColumnItem>` tag can also contain a `<FormatString>` tag that specifies how the property or the calculated results will be displayed.</span></span>

### <a name="listcontrol-tag"></a><span data-ttu-id="5e2c3-195">ListControl タグ</span><span class="sxs-lookup"><span data-stu-id="5e2c3-195">ListControl tag</span></span>

<span data-ttu-id="5e2c3-196">`<ListControl>`タグには、通常、タグが含まれてい `<ListEntries>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-196">The `<ListControl>` tag typically contains a `<ListEntries>` tag.</span></span> <span data-ttu-id="5e2c3-197">タグには `<ListEntries>` タグが含まれてい `<ListEntry>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-197">The `<ListEntries>` tag contains a `<ListEntry>` tag.</span></span> <span data-ttu-id="5e2c3-198">タグには `<ListEntry>` タグが含まれてい `<ListItems>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-198">The `<ListEntry>` tag contains a `<ListItems>` tag.</span></span> <span data-ttu-id="5e2c3-199">タグにはタグが含ま `<ListItems>` れてい `<ListItem>` `<PropertyName>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-199">The `<ListItems>` tag contains `<ListItem>` tags, which contain `<PropertyName>` tags.</span></span> <span data-ttu-id="5e2c3-200">タグは、 `<PropertyName>` 一覧の指定した位置に表示されるオブジェクトプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-200">The `<PropertyName>` tags specify the object property to be displayed at the specified location in the list.</span></span> <span data-ttu-id="5e2c3-201">選択セットを使用してビューの選択が定義されている場合は、タグ `<ListControl>` と `<ListEntry>` タグに1つ以上のタグを含むタグを含めることもでき `<EntrySelectedBy>` `<TypeName>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-201">If the view selection is defined using a selection set, the `<ListControl>` and `<ListEntry>` tags can also contain an `<EntrySelectedBy>` tag that contains one or more `<TypeName>` tags.</span></span> <span data-ttu-id="5e2c3-202">これらの `<TypeName>` タグは、タグの表示対象となるオブジェクトの種類を指定し `<ListControl>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-202">These `<TypeName>` tags specify the object type that the `<ListControl>` tag is intended to display.</span></span>

### <a name="widecontrol-tag"></a><span data-ttu-id="5e2c3-203">WideControl タグ</span><span class="sxs-lookup"><span data-stu-id="5e2c3-203">WideControl tag</span></span>

<span data-ttu-id="5e2c3-204">`<WideControl>`タグには、通常、タグが含まれてい `<WideEntries>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-204">The `<WideControl>` tag typically contains a `<WideEntries>` tag.</span></span> <span data-ttu-id="5e2c3-205">`<WideEntries>`タグに1つ以上のタグが含まれてい `<WideEntry>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-205">The `<WideEntries>` tag contains one or more `<WideEntry>` tags.</span></span> <span data-ttu-id="5e2c3-206">通常、タグには、 `<WideEntry>` `<PropertyName>` ビュー内の指定した位置に表示されるプロパティを指定するタグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-206">A `<WideEntry>` tag typically contains a `<PropertyName>` tag that specifies the property to be displayed at the specified location in the view.</span></span> <span data-ttu-id="5e2c3-207">タグには、 `<PropertyName>` `<FormatString>` プロパティを表示する方法を指定するタグを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-207">The `<PropertyName>` tag can contain a `<FormatString>` tag that specifies how the property is to be displayed.</span></span>

### <a name="customcontrol-tag"></a><span data-ttu-id="5e2c3-208">CustomControl タグ</span><span class="sxs-lookup"><span data-stu-id="5e2c3-208">CustomControl tag</span></span>

<span data-ttu-id="5e2c3-209">`<CustomControl>`タグを使用すると、スクリプトブロックを使用して形式を定義できます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-209">The `<CustomControl>` tag lets you use a script block to define a format.</span></span> <span data-ttu-id="5e2c3-210">`<CustomControl>`タグには、通常、複数のタグを含むタグが含まれてい `<CustomEntries>` `<CustomEntry>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-210">A `<CustomControl>` tag typically contains a `<CustomEntries>` tag that contains multiple `<CustomEntry>` tags.</span></span> <span data-ttu-id="5e2c3-211">各 `<CustomEntry>` タグには `<CustomItem>` 、、、、タグなど、ビュー内の指定された場所の内容と書式を指定するさまざまなタグを含めることができるタグが含まれてい `<Text>` `<Indentation>` `<ExpressionBinding>` `<NewLine>` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-211">Each `<CustomEntry>` tag contains a `<CustomItem>` tag that can contain a variety of tags that specify contents and formatting of the specified location in the view, including `<Text>`, `<Indentation>`, `<ExpressionBinding>`, and `<NewLine>` tags.</span></span>

## <a name="default-displays-in-typesps1xml"></a><span data-ttu-id="5e2c3-212">Types.ps1xml での既定の表示</span><span class="sxs-lookup"><span data-stu-id="5e2c3-212">Default displays in Types.ps1xml</span></span>

<span data-ttu-id="5e2c3-213">いくつかの基本的なオブジェクトの種類の既定の表示は、ディレクトリ内のファイルで定義されてい `Types.ps1xml` `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-213">The default displays of some basic object types are defined in the `Types.ps1xml` file in the `$PSHOME` directory.</span></span> <span data-ttu-id="5e2c3-214">ノードには **Psstandardmembers** という名前が付けられ、サブノードは次のいずれかのタグを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-214">The nodes are named **PsStandardMembers** , and the subnodes use one of the following tags:</span></span>

- `<DefaultDisplayProperty>`
- `<DefaultDisplayPropertySet>`
- `<DefaultKeyPropertySet>`

<span data-ttu-id="5e2c3-215">詳細については、「 [about_Types.ps1xml](about_Types.ps1xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-215">For more information, see [about_Types.ps1xml](about_Types.ps1xml.md).</span></span>

## <a name="tracing-formatps1xml-file-use"></a><span data-ttu-id="5e2c3-216">Xml ファイルの使用 Format.ps1のトレース</span><span class="sxs-lookup"><span data-stu-id="5e2c3-216">Tracing Format.ps1xml file use</span></span>

<span data-ttu-id="5e2c3-217">ファイルの読み込みまたはアプリケーションで発生したエラーを検出するには、 `Format.ps1xml` `Trace-Command` **Name** パラメーターの値として、次のいずれかの形式コンポーネントを指定したコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-217">To detect errors in the loading or application of `Format.ps1xml` files, use the `Trace-Command` cmdlet with any of the following format components as the value of the **Name** parameter:</span></span>

- <span data-ttu-id="5e2c3-218">FormatFileLoading</span><span class="sxs-lookup"><span data-stu-id="5e2c3-218">FormatFileLoading</span></span>
- <span data-ttu-id="5e2c3-219">FormatViewBinding</span><span class="sxs-lookup"><span data-stu-id="5e2c3-219">FormatViewBinding</span></span>

<span data-ttu-id="5e2c3-220">詳細については、「 [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) と [Get tracesource](xref:Microsoft.PowerShell.Utility.Get-TraceSource)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-220">For more information, see [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) and [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).</span></span>

## <a name="signing-a-formatps1xml-file"></a><span data-ttu-id="5e2c3-221">Format.ps1xml ファイルへの署名</span><span class="sxs-lookup"><span data-stu-id="5e2c3-221">Signing a Format.ps1xml file</span></span>

<span data-ttu-id="5e2c3-222">ファイルのユーザーを保護するには `Format.ps1xml` 、デジタル署名を使用してファイルに署名します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-222">To protect the users of your `Format.ps1xml` file, sign the file using a digital signature.</span></span> <span data-ttu-id="5e2c3-223">詳細については、「 [about_Signing](about_Signing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-223">For more information, see [about_Signing](about_Signing.md).</span></span>

## <a name="sample-xml-for-a-format-table-custom-view"></a><span data-ttu-id="5e2c3-224">Format-Table カスタムビューのサンプル XML</span><span class="sxs-lookup"><span data-stu-id="5e2c3-224">Sample XML for a Format-Table custom view</span></span>

<span data-ttu-id="5e2c3-225">次の例では、 `Format-Table` によって作成される **DirectoryInfo** および system.object オブジェクトのカスタムビュー **を作成** し `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-225">The following sample creates a `Format-Table` custom view for the **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects created by `Get-ChildItem`.</span></span> <span data-ttu-id="5e2c3-226">カスタムビューには **mygciview** という名前が付けられ、テーブルに "作成 **後の時間** " 列が追加されます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-226">The custom view is named **mygciview** and adds the **CreationTime** column to the table.</span></span>

<span data-ttu-id="5e2c3-227">カスタムビューは、 `FileSystem.Format.ps1xml` PowerShell 5.1 のに格納されているファイルの編集されたバージョンから作成され `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-227">The custom view is created from an edited version of the `FileSystem.Format.ps1xml` file that's stored in `$PSHOME` on PowerShell 5.1.</span></span>

<span data-ttu-id="5e2c3-228">カスタムファイルが保存されたら、を使用して、 `.ps1xml` `Update-FormatData` PowerShell セッションにビューを含めます。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-228">After your custom `.ps1xml` file is saved, use `Update-FormatData` to include the view in a PowerShell session.</span></span> <span data-ttu-id="5e2c3-229">この例では、カスタムビューでテーブル形式を使用する必要があります。そうしないと、は `Format-Table` 失敗します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-229">For this example, the custom view must use the table format, otherwise, `Format-Table` fails.</span></span>

<span data-ttu-id="5e2c3-230">`Format-Table`カスタムビューの名前を指定し、テーブルの出力を書式設定するには、 **view** パラメーターと共にを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-230">Use `Format-Table` with the **View** parameter to specify the custom view's name and format the table's output.</span></span> <span data-ttu-id="5e2c3-231">コマンドの実行方法の例については、「 [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-231">For an example of how the command is run, see [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

```powershell
$Parms = @{
  Path = "$PSHOME\*Format.ps1xml"
  Pattern = "System.IO.DirectoryInfo"
}
Select-String @Parms
Copy-Item $PSHome\FileSystem.format.ps1xml .\MyFileSystem.Format.ps1xml
Update-FormatData -PrependPath $PSHOME\Format\MyFileSystem.Format.ps1xml
```

> [!NOTE]
> <span data-ttu-id="5e2c3-232">行幅の制限内に XML サンプルを収めるには、いくつかのインデントを圧縮し、コード内で改行を使用する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="5e2c3-232">To fit the XML sample within line width limitations, it was necessary to compress some indentation and use line breaks within the code.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Configuration>
    <SelectionSets>
        <SelectionSet>
            <Name>FileSystemTypes</Name>
            <Types>
                <TypeName>System.IO.DirectoryInfo</TypeName>
                <TypeName>System.IO.FileInfo</TypeName>
            </Types>
        </SelectionSet>
    </SelectionSets>
<Controls>
<Control>
<Name>FileSystemTypes-GroupingFormat</Name>
<CustomControl>
 <CustomEntries>
  <CustomEntry>
    <CustomItem>
    <Frame>
    <LeftIndent>4</LeftIndent>
    <CustomItem>
    <Text AssemblyName="System.Management.Automation"
    BaseName="FileSystemProviderStrings"
    ResourceId="DirectoryDisplayGrouping"/>
    <ExpressionBinding>
     <ScriptBlock>
      $_.PSParentPath.Replace("Microsoft.PowerShell.Core\FileSystem::", "")
     </ScriptBlock>
    </ExpressionBinding>
    <NewLine/>
    </CustomItem>
    </Frame>
    </CustomItem>
    </CustomEntry>
 </CustomEntries>
</CustomControl>
</Control>
</Controls>
<ViewDefinitions>
    <View>
    <Name>mygciview</Name>
    <ViewSelectedBy>
        <SelectionSetName>FileSystemTypes</SelectionSetName>
    </ViewSelectedBy>
    <GroupBy>
      <PropertyName>PSParentPath</PropertyName>
      <CustomControlName>FileSystemTypes-GroupingFormat</CustomControlName>
    </GroupBy>
        <TableControl>
            <TableHeaders>
                <TableColumnHeader>
                    <Label>Mode</Label>
                    <Width>7</Width>
                    <Alignment>left</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>LastWriteTime</Label>
                    <Width>25</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>CreationTime</Label>
                    <Width>25</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader>
                    <Label>Length</Label>
                    <Width>14</Width>
                    <Alignment>right</Alignment>
                </TableColumnHeader>
                <TableColumnHeader/>
            </TableHeaders>
            <TableRowEntries>
                <TableRowEntry>
                    <Wrap/>
                    <TableColumnItems>
                        <TableColumnItem>
                            <PropertyName>Mode</PropertyName>
                        </TableColumnItem>
                        <TableColumnItem>
                            <ScriptBlock>
                                [String]::Format("{0,10}  {1,8}",
                                    $_.LastWriteTime.ToString("d"),
                                    $_.LastWriteTime.ToString("t"))
                            </ScriptBlock>
                        </TableColumnItem>
                        <TableColumnItem>
                            <ScriptBlock>
                                [String]::Format("{0,10}  {1,8}",
                                    $_.CreationTime.ToString("d"),
                                    $_.LastWriteTime.ToString("t"))
                            </ScriptBlock>
                        </TableColumnItem>
                        <TableColumnItem>
                        <PropertyName>Length</PropertyName>
                        </TableColumnItem>
                        <TableColumnItem>
                            <PropertyName>Name</PropertyName>
                        </TableColumnItem>
                    </TableColumnItems>
                </TableRowEntry>
            </TableRowEntries>
        </TableControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a><span data-ttu-id="5e2c3-233">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e2c3-233">See also</span></span>

[<span data-ttu-id="5e2c3-234">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="5e2c3-234">Export-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Export-FormatData)

[<span data-ttu-id="5e2c3-235">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="5e2c3-235">Get-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Get-FormatData)

[<span data-ttu-id="5e2c3-236">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="5e2c3-236">Get-TraceSource</span></span>](xref:Microsoft.PowerShell.Utility.Get-TraceSource)

[<span data-ttu-id="5e2c3-237">書式設定スキーマ XML リファレンス</span><span class="sxs-lookup"><span data-stu-id="5e2c3-237">Format Schema XML Reference</span></span>](/powershell/scripting/developer/format/format-schema-xml-reference)

[<span data-ttu-id="5e2c3-238">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="5e2c3-238">Trace-Command</span></span>](xref:Microsoft.PowerShell.Utility.Trace-Command)

[<span data-ttu-id="5e2c3-239">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="5e2c3-239">Update-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Update-FormatData)

[<span data-ttu-id="5e2c3-240">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="5e2c3-240">Writing a PowerShell Formatting File</span></span>](/powershell/scripting/developer/format/writing-a-powershell-formatting-file)
