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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860808"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a><span data-ttu-id="71b59-102">コマンドレットのヘルプ トピックに入力の種類を追加する方法</span><span class="sxs-lookup"><span data-stu-id="71b59-102">How to Add Input Types to a Cmdlet Help Topic</span></span>

<span data-ttu-id="71b59-103">このセクションでは、Windows PowerShell® コマンドレットのヘルプ トピックへの入力セクションを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="71b59-103">This section describes how to add an INPUTS section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="71b59-104">入力のセクションでは、コマンドレットは、値またはプロパティ名のいずれか、パイプラインからの入力として受け取るオブジェクトの .NET クラスが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="71b59-104">The INPUTS section lists the .NET classes of objects that the cmdlet accepts as input from the pipeline, either by value or by property name.</span></span>

<span data-ttu-id="71b59-105">クラスの入力 セクションに追加できる数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="71b59-105">There is no limit to the number of classes that you can add to an INPUTS section.</span></span> <span data-ttu-id="71b59-106">入力の型がで囲まれた、\<コマンド: inputTypes > で囲まれた各クラスを使用して、ノード、\<コマンド: inputType > 要素。</span><span class="sxs-lookup"><span data-stu-id="71b59-106">The input types are enclosed in a \<command:inputTypes> node, with each class enclosed in a  \<command:inputType> element.</span></span>

<span data-ttu-id="71b59-107">2 つには、スキーマ\<maml:description > の各要素\<コマンド: inputType > 要素。</span><span class="sxs-lookup"><span data-stu-id="71b59-107">The schema includes two \<maml:description> elements in each \<command:inputType> element.</span></span> <span data-ttu-id="71b59-108">ただし、`Get-Help`コマンドレットのコンテンツのみを表示する、\<コマンド: inputType >/\<maml:description >) 要素。</span><span class="sxs-lookup"><span data-stu-id="71b59-108">However, the `Get-Help` cmdlet displays only the content of the \<command:inputType>/\<maml:description>) element.</span></span>

<span data-ttu-id="71b59-109">Windows PowerShell 3.0 以降では、`Get-Help`コマンドレットのコンテンツを表示する、 \<maml:uri > 要素。</span><span class="sxs-lookup"><span data-stu-id="71b59-109">Beginning in Windows PowerShell 3.0, the `Get-Help` cmdlet displays the content of the \<maml:uri> element.</span></span> <span data-ttu-id="71b59-110">この要素では、.NET クラスを説明するトピックへのユーザーに指示できます。</span><span class="sxs-lookup"><span data-stu-id="71b59-110">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="71b59-111">次の XML に示す、 \<maml:inputTypes > ノード。</span><span class="sxs-lookup"><span data-stu-id="71b59-111">The following XML shows the \<maml:inputTypes> node.</span></span>

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

<span data-ttu-id="71b59-112">次の XML を使用する例を示しています、 \<maml:inputTypes > ノードをドキュメントの入力の種類。</span><span class="sxs-lookup"><span data-stu-id="71b59-112">The following XML shows an example of using the \<maml:inputTypes> node to document an input type.</span></span>

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