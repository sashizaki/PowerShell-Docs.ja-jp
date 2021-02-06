---
description: PowerShell でハッシュテーブルを作成、使用、および並べ替える方法について説明します。
Locale: en-US
ms.date: 11/28/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_hash_tables?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Hash_Tables
ms.openlocfilehash: dec2683acfa4fcf79419beea9e0840387d3d43d1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603209"
---
# <a name="about-hash-tables"></a><span data-ttu-id="a2b6e-103">ハッシュテーブルについて</span><span class="sxs-lookup"><span data-stu-id="a2b6e-103">About Hash Tables</span></span>

## <a name="short-description"></a><span data-ttu-id="a2b6e-104">概要</span><span class="sxs-lookup"><span data-stu-id="a2b6e-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="a2b6e-105">PowerShell でハッシュテーブルを作成、使用、および並べ替える方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-105">Describes how to create, use, and sort hash tables in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="a2b6e-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="a2b6e-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="a2b6e-107">ハッシュテーブルは、ディクショナリまたは連想配列とも呼ばれ、1つまたは複数のキーと値のペアを格納するコンパクトなデータ構造です。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-107">A hash table, also known as a dictionary or associative array, is a compact data structure that stores one or more key/value pairs.</span></span> <span data-ttu-id="a2b6e-108">たとえば、ハッシュテーブルには、一連の IP アドレスとコンピューター名が含まれている場合があります。 IP アドレスはキー、コンピューター名は値、またはその逆です。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-108">For example, a hash table might contain a series of IP addresses and computer names, where the IP addresses are the keys and the computer names are the values, or vice versa.</span></span>

<span data-ttu-id="a2b6e-109">PowerShell では、各ハッシュテーブルは Hashtable (system.string) オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-109">In PowerShell, each hash table is a Hashtable (System.Collections.Hashtable) object.</span></span> <span data-ttu-id="a2b6e-110">PowerShell では、Hashtable オブジェクトのプロパティとメソッドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-110">You can use the properties and methods of Hashtable objects in PowerShell.</span></span>

<span data-ttu-id="a2b6e-111">PowerShell 3.0 以降では、PowerShell で [ordered] 属性を使用して、順序付けされた辞書 (OrderedDictionary) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-111">Beginning in PowerShell 3.0, you can use the [ordered] attribute to create an ordered dictionary (System.Collections.Specialized.OrderedDictionary) in PowerShell.</span></span>

<span data-ttu-id="a2b6e-112">順序付けされたディクショナリはハッシュテーブルとは異なり、キーは常に一覧表示される順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-112">Ordered dictionaries differ from hash tables in that the keys always appear in the order in which you list them.</span></span> <span data-ttu-id="a2b6e-113">ハッシュテーブル内のキーの順序は決定されません。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-113">The order of keys in a hash table is not determined.</span></span>

<span data-ttu-id="a2b6e-114">ハッシュテーブルのキーと値は、.NET オブジェクトでもあります。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-114">The keys and value in hash tables are also .NET objects.</span></span> <span data-ttu-id="a2b6e-115">多くの場合、文字列または整数ですが、任意のオブジェクト型を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-115">They are most often strings or integers, but they can have any object type.</span></span> <span data-ttu-id="a2b6e-116">また、入れ子になったハッシュテーブルを作成することもできます。この場合、キーの値は別のハッシュテーブルになります。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-116">You can also create nested hash tables, in which the value of a key is another hash table.</span></span>

<span data-ttu-id="a2b6e-117">ハッシュテーブルは、データの検索と取得に非常に効率的であるため、頻繁に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-117">Hash tables are frequently used because they are very efficient for finding and retrieving data.</span></span> <span data-ttu-id="a2b6e-118">ハッシュテーブルを使用して、一覧を格納したり、PowerShell で計算されたプロパティを作成したりできます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-118">You can use hash tables to store lists and to create calculated properties in PowerShell.</span></span> <span data-ttu-id="a2b6e-119">また、PowerShell には、文字列をハッシュテーブルに変換する Convertfrom-csv Convertfrom-stringdata というコマンドレットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-119">And, PowerShell has a cmdlet, ConvertFrom-StringData, that converts strings to a hash table.</span></span>

### <a name="syntax"></a><span data-ttu-id="a2b6e-120">構文</span><span class="sxs-lookup"><span data-stu-id="a2b6e-120">Syntax</span></span>

<span data-ttu-id="a2b6e-121">ハッシュテーブルの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-121">The syntax of a hash table is as follows:</span></span>

```powershell
@{ <name> = <value>; [<name> = <value> ] ...}
```

<span data-ttu-id="a2b6e-122">順序付けられたディクショナリの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-122">The syntax of an ordered dictionary is as follows:</span></span>

```powershell
[ordered]@{ <name> = <value>; [<name> = <value> ] ...}
```

<span data-ttu-id="a2b6e-123">PowerShell 3.0 では、[ordered] 属性が導入されました。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-123">The [ordered] attribute was introduced in PowerShell 3.0.</span></span>

### <a name="creating-hash-tables"></a><span data-ttu-id="a2b6e-124">ハッシュテーブルの作成</span><span class="sxs-lookup"><span data-stu-id="a2b6e-124">Creating Hash Tables</span></span>

<span data-ttu-id="a2b6e-125">ハッシュテーブルを作成するには、次のガイドラインに従います。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-125">To create a hash table, follow these guidelines:</span></span>

- <span data-ttu-id="a2b6e-126">アットマーク (@) を使用してハッシュテーブルを開始します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-126">Begin the hash table with an at sign (@).</span></span>
- <span data-ttu-id="a2b6e-127">ハッシュテーブルを中かっこ () で囲み {} ます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-127">Enclose the hash table in braces ({}).</span></span>
- <span data-ttu-id="a2b6e-128">ハッシュテーブルのコンテンツの1つまたは複数のキーと値のペアを入力します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-128">Enter one or more key/value pairs for the content of the hash table.</span></span>
- <span data-ttu-id="a2b6e-129">各キーを値から区切るには、等号 (=) を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-129">Use an equal sign (=) to separate each key from its value.</span></span>
- <span data-ttu-id="a2b6e-130">セミコロン (;) を使用するまたは、キーと値のペアを区切るための改行。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-130">Use a semicolon (;) or a line break to separate the key/value pairs.</span></span>
- <span data-ttu-id="a2b6e-131">スペースが含まれているキーは、引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-131">Key that contains spaces must be enclosed in quotation marks.</span></span> <span data-ttu-id="a2b6e-132">値は有効な PowerShell 式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-132">Values must be valid PowerShell expressions.</span></span> <span data-ttu-id="a2b6e-133">文字列は、スペースを含まない場合でも引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-133">Strings must appear in quotation marks, even if they do not include spaces.</span></span>
- <span data-ttu-id="a2b6e-134">ハッシュテーブルを管理するには、それを変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-134">To manage the hash table, save it in a variable.</span></span>
- <span data-ttu-id="a2b6e-135">順序付けされたハッシュテーブルを変数に割り当てる場合は、[ordered] 属性を "@" 記号の前に配置します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-135">When assigning an ordered hash table to a variable, place the [ordered] attribute before the "@" symbol.</span></span> <span data-ttu-id="a2b6e-136">変数名の前に配置すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-136">If you place it before the variable name, the command fails.</span></span>

<span data-ttu-id="a2b6e-137">$Hash の値に空のハッシュテーブルを作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-137">To create an empty hash table in the value of $hash, type:</span></span>

```powershell
$hash = @{}
```

<span data-ttu-id="a2b6e-138">ハッシュテーブルを作成するときに、キーと値を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-138">You can also add keys and values to a hash table when you create it.</span></span> <span data-ttu-id="a2b6e-139">たとえば、次のステートメントでは、3つのキーを持つハッシュテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-139">For example, the following statement creates a hash table with three keys.</span></span>

```powershell
$hash = @{ Number = 1; Shape = "Square"; Color = "Blue"}
```

### <a name="creating-ordered-dictionaries"></a><span data-ttu-id="a2b6e-140">並べ替えられた辞書の作成</span><span class="sxs-lookup"><span data-stu-id="a2b6e-140">Creating Ordered Dictionaries</span></span>

<span data-ttu-id="a2b6e-141">OrderedDictionary 型のオブジェクトを追加することによって、順序付けされたディクショナリを作成できますが、順序付けられたディクショナリを作成する最も簡単な方法は [Ordered] 属性を使用することです。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-141">You can create an ordered dictionary by adding an object of the OrderedDictionary type, but the easiest way to create an ordered dictionary is use the [Ordered] attribute.</span></span>

<span data-ttu-id="a2b6e-142">[Ordered] 属性は、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-142">The [ordered] attribute is introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="a2b6e-143">"@" 記号の直前に属性を配置します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-143">Place the attribute immediately before the "@" symbol.</span></span>

```powershell
$hash = [ordered]@{ Number = 1; Shape = "Square"; Color = "Blue"}
```

<span data-ttu-id="a2b6e-144">順序付けされたディクショナリは、ハッシュテーブルを使用するのと同じ方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-144">You can use ordered dictionaries in the same way that you use hash tables.</span></span>
<span data-ttu-id="a2b6e-145">どちらの種類も、ハッシュテーブルまたはディクショナリ (iDictionary) を受け取るパラメーターの値として使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-145">Either type can be used as the value of parameters that take a hash table or dictionary (iDictionary).</span></span>

<span data-ttu-id="a2b6e-146">[Ordered] 属性を使用してハッシュテーブルを変換またはキャストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-146">You cannot use the [ordered] attribute to convert or cast a hash table.</span></span> <span data-ttu-id="a2b6e-147">順序付けされた属性を変数名の前に配置すると、コマンドは失敗し、次のエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-147">If you place the ordered attribute before the variable name, the command fails with the following error message.</span></span>

```powershell
PS C:\> [ordered]$hash = @{}
At line:1 char:1
+ [ordered]$hash = @{}
+ [!INCLUDE[]()]
The ordered attribute can be specified only on a hash literal node.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordExc
eption
+ FullyQualifiedErrorId : OrderedAttributeOnlyOnHashLiteralNode
```

<span data-ttu-id="a2b6e-148">式を修正するには、[ordered] 属性を移動します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-148">To correct the expression, move the [ordered] attribute.</span></span>

```powershell
PS C:\> $hash = [ordered]@{}
```

<span data-ttu-id="a2b6e-149">順序付けされたディクショナリをハッシュテーブルにキャストできますが、変数をクリアして新しい値を入力しても、順序付けされた属性を回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-149">You can cast an ordered dictionary to a hash table, but you cannot recover the ordered attribute, even if you clear the variable and enter new values.</span></span> <span data-ttu-id="a2b6e-150">順序を再設定するには、変数を削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-150">To re-establish the order, you must remove and recreate the variable.</span></span>

```
PS C:\> [hashtable]$hash = [ordered]@{
>> Number = 1; Shape = "Square"; Color = "Blue"}
PS C:\> $hash

Name                           Value
----                           -----
Color                          Blue
Shape                          Square
Number                         1
```

### <a name="displaying-hash-tables"></a><span data-ttu-id="a2b6e-151">ハッシュテーブルの表示</span><span class="sxs-lookup"><span data-stu-id="a2b6e-151">Displaying Hash Tables</span></span>

<span data-ttu-id="a2b6e-152">変数に保存されているハッシュテーブルを表示するには、変数名を入力します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-152">To display a hash table that is saved in a variable, type the variable name.</span></span>
<span data-ttu-id="a2b6e-153">既定では、ハッシュテーブルは、キーの列が1つ、値が1つのテーブルとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-153">By default, a hash tables is displayed as a table with one column for keys and one for values.</span></span>

```powershell
C:\PS> $hash

Name                           Value
----                           -----
Shape                          Square
Color                          Blue
Number                         1
```

<span data-ttu-id="a2b6e-154">ハッシュテーブルには、キーと値のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-154">Hash tables have Keys and Values properties.</span></span> <span data-ttu-id="a2b6e-155">すべてのキーまたはすべての値を表示するには、ドット表記を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-155">Use dot notation to display all of the keys or all of the values.</span></span>

```powershell
C:\PS> $hash.keys
Number
Shape
Color

C:\PS> $hash.values
1
Square
Blue
```

<span data-ttu-id="a2b6e-156">また、各キー名はハッシュテーブルのプロパティであり、その値はキー名プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-156">Each key name is also a property of the hash table, and its value is the value of the key-name property.</span></span> <span data-ttu-id="a2b6e-157">プロパティ値を表示するには、次の形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-157">Use the following format to display the property values.</span></span>

```powershell
$hashtable.<key>
<value>
```

<span data-ttu-id="a2b6e-158">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-158">For example:</span></span>

```powershell
C:\PS> $hash.Number
1

C:\PS> $hash.Color
Blue
```

<span data-ttu-id="a2b6e-159">キー名がハッシュテーブルの型のいずれかのプロパティ名と競合する場合は、を使用して `PSBase` これらのプロパティにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-159">If the key name collides with one of the property names of the HashTable type, you can use `PSBase` to access those properties.</span></span> <span data-ttu-id="a2b6e-160">たとえば、キー名がで、キーのコレクションを取得する場合は、次の `keys` 構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-160">For example, if the key name is `keys` and you want to return the collection of Keys, use this syntax:</span></span>

```powershell
$hashtable.PSBase.Keys
```

<span data-ttu-id="a2b6e-161">ハッシュテーブルには、ハッシュテーブル内のキーと値のペアの数を示す Count プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-161">Hash tables have a Count property that indicates the number of key-value pairs in the hash table.</span></span>

```powershell
C:\PS> $hash.count
3
```

<span data-ttu-id="a2b6e-162">ハッシュテーブルテーブルは配列ではないため、ハッシュテーブルのインデックスとして整数を使用することはできませんが、ハッシュテーブルにインデックスを作成するには、キー名を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-162">Hash table tables are not arrays, so you cannot use an integer as an index into the hash table, but you can use a key name to index into the hash table.</span></span>
<span data-ttu-id="a2b6e-163">キーが文字列値の場合は、キー名を引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-163">If the key is a string value, enclose the key name in quotation marks.</span></span>

<span data-ttu-id="a2b6e-164">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-164">For example:</span></span>

```powershell
C:\PS> $hash["Number"]
1
```

### <a name="adding-and-removing-keys-and-values"></a><span data-ttu-id="a2b6e-165">キーと値の追加と削除</span><span class="sxs-lookup"><span data-stu-id="a2b6e-165">Adding and Removing Keys and Values</span></span>

<span data-ttu-id="a2b6e-166">ハッシュテーブルにキーと値を追加するには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-166">To add keys and values to a hash table, use the following command format.</span></span>

```powershell
$hash["<key>"] = "<value>"
```

<span data-ttu-id="a2b6e-167">たとえば、"Now" という値を持つ "Time" キーをハッシュテーブルに追加するには、次のステートメント形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-167">For example, to add a "Time" key with a value of "Now" to the hash table, use the following statement format.</span></span>

```powershell
$hash["Time"] = "Now"
```

<span data-ttu-id="a2b6e-168">また、配列の Add メソッドを使用して、キーと値をハッシュテーブルに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-168">You can also add keys and values to a hash table by using the Add method of the System.Collections.Hashtable object.</span></span> <span data-ttu-id="a2b6e-169">Add メソッドには、次の構文があります。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-169">The Add method has the following syntax:</span></span>

```powershell
Add(Key, Value)
```

<span data-ttu-id="a2b6e-170">たとえば、"Now" という値を持つ "Time" キーをハッシュテーブルに追加するには、次のステートメント形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-170">For example, to add a "Time" key with a value of "Now" to the hash table, use the following statement format.</span></span>

```powershell
$hash.Add("Time", "Now")
```

<span data-ttu-id="a2b6e-171">また、加算演算子 (+) を使用してハッシュテーブルを既存のハッシュテーブルに追加することで、ハッシュテーブルにキーと値を追加できます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-171">And, you can add keys and values to a hash table by using the addition operator (+) to add a hash table to an existing hash table.</span></span> <span data-ttu-id="a2b6e-172">たとえば、次のステートメントは、値が "Now" の "Time" キーを $hash 変数のハッシュテーブルに追加します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-172">For example, the following statement adds a "Time" key with a value of "Now" to the hash table in the $hash variable.</span></span>

```powershell
$hash = $hash + @{Time="Now"}
```

<span data-ttu-id="a2b6e-173">変数に格納されている値を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-173">You can also add values that are stored in variables.</span></span>

```powershell
$t = "Today"
$now = (Get-Date)

$hash.Add($t, $now)
```

<span data-ttu-id="a2b6e-174">減算演算子を使用してハッシュテーブルからキーと値のペアを削除することはできませんが、Hashtable オブジェクトの Remove メソッドを使用することはできます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-174">You cannot use a subtraction operator to remove a key/value pair from a hash table, but you can use the Remove method of the Hashtable object.</span></span> <span data-ttu-id="a2b6e-175">Remove メソッドでは、キーが値として取得されます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-175">The Remove method takes the key as its value.</span></span>

<span data-ttu-id="a2b6e-176">Remove メソッドの構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-176">The Remove method has the following syntax:</span></span>

```
Remove(Key)
```

<span data-ttu-id="a2b6e-177">たとえば、$hash 変数の値のハッシュテーブルから Time = Now のキーと値のペアを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-177">For example, to remove the Time=Now key/value pair from the hash table in the value of the $hash variable, type:</span></span>

```powershell
$hash.Remove("Time")
```

<span data-ttu-id="a2b6e-178">PowerShell では、Hashtable オブジェクトのすべてのプロパティとメソッド (Contains、Clear、Clone、CopyTo など) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-178">You can use all of the properties and methods of Hashtable objects in PowerShell, including Contains, Clear, Clone, and CopyTo.</span></span> <span data-ttu-id="a2b6e-179">Hashtable オブジェクトの詳細については [、「system.string](/dotnet/api/system.collections.hashtable)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-179">For more information about Hashtable objects, see [System.Collections.Hashtable](/dotnet/api/system.collections.hashtable).</span></span>

### <a name="object-types-in-hashtables"></a><span data-ttu-id="a2b6e-180">ハッシュテーブルのオブジェクトの種類</span><span class="sxs-lookup"><span data-stu-id="a2b6e-180">Object Types in HashTables</span></span>

<span data-ttu-id="a2b6e-181">ハッシュテーブル内のキーと値は任意の .NET オブジェクト型を持つことができ、1つのハッシュテーブルには複数の型のキーと値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-181">The keys and values in a hash table can have any .NET object type, and a single hash table can have keys and values of multiple types.</span></span>

<span data-ttu-id="a2b6e-182">次のステートメントでは、プロセス名の文字列のハッシュテーブルを作成し、オブジェクトの値を処理して、変数に保存し `$p` ます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-182">The following statement creates a hash table of process name strings and process object values and saves it in the `$p` variable.</span></span>

```powershell
$p = @{"PowerShell" = (Get-Process PowerShell);
"Notepad" = (Get-Process notepad)}
```

<span data-ttu-id="a2b6e-183">でハッシュテーブルを表示し、キー名プロパティを使用して値を表示することができ `$p` ます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-183">You can display the hash table in `$p` and use the key-name properties to display the values.</span></span>

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)

C:\PS> $p.PowerShell

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    441      24    54196      54012   571     5.10   1788 PowerShell

C:\PS> $p.keys | foreach {$p.$_.handles}
441
251
```

<span data-ttu-id="a2b6e-184">ハッシュテーブル内のキーは、任意の .NET 型にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-184">The keys in a hash table can also be any .NET type.</span></span> <span data-ttu-id="a2b6e-185">次のステートメントは、変数のハッシュテーブルにキーと値のペアを追加し `$p` ます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-185">The following statement adds a key/value pair to the hash table in the `$p` variable.</span></span> <span data-ttu-id="a2b6e-186">キーは、WinRM サービスを表すサービスオブジェクトであり、値はサービスの現在の状態です。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-186">The key is a Service object that represents the WinRM service, and the value is the current status of the service.</span></span>

```powershell
C:\PS> $p = $p + @{(Get-Service WinRM) = ((Get-Service WinRM).Status)}
```

<span data-ttu-id="a2b6e-187">新しいキーと値のペアを表示してアクセスするには、ハッシュテーブル内の他のペアに使用するのと同じメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-187">You can display and access the new key/value pair by using the same methods that you use for other pairs in the hash table.</span></span>

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running

C:\PS> $p.keys
PowerShell
Notepad

Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...

C:\PS> $p.keys | foreach {$_.name}
winrm
```

<span data-ttu-id="a2b6e-188">ハッシュテーブル内のキーと値は、Hashtable オブジェクトにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-188">The keys and values in a hash table can also be Hashtable objects.</span></span> <span data-ttu-id="a2b6e-189">次のステートメントでは、キーが文字列である変数のハッシュテーブルにキーと値のペアを追加し、 `$p` 値は、3つのキーと値のペアを持つハッシュテーブルに Hash2 ます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-189">The following statement adds key/value pair to the hash table in the `$p` variable in which the key is a string, Hash2, and the value is a hash table with three key/value pairs.</span></span>

```powershell
C:\PS> $p = $p + @{"Hash2"= @{a=1; b=2; c=3}}
```

<span data-ttu-id="a2b6e-190">同じメソッドを使用して、新しい値を表示したり、アクセスしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-190">You can display and access the new values by using the same methods.</span></span>

```powershell
C:\PS> $p

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running
Hash2                          {a, b, c}

C:\PS> $p.Hash2

Name                           Value
----                           -----
a                              1
b                              2
c                              3

C:\PS> $p.Hash2.b
2
```

### <a name="sorting-keys-and-values"></a><span data-ttu-id="a2b6e-191">キーと値の並べ替え</span><span class="sxs-lookup"><span data-stu-id="a2b6e-191">Sorting Keys and Values</span></span>

<span data-ttu-id="a2b6e-192">ハッシュテーブル内の項目は、本質的に順序付けられていません。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-192">The items in a hash table are intrinsically unordered.</span></span> <span data-ttu-id="a2b6e-193">キーと値のペアは、表示するたびに異なる順序で表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-193">The key/value pairs might appear in a different order each time that you display them.</span></span>

<span data-ttu-id="a2b6e-194">ハッシュテーブルを並べ替えることはできませんが、ハッシュテーブルの GetEnumerator メソッドを使用してキーと値を列挙し、Sort-Object コマンドレットを使用して列挙値を並べ替えて表示することができます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-194">Although you cannot sort a hash table, you can use the GetEnumerator method of hash tables to enumerate the keys and values, and then use the Sort-Object cmdlet to sort the enumerated values for display.</span></span>

<span data-ttu-id="a2b6e-195">たとえば、次のコマンドは、変数内のハッシュテーブル内のキーと値を列挙 `$p` し、キーをアルファベット順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-195">For example, the following commands enumerate the keys and values in the hash table in the `$p` variable and then sort the keys in alphabetical order.</span></span>

```powershell
C:\PS> $p.GetEnumerator() | Sort-Object -Property key

Name                           Value
----                           -----
Notepad                        System.Diagnostics.Process (notepad)
PowerShell                     System.Diagnostics.Process (PowerShell)
System.ServiceProcess.Servi... Running
```

<span data-ttu-id="a2b6e-196">次のコマンドでは、同じ手順を使用して、ハッシュ値を降順で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-196">The following command uses the same procedure to sort the hash values in descending order.</span></span>

```powershell
C:\PS> $p.getenumerator() | Sort-Object -Property Value -Descending

Name                           Value
----                           -----
PowerShell                     System.Diagnostics.Process (PowerShell)
Notepad                        System.Diagnostics.Process (notepad)
System.ServiceProcess.Servi... Running
```

### <a name="creating-objects-from-hash-tables"></a><span data-ttu-id="a2b6e-197">ハッシュテーブルからのオブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="a2b6e-197">Creating Objects from Hash Tables</span></span>

<span data-ttu-id="a2b6e-198">PowerShell 3.0 以降では、プロパティとプロパティ値のハッシュテーブルからオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-198">Beginning in PowerShell 3.0, you can create an object from a hash table of properties and property values.</span></span>

<span data-ttu-id="a2b6e-199">構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-199">The syntax is as follows:</span></span>

```powershell
[<class-name>]@{
  <property-name>=<property-value>
  <property-name>=<property-value>
}
```

<span data-ttu-id="a2b6e-200">このメソッドは、null コンストラクターを持つクラス (つまり、パラメーターを持たないコンストラクター) に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-200">This method works only for classes that have a null constructor, that is, a constructor that has no parameters.</span></span> <span data-ttu-id="a2b6e-201">オブジェクトのプロパティは、パブリックで設定可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-201">The object properties must be public and settable.</span></span>

<span data-ttu-id="a2b6e-202">詳細については、「 [about_Object_Creation](about_Object_Creation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-202">For more information, see [about_Object_Creation](about_Object_Creation.md).</span></span>

### <a name="convertfrom-stringdata"></a><span data-ttu-id="a2b6e-203">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="a2b6e-203">ConvertFrom-StringData</span></span>

<span data-ttu-id="a2b6e-204">`ConvertFrom-StringData`コマンドレットは、文字列またはキーと値のペアのここから文字列をハッシュテーブルに変換します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-204">The `ConvertFrom-StringData` cmdlet converts a string or a here-string of key/value pairs into a hash table.</span></span> <span data-ttu-id="a2b6e-205">スクリプトのデータセクションでコマンドレットを安全に使用できます。また、コマンドレットを使用して、 `ConvertFrom-StringData` `Import-LocalizedData` 現在のユーザーのユーザーインターフェイス (UI) カルチャにユーザーメッセージを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-205">You can use the `ConvertFrom-StringData` cmdlet safely in the Data section of a script, and you can use it with the `Import-LocalizedData` cmdlet to display user messages in the user-interface (UI) culture of the current user.</span></span>

<span data-ttu-id="a2b6e-206">ここでは、ハッシュテーブルの値に引用符が含まれている場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-206">Here-strings are especially useful when the values in the hash table include quotation marks.</span></span> <span data-ttu-id="a2b6e-207">ここで説明する文字列の詳細については、「 [about_Quoting_Rules](about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-207">For more information about here-strings, see [about_Quoting_Rules](about_Quoting_Rules.md).</span></span>

<span data-ttu-id="a2b6e-208">次の例では、前の例でユーザーメッセージのここから文字列を作成する方法と、を使用して `ConvertFrom-StringData` 文字列からハッシュテーブルに変換する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-208">The following example shows how to create a here-string of the user messages in the previous example and how to use `ConvertFrom-StringData` to convert them from a string into a hash table.</span></span>

<span data-ttu-id="a2b6e-209">次のコマンドは、キーと値のペアのここに文字列を作成し、文字列変数に保存し \$ ます。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-209">The following command creates a here-string of the key/value pairs and then saves it in the \$string variable.</span></span>

```powershell
C:\PS> $string = @"
Msg1 = Type "Windows".
Msg2 = She said, "Hello, World."
Msg3 = Enter an alias (or "nickname").
"@
```

<span data-ttu-id="a2b6e-210">このコマンドは、ConvertFrom-StringData コマンドレットを使用して、この文字列をハッシュテーブルに変換します。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-210">This command uses the ConvertFrom-StringData cmdlet to convert the here-string into a hash table.</span></span>

```powershell
C:\PS> ConvertFrom-StringData $string

Name                           Value
----                           -----
Msg3                           Enter an alias (or "nickname").
Msg2                           She said, "Hello, World."
Msg1                           Type "Windows".
```

<span data-ttu-id="a2b6e-211">ここで説明する文字列の詳細については、「 [about_Quoting_Rules](about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2b6e-211">For more information about here-strings, see [about_Quoting_Rules](about_Quoting_Rules.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a2b6e-212">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2b6e-212">SEE ALSO</span></span>

[<span data-ttu-id="a2b6e-213">about_Arrays</span><span class="sxs-lookup"><span data-stu-id="a2b6e-213">about_Arrays</span></span>](about_Arrays.md)

[<span data-ttu-id="a2b6e-214">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="a2b6e-214">about_Object_Creation</span></span>](about_Object_Creation.md)

[<span data-ttu-id="a2b6e-215">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="a2b6e-215">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)

[<span data-ttu-id="a2b6e-216">about_Script_Internationalization</span><span class="sxs-lookup"><span data-stu-id="a2b6e-216">about_Script_Internationalization</span></span>](about_Script_Internationalization.md)

[<span data-ttu-id="a2b6e-217">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="a2b6e-217">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)

[<span data-ttu-id="a2b6e-218">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="a2b6e-218">Import-LocalizedData</span></span>](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)

[<span data-ttu-id="a2b6e-219">System.Collections.Hashtable</span><span class="sxs-lookup"><span data-stu-id="a2b6e-219">System.Collections.Hashtable</span></span>](/dotnet/api/system.collections.hashtable)
