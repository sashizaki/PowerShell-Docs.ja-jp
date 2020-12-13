---
ms.date: 09/12/2016
ms.topic: reference
title: コマンドレットのヘルプ トピックに構文を追加する方法
description: コマンドレットのヘルプ トピックに構文を追加する方法
ms.openlocfilehash: bcc037d22051c162cd0f70702da17afe7ed9c01a
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659072"
---
# <a name="how-to-add-syntax-to-a-cmdlet-help-topic"></a><span data-ttu-id="2479e-103">コマンドレットのヘルプ トピックに構文を追加する方法</span><span class="sxs-lookup"><span data-stu-id="2479e-103">How to Add Syntax to a Cmdlet Help Topic</span></span>

<span data-ttu-id="2479e-104">コマンドレットのヘルプファイルで構文ダイアグラムの XML のコーディングを開始する前に、このセクションを参照して、パラメーター属性など、指定する必要があるデータの種類と、そのデータが構文図に表示される方法を明確に把握してください。「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2479e-104">Before you start to code the XML for the syntax diagram in the cmdlet Help file, read this section to get a clear picture of the kind of data you need to provide, such as the parameter attributes, and how that data is displayed in the syntax diagram..</span></span>

## <a name="parameter-attributes"></a><span data-ttu-id="2479e-105">パラメーター属性</span><span class="sxs-lookup"><span data-stu-id="2479e-105">Parameter Attributes</span></span>

- <span data-ttu-id="2479e-106">必須</span><span class="sxs-lookup"><span data-stu-id="2479e-106">Required</span></span>
  - <span data-ttu-id="2479e-107">True の場合、パラメーターセットを使用するすべてのコマンドにパラメーターが指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2479e-107">If true, the parameter must appear in all commands that use the parameter set.</span></span>
  - <span data-ttu-id="2479e-108">False の場合、パラメーターセットを使用するすべてのコマンドでパラメーターを省略できます。</span><span class="sxs-lookup"><span data-stu-id="2479e-108">If false, the parameter is optional in all commands that use the parameter set.</span></span>
- <span data-ttu-id="2479e-109">[位置]</span><span class="sxs-lookup"><span data-stu-id="2479e-109">Position</span></span>
  - <span data-ttu-id="2479e-110">名前が指定されている場合は、パラメーター名が必要です。</span><span class="sxs-lookup"><span data-stu-id="2479e-110">If named, the parameter name is required.</span></span>
  - <span data-ttu-id="2479e-111">位置指定の場合、パラメーター名は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2479e-111">If positional, the parameter name is optional.</span></span> <span data-ttu-id="2479e-112">省略した場合、パラメーター値は、コマンド内の指定した位置にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="2479e-112">When it is omitted, the parameter value must be in the specified position in the command.</span></span> <span data-ttu-id="2479e-113">たとえば、値が position = "1" の場合、パラメーター値は、コマンドの最初のパラメーター値または無名のパラメーター値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2479e-113">For example, if the value is position="1", the parameter value must be the first or only unnamed parameter value in the command.</span></span>
- <span data-ttu-id="2479e-114">パイプライン入力</span><span class="sxs-lookup"><span data-stu-id="2479e-114">Pipeline Input</span></span>
  - <span data-ttu-id="2479e-115">True (ByValue) の場合は、パラメーターに入力をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="2479e-115">If true (ByValue), you can pipe input to the parameter.</span></span> <span data-ttu-id="2479e-116">入力は、プロパティ名とオブジェクトの型が予期される型と一致しない場合でも、パラメーターに関連付けられています ("バインド先")。</span><span class="sxs-lookup"><span data-stu-id="2479e-116">The input is associated with ("bound to") the parameter even if the property name and the object type do not match the expected type.</span></span>
    <span data-ttu-id="2479e-117">PowerShell パラメーターのバインドコンポーネントは、入力を正しい型に変換しようとし、型を変換できない場合にのみコマンドを失敗とします。</span><span class="sxs-lookup"><span data-stu-id="2479e-117">The PowerShell parameter binding components try to convert the input to the correct type and fail the command only when the type cannot be converted.</span></span> <span data-ttu-id="2479e-118">パラメーターセット内の1つのパラメーターのみを値で関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="2479e-118">Only one parameter in a parameter set can be associated by value.</span></span>
  - <span data-ttu-id="2479e-119">True (ByPropertyName) の場合は、パラメーターに入力をパイプ処理できます。</span><span class="sxs-lookup"><span data-stu-id="2479e-119">If true (ByPropertyName), you can pipe input to the parameter.</span></span> <span data-ttu-id="2479e-120">ただし、入力がパラメーターに関連付けられるのは、パラメーター名が入力オブジェクトのプロパティの名前と一致する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="2479e-120">However, the input is associated with the parameter only when the parameter name matches the name of a property of the input object.</span></span> <span data-ttu-id="2479e-121">たとえば、パラメーター名がの場合、 `Path` コマンドレットにパイプされたオブジェクトは、オブジェクトに path という名前のプロパティがある場合にのみ、そのパラメーターに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="2479e-121">For example, if the parameter name is `Path`, objects piped to the cmdlet are associated with that parameter only when the object has a property named path.</span></span>
  - <span data-ttu-id="2479e-122">True (ByValue, Byvalue) の場合は、プロパティ名または値によって入力をパラメーターにパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="2479e-122">If true (ByValue, ByPropertyName), you can pipe input to the parameter either by property name or by value.</span></span> <span data-ttu-id="2479e-123">パラメーターセット内の1つのパラメーターのみを値で関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="2479e-123">Only one parameter in a parameter set can be associated by value.</span></span>
  - <span data-ttu-id="2479e-124">False の場合、このパラメーターに入力をパイプすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2479e-124">If false, you cannot pipe input to this parameter.</span></span>
- <span data-ttu-id="2479e-125">グロビング</span><span class="sxs-lookup"><span data-stu-id="2479e-125">Globbing</span></span>
  - <span data-ttu-id="2479e-126">True の場合、ユーザーがパラメーター値に入力するテキストには、ワイルドカード文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2479e-126">If true, the text that the user types for the parameter value can include wildcard characters.</span></span>
  - <span data-ttu-id="2479e-127">False の場合、ユーザーがパラメーター値に入力するテキストには、ワイルドカード文字を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="2479e-127">If false, the text that the user types for the parameter value cannot include wildcard characters.</span></span>

### <a name="parameter-value-attributes"></a><span data-ttu-id="2479e-128">パラメーター値の属性</span><span class="sxs-lookup"><span data-stu-id="2479e-128">Parameter Value Attributes</span></span>

- <span data-ttu-id="2479e-129">必須</span><span class="sxs-lookup"><span data-stu-id="2479e-129">Required</span></span>
  - <span data-ttu-id="2479e-130">True の場合は、コマンドでパラメーターを使用するときに、指定した値を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2479e-130">If true, the specified value must be used whenever using the parameter in a command.</span></span>
  - <span data-ttu-id="2479e-131">False の場合、パラメーター値は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2479e-131">If false, the parameter value is optional.</span></span> <span data-ttu-id="2479e-132">通常、値は、列挙型など、パラメーターのいくつかの有効な値のいずれかである場合にのみ省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2479e-132">Typically, a value is optional only when it is one of several valid values for a parameter, such as in an enumerated type.</span></span>

<span data-ttu-id="2479e-133">パラメーター値の **必須** 属性が、パラメーターの **必須** 属性と異なります。</span><span class="sxs-lookup"><span data-stu-id="2479e-133">The **Required** attribute of a parameter value is different from the **Required** attribute of a parameter.</span></span>

<span data-ttu-id="2479e-134">パラメーターの required 属性は、コマンドレットを呼び出すときに、パラメーター (およびその値) を含める必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2479e-134">The required attribute of a parameter indicates whether the parameter (and its value) must be included when invoking the cmdlet.</span></span> <span data-ttu-id="2479e-135">これに対して、パラメーター値の必須の属性は、パラメーターがコマンドに含まれている場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="2479e-135">In contrast, the required attribute of a parameter value is used only when the parameter is included in the command.</span></span> <span data-ttu-id="2479e-136">パラメーターと共に特定の値を使用する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2479e-136">It indicates whether that particular value must be used with the parameter.</span></span>

<span data-ttu-id="2479e-137">通常、プレースホルダーであるパラメーター値は必須であり、リテラルであるパラメーター値は必須ではありません。これは、パラメーターで使用される可能性のあるいくつかの値の1つであるためです。</span><span class="sxs-lookup"><span data-stu-id="2479e-137">Typically, parameter values that are placeholders are required and parameter values that are literal are not required, because they are one of several values that might be used with the parameter.</span></span>

### <a name="gathering-syntax-information"></a><span data-ttu-id="2479e-138">構文情報を収集しています</span><span class="sxs-lookup"><span data-stu-id="2479e-138">Gathering Syntax Information</span></span>

1. <span data-ttu-id="2479e-139">コマンドレット名を使用して開始します。</span><span class="sxs-lookup"><span data-stu-id="2479e-139">Start with the cmdlet name.</span></span>

   ```
   SYNTAX
       Get-Tech
   ```

1. <span data-ttu-id="2479e-140">コマンドレットのすべてのパラメーターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="2479e-140">List all the parameters of the cmdlet.</span></span> <span data-ttu-id="2479e-141">`-`各パラメーター名の前にハイフン () (ASCII 45) を入力します。</span><span class="sxs-lookup"><span data-stu-id="2479e-141">Type a hyphen (`-`) (ASCII 45) before each parameter name.</span></span>
   <span data-ttu-id="2479e-142">パラメーターをパラメーターセットに分割します (一部のコマンドレットにはパラメーターセットが1つだけ含まれる場合があります)。</span><span class="sxs-lookup"><span data-stu-id="2479e-142">Separate the parameters into parameter sets (some cmdlets may have only one parameter set).</span></span> <span data-ttu-id="2479e-143">この例では、Get-Tech コマンドレットに2つのパラメーターセットがあります。</span><span class="sxs-lookup"><span data-stu-id="2479e-143">In this example the Get-Tech cmdlet has two parameter sets.</span></span>

   ```
   SYNTAX
       Get-Tech -name -type
       Get-Tech -ID -list -type
   ```

   <span data-ttu-id="2479e-144">コマンドレット名を使用して各パラメーターセットを開始します。</span><span class="sxs-lookup"><span data-stu-id="2479e-144">Start each parameter set with the cmdlet name.</span></span>

   <span data-ttu-id="2479e-145">最初に既定のパラメーターセットを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="2479e-145">List the default parameter set first.</span></span> <span data-ttu-id="2479e-146">既定のパラメーターは、コマンドレットクラスによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="2479e-146">The default parameter is specified by the cmdlet class.</span></span>

   <span data-ttu-id="2479e-147">最初に表示する必要がある位置指定パラメーターがない場合は、各パラメーターセットに対して、最初に一意のパラメーターをリストします。</span><span class="sxs-lookup"><span data-stu-id="2479e-147">For each parameter set, list its unique parameter first, unless there are positional parameters that must appear first.</span></span> <span data-ttu-id="2479e-148">前の例では、Name パラメーターと ID パラメーターは、2つのパラメーターセットの一意のパラメーターです (各パラメーターセットには、そのパラメーターセットに固有のパラメーターを1つ指定する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="2479e-148">In the previous example, the Name and ID parameters are unique parameters for the two parameter sets (each parameter set must have one parameter that is unique to that parameter set).</span></span> <span data-ttu-id="2479e-149">これにより、パラメーターセットに必要なパラメーターをユーザーが簡単に識別できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2479e-149">This makes it easier for users to identify what parameter they need to supply for the parameter set.</span></span>

   <span data-ttu-id="2479e-150">コマンドに表示される順序でパラメーターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="2479e-150">List the parameters in the order that they should appear in the command.</span></span> <span data-ttu-id="2479e-151">順序が問題にならない場合は、関連するパラメーターをまとめて表示するか、最も頻繁に使用されるパラメーターを最初に一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="2479e-151">If the order does not matter, list related parameters together, or list the most frequently used parameters first.</span></span>

   <span data-ttu-id="2479e-152">コマンドレットで入力処理がサポートされている場合は、WhatIf パラメーターと Confirm パラメーターを必ず指定してください。</span><span class="sxs-lookup"><span data-stu-id="2479e-152">Be sure to list the WhatIf and Confirm parameters if the cmdlet supports ShouldProcess.</span></span>

   <span data-ttu-id="2479e-153">構文図に共通パラメーター (Verbose、Debug、ErrorAction など) を一覧表示しません。</span><span class="sxs-lookup"><span data-stu-id="2479e-153">Do not list the common parameters (such as Verbose, Debug, and ErrorAction) in your syntax diagram.</span></span> <span data-ttu-id="2479e-154">`Get-Help`コマンドレットは、ヘルプトピックを表示するときに、その情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="2479e-154">The `Get-Help` cmdlet adds that information for you when it displays the Help topic.</span></span>

1. <span data-ttu-id="2479e-155">パラメーターの値を追加します。</span><span class="sxs-lookup"><span data-stu-id="2479e-155">Add the parameter values.</span></span> <span data-ttu-id="2479e-156">PowerShell では、パラメーター値は .NET 型によって表されます。</span><span class="sxs-lookup"><span data-stu-id="2479e-156">In PowerShell, parameter values are represented by their .NET type.</span></span>
   <span data-ttu-id="2479e-157">ただし、system.string の "文字列" のように、型名を省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="2479e-157">However, the type name can be abbreviated, such as "string" for System.String.</span></span>

   ```
   SYNTAX
       Get-Tech -name string -type basic advanced
       Get-Tech -ID int -list -type basic advanced
   ```

   <span data-ttu-id="2479e-158">**System.string の文字列や system.string** の **int** など、意味が明確でない限り、型を **省略します**。</span><span class="sxs-lookup"><span data-stu-id="2479e-158">Abbreviate types as long as their meaning is clear, such as **string** for **System.String** and **int** for **System.Int32**.</span></span>

   <span data-ttu-id="2479e-159">前の例のパラメーターなど、列挙のすべての値を一覧表示し `-type` ます。これは、 **basic** または **advanced** に設定できます。</span><span class="sxs-lookup"><span data-stu-id="2479e-159">List all values of enumerations, such as the `-type` parameter in the previous example, which can be set to **basic** or **advanced**.</span></span>

   <span data-ttu-id="2479e-160">スイッチパラメーター (前の例のなど) には `-list` 値がありません。</span><span class="sxs-lookup"><span data-stu-id="2479e-160">Switch parameters, such as `-list` in the previous example, do not have values.</span></span>

1. <span data-ttu-id="2479e-161">リテラルであるパラメーター値と比較して、プレースホルダーであるパラメーター値に山かっこを追加します。</span><span class="sxs-lookup"><span data-stu-id="2479e-161">Add angle brackets to parameters values that are placeholder, as compared to parameter values that are literals.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> -type basic advanced
       Get-Tech -ID <int> -list -type basic advanced
   ```

1. <span data-ttu-id="2479e-162">省略可能なパラメーターとその値を角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="2479e-162">Enclose optional parameters and their vales in square brackets.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

1. <span data-ttu-id="2479e-163">省略可能なパラメーター名 (位置指定パラメーターの場合) を角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="2479e-163">Enclose optional parameters names (for positional parameters) in square brackets.</span></span> <span data-ttu-id="2479e-164">次の例の名前パラメーターなど、位置指定のパラメーターの名前は、コマンドに含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2479e-164">The name for parameters that are positional, such as the Name parameter in the following example, do not have to be included in the command.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

1. <span data-ttu-id="2479e-165">パラメーター値に複数の値 (Name パラメーターの名前のリストなど) を含めることができる場合は、パラメーター値の直後に角かっこのペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="2479e-165">If a parameter value can contain multiple values, such as a list of names in the Name parameter, add a pair of square brackets directly following the parameter value.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type basic advanced]
       Get-Tech -ID <int[]> [-list] [-type basic advanced]
   ```

1. <span data-ttu-id="2479e-166">ユーザーがパラメーターまたはパラメーター値 (型パラメーターなど) から選択できる場合は、選択項目を中かっこで囲み、排他または記号 (;) で区切ります。</span><span class="sxs-lookup"><span data-stu-id="2479e-166">If the user can choose from parameters or parameter values, such as the Type parameter, enclose the choices in curly brackets and separate them with the exclusive OR symbol(;).</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

1. <span data-ttu-id="2479e-167">パラメーター値で引用符やかっこなどの特定の書式を使用する必要がある場合は、構文で形式を表示します。</span><span class="sxs-lookup"><span data-stu-id="2479e-167">If the parameter value must use specific formatting, such as quotation marks or parentheses, show the format in the syntax.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <"string[]"> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

## <a name="coding-the-syntax-diagram-xml"></a><span data-ttu-id="2479e-168">構文図の XML のコーディング</span><span class="sxs-lookup"><span data-stu-id="2479e-168">Coding the Syntax Diagram XML</span></span>

<span data-ttu-id="2479e-169">XML の構文ノードは、説明ノードの直後 (タグで終了) に開始され `</maml:description>` ます。</span><span class="sxs-lookup"><span data-stu-id="2479e-169">The syntax node of the XML begins immediately after the description node, which ends with the `</maml:description>` tag.</span></span> <span data-ttu-id="2479e-170">構文ダイアグラムで使用されるデータの収集の詳細については、「 [構文情報の収集](#gathering-syntax-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2479e-170">For information about gathering the data used in the syntax diagram, see [Gathering Syntax Information](#gathering-syntax-information).</span></span>

### <a name="adding-a-syntax-node"></a><span data-ttu-id="2479e-171">構文ノードの追加</span><span class="sxs-lookup"><span data-stu-id="2479e-171">Adding a Syntax Node</span></span>

<span data-ttu-id="2479e-172">コマンドレットのヘルプトピックに表示される構文図は、XML の構文ノードのデータから生成されます。</span><span class="sxs-lookup"><span data-stu-id="2479e-172">The syntax diagram displayed in the cmdlet Help topic is generated from the data in the syntax node of the XML.</span></span> <span data-ttu-id="2479e-173">構文ノードは、タグの場合はペアで囲まれ `<command:syntax>` ます。</span><span class="sxs-lookup"><span data-stu-id="2479e-173">The syntax node is enclosed in a pair if `<command:syntax>` tags.</span></span> <span data-ttu-id="2479e-174">コマンドレットの各パラメーターセットをタグのペアで囲んで指定 `<command:syntaxitem>` します。</span><span class="sxs-lookup"><span data-stu-id="2479e-174">With each parameter set of the cmdlet enclosed in a pair of `<command:syntaxitem>` tags.</span></span> <span data-ttu-id="2479e-175">追加できるタグの数に制限はありません `<command:syntaxitem>` 。</span><span class="sxs-lookup"><span data-stu-id="2479e-175">There is no limit to the number of `<command:syntaxitem>` tags that you can add.</span></span>

<span data-ttu-id="2479e-176">次の例は、2つのパラメーターセットの構文項目ノードを持つ構文ノードを示しています。</span><span class="sxs-lookup"><span data-stu-id="2479e-176">The following example shows a syntax node that has syntax item nodes for two parameter sets.</span></span>

```xml
<command:syntax>
  <command:syntaxItem>
    ...
    <!--Parameter Set 1 (default parameter set) parameters go here-->
    ...
  </command:syntaxItem>
  <command:syntaxItem>
    ...
    <!--Parameter Set 2 parameters go here-->
    ...
  </command:syntaxItem>
</command:syntax>
```

### <a name="adding-the-cmdlet-name-to-the-parameter-set-data"></a><span data-ttu-id="2479e-177">パラメーターセットデータへのコマンドレット名の追加</span><span class="sxs-lookup"><span data-stu-id="2479e-177">Adding the Cmdlet Name to the Parameter Set Data</span></span>

<span data-ttu-id="2479e-178">コマンドレットの各パラメーターセットは、[構文項目] ノードで指定します。</span><span class="sxs-lookup"><span data-stu-id="2479e-178">Each parameter set of the cmdlet is specified in a syntax item node.</span></span> <span data-ttu-id="2479e-179">各構文項目ノードは、 `<maml:name>` コマンドレットの名前を含むタグのペアで始まります。</span><span class="sxs-lookup"><span data-stu-id="2479e-179">Each syntax item node begins with a pair of `<maml:name>` tags that include the name of the cmdlet.</span></span>

<span data-ttu-id="2479e-180">次の例には、2つのパラメーターセットの構文項目ノードを持つ構文ノードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2479e-180">The following example includes a syntax node that has syntax item nodes for two parameter sets.</span></span>

```xml
<command:syntax>
  <command:syntaxItem>
    <maml:name>Cmdlet-Name</maml:name>
  </command:syntaxItem>
  <command:syntaxItem>
    <maml:name>Cmdlet-Name</maml:name>
  </command:syntaxItem>
</command:syntax>
```

### <a name="adding-parameters"></a><span data-ttu-id="2479e-181">パラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="2479e-181">Adding Parameters</span></span>

<span data-ttu-id="2479e-182">構文項目ノードに追加された各パラメーターは、1組のタグ内で指定され `<command:parameter>` ます。</span><span class="sxs-lookup"><span data-stu-id="2479e-182">Each parameter added to the syntax item node is specified within a pair of `<command:parameter>` tags.</span></span> <span data-ttu-id="2479e-183">`<command:parameter>`パラメーターセットに含まれる各パラメーターには、PowerShell によって提供される共通パラメーターを除き、1組のタグが必要です。</span><span class="sxs-lookup"><span data-stu-id="2479e-183">You need a pair of `<command:parameter>` tags for each parameter included in the parameter set, with the exception of the common parameters that are provided by PowerShell.</span></span>

<span data-ttu-id="2479e-184">開始タグの属性によって、 `<command:parameter>` 構文図にパラメーターがどのように表示されるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="2479e-184">The attributes of the opening `<command:parameter>` tag determine how the parameter appears in the syntax diagram.</span></span> <span data-ttu-id="2479e-185">パラメーター属性の詳細については、「 [パラメーター属性](#parameter-attributes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2479e-185">For information on parameter attributes, see [Parameter Attributes](#parameter-attributes).</span></span>

> [!NOTE]
> <span data-ttu-id="2479e-186">タグは、 `<command:parameter>` `<maml:description>` コンテンツが表示されない子要素をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2479e-186">The `<command:parameter>` tag supports a child element `<maml:description>` whose content is never displayed.</span></span> <span data-ttu-id="2479e-187">パラメーターの説明は、XML のパラメーターノードで指定します。</span><span class="sxs-lookup"><span data-stu-id="2479e-187">The parameter descriptions are specified in the parameter node of the XML.</span></span> <span data-ttu-id="2479e-188">構文項目兆しとパラメーターノードの情報が矛盾しないようにするには、を省略し `<maml:description>` ます (または空のままにします。</span><span class="sxs-lookup"><span data-stu-id="2479e-188">To avoid inconsistencies between the information in the syntax item bodes and the parameter node, omit the (`<maml:description>` or leave it empty.</span></span>

<span data-ttu-id="2479e-189">次の例には、2つのパラメーターを持つパラメーターセットの構文項目ノードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2479e-189">The following example includes a syntax item node for a parameter set with two parameters.</span></span>

```xml
<command:syntaxItem>
  <maml:name>Cmdlet-Name</maml:name>
  <command:parameter required="true" globbing="true"
    pipelineInput="true (ByValue)" position="1">
    <maml:name>ParameterName1</maml:name>
    <command:parameterValue required="true">
      string[]
    </command:parameterValue>
  </command:parameter>
  <command:parameter required="true" globbing="true"
    pipelineInput="true (ByPropertyName)">
    <maml:name>ParameterName2</maml:name>
    <command:parameterValue required="true">
      int32[]
    </command:parameterValue>
  </command:parameter>
</command:syntaxItem>
```
