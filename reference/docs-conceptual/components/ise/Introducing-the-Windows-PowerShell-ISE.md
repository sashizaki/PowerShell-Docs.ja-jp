---
ms.date: 08/14/2018
keywords: powershell,コマンドレット
title: Windows PowerShell ISE の紹介
ms.openlocfilehash: 3e4471d0982ba4d7ef1a9d59906a9ff297f6f7cb
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "75736200"
---
# <a name="the-windows-powershell-ise"></a><span data-ttu-id="8786c-103">Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="8786c-103">The Windows PowerShell ISE</span></span>

<span data-ttu-id="8786c-104">Windows PowerShell Integrated Scripting Environment (ISE) は、Windows PowerShell のホスト アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="8786c-104">The Windows PowerShell Integrated Scripting Environment (ISE) is a host application for Windows PowerShell.</span></span> <span data-ttu-id="8786c-105">ISE では、コマンドを実行して、単一の Windows ベースのグラフィカル ユーザー インターフェイスでスクリプトの書き込み、テスト、およびデバッグを行うことが可能です。</span><span class="sxs-lookup"><span data-stu-id="8786c-105">In the ISE, you can run commands and write, test, and debug scripts in a single Windows-based graphic user interface.</span></span> <span data-ttu-id="8786c-106">ISE では、複数行の編集、タブ補完、構文の色分け、選択的な実行、状況依存のヘルプ、および右から左方向の言語のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="8786c-106">The ISE provides multiline editing, tab completion, syntax coloring, selective execution, context-sensitive help, and support for right-to-left languages.</span></span> <span data-ttu-id="8786c-107">メニュー項目とキーボード ショートカットは、Windows PowerShell コンソールで実行する多数の同じタスクにマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="8786c-107">Menu items and keyboard shortcuts are mapped to many of the same tasks that you would do in the Windows PowerShell console.</span></span> <span data-ttu-id="8786c-108">たとえば、ISE でスクリプトをデバッグするとき、編集ウィンドウでコード行を右クリックするとブレークポイントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8786c-108">For example, when you debug a script in the ISE, you can right-click on a line of code in the edit pane to set a breakpoint.</span></span>

## <a name="support"></a><span data-ttu-id="8786c-109">サポート</span><span class="sxs-lookup"><span data-stu-id="8786c-109">Support</span></span>

<span data-ttu-id="8786c-110">ISE は、Windows PowerShell V2 で初めて導入され、PowerShell V3 で再設計されました。</span><span class="sxs-lookup"><span data-stu-id="8786c-110">The ISE was first introduced with Windows PowerShell V2 and was re-designed with PowerShell V3.</span></span> <span data-ttu-id="8786c-111">ISE は、Windows PowerShell V5.1 までのすべてのサポートされているバージョンの Windows PowerShell でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8786c-111">The ISE is supported in all supported versions of Windows PowerShell up to and including Windows PowerShell V5.1.</span></span>

> [!NOTE]
> <span data-ttu-id="8786c-112">PowerShell ISE は、アクティブな機能開発の対象ではなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8786c-112">The PowerShell ISE is no longer in active feature development.</span></span> <span data-ttu-id="8786c-113">Windows に付属するコンポーネントとして、セキュリティや優先順位の高いサービスに関する修正プログラムが引き続き公式でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="8786c-113">As a shipping component of Windows, it continues to be officially supported for security and high-priority servicing fixes.</span></span>
> <span data-ttu-id="8786c-114">現在、Windows から ISE が削除される予定はありません。</span><span class="sxs-lookup"><span data-stu-id="8786c-114">We currently have no plans to remove the ISE from Windows.</span></span>
>
> <span data-ttu-id="8786c-115">PowerShell v6 以降では、ISE はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8786c-115">There is no support for the ISE in PowerShell v6 and beyond.</span></span> <span data-ttu-id="8786c-116">ISE の代替をお探しのユーザーは、[PowerShell 拡張機能](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell)と共に [Visual Studio Code](https://code.visualstudio.com/) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8786c-116">Users looking for replacement for the ISE should use [Visual Studio Code](https://code.visualstudio.com/) with the [PowerShell Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.PowerShell).</span></span>

## <a name="key-features"></a><span data-ttu-id="8786c-117">主な機能</span><span class="sxs-lookup"><span data-stu-id="8786c-117">Key Features</span></span>

<span data-ttu-id="8786c-118">Windows PowerShell ISE の主な機能:</span><span class="sxs-lookup"><span data-stu-id="8786c-118">Key features in Windows PowerShell ISE include:</span></span>

- <span data-ttu-id="8786c-119">複数行の編集:[コマンド] ペインで現在の行の下に空白行を挿入するには、<kbd>Shift</kbd>+<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8786c-119">Multiline editing: To insert a blank line under the current line in the Command pane, press <kbd>SHIFT</kbd>+<kbd>ENTER</kbd>.</span></span>
- <span data-ttu-id="8786c-120">選択して実行:スクリプトの一部を実行するには、実行するテキストを選択して、 **[スクリプトの実行]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8786c-120">Selective execution: To run part of a script, select the text you want to run, and then click the **Run Script** button.</span></span> <span data-ttu-id="8786c-121">または、<kbd>F5</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8786c-121">Or, press <kbd>F5</kbd>.</span></span>
- <span data-ttu-id="8786c-122">状況依存ヘルプ:「`Invoke-Item`」と入力してから、<kbd>F1</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8786c-122">Context-sensitive help: Type `Invoke-Item`, and then press <kbd>F1</kbd>.</span></span> <span data-ttu-id="8786c-123">ヘルプ ファイルが開き、`Invoke-Item` コマンドレットの記事が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8786c-123">The Help file opens to the article for the `Invoke-Item` cmdlet.</span></span>

<span data-ttu-id="8786c-124">Windows PowerShell ISE では、外観の一部をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="8786c-124">The Windows PowerShell ISE lets you customize some aspects of its appearance.</span></span> <span data-ttu-id="8786c-125">また、独自の Windows PowerShell プロファイル スクリプトもあります。</span><span class="sxs-lookup"><span data-stu-id="8786c-125">It also has its own Windows PowerShell profile script.</span></span>

## <a name="to-start-the-windows-powershell-ise"></a><span data-ttu-id="8786c-126">Windows PowerShell ISE を開始するには</span><span class="sxs-lookup"><span data-stu-id="8786c-126">To start the Windows PowerShell ISE</span></span>

<span data-ttu-id="8786c-127">**[スタート]** をクリックし、 **[Windows PowerShell]** を選択して、 **[Windows PowerShell ISE]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8786c-127">Click **Start**, select **Windows PowerShell**, and then click **Windows PowerShell ISE**.</span></span>
<span data-ttu-id="8786c-128">代わりに、任意のコマンド シェルまたは [実行] ボックスに `powershell_ise.exe` を入力することも可能です。</span><span class="sxs-lookup"><span data-stu-id="8786c-128">Alternately, you can type `powershell_ise.exe` in any command shell or in the Run box.</span></span>

## <a name="to-get-help-in-the-windows-powershell-ise"></a><span data-ttu-id="8786c-129">Windows PowerShell ISE のヘルプを利用するには</span><span class="sxs-lookup"><span data-stu-id="8786c-129">To get Help in the Windows PowerShell ISE</span></span>

<span data-ttu-id="8786c-130">**[ヘルプ]** メニューで、 **[Windows PowerShell ヘルプ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8786c-130">On the **Help** menu, click **Windows PowerShell Help**.</span></span> <span data-ttu-id="8786c-131">または、<kbd>F1</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8786c-131">Or, press <kbd>F1</kbd>.</span></span> <span data-ttu-id="8786c-132">開かれたファイルに、Windows PowerShell ISE と Windows PowerShell に関する説明が表示されます。これには、`Get-Help` コマンドレットから入手できるヘルプがすべて含まれています。</span><span class="sxs-lookup"><span data-stu-id="8786c-132">The file that opens describes Windows PowerShell ISE and Windows PowerShell, including all the help available from the `Get-Help` cmdlet.</span></span>
