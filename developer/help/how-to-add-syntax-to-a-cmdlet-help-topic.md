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
ms.openlocfilehash: 947d0c0188df5bba3a9fb617fe5abf0b3b28eb51
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857998"
---
# <a name="how-to-add-syntax-to-a-cmdlet-help-topic"></a><span data-ttu-id="c2ce4-102">コマンドレットのヘルプ トピックに構文を追加する方法</span><span class="sxs-lookup"><span data-stu-id="c2ce4-102">How to Add Syntax to a Cmdlet Help Topic</span></span>

- [<span data-ttu-id="c2ce4-103">パラメーター属性</span><span class="sxs-lookup"><span data-stu-id="c2ce4-103">Parameter Attributes</span></span>](#Parameter-Attributes)

- [<span data-ttu-id="c2ce4-104">パラメーター値の属性</span><span class="sxs-lookup"><span data-stu-id="c2ce4-104">Parameter Value Attributes</span></span>](#Parameter-Value-Attributes)

- [<span data-ttu-id="c2ce4-105">構文情報の収集</span><span class="sxs-lookup"><span data-stu-id="c2ce4-105">Gathering Syntax Information</span></span>](#Gathering-Syntax-Information)

- [<span data-ttu-id="c2ce4-106">XML 構文ダイアグラムのコーディング</span><span class="sxs-lookup"><span data-stu-id="c2ce4-106">Coding the Syntax Diagram XML</span></span>](#Coding-the-Syntax-Diagram-XML)

## <a name="things-to-know-about-the-syntax-diagram-in-cmdlet-help"></a><span data-ttu-id="c2ce4-107">コマンドレット ヘルプの構文ダイアグラムについて知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="c2ce4-107">Things to Know About the Syntax Diagram in Cmdlet Help</span></span>

<span data-ttu-id="c2ce4-108">コマンドレットのヘルプ ファイルで構文ダイアグラムの XML コードを開始する前に、パラメーターの属性と構文ダイアグラムでそのデータを表示する方法など、提供する必要があるデータの種類を明確に把握するには、このセクションを読む.</span><span class="sxs-lookup"><span data-stu-id="c2ce4-108">Before you start to code the XML for the syntax diagram in the cmdlet Help file, read this section to get a clear picture of the kind of data you need to provide, such as the parameter attributes, and how that data is displayed in the syntax diagram..</span></span>

### <a name="parameter-attributes"></a><span data-ttu-id="c2ce4-109">パラメーター属性</span><span class="sxs-lookup"><span data-stu-id="c2ce4-109">Parameter Attributes</span></span>

- <span data-ttu-id="c2ce4-110">必須</span><span class="sxs-lookup"><span data-stu-id="c2ce4-110">Required</span></span>

  - <span data-ttu-id="c2ce4-111">True の場合、パラメーター セットを使用するすべてのコマンドで、パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-111">If true, the parameter must appear in all commands that use the parameter set.</span></span>

  - <span data-ttu-id="c2ce4-112">False の場合、パラメーターはパラメーター セットを使用するすべてのコマンドでは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-112">If false, the parameter is optional in all commands that use the parameter set.</span></span>

- <span data-ttu-id="c2ce4-113">位置</span><span class="sxs-lookup"><span data-stu-id="c2ce4-113">Position</span></span>

  - <span data-ttu-id="c2ce4-114">という名前の場合、パラメーター名が必要です。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-114">If named, the parameter name is required.</span></span>

  - <span data-ttu-id="c2ce4-115">場合、位置指定パラメーター名は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-115">If positional, the parameter name is optional.</span></span> <span data-ttu-id="c2ce4-116">省略すると、パラメーターの値は、コマンドで指定された位置にあります。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-116">When it is omitted, the parameter value must be in the specified position in the command.</span></span> <span data-ttu-id="c2ce4-117">場合は、値は位置の「1」、たとえば、=、パラメーター値には初または唯一無名のコマンドのパラメーターの値。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-117">For example, if the value is position="1", the parameter value must be the first or only unnamed parameter value in the command.</span></span>

- <span data-ttu-id="c2ce4-118">パイプラインの入力</span><span class="sxs-lookup"><span data-stu-id="c2ce4-118">Pipeline Input</span></span>

  - <span data-ttu-id="c2ce4-119">True (ByValue) パラメーターへの入力をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-119">If true (ByValue), you can pipe input to the parameter.</span></span> <span data-ttu-id="c2ce4-120">入力が関連付けられている (「バインドする」) で、プロパティ名とオブジェクトの種類も予期される型が一致しない場合でもパラメーター。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-120">The input is associated with ("bound to") the parameter even if the property name and the object type do not match the expected type.</span></span> <span data-ttu-id="c2ce4-121">Windows PowerShell ですか。コンポーネントのパラメーター バインドしようと適切な型への入力を変換し、型を変換できない場合にのみコマンドが失敗します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-121">The Windows PowerShell? parameter binding components try to convert the input to the correct type and fail the command only when the type cannot be converted.</span></span> <span data-ttu-id="c2ce4-122">パラメーター セットで 1 つだけのパラメーター値で関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-122">Only one parameter in a parameter set can be associated by value.</span></span>

  - <span data-ttu-id="c2ce4-123">True の場合 (ByPropertyName) パラメーターへの入力をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-123">If true (ByPropertyName), you can pipe input to the parameter.</span></span> <span data-ttu-id="c2ce4-124">ただし、入力は、パラメーター名が、入力オブジェクトのプロパティの名前と一致する場合にのみ、パラメーターに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-124">However, the input is associated with the parameter only when the parameter name matches the name of a property of the input object.</span></span> <span data-ttu-id="c2ce4-125">たとえば、パラメーター名は`Path`オブジェクトがパスをという名前のプロパティがある場合のみをコマンドレットにパイプ処理されたオブジェクトがそのパラメーターと関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-125">For example, if the parameter name is `Path`, objects piped to the cmdlet are associated with that parameter only when the object has a property named path.</span></span>

  - <span data-ttu-id="c2ce4-126">場合は true (ByValue、ByPropertyName) がプロパティ名または値のいずれかのパラメーターへの入力をパイプ処理できます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-126">If true (ByValue, ByPropertyName), you can pipe input to the parameter either by property name or by value.</span></span> <span data-ttu-id="c2ce4-127">パラメーター セットで 1 つだけのパラメーター値で関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-127">Only one parameter in a parameter set can be associated by value.</span></span>

  - <span data-ttu-id="c2ce4-128">False の場合は、このパラメーターへの入力をパイプすることはできません。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-128">If false, you cannot pipe input to this parameter.</span></span>

- <span data-ttu-id="c2ce4-129">グロビング</span><span class="sxs-lookup"><span data-stu-id="c2ce4-129">Globbing</span></span>

  - <span data-ttu-id="c2ce4-130">True の場合、ユーザーがパラメーター値を入力するテキストは、ワイルドカード文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-130">If true, the text that the user types for the parameter value can include wildcard characters.</span></span>

  - <span data-ttu-id="c2ce4-131">False の場合、ユーザーがパラメーター値を入力するテキストは、ワイルドカード文字を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-131">If false, the text that the user types for the parameter value cannot include wildcard characters.</span></span>

### <a name="parameter-value-attributes"></a><span data-ttu-id="c2ce4-132">パラメーター値の属性</span><span class="sxs-lookup"><span data-stu-id="c2ce4-132">Parameter Value Attributes</span></span>

- <span data-ttu-id="c2ce4-133">必須</span><span class="sxs-lookup"><span data-stu-id="c2ce4-133">Required</span></span>

  - <span data-ttu-id="c2ce4-134">True の場合は、コマンドで、パラメーターを使用するたびに、指定した値が使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-134">If true, the specified value must be used whenever using the parameter in a command.</span></span>

  - <span data-ttu-id="c2ce4-135">False の場合、パラメーターの値は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-135">If false, the parameter value is optional.</span></span> <span data-ttu-id="c2ce4-136">通常、ある場合にのみ、パラメーターのいくつかの有効な値のいずれかのように列挙型では、値は省略できます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-136">Typically, a value is optional only when it is one of several valid values for a parameter, such as in an enumerated type.</span></span>

<span data-ttu-id="c2ce4-137">パラメーターの値の必須の属性は、パラメーターの必須の属性と異なります。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-137">The Required attribute of a parameter value is different from the Required attribute of a parameter.</span></span>

<span data-ttu-id="c2ce4-138">パラメーターの必須の属性は、かどうか、パラメーター (とその値) 含める必要がある、コマンドレットを呼び出すときを示します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-138">The required attribute of a parameter indicates whether the parameter (and its value) must be included when invoking the cmdlet.</span></span> <span data-ttu-id="c2ce4-139">これに対し、必要なパラメーターの値の属性は、コマンドのパラメーターが含まれている場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-139">In contrast, the required attribute of a parameter value is used only when the parameter is included in the command.</span></span> <span data-ttu-id="c2ce4-140">これは、その特定の値をパラメーターと共に使用する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-140">It indicates whether that particular value must be used with the parameter.</span></span>

<span data-ttu-id="c2ce4-141">通常、プレース ホルダーをパラメーター値が必要ですし、リテラルのパラメーター値のパラメーターと共に使用されるいくつかの値のいずれかがいるため、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-141">Typically, parameter values that are placeholders are required and parameter values that are literal are not required, because they are one of several values that might be used with the parameter.</span></span>

### <a name="gathering-syntax-information"></a><span data-ttu-id="c2ce4-142">構文情報の収集</span><span class="sxs-lookup"><span data-stu-id="c2ce4-142">Gathering Syntax Information</span></span>

1. <span data-ttu-id="c2ce4-143">コマンドレット名で始まります。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-143">Start with the cmdlet name.</span></span>

   ```
   SYNTAX
       Get-Tech
   ```

2. <span data-ttu-id="c2ce4-144">コマンドレットのすべてのパラメーターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-144">List all the parameters of the cmdlet.</span></span> <span data-ttu-id="c2ce4-145">入力をダッシュ ("dash"または""(ASCII 45) 前にマイナス記号各パラメーター名とも呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-145">Type a dash (also known as a "dash" or "minus sign" (ASCII 45) before each parameter name.</span></span> <span data-ttu-id="c2ce4-146">パラメーターを (いくつかのコマンドレットは 1 つだけのパラメーター セットである必要があります) のパラメーター セットに分けます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-146">Separate the parameters into parameter sets (some cmdlets may have only one parameter set).</span></span> <span data-ttu-id="c2ce4-147">Get Tech この例では、コマンドレットは、2 つのパラメーター セットにします。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-147">In this example the Get-Tech cmdlet has two parameter sets.</span></span>

   ```
   SYNTAX
       Get-Tech -name -type
       Get-Tech -ID -list -type
   ```

   <span data-ttu-id="c2ce4-148">各パラメーターをコマンドレットの名前を持つセットを開始します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-148">Start each parameter set with the cmdlet name.</span></span>

   <span data-ttu-id="c2ce4-149">最初に設定する既定のパラメーターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-149">List the default parameter set first.</span></span> <span data-ttu-id="c2ce4-150">既定のパラメーターは、コマンドレット クラスによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-150">The default parameter is specified by the cmdlet class.</span></span>

   <span data-ttu-id="c2ce4-151">各パラメーターを設定する必要がありますは最初に示される位置指定パラメーターがない限り、その一意のパラメーターを最初に、リストします。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-151">For each parameter set, list its unique parameter first, unless there are positional parameters that must appear first.</span></span> <span data-ttu-id="c2ce4-152">前の例では、名前と ID パラメーターは、2 つのパラメーター セットの一意のパラメーター (各パラメーター セットは、そのパラメーターのセットに一意である 1 つのパラメーターをいる必要があります)。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-152">In the previous example, the Name and ID parameters are unique parameters for the two parameter sets (each parameter set must have one parameter that is unique to that parameter set).</span></span> <span data-ttu-id="c2ce4-153">これにより、どのようなパラメーターのパラメーターを指定する必要がある設定を識別するためにユーザーが簡単にします。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-153">This makes it easier for users to identify what parameter they need to supply for the parameter set.</span></span>

   <span data-ttu-id="c2ce4-154">コマンドに表示される順序でパラメーターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-154">List the parameters in the order that they should appear in the command.</span></span> <span data-ttu-id="c2ce4-155">順序は関係ありませんが場合、は、関連パラメーターを同時に、一覧表示するか、最初に最もよく使用されるパラメーターを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-155">If the order does not matter, list related parameters together, or list the most frequently used parameters first.</span></span>

   <span data-ttu-id="c2ce4-156">コマンドレットが ShouldProcess をサポートしている場合は、WhatIf、Confirm パラメーターを一覧表示してください。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-156">Be sure to list the WhatIf and Confirm parameters if the cmdlet supports ShouldProcess.</span></span>

   <span data-ttu-id="c2ce4-157">(Verbose、Debug、ErrorAction など) の構文ダイアグラムでの共通のパラメーターは表示されません。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-157">Do not list the common parameters (such as Verbose, Debug, and ErrorAction) in your syntax diagram.</span></span> <span data-ttu-id="c2ce4-158">`Get-Help`コマンドレット ヘルプ トピックを表示するときにその情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-158">The `Get-Help` cmdlet adds that information for you when it displays the Help topic.</span></span>

3. <span data-ttu-id="c2ce4-159">パラメーターの値を追加します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-159">Add the parameter values.</span></span> <span data-ttu-id="c2ce4-160">Windows powershell?、パラメーター値は、.NET 型によって表されます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-160">In Windows PowerShell?, parameter values are represented by their .NET type.</span></span> <span data-ttu-id="c2ce4-161">ただし、型名に短縮できます、System.String の"string"など。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-161">However, the type name can be abbreviated, such as "string" for System.String.</span></span>

   ```
   SYNTAX
       Get-Tech -name string -type basic advanced
       Get-Tech -ID int -list -type basic advanced
   ```

   <span data-ttu-id="c2ce4-162">その意味が明確に"string"に System.String および System.Int32 の"int"などの型の省略形します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-162">Abbreviate types as long as their meaning is clear, such as "string" for System.String and "int" for System.Int32.</span></span>

   <span data-ttu-id="c2ce4-163">列挙型のすべての値を一覧表示など、前の例では、型パラメーター、これは、"basic"または「詳細」に設定できます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-163">List all values of enumerations, such as the -type parameter in the previous example, wich can be set to "basic" or "advanced".</span></span>

   <span data-ttu-id="c2ce4-164">スイッチ パラメーターは、前の例の一覧など、値はありません。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-164">Switch parameters, such as -list in the previous example, do not have values.</span></span>

4. <span data-ttu-id="c2ce4-165">リテラルのパラメーター値と比較して、プレース ホルダーをパラメーターの値には、山かっこを追加します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-165">Add angle brackets to parameters values that are placeholder, as compared to parameter values that are literals.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> -type basic advanced
       Get-Tech -ID <int> -list -type basic advanced
   ```

5. <span data-ttu-id="c2ce4-166">省略可能なパラメーターとその値を角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-166">Enclose optional parameters and their vales in square brackets.</span></span>

   ```
   SYNTAX
       Get-Tech -name <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

6. <span data-ttu-id="c2ce4-167">(位置指定パラメーター) の省略可能なパラメーター名を角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-167">Enclose optional parameters names (for positional parameters) in square brackets.</span></span> <span data-ttu-id="c2ce4-168">次の例では、Name パラメーターなど、位置指定されるパラメーターの名前をコマンドに含まれる必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-168">The name for parameters that are positional, such as the Name parameter in the following example, do not have to be included in the command.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

7. <span data-ttu-id="c2ce4-169">パラメーターの値は、Name パラメーターの名前の一覧など、複数の値を格納する場合は、パラメーター値の直後の角かっこのペアを追加します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-169">If a parameter value can contain multiple values, such as a list of names in the Name parameter, add a pair of square brackets directly following the parameter value.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type basic advanced]
       Get-Tech -ID <int[]> [-list] [-type basic advanced]
   ```

8. <span data-ttu-id="c2ce4-170">パラメーターまたはパラメーター値からユーザーを選択できる場合、型パラメーターなど、選択肢を中かっこで囲み、排他的 OR symbol(;) で区切ります。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-170">If the user can choose from parameters or parameter values, such as the Type parameter, enclose the choices in curly brackets and separate them with the exclusive OR symbol(;).</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

9. <span data-ttu-id="c2ce4-171">パラメーターの値が引用符やかっこなどの特定の書式を使用する必要がある場合は、構文の形式を表示します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-171">If the parameter value must use specific formatting, such as quotation marks or parentheses, show the format in the syntax.</span></span>

   ```
   SYNTAX
       Get-Tech [-name] <"string[]"> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

## <a name="coding-the-syntax-diagram-xml"></a><span data-ttu-id="c2ce4-172">XML 構文ダイアグラムのコーディング</span><span class="sxs-lookup"><span data-stu-id="c2ce4-172">Coding the Syntax Diagram XML</span></span>

<span data-ttu-id="c2ce4-173">終わる説明ノードの直後に、XML の構文ノードを開始、 \</maml:description > タグです。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-173">The syntax node of the XML begins immediately after the description node, which ends with the \</maml:description> tag.</span></span> <span data-ttu-id="c2ce4-174">構文ダイアグラムで使用されるデータの収集方法の詳細については、次を参照してください。[構文情報の収集](#Gathering-Syntax-Information)します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-174">For information about gathering the data used in the syntax diagram, see [Gathering Syntax Information](#Gathering-Syntax-Information).</span></span>

### <a name="adding-a-syntax-node"></a><span data-ttu-id="c2ce4-175">構文ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-175">Adding a Syntax Node</span></span>

<span data-ttu-id="c2ce4-176">コマンドレットのヘルプ トピックに表示されている構文ダイアグラムは、XML の構文ノード内のデータから生成されます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-176">The syntax diagram displayed in the cmdlet Help topic is generated from the data in the syntax node of the XML.</span></span> <span data-ttu-id="c2ce4-177">場合、構文ノードが、ペアで囲まれた\<コマンドの構文: > タグです。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-177">The syntax node is enclosed in a pair if \<command:syntax> tags.</span></span> <span data-ttu-id="c2ce4-178">各パラメーターのセットのペアで囲まれているコマンドレットの\<コマンド: syntaxitem > タグです。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-178">With each parameter set of the cmdlet enclosed in a pair of \<command:syntaxitem> tags.</span></span> <span data-ttu-id="c2ce4-179">数に制限はありません\<コマンド: syntaxitem > タグを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-179">There is no limit to the number of \<command:syntaxitem> tags that you can add.</span></span>

<span data-ttu-id="c2ce4-180">次の例では、2 つのパラメーター セットの構文項目ノードを持つ構文ノードを示します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-180">The following example shows a syntax node that has syntax item nodes for two parameter sets.</span></span>

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

### <a name="adding-the-cmdlet-name-to-the-parameter-set-data"></a><span data-ttu-id="c2ce4-181">データを設定するパラメーターをコマンドレット名を追加します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-181">Adding the Cmdlet Name to the Parameter Set Data</span></span>

<span data-ttu-id="c2ce4-182">コマンドレットの各パラメーター セットは、構文項目のノードで指定されます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-182">Each parameter set of the cmdlet is specified in a syntax item node.</span></span> <span data-ttu-id="c2ce4-183">構文項目の各ノードは、のペアで始まる\<maml:name > タグを含むコマンドレットの名前。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-183">Each syntax item node begins with a pair of \<maml:name> tags that include the name of the cmdlet.</span></span>

<span data-ttu-id="c2ce4-184">次の例には、2 つのパラメーター セットの構文項目ノードを持つ構文ノードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-184">The following example includes a syntax node that has syntax item nodes for two parameter sets.</span></span>

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

### <a name="adding-parameters"></a><span data-ttu-id="c2ce4-185">パラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="c2ce4-185">Adding Parameters</span></span>

<span data-ttu-id="c2ce4-186">囲まれた構文項目ノードに追加された各パラメーターが指定されて\<コマンド: パラメーター > タグです。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-186">Each parameter added to the syntax item node is specified within a pair of \<command:parameter> tags.</span></span> <span data-ttu-id="c2ce4-187">ペアを作成する必要があります\<コマンド: パラメーター > タグを除く、Windows PowerShell によって提供される共通パラメーター、パラメーター セットに含める各パラメーターのですか。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-187">You need a pair of \<command:parameter> tags for each parameter included in the parameter set, with the exception of the common parameters that are provided by Windows PowerShell?.</span></span>

<span data-ttu-id="c2ce4-188">開始の属性\<コマンド: パラメーター > タグは、構文ダイアグラムでのパラメーターの表示方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-188">The attributes of the opening \<command:parameter> tag determine how the parameter appears in the syntax diagram.</span></span> <span data-ttu-id="c2ce4-189">パラメーターの属性については、次を参照してください。[パラメーター属性](#Parameter-Attributes)します。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-189">For information on parameter attributes, see [Parameter Attributes](#Parameter-Attributes).</span></span>

> [!NOTE]
> <span data-ttu-id="c2ce4-190">\<コマンド: パラメーター > タグは子要素をサポートする\<maml:description > のコンテンツを表示することはありません。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-190">The \<command:parameter> tag supports a child element \<maml:description> whose content is never displayed.</span></span> <span data-ttu-id="c2ce4-191">パラメーターの説明は、XML のパラメーターのノードで指定されます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-191">The parameter descriptions are specified in the parameter node of the XML.</span></span> <span data-ttu-id="c2ce4-192">構文項目の情報は、間の不整合を回避するために bodes 省略 [パラメーター] ノード、(\<maml:description > か、空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-192">To avoid inconsistencies between the information in the syntax item bodes and the parameter node, omit the (\<maml:description> or leave it empty.</span></span>

<span data-ttu-id="c2ce4-193">次の例には、2 つのパラメーターを設定するパラメーターの構文項目ノードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c2ce4-193">The following example includes a syntax item node for a parameter set with two parameters.</span></span>

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
