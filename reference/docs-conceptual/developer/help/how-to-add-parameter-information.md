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
ms.openlocfilehash: b9ccca75c2d9126e84a7f486ffe803042a742b62
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83565562"
---
# <a name="how-to-add-parameter-information"></a>パラメーター情報を追加する方法

このセクションでは、コマンドレットのヘルプトピックの「パラメーター」セクションに表示されるコンテンツを追加する方法について説明します。 ヘルプトピックの「パラメーター」セクションでは、コマンドレットの各パラメーターの一覧を示し、各パラメーターの詳細について説明します。

PARAMETERS セクションの内容は、ヘルプトピックの「構文」セクションの内容と一致している必要があります。 構文とパラメーターノードの両方に類似した XML 要素が含まれているかどうかを確認するのは、ヘルプの作成者の責任です。

> [!NOTE]
> ヘルプファイルの完全なビューを表示するには、Windows PowerShell のインストールディレクトリにあるいずれかの dll-Help ファイルを開きます。 たとえば、dll-Help ファイルには、いくつかの Windows PowerShell コマンドレットのコンテンツが含まれています。

### <a name="to-add-parameters"></a>パラメーターを追加するには

1. コマンドレットのヘルプファイルを開き、ドキュメント化しているコマンドレットのコマンドノードを見つけます。 新しいコマンドレットを追加する場合は、新しいコマンドノードを作成する必要があります。 ヘルプファイルには、ヘルプコンテンツを提供しているコマンドレットごとにコマンドノードが含まれています。 空のコマンドノードの例を次に示します。

    ```xml
    <command:command>
    </command:command>
    ```

2. 次に示すように、[コマンド] ノードで [説明] ノードを見つけて、[パラメーター] ノードを追加します。 パラメーターノードは1つしか使用できません。構文ノードの直後に指定する必要があります。

    ```xml
    <command:command>
      <command:details></command:details>
      <maml:description></maml:description>
      <command:syntax></command:syntax>
      <command:parameters>
      </command:Parameters>
    </command:command>
    ```

3. 次に示すように、[パラメーター] ノード内で、コマンドレットの各パラメーターのパラメーターノードを追加します。

   この例では、3つのパラメーターにパラメーターノードが追加されています。

    ```xml
    <command:parameters>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
      <command:parameter></command:parameter>
    </command:Parameters>
    ```

   これらは構文ノードで使用される XML タグと同じであるため、ここで指定するパラメーターは、構文ノードで指定されたパラメーターと一致する必要があるため、[構文] ノードからパラメーターノードをコピーし、[パラメーター] ノードに貼り付けることができます。 ただし、構文内の複数のパラメーターセットでパラメーターが指定されている場合でも、パラメーターノードのインスタンスを1つだけコピーしてください。

4. 各パラメーターノードについて、各パラメーターの特性を定義する属性値を設定します。 これらの属性には、required、グロビング、pipelineinput、position などがあります。

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

5. パラメーターノードごとに、パラメーターの名前を追加します。 パラメーターノードに追加されたパラメーター名の例を次に示します。

    ```xml
    <command:parameters>
      <command:parameter required="true" globbing="true"
               pipelineInput="false" position="named">
        <maml:name> Add parameter name...  </maml:name>
      </command:parameter>
    </command:Parameters>
    ```

6. パラメーターノードごとに、パラメーターの説明を追加します。 パラメーターノードに追加されたパラメーターの説明の例を次に示します。

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

7. パラメーターノードごとに、パラメーターの .NET Framework 型を追加します。 パラメーターの型がパラメーター名と共に表示されます。

   パラメーターノードに追加された .NET Framework 型のパラメーターの例を次に示します。

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

8. パラメーターノードごとに、パラメーターの既定値を追加します。 コンテンツが表示されると、次の文がパラメーターの説明に追加されます。 "DefaultValue" が既定値です。

   パラメーターノードに既定値を追加する例を次に示します。

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

9. 複数の値を持つパラメーターごとに、使用可能な値ノードを追加します。

   パラメーターに使用可能な2つの値を定義する、使用可能な値ノードのの例を次に示します。

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

ここでは、パラメーターを追加する際の注意事項について説明します。

- パラメーターの属性は、コマンドレットのヘルプトピックのすべてのビューに表示されません。 ただし、ユーザーがトピックの完全な (Get-help \< の形式名>) またはパラメーター (get-help の ">") ビューを要求したときに、パラメーターの説明の後の表に表示され \< ます。

- パラメーターの説明は、コマンドレットのヘルプトピックの中で最も重要な部分の1つです。 説明は簡潔で、完全なものである必要があります。 また、2つのパラメーターが相互に対話する場合など、パラメーターの説明が長すぎる場合は、コマンドレットのヘルプトピックの「NOTES」セクションでコンテンツを追加することもできます。

  パラメーターの説明は、2種類の情報を提供します。

- パラメーターを使用した場合のコマンドレットの動作

- パラメーターの有効な値を指定します。

- パラメーター値は .NET Framework オブジェクトとして表現されるため、ユーザーは従来のコマンドラインヘルプよりもこれらの値に関する詳細情報を必要とします。 パラメーターによって使用されるデータの種類をユーザーに通知し、例を含めます。

パラメーターの既定値は、パラメーターがコマンドラインで指定されていない場合に使用される値です。 既定値は省略可能であり、必須パラメーターなど、一部のパラメーターには必要ないことに注意してください。 ただし、ほとんどのオプションのパラメーターには既定値を指定する必要があります。

既定値は、ユーザーがパラメーターを使用しない場合の効果を理解するのに役立ちます。 "現在のディレクトリ" や "Windows PowerShell インストールディレクトリ ($pshome)" など、オプションのパスの既定値に特に説明を付けます。 また、パラメーターに使用される次の文など、既定値を説明する文を記述することもできます `PassThru` 。 "If PassThru が指定されていない場合、コマンドレットはオブジェクトをパイプラインから渡しません。"  また、値はフィールド名 "**default value**" の反対に表示されるため、エントリに "default value" という用語を含める必要はありません。

パラメーターの既定値は、コマンドレットのヘルプトピックのすべてのビューに表示されません。 ただし、ユーザーがトピックの完全な (Get-help \< のファイル名>) またはパラメーター (get-help の \< 形式名> パラメーター) を要求したときに、パラメーターの説明の後にあるテーブル (パラメーター属性と共に) に表示されます。

次の XML は、 `<dev:defaultValue>` ノードに追加されたタグのペアを示して `<command:parameter>` います。 既定値は、終了タグの直後 `</command:parameterValue>` (パラメーター値が指定されている場合) または `</maml:description>` パラメーターの説明の終了タグの直後に続くことに注意してください。 name:

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

列挙型の値の追加

パラメーターに列挙型の複数の値または値が含まれている場合は、オプションの dev: 使用可能な \< 値> ノードで使用できます。 このノードでは、複数の値の名前と説明を指定できます。

列挙値の説明はコマンドレットによって表示される既定のヘルプビューには表示されません `Get-Help` が、他のヘルプビューアーではビューにこのコンテンツが表示される場合があることに注意してください。

次の XML は、 `<dev:possibleValues>` 2 つの値が指定されたノードを示しています。

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
