---
title: Windows PowerShell モジュールの記述 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bfbccc5b-2b2b-432a-a971-9f8ab503cdc3
caps.latest.revision: 17
ms.openlocfilehash: 0b7263ea19745e902fff04b993933e443d4d6333
ms.sourcegitcommit: 58fb23c854f5a8b40ad1f952d3323aeeccac7a24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65229350"
---
# <a name="writing-a-windows-powershell-module"></a><span data-ttu-id="ca65e-102">Windows PowerShell モジュールを記述する</span><span class="sxs-lookup"><span data-stu-id="ca65e-102">Writing a Windows PowerShell Module</span></span>

<span data-ttu-id="ca65e-103">管理者、スクリプトの開発者、およびパッケージ化して、Windows PowerShell コマンドレットを配布する必要があるコマンドレットの開発者は、このドキュメントが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="ca65e-103">This document is written for administrators, script developers, and cmdlet developers who need to package and distribute their Windows PowerShell cmdlets.</span></span> <span data-ttu-id="ca65e-104">Windows PowerShell モジュールを使用すると、パッケージ化し、コンパイル済みの言語を使用せずに、Windows PowerShell のソリューションを配布できます。</span><span class="sxs-lookup"><span data-stu-id="ca65e-104">By using Windows PowerShell modules, you can package and distribute your Windows PowerShell solutions without using a compiled language.</span></span>

<span data-ttu-id="ca65e-105">Windows PowerShell モジュールは、パーティションに有効にする、整理、および再利用可能な自己完結型の単位に、Windows PowerShell コードを抽象化します。</span><span class="sxs-lookup"><span data-stu-id="ca65e-105">Windows PowerShell modules enable you to partition, organize, and abstract your Windows PowerShell code into self-contained, reusable units.</span></span> <span data-ttu-id="ca65e-106">これらの再利用可能なユニットでは、他のユーザーと直接モジュールを簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="ca65e-106">With these reusable units, you can easily share your modules directly with others.</span></span> <span data-ttu-id="ca65e-107">スクリプトを開発している場合、カスタムのスクリプト ベースのアプリケーションを作成するサード パーティ モジュールも再パッケージ化できます。</span><span class="sxs-lookup"><span data-stu-id="ca65e-107">If you are a script developer, you can also repackage third-party modules to create custom script-based applications.</span></span> <span data-ttu-id="ca65e-108">モジュール、Perl、Python などの他のスクリプト言語でモジュールのような再パッケージ化し、複数のコンポーネントが抽象化を有効にする追加の特典で再利用可能な再頒布可能パッケージのコンポーネントを使用する実稼働可能なスクリプト ソリューションを有効にします。カスタム ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ca65e-108">Modules, similar to modules in other scripting languages such as Perl and Python, enable production-ready scripting solutions that use reusable, redistributable components, with the added benefit of enabling you to repackage and abstract multiple components to create custom solutions.</span></span>

<span data-ttu-id="ca65e-109">その最も基本的な Windows PowerShell は、有効な Windows PowerShell スクリプト コードをモジュールとして .psm1 ファイルに保存を扱います。</span><span class="sxs-lookup"><span data-stu-id="ca65e-109">At their most basic, Windows PowerShell will treat any valid Windows PowerShell script code saved in a .psm1 file as a module.</span></span> <span data-ttu-id="ca65e-110">PowerShell では、モジュールとして任意のコマンドレットがバイナリ アセンブリも自動的に扱います。</span><span class="sxs-lookup"><span data-stu-id="ca65e-110">PowerShell will also automatically treat any binary cmdlet assembly as a module.</span></span> <span data-ttu-id="ca65e-111">ただし、ソリューション全体を一緒にバンドルするモジュール (またはより具体的には、モジュール マニフェスト) を使用することができますも。</span><span class="sxs-lookup"><span data-stu-id="ca65e-111">However, you can also use a module (or more specifically, a module manifest) to bundle an entire solution together.</span></span> <span data-ttu-id="ca65e-112">次のシナリオでは、Windows PowerShell モジュールの一般的な用途について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca65e-112">The following scenarios describe typical uses for Windows PowerShell modules.</span></span>

### <a name="libraries"></a><span data-ttu-id="ca65e-113">ライブラリ</span><span class="sxs-lookup"><span data-stu-id="ca65e-113">Libraries</span></span>

<span data-ttu-id="ca65e-114">パッケージ化し、一般的なタスクを実行する関数のまとまりのあるライブラリを配布するのには、モジュールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca65e-114">Modules can be used to package and distribute cohesive libraries of functions that perform common tasks.</span></span> <span data-ttu-id="ca65e-115">通常、これらの関数の名前は、それらに使用される一般的なタスクを反映した 1 つまたは複数の名詞を共有します。</span><span class="sxs-lookup"><span data-stu-id="ca65e-115">Typically, the names of these functions share one or more nouns that reflect the common task that they are used for.</span></span> <span data-ttu-id="ca65e-116">これらの関数はパブリックおよびプライベート メンバーを持つことで、.NET Framework のクラスに似ていますにも。</span><span class="sxs-lookup"><span data-stu-id="ca65e-116">These functions can also be similar to .NET Framework classes in that they can have public and private members.</span></span> <span data-ttu-id="ca65e-117">たとえば、ライブラリでは、ファイル転送の一連の関数を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ca65e-117">For example, a library can contain a set of functions for file transfers.</span></span> <span data-ttu-id="ca65e-118">この場合、一般的なタスクを反映した名詞は"file です"可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ca65e-118">In this case, the noun reflecting the common task might be "file."</span></span>

### <a name="configuration"></a><span data-ttu-id="ca65e-119">構成</span><span class="sxs-lookup"><span data-stu-id="ca65e-119">Configuration</span></span>

<span data-ttu-id="ca65e-120">特定のコマンドレット、プロバイダー、関数、および変数を追加して、環境をカスタマイズするモジュールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca65e-120">Modules can be used to customize your environment by adding specific cmdlets, providers, functions, and variables.</span></span>

### <a name="compiled-code-development-and-distribution"></a><span data-ttu-id="ca65e-121">コンパイル済みコードの開発と配布</span><span class="sxs-lookup"><span data-stu-id="ca65e-121">Compiled Code Development and Distribution</span></span>

<span data-ttu-id="ca65e-122">コマンドレットとプロバイダーの開発者は、テストして、スナップインを作成しなくても、コンパイル済みコードを配布するモジュールを使用できます。(バイナリ モジュール) をモジュールとしてコンパイルされたコードを含むアセンブリをインポート、作成し、スナップインを登録する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ca65e-122">Cmdlet and provider developers can use modules to test and distribute their compiled code without needing to create snap-ins. They can import the assembly that contains the compiled code as a module (a binary module) without needing to create and register snap-ins.</span></span>

## <a name="see-also"></a><span data-ttu-id="ca65e-123">参照</span><span class="sxs-lookup"><span data-stu-id="ca65e-123">See Also</span></span>

[<span data-ttu-id="ca65e-124">Windows PowerShell モジュールを理解します。</span><span class="sxs-lookup"><span data-stu-id="ca65e-124">Understanding a Windows PowerShell Module</span></span>](./understanding-a-windows-powershell-module.md)

[<span data-ttu-id="ca65e-125">PowerShell スクリプト モジュールを記述する方法</span><span class="sxs-lookup"><span data-stu-id="ca65e-125">How to Write a PowerShell Script Module</span></span>](./how-to-write-a-powershell-script-module.md)

[<span data-ttu-id="ca65e-126">PowerShell バイナリ モジュールを記述する方法</span><span class="sxs-lookup"><span data-stu-id="ca65e-126">How to Write a PowerShell Binary Module</span></span>](./how-to-write-a-powershell-binary-module.md)

[<span data-ttu-id="ca65e-127">PowerShell モジュールのマニフェストを作成する方法</span><span class="sxs-lookup"><span data-stu-id="ca65e-127">How to Write a PowerShell Module Manifest</span></span>](how-to-write-a-powershell-module-manifest.md)

[<span data-ttu-id="ca65e-128">PSModulePath インストール パスの変更</span><span class="sxs-lookup"><span data-stu-id="ca65e-128">Modifying the PSModulePath Installation Path</span></span>](./modifying-the-psmodulepath-installation-path.md)

[<span data-ttu-id="ca65e-129">PowerShell モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ca65e-129">Importing a PowerShell Module</span></span>](./importing-a-powershell-module.md)

[<span data-ttu-id="ca65e-130">PowerShell モジュールのインストール</span><span class="sxs-lookup"><span data-stu-id="ca65e-130">Installing a PowerShell Module</span></span>](./installing-a-powershell-module.md)
