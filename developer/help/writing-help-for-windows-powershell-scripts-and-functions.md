---
title: PowerShell スクリプトや関数のヘルプの記述 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 859a6e22-75b1-43d4-ba62-62c107803b37
caps.latest.revision: 7
ms.openlocfilehash: 98a3f61ff4fa2367f69357173d4e8e14288ff429
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857478"
---
# <a name="writing-help-for-powershell-scripts-and-functions"></a><span data-ttu-id="ee2ee-102">PowerShell スクリプトや関数のヘルプの記述</span><span class="sxs-lookup"><span data-stu-id="ee2ee-102">Writing Help for PowerShell Scripts and Functions</span></span>

<span data-ttu-id="ee2ee-103">PowerShell スクリプトと関数が完全に記述する他のユーザーと共有されるたびに。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-103">PowerShell scripts and functions should be fully documented whenever they are shared with others.</span></span>
<span data-ttu-id="ee2ee-104">`Get-Help`コマンドレット、およびすべてのヘルプが表示されるコマンドレットに同じ形式でスクリプトおよび関数のヘルプ トピックが表示されます、`Get-Help`パラメーターは、スクリプトと関数のヘルプ トピックに機能します。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-104">The `Get-Help` cmdlet displays the script and function help topics in the same format as it displays help for cmdlets, and all of the `Get-Help` parameters work on script and function help topics.</span></span>

<span data-ttu-id="ee2ee-105">PowerShell スクリプトでは、スクリプトの詳細についてのヘルプ トピックと各機能についてのヘルプ トピックをスクリプトに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-105">PowerShell scripts can include a help topic about the script and help topics about each functions in the script.</span></span>
<span data-ttu-id="ee2ee-106">スクリプトとは無関係に共有されている関数は、独自のヘルプ トピックを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-106">Functions that are shared independently of scripts can include their own help topics.</span></span>

<span data-ttu-id="ee2ee-107">このドキュメントは、形式と、ヘルプ トピックの正しい配置について説明し、コンテンツのガイドラインが推奨されています。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-107">This document explains the format and correct placement of the help topics, and it suggests guidelines for the content.</span></span>

## <a name="types-of-script-and-function-help"></a><span data-ttu-id="ee2ee-108">スクリプトと関数のヘルプの種類</span><span class="sxs-lookup"><span data-stu-id="ee2ee-108">Types of Script and Function Help</span></span>

### <a name="comment-based-help"></a><span data-ttu-id="ee2ee-109">コメント ベースのヘルプ</span><span class="sxs-lookup"><span data-stu-id="ee2ee-109">Comment-Based Help</span></span>
<span data-ttu-id="ee2ee-110">スクリプトまたは関数を説明するヘルプ トピックは、スクリプトまたは関数内のコメントのセットとして実装できます。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-110">The help topic that describes a script or function can be implemented as a set of comments within the script or function.</span></span>
<span data-ttu-id="ee2ee-111">スクリプトのコメント ベースのヘルプ、スクリプトおよび関数を記述する場合は、コメント ベースのヘルプを配置するための規則に注意を払います。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-111">When writing comment-based help for a script and for functions in a script, pay careful attention to the rules for placing the comment-based help.</span></span>
<span data-ttu-id="ee2ee-112">配置を決定するかどうか、`Get-Help`コマンドレットは、スクリプトまたは関数のヘルプ トピックを関連付けます。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-112">The placement determines whether the `Get-Help` cmdlet associates the help topic with the script or a function.</span></span>
<span data-ttu-id="ee2ee-113">ヘルプ トピックのコメント ベースの記述方法の詳細については、[about_Comment_Based_Help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-113">For more information about writing comment-based help topics, see [about_Comment_Based_Help](/powershell/module/microsoft.powershell.core/about/about_comment_based_help).</span></span>

### <a name="xml-based-command-help"></a><span data-ttu-id="ee2ee-114">XML ベースのコマンドのヘルプ</span><span class="sxs-lookup"><span data-stu-id="ee2ee-114">XML-Based Command Help</span></span>
<span data-ttu-id="ee2ee-115">スクリプトまたは関数を説明するヘルプ トピックは、コマンドのヘルプのスキーマを使用する XML ファイルに実装できます。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-115">The help topic that describes a script or function can be implemented in an XML file that uses the command help schema.</span></span>
<span data-ttu-id="ee2ee-116">スクリプトまたは関数を XML ファイルに関連付けるには、使用、`ExternalHelp`キーワードの後に、XML ファイルの名前とパスをコメントします。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-116">To associate the script or function with the XML file, use the `ExternalHelp` comment keyword followed by the path and name of the XML file.</span></span>

<span data-ttu-id="ee2ee-117">ときに、`ExternalHelp`場合でも、コメント、キーワードが存在する、コメント ベースのヘルプよりも優先`Get-Help`の値に一致するヘルプ ファイルを見つけることができません、`ExternalHelp`キーワード。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-117">When the `ExternalHelp` comment keyword is present, it takes precedence over comment-based help, even when `Get-Help` cannot find a help file that matches the value of the `ExternalHelp` keyword.</span></span>

### <a name="online-help"></a><span data-ttu-id="ee2ee-118">オンライン ヘルプ</span><span class="sxs-lookup"><span data-stu-id="ee2ee-118">Online Help</span></span>
<span data-ttu-id="ee2ee-119">インターネット上のヘルプ トピックを投稿して、ダイレクト`Get-Help`トピックを開きます。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-119">You can post your help topics on the Internet and then direct `Get-Help` to open the topics.</span></span>
<span data-ttu-id="ee2ee-120">ヘルプ トピックのコメント ベースの記述方法の詳細については、[オンライン ヘルプのサポート](../module/supporting-online-help.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-120">For more information about writing comment-based help topics, see [Supporting Online Help](../module/supporting-online-help.md).</span></span>

<span data-ttu-id="ee2ee-121">書き込み用の確立されたメソッドがコンセプト (「About」) のスクリプトや関数のトピックではありません。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-121">There is no established method for writing conceptual ("About") topics for scripts and functions.</span></span>
<span data-ttu-id="ee2ee-122">ただしに投稿できるインターネット リストの概念説明のトピックのトピックと、Url コマンドのヘルプ トピックの「関連リンク」。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-122">However, you can post conceptual topics on the Internet list the topics and their URLs in the Related Links section of a command help topic.</span></span>

## <a name="content-considerations-for-script-and-function-help"></a><span data-ttu-id="ee2ee-123">コンテンツの考慮事項はスクリプトと関数をヘルプします。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-123">Content Considerations for Script and Function Help</span></span>

- <span data-ttu-id="ee2ee-124">のみの使用可能なコマンドのヘルプ セクションでは、いくつか非常に簡単なヘルプ トピックを作成する場合は、スクリプトまたは関数のパラメーターのクリアの説明を含めることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-124">If you are writing a very brief help topic with only a few of the available command help sections, be sure to include clear descriptions of the script or function parameters.</span></span> <span data-ttu-id="ee2ee-125">例の説明を省略する場合でもは、1 つまたは 2 つのサンプル コマンドは、例」に含まれます。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-125">Also include one or two sample commands in the examples section, even if you decide to omit example descriptions.</span></span>

- <span data-ttu-id="ee2ee-126">すべての説明では、スクリプトまたは関数のようにコマンドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-126">In all descriptions, refer to the command as a script or function.</span></span> <span data-ttu-id="ee2ee-127">この情報は、理解し、コマンドを管理するユーザーに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-127">This information helps the user to understand and manage the command.</span></span>

  <span data-ttu-id="ee2ee-128">たとえば、次の詳細な説明は新規トピック コマンドがスクリプトを示しています。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-128">For example, the following detailed description states that the New-Topic command is a script.</span></span> <span data-ttu-id="ee2ee-129">これは、実行するときに、完全な名前とパスを指定する必要があることを通知します。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-129">This reminds users that they need to specify the path and full name when they run it.</span></span>

  > <span data-ttu-id="ee2ee-130">「新規トピック スクリプトは、入力ファイル の各トピック名を空白の概念説明トピックを作成」</span><span class="sxs-lookup"><span data-stu-id="ee2ee-130">"The New-Topic script creates a blank conceptual topic for each topic name in the input file..."</span></span>

  <span data-ttu-id="ee2ee-131">次の詳細については、ことを示す`Disable-PSRemoting`関数です。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-131">The following detailed description states that `Disable-PSRemoting` is a function.</span></span> <span data-ttu-id="ee2ee-132">この情報は、セッションには、一部の優先順位の高いコマンドによって隠される可能性が、同じ名前の複数のコマンドが含まれている場合、ユーザーに特に便利です。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-132">This information is particularly useful to users when the session includes multiple commands with the same name, some of which might be hidden by a command with higher precedence.</span></span>

  > <span data-ttu-id="ee2ee-133">`Disable-PSRemoting`関数は、ローカル コンピューター上のすべてのセッション構成を無効にしています.</span><span class="sxs-lookup"><span data-stu-id="ee2ee-133">The `Disable-PSRemoting` function disables all session configurations on the local computer...</span></span>

- <span data-ttu-id="ee2ee-134">スクリプトのヘルプ トピックでは、全体として、スクリプトを使用する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-134">In a script help topic, explain how to use the script as a whole.</span></span> <span data-ttu-id="ee2ee-135">スクリプトに関数のヘルプ トピックを作成する場合は、スクリプトのヘルプ トピック内の関数について説明し、スクリプトのヘルプ トピックの「関連リンク」に関数のヘルプ トピックへの参照を含めます。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-135">If you are also writing help topics for functions in the script, mention the functions in your script help topic and include references to the function help topics in the Related Links section of the script help topic.</span></span> <span data-ttu-id="ee2ee-136">逆に、関数は、スクリプトの一部が、について説明する関数のヘルプ トピックの方法で使用できるようにしない独立して、スクリプトで関数が果たす役割。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-136">Conversely, when a function is part of a script, explain in the function help topic the role that the function plays in the script and how it might be used independently.</span></span> <span data-ttu-id="ee2ee-137">関数のヘルプ トピックの「関連リンク」のスクリプトのヘルプ トピックを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-137">Then list the script help topic in the Related Links section of the function help topic.</span></span>

- <span data-ttu-id="ee2ee-138">スクリプトのヘルプ トピックの例を記述する場合は、コマンドの例に、スクリプト ファイルへのパスを含めることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-138">When writing examples for a script help topic, be sure to include the path to the script file in the example command.</span></span> <span data-ttu-id="ee2ee-139">これは通知ことが必要があるパスを指定、明示的にも、スクリプトが現在のディレクトリ内のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-139">This reminds users that they must specify the path explicitly, even when the script is in the current directory.</span></span>

- <span data-ttu-id="ee2ee-140">関数のヘルプ トピックでは、関数が、現在のセッションにのみ存在するユーザーに通知して、追加、または PowerShell プロファイルを追加する必要な他のセッションでこれを使用します。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-140">In a function help topic, remind users that the function exists only in the current session and, to use it in other sessions, they need to add it, or add it a PowerShell profile.</span></span>

- <span data-ttu-id="ee2ee-141">`Get-Help` スクリプト ファイルとヘルプ トピック ファイルは、正しい場所に保存された場合にのみ、スクリプトまたは関数のヘルプ トピックが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-141">`Get-Help` displays the help topic for a script or function only when the script file and help topic files are saved in the correct locations.</span></span> <span data-ttu-id="ee2ee-142">そのため、PowerShell のインストールまたは保存またはスクリプトまたは関数のヘルプ トピックのスクリプトまたは関数をインストールする方法を紹介有用ではありません。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-142">Therefore, it is not useful to include instructions for installing PowerShell, or saving or installing the script or function in a script or function help topic.</span></span> <span data-ttu-id="ee2ee-143">代わりに、スクリプトまたは関数の配布を使用するドキュメントで、インストール手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ee2ee-143">Instead, include any installation instructions in the document that you use to distribute the script or function.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee2ee-144">参照</span><span class="sxs-lookup"><span data-stu-id="ee2ee-144">See Also</span></span>

 [<span data-ttu-id="ee2ee-145">スクリプトや関数のヘルプ トピックを XML ベースの書き込み</span><span class="sxs-lookup"><span data-stu-id="ee2ee-145">Writing XML-Based Help Topics for Scripts and Functions</span></span>](./writing-xml-based-help-topics-for-scripts-and-functions.md)

 [<span data-ttu-id="ee2ee-146">コマンドのヘルプ トピックを XML ベースの書き込み</span><span class="sxs-lookup"><span data-stu-id="ee2ee-146">Writing XML-Based Help Topics for Commands</span></span>](./writing-xml-based-help-topics-for-commands.md)

 [<span data-ttu-id="ee2ee-147">ヘルプ トピックのコメント ベースの書き込み</span><span class="sxs-lookup"><span data-stu-id="ee2ee-147">Writing Comment-Based Help Topics</span></span>](./writing-comment-based-help-topics.md)
