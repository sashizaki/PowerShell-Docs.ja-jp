---
title: コマンドレットのヘルプ トピックに戻り値を追加する方法
ms.date: 09/12/2016
ms.openlocfilehash: c164556cd06b332d04857987360c98f740a150b5
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893358"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a><span data-ttu-id="71ff3-102">コマンドレットのヘルプ トピックに戻り値を追加する方法</span><span class="sxs-lookup"><span data-stu-id="71ff3-102">How to Add Return Values to a Cmdlet Help Topic</span></span>

<span data-ttu-id="71ff3-103">このセクションでは、出力セクションを PowerShell コマンドレットのヘルプトピックに追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="71ff3-103">This section describes how to add an OUTPUTS section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="71ff3-104">**OUTPUTS**セクションには、コマンドレットが返す、またはパイプラインを渡すオブジェクトの .net クラスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="71ff3-104">The **OUTPUTS** section lists the .NET classes of objects that the cmdlet returns or passes down the pipeline.</span></span>

<span data-ttu-id="71ff3-105">**OUTPUTS**セクションに追加できるクラスの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="71ff3-105">There is no limit to the number of classes that you can add to the **OUTPUTS** section.</span></span> <span data-ttu-id="71ff3-106">コマンドレットの戻り値の型はノードで囲み `<command:returnValues>` 、各クラスは要素で囲まれてい `<command:returnValue>` ます。</span><span class="sxs-lookup"><span data-stu-id="71ff3-106">The return types of a cmdlet are enclosed in a `<command:returnValues>` node, with each class enclosed in a `<command:returnValue>` element.</span></span>

<span data-ttu-id="71ff3-107">コマンドレットで出力が生成されない場合は、出力がないことを示すためにこのセクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="71ff3-107">If a cmdlet does not generate any output, use this section to indicate that there is no output.</span></span> <span data-ttu-id="71ff3-108">たとえば、クラス名の代わりに、 **「None** 」と記述し、簡単な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="71ff3-108">For example, in place of the class name, write **None** and provide a brief explanation.</span></span> <span data-ttu-id="71ff3-109">コマンドレットによって出力が条件付きで生成される場合は、このノードを使用して条件を説明し、条件付き出力を記述します。</span><span class="sxs-lookup"><span data-stu-id="71ff3-109">If the cmdlet generates output conditionally, use this node to explain the conditions and describe the conditional output.</span></span>

<span data-ttu-id="71ff3-110">スキーマには、各要素に2つの要素が含まれてい `<maml:description>` `<command:returnValue>` ます。</span><span class="sxs-lookup"><span data-stu-id="71ff3-110">The schema includes two `<maml:description>` elements in each `<command:returnValue>` element.</span></span>
<span data-ttu-id="71ff3-111">ただし、この `Get-Help` コマンドレットは要素の内容のみを表示し `<command:returnValue>/<maml:description>` ます。</span><span class="sxs-lookup"><span data-stu-id="71ff3-111">However, the `Get-Help` cmdlet displays only the content of the `<command:returnValue>/<maml:description>` element.</span></span>

<span data-ttu-id="71ff3-112">PowerShell 3.0 以降では、 `Get-Help` コマンドレットによって要素の内容が表示され `<maml:uri>` ます。</span><span class="sxs-lookup"><span data-stu-id="71ff3-112">Beginning in PowerShell 3.0, the `Get-Help` cmdlet displays the content of the `<maml:uri>` element.</span></span>
<span data-ttu-id="71ff3-113">この要素を使用すると、.NET クラスを説明するトピックにユーザーを誘導できます。</span><span class="sxs-lookup"><span data-stu-id="71ff3-113">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="71ff3-114">次の XML は、ノードを示して `<maml:returnValues>` います。</span><span class="sxs-lookup"><span data-stu-id="71ff3-114">The following XML shows the `<maml:returnValues>` node.</span></span>

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

<span data-ttu-id="71ff3-115">次の XML は、ノードを使用して出力の種類をドキュメント化する例を示して `<maml:returnValues>` います。</span><span class="sxs-lookup"><span data-stu-id="71ff3-115">The following XML shows an example of using the `<maml:returnValues>` node to document an output type.</span></span>

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Get-Date returns a DateTime object. <maml:para>
    </maml:description>
  </command: returnValue>
</command: returnValues>
```
