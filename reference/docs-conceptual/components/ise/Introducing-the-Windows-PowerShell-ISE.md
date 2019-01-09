---
ms.date: 08/14/2018
keywords: PowerShell, コマンドレット
title: Windows PowerShell ISE の紹介
ms.openlocfilehash: 09a28b295855fd2a3c62bba8a681399dae3454f8
ms.sourcegitcommit: 3402a478cf118c11a5642038eb117bc76553e3ab
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53411584"
---
# <a name="the-windows-powershell-ise"></a><span data-ttu-id="90f15-103">Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="90f15-103">The Windows PowerShell ISE</span></span>

<span data-ttu-id="90f15-104">Windows PowerShell Integrated Scripting Environment (ISE) は、Windows PowerShell のホスト アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="90f15-104">The Windows PowerShell Integrated Scripting Environment (ISE) is a host application for Windows PowerShell.</span></span> <span data-ttu-id="90f15-105">ISE で、コマンドと作成、テストを実行し、1 つの Windows ベースのグラフィック ユーザー インターフェイスでスクリプトをデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="90f15-105">In the ISE, you can run commands and write, test, and debug scripts in a single Windows-based graphic user interface.</span></span> <span data-ttu-id="90f15-106">ISE は、右から左の言語の複数行の編集、タブ補完、構文の色分け、選択的な実行、状況依存のヘルプとサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="90f15-106">The ISE provides multiline editing, tab completion, syntax coloring, selective execution, context-sensitive help, and support for right-to-left languages.</span></span> <span data-ttu-id="90f15-107">メニュー項目とキーボード ショートカットは、Windows PowerShell コンソールで実行する多数の同じタスクにマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="90f15-107">Menu items and keyboard shortcuts are mapped to many of the same tasks that you would do in the Windows PowerShell console.</span></span> <span data-ttu-id="90f15-108">たとえば、ISE でスクリプトをデバッグするときに、行のブレークポイントを設定する編集ウィンドウでコードを右クリックできます。</span><span class="sxs-lookup"><span data-stu-id="90f15-108">For example, when you debug a script in the ISE, you can right-click on a line of code in the edit pane to set a breakpoint.</span></span>

## <a name="support"></a><span data-ttu-id="90f15-109">サポート</span><span class="sxs-lookup"><span data-stu-id="90f15-109">Support</span></span>

<span data-ttu-id="90f15-110">ISE は、Windows PowerShell V2 で初めて導入されたおよび PowerShell V3 を再設計されています。</span><span class="sxs-lookup"><span data-stu-id="90f15-110">The ISE was first introduced with Windows PowerShell V2 and was re-designed with PowerShell V3.</span></span> <span data-ttu-id="90f15-111">ISE に Windows PowerShell となどの Windows PowerShell V5.1 のサポートされているすべてのバージョンでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="90f15-111">The ISE is supported in all supported versions of Windows PowerShell up to and including Windows PowerShell V5.1.</span></span> <span data-ttu-id="90f15-112">ISE がただしは maintennce モードであり、新機能を追加する可能性はありません。</span><span class="sxs-lookup"><span data-stu-id="90f15-112">The ISE, however, is in maintennce mode and no new features are likely to be added.</span></span>
<span data-ttu-id="90f15-113">さらに、ISE で PowerShell v6 や他の製品のサポートはありません。</span><span class="sxs-lookup"><span data-stu-id="90f15-113">Additionally, there is no support for the ISE with PowerShell v6 and beyond.</span></span> <span data-ttu-id="90f15-114">PowerShell スクリプトなどを管理するためのグラフィカル ツールとしているユーザーを考慮する必要があります[Visual Studio Code](https://code.visualstudio.com/)します。</span><span class="sxs-lookup"><span data-stu-id="90f15-114">Users wanting a graphical tool with which to manage PowerShell scrips, etc, should consider [Visual Studio Code](https://code.visualstudio.com/).</span></span>

## <a name="key-features"></a><span data-ttu-id="90f15-115">主な機能</span><span class="sxs-lookup"><span data-stu-id="90f15-115">Key Features</span></span>

<span data-ttu-id="90f15-116">Windows PowerShell ISE の主要な機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="90f15-116">Key features in Windows PowerShell ISE include:</span></span>

- <span data-ttu-id="90f15-117">複数行の編集:[コマンド] ウィンドウで現在の行の下に空白行を挿入するには、SHIFT キーを押しながら ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="90f15-117">Multiline editing: To insert a blank line under the current line in the Command pane, press SHIFT+ENTER.</span></span>
- <span data-ttu-id="90f15-118">選択して実行する場合:スクリプトの一部を実行するには、実行するテキストを選択して、**[スクリプトの実行]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="90f15-118">Selective execution: To run part of a script, select the text you want to run, and then click the **Run Script** button.</span></span> <span data-ttu-id="90f15-119">または、F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="90f15-119">Or, press F5.</span></span>
- <span data-ttu-id="90f15-120">状況依存ヘルプ:**Invoke-Item** と入力し、F1 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="90f15-120">Context-sensitive help: Type **Invoke-Item**, and then press F1.</span></span> <span data-ttu-id="90f15-121">ヘルプ ファイルの **Invoke-Item** コマンドレットに関する記事が開きます。</span><span class="sxs-lookup"><span data-stu-id="90f15-121">The Help file opens to the article for the **Invoke-Item** cmdlet.</span></span>

<span data-ttu-id="90f15-122">Windows PowerShell ISE では、外観の一部をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="90f15-122">The Windows PowerShell ISE lets you customize some aspects of its appearance.</span></span> <span data-ttu-id="90f15-123">また、独自の Windows PowerShell プロファイル スクリプトもあります。</span><span class="sxs-lookup"><span data-stu-id="90f15-123">It also has its own Windows PowerShell profile script.</span></span>

## <a name="to-start-the-windows-powershell-ise"></a><span data-ttu-id="90f15-124">Windows PowerShell ISE を開始するには</span><span class="sxs-lookup"><span data-stu-id="90f15-124">To start the Windows PowerShell ISE</span></span>

<span data-ttu-id="90f15-125">**[スタート]** をクリックし、**[Windows PowerShell]** を選択して、**[Windows PowerShell ISE]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90f15-125">Click **Start**, select **Windows PowerShell**, and then click **Windows PowerShell ISE**.</span></span>
<span data-ttu-id="90f15-126">代わりに、任意のコマンド シェルまたは [実行] ボックスに `powershell_ise.exe` を入力することも可能です。</span><span class="sxs-lookup"><span data-stu-id="90f15-126">Alternately, you can type `powershell_ise.exe` in any command shell or in the Run box.</span></span>

## <a name="to-get-help-in-the-windows-powershell-ise"></a><span data-ttu-id="90f15-127">Windows PowerShell ISE のヘルプを利用するには</span><span class="sxs-lookup"><span data-stu-id="90f15-127">To get Help in the Windows PowerShell ISE</span></span>

<span data-ttu-id="90f15-128">**[ヘルプ]** メニューで、**[Windows PowerShell ヘルプ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="90f15-128">On the **Help** menu, click **Windows PowerShell Help**.</span></span> <span data-ttu-id="90f15-129">または、F1 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="90f15-129">Or, press F1.</span></span> <span data-ttu-id="90f15-130">開いたファイルは、Get-Help コマンドレットから利用できるすべてのヘルプを含む、Windows PowerShell ISE と Windows PowerShell について説明しています。</span><span class="sxs-lookup"><span data-stu-id="90f15-130">The file that opens describes Windows PowerShell ISE and Windows PowerShell, including all of the help available from the Get-Help cmdlet.</span></span>
