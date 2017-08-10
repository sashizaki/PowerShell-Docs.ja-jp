---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell について"
ms.assetid: 979654ae-7994-47f8-be43-d79e7a140143
ms.openlocfilehash: 5e6d1bb4d8915ba3c83ba0020b959e444b5211cd
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="about-windows-powershell"></a><span data-ttu-id="a6c14-103">Windows PowerShell について</span><span class="sxs-lookup"><span data-stu-id="a6c14-103">About Windows PowerShell</span></span>
<span data-ttu-id="a6c14-104">Windows PowerShell は、従来からの問題を排除し、新しい機能を追加することにより、コマンド ラインおよびスクリプト環境を改善することを目的として設計されています。</span><span class="sxs-lookup"><span data-stu-id="a6c14-104">Windows PowerShell is designed to improve the command-line and scripting environment by eliminating long-standing problems and adding new features.</span></span>

## <a name="discoverability"></a><span data-ttu-id="a6c14-105">機能の見つけやすさ</span><span class="sxs-lookup"><span data-stu-id="a6c14-105">Discoverability</span></span>
<span data-ttu-id="a6c14-106">Windows PowerShell では、簡単にその機能を見つけられます。</span><span class="sxs-lookup"><span data-stu-id="a6c14-106">Windows PowerShell makes it easy to discover its features.</span></span> <span data-ttu-id="a6c14-107">たとえば、Windows サービスを表示したり変更したりするコマンドレットの一覧を検索するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a6c14-107">For example, to find a list of cmdlets that view and change Windows services, type:</span></span>

```
Get-Command *-Service
```

<span data-ttu-id="a6c14-108">タスクを実行するコマンドレットが見つかったら、Get-Help コマンドレットを使用して、コマンドレットの詳細を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="a6c14-108">After discovering which cmdlet accomplishes a task, you can learn more about the cmdlet by using the Get-Help cmdlet.</span></span> <span data-ttu-id="a6c14-109">たとえば、Get-Service コマンドレットのヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="a6c14-109">For example, to display help about the Get-Service cmdlet, type:</span></span>

```
Get-Help Get-Service
```
<span data-ttu-id="a6c14-110">ほとんどのコマンドレットでは、操作を加えてから表示用のテキストに変換できるオブジェクトが出力されます。</span><span class="sxs-lookup"><span data-stu-id="a6c14-110">Most cmdlets emit objects which can be manipulated and then rendered into text for display.</span></span> <span data-ttu-id="a6c14-111">そのコマンドレットの出力を完全に理解するには、Get-Member コマンドレットにその出力をパイプ処理します。</span><span class="sxs-lookup"><span data-stu-id="a6c14-111">To fully understand the output of that cmdlet, pipe its output to the Get-Member cmdlet.</span></span> <span data-ttu-id="a6c14-112">たとえば、次のコマンドは、Get-Service コマンドレットによって出力されるオブジェクトのメンバーについての情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="a6c14-112">For example, the following command displays information about the members of the object output by the Get-Service cmdlet.</span></span>

```
Get-Service | Get-Member
```

## <a name="consistency"></a><span data-ttu-id="a6c14-113">Consistency</span><span class="sxs-lookup"><span data-stu-id="a6c14-113">Consistency</span></span>
<span data-ttu-id="a6c14-114">システム管理は複雑な作業になる場合があります。一貫性のあるインターフェースを備えたツールを使用することで、システム管理に特有の複雑な作業を制御しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="a6c14-114">Managing systems can be a complex endeavor and tools that have a consistent interface help to control the inherent complexity.</span></span> <span data-ttu-id="a6c14-115">残念ながら、コマンド ライン ツールもスクリプト可能な COM オブジェクトも一貫性に優れてはいません。</span><span class="sxs-lookup"><span data-stu-id="a6c14-115">Unfortunately, neither command-line tools nor scriptable COM objects have been known for their consistency.</span></span>

<span data-ttu-id="a6c14-116">Windows PowerShell の持つ一貫性は、その主要な利点の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="a6c14-116">The consistency of Windows PowerShell is one of its primary assets.</span></span> <span data-ttu-id="a6c14-117">たとえば、Sort-Object コマンドレットの使用法を習得すると、その知識を使用して、あらゆるコマンドレットの出力を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="a6c14-117">For example, if you learn how to use the Sort-Object cmdlet, you can use that knowledge to sort the output of any cmdlet.</span></span> <span data-ttu-id="a6c14-118">コマンドレットごとに異なる並べ替えルーチンを習得する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a6c14-118">You do not have to learn the different sorting routines of each cmdlet.</span></span>

<span data-ttu-id="a6c14-119">さらに、コマンドレットの開発者は、コマンドレットの並べ替え機能を設計する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a6c14-119">In addition, cmdlet developers do not have to design sorting features for their cmdlets.</span></span> <span data-ttu-id="a6c14-120">Windows PowerShell は、基本的な機能を備えたフレームワークをコマンドレット開発者に提供し、インターフェイスの多くの側面について一貫性が維持されるよう開発者に強制します。</span><span class="sxs-lookup"><span data-stu-id="a6c14-120">Windows PowerShell gives them a framework that provides the basic features and forces them to be consistent about many aspects of the interface.</span></span> <span data-ttu-id="a6c14-121">このフレームワークにより、通常は開発者に委ねられる選択の一部が減ることになりますが、その代わり、堅牢かつ使いやすいコマンドレットの開発がより簡単に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a6c14-121">The framework eliminates some of the choices that are typically left to the developer, but, in return, it makes the development of robust and easy-to-use cmdlets much simpler.</span></span>

## <a name="interactive-and-scripting-environments"></a><span data-ttu-id="a6c14-122">対話型環境とスクリプト環境</span><span class="sxs-lookup"><span data-stu-id="a6c14-122">Interactive and Scripting Environments</span></span>
<span data-ttu-id="a6c14-123">Windows PowerShell は、対話型環境とスクリプト環境を組み合わせた環境であり、コマンド ライン ツールと COM オブジェクトへのアクセスを提供するだけでなく、.NET Framework クラス ライブラリ (FCL) の強力な機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a6c14-123">Windows PowerShell is a combined interactive and scripting environment that gives you access to command-line tools and COM objects, and also enables you to use the power of the .NET Framework Class Library (FCL).</span></span>

<span data-ttu-id="a6c14-124">この環境は Windows コマンド プロンプトを改良したもので、複数のコマンド ライン ツールを備えた対話型環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="a6c14-124">This environment improves upon the Windows Command Prompt, which provides an interactive environment with multiple command-line tools.</span></span> <span data-ttu-id="a6c14-125">またそれは、Windows Script Host (WSH) スクリプトを改良したものでもあります。WSH では、さまざまなコマンドライン ツールや COM オートメーション オブジェクトを利用できますが、対話型の環境は用意されていません。</span><span class="sxs-lookup"><span data-stu-id="a6c14-125">It also improves upon Windows Script Host (WSH) scripts, which let you use multiple command-line tools and COM automation objects, but do not provide an interactive environment.</span></span>

<span data-ttu-id="a6c14-126">Windows PowerShell では、これらのすべての機能へのアクセスを統合することで、対話型環境のユーザーとスクリプト作成者の作業能力を向上させ、システム管理をより容易に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a6c14-126">By combining access to all of these features, Windows PowerShell extends the ability of the interactive user and the script writer, and makes system administration more manageable.</span></span>

## <a name="object-orientation"></a><span data-ttu-id="a6c14-127">オブジェクト指向</span><span class="sxs-lookup"><span data-stu-id="a6c14-127">Object Orientation</span></span>
<span data-ttu-id="a6c14-128">Windows PowerShell との対話はコマンドをテキストで入力して行いますが、Windows PowerShell は、テキストではなくオブジェクトに基づいています。</span><span class="sxs-lookup"><span data-stu-id="a6c14-128">Although you interact with Windows PowerShell by typing commands in text, Windows PowerShell is based on objects, not text.</span></span> <span data-ttu-id="a6c14-129">コマンドの出力は、オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="a6c14-129">The output of a command is an object.</span></span> <span data-ttu-id="a6c14-130">出力されたオブジェクトは、別のコマンドの入力として渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="a6c14-130">You can send the output object to another command as its input.</span></span> <span data-ttu-id="a6c14-131">その結果、Windows PowerShell は、新しい強力なコマンド ライン パラダイムを導入すると同時に、他のシェルを利用してきたユーザーにとって使い慣れたインターフェイスを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="a6c14-131">As a result, Windows PowerShell provides a familiar interface to people experienced with other shells, while introducing a new and powerful command-line paradigm.</span></span> <span data-ttu-id="a6c14-132">Windows PowerShell では、テキストではなくオブジェクトを渡せるようにすることで、コマンド間でデータを送信するという概念が拡張されています。</span><span class="sxs-lookup"><span data-stu-id="a6c14-132">It extends the concept of sending data between commands by enabling you to send objects, rather than text.</span></span>

## <a name="easy-transition-to-scripting"></a><span data-ttu-id="a6c14-133">スクリプトへの移行が容易</span><span class="sxs-lookup"><span data-stu-id="a6c14-133">Easy Transition to Scripting</span></span>
<span data-ttu-id="a6c14-134">Windows PowerShell では、対話的なコマンドの入力から、それを基にしたスクリプトの作成および実行に容易に移行できます。</span><span class="sxs-lookup"><span data-stu-id="a6c14-134">Windows PowerShell makes it easy to transition from typing commands interactively to creating and running scripts.</span></span> <span data-ttu-id="a6c14-135">Windows PowerShell コマンド プロンプトでコマンドを入力することにより、タスクを実行するコマンドを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="a6c14-135">You can type commands at the Windows PowerShell command prompt to discover the commands that perform a task.</span></span> <span data-ttu-id="a6c14-136">見つかったコマンドはトランスクリプト (履歴) に保存し、後でスクリプトとして使用するためにファイルにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="a6c14-136">Then, you can save those commands in a transcript or a history before copying them to a file for use as a script.</span></span>

