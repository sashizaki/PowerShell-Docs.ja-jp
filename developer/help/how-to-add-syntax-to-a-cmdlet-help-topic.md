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
ms.openlocfilehash: 2e9dbc9ff8f9507f2008cd6e114ba6fec36b10bf
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054613"
---
# <a name="how-to-add-syntax-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに構文を追加する方法

- [パラメーター属性](#Parameter-Attributes)

- [パラメーター値の属性](#Parameter-Value-Attributes)

- [構文情報の収集](#Gathering-Syntax-Information)

- [XML 構文ダイアグラムのコーディング](#Coding-the-Syntax-Diagram-XML)

## <a name="things-to-know-about-the-syntax-diagram-in-cmdlet-help"></a>コマンドレット ヘルプの構文ダイアグラムについて知っておくべきこと

コマンドレットのヘルプ ファイルで構文ダイアグラムの XML コードを開始する前に、パラメーターの属性と構文ダイアグラムでそのデータを表示する方法など、提供する必要があるデータの種類を明確に把握するには、このセクションを読む.

### <a name="parameter-attributes"></a>パラメーター属性

- 必須

  - True の場合、パラメーター セットを使用するすべてのコマンドで、パラメーターがあります。

  - False の場合、パラメーターはパラメーター セットを使用するすべてのコマンドでは省略可能です。

- 位置

  - という名前の場合、パラメーター名が必要です。

  - 場合、位置指定パラメーター名は省略可能です。 省略すると、パラメーターの値は、コマンドで指定された位置にあります。 場合は、値は位置の「1」、たとえば、=、パラメーター値には初または唯一無名のコマンドのパラメーターの値。

- パイプラインの入力

  - True (ByValue) パラメーターへの入力をパイプすることができます。 入力が関連付けられている (「バインドする」) で、プロパティ名とオブジェクトの種類も予期される型が一致しない場合でもパラメーター。 Windows PowerShell ですか。コンポーネントのパラメーター バインドしようと適切な型への入力を変換し、型を変換できない場合にのみコマンドが失敗します。 パラメーター セットで 1 つだけのパラメーター値で関連付けることができます。

  - True の場合 (ByPropertyName) パラメーターへの入力をパイプすることができます。 ただし、入力は、パラメーター名が、入力オブジェクトのプロパティの名前と一致する場合にのみ、パラメーターに関連付けられます。 たとえば、パラメーター名は`Path`オブジェクトがパスをという名前のプロパティがある場合のみをコマンドレットにパイプ処理されたオブジェクトがそのパラメーターと関連付けられます。

  - 場合は true (ByValue、ByPropertyName) がプロパティ名または値のいずれかのパラメーターへの入力をパイプ処理できます。 パラメーター セットで 1 つだけのパラメーター値で関連付けることができます。

  - False の場合は、このパラメーターへの入力をパイプすることはできません。

- グロビング

  - True の場合、ユーザーがパラメーター値を入力するテキストは、ワイルドカード文字を含めることができます。

  - False の場合、ユーザーがパラメーター値を入力するテキストは、ワイルドカード文字を含めることはできません。

### <a name="parameter-value-attributes"></a>パラメーター値の属性

- 必須

  - True の場合は、コマンドで、パラメーターを使用するたびに、指定した値が使用する必要があります。

  - False の場合、パラメーターの値は省略可能です。 通常、ある場合にのみ、パラメーターのいくつかの有効な値のいずれかのように列挙型では、値は省略できます。

パラメーターの値の必須の属性は、パラメーターの必須の属性と異なります。

パラメーターの必須の属性は、かどうか、パラメーター (とその値) 含める必要がある、コマンドレットを呼び出すときを示します。 これに対し、必要なパラメーターの値の属性は、コマンドのパラメーターが含まれている場合にのみ使用されます。 これは、その特定の値をパラメーターと共に使用する必要があるかどうかを示します。

通常、プレース ホルダーをパラメーター値が必要ですし、リテラルのパラメーター値のパラメーターと共に使用されるいくつかの値のいずれかがいるため、必須ではありません。

### <a name="gathering-syntax-information"></a>構文情報の収集

1. コマンドレット名で始まります。

   ```
   SYNTAX
       Get-Tech
   ```

2. コマンドレットのすべてのパラメーターを一覧表示します。 入力をダッシュ ("dash"または""(ASCII 45) 前にマイナス記号各パラメーター名とも呼ばれます。 パラメーターを (いくつかのコマンドレットは 1 つだけのパラメーター セットである必要があります) のパラメーター セットに分けます。 Get Tech この例では、コマンドレットは、2 つのパラメーター セットにします。

   ```
   SYNTAX
       Get-Tech -name -type
       Get-Tech -ID -list -type
   ```

   各パラメーターをコマンドレットの名前を持つセットを開始します。

   最初に設定する既定のパラメーターを一覧表示します。 既定のパラメーターは、コマンドレット クラスによって指定されます。

   各パラメーターを設定する必要がありますは最初に示される位置指定パラメーターがない限り、その一意のパラメーターを最初に、リストします。 前の例では、名前と ID パラメーターは、2 つのパラメーター セットの一意のパラメーター (各パラメーター セットは、そのパラメーターのセットに一意である 1 つのパラメーターをいる必要があります)。 これにより、どのようなパラメーターのパラメーターを指定する必要がある設定を識別するためにユーザーが簡単にします。

   コマンドに表示される順序でパラメーターを一覧表示します。 順序は関係ありませんが場合、は、関連パラメーターを同時に、一覧表示するか、最初に最もよく使用されるパラメーターを一覧表示します。

   コマンドレットが ShouldProcess をサポートしている場合は、WhatIf、Confirm パラメーターを一覧表示してください。

   (Verbose、Debug、ErrorAction など) の構文ダイアグラムでの共通のパラメーターは表示されません。 `Get-Help`コマンドレット ヘルプ トピックを表示するときにその情報を追加します。

3. パラメーターの値を追加します。 Windows powershell?、パラメーター値は、.NET 型によって表されます。 ただし、型名に短縮できます、System.String の"string"など。

   ```
   SYNTAX
       Get-Tech -name string -type basic advanced
       Get-Tech -ID int -list -type basic advanced
   ```

   その意味が明確に"string"に System.String および System.Int32 の"int"などの型の省略形します。

   列挙型のすべての値を一覧表示など、型パラメーターを指定する前の例では、"basic"または「詳細」に設定することができます。

   スイッチ パラメーターは、前の例の一覧など、値はありません。

4. リテラルのパラメーター値と比較して、プレース ホルダーをパラメーターの値には、山かっこを追加します。

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

6. (位置指定パラメーター) の省略可能なパラメーター名を角かっこで囲みます。 次の例では、Name パラメーターなど、位置指定されるパラメーターの名前をコマンドに含まれる必要はありません。

   ```
   SYNTAX
       Get-Tech [-name] <string> [-type basic advanced]
       Get-Tech -ID <int> [-list] [-type basic advanced]
   ```

7. パラメーターの値は、Name パラメーターの名前の一覧など、複数の値を格納する場合は、パラメーター値の直後の角かっこのペアを追加します。

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type basic advanced]
       Get-Tech -ID <int[]> [-list] [-type basic advanced]
   ```

8. パラメーターまたはパラメーター値からユーザーを選択できる場合、型パラメーターなど、選択肢を中かっこで囲み、排他的 OR symbol(;) で区切ります。

   ```
   SYNTAX
       Get-Tech [-name] <string[]> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

9. パラメーターの値が引用符やかっこなどの特定の書式を使用する必要がある場合は、構文の形式を表示します。

   ```
   SYNTAX
       Get-Tech [-name] <"string[]"> [-type {basic | advanced}]
       Get-Tech -ID <int[]> [-list] [-type {basic | advanced}]
   ```

## <a name="coding-the-syntax-diagram-xml"></a>XML 構文ダイアグラムのコーディング

終わる説明ノードの直後に、XML の構文ノードを開始、 \</maml:description > タグです。 構文ダイアグラムで使用されるデータの収集方法の詳細については、次を参照してください。[構文情報の収集](#Gathering-Syntax-Information)します。

### <a name="adding-a-syntax-node"></a>構文ノードを追加します。

コマンドレットのヘルプ トピックに表示されている構文ダイアグラムは、XML の構文ノード内のデータから生成されます。 場合、構文ノードが、ペアで囲まれた\<コマンドの構文: > タグです。 各パラメーターのセットのペアで囲まれているコマンドレットの\<コマンド: syntaxitem > タグです。 数に制限はありません\<コマンド: syntaxitem > タグを追加することができます。

次の例では、2 つのパラメーター セットの構文項目ノードを持つ構文ノードを示します。

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

### <a name="adding-the-cmdlet-name-to-the-parameter-set-data"></a>データを設定するパラメーターをコマンドレット名を追加します。

コマンドレットの各パラメーター セットは、構文項目のノードで指定されます。 構文項目の各ノードは、のペアで始まる\<maml:name > タグを含むコマンドレットの名前。

次の例には、2 つのパラメーター セットの構文項目ノードを持つ構文ノードが含まれます。

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

囲まれた構文項目ノードに追加された各パラメーターが指定されて\<コマンド: パラメーター > タグです。 ペアを作成する必要があります\<コマンド: パラメーター > タグを除く、Windows PowerShell によって提供される共通パラメーター、パラメーター セットに含める各パラメーターのですか。

開始の属性\<コマンド: パラメーター > タグは、構文ダイアグラムでのパラメーターの表示方法を決定します。 パラメーターの属性については、次を参照してください。[パラメーター属性](#Parameter-Attributes)します。

> [!NOTE]
> \<コマンド: パラメーター > タグは子要素をサポートする\<maml:description > のコンテンツを表示することはありません。 パラメーターの説明は、XML のパラメーターのノードで指定されます。 構文項目の情報は、間の不整合を回避するために bodes 省略 [パラメーター] ノード、(\<maml:description > か、空白のままにします。

次の例には、2 つのパラメーターを設定するパラメーターの構文項目ノードが含まれます。

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
