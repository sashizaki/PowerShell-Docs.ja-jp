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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083367"
---
# <a name="how-to-add-parameter-information"></a>パラメーター情報を追加する方法

このセクションでは、コマンドレットのヘルプ トピックの PARAMETERS セクションに表示されるコンテンツを追加する方法について説明します。 ヘルプ トピックのパラメーター セクションでは、各コマンドレットのパラメーターの一覧を表示し、各パラメーターの詳細な説明を提供します。

PARAMETERS セクションの内容は、一貫性のあるヘルプ トピックの「構文」セクションのコンテンツを含む必要があります。 構文とパラメーターの両方のノードに同様の XML 要素が含まれているかどうかを確認するヘルプ作成者の役割です。

> [!NOTE]
> ヘルプ ファイル、開いている Windows PowerShell のインストール ディレクトリにある dll Help.xml ファイルの 1 つの完全なビュー。 たとえば、Microsoft.PowerShell.Commands.Management.dll Help.xml ファイルには、Windows PowerShell コマンドレットのいくつかのコンテンツが含まれています。

### <a name="to-add-parameters"></a>パラメーターを追加するには

1. コマンドレットのヘルプ ファイルを開き、文書化するコマンドレットのコマンドのノードを探します。 新しいコマンドレットを追加する場合は、新しいコマンド ノードを作成する必要があります。 ヘルプ ファイルは、各コマンドレットのヘルプ コンテンツを提供しているコマンドのノードが含まれます。 コマンドの空白ノードの例を次に示します。

    ```xml
    <command:command>
    </command:command>
    ```

2. コマンド ノード内で、[説明] ノードを見つけて次に示すように、[パラメーター] ノードを追加します。 パラメーター ノードの 1 つだけが許可され、すぐに、構文ノードに従ってください。

    ```xml
    <command:command>
      <command:details></command:details>
      <maml:description></maml:description>
      <command:syntax></command:syntax>
      <command:parameters>
      </command:Parameters>
    </command:command>
    ```

3. [パラメーター] ノード内には、次に示すよう、コマンドレットの各パラメーターのパラメーター ノードを追加します。

   この例では、3 つのパラメーターのパラメーター ノードが追加されます。

    ```xml
    <command:parameters>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
    </command:Parameters>
    ```

   これらは、構文ノードが使用され、ここで、パラメーターが指定されているため、構文ノードで指定されたパラメーターに一致する必要がありますが、同じ XML タグであるためは、構文ノードからパラメーター ノードをコピーし、パラメーター ノードに貼り付けます。 ただし、必ずパラメーター ノードの 1 つだけのインスタンスのコピーで、構文で複数のパラメーターを設定で、パラメーターが指定した場合でもです。

4. パラメーターの各ノードの各パラメーターの特性を定義する属性の値を設定します。 これらの属性には、次が含まれます。 必要に応じて、グロビング、pipelineinput、および位置。

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

5. パラメーターの各ノードには、パラメーターの名前を追加します。 パラメーター ノードに追加するパラメーター名の例を次に示します。

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
      </command:parameter>
    </command:Parameters>
    ```

6. パラメーターの各ノードには、パラメーターの説明を追加します。 パラメーター ノードに追加されたパラメーターの説明の例を次に示します。

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

7. パラメーターの各ノードには、パラメーターの .NET Framework 型を追加します。 パラメーターの型パラメーター名が表示されます。

   パラメーター ノードに追加されたパラメーターの .NET Framework 型の例を次に示します。

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

8. パラメーターの各ノードには、パラメーターの既定値を追加します。 次の文は、コンテンツを表示するときに、パラメーターの説明に追加されます。"DefaultValue"では、既定値です。

   パラメーター ノードに追加パラメーターの既定値の例を次に示します。

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

9. 複数の値を持つ各パラメーターの使用可能な値のノードを追加します。

   次の例に示します、パラメーターの 2 つの値を定義する使用可能な値のノードの

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

パラメーターを追加するときの注意点を次に示します。

- パラメーターの属性は、コマンドレットのヘルプ トピックのすべてのビューでは表示されません。 ただし、完全なユーザーを要求するときに、パラメーターの説明を次の表に表示されている (Get-help\<コマンドレット名 >-フル) またはパラメーター (Get-help\<コマンドレット名 >-パラメーター) トピックの表示。

- パラメーターの説明では、コマンドレットのヘルプ トピックの最も重要な部分の 1 つです。 概要と詳細な説明があります。 また、パラメーターの説明になると、長すぎる、2 つのパラメーターが相互にやり取りするときなど、追加することできますより多くのコンテンツのコマンドレット ヘルプ トピックのノートのセクションでは注意してください。

  パラメーターの説明では、2 種類の情報を提供します。

- どのようなコマンドレットは、パラメーターを使用する場合は。

- どのような有効な値は、パラメーターです。

- パラメーターの値は .NET Framework のオブジェクトとして表される、ため、ユーザーは従来のコマンドラインのヘルプ内にある場合よりも詳細については、これらの値は必要があります。 パラメーターが、そのまま使用するように設計するデータの種類に、ユーザーに通知し、例を含めます。

パラメーターの既定値は、コマンドラインでパラメーターが指定されていない場合に使用される値です。 既定値は省略可能で、必要なパラメーターなど、いくつかのパラメーターが必要ないことに注意してください。 ただし、ほとんどの省略可能なパラメーターの既定値を指定する必要があります。

既定値は、ユーザーを使用していない、パラメーターの影響を理解するのには役立ちます。 非常に具体的には、既定値「現在のディレクトリ」または「Windows PowerShell のインストール ディレクトリ ($pshome)」オプションのパスなどについて説明します。 既定値は、次の文の使用などを説明する文章を記述することも、`PassThru`パラメーター。「PassThru が指定されていない場合、コマンドレットは渡さないオブジェクトをパイプライン。」  また、反対のフィールド名、値が表示されるためです"**既定値**"、「既定値」という用語をエントリに含める必要はありません。

パラメーターの既定値は、コマンドレットのヘルプ トピックのすべてのビューでは表示されません。 ただし、パラメーターの説明を以下に、完全なユーザーを要求する (パラメーターの属性) と共にテーブルに表示されます (Get-help\<コマンドレット名 >-フル) またはパラメーター (Get-help\<コマンドレット名 >-パラメーター) ビュートピックです。

次の XML は 1 組の`<dev:defaultValue>`にタグを追加、`<command:parameter>`ノード。 既定値が終了した直後に続く通知`</command:parameterValue>`(パラメーターの値が指定された) ときにタグまたは終了`</maml:description>`パラメーターの説明のタグ。 名前。

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

列挙型の値を追加します。

省略可能なを使用することができます、パラメーターに複数の値または列挙型の値がある場合は、 \<dev:possibleValues > ノード。 このノードでは、複数の値の説明と名前を指定できます。

列挙値の説明については、表示されないことで、既定値のいずれかによって表示されるヘルプのビューに注意してください、`Get-Help`コマンドレットが、その他のヘルプ ビューアーは、ビューにこのコンテンツを表示可能性があります。

次の XML に示す、`<dev:possibleValues>`指定された 2 つの値を持つノード。

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