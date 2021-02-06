---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-member?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Member
ms.openlocfilehash: 4e9e5ec6d188bec0b4032151fb92e6995d8efbb8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601795"
---
# <span data-ttu-id="acd2b-102">Add-Member</span><span class="sxs-lookup"><span data-stu-id="acd2b-102">Add-Member</span></span>

## <span data-ttu-id="acd2b-103">概要</span><span class="sxs-lookup"><span data-stu-id="acd2b-103">SYNOPSIS</span></span>
<span data-ttu-id="acd2b-104">PowerShell オブジェクトのインスタンスにカスタムプロパティとメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-104">Adds custom properties and methods to an instance of a PowerShell object.</span></span>

## <span data-ttu-id="acd2b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="acd2b-105">SYNTAX</span></span>

### <span data-ttu-id="acd2b-106">TypeNameSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="acd2b-106">TypeNameSet (Default)</span></span>

```
Add-Member -InputObject <PSObject> -TypeName <String> [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="acd2b-107">注 Propertymultiメンバセット</span><span class="sxs-lookup"><span data-stu-id="acd2b-107">NotePropertyMultiMemberSet</span></span>

```
Add-Member -InputObject <PSObject> [-TypeName <String>] [-Force] [-PassThru]
 [-NotePropertyMembers] <IDictionary> [<CommonParameters>]
```

### <span data-ttu-id="acd2b-108">NotePropertySingleMemberSet</span><span class="sxs-lookup"><span data-stu-id="acd2b-108">NotePropertySingleMemberSet</span></span>

```
Add-Member -InputObject <PSObject> [-TypeName <String>] [-Force] [-PassThru] [-NotePropertyName] <String>
 [-NotePropertyValue] <Object> [<CommonParameters>]
```

### <span data-ttu-id="acd2b-109">セット</span><span class="sxs-lookup"><span data-stu-id="acd2b-109">MemberSet</span></span>

```
Add-Member -InputObject <PSObject> [-MemberType] <PSMemberTypes> [-Name] <String> [[-Value] <Object>]
 [[-SecondValue] <Object>] [-TypeName <String>] [-Force] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="acd2b-110">Description</span><span class="sxs-lookup"><span data-stu-id="acd2b-110">DESCRIPTION</span></span>

<span data-ttu-id="acd2b-111">`Add-Member`コマンドレットを使用すると、PowerShell オブジェクトのインスタンスにメンバー (プロパティとメソッド) を追加できます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-111">The `Add-Member` cmdlet lets you add members (properties and methods) to an instance of a PowerShell object.</span></span> <span data-ttu-id="acd2b-112">たとえば、オブジェクトの説明が含まれている、またはオブジェクトを変更するスクリプトを実行する **Scriptmethod** メンバーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-112">For instance, you can add a NoteProperty member that contains a description of the object or a **ScriptMethod** member that runs a script to change the object.</span></span>

<span data-ttu-id="acd2b-113">を使用するに `Add-Member` は、オブジェクトをにパイプ処理するか、 `Add-Member` **InputObject** パラメーターを使用してオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-113">To use `Add-Member`, pipe the object to `Add-Member`, or use the **InputObject** parameter to specify the object.</span></span>

<span data-ttu-id="acd2b-114">**MemberType** パラメーターは、追加するメンバーの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-114">The **MemberType** parameter indicates the type of member that you want to add.</span></span> <span data-ttu-id="acd2b-115">**Name** パラメーターを指定すると、新しいメンバーに名前が割り当てられ、 **value** パラメーターによってメンバーの値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-115">The **Name** parameter assigns a name to the new member, and the **Value** parameter sets the value of the member.</span></span>

<span data-ttu-id="acd2b-116">追加するプロパティとメソッドは、指定したオブジェクトの特定のインスタンスにのみ追加されます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-116">The properties and methods that you add are added only to the particular instance of the object that you specify.</span></span> <span data-ttu-id="acd2b-117">`Add-Member` では、オブジェクトの種類は変更されません。</span><span class="sxs-lookup"><span data-stu-id="acd2b-117">`Add-Member` does not change the object type.</span></span> <span data-ttu-id="acd2b-118">新しいオブジェクトの種類を作成するには、コマンドレットを使用し `Add-Type` ます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-118">To create a new object type, use the `Add-Type` cmdlet.</span></span>

<span data-ttu-id="acd2b-119">また、コマンドレットを使用して、 `Export-Clixml` 追加のメンバーを含むオブジェクトのインスタンスをファイルに保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-119">You can also use the `Export-Clixml` cmdlet to save the instance of the object, including the additional members, in a file.</span></span> <span data-ttu-id="acd2b-120">次に、コマンドレットを使用して、エクスポートされた `Import-Clixml` ファイルに格納されている情報からオブジェクトのインスタンスを再作成します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-120">Then you can use the `Import-Clixml` cmdlet to re-create the instance of the object from the information that is stored in the exported file.</span></span>

<span data-ttu-id="acd2b-121">Windows PowerShell 3.0 以降で `Add-Member` は、オブジェクトへのノートプロパティの追加を容易にする新機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="acd2b-121">Beginning in Windows PowerShell 3.0, `Add-Member` has new features that make it easier to add note properties to objects.</span></span>
<span data-ttu-id="acd2b-122">**NotePropertyName** パラメーターと **NotePropertyValue** パラメーターを使用してノート プロパティを定義することも、ノート プロパティの名前と値のハッシュ テーブルを受け取る **NotePropertyMembers** パラメーターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-122">You can use the **NotePropertyName** and **NotePropertyValue** parameters to define a note property or use the **NotePropertyMembers** parameter, which takes a hash table of note property names and values.</span></span>

<span data-ttu-id="acd2b-123">また、Windows PowerShell 3.0 以降では、出力オブジェクトを生成する **PassThru** パラメーターを使用する必要性が減っています。</span><span class="sxs-lookup"><span data-stu-id="acd2b-123">Also, beginning in Windows PowerShell 3.0, the **PassThru** parameter, which generates an output object, is needed less frequently.</span></span> <span data-ttu-id="acd2b-124">`Add-Member` では、新しいメンバーをさらに多くの型の入力オブジェクトに直接追加します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-124">`Add-Member` now adds the new members directly to the input object of more types.</span></span> <span data-ttu-id="acd2b-125">詳細については、**PassThru** パラメーターの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acd2b-125">For more information, see the **PassThru** parameter description.</span></span>

## <span data-ttu-id="acd2b-126">例</span><span class="sxs-lookup"><span data-stu-id="acd2b-126">EXAMPLES</span></span>

### <span data-ttu-id="acd2b-127">例 1: PSObject に note プロパティを追加する</span><span class="sxs-lookup"><span data-stu-id="acd2b-127">Example 1: Add a note property to a PSObject</span></span>

<span data-ttu-id="acd2b-128">次の例では、ファイルを表す **FileInfo** オブジェクトに "Done" という値を持つ **Status** note プロパティを追加し `Test.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-128">The following example adds a **Status** note property with a value of "Done" to the **FileInfo** object that represents the `Test.txt` file.</span></span>

<span data-ttu-id="acd2b-129">最初のコマンドは、 `Get-ChildItem` コマンドレットを使用して、ファイルを表す **FileInfo** オブジェクトを取得し `Test.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-129">The first command uses the `Get-ChildItem` cmdlet to get a **FileInfo** object representing the `Test.txt` file.</span></span> <span data-ttu-id="acd2b-130">変数に保存 `$a` します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-130">It saves it in the `$a` variable.</span></span>

<span data-ttu-id="acd2b-131">2番目のコマンドは、のオブジェクトに note プロパティを追加し `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-131">The second command adds the note property to the object in `$a`.</span></span>

<span data-ttu-id="acd2b-132">3番目のコマンドは、ドット表記を使用して、内のオブジェクトの **Status** プロパティの値を取得し `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-132">The third command uses dot notation to get the value of the **Status** property of the object in `$a`.</span></span> <span data-ttu-id="acd2b-133">出力に示されているように、値は "Done" です。</span><span class="sxs-lookup"><span data-stu-id="acd2b-133">As the output shows, the value is "Done".</span></span>

```powershell
$A = Get-ChildItem c:\ps-test\test.txt
$A | Add-Member -NotePropertyName Status -NotePropertyValue Done
$A.Status
```

```Output
Done
```

### <span data-ttu-id="acd2b-134">例 2: PSObject にエイリアスプロパティを追加する</span><span class="sxs-lookup"><span data-stu-id="acd2b-134">Example 2: Add an alias property to a PSObject</span></span>

<span data-ttu-id="acd2b-135">次の例では、ファイルを表すオブジェクトに **Size** エイリアスプロパティを追加し `Test.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-135">The following example adds a **Size** alias property to the object that represents the `Test.txt` file.</span></span> <span data-ttu-id="acd2b-136">新しいプロパティは、 **Length** プロパティのエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="acd2b-136">The new property is an alias for the **Length** property.</span></span>

<span data-ttu-id="acd2b-137">最初のコマンドは、 `Get-ChildItem` コマンドレットを使用して、 `Test.txt` **FileInfo** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-137">The first command uses the `Get-ChildItem` cmdlet to get the `Test.txt` **FileInfo** object.</span></span>

<span data-ttu-id="acd2b-138">2番目のコマンドは、 **Size** エイリアスプロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-138">The second command adds the **Size** alias property.</span></span>
<span data-ttu-id="acd2b-139">3番目のコマンドは、ドット表記を使用して、新しい **Size** プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-139">The third command uses dot notation to get the value of the new **Size** property.</span></span>

```powershell
$A = Get-ChildItem C:\Temp\test.txt
$A | Add-Member -MemberType AliasProperty -Name Size -Value Length
$A.Size
```

```Output
2394
```

### <span data-ttu-id="acd2b-140">例 3: 文字列に StringUse note プロパティを追加する</span><span class="sxs-lookup"><span data-stu-id="acd2b-140">Example 3: Add a StringUse note property to a string</span></span>

<span data-ttu-id="acd2b-141">この例では、 **Stringuse** note プロパティを文字列に追加します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-141">This example adds the **StringUse** note property to a string.</span></span>
<span data-ttu-id="acd2b-142">`Add-Member`は、**文字列** 入力オブジェクトに型を追加できないため、 **PassThru** パラメーターを指定して出力オブジェクトを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-142">Because `Add-Member` cannot add types to **String** input objects, you can specify the **PassThru** parameter to generate an output object.</span></span> <span data-ttu-id="acd2b-143">例の最後のコマンドは、新しいプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-143">The last command in the example displays the new property.</span></span>

<span data-ttu-id="acd2b-144">この例では、 **注 Propertymembers** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-144">This example uses the **NotePropertyMembers** parameter.</span></span> <span data-ttu-id="acd2b-145">**NotePropertyMembers** パラメーターの値はハッシュ テーブルです。</span><span class="sxs-lookup"><span data-stu-id="acd2b-145">The value of the **NotePropertyMembers** parameter is a hash table.</span></span> <span data-ttu-id="acd2b-146">キーはノートプロパティの名前である **Stringuse** で、値はノートプロパティの値である **Display** です。</span><span class="sxs-lookup"><span data-stu-id="acd2b-146">The key is the note property name, **StringUse**, and the value is the note property value, **Display**.</span></span>

```powershell
$A = "A string"
$A = $A | Add-Member -NotePropertyMembers @{StringUse="Display"} -PassThru
$A.StringUse
```

```Output
Display
```

### <span data-ttu-id="acd2b-147">例 4: FileInfo オブジェクトにスクリプトメソッドを追加する</span><span class="sxs-lookup"><span data-stu-id="acd2b-147">Example 4: Add a script method to a FileInfo object</span></span>

<span data-ttu-id="acd2b-148">この例では、ファイルサイズを最も近いメガバイトに計算する **FileInfo** オブジェクトに **sizeinmb** スクリプトメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-148">This example adds the **SizeInMB** script method to a **FileInfo** object which calculates the file size to the nearest MegaByte.</span></span> <span data-ttu-id="acd2b-149">2番目のコマンドは、型の **round** static メソッドを使用して、 `[math]` ファイルサイズを2番目の小数点以下桁数に丸める ScriptBlock を作成します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-149">The second command creates a **ScriptBlock** that uses the **Round** static method from the `[math]` type to round the file size to the second decimal place.</span></span>

<span data-ttu-id="acd2b-150">**値** パラメーターは、現在の `$This` オブジェクトを表す自動変数も使用します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-150">The **Value** parameter also uses the `$This` automatic variable, which represents the current object.</span></span> <span data-ttu-id="acd2b-151">`$This`変数は、新しいプロパティとメソッドを定義するスクリプトブロックでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="acd2b-151">The `$This` variable is valid only in script blocks that define new properties and methods.</span></span>

<span data-ttu-id="acd2b-152">最後のコマンドは、ドット表記を使用して、変数内のオブジェクトに対して新しい **Sizeinmb** スクリプトメソッドを呼び出し `$A` ます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-152">The last command uses dot notation to call the new **SizeInMB** script method on the object in the `$A` variable.</span></span>

```powershell
$A = Get-ChildItem C:\Temp\test.txt
$S = {[math]::Round(($this.Length / 1MB), 2)}
$A | Add-Member -MemberType ScriptMethod -Name "SizeInMB" -Value $S
$A.SizeInMB()
```

```Output
0.43
```

### <span data-ttu-id="acd2b-153">例 5: オブジェクトのすべてのプロパティを別のオブジェクトにコピーする</span><span class="sxs-lookup"><span data-stu-id="acd2b-153">Example 5: Copy all properties of an object to another</span></span>

<span data-ttu-id="acd2b-154">この関数は、1 つのオブジェクトのすべてのプロパティを別のオブジェクトにコピーします。</span><span class="sxs-lookup"><span data-stu-id="acd2b-154">This function copies all of the properties of one object to another object.</span></span>

<span data-ttu-id="acd2b-155">このループでは、 `foreach` コマンドレットを使用して `Get-Member` 、 **From** オブジェクトの各プロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-155">The `foreach` loop uses the `Get-Member` cmdlet to get each of the properties of the **From** object.</span></span> <span data-ttu-id="acd2b-156">ループ内のコマンド `foreach` は、各プロパティの系列で実行されます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-156">The commands within the `foreach` loop are performed in series on each of the properties.</span></span>

<span data-ttu-id="acd2b-157">この `Add-Member` コマンドは、 **From** オブジェクトのプロパティを、 **lastproperty** として **to** オブジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-157">The `Add-Member` command adds the property of the **From** object to the **To** object as a **NoteProperty**.</span></span> <span data-ttu-id="acd2b-158">値は、 **値** パラメーターを使用してコピーされます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-158">The value is copied using the **Value** parameter.</span></span> <span data-ttu-id="acd2b-159">**Force** パラメーターを使用して、同じメンバー名を持つメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-159">It uses the **Force** parameter to add members with the same member name.</span></span>

```powershell
function Copy-Property ($From, $To)
{
    $properties = Get-Member -InputObject $From -MemberType Property
    foreach ($p in $properties)
    {
        $To | Add-Member -MemberType NoteProperty -Name $p.Name -Value $From.$($p.Name) -Force
    }
}
```

### <span data-ttu-id="acd2b-160">例 6: カスタムオブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="acd2b-160">Example 6: Create a custom object</span></span>

<span data-ttu-id="acd2b-161">この例では、 **Asset** カスタムオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-161">This example creates an **Asset** custom object.</span></span>

<span data-ttu-id="acd2b-162">`New-Object`コマンドレットでは、 **PSObject** を作成します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-162">The `New-Object` cmdlet creates a **PSObject**.</span></span> <span data-ttu-id="acd2b-163">この例では、 **PSObject** を変数に保存し `$Asset` ます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-163">The example saves the **PSObject** in the `$Asset` variable.</span></span>

<span data-ttu-id="acd2b-164">2番目のコマンドは、型アクセラレータを使用して、 `[ordered]` 名前と値の順序付けされた辞書を作成します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-164">The second command uses the `[ordered]` type accelerator to create an ordered dictionary of names and values.</span></span> <span data-ttu-id="acd2b-165">このコマンドは、変数に結果を保存し `$D` ます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-165">The command saves the result in the `$D` variable.</span></span>

<span data-ttu-id="acd2b-166">3番目のコマンドは、コマンドレットの "dictionary **Propertymembers** " パラメーターを使用して、 `Add-Member` 変数内の辞書 `$D` を **PSObject** に追加します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-166">The third command uses the **NotePropertyMembers** parameter of the `Add-Member` cmdlet to add the dictionary in the `$D` variable to the **PSObject**.</span></span>
<span data-ttu-id="acd2b-167">**TypeName** プロパティは、新しい名前である **Asset** を **PSObject** に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-167">The **TypeName** property assigns a new name, **Asset**, to the **PSObject**.</span></span>

<span data-ttu-id="acd2b-168">最後のコマンドは、新しい **Asset** オブジェクトをコマンドレットにパイプし `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-168">The last command pipes the new **Asset** object to the `Get-Member` cmdlet.</span></span> <span data-ttu-id="acd2b-169">出力には、オブジェクトに **Asset** という型名と、順序付けされた辞書で定義した note プロパティがあることが示されています。</span><span class="sxs-lookup"><span data-stu-id="acd2b-169">The output shows that the object has a type name of **Asset** and the note properties that we defined in the ordered dictionary.</span></span>

```powershell
$Asset = New-Object -TypeName PSObject
$d = [ordered]@{Name="Server30";System="Server Core";PSVersion="4.0"}
$Asset | Add-Member -NotePropertyMembers $d -TypeName Asset
$Asset | Get-Member
```

```Output
   TypeName: Asset

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Name        NoteProperty System.String Name=Server30
PSVersion   NoteProperty System.String PSVersion=4.0
System      NoteProperty System.String System=Server Core
```

## <span data-ttu-id="acd2b-170">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="acd2b-170">PARAMETERS</span></span>

### <span data-ttu-id="acd2b-171">-Force</span><span class="sxs-lookup"><span data-stu-id="acd2b-171">-Force</span></span>

<span data-ttu-id="acd2b-172">オブジェクトに同じ名前のカスタムメンバーがある場合でも、このコマンドレットによって新しいメンバーが追加されることを示します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-172">Indicates that this cmdlet adds a new member even the object has a custom member with the same name.</span></span>
<span data-ttu-id="acd2b-173">**Force** パラメーターを使用して、型の標準メンバーを置き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="acd2b-173">You cannot use the **Force** parameter to replace a standard member of a type.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: MemberSet, NotePropertySingleMemberSet, NotePropertyMultiMemberSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="acd2b-174">-InputObject</span><span class="sxs-lookup"><span data-stu-id="acd2b-174">-InputObject</span></span>

<span data-ttu-id="acd2b-175">新しいメンバーを追加するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-175">Specifies the object to which the new member is added.</span></span>
<span data-ttu-id="acd2b-176">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-176">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="acd2b-177">-MemberType</span><span class="sxs-lookup"><span data-stu-id="acd2b-177">-MemberType</span></span>

<span data-ttu-id="acd2b-178">追加するメンバーの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-178">Specifies the type of the member to add.</span></span>
<span data-ttu-id="acd2b-179">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="acd2b-179">This parameter is required.</span></span>
<span data-ttu-id="acd2b-180">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="acd2b-180">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="acd2b-181">NoteProperty</span><span class="sxs-lookup"><span data-stu-id="acd2b-181">NoteProperty</span></span>
- <span data-ttu-id="acd2b-182">AliasProperty</span><span class="sxs-lookup"><span data-stu-id="acd2b-182">AliasProperty</span></span>
- <span data-ttu-id="acd2b-183">ScriptProperty</span><span class="sxs-lookup"><span data-stu-id="acd2b-183">ScriptProperty</span></span>
- <span data-ttu-id="acd2b-184">CodeProperty</span><span class="sxs-lookup"><span data-stu-id="acd2b-184">CodeProperty</span></span>
- <span data-ttu-id="acd2b-185">ScriptMethod</span><span class="sxs-lookup"><span data-stu-id="acd2b-185">ScriptMethod</span></span>
- <span data-ttu-id="acd2b-186">CodeMethod</span><span class="sxs-lookup"><span data-stu-id="acd2b-186">CodeMethod</span></span>

<span data-ttu-id="acd2b-187">これらの値の詳細については、「 [PSMemberTypes Enumeration](/dotnet/api/system.management.automation.psmembertypes) In THE PowerShell SDK」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acd2b-187">For information about these values, see [PSMemberTypes Enumeration](/dotnet/api/system.management.automation.psmembertypes) in the PowerShell SDK.</span></span>

<span data-ttu-id="acd2b-188">すべてのオブジェクトにすべての型のメンバーがあるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="acd2b-188">Not all objects have every type of member.</span></span>
<span data-ttu-id="acd2b-189">オブジェクトに含まれていないメンバーの種類を指定すると、PowerShell はエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-189">If you specify a member type that the object does not have, PowerShell returns an error.</span></span>

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: MemberSet
Aliases: Type
Accepted values: AliasProperty, CodeProperty, Property, NoteProperty, ScriptProperty, Properties, PropertySet, Method, CodeMethod, ScriptMethod, Methods, ParameterizedProperty, MemberSet, Event, Dynamic, All

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="acd2b-190">-Name</span><span class="sxs-lookup"><span data-stu-id="acd2b-190">-Name</span></span>

<span data-ttu-id="acd2b-191">このコマンドレットによって追加されるメンバーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-191">Specifies the name of the member that this cmdlet adds.</span></span>

```yaml
Type: System.String
Parameter Sets: MemberSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="acd2b-192">-注 Propertymembers</span><span class="sxs-lookup"><span data-stu-id="acd2b-192">-NotePropertyMembers</span></span>

<span data-ttu-id="acd2b-193">ノート プロパティの名前と値のハッシュ テーブルまたは順序付けされた辞書を指定します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-193">Specifies a hash table or ordered dictionary of note property names and values.</span></span>
<span data-ttu-id="acd2b-194">ノート プロパティの名前をキーとして持ち、ノート プロパティの値を値として持つハッシュ テーブルまたは辞書を指定します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-194">Type a hash table or dictionary in which the keys are note property names and the values are note property values.</span></span>

<span data-ttu-id="acd2b-195">PowerShell のハッシュテーブルと順序付けされたディクショナリの詳細については、「 [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acd2b-195">For more information about hash tables and ordered dictionaries in PowerShell, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

<span data-ttu-id="acd2b-196">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="acd2b-196">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: NotePropertyMultiMemberSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="acd2b-197">-注 Propertyname</span><span class="sxs-lookup"><span data-stu-id="acd2b-197">-NotePropertyName</span></span>

<span data-ttu-id="acd2b-198">ノートプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-198">Specifies the note property name.</span></span>

<span data-ttu-id="acd2b-199">このパラメーターは、**NotePropertyValue** パラメーターと一緒に使用します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-199">Use this parameter with the **NotePropertyValue** parameter.</span></span>
<span data-ttu-id="acd2b-200">このパラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="acd2b-200">This parameter is optional.</span></span>

<span data-ttu-id="acd2b-201">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="acd2b-201">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: NotePropertySingleMemberSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="acd2b-202">-注 Propertyvalue</span><span class="sxs-lookup"><span data-stu-id="acd2b-202">-NotePropertyValue</span></span>

<span data-ttu-id="acd2b-203">メモのプロパティ値を指定します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-203">Specifies the note property value.</span></span>

<span data-ttu-id="acd2b-204">このパラメーターは、 **メモの propertyname** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-204">Use this parameter with the **NotePropertyName** parameter.</span></span>
<span data-ttu-id="acd2b-205">このパラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="acd2b-205">This parameter is optional.</span></span>

<span data-ttu-id="acd2b-206">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="acd2b-206">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: NotePropertySingleMemberSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="acd2b-207">-PassThru</span><span class="sxs-lookup"><span data-stu-id="acd2b-207">-PassThru</span></span>

<span data-ttu-id="acd2b-208">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-208">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="acd2b-209">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="acd2b-209">By default, this cmdlet does not generate any output.</span></span>

<span data-ttu-id="acd2b-210">ほとんどのオブジェクトでは、 `Add-Member` 入力オブジェクトに新しいメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-210">For most objects, `Add-Member` adds the new members to the input object.</span></span>
<span data-ttu-id="acd2b-211">ただし、入力オブジェクトが文字列の場合、は `Add-Member` そのメンバーを入力オブジェクトに追加できません。</span><span class="sxs-lookup"><span data-stu-id="acd2b-211">However, when the input object is a string, `Add-Member` cannot add the member to the input object.</span></span>
<span data-ttu-id="acd2b-212">これらのオブジェクトに対しては、**PassThru** パラメーターを使用して、出力オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-212">For these objects, use the **PassThru** parameter to create an output object.</span></span>

<span data-ttu-id="acd2b-213">Windows PowerShell 2.0 では、オブジェクトでは `Add-Member` なく、オブジェクトの **PSObject** ラッパーにのみメンバーが追加されました。</span><span class="sxs-lookup"><span data-stu-id="acd2b-213">In Windows PowerShell 2.0, `Add-Member` added members only to the **PSObject** wrapper of objects, not to the object.</span></span>
<span data-ttu-id="acd2b-214">**PassThru** パラメーターを使用して、 **PSObject** ラッパーを持つ任意のオブジェクトの出力オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-214">Use the **PassThru** parameter to create an output object for any object that has a **PSObject** wrapper.</span></span>

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

### <span data-ttu-id="acd2b-215">-SecondValue</span><span class="sxs-lookup"><span data-stu-id="acd2b-215">-SecondValue</span></span>

<span data-ttu-id="acd2b-216">**AliasProperty**、**ScriptProperty**、**CodeProperty**、または **CodeMethod** の各メンバーに関する省略可能な追加情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-216">Specifies optional additional information about **AliasProperty**, **ScriptProperty**, **CodeProperty**, or **CodeMethod** members.</span></span>

<span data-ttu-id="acd2b-217">**エイリアスプロパティ** を追加するときに使用する場合、このパラメーターはデータ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="acd2b-217">If used when adding an **AliasProperty**, this parameter must be a data type.</span></span>
<span data-ttu-id="acd2b-218">指定されたデータ型への変換は、 **エイリアスプロパティ** の値に追加されます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-218">A conversion to the specified data type is added to the value of the **AliasProperty**.</span></span>

<span data-ttu-id="acd2b-219">たとえば、文字列プロパティの代替名を提供する **エイリアスプロパティ** を追加する場合、System.string の **SecondValue** パラメーターを指定して、対応する **エイリアスプロパティ** を使用してアクセスしたときに、その文字列プロパティの値を整数に変換する必要があることを示すことも **できます。**</span><span class="sxs-lookup"><span data-stu-id="acd2b-219">For example, if you add an **AliasProperty** that provides an alternate name for a string property, you can also specify a **SecondValue** parameter of **System.Int32** to indicate that the value of that string property should be converted to an integer when accessed by using the corresponding **AliasProperty**.</span></span>

<span data-ttu-id="acd2b-220">**Scriptproperty** メンバーを追加するときに、 **SecondValue** パラメーターを使用して追加の **ScriptBlock** を指定できます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-220">You can use the **SecondValue** parameter to specify an additional **ScriptBlock** when adding a **ScriptProperty** member.</span></span> <span data-ttu-id="acd2b-221">**Value** パラメーターで指定された最初の **ScriptBlock** は、変数の値を取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-221">The first **ScriptBlock**, specified in the **Value** parameter, is used to get the value of a variable.</span></span> <span data-ttu-id="acd2b-222">**SecondValue** パラメーターで指定した2つ目の **ScriptBlock** は、変数の値を設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-222">The second **ScriptBlock**, specified in the **SecondValue** parameter, is used to set the value of a variable.</span></span>

```yaml
Type: System.Object
Parameter Sets: MemberSet
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="acd2b-223">-Value</span><span class="sxs-lookup"><span data-stu-id="acd2b-223">-Value</span></span>

<span data-ttu-id="acd2b-224">追加されたメンバーの初期値を指定します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-224">Specifies the initial value of the added member.</span></span>
<span data-ttu-id="acd2b-225">**エイリアスプロパティ**、 **codeproperty**、 **Scriptproperty** 、または **codeproperty** メンバーを追加する場合は、 **SecondValue** パラメーターを使用して、省略可能な追加情報を指定できます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-225">If you add an **AliasProperty**, **CodeProperty**, **ScriptProperty** or **CodeMethod** member, you can supply optional, additional information by using the **SecondValue** parameter.</span></span>

```yaml
Type: System.Object
Parameter Sets: MemberSet
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="acd2b-226">-TypeName</span><span class="sxs-lookup"><span data-stu-id="acd2b-226">-TypeName</span></span>

<span data-ttu-id="acd2b-227">型の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-227">Specifies a name for the type.</span></span>

<span data-ttu-id="acd2b-228">型が **System** 名前空間のクラス、または型アクセラレータを持つ型である場合は、型の短い名前を入力できます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-228">When the type is a class in the **System** namespace or a type that has a type accelerator, you can enter the short name of the type.</span></span> <span data-ttu-id="acd2b-229">それ以外の場合は、完全な型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="acd2b-229">Otherwise, the full type name is required.</span></span>
<span data-ttu-id="acd2b-230">このパラメーターは、 **InputObject** が **PSObject** の場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="acd2b-230">This parameter is effective only when the **InputObject** is a **PSObject**.</span></span>

<span data-ttu-id="acd2b-231">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="acd2b-231">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: TypeNameSet, NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet
Aliases:

Required: True (TypeNameSet), False (NotePropertyMultiMemberSet, NotePropertySingleMemberSet, MemberSet)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="acd2b-232">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="acd2b-232">CommonParameters</span></span>

<span data-ttu-id="acd2b-233">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="acd2b-233">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="acd2b-234">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acd2b-234">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="acd2b-235">入力</span><span class="sxs-lookup"><span data-stu-id="acd2b-235">INPUTS</span></span>

### <span data-ttu-id="acd2b-236">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="acd2b-236">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="acd2b-237">パイプを使用して、任意のオブジェクトの種類をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-237">You can pipe any object type to this cmdlet.</span></span>

## <span data-ttu-id="acd2b-238">出力</span><span class="sxs-lookup"><span data-stu-id="acd2b-238">OUTPUTS</span></span>

### <span data-ttu-id="acd2b-239">None または System.object</span><span class="sxs-lookup"><span data-stu-id="acd2b-239">None or System.Object</span></span>

<span data-ttu-id="acd2b-240">**PassThru** パラメーターを使用すると、このコマンドレットは、新しく拡張されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-240">When you use the **PassThru** parameter, this cmdlet returns the newly-extended object.</span></span>
<span data-ttu-id="acd2b-241">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="acd2b-241">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="acd2b-242">注</span><span class="sxs-lookup"><span data-stu-id="acd2b-242">NOTES</span></span>

<span data-ttu-id="acd2b-243">メンバーを追加できるのは、 **PSObject** オブジェクトだけです。</span><span class="sxs-lookup"><span data-stu-id="acd2b-243">You can add members only to **PSObject** objects.</span></span> <span data-ttu-id="acd2b-244">オブジェクトが **PSObject** オブジェクトであるかどうかを判断するには、演算子を使用し `-is` ます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-244">To determine whether an object is a **PSObject** object, use the `-is` operator.</span></span>

<span data-ttu-id="acd2b-245">たとえば、変数に格納されているオブジェクトをテストするには `$obj` 、「」と入力 `$obj -is [PSObject]` します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-245">For instance, to test an object stored in the `$obj` variable, type `$obj -is [PSObject]`.</span></span>

<span data-ttu-id="acd2b-246">**MemberType**、 **Name**、 **Value**、 **SecondValue** の各パラメーターの名前は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="acd2b-246">The names of the **MemberType**, **Name**, **Value**, and **SecondValue** parameters are optional.</span></span>
<span data-ttu-id="acd2b-247">パラメーター名を省略した場合、名前のないパラメーター値は、 **MemberType**、 **Name**、 **Value**、 **SecondValue** の順に表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="acd2b-247">If you omit the parameter names, the unnamed parameter values must appear in this order: **MemberType**, **Name**, **Value**, and **SecondValue**.</span></span>

<span data-ttu-id="acd2b-248">パラメーター名を指定する場合は、パラメーターの順序に決まりはありません。</span><span class="sxs-lookup"><span data-stu-id="acd2b-248">If you include the parameter names, the parameters can appear in any order.</span></span>

<span data-ttu-id="acd2b-249">`$this`新しいプロパティとメソッドの値を定義するスクリプトブロックでは、自動変数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="acd2b-249">You can use the `$this` automatic variable in script blocks that define the values of new properties and methods.</span></span>
<span data-ttu-id="acd2b-250">変数は、 `$this` プロパティとメソッドを追加するオブジェクトのインスタンスを参照します。</span><span class="sxs-lookup"><span data-stu-id="acd2b-250">The `$this` variable refers to the instance of the object to which the properties and methods are being added.</span></span> <span data-ttu-id="acd2b-251">変数の詳細については `$this` 、「 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acd2b-251">For more information about the `$this` variable, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

## <span data-ttu-id="acd2b-252">関連リンク</span><span class="sxs-lookup"><span data-stu-id="acd2b-252">RELATED LINKS</span></span>

[<span data-ttu-id="acd2b-253">Export-Clixml</span><span class="sxs-lookup"><span data-stu-id="acd2b-253">Export-Clixml</span></span>](Export-Clixml.md)

[<span data-ttu-id="acd2b-254">Get-Member</span><span class="sxs-lookup"><span data-stu-id="acd2b-254">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="acd2b-255">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="acd2b-255">Import-Clixml</span></span>](Import-Clixml.md)

[<span data-ttu-id="acd2b-256">New-Object</span><span class="sxs-lookup"><span data-stu-id="acd2b-256">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="acd2b-257">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="acd2b-257">about_Automatic_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)

