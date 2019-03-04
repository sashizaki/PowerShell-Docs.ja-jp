---
title: パラメーター情報を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf6c1442-60aa-477a-8f30-ab02b1b11039
caps.latest.revision: 7
ms.openlocfilehash: d4a5fc934a41b00f89862674e44e4540680674f7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863328"
---
# <a name="how-to-add-parameter-information"></a><span data-ttu-id="62de2-102">パラメーター情報を追加する方法</span><span class="sxs-lookup"><span data-stu-id="62de2-102">How to Add Parameter Information</span></span>

<span data-ttu-id="62de2-103">このセクションでは、コマンドレットのヘルプ トピックの PARAMETERS セクションに表示されるコンテンツを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="62de2-103">This section describes how to add content that is displayed in the PARAMETERS section of the cmdlet Help topic.</span></span> <span data-ttu-id="62de2-104">ヘルプ トピックのパラメーター セクションでは、各コマンドレットのパラメーターの一覧を表示し、各パラメーターの詳細な説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="62de2-104">The PARAMETERS section of the Help topic lists each of the parameters of the cmdlet and provides a detailed description of each parameter.</span></span>

<span data-ttu-id="62de2-105">PARAMETERS セクションの内容は、一貫性のあるヘルプ トピックの「構文」セクションのコンテンツを含む必要があります。</span><span class="sxs-lookup"><span data-stu-id="62de2-105">The content of the PARAMETERS section should be consistent with the content of the SYNTAX section of the Help topic.</span></span> <span data-ttu-id="62de2-106">構文とパラメーターの両方のノードに同様の XML 要素が含まれているかどうかを確認するヘルプ作成者の役割です。</span><span class="sxs-lookup"><span data-stu-id="62de2-106">It is the responsibility of the Help author to make sure that both the Syntax and Parameters node contain similar XML elements.</span></span>

> [!NOTE]
> <span data-ttu-id="62de2-107">ヘルプ ファイル、開いている Windows PowerShell のインストール ディレクトリにある dll Help.xml ファイルの 1 つの完全なビュー。</span><span class="sxs-lookup"><span data-stu-id="62de2-107">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="62de2-108">たとえば、Microsoft.PowerShell.Commands.Management.dll Help.xml ファイルには、Windows PowerShell コマンドレットのいくつかのコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="62de2-108">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="to-add-parameters"></a><span data-ttu-id="62de2-109">パラメーターを追加するには</span><span class="sxs-lookup"><span data-stu-id="62de2-109">To Add Parameters</span></span>

1. <span data-ttu-id="62de2-110">コマンドレットのヘルプ ファイルを開き、文書化するコマンドレットのコマンドのノードを探します。</span><span class="sxs-lookup"><span data-stu-id="62de2-110">Open the cmdlet Help file and locate the Command node for the cmdlet you are documenting.</span></span> <span data-ttu-id="62de2-111">新しいコマンドレットを追加する場合は、新しいコマンド ノードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62de2-111">If you are adding a new cmdlet you will need to create a new Command node.</span></span> <span data-ttu-id="62de2-112">ヘルプ ファイルは、各コマンドレットのヘルプ コンテンツを提供しているコマンドのノードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="62de2-112">Your Help file will contain a Command node for each cmdlet that you are providing Help content for.</span></span> <span data-ttu-id="62de2-113">コマンドの空白ノードの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="62de2-113">Here is an example of a blank Command node.</span></span>

    ```xml
    <command:command>
    </command:command>
    ```

2. <span data-ttu-id="62de2-114">コマンド ノード内で、[説明] ノードを見つけて次に示すように、[パラメーター] ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="62de2-114">Within the Command node, locate the Description node and add a Parameters node as shown below.</span></span> <span data-ttu-id="62de2-115">パラメーター ノードの 1 つだけが許可され、すぐに、構文ノードに従ってください。</span><span class="sxs-lookup"><span data-stu-id="62de2-115">Only one Parameters node is allowed, and it should immediately follow the Syntax node.</span></span>

    ```xml
    <command:command>
      <command:details></command:details>
      <maml:description></maml:description>
      <command:syntax></command:syntax>
      <command:parameters>
      </command:Parameters>
    </command:command>
    ```

3. <span data-ttu-id="62de2-116">[パラメーター] ノード内には、次に示すよう、コマンドレットの各パラメーターのパラメーター ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="62de2-116">Within the Parameters node, add a Parameter node for each parameter of the cmdlet as shown below.</span></span>

   <span data-ttu-id="62de2-117">この例では、3 つのパラメーターのパラメーター ノードが追加されます。</span><span class="sxs-lookup"><span data-stu-id="62de2-117">In this example, a Parameter node is added for three parameters.</span></span>

    ```xml
    <command:parameters>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
    </command:Parameters>
    ```

   <span data-ttu-id="62de2-118">これらは、構文ノードが使用され、ここで、パラメーターが指定されているため、構文ノードで指定されたパラメーターに一致する必要がありますが、同じ XML タグであるためは、構文ノードからパラメーター ノードをコピーし、パラメーター ノードに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="62de2-118">Because these are the same XML tags that are used in the Syntax node, and because the parameters specified here must match the parameters specified by the Syntax node, you can copy the Parameter nodes from the Syntax node and paste them into the Parameters node.</span></span> <span data-ttu-id="62de2-119">ただし、必ずパラメーター ノードの 1 つだけのインスタンスのコピーで、構文で複数のパラメーターを設定で、パラメーターが指定した場合でもです。</span><span class="sxs-lookup"><span data-stu-id="62de2-119">However, be sure to copy only one instance of a Parameter node, even if the parameter is specified in multiple parameter sets in the syntax.</span></span>

4. <span data-ttu-id="62de2-120">パラメーターの各ノードの各パラメーターの特性を定義する属性の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="62de2-120">For each Parameter node, set the attribute values that define the characteristics of each parameter.</span></span> <span data-ttu-id="62de2-121">これらの属性には、次が含まれます。 必要に応じて、グロビング、pipelineinput、および位置。</span><span class="sxs-lookup"><span data-stu-id="62de2-121">These attributes include the following: required, globbing, pipelineinput, and position.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
      </command:parameter>
      <command:parameter required="false" globbing="false"
               pipelineInput="false" position="named">
      </command:parameter>
      <command:parameter required="false" globbing="false"
               pipelineInput="false" position="named" ></command:parameter>
    </command:Parameters>
    ```

5. <span data-ttu-id="62de2-122">パラメーターの各ノードには、パラメーターの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="62de2-122">For each Parameter node, add the name of the parameter.</span></span> <span data-ttu-id="62de2-123">パラメーター ノードに追加するパラメーター名の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="62de2-123">Here is an example of the parameter name added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
      </command:parameter>
    </command:Parameters>
    ```

6. <span data-ttu-id="62de2-124">パラメーターの各ノードには、パラメーターの説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="62de2-124">For each Parameter node, add the description of the parameter.</span></span> <span data-ttu-id="62de2-125">パラメーター ノードに追加されたパラメーターの説明の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="62de2-125">Here is an example of the parameter description added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
      </command:parameter>
    </command:parameters>
    ```

7. <span data-ttu-id="62de2-126">パラメーターの各ノードには、パラメーターの .NET Framework 型を追加します。</span><span class="sxs-lookup"><span data-stu-id="62de2-126">For each Parameter node, add the .NET Framework type of the parameter.</span></span> <span data-ttu-id="62de2-127">パラメーターの型パラメーター名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="62de2-127">The parameter type is displayed along with the parameter name.</span></span>

   <span data-ttu-id="62de2-128">パラメーター ノードに追加されたパラメーターの .NET Framework 型の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="62de2-128">Here is an example of the parameter .NET Framework type added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
        <dev:type> Add .NET Framework type... </dev:type>
      </command:parameter>
    </command:parameters>
    ```

8. <span data-ttu-id="62de2-129">パラメーターの各ノードには、パラメーターの既定値を追加します。</span><span class="sxs-lookup"><span data-stu-id="62de2-129">For each Parameter node, add the default value of the parameter.</span></span> <span data-ttu-id="62de2-130">次の文は、コンテンツを表示するときに、パラメーターの説明に追加されます。"DefaultValue"では、既定値です。</span><span class="sxs-lookup"><span data-stu-id="62de2-130">The following sentence is added to the parameter description when the content is displayed: "DefaultValue" is the default.</span></span>

   <span data-ttu-id="62de2-131">パラメーター ノードに追加パラメーターの既定値の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="62de2-131">Here is an example of the parameter default value is added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
        <maml:description>
          <maml:para> Add parameter description... </maml:para>
        </maml:description>
        <dev:type> Add .NET Framework type... </dev:type>
        <dev:defaultvalue> Add default value...</dev:defaultvalue>
      </command:parameter>
    </command:parameters>
    ```

9. <span data-ttu-id="62de2-132">複数の値を持つ各パラメーターの使用可能な値のノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="62de2-132">For each Parameter that has multiple values, add a possible values node.</span></span>

   <span data-ttu-id="62de2-133">次の例に示します、パラメーターの 2 つの値を定義する使用可能な値のノードの</span><span class="sxs-lookup"><span data-stu-id="62de2-133">Here is an example of the of a possible values node that defines two possible values for the parameter</span></span>

    ```xml
    <dev:possiblevalues>
      <dev:possiblevalue>
        <dev:value>Unknown</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      /dev:possiblevalue>
      <dev:possiblevalue>
        <dev:value>String</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      </dev:possibleValue>
    </dev:possiblevalues>
    ```

<span data-ttu-id="62de2-134">パラメーターを追加するときの注意点を次に示します。</span><span class="sxs-lookup"><span data-stu-id="62de2-134">Here are some things to remember when adding parameters.</span></span>

- <span data-ttu-id="62de2-135">パラメーターの属性は、コマンドレットのヘルプ トピックのすべてのビューでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="62de2-135">The attributes of the parameter are not displayed in all views of the cmdlet Help topic.</span></span> <span data-ttu-id="62de2-136">ただし、完全なユーザーを要求するときに、パラメーターの説明を次の表に表示されている (Get-help\<コマンドレット名 >-フル) またはパラメーター (Get-help\<コマンドレット名 >-パラメーター) トピックの表示。</span><span class="sxs-lookup"><span data-stu-id="62de2-136">However, they are displayed in a table following the parameter description when the user asks for the Full (Get-Help \<cmdletname> -full) or Parameter (Get-Help \<cmdletname> -parameter) view of the topic.</span></span>

- <span data-ttu-id="62de2-137">パラメーターの説明では、コマンドレットのヘルプ トピックの最も重要な部分の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="62de2-137">The parameter description is one of the most important parts of a cmdlet Help topic.</span></span> <span data-ttu-id="62de2-138">概要と詳細な説明があります。</span><span class="sxs-lookup"><span data-stu-id="62de2-138">The description should be brief, as well as thorough.</span></span> <span data-ttu-id="62de2-139">また、パラメーターの説明になると、長すぎる、2 つのパラメーターが相互にやり取りするときなど、追加することできますより多くのコンテンツのコマンドレット ヘルプ トピックのノートのセクションでは注意してください。</span><span class="sxs-lookup"><span data-stu-id="62de2-139">Also, remember that if the parameter description becomes too long, such as when two parameters interact with each other, you can add more content in the NOTES section of the cmdlet Help topic.</span></span>

  <span data-ttu-id="62de2-140">パラメーターの説明では、2 種類の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="62de2-140">The parameter description provides two types of information.</span></span>

- <span data-ttu-id="62de2-141">どのようなコマンドレットは、パラメーターを使用する場合は。</span><span class="sxs-lookup"><span data-stu-id="62de2-141">What the cmdlet does when the parameter is used.</span></span>

- <span data-ttu-id="62de2-142">どのような有効な値は、パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="62de2-142">What a legal value is for the parameter.</span></span>

- <span data-ttu-id="62de2-143">パラメーターの値は .NET Framework のオブジェクトとして表される、ため、ユーザーは従来のコマンドラインのヘルプ内にある場合よりも詳細については、これらの値は必要があります。</span><span class="sxs-lookup"><span data-stu-id="62de2-143">Because the parameter values are expressed as .NET Framework objects, users need more information about these values than they would in a traditional command-line Help.</span></span> <span data-ttu-id="62de2-144">パラメーターが、そのまま使用するように設計するデータの種類に、ユーザーに通知し、例を含めます。</span><span class="sxs-lookup"><span data-stu-id="62de2-144">Tell the user what type of data the parameter is designed to accept, and include examples.</span></span>

<span data-ttu-id="62de2-145">パラメーターの既定値は、コマンドラインでパラメーターが指定されていない場合に使用される値です。</span><span class="sxs-lookup"><span data-stu-id="62de2-145">The default value of the parameter is the value that is used if the parameter is not specified on the command line.</span></span> <span data-ttu-id="62de2-146">既定値は省略可能で、必要なパラメーターなど、いくつかのパラメーターが必要ないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="62de2-146">Note that the default value is optional, and is not needed for some parameters, such as required parameters.</span></span> <span data-ttu-id="62de2-147">ただし、ほとんどの省略可能なパラメーターの既定値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62de2-147">However, you should specify a default value for most optional parameters.</span></span>

<span data-ttu-id="62de2-148">既定値は、ユーザーを使用していない、パラメーターの影響を理解するのには役立ちます。</span><span class="sxs-lookup"><span data-stu-id="62de2-148">The default value helps the user to understand the effect of not using the parameter.</span></span> <span data-ttu-id="62de2-149">非常に具体的には、既定値「現在のディレクトリ」または「Windows PowerShell のインストール ディレクトリ ($pshome)」オプションのパスなどについて説明します。</span><span class="sxs-lookup"><span data-stu-id="62de2-149">Describe the default value very specifically, such as the "Current directory" or the "Windows PowerShell installation directory ($pshome)" for an optional path.</span></span> <span data-ttu-id="62de2-150">既定値は、次の文の使用などを説明する文章を記述することも、`PassThru`パラメーター。「PassThru が指定されていない場合、コマンドレットは渡さないオブジェクトをパイプライン。」</span><span class="sxs-lookup"><span data-stu-id="62de2-150">You can also write a sentence that describes the default, such as the following sentence used for the `PassThru` parameter: "If PassThru is not specified, the cmdlet does not pass objects down the pipeline."</span></span>  <span data-ttu-id="62de2-151">また、反対のフィールド名、値が表示されるためです"**既定値**"、「既定値」という用語をエントリに含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="62de2-151">Also, because the value is displayed opposite the field name "**Default value**", you do not need to include the term "default value" in the entry.</span></span>

<span data-ttu-id="62de2-152">パラメーターの既定値は、コマンドレットのヘルプ トピックのすべてのビューでは表示されません。</span><span class="sxs-lookup"><span data-stu-id="62de2-152">The default value of the parameter is not displayed in all views of the cmdlet Help topic.</span></span> <span data-ttu-id="62de2-153">ただし、パラメーターの説明を以下に、完全なユーザーを要求する (パラメーターの属性) と共にテーブルに表示されます (Get-help\<コマンドレット名 >-フル) またはパラメーター (Get-help\<コマンドレット名 >-パラメーター) ビュートピックです。</span><span class="sxs-lookup"><span data-stu-id="62de2-153">However, it is displayed in a table (along with the parameter attributes) following the parameter description when the user asks for the Full (Get-Help \<cmdletname> -full) or Parameter (Get-Help \<cmdletname> -parameter) view of the topic.</span></span>

<span data-ttu-id="62de2-154">次の XML は 1 組の`<dev:defaultValue>`にタグを追加、`<command:parameter>`ノード。</span><span class="sxs-lookup"><span data-stu-id="62de2-154">The following XML shows a pair of `<dev:defaultValue>` tags added to the `<command:parameter>` node.</span></span> <span data-ttu-id="62de2-155">既定値が終了した直後に続く通知`</command:parameterValue>`(パラメーターの値が指定された) ときにタグまたは終了`</maml:description>`パラメーターの説明のタグ。</span><span class="sxs-lookup"><span data-stu-id="62de2-155">Notice that the default value follows immediately after the closing `</command:parameterValue>` tag (when the parameter value is specified) or the closing `</maml:description>` tag of the parameter description.</span></span> <span data-ttu-id="62de2-156">名前。</span><span class="sxs-lookup"><span data-stu-id="62de2-156">name.</span></span>

```xml
<command:parameters>
  <command:parameter required="true" globbing="true"
           pipelineInput="false" position="named">
    <maml:name> Parameter name </maml:name>
    <maml:description>
      <maml:para> Parameter Description </maml:para>
    </maml:description>
    <command:parameterValue required="true">
      Value
    </command:parameterValue>
    <dev:defaultValue> Default parameter value </dev:defaultValue>
  </command:parameter>
</command:parameters>
```

<span data-ttu-id="62de2-157">列挙型の値を追加します。</span><span class="sxs-lookup"><span data-stu-id="62de2-157">Add Values for Enumerated Types</span></span>

<span data-ttu-id="62de2-158">省略可能なを使用することができます、パラメーターに複数の値または列挙型の値がある場合は、 \<dev:possibleValues > ノード。</span><span class="sxs-lookup"><span data-stu-id="62de2-158">If the parameter has multiple values or values of an enumerated type, you can use an optional \<dev:possibleValues> node.</span></span> <span data-ttu-id="62de2-159">このノードでは、複数の値の説明と名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="62de2-159">This node allows you to specify a name and description for multiple values.</span></span>

<span data-ttu-id="62de2-160">列挙値の説明については、表示されないことで、既定値のいずれかによって表示されるヘルプのビューに注意してください、`Get-Help`コマンドレットが、その他のヘルプ ビューアーは、ビューにこのコンテンツを表示可能性があります。</span><span class="sxs-lookup"><span data-stu-id="62de2-160">Be aware that the descriptions of the enumerated values do not appear in any of the default Help views displayed by the `Get-Help` cmdlet, but other Help viewers may display this content in their views.</span></span>

<span data-ttu-id="62de2-161">次の XML に示す、`<dev:possibleValues>`指定された 2 つの値を持つノード。</span><span class="sxs-lookup"><span data-stu-id="62de2-161">The following XML shows a `<dev:possibleValues>` node with two values specified.</span></span>

```xml
<command:parameters>
  <command:parameter required="true" globbing="true"
           pipelineInput="false" position="named">
    <maml:name> Parameter name </maml:name>
    <maml:description>
      <maml:para> Parameter Description </maml:para>
    </maml:description>
    <command:parameterValue required="true">
      Value
    </command:parameterValue>
    <dev:defaultValue> Default parameter value </dev:defaultValue>
    <dev:possibleValues>
      <dev:possibleValue>
        <dev:value> Value 1 </dev:value>
        <maml:description>
          <maml:para> Description 1 </maml:para>
        </maml:description>
      <dev:possibleValue>
      <dev:possibleValue>
        <dev:value> Value 2 </dev:value>
        <maml:description>
          <maml:para> Description 2 </maml:para>
        </maml:description>
      <dev:possibleValue>
    </dev:possibleValues>
  </command:parameter>
</command:parameters>
```