---
title: コマンドレットのヘルプファイルを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a88dd89-6beb-494f-9e2a-6b10baed1a8d
caps.latest.revision: 17
ms.openlocfilehash: 08e05939f8aee42f2cd502a3da7a528d8460dec1
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361201"
---
# <a name="how-to-create-the-cmdlet-help-file"></a><span data-ttu-id="28a3f-102">コマンドレットのヘルプ ファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="28a3f-102">How to Create the Cmdlet Help File</span></span>

<span data-ttu-id="28a3f-103">このセクションでは、Windows PowerShell コマンドレットのヘルプトピックを含む有効な XML ファイルを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="28a3f-103">This section describes how to create a valid XML file that contains content for Windows PowerShell cmdlet Help topics.</span></span> <span data-ttu-id="28a3f-104">このセクションでは、ヘルプファイルに名前を付ける方法、適切な XML ヘッダーを追加する方法、コマンドレットのヘルプコンテンツのさまざまなセクションを含むノードを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="28a3f-104">This section discusses how to name the Help file, how to add the appropriate XML headers, and how to add nodes that will contain the different sections of the cmdlet Help content.</span></span>

> [!NOTE]
> <span data-ttu-id="28a3f-105">ヘルプファイルの完全なビューを表示するには、Windows PowerShell のインストールディレクトリにあるいずれかの dll-Help ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="28a3f-105">For a complete view of a Help file, open one of the dll-Help.xml files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="28a3f-106">たとえば、dll-Help ファイルには、いくつかの Windows PowerShell コマンドレットのコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="28a3f-106">For example, the Microsoft.PowerShell.Commands.Management.dll-Help.xml file contains content for several of the Windows PowerShell cmdlets.</span></span>

### <a name="how-to-create-a-cmdlet-help-file"></a><span data-ttu-id="28a3f-107">コマンドレットのヘルプファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="28a3f-107">How to Create a Cmdlet Help File</span></span>

1. <span data-ttu-id="28a3f-108">テキストファイルを作成し、UTF8 エンコーディングを使用して保存します。</span><span class="sxs-lookup"><span data-stu-id="28a3f-108">Create a text file and save it using UTF8 encoding.</span></span> <span data-ttu-id="28a3f-109">Windows PowerShell でコマンドレットヘルプファイルとして検出できるように、ファイル名は次の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="28a3f-109">The file name must have the following format so that Windows PowerShell can detect it as a cmdlet Help file.</span></span>

   `<PSSnapInAssemblyName>.dll-Help.xml`

2. <span data-ttu-id="28a3f-110">次の XML ヘッダーをテキストファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="28a3f-110">Add the following XML headers to the text file.</span></span> <span data-ttu-id="28a3f-111">ファイルは、マルチエージェントモデリング言語 (MAML) スキーマに対して検証されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="28a3f-111">Be aware that the file will be validated against the Multi-Agent Modeling Language (MAML) schema.</span></span> <span data-ttu-id="28a3f-112">現在、Windows PowerShell には、ファイルを検証するためのツールは用意されていません。</span><span class="sxs-lookup"><span data-stu-id="28a3f-112">Currently, Windows PowerShell does not provide any tools to validate the file.</span></span>

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

3. <span data-ttu-id="28a3f-113">コマンドノードを、アセンブリ内の各コマンドレットのコマンドレットヘルプファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="28a3f-113">Add a Command node to the cmdlet Help file for each cmdlet in the assembly.</span></span> <span data-ttu-id="28a3f-114">コマンドノード内の各ノードは、コマンドレットのヘルプトピックのさまざまなセクションに関連しています。</span><span class="sxs-lookup"><span data-stu-id="28a3f-114">Each node within the Command node relates to the different sections of the cmdlet Help topic.</span></span>

   <span data-ttu-id="28a3f-115">次の表に、各ノードの XML 要素と各ノードの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="28a3f-115">The following table lists the XML element for each node, followed by a descriptions of each node.</span></span>

   |<span data-ttu-id="28a3f-116">ノード</span><span class="sxs-lookup"><span data-stu-id="28a3f-116">Node</span></span>|<span data-ttu-id="28a3f-117">[説明]</span><span class="sxs-lookup"><span data-stu-id="28a3f-117">Description</span></span>|
   |----------|-----------------|
   |`<details>`|<span data-ttu-id="28a3f-118">コマンドレットのヘルプトピックの [名前] セクションと [概要] セクションの内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="28a3f-118">Adds content for the NAME and SYNOPSIS sections of the cmdlet Help topic.</span></span> <span data-ttu-id="28a3f-119">詳細については、「[コマンドレット名と概要の追加方法](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28a3f-119">For more information, see [How to Add the Cmdlet Name and Synopsis](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md).</span></span>|
   |`<maml:description>`|<span data-ttu-id="28a3f-120">コマンドレットのヘルプトピックの [説明] セクションの内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="28a3f-120">Adds content for the DESCRIPTION section of the cmdlet Help topic.</span></span> <span data-ttu-id="28a3f-121">詳細については、[コマンドレットのヘルプトピックの「詳細な説明を追加する方法](./how-to-add-a-cmdlet-description.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28a3f-121">For more information, see [How to Add the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span>|
   |`<command:syntax>`|<span data-ttu-id="28a3f-122">コマンドレットのヘルプトピックの「構文」セクションの内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="28a3f-122">Adds content for the SYNTAX section of the cmdlet Help topic.</span></span> <span data-ttu-id="28a3f-123">詳細については、[コマンドレットヘルプトピックの「構文を追加する方法](./how-to-add-syntax-to-a-cmdlet-help-topic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28a3f-123">For more information, see [How to Add Syntax to a Cmdlet Help Topic](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span></span>|
   |`<command:parameters>`|<span data-ttu-id="28a3f-124">コマンドレットのヘルプトピックの PARAMETERS セクションにコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="28a3f-124">Adds content for the PARAMETERS section of the cmdlet Help topic.</span></span> <span data-ttu-id="28a3f-125">詳細については、「[コマンドレットにパラメーターを追加する方法](./how-to-add-parameter-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28a3f-125">For more information, see [How to Add Parameters to a Cmdlet Help Topic](./how-to-add-parameter-information.md).</span></span>|
   |`<command:inputTypes>`|<span data-ttu-id="28a3f-126">コマンドレットのヘルプトピックの入力セクションの内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="28a3f-126">Adds content for the INPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="28a3f-127">詳細については、[コマンドレットヘルプトピックの「入力の種類を追加する方法](./how-to-add-input-types-to-a-cmdlet-help-topic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28a3f-127">For more information, see [How to Add Input Types to a Cmdlet Help Topic](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span></span>|
   |`<command:returnValues>`|<span data-ttu-id="28a3f-128">コマンドレットヘルプトピックの出力セクションの内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="28a3f-128">Adds content for the OUTPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="28a3f-129">詳細については、[コマンドレットヘルプトピックの「戻り値を追加する方法](./how-to-add-return-values-to-a-cmdlet-help-topic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28a3f-129">For more information, see [How to Add Return Values to a Cmdlet Help Topic](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span></span>|
   |`<maml:alertset>`|<span data-ttu-id="28a3f-130">コマンドレットのヘルプトピックのメモセクションにコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="28a3f-130">Adds content to the NOTES section of the cmdlet Help topic.</span></span> <span data-ttu-id="28a3f-131">詳細については、「[コマンドレットにメモを追加する方法](./how-to-add-notes-to-a-cmdlet-help-topic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28a3f-131">For more information, see [How to add Notes to a Cmdlet Help Topic](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span></span>|
   |`<command:examples>`|<span data-ttu-id="28a3f-132">コマンドレットのヘルプトピックの「例」セクションの内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="28a3f-132">Adds content for the EXAMPLES section of the cmdlet Help topic.</span></span> <span data-ttu-id="28a3f-133">詳細については、「 [How To Add 例をコマンドレットヘルプトピックに追加する方法](./how-to-add-examples-to-a-cmdlet-help-topic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28a3f-133">For more information, see [How to Add Examples to a Cmdlet Help Topic](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span></span>|
   |`<maml:relatedLinks>`|<span data-ttu-id="28a3f-134">コマンドレットヘルプトピックの「関連リンク」セクションの内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="28a3f-134">Adds content for the RELATED LINKS section of the cmdlet Help topic.</span></span> <span data-ttu-id="28a3f-135">詳細については、[コマンドレットヘルプトピックの「関連リンクを追加する方法](./how-to-add-related-links-to-a-cmdlet-help-topic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="28a3f-135">For more information, see [How to Add Related Links to a Cmdlet Help Topic](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span></span>|

## <a name="example"></a><span data-ttu-id="28a3f-136">例</span><span class="sxs-lookup"><span data-stu-id="28a3f-136">Example</span></span>

 <span data-ttu-id="28a3f-137">コマンドレットのヘルプトピックのさまざまなセクションのノードを含むコマンドノードの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="28a3f-137">Here is an example of a Command node that includes the nodes for the various sections of the cmdlet Help topic.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="28a3f-138">参照</span><span class="sxs-lookup"><span data-stu-id="28a3f-138">See Also</span></span>

 [<span data-ttu-id="28a3f-139">コマンドレット名と概要を追加する方法</span><span class="sxs-lookup"><span data-stu-id="28a3f-139">How to Add the Cmdlet Name and Synopsis</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="28a3f-140">詳細な説明をコマンドレットヘルプトピックに追加する方法</span><span class="sxs-lookup"><span data-stu-id="28a3f-140">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="28a3f-141">コマンドレットヘルプトピックに構文を追加する方法</span><span class="sxs-lookup"><span data-stu-id="28a3f-141">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="28a3f-142">コマンドレットにパラメーターを追加する方法に関するヘルプトピック</span><span class="sxs-lookup"><span data-stu-id="28a3f-142">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="28a3f-143">コマンドレットのヘルプトピックに入力の種類を追加する方法</span><span class="sxs-lookup"><span data-stu-id="28a3f-143">How to Add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="28a3f-144">コマンドレットヘルプトピックに戻り値を追加する方法</span><span class="sxs-lookup"><span data-stu-id="28a3f-144">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="28a3f-145">コマンドレットヘルプトピックにメモを追加する方法</span><span class="sxs-lookup"><span data-stu-id="28a3f-145">How to add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="28a3f-146">コマンドレットのヘルプトピックに例を追加する方法</span><span class="sxs-lookup"><span data-stu-id="28a3f-146">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="28a3f-147">コマンドレットヘルプトピックに関連リンクを追加する方法</span><span class="sxs-lookup"><span data-stu-id="28a3f-147">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="28a3f-148">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="28a3f-148">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)