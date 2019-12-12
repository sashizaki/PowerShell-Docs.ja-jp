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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361211"
---
# <a name="how-to-add-syntax-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに構文を追加する方法

コマンドレットのヘルプファイルで構文ダイアグラムの XML のコーディングを開始する前に、このセクションを参照して、パラメーター属性など、指定する必要があるデータの種類と、そのデータが構文図に表示される方法を明確に把握してください。「」を参照してください。

### <a name="parameter-attributes"></a>パラメーター属性

- 必須

  - True の場合、パラメーターセットを使用するすべてのコマンドにパラメーターが指定されている必要があります。

  - False の場合、パラメーターセットを使用するすべてのコマンドでパラメーターを省略できます。

- 位置

  - 名前が指定されている場合は、パラメーター名が必要です。

  - 位置指定の場合、パラメーター名は省略可能です。 省略した場合、パラメーター値は、コマンド内の指定した位置にある必要があります。 たとえば、値が position = "1" の場合、パラメーター値は、コマンドの最初のパラメーター値または無名のパラメーター値である必要があります。

- パイプラインの入力

  - True (ByValue) の場合は、パラメーターに入力をパイプすることができます。 入力は、プロパティ名とオブジェクトの型が予期される型と一致しない場合でも、パラメーターに関連付けられています ("バインド先")。 Windows PowerShell とはパラメーターバインドコンポーネントは、入力を正しい型に変換しようとし、型を変換できない場合にのみコマンドを失敗とします。 パラメーターセット内の1つのパラメーターのみを値で関連付けることができます。

  - True (ByPropertyName) の場合は、パラメーターに入力をパイプ処理できます。 ただし、入力がパラメーターに関連付けられるのは、パラメーター名が入力オブジェクトのプロパティの名前と一致する場合のみです。 たとえば、パラメーター名が `Path`の場合、コマンドレットにパイプされたオブジェクトは、オブジェクトに path という名前のプロパティがある場合にのみ、そのパラメーターに関連付けられます。

  - True (ByValue, Byvalue) の場合は、プロパティ名または値によって入力をパラメーターにパイプすることができます。 パラメーターセット内の1つのパラメーターのみを値で関連付けることができます。

  - False の場合、このパラメーターに入力をパイプすることはできません。

- グロビング

  - True の場合、ユーザーがパラメーター値に入力するテキストには、ワイルドカード文字を含めることができます。

  - False の場合、ユーザーがパラメーター値に入力するテキストには、ワイルドカード文字を含めることはできません。

### <a name="parameter-value-attributes"></a>パラメーター値の属性

- 必須

  - True の場合は、コマンドでパラメーターを使用するときに、指定した値を使用する必要があります。

  - False の場合、パラメーター値は省略可能です。 通常、値は、列挙型など、パラメーターのいくつかの有効な値のいずれかである場合にのみ省略可能です。

パラメーター値の必須属性が、パラメーターの必須属性と異なります。

パラメーターの required 属性は、コマンドレットを呼び出すときに、パラメーター (およびその値) を含める必要があるかどうかを示します。 これに対して、パラメーター値の必須の属性は、パラメーターがコマンドに含まれている場合にのみ使用されます。 パラメーターと共に特定の値を使用する必要があるかどうかを示します。

通常、プレースホルダーであるパラメーター値は必須であり、リテラルであるパラメーター値は必須ではありません。これは、パラメーターで使用される可能性のあるいくつかの値の1つであるためです。

### <a name="gathering-syntax-information"></a>構文情報を収集しています

1. コマンドレット名を使用して開始します。

   ```
   SYNTAX
       Get-Tech
   ```

2. コマンドレットのすべてのパラメーターを一覧表示します。 各パラメーター名の前にダッシュ ("ダッシュ" または "マイナス記号" (ASCII 45) とも呼ばれる) を入力します。 パラメーターをパラメーターセットに分割します (一部のコマンドレットにはパラメーターセットが1つだけ含まれる場合があります)。 この例では、Get-help コマンドレットに2つのパラメーターセットがあります。

   ```
   SYNTAX
       Get-Tech -name -type
       Get-Tech -ID -list -type
   ```

   コマンドレット名を使用して各パラメーターセットを開始します。

   最初に既定のパラメーターセットを一覧表示します。 既定のパラメーターは、コマンドレットクラスによって指定されます。

   最初に表示する必要がある位置指定パラメーターがない場合は、各パラメーターセットに対して、最初に一意のパラメーターをリストします。 前の例では、Name パラメーターと ID パラメーターは、2つのパラメーターセットの一意のパラメーターです (各パラメーターセットには、そのパラメーターセットに固有のパラメーターを1つ指定する必要があります)。 これにより、パラメーターセットに必要なパラメーターをユーザーが簡単に識別できるようになります。

   コマンドに表示される順序でパラメーターを一覧表示します。 順序が問題にならない場合は、関連するパラメーターをまとめて表示するか、最も頻繁に使用されるパラメーターを最初に一覧表示します。

   コマンドレットで入力処理がサポートされている場合は、WhatIf パラメーターと Confirm パラメーターを必ず指定してください。

   構文図に共通パラメーター (Verbose、Debug、ErrorAction など) を一覧表示しません。 `Get-Help` コマンドレットは、ヘルプトピックを表示するときに、その情報を追加します。

3. パラメーターの値を追加します。 Windows PowerShell では、パラメーター値は .NET 型によって表されます。 ただし、system.string の "文字列" のように、型名を省略することもできます。

   ```
   SYNTAX
       Get-Tech -name string -type basic advanced
       Get-Tech -ID int -list -type basic advanced
   ```

   System.string の場合は "string"、system.string の場合は "int" など、意味が明確でない限り型を省略します。

   前の例の-type パラメーターなど、列挙のすべての値を一覧表示します。これは、"basic" または "advanced" に設定できます。

   前の例の-list などのスイッチパラメーターには値がありません。

4. リテラルであるパラメーター値と比較して、プレースホルダーであるパラメーター値に山かっこを追加します。

   ```
   SYNTAX
       Get-Tech -name <string> -type basic advanced
       Get-Tech -ID <int> -list -type basic advanced
   ```

5. 省略可能なパラメーターとその値を角かっこで囲みます。

   ```
   SYNTAX
       Get-Tech -name <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

6. 省略可能なパラメーター名 (位置指定パラメーターの場合) を角かっこで囲みます。 次の例の名前パラメーターなど、位置指定のパラメーターの名前は、コマンドに含める必要はありません。

   ```
   SYNTAX
       Get-Tech [-name] <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

7. パラメーター値に複数の値 (Name パラメーターの名前のリストなど) を含めることができる場合は、パラメーター値の直後に角かっこのペアを追加します。

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type basic advanced]
       Get-Tech -ID <int[]> [-list] [-type basic advanced]
   ```

8. ユーザーがパラメーターまたはパラメーター値 (型パラメーターなど) から選択できる場合は、選択項目を中かっこで囲み、排他または記号 (;) で区切ります。

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

9. パラメーター値で引用符やかっこなどの特定の書式を使用する必要がある場合は、構文で形式を表示します。

   ```
   SYNTAX
       Get-Tech [-name] <"string[]"> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

## <a name="coding-the-syntax-diagram-xml"></a>構文図の XML のコーディング

XML の構文ノードは説明ノードの直後に始まり、\</maml: description > タグで終わります。 構文ダイアグラムで使用されるデータの収集の詳細については、「[構文情報の収集](#gathering-syntax-information)」を参照してください。

### <a name="adding-a-syntax-node"></a>構文ノードの追加

コマンドレットのヘルプトピックに表示される構文図は、XML の構文ノードのデータから生成されます。 構文ノードは、\<コマンド: 構文 > タグの場合、ペアで囲まれます。 コマンドレットの各パラメーターセットを \<コマンドのペア > タグと組み合わせて使用します。 \<コマンドの数に制限はありません: syntaxitem > タグを追加できます。

次の例は、2つのパラメーターセットの構文項目ノードを持つ構文ノードを示しています。

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

### <a name="adding-the-cmdlet-name-to-the-parameter-set-data"></a>パラメーターセットデータへのコマンドレット名の追加

コマンドレットの各パラメーターセットは、[構文項目] ノードで指定します。 各構文項目ノードは、コマンドレットの名前を含む \<maml: name > タグのペアで始まります。

次の例には、2つのパラメーターセットの構文項目ノードを持つ構文ノードが含まれています。

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

### <a name="adding-parameters"></a>パラメーターの追加

構文項目ノードに追加された各パラメーターは、\<コマンドパラメーター > タグのペア内で指定されます。 パラメーターセットに含まれる各パラメーターに対して、パラメーター > の \<コマンドのペアが必要です。ただし、Windows PowerShell で提供される共通のパラメーターは除きます。

開始 \<コマンド: parameter > タグの属性によって、構文図にパラメーターがどのように表示されるかが決まります。 パラメーター属性の詳細については、「[パラメーター属性](#parameter-attributes)」を参照してください。

> [!NOTE]
> \<コマンド: parameter > タグは、コンテンツが表示されない maml: description > \<子要素をサポートします。 パラメーターの説明は、XML のパラメーターノードで指定します。 構文項目兆しとパラメーターノードの情報が矛盾しないようにするには、(\<maml: description > を省略するか、空のままにします。

次の例には、2つのパラメーターを持つパラメーターセットの構文項目ノードが含まれています。

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
