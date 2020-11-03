---
description: PowerShell 6 以降では、オブジェクトの既定のビューが PowerShell ソースコードで定義されています。  独自 `Format.ps1xml` のファイルを作成して、オブジェクトの表示を変更したり、PowerShell で作成した新しいオブジェクトの種類の既定の表示を定義したりすることができます。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 11/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_format.ps1xml?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Format.ps1xml
ms.openlocfilehash: c638001c8442284224c0cb554513ef988ba59f3d
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223603"
---
# <a name="about-formatps1xml"></a><span data-ttu-id="09232-105">Format.ps1xml について</span><span class="sxs-lookup"><span data-stu-id="09232-105">About Format.ps1xml</span></span>

## <a name="short-description"></a><span data-ttu-id="09232-106">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="09232-106">Short description</span></span>

<span data-ttu-id="09232-107">PowerShell 6 以降では、オブジェクトの既定のビューが PowerShell ソースコードで定義されています。</span><span class="sxs-lookup"><span data-stu-id="09232-107">Beginning in PowerShell 6, the default views for objects are defined in PowerShell source code.</span></span>

<span data-ttu-id="09232-108">独自 `Format.ps1xml` のファイルを作成して、オブジェクトの表示を変更したり、PowerShell で作成した新しいオブジェクトの種類の既定の表示を定義したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="09232-108">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="09232-109">長い説明</span><span class="sxs-lookup"><span data-stu-id="09232-109">Long description</span></span>

<span data-ttu-id="09232-110">PowerShell 6 以降では、既定のビューが PowerShell ソースコードで定義されています。</span><span class="sxs-lookup"><span data-stu-id="09232-110">Beginning in PowerShell 6, the default views are defined in PowerShell source code.</span></span> <span data-ttu-id="09232-111">Powershell `Format.ps1xml` 5.1 以前のバージョンのファイルは、powershell 6 以降のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="09232-111">The `Format.ps1xml` files from PowerShell 5.1 and earlier versions don't exist in PowerShell 6 and later versions.</span></span>

<span data-ttu-id="09232-112">Powershell ソースコードは、PowerShell コンソールでのオブジェクトの既定の表示を定義します。</span><span class="sxs-lookup"><span data-stu-id="09232-112">The PowerShell source code defines the default display of objects in the PowerShell console.</span></span> <span data-ttu-id="09232-113">独自 `Format.ps1xml` のファイルを作成して、オブジェクトの表示を変更したり、PowerShell で作成した新しいオブジェクトの種類の既定の表示を定義したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="09232-113">You can create your own `Format.ps1xml` files to change the display of objects or to define default displays for new object types that you create in PowerShell.</span></span>

<span data-ttu-id="09232-114">PowerShell がオブジェクトを表示すると、構造化された書式設定ファイルのデータを使用して、オブジェクトの既定の表示を決定します。</span><span class="sxs-lookup"><span data-stu-id="09232-114">When PowerShell displays an object, it uses the data in structured formatting files to determine the default display of the object.</span></span> <span data-ttu-id="09232-115">書式設定ファイルのデータは、オブジェクトがテーブルとリストのどちらで表示されるかを決定し、既定で表示されるプロパティを決定します。</span><span class="sxs-lookup"><span data-stu-id="09232-115">The data in the formatting files determines whether the object is rendered in a table or in a list, and it determines which properties are displayed by default.</span></span>

<span data-ttu-id="09232-116">書式設定は、表示のみに影響します。</span><span class="sxs-lookup"><span data-stu-id="09232-116">The formatting affects the display only.</span></span> <span data-ttu-id="09232-117">パイプラインで渡されるオブジェクトのプロパティや、パイプラインが渡される方法には影響しません。</span><span class="sxs-lookup"><span data-stu-id="09232-117">It doesn't affect which object properties are passed down the pipeline or how they're passed.</span></span> <span data-ttu-id="09232-118">`Format.ps1xml` ファイルを使用して、ハッシュテーブルの出力形式をカスタマイズすることはできません。</span><span class="sxs-lookup"><span data-stu-id="09232-118">`Format.ps1xml` files can't be used to customize the output format for hash tables.</span></span>

<span data-ttu-id="09232-119">フォーマットファイルでは、 `.ps1xml` 各オブジェクトの4つの異なるビューを定義できます。</span><span class="sxs-lookup"><span data-stu-id="09232-119">A `.ps1xml` formatting file can define four different views of each object:</span></span>

- <span data-ttu-id="09232-120">テーブル</span><span class="sxs-lookup"><span data-stu-id="09232-120">Table</span></span>
- <span data-ttu-id="09232-121">List</span><span class="sxs-lookup"><span data-stu-id="09232-121">List</span></span>
- <span data-ttu-id="09232-122">Wide</span><span class="sxs-lookup"><span data-stu-id="09232-122">Wide</span></span>
- <span data-ttu-id="09232-123">Custom</span><span class="sxs-lookup"><span data-stu-id="09232-123">Custom</span></span>

<span data-ttu-id="09232-124">たとえば、コマンドの出力を `Get-ChildItem` コマンドにパイプすると `Format-List` 、は `Format-List` ソースコードで定義されているリストビューを使用して、ファイルおよびフォルダーオブジェクトを一覧として表示する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="09232-124">For example, when the output of a `Get-ChildItem` command is piped to a `Format-List` command, `Format-List` uses the list view defined in the source code to determine how to display the file and folder objects as a list.</span></span>

<span data-ttu-id="09232-125">フォーマットファイルにオブジェクトの複数のビューが含まれている場合、PowerShell では、最初に見つかったビューが適用されます。</span><span class="sxs-lookup"><span data-stu-id="09232-125">When a formatting file includes more than one view of an object, PowerShell applies the first view that it finds.</span></span>

<span data-ttu-id="09232-126">カスタムファイルで `Format.ps1xml` は、ビューの名前、適用先のオブジェクトの種類、列ヘッダー、およびビューの本文に表示されるプロパティを記述する XML タグのセットによって、ビューが定義されます。</span><span class="sxs-lookup"><span data-stu-id="09232-126">In a custom `Format.ps1xml` file, a view is defined by a set of XML tags that describe the name of the view, the type of object to which it can be applied, the column headers, and the properties that are displayed in the body of the view.</span></span> <span data-ttu-id="09232-127">ファイルの形式は、 `Format.ps1xml` データがユーザーに表示される直前に適用されます。</span><span class="sxs-lookup"><span data-stu-id="09232-127">The format in `Format.ps1xml` files is applied just before the data is presented to the user.</span></span>

## <a name="creating-new-formatps1xml-files"></a><span data-ttu-id="09232-128">新しい Format.ps1xml ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="09232-128">Creating new Format.ps1xml files</span></span>

<span data-ttu-id="09232-129">既存のオブジェクトビューの表示形式を変更する、または新しいオブジェクトのビューを追加するには、独自の `Format.ps1xml` ファイルを作成して、PowerShell セッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="09232-129">To change the display format of an existing object view, or to add views for new objects, create your own `Format.ps1xml` files, and then add them to your PowerShell session.</span></span>

<span data-ttu-id="09232-130">カスタムビューを定義するファイルを作成するには、 `Format.ps1xml` [Get formatdata](xref:Microsoft.PowerShell.Utility.Get-FormatData) コマンドレットと [Export-formatdata](xref:Microsoft.PowerShell.Utility.Export-FormatData) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="09232-130">To create a `Format.ps1xml` file to define a custom view, use the [Get-FormatData](xref:Microsoft.PowerShell.Utility.Get-FormatData) and [Export-FormatData](xref:Microsoft.PowerShell.Utility.Export-FormatData) cmdlets.</span></span> <span data-ttu-id="09232-131">ファイルを編集するには、テキストエディターを使用します。</span><span class="sxs-lookup"><span data-stu-id="09232-131">Use a text editor to edit the file.</span></span> <span data-ttu-id="09232-132">ファイルは、PowerShell がアクセスできる任意のディレクトリ (のサブディレクトリなど) に保存でき `$HOME` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-132">The file can be saved to any directory that PowerShell can access, such as a subdirectory of `$HOME`.</span></span>

<span data-ttu-id="09232-133">現在のビューの書式を変更するには、書式設定ファイルでビューを探し、タグを使用してビューを変更します。</span><span class="sxs-lookup"><span data-stu-id="09232-133">To change the formatting of a current view, locate the view in the formatting file, and then use the tags to change the view.</span></span> <span data-ttu-id="09232-134">新しいオブジェクトの種類のビューを作成するには、新しいビューを作成するか、既存のビューをモデルとして使用します。</span><span class="sxs-lookup"><span data-stu-id="09232-134">To create a view for a new object type, create a new view, or use an existing view as a model.</span></span> <span data-ttu-id="09232-135">これらのタグについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="09232-135">The tags are described in the next section.</span></span> <span data-ttu-id="09232-136">その後、ファイル内の他のすべてのビューを削除して、ファイルを調べるすべてのユーザーに対して変更が明らかになるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="09232-136">You can then delete all the other views in the file so that the changes are obvious to anyone examining the file.</span></span>

<span data-ttu-id="09232-137">変更を保存したら、 [更新プログラムの FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData) を使用して、PowerShell セッションに新しいファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="09232-137">After you save the changes, use the [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData) to add the new file to your PowerShell session.</span></span> <span data-ttu-id="09232-138">組み込みファイルで定義されているビューよりもビューを優先する場合は、 **PrependPath** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="09232-138">If you want your view to take precedence over a view defined in the built-in files, use the **PrependPath** parameter.</span></span> <span data-ttu-id="09232-139">`Update-FormatData` 現在のセッションのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="09232-139">`Update-FormatData` affects only the current session.</span></span> <span data-ttu-id="09232-140">今後のすべてのセッションに変更を加えるには、 `Update-FormatData` PowerShell プロファイルにコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="09232-140">To make the change to all future sessions, add the `Update-FormatData` command to your PowerShell profile.</span></span>

### <a name="example-add-calendar-data-to-culture-objects"></a><span data-ttu-id="09232-141">例: カルチャオブジェクトへのカレンダーデータの追加</span><span class="sxs-lookup"><span data-stu-id="09232-141">Example: Add calendar data to culture objects</span></span>

<span data-ttu-id="09232-142">この例では、現在の PowerShell セッションで、コマンドレットによって生成 **さ** れるカルチャオブジェクトの書式設定を変更する方法を示し `Get-Culture` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-142">This example shows how to change the formatting of the culture objects **System.Globalization.CultureInfo** generated by the `Get-Culture` cmdlet in the current PowerShell session.</span></span> <span data-ttu-id="09232-143">この例のコマンドでは、カルチャオブジェクトの既定のテーブルビュー表示に **Calendar** プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="09232-143">The commands in the example add the **Calendar** property to the default table view display of culture objects.</span></span>

<span data-ttu-id="09232-144">まず、ソースコードファイルから書式データを取得し、 `Format.ps1xml` カルチャオブジェクトの現在のビューを含むファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="09232-144">To begin, get the format data from the source code file and create a `Format.ps1xml` file that contains the current view of the culture objects.</span></span>

```powershell
Get-FormatData -TypeName System.Globalization.CultureInfo |
  Export-FormatData -Path $HOME\Format\CultureInfo.Format.ps1xml
```

<span data-ttu-id="09232-145">`CultureInfo.Format.ps1xml`Visual Studio Code など、任意の XML エディターまたはテキストエディターでファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="09232-145">Open the `CultureInfo.Format.ps1xml` file in any XML or text editor, such as Visual Studio Code.</span></span> <span data-ttu-id="09232-146">次の XML は、 **CultureInfo** オブジェクトのビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="09232-146">The following XML defines the views of the **CultureInfo** object.</span></span>

<span data-ttu-id="09232-147">`CultureInfo.Format.ps1xml`ファイルは次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="09232-147">The `CultureInfo.Format.ps1xml` file should look like the following sample:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>System.Globalization.CultureInfo</Name>
      <ViewSelectedBy>
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
          <TableColumnHeader />
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

<span data-ttu-id="09232-148">新しいタグのセットを追加して、 **Calendar** プロパティの新しい列を作成し `<TableColumnHeader>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-148">Create a new column for the **Calendar** property by adding a new set of `<TableColumnHeader>` tags.</span></span> <span data-ttu-id="09232-149">**Calendar** プロパティの値は long であるため、45文字の値をとして指定し `<Width>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-149">The value of the **Calendar** property can be long, so specify a value of 45 characters as the `<Width>`.</span></span>

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

<span data-ttu-id="09232-150">タグとタグを使用して、テーブルの行に **Calendar** の新しい列項目を追加し `<TableColumnItem>` `<PropertyName` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-150">Add a new column item for **Calendar** in the table rows using the `<TableColumnItem>` and `<PropertyName` tags:</span></span>

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

<span data-ttu-id="09232-151">ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="09232-151">Save and close the file.</span></span> <span data-ttu-id="09232-152">`Update-FormatData`新しいフォーマットファイルを現在の PowerShell セッションに追加するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="09232-152">Use `Update-FormatData` to add the new format file to the current PowerShell session.</span></span>

<span data-ttu-id="09232-153">この例では、 **PrependPath** パラメーターを使用して、新しいファイルを元のファイルよりも優先順位の高い順に配置します。</span><span class="sxs-lookup"><span data-stu-id="09232-153">This example uses the **PrependPath** parameter to place the new file in a higher precedence order than the original file.</span></span> <span data-ttu-id="09232-154">詳細については、「 [更新-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09232-154">For more information, see [Update-FormatData](xref:Microsoft.PowerShell.Utility.Update-FormatData).</span></span>

```powershell
Update-FormatData -PrependPath $HOME\Format\CultureInfo.Format.ps1xml
```

<span data-ttu-id="09232-155">変更をテストするには、 `Get-Culture` **Calendar** プロパティを含む出力を入力して確認します。</span><span class="sxs-lookup"><span data-stu-id="09232-155">To test the change, type `Get-Culture` and review the output that includes the **Calendar** property.</span></span>

```powershell
Get-Culture
```

```Output
LCID  Name   Calendar                                DisplayName
----  ----   --------                                -----------
1033  en-US  System.Globalization.GregorianCalendar  English (United States)
```

## <a name="the-xml-in-formatps1xml-files"></a><span data-ttu-id="09232-156">Format.ps1xml ファイル内の XML</span><span class="sxs-lookup"><span data-stu-id="09232-156">The XML in Format.ps1xml files</span></span>

<span data-ttu-id="09232-157">完全なスキーマ定義は、GitHub の PowerShell ソースコードリポジトリの [.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) にあります。</span><span class="sxs-lookup"><span data-stu-id="09232-157">The full schema definition can be found in [Format.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Format.xsd) in the PowerShell source code repository on GitHub.</span></span>

<span data-ttu-id="09232-158">各ファイルの **Viewdefinitions** セクションには `Format.ps1xml` 、 `<View>` 各ビューを定義するタグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="09232-158">The **ViewDefinitions** section of each `Format.ps1xml` file contains the `<View>` tags that define each view.</span></span> <span data-ttu-id="09232-159">一般的な `<View>` タグには、次のタグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09232-159">A typical `<View>` tag includes the following tags:</span></span>

- <span data-ttu-id="09232-160">`<Name>` ビューの名前を識別します。</span><span class="sxs-lookup"><span data-stu-id="09232-160">`<Name>` identifies the name of the view.</span></span>
- <span data-ttu-id="09232-161">`<ViewSelectedBy>` ビューが適用されるオブジェクトの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="09232-161">`<ViewSelectedBy>` specifies the object type or types to which the view applies.</span></span>
- <span data-ttu-id="09232-162">`<GroupBy>` ビュー内の項目をグループにまとめる方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="09232-162">`<GroupBy>` specifies how items in the view will be combined in groups.</span></span>
- <span data-ttu-id="09232-163">`<TableControl>`、、、およびには、 `<ListControl>` `<WideControl>` `<CustomControl>` 各項目の表示方法を指定するタグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="09232-163">`<TableControl>`, `<ListControl>`, `<WideControl>`, and `<CustomControl>` contain the tags that specify how each item will be displayed.</span></span>

### <a name="viewselectedby-tag"></a><span data-ttu-id="09232-164">タグで viewselected</span><span class="sxs-lookup"><span data-stu-id="09232-164">ViewSelectedBy tag</span></span>

<span data-ttu-id="09232-165">タグには `<ViewSelectedBy>` `<TypeName>` 、ビューが適用されるオブジェクトの種類ごとにタグを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="09232-165">The `<ViewSelectedBy>` tag can contain a `<TypeName>` tag for each object type to which the view applies.</span></span> <span data-ttu-id="09232-166">または、タグを使用して、他の場所で定義されている `<SelectionSetName>` 選択セットを参照するタグを含めることもでき `<SelectionSet>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-166">Or, it can contain a `<SelectionSetName>` tag that references a selection set that is defined elsewhere by using a `<SelectionSet>` tag.</span></span>

### <a name="groupby-tag"></a><span data-ttu-id="09232-167">GroupBy タグ</span><span class="sxs-lookup"><span data-stu-id="09232-167">GroupBy tag</span></span>

<span data-ttu-id="09232-168">タグには、アイテムをグループ化するために使用する `<GroupBy>` オブジェクトプロパティを指定するタグが含まれてい `<PropertyName>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-168">The `<GroupBy>` tag contains a `<PropertyName>` tag that specifies the object property by which items are to be grouped.</span></span> <span data-ttu-id="09232-169">また、 `<Label>` 各グループのラベルとして使用する文字列を指定するタグ、またはタグを `<CustomControlName>` 使用して他の場所で定義されたカスタムコントロールを参照するタグのいずれかも含まれ `<Control>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-169">It also contains either a `<Label>` tag that specifies a string to be used as a label for each group or a `<CustomControlName>` tag that references a custom control defined elsewhere using a `<Control>` tag.</span></span> <span data-ttu-id="09232-170">タグにはタグ `<Control>` とタグが含まれてい `<Name>` `<CustomControl>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-170">The `<Control>` tag contains a `<Name>` tag and a `<CustomControl>` tag.</span></span>

### <a name="tablecontroltag"></a><span data-ttu-id="09232-171">TableControlTag</span><span class="sxs-lookup"><span data-stu-id="09232-171">TableControlTag</span></span>

<span data-ttu-id="09232-172">`<TableControl>`タグには、通常、 `<TableHeaders>` `<TableRowEntries>` テーブルのヘッドと行の書式を定義するタグとタグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="09232-172">The `<TableControl>` tag typically contains `<TableHeaders>` and `<TableRowEntries>` tags that define the formatting for the table's heads and rows.</span></span> <span data-ttu-id="09232-173">`<TableHeaders>`タグには `<TableColumnHeader>` 、通常 `<Label>` 、、、タグを含むタグが含まれてい `<Width>` `<Alignment>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-173">The `<TableHeaders>` tag typically contains `<TableColumnHeader>` tags that contain `<Label>`, `<Width>`, and `<Alignment>` tags.</span></span> <span data-ttu-id="09232-174">`<TableRowEntries>`タグには `<TableRowEntry>` 、テーブルの各行のタグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="09232-174">The `<TableRowEntries>` tag contains `<TableRowEntry>` tags for each row in the table.</span></span> <span data-ttu-id="09232-175">タグには、 `<TableRowEntry>` `<TableColumnItems>` 行の `<TableColumnItem>` 各列のタグを含むタグが含まれています。</span><span class="sxs-lookup"><span data-stu-id="09232-175">The `<TableRowEntry>` tag contains a `<TableColumnItems>` tag that contains a `<TableColumnItem>` tag for each column in the row.</span></span> <span data-ttu-id="09232-176">通常、タグには、定義された `<TableColumnItem>` `<PropertyName>` 場所に表示されるオブジェクトプロパティを識別するタグ、または `<ScriptBlock>` 場所に表示される結果を計算するスクリプトコードを含むタグのいずれかが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09232-176">Typically, the `<TableColumnItem>` tag contains either a `<PropertyName>` tag that identifies the object property to be displayed in the defined location, or a `<ScriptBlock>` tag that contains script code that calculates a result that is to be displayed in the location.</span></span>

> [!NOTE]
> <span data-ttu-id="09232-177">スクリプトブロックは、計算された結果が役に立つ場所の他の場所でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="09232-177">Script blocks can also be used elsewhere in locations where calculated results can be useful.</span></span>

<span data-ttu-id="09232-178">タグには、 `<TableColumnItem>` `<FormatString>` プロパティまたは計算された結果の表示方法を指定するタグを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="09232-178">The `<TableColumnItem>` tag can also contain a `<FormatString>` tag that specifies how the property or the calculated results will be displayed.</span></span>

### <a name="listcontrol-tag"></a><span data-ttu-id="09232-179">ListControl タグ</span><span class="sxs-lookup"><span data-stu-id="09232-179">ListControl tag</span></span>

<span data-ttu-id="09232-180">`<ListControl>`タグには、通常、タグが含まれてい `<ListEntries>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-180">The `<ListControl>` tag typically contains a `<ListEntries>` tag.</span></span> <span data-ttu-id="09232-181">タグには `<ListEntries>` タグが含まれてい `<ListEntry>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-181">The `<ListEntries>` tag contains a `<ListEntry>` tag.</span></span> <span data-ttu-id="09232-182">タグには `<ListEntry>` タグが含まれてい `<ListItems>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-182">The `<ListEntry>` tag contains a `<ListItems>` tag.</span></span> <span data-ttu-id="09232-183">タグにはタグが含ま `<ListItems>` れてい `<ListItem>` `<PropertyName>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-183">The `<ListItems>` tag contains `<ListItem>` tags, which contain `<PropertyName>` tags.</span></span> <span data-ttu-id="09232-184">タグは、 `<PropertyName>` 一覧の指定した位置に表示されるオブジェクトプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="09232-184">The `<PropertyName>` tags specify the object property to be displayed at the specified location in the list.</span></span> <span data-ttu-id="09232-185">選択セットを使用してビューの選択が定義されている場合は、タグ `<ListControl>` と `<ListEntry>` タグに1つ以上のタグを含むタグを含めることもでき `<EntrySelectedBy>` `<TypeName>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-185">If the view selection is defined using a selection set, the `<ListControl>` and `<ListEntry>` tags can also contain an `<EntrySelectedBy>` tag that contains one or more `<TypeName>` tags.</span></span> <span data-ttu-id="09232-186">これらの `<TypeName>` タグは、タグの表示対象となるオブジェクトの種類を指定し `<ListControl>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-186">These `<TypeName>` tags specify the object type that the `<ListControl>` tag is intended to display.</span></span>

### <a name="widecontrol-tag"></a><span data-ttu-id="09232-187">WideControl タグ</span><span class="sxs-lookup"><span data-stu-id="09232-187">WideControl tag</span></span>

<span data-ttu-id="09232-188">`<WideControl>`タグには、通常、タグが含まれてい `<WideEntries>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-188">The `<WideControl>` tag typically contains a `<WideEntries>` tag.</span></span> <span data-ttu-id="09232-189">`<WideEntries>`タグに1つ以上のタグが含まれてい `<WideEntry>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-189">The `<WideEntries>` tag contains one or more `<WideEntry>` tags.</span></span> <span data-ttu-id="09232-190">通常、タグには、 `<WideEntry>` `<PropertyName>` ビュー内の指定した位置に表示されるプロパティを指定するタグが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09232-190">A `<WideEntry>` tag typically contains a `<PropertyName>` tag that specifies the property to be displayed at the specified location in the view.</span></span> <span data-ttu-id="09232-191">タグには、 `<PropertyName>` `<FormatString>` プロパティを表示する方法を指定するタグを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="09232-191">The `<PropertyName>` tag can contain a `<FormatString>` tag that specifies how the property is to be displayed.</span></span>

### <a name="customcontrol-tag"></a><span data-ttu-id="09232-192">CustomControl タグ</span><span class="sxs-lookup"><span data-stu-id="09232-192">CustomControl tag</span></span>

<span data-ttu-id="09232-193">`<CustomControl>`タグを使用すると、スクリプトブロックを使用して形式を定義できます。</span><span class="sxs-lookup"><span data-stu-id="09232-193">The `<CustomControl>` tag lets you use a script block to define a format.</span></span> <span data-ttu-id="09232-194">`<CustomControl>`タグには、通常、複数のタグを含むタグが含まれてい `<CustomEntries>` `<CustomEntry>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-194">A `<CustomControl>` tag typically contains a `<CustomEntries>` tag that contains multiple `<CustomEntry>` tags.</span></span> <span data-ttu-id="09232-195">各 `<CustomEntry>` タグには `<CustomItem>` 、、、、タグなど、ビュー内の指定された場所の内容と書式を指定するさまざまなタグを含めることができるタグが含まれてい `<Text>` `<Indentation>` `<ExpressionBinding>` `<NewLine>` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-195">Each `<CustomEntry>` tag contains a `<CustomItem>` tag that can contain a variety of tags that specify contents and formatting of the specified location in the view, including `<Text>`, `<Indentation>`, `<ExpressionBinding>`, and `<NewLine>` tags.</span></span>

## <a name="tracing-formatps1xml-file-use"></a><span data-ttu-id="09232-196">Xml ファイルの使用 Format.ps1のトレース</span><span class="sxs-lookup"><span data-stu-id="09232-196">Tracing Format.ps1xml file use</span></span>

<span data-ttu-id="09232-197">ファイルの読み込みまたはアプリケーションで発生したエラーを検出するには、 `Format.ps1xml` `Trace-Command` **Name** パラメーターの値として、次のいずれかの形式コンポーネントを指定したコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="09232-197">To detect errors in the loading or application of `Format.ps1xml` files, use the `Trace-Command` cmdlet with any of the following format components as the value of the **Name** parameter:</span></span>

- <span data-ttu-id="09232-198">FormatFileLoading</span><span class="sxs-lookup"><span data-stu-id="09232-198">FormatFileLoading</span></span>
- <span data-ttu-id="09232-199">FormatViewBinding</span><span class="sxs-lookup"><span data-stu-id="09232-199">FormatViewBinding</span></span>

<span data-ttu-id="09232-200">詳細については、「 [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) と [Get tracesource](xref:Microsoft.PowerShell.Utility.Get-TraceSource)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09232-200">For more information, see [Trace-Command](xref:Microsoft.PowerShell.Utility.Trace-Command) and [Get-TraceSource](xref:Microsoft.PowerShell.Utility.Get-TraceSource).</span></span>

## <a name="signing-a-formatps1xml-file"></a><span data-ttu-id="09232-201">Format.ps1xml ファイルへの署名</span><span class="sxs-lookup"><span data-stu-id="09232-201">Signing a Format.ps1xml file</span></span>

<span data-ttu-id="09232-202">ファイルのユーザーを保護するには `Format.ps1xml` 、デジタル署名を使用してファイルに署名します。</span><span class="sxs-lookup"><span data-stu-id="09232-202">To protect the users of your `Format.ps1xml` file, sign the file using a digital signature.</span></span> <span data-ttu-id="09232-203">詳細については、「 [about_Signing](about_Signing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09232-203">For more information, see [about_Signing](about_Signing.md).</span></span>

## <a name="sample-xml-for-a-format-table-custom-view"></a><span data-ttu-id="09232-204">Format-Table カスタムビューのサンプル XML</span><span class="sxs-lookup"><span data-stu-id="09232-204">Sample XML for a Format-Table custom view</span></span>

<span data-ttu-id="09232-205">次の XML サンプルでは、 `Format-Table` によって作成される **DirectoryInfo** および system.object オブジェクトのカスタムビュー **を作成** し `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-205">The following XML sample creates a `Format-Table` custom view for the **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects created by `Get-ChildItem`.</span></span> <span data-ttu-id="09232-206">カスタムビューには **mygciview** という名前が付けられ、テーブルに "作成 **後の時間** " 列が追加されます。</span><span class="sxs-lookup"><span data-stu-id="09232-206">The custom view is named **mygciview** and adds the **CreationTime** column to the table.</span></span>

<span data-ttu-id="09232-207">カスタムビューを作成するには、 `Get-FormatData` コマンドレットとコマンドレットを使用して `Export-FormatData` ファイルを生成し `.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="09232-207">To create the custom view, use the `Get-FormatData` and `Export-FormatData` cmdlets to generate a `.ps1xml` file.</span></span> <span data-ttu-id="09232-208">次に、ファイルを編集して、 `.ps1xml` カスタムビューのコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="09232-208">Then, edit your `.ps1xml` file to create the code for your custom view.</span></span> <span data-ttu-id="09232-209">ファイルは、 `.ps1xml` PowerShell がアクセスできる任意のディレクトリに格納できます。</span><span class="sxs-lookup"><span data-stu-id="09232-209">The `.ps1xml` file can be stored in any directory that PowerShell can access.</span></span> <span data-ttu-id="09232-210">たとえば、のサブディレクトリ `$HOME` です。</span><span class="sxs-lookup"><span data-stu-id="09232-210">For example, a subdirectory of `$HOME`.</span></span>

<span data-ttu-id="09232-211">`.ps1xml`ファイルが作成されたら、コマンドレットを使用して、 `Update-FormatData` 現在の PowerShell セッションにビューを含めます。</span><span class="sxs-lookup"><span data-stu-id="09232-211">After the `.ps1xml` file is created, use the `Update-FormatData` cmdlet to include the view in the current PowerShell session.</span></span> <span data-ttu-id="09232-212">または、すべての PowerShell セッションでビューを使用できるようにする必要がある場合は、PowerShell プロファイルに update コマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="09232-212">Or, add the update command to your PowerShell profile if you need the view available in all PowerShell sessions.</span></span>

<span data-ttu-id="09232-213">この例では、カスタムビューでテーブル形式を使用する必要があります。そうしないと、は `Format-Table` 失敗します。</span><span class="sxs-lookup"><span data-stu-id="09232-213">For this example, the custom view must use the table format, otherwise, `Format-Table` fails.</span></span>

<span data-ttu-id="09232-214">`Format-Table` **View** パラメーターと共にを使用してカスタムビューの名前を指定し、 **mygciview** を使用して、テーブルの出力の形式を作成 **時** の列に設定します。</span><span class="sxs-lookup"><span data-stu-id="09232-214">Use `Format-Table` with the **View** parameter to specify the custom view's name, **mygciview** , and format the table's output with the **CreationTime** column.</span></span> <span data-ttu-id="09232-215">コマンドの実行方法の例については、「 [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09232-215">For an example of how the command is run, see [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

> [!NOTE]
> <span data-ttu-id="09232-216">カスタムビューを作成するためにソースコードから書式設定 XML を取得できますが、必要な結果を得るためにより多くの開発が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="09232-216">Although you can get the formatting XML from the source code to create a custom view, more development might be needed to get the desired result.</span></span>

<span data-ttu-id="09232-217">次のコマンドでは `Get-FormatData` 、 **powershellversion** パラメーターの代わりに、すべてのローカル書式情報が返されるようにしています。</span><span class="sxs-lookup"><span data-stu-id="09232-217">In the following `Get-FormatData` command, there's an alternative for the **PowerShellVersion** parameter to ensure that all local formatting information is returned.</span></span> <span data-ttu-id="09232-218">`-PowerShellVersion $PSVersionTable.PSVersion`特定の PowerShell バージョンではなくを使用します。</span><span class="sxs-lookup"><span data-stu-id="09232-218">Use `-PowerShellVersion $PSVersionTable.PSVersion` rather than a specific PowerShell version.</span></span>

```powershell
Get-FormatData -PowerShellVersion 5.1 -TypeName System.IO.DirectoryInfo |
   Export-FormatData -Path ./Mygciview.Format.ps1xml
Update-FormatData -AppendPath ./Mygciview.Format.ps1xml
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<Configuration>
  <ViewDefinitions>
    <View>
      <Name>mygciview</Name>
      <ViewSelectedBy>
        <TypeName>System.IO.DirectoryInfo</TypeName>
        <TypeName>System.IO.FileInfo</TypeName>
      </ViewSelectedBy>
      <GroupBy>
        <PropertyName>PSParentPath</PropertyName>
      </GroupBy>
      <TableControl>
        <TableHeaders>
          <TableColumnHeader>
            <Label>Mode</Label>
            <Width>7</Width>
            <Alignment>Left</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>LastWriteTime</Label>
            <Width>26</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>CreationTime</Label>
            <Width>26</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>Length</Label>
            <Width>14</Width>
            <Alignment>Right</Alignment>
          </TableColumnHeader>
          <TableColumnHeader>
            <Label>Name</Label>
            <Alignment>Left</Alignment>
          </TableColumnHeader>
        </TableHeaders>
        <TableRowEntries>
          <TableRowEntry>
            <Wrap />
            <TableColumnItems>
              <TableColumnItem>
                <PropertyName>ModeWithoutHardLink</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>LastWriteTime</PropertyName>
              </TableColumnItem>
              <TableColumnItem>
                <PropertyName>CreationTime</PropertyName>
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

## <a name="see-also"></a><span data-ttu-id="09232-219">関連項目</span><span class="sxs-lookup"><span data-stu-id="09232-219">See also</span></span>

[<span data-ttu-id="09232-220">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="09232-220">Export-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Export-FormatData)

[<span data-ttu-id="09232-221">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="09232-221">Get-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Get-FormatData)

[<span data-ttu-id="09232-222">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="09232-222">Get-TraceSource</span></span>](xref:Microsoft.PowerShell.Utility.Get-TraceSource)

[<span data-ttu-id="09232-223">書式設定スキーマ XML リファレンス</span><span class="sxs-lookup"><span data-stu-id="09232-223">Format Schema XML Reference</span></span>](/powershell/scripting/developer/format/format-schema-xml-reference)

[<span data-ttu-id="09232-224">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="09232-224">Trace-Command</span></span>](xref:Microsoft.PowerShell.Utility.Trace-Command)

[<span data-ttu-id="09232-225">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="09232-225">Update-FormatData</span></span>](xref:Microsoft.PowerShell.Utility.Update-FormatData)

[<span data-ttu-id="09232-226">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="09232-226">Writing a PowerShell Formatting File</span></span>](/powershell/scripting/developer/format/writing-a-powershell-formatting-file)
