---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell ISE の紹介"
ms.openlocfilehash: 75242c20548e2e83397867214417a48806c897ec
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2017
---
# <a name="introducing-the-windows-powershell-ise"></a><span data-ttu-id="8ae7a-103">Windows PowerShell ISE の紹介</span><span class="sxs-lookup"><span data-stu-id="8ae7a-103">Introducing the Windows PowerShell ISE</span></span>
<span data-ttu-id="8ae7a-104">Windows PowerShell Integrated Scripting Environment (ISE) は、Windows PowerShell のホスト アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-104">The Windows PowerShell Integrated Scripting Environment (ISE) is a host application for Windows PowerShell.</span></span> <span data-ttu-id="8ae7a-105">Windows PowerShell ISE では、複数行の編集、タブ補完、構文の色分け、選択的な実行、状況依存ヘルプ、右から左へ記述する言語のサポートが可能な単一の Windows ベースのグラフィック ユーザー インターフェイス内で、コマンドの実行や、スクリプトの作成、テスト、およびデバッグを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-105">In Windows PowerShell ISE, you can run commands and write, test, and debug scripts in a single Windows-based graphic user interface with multiline editing, tab completion, syntax coloring, selective execution, context-sensitive help, and support for right-to-left languages.</span></span>
<span data-ttu-id="8ae7a-106">メニュー項目とキーボード ショートカットを使用して、Windows PowerShell コンソールで実行するタスクの多くを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-106">You can use menu items and keyboard shortcuts to perform many of the same tasks that you would perform in the Windows PowerShell console.</span></span>  <span data-ttu-id="8ae7a-107">たとえば、Windows PowerShell ISE 内のスクリプトをデバッグする場合に、スクリプト内の行のブレークポイントを設定するために、コードの行を右クリックして、**[ブレークポイントの設定/解除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-107">For example, when you debug a script in the Windows PowerShell ISE, to set a line breakpoint in a script, right-click the line of code, and then click **Toggle Breakpoint**.</span></span>

<span data-ttu-id="8ae7a-108">Windows PowerShell ISE の新機能をお試しください。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-108">Try these features in Windows PowerShell ISE.</span></span>

- <span data-ttu-id="8ae7a-109">複数行の編集: [コマンド] ウィンドウで現在の行の下に空白行を挿入するには、SHIFT キーを押しながら ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-109">Multiline editing: To insert a blank line under the current line in the Command pane, press SHIFT+ENTER.</span></span>

- <span data-ttu-id="8ae7a-110">選択的な実行: スクリプトの一部を実行するには、実行するテキストを選んで、**[スクリプトの実行]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-110">Selective execution: To run part of a script, select the text you want to run, and then click the **Run Script** button.</span></span> <span data-ttu-id="8ae7a-111">または、F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-111">Or, press F5.</span></span>

- <span data-ttu-id="8ae7a-112">状況依存ヘルプ: **Invoke-Item** と入力し、F1 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-112">Context-sensitive help: Type **Invoke-Item**, and then press F1.</span></span> <span data-ttu-id="8ae7a-113">ヘルプ ファイルの **Invoke-Item** コマンドレットに関するヘルプ トピックが開きます。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-113">The Help file opens to the Help topic for the **Invoke-Item** cmdlet.</span></span>

<span data-ttu-id="8ae7a-114">Windows PowerShell ISE では、外観の一部をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-114">The Windows PowerShell ISE lets you customize some aspects of its appearance.</span></span> <span data-ttu-id="8ae7a-115">また、独自の Windows PowerShell プロファイルも持ち、Windows PowerShell ISE で使用する関数、エイリアス、変数、およびコマンドを格納できます。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-115">It also has its own Windows PowerShell profile, where you can store functions, aliases, variables, and commands you use in the Windows PowerShell ISE.</span></span>

### <a name="to-start-the-windows-powershell-ise"></a><span data-ttu-id="8ae7a-116">Windows PowerShell ISE を開始するには</span><span class="sxs-lookup"><span data-stu-id="8ae7a-116">To start the Windows PowerShell ISE</span></span>

1. <span data-ttu-id="8ae7a-117">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-117">Do one of the following:</span></span>

    -   <span data-ttu-id="8ae7a-118">**[スタート]** をクリックして **[すべてのプログラム]** をポイントし、**[Windows PowerShell V2]** をポイントして **[Windows PowerShell ISE]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-118">Click **Start**, point to **All Programs**, point to **Windows PowerShell V2**, and then click **Windows PowerShell ISE**.</span></span>

    -   <span data-ttu-id="8ae7a-119">Windows PowerShell コンソール (Cmd.exe)、または [コマンド名を指定して実行] ボックスで、「**powershell_ise.exe**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-119">In the Windows PowerShell console Cmd.exe, or in the Run box, type, **powershell_ise.exe**.</span></span>

### <a name="to-get-help-in-the-windows-powershell-ise"></a><span data-ttu-id="8ae7a-120">Windows PowerShell ISE のヘルプを利用するには</span><span class="sxs-lookup"><span data-stu-id="8ae7a-120">To get Help in the Windows PowerShell ISE</span></span>

- <span data-ttu-id="8ae7a-121">**[ヘルプ]** メニューで、**[Windows PowerShell ヘルプ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-121">On the **Help** menu, click **Windows PowerShell Help**.</span></span> <span data-ttu-id="8ae7a-122">または、F1 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-122">Or, press F1.</span></span> <span data-ttu-id="8ae7a-123">開いたファイルは、Get-Help コマンドレットから利用できるすべてのヘルプを含む、Windows PowerShell ISE と Windows PowerShell について説明しています。</span><span class="sxs-lookup"><span data-stu-id="8ae7a-123">The file that opens describes Windows PowerShell ISE and Windows PowerShell, including all of the help available from the Get-Help cmdlet.</span></span>

