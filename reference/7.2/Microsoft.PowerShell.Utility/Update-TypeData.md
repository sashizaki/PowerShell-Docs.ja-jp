---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/update-typedata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-TypeData
ms.openlocfilehash: 1314d388bff5a46bcf335f3da7908a65233aa46e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602404"
---
# <span data-ttu-id="6c46e-102">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="6c46e-102">Update-TypeData</span></span>

## <span data-ttu-id="6c46e-103">構文</span><span class="sxs-lookup"><span data-stu-id="6c46e-103">Synopsis</span></span>
<span data-ttu-id="6c46e-104">セッションで、拡張型データを更新します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-104">Updates the extended type data in the session.</span></span>

## <span data-ttu-id="6c46e-105">構文</span><span class="sxs-lookup"><span data-stu-id="6c46e-105">Syntax</span></span>

### <span data-ttu-id="6c46e-106">の場合 (既定)</span><span class="sxs-lookup"><span data-stu-id="6c46e-106">FileSet (Default)</span></span>

```
Update-TypeData [[-AppendPath] <String[]>] [-PrependPath <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="6c46e-107">DynamicTypeSet</span><span class="sxs-lookup"><span data-stu-id="6c46e-107">DynamicTypeSet</span></span>

```
Update-TypeData [-MemberType <PSMemberTypes>] [-MemberName <String>] [-Value <Object>]
 [-SecondValue <Object>] [-TypeConverter <Type>] [-TypeAdapter <Type>]
 [-SerializationMethod <String>] [-TargetTypeForDeserialization <Type>]
 [-SerializationDepth <Int32>] [-DefaultDisplayProperty <String>]
 [-InheritPropertySerializationSet <Nullable`1>] [-StringSerializationSource <String>]
 [-DefaultDisplayPropertySet <String[]>] [-DefaultKeyPropertySet <String[]>]
 [-PropertySerializationSet <String[]>] -TypeName <String> [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="6c46e-108">TypeDataSet</span><span class="sxs-lookup"><span data-stu-id="6c46e-108">TypeDataSet</span></span>

```
Update-TypeData [-Force] [-TypeData] <TypeData[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6c46e-109">説明</span><span class="sxs-lookup"><span data-stu-id="6c46e-109">Description</span></span>

<span data-ttu-id="6c46e-110">`Update-TypeData`コマンドレットは、ファイルをメモリに再度読み込んで `Types.ps1xml` 新しい拡張型データを追加することによって、セッションの拡張型データを更新します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-110">The `Update-TypeData` cmdlet updates the extended type data in the session by reloading the `Types.ps1xml` files into memory and adding new extended type data.</span></span>

<span data-ttu-id="6c46e-111">既定では、PowerShell は必要に応じて拡張型データを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-111">By default, PowerShell loads extended type data as it is needed.</span></span> <span data-ttu-id="6c46e-112">パラメーターを指定しない場合は、 `Update-TypeData` 追加したすべての `Types.ps1xml` 種類のファイルを含め、セッションに読み込まれたすべてのファイルを再読み込みします。</span><span class="sxs-lookup"><span data-stu-id="6c46e-112">Without parameters, `Update-TypeData` reloads all of the `Types.ps1xml` files that it has loaded in the session, including any type files that you added.</span></span> <span data-ttu-id="6c46e-113">のパラメーターを使用し `Update-TypeData` て、新しい型ファイルを追加したり、拡張型データを追加したり置換したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-113">You can use the parameters of `Update-TypeData` to add new type files and add and replace extended type data.</span></span>

<span data-ttu-id="6c46e-114">コマンドレットを使用すると、 `Update-TypeData` すべての型データを事前に読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-114">The `Update-TypeData` cmdlet can be used to preload all type data.</span></span> <span data-ttu-id="6c46e-115">この機能は、型を開発し、テスト目的でそれらの新しい型を読み込むときに特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-115">This feature is particularly useful when you are developing types and want to load those new types for testing purposes.</span></span>

<span data-ttu-id="6c46e-116">Windows PowerShell 3.0 以降では、を使用し `Update-TypeData` て、ファイルを使用せずに、セッションの拡張型データを追加および置換できます `Types.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="6c46e-116">Beginning in Windows PowerShell 3.0, you can use `Update-TypeData` to add and replace extended type data in the session without using a `Types.ps1xml` file.</span></span> <span data-ttu-id="6c46e-117">動的、つまりファイルを使用せずに追加される型データは、現在のセッションのみに追加されます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-117">Type data that is added dynamically, that is, without a file, is added only to the current session.</span></span> <span data-ttu-id="6c46e-118">すべてのセッションに型データを追加するには、 `Update-TypeData` PowerShell プロファイルにコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-118">To add the type data to all sessions, add an `Update-TypeData` command to your PowerShell profile.</span></span> <span data-ttu-id="6c46e-119">詳細については、「 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c46e-119">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="6c46e-120">また、Windows PowerShell 3.0 以降では、コマンドレットを使用して、現在のセッションの拡張型を取得したり、コマンドレットを使用して `Get-TypeData` 現在の `Remove-TypeData` セッションから拡張型を削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-120">Also, beginning in Windows PowerShell 3.0, you can use the `Get-TypeData` cmdlet to get the extended types in the current session and the `Remove-TypeData` cmdlet to delete extended types from the current session.</span></span>

<span data-ttu-id="6c46e-121">プロパティで発生した例外、またはプロパティをコマンドに追加した場合 `Update-TypeData` 、エラーは報告されません。</span><span class="sxs-lookup"><span data-stu-id="6c46e-121">Exceptions that occur in properties, or from adding properties to an `Update-TypeData` command, do not report errors.</span></span> <span data-ttu-id="6c46e-122">これは、書式設定および出力の際に、多くの一般的な型で発生する例外を抑制します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-122">This is to suppress exceptions that would occur in many common types during formatting and outputting.</span></span> <span data-ttu-id="6c46e-123">.NET のプロパティを取得する場合は、次の例に示すように、代わりにメソッド構文を使用して例外の抑制を回避できます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-123">If you are getting .NET properties, you can work around the suppression of exceptions by using method syntax instead, as shown in the following example:</span></span>

`"hello".get_Length()`

<span data-ttu-id="6c46e-124">メソッド構文は .NET プロパティでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-124">Note that method syntax can only be used with .NET properties.</span></span> <span data-ttu-id="6c46e-125">コマンドレットの実行によって追加されたプロパティ `Update-TypeData` は、メソッド構文を使用できません。</span><span class="sxs-lookup"><span data-stu-id="6c46e-125">Properties that are added by running the `Update-TypeData` cmdlet cannot use method syntax.</span></span>

<span data-ttu-id="6c46e-126">PowerShell でのファイルの詳細につい `Types.ps1xml` ては、「 [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c46e-126">For more information about the `Types.ps1xml` files in PowerShell, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span>

## <span data-ttu-id="6c46e-127">例</span><span class="sxs-lookup"><span data-stu-id="6c46e-127">Examples</span></span>

### <span data-ttu-id="6c46e-128">例 1: 拡張型を更新する</span><span class="sxs-lookup"><span data-stu-id="6c46e-128">Example 1: Update extended types</span></span>

```powershell
Update-TypeData
```

<span data-ttu-id="6c46e-129">このコマンドは、 `Types.ps1xml` セッションで既に使用されているファイルから拡張型の構成を更新します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-129">This command updates the extended type configuration from the `Types.ps1xml` files that have already been used in the session.</span></span>

### <span data-ttu-id="6c46e-130">例 2: 型を複数回更新する</span><span class="sxs-lookup"><span data-stu-id="6c46e-130">Example 2: Update types multiple times</span></span>

<span data-ttu-id="6c46e-131">この例では、同じセッションで型ファイル内の型を複数回更新する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-131">This example shows how to update the types in a type file multiple times in the same session.</span></span>

<span data-ttu-id="6c46e-132">最初のコマンドは、ファイルから拡張型の構成を更新して、 `Types.ps1xml` `TypesA.types.ps1xml` ファイルとファイルを最初に処理し `TypesB.types.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-132">The first command updates the extended type configuration from the `Types.ps1xml` files, processing the `TypesA.types.ps1xml` and `TypesB.types.ps1xml` files first.</span></span>

<span data-ttu-id="6c46e-133">2番目のコマンドは、 `TypesA.types.ps1xml` ファイルの型を追加または変更した場合など、をもう一度更新する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="6c46e-133">The second command shows how to update the `TypesA.types.ps1xml` again, such as you might do if you added or changed a type in the file.</span></span> <span data-ttu-id="6c46e-134">ファイルに対して前のコマンドを繰り返すか、 `TypesA.types.ps1xml` `Update-TypeData` パラメーターを指定せずにコマンドを実行することができ `TypesA.types.ps1xml` ます。これは、が既に現在のセッションの型ファイルリストに存在するためです。</span><span class="sxs-lookup"><span data-stu-id="6c46e-134">You can either repeat the previous command for the `TypesA.types.ps1xml` file, or run an `Update-TypeData` command without parameters, because `TypesA.types.ps1xml` is already in the type file list for the current session.</span></span>

```powershell
Update-TypeData -PrependPath TypesA.types.ps1xml, TypesB.types.ps1xml
Update-TypeData -PrependPath TypesA.types.ps1xml
```

### <span data-ttu-id="6c46e-135">例 3: DateTime オブジェクトにスクリプトプロパティを追加する</span><span class="sxs-lookup"><span data-stu-id="6c46e-135">Example 3: Add a script property to DateTime objects</span></span>

<span data-ttu-id="6c46e-136">この例では、を使用して、現在のセッションの system.string `Update-TypeData` オブジェクト (コマンドレットによって返されるオブジェクトなど) に **Quarter** スクリプトプロパティ **を** 追加し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-136">This example uses `Update-TypeData` to add the **Quarter** script property to **System.DateTime** objects in the current session, such as those returned by the `Get-Date` cmdlet.</span></span>

```powershell
Update-TypeData -TypeName "System.DateTime" -MemberType ScriptProperty -MemberName "Quarter" -Value {
  if ($this.Month -in @(1,2,3)) {"Q1"}
  elseif ($this.Month -in @(4,5,6)) {"Q2"}
  elseif ($this.Month -in @(7,8,9)) {"Q3"}
  else {"Q4"}
}
(Get-Date).Quarter
```

```Output
Q1
```

<span data-ttu-id="6c46e-137">この `Update-TypeData` コマンドは、 **TypeName** パラメーターを使用 **して system.string** 型を指定し **、MemberName** パラメーターを使用して新しいプロパティの名前を指定し、 **MemberType** プロパティを使用して **scriptproperty** 型を指定し、 **Value** パラメーターを使用して年間四半期を決定するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-137">The `Update-TypeData` command uses the **TypeName** parameter to specify **the System.DateTime** type, the **MemberName** parameter to specify a name for the new property, the **MemberType** property to specify the **ScriptProperty** type, and the **Value** parameter to specify the script that determines the annual quarter.</span></span>

<span data-ttu-id="6c46e-138">**Value** プロパティの値は、現在の年間の四半期を計算するスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="6c46e-138">The value of the **Value** property is a script that calculates the current annual quarter.</span></span> <span data-ttu-id="6c46e-139">スクリプトブロックは、 `$this` オブジェクトの現在のインスタンスを表す自動変数と In 演算子を使用して、月の値が各整数配列に表示されるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-139">The script block uses the `$this` automatic variable to represent the current instance of the object and the In operator to determine whether the month value appears in each integer array.</span></span> <span data-ttu-id="6c46e-140">オペレーターの詳細については `-in` 、「 [about_Comparison_Operators](../Microsoft.PowerShell.Core/about/about_Comparison_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c46e-140">For more information about the `-in` operator, see [about_Comparison_Operators](../Microsoft.PowerShell.Core/about/about_Comparison_Operators.md).</span></span>

<span data-ttu-id="6c46e-141">2 番目のコマンドは、現在の日付の新しい Quarter プロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-141">The second command gets the new Quarter property of the current date.</span></span>

### <span data-ttu-id="6c46e-142">例 4: 既定でリスト内に表示される型を更新する</span><span class="sxs-lookup"><span data-stu-id="6c46e-142">Example 4: Update a type that displays in lists by default</span></span>

<span data-ttu-id="6c46e-143">この例では、プロパティが指定されていない場合に、既定でリスト内に表示される型のプロパティを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-143">This example shows how to set the properties of a type that displays in lists by default, that is, when no properties are specified.</span></span> <span data-ttu-id="6c46e-144">型データはファイルで指定されていないため `Types.ps1xml` 、現在のセッションでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="6c46e-144">Because the type data is not specified in a `Types.ps1xml` file, it is effective only in the current session.</span></span>

```powershell
Update-TypeData -TypeName "System.DateTime" -DefaultDisplayPropertySet "DateTime, DayOfYear, Quarter"
Get-Date | Format-List
```

```Output
Thursday, March 15, 2012 12:00:00 AM
DayOfYear : 75
Quarter   : Q1
```

<span data-ttu-id="6c46e-145">最初のコマンドは、コマンドレットを使用して、system.string `Update-TypeData` 型の既定のリストプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-145">The first command uses the `Update-TypeData` cmdlet to set the default list properties for the **System.DateTime** type.</span></span> <span data-ttu-id="6c46e-146">このコマンドは、**TypeName** パラメーターを使用して型を指定し、**DefaultDisplayPropertySet** パラメーターを使用して一覧の既定のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-146">The command uses the **TypeName** parameter to specify the type and the **DefaultDisplayPropertySet** parameter to specify the default properties for a list.</span></span> <span data-ttu-id="6c46e-147">選択したプロパティには、前の例で追加した新しい **Quarter** スクリプトプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6c46e-147">The selected properties include the new **Quarter** script property that was added in a previous example.</span></span>

<span data-ttu-id="6c46e-148">2番目のコマンドは、コマンドレットを使用して、 `Get-Date` 現在の日付を表す system.string オブジェクトを取得します **。**</span><span class="sxs-lookup"><span data-stu-id="6c46e-148">The second command uses the `Get-Date` cmdlet to get a **System.DateTime** object that represents the current date.</span></span> <span data-ttu-id="6c46e-149">このコマンドは、パイプライン演算子 () を使用して、 `|` **DateTime** オブジェクトをコマンドレットに送信し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-149">The command uses a pipeline operator (`|`) to send the **DateTime** object to the `Format-List` cmdlet.</span></span> <span data-ttu-id="6c46e-150">コマンドでは、 `Format-List` 一覧に表示するプロパティが指定されていないため、PowerShell はコマンドによって設定された既定値を使用し `Update-TypeData` ます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-150">Because the `Format-List` command does not specify the properties to display in the list, PowerShell uses the default values that were established by the `Update-TypeData` command.</span></span>

### <span data-ttu-id="6c46e-151">例 5: パイプを使用したオブジェクトの型データを更新する</span><span class="sxs-lookup"><span data-stu-id="6c46e-151">Example 5: Update type data for a piped object</span></span>

```powershell
Get-Module | Update-TypeData -MemberType ScriptProperty -MemberName "SupportsUpdatableHelp" -Value {
  if ($this.HelpInfoUri) {$True} else {$False}
}
Get-Module -ListAvailable | Format-Table Name, SupportsUpdatableHelp
```

```Output
Name                             SupportsUpdatableHelp
----                             ---------------------
Microsoft.PowerShell.Diagnostics                  True
Microsoft.PowerShell.Host                         True
Microsoft.PowerShell.Management                   True
Microsoft.PowerShell.Security                     True
Microsoft.PowerShell.Utility                      True
Microsoft.WSMan.Management                        True
PSDiagnostics                                    False
PSScheduledJob                                    True
PSWorkflow                                        True
ServerManager                                     True
TroubleshootingPack                              False
```

<span data-ttu-id="6c46e-152">この例では、オブジェクトをにパイプするときに `Update-TypeData` 、 `Update-TypeData` オブジェクト型の拡張型データを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-152">This example demonstrates that when you pipe an object to `Update-TypeData`, `Update-TypeData` adds extended type data for the object type.</span></span>

<span data-ttu-id="6c46e-153">この方法は、 `Get-Member` コマンドレットまたはメソッドを使用して `Get-Type` オブジェクトの型を取得するよりも高速です。</span><span class="sxs-lookup"><span data-stu-id="6c46e-153">This technique is quicker than using the `Get-Member` cmdlet or the `Get-Type` method to get the object type.</span></span> <span data-ttu-id="6c46e-154">ただし、オブジェクトのコレクションをにパイプする場合は `Update-TypeData` 、最初のオブジェクト型の型データを更新してから、コレクション内の他のすべてのオブジェクトに対してエラーを返します。これは、メンバーが型に対して既に定義されているためです。</span><span class="sxs-lookup"><span data-stu-id="6c46e-154">However, if you pipe a collection of objects to `Update-TypeData`, it updates the type data of the first object type and then returns an error for all other objects in the collection because the member is already defined on the type.</span></span>

<span data-ttu-id="6c46e-155">最初のコマンドは、 `Get-Module` コマンドレットを使用して PSScheduledJob モジュールを取得します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-155">The first command uses the `Get-Module` cmdlet to get the PSScheduledJob module.</span></span> <span data-ttu-id="6c46e-156">このコマンドは、モジュールオブジェクトをコマンドレットにパイプします。このコマンドレットは、 `Update-TypeData`  `Get-Module` コマンドで **ListAvailable** パラメーターを使用したときに返される Moduleinfogrouping 型など、PSModuleInfo 型とそれから派生した型の型データを更新します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-156">The command pipes the module object to the `Update-TypeData` cmdlet, which updates the type data for the **System.Management.Automation.PSModuleInfo** type and the types derived from it, such as the ModuleInfoGrouping type that `Get-Module` returns when you use the **ListAvailable** parameter in the command.</span></span>

<span data-ttu-id="6c46e-157">これらのコマンドは、インポートされた `Update-TypeData` すべてのモジュールに **Supportsupthe help** script プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-157">The `Update-TypeData` commands adds the **SupportsUpdatableHelp** script property to all imported modules.</span></span> <span data-ttu-id="6c46e-158">**Value** パラメーターの値は、 `$True` モジュールの **helpinfouri** プロパティが設定されている場合はを返し、それ以外の場合はを返すスクリプトです `$False` 。</span><span class="sxs-lookup"><span data-stu-id="6c46e-158">The value of the **Value** parameter is a script that returns `$True` if the **HelpInfoUri** property of the module is populated and `$False` otherwise.</span></span>

<span data-ttu-id="6c46e-159">2番目のコマンドは、モジュールオブジェクトをから `Get-Module` コマンドレットにパイプします。このコマンドレットは、 `Format-Table` リスト内のすべてのモジュールの **Name** プロパティと **supportsuphelp** プロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-159">The second command pipes the module objects from `Get-Module` to the `Format-Table` cmdlet, which displays the **Name** and **SupportsUpdatableHelp** properties of all modules in a list.</span></span>

## <span data-ttu-id="6c46e-160">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6c46e-160">Parameters</span></span>

### <span data-ttu-id="6c46e-161">-AppendPath</span><span class="sxs-lookup"><span data-stu-id="6c46e-161">-AppendPath</span></span>

<span data-ttu-id="6c46e-162">省略可能なファイルへのパスを指定し `.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-162">Specifies the path to optional `.ps1xml` files.</span></span> <span data-ttu-id="6c46e-163">指定されたファイルは、組み込みファイルが読み込まれた後にリストされる順序で、読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-163">The specified files are loaded in the order that they are listed after the built-in files are loaded.</span></span> <span data-ttu-id="6c46e-164">また、 **Appendpath** 値をにパイプすることもでき `Update-TypeData` ます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-164">You can also pipe an **AppendPath** value to `Update-TypeData`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases: PSPath, Path

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-165">-DefaultDisplayProperty</span><span class="sxs-lookup"><span data-stu-id="6c46e-165">-DefaultDisplayProperty</span></span>

<span data-ttu-id="6c46e-166">他のプロパティが指定されていない場合に、コマンドレットによって表示される型のプロパティを指定し `Format-Wide` ます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-166">Specifies the property of the type that is displayed by the `Format-Wide` cmdlet when no other properties are specified.</span></span>

<span data-ttu-id="6c46e-167">型の標準および拡張プロパティの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-167">Type the name of a standard or extended property of the type.</span></span> <span data-ttu-id="6c46e-168">このパラメーターの値には、同じコマンドに追加される型の名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-168">The value of this parameter can be the name of a type that is added in the same command.</span></span>

<span data-ttu-id="6c46e-169">この値は、ファイル内の型に対して定義されているワイドビューがない場合にのみ有効です `Format.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="6c46e-169">This value is effective only when there are no wide views defined for the type in a `Format.ps1xml` file.</span></span>

<span data-ttu-id="6c46e-170">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c46e-170">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-171">-DefaultDisplayPropertySet</span><span class="sxs-lookup"><span data-stu-id="6c46e-171">-DefaultDisplayPropertySet</span></span>

<span data-ttu-id="6c46e-172">型の 1 つまたは複数のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-172">Specifies one or more properties of the type.</span></span> <span data-ttu-id="6c46e-173">これらのプロパティは、他のプロパティが指定されていない場合に、コマンドレットによって表示され `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-173">These properties are displayed by the `Format-List` cmdlet when no other properties are specified.</span></span>

<span data-ttu-id="6c46e-174">型の標準および拡張プロパティの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-174">Type the names of standard or extended properties of the type.</span></span> <span data-ttu-id="6c46e-175">このパラメーターの値には、同じコマンドに追加される型の名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-175">The value of this parameter can be the names of types that are added in the same command.</span></span>

<span data-ttu-id="6c46e-176">この値は、ファイル内の型に対して定義されているリストビューがない場合にのみ有効です `Format.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="6c46e-176">This value is effective only when there are no list views defined for the type in a `Format.ps1xml` file.</span></span>

<span data-ttu-id="6c46e-177">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c46e-177">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-178">-DefaultKeyPropertySet</span><span class="sxs-lookup"><span data-stu-id="6c46e-178">-DefaultKeyPropertySet</span></span>

<span data-ttu-id="6c46e-179">型の 1 つまたは複数のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-179">Specifies one or more properties of the type.</span></span> <span data-ttu-id="6c46e-180">これらのプロパティは、 `Group-Object` `Sort-Object` 他のプロパティが指定されていない場合に、コマンドレットとコマンドレットで使用されます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-180">These properties are used by the `Group-Object` and `Sort-Object` cmdlets when no other properties are specified.</span></span>

<span data-ttu-id="6c46e-181">型の標準および拡張プロパティの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-181">Type the names of standard or extended properties of the type.</span></span> <span data-ttu-id="6c46e-182">このパラメーターの値には、同じコマンドに追加される型の名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-182">The value of this parameter can be the names of types that are added in the same command.</span></span>

<span data-ttu-id="6c46e-183">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c46e-183">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-184">-Force</span><span class="sxs-lookup"><span data-stu-id="6c46e-184">-Force</span></span>

<span data-ttu-id="6c46e-185">型データがその型に対して既に指定されている場合でも、コマンドレットで指定された型データを使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-185">Indicates that the cmdlet uses the specified type data, even if type data has already been specified for that type.</span></span>

<span data-ttu-id="6c46e-186">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c46e-186">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DynamicTypeSet, TypeDataSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-187">-InheritPropertySerializationSet</span><span class="sxs-lookup"><span data-stu-id="6c46e-187">-InheritPropertySerializationSet</span></span>

<span data-ttu-id="6c46e-188">シリアル化されたプロパティのセットが継承されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-188">Indicates whether the set of properties that are serialized is inherited.</span></span> <span data-ttu-id="6c46e-189">既定値は `$Null` です。</span><span class="sxs-lookup"><span data-stu-id="6c46e-189">The default value is `$Null`.</span></span> <span data-ttu-id="6c46e-190">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6c46e-190">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="6c46e-191">`$True`.</span><span class="sxs-lookup"><span data-stu-id="6c46e-191">`$True`.</span></span> <span data-ttu-id="6c46e-192">プロパティ セットは継承されます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-192">The property set is inherited.</span></span>
- <span data-ttu-id="6c46e-193">`$False`.</span><span class="sxs-lookup"><span data-stu-id="6c46e-193">`$False`.</span></span> <span data-ttu-id="6c46e-194">プロパティ セットは継承されません。</span><span class="sxs-lookup"><span data-stu-id="6c46e-194">The property set is not inherited.</span></span>
- <span data-ttu-id="6c46e-195">`$Null`.</span><span class="sxs-lookup"><span data-stu-id="6c46e-195">`$Null`.</span></span> <span data-ttu-id="6c46e-196">継承は定義されていません。</span><span class="sxs-lookup"><span data-stu-id="6c46e-196">Inheritance is not defined.</span></span>

<span data-ttu-id="6c46e-197">このパラメーターは、 **Serializationmethod** パラメーターの値がの場合にのみ有効です `SpecificProperties` 。</span><span class="sxs-lookup"><span data-stu-id="6c46e-197">This parameter is valid only when the value of the **SerializationMethod** parameter is `SpecificProperties`.</span></span> <span data-ttu-id="6c46e-198">このパラメーターの値がの場合は `$False` 、 **Propertyserializationset** パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="6c46e-198">When the value of this parameter is `$False`, the **PropertySerializationSet** parameter is required.</span></span>

<span data-ttu-id="6c46e-199">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c46e-199">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-200">-MemberName</span><span class="sxs-lookup"><span data-stu-id="6c46e-200">-MemberName</span></span>

<span data-ttu-id="6c46e-201">プロパティまたはメソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-201">Specifies the name of a property or method.</span></span>

<span data-ttu-id="6c46e-202">このパラメーターを **TypeName**、**MemberType**、**Value**、および **SecondValue** パラメーターと共に使用して、型のプロパティまたはメソッドを追加または変更できます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-202">Use this parameter with the **TypeName**, **MemberType**, **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="6c46e-203">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c46e-203">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-204">-MemberType</span><span class="sxs-lookup"><span data-stu-id="6c46e-204">-MemberType</span></span>

<span data-ttu-id="6c46e-205">追加または変更するメンバーの型を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-205">Specifies the type of the member to add or change.</span></span>

<span data-ttu-id="6c46e-206">このパラメーターを **TypeName**、**MemberType**、**Value**、および **SecondValue** パラメーターと共に使用して、型のプロパティまたはメソッドを追加または変更できます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-206">Use this parameter with the **TypeName**, **MemberType**, **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span> <span data-ttu-id="6c46e-207">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6c46e-207">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="6c46e-208">AliasProperty</span><span class="sxs-lookup"><span data-stu-id="6c46e-208">AliasProperty</span></span>
- <span data-ttu-id="6c46e-209">CodeMethod</span><span class="sxs-lookup"><span data-stu-id="6c46e-209">CodeMethod</span></span>
- <span data-ttu-id="6c46e-210">CodeProperty</span><span class="sxs-lookup"><span data-stu-id="6c46e-210">CodeProperty</span></span>
- <span data-ttu-id="6c46e-211">Noteproperty</span><span class="sxs-lookup"><span data-stu-id="6c46e-211">Noteproperty</span></span>
- <span data-ttu-id="6c46e-212">ScriptMethod</span><span class="sxs-lookup"><span data-stu-id="6c46e-212">ScriptMethod</span></span>
- <span data-ttu-id="6c46e-213">ScriptProperty</span><span class="sxs-lookup"><span data-stu-id="6c46e-213">ScriptProperty</span></span>

<span data-ttu-id="6c46e-214">これらの値の詳細については、「 [PSMemberTypes Enumeration](/dotnet/api/system.management.automation.psmembertypes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c46e-214">For information about these values, see [PSMemberTypes Enumeration](/dotnet/api/system.management.automation.psmembertypes).</span></span>

<span data-ttu-id="6c46e-215">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c46e-215">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: DynamicTypeSet
Aliases:
Accepted values: NoteProperty, AliasProperty, ScriptProperty, CodeProperty, ScriptMethod, CodeMethod

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-216">-PrependPath</span><span class="sxs-lookup"><span data-stu-id="6c46e-216">-PrependPath</span></span>

<span data-ttu-id="6c46e-217">オプションファイルへのパスを指定し `.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-217">Specifies the path to the optional `.ps1xml` files.</span></span> <span data-ttu-id="6c46e-218">指定されたファイルは、組み込みファイルが読み込まれる前にリストされる順序で、読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-218">The specified files are loaded in the order that they are listed before the built-in files are loaded.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FileSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-219">-PropertySerializationSet</span><span class="sxs-lookup"><span data-stu-id="6c46e-219">-PropertySerializationSet</span></span>

<span data-ttu-id="6c46e-220">シリアル化するプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-220">Specifies the names of properties that are serialized.</span></span> <span data-ttu-id="6c46e-221">このパラメーターは、**SerializationMethod** パラメーターの値が **SpecificProperties** の場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-221">Use this parameter when the value of the **SerializationMethod** parameter is **SpecificProperties**.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-222">-SecondValue</span><span class="sxs-lookup"><span data-stu-id="6c46e-222">-SecondValue</span></span>

<span data-ttu-id="6c46e-223">**AliasProperty**、**ScriptProperty**、**CodeProperty**、または **CodeMethod** メンバーの追加値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-223">Specifies additional values for **AliasProperty**, **ScriptProperty**, **CodeProperty**, or **CodeMethod** members.</span></span>

<span data-ttu-id="6c46e-224">型のプロパティまたはメソッドを追加または変更するには、このパラメーターを **TypeName**、 **MemberType**、 **Value**、および **SecondValue** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-224">Use this parameter with the **TypeName**, **MemberType**, **Value**, and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="6c46e-225">**MemberType** パラメーターの値がの場合 `AliasProperty` 、 **SecondValue** パラメーターの値はデータ型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c46e-225">When the value of the **MemberType** parameter is `AliasProperty`, the value of the **SecondValue** parameter must be a data type.</span></span> <span data-ttu-id="6c46e-226">PowerShell は、alias プロパティの値を指定された型に変換します (つまり、キャストします)。</span><span class="sxs-lookup"><span data-stu-id="6c46e-226">PowerShell converts (that is, casts) the value of the alias property to the specified type.</span></span> <span data-ttu-id="6c46e-227">たとえば、文字列プロパティの代替名を提供するエイリアスプロパティを追加する場合、 **SecondValue** の値を指定して、エイリアス化された文字列値を整数に変換することも **できます。**</span><span class="sxs-lookup"><span data-stu-id="6c46e-227">For example, if you add an alias property that provides an alternate name for a string property, you can also specify a **SecondValue** of **System.Int32** to convert the aliased string value to an integer.</span></span>

<span data-ttu-id="6c46e-228">**MemberType** パラメーターの値がの場合は `ScriptProperty` 、 **SecondValue** パラメーターを使用して、追加のスクリプトブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-228">When the value of the **MemberType** parameter is `ScriptProperty`, you can use the **SecondValue** parameter to specify an additional script block.</span></span> <span data-ttu-id="6c46e-229">**Value** パラメーターの値内のスクリプト ブロックは、変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-229">The script block in the value of the **Value** parameter gets the value of a variable.</span></span> <span data-ttu-id="6c46e-230">**SecondValue** パラメーターの値内のスクリプト ブロックは、変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-230">The script block in the value of the **SecondValue** parameter set the value of the variable.</span></span>

<span data-ttu-id="6c46e-231">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c46e-231">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-232">-SerializationDepth</span><span class="sxs-lookup"><span data-stu-id="6c46e-232">-SerializationDepth</span></span>

<span data-ttu-id="6c46e-233">文字列としてシリアル化する型オブジェクトのレベル数を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-233">Specifies how many levels of type objects are serialized as strings.</span></span> <span data-ttu-id="6c46e-234">既定値は、 `1` オブジェクトとそのプロパティをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-234">The default value `1` serializes the object and its properties.</span></span> <span data-ttu-id="6c46e-235">値は、 `0` オブジェクトをシリアル化しますが、そのプロパティはシリアル化しません。</span><span class="sxs-lookup"><span data-stu-id="6c46e-235">A value of `0` serializes the object, but not its properties.</span></span> <span data-ttu-id="6c46e-236">値は、 `2` オブジェクト、そのプロパティ、およびプロパティ値内のオブジェクトをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-236">A value of `2` serializes the object, its properties, and any objects in property values.</span></span>

<span data-ttu-id="6c46e-237">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c46e-237">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-238">-SerializationMethod</span><span class="sxs-lookup"><span data-stu-id="6c46e-238">-SerializationMethod</span></span>

<span data-ttu-id="6c46e-239">型のシリアル化メソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-239">Specifies a serialization method for the type.</span></span> <span data-ttu-id="6c46e-240">シリアル化メソッドは、シリアル化される型のプロパティとそれらのシリアル化に使用する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-240">A serialization method determines which properties of the type are serialized and the technique that is used to serialize them.</span></span> <span data-ttu-id="6c46e-241">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6c46e-241">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="6c46e-242">`AllPublicProperties`.</span><span class="sxs-lookup"><span data-stu-id="6c46e-242">`AllPublicProperties`.</span></span> <span data-ttu-id="6c46e-243">型のすべてのパブリック プロパティをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-243">Serialize all public properties of the type.</span></span> <span data-ttu-id="6c46e-244">**SerializationDepth** パラメーターを使用して、子プロパティをシリアル化するかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-244">You can use the **SerializationDepth** parameter to determine whether child properties are serialized.</span></span>
- <span data-ttu-id="6c46e-245">`String`.</span><span class="sxs-lookup"><span data-stu-id="6c46e-245">`String`.</span></span> <span data-ttu-id="6c46e-246">文字列として、型をシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-246">Serialize the type as a string.</span></span> <span data-ttu-id="6c46e-247">**StringSerializationSource** を使用して、シリアル化の結果として使用する型のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-247">You can use the **StringSerializationSource** to specify a property of the type to use as the serialization result.</span></span> <span data-ttu-id="6c46e-248">指定しない場合、型はオブジェクトの **ToString** メソッドを使用してシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-248">Otherwise, the type is serialized by using the **ToString** method of the object.</span></span>
- <span data-ttu-id="6c46e-249">`SpecificProperties`.</span><span class="sxs-lookup"><span data-stu-id="6c46e-249">`SpecificProperties`.</span></span> <span data-ttu-id="6c46e-250">この型の指定されたプロパティのみをシリアル化します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-250">Serialize only the specified properties of this type.</span></span> <span data-ttu-id="6c46e-251">**PropertySerializationSet** パラメーターを使用して、シリアル化される型のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-251">Use the **PropertySerializationSet** parameter to specify the properties of the type that are serialized.</span></span>
  <span data-ttu-id="6c46e-252">また、**InheritPropertySerializationSet** パラメーターを使用してプロパティ セットを継承するかどうかを決定することも、**SerializationDepth** パラメーターを使用して子プロパティをシリアル化するかどうかを決定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-252">You can also use the **InheritPropertySerializationSet** parameter to determine whether the property set is inherited and the **SerializationDepth** parameter to determine whether child properties are serialized.</span></span>

<span data-ttu-id="6c46e-253">PowerShell では、シリアル化メソッドは **Psstandardmembers** 内部オブジェクトに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-253">In PowerShell, serialization methods are stored in **PSStandardMembers** internal objects.</span></span>

<span data-ttu-id="6c46e-254">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c46e-254">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-255">-StringSerializationSource</span><span class="sxs-lookup"><span data-stu-id="6c46e-255">-StringSerializationSource</span></span>

<span data-ttu-id="6c46e-256">型のプロパティの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-256">Specifies the name of a property of the type.</span></span> <span data-ttu-id="6c46e-257">指定されたプロパティの値は、シリアル化の結果として使用されます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-257">The value of specified property is used as the serialization result.</span></span> <span data-ttu-id="6c46e-258">このパラメーターは、 **Serializationmethod** パラメーターの値が String の場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="6c46e-258">This parameter is valid only when the value of the **SerializationMethod** parameter is String.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-259">-TargetTypeForDeserialization シリアル化</span><span class="sxs-lookup"><span data-stu-id="6c46e-259">-TargetTypeForDeserialization</span></span>

<span data-ttu-id="6c46e-260">この型のオブジェクトが、逆シリアル化時に変換される型を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-260">Specifies the type to which object of this type are converted when they are deserialized.</span></span>

<span data-ttu-id="6c46e-261">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c46e-261">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-262">-TypeAdapter</span><span class="sxs-lookup"><span data-stu-id="6c46e-262">-TypeAdapter</span></span>

<span data-ttu-id="6c46e-263">型アダプターの種類 ( **microsoft.powershell.cim.ciminstanceadapter など** など) を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-263">Specifies the type of a type adapter, such as **Microsoft.PowerShell.Cim.CimInstanceAdapter**.</span></span> <span data-ttu-id="6c46e-264">型アダプターを使用すると、PowerShell は型のメンバーを取得できます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-264">A type adapter enables PowerShell to get the members of a type.</span></span>

<span data-ttu-id="6c46e-265">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c46e-265">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-266">-TypeConverter</span><span class="sxs-lookup"><span data-stu-id="6c46e-266">-TypeConverter</span></span>

<span data-ttu-id="6c46e-267">さまざまな型の間で値を変換する型コンバーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-267">Specifies a type converter to convert values between different types.</span></span> <span data-ttu-id="6c46e-268">型の型コンバーターが定義されている場合、型コンバーターのインスタンスが変換に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-268">If a type converter is defined for a type, an instance of the type converter is used for the conversion.</span></span>

<span data-ttu-id="6c46e-269">**System.Type** 値 (**System.ComponentModel.TypeConverter** または **System.Management.Automation.PSTypeConverter** クラスから派生したもの) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-269">Enter a **System.Type** value that is derived from the **System.ComponentModel.TypeConverter** or **System.Management.Automation.PSTypeConverter** classes.</span></span>

<span data-ttu-id="6c46e-270">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c46e-270">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Type
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-271">-TypeData</span><span class="sxs-lookup"><span data-stu-id="6c46e-271">-TypeData</span></span>

<span data-ttu-id="6c46e-272">このコマンドレットによってセッションに追加されるデータ型の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-272">Specifies an array of type data that this cmdlet adds to the session.</span></span> <span data-ttu-id="6c46e-273">**Typedata** オブジェクトを含む変数、またはコマンドなどの **typedata** オブジェクトを取得するコマンドを入力し `Get-TypeData` ます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-273">Enter a variable that contains a **TypeData** object or a command that gets a **TypeData** object, such as a `Get-TypeData` command.</span></span> <span data-ttu-id="6c46e-274">パイプを使用して **Typedata** オブジェクトをにパイプすることもでき `Update-TypeData` ます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-274">You can also pipe a **TypeData** object to `Update-TypeData`.</span></span>

<span data-ttu-id="6c46e-275">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c46e-275">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.TypeData[]
Parameter Sets: TypeDataSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-276">-TypeName</span><span class="sxs-lookup"><span data-stu-id="6c46e-276">-TypeName</span></span>

<span data-ttu-id="6c46e-277">拡張する型の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-277">Specifies the name of the type to extend.</span></span>

<span data-ttu-id="6c46e-278">**System** 名前空間内の型の場合は、短い名前を入力してください。</span><span class="sxs-lookup"><span data-stu-id="6c46e-278">For types in the **System** namespace, enter the short name.</span></span> <span data-ttu-id="6c46e-279">それ以外の場合は、完全な型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="6c46e-279">Otherwise, the full type name is required.</span></span> <span data-ttu-id="6c46e-280">ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6c46e-280">Wildcards are not supported.</span></span>

<span data-ttu-id="6c46e-281">パイプを使用して型名をにすることができ `Update-TypeData` ます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-281">You can pipe type names to `Update-TypeData`.</span></span> <span data-ttu-id="6c46e-282">パイプを使用してオブジェクトをにパイプすると `Update-TypeData` 、オブジェクト `Update-TypeData` の型名と型のデータがオブジェクト型に取得されます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-282">When you pipe an object to `Update-TypeData`, `Update-TypeData` gets the type name of the object and type data to the object type.</span></span>

<span data-ttu-id="6c46e-283">このパラメーターを **MemberName**、 **MemberType**、 **Value** 、 **SecondValue** の各パラメーターと共に使用して、型のプロパティまたはメソッドを追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-283">Use this parameter with the **MemberName**, **MemberType**, **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="6c46e-284">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c46e-284">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: DynamicTypeSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-285">-Value</span><span class="sxs-lookup"><span data-stu-id="6c46e-285">-Value</span></span>

<span data-ttu-id="6c46e-286">プロパティまたはメソッドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-286">Specifies the value of the property or method.</span></span>

<span data-ttu-id="6c46e-287">、、、またはのメンバーを追加する場合は、 `AliasProperty` `CodeProperty` `ScriptProperty` `CodeMethod` **SecondValue** パラメーターを使用して追加情報を追加できます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-287">If you add an `AliasProperty`, `CodeProperty`, `ScriptProperty`, or `CodeMethod` member, you can use the **SecondValue** parameter to add additional information.</span></span>

<span data-ttu-id="6c46e-288">このパラメーターを **MemberName**、 **MemberType**、 **Value** 、 **SecondValue** の各パラメーターと共に使用して、型のプロパティまたはメソッドを追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-288">Use this parameter with the **MemberName**, **MemberType**, **Value** and **SecondValue** parameters to add or change a property or method of a type.</span></span>

<span data-ttu-id="6c46e-289">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6c46e-289">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: DynamicTypeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-290">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6c46e-290">-Confirm</span></span>

<span data-ttu-id="6c46e-291">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-291">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-292">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6c46e-292">-WhatIf</span></span>

<span data-ttu-id="6c46e-293">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="6c46e-293">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="6c46e-294">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="6c46e-294">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6c46e-295">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6c46e-295">CommonParameters</span></span>

<span data-ttu-id="6c46e-296">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6c46e-296">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6c46e-297">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c46e-297">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6c46e-298">入力</span><span class="sxs-lookup"><span data-stu-id="6c46e-298">Inputs</span></span>

### <span data-ttu-id="6c46e-299">System.String</span><span class="sxs-lookup"><span data-stu-id="6c46e-299">System.String</span></span>

<span data-ttu-id="6c46e-300">パイプを使用して、 **Appendpath**、 **TypeName**、または **typedata** パラメーターの値を含む文字列をに渡すことができ `Update-TypeData` ます。</span><span class="sxs-lookup"><span data-stu-id="6c46e-300">You can pipe a string that contains the values of the **AppendPath**, **TypeName**, or **TypeData** parameters to `Update-TypeData`.</span></span>

## <span data-ttu-id="6c46e-301">出力</span><span class="sxs-lookup"><span data-stu-id="6c46e-301">Outputs</span></span>

### <span data-ttu-id="6c46e-302">なし</span><span class="sxs-lookup"><span data-stu-id="6c46e-302">None</span></span>

<span data-ttu-id="6c46e-303">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="6c46e-303">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="6c46e-304">メモ</span><span class="sxs-lookup"><span data-stu-id="6c46e-304">Notes</span></span>

## <span data-ttu-id="6c46e-305">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6c46e-305">Related links</span></span>

[<span data-ttu-id="6c46e-306">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="6c46e-306">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="6c46e-307">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="6c46e-307">Get-TypeData</span></span>](Get-TypeData.md)

[<span data-ttu-id="6c46e-308">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="6c46e-308">Remove-TypeData</span></span>](Remove-TypeData.md)

