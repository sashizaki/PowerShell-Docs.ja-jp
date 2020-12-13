---
ms.date: 09/12/2016
ms.topic: reference
title: コマンドレットのヘルプ トピックに入力の種類を追加する方法
description: コマンドレットのヘルプ トピックに入力の種類を追加する方法
ms.openlocfilehash: f2ad87c54230bcdd7e0ea708e9a1869daef7495f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "94391104"
---
# <a name="how-to-add-input-types-to-a-cmdlet-help-topic"></a><span data-ttu-id="1d20b-103">コマンドレットのヘルプ トピックに入力の種類を追加する方法</span><span class="sxs-lookup"><span data-stu-id="1d20b-103">How to Add Input Types to a Cmdlet Help Topic</span></span>

<span data-ttu-id="1d20b-104">ここでは、PowerShell コマンドレットのヘルプトピックに **入力** セクションを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1d20b-104">This section describes how to add an **INPUTS** section to a PowerShell cmdlet Help topic.</span></span> <span data-ttu-id="1d20b-105">[ **入力** ] セクションには、コマンドレットがパイプラインからの入力として受け取るオブジェクトの .net クラスが、値またはプロパティ名のいずれかで一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="1d20b-105">The **INPUTS** section lists the .NET classes of objects that the cmdlet accepts as input from the pipeline, either by value or by property name.</span></span>

<span data-ttu-id="1d20b-106">**入力** セクションに追加できるクラスの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="1d20b-106">There is no limit to the number of classes that you can add to an **INPUTS** section.</span></span> <span data-ttu-id="1d20b-107">入力型はノードで囲まれ `<command:inputTypes>` 、各クラスは要素で囲まれて `<command:inputType>` います。</span><span class="sxs-lookup"><span data-stu-id="1d20b-107">The input types are enclosed in a `<command:inputTypes>` node, with each class enclosed in a `<command:inputType>` element.</span></span>

<span data-ttu-id="1d20b-108">スキーマには、各要素に2つの要素が含まれてい `<maml:description>` `<command:inputType>` ます。</span><span class="sxs-lookup"><span data-stu-id="1d20b-108">The schema includes two `<maml:description>` elements in each `<command:inputType>` element.</span></span>
<span data-ttu-id="1d20b-109">ただし、この `Get-Help` コマンドレットは要素の内容のみを表示し `<command:inputType>/<maml:description>` ます。</span><span class="sxs-lookup"><span data-stu-id="1d20b-109">However, the `Get-Help` cmdlet displays only the content of the `<command:inputType>/<maml:description>` element.</span></span>

<span data-ttu-id="1d20b-110">PowerShell 3.0 以降では、 `Get-Help` コマンドレットによって要素の内容が表示され `<maml:uri>` ます。</span><span class="sxs-lookup"><span data-stu-id="1d20b-110">Beginning in PowerShell 3.0, the `Get-Help` cmdlet displays the content of the `<maml:uri>` element.</span></span>
<span data-ttu-id="1d20b-111">この要素を使用すると、.NET クラスを説明するトピックにユーザーを誘導できます。</span><span class="sxs-lookup"><span data-stu-id="1d20b-111">This element lets you direct users to topics that describe the .NET class.</span></span>

<span data-ttu-id="1d20b-112">次の XML は、ノードを示して `<maml:inputTypes>` います。</span><span class="sxs-lookup"><span data-stu-id="1d20b-112">The following XML shows the `<maml:inputTypes>` node.</span></span>

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

<span data-ttu-id="1d20b-113">次の XML は、ノードを使用して入力の種類をドキュメント化する例を示して `<maml:inputTypes>` います。</span><span class="sxs-lookup"><span data-stu-id="1d20b-113">The following XML shows an example of using the `<maml:inputTypes>` node to document an input type.</span></span>

```xml
<command:inputTypes>
  <command:inputType>
    <dev:type>
      <maml:name>System.DateTime</maml:name>
      <maml:uri>https://docs.microsoft.com/dotnet/api/system.datetime</maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> You can pipe a date to the Set-Date cmdlet. <maml:para>
    <maml:description>
  </command:inputType>
</command:inputTypes>
```
