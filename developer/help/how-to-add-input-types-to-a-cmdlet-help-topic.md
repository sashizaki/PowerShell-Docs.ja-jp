---
title: コマンドレットのヘルプ トピックへの入力の種類を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 432798e4-5d69-46b1-9517-ff09bffaa4be
caps.latest.revision: 7
ms.openlocfilehash: f213605dda0132051d983f8608515325e815c455
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083435"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに入力の種類を追加する方法

このセクションでは、Windows PowerShell® コマンドレットのヘルプ トピックへの入力セクションを追加する方法について説明します。 入力のセクションでは、コマンドレットは、値またはプロパティ名のいずれか、パイプラインからの入力として受け取るオブジェクトの .NET クラスが一覧表示します。

クラスの入力 セクションに追加できる数に制限はありません。 入力の型がで囲まれた、\<コマンド: inputTypes > で囲まれた各クラスを使用して、ノード、\<コマンド: inputType > 要素。

2 つには、スキーマ\<maml:description > の各要素\<コマンド: inputType > 要素。 ただし、`Get-Help`コマンドレットのコンテンツのみを表示する、\<コマンド: inputType >/\<maml:description >) 要素。

Windows PowerShell 3.0 以降では、`Get-Help`コマンドレットのコンテンツを表示する、 \<maml:uri > 要素。 この要素では、.NET クラスを説明するトピックへのユーザーに指示できます。

次の XML に示す、 \<maml:inputTypes > ノード。

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

次の XML を使用する例を示しています、 \<maml:inputTypes > ノードをドキュメントの入力の種類。

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