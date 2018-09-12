---
ms.date: 08/14/2018
keywords: PowerShell, コマンドレット
title: Windows PowerShell ISE の紹介
ms.openlocfilehash: d27a0eb594d7271121cee59f38d096995cc98648
ms.sourcegitcommit: 56b9be8503a5a1342c0b85b36f5ba6f57c281b63
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "43133134"
---
# <a name="introducing-the-windows-powershell-ise"></a><span data-ttu-id="5bf96-103">Windows PowerShell ISE の紹介</span><span class="sxs-lookup"><span data-stu-id="5bf96-103">Introducing the Windows PowerShell ISE</span></span>

<span data-ttu-id="5bf96-104">Windows PowerShell Integrated Scripting Environment (ISE) は、Windows PowerShell のホスト アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="5bf96-104">The Windows PowerShell Integrated Scripting Environment (ISE) is a host application for Windows PowerShell.</span></span> <span data-ttu-id="5bf96-105">Windows PowerShell ISE でコマンドを実行して、単一の Windows ベースのグラフィカル ユーザー インターフェイスでスクリプトの書き込み、テスト、およびデバッグを行うことが可能です。</span><span class="sxs-lookup"><span data-stu-id="5bf96-105">In Windows PowerShell ISE, you can run commands and write, test, and debug scripts in a single Windows-based graphic user interface.</span></span> <span data-ttu-id="5bf96-106">インターフェイスでは、複数行の編集、タブ補完、構文の色分け、選択的な実行、状況依存のヘルプ、および右から左方向の言語のサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="5bf96-106">The interface provides multiline editing, tab completion, syntax coloring, selective execution, context-sensitive help, and support for right-to-left languages.</span></span> <span data-ttu-id="5bf96-107">メニュー項目とキーボード ショートカットは、Windows PowerShell コンソールで実行する多数の同じタスクにマッピングされます。</span><span class="sxs-lookup"><span data-stu-id="5bf96-107">Menu items and keyboard shortcuts are mapped to many of the same tasks that you would do in the Windows PowerShell console.</span></span> <span data-ttu-id="5bf96-108">たとえば、Windows PowerShell ISE でスクリプトをデバッグするとき、コード行を右クリックするとブレークポイントを設定できます。</span><span class="sxs-lookup"><span data-stu-id="5bf96-108">For example, when you debug a script in the Windows PowerShell ISE, you can right-click on a line of code to set a breakpoint.</span></span>

<span data-ttu-id="5bf96-109">Windows PowerShell ISE の新機能をお試しください。</span><span class="sxs-lookup"><span data-stu-id="5bf96-109">Try these features in Windows PowerShell ISE.</span></span>

- <span data-ttu-id="5bf96-110">複数行の編集: [コマンド] ウィンドウで現在の行の下に空白行を挿入するには、SHIFT キーを押しながら ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5bf96-110">Multiline editing: To insert a blank line under the current line in the Command pane, press SHIFT+ENTER.</span></span>
- <span data-ttu-id="5bf96-111">選択的な実行: スクリプトの一部を実行するには、実行するテキストを選んで、**[スクリプトの実行]** ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bf96-111">Selective execution: To run part of a script, select the text you want to run, and then click the **Run Script** button.</span></span> <span data-ttu-id="5bf96-112">または、F5 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5bf96-112">Or, press F5.</span></span>
- <span data-ttu-id="5bf96-113">状況依存ヘルプ: **Invoke-Item** と入力し、F1 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5bf96-113">Context-sensitive help: Type **Invoke-Item**, and then press F1.</span></span> <span data-ttu-id="5bf96-114">ヘルプ ファイルの **Invoke-Item** コマンドレットに関する記事が開きます。</span><span class="sxs-lookup"><span data-stu-id="5bf96-114">The Help file opens to the article for the **Invoke-Item** cmdlet.</span></span>

<span data-ttu-id="5bf96-115">Windows PowerShell ISE では、外観の一部をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="5bf96-115">The Windows PowerShell ISE lets you customize some aspects of its appearance.</span></span> <span data-ttu-id="5bf96-116">また、独自の Windows PowerShell プロファイル スクリプトもあります。</span><span class="sxs-lookup"><span data-stu-id="5bf96-116">It also has its own Windows PowerShell profile script.</span></span>

## <a name="to-start-the-windows-powershell-ise"></a><span data-ttu-id="5bf96-117">Windows PowerShell ISE を開始するには</span><span class="sxs-lookup"><span data-stu-id="5bf96-117">To start the Windows PowerShell ISE</span></span>

<span data-ttu-id="5bf96-118">**[スタート]** をクリックし、**[Windows PowerShell]** を選択して、**[Windows PowerShell ISE]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bf96-118">Click **Start**, select **Windows PowerShell**, and then click **Windows PowerShell ISE**.</span></span>
<span data-ttu-id="5bf96-119">代わりに、任意のコマンド シェルまたは [実行] ボックスに `powershell_ise.exe` を入力することも可能です。</span><span class="sxs-lookup"><span data-stu-id="5bf96-119">Alternately, you can type `powershell_ise.exe` in any command shell or in the Run box.</span></span>

## <a name="to-get-help-in-the-windows-powershell-ise"></a><span data-ttu-id="5bf96-120">Windows PowerShell ISE のヘルプを利用するには</span><span class="sxs-lookup"><span data-stu-id="5bf96-120">To get Help in the Windows PowerShell ISE</span></span>

<span data-ttu-id="5bf96-121">**[ヘルプ]** メニューで、**[Windows PowerShell ヘルプ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bf96-121">On the **Help** menu, click **Windows PowerShell Help**.</span></span> <span data-ttu-id="5bf96-122">または、F1 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5bf96-122">Or, press F1.</span></span> <span data-ttu-id="5bf96-123">開いたファイルは、Get-Help コマンドレットから利用できるすべてのヘルプを含む、Windows PowerShell ISE と Windows PowerShell について説明しています。</span><span class="sxs-lookup"><span data-stu-id="5bf96-123">The file that opens describes Windows PowerShell ISE and Windows PowerShell, including all of the help available from the Get-Help cmdlet.</span></span>