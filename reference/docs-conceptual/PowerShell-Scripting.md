---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: PowerShell スクリプト
ms.openlocfilehash: 7de5a3f3149d8d464b34101d94a5f9430d9b0f23
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34222402"
---
# <a name="powershell"></a><span data-ttu-id="ba729-103">PowerShell</span><span class="sxs-lookup"><span data-stu-id="ba729-103">PowerShell</span></span>

<span data-ttu-id="ba729-104">PowerShell は、システム管理者とパワーユーザー向けに .NET Framework 上に構築されたタスクベースのコマンドライン シェルとスクリプト言語であり、複数のオペレーティング システム (Linux、macOS、Unix、Windows) の管理とこれらのオペレーティング システム上で実行されるアプリケーションに関連するプロセスを迅速に自動化するものです。</span><span class="sxs-lookup"><span data-stu-id="ba729-104">Built on the .NET Framework, PowerShell is a task-based command-line shell and scripting language; it is designed specifically for system administrators and power-users, to rapidly automate the administration of multiple operating systems (Linux, macOS, Unix, and Windows) and the processes related to the applications that run on those operating systems.</span></span>

## <a name="powershell-is-open-source"></a><span data-ttu-id="ba729-105">PowerShell はオープン ソースです</span><span class="sxs-lookup"><span data-stu-id="ba729-105">PowerShell is open source</span></span>

<span data-ttu-id="ba729-106">PowerShell ベースのソース コードは現在、GitHub で入手可能であり、コミュニティ投稿が可能です。</span><span class="sxs-lookup"><span data-stu-id="ba729-106">PowerShell base source code is now available in GitHub and open to community contributions.</span></span> <span data-ttu-id="ba729-107">[GitHub の PowerShell のソース](https://github.com/powershell/powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba729-107">See [PowerShell source on GitHub](https://github.com/powershell/powershell).</span></span>

<span data-ttu-id="ba729-108">「[PowerShell を入手](https://github.com/PowerShell/PowerShell#get-powershell)」で必要なものから開始できます。</span><span class="sxs-lookup"><span data-stu-id="ba729-108">You can start with the bits you need at [get PowerShell](https://github.com/PowerShell/PowerShell#get-powershell).</span></span>
<span data-ttu-id="ba729-109">または、「[はじめに](https://github.com/PowerShell/PowerShell/blob/master/docs/learning-powershell)」からクイック ツアーを開始します。</span><span class="sxs-lookup"><span data-stu-id="ba729-109">Or, perhaps, with a quick tour at [Getting Started](https://github.com/PowerShell/PowerShell/blob/master/docs/learning-powershell)</span></span>

## <a name="powershell-design-goals"></a><span data-ttu-id="ba729-110">PowerShell の設計目標</span><span class="sxs-lookup"><span data-stu-id="ba729-110">PowerShell design goals</span></span>
<span data-ttu-id="ba729-111">Windows PowerShell は、従来からの問題を排除し、新しい機能を追加することにより、コマンド ラインおよびスクリプト環境を改善することを目的として設計されています。</span><span class="sxs-lookup"><span data-stu-id="ba729-111">Windows PowerShell is designed to improve the command-line and scripting environment by eliminating long-standing problems and adding new features.</span></span>

### <a name="discoverability"></a><span data-ttu-id="ba729-112">機能の見つけやすさ</span><span class="sxs-lookup"><span data-stu-id="ba729-112">Discoverability</span></span>
<span data-ttu-id="ba729-113">Windows PowerShell では、簡単にその機能を見つけられます。</span><span class="sxs-lookup"><span data-stu-id="ba729-113">Windows PowerShell makes it easy to discover its features.</span></span> <span data-ttu-id="ba729-114">たとえば、Windows サービスを表示したり変更したりするコマンドレットの一覧を検索するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ba729-114">For example, to find a list of cmdlets that view and change Windows services, type:</span></span>

```powershell
Get-Command *-Service
```

<span data-ttu-id="ba729-115">タスクを実行するコマンドレットが見つかったら、Get-Help コマンドレットを使用して、コマンドレットの詳細を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="ba729-115">After discovering which cmdlet accomplishes a task, you can learn more about the cmdlet by using the Get-Help cmdlet.</span></span> <span data-ttu-id="ba729-116">たとえば、Get-Service コマンドレットのヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ba729-116">For example, to display help about the Get-Service cmdlet, type:</span></span>

```powershell
Get-Help Get-Service
```
<span data-ttu-id="ba729-117">ほとんどのコマンドレットでは、操作を加えてから表示用のテキストに変換できるオブジェクトが出力されます。</span><span class="sxs-lookup"><span data-stu-id="ba729-117">Most cmdlets emit objects which can be manipulated and then rendered into text for display.</span></span> <span data-ttu-id="ba729-118">そのコマンドレットの出力を完全に理解するには、Get-Member コマンドレットにその出力をパイプ処理します。</span><span class="sxs-lookup"><span data-stu-id="ba729-118">To fully understand the output of that cmdlet, pipe its output to the Get-Member cmdlet.</span></span> <span data-ttu-id="ba729-119">たとえば、次のコマンドは、Get-Service コマンドレットによって出力されるオブジェクトのメンバーについての情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="ba729-119">For example, the following command displays information about the members of the object output by the Get-Service cmdlet.</span></span>

```powershell
Get-Service | Get-Member
```

### <a name="consistency"></a><span data-ttu-id="ba729-120">Consistency</span><span class="sxs-lookup"><span data-stu-id="ba729-120">Consistency</span></span>
<span data-ttu-id="ba729-121">システム管理は複雑な作業になる場合があります。一貫性のあるインターフェースを備えたツールを使用することで、システム管理に特有の複雑な作業を制御しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="ba729-121">Managing systems can be a complex endeavor and tools that have a consistent interface help to control the inherent complexity.</span></span> <span data-ttu-id="ba729-122">残念ながら、コマンド ライン ツールもスクリプト可能な COM オブジェクトも一貫性に優れてはいません。</span><span class="sxs-lookup"><span data-stu-id="ba729-122">Unfortunately, neither command-line tools nor scriptable COM objects have been known for their consistency.</span></span>

<span data-ttu-id="ba729-123">Windows PowerShell の持つ一貫性は、その主要な利点の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="ba729-123">The consistency of Windows PowerShell is one of its primary assets.</span></span> <span data-ttu-id="ba729-124">たとえば、Sort-Object コマンドレットの使用法を習得すると、その知識を使用して、あらゆるコマンドレットの出力を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="ba729-124">For example, if you learn how to use the Sort-Object cmdlet, you can use that knowledge to sort the output of any cmdlet.</span></span> <span data-ttu-id="ba729-125">コマンドレットごとに異なる並べ替えルーチンを習得する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ba729-125">You do not have to learn the different sorting routines of each cmdlet.</span></span>

<span data-ttu-id="ba729-126">さらに、コマンドレットの開発者は、コマンドレットの並べ替え機能を設計する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ba729-126">In addition, cmdlet developers do not have to design sorting features for their cmdlets.</span></span> <span data-ttu-id="ba729-127">Windows PowerShell は、基本的な機能を備えたフレームワークをコマンドレット開発者に提供し、インターフェイスの多くの側面について一貫性が維持されるよう開発者に強制します。</span><span class="sxs-lookup"><span data-stu-id="ba729-127">Windows PowerShell gives them a framework that provides the basic features and forces them to be consistent about many aspects of the interface.</span></span> <span data-ttu-id="ba729-128">このフレームワークにより、通常は開発者に委ねられる選択の一部が減ることになりますが、その代わり、堅牢かつ使いやすいコマンドレットの開発がより簡単に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="ba729-128">The framework eliminates some of the choices that are typically left to the developer, but, in return, it makes the development of robust and easy-to-use cmdlets much simpler.</span></span>

### <a name="interactive-and-scripting-environments"></a><span data-ttu-id="ba729-129">対話型環境とスクリプト環境</span><span class="sxs-lookup"><span data-stu-id="ba729-129">Interactive and Scripting Environments</span></span>
<span data-ttu-id="ba729-130">Windows PowerShell は、対話型環境とスクリプト環境を組み合わせた環境であり、コマンド ライン ツールと COM オブジェクトへのアクセスを提供するだけでなく、.NET Framework クラス ライブラリ (FCL) の強力な機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ba729-130">Windows PowerShell is a combined interactive and scripting environment that gives you access to command-line tools and COM objects, and also enables you to use the power of the .NET Framework Class Library (FCL).</span></span>

<span data-ttu-id="ba729-131">この環境は Windows コマンド プロンプトを改良したもので、複数のコマンド ライン ツールを備えた対話型環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="ba729-131">This environment improves upon the Windows Command Prompt, which provides an interactive environment with multiple command-line tools.</span></span> <span data-ttu-id="ba729-132">またそれは、Windows Script Host (WSH) スクリプトを改良したものでもあります。WSH では、さまざまなコマンドライン ツールや COM オートメーション オブジェクトを利用できますが、対話型の環境は用意されていません。</span><span class="sxs-lookup"><span data-stu-id="ba729-132">It also improves upon Windows Script Host (WSH) scripts, which let you use multiple command-line tools and COM automation objects, but do not provide an interactive environment.</span></span>

<span data-ttu-id="ba729-133">Windows PowerShell では、これらのすべての機能へのアクセスを統合することで、対話型環境のユーザーとスクリプト作成者の作業能力を向上させ、システム管理をより容易に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ba729-133">By combining access to all of these features, Windows PowerShell extends the ability of the interactive user and the script writer, and makes system administration more manageable.</span></span>

### <a name="object-orientation"></a><span data-ttu-id="ba729-134">オブジェクト指向</span><span class="sxs-lookup"><span data-stu-id="ba729-134">Object Orientation</span></span>
<span data-ttu-id="ba729-135">Windows PowerShell との対話はコマンドをテキストで入力して行いますが、Windows PowerShell は、テキストではなくオブジェクトに基づいています。</span><span class="sxs-lookup"><span data-stu-id="ba729-135">Although you interact with Windows PowerShell by typing commands in text, Windows PowerShell is based on objects, not text.</span></span> <span data-ttu-id="ba729-136">コマンドの出力は、オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="ba729-136">The output of a command is an object.</span></span> <span data-ttu-id="ba729-137">出力されたオブジェクトは、別のコマンドの入力として渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="ba729-137">You can send the output object to another command as its input.</span></span> <span data-ttu-id="ba729-138">その結果、Windows PowerShell は、新しい強力なコマンド ライン パラダイムを導入すると同時に、他のシェルを利用してきたユーザーにとって使い慣れたインターフェイスを提供することができます。</span><span class="sxs-lookup"><span data-stu-id="ba729-138">As a result, Windows PowerShell provides a familiar interface to people experienced with other shells, while introducing a new and powerful command-line paradigm.</span></span> <span data-ttu-id="ba729-139">Windows PowerShell では、テキストではなくオブジェクトを渡せるようにすることで、コマンド間でデータを送信するという概念が拡張されています。</span><span class="sxs-lookup"><span data-stu-id="ba729-139">It extends the concept of sending data between commands by enabling you to send objects, rather than text.</span></span>

### <a name="easy-transition-to-scripting"></a><span data-ttu-id="ba729-140">スクリプトへの移行が容易</span><span class="sxs-lookup"><span data-stu-id="ba729-140">Easy Transition to Scripting</span></span>
<span data-ttu-id="ba729-141">Windows PowerShell では、対話的なコマンドの入力から、それを基にしたスクリプトの作成および実行に容易に移行できます。</span><span class="sxs-lookup"><span data-stu-id="ba729-141">Windows PowerShell makes it easy to transition from typing commands interactively to creating and running scripts.</span></span> <span data-ttu-id="ba729-142">Windows PowerShell コマンド プロンプトでコマンドを入力することにより、タスクを実行するコマンドを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="ba729-142">You can type commands at the Windows PowerShell command prompt to discover the commands that perform a task.</span></span> <span data-ttu-id="ba729-143">見つかったコマンドはトランスクリプト (履歴) に保存し、後でスクリプトとして使用するためにファイルにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="ba729-143">Then, you can save those commands in a transcript or a history before copying them to a file for use as a script.</span></span>
