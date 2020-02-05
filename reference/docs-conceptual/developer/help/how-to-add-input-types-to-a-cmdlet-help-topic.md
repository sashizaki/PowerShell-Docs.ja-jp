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
ms.openlocfilehash: 37af16d0279b6487c78f90eb19bcfe5c152ed9e7
ms.sourcegitcommit: bc9a4904c2b1561386d748fc9ac242699d2f1694
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "76996054"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに入力の種類を追加する方法

このセクションでは、Windows PowerShell®コマンドレットのヘルプトピックに入力セクションを追加する方法について説明します。 [入力] セクションには、コマンドレットがパイプラインからの入力として受け取るオブジェクトの .NET クラスが、値またはプロパティ名のいずれかで一覧表示されます。

入力セクションに追加できるクラスの数に制限はありません。 入力の型は \<コマンド: inputTypes > node で囲まれており、各クラスは \<コマンド: inputType > 要素で囲まれています。

スキーマには、各 \<コマンド: inputType > 要素の2つの \<maml: description > 要素が含まれています。 ただし、`Get-Help` コマンドレットでは、\<コマンド: inputType >/\<maml: description >) 要素の内容のみが表示されます。

Windows PowerShell 3.0 以降では、`Get-Help` コマンドレットは \<maml: uri > 要素の内容を表示します。 この要素を使用すると、.NET クラスを説明するトピックにユーザーを誘導できます。

次の XML は、\<maml: inputTypes > ノードを示しています。

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

次の XML は、\<maml: inputTypes > ノードを使用して入力の種類を文書化する例を示しています。

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> You can pipe a date to the Set-Date cmdlet. <maml:para>
    <maml:description>
  </command:inputType>
</command:inputTypes>
```