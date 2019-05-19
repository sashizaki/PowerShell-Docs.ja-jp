---
title: コマンドレットのヘルプ トピックに構文を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0c6d03f-1c1a-43d8-928e-e3290e90e0bc
caps.latest.revision: 5
ms.openlocfilehash: 0210b5ed3104777541692a0e78e7d3b16f9c8256
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855131"
---
# <a name="how-to-add-syntax-to-a-cmdlet-help-topic"></a><span data-ttu-id="c99cb-102">コマンドレットのヘルプ トピックに構文を追加する方法</span><span class="sxs-lookup"><span data-stu-id="c99cb-102">How to Add Syntax to a Cmdlet Help Topic</span></span>

<span data-ttu-id="c99cb-103">コマンドレットのヘルプ ファイルで構文ダイアグラムの XML コードを開始する前に、パラメーターの属性と構文ダイアグラムでそのデータを表示する方法など、提供する必要があるデータの種類を明確に把握するには、このセクションを読む.</span><span class="sxs-lookup"><span data-stu-id="c99cb-103">Before you start to code the XML for the syntax diagram in the cmdlet Help file, read this section to get a clear picture of the kind of data you need to provide, such as the parameter attributes, and how that data is displayed in the syntax diagram..</span></span>

### <a name="parameter-attributes"></a><span data-ttu-id="c99cb-104">パラメーター属性</span><span class="sxs-lookup"><span data-stu-id="c99cb-104">Parameter Attributes</span></span>

- <span data-ttu-id="c99cb-105">必須</span><span class="sxs-lookup"><span data-stu-id="c99cb-105">Required</span></span>

  - <span data-ttu-id="c99cb-106">True の場合、パラメーター セットを使用するすべてのコマンドで、パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="c99cb-106">If true, the parameter must appear in all commands that use the parameter set.</span></span>

  - <span data-ttu-id="c99cb-107">False の場合、パラメーターはパラメーター セットを使用するすべてのコマンドでは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c99cb-107">If false, the parameter is optional in all commands that use the parameter set.</span></span>

- <span data-ttu-id="c99cb-108">位置</span><span class="sxs-lookup"><span data-stu-id="c99cb-108">Position</span></span>

  - <span data-ttu-id="c99cb-109">という名前の場合、パラメーター名が必要です。</span><span class="sxs-lookup"><span data-stu-id="c99cb-109">If named, the parameter name is required.</span></span>

  - <span data-ttu-id="c99cb-110">場合、位置指定パラメーター名は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c99cb-110">If positional, the parameter name is optional.</span></span> <span data-ttu-id="c99cb-111">省略すると、パラメーターの値は、コマンドで指定された位置にあります。</span><span class="sxs-lookup"><span data-stu-id="c99cb-111">When it is omitted, the parameter value must be in the specified position in the command.</span></span> <span data-ttu-id="c99cb-112">場合は、値は位置の「1」、たとえば、=、パラメーター値には初または唯一無名のコマンドのパラメーターの値。</span><span class="sxs-lookup"><span data-stu-id="c99cb-112">For example, if the value is position="1", the parameter value must be the first or only unnamed parameter value in the command.</span></span>

- <span data-ttu-id="c99cb-113">パイプラインの入力</span><span class="sxs-lookup"><span data-stu-id="c99cb-113">Pipeline Input</span></span>

  - <span data-ttu-id="c99cb-114">True (ByValue) パラメーターへの入力をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-114">If true (ByValue), you can pipe input to the parameter.</span></span> <span data-ttu-id="c99cb-115">入力が関連付けられている (「バインドする」) で、プロパティ名とオブジェクトの種類も予期される型が一致しない場合でもパラメーター。</span><span class="sxs-lookup"><span data-stu-id="c99cb-115">The input is associated with ("bound to") the parameter even if the property name and the object type do not match the expected type.</span></span> <span data-ttu-id="c99cb-116">Windows PowerShell ですか。コンポーネントのパラメーター バインドしようと適切な型への入力を変換し、型を変換できない場合にのみコマンドが失敗します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-116">The Windows PowerShell? parameter binding components try to convert the input to the correct type and fail the command only when the type cannot be converted.</span></span> <span data-ttu-id="c99cb-117">パラメーター セットで 1 つだけのパラメーター値で関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-117">Only one parameter in a parameter set can be associated by value.</span></span>

  - <span data-ttu-id="c99cb-118">True の場合 (ByPropertyName) パラメーターへの入力をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-118">If true (ByPropertyName), you can pipe input to the parameter.</span></span> <span data-ttu-id="c99cb-119">ただし、入力は、パラメーター名が、入力オブジェクトのプロパティの名前と一致する場合にのみ、パラメーターに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-119">However, the input is associated with the parameter only when the parameter name matches the name of a property of the input object.</span></span> <span data-ttu-id="c99cb-120">たとえば、パラメーター名は`Path`オブジェクトがパスをという名前のプロパティがある場合のみをコマンドレットにパイプ処理されたオブジェクトがそのパラメーターと関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-120">For example, if the parameter name is `Path`, objects piped to the cmdlet are associated with that parameter only when the object has a property named path.</span></span>

  - <span data-ttu-id="c99cb-121">場合は true (ByValue、ByPropertyName) がプロパティ名または値のいずれかのパラメーターへの入力をパイプ処理できます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-121">If true (ByValue, ByPropertyName), you can pipe input to the parameter either by property name or by value.</span></span> <span data-ttu-id="c99cb-122">パラメーター セットで 1 つだけのパラメーター値で関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-122">Only one parameter in a parameter set can be associated by value.</span></span>

  - <span data-ttu-id="c99cb-123">False の場合は、このパラメーターへの入力をパイプすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c99cb-123">If false, you cannot pipe input to this parameter.</span></span>

- <span data-ttu-id="c99cb-124">グロビング</span><span class="sxs-lookup"><span data-stu-id="c99cb-124">Globbing</span></span>

  - <span data-ttu-id="c99cb-125">True の場合、ユーザーがパラメーター値を入力するテキストは、ワイルドカード文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-125">If true, the text that the user types for the parameter value can include wildcard characters.</span></span>

  - <span data-ttu-id="c99cb-126">False の場合、ユーザーがパラメーター値を入力するテキストは、ワイルドカード文字を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="c99cb-126">If false, the text that the user types for the parameter value cannot include wildcard characters.</span></span>

### <a name="parameter-value-attributes"></a><span data-ttu-id="c99cb-127">パラメーター値の属性</span><span class="sxs-lookup"><span data-stu-id="c99cb-127">Parameter Value Attributes</span></span>

- <span data-ttu-id="c99cb-128">必須</span><span class="sxs-lookup"><span data-stu-id="c99cb-128">Required</span></span>

  - <span data-ttu-id="c99cb-129">True の場合は、コマンドで、パラメーターを使用するたびに、指定した値が使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c99cb-129">If true, the specified value must be used whenever using the parameter in a command.</span></span>

  - <span data-ttu-id="c99cb-130">False の場合、パラメーターの値は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c99cb-130">If false, the parameter value is optional.</span></span> <span data-ttu-id="c99cb-131">通常、ある場合にのみ、パラメーターのいくつかの有効な値のいずれかのように列挙型では、値は省略できます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-131">Typically, a value is optional only when it is one of several valid values for a parameter, such as in an enumerated type.</span></span>

<span data-ttu-id="c99cb-132">パラメーターの値の必須の属性は、パラメーターの必須の属性と異なります。</span><span class="sxs-lookup"><span data-stu-id="c99cb-132">The Required attribute of a parameter value is different from the Required attribute of a parameter.</span></span>

<span data-ttu-id="c99cb-133">パラメーターの必須の属性は、かどうか、パラメーター (とその値) 含める必要がある、コマンドレットを呼び出すときを示します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-133">The required attribute of a parameter indicates whether the parameter (and its value) must be included when invoking the cmdlet.</span></span> <span data-ttu-id="c99cb-134">これに対し、必要なパラメーターの値の属性は、コマンドのパラメーターが含まれている場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-134">In contrast, the required attribute of a parameter value is used only when the parameter is included in the command.</span></span> <span data-ttu-id="c99cb-135">これは、その特定の値をパラメーターと共に使用する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-135">It indicates whether that particular value must be used with the parameter.</span></span>

<span data-ttu-id="c99cb-136">通常、プレース ホルダーをパラメーター値が必要ですし、リテラルのパラメーター値のパラメーターと共に使用されるいくつかの値のいずれかがいるため、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="c99cb-136">Typically, parameter values that are placeholders are required and parameter values that are literal are not required, because they are one of several values that might be used with the parameter.</span></span>

### <a name="gathering-syntax-information"></a><span data-ttu-id="c99cb-137">構文情報の収集</span><span class="sxs-lookup"><span data-stu-id="c99cb-137">Gathering Syntax Information</span></span>

1. <span data-ttu-id="c99cb-138">コマンドレット名で始まります。</span><span class="sxs-lookup"><span data-stu-id="c99cb-138">Start with the cmdlet name.</span></span>

   ```
   SYNTAX
       Get-Tech
   ```

2. <span data-ttu-id="c99cb-139">コマンドレットのすべてのパラメーターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-139">List all the parameters of the cmdlet.</span></span> <span data-ttu-id="c99cb-140">入力をダッシュ ("dash"または""(ASCII 45) 前にマイナス記号各パラメーター名とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-140">Type a dash (also known as a "dash" or "minus sign" (ASCII 45) before each parameter name.</span></span> <span data-ttu-id="c99cb-141">パラメーターを (いくつかのコマンドレットは 1 つだけのパラメーター セットである必要があります) のパラメーター セットに分けます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-141">Separate the parameters into parameter sets (some cmdlets may have only one parameter set).</span></span> <span data-ttu-id="c99cb-142">Get Tech この例では、コマンドレットは、2 つのパラメーター セットにします。</span><span class="sxs-lookup"><span data-stu-id="c99cb-142">In this example the Get-Tech cmdlet has two parameter sets.</span></span>

   ```
   SYNTAX
       Get-Tech -name -type
       Get-Tech -ID -list -type
   ```

   <span data-ttu-id="c99cb-143">各パラメーターをコマンドレットの名前を持つセットを開始します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-143">Start each parameter set with the cmdlet name.</span></span>

   <span data-ttu-id="c99cb-144">最初に設定する既定のパラメーターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-144">List the default parameter set first.</span></span> <span data-ttu-id="c99cb-145">既定のパラメーターは、コマンドレット クラスによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-145">The default parameter is specified by the cmdlet class.</span></span>

   <span data-ttu-id="c99cb-146">各パラメーターを設定する必要がありますは最初に示される位置指定パラメーターがない限り、その一意のパラメーターを最初に、リストします。</span><span class="sxs-lookup"><span data-stu-id="c99cb-146">For each parameter set, list its unique parameter first, unless there are positional parameters that must appear first.</span></span> <span data-ttu-id="c99cb-147">前の例では、名前と ID パラメーターは、2 つのパラメーター セットの一意のパラメーター (各パラメーター セットは、そのパラメーターのセットに一意である 1 つのパラメーターをいる必要があります)。</span><span class="sxs-lookup"><span data-stu-id="c99cb-147">In the previous example, the Name and ID parameters are unique parameters for the two parameter sets (each parameter set must have one parameter that is unique to that parameter set).</span></span> <span data-ttu-id="c99cb-148">これにより、どのようなパラメーターのパラメーターを指定する必要がある設定を識別するためにユーザーが簡単にします。</span><span class="sxs-lookup"><span data-stu-id="c99cb-148">This makes it easier for users to identify what parameter they need to supply for the parameter set.</span></span>

   <span data-ttu-id="c99cb-149">コマンドに表示される順序でパラメーターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-149">List the parameters in the order that they should appear in the command.</span></span> <span data-ttu-id="c99cb-150">順序は関係ありませんが場合、は、関連パラメーターを同時に、一覧表示するか、最初に最もよく使用されるパラメーターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-150">If the order does not matter, list related parameters together, or list the most frequently used parameters first.</span></span>

   <span data-ttu-id="c99cb-151">コマンドレットが ShouldProcess をサポートしている場合は、WhatIf、Confirm パラメーターを一覧表示してください。</span><span class="sxs-lookup"><span data-stu-id="c99cb-151">Be sure to list the WhatIf and Confirm parameters if the cmdlet supports ShouldProcess.</span></span>

   <span data-ttu-id="c99cb-152">(Verbose、Debug、ErrorAction など) の構文ダイアグラムでの共通のパラメーターは表示されません。</span><span class="sxs-lookup"><span data-stu-id="c99cb-152">Do not list the common parameters (such as Verbose, Debug, and ErrorAction) in your syntax diagram.</span></span> <span data-ttu-id="c99cb-153">`Get-Help`コマンドレット ヘルプ トピックを表示するときにその情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-153">The `Get-Help` cmdlet adds that information for you when it displays the Help topic.</span></span>

3. <span data-ttu-id="c99cb-154">パラメーターの値を追加します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-154">Add the parameter values.</span></span> <span data-ttu-id="c99cb-155">Windows powershell?、パラメーター値は、.NET 型によって表されます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-155">In Windows PowerShell?, parameter values are represented by their .NET type.</span></span> <span data-ttu-id="c99cb-156">ただし、型名に短縮できます、System.String の"string"など。</span><span class="sxs-lookup"><span data-stu-id="c99cb-156">However, the type name can be abbreviated, such as "string" for System.String.</span></span>

   ```
   SYNTAX
       Get-Tech -name string -type basic advanced
       Get-Tech -ID int -list -type basic advanced
   ```

   <span data-ttu-id="c99cb-157">その意味が明確に"string"に System.String および System.Int32 の"int"などの型の省略形します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-157">Abbreviate types as long as their meaning is clear, such as "string" for System.String and "int" for System.Int32.</span></span>

   <span data-ttu-id="c99cb-158">列挙型のすべての値を一覧表示など、型パラメーターを指定する前の例では、"basic"または「詳細」に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-158">List all values of enumerations, such as the -type parameter in the previous example, which can be set to "basic" or "advanced".</span></span>

   <span data-ttu-id="c99cb-159">スイッチ パラメーターは、前の例の一覧など、値はありません。</span><span class="sxs-lookup"><span data-stu-id="c99cb-159">Switch parameters, such as -list in the previous example, do not have values.</span></span>

4. <span data-ttu-id="c99cb-160">リテラルのパラメーター値と比較して、プレース ホルダーをパラメーターの値には、山かっこを追加します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-160">Add angle brackets to parameters values that are placeholder, as compared to parameter values that are literals.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> -type basic advanced
       Get-Tech -ID <int> -list -type basic advanced
   ```

5. <span data-ttu-id="c99cb-161">省略可能なパラメーターとその値を角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-161">Enclose optional parameters and their vales in square brackets.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

6. <span data-ttu-id="c99cb-162">(位置指定パラメーター) の省略可能なパラメーター名を角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-162">Enclose optional parameters names (for positional parameters) in square brackets.</span></span> <span data-ttu-id="c99cb-163">次の例では、Name パラメーターなど、位置指定されるパラメーターの名前をコマンドに含まれる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c99cb-163">The name for parameters that are positional, such as the Name parameter in the following example, do not have to be included in the command.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

7. <span data-ttu-id="c99cb-164">パラメーターの値は、Name パラメーターの名前の一覧など、複数の値を格納する場合は、パラメーター値の直後の角かっこのペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-164">If a parameter value can contain multiple values, such as a list of names in the Name parameter, add a pair of square brackets directly following the parameter value.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type basic advanced]
       Get-Tech -ID <int[]> [-list] [-type basic advanced]
   ```

8. <span data-ttu-id="c99cb-165">パラメーターまたはパラメーター値からユーザーを選択できる場合、型パラメーターなど、選択肢を中かっこで囲み、排他的 OR symbol(;) で区切ります。</span><span class="sxs-lookup"><span data-stu-id="c99cb-165">If the user can choose from parameters or parameter values, such as the Type parameter, enclose the choices in curly brackets and separate them with the exclusive OR symbol(;).</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

9. <span data-ttu-id="c99cb-166">パラメーターの値が引用符やかっこなどの特定の書式を使用する必要がある場合は、構文の形式を表示します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-166">If the parameter value must use specific formatting, such as quotation marks or parentheses, show the format in the syntax.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <"string[]"> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

## <a name="coding-the-syntax-diagram-xml"></a><span data-ttu-id="c99cb-167">XML 構文ダイアグラムのコーディング</span><span class="sxs-lookup"><span data-stu-id="c99cb-167">Coding the Syntax Diagram XML</span></span>

<span data-ttu-id="c99cb-168">終わる説明ノードの直後に、XML の構文ノードを開始、 \</maml:description > タグです。</span><span class="sxs-lookup"><span data-stu-id="c99cb-168">The syntax node of the XML begins immediately after the description node, which ends with the \</maml:description> tag.</span></span> <span data-ttu-id="c99cb-169">構文ダイアグラムで使用されるデータの収集方法の詳細については、次を参照してください。[構文情報の収集](#gathering-syntax-information)します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-169">For information about gathering the data used in the syntax diagram, see [Gathering Syntax Information](#gathering-syntax-information).</span></span>

### <a name="adding-a-syntax-node"></a><span data-ttu-id="c99cb-170">構文ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-170">Adding a Syntax Node</span></span>

<span data-ttu-id="c99cb-171">コマンドレットのヘルプ トピックに表示されている構文ダイアグラムは、XML の構文ノード内のデータから生成されます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-171">The syntax diagram displayed in the cmdlet Help topic is generated from the data in the syntax node of the XML.</span></span> <span data-ttu-id="c99cb-172">場合、構文ノードが、ペアで囲まれた\<コマンドの構文: > タグです。</span><span class="sxs-lookup"><span data-stu-id="c99cb-172">The syntax node is enclosed in a pair if \<command:syntax> tags.</span></span> <span data-ttu-id="c99cb-173">各パラメーターのセットのペアで囲まれているコマンドレットの\<コマンド: syntaxitem > タグです。</span><span class="sxs-lookup"><span data-stu-id="c99cb-173">With each parameter set of the cmdlet enclosed in a pair of \<command:syntaxitem> tags.</span></span> <span data-ttu-id="c99cb-174">数に制限はありません\<コマンド: syntaxitem > タグを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-174">There is no limit to the number of \<command:syntaxitem> tags that you can add.</span></span>

<span data-ttu-id="c99cb-175">次の例では、2 つのパラメーター セットの構文項目ノードを持つ構文ノードを示します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-175">The following example shows a syntax node that has syntax item nodes for two parameter sets.</span></span>

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

### <a name="adding-the-cmdlet-name-to-the-parameter-set-data"></a><span data-ttu-id="c99cb-176">データを設定するパラメーターをコマンドレット名を追加します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-176">Adding the Cmdlet Name to the Parameter Set Data</span></span>

<span data-ttu-id="c99cb-177">コマンドレットの各パラメーター セットは、構文項目のノードで指定されます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-177">Each parameter set of the cmdlet is specified in a syntax item node.</span></span> <span data-ttu-id="c99cb-178">構文項目の各ノードは、のペアで始まる\<maml:name > タグを含むコマンドレットの名前。</span><span class="sxs-lookup"><span data-stu-id="c99cb-178">Each syntax item node begins with a pair of \<maml:name> tags that include the name of the cmdlet.</span></span>

<span data-ttu-id="c99cb-179">次の例には、2 つのパラメーター セットの構文項目ノードを持つ構文ノードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-179">The following example includes a syntax node that has syntax item nodes for two parameter sets.</span></span>

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

### <a name="adding-parameters"></a><span data-ttu-id="c99cb-180">パラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="c99cb-180">Adding Parameters</span></span>

<span data-ttu-id="c99cb-181">囲まれた構文項目ノードに追加された各パラメーターが指定されて\<コマンド: パラメーター > タグです。</span><span class="sxs-lookup"><span data-stu-id="c99cb-181">Each parameter added to the syntax item node is specified within a pair of \<command:parameter> tags.</span></span> <span data-ttu-id="c99cb-182">ペアを作成する必要があります\<コマンド: パラメーター > タグを除く、Windows PowerShell によって提供される共通パラメーター、パラメーター セットに含める各パラメーターのですか。</span><span class="sxs-lookup"><span data-stu-id="c99cb-182">You need a pair of \<command:parameter> tags for each parameter included in the parameter set, with the exception of the common parameters that are provided by Windows PowerShell?.</span></span>

<span data-ttu-id="c99cb-183">開始の属性\<コマンド: パラメーター > タグは、構文ダイアグラムでのパラメーターの表示方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-183">The attributes of the opening \<command:parameter> tag determine how the parameter appears in the syntax diagram.</span></span> <span data-ttu-id="c99cb-184">パラメーターの属性については、次を参照してください。[パラメーター属性](#parameter-attributes)します。</span><span class="sxs-lookup"><span data-stu-id="c99cb-184">For information on parameter attributes, see [Parameter Attributes](#parameter-attributes).</span></span>

> [!NOTE]
> <span data-ttu-id="c99cb-185">\<コマンド: パラメーター > タグは子要素をサポートする\<maml:description > のコンテンツを表示することはありません。</span><span class="sxs-lookup"><span data-stu-id="c99cb-185">The \<command:parameter> tag supports a child element \<maml:description> whose content is never displayed.</span></span> <span data-ttu-id="c99cb-186">パラメーターの説明は、XML のパラメーターのノードで指定されます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-186">The parameter descriptions are specified in the parameter node of the XML.</span></span> <span data-ttu-id="c99cb-187">構文項目の情報は、間の不整合を回避するために bodes 省略 [パラメーター] ノード、(\<maml:description > か、空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="c99cb-187">To avoid inconsistencies between the information in the syntax item bodes and the parameter node, omit the (\<maml:description> or leave it empty.</span></span>

<span data-ttu-id="c99cb-188">次の例には、2 つのパラメーターを設定するパラメーターの構文項目ノードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c99cb-188">The following example includes a syntax item node for a parameter set with two parameters.</span></span>

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
