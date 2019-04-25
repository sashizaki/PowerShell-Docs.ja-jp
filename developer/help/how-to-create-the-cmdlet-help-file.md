---
title: コマンドレットのヘルプ ファイルを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a88dd89-6beb-494f-9e2a-6b10baed1a8d
caps.latest.revision: 17
ms.openlocfilehash: 08e05939f8aee42f2cd502a3da7a528d8460dec1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083248"
---
# <a name="how-to-create-the-cmdlet-help-file"></a><span data-ttu-id="7beb3-102">コマンドレットのヘルプ ファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="7beb3-102">How to Create the Cmdlet Help File</span></span>

<span data-ttu-id="7beb3-103">このセクションでは、Windows PowerShell コマンドレットのヘルプ トピックのコンテンツを含む有効な XML ファイルを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-103">This section describes how to create a valid XML file that contains content for Windows PowerShell cmdlet Help topics.</span></span> <span data-ttu-id="7beb3-104">このセクションでは、ヘルプ ファイルの名前を付ける方法や、適切な XML ヘッダーを追加する方法、コマンドレットのヘルプ コンテンツのさまざまなセクションを含むノードを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-104">This section discusses how to name the Help file, how to add the appropriate XML headers, and how to add nodes that will contain the different sections of the cmdlet Help content.</span></span>

> [!NOTE]
> <span data-ttu-id="7beb3-105">ヘルプ ファイル、開いている Windows PowerShell のインストール ディレクトリにある dll Help.xml ファイルの 1 つの完全なビュー。</span><span class="sxs-lookup"><span data-stu-id="7beb3-105">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="7beb3-106">たとえば、Microsoft.PowerShell.Commands.Management.dll Help.xml ファイルには、Windows PowerShell コマンドレットのいくつかのコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7beb3-106">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="how-to-create-a-cmdlet-help-file"></a><span data-ttu-id="7beb3-107">コマンドレットのヘルプ ファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="7beb3-107">How to Create a Cmdlet Help File</span></span>

1. <span data-ttu-id="7beb3-108">テキスト ファイルを作成し、UTF8 エンコーディングを使用して保存します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-108">Create a text file and save it using UTF8 encoding.</span></span> <span data-ttu-id="7beb3-109">ファイル名は、Windows PowerShell を使用すると、コマンドレットのヘルプ ファイルとして検出できるように、次の形式にすることが必要です。</span><span class="sxs-lookup"><span data-stu-id="7beb3-109">The file name must have the following format so that Windows PowerShell can detect it as a cmdlet Help file.</span></span>

   `<PSSnapInAssemblyName>.dll-Help.xml`

2. <span data-ttu-id="7beb3-110">テキスト ファイルに次の XML ヘッダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-110">Add the following XML headers to the text file.</span></span> <span data-ttu-id="7beb3-111">ファイルが複数のエージェントのモデリング言語 (MAML) スキーマに対して検証されることに注意します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-111">Be aware that the file will be validated against the Multi-Agent Modeling Language (MAML) schema.</span></span> <span data-ttu-id="7beb3-112">現時点では、Windows PowerShell では、ファイルを検証する任意のツールは提供されません。</span><span class="sxs-lookup"><span data-stu-id="7beb3-112">Currently, Windows PowerShell does not provide any tools to validate the file.</span></span>

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

3. <span data-ttu-id="7beb3-113">コマンド ノードをアセンブリ内の各コマンドレットのヘルプ ファイルをコマンドレットに追加します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-113">Add a Command node to the cmdlet Help file for each cmdlet in the assembly.</span></span> <span data-ttu-id="7beb3-114">コマンド ノード内の各ノードは、コマンドレットのヘルプ トピックのさまざまなセクションに関連しています。</span><span class="sxs-lookup"><span data-stu-id="7beb3-114">Each node within the Command node relates to the different sections of the cmdlet Help topic.</span></span>

   <span data-ttu-id="7beb3-115">次の表では、各ノードの説明については、後に、各ノードの XML 要素を示します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-115">The following table lists the XML element for each node, followed by a descriptions of each node.</span></span>

   |<span data-ttu-id="7beb3-116">ノード</span><span class="sxs-lookup"><span data-stu-id="7beb3-116">Node</span></span>|<span data-ttu-id="7beb3-117">説明</span><span class="sxs-lookup"><span data-stu-id="7beb3-117">Description</span></span>|
   |----------|-----------------|
   |`<details>`|<span data-ttu-id="7beb3-118">コマンドレットのヘルプ トピックの名前と概要セクションのコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-118">Adds content for the NAME and SYNOPSIS sections of the cmdlet Help topic.</span></span> <span data-ttu-id="7beb3-119">詳細については、次を参照してください。[概要とコマンドレットの名前を追加する方法](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-119">For more information, see [How to Add the Cmdlet Name and Synopsis](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md).</span></span>|
   |`<maml:description>`|<span data-ttu-id="7beb3-120">コマンドレットのヘルプ トピックの説明 セクションのコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-120">Adds content for the DESCRIPTION section of the cmdlet Help topic.</span></span> <span data-ttu-id="7beb3-121">詳細については、次を参照してください。[コマンドレットのヘルプ トピックを詳細な説明を追加する方法](./how-to-add-a-cmdlet-description.md)します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-121">For more information, see [How to Add the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span>|
   |`<command:syntax>`|<span data-ttu-id="7beb3-122">コマンドレットのヘルプ トピックの「構文」セクションのコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-122">Adds content for the SYNTAX section of the cmdlet Help topic.</span></span> <span data-ttu-id="7beb3-123">詳細については、次を参照してください。[構文コマンドレットのヘルプ トピックをに追加する方法](./how-to-add-syntax-to-a-cmdlet-help-topic.md)します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-123">For more information, see [How to Add Syntax to a Cmdlet Help Topic](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span></span>|
   |`<command:parameters>`|<span data-ttu-id="7beb3-124">コマンドレットのヘルプ トピックの PARAMETERS セクションのコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-124">Adds content for the PARAMETERS section of the cmdlet Help topic.</span></span> <span data-ttu-id="7beb3-125">詳細については、次を参照してください。[コマンドレットのヘルプ トピックにパラメーターを追加する方法](./how-to-add-parameter-information.md)します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-125">For more information, see [How to Add Parameters to a Cmdlet Help Topic](./how-to-add-parameter-information.md).</span></span>|
   |`<command:inputTypes>`|<span data-ttu-id="7beb3-126">コマンドレットのヘルプ トピックの入力のセクションのコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-126">Adds content for the INPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="7beb3-127">詳細については、次を参照してください。[コマンドレットのヘルプ トピックへの入力タイプの追加方法](./how-to-add-input-types-to-a-cmdlet-help-topic.md)します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-127">For more information, see [How to Add Input Types to a Cmdlet Help Topic](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span></span>|
   |`<command:returnValues>`|<span data-ttu-id="7beb3-128">コマンドレットのヘルプ トピックの出力セクションのコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-128">Adds content for the OUTPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="7beb3-129">詳細については、次を参照してください。[戻り値の追加コマンドレットのヘルプ トピックにする方法](./how-to-add-return-values-to-a-cmdlet-help-topic.md)します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-129">For more information, see [How to Add Return Values to a Cmdlet Help Topic](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span></span>|
   |`<maml:alertset>`|<span data-ttu-id="7beb3-130">コマンドレットのヘルプ トピックのノートのセクションには、コンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-130">Adds content to the NOTES section of the cmdlet Help topic.</span></span> <span data-ttu-id="7beb3-131">詳細については、次を参照してください。[を追加する方法は、コマンドレットのヘルプ トピックをノート](./how-to-add-notes-to-a-cmdlet-help-topic.md)します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-131">For more information, see [How to add Notes to a Cmdlet Help Topic](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span></span>|
   |`<command:examples>`|<span data-ttu-id="7beb3-132">コマンドレットのヘルプ トピックの例」のセクションのコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-132">Adds content for the EXAMPLES section of the cmdlet Help topic.</span></span> <span data-ttu-id="7beb3-133">詳細については、次を参照してください。[コマンドレットのヘルプ トピックに例を追加する方法](./how-to-add-examples-to-a-cmdlet-help-topic.md)します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-133">For more information, see [How to Add Examples to a Cmdlet Help Topic](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span></span>|
   |`<maml:relatedLinks>`|<span data-ttu-id="7beb3-134">コマンドレットのヘルプ トピックの「関連リンク」のコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-134">Adds content for the RELATED LINKS section of the cmdlet Help topic.</span></span> <span data-ttu-id="7beb3-135">詳細については、次を参照してください。[コマンドレットのヘルプ トピックへの関連リンクの追加方法](./how-to-add-related-links-to-a-cmdlet-help-topic.md)します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-135">For more information, see [How to Add Related Links to a Cmdlet Help Topic](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span></span>|

## <a name="example"></a><span data-ttu-id="7beb3-136">例</span><span class="sxs-lookup"><span data-stu-id="7beb3-136">Example</span></span>

 <span data-ttu-id="7beb3-137">次のコマンドレットのヘルプ トピックのさまざまなセクションでは、ノードを含むコマンド ノードの例に示します。</span><span class="sxs-lookup"><span data-stu-id="7beb3-137">Here is an example of a Command node that includes the nodes for the various sections of the cmdlet Help topic.</span></span>

```xml
<command:command
  xmlns:maml="http://schemas.microsoft.com/maml/2004/10"
  xmlns:command="http://schemas.microsoft.com/maml/dev/command/2004/10"
  xmlns:dev="http://schemas.microsoft.com/maml/dev/2004/10">
  <command:details>
    <!--Add name an synopsis here-->
  </command:details>
  <maml:description>
    <!--Add detailed description here-->
  </maml:description>
  <command:syntax>
    <!--Add syntax information here-->
  </command:syntax>
  <command:parameters>
    <!--Add parameter information here-->
  </command:parameters>
  <command:inputTypes>
    <!--Add input type information here-->
  </command:inputTypes>
  <command:returnValues>
    <!--Add return value information here-->
  </command:returnValues>
  <maml:alertSet>
    <!--Add Note information here-->
  </maml:alertSet>
  <command:examples>
    <!--Add cmdlet examples here-->
  </command:examples>
  <maml:relatedLinks>
    <!--Add links to related content here-->
  </maml:relatedLinks>
</command:command>
```

## <a name="see-also"></a><span data-ttu-id="7beb3-138">参照</span><span class="sxs-lookup"><span data-stu-id="7beb3-138">See Also</span></span>

 [<span data-ttu-id="7beb3-139">概要とコマンドレットの名前を追加する方法</span><span class="sxs-lookup"><span data-stu-id="7beb3-139">How to Add the Cmdlet Name and Synopsis</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="7beb3-140">コマンドレットのヘルプ トピックの詳細な説明を追加する方法</span><span class="sxs-lookup"><span data-stu-id="7beb3-140">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="7beb3-141">コマンドレットのヘルプ トピックに構文を追加する方法</span><span class="sxs-lookup"><span data-stu-id="7beb3-141">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="7beb3-142">コマンドレットのヘルプ トピックにパラメーターを追加する方法</span><span class="sxs-lookup"><span data-stu-id="7beb3-142">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="7beb3-143">コマンドレットのヘルプ トピックへの入力の種類を追加する方法</span><span class="sxs-lookup"><span data-stu-id="7beb3-143">How to Add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="7beb3-144">コマンドレットのヘルプ トピックに戻り値を追加する方法</span><span class="sxs-lookup"><span data-stu-id="7beb3-144">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="7beb3-145">追加する方法は、コマンドレットのヘルプ トピックをノートします。</span><span class="sxs-lookup"><span data-stu-id="7beb3-145">How to add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="7beb3-146">コマンドレットのヘルプ トピックの例を追加する方法</span><span class="sxs-lookup"><span data-stu-id="7beb3-146">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="7beb3-147">コマンドレットのヘルプ トピックに関連するリンクを追加する方法</span><span class="sxs-lookup"><span data-stu-id="7beb3-147">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="7beb3-148">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="7beb3-148">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)