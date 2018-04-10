---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: Windows PowerShell パイプラインを理解する
ms.assetid: 6be50926-7943-4ef7-9499-4490d72a63fb
ms.openlocfilehash: c3f1d17432cf3a77c0f5ecae137a4233a28a19d7
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="understanding-the-windows-powershell-pipeline"></a><span data-ttu-id="26470-103">Windows PowerShell パイプラインを理解する</span><span class="sxs-lookup"><span data-stu-id="26470-103">Understanding the Windows PowerShell Pipeline</span></span>
<span data-ttu-id="26470-104">Windows PowerShell では、パイプ処理をほぼすべての状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="26470-104">Piping works virtually everywhere in Windows PowerShell.</span></span> <span data-ttu-id="26470-105">画面にはテキストが表示されますが、コマンド間で受け渡しされる情報はテキストではありません。</span><span class="sxs-lookup"><span data-stu-id="26470-105">Although you see text on the screen, Windows PowerShell does not pipe text between commands.</span></span> <span data-ttu-id="26470-106">パイプの中を流れるデータは、実際にはオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="26470-106">Instead, it pipes objects.</span></span>

<span data-ttu-id="26470-107">パイプラインで使う表記は他のシェルで使う表記に似ているため、一見すると、Windows PowerShell で何かが新しく導入されたことがわかりにくい可能性があります。</span><span class="sxs-lookup"><span data-stu-id="26470-107">The notation used for pipelines is similar to that used in other shells, so at first glance, it may not be apparent that Windows PowerShell introduces something new.</span></span> <span data-ttu-id="26470-108">たとえば、**Out-Host** コマンドレットを使用して、別のコマンドからの出力をページ単位で表示させると、通常のテキストがページごとに分割されて画面上に表示されているだけのように見えます。</span><span class="sxs-lookup"><span data-stu-id="26470-108">For example, if you use the **Out-Host** cmdlet to force a page-by-page display of output from another command, the output looks just like the normal text displayed on the screen, broken up into pages:</span></span>

```
PS> Get-ChildItem -Path C:\WINDOWS\System32 | Out-Host -Paging

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\WINDOWS\system32

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2005-10-22  11:04 PM        315 $winnt$.inf
-a---        2004-08-04   8:00 AM      68608 access.cpl
-a---        2004-08-04   8:00 AM      64512 acctres.dll
-a---        2004-08-04   8:00 AM     183808 accwiz.exe
-a---        2004-08-04   8:00 AM      61952 acelpdec.ax
-a---        2004-08-04   8:00 AM     129536 acledit.dll
-a---        2004-08-04   8:00 AM     114688 aclui.dll
-a---        2004-08-04   8:00 AM     194048 activeds.dll
-a---        2004-08-04   8:00 AM     111104 activeds.tlb
-a---        2004-08-04   8:00 AM       4096 actmovie.exe
-a---        2004-08-04   8:00 AM     101888 actxprxy.dll
-a---        2003-02-21   6:50 PM     143150 admgmt.msc
-a---        2006-01-25   3:35 PM      53760 admparse.dll
<SPACE> next page; <CR> next line; Q quit
...
```

<span data-ttu-id="26470-109">Out-Host -Paging コマンドは、長大な出力結果を少しずつ表示したい場合に役立つパイプライン要素です。</span><span class="sxs-lookup"><span data-stu-id="26470-109">The Out-Host -Paging command is a useful pipeline element whenever you have lengthy output that you would like to display slowly.</span></span> <span data-ttu-id="26470-110">特に、CPU への負荷がきわめて大きい処理で使用すると便利です。</span><span class="sxs-lookup"><span data-stu-id="26470-110">It is especially useful if the operation is very CPU-intensive.</span></span> <span data-ttu-id="26470-111">処理は 1 ページ分を表示する準備が整った段階で Out-Host コマンドレットに渡されるため、パイプラインにおける直前のコマンドレットは、次のページの出力の用意ができるまで処理を中断します。</span><span class="sxs-lookup"><span data-stu-id="26470-111">Because processing is transferred to the Out-Host cmdlet when it has a complete page ready to display, cmdlets that precede it in the pipeline halt operation until the next page of output is available.</span></span> <span data-ttu-id="26470-112">このことは、Windows PowerShell による CPU およびメモリの使用状況を Windows タスク マネージャーで監視するとわかります。</span><span class="sxs-lookup"><span data-stu-id="26470-112">You can see this if you use the Windows Task Manager to monitor CPU and memory use by Windows PowerShell.</span></span>

<span data-ttu-id="26470-113">次のコマンドを実行します:**Get-ChildItem C:\\Windows -Recurse**。</span><span class="sxs-lookup"><span data-stu-id="26470-113">Run the following command: **Get-ChildItem C:\\Windows -Recurse**.</span></span> <span data-ttu-id="26470-114">CPU とメモリ使用量を、次のコマンドと比較します: **Get-ChildItem C:\\Windows -Recurse | Out-Host -Paging**。</span><span class="sxs-lookup"><span data-stu-id="26470-114">Compare the CPU and memory usage to this command: **Get-ChildItem C:\\Windows -Recurse | Out-Host -Paging**.</span></span> <span data-ttu-id="26470-115">画面に表示されるのはテキストですが、これは、コンソール ウィンドウに表示するためには、オブジェクトをテキストで表す必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="26470-115">What you see on the screen is text, but that is because it is necessary to represent objects as text in a console window.</span></span> <span data-ttu-id="26470-116">これは、Windows PowerShell 内部で実際に行われていることを表現するための 1 つの手段にすぎません。</span><span class="sxs-lookup"><span data-stu-id="26470-116">This is just a representation of what is really going on inside Windows PowerShell.</span></span> <span data-ttu-id="26470-117">Get-Location コマンドレットを例に考えてみます。</span><span class="sxs-lookup"><span data-stu-id="26470-117">For example, consider the Get-Location cmdlet.</span></span> <span data-ttu-id="26470-118">現在の場所が C ドライブのルートである場合に、**Get-Location** と入力すると、次のような出力結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="26470-118">If you type **Get-Location** while your current location is the root of the C drive, you would see the following output:</span></span>

```
PS> Get-Location

Path
----
C:\
```

<span data-ttu-id="26470-119">パイプラインを流れるデータがテキストだとした場合、**Get-Location | Out-Host** というコマンドを実行すると、**Get-Location** から **Out-Host** には、一連の文字が、画面に表示される順番で渡されます。</span><span class="sxs-lookup"><span data-stu-id="26470-119">If Windows PowerShell pipelined text, issuing a command such as **Get-Location | Out-Host**, would pass from **Get-Location** to **Out-Host** a set of characters in the order they are displayed onscreen.</span></span> <span data-ttu-id="26470-120">つまり、見出し情報を無視すれば、**Out-Host** は '**C'**、'**:'**、'**\\'** の順に文字を受け取ることになります。</span><span class="sxs-lookup"><span data-stu-id="26470-120">In other words, if you were to ignore the heading information, **Out-Host** would first receive the character '**C'**, then the character '**:'**, then the character '**\\'**.</span></span> <span data-ttu-id="26470-121">**Out-Host** コマンドレットは、**Get-Location** コマンドレットによって出力された文字にどの意味を関連付けるかを判断できません。</span><span class="sxs-lookup"><span data-stu-id="26470-121">The **Out-Host** cmdlet could not determine what meaning to associate with the characters output by the **Get-Location** cmdlet.</span></span>

<span data-ttu-id="26470-122">Windows PowerShell では、パイプラインのコマンド間でデータを受け渡すのに、テキストではなくオブジェクトが使用されています。</span><span class="sxs-lookup"><span data-stu-id="26470-122">Instead of using text to let commands in a pipeline communicate, Windows PowerShell uses objects.</span></span> <span data-ttu-id="26470-123">ユーザーの立場から見ると、関連する情報がオブジェクトとしてパッケージ化されることにより、情報が扱いやすい単位でまとめられ、必要に応じて特定の項目だけを抽出できるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="26470-123">From the standpoint of a user, objects package related information into a form that makes it easier to manipulate the information as a unit, and extract specific items that you need.</span></span>

<span data-ttu-id="26470-124">**Get-Location** コマンドは、現在のパスを表すテキストを返すわけではありません。</span><span class="sxs-lookup"><span data-stu-id="26470-124">The **Get-Location** command does not return text that contains the current path.</span></span> <span data-ttu-id="26470-125">実際に返されるのは、**PathInfo** オブジェクトという情報のパッケージです。このオブジェクトには、現在のパスだけでなく、他の情報も一緒に格納されています。</span><span class="sxs-lookup"><span data-stu-id="26470-125">It returns a package of information called a **PathInfo** object that contains the current path along with some other information.</span></span> <span data-ttu-id="26470-126">この **PathInfo** オブジェクトが **Out-Host** コマンドレットによって画面に送られると、Windows PowerShell は、どの情報をどのように表示するかを書式ルールに基づいて決定します。</span><span class="sxs-lookup"><span data-stu-id="26470-126">The **Out-Host** cmdlet then sends this **PathInfo** object to the screen, and Windows PowerShell decides what information to display and how to display it based on its formatting rules.</span></span>

<span data-ttu-id="26470-127">実際、**Get-Location** コマンドレットによって出力される見出し情報は、処理の最後になって初めて、画面表示用にデータを書式設定するプロセスの一部として追加されます。</span><span class="sxs-lookup"><span data-stu-id="26470-127">In fact, the heading information output by the **Get-Location** cmdlet is added only at the end of the process, as part of the process of formatting the data for onscreen display.</span></span> <span data-ttu-id="26470-128">ユーザーが画面で確認できるのは情報の要約であり、出力されたオブジェクトの完全な表現ではありません。</span><span class="sxs-lookup"><span data-stu-id="26470-128">What you see onscreen is a summary of information, and not a complete representation of the output object.</span></span>

<span data-ttu-id="26470-129">Windows PowerShell のコマンドから、コンソール ウィンドウに表示されている以上の情報が出力されているとすれば、見えない要素を取得するにはどうすればよいのかという疑問が残ります。</span><span class="sxs-lookup"><span data-stu-id="26470-129">Given that there may be more information output from a Windows PowerShell command than what we see displayed in the console window, how can you retrieve the non-visible elements?</span></span> <span data-ttu-id="26470-130">つまり、残りのデータを表示するにはどうすればよいか、</span><span class="sxs-lookup"><span data-stu-id="26470-130">How do you view the extra data?</span></span> <span data-ttu-id="26470-131">また、Windows PowerShell で通常使用される表示形式とは異なる形式でデータを表示するにはどうすればよいのかという点です。</span><span class="sxs-lookup"><span data-stu-id="26470-131">And what if you want to view the data in a format different than the one Windows PowerShell normally uses?</span></span>

<span data-ttu-id="26470-132">この章の残りの部分では、特定の Windows PowerShell オブジェクトの構造を調べる方法、特定の項目を選んで見やすいように書式化する方法、この情報を他の出力場所 (ファイルやプリンターなど) に送る方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="26470-132">The rest of this chapter discusses how you can discover the structure of specific Windows PowerShell objects, selecting specific items and formatting them for easier display, and how to send this information to alternative output locations such as files and printers.</span></span>