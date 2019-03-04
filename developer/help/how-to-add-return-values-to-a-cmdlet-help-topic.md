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
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a><span data-ttu-id="523b7-102">コマンドレットのヘルプ トピックに戻り値を追加する方法</span><span class="sxs-lookup"><span data-stu-id="523b7-102">How to Add Return Values to a Cmdlet Help Topic</span></span>

<span data-ttu-id="523b7-103">このセクションでは、OUTPUTS セクションを Windows PowerShell® コマンドレットのヘルプ トピックを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="523b7-103">This section describes how to add an OUTPUTS section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="523b7-104">OUTPUTS セクションでは、コマンドレットを返すか、パイプラインに渡すオブジェクトの .NET クラスが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="523b7-104">The OUTPUTS section lists the .NET classes of objects that the cmdlet returns or passes down the pipeline.</span></span>

<span data-ttu-id="523b7-105">クラス、OUTPUTS セクションに追加できる数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="523b7-105">There is no limit to the number of classes that you can add to the OUTPUTS section.</span></span> <span data-ttu-id="523b7-106">コマンドレットの戻り値の型がで囲まれた、\<コマンド: してください。 > で囲まれた各クラスを使用して、ノード、\<コマンド: returnValue > 要素。</span><span class="sxs-lookup"><span data-stu-id="523b7-106">The return types of a cmdlet are enclosed in a \<command:returnValues> node, with each class enclosed in a \<command:returnValue> element.</span></span>

<span data-ttu-id="523b7-107">コマンドレットが出力を生成しない場合は、このセクションを使用して、出力がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="523b7-107">If a cmdlet does not generate any output, use this section to indicate that there is no output.</span></span> <span data-ttu-id="523b7-108">たとえば、クラス名の代わりに"None"を記述し、簡単な説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="523b7-108">For example, in place of the class name, write "None" and provide a brief explanation.</span></span> <span data-ttu-id="523b7-109">コマンドレットでは、条件付きで出力を生成する場合は、条件を説明し、条件付きの出力を説明するこのノードを使用します。</span><span class="sxs-lookup"><span data-stu-id="523b7-109">If the cmdlet generates output conditionally, use this node to explain the conditions and describe the conditional output.</span></span>

<span data-ttu-id="523b7-110">2 つには、スキーマ\<maml:description > の各要素\<コマンド: returnValue > 要素。</span><span class="sxs-lookup"><span data-stu-id="523b7-110">The schema includes two \<maml:description> elements in each \<command:returnValue> element.</span></span> <span data-ttu-id="523b7-111">ただし、`Get-Help`コマンドレットのコンテンツのみを表示する、\<コマンド: returnValue >/\<maml:description > 要素。</span><span class="sxs-lookup"><span data-stu-id="523b7-111">However, the `Get-Help` cmdlet displays only the content of the \<command:returnValue>/\<maml:description> element.</span></span>

<span data-ttu-id="523b7-112">Windows PowerShell 3.0 以降では、`Get-Help`コマンドレットのコンテンツを表示する、 \<maml:uri > 要素。</span><span class="sxs-lookup"><span data-stu-id="523b7-112">Beginning in Windows PowerShell 3.0, the `Get-Help` cmdlet displays the content of the \<maml:uri> element.</span></span> <span data-ttu-id="523b7-113">この要素では、.NET クラスを説明するトピックへのユーザーに指示できます。</span><span class="sxs-lookup"><span data-stu-id="523b7-113">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="523b7-114">次の XML に示す、 \<maml:returnValues > ノード。</span><span class="sxs-lookup"><span data-stu-id="523b7-114">The following XML shows the \<maml:returnValues> node.</span></span>

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

<span data-ttu-id="523b7-115">次の XML を使用する例を示しています、 \<maml:returnValues > ノードをドキュメント出力の種類。</span><span class="sxs-lookup"><span data-stu-id="523b7-115">The following XML shows an example of using the \<maml:returnValues> node to document an output type.</span></span>

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



