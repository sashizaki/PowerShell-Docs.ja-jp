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
ms.openlocfilehash: 5e8d1df6b423bfd2cd6b0a64a8875dea9c3fb4ef
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857318"
---
# <a name="how-to-add-examples-to-a-cmdlet-help-topic"></a><span data-ttu-id="f88fc-102">コマンドレットのヘルプ トピックに例を追加する方法</span><span class="sxs-lookup"><span data-stu-id="f88fc-102">How to Add Examples to a Cmdlet Help Topic</span></span>

- [<span data-ttu-id="f88fc-103">コマンドレットのヘルプの例について知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="f88fc-103">Things to Know about Examples in Cmdlet Help</span></span>](#Things-to-Know-about-Examples-in-Cmdlet-Help)

- [<span data-ttu-id="f88fc-104">例を表示するビューについてのヘルプ</span><span class="sxs-lookup"><span data-stu-id="f88fc-104">Help Views that Display Examples</span></span>](#Help-Views-that-Display-Examples)

- [<span data-ttu-id="f88fc-105">例として、ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-105">Adding an Examples Node</span></span>](#Adding-an-Examples-Node)

- [<span data-ttu-id="f88fc-106">文字の前の追加</span><span class="sxs-lookup"><span data-stu-id="f88fc-106">Adding Preceding Characters</span></span>](#Adding-Preceding-Characters)

- [<span data-ttu-id="f88fc-107">コマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-107">Adding the Command</span></span>](#Adding-the-Command)

- [<span data-ttu-id="f88fc-108">説明の追加</span><span class="sxs-lookup"><span data-stu-id="f88fc-108">Adding a Description</span></span>](#Adding-a-Description)

- [<span data-ttu-id="f88fc-109">出力例を追加します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-109">Adding Example Output</span></span>](#Adding-Example-Output)

## <a name="things-to-know-about-examples-in-cmdlet-help"></a><span data-ttu-id="f88fc-110">コマンドレットのヘルプの例について知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="f88fc-110">Things to Know about Examples in Cmdlet Help</span></span>

- <span data-ttu-id="f88fc-111">パラメーター名は省略可能な場合でも、すべてのコマンドでパラメーター名の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-111">List all of the parameter names in the command, even when the parameter names are optional.</span></span> <span data-ttu-id="f88fc-112">これにより、ユーザーがコマンドを簡単に解釈できます。</span><span class="sxs-lookup"><span data-stu-id="f88fc-112">This helps the user to interpret the command easily.</span></span>

- <span data-ttu-id="f88fc-113">Windows PowerShell® で作業する場合でも、エイリアスと部分的なパラメーターの名前をしないでください。</span><span class="sxs-lookup"><span data-stu-id="f88fc-113">Avoid aliases and partial parameter names, even though they work in Windows PowerShell®.</span></span>

- <span data-ttu-id="f88fc-114">例の説明で合理的なコマンドを構築するための手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-114">In the example description, explain the rational for the construction of the command.</span></span> <span data-ttu-id="f88fc-115">特定のパラメーターと値を選択した理由と、変数を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-115">Explain why you chose particular parameters and values, and how you use variables.</span></span>

- <span data-ttu-id="f88fc-116">コマンドは、式を使用している場合は、詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-116">If the command uses expressions, explain them in detail.</span></span>

- <span data-ttu-id="f88fc-117">コマンドは、既定の表示に表示されないプロパティ特に、オブジェクトのプロパティとメソッドを使用している場合は、営業案件に、オブジェクトについて、ユーザーに通知するよう、例を使用します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-117">If the command uses properties and methods of objects, especially properties that do not appear in the default display, use the example as an opportunity tell the user about the object.</span></span>

## <a name="help-views-that-display-examples"></a><span data-ttu-id="f88fc-118">例を表示するビューについてのヘルプ</span><span class="sxs-lookup"><span data-stu-id="f88fc-118">Help Views that Display Examples</span></span>

<span data-ttu-id="f88fc-119">例については、コマンドレットのヘルプの詳細と完全なビューでのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="f88fc-119">Examples appear only in the Detailed and Full views of cmdlet Help.</span></span>

## <a name="adding-an-examples-node"></a><span data-ttu-id="f88fc-120">例として、ノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-120">Adding an Examples Node</span></span>

<span data-ttu-id="f88fc-121">次の XML では、1 つのノードの例を含む例ノードを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-121">The following XML shows how to add an Examples node that contains a single Example node.</span></span> <span data-ttu-id="f88fc-122">各例については、トピックに追加するその他の例のノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-122">Add additional example nodes for each examples you want to include in the topic.</span></span>

```xml
<command:examples>
  <command:example>
  </command:example>
</command:examples>
```

## <a name="adding-an-example-title"></a><span data-ttu-id="f88fc-123">例のタイトルを追加します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-123">Adding an Example Title</span></span>

<span data-ttu-id="f88fc-124">次の XML では、例では、タイトルを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-124">The following XML shows how to add a title for the example.</span></span> <span data-ttu-id="f88fc-125">タイトルは、その他の例とは別の例の設定に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f88fc-125">The title is used to set the example apart from other examples.</span></span> <span data-ttu-id="f88fc-126">Windows PowerShell® では、逐次の例の番号を含む標準ヘッダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-126">Windows PowerShell® uses a standard header that includes a sequential example number.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
  </command:example>
</command:examples>
```

## <a name="adding-preceding-characters"></a><span data-ttu-id="f88fc-127">文字の前の追加</span><span class="sxs-lookup"><span data-stu-id="f88fc-127">Adding Preceding Characters</span></span>

<span data-ttu-id="f88fc-128">次の XML では、介在するスペース) を含めずコマンドの例の直前に表示される、Windows PowerShell プロンプトなどの文字を追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-128">The following XML shows how to add characters, such as the Windows PowerShell prompt, that are displayed immediately before the example command (without any intervening spaces).</span></span> <span data-ttu-id="f88fc-129">Windows PowerShell® では、Windows PowerShell プロンプトを使用します。C:\PS &GT;。</span><span class="sxs-lookup"><span data-stu-id="f88fc-129">Windows PowerShell® uses the Windows PowerShell prompt: C:\PS>.</span></span>

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

## <a name="adding-the-command"></a><span data-ttu-id="f88fc-130">コマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-130">Adding the Command</span></span>

<span data-ttu-id="f88fc-131">次の XML では、実際の例では、コマンドを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-131">The following XML shows how to add the actual command of the example.</span></span> <span data-ttu-id="f88fc-132">コマンドを追加する場合は、全体の名前を入力 (エイリアスは使用されません) のコマンドレットとパラメーター。</span><span class="sxs-lookup"><span data-stu-id="f88fc-132">When adding the command, type the entire name (do not use alias) of cmdlets and parameters.</span></span> <span data-ttu-id="f88fc-133">また、可能であれば小文字の文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-133">Also, use lowercase characters whenever possible.</span></span>

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

## <a name="adding-a-description"></a><span data-ttu-id="f88fc-134">説明の追加</span><span class="sxs-lookup"><span data-stu-id="f88fc-134">Adding a Description</span></span>

<span data-ttu-id="f88fc-135">次の XML では、この例の説明を追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-135">The following XML shows how to add a description for the example.</span></span> <span data-ttu-id="f88fc-136">Windows PowerShell® の 1 つのセットを使用して\<maml:para > 場合でも、説明のタグ複数\<maml:para > タグを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f88fc-136">Windows PowerShell® uses a single set of \<maml:para> tags for the description, even though multiple \<maml:para> tags can be used.</span></span>

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

## <a name="adding-example-output"></a><span data-ttu-id="f88fc-137">出力例を追加します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-137">Adding Example Output</span></span>

<span data-ttu-id="f88fc-138">次の XML では、コマンドの出力を追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-138">The following XML shows how to add the output of the command.</span></span> <span data-ttu-id="f88fc-139">コマンドの結果の情報は省略可能では、場合によっては、特定のパラメーターを使用しての効果を付けると便利です。</span><span class="sxs-lookup"><span data-stu-id="f88fc-139">The command results information is optional, but in some cases it is helpful to demonstrate the effect of using specific parameters.</span></span> <span data-ttu-id="f88fc-140">Windows PowerShell® が空白の 2 つのセットを使用して\<maml:para > タグからのコマンドは、コマンドの出力を分離します。</span><span class="sxs-lookup"><span data-stu-id="f88fc-140">Windows PowerShell® uses two sets of blank \<maml:para> tags to separate the command output from the command.</span></span>

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