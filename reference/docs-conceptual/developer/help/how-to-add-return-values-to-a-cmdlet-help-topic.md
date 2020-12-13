---
ms.date: 09/12/2016
ms.topic: reference
title: コマンドレットのヘルプ トピックに戻り値を追加する方法
description: コマンドレットのヘルプ トピックに戻り値を追加する方法
ms.openlocfilehash: 8c556821a257451a320916231cb20fc82e75ebb4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "94389744"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a><span data-ttu-id="fb3e8-103">コマンドレットのヘルプ トピックに戻り値を追加する方法</span><span class="sxs-lookup"><span data-stu-id="fb3e8-103">How to Add Return Values to a Cmdlet Help Topic</span></span>

<span data-ttu-id="fb3e8-104">このセクションでは、出力セクションを PowerShell コマンドレットのヘルプトピックに追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb3e8-104">This section describes how to add an OUTPUTS section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="fb3e8-105">**OUTPUTS** セクションには、コマンドレットが返す、またはパイプラインを渡すオブジェクトの .net クラスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb3e8-105">The **OUTPUTS** section lists the .NET classes of objects that the cmdlet returns or passes down the pipeline.</span></span>

<span data-ttu-id="fb3e8-106">**OUTPUTS** セクションに追加できるクラスの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="fb3e8-106">There is no limit to the number of classes that you can add to the **OUTPUTS** section.</span></span> <span data-ttu-id="fb3e8-107">コマンドレットの戻り値の型はノードで囲み `<command:returnValues>` 、各クラスは要素で囲まれてい `<command:returnValue>` ます。</span><span class="sxs-lookup"><span data-stu-id="fb3e8-107">The return types of a cmdlet are enclosed in a `<command:returnValues>` node, with each class enclosed in a `<command:returnValue>` element.</span></span>

<span data-ttu-id="fb3e8-108">コマンドレットで出力が生成されない場合は、出力がないことを示すためにこのセクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb3e8-108">If a cmdlet does not generate any output, use this section to indicate that there is no output.</span></span> <span data-ttu-id="fb3e8-109">たとえば、クラス名の代わりに、 **「None** 」と記述し、簡単な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="fb3e8-109">For example, in place of the class name, write **None** and provide a brief explanation.</span></span> <span data-ttu-id="fb3e8-110">コマンドレットによって出力が条件付きで生成される場合は、このノードを使用して条件を説明し、条件付き出力を記述します。</span><span class="sxs-lookup"><span data-stu-id="fb3e8-110">If the cmdlet generates output conditionally, use this node to explain the conditions and describe the conditional output.</span></span>

<span data-ttu-id="fb3e8-111">スキーマには、各要素に2つの要素が含まれてい `<maml:description>` `<command:returnValue>` ます。</span><span class="sxs-lookup"><span data-stu-id="fb3e8-111">The schema includes two `<maml:description>` elements in each `<command:returnValue>` element.</span></span>
<span data-ttu-id="fb3e8-112">ただし、この `Get-Help` コマンドレットは要素の内容のみを表示し `<command:returnValue>/<maml:description>` ます。</span><span class="sxs-lookup"><span data-stu-id="fb3e8-112">However, the `Get-Help` cmdlet displays only the content of the `<command:returnValue>/<maml:description>` element.</span></span>

<span data-ttu-id="fb3e8-113">PowerShell 3.0 以降では、 `Get-Help` コマンドレットによって要素の内容が表示され `<maml:uri>` ます。</span><span class="sxs-lookup"><span data-stu-id="fb3e8-113">Beginning in PowerShell 3.0, the `Get-Help` cmdlet displays the content of the `<maml:uri>` element.</span></span>
<span data-ttu-id="fb3e8-114">この要素を使用すると、.NET クラスを説明するトピックにユーザーを誘導できます。</span><span class="sxs-lookup"><span data-stu-id="fb3e8-114">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="fb3e8-115">次の XML は、ノードを示して `<maml:returnValues>` います。</span><span class="sxs-lookup"><span data-stu-id="fb3e8-115">The following XML shows the `<maml:returnValues>` node.</span></span>

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

<span data-ttu-id="fb3e8-116">次の XML は、ノードを使用して出力の種類をドキュメント化する例を示して `<maml:returnValues>` います。</span><span class="sxs-lookup"><span data-stu-id="fb3e8-116">The following XML shows an example of using the `<maml:returnValues>` node to document an output type.</span></span>

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://docs.microsoft.com/dotnet/api/system.datetime </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Get-Date returns a DateTime object. <maml:para>
    </maml:description>
  </command: returnValue>
</command: returnValues>
```
