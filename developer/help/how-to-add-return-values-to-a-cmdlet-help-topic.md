---
title: コマンドレットのヘルプ トピックに戻り値を追加する方法の値 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a52ab737-753c-4d04-8af7-758d5c805e18
caps.latest.revision: 7
ms.openlocfilehash: b21811e5a5a819c3d5c4a55fcbe685a84819b71d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859438"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに戻り値を追加する方法

このセクションでは、OUTPUTS セクションを Windows PowerShell® コマンドレットのヘルプ トピックを追加する方法について説明します。 OUTPUTS セクションでは、コマンドレットを返すか、パイプラインに渡すオブジェクトの .NET クラスが一覧表示します。

クラス、OUTPUTS セクションに追加できる数に制限はありません。 コマンドレットの戻り値の型がで囲まれた、\<コマンド: してください。 > で囲まれた各クラスを使用して、ノード、\<コマンド: returnValue > 要素。

コマンドレットが出力を生成しない場合は、このセクションを使用して、出力がないことを示します。 たとえば、クラス名の代わりに"None"を記述し、簡単な説明を提供します。 コマンドレットでは、条件付きで出力を生成する場合は、条件を説明し、条件付きの出力を説明するこのノードを使用します。

2 つには、スキーマ\<maml:description > の各要素\<コマンド: returnValue > 要素。 ただし、`Get-Help`コマンドレットのコンテンツのみを表示する、\<コマンド: returnValue >/\<maml:description > 要素。

Windows PowerShell 3.0 以降では、`Get-Help`コマンドレットのコンテンツを表示する、 \<maml:uri > 要素。 この要素では、.NET クラスを説明するトピックへのユーザーに指示できます。

次の XML に示す、 \<maml:returnValues > ノード。

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

次の XML を使用する例を示しています、 \<maml:returnValues > ノードをドキュメント出力の種類。

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



