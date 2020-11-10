---
description: Windows PowerShell Integrated Scripting Environment (ISE) の機能とシステム要件について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_powershell_ise?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_PowerShell_ISE
ms.openlocfilehash: ff543024d7c62c70217eeaf3ded192a5a24c4757
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388843"
---
# <a name="about-windows-powershell-ise"></a><span data-ttu-id="8ed96-104">Windows PowerShell ISE について</span><span class="sxs-lookup"><span data-stu-id="8ed96-104">About Windows PowerShell ISE</span></span>

## <a name="short-description"></a><span data-ttu-id="8ed96-105">概要</span><span class="sxs-lookup"><span data-stu-id="8ed96-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="8ed96-106">Windows PowerShell Integrated Scripting Environment (ISE) の機能とシステム要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="8ed96-106">Describes the features and system requirements of Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="long-description"></a><span data-ttu-id="8ed96-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="8ed96-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="8ed96-108">Windows PowerShell ISE は、Windows PowerShell 用のグラフィカルホストアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="8ed96-108">Windows PowerShell ISE is a graphical host application for Windows PowerShell.</span></span>
<span data-ttu-id="8ed96-109">Windows PowerShell ISE では、1つの Windows ベースのグラフィカルユーザーインターフェイスでコマンドを実行し、スクリプトの記述、テスト、およびデバッグを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-109">In Windows PowerShell ISE, you can run commands and write, test, and debug scripts in a single Windows-based graphical user interface.</span></span> <span data-ttu-id="8ed96-110">その機能には、Intellisense、複数行の編集、タブ補完、自動保存、構文の色分け、選択的な実行、状況依存のヘルプ、コマンドの表示 (ウィンドウでのコマンドの作成)、2バイト文字セットと右から左へ記述する言語のサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-110">Its features include Intellisense, multiline editing, tab completion, auto-save, syntax coloring, selective execution, context-sensitive help, Show Command (compose commands in a window) and support for double-byte character sets and right-to-left languages.</span></span>

<span data-ttu-id="8ed96-111">Windows PowerShell ISE は初心者向けの優れたツールです。</span><span class="sxs-lookup"><span data-stu-id="8ed96-111">Windows PowerShell ISE is an excellent tool for beginners.</span></span> <span data-ttu-id="8ed96-112">[コマンドウィンドウと新しいリモート PowerShell の表示] タブでは、最初の試行を成功させるためのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-112">The Show Command window and New Remote PowerShell Tab guide you through tasks so that you can be successful on the first try.</span></span> <span data-ttu-id="8ed96-113">スニペットとエラーインジケーターは、作業中に Windows PowerShell 言語を学習するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-113">Snippets and error indicators help you learn the Windows PowerShell language as you work.</span></span>

<span data-ttu-id="8ed96-114">上級ユーザーは、洗練されたデバッグ機能、アドオン、および Windows PowerShell ISE オブジェクトモデルを利用できます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-114">Advanced users can take advantage of the sophisticated debugging features, add-ons, and the Windows PowerShell ISE object model.</span></span>

<span data-ttu-id="8ed96-115">Windows PowerShell 4.0 での Windows PowerShell ISE の新機能</span><span class="sxs-lookup"><span data-stu-id="8ed96-115">What's New in Windows PowerShell ISE in Windows PowerShell 4.0</span></span>

<span data-ttu-id="8ed96-116">Windows PowerShell ISE には、Windows PowerShell 4.0 の2つの新機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="8ed96-116">Windows PowerShell ISE introduces two new features in Windows PowerShell 4.0.</span></span>

- <span data-ttu-id="8ed96-117">Windows PowerShell ISE で、Windows PowerShell ワークフローデバッグとリモートスクリプトデバッグの両方がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="8ed96-117">Windows PowerShell ISE now supports both Windows PowerShell Workflow debugging and remote script debugging.</span></span> <span data-ttu-id="8ed96-118">詳細については、「about_Debuggers」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ed96-118">For more Information, see about_Debuggers.</span></span>

- <span data-ttu-id="8ed96-119">Windows PowerShell Desired State Configuration のプロバイダーおよび構成に IntelliSense サポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="8ed96-119">IntelliSense support has been added for Windows PowerShell Desired State Configuration providers and configurations.</span></span>

## <a name="starting-windows-powershell-ise"></a><span data-ttu-id="8ed96-120">Windows PowerShell ISE の開始</span><span class="sxs-lookup"><span data-stu-id="8ed96-120">Starting Windows PowerShell ISE</span></span>

<span data-ttu-id="8ed96-121">サポートされているすべてのバージョンの Windows で、Windows PowerShell ISE がインストールされ、有効になっており、使用準備ができています。</span><span class="sxs-lookup"><span data-stu-id="8ed96-121">Windows PowerShell ISE is installed, enabled, and ready to use in all supported versions of Windows.</span></span>

- <span data-ttu-id="8ed96-122">Windows 8.1、Windows 8、Windows Server 2012 R2、および Windows Server 2012 では、スタート画面で「PowerShell_ISE」と入力し、[PowerShell_ISE] または [Windows PowerShell ISE] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ed96-122">In Windows 8.1, Windows 8, Windows Server 2012 R2, and Windows Server 2012, on the Start screen, type PowerShell_ISE, and then click PowerShell_ISE or Windows PowerShell ISE.</span></span>

- <span data-ttu-id="8ed96-123">Windows Server 2012 R2 および Windows Server 2012 のサーバーマネージャーで、[ツール] メニューの [Windows PowerShell ISE] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ed96-123">In Windows Server 2012 R2 and Windows Server 2012, in Server Manager, on the Tools menu, click Windows PowerShell ISE.</span></span>

- <span data-ttu-id="8ed96-124">以前のバージョンの Windows では、[スタート]、[すべてのプログラム]、[アクセサリ]、[Windows PowerShell] の順にクリックし、[Windows PowerShell ISE] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ed96-124">In earlier versions of Windows, click Start, All Programs, Accessories, Windows PowerShell, and then click Windows PowerShell ISE.</span></span>

- <span data-ttu-id="8ed96-125">Windows PowerShell コンソール、Cmd.exe、または Windows の [実行] または [検索] ボックスに「PowerShell_ise.exe」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8ed96-125">In a Windows PowerShell console, Cmd.exe, or the Run or Search box in Windows, type "PowerShell_ise.exe".</span></span> <span data-ttu-id="8ed96-126">NoProfile スイッチなどのコマンドラインパラメーターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-126">You can also use the command-line parameters, including the NoProfile switch.</span></span> <span data-ttu-id="8ed96-127">詳細については、 [PowerShell_ISE.exe コンソールのヘルプ](about_powershell_ise_exe.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ed96-127">For more information, see [PowerShell_ISE.exe Console Help](about_powershell_ise_exe.md).</span></span>

## <a name="running-interactive-commands"></a><span data-ttu-id="8ed96-128">対話型コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="8ed96-128">Running Interactive Commands</span></span>

<span data-ttu-id="8ed96-129">Windows PowerShell ISE では、任意の Windows PowerShell 式またはコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-129">You can run any Windows PowerShell expression or command in Windows PowerShell ISE.</span></span> <span data-ttu-id="8ed96-130">Windows PowerShell コンソールで使用するのと同じように、コマンドレット、プロバイダー、スナップイン、およびモジュールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-130">You can use cmdlets, providers, snap-ins, and modules as you would use them in the Windows PowerShell console.</span></span>

<span data-ttu-id="8ed96-131">対話型コマンドは、コンソールウィンドウで入力または貼り付けできます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-131">You can type or paste interactive commands in the Console pane.</span></span> <span data-ttu-id="8ed96-132">コマンドを実行するには、ボタン、メニュー項目、およびキーボードショートカットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8ed96-132">To run the commands, you can use buttons, menu items, and keyboard shortcuts.</span></span>

<span data-ttu-id="8ed96-133">複数行編集機能を使用すると、複数行のコードを一度に入力するか、コンソールウィンドウに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-133">You can use the multiline editing feature to type or paste several lines of code into the Console pane at once.</span></span> <span data-ttu-id="8ed96-134">上方向キーを押して前のコマンドを再実行すると、コマンド内のすべての行が再呼び出しされます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-134">When you press the UP ARROW key to recall the previous command, all the lines in the command are recalled.</span></span> <span data-ttu-id="8ed96-135">コマンドを入力するときに、SHIFT + ENTER キーを押すと、新しい空白行が現在の行に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-135">When you type commands, press SHIFT+ENTER to make a new blank line appear under the current line.</span></span>

## <a name="viewing-output"></a><span data-ttu-id="8ed96-136">出力の表示</span><span class="sxs-lookup"><span data-stu-id="8ed96-136">Viewing Output</span></span>

<span data-ttu-id="8ed96-137">コマンドおよびスクリプトの結果がコンソールウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-137">The results of commands and scripts are displayed in the Console pane.</span></span> <span data-ttu-id="8ed96-138">コンソールウィンドウで、キーボードショートカットまたはツールバーの [コピー] ボタンを使用して、結果を移動またはコピーできます。また、結果をスクリプトウィンドウまたはコンソールウィンドウまたはその他のプログラムに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-138">You can move or copy the results from the Console pane by using keyboard shortcuts or the Copy button on the toolbar, and you can paste the results in the Script pane or Console panes or other programs.</span></span> <span data-ttu-id="8ed96-139">コンソールウィンドウをクリアするには、[出力ウィンドウのクリア] ボタンをクリックするか、次のいずれかのコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="8ed96-139">To clear the Console pane, click the "Clear Output Pane" button or type one of the following commands:</span></span>

```
Clear-Host
cls
```

## <a name="writing-scripts-and-functions"></a><span data-ttu-id="8ed96-140">スクリプトと関数の記述</span><span class="sxs-lookup"><span data-stu-id="8ed96-140">Writing Scripts and Functions</span></span>

<span data-ttu-id="8ed96-141">スクリプトウィンドウでは、スクリプトのオープン、作成、編集、および実行を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-141">In the Script pane, you can open, compose, edit, and run scripts.</span></span> <span data-ttu-id="8ed96-142">スクリプトウィンドウでは、ボタンとキーボードショートカットを使用してスクリプトを編集できます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-142">The Script pane lets you edit scripts by using buttons and keyboard shortcuts.</span></span> <span data-ttu-id="8ed96-143">スクリプトウィンドウとコンソールウィンドウの間でテキストをコピー、切り取り、貼り付けすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-143">You can also copy, cut, and paste text between the Script pane and the Console pane.</span></span>

<span data-ttu-id="8ed96-144">選択的実行機能を使用すると、スクリプトの全部または一部を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-144">You can use the selective run feature to run all or part of a script.</span></span> <span data-ttu-id="8ed96-145">スクリプトの一部を実行するには、実行するテキストを選択し、[選択項目の実行] ボタンをクリックするか、F8 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8ed96-145">To run part of a script, select the text you want to run, and then click the Run Selection button or press F8.</span></span> <span data-ttu-id="8ed96-146">既定では、F8 は現在の行を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ed96-146">By default, F8 runs the current line.</span></span>

<span data-ttu-id="8ed96-147">高度な編集機能には、かっこ一致、展開/折りたたみ、行番号、エラーインジケーター、ブロック編集とインデント、リッチコピー、および大文字小文字の変換が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-147">Advanced editing features include brace-matching, expand-collapse, line numbers, error indicators, block editing and indenting, rich copy, and case conversion.</span></span>

## <a name="getting-help"></a><span data-ttu-id="8ed96-148">ヘルプ情報の入手</span><span class="sxs-lookup"><span data-stu-id="8ed96-148">Getting Help</span></span>

<span data-ttu-id="8ed96-149">Windows PowerShell ISE には、その使用方法を説明するヘルプトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8ed96-149">Windows PowerShell ISE includes help topics that describe its use.</span></span> <span data-ttu-id="8ed96-150">また、インストールされているすべてのヘルプファイルには、[スクリプト] ウィンドウと [コマンド] ペインからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-150">In addition, all installed help files are accessible from the Script and Command panes.</span></span>

<span data-ttu-id="8ed96-151">Windows PowerShell ISE は、状況依存のヘルプもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8ed96-151">Windows PowerShell ISE also supports context-sensitive help.</span></span> <span data-ttu-id="8ed96-152">特定のコマンドレット、プロバイダー、またはキーワードに関するヘルプを表示するには、項目の名前にカーソルを置き、F1 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8ed96-152">To get help about a particular cmdlet, provider, or keyword, place the cursor in the name of the item and press F1.</span></span> <span data-ttu-id="8ed96-153">ヘルプトピックを検索するには、F1 キーを押して検索語句を入力します。</span><span class="sxs-lookup"><span data-stu-id="8ed96-153">To search the help topics, press F1 and type the search term.</span></span>

<span data-ttu-id="8ed96-154">コンピューターのヘルプトピックを更新するには、[ヘルプ] メニューの [Windows PowerShell の更新] ヘルプ項目を使用します。</span><span class="sxs-lookup"><span data-stu-id="8ed96-154">To update the help topics on the computer, use the Update Windows PowerShell Help item in the Help menu.</span></span> <span data-ttu-id="8ed96-155">この項目は、現在の UI カルチャで現在のセッションにあるモジュールのヘルプを更新します。</span><span class="sxs-lookup"><span data-stu-id="8ed96-155">This item updates help for the modules in the current session in the current UI culture.</span></span> <span data-ttu-id="8ed96-156">これは、パラメーターを指定せずに Update-Help コマンドレットを実行することと同じです。</span><span class="sxs-lookup"><span data-stu-id="8ed96-156">It is equivalent to running the Update-Help cmdlet without parameters.</span></span> <span data-ttu-id="8ed96-157">Windows PowerShell に付属するコマンドレットのヘルプを更新するには、[管理者として実行] オプションを使用して Windows PowerShell ISE を開始します。</span><span class="sxs-lookup"><span data-stu-id="8ed96-157">To update help for the cmdlets that come with Windows PowerShell, start Windows PowerShell ISE with the "Run as administrator" option.</span></span>

<span data-ttu-id="8ed96-158">Windows PowerShell コンソールで使用する場合と同様に、Windows PowerShell ISE で Get-help、Save Help、および Update-Help コマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-158">You can also use the Get-Help, Save-Help, and Update-Help cmdlets in Windows PowerShell ISE, just as you use it in the Windows PowerShell console.</span></span> <span data-ttu-id="8ed96-159">ただし、Windows PowerShell ISE では、ヘルプ関数は、一度に1ページではなく、ヘルプトピック全体を表示します。</span><span class="sxs-lookup"><span data-stu-id="8ed96-159">However, in Windows PowerShell ISE, the Help function displays the entire help topic, not one page at a time.</span></span>

## <a name="debugging-scripts"></a><span data-ttu-id="8ed96-160">スクリプトのデバッグ</span><span class="sxs-lookup"><span data-stu-id="8ed96-160">Debugging Scripts</span></span>

<span data-ttu-id="8ed96-161">Windows PowerShell ISE デバッガーを使用して、Windows PowerShell スクリプトまたは関数をデバッグすることができます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-161">You can use the Windows PowerShell ISE debugger to debug a Windows PowerShell script or function.</span></span> <span data-ttu-id="8ed96-162">スクリプトをデバッグするときに、メニュー項目とショートカットキーを使用して、Windows PowerShell コンソールで実行するのと同じタスクの多くを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-162">When you debug a script, you can use menu items and shortcut keys to perform many of the same tasks that you would perform in the Windows PowerShell console.</span></span> <span data-ttu-id="8ed96-163">たとえば、スクリプトに行のブレークポイントを設定するには、コード行を右クリックし、[ブレークポイントの設定/解除] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ed96-163">For example, to set a line breakpoint in a script, right-click the line of code, and then click Toggle Breakpoint.</span></span>

<span data-ttu-id="8ed96-164">デバッグ中にスクリプトをステップ実行すると、デバッグの蛍光ペンは、コマンドのどの部分が実行されているかを正確に示し、呼び出された関数とスクリプトを含むファイルを自動的に開きます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-164">As you step through a script while debugging, the debugging highlighter shows precisely which part of the command is running and automatically opens files that include called functions and scripts.</span></span>

<span data-ttu-id="8ed96-165">既定では、[ブレークポイントの設定/解除] メニュー項目は、スクリプト内の行全体にブレークポイントを設定しますが、変数またはコマンド名にブレークポイントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-165">By default, the Toggle Breakpoint menu item sets a breakpoint on an entire line in a script, but you can set a breakpoint on a variable or command name.</span></span>
<span data-ttu-id="8ed96-166">また、行と列の番号によってコマンドにブレークポイントを設定して、長いパイプラインコマンドを簡単にデバッグできるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-166">You can also set a breakpoint on a command by line and column number, making it easier to debug long pipeline commands.</span></span>

<span data-ttu-id="8ed96-167">多くの場合、Windows PowerShell ISE でスクリプトファイルを開くだけで、スクリプト内の構文エラーをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-167">Often, you can debug syntax errors in a script just by opening the script file in Windows PowerShell ISE.</span></span> <span data-ttu-id="8ed96-168">エラーインジケーターでは、構文エラーを識別し、アウトライン機能を使用して、スクリプトの一部を折りたたみ、問題点に焦点を当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-168">The error indicators identify syntax errors and the outlining features let you collapse parts of the script to focus on trouble spots.</span></span>

<span data-ttu-id="8ed96-169">コンソールで使用するのと同じように、コマンドウィンドウで Windows PowerShell デバッガーコマンドレットを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-169">You can also use the Windows PowerShell debugger cmdlets in the Command pane just as you would use them in the console.</span></span>

## <a name="running-remote-commands"></a><span data-ttu-id="8ed96-170">リモート コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="8ed96-170">Running Remote Commands</span></span>

<span data-ttu-id="8ed96-171">新しいリモート PowerShell タブ機能を使用すると、ユーザーが管理する永続的な Windows PowerShell セッション ("PSSession") をローカルコンピューターまたはリモートコンピューターに簡単に確立できます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-171">The New Remote PowerShell Tab feature makes it easy to establish a persistent user-managed Windows PowerShell session ("PSSession") to the local computer or a remote computer.</span></span> <span data-ttu-id="8ed96-172">コマンドを実行すると、ポップアップウィンドウが開き、リモートコンピューターでコマンドを実行するアクセス許可を持つコンピューター名とユーザーアカウントを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-172">The command opens a pop-up window that prompts you for a computer name and for the user account that has permission to run commands on the remote computer.</span></span>

## <a name="customizing-the-view"></a><span data-ttu-id="8ed96-173">ビューのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="8ed96-173">Customizing the View</span></span>

<span data-ttu-id="8ed96-174">Windows PowerShell ISE の機能を使用して、コンソールウィンドウとスクリプトウィンドウの移動やサイズ変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-174">You can use Windows PowerShell ISE features to move and to resize the Console pane and the Script pane.</span></span> <span data-ttu-id="8ed96-175">いずれかのペインの表示と非表示を切り替えることができ、すべてのウィンドウでテキストのサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-175">You can show and hide either pane, and you can change the text size in all the panes.</span></span>

<span data-ttu-id="8ed96-176">また、[オプション] ウィンドウを使用して、Windows PowerShell ISE の外観と操作をカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-176">You can also use the Options window to customize the appearance and operation of Windows PowerShell ISE.</span></span> <span data-ttu-id="8ed96-177">さらに、Windows PowerShell ISE には、メニューやメニュー項目の追加などの Windows PowerShell ISE をカスタマイズするために使用できる、$psISE カスタムホスト変数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="8ed96-177">In addition, Windows PowerShell ISE has a custom host variable, $psISE, that you can use to customize Windows PowerShell ISE, including adding menus and menu items.</span></span>

## <a name="windows-powershell-ise-profile"></a><span data-ttu-id="8ed96-178">プロファイルの Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="8ed96-178">Windows PowerShell ISE Profile</span></span>

<span data-ttu-id="8ed96-179">Windows PowerShell ISE には、独自の Windows PowerShell プロファイル、Microsoft.PowerShellISE_profile.ps1 があります。</span><span class="sxs-lookup"><span data-stu-id="8ed96-179">Windows PowerShell ISE has its own Windows PowerShell profile, Microsoft.PowerShellISE_profile.ps1.</span></span> <span data-ttu-id="8ed96-180">このプロファイルには、Windows PowerShell ISE で使用する関数、エイリアス、変数、およびコマンドを格納できます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-180">In this profile, you can store functions, aliases, variables, and commands that you use in Windows PowerShell ISE.</span></span>

<span data-ttu-id="8ed96-181">Windows PowerShell AllHosts プロファイル (CurrentUser \\ allhosts および AllUsers \\ allhosts) の項目は、windows powershell ホストプログラムと同様に Windows PowerShell ISE でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-181">Items in the Windows PowerShell AllHosts profiles (CurrentUser\\AllHosts and AllUsers\\AllHosts) are also available in Windows PowerShell ISE, just as they are in any Windows PowerShell host program.</span></span> <span data-ttu-id="8ed96-182">ただし、Windows PowerShell コンソールプロファイルの項目は Windows PowerShell ISE では使用できません。</span><span class="sxs-lookup"><span data-stu-id="8ed96-182">However, the items in your Windows PowerShell console profiles are not available in Windows PowerShell ISE.</span></span>

<span data-ttu-id="8ed96-183">プロファイルの移動と再構成の手順については、Windows PowerShell ISE ヘルプおよび about_Profiles を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ed96-183">Instructions for moving and reconfiguring your profiles are available in Windows PowerShell ISE Help and in about_Profiles.</span></span>

## <a name="notes"></a><span data-ttu-id="8ed96-184">注</span><span class="sxs-lookup"><span data-stu-id="8ed96-184">NOTES</span></span>

<span data-ttu-id="8ed96-185">Windows PowerShell ISE は、Windows のクライアントバージョンとサーバーバージョンで既定で有効になっているオプションの Windows 機能です。</span><span class="sxs-lookup"><span data-stu-id="8ed96-185">Windows PowerShell ISE is an optional Windows Feature that is turned on by default on client and server versions of Windows.</span></span> <span data-ttu-id="8ed96-186">クライアントバージョンの Windows で Windows PowerShell ISE を有効または無効にするには、コントロールパネルの [Windows の機能の有効化または無効化] を使用します。</span><span class="sxs-lookup"><span data-stu-id="8ed96-186">To enable and disable Windows PowerShell ISE in client versions of Windows, use Turn Windows Features On or Off in Control Panel.</span></span> <span data-ttu-id="8ed96-187">Windows のサーバーバージョンで Windows PowerShell ISE を有効または無効にするにはサーバーマネージャーの役割と機能の追加ウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="8ed96-187">To enable and disable Windows PowerShell ISE in server versions of Windows, use the Add Roles and Features Wizard in Server Manager.</span></span>

<span data-ttu-id="8ed96-188">Windows PowerShell ISE にはユーザーインターフェイスが必要なため、Windows Server の Server Core インストールでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="8ed96-188">Because Windows PowerShell ISE requires a user interface, it does not work on Server Core installations of Windows Server.</span></span> <span data-ttu-id="8ed96-189">ただし、Windows PowerShell ISE 機能を追加すると、インストールは自動的に GUI を使用してサーバーに変換されます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-189">However, if you add the Windows PowerShell ISE feature, the installation automatically converts to Server with a GUI.</span></span>

<span data-ttu-id="8ed96-190">Windows PowerShell ISE は、Windows Presentation Foundation (WPF) に基づいて構築されています。</span><span class="sxs-lookup"><span data-stu-id="8ed96-190">Windows PowerShell ISE is built on the Windows Presentation Foundation (WPF).</span></span>
<span data-ttu-id="8ed96-191">Windows PowerShell ISE のグラフィカル要素がシステム上で正しくレンダリングされない場合は、システム上で "WPF ハードウェアアクセラレータを無効にする" グラフィックスレンダリング設定を追加または調整することによって、問題を解決することができます。</span><span class="sxs-lookup"><span data-stu-id="8ed96-191">If the graphical elements of Windows PowerShell ISE do not render correctly on your system, you might resolve the problem by adding or adjusting the "Disable WPF Hardware acceleration" graphics rendering settings on your system.</span></span> <span data-ttu-id="8ed96-192">詳細については、「[グラフィックス レンダリングのレジストリ設定](/dotnet/framework/wpf/graphics-multimedia/graphics-rendering-registry-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ed96-192">For more information, see [Graphics Rendering Registry Settings](/dotnet/framework/wpf/graphics-multimedia/graphics-rendering-registry-settings).</span></span>

## <a name="see-also"></a><span data-ttu-id="8ed96-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="8ed96-193">SEE ALSO</span></span>

[<span data-ttu-id="8ed96-194">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="8ed96-194">about_Debuggers</span></span>](about_Debuggers.md)

[<span data-ttu-id="8ed96-195">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="8ed96-195">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="8ed96-196">about_Updatable_Help</span><span class="sxs-lookup"><span data-stu-id="8ed96-196">about_Updatable_Help</span></span>](about_Updatable_Help.md)

[<span data-ttu-id="8ed96-197">Get-Help</span><span class="sxs-lookup"><span data-stu-id="8ed96-197">Get-Help</span></span>](xref:Microsoft.PowerShell.Core.Get-Help)

[<span data-ttu-id="8ed96-198">Get-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="8ed96-198">Get-IseSnippet</span></span>](xref:ISE.Get-IseSnippet)

[<span data-ttu-id="8ed96-199">Import-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="8ed96-199">Import-IseSnippet</span></span>](xref:ISE.Import-IseSnippet)

[<span data-ttu-id="8ed96-200">New-IseSnippet</span><span class="sxs-lookup"><span data-stu-id="8ed96-200">New-IseSnippet</span></span>](xref:ISE.New-IseSnippet)

[<span data-ttu-id="8ed96-201">Save-Help</span><span class="sxs-lookup"><span data-stu-id="8ed96-201">Save-Help</span></span>](xref:Microsoft.PowerShell.Core.Save-Help)

[<span data-ttu-id="8ed96-202">Show-Command</span><span class="sxs-lookup"><span data-stu-id="8ed96-202">Show-Command</span></span>](xref:Microsoft.PowerShell.Utility.Show-Command)

[<span data-ttu-id="8ed96-203">Update-Help</span><span class="sxs-lookup"><span data-stu-id="8ed96-203">Update-Help</span></span>](xref:Microsoft.PowerShell.Core.Update-Help)
