---
ms.date: 09/13/2016
ms.topic: reference
title: コマンドレットのヘルプ ファイルを作成する方法
description: コマンドレットのヘルプ ファイルを作成する方法
ms.openlocfilehash: 40259c8f9496b10380805a78f3711aed6f1bf2e5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659089"
---
# <a name="how-to-create-the-cmdlet-help-file"></a><span data-ttu-id="cc54c-103">コマンドレットのヘルプ ファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="cc54c-103">How to Create the Cmdlet Help File</span></span>

<span data-ttu-id="cc54c-104">このセクションでは、Windows PowerShell コマンドレットのヘルプトピックを含む有効な XML ファイルを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-104">This section describes how to create a valid XML file that contains content for Windows PowerShell cmdlet Help topics.</span></span> <span data-ttu-id="cc54c-105">このセクションでは、ヘルプファイルに名前を付ける方法、適切な XML ヘッダーを追加する方法、コマンドレットのヘルプコンテンツのさまざまなセクションを含むノードを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-105">This section discusses how to name the Help file, how to add the appropriate XML headers, and how to add nodes that will contain the different sections of the cmdlet Help content.</span></span>

> [!NOTE]
> <span data-ttu-id="cc54c-106">ヘルプファイルの完全なビューを表示するには、 `dll-Help.xml` Windows PowerShell のインストールディレクトリにあるいずれかのファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="cc54c-106">For a complete view of a Help file, open one of the `dll-Help.xml` files located in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="cc54c-107">たとえば、ファイルには、 `Microsoft.PowerShell.Commands.Management.dll-Help.xml` いくつかの PowerShell コマンドレットのコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc54c-107">For example, the `Microsoft.PowerShell.Commands.Management.dll-Help.xml` file contains content for several of the PowerShell cmdlets.</span></span>

### <a name="how-to-create-a-cmdlet-help-file"></a><span data-ttu-id="cc54c-108">コマンドレットのヘルプファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="cc54c-108">How to Create a Cmdlet Help File</span></span>

1. <span data-ttu-id="cc54c-109">テキストファイルを作成し、UTF8 エンコーディングを使用して保存します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-109">Create a text file and save it using UTF8 encoding.</span></span> <span data-ttu-id="cc54c-110">ファイル名は、Windows PowerShell がコマンドレットヘルプファイルとして検出できるように、次の形式にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc54c-110">The filename must have the following format so that Windows PowerShell can detect it as a cmdlet Help file.</span></span>

   `<PSSnapInAssemblyName>.dll-Help.xml`

1. <span data-ttu-id="cc54c-111">次の XML ヘッダーをテキストファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-111">Add the following XML headers to the text file.</span></span> <span data-ttu-id="cc54c-112">ファイルは、Microsoft アシスタンスマークアップ言語 (MAML) スキーマに対して検証されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cc54c-112">Be aware that the file will be validated against the Microsoft Assistance Markup Language (MAML) schema.</span></span> <span data-ttu-id="cc54c-113">現在、PowerShell には、ファイルを検証するためのツールは用意されていません。</span><span class="sxs-lookup"><span data-stu-id="cc54c-113">Currently, PowerShell does not provide any tools to validate the file.</span></span>

   `<?xml version="1.0" encoding="utf-8" ?> <helpItems xmlns="http://msh" schema="maml">`

1. <span data-ttu-id="cc54c-114">**コマンド** ノードを、アセンブリ内の各コマンドレットのコマンドレットヘルプファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-114">Add a **Command** node to the cmdlet Help file for each cmdlet in the assembly.</span></span> <span data-ttu-id="cc54c-115">**コマンド** ノード内の各ノードは、コマンドレットのヘルプトピックのさまざまなセクションに関連しています。</span><span class="sxs-lookup"><span data-stu-id="cc54c-115">Each node within the **Command** node relates to the different sections of the cmdlet Help topic.</span></span>

   <span data-ttu-id="cc54c-116">次の表に、各ノードの XML 要素と各ノードの説明を示します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-116">The following table lists the XML element for each node, followed by a descriptions of each node.</span></span>

   |           <span data-ttu-id="cc54c-117">Node</span><span class="sxs-lookup"><span data-stu-id="cc54c-117">Node</span></span>           |                                                                                                     <span data-ttu-id="cc54c-118">説明</span><span class="sxs-lookup"><span data-stu-id="cc54c-118">Description</span></span>                                                                                                     |
   | ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
   | `<details>`              | <span data-ttu-id="cc54c-119">コマンドレットのヘルプトピックの [名前] セクションと [概要] セクションの内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-119">Adds content for the NAME and SYNOPSIS sections of the cmdlet Help topic.</span></span> <span data-ttu-id="cc54c-120">詳細については、「 [コマンドレット名と概要の追加方法](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc54c-120">For more information, see [How to Add the Cmdlet Name and Synopsis](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md).</span></span> |
   | `<maml:description>`     | <span data-ttu-id="cc54c-121">コマンドレットのヘルプトピックの [説明] セクションの内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-121">Adds content for the DESCRIPTION section of the cmdlet Help topic.</span></span> <span data-ttu-id="cc54c-122">詳細については、 [コマンドレットのヘルプトピックの「詳細な説明を追加する方法](./how-to-add-a-cmdlet-description.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc54c-122">For more information, see [How to Add the Detailed Description to a Cmdlet Help Topic](./how-to-add-a-cmdlet-description.md).</span></span>                    |
   | `<command:syntax>`       | <span data-ttu-id="cc54c-123">コマンドレットのヘルプトピックの「構文」セクションの内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-123">Adds content for the SYNTAX section of the cmdlet Help topic.</span></span> <span data-ttu-id="cc54c-124">詳細については、 [コマンドレットヘルプトピックの「構文を追加する方法](./how-to-add-syntax-to-a-cmdlet-help-topic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc54c-124">For more information, see [How to Add Syntax to a Cmdlet Help Topic](./how-to-add-syntax-to-a-cmdlet-help-topic.md).</span></span>                                  |
   | `<command:parameters>`   | <span data-ttu-id="cc54c-125">コマンドレットのヘルプトピックの PARAMETERS セクションにコンテンツを追加します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-125">Adds content for the PARAMETERS section of the cmdlet Help topic.</span></span> <span data-ttu-id="cc54c-126">詳細については、「 [コマンドレットにパラメーターを追加する方法](./how-to-add-parameter-information.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc54c-126">For more information, see [How to Add Parameters to a Cmdlet Help Topic](./how-to-add-parameter-information.md).</span></span>                                  |
   | `<command:inputTypes>`   | <span data-ttu-id="cc54c-127">コマンドレットのヘルプトピックの入力セクションの内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-127">Adds content for the INPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="cc54c-128">詳細については、 [コマンドレットヘルプトピックの「入力の種類を追加する方法](./how-to-add-input-types-to-a-cmdlet-help-topic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc54c-128">For more information, see [How to Add Input Types to a Cmdlet Help Topic](./how-to-add-input-types-to-a-cmdlet-help-topic.md).</span></span>                        |
   | `<command:returnValues>` | <span data-ttu-id="cc54c-129">コマンドレットヘルプトピックの出力セクションの内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-129">Adds content for the OUTPUTS section of the cmdlet Help topic.</span></span> <span data-ttu-id="cc54c-130">詳細については、 [コマンドレットヘルプトピックの「戻り値を追加する方法](./how-to-add-return-values-to-a-cmdlet-help-topic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc54c-130">For more information, see [How to Add Return Values to a Cmdlet Help Topic](./how-to-add-return-values-to-a-cmdlet-help-topic.md).</span></span>                   |
   | `<maml:alertset>`        | <span data-ttu-id="cc54c-131">コマンドレットのヘルプトピックのメモセクションの内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-131">Adds content for the NOTES section of the cmdlet Help topic.</span></span> <span data-ttu-id="cc54c-132">詳細については、「 [コマンドレットにメモを追加する方法](./how-to-add-notes-to-a-cmdlet-help-topic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc54c-132">For more information, see [How to add Notes to a Cmdlet Help Topic](./how-to-add-notes-to-a-cmdlet-help-topic.md).</span></span>                                      |
   | `<command:examples>`     | <span data-ttu-id="cc54c-133">コマンドレットのヘルプトピックの「例」セクションの内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-133">Adds content for the EXAMPLES section of the cmdlet Help topic.</span></span> <span data-ttu-id="cc54c-134">詳細については、「 [How To Add 例をコマンドレットヘルプトピックに追加する方法](./how-to-add-examples-to-a-cmdlet-help-topic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc54c-134">For more information, see [How to Add Examples to a Cmdlet Help Topic](./how-to-add-examples-to-a-cmdlet-help-topic.md).</span></span>                            |
   | `<maml:relatedLinks>`    | <span data-ttu-id="cc54c-135">コマンドレットヘルプトピックの「関連リンク」セクションの内容を追加します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-135">Adds content for the RELATED LINKS section of the cmdlet Help topic.</span></span> <span data-ttu-id="cc54c-136">詳細については、 [コマンドレットヘルプトピックの「関連リンクを追加する方法](./how-to-add-related-links-to-a-cmdlet-help-topic.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc54c-136">For more information, see [How to Add Related Links to a Cmdlet Help Topic](./how-to-add-related-links-to-a-cmdlet-help-topic.md).</span></span>             |

## <a name="example"></a><span data-ttu-id="cc54c-137">例</span><span class="sxs-lookup"><span data-stu-id="cc54c-137">Example</span></span>

 <span data-ttu-id="cc54c-138">コマンドレットのヘルプトピックのさまざまなセクションのノードを含む **コマンド** ノードの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cc54c-138">Here is an example of a **Command** node that includes the nodes for the various sections of the cmdlet Help topic.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="cc54c-139">参照</span><span class="sxs-lookup"><span data-stu-id="cc54c-139">See Also</span></span>

 [<span data-ttu-id="cc54c-140">コマンドレット名と概要を追加する方法</span><span class="sxs-lookup"><span data-stu-id="cc54c-140">How to Add the Cmdlet Name and Synopsis</span></span>](./how-to-add-the-cmdlet-name-and-synopsis-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="cc54c-141">詳細な説明をコマンドレットヘルプトピックに追加する方法</span><span class="sxs-lookup"><span data-stu-id="cc54c-141">How to Add the Detailed Description to a Cmdlet Help Topic</span></span>](./how-to-add-a-cmdlet-description.md)

 [<span data-ttu-id="cc54c-142">コマンドレットのヘルプ トピックに構文を追加する方法</span><span class="sxs-lookup"><span data-stu-id="cc54c-142">How to Add Syntax to a Cmdlet Help Topic</span></span>](./how-to-add-syntax-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="cc54c-143">コマンドレットにパラメーターを追加する方法に関するヘルプトピック</span><span class="sxs-lookup"><span data-stu-id="cc54c-143">How to Add Parameters to a Cmdlet Help Topic</span></span>](./how-to-add-parameter-information.md)

 [<span data-ttu-id="cc54c-144">コマンドレットのヘルプ トピックに入力の種類を追加する方法</span><span class="sxs-lookup"><span data-stu-id="cc54c-144">How to Add Input Types to a Cmdlet Help Topic</span></span>](./how-to-add-input-types-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="cc54c-145">コマンドレットのヘルプ トピックに戻り値を追加する方法</span><span class="sxs-lookup"><span data-stu-id="cc54c-145">How to Add Return Values to a Cmdlet Help Topic</span></span>](./how-to-add-return-values-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="cc54c-146">コマンドレットヘルプトピックにメモを追加する方法</span><span class="sxs-lookup"><span data-stu-id="cc54c-146">How to add Notes to a Cmdlet Help Topic</span></span>](./how-to-add-notes-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="cc54c-147">コマンドレットのヘルプ トピックに例を追加する方法</span><span class="sxs-lookup"><span data-stu-id="cc54c-147">How to Add Examples to a Cmdlet Help Topic</span></span>](./how-to-add-examples-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="cc54c-148">コマンドレットのヘルプ トピックに関連リンクを追加する方法</span><span class="sxs-lookup"><span data-stu-id="cc54c-148">How to Add Related Links to a Cmdlet Help Topic</span></span>](./how-to-add-related-links-to-a-cmdlet-help-topic.md)

 [<span data-ttu-id="cc54c-149">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="cc54c-149">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
