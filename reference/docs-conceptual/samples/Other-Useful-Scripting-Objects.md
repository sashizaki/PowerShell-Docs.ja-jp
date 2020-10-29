---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: その他の役に立つスクリプティング オブジェクト
description: この記事では、Windows PowerShell ISE で追加のスクリプト機能を提供するオブジェクトについて説明します。
ms.openlocfilehash: c20daa0045bc07b1f21aafa42a80ce7c47ee7331
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500268"
---
# <a name="other-useful-scripting-objects"></a><span data-ttu-id="ae352-104">その他の役に立つスクリプティング オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ae352-104">Other Useful Scripting Objects</span></span>

<span data-ttu-id="ae352-105">次のオブジェクトは、Windows PowerShell ISE で追加のスクリプト機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="ae352-105">The following objects provide additional scripting functionality in Windows PowerShell ISE.</span></span> <span data-ttu-id="ae352-106">これらのオブジェクトは **$psISE** 階層の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="ae352-106">They are not part of the **$psISE** hierarchy.</span></span>

## <a name="useful-scripting-objects"></a><span data-ttu-id="ae352-107">役に立つスクリプティング オブジェクト</span><span class="sxs-lookup"><span data-stu-id="ae352-107">Useful Scripting objects</span></span>

### <a name="psunsupportedconsoleapplications"></a><span data-ttu-id="ae352-108">$psUnsupportedConsoleApplications</span><span class="sxs-lookup"><span data-stu-id="ae352-108">$psUnsupportedConsoleApplications</span></span>

<span data-ttu-id="ae352-109">Windows PowerShell ISE がコンソール アプリケーションと対話操作する方法に関していくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="ae352-109">There are some limitations on how Windows PowerShell ISE interacts with console applications.</span></span> <span data-ttu-id="ae352-110">ユーザーの介入を必要とするコマンドまたは自動化スクリプトは、Windows PowerShell コンソールで機能する場合と同様には機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ae352-110">A command or an automation script that requires user intervention might not work the way it works from the Windows PowerShell console.</span></span> <span data-ttu-id="ae352-111">Windows PowerShell ISE のコマンド ウィンドウでこれらのコマンドまたはスクリプトが実行されないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae352-111">You might want to block these commands or scripts from running in the Windows PowerShell ISE Command pane.</span></span> <span data-ttu-id="ae352-112">**$PsUnsupportedConsoleApplications** オブジェクトは、このようなコマンドの一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="ae352-112">The **$psUnsupportedConsoleApplications** object keeps a list of such commands.</span></span> <span data-ttu-id="ae352-113">この一覧に含まれるコマンドを実行しようとすると、そのコマンドがサポートされていないことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ae352-113">If you try to run the commands in this list, you get a message that they are not supported.</span></span> <span data-ttu-id="ae352-114">次のスクリプトによって一覧にエントリが追加されます。</span><span class="sxs-lookup"><span data-stu-id="ae352-114">The following script adds an entry to the list.</span></span>

```powershell
# List the unsupported commands
$psUnsupportedConsoleApplications

# Add a command to this list
$psUnsupportedConsoleApplications.Add('Mycommand')

# Show the augmented list of commands
$psUnsupportedConsoleApplications
```

### <a name="pslocalhelp"></a><span data-ttu-id="ae352-115">$psLocalHelp</span><span class="sxs-lookup"><span data-stu-id="ae352-115">$psLocalHelp</span></span>

<span data-ttu-id="ae352-116">これは、ヘルプ トピックと、ローカルのコンパイル済み HTML ヘルプ ファイル内の関連するリンクの間のコンテキスト依存のマッピングを保持するディクショナリ オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="ae352-116">This is a dictionary object that maintains a context-sensitive mapping between Help topics and their associated links in the local compiled HTML Help file.</span></span> <span data-ttu-id="ae352-117">特定のトピックのローカル ヘルプを見つけるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae352-117">It is used to locate the local Help for a particular topic.</span></span> <span data-ttu-id="ae352-118">この一覧からトピックを追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ae352-118">You can add or delete topics from this list.</span></span> <span data-ttu-id="ae352-119">次のコード例では、`$psLocalHelp` に含まれているキーと値のペアの例を示します。</span><span class="sxs-lookup"><span data-stu-id="ae352-119">The following code example shows some example key-value pairs that are contained in `$psLocalHelp`.</span></span>

```powershell
# See the local help map
$psLocalHelp | Format-List
```

```Output
Key   : Add-Computer
Value : WindowsPowerShellHelp.chm::/html/093f660c-b8d5-43cf-aa0c-54e5e54e76f9.htm

Key   : Add-Content
Value : WindowsPowerShellHelp.chm::/html/0c836a1b-f389-4e9a-9325-0f415686d194.htm
```

<span data-ttu-id="ae352-120">次のスクリプトによって一覧にエントリが追加されます。</span><span class="sxs-lookup"><span data-stu-id="ae352-120">The following script adds an entry to the list.</span></span>

```powershell
$psLocalHelp.Add("get-myNoun", "c:\MyFolder\MyHelpChm.chm::/html/0198854a-1298-57ae-aa0c-87b5e5a84712.htm")
```

### <a name="psonlinehelp"></a><span data-ttu-id="ae352-121">$psOnlineHelp</span><span class="sxs-lookup"><span data-stu-id="ae352-121">$psOnlineHelp</span></span>

<span data-ttu-id="ae352-122">これは、ヘルプ トピックのトピック タイトルと、関連する外部 URL の間のコンテキスト依存のマッピングを保持するディクショナリ オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="ae352-122">This is a dictionary object that maintains a context-sensitive mapping between topic titles of Help topics and their associated external URLs.</span></span> <span data-ttu-id="ae352-123">Web で特定のトピックのヘルプを見つけるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae352-123">It is used to locate the Help for a particular topic on the web.</span></span> <span data-ttu-id="ae352-124">この一覧からトピックを追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ae352-124">You can add or delete topics from this list.</span></span>

```powershell
$psOnlineHelp | Format-List
```

```Output
Key   : Add-Computer
Value : https://go.microsoft.com/fwlink/p/?LinkID=135194

Key   : Add-Content
Value : https://go.microsoft.com/fwlink/p/?LinkID=113278
```

<span data-ttu-id="ae352-125">次のスクリプトによって一覧にエントリが追加されます。</span><span class="sxs-lookup"><span data-stu-id="ae352-125">The following script adds an entry to the list.</span></span>

```powershell
$psOnlineHelp.Add("get-myNoun", "https://www.mydomain.com/MyNoun.html")
```

## <a name="see-also"></a><span data-ttu-id="ae352-126">参照</span><span class="sxs-lookup"><span data-stu-id="ae352-126">See Also</span></span>

[<span data-ttu-id="ae352-127">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="ae352-127">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](../components/ise/object-model/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
