---
title: 例をコマンドレットに追加する方法に関するヘルプトピック |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f723b21-8f95-4981-8b6e-4f07c22d601a
caps.latest.revision: 5
ms.openlocfilehash: 82bee7b7bb0ef49203636f2a293075f3db924ce4
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557092"
---
# <a name="how-to-add-examples-to-a-cmdlet-help-topic"></a><span data-ttu-id="31bac-102">コマンドレットのヘルプ トピックに例を追加する方法</span><span class="sxs-lookup"><span data-stu-id="31bac-102">How to Add Examples to a Cmdlet Help Topic</span></span>

## <a name="things-to-know-about-examples-in-cmdlet-help"></a><span data-ttu-id="31bac-103">コマンドレットのヘルプの例について理解しておくべきこと</span><span class="sxs-lookup"><span data-stu-id="31bac-103">Things to Know about Examples in Cmdlet Help</span></span>

- <span data-ttu-id="31bac-104">パラメーター名が省略可能な場合でも、コマンド内のすべてのパラメーター名を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="31bac-104">List all of the parameter names in the command, even when the parameter names are optional.</span></span> <span data-ttu-id="31bac-105">これにより、ユーザーがコマンドを簡単に解釈できるようになります。</span><span class="sxs-lookup"><span data-stu-id="31bac-105">This helps the user to interpret the command easily.</span></span>

- <span data-ttu-id="31bac-106">Windows PowerShell®で動作する場合でも、エイリアスと部分的なパラメーター名は避けてください。</span><span class="sxs-lookup"><span data-stu-id="31bac-106">Avoid aliases and partial parameter names, even though they work in Windows PowerShell®.</span></span>

- <span data-ttu-id="31bac-107">この例では、コマンドの構築のための有理数について説明します。</span><span class="sxs-lookup"><span data-stu-id="31bac-107">In the example description, explain the rational for the construction of the command.</span></span> <span data-ttu-id="31bac-108">特定のパラメーターと値を選択した理由、および変数の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31bac-108">Explain why you chose particular parameters and values, and how you use variables.</span></span>

- <span data-ttu-id="31bac-109">コマンドで式を使用する場合は、詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="31bac-109">If the command uses expressions, explain them in detail.</span></span>

- <span data-ttu-id="31bac-110">コマンドでオブジェクトのプロパティとメソッド (特に既定の表示に表示されないプロパティ) を使用する場合は、オブジェクトについてユーザーに通知する機会として例を使用します。</span><span class="sxs-lookup"><span data-stu-id="31bac-110">If the command uses properties and methods of objects, especially properties that do not appear in the default display, use the example as an opportunity tell the user about the object.</span></span>

## <a name="help-views-that-display-examples"></a><span data-ttu-id="31bac-111">例を表示するヘルプビュー</span><span class="sxs-lookup"><span data-stu-id="31bac-111">Help Views that Display Examples</span></span>

<span data-ttu-id="31bac-112">例は、コマンドレットのヘルプの詳細ビューと完全ビューでのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="31bac-112">Examples appear only in the Detailed and Full views of cmdlet Help.</span></span>

## <a name="adding-an-examples-node"></a><span data-ttu-id="31bac-113">例ノードの追加</span><span class="sxs-lookup"><span data-stu-id="31bac-113">Adding an Examples Node</span></span>

<span data-ttu-id="31bac-114">次の XML は、1つの例のノードを含む例ノードを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="31bac-114">The following XML shows how to add an Examples node that contains a single Example node.</span></span> <span data-ttu-id="31bac-115">トピックに含める例ごとに、その他の例のノードを追加します。</span><span class="sxs-lookup"><span data-stu-id="31bac-115">Add additional example nodes for each examples you want to include in the topic.</span></span>

```xml
<command:examples>
  <command:example>
  </command:example>
</command:examples>
```

## <a name="adding-an-example-title"></a><span data-ttu-id="31bac-116">例のタイトルの追加</span><span class="sxs-lookup"><span data-stu-id="31bac-116">Adding an Example Title</span></span>

<span data-ttu-id="31bac-117">次の XML は、この例のタイトルを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="31bac-117">The following XML shows how to add a title for the example.</span></span> <span data-ttu-id="31bac-118">タイトルは、例を他の例とは別に設定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="31bac-118">The title is used to set the example apart from other examples.</span></span> <span data-ttu-id="31bac-119">Windows PowerShell®では、連番のサンプル番号を含む標準ヘッダーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="31bac-119">Windows PowerShell® uses a standard header that includes a sequential example number.</span></span>

```xml
<command:examples>
  <command:example>
    <maml:title>----------  EXAMPLE 1  ----------</maml:title>
  </command:example>
</command:examples>
```

## <a name="adding-preceding-characters"></a><span data-ttu-id="31bac-120">追加 (前の文字を)</span><span class="sxs-lookup"><span data-stu-id="31bac-120">Adding Preceding Characters</span></span>

<span data-ttu-id="31bac-121">次の XML は、例のコマンドの直前に表示される、Windows PowerShell プロンプトなどの文字を追加する方法を示しています (スペースは不要です)。</span><span class="sxs-lookup"><span data-stu-id="31bac-121">The following XML shows how to add characters, such as the Windows PowerShell prompt, that are displayed immediately before the example command (without any intervening spaces).</span></span> <span data-ttu-id="31bac-122">Windows PowerShell®では、Windows PowerShell プロンプト: C:\ PS> が使用されます。</span><span class="sxs-lookup"><span data-stu-id="31bac-122">Windows PowerShell® uses the Windows PowerShell prompt: C:\PS>.</span></span>

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

## <a name="adding-the-command"></a><span data-ttu-id="31bac-123">コマンドの追加</span><span class="sxs-lookup"><span data-stu-id="31bac-123">Adding the Command</span></span>

<span data-ttu-id="31bac-124">次の XML は、例の実際のコマンドを追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="31bac-124">The following XML shows how to add the actual command of the example.</span></span> <span data-ttu-id="31bac-125">コマンドを追加するときに、コマンドレットとパラメーターの名前全体 (エイリアスを使用しない) を入力します。</span><span class="sxs-lookup"><span data-stu-id="31bac-125">When adding the command, type the entire name (do not use alias) of cmdlets and parameters.</span></span> <span data-ttu-id="31bac-126">また、可能な限り小文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="31bac-126">Also, use lowercase characters whenever possible.</span></span>

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

## <a name="adding-a-description"></a><span data-ttu-id="31bac-127">説明の追加</span><span class="sxs-lookup"><span data-stu-id="31bac-127">Adding a Description</span></span>

<span data-ttu-id="31bac-128">次の XML は、この例の説明を追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="31bac-128">The following XML shows how to add a description for the example.</span></span> <span data-ttu-id="31bac-129">Windows PowerShell®では、複数の \< \< maml: 段落> タグを使用することもできますが、説明のために maml: 段落> タグの1つのセットを使用します。</span><span class="sxs-lookup"><span data-stu-id="31bac-129">Windows PowerShell® uses a single set of \<maml:para> tags for the description, even though multiple \<maml:para> tags can be used.</span></span>

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

## <a name="adding-example-output"></a><span data-ttu-id="31bac-130">出力例の追加</span><span class="sxs-lookup"><span data-stu-id="31bac-130">Adding Example Output</span></span>

<span data-ttu-id="31bac-131">次の XML は、コマンドの出力を追加する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="31bac-131">The following XML shows how to add the output of the command.</span></span> <span data-ttu-id="31bac-132">コマンドの結果情報は省略可能ですが、場合によっては、特定のパラメーターを使用した場合の影響を示すのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="31bac-132">The command results information is optional, but in some cases it is helpful to demonstrate the effect of using specific parameters.</span></span> <span data-ttu-id="31bac-133">Windows PowerShell®では、コマンドの \< 出力をコマンドから分離するために、2つの空白の maml: 段落> タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="31bac-133">Windows PowerShell® uses two sets of blank \<maml:para> tags to separate the command output from the command.</span></span>

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
