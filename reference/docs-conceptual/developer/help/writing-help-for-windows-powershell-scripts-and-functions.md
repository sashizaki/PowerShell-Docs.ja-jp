---
title: PowerShell スクリプトと関数のヘルプを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 859a6e22-75b1-43d4-ba62-62c107803b37
caps.latest.revision: 7
ms.openlocfilehash: af989fb2eeba6b68f2e3e6506f3f60d5be6f7d8a
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367721"
---
# <a name="writing-help-for-powershell-scripts-and-functions"></a><span data-ttu-id="b1eed-102">PowerShell スクリプトと関数のヘルプの作成</span><span class="sxs-lookup"><span data-stu-id="b1eed-102">Writing Help for PowerShell Scripts and Functions</span></span>

<span data-ttu-id="b1eed-103">PowerShell スクリプトと関数は、他のユーザーと共有されるたびに、完全に文書化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1eed-103">PowerShell scripts and functions should be fully documented whenever they are shared with others.</span></span>
<span data-ttu-id="b1eed-104">`Get-Help` コマンドレットは、コマンドレットのヘルプを表示するのと同じ形式のスクリプトと関数のヘルプトピックを表示します。また、すべての `Get-Help` パラメーターは、スクリプトと関数のヘルプトピックで動作します。</span><span class="sxs-lookup"><span data-stu-id="b1eed-104">The `Get-Help` cmdlet displays the script and function help topics in the same format as it displays help for cmdlets, and all of the `Get-Help` parameters work on script and function help topics.</span></span>

<span data-ttu-id="b1eed-105">PowerShell スクリプトには、スクリプトの各関数に関するスクリプトとヘルプトピックに関するヘルプトピックを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b1eed-105">PowerShell scripts can include a help topic about the script and help topics about each functions in the script.</span></span>
<span data-ttu-id="b1eed-106">スクリプトとは無関係に共有される関数には、独自のヘルプトピックを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b1eed-106">Functions that are shared independently of scripts can include their own help topics.</span></span>

<span data-ttu-id="b1eed-107">このドキュメントでは、ヘルプトピックの形式と正しい配置について説明し、コンテンツのガイドラインを提示します。</span><span class="sxs-lookup"><span data-stu-id="b1eed-107">This document explains the format and correct placement of the help topics, and it suggests guidelines for the content.</span></span>

## <a name="types-of-script-and-function-help"></a><span data-ttu-id="b1eed-108">スクリプトと関数のヘルプの種類</span><span class="sxs-lookup"><span data-stu-id="b1eed-108">Types of Script and Function Help</span></span>

### <a name="comment-based-help"></a><span data-ttu-id="b1eed-109">コメントベースのヘルプ</span><span class="sxs-lookup"><span data-stu-id="b1eed-109">Comment-Based Help</span></span>
<span data-ttu-id="b1eed-110">スクリプトまたは関数について説明するヘルプトピックは、スクリプトまたは関数内の一連のコメントとして実装できます。</span><span class="sxs-lookup"><span data-stu-id="b1eed-110">The help topic that describes a script or function can be implemented as a set of comments within the script or function.</span></span>
<span data-ttu-id="b1eed-111">スクリプトおよびスクリプト内の関数のコメントベースのヘルプを作成する場合は、コメントベースのヘルプを配置するための規則に注意してください。</span><span class="sxs-lookup"><span data-stu-id="b1eed-111">When writing comment-based help for a script and for functions in a script, pay careful attention to the rules for placing the comment-based help.</span></span>
<span data-ttu-id="b1eed-112">配置によって、`Get-Help` コマンドレットがヘルプトピックをスクリプトまたは関数に関連付けるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="b1eed-112">The placement determines whether the `Get-Help` cmdlet associates the help topic with the script or a function.</span></span>
<span data-ttu-id="b1eed-113">コメントベースのヘルプトピックの記述の詳細については、「 [about_Comment_Based_Help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1eed-113">For more information about writing comment-based help topics, see [about_Comment_Based_Help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help).</span></span>

### <a name="xml-based-command-help"></a><span data-ttu-id="b1eed-114">XML ベースのコマンドのヘルプ</span><span class="sxs-lookup"><span data-stu-id="b1eed-114">XML-Based Command Help</span></span>
<span data-ttu-id="b1eed-115">スクリプトまたは関数について説明するヘルプトピックは、コマンドヘルプスキーマを使用する XML ファイルに実装できます。</span><span class="sxs-lookup"><span data-stu-id="b1eed-115">The help topic that describes a script or function can be implemented in an XML file that uses the command help schema.</span></span>
<span data-ttu-id="b1eed-116">スクリプトまたは関数を XML ファイルに関連付けるには、`ExternalHelp` comment キーワードの後に XML ファイルのパスと名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1eed-116">To associate the script or function with the XML file, use the `ExternalHelp` comment keyword followed by the path and name of the XML file.</span></span>

<span data-ttu-id="b1eed-117">`ExternalHelp` comment キーワードが存在する場合、`ExternalHelp` キーワードの値に一致するヘルプファイルが見つからない `Get-Help` 場合でも、コメントベースのヘルプよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="b1eed-117">When the `ExternalHelp` comment keyword is present, it takes precedence over comment-based help, even when `Get-Help` cannot find a help file that matches the value of the `ExternalHelp` keyword.</span></span>

### <a name="online-help"></a><span data-ttu-id="b1eed-118">オンラインヘルプ</span><span class="sxs-lookup"><span data-stu-id="b1eed-118">Online Help</span></span>
<span data-ttu-id="b1eed-119">ヘルプトピックをインターネットに投稿し、`Get-Help` にダイレクトして、トピックを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="b1eed-119">You can post your help topics on the Internet and then direct `Get-Help` to open the topics.</span></span>
<span data-ttu-id="b1eed-120">コメントベースのヘルプトピックの記述の詳細については、「[オンラインヘルプのサポート](../module/supporting-online-help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1eed-120">For more information about writing comment-based help topics, see [Supporting Online Help](../module/supporting-online-help.md).</span></span>

<span data-ttu-id="b1eed-121">スクリプトと関数に関する概念 ("About") トピックを記述するための方法は確立されていません。</span><span class="sxs-lookup"><span data-stu-id="b1eed-121">There is no established method for writing conceptual ("About") topics for scripts and functions.</span></span>
<span data-ttu-id="b1eed-122">ただし、コマンドのヘルプトピックの「関連リンク」セクションに、トピックとその Url を記載した概念説明のトピックをインターネットに掲載することができます。</span><span class="sxs-lookup"><span data-stu-id="b1eed-122">However, you can post conceptual topics on the Internet list the topics and their URLs in the Related Links section of a command help topic.</span></span>

## <a name="content-considerations-for-script-and-function-help"></a><span data-ttu-id="b1eed-123">スクリプトと関数のヘルプに関するコンテンツに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="b1eed-123">Content Considerations for Script and Function Help</span></span>

- <span data-ttu-id="b1eed-124">使用できるコマンドのヘルプセクションの一部だけを含む非常に短いヘルプトピックを作成する場合は、スクリプトまたは関数のパラメーターについて明確に説明するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="b1eed-124">If you are writing a very brief help topic with only a few of the available command help sections, be sure to include clear descriptions of the script or function parameters.</span></span> <span data-ttu-id="b1eed-125">また、例の説明を省略する場合でも、1つまたは2つのサンプルコマンドを例のセクションに含めます。</span><span class="sxs-lookup"><span data-stu-id="b1eed-125">Also include one or two sample commands in the examples section, even if you decide to omit example descriptions.</span></span>

- <span data-ttu-id="b1eed-126">すべての説明で、スクリプトまたは関数としてコマンドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1eed-126">In all descriptions, refer to the command as a script or function.</span></span> <span data-ttu-id="b1eed-127">この情報は、ユーザーがコマンドを理解し、管理するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b1eed-127">This information helps the user to understand and manage the command.</span></span>

  <span data-ttu-id="b1eed-128">たとえば、次の詳細な説明は、新しいトピックのコマンドがスクリプトであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="b1eed-128">For example, the following detailed description states that the New-Topic command is a script.</span></span> <span data-ttu-id="b1eed-129">これにより、ユーザーが実行時にパスと完全名を指定する必要があることがユーザーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="b1eed-129">This reminds users that they need to specify the path and full name when they run it.</span></span>

  > <span data-ttu-id="b1eed-130">「新しいトピックのスクリプトは、入力ファイル内の各トピック名に対して、空の概念トピックを作成します。」</span><span class="sxs-lookup"><span data-stu-id="b1eed-130">"The New-Topic script creates a blank conceptual topic for each topic name in the input file..."</span></span>

  <span data-ttu-id="b1eed-131">次の詳細な説明は、`Disable-PSRemoting` が関数であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="b1eed-131">The following detailed description states that `Disable-PSRemoting` is a function.</span></span> <span data-ttu-id="b1eed-132">この情報は、セッションに同じ名前の複数のコマンドが含まれていて、優先順位の高いコマンドによって非表示になっている可能性がある場合に、ユーザーにとって特に便利です。</span><span class="sxs-lookup"><span data-stu-id="b1eed-132">This information is particularly useful to users when the session includes multiple commands with the same name, some of which might be hidden by a command with higher precedence.</span></span>

  > <span data-ttu-id="b1eed-133">`Disable-PSRemoting` 関数は、ローカルコンピューター上のすべてのセッション構成を無効にします...</span><span class="sxs-lookup"><span data-stu-id="b1eed-133">The `Disable-PSRemoting` function disables all session configurations on the local computer...</span></span>

- <span data-ttu-id="b1eed-134">スクリプトのヘルプトピックでは、スクリプト全体の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b1eed-134">In a script help topic, explain how to use the script as a whole.</span></span> <span data-ttu-id="b1eed-135">スクリプト内の関数に関するヘルプトピックを作成する場合は、スクリプトのヘルプトピックにある関数について説明し、スクリプトヘルプトピックの「関連リンク」セクションの関数ヘルプトピックへの参照を含めてください。</span><span class="sxs-lookup"><span data-stu-id="b1eed-135">If you are also writing help topics for functions in the script, mention the functions in your script help topic and include references to the function help topics in the Related Links section of the script help topic.</span></span> <span data-ttu-id="b1eed-136">逆に、関数がスクリプトの一部である場合は、関数がスクリプトで果たす役割と、その関数が個別に使用される方法について、関数のヘルプトピックで説明します。</span><span class="sxs-lookup"><span data-stu-id="b1eed-136">Conversely, when a function is part of a script, explain in the function help topic the role that the function plays in the script and how it might be used independently.</span></span> <span data-ttu-id="b1eed-137">次に、関数のヘルプトピックの「関連リンク」セクションで、スクリプトのヘルプトピックを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="b1eed-137">Then list the script help topic in the Related Links section of the function help topic.</span></span>

- <span data-ttu-id="b1eed-138">スクリプトのヘルプトピックの例を記述するときは、スクリプトファイルへのパスを例のコマンドに含めてください。</span><span class="sxs-lookup"><span data-stu-id="b1eed-138">When writing examples for a script help topic, be sure to include the path to the script file in the example command.</span></span> <span data-ttu-id="b1eed-139">これにより、スクリプトが現在のディレクトリにある場合でも、パスを明示的に指定する必要があることがユーザーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="b1eed-139">This reminds users that they must specify the path explicitly, even when the script is in the current directory.</span></span>

- <span data-ttu-id="b1eed-140">関数のヘルプトピックでは、関数が現在のセッションにのみ存在することをユーザーに通知し、他のセッションで使用するには、その機能を追加するか、PowerShell プロファイルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1eed-140">In a function help topic, remind users that the function exists only in the current session and, to use it in other sessions, they need to add it, or add it a PowerShell profile.</span></span>

- <span data-ttu-id="b1eed-141">`Get-Help` スクリプトまたは関数のヘルプトピックが表示されるのは、スクリプトファイルとヘルプトピックファイルが正しい場所に保存されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="b1eed-141">`Get-Help` displays the help topic for a script or function only when the script file and help topic files are saved in the correct locations.</span></span> <span data-ttu-id="b1eed-142">そのため、PowerShell のインストール手順を含めたり、スクリプトや関数をスクリプトまたは関数のヘルプトピックに保存したりインストールしたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b1eed-142">Therefore, it is not useful to include instructions for installing PowerShell, or saving or installing the script or function in a script or function help topic.</span></span> <span data-ttu-id="b1eed-143">代わりに、スクリプトまたは関数の配布に使用するすべてのインストール手順をドキュメントに含めます。</span><span class="sxs-lookup"><span data-stu-id="b1eed-143">Instead, include any installation instructions in the document that you use to distribute the script or function.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1eed-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="b1eed-144">See Also</span></span>

[<span data-ttu-id="b1eed-145">コメントベースのヘルプトピックの作成</span><span class="sxs-lookup"><span data-stu-id="b1eed-145">Writing Comment-Based Help Topics</span></span>](./writing-comment-based-help-topics.md)
