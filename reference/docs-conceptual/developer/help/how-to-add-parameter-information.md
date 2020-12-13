---
ms.date: 09/12/2016
ms.topic: reference
title: パラメーター情報を追加する方法
description: パラメーター情報を追加する方法
ms.openlocfilehash: 8f4fc46ef256a77b058df4ba506124f80732cb39
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92663052"
---
# <a name="how-to-add-parameter-information"></a><span data-ttu-id="4b770-103">パラメーター情報を追加する方法</span><span class="sxs-lookup"><span data-stu-id="4b770-103">How to Add Parameter Information</span></span>

<span data-ttu-id="4b770-104">このセクションでは、コマンドレットのヘルプトピックの「 **パラメーター** 」セクションに表示されるコンテンツを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b770-104">This section describes how to add content that is displayed in the **PARAMETERS** section of the cmdlet Help topic.</span></span> <span data-ttu-id="4b770-105">ヘルプトピックの「 **パラメーター** 」セクションでは、コマンドレットの各パラメーターの一覧を示し、各パラメーターの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b770-105">The **PARAMETERS** section of the Help topic lists each of the parameters of the cmdlet and provides a detailed description of each parameter.</span></span>

<span data-ttu-id="4b770-106">**PARAMETERS** セクションの内容は、ヘルプトピックの「**構文**」セクションの内容と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b770-106">The content of the **PARAMETERS** section should be consistent with the content of the **SYNTAX** section of the Help topic.</span></span> <span data-ttu-id="4b770-107">**構文** と **パラメーター** ノードの両方に類似した XML 要素が含まれているかどうかを確認するのは、ヘルプの作成者の責任です。</span><span class="sxs-lookup"><span data-stu-id="4b770-107">It is the responsibility of the Help author to make sure that both the **Syntax** and **Parameters** node contain similar XML elements.</span></span>

> [!NOTE]
> <span data-ttu-id="4b770-108">ヘルプファイルの完全なビューを表示するには、 `dll-Help.xml` PowerShell インストールディレクトリにあるいずれかのファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="4b770-108">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the PowerShell installation directory.</span></span> <span data-ttu-id="4b770-109">たとえば、ファイルには、 `Microsoft.PowerShell.Commands.Management.dll-Help.xml` いくつかの PowerShell コマンドレットのコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b770-109">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

### <a name="to-add-parameters"></a><span data-ttu-id="4b770-110">パラメーターを追加するには</span><span class="sxs-lookup"><span data-stu-id="4b770-110">To Add Parameters</span></span>

1. <span data-ttu-id="4b770-111">コマンドレットのヘルプファイルを開き、ドキュメント化しているコマンドレットのコマンドノードを見つけます。</span><span class="sxs-lookup"><span data-stu-id="4b770-111">Open the cmdlet Help file and locate the Command node for the cmdlet you are documenting.</span></span> <span data-ttu-id="4b770-112">新しいコマンドレットを追加する場合は、新しいコマンドノードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b770-112">If you are adding a new cmdlet you will need to create a new Command node.</span></span> <span data-ttu-id="4b770-113">ヘルプファイルには、ヘルプコンテンツを提供しているコマンドレットごとにコマンドノードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b770-113">Your Help file will contain a Command node for each cmdlet that you are providing Help content for.</span></span> <span data-ttu-id="4b770-114">空のコマンドノードの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4b770-114">Here is an example of a blank Command node.</span></span>

    ```xml
    <command:command>
    </command:command>
    ```

1. <span data-ttu-id="4b770-115">次に示すように、[コマンド] ノードで [説明] ノードを見つけて、[パラメーター] ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b770-115">Within the Command node, locate the Description node and add a Parameters node as shown below.</span></span>
   <span data-ttu-id="4b770-116">パラメーターノードは1つしか使用できません。構文ノードの直後に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b770-116">Only one Parameters node is allowed, and it should immediately follow the Syntax node.</span></span>

    ```xml
    <command:command>
      <command:details></command:details>
      <maml:description></maml:description>
      <command:syntax></command:syntax>
      <command:parameters>
      </command:Parameters>
    </command:command>
    ```

1. <span data-ttu-id="4b770-117">次に示すように、[パラメーター] ノード内で、コマンドレットの各パラメーターの **パラメーター** ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b770-117">Within the Parameters node, add a **Parameter** node for each parameter of the cmdlet as shown below.</span></span>

   <span data-ttu-id="4b770-118">この例では、3つのパラメーターに **パラメーター** ノードが追加されています。</span><span class="sxs-lookup"><span data-stu-id="4b770-118">In this example, a **Parameter** node is added for three parameters.</span></span>

    ```xml
    <command:parameters>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
    </command:Parameters>
    ```

   <span data-ttu-id="4b770-119">これらは構文ノードで使用される XML タグと同じであるため、ここで指定するパラメーターは、構文ノードで指定されたパラメーターと一致する必要があるため、[構文] ノードからパラメーターノードをコピーし、[パラメーター] ノードに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="4b770-119">Because these are the same XML tags that are used in the Syntax node, and because the parameters specified here must match the parameters specified by the Syntax node, you can copy the Parameter nodes from the Syntax node and paste them into the Parameters node.</span></span> <span data-ttu-id="4b770-120">ただし、構文内の複数のパラメーターセットでパラメーターが指定されている場合でも、パラメーターノードのインスタンスを1つだけコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="4b770-120">However, be sure to copy only one instance of a Parameter node, even if the parameter is specified in multiple parameter sets in the syntax.</span></span>

1. <span data-ttu-id="4b770-121">各パラメーターノードについて、各パラメーターの特性を定義する属性値を設定します。</span><span class="sxs-lookup"><span data-stu-id="4b770-121">For each Parameter node, set the attribute values that define the characteristics of each parameter.</span></span> <span data-ttu-id="4b770-122">これらの属性には、required、グロビング、pipelineinput、position などがあります。</span><span class="sxs-lookup"><span data-stu-id="4b770-122">These attributes include the following: required, globbing, pipelineinput, and position.</span></span>

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

1. <span data-ttu-id="4b770-123">パラメーターノードごとに、パラメーターの名前を追加します。</span><span class="sxs-lookup"><span data-stu-id="4b770-123">For each Parameter node, add the name of the parameter.</span></span> <span data-ttu-id="4b770-124">パラメーターノードに追加されたパラメーター名の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4b770-124">Here is an example of the parameter name added to the Parameter node.</span></span>

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
      </command:parameter>
    </command:Parameters>
    ```

1. <span data-ttu-id="4b770-125">**パラメーター** ノードごとに、パラメーターの説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="4b770-125">For each **Parameter** node, add the description of the parameter.</span></span> <span data-ttu-id="4b770-126">**パラメーターノードに** 追加されたパラメーターの説明の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4b770-126">Here is an example of the parameter description added to the **Parameter** node.</span></span>

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

1. <span data-ttu-id="4b770-127">**パラメーター** ノードごとに、パラメーターの .net 型を追加します。</span><span class="sxs-lookup"><span data-stu-id="4b770-127">For each **Parameter** node, add the .NET type of the parameter.</span></span> <span data-ttu-id="4b770-128">パラメーターの型がパラメーター名と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b770-128">The parameter type is displayed along with the parameter name.</span></span>

   <span data-ttu-id="4b770-129">**パラメーターノードに** 追加された .net 型のパラメーターの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4b770-129">Here is an example of the parameter .NET type added to the **Parameter** node.</span></span>

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

1. <span data-ttu-id="4b770-130">**パラメーター** ノードごとに、パラメーターの既定値を追加します。</span><span class="sxs-lookup"><span data-stu-id="4b770-130">For each **Parameter** node, add the default value of the parameter.</span></span> <span data-ttu-id="4b770-131">コンテンツが表示されると、次の文がパラメーターの説明に追加されます。 **DefaultValue** が既定値です。</span><span class="sxs-lookup"><span data-stu-id="4b770-131">The following sentence is added to the parameter description when the content is displayed: **DefaultValue** is the default.</span></span>

   <span data-ttu-id="4b770-132">**パラメーターノードに** 既定値を追加する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4b770-132">Here is an example of the parameter default value is added to the **Parameter** node.</span></span>

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

1. <span data-ttu-id="4b770-133">複数の値を持つパラメーターごとに、使用可能な値ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4b770-133">For each Parameter that has multiple values, add a possible values node.</span></span>

   <span data-ttu-id="4b770-134">パラメーターに使用可能な2つの値を定義する、使用可能な値ノードのの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4b770-134">Here is an example of the of a possible values node that defines two possible values for the parameter</span></span>

    ```xml
    <dev:possiblevalues>
      <dev:possiblevalue>
        <dev:value>Unknown</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      </dev:possiblevalue>
      <dev:possiblevalue>
        <dev:value>String</dev:value>
        <maml:description>
          <maml:para></maml:para>
        </maml:description>
      </dev:possibleValue>
    </dev:possiblevalues>
    ```

<span data-ttu-id="4b770-135">ここでは、パラメーターを追加する際の注意事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b770-135">Here are some things to remember when adding parameters.</span></span>

- <span data-ttu-id="4b770-136">パラメーターの属性は、コマンドレットのヘルプトピックのすべてのビューに表示されません。</span><span class="sxs-lookup"><span data-stu-id="4b770-136">The attributes of the parameter are not displayed in all views of the cmdlet Help topic.</span></span> <span data-ttu-id="4b770-137">ただし、ユーザーがトピックの **Full** ( `Get-Help <cmdletname> -full` ) または **parameter** () ビューを要求したときに、パラメーターの説明の後の表に表示され `Get-Help <cmdletname> -parameter` ます。</span><span class="sxs-lookup"><span data-stu-id="4b770-137">However, they are displayed in a table following the parameter description when the user asks for the **Full** (`Get-Help <cmdletname> -full`) or **Parameter** (`Get-Help <cmdletname> -parameter`) view of the topic.</span></span>

- <span data-ttu-id="4b770-138">パラメーターの説明は、コマンドレットのヘルプトピックの中で最も重要な部分の1つです。</span><span class="sxs-lookup"><span data-stu-id="4b770-138">The parameter description is one of the most important parts of a cmdlet Help topic.</span></span> <span data-ttu-id="4b770-139">説明は簡潔で、完全なものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b770-139">The description should be brief, as well as thorough.</span></span> <span data-ttu-id="4b770-140">また、2つのパラメーターが相互に対話する場合など、パラメーターの説明が長すぎる場合は、コマンドレットのヘルプトピックの「NOTES」セクションでコンテンツを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b770-140">Also, remember that if the parameter description becomes too long, such as when two parameters interact with each other, you can add more content in the NOTES section of the cmdlet Help topic.</span></span>

  <span data-ttu-id="4b770-141">パラメーターの説明は、2種類の情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="4b770-141">The parameter description provides two types of information.</span></span>

- <span data-ttu-id="4b770-142">パラメーターを使用した場合のコマンドレットの動作</span><span class="sxs-lookup"><span data-stu-id="4b770-142">What the cmdlet does when the parameter is used.</span></span>

- <span data-ttu-id="4b770-143">パラメーターの有効な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="4b770-143">What a legal value is for the parameter.</span></span>

- <span data-ttu-id="4b770-144">パラメーター値は .NET オブジェクトとして表現されるため、ユーザーは従来のコマンドラインヘルプよりもこれらの値に関する詳細情報を必要とします。</span><span class="sxs-lookup"><span data-stu-id="4b770-144">Because the parameter values are expressed as .NET objects, users need more information about these values than they would in a traditional command-line Help.</span></span> <span data-ttu-id="4b770-145">パラメーターによって使用されるデータの種類をユーザーに通知し、例を含めます。</span><span class="sxs-lookup"><span data-stu-id="4b770-145">Tell the user what type of data the parameter is designed to accept, and include examples.</span></span>

<span data-ttu-id="4b770-146">パラメーターの既定値は、パラメーターがコマンドラインで指定されていない場合に使用される値です。</span><span class="sxs-lookup"><span data-stu-id="4b770-146">The default value of the parameter is the value that is used if the parameter is not specified on the command line.</span></span> <span data-ttu-id="4b770-147">既定値は省略可能であり、必須パラメーターなど、一部のパラメーターには必要ないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4b770-147">Note that the default value is optional, and is not needed for some parameters, such as required parameters.</span></span> <span data-ttu-id="4b770-148">ただし、ほとんどのオプションのパラメーターには既定値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b770-148">However, you should specify a default value for most optional parameters.</span></span>

<span data-ttu-id="4b770-149">既定値は、ユーザーがパラメーターを使用しない場合の効果を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4b770-149">The default value helps the user to understand the effect of not using the parameter.</span></span> <span data-ttu-id="4b770-150">"現在のディレクトリ" や "PowerShell のインストールディレクトリ ()" など、オプションのパスの既定値を指定し `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="4b770-150">Describe the default value very specifically, such as the "Current directory" or the "PowerShell installation directory (`$PSHOME`)" for an optional path.</span></span> <span data-ttu-id="4b770-151">また、 **passthru** パラメーターに使用される次の文など、既定値を説明する文を記述することもできます。 "passthru が指定されていない場合、コマンドレットはオブジェクトをパイプラインから渡しません。"</span><span class="sxs-lookup"><span data-stu-id="4b770-151">You can also write a sentence that describes the default, such as the following sentence used for the **PassThru** parameter: "If PassThru is not specified, the cmdlet does not pass objects down the pipeline."</span></span> <span data-ttu-id="4b770-152">また、値はフィールド名の **既定値** の反対に表示されるため、エントリに "Default value" という用語を含める必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4b770-152">Also, because the value is displayed opposite the field name **Default value**, you do not need to include the term "default value" in the entry.</span></span>

<span data-ttu-id="4b770-153">パラメーターの既定値は、コマンドレットのヘルプトピックのすべてのビューに表示されません。</span><span class="sxs-lookup"><span data-stu-id="4b770-153">The default value of the parameter is not displayed in all views of the cmdlet Help topic.</span></span> <span data-ttu-id="4b770-154">ただし、ユーザーがトピックの **Full** ( `Get-Help <cmdletname> -full` ) または **parameter** () ビューを要求したときに、パラメーターの説明に続くテーブル (パラメーター属性と共に) に表示され `Get-Help
<cmdletname> -parameter` ます。</span><span class="sxs-lookup"><span data-stu-id="4b770-154">However, it is displayed in a table (along with the parameter attributes) following the parameter description when the user asks for the **Full** (`Get-Help <cmdletname> -full`) or **Parameter** (`Get-Help
<cmdletname> -parameter`) view of the topic.</span></span>

<span data-ttu-id="4b770-155">次の XML は、 `<dev:defaultValue>` ノードに追加されたタグのペアを示して `<command:parameter>` います。</span><span class="sxs-lookup"><span data-stu-id="4b770-155">The following XML shows a pair of `<dev:defaultValue>` tags added to the `<command:parameter>` node.</span></span>
<span data-ttu-id="4b770-156">既定値は、終了タグの直後 `</command:parameterValue>` (パラメーター値が指定されている場合) または `</maml:description>` パラメーターの説明の終了タグの直後に続くことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4b770-156">Notice that the default value follows immediately after the closing `</command:parameterValue>` tag (when the parameter value is specified) or the closing `</maml:description>` tag of the parameter description.</span></span> <span data-ttu-id="4b770-157">name:</span><span class="sxs-lookup"><span data-stu-id="4b770-157">name.</span></span>

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

<span data-ttu-id="4b770-158">列挙型の値の追加</span><span class="sxs-lookup"><span data-stu-id="4b770-158">Add Values for Enumerated Types</span></span>

<span data-ttu-id="4b770-159">パラメーターに列挙型の複数の値または値が含まれている場合は、省略可能なノードを使用でき \<dev:possibleValues> ます。</span><span class="sxs-lookup"><span data-stu-id="4b770-159">If the parameter has multiple values or values of an enumerated type, you can use an optional \<dev:possibleValues> node.</span></span> <span data-ttu-id="4b770-160">このノードでは、複数の値の名前と説明を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4b770-160">This node allows you to specify a name and description for multiple values.</span></span>

<span data-ttu-id="4b770-161">列挙値の説明はコマンドレットによって表示される既定のヘルプビューには表示されません `Get-Help` が、他のヘルプビューアーではビューにこのコンテンツが表示される場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4b770-161">Be aware that the descriptions of the enumerated values do not appear in any of the default Help views displayed by the `Get-Help` cmdlet, but other Help viewers may display this content in their views.</span></span>

<span data-ttu-id="4b770-162">次の XML は、 `<dev:possibleValues>` 2 つの値が指定されたノードを示しています。</span><span class="sxs-lookup"><span data-stu-id="4b770-162">The following XML shows a `<dev:possibleValues>` node with two values specified.</span></span>

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
