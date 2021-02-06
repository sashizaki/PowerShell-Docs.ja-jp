---
description: 関数が返すオブジェクトの種類を報告する属性について説明します。
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_outputtypeattribute?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_OutputTypeAttribute
ms.openlocfilehash: 82f1615c4a2fe2a24f104d8e5637103dea6e5a0a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599929"
---
# <a name="about-functions-outputtypeattribute"></a><span data-ttu-id="8b284-103">関数の概要 OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="8b284-103">About Functions OutputTypeAttribute</span></span>

## <a name="short-description"></a><span data-ttu-id="8b284-104">概要</span><span class="sxs-lookup"><span data-stu-id="8b284-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="8b284-105">関数が返すオブジェクトの種類を報告する属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b284-105">Describes an attribute that reports the type of object that the function returns.</span></span>

## <a name="long-description"></a><span data-ttu-id="8b284-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="8b284-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="8b284-107">OutputType 属性は、関数が返すオブジェクトの .NET 型を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="8b284-107">The OutputType attribute lists the .NET types of objects that the functions returns.</span></span> <span data-ttu-id="8b284-108">省略可能な ParameterSetName パラメーターを使用して、各パラメーターセットに対して異なる出力の種類を一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="8b284-108">You can use its optional ParameterSetName parameter to list different output types for each parameter set.</span></span>

<span data-ttu-id="8b284-109">OutputType 属性は、単純関数と高度な関数でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8b284-109">The OutputType attribute is supported on simple and advanced functions.</span></span> <span data-ttu-id="8b284-110">これは、ファイルレットバインド属性に依存しません。</span><span class="sxs-lookup"><span data-stu-id="8b284-110">It is independent of the CmdletBinding attribute.</span></span>

<span data-ttu-id="8b284-111">OutputType 属性は、コマンドレットが返す **、system.servicemodel オブジェクトの** outputtype プロパティの値を提供し `Get-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="8b284-111">The OutputType attribute provides the value of the OutputType property of the **System.Management.Automation.FunctionInfo** object that the `Get-Command` cmdlet returns.</span></span>

<span data-ttu-id="8b284-112">OutputType 属性値は、ドキュメントのメモにすぎません。</span><span class="sxs-lookup"><span data-stu-id="8b284-112">The OutputType attribute value is only a documentation note.</span></span> <span data-ttu-id="8b284-113">関数のコードから派生したり、実際の関数の出力と比較したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8b284-113">It is not derived from the function code or compared to the actual function output.</span></span> <span data-ttu-id="8b284-114">そのため、値が不正確になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8b284-114">As such, the value might be inaccurate.</span></span>

## <a name="syntax"></a><span data-ttu-id="8b284-115">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8b284-115">SYNTAX</span></span>

<span data-ttu-id="8b284-116">関数の OutputType 属性の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8b284-116">The OutputType attribute of functions has the following syntax:</span></span>

```
[OutputType([<TypeLiteral>], ParameterSetName="<Name>")]
[OutputType("<TypeNameString>", ParameterSetName="<Name>")]
```

<span data-ttu-id="8b284-117">**ParameterSetName** パラメーターは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="8b284-117">The **ParameterSetName** parameter is optional.</span></span>

<span data-ttu-id="8b284-118">OutputType 属性では、複数の型を一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="8b284-118">You can list multiple types in the OutputType attribute.</span></span>

```
[OutputType([<Type1>],[<Type2>],[<Type3>])]
```

<span data-ttu-id="8b284-119">**ParameterSetName** パラメーターを使用して、異なるパラメーターセットが異なる型を返すことを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="8b284-119">You can use the **ParameterSetName** parameter to indicate that different parameter sets return different types.</span></span>

```
[OutputType([<Type1>], ParameterSetName=("<Set1>","<Set2>"))]
[OutputType([<Type2>], ParameterSetName="<Set3>")]
```

<span data-ttu-id="8b284-120">OutputType 属性のステートメントを、ステートメントの前にある属性リストに配置し `Param` ます。</span><span class="sxs-lookup"><span data-stu-id="8b284-120">Place the OutputType attribute statements in the attributes list that precedes the `Param` statement.</span></span>

<span data-ttu-id="8b284-121">次の例は、単純な関数における OutputType 属性の配置を示しています。</span><span class="sxs-lookup"><span data-stu-id="8b284-121">The following example shows the placement of the OutputType attribute in a simple function.</span></span>

```powershell
function SimpleFunction2
{
  [OutputType([<Type>])]
  Param ($Parameter1)

  <function body>
}
```

<span data-ttu-id="8b284-122">次の例は、高度な関数における OutputType 属性の配置を示しています。</span><span class="sxs-lookup"><span data-stu-id="8b284-122">The following example shows the placement of the OutputType attribute in advanced functions.</span></span>

```powershell
function AdvancedFunction1
{
  [OutputType([<Type>])]
  Param (
    [parameter(Mandatory=$true)]
    [String[]]
    $Parameter1
  )

  <function body>
}

function AdvancedFunction2
{
  [CmdletBinding(SupportsShouldProcess=<Boolean>)]
  [OutputType([<Type>])]
  Param (
    [parameter(Mandatory=$true)]
    [String[]]
    $Parameter1
  )

  <function body>
}
```

## <a name="examples"></a><span data-ttu-id="8b284-123">例</span><span class="sxs-lookup"><span data-stu-id="8b284-123">EXAMPLES</span></span>

### <a name="example-1-create-a-function-that-has-the-outputtype-of-string"></a><span data-ttu-id="8b284-124">例 1: 文字列の OutputType を持つ関数を作成する</span><span class="sxs-lookup"><span data-stu-id="8b284-124">Example 1: Create a function that has the OutputType of String</span></span>

```powershell
function Send-Greeting
{
  [OutputType([String])]
  Param ($Name)

  "Hello, $Name"
}
```

<span data-ttu-id="8b284-125">結果の出力の種類のプロパティを表示するには、コマンドレットを使用し `Get-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="8b284-125">To see the resulting output type property, use the `Get-Command` cmdlet.</span></span>

```powershell
(Get-Command Send-Greeting).OutputType
```

```Output
Name                                               Type
----                                               ----
System.String                                      System.String
```

### <a name="example-2-use-the-output-attribute-to-indicate-dynamic-output-types"></a><span data-ttu-id="8b284-126">例 2: 出力属性を使用して動的な出力の種類を指定する</span><span class="sxs-lookup"><span data-stu-id="8b284-126">Example 2: Use the Output attribute to indicate dynamic output types</span></span>

<span data-ttu-id="8b284-127">次の高度な関数では、OutputType 属性を使用して、関数が関数コマンドで使用されるパラメーターセットに応じて異なる型を返すことを示しています。</span><span class="sxs-lookup"><span data-stu-id="8b284-127">The following advanced function uses the OutputType attribute to indicate that the function returns different types depending on the parameter set used in the function command.</span></span>

```powershell
function Get-User
{
  [CmdletBinding(DefaultParameterSetName="ID")]

  [OutputType("System.Int32", ParameterSetName="ID")]
  [OutputType([String], ParameterSetName="Name")]

  Param (
    [parameter(Mandatory=$true, ParameterSetName="ID")]
    [Int[]]
    $UserID,

    [parameter(Mandatory=$true, ParameterSetName="Name")]
    [String[]]
    $UserName
  )

  <function body>
}
```

### <a name="example-3-shows-when-an-actual-output-differs-from-the-outputtype"></a><span data-ttu-id="8b284-128">例 3: 実際の出力が OutputType と異なるタイミングを示します。</span><span class="sxs-lookup"><span data-stu-id="8b284-128">Example 3: Shows when an actual output differs from the OutputType</span></span>

<span data-ttu-id="8b284-129">次の例では、正確でない場合でも、[出力の種類] プロパティの値に OutputType 属性の値が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="8b284-129">The following example demonstrates that the output type property value displays the value of the OutputType attribute, even when it is inaccurate.</span></span>

<span data-ttu-id="8b284-130">関数は、 `Get-Time` 任意の DateTime オブジェクトの短い形式の時刻を含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="8b284-130">The `Get-Time` function returns a string that contains the short form of the time in any DateTime object.</span></span> <span data-ttu-id="8b284-131">ただし、OutputType 属性は、 **system.string オブジェクトが** 返されることを報告します。</span><span class="sxs-lookup"><span data-stu-id="8b284-131">However, the OutputType attribute reports that it returns a **System.DateTime** object.</span></span>

```powershell
function Get-Time
{
  [OutputType([DateTime])]
  Param (
    [parameter(Mandatory=$true)]
    [Datetime]$DateTime
  )

  $DateTime.ToShortTimeString()
}
```

<span data-ttu-id="8b284-132">メソッドは、 `GetType()` 関数が文字列を返すことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8b284-132">The `GetType()` method confirms that the function returns a string.</span></span>

```powershell
(Get-Time -DateTime (Get-Date)).GetType().FullName
```

```Output
System.String
```

<span data-ttu-id="8b284-133">ただし、outputtype 属性から値を取得する OutputType プロパティは、関数が **DateTime** オブジェクトを返すことを報告します。</span><span class="sxs-lookup"><span data-stu-id="8b284-133">However, the OutputType property, which gets its value from the OutputType attribute, reports that the function returns a **DateTime** object.</span></span>

```powershell
(Get-Command Get-Time).OutputType
```

```Output
Name                                      Type
----                                      ----
System.DateTime                           System.DateTime
```

### <a name="example-4-a-function--that-shouldnt-have-output"></a><span data-ttu-id="8b284-134">例 4: 出力を持たない関数</span><span class="sxs-lookup"><span data-stu-id="8b284-134">Example 4: A function  that shouldn't have output</span></span>

<span data-ttu-id="8b284-135">次の例は、およびアクションを実行する必要がありますが、何も返さないカスタム関数を示しています。</span><span class="sxs-lookup"><span data-stu-id="8b284-135">The following example shows a custom function that should perform and action but not return anything.</span></span>

```powershell
function Invoke-Notepad
{
  [OutputType([System.Void])]
  Param ()
  & notepad.exe | Out-Null
}
```

## <a name="notes"></a><span data-ttu-id="8b284-136">注</span><span class="sxs-lookup"><span data-stu-id="8b284-136">NOTES</span></span>

<span data-ttu-id="8b284-137">**Functioninfo** オブジェクトの OutputType プロパティの値は、 **PSTypeName** オブジェクトの配列であり、それぞれに Name プロパティと Type プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="8b284-137">The value of the OutputType property of a **FunctionInfo** object is an array of **System.Management.Automation.PSTypeName** objects, each of which have Name and Type properties.</span></span>

<span data-ttu-id="8b284-138">各出力の種類の名前のみを取得するには、次の形式のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b284-138">To get only the name of each output type, use a command with the following format.</span></span>

```powershell
(Get-Command Get-Time).OutputType | ForEach {$_.Name}
```

<span data-ttu-id="8b284-139">OutputType プロパティの値には null を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8b284-139">The value of the OutputType property can be null.</span></span> <span data-ttu-id="8b284-140">出力が、 **WMI** オブジェクトやオブジェクトの書式付きビューなどの .net 型ではない場合は、null 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="8b284-140">Use a null value when the output is a not a .NET type, such as a **WMI** object or a formatted view of an object.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b284-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b284-141">SEE ALSO</span></span>

[<span data-ttu-id="8b284-142">about_Functions</span><span class="sxs-lookup"><span data-stu-id="8b284-142">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="8b284-143">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="8b284-143">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="8b284-144">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="8b284-144">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="8b284-145">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="8b284-145">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="8b284-146">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="8b284-146">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

