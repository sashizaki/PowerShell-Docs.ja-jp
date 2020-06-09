---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: Windows PowerShell 用語集
ms.openlocfilehash: 1e2285bb49ed6a30fb5624ab3cf136cbf06401b5
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809198"
---
# <a name="windows-powershell-glossary"></a><span data-ttu-id="47b2d-103">Windows PowerShell 用語集</span><span class="sxs-lookup"><span data-stu-id="47b2d-103">Windows PowerShell Glossary</span></span>

|<span data-ttu-id="47b2d-104">期間</span><span class="sxs-lookup"><span data-stu-id="47b2d-104">Term</span></span>|<span data-ttu-id="47b2d-105">定義</span><span class="sxs-lookup"><span data-stu-id="47b2d-105">Definition</span></span>|
|--------|--------------|
|<span data-ttu-id="47b2d-106">バイナリ モジュール</span><span class="sxs-lookup"><span data-stu-id="47b2d-106">binary module</span></span>|<span data-ttu-id="47b2d-107">ルート モジュールがバイナリ モジュール ファイル (.dll) である Windows PowerShell モジュール。</span><span class="sxs-lookup"><span data-stu-id="47b2d-107">A Windows PowerShell module whose root module is a binary module file (.dll).</span></span> <span data-ttu-id="47b2d-108">バイナリ モジュールにはモジュール マニフェストが含まれる場合と、含まれない場合があります。</span><span class="sxs-lookup"><span data-stu-id="47b2d-108">A binary module may or may not include a module manifest.</span></span>|
|<span data-ttu-id="47b2d-109">共有パラメーター</span><span class="sxs-lookup"><span data-stu-id="47b2d-109">common parameter</span></span>|<span data-ttu-id="47b2d-110">Windows PowerShell エンジンによってすべてのコマンドレット、高度な関数、およびワークフローに追加されるパラメーター。</span><span class="sxs-lookup"><span data-stu-id="47b2d-110">A parameter that is added to all cmdlets, advanced functions, and workflows by the Windows PowerShell engine.</span></span>|
|<span data-ttu-id="47b2d-111">ドット ソース</span><span class="sxs-lookup"><span data-stu-id="47b2d-111">dot source</span></span>|<span data-ttu-id="47b2d-112">Windows PowerShell では、コマンドの前にドットとスペースを入力することによってコマンドを開始すること。</span><span class="sxs-lookup"><span data-stu-id="47b2d-112">In Windows PowerShell, to start a command by typing a dot and a space before the command.</span></span> <span data-ttu-id="47b2d-113">ドット ソースのコマンドは、新しいスコープではなく、現在のスコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="47b2d-113">Commands that are dot sourced run in the current scope instead of in a new scope.</span></span> <span data-ttu-id="47b2d-114">コマンドが作成するすべての変数、エイリアス、関数、またはドライブは、現在のスコープで作成され、コマンドが完了すると使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="47b2d-114">Any variables, aliases, functions, or drives that command creates are created in the current scope and are available to users when the command is completed.</span></span>|
|<span data-ttu-id="47b2d-115">動的モジュール</span><span class="sxs-lookup"><span data-stu-id="47b2d-115">dynamic module</span></span>|<span data-ttu-id="47b2d-116">メモリ内にのみ存在するモジュール。</span><span class="sxs-lookup"><span data-stu-id="47b2d-116">A module that exists only in memory.</span></span> <span data-ttu-id="47b2d-117">New-Module コマンドレットと Import-PSSession コマンドレットは動的モジュールを作成します。</span><span class="sxs-lookup"><span data-stu-id="47b2d-117">The New-Module and Import-PSSession cmdlets create dynamic modules.</span></span>|
|<span data-ttu-id="47b2d-118">動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="47b2d-118">dynamic parameter</span></span>|<span data-ttu-id="47b2d-119">Windows PowerShell コマンドレット、関数、または特定の条件下のスクリプトに追加されるパラメーター。</span><span class="sxs-lookup"><span data-stu-id="47b2d-119">A parameter that is added to a Windows PowerShell cmdlet, function, or script under certain conditions.</span></span> <span data-ttu-id="47b2d-120">コマンドレット、関数、プロバイダー、およびスクリプトは動的パラメーターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="47b2d-120">Cmdlets, functions, providers, and scripts can add dynamic parameters.</span></span>|
|<span data-ttu-id="47b2d-121">書式設定ファイル</span><span class="sxs-lookup"><span data-stu-id="47b2d-121">formatting file</span></span>|<span data-ttu-id="47b2d-122">拡張子が .format.ps1xml で、Windows PowerShell がどのように .NET Framework 型に基づいてオブジェクオを表示するかを定義する Windows PowerShell XML ファイル。</span><span class="sxs-lookup"><span data-stu-id="47b2d-122">A Windows PowerShell XML file that has the .format.ps1xml extension and that defines how Windows PowerShell displays an object based on its .NET Framework type.</span></span>|
|<span data-ttu-id="47b2d-123">グローバル セッション状態</span><span class="sxs-lookup"><span data-stu-id="47b2d-123">global session state</span></span>|<span data-ttu-id="47b2d-124">Windows PowerShell セッションのユーザーがアクセスできるデータを含むセッション状態。</span><span class="sxs-lookup"><span data-stu-id="47b2d-124">The session state that contains the data that is accessible to the user of a Windows PowerShell session.</span></span>|
|<span data-ttu-id="47b2d-125">host</span><span class="sxs-lookup"><span data-stu-id="47b2d-125">host</span></span>|<span data-ttu-id="47b2d-126">Windows PowerShell エンジンがユーザーとの通信に使用するインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="47b2d-126">The interface that the Windows PowerShell engine uses to communicate with the user.</span></span> <span data-ttu-id="47b2d-127">たとえば、ホストは Windows PowerShell とユーザー間でプロンプトが処理される方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="47b2d-127">For example, the host specifies how prompts are handled between Windows PowerShell and the user.</span></span>|
|<span data-ttu-id="47b2d-128">ホスト アプリケーション</span><span class="sxs-lookup"><span data-stu-id="47b2d-128">host application</span></span>|<span data-ttu-id="47b2d-129">Windows PowerShell エンジンをそのプロセスに読み込み、操作を実行するのに使用するプログラム。</span><span class="sxs-lookup"><span data-stu-id="47b2d-129">A program that loads the Windows PowerShell engine into its process and uses it to perform operations.</span></span>|
|<span data-ttu-id="47b2d-130">入力処理メソッド</span><span class="sxs-lookup"><span data-stu-id="47b2d-130">input processing method</span></span>|<span data-ttu-id="47b2d-131">コマンドが入力として受信するレコードを処理するのに使用できるメソッド。</span><span class="sxs-lookup"><span data-stu-id="47b2d-131">A method that a cmdlet can use to process the records it receives as input.</span></span> <span data-ttu-id="47b2d-132">入力処理メソッドには、BeginProcessing メソッド、ProcessRecord メソッド、EndProcessing メソッド、および StopProcessing メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="47b2d-132">The input processing methods include the BeginProcessing method, the ProcessRecord method, the EndProcessing method, and the StopProcessing method.</span></span>|
|<span data-ttu-id="47b2d-133">マニフェスト モジュール</span><span class="sxs-lookup"><span data-stu-id="47b2d-133">manifest module</span></span>|<span data-ttu-id="47b2d-134">マニフェストがあり、RootModule キーが空の Windows PowerShell モジュール。</span><span class="sxs-lookup"><span data-stu-id="47b2d-134">A Windows PowerShell module that has a manifest and whose RootModule key is empty.</span></span>|
|<span data-ttu-id="47b2d-135">モジュール マニフェスト</span><span class="sxs-lookup"><span data-stu-id="47b2d-135">module manifest</span></span>|<span data-ttu-id="47b2d-136">モジュールのコンテンツを説明し、モジュールが処理される方法を制御する Windows PowerShell データ ファイル (.psd1)。</span><span class="sxs-lookup"><span data-stu-id="47b2d-136">A Windows PowerShell data file (.psd1) that describes the contents of a module and that controls how a module is processed.</span></span>|
|<span data-ttu-id="47b2d-137">モジュール セッション状態</span><span class="sxs-lookup"><span data-stu-id="47b2d-137">module session state</span></span>|<span data-ttu-id="47b2d-138">Windows PowerShell モジュールのパブリック データとプライベート データを含むセッション状態。</span><span class="sxs-lookup"><span data-stu-id="47b2d-138">The session state that contains the public and private data of a Windows PowerShell module.</span></span> <span data-ttu-id="47b2d-139">このセッション状態のプライベート データは、Windows PowerShell セッションのユーザーは使用できません。</span><span class="sxs-lookup"><span data-stu-id="47b2d-139">The private data in this session state is not available to the user of a Windows PowerShell session.</span></span>|
|<span data-ttu-id="47b2d-140">終了しないエラー</span><span class="sxs-lookup"><span data-stu-id="47b2d-140">non-terminating error</span></span>|<span data-ttu-id="47b2d-141">Windows PowerShell でのコマンドの処理の継続が停止しないエラー。</span><span class="sxs-lookup"><span data-stu-id="47b2d-141">An error that does not stop Windows PowerShell from continuing to process the command.</span></span>|
|<span data-ttu-id="47b2d-142">名詞</span><span class="sxs-lookup"><span data-stu-id="47b2d-142">noun</span></span>|<span data-ttu-id="47b2d-143">Windows PowerShell コマンドレット名でハイフンの後に続く単語。</span><span class="sxs-lookup"><span data-stu-id="47b2d-143">The word that follows the hyphen in a Windows PowerShell cmdlet name.</span></span> <span data-ttu-id="47b2d-144">名詞は、コマンドレットの処理対象のリソースを説明します。</span><span class="sxs-lookup"><span data-stu-id="47b2d-144">The noun describes the resources upon which the cmdlet acts.</span></span>|
|<span data-ttu-id="47b2d-145">パラメーター セット</span><span class="sxs-lookup"><span data-stu-id="47b2d-145">parameter set</span></span>|<span data-ttu-id="47b2d-146">特定のアクションを実行するために同じコマンドで使用できるパラメーターのグループ。</span><span class="sxs-lookup"><span data-stu-id="47b2d-146">A group of parameters that can be used in the same command to perform a specific action.</span></span>|
|<span data-ttu-id="47b2d-147">パイプ</span><span class="sxs-lookup"><span data-stu-id="47b2d-147">pipe</span></span>|<span data-ttu-id="47b2d-148">Windows PowerShell で、前のコマンドの結果を、入力としてパイプラインの次のコマンドに送信するためのもの。</span><span class="sxs-lookup"><span data-stu-id="47b2d-148">In Windows PowerShell, to send the results of the preceding command as input to the next command in the pipeline.</span></span>|
|<span data-ttu-id="47b2d-149">pipeline</span><span class="sxs-lookup"><span data-stu-id="47b2d-149">pipeline</span></span>|<span data-ttu-id="47b2d-150">パイプライン演算子 (&#124;) (ASCII 124) によって接続された一連のコマンド。</span><span class="sxs-lookup"><span data-stu-id="47b2d-150">A series of commands connected by pipeline operators (&#124;) (ASCII 124).</span></span> <span data-ttu-id="47b2d-151">各パイプライン演算子は、前のコマンドの結果を入力として次のコマンドに送信します。</span><span class="sxs-lookup"><span data-stu-id="47b2d-151">Each pipeline operator sends the results of the preceding command as input to the next command.</span></span>|
|<span data-ttu-id="47b2d-152">PSSession</span><span class="sxs-lookup"><span data-stu-id="47b2d-152">PSSession</span></span>|<span data-ttu-id="47b2d-153">ユーザーによって作成され、管理され、閉じられる Windows PowerShell セッションの一種。</span><span class="sxs-lookup"><span data-stu-id="47b2d-153">A type of Windows PowerShell session that is created, managed, and closed by the user.</span></span>|
|<span data-ttu-id="47b2d-154">ルート モジュール</span><span class="sxs-lookup"><span data-stu-id="47b2d-154">root module</span></span>|<span data-ttu-id="47b2d-155">モジュール マニフェスト内の RootModule キーで指定されたモジュール。</span><span class="sxs-lookup"><span data-stu-id="47b2d-155">The module specified in the RootModule key in a module manifest.</span></span>|
|<span data-ttu-id="47b2d-156">実行空間</span><span class="sxs-lookup"><span data-stu-id="47b2d-156">runspace</span></span>|<span data-ttu-id="47b2d-157">Windows PowerShell で、パイプラン内の各コマンドが実行される操作環境。</span><span class="sxs-lookup"><span data-stu-id="47b2d-157">In Windows PowerShell, the operating environment in which each command in a pipeline is executed.</span></span>|
|<span data-ttu-id="47b2d-158">スクリプト ブロック</span><span class="sxs-lookup"><span data-stu-id="47b2d-158">script block</span></span>|<span data-ttu-id="47b2d-159">Windows PowerShell プログラミング言語で、1 つの単位として使用できるステートメントまたは表現のコレクション。</span><span class="sxs-lookup"><span data-stu-id="47b2d-159">In the Windows PowerShell programming language, a collection of statements or expressions that can be used as a single unit.</span></span> <span data-ttu-id="47b2d-160">スクリプト ブロックは引数を受け取り、値を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="47b2d-160">A script block can accept arguments and return values.</span></span>|
|<span data-ttu-id="47b2d-161">スクリプト モジュール</span><span class="sxs-lookup"><span data-stu-id="47b2d-161">script module</span></span>|<span data-ttu-id="47b2d-162">ルート モジュールがスクリプト モジュール ファイル (.psm1) である Windows PowerShell モジュール。</span><span class="sxs-lookup"><span data-stu-id="47b2d-162">A Windows PowerShell module whose root module is a script module file (.psm1).</span></span> <span data-ttu-id="47b2d-163">スクリプト モジュールにはモジュール マニフェストが含まれる場合と、含まれない場合があります。</span><span class="sxs-lookup"><span data-stu-id="47b2d-163">A script module may or may not include a module manifest.</span></span>|
|<span data-ttu-id="47b2d-164">スクリプト モジュール ファイル</span><span class="sxs-lookup"><span data-stu-id="47b2d-164">script module file</span></span>|<span data-ttu-id="47b2d-165">Windows PowerShell スクリプトを含むファイル。</span><span class="sxs-lookup"><span data-stu-id="47b2d-165">A file that contains a Windows PowerShell script.</span></span> <span data-ttu-id="47b2d-166">スクリプトは、スクリプト モジュールがエクスポートするメンバーを定義します。</span><span class="sxs-lookup"><span data-stu-id="47b2d-166">The script defines the members that the script module exports.</span></span> <span data-ttu-id="47b2d-167">スクリプト モジュール ファイルのファイル名拡張子は .psm1 です。</span><span class="sxs-lookup"><span data-stu-id="47b2d-167">Script module files have the .psm1 file name extension.</span></span>|
|<span data-ttu-id="47b2d-168">シェル</span><span class="sxs-lookup"><span data-stu-id="47b2d-168">shell</span></span>|<span data-ttu-id="47b2d-169">コマンドをオペレーティング システムに渡すのに使用されるコマンド インタープリター。</span><span class="sxs-lookup"><span data-stu-id="47b2d-169">The command interpreter that is used to pass commands to the operating system.</span></span>|
|<span data-ttu-id="47b2d-170">スイッチ パラメーター</span><span class="sxs-lookup"><span data-stu-id="47b2d-170">switch parameter</span></span>|<span data-ttu-id="47b2d-171">引数を受け取らないパラメーター。</span><span class="sxs-lookup"><span data-stu-id="47b2d-171">A parameter that does not take an argument.</span></span>|
|<span data-ttu-id="47b2d-172">終了エラー</span><span class="sxs-lookup"><span data-stu-id="47b2d-172">terminating error</span></span>|<span data-ttu-id="47b2d-173">Windows PowerShell でのコマンドの処理を停止するエラー。</span><span class="sxs-lookup"><span data-stu-id="47b2d-173">An error that stops Windows PowerShell from processing the command.</span></span>|
|<span data-ttu-id="47b2d-174">transaction</span><span class="sxs-lookup"><span data-stu-id="47b2d-174">transaction</span></span>|<span data-ttu-id="47b2d-175">作業のアトミック単位。</span><span class="sxs-lookup"><span data-stu-id="47b2d-175">An atomic unit of work.</span></span> <span data-ttu-id="47b2d-176">トランザクションでの作業は全体として完了する必要があります。トランザクションの一部が失敗すると、トランザクション全体が失敗します。</span><span class="sxs-lookup"><span data-stu-id="47b2d-176">The work in a transaction must be completed as a whole; if any part of the transaction fails, the entire transaction fails.</span></span>|
|<span data-ttu-id="47b2d-177">型ファイル</span><span class="sxs-lookup"><span data-stu-id="47b2d-177">types file</span></span>|<span data-ttu-id="47b2d-178">拡張子が .ps1xml で、Microsoft .NET Framework 型のプロパティを Windows PowerShell で拡張する Windows PowerShell XML ファイル。</span><span class="sxs-lookup"><span data-stu-id="47b2d-178">A Windows PowerShell XML file that has the .ps1xml extension and that extends the properties of Microsoft .NET Framework types in Windows PowerShell.</span></span>|
|<span data-ttu-id="47b2d-179">Verb</span><span class="sxs-lookup"><span data-stu-id="47b2d-179">verb</span></span>|<span data-ttu-id="47b2d-180">Windows PowerShell コマンドレット名でハイフンの前に使用される単語。</span><span class="sxs-lookup"><span data-stu-id="47b2d-180">The word that precedes the hyphen in a Windows PowerShell cmdlet  name.</span></span> <span data-ttu-id="47b2d-181">動詞はコマンドレットが実行するアクションを説明します。</span><span class="sxs-lookup"><span data-stu-id="47b2d-181">The verb describes the action that the cmdlet performs.</span></span>|
|<span data-ttu-id="47b2d-182">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="47b2d-182">Windows PowerShell</span></span>|<span data-ttu-id="47b2d-183">IT 管理者に包括的な制御とシステム管理タスクの自動化を提供するコマンド ライン シェルとタスク ベースのスクリプト技術。</span><span class="sxs-lookup"><span data-stu-id="47b2d-183">A command-line shell and task-based scripting technology that provides IT administrators comprehensive control and automation of system administration tasks.</span></span>|
|<span data-ttu-id="47b2d-184">Windows PowerShell コマンド</span><span class="sxs-lookup"><span data-stu-id="47b2d-184">Windows PowerShell command</span></span>|<span data-ttu-id="47b2d-185">アクションを実行させるパイプライン内の要素。Windows PowerShell コマンドは、キーボードで入力されるか、プログラムで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="47b2d-185">The elements in a pipeline that cause an action to be carried out. Windows PowerShell commands are either typed at the keyboard or invoked programmatically.</span></span>|
|<span data-ttu-id="47b2d-186">Windows PowerShell データ ファイル</span><span class="sxs-lookup"><span data-stu-id="47b2d-186">Windows PowerShell data file</span></span>|<span data-ttu-id="47b2d-187">.psd1 ファイル名拡張子を持つテキスト ファイル。</span><span class="sxs-lookup"><span data-stu-id="47b2d-187">A text file that has the .psd1 file name extension.</span></span> <span data-ttu-id="47b2d-188">Windows PowerShell では、モジュール マニフェスト データの格納や、スクリプトの国際化のための翻訳された文字列の格納など、さまざまな目的でデータ ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="47b2d-188">Windows PowerShell uses data files for various purposes such as storing module manifest data and storing translated strings for script internationalization.</span></span>|
|<span data-ttu-id="47b2d-189">Windows PowerShell ドライブ</span><span class="sxs-lookup"><span data-stu-id="47b2d-189">Windows PowerShell drive</span></span>|<span data-ttu-id="47b2d-190">データ ストアに直接アクセスできる仮想ドライブ。</span><span class="sxs-lookup"><span data-stu-id="47b2d-190">A virtual drive that provides direct access to a data store.</span></span> <span data-ttu-id="47b2d-191">Windows PowerShell プロバイダーによって定義されるか、コマンド ラインで作成されます。</span><span class="sxs-lookup"><span data-stu-id="47b2d-191">It can be defined by a Windows PowerShell provider or created at the command line.</span></span> <span data-ttu-id="47b2d-192">コマンド ラインで作成されたドライブは、セッション固有のドライブであり、セッションが閉じられたときに失われます。</span><span class="sxs-lookup"><span data-stu-id="47b2d-192">Drives created at the command line are session-specific drives and are lost when the session is closed.</span></span>|
|<span data-ttu-id="47b2d-193">Windows PowerShell Integrated Scripting Environment (ISE)</span><span class="sxs-lookup"><span data-stu-id="47b2d-193">Windows PowerShell Integrated Scripting Environment (ISE)</span></span>|<span data-ttu-id="47b2d-194">Windows PowerShell ホスト アプリケーション。分かりやすくて、構文がカラーで表記された、ユニコード準拠の環境で、コマンドを実行し、スクリプトを書き、テストし、デバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="47b2d-194">A Windows PowerShell host application that enables you to run commands and to write, test, and debug scripts in a friendly, syntax-colored, Unicode-compliant environment.</span></span>|
|<span data-ttu-id="47b2d-195">Windows PowerShell モジュール</span><span class="sxs-lookup"><span data-stu-id="47b2d-195">Windows PowerShell module</span></span>|<span data-ttu-id="47b2d-196">Windows PowerShell コードをパーティション分割、整理、抽象化するための再利用可能な自己完結型の単位。</span><span class="sxs-lookup"><span data-stu-id="47b2d-196">A self-contained reusable unit that allows you to partition, organize, and abstract your Windows PowerShell  code.</span></span> <span data-ttu-id="47b2d-197">モジュールには、1 つの単位としてインポートできるコマンドレット、プロバイダー、関数、変数、その他の種類のリソースを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="47b2d-197">A module can contain cmdlets, providers, functions, variables, and other types of resources that can be imported as a single unit.</span></span>|
|<span data-ttu-id="47b2d-198">Windows PowerShell プロバイダー</span><span class="sxs-lookup"><span data-stu-id="47b2d-198">Windows PowerShell provider</span></span>|<span data-ttu-id="47b2d-199">特化されたデータ ストアのデータを Windows PowerShell で利用できるようにし、そのデータを表示および管理できるようにするための Microsoft .NET Framework ベースのプログラム。</span><span class="sxs-lookup"><span data-stu-id="47b2d-199">A Microsoft .NET Framework-based program that makes the data in a specialized data store available in Windows PowerShell so that you can view and manage it.</span></span>|
|<span data-ttu-id="47b2d-200">Windows PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="47b2d-200">Windows PowerShell script</span></span>|<span data-ttu-id="47b2d-201">Windows PowerShell 言語で記述されたスクリプト。</span><span class="sxs-lookup"><span data-stu-id="47b2d-201">A script that is written in the Windows PowerShell language.</span></span>|
|<span data-ttu-id="47b2d-202">Windows PowerShell スクリプト ファイル</span><span class="sxs-lookup"><span data-stu-id="47b2d-202">Windows PowerShell script file</span></span>|<span data-ttu-id="47b2d-203">.ps1 拡張子を持ち、Windows PowerShell 言語で記述されたスクリプトを含むファイル。</span><span class="sxs-lookup"><span data-stu-id="47b2d-203">A file that has the .ps1 extension and that contains a script that is written in the Windows PowerShell language.</span></span>|
|<span data-ttu-id="47b2d-204">Windows PowerShell スナップイン</span><span class="sxs-lookup"><span data-stu-id="47b2d-204">Windows PowerShell snap-in</span></span>|<span data-ttu-id="47b2d-205">Windows PowerShell 環境に追加できるコマンドレット、プロバイダー、および Microsoft .NET Framework の型のセットを定義するリソース。</span><span class="sxs-lookup"><span data-stu-id="47b2d-205">A resource that defines a set of cmdlets, providers, and Microsoft .NET Framework types that can be added to the Windows PowerShell environment.</span></span>|
|<span data-ttu-id="47b2d-206">Windows PowerShell ワークフロー</span><span class="sxs-lookup"><span data-stu-id="47b2d-206">Windows PowerShell Workflow</span></span>|<span data-ttu-id="47b2d-207">A workflow is a sequence of programmed, connected steps that perform long-running tasks or require the coordination of multiple steps across multiple devices or managed nodes.</span><span class="sxs-lookup"><span data-stu-id="47b2d-207">A workflow is a sequence of programmed, connected steps that perform long-running tasks or require the coordination of multiple steps across multiple devices or managed nodes.</span></span> <span data-ttu-id="47b2d-208">Windows PowerShell ワークフローを使用することで、IT 担当者や開発者は、マルチデバイス管理アクティビティのシーケンス (ワークフロー内の 1 つのタスク) をワークフローとして作成できます。</span><span class="sxs-lookup"><span data-stu-id="47b2d-208">Windows PowerShell Workflow lets IT pros and developers author sequences of multi-device management activities, or single tasks within a workflow, as workflows.</span></span> <span data-ttu-id="47b2d-209">Windows PowerShell ワークフローを使用すると、Windows PowerShell スクリプトと XAML ファイルの両方をワークフローとして適応し実行できます。</span><span class="sxs-lookup"><span data-stu-id="47b2d-209">Windows PowerShell Workflow lets you adapt and run both Windows PowerShell scripts and XAML files as workflows.</span></span>|