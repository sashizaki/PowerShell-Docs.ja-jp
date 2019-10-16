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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367801"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a><span data-ttu-id="ccd29-102">コマンドレットのヘルプ トピックに戻り値を追加する方法</span><span class="sxs-lookup"><span data-stu-id="ccd29-102">How to Add Return Values to a Cmdlet Help Topic</span></span>

<span data-ttu-id="ccd29-103">このセクションでは、Windows PowerShell®コマンドレットのヘルプトピックに OUTPUTS セクションを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ccd29-103">This section describes how to add an OUTPUTS section to a Windows PowerShell® cmdlet Help topic.</span></span> <span data-ttu-id="ccd29-104">OUTPUTS セクションには、コマンドレットが返す、またはパイプラインを渡すオブジェクトの .NET クラスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="ccd29-104">The OUTPUTS section lists the .NET classes of objects that the cmdlet returns or passes down the pipeline.</span></span>

<span data-ttu-id="ccd29-105">OUTPUTS セクションに追加できるクラスの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="ccd29-105">There is no limit to the number of classes that you can add to the OUTPUTS section.</span></span> <span data-ttu-id="ccd29-106">コマンドレットの戻り値の型は、@no__t 0command: returnValues > node に囲まれています。各クラスは \<command: 戻り値 > 要素で囲まれています。</span><span class="sxs-lookup"><span data-stu-id="ccd29-106">The return types of a cmdlet are enclosed in a \<command:returnValues> node, with each class enclosed in a \<command:returnValue> element.</span></span>

<span data-ttu-id="ccd29-107">コマンドレットで出力が生成されない場合は、出力がないことを示すためにこのセクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="ccd29-107">If a cmdlet does not generate any output, use this section to indicate that there is no output.</span></span> <span data-ttu-id="ccd29-108">たとえば、クラス名の代わりに "None" を記述し、簡単な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="ccd29-108">For example, in place of the class name, write "None" and provide a brief explanation.</span></span> <span data-ttu-id="ccd29-109">コマンドレットによって出力が条件付きで生成される場合は、このノードを使用して条件を説明し、条件付き出力を記述します。</span><span class="sxs-lookup"><span data-stu-id="ccd29-109">If the cmdlet generates output conditionally, use this node to explain the conditions and describe the conditional output.</span></span>

<span data-ttu-id="ccd29-110">スキーマには、各 \<command: 戻り > 要素の2つの @no__t 0maml: description > 要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ccd29-110">The schema includes two \<maml:description> elements in each \<command:returnValue> element.</span></span> <span data-ttu-id="ccd29-111">ただし、`Get-Help` コマンドレットは、\<command: 戻り >/\<maml: description > 要素の内容のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="ccd29-111">However, the `Get-Help` cmdlet displays only the content of the \<command:returnValue>/\<maml:description> element.</span></span>

<span data-ttu-id="ccd29-112">Windows PowerShell 3.0 以降では、`Get-Help` コマンドレットは、@no__t 1maml: uri > 要素の内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="ccd29-112">Beginning in Windows PowerShell 3.0, the `Get-Help` cmdlet displays the content of the \<maml:uri> element.</span></span> <span data-ttu-id="ccd29-113">この要素を使用すると、.NET クラスを説明するトピックにユーザーを誘導できます。</span><span class="sxs-lookup"><span data-stu-id="ccd29-113">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="ccd29-114">次の XML は、@no__t 0maml: returnValues > ノードを示しています。</span><span class="sxs-lookup"><span data-stu-id="ccd29-114">The following XML shows the \<maml:returnValues> node.</span></span>

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

<span data-ttu-id="ccd29-115">次の XML は、@no__t 0maml: returnValues > ノードを使用して、出力の種類を文書化する例を示しています。</span><span class="sxs-lookup"><span data-stu-id="ccd29-115">The following XML shows an example of using the \<maml:returnValues> node to document an output type.</span></span>

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



