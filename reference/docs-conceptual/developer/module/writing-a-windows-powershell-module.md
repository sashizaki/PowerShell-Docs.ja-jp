---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell モジュールを記述する
description: Windows PowerShell モジュールを記述する
ms.openlocfilehash: 307241f0fb4d12c1a5cbd651a0ae4d5303098b27
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659423"
---
# <a name="writing-a-windows-powershell-module"></a><span data-ttu-id="3c205-103">Windows PowerShell モジュールを記述する</span><span class="sxs-lookup"><span data-stu-id="3c205-103">Writing a Windows PowerShell Module</span></span>

<span data-ttu-id="3c205-104">このドキュメントは、Windows PowerShell コマンドレットをパッケージ化して配布する必要がある管理者、スクリプト開発者、およびコマンドレットの開発者を対象に書かれています。</span><span class="sxs-lookup"><span data-stu-id="3c205-104">This document is written for administrators, script developers, and cmdlet developers who need to package and distribute their Windows PowerShell cmdlets.</span></span> <span data-ttu-id="3c205-105">Windows PowerShell モジュールを使用すると、コンパイルされた言語を使用せずに、Windows PowerShell ソリューションをパッケージ化して配布することができます。</span><span class="sxs-lookup"><span data-stu-id="3c205-105">By using Windows PowerShell modules, you can package and distribute your Windows PowerShell solutions without using a compiled language.</span></span>

<span data-ttu-id="3c205-106">Windows PowerShell モジュールを使用すると、Windows PowerShell コードをパーティション分割し、自己完結型の再利用可能な単位にまとめることができます。</span><span class="sxs-lookup"><span data-stu-id="3c205-106">Windows PowerShell modules enable you to partition, organize, and abstract your Windows PowerShell code into self-contained, reusable units.</span></span> <span data-ttu-id="3c205-107">これらの再利用可能なユニットを使用すると、モジュールを他のユーザーと直接簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="3c205-107">With these reusable units, you can easily share your modules directly with others.</span></span> <span data-ttu-id="3c205-108">スクリプト開発者は、サードパーティのモジュールを再パッケージ化して、カスタムスクリプトベースのアプリケーションを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3c205-108">If you are a script developer, you can also repackage third-party modules to create custom script-based applications.</span></span> <span data-ttu-id="3c205-109">モジュールは、Perl や Python などの他のスクリプト言語のモジュールに似ており、再頒布可能な再頒布可能コンポーネントを使用する実稼働対応のスクリプトソリューションを実現し、複数のコンポーネントを再パッケージ化および抽象化してカスタムソリューションを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3c205-109">Modules, similar to modules in other scripting languages such as Perl and Python, enable production-ready scripting solutions that use reusable, redistributable components, with the added benefit of enabling you to repackage and abstract multiple components to create custom solutions.</span></span>

<span data-ttu-id="3c205-110">基本的には、Windows PowerShell は、hbase-runner.psm1 ファイルに保存されている有効な Windows PowerShell スクリプトコードをモジュールとして扱います。</span><span class="sxs-lookup"><span data-stu-id="3c205-110">At their most basic, Windows PowerShell will treat any valid Windows PowerShell script code saved in a .psm1 file as a module.</span></span> <span data-ttu-id="3c205-111">また、PowerShell は、バイナリコマンドレットアセンブリをモジュールとして自動的に処理します。</span><span class="sxs-lookup"><span data-stu-id="3c205-111">PowerShell will also automatically treat any binary cmdlet assembly as a module.</span></span> <span data-ttu-id="3c205-112">ただし、モジュール (具体的にはモジュールマニフェスト) を使用して、ソリューション全体をまとめてバンドルすることもできます。</span><span class="sxs-lookup"><span data-stu-id="3c205-112">However, you can also use a module (or more specifically, a module manifest) to bundle an entire solution together.</span></span> <span data-ttu-id="3c205-113">次のシナリオでは、Windows PowerShell モジュールの一般的な使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3c205-113">The following scenarios describe typical uses for Windows PowerShell modules.</span></span>

### <a name="libraries"></a><span data-ttu-id="3c205-114">ライブラリ</span><span class="sxs-lookup"><span data-stu-id="3c205-114">Libraries</span></span>

<span data-ttu-id="3c205-115">モジュールを使用すると、一般的なタスクを実行する関数のまとまりのあるライブラリをパッケージ化して配布することができます。</span><span class="sxs-lookup"><span data-stu-id="3c205-115">Modules can be used to package and distribute cohesive libraries of functions that perform common tasks.</span></span> <span data-ttu-id="3c205-116">通常、これらの関数の名前は、使用される一般的なタスクを反映する1つまたは複数の名詞を共有します。</span><span class="sxs-lookup"><span data-stu-id="3c205-116">Typically, the names of these functions share one or more nouns that reflect the common task that they are used for.</span></span> <span data-ttu-id="3c205-117">これらの関数は、パブリックメンバーとプライベートメンバーを持つことができるという点で .NET Framework クラスに似ている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="3c205-117">These functions can also be similar to .NET Framework classes in that they can have public and private members.</span></span> <span data-ttu-id="3c205-118">たとえば、ライブラリには、ファイル転送用の一連の関数を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3c205-118">For example, a library can contain a set of functions for file transfers.</span></span> <span data-ttu-id="3c205-119">この場合、共通タスクを反映する名詞が "file" である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3c205-119">In this case, the noun reflecting the common task might be "file."</span></span>

### <a name="configuration"></a><span data-ttu-id="3c205-120">構成</span><span class="sxs-lookup"><span data-stu-id="3c205-120">Configuration</span></span>

<span data-ttu-id="3c205-121">モジュールを使用して、特定のコマンドレット、プロバイダー、関数、および変数を追加することによって環境をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="3c205-121">Modules can be used to customize your environment by adding specific cmdlets, providers, functions, and variables.</span></span>

### <a name="compiled-code-development-and-distribution"></a><span data-ttu-id="3c205-122">コンパイル済みのコードの開発と配布</span><span class="sxs-lookup"><span data-stu-id="3c205-122">Compiled Code Development and Distribution</span></span>

<span data-ttu-id="3c205-123">コマンドレットとプロバイダーの開発者は、モジュールを使用して、スナップインを作成しなくても、コンパイル済みのコードをテストおよび配布できます。これにより、スナップインの作成と登録を必要とせずに、コンパイルされたコードを含むアセンブリをモジュール (バイナリモジュール) としてインポートできます。</span><span class="sxs-lookup"><span data-stu-id="3c205-123">Cmdlet and provider developers can use modules to test and distribute their compiled code without needing to create snap-ins. They can import the assembly that contains the compiled code as a module (a binary module) without needing to create and register snap-ins.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c205-124">参照</span><span class="sxs-lookup"><span data-stu-id="3c205-124">See Also</span></span>

[<span data-ttu-id="3c205-125">Windows PowerShell モジュールを理解する</span><span class="sxs-lookup"><span data-stu-id="3c205-125">Understanding a Windows PowerShell Module</span></span>](./understanding-a-windows-powershell-module.md)

[<span data-ttu-id="3c205-126">PowerShell スクリプト モジュールを記述する方法</span><span class="sxs-lookup"><span data-stu-id="3c205-126">How to Write a PowerShell Script Module</span></span>](./how-to-write-a-powershell-script-module.md)

[<span data-ttu-id="3c205-127">PowerShell バイナリ モジュールを記述する方法</span><span class="sxs-lookup"><span data-stu-id="3c205-127">How to Write a PowerShell Binary Module</span></span>](./how-to-write-a-powershell-binary-module.md)

[<span data-ttu-id="3c205-128">PowerShell モジュール マニフェストを記述する方法</span><span class="sxs-lookup"><span data-stu-id="3c205-128">How to Write a PowerShell Module Manifest</span></span>](how-to-write-a-powershell-module-manifest.md)

[<span data-ttu-id="3c205-129">PSModulePath インストール パスを変更する</span><span class="sxs-lookup"><span data-stu-id="3c205-129">Modifying the PSModulePath Installation Path</span></span>](./modifying-the-psmodulepath-installation-path.md)

[<span data-ttu-id="3c205-130">PowerShell モジュールをインポートする</span><span class="sxs-lookup"><span data-stu-id="3c205-130">Importing a PowerShell Module</span></span>](./importing-a-powershell-module.md)

[<span data-ttu-id="3c205-131">PowerShell モジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="3c205-131">Installing a PowerShell Module</span></span>](./installing-a-powershell-module.md)
