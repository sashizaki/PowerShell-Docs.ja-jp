---
description: ファイルを使用して `Types.ps1xml` 、PowerShell で使用されるオブジェクトの種類を拡張する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_types.ps1xml?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Types.ps1xml
ms.openlocfilehash: 0b0fcec004b1e9d5b1cd393df675637b550ecf92
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222456"
---
# <a name="about-typesps1xml"></a><span data-ttu-id="55211-104">Types.ps1xml について</span><span class="sxs-lookup"><span data-stu-id="55211-104">About Types.ps1xml</span></span>

## <a name="short-description"></a><span data-ttu-id="55211-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="55211-105">Short description</span></span>
<span data-ttu-id="55211-106">ファイルを使用して `Types.ps1xml` 、PowerShell で使用されるオブジェクトの種類を拡張する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="55211-106">Explains how to use `Types.ps1xml` files to extend the types of objects that are used in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="55211-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="55211-107">Long description</span></span>

<span data-ttu-id="55211-108">拡張型データは、PowerShell でオブジェクト型の追加のプロパティとメソッド ("メンバー") を定義します。</span><span class="sxs-lookup"><span data-stu-id="55211-108">Extended type data defines additional properties and methods ("members") of object types in PowerShell.</span></span> <span data-ttu-id="55211-109">PowerShell セッションに拡張型データを追加するには、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="55211-109">There are two techniques for adding extended type data to a PowerShell session.</span></span>

- <span data-ttu-id="55211-110">`Types.ps1xml` file: 拡張型データを定義する XML ファイル。</span><span class="sxs-lookup"><span data-stu-id="55211-110">`Types.ps1xml` file: An XML file that defines extended type data.</span></span>
- <span data-ttu-id="55211-111">`Update-TypeData`: ファイルを再読み込み `Types.ps1xml` し、現在のセッションの型の拡張データを定義するコマンドレット。</span><span class="sxs-lookup"><span data-stu-id="55211-111">`Update-TypeData`: A cmdlet that reloads `Types.ps1xml` files and defines extended data for types in the current session.</span></span>

<span data-ttu-id="55211-112">このトピックでは、ファイルについて説明し `Types.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="55211-112">This topic describes `Types.ps1xml` files.</span></span> <span data-ttu-id="55211-113">コマンドレットを使用して `Update-TypeData` 動的な拡張型データを現在のセッションに追加する方法の詳細については、「 [更新-typedata](xref:Microsoft.PowerShell.Utility.Update-TypeData)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55211-113">For more information about using the `Update-TypeData` cmdlet to add dynamic extended type data to the current session see [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span></span>

## <a name="about-extended-type-data"></a><span data-ttu-id="55211-114">拡張型データについて</span><span class="sxs-lookup"><span data-stu-id="55211-114">About extended type data</span></span>

<span data-ttu-id="55211-115">拡張型データは、PowerShell でオブジェクト型の追加のプロパティとメソッド ("メンバー") を定義します。</span><span class="sxs-lookup"><span data-stu-id="55211-115">Extended type data defines additional properties and methods ("members") of object types in PowerShell.</span></span> <span data-ttu-id="55211-116">PowerShell でサポートされている任意の型を拡張し、オブジェクトの種類で定義されているプロパティを使用するのと同じ方法で、追加されたプロパティとメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="55211-116">You can extend any type that is supported by PowerShell and use the added properties and methods in the same way that you use the properties that are defined on the object types.</span></span>

<span data-ttu-id="55211-117">たとえば、PowerShell では、 **DateTime** `System.DateTime` コマンドレットから返されるものなど、すべてのオブジェクトに DateTime プロパティが追加さ `Get-Date` れます。</span><span class="sxs-lookup"><span data-stu-id="55211-117">For example, PowerShell adds a **DateTime** property to all `System.DateTime` objects, such as the ones that the `Get-Date` cmdlet returns.</span></span>

```powershell
(Get-Date).DateTime
```

```Output
Sunday, January 29, 2012 9:43:57 AM
```

<span data-ttu-id="55211-118">**Datetime** プロパティは、datetime 構造体の説明には [あり](/dotnet/api/system.datetime)ません。これは、powershell によってプロパティが追加され、powershell でのみ表示されるためです。</span><span class="sxs-lookup"><span data-stu-id="55211-118">You won't find the **DateTime** property in the description of the [System.DateTime](/dotnet/api/system.datetime) structure, because PowerShell adds the property and it is visible only in PowerShell.</span></span>

<span data-ttu-id="55211-119">PowerShell は、内部的に拡張型の既定のセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="55211-119">PowerShell internally defines a default set of extended types.</span></span> <span data-ttu-id="55211-120">この型情報は、起動時にすべての PowerShell セッションに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="55211-120">This type information is loaded in every PowerShell session at startup.</span></span> <span data-ttu-id="55211-121">**DateTime** プロパティは、この既定のセットの一部です。</span><span class="sxs-lookup"><span data-stu-id="55211-121">The **DateTime** property is part of this default set.</span></span> <span data-ttu-id="55211-122">PowerShell 6 より前の場合、型定義は `Types.ps1xml` powershell インストールディレクトリ () に格納されていました `$PSHOME` 。</span><span class="sxs-lookup"><span data-stu-id="55211-122">Prior to PowerShell 6, the type definitions were stored the `Types.ps1xml` file in the PowerShell installation directory (`$PSHOME`).</span></span>

## <a name="adding-extended-type-data-to-powershell"></a><span data-ttu-id="55211-123">PowerShell への拡張型データの追加</span><span class="sxs-lookup"><span data-stu-id="55211-123">Adding extended type data to PowerShell</span></span>

<span data-ttu-id="55211-124">PowerShell セッションには、拡張型データの3つのソースがあります。</span><span class="sxs-lookup"><span data-stu-id="55211-124">There are three sources of extended type data in PowerShell sessions.</span></span>

- <span data-ttu-id="55211-125">PowerShell で定義されたとは、すべての PowerShell セッションに自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="55211-125">The defined by PowerShell and is loaded automatically into every PowerShell session.</span></span> <span data-ttu-id="55211-126">PowerShell 6 以降では、この情報は PowerShell にコンパイルされ、ファイルには付属しなくなりました `Types.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="55211-126">Beginning with PowerShell 6, this information is compiled into PowerShell and is no longer shipped in a `Types.ps1xml` file.</span></span>

- <span data-ttu-id="55211-127">`Types.ps1xml`モジュールが現在のセッションにインポートされるときに、モジュールによってエクスポートされるファイルが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="55211-127">The `Types.ps1xml` files that modules export are loaded when the module is imported into the current session.</span></span>

- <span data-ttu-id="55211-128">コマンドレットを使用して定義されている拡張型データ `Update-TypeData` は、現在のセッションにのみ追加されます。</span><span class="sxs-lookup"><span data-stu-id="55211-128">Extended type data that is defined by using the `Update-TypeData` cmdlet is added only to the current session.</span></span> <span data-ttu-id="55211-129">ファイルには保存されません。</span><span class="sxs-lookup"><span data-stu-id="55211-129">It is not saved in a file.</span></span>

<span data-ttu-id="55211-130">セッションでは、3つのソースからの拡張型データが同じ方法でオブジェクトに適用され、指定された型のすべてのオブジェクトで使用できます。</span><span class="sxs-lookup"><span data-stu-id="55211-130">In the session, the extended type data from the three sources is applied to objects in the same way and is available on all objects of the specified types.</span></span>

## <a name="the-typedata-cmdlets"></a><span data-ttu-id="55211-131">TypeData コマンドレット</span><span class="sxs-lookup"><span data-stu-id="55211-131">The TypeData cmdlets</span></span>

<span data-ttu-id="55211-132">次のコマンドレットは、PowerShell 3.0 以降の **Microsoft Powershell ユーティリティ** モジュールに含まれています。</span><span class="sxs-lookup"><span data-stu-id="55211-132">The following cmdlets are included in the **Microsoft.PowerShell.Utility** module in PowerShell 3.0 and later.</span></span>

- <span data-ttu-id="55211-133">`Get-TypeData`: 現在のセッションの拡張型データを取得します。</span><span class="sxs-lookup"><span data-stu-id="55211-133">`Get-TypeData`: Gets extended type data in the current session.</span></span>
- <span data-ttu-id="55211-134">`Update-TypeData`: `Types.ps1xml` ファイルを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="55211-134">`Update-TypeData`: Reloads `Types.ps1xml` files.</span></span> <span data-ttu-id="55211-135">拡張型データを現在のセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="55211-135">Adds extended type data to the current session.</span></span>
- <span data-ttu-id="55211-136">`Remove-TypeData`: 現在のセッションから拡張型データを削除します。</span><span class="sxs-lookup"><span data-stu-id="55211-136">`Remove-TypeData`: Removes extended type data from the current session.</span></span>

<span data-ttu-id="55211-137">これらのコマンドレットの詳細については、各コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="55211-137">For more information about these cmdlets, see the help topic for each cmdlet.</span></span>

## <a name="built-in-typesps1xml-files"></a><span data-ttu-id="55211-138">組み込みの Types.ps1xml ファイル</span><span class="sxs-lookup"><span data-stu-id="55211-138">Built-in Types.ps1xml files</span></span>

<span data-ttu-id="55211-139">`Types.ps1xml`ディレクトリ内のファイル `$PSHOME` は、すべてのセッションに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="55211-139">The `Types.ps1xml` files in the `$PSHOME` directory are added automatically to every session.</span></span>

<span data-ttu-id="55211-140">`Types.ps1xml`Powershell インストールディレクトリ () のファイル `$PSHOME` は XML ベースのテキストファイルで、powershell で使用されるオブジェクトにプロパティとメソッドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="55211-140">The `Types.ps1xml` file in the PowerShell installation directory (`$PSHOME`) is an XML-based text file that lets you add properties and methods to the objects that are used in PowerShell.</span></span> <span data-ttu-id="55211-141">PowerShell には、 `Types.ps1xml` .net 型にいくつかの要素を追加する組み込みファイルがありますが、追加のファイルを作成して `Types.ps1xml` さらに型を拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="55211-141">PowerShell has built-in `Types.ps1xml` files that add several elements to the .NET types, but you can create additional `Types.ps1xml` files to further extend the types.</span></span>

<span data-ttu-id="55211-142">たとえば、既定では、配列オブジェクト () には、 `System.Array` 配列内のオブジェクトの数を一覧表示する **Length** プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="55211-142">For example, by default, array objects (`System.Array`) have a **Length** property that lists the number of objects in the array.</span></span> <span data-ttu-id="55211-143">ただし、名前の **長さ** によってプロパティが明確に記述されていないため、PowerShell では、同じ値を表示する **Count** という名前のエイリアスプロパティが追加されます。</span><span class="sxs-lookup"><span data-stu-id="55211-143">However, because the name **Length** does not clearly describe the property, PowerShell adds an alias property named **Count** that displays the same value.</span></span> <span data-ttu-id="55211-144">次の XML では、 **Count** プロパティを型に追加して `System.Array` います。</span><span class="sxs-lookup"><span data-stu-id="55211-144">The following XML adds the **Count** property to the `System.Array` type.</span></span>

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>
        Length
      </ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

<span data-ttu-id="55211-145">新しい **エイリアスプロパティ** を取得するには、 `Get-Member` 次の例に示すように、任意の配列に対してコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="55211-145">To get the new **AliasProperty** , use a `Get-Member` command on any array, as shown in the following example.</span></span>

```powershell
Get-Member -InputObject (1,2,3,4)
```

<span data-ttu-id="55211-146">コマンドを実行すると、次の結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="55211-146">The command returns the following results.</span></span>

```Output
Name       MemberType    Definition
----       ----------    ----------
Count      AliasProperty Count = Length
Address    Method        System.Object& Address(Int32)
Clone      Method        System.Object Clone()
CopyTo     Method        System.Void CopyTo(Array array, Int32 index):
Equals     Method        System.Boolean Equals(Object obj)
Get        Method        System.Object Get(Int32)
# ...
```

<span data-ttu-id="55211-147">その結果、PowerShell では、 **Count** プロパティまたは配列の **Length** プロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="55211-147">As a result, you can use either the **Count** property or the **Length** property of arrays in PowerShell.</span></span> <span data-ttu-id="55211-148">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="55211-148">For example:</span></span>

```powershell
(1, 2, 3, 4).count
4
```

```powershell
(1, 2, 3, 4).length
4
```

## <a name="creating-new-typesps1xml-files"></a><span data-ttu-id="55211-149">新しい Types.ps1xml ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="55211-149">Creating new Types.ps1xml files</span></span>

<span data-ttu-id="55211-150">`.ps1xml`PowerShell を使用してインストールされるファイルは、書式設定にスクリプトブロックを含めることができるため、改ざんを防ぐためにデジタル署名されています。</span><span class="sxs-lookup"><span data-stu-id="55211-150">The `.ps1xml` files that are installed with PowerShell are digitally signed to prevent tampering because the formatting can include script blocks.</span></span> <span data-ttu-id="55211-151">そのため、.NET 型にプロパティまたはメソッドを追加するには、独自のファイルを作成 `Types.ps1xml` し、PowerShell セッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="55211-151">Therefore, to add a property or method to a .NET type, create your own `Types.ps1xml` files, and then add them to your PowerShell session.</span></span>

<span data-ttu-id="55211-152">新しいファイルを作成するには、まず既存のファイルをコピーし `Types.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="55211-152">To create a new file, start by copying an existing `Types.ps1xml` file.</span></span> <span data-ttu-id="55211-153">新しいファイルには任意の名前を付けることができますが、ファイル名拡張子を持つ必要があり `.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="55211-153">The new file can have any name, but it must have a `.ps1xml` file name extension.</span></span> <span data-ttu-id="55211-154">PowerShell にアクセスできる任意のディレクトリに新しいファイルを配置できますが、ファイルを PowerShell インストールディレクトリ ( `$PSHOME` ) またはインストールディレクトリのサブディレクトリに配置すると便利です。</span><span class="sxs-lookup"><span data-stu-id="55211-154">You can place the new file in any directory that is accessible to PowerShell, but it is useful to place the files in the PowerShell installation directory (`$PSHOME`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="55211-155">新しいファイルを保存したら、コマンドレットを使用し `Update-TypeData` て PowerShell セッションに新しいファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="55211-155">When you have saved the new file, use the `Update-TypeData` cmdlet to add the new file to your PowerShell session.</span></span> <span data-ttu-id="55211-156">定義されている組み込み型よりも型を優先する場合は、コマンドレットの **PrependData** パラメーターを使用し `Update-TypeData` ます。</span><span class="sxs-lookup"><span data-stu-id="55211-156">If you want your types to take precedence over the built-in types that are defined, use the **PrependData** parameter of the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="55211-157">`Update-TypeData` 現在のセッションのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="55211-157">`Update-TypeData` affects only the current session.</span></span> <span data-ttu-id="55211-158">今後のすべてのセッションに変更を加えるには、コンソールをエクスポートするか、 `Update-TypeData` PowerShell プロファイルにコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="55211-158">To make the change to all future sessions, export the console, or add the `Update-TypeData` command to your PowerShell profile.</span></span>

## <a name="typesps1xml-and-add-member"></a><span data-ttu-id="55211-159">Types.ps1xml と Add-Member</span><span class="sxs-lookup"><span data-stu-id="55211-159">Types.ps1xml and Add-Member</span></span>

<span data-ttu-id="55211-160">ファイルは、 `Types.ps1xml` 影響を受ける PowerShell セッションで、指定された .net 型のオブジェクトのすべてのインスタンスにプロパティとメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="55211-160">The `Types.ps1xml` files add properties and methods to all the instances of the objects of the specified .NET type in the affected PowerShell session.</span></span> <span data-ttu-id="55211-161">ただし、プロパティまたはメソッドをオブジェクトの1つのインスタンスにのみ追加する必要がある場合は、コマンドレットを使用し `Add-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="55211-161">However, if you need to add properties or methods only to one instance of an object, use the `Add-Member` cmdlet.</span></span>

<span data-ttu-id="55211-162">詳細については、「 [メンバーの追加](xref:Microsoft.PowerShell.Utility.Add-Member)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55211-162">For more information, see [Add-Member](xref:Microsoft.PowerShell.Utility.Add-Member).</span></span>

## <a name="example-adding-an-age-member-to-fileinfo-objects"></a><span data-ttu-id="55211-163">例: FileInfo オブジェクトへの Age メンバーの追加</span><span class="sxs-lookup"><span data-stu-id="55211-163">Example: Adding an Age member to FileInfo objects</span></span>

<span data-ttu-id="55211-164">この例では、 **Age** プロパティを system.object オブジェクトに追加する **方法を示し** ます。</span><span class="sxs-lookup"><span data-stu-id="55211-164">This example shows how to add an **Age** property to **System.IO.FileInfo** objects.</span></span> <span data-ttu-id="55211-165">ファイルの有効期間は、その作成時刻と現在の時刻の差です (日数)。</span><span class="sxs-lookup"><span data-stu-id="55211-165">The age of a file is the difference between its creation time and the current time in days.</span></span>

<span data-ttu-id="55211-166">**Age** プロパティは、スクリプトブロックを使用して計算されるので、 `<ScriptProperty>` 新しい **age** プロパティのモデルとして使用するタグを見つけます。</span><span class="sxs-lookup"><span data-stu-id="55211-166">Because the **Age** property is calculated by using a script block, find a `<ScriptProperty>` tag to use as a model for the new **Age** property.</span></span>

<span data-ttu-id="55211-167">次の XML コードをファイルに保存し `$PSHOME\MyTypes.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="55211-167">Save the follow XML code to the file `$PSHOME\MyTypes.ps1xml`.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<Types>
  <Type>
    <Name>System.IO.FileInfo</Name>
    <Members>
      <ScriptProperty>
        <Name>Age</Name>
        <GetScriptBlock>
          ((Get-Date) - ($this.CreationTime)).Days
        </GetScriptBlock>
      </ScriptProperty>
    </Members>
  </Type>
</Types>
```

<span data-ttu-id="55211-168">を実行して、 `Update-TypeData` 現在のセッションに新しいファイルを追加し `Types.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="55211-168">Run `Update-TypeData` to add the new `Types.ps1xml` file to the current session.</span></span> <span data-ttu-id="55211-169">このコマンドは、 **PrependData** パラメーターを使用して、新しいファイルを元の定義よりも上位の優先順位に配置します。</span><span class="sxs-lookup"><span data-stu-id="55211-169">The command uses the **PrependData** parameter to place the new file in a precedence order higher than the original definitions.</span></span>

<span data-ttu-id="55211-170">の詳細について `Update-TypeData` は、「 [更新-typedata](xref:Microsoft.PowerShell.Utility.Update-TypeData)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55211-170">For more information about `Update-TypeData`, see [Update-TypeData](xref:Microsoft.PowerShell.Utility.Update-TypeData).</span></span>

```powershell
Update-Typedata -PrependPath $PSHOME\MyTypes.ps1xml
```

<span data-ttu-id="55211-171">変更をテストするには、コマンドを実行して `Get-ChildItem` ディレクトリ内の PowerShell.exe ファイルを取得し、そのファイルを `$PSHOME` コマンドレットにパイプして、 `Format-List` ファイルのすべてのプロパティを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="55211-171">To test the change, run a `Get-ChildItem` command to get the PowerShell.exe file in the `$PSHOME` directory, and then pipe the file to the `Format-List` cmdlet to list all of the properties of the file.</span></span> <span data-ttu-id="55211-172">変更の結果として、 **Age** プロパティが一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="55211-172">As a result of the change, the **Age** property appears in the list.</span></span>

```powershell
Get-ChildItem $PSHOME\pwsh.exe | Select-Object Age
```

```Output
142
```

## <a name="the-xml-in-typesps1xml-files"></a><span data-ttu-id="55211-173">Types.ps1xml ファイル内の XML</span><span class="sxs-lookup"><span data-stu-id="55211-173">The XML in Types.ps1xml files</span></span>

<span data-ttu-id="55211-174">完全なスキーマ定義は、GitHub の PowerShell ソースコードリポジトリにある [Types .xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Types.xsd) にあります。</span><span class="sxs-lookup"><span data-stu-id="55211-174">The full schema definition can be found in [Types.xsd](https://github.com/PowerShell/PowerShell/blob/master/src/Schemas/Types.xsd) in the PowerShell source code repository on GitHub.</span></span>

<span data-ttu-id="55211-175">タグは、 `<Types>` ファイルで定義されているすべての型を囲みます。</span><span class="sxs-lookup"><span data-stu-id="55211-175">The `<Types>` tag encloses all of the types that are defined in the file.</span></span> <span data-ttu-id="55211-176">タグは1つだけにする必要があり `<Types>` ます。</span><span class="sxs-lookup"><span data-stu-id="55211-176">There should be only one `<Types>` tag.</span></span>

<span data-ttu-id="55211-177">ファイルに記述されている各 .NET 型は、タグで表す必要があり `<Type>` ます。</span><span class="sxs-lookup"><span data-stu-id="55211-177">Each .NET type mentioned in the file should be represented by a `<Type>` tag.</span></span>

<span data-ttu-id="55211-178">型タグには、次のタグが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="55211-178">The type tags must contain the following tags:</span></span>

<span data-ttu-id="55211-179">`<Name>`: 影響を受ける .NET 型の名前を囲みます。</span><span class="sxs-lookup"><span data-stu-id="55211-179">`<Name>`: Encloses the name of the affected .NET type.</span></span>

<span data-ttu-id="55211-180">`<Members>`: .NET 型に対して定義されている新しいプロパティとメソッドのタグを囲みます。</span><span class="sxs-lookup"><span data-stu-id="55211-180">`<Members>`: Encloses the tags for the new properties and methods that are defined for the .NET type.</span></span>

<span data-ttu-id="55211-181">タグ内には、次のいずれかのメンバータグを含めることができ `<Members>` ます。</span><span class="sxs-lookup"><span data-stu-id="55211-181">Any of the following member tags can be inside the `<Members>` tag.</span></span>

<span data-ttu-id="55211-182">`<AliasProperty>`: 既存のプロパティの新しい名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="55211-182">`<AliasProperty>`: Defines a new name for an existing property.</span></span>

<span data-ttu-id="55211-183">タグには、 `<AliasProperty>` `<Name>` 新しいプロパティの名前と既存のプロパティを指定するタグを指定するタグが必要 `<ReferencedMemberName>` です。</span><span class="sxs-lookup"><span data-stu-id="55211-183">The `<AliasProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<ReferencedMemberName>` tag that specifies the existing property.</span></span>

<span data-ttu-id="55211-184">たとえば、 **Count** エイリアスプロパティは、配列オブジェクトの **Length** プロパティのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="55211-184">For example, the **Count** alias property is an alias for the **Length** property of array objects.</span></span>

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>Length</ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

<span data-ttu-id="55211-185">`<CodeMethod>`: .NET クラスの静的メソッドを参照します。</span><span class="sxs-lookup"><span data-stu-id="55211-185">`<CodeMethod>`:  References a static method of a .NET class.</span></span>

<span data-ttu-id="55211-186">タグには、 `<CodeMethod>` `<Name>` 新しいメソッドの名前を指定するタグと `<GetCodeReference>` 、メソッドが定義されているコードを指定するタグが必要です。</span><span class="sxs-lookup"><span data-stu-id="55211-186">The `<CodeMethod>` tag must have a `<Name>` tag that specifies the name of the new method and a `<GetCodeReference>` tag that specifies the code in which the method is defined.</span></span>

<span data-ttu-id="55211-187">たとえば、オブジェクトの **Mode** プロパティ `System.IO.DirectoryInfo` は、PowerShell FileSystem プロバイダーで定義されているコードプロパティです。</span><span class="sxs-lookup"><span data-stu-id="55211-187">For example, the **Mode** property of `System.IO.DirectoryInfo` objects is a code property defined in the PowerShell FileSystem provider.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>
          Microsoft.PowerShell.Commands.FileSystemProvider
        </TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

<span data-ttu-id="55211-188">`<CodeProperty>`: .NET クラスの静的メソッドを参照します。</span><span class="sxs-lookup"><span data-stu-id="55211-188">`<CodeProperty>`: References a static method of a .NET class.</span></span>

<span data-ttu-id="55211-189">タグには、 `<CodeProperty>` `<Name>` 新しいプロパティの名前を指定するタグと、プロパティが定義されているコードを指定するタグが必要 `<GetCodeReference>` です。</span><span class="sxs-lookup"><span data-stu-id="55211-189">The `<CodeProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<GetCodeReference>` tag that specifies the code in which the property is defined.</span></span>

<span data-ttu-id="55211-190">たとえば、オブジェクトの **Mode** プロパティ `System.IO.DirectoryInfo` は、PowerShell FileSystem プロバイダーで定義されているコードプロパティです。</span><span class="sxs-lookup"><span data-stu-id="55211-190">For example, the **Mode** property of `System.IO.DirectoryInfo` objects is a code property defined in the PowerShell FileSystem provider.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>
          Microsoft.PowerShell.Commands.FileSystemProvider
        </TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

<span data-ttu-id="55211-191">`<MemberSet>`: メンバーのコレクション (プロパティとメソッド) を定義します。</span><span class="sxs-lookup"><span data-stu-id="55211-191">`<MemberSet>`: Defines a collection of members (properties and methods).</span></span>

<span data-ttu-id="55211-192">タグは、 `<MemberSet>` プライマリタグ内に表示され `<Members>` ます。</span><span class="sxs-lookup"><span data-stu-id="55211-192">The `<MemberSet>` tags appear within the primary `<Members>` tags.</span></span> <span data-ttu-id="55211-193">タグは、 `<Name>` メンバーセットの名前を囲むタグと `<Members>` 、セット内のメンバー (プロパティとメソッド) を囲むセカンダリタグで囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="55211-193">The tags must enclose a `<Name>` tag surrounding the name of the member set and a secondary `<Members>` tag that surround the members (properties and methods) in the set.</span></span> <span data-ttu-id="55211-194">プロパティ (やなど) またはメソッド (やなど) を作成するすべてのタグは `<NoteProperty>` `<ScriptProperty>` `<Method>` `<ScriptMethod>` 、セットのメンバーになることができます。</span><span class="sxs-lookup"><span data-stu-id="55211-194">Any of the tags that create a property (such as `<NoteProperty>` or `<ScriptProperty>`) or a method (such as `<Method>` or `<ScriptMethod>`) can be members of the set.</span></span>

<span data-ttu-id="55211-195">ファイルでは、タグを使用して `Types.ps1xml` `<MemberSet>` PowerShell で .net オブジェクトの既定のビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="55211-195">In `Types.ps1xml` files, the `<MemberSet>` tag is used to define the default views of the .NET objects in PowerShell.</span></span> <span data-ttu-id="55211-196">この場合、メンバーセットの名前 (タグ内の値 `<Name>` ) は常に **Psstandardmembers** で、プロパティの名前 (タグの値 `<Name>` ) は次のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="55211-196">In this case, the name of the member set (the value within the `<Name>` tags) is always **PsStandardMembers** , and the names of the properties (the value of the `<Name>` tag) are one of the following:</span></span>

- <span data-ttu-id="55211-197">`DefaultDisplayProperty`: オブジェクトの1つのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="55211-197">`DefaultDisplayProperty`: A single property of an object.</span></span>

- <span data-ttu-id="55211-198">`DefaultDisplayPropertySet`: オブジェクトの1つ以上のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="55211-198">`DefaultDisplayPropertySet`: One or more properties of an object.</span></span>

- <span data-ttu-id="55211-199">`DefaultKeyPropertySet`: オブジェクトの1つまたは複数のキープロパティ。</span><span class="sxs-lookup"><span data-stu-id="55211-199">`DefaultKeyPropertySet`: One or more key properties of an object.</span></span> <span data-ttu-id="55211-200">キープロパティは、セッション履歴内の項目の ID 番号など、プロパティ値のインスタンスを識別します。</span><span class="sxs-lookup"><span data-stu-id="55211-200">A key property identifies instances of property values, such as the ID number of items in a session history.</span></span>

<span data-ttu-id="55211-201">たとえば、次の XML では、 `System.ServiceProcess.ServiceController` コマンドレットによって返されるサービス (オブジェクト) の既定の表示を定義して `Get-Service` います。</span><span class="sxs-lookup"><span data-stu-id="55211-201">For example, the following XML defines the default display of services (`System.ServiceProcess.ServiceController` objects) that are returned by the `Get-Service` cmdlet.</span></span> <span data-ttu-id="55211-202">**Psstandardmembers** という名前のメンバーセットを定義します。これは、 **Status** 、 **Name** 、 **DisplayName** の各プロパティが設定された既定のプロパティで構成されます。</span><span class="sxs-lookup"><span data-stu-id="55211-202">It defines a member set named **PsStandardMembers** that consists of a default property set with the **Status** , **Name** , and **DisplayName** properties.</span></span>

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
          <Name>DefaultDisplayPropertySet</Name>
          <ReferencedProperties>
            <Name>Status</Name>
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

<span data-ttu-id="55211-203">`<Method>`: 基になるオブジェクトのネイティブメソッドを参照します。</span><span class="sxs-lookup"><span data-stu-id="55211-203">`<Method>`: References a native method of the underlying object.</span></span>

<span data-ttu-id="55211-204">`<Methods>`: オブジェクトのメソッドのコレクション。</span><span class="sxs-lookup"><span data-stu-id="55211-204">`<Methods>`: A collection of the methods of the object.</span></span>

<span data-ttu-id="55211-205">`<NoteProperty>`: 静的な値を持つプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="55211-205">`<NoteProperty>`: Defines a property with a static value.</span></span>

<span data-ttu-id="55211-206">タグには、 `<NoteProperty>` `<Name>` 新しいプロパティの名前を指定するタグと、 `<Value>` プロパティの値を指定するタグが必要です。</span><span class="sxs-lookup"><span data-stu-id="55211-206">The `<NoteProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<Value>` tag that specifies the value of the property.</span></span>

<span data-ttu-id="55211-207">たとえば、次の XML では、 **DirectoryInfo** オブジェクトの **Status** プロパティが作成されます。</span><span class="sxs-lookup"><span data-stu-id="55211-207">For example, the following XML creates a **Status** property for **System.IO.DirectoryInfo** objects.</span></span> <span data-ttu-id="55211-208">**Status** プロパティの値は常に **Success** です。</span><span class="sxs-lookup"><span data-stu-id="55211-208">The value of the **Status** property is always **Success**.</span></span>

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <NoteProperty>
      <Name>Status</Name>
      <Value>Success</Value>
    </NoteProperty>
  </Members>
</Type>
```

<span data-ttu-id="55211-209">`<ParameterizedProperty>`: 引数を受け取り、値を返すプロパティ。</span><span class="sxs-lookup"><span data-stu-id="55211-209">`<ParameterizedProperty>`: Properties that take arguments and return a value.</span></span>

<span data-ttu-id="55211-210">`<Properties>`: オブジェクトのプロパティのコレクション。</span><span class="sxs-lookup"><span data-stu-id="55211-210">`<Properties>`: A collection of the properties of the object.</span></span>

<span data-ttu-id="55211-211">`<Property>`: ベースオブジェクトのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="55211-211">`<Property>`: A property of the base object.</span></span>

<span data-ttu-id="55211-212">`<PropertySet>`: オブジェクトのプロパティのコレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="55211-212">`<PropertySet>`: Defines a collection of properties of the object.</span></span>

<span data-ttu-id="55211-213">タグには、 `<PropertySet>` `<Name>` プロパティセットの名前と、プロパティを指定するタグを指定するタグが必要 `<ReferencedProperty>` です。</span><span class="sxs-lookup"><span data-stu-id="55211-213">The `<PropertySet>` tag must have a `<Name>` tag that specifies the name of the property set and a `<ReferencedProperty>` tag that specifies the properties.</span></span> <span data-ttu-id="55211-214">プロパティの名前はタグで囲まれ `<Name>` ます。</span><span class="sxs-lookup"><span data-stu-id="55211-214">The names of the properties are enclosed in `<Name>` tag.</span></span>

<span data-ttu-id="55211-215">で `Types.ps1xml` は、タグを使用して、 `<PropertySet>` オブジェクトの既定の表示のプロパティのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="55211-215">In `Types.ps1xml`, `<PropertySet>` tags are used to define sets of properties for the default display of an object.</span></span> <span data-ttu-id="55211-216">既定の表示は、タグのタグの **Psstandardmembers** 値によって識別でき `<Name>` `<MemberSet>` ます。</span><span class="sxs-lookup"><span data-stu-id="55211-216">You can identify the default displays by the value **PsStandardMembers** in the `<Name>` tag of a `<MemberSet>` tag.</span></span>

<span data-ttu-id="55211-217">たとえば、次の XML では、オブジェクトの **Status** プロパティが作成され `System.IO.DirectoryInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="55211-217">For example, the following XML creates a **Status** property for the `System.IO.DirectoryInfo` object.</span></span> <span data-ttu-id="55211-218">**Status** プロパティの値は常に **Success** です。</span><span class="sxs-lookup"><span data-stu-id="55211-218">The value of the **Status** property is always **Success**.</span></span>

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
          <Name>DefaultDisplayPropertySet</Name>
          <ReferencedProperties>
            <Name>Status</Name>
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

<span data-ttu-id="55211-219">`<ScriptMethod>`: スクリプトの出力を値として持つメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="55211-219">`<ScriptMethod>`: Defines a method whose value is the output of a script.</span></span>

<span data-ttu-id="55211-220">タグには、 `<ScriptMethod>` `<Name>` 新しいメソッドの名前と、 `<Script>` メソッドの結果を返すスクリプトブロックを囲むタグを指定するタグが必要です。</span><span class="sxs-lookup"><span data-stu-id="55211-220">The `<ScriptMethod>` tag must have a `<Name>` tag that specifies the name of the new method and a `<Script>` tag that encloses the script block that returns the method result.</span></span>

<span data-ttu-id="55211-221">たとえば、 `ConvertToDateTime` `ConvertFromDateTime` 管理オブジェクト () のメソッドとメソッド `System.System.Management.ManagementObject` は、 `ToDateTime` `ToDmtfDateTime` クラスのおよび静的メソッドを使用するスクリプトメソッドです `System.Management.ManagementDateTimeConverter` 。</span><span class="sxs-lookup"><span data-stu-id="55211-221">For example, the `ConvertToDateTime` and `ConvertFromDateTime` methods of management objects (`System.System.Management.ManagementObject`) are script methods that use the `ToDateTime` and `ToDmtfDateTime` static methods of the `System.Management.ManagementDateTimeConverter` class.</span></span>

```xml
<Type>
 <Name>System.Management.ManagementObject</Name>
 <Members>
 <ScriptMethod>
   <Name>ConvertToDateTime</Name>
   <Script>
   [System.Management.ManagementDateTimeConverter]::ToDateTime($args[0])
   </Script>
 </ScriptMethod>
 <ScriptMethod>
   <Name>ConvertFromDateTime</Name>
   <Script>
   [System.Management.ManagementDateTimeConverter]::ToDmtfDateTime($args[0])
   </Script>
 </ScriptMethod>
 </Members>
</Type>
```

<span data-ttu-id="55211-222">`<ScriptProperty>`: スクリプトの出力を値として持つプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="55211-222">`<ScriptProperty>`: Defines a property whose value is the output of a script.</span></span>

<span data-ttu-id="55211-223">タグには、 `<ScriptProperty>` `<Name>` 新しいプロパティの名前を指定するタグと、 `<GetScriptBlock>` プロパティ値を返すスクリプトブロックを囲むタグが必要です。</span><span class="sxs-lookup"><span data-stu-id="55211-223">The `<ScriptProperty>` tag must have a `<Name>` tag that specifies the name of the new property and a `<GetScriptBlock>` tag that encloses the script block that returns the property value.</span></span>

<span data-ttu-id="55211-224">たとえば、 **VersionInfo** オブジェクトの GetVersionInfo プロパティは、 **FileVersionInfo** オブジェクトの **GetVersionInfo** 静的メソッドの **FullName** プロパティを使用した結果として得られるスクリプトプロパティ **です。**</span><span class="sxs-lookup"><span data-stu-id="55211-224">For example, the **VersionInfo** property of the **System.IO.FileInfo** object is a script property that results from using the **FullName** property of the **GetVersionInfo** static method of **System.Diagnostics.FileVersionInfo** objects.</span></span>

```xml
<Type>
  <Name>System.IO.FileInfo</Name>
  <Members>
    <ScriptProperty>
      <Name>VersionInfo</Name>
      <GetScriptBlock>
      [System.Diagnostics.FileVersionInfo]::GetVersionInfo($this.FullName)
      </GetScriptBlock>
    </ScriptProperty>
  </Members>
</Type>
```

<span data-ttu-id="55211-225">詳細については、「 [Windows PowerShell Software Development Kit (SDK)](/powershell/scripting/developer/windows-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55211-225">For more information, see the [Windows PowerShell Software Development Kit (SDK)](/powershell/scripting/developer/windows-powershell).</span></span>

## <a name="update-typedata"></a><span data-ttu-id="55211-226">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="55211-226">Update-TypeData</span></span>

<span data-ttu-id="55211-227">`Types.ps1xml`PowerShell セッションにファイルを読み込むには、コマンドレットを実行し `Update-TypeData` ます。</span><span class="sxs-lookup"><span data-stu-id="55211-227">To load your `Types.ps1xml` files into a PowerShell session, run the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="55211-228">ファイル内の型を組み込みファイル内の型よりも優先する場合は `Types.ps1xml` 、の **PrependData** パラメーターを追加し `Update-TypeData` ます。</span><span class="sxs-lookup"><span data-stu-id="55211-228">If you want the types in your file to take precedence over types in the built-in `Types.ps1xml` file, add the **PrependData** parameter of `Update-TypeData`.</span></span> <span data-ttu-id="55211-229">`Update-TypeData` 現在のセッションのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="55211-229">`Update-TypeData` affects only the current session.</span></span> <span data-ttu-id="55211-230">今後のすべてのセッションに変更を加えるには、セッションをエクスポートするか、 `Update-TypeData` PowerShell プロファイルにコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="55211-230">To make the change to all future sessions, export the session, or add the `Update-TypeData` command to your PowerShell profile.</span></span>

<span data-ttu-id="55211-231">プロパティで発生した例外、またはプロパティをコマンドに追加したときに発生した例外は `Update-TypeData` 、にエラーを報告しません `StdErr` 。</span><span class="sxs-lookup"><span data-stu-id="55211-231">Exceptions that occur in properties, or from adding properties to an `Update-TypeData` command, do not report errors to `StdErr`.</span></span> <span data-ttu-id="55211-232">これは、書式設定および出力の際に、多くの一般的な型で発生する例外を抑制します。</span><span class="sxs-lookup"><span data-stu-id="55211-232">This is to suppress exceptions that would occur in many common types during formatting and outputting.</span></span> <span data-ttu-id="55211-233">.NET のプロパティを取得する場合は、次の例に示すように、代わりにメソッド構文を使用して例外の抑制を回避できます。</span><span class="sxs-lookup"><span data-stu-id="55211-233">If you are getting .NET properties, you can work around the suppression of exceptions by using method syntax instead, as shown in the following example:</span></span>

```powershell
"hello".get_Length()
```

<span data-ttu-id="55211-234">メソッド構文は .NET プロパティでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="55211-234">Note that method syntax can only be used with .NET properties.</span></span> <span data-ttu-id="55211-235">コマンドレットの実行によって追加されたプロパティ `Update-TypeData` は、メソッド構文を使用できません。</span><span class="sxs-lookup"><span data-stu-id="55211-235">Properties that are added by running the `Update-TypeData` cmdlet cannot use method syntax.</span></span>

## <a name="signing-a-typesps1xml-file"></a><span data-ttu-id="55211-236">Types.ps1xml ファイルへの署名</span><span class="sxs-lookup"><span data-stu-id="55211-236">Signing a Types.ps1xml file</span></span>

<span data-ttu-id="55211-237">ファイルのユーザーを保護するために `Types.ps1xml` 、デジタル署名を使用してファイルに署名することができます。</span><span class="sxs-lookup"><span data-stu-id="55211-237">To protect users of your `Types.ps1xml` file, you can sign the file using a digital signature.</span></span> <span data-ttu-id="55211-238">詳細については、「 [about_Signing](about_Signing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55211-238">For more information, see [about_Signing](about_Signing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="55211-239">関連項目</span><span class="sxs-lookup"><span data-stu-id="55211-239">See also</span></span>

[<span data-ttu-id="55211-240">about_Signing</span><span class="sxs-lookup"><span data-stu-id="55211-240">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="55211-241">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="55211-241">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)

[<span data-ttu-id="55211-242">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="55211-242">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

[<span data-ttu-id="55211-243">Get-Member</span><span class="sxs-lookup"><span data-stu-id="55211-243">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

[<span data-ttu-id="55211-244">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="55211-244">Get-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Get-TypeData)

[<span data-ttu-id="55211-245">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="55211-245">Remove-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Remove-TypeData)

[<span data-ttu-id="55211-246">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="55211-246">Update-TypeData</span></span>](xref:Microsoft.PowerShell.Utility.Update-TypeData)
