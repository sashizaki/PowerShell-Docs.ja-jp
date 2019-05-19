---
title: コマンドレットのヘルプ トピックの例を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f723b21-8f95-4981-8b6e-4f07c22d601a
caps.latest.revision: 5
ms.openlocfilehash: b6f8aef76a5f4b5dc1a60425541856ead9a9c77a
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855127"
---
# <a name="how-to-add-examples-to-a-cmdlet-help-topic"></a><span data-ttu-id="4373d-102">コマンドレットのヘルプ トピックに例を追加する方法</span><span class="sxs-lookup"><span data-stu-id="4373d-102">How to Add Examples to a Cmdlet Help Topic</span></span>

## <a name="things-to-know-about-examples-in-cmdlet-help"></a><span data-ttu-id="4373d-103">コマンドレットのヘルプの例について知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="4373d-103">Things to Know about Examples in Cmdlet Help</span></span>

- <span data-ttu-id="4373d-104">パラメーター名は省略可能な場合でも、すべてのコマンドでパラメーター名の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="4373d-104">List all of the parameter names in the command, even when the parameter names are optional.</span></span> <span data-ttu-id="4373d-105">これにより、ユーザーがコマンドを簡単に解釈できます。</span><span class="sxs-lookup"><span data-stu-id="4373d-105">This helps the user to interpret the command easily.</span></span>

- <span data-ttu-id="4373d-106">Windows PowerShell® で作業する場合でも、エイリアスと部分的なパラメーターの名前をしないでください。</span><span class="sxs-lookup"><span data-stu-id="4373d-106">Avoid aliases and partial parameter names, even though they work in Windows PowerShell®.</span></span>

- <span data-ttu-id="4373d-107">例の説明で合理的なコマンドを構築するための手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="4373d-107">In the example description, explain the rational for the construction of the command.</span></span> <span data-ttu-id="4373d-108">特定のパラメーターと値を選択した理由と、変数を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4373d-108">Explain why you chose particular parameters and values, and how you use variables.</span></span>

- <span data-ttu-id="4373d-109">コマンドは、式を使用している場合は、詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="4373d-109">If the command uses expressions, explain them in detail.</span></span>

- <span data-ttu-id="4373d-110">コマンドは、既定の表示に表示されないプロパティ特に、オブジェクトのプロパティとメソッドを使用している場合は、営業案件に、オブジェクトについて、ユーザーに通知するよう、例を使用します。</span><span class="sxs-lookup"><span data-stu-id="4373d-110">If the command uses properties and methods of objects, especially properties that do not appear in the default display, use the example as an opportunity tell the user about the object.</span></span>

## <a name="help-views-that-display-examples"></a><span data-ttu-id="4373d-111">例を表示するビューについてのヘルプ</span><span class="sxs-lookup"><span data-stu-id="4373d-111">Help Views that Display Examples</span></span>

<span data-ttu-id="4373d-112">例については、コマンドレットのヘルプの詳細と完全なビューでのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="4373d-112">Examples appear only in the Detailed and Full views of cmdlet Help.</span></span>

## <a name="adding-an-examples-node"></a><span data-ttu-id="4373d-113">例として、ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4373d-113">Adding an Examples Node</span></span>

<span data-ttu-id="4373d-114">次の XML では、1 つのノードの例を含む例ノードを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4373d-114">The following XML shows how to add an Examples node that contains a single Example node.</span></span> <span data-ttu-id="4373d-115">各例については、トピックに追加するその他の例のノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="4373d-115">Add additional example nodes for each examples you want to include in the topic.</span></span>

```xml
<command:examples>
  <command:example>
  </command:example>
</command:examples>
```

## <a name="adding-an-example-title"></a><span data-ttu-id="4373d-116">例のタイトルを追加します。</span><span class="sxs-lookup"><span data-stu-id="4373d-116">Adding an Example Title</span></span>

<span data-ttu-id="4373d-117">次の XML では、例では、タイトルを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4373d-117">The following XML shows how to add a title for the example.</span></span> <span data-ttu-id="4373d-118">タイトルは、その他の例とは別の例の設定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4373d-118">The title is used to set the example apart from other examples.</span></span> <span data-ttu-id="4373d-119">Windows PowerShell® では、逐次の例の番号を含む標準ヘッダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="4373d-119">Windows PowerShell® uses a standard header that includes a sequential example number.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
  </command:example>
</command:examples>
```

## <a name="adding-preceding-characters"></a><span data-ttu-id="4373d-120">文字の前の追加</span><span class="sxs-lookup"><span data-stu-id="4373d-120">Adding Preceding Characters</span></span>

<span data-ttu-id="4373d-121">次の XML では、介在するスペース) を含めずコマンドの例の直前に表示される、Windows PowerShell プロンプトなどの文字を追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4373d-121">The following XML shows how to add characters, such as the Windows PowerShell prompt, that are displayed immediately before the example command (without any intervening spaces).</span></span> <span data-ttu-id="4373d-122">Windows PowerShell® では、Windows PowerShell プロンプトを使用します。C:\PS &GT;。</span><span class="sxs-lookup"><span data-stu-id="4373d-122">Windows PowerShell® uses the Windows PowerShell prompt: C:\PS>.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
</command:example>
</command:examples>
```

## <a name="adding-the-command"></a><span data-ttu-id="4373d-123">コマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="4373d-123">Adding the Command</span></span>

<span data-ttu-id="4373d-124">次の XML では、実際の例では、コマンドを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4373d-124">The following XML shows how to add the actual command of the example.</span></span> <span data-ttu-id="4373d-125">コマンドを追加する場合は、全体の名前を入力 (エイリアスは使用されません) のコマンドレットとパラメーター。</span><span class="sxs-lookup"><span data-stu-id="4373d-125">When adding the command, type the entire name (do not use alias) of cmdlets and parameters.</span></span> <span data-ttu-id="4373d-126">また、可能であれば小文字の文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="4373d-126">Also, use lowercase characters whenever possible.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
</command:example>
</command:examples>
```

## <a name="adding-a-description"></a><span data-ttu-id="4373d-127">説明の追加</span><span class="sxs-lookup"><span data-stu-id="4373d-127">Adding a Description</span></span>

<span data-ttu-id="4373d-128">次の XML では、この例の説明を追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4373d-128">The following XML shows how to add a description for the example.</span></span> <span data-ttu-id="4373d-129">Windows PowerShell® の 1 つのセットを使用して\<maml:para > 場合でも、説明のタグ複数\<maml:para > タグを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4373d-129">Windows PowerShell® uses a single set of \<maml:para> tags for the description, even though multiple \<maml:para> tags can be used.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
    <dev:remarks>
      <maml:para> command description </maml:para>
    </dev:remarks>
</command:example>
</command:examples>
```

## <a name="adding-example-output"></a><span data-ttu-id="4373d-130">出力例を追加します。</span><span class="sxs-lookup"><span data-stu-id="4373d-130">Adding Example Output</span></span>

<span data-ttu-id="4373d-131">次の XML では、コマンドの出力を追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4373d-131">The following XML shows how to add the output of the command.</span></span> <span data-ttu-id="4373d-132">コマンドの結果の情報は省略可能では、場合によっては、特定のパラメーターを使用しての効果を付けると便利です。</span><span class="sxs-lookup"><span data-stu-id="4373d-132">The command results information is optional, but in some cases it is helpful to demonstrate the effect of using specific parameters.</span></span> <span data-ttu-id="4373d-133">Windows PowerShell® が空白の 2 つのセットを使用して\<maml:para > タグからのコマンドは、コマンドの出力を分離します。</span><span class="sxs-lookup"><span data-stu-id="4373d-133">Windows PowerShell® uses two sets of blank \<maml:para> tags to separate the command output from the command.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
    <maml:Introduction>
      <maml:paragraph>C:\PS></maml:paragraph>
    </maml:Introduction>
    <dev:code> command </dev:code>
    <dev:remarks>
      <maml:para> command description </maml:para>
      <maml:para></maml:para>
      <maml:para></maml:para>
      <maml:para> command output </maml:para>
</dev:remarks>
</command:example>
</command:examples>
```