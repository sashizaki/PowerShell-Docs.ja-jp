---
title: コマンドレットに入力の種類を追加する方法に関するヘルプトピック |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 432798e4-5d69-46b1-9517-ff09bffaa4be
caps.latest.revision: 7
ms.openlocfilehash: f213605dda0132051d983f8608515325e815c455
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361241"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに入力の種類を追加する方法

このセクションでは、Windows PowerShell®コマンドレットのヘルプトピックに入力セクションを追加する方法について説明します。 [入力] セクションには、コマンドレットがパイプラインからの入力として受け取るオブジェクトの .NET クラスが、値またはプロパティ名のいずれかで一覧表示されます。

入力セクションに追加できるクラスの数に制限はありません。 入力の種類は @no__t 0command: inputTypes > node で囲まれており、各クラスは \<command: inputType > 要素で囲まれています。

スキーマには、各 \<command: inputType > 要素に2つの @no__t 0maml: description > 要素が含まれています。 ただし、`Get-Help` コマンドレットは、\<command: inputType >/\<maml: description >) 要素の内容のみを表示します。

Windows PowerShell 3.0 以降では、`Get-Help` コマンドレットは、@no__t 1maml: uri > 要素の内容を表示します。 この要素を使用すると、.NET クラスを説明するトピックにユーザーを誘導できます。

次の XML は、@no__t 0maml: inputTypes > ノードを示しています。

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> Class name </maml:name>
      <maml:uri>  URI of a topic that describes the class </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Brief description </maml:para>
    </maml:description>
  </command:inputType>
</command:inputTypes>
```

次の XML は、@no__t 0maml: inputTypes > ノードを使用して入力の種類を文書化する例を示しています。

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  http://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> You can pipe a date to the Set-Date cmdlet. <maml:para>
    <maml:description>
  </command:inputType>
</command:inputTypes>
```