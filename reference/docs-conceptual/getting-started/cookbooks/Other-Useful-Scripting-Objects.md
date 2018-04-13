---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: その他の役に立つスクリプティング オブジェクト
ms.assetid: 4d781196-720b-4ccc-90d2-c570e5e719f5
ms.openlocfilehash: 0e87e9919199e011ab5abec5b07dccc8494ad64a
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="other-useful-scripting-objects"></a><span data-ttu-id="e508a-103">その他の役に立つスクリプティング オブジェクト</span><span class="sxs-lookup"><span data-stu-id="e508a-103">Other Useful Scripting Objects</span></span>

<span data-ttu-id="e508a-104">次のオブジェクトは、Windows PowerShell ISE で追加のスクリプト機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="e508a-104">The following objects provide additional scripting functionality in Windows PowerShell ISE.</span></span> <span data-ttu-id="e508a-105">これらのオブジェクトは **$psISE** 階層の一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="e508a-105">They are not part of the **$psISE** hierarchy.</span></span>

## <a name="useful-scripting-objects"></a><span data-ttu-id="e508a-106">役に立つスクリプティング オブジェクト</span><span class="sxs-lookup"><span data-stu-id="e508a-106">Useful Scripting objects</span></span>

### <a name="psunsupportedconsoleapplications"></a><span data-ttu-id="e508a-107">$psUnsupportedConsoleApplications</span><span class="sxs-lookup"><span data-stu-id="e508a-107">$psUnsupportedConsoleApplications</span></span>

<span data-ttu-id="e508a-108">Windows PowerShell ISE がコンソール アプリケーションと対話操作する方法に関していくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="e508a-108">There are some limitations on how Windows PowerShell ISE interacts with console applications.</span></span> <span data-ttu-id="e508a-109">ユーザーの介入を必要とするコマンドまたは自動化スクリプトは、Windows PowerShell コンソールで機能する場合と同様には機能しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e508a-109">A command or an automation script that requires user intervention might not work the way it works from the Windows PowerShell console.</span></span> <span data-ttu-id="e508a-110">Windows PowerShell ISE のコマンド ウィンドウでこれらのコマンドまたはスクリプトが実行されないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e508a-110">You might want to block these commands or scripts from running in the Windows PowerShell ISE Command pane.</span></span> <span data-ttu-id="e508a-111">**$PsUnsupportedConsoleApplications** オブジェクトは、このようなコマンドの一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="e508a-111">The **$psUnsupportedConsoleApplications** object keeps a list of such commands.</span></span> <span data-ttu-id="e508a-112">この一覧に含まれるコマンドを実行しようとすると、そのコマンドがサポートされていないことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e508a-112">If you try to run the commands in this list, you get a message that they are not supported.</span></span> <span data-ttu-id="e508a-113">次のスクリプトによって一覧にエントリが追加されます。</span><span class="sxs-lookup"><span data-stu-id="e508a-113">The following script adds an entry to the list.</span></span>

```powershell
# List the unsupported commands
$psUnsupportedConsoleApplications

# Add a command to this list
$psUnsupportedConsoleApplications.Add('Mycommand')

# Show the augmented list of commands
$psUnsupportedConsoleApplications
```

### <a name="pslocalhelp"></a><span data-ttu-id="e508a-114">$psLocalHelp</span><span class="sxs-lookup"><span data-stu-id="e508a-114">$psLocalHelp</span></span>

<span data-ttu-id="e508a-115">これは、ヘルプ トピックと、ローカルのコンパイル済み HTML ヘルプ ファイル内の関連するリンクの間のコンテキスト依存のマッピングを保持するディクショナリ オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="e508a-115">This is a dictionary object that maintains a context-sensitive mapping between Help topics and their associated links in the local compiled HTML Help file.</span></span> <span data-ttu-id="e508a-116">特定のトピックのローカル ヘルプを見つけるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e508a-116">It is used to locate the local Help for a particular topic.</span></span> <span data-ttu-id="e508a-117">この一覧からトピックを追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e508a-117">You can add or delete topics from this list.</span></span> <span data-ttu-id="e508a-118">次のコード例では、**$psLocalHelp** に含まれているキーと値のペアの例を示します。</span><span class="sxs-lookup"><span data-stu-id="e508a-118">The following code example shows some example key-value pairs that are contained in **$psLocalHelp**.</span></span>

```powershell
# See the local help map
$psLocalHelp | Format-List
```

### <a name="sample-output"></a><span data-ttu-id="e508a-119">サンプル出力</span><span class="sxs-lookup"><span data-stu-id="e508a-119">Sample Output</span></span>

|||
|-|-|
|<span data-ttu-id="e508a-120">キー: Add-Computer</span><span class="sxs-lookup"><span data-stu-id="e508a-120">Key : Add-Computer</span></span>|<span data-ttu-id="e508a-121">値: WindowsPowerShellHelp.chm::/html/093f660c-b8d5-43cf-aa0c-54e5e54e76f9.htm</span><span class="sxs-lookup"><span data-stu-id="e508a-121">Value : WindowsPowerShellHelp.chm::/html/093f660c-b8d5-43cf-aa0c-54e5e54e76f9.htm</span></span>|
|<span data-ttu-id="e508a-122">キー: Add-Content</span><span class="sxs-lookup"><span data-stu-id="e508a-122">Key : Add-Content</span></span>|<span data-ttu-id="e508a-123">値: WindowsPowerShellHelp.chm::/html/0c836a1b-f389-4e9a-9325-0f415686d194.htm</span><span class="sxs-lookup"><span data-stu-id="e508a-123">Value : WindowsPowerShellHelp.chm::/html/0c836a1b-f389-4e9a-9325-0f415686d194.htm</span></span>|

<span data-ttu-id="e508a-124">次のスクリプトによって一覧にエントリが追加されます。</span><span class="sxs-lookup"><span data-stu-id="e508a-124">The following script adds an entry to the list.</span></span>

```powershell
$psLocalHelp.Add("get-myNoun", "c:\MyFolder\MyHelpChm.chm::/html/0198854a-1298-57ae-aa0c-87b5e5a84712.htm")
```

### <a name="psonlinehelp"></a><span data-ttu-id="e508a-125">$psOnlineHelp</span><span class="sxs-lookup"><span data-stu-id="e508a-125">$psOnlineHelp</span></span>

<span data-ttu-id="e508a-126">これは、ヘルプ トピックのトピック タイトルと、関連する外部 URL の間のコンテキスト依存のマッピングを保持するディクショナリ オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="e508a-126">This is a dictionary object that maintains a context-sensitive mapping between topic titles of Help topics and their associated external URLs.</span></span> <span data-ttu-id="e508a-127">Web で特定のトピックのヘルプを見つけるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e508a-127">It is used to locate the Help for a particular topic on the web.</span></span> <span data-ttu-id="e508a-128">この一覧からトピックを追加または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e508a-128">You can add or delete topics from this list.</span></span>

```powershell
$psOnlineHelp | Format-List
```

### <a name="sample-output"></a><span data-ttu-id="e508a-129">サンプル出力</span><span class="sxs-lookup"><span data-stu-id="e508a-129">Sample Output</span></span>

|||
|-|-|
|<span data-ttu-id="e508a-130">キー: Add-Computer</span><span class="sxs-lookup"><span data-stu-id="e508a-130">Key : Add-Computer</span></span>|<span data-ttu-id="e508a-131">値: http://go.microsoft.com/fwlink/p/?LinkID=135194</span><span class="sxs-lookup"><span data-stu-id="e508a-131">Value : http://go.microsoft.com/fwlink/p/?LinkID=135194</span></span>|
|<span data-ttu-id="e508a-132">キー: Add-Content</span><span class="sxs-lookup"><span data-stu-id="e508a-132">Key : Add-Content</span></span>|<span data-ttu-id="e508a-133">値: http://go.microsoft.com/fwlink/p/?LinkID=113278</span><span class="sxs-lookup"><span data-stu-id="e508a-133">Value : http://go.microsoft.com/fwlink/p/?LinkID=113278</span></span>|

 <span data-ttu-id="e508a-134">次のスクリプトによって一覧にエントリが追加されます。</span><span class="sxs-lookup"><span data-stu-id="e508a-134">The following script adds an entry to the list.</span></span>

```powershell
$psOnlineHelp.Add("get-myNoun", "http://www.mydomain.com/MyNoun.html")
```

## <a name="see-also"></a><span data-ttu-id="e508a-135">参照</span><span class="sxs-lookup"><span data-stu-id="e508a-135">See Also</span></span>

- [<span data-ttu-id="e508a-136">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="e508a-136">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](../../core-powershell/ise/Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)