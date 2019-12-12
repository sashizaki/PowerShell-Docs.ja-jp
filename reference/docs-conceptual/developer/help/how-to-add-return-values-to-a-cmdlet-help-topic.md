---
title: コマンドレットに戻り値を追加する方法に関するヘルプトピック |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a52ab737-753c-4d04-8af7-758d5c805e18
caps.latest.revision: 7
ms.openlocfilehash: b21811e5a5a819c3d5c4a55fcbe685a84819b71d
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367801"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに戻り値を追加する方法

このセクションでは、Windows PowerShell®コマンドレットのヘルプトピックに OUTPUTS セクションを追加する方法について説明します。 OUTPUTS セクションには、コマンドレットが返す、またはパイプラインを渡すオブジェクトの .NET クラスが一覧表示されます。

OUTPUTS セクションに追加できるクラスの数に制限はありません。 コマンドレットの戻り値の型は、\<コマンド: returnValues > node で囲みます。各クラスは、\<command: 戻り値 > 要素で囲まれています。

コマンドレットで出力が生成されない場合は、出力がないことを示すためにこのセクションを使用します。 たとえば、クラス名の代わりに "None" を記述し、簡単な説明を入力します。 コマンドレットによって出力が条件付きで生成される場合は、このノードを使用して条件を説明し、条件付き出力を記述します。

このスキーマには、各 \<コマンドに2つの \<maml: description > 要素が含まれています: 戻り > 要素。 ただし、`Get-Help` コマンドレットを実行すると、\<command: 戻り >/\<maml: description > 要素の内容のみが表示されます。

Windows PowerShell 3.0 以降では、`Get-Help` コマンドレットは \<maml: uri > 要素の内容を表示します。 この要素を使用すると、.NET クラスを説明するトピックにユーザーを誘導できます。

次の XML は、\<maml: returnValues > ノードを示しています。

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> Class Name </maml:name>
      <maml:uri>  URI of a topic that describes the class </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
       <maml:para> Brief description <maml:para>

</maml:description>
  </command: returnValue>
</command: returnValues>
```

次の XML は、\<maml: returnValues > ノードを使用して、出力の種類を文書化する例を示しています。

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  http://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Get-Date returns a DateTime object. <maml:para>
    </maml:description>
  </command: returnValue>
</command: returnValues>
```



