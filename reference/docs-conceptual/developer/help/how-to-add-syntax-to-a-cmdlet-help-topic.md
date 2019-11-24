---
title: コマンドレットに構文を追加する方法に関するヘルプトピック |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0c6d03f-1c1a-43d8-928e-e3290e90e0bc
caps.latest.revision: 5
ms.openlocfilehash: 0210b5ed3104777541692a0e78e7d3b16f9c8256
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361211"
---
# <a name="how-to-add-syntax-to-a-cmdlet-help-topic"></a><span data-ttu-id="46106-102">コマンドレットのヘルプ トピックに構文を追加する方法</span><span class="sxs-lookup"><span data-stu-id="46106-102">How to Add Syntax to a Cmdlet Help Topic</span></span>

<span data-ttu-id="46106-103">コマンドレットのヘルプファイルで構文ダイアグラムの XML のコーディングを開始する前に、このセクションを参照して、パラメーター属性など、指定する必要があるデータの種類と、そのデータが構文図に表示される方法を明確に把握してください。「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46106-103">Before you start to code the XML for the syntax diagram in the cmdlet Help file, read this section to get a clear picture of the kind of data you need to provide, such as the parameter attributes, and how that data is displayed in the syntax diagram..</span></span>

### <a name="parameter-attributes"></a><span data-ttu-id="46106-104">パラメーター属性</span><span class="sxs-lookup"><span data-stu-id="46106-104">Parameter Attributes</span></span>

- <span data-ttu-id="46106-105">必須</span><span class="sxs-lookup"><span data-stu-id="46106-105">Required</span></span>

  - <span data-ttu-id="46106-106">True の場合、パラメーターセットを使用するすべてのコマンドにパラメーターが指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="46106-106">If true, the parameter must appear in all commands that use the parameter set.</span></span>

  - <span data-ttu-id="46106-107">False の場合、パラメーターセットを使用するすべてのコマンドでパラメーターを省略できます。</span><span class="sxs-lookup"><span data-stu-id="46106-107">If false, the parameter is optional in all commands that use the parameter set.</span></span>

- <span data-ttu-id="46106-108">位置</span><span class="sxs-lookup"><span data-stu-id="46106-108">Position</span></span>

  - <span data-ttu-id="46106-109">名前が指定されている場合は、パラメーター名が必要です。</span><span class="sxs-lookup"><span data-stu-id="46106-109">If named, the parameter name is required.</span></span>

  - <span data-ttu-id="46106-110">位置指定の場合、パラメーター名は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="46106-110">If positional, the parameter name is optional.</span></span> <span data-ttu-id="46106-111">省略した場合、パラメーター値は、コマンド内の指定した位置にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="46106-111">When it is omitted, the parameter value must be in the specified position in the command.</span></span> <span data-ttu-id="46106-112">たとえば、値が position = "1" の場合、パラメーター値は、コマンドの最初のパラメーター値または無名のパラメーター値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="46106-112">For example, if the value is position="1", the parameter value must be the first or only unnamed parameter value in the command.</span></span>

- <span data-ttu-id="46106-113">パイプラインの入力</span><span class="sxs-lookup"><span data-stu-id="46106-113">Pipeline Input</span></span>

  - <span data-ttu-id="46106-114">True (ByValue) の場合は、パラメーターに入力をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="46106-114">If true (ByValue), you can pipe input to the parameter.</span></span> <span data-ttu-id="46106-115">入力は、プロパティ名とオブジェクトの型が予期される型と一致しない場合でも、パラメーターに関連付けられています ("バインド先")。</span><span class="sxs-lookup"><span data-stu-id="46106-115">The input is associated with ("bound to") the parameter even if the property name and the object type do not match the expected type.</span></span> <span data-ttu-id="46106-116">Windows PowerShell とはパラメーターバインドコンポーネントは、入力を正しい型に変換しようとし、型を変換できない場合にのみコマンドを失敗とします。</span><span class="sxs-lookup"><span data-stu-id="46106-116">The Windows PowerShell? parameter binding components try to convert the input to the correct type and fail the command only when the type cannot be converted.</span></span> <span data-ttu-id="46106-117">パラメーターセット内の1つのパラメーターのみを値で関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="46106-117">Only one parameter in a parameter set can be associated by value.</span></span>

  - <span data-ttu-id="46106-118">True (ByPropertyName) の場合は、パラメーターに入力をパイプ処理できます。</span><span class="sxs-lookup"><span data-stu-id="46106-118">If true (ByPropertyName), you can pipe input to the parameter.</span></span> <span data-ttu-id="46106-119">ただし、入力がパラメーターに関連付けられるのは、パラメーター名が入力オブジェクトのプロパティの名前と一致する場合のみです。</span><span class="sxs-lookup"><span data-stu-id="46106-119">However, the input is associated with the parameter only when the parameter name matches the name of a property of the input object.</span></span> <span data-ttu-id="46106-120">たとえば、パラメーター名が `Path`の場合、コマンドレットにパイプされたオブジェクトは、オブジェクトに path という名前のプロパティがある場合にのみ、そのパラメーターに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="46106-120">For example, if the parameter name is `Path`, objects piped to the cmdlet are associated with that parameter only when the object has a property named path.</span></span>

  - <span data-ttu-id="46106-121">True (ByValue, Byvalue) の場合は、プロパティ名または値によって入力をパラメーターにパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="46106-121">If true (ByValue, ByPropertyName), you can pipe input to the parameter either by property name or by value.</span></span> <span data-ttu-id="46106-122">パラメーターセット内の1つのパラメーターのみを値で関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="46106-122">Only one parameter in a parameter set can be associated by value.</span></span>

  - <span data-ttu-id="46106-123">False の場合、このパラメーターに入力をパイプすることはできません。</span><span class="sxs-lookup"><span data-stu-id="46106-123">If false, you cannot pipe input to this parameter.</span></span>

- <span data-ttu-id="46106-124">グロビング</span><span class="sxs-lookup"><span data-stu-id="46106-124">Globbing</span></span>

  - <span data-ttu-id="46106-125">True の場合、ユーザーがパラメーター値に入力するテキストには、ワイルドカード文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="46106-125">If true, the text that the user types for the parameter value can include wildcard characters.</span></span>

  - <span data-ttu-id="46106-126">False の場合、ユーザーがパラメーター値に入力するテキストには、ワイルドカード文字を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="46106-126">If false, the text that the user types for the parameter value cannot include wildcard characters.</span></span>

### <a name="parameter-value-attributes"></a><span data-ttu-id="46106-127">パラメーター値の属性</span><span class="sxs-lookup"><span data-stu-id="46106-127">Parameter Value Attributes</span></span>

- <span data-ttu-id="46106-128">必須</span><span class="sxs-lookup"><span data-stu-id="46106-128">Required</span></span>

  - <span data-ttu-id="46106-129">True の場合は、コマンドでパラメーターを使用するときに、指定した値を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46106-129">If true, the specified value must be used whenever using the parameter in a command.</span></span>

  - <span data-ttu-id="46106-130">False の場合、パラメーター値は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="46106-130">If false, the parameter value is optional.</span></span> <span data-ttu-id="46106-131">通常、値は、列挙型など、パラメーターのいくつかの有効な値のいずれかである場合にのみ省略可能です。</span><span class="sxs-lookup"><span data-stu-id="46106-131">Typically, a value is optional only when it is one of several valid values for a parameter, such as in an enumerated type.</span></span>

<span data-ttu-id="46106-132">パラメーター値の必須属性が、パラメーターの必須属性と異なります。</span><span class="sxs-lookup"><span data-stu-id="46106-132">The Required attribute of a parameter value is different from the Required attribute of a parameter.</span></span>

<span data-ttu-id="46106-133">パラメーターの required 属性は、コマンドレットを呼び出すときに、パラメーター (およびその値) を含める必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="46106-133">The required attribute of a parameter indicates whether the parameter (and its value) must be included when invoking the cmdlet.</span></span> <span data-ttu-id="46106-134">これに対して、パラメーター値の必須の属性は、パラメーターがコマンドに含まれている場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="46106-134">In contrast, the required attribute of a parameter value is used only when the parameter is included in the command.</span></span> <span data-ttu-id="46106-135">パラメーターと共に特定の値を使用する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="46106-135">It indicates whether that particular value must be used with the parameter.</span></span>

<span data-ttu-id="46106-136">通常、プレースホルダーであるパラメーター値は必須であり、リテラルであるパラメーター値は必須ではありません。これは、パラメーターで使用される可能性のあるいくつかの値の1つであるためです。</span><span class="sxs-lookup"><span data-stu-id="46106-136">Typically, parameter values that are placeholders are required and parameter values that are literal are not required, because they are one of several values that might be used with the parameter.</span></span>

### <a name="gathering-syntax-information"></a><span data-ttu-id="46106-137">構文情報を収集しています</span><span class="sxs-lookup"><span data-stu-id="46106-137">Gathering Syntax Information</span></span>

1. <span data-ttu-id="46106-138">コマンドレット名を使用して開始します。</span><span class="sxs-lookup"><span data-stu-id="46106-138">Start with the cmdlet name.</span></span>

   ```
   SYNTAX
       Get-Tech
   ```

2. <span data-ttu-id="46106-139">コマンドレットのすべてのパラメーターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="46106-139">List all the parameters of the cmdlet.</span></span> <span data-ttu-id="46106-140">各パラメーター名の前にダッシュ ("ダッシュ" または "マイナス記号" (ASCII 45) とも呼ばれる) を入力します。</span><span class="sxs-lookup"><span data-stu-id="46106-140">Type a dash (also known as a "dash" or "minus sign" (ASCII 45) before each parameter name.</span></span> <span data-ttu-id="46106-141">パラメーターをパラメーターセットに分割します (一部のコマンドレットにはパラメーターセットが1つだけ含まれる場合があります)。</span><span class="sxs-lookup"><span data-stu-id="46106-141">Separate the parameters into parameter sets (some cmdlets may have only one parameter set).</span></span> <span data-ttu-id="46106-142">この例では、Get-help コマンドレットに2つのパラメーターセットがあります。</span><span class="sxs-lookup"><span data-stu-id="46106-142">In this example the Get-Tech cmdlet has two parameter sets.</span></span>

   ```
   SYNTAX
       Get-Tech -name -type
       Get-Tech -ID -list -type
   ```

   <span data-ttu-id="46106-143">コマンドレット名を使用して各パラメーターセットを開始します。</span><span class="sxs-lookup"><span data-stu-id="46106-143">Start each parameter set with the cmdlet name.</span></span>

   <span data-ttu-id="46106-144">最初に既定のパラメーターセットを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="46106-144">List the default parameter set first.</span></span> <span data-ttu-id="46106-145">既定のパラメーターは、コマンドレットクラスによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="46106-145">The default parameter is specified by the cmdlet class.</span></span>

   <span data-ttu-id="46106-146">最初に表示する必要がある位置指定パラメーターがない場合は、各パラメーターセットに対して、最初に一意のパラメーターをリストします。</span><span class="sxs-lookup"><span data-stu-id="46106-146">For each parameter set, list its unique parameter first, unless there are positional parameters that must appear first.</span></span> <span data-ttu-id="46106-147">前の例では、Name パラメーターと ID パラメーターは、2つのパラメーターセットの一意のパラメーターです (各パラメーターセットには、そのパラメーターセットに固有のパラメーターを1つ指定する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="46106-147">In the previous example, the Name and ID parameters are unique parameters for the two parameter sets (each parameter set must have one parameter that is unique to that parameter set).</span></span> <span data-ttu-id="46106-148">これにより、パラメーターセットに必要なパラメーターをユーザーが簡単に識別できるようになります。</span><span class="sxs-lookup"><span data-stu-id="46106-148">This makes it easier for users to identify what parameter they need to supply for the parameter set.</span></span>

   <span data-ttu-id="46106-149">コマンドに表示される順序でパラメーターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="46106-149">List the parameters in the order that they should appear in the command.</span></span> <span data-ttu-id="46106-150">順序が問題にならない場合は、関連するパラメーターをまとめて表示するか、最も頻繁に使用されるパラメーターを最初に一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="46106-150">If the order does not matter, list related parameters together, or list the most frequently used parameters first.</span></span>

   <span data-ttu-id="46106-151">コマンドレットで入力処理がサポートされている場合は、WhatIf パラメーターと Confirm パラメーターを必ず指定してください。</span><span class="sxs-lookup"><span data-stu-id="46106-151">Be sure to list the WhatIf and Confirm parameters if the cmdlet supports ShouldProcess.</span></span>

   <span data-ttu-id="46106-152">構文図に共通パラメーター (Verbose、Debug、ErrorAction など) を一覧表示しません。</span><span class="sxs-lookup"><span data-stu-id="46106-152">Do not list the common parameters (such as Verbose, Debug, and ErrorAction) in your syntax diagram.</span></span> <span data-ttu-id="46106-153">`Get-Help` コマンドレットは、ヘルプトピックを表示するときに、その情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="46106-153">The `Get-Help` cmdlet adds that information for you when it displays the Help topic.</span></span>

3. <span data-ttu-id="46106-154">パラメーターの値を追加します。</span><span class="sxs-lookup"><span data-stu-id="46106-154">Add the parameter values.</span></span> <span data-ttu-id="46106-155">Windows PowerShell では、パラメーター値は .NET 型によって表されます。</span><span class="sxs-lookup"><span data-stu-id="46106-155">In Windows PowerShell?, parameter values are represented by their .NET type.</span></span> <span data-ttu-id="46106-156">ただし、system.string の "文字列" のように、型名を省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="46106-156">However, the type name can be abbreviated, such as "string" for System.String.</span></span>

   ```
   SYNTAX
       Get-Tech -name string -type basic advanced
       Get-Tech -ID int -list -type basic advanced
   ```

   <span data-ttu-id="46106-157">System.string の場合は "string"、system.string の場合は "int" など、意味が明確でない限り型を省略します。</span><span class="sxs-lookup"><span data-stu-id="46106-157">Abbreviate types as long as their meaning is clear, such as "string" for System.String and "int" for System.Int32.</span></span>

   <span data-ttu-id="46106-158">前の例の-type パラメーターなど、列挙のすべての値を一覧表示します。これは、"basic" または "advanced" に設定できます。</span><span class="sxs-lookup"><span data-stu-id="46106-158">List all values of enumerations, such as the -type parameter in the previous example, which can be set to "basic" or "advanced".</span></span>

   <span data-ttu-id="46106-159">前の例の-list などのスイッチパラメーターには値がありません。</span><span class="sxs-lookup"><span data-stu-id="46106-159">Switch parameters, such as -list in the previous example, do not have values.</span></span>

4. <span data-ttu-id="46106-160">リテラルであるパラメーター値と比較して、プレースホルダーであるパラメーター値に山かっこを追加します。</span><span class="sxs-lookup"><span data-stu-id="46106-160">Add angle brackets to parameters values that are placeholder, as compared to parameter values that are literals.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> -type basic advanced
       Get-Tech -ID <int> -list -type basic advanced
   ```

5. <span data-ttu-id="46106-161">省略可能なパラメーターとその値を角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="46106-161">Enclose optional parameters and their vales in square brackets.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

6. <span data-ttu-id="46106-162">省略可能なパラメーター名 (位置指定パラメーターの場合) を角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="46106-162">Enclose optional parameters names (for positional parameters) in square brackets.</span></span> <span data-ttu-id="46106-163">次の例の名前パラメーターなど、位置指定のパラメーターの名前は、コマンドに含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="46106-163">The name for parameters that are positional, such as the Name parameter in the following example, do not have to be included in the command.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

7. <span data-ttu-id="46106-164">パラメーター値に複数の値 (Name パラメーターの名前のリストなど) を含めることができる場合は、パラメーター値の直後に角かっこのペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="46106-164">If a parameter value can contain multiple values, such as a list of names in the Name parameter, add a pair of square brackets directly following the parameter value.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type basic advanced]
       Get-Tech -ID <int[]> [-list] [-type basic advanced]
   ```

8. <span data-ttu-id="46106-165">ユーザーがパラメーターまたはパラメーター値 (型パラメーターなど) から選択できる場合は、選択項目を中かっこで囲み、排他または記号 (;) で区切ります。</span><span class="sxs-lookup"><span data-stu-id="46106-165">If the user can choose from parameters or parameter values, such as the Type parameter, enclose the choices in curly brackets and separate them with the exclusive OR symbol(;).</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

9. <span data-ttu-id="46106-166">パラメーター値で引用符やかっこなどの特定の書式を使用する必要がある場合は、構文で形式を表示します。</span><span class="sxs-lookup"><span data-stu-id="46106-166">If the parameter value must use specific formatting, such as quotation marks or parentheses, show the format in the syntax.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <"string[]"> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

## <a name="coding-the-syntax-diagram-xml"></a><span data-ttu-id="46106-167">構文図の XML のコーディング</span><span class="sxs-lookup"><span data-stu-id="46106-167">Coding the Syntax Diagram XML</span></span>

<span data-ttu-id="46106-168">XML の構文ノードは説明ノードの直後に始まり、\</maml: description > タグで終わります。</span><span class="sxs-lookup"><span data-stu-id="46106-168">The syntax node of the XML begins immediately after the description node, which ends with the \</maml:description> tag.</span></span> <span data-ttu-id="46106-169">構文ダイアグラムで使用されるデータの収集の詳細については、「[構文情報の収集](#gathering-syntax-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46106-169">For information about gathering the data used in the syntax diagram, see [Gathering Syntax Information](#gathering-syntax-information).</span></span>

### <a name="adding-a-syntax-node"></a><span data-ttu-id="46106-170">構文ノードの追加</span><span class="sxs-lookup"><span data-stu-id="46106-170">Adding a Syntax Node</span></span>

<span data-ttu-id="46106-171">コマンドレットのヘルプトピックに表示される構文図は、XML の構文ノードのデータから生成されます。</span><span class="sxs-lookup"><span data-stu-id="46106-171">The syntax diagram displayed in the cmdlet Help topic is generated from the data in the syntax node of the XML.</span></span> <span data-ttu-id="46106-172">構文ノードは、\<コマンド: 構文 > タグの場合、ペアで囲まれます。</span><span class="sxs-lookup"><span data-stu-id="46106-172">The syntax node is enclosed in a pair if \<command:syntax> tags.</span></span> <span data-ttu-id="46106-173">コマンドレットの各パラメーターセットを \<コマンドのペア > タグと組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="46106-173">With each parameter set of the cmdlet enclosed in a pair of \<command:syntaxitem> tags.</span></span> <span data-ttu-id="46106-174">\<コマンドの数に制限はありません: syntaxitem > タグを追加できます。</span><span class="sxs-lookup"><span data-stu-id="46106-174">There is no limit to the number of \<command:syntaxitem> tags that you can add.</span></span>

<span data-ttu-id="46106-175">次の例は、2つのパラメーターセットの構文項目ノードを持つ構文ノードを示しています。</span><span class="sxs-lookup"><span data-stu-id="46106-175">The following example shows a syntax node that has syntax item nodes for two parameter sets.</span></span>

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

### <a name="adding-the-cmdlet-name-to-the-parameter-set-data"></a><span data-ttu-id="46106-176">パラメーターセットデータへのコマンドレット名の追加</span><span class="sxs-lookup"><span data-stu-id="46106-176">Adding the Cmdlet Name to the Parameter Set Data</span></span>

<span data-ttu-id="46106-177">コマンドレットの各パラメーターセットは、[構文項目] ノードで指定します。</span><span class="sxs-lookup"><span data-stu-id="46106-177">Each parameter set of the cmdlet is specified in a syntax item node.</span></span> <span data-ttu-id="46106-178">各構文項目ノードは、コマンドレットの名前を含む \<maml: name > タグのペアで始まります。</span><span class="sxs-lookup"><span data-stu-id="46106-178">Each syntax item node begins with a pair of \<maml:name> tags that include the name of the cmdlet.</span></span>

<span data-ttu-id="46106-179">次の例には、2つのパラメーターセットの構文項目ノードを持つ構文ノードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="46106-179">The following example includes a syntax node that has syntax item nodes for two parameter sets.</span></span>

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

### <a name="adding-parameters"></a><span data-ttu-id="46106-180">パラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="46106-180">Adding Parameters</span></span>

<span data-ttu-id="46106-181">構文項目ノードに追加された各パラメーターは、\<コマンドパラメーター > タグのペア内で指定されます。</span><span class="sxs-lookup"><span data-stu-id="46106-181">Each parameter added to the syntax item node is specified within a pair of \<command:parameter> tags.</span></span> <span data-ttu-id="46106-182">パラメーターセットに含まれる各パラメーターに対して、パラメーター > の \<コマンドのペアが必要です。ただし、Windows PowerShell で提供される共通のパラメーターは除きます。</span><span class="sxs-lookup"><span data-stu-id="46106-182">You need a pair of \<command:parameter> tags for each parameter included in the parameter set, with the exception of the common parameters that are provided by Windows PowerShell?.</span></span>

<span data-ttu-id="46106-183">開始 \<コマンド: parameter > タグの属性によって、構文図にパラメーターがどのように表示されるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="46106-183">The attributes of the opening \<command:parameter> tag determine how the parameter appears in the syntax diagram.</span></span> <span data-ttu-id="46106-184">パラメーター属性の詳細については、「[パラメーター属性](#parameter-attributes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46106-184">For information on parameter attributes, see [Parameter Attributes](#parameter-attributes).</span></span>

> [!NOTE]
> <span data-ttu-id="46106-185">\<コマンド: parameter > タグは、コンテンツが表示されない maml: description > \<子要素をサポートします。</span><span class="sxs-lookup"><span data-stu-id="46106-185">The \<command:parameter> tag supports a child element \<maml:description> whose content is never displayed.</span></span> <span data-ttu-id="46106-186">パラメーターの説明は、XML のパラメーターノードで指定します。</span><span class="sxs-lookup"><span data-stu-id="46106-186">The parameter descriptions are specified in the parameter node of the XML.</span></span> <span data-ttu-id="46106-187">構文項目兆しとパラメーターノードの情報が矛盾しないようにするには、(\<maml: description > を省略するか、空のままにします。</span><span class="sxs-lookup"><span data-stu-id="46106-187">To avoid inconsistencies between the information in the syntax item bodes and the parameter node, omit the (\<maml:description> or leave it empty.</span></span>

<span data-ttu-id="46106-188">次の例には、2つのパラメーターを持つパラメーターセットの構文項目ノードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="46106-188">The following example includes a syntax item node for a parameter set with two parameters.</span></span>

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
