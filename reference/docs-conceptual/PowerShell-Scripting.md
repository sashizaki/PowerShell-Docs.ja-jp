---
ms.date: 08/27/2018
keywords: PowerShell, コマンドレット
title: PowerShell スクリプト
ms.openlocfilehash: 754805148dc815a12c5c77e4894fb598c6927f7e
ms.sourcegitcommit: 59727f71dc204785a1bcdedc02716d8340a77aeb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "43133995"
---
# <a name="powershell"></a><span data-ttu-id="7425e-103">PowerShell</span><span class="sxs-lookup"><span data-stu-id="7425e-103">PowerShell</span></span>

<span data-ttu-id="7425e-104">PowerShell は、.NET Framework 上に構築されたタスクベースのコマンド ライン シェルおよびスクリプト言語です。</span><span class="sxs-lookup"><span data-stu-id="7425e-104">PowerShell is a task-based command-line shell and scripting language built on the .NET Framework.</span></span>
<span data-ttu-id="7425e-105">PowerShell によって、システム管理者およびパワー ユーザーは、オペレーティング システム (Linux、macOS、および Windows) とプロセスを管理するタスクを迅速に自動化できます。</span><span class="sxs-lookup"><span data-stu-id="7425e-105">PowerShell helps system administrators and power-users can rapidly automate tasks that manage operating systems (Linux, macOS, and Windows) and processes.</span></span>

<span data-ttu-id="7425e-106">PowerShell コマンドを使用すると、コマンド ラインからコンピューターを管理できます。</span><span class="sxs-lookup"><span data-stu-id="7425e-106">PowerShell commands let you manage computers from the command line.</span></span> <span data-ttu-id="7425e-107">PowerShell プロバイダーを使用すると、レジストリや証明書ストアなどのデータ ストアに、ファイル システムにアクセスする場合と同じくらい簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7425e-107">PowerShell providers let you access data stores, such as the registry and certificate store, as easily as you access the file system.</span></span> <span data-ttu-id="7425e-108">PowerShell には、豊富な式パーサーと、完全に開発されたスクリプト言語があります。</span><span class="sxs-lookup"><span data-stu-id="7425e-108">PowerShell includes a rich expression parser and a fully developed scripting language.</span></span>

## <a name="powershell-is-open-source"></a><span data-ttu-id="7425e-109">オープン ソースの PowerShell</span><span class="sxs-lookup"><span data-stu-id="7425e-109">PowerShell is open-source</span></span>

<span data-ttu-id="7425e-110">PowerShell ベースのソース コードは現在、GitHub で入手可能であり、コミュニティ投稿が可能です。</span><span class="sxs-lookup"><span data-stu-id="7425e-110">PowerShell base source code is now available in GitHub and open to community contributions.</span></span>
<span data-ttu-id="7425e-111">[GitHub の PowerShell のソース](https://github.com/powershell/powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7425e-111">See [PowerShell source on GitHub](https://github.com/powershell/powershell).</span></span>

<span data-ttu-id="7425e-112">「[PowerShell を入手](https://github.com/PowerShell/PowerShell#get-powershell)」で必要なものから開始できます。</span><span class="sxs-lookup"><span data-stu-id="7425e-112">You can start with the bits you need at [Get PowerShell](https://github.com/PowerShell/PowerShell#get-powershell).</span></span>
<span data-ttu-id="7425e-113">または、「[はじめに](https://github.com/PowerShell/PowerShell/blob/master/docs/learning-powershell)」からクイック ツアーを開始します。</span><span class="sxs-lookup"><span data-stu-id="7425e-113">Or, perhaps, with a quick tour at [Getting Started](https://github.com/PowerShell/PowerShell/blob/master/docs/learning-powershell).</span></span>

## <a name="powershell-design-goals"></a><span data-ttu-id="7425e-114">PowerShell の設計目標</span><span class="sxs-lookup"><span data-stu-id="7425e-114">PowerShell design goals</span></span>

<span data-ttu-id="7425e-115">PowerShell は、従来からの問題を排除し、新しい機能を追加することにより、コマンド ラインおよびスクリプト環境を改善することを目的として設計されています。</span><span class="sxs-lookup"><span data-stu-id="7425e-115">PowerShell is designed to improve the command-line and scripting environment by eliminating long-standing problems and adding new features.</span></span>

### <a name="discoverability"></a><span data-ttu-id="7425e-116">機能の見つけやすさ</span><span class="sxs-lookup"><span data-stu-id="7425e-116">Discoverability</span></span>

<span data-ttu-id="7425e-117">PowerShell では、簡単にその機能を見つけられます。</span><span class="sxs-lookup"><span data-stu-id="7425e-117">PowerShell makes it easy to discover its features.</span></span> <span data-ttu-id="7425e-118">たとえば、Windows サービスを表示したり変更したりするコマンドレットの一覧を検索するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7425e-118">For example, to find a list of cmdlets that view and change Windows services, type:</span></span>

```powershell
Get-Command *-Service
```

<span data-ttu-id="7425e-119">タスクを実行するコマンドレットが見つかったら、`Get-Help` コマンドレットを使用して、コマンドレットの詳細を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="7425e-119">After discovering which cmdlet accomplishes a task, you can learn more about the cmdlet by using the `Get-Help` cmdlet.</span></span> <span data-ttu-id="7425e-120">たとえば、`Get-Service` コマンドレットのヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7425e-120">For example, to display help about the `Get-Service` cmdlet, type:</span></span>

```powershell
Get-Help Get-Service
```

<span data-ttu-id="7425e-121">ほとんどのコマンドレットでは、操作が加えられて表示用のテキストとしてレンダリングできるオブジェクトが返されます。</span><span class="sxs-lookup"><span data-stu-id="7425e-121">Most cmdlets return objects that can be manipulated and then rendered as text for display.</span></span> <span data-ttu-id="7425e-122">コマンドレットの出力を完全に理解するには、`Get-Member` コマンドレットにその出力をパイプ処理します。</span><span class="sxs-lookup"><span data-stu-id="7425e-122">To fully understand the output of a cmdlet, pipe the output to the `Get-Member` cmdlet.</span></span> <span data-ttu-id="7425e-123">たとえば、次のコマンドは、`Get-Service` コマンドレットによって出力されるオブジェクトのメンバーについての情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="7425e-123">For example, the following command displays information about the members of the object output by the `Get-Service` cmdlet.</span></span>

```powershell
Get-Service | Get-Member
```

### <a name="consistency"></a><span data-ttu-id="7425e-124">Consistency</span><span class="sxs-lookup"><span data-stu-id="7425e-124">Consistency</span></span>

<span data-ttu-id="7425e-125">システム管理は複雑な作業になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7425e-125">Managing systems can be a complex task.</span></span> <span data-ttu-id="7425e-126">一貫性のあるインターフェースを備えたツールを使用することで、システム管理に特有の複雑な作業を制御しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="7425e-126">Tools that have a consistent interface help to control the inherent complexity.</span></span> <span data-ttu-id="7425e-127">残念ながら、コマンド ライン ツールもスクリプト可能な COM オブジェクトも一貫性に優れてはいません。</span><span class="sxs-lookup"><span data-stu-id="7425e-127">Unfortunately, command-line tools and scriptable COM objects aren't known for their consistency.</span></span>

<span data-ttu-id="7425e-128">PowerShell の持つ一貫性は、その主要な利点の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="7425e-128">The consistency of PowerShell is one of its primary assets.</span></span> <span data-ttu-id="7425e-129">たとえば、`Sort-Object` コマンドレットの使用法を習得すると、その知識を利用してあらゆるコマンドレットの出力を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="7425e-129">For example, if you learn how to use the `Sort-Object` cmdlet, you can use that knowledge to sort the output of any cmdlet.</span></span> <span data-ttu-id="7425e-130">コマンドレットごとに異なる並べ替えルーチンを習得する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7425e-130">You don't have to learn the different sorting routines of each cmdlet.</span></span>

<span data-ttu-id="7425e-131">さらに、コマンドレットの開発者は、コマンドレットの並べ替え機能を設計する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7425e-131">Additionally, cmdlet developers don't have to design sorting features for their cmdlets.</span></span> <span data-ttu-id="7425e-132">PowerShell では、一貫性を適用する基本的な機能を、フレームワークに対して提供しています。</span><span class="sxs-lookup"><span data-stu-id="7425e-132">PowerShell provides a framework with the basic features that forces consistency.</span></span> <span data-ttu-id="7425e-133">フレームワークを使用すると、開発者に委ねられている一部の選択肢は利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7425e-133">The framework eliminates some choices that are left to the developer.</span></span> <span data-ttu-id="7425e-134">ただし、その見返りとして、コマンドレットの開発はずっと簡単になります。</span><span class="sxs-lookup"><span data-stu-id="7425e-134">But, in return, it makes the development of cmdlets much simpler.</span></span>

### <a name="interactive-and-scripting-environments"></a><span data-ttu-id="7425e-135">対話型環境とスクリプト環境</span><span class="sxs-lookup"><span data-stu-id="7425e-135">Interactive and scripting environments</span></span>

<span data-ttu-id="7425e-136">Windows コマンド プロンプトは、コマンドライン ツールと基本的なスクリプトへのアクセスを備えた対話型シェルを提供しています。</span><span class="sxs-lookup"><span data-stu-id="7425e-136">The Windows Command Prompt provides an interactive shell with access to command-line tools and basic scripting.</span></span> <span data-ttu-id="7425e-137">Windows Script Host (WSH) は、スクリプトを作成できるコマンドライン ツールと COM 自動化オブジェクトを備えていますが、対話型シェルは提供していません。</span><span class="sxs-lookup"><span data-stu-id="7425e-137">Windows Script Host (WSH) has scriptable command-line tools and COM automation objects, but doesn't provide an interactive shell.</span></span>

<span data-ttu-id="7425e-138">PowerShell では、対話型シェルとスクリプト環境を組み合わせています。</span><span class="sxs-lookup"><span data-stu-id="7425e-138">PowerShell combines an interactive shell and a scripting environment.</span></span> <span data-ttu-id="7425e-139">PowerShell では、コマンド ライン ツール、COM オブジェクト、および .NET クラス ライブラリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7425e-139">PowerShell can access command-line tools, COM objects, and .NET class libraries.</span></span> <span data-ttu-id="7425e-140">この機能の組み合わせによって、対話型ユーザー、スクリプトの作成者、およびシステム管理者が利用できる機能が拡張されます。</span><span class="sxs-lookup"><span data-stu-id="7425e-140">This combination of features extends the capabilities of the interactive user, the script writer, and the system administrator.</span></span>

### <a name="object-orientation"></a><span data-ttu-id="7425e-141">オブジェクト指向</span><span class="sxs-lookup"><span data-stu-id="7425e-141">Object orientation</span></span>

<span data-ttu-id="7425e-142">PowerShell は、テキストではなくオブジェクトに基づいています。</span><span class="sxs-lookup"><span data-stu-id="7425e-142">PowerShell is based on object not text.</span></span> <span data-ttu-id="7425e-143">コマンドの出力は、オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="7425e-143">The output of a command is an object.</span></span> <span data-ttu-id="7425e-144">出力されたオブジェクトは、パイプライン経由で、別のコマンドに入力として送信できます。</span><span class="sxs-lookup"><span data-stu-id="7425e-144">You can send the output object, through the pipeline, to another command as its input.</span></span>

<span data-ttu-id="7425e-145">このパイプラインは、他のシェルの使用経験があるユーザーにとって使い慣れたインターフェイスを提供しています。</span><span class="sxs-lookup"><span data-stu-id="7425e-145">This pipeline provides a familiar interface for people experienced with other shells.</span></span> <span data-ttu-id="7425e-146">PowerShell では、テキストではなくオブジェクトを送信することによって、この概念を拡張します。</span><span class="sxs-lookup"><span data-stu-id="7425e-146">PowerShell extends this concept by sending objects rather than text.</span></span>

### <a name="easy-transition-to-scripting"></a><span data-ttu-id="7425e-147">スクリプトへの移行が容易</span><span class="sxs-lookup"><span data-stu-id="7425e-147">Easy transition to scripting</span></span>

<span data-ttu-id="7425e-148">PowerShell のコマンドは見つけやすいので、対話的なコマンドの入力からスクリプトの作成および実行へと、簡単に移行できます。</span><span class="sxs-lookup"><span data-stu-id="7425e-148">PowerShell's command discoverability makes it easy to transition from typing commands interactively to creating and running scripts.</span></span> <span data-ttu-id="7425e-149">PowerShell のトランスクリプトと履歴を利用して、コマンドをファイルにコピーして、簡単にスクリプトとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="7425e-149">PowerShell transcripts and history make it easy to copy commands to a file for use as a script.</span></span>
