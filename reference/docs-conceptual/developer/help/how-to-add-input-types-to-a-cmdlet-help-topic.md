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
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a><span data-ttu-id="d1312-102">コマンドレットのヘルプ トピックに入力の種類を追加する方法</span><span class="sxs-lookup"><span data-stu-id="d1312-102">How to Add Input Types to a Cmdlet Help Topic</span></span>

<span data-ttu-id="d1312-103">このセクションでは、Windows PowerShell®コマンドレットのヘルプトピックに入力セクションを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1312-103">This section describes how to add an INPUTS section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="d1312-104">[入力] セクションには、コマンドレットがパイプラインからの入力として受け取るオブジェクトの .NET クラスが、値またはプロパティ名のいずれかで一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1312-104">The INPUTS section lists the .NET classes of objects that the cmdlet accepts as input from the pipeline, either by value or by property name.</span></span>

<span data-ttu-id="d1312-105">入力セクションに追加できるクラスの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="d1312-105">There is no limit to the number of classes that you can add to an INPUTS section.</span></span> <span data-ttu-id="d1312-106">入力の型は \<コマンド: inputTypes > node で囲まれており、各クラスは \<コマンド: inputType > 要素で囲まれています。</span><span class="sxs-lookup"><span data-stu-id="d1312-106">The input types are enclosed in a \<command:inputTypes> node, with each class enclosed in a  \<command:inputType> element.</span></span>

<span data-ttu-id="d1312-107">スキーマには、各 \<コマンド: inputType > 要素の2つの \<maml: description > 要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d1312-107">The schema includes two \<maml:description> elements in each \<command:inputType> element.</span></span> <span data-ttu-id="d1312-108">ただし、`Get-Help` コマンドレットでは、\<コマンド: inputType >/\<maml: description >) 要素の内容のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1312-108">However, the `Get-Help` cmdlet displays only the content of the \<command:inputType>/\<maml:description>) element.</span></span>

<span data-ttu-id="d1312-109">Windows PowerShell 3.0 以降では、`Get-Help` コマンドレットは \<maml: uri > 要素の内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="d1312-109">Beginning in Windows PowerShell 3.0, the `Get-Help` cmdlet displays the content of the \<maml:uri> element.</span></span> <span data-ttu-id="d1312-110">この要素を使用すると、.NET クラスを説明するトピックにユーザーを誘導できます。</span><span class="sxs-lookup"><span data-stu-id="d1312-110">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="d1312-111">次の XML は、\<maml: inputTypes > ノードを示しています。</span><span class="sxs-lookup"><span data-stu-id="d1312-111">The following XML shows the \<maml:inputTypes> node.</span></span>

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

<span data-ttu-id="d1312-112">次の XML は、\<maml: inputTypes > ノードを使用して入力の種類を文書化する例を示しています。</span><span class="sxs-lookup"><span data-stu-id="d1312-112">The following XML shows an example of using the \<maml:inputTypes> node to document an input type.</span></span>

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