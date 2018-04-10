---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: Windows PowerShell ISE でコンソール ウィンドウを使用する方法
ms.assetid: 44d67705-87c7-4a69-a53e-6471fdebb757
ms.openlocfilehash: 5bbbdd3b1f0324ff1a4f2298459f58640c4dc9a6
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="how-to-use-the-console-pane-in-the-windows-powershell-ise"></a><span data-ttu-id="85648-103">Windows PowerShell ISE でコンソール ウィンドウを使用する方法</span><span class="sxs-lookup"><span data-stu-id="85648-103">How to Use the Console Pane in the Windows PowerShell ISE</span></span>

<span data-ttu-id="85648-104">Windows PowerShell Integrated Scripting Environment (ISE) のコンソール ウィンドウは、スタンドアロンの Windows PowerShell ISE コンソール ウィンドウとまったく同じ動作をします。</span><span class="sxs-lookup"><span data-stu-id="85648-104">The Console pane in the Windows PowerShell Integrated Scripting Environment (ISE) operates exactly like the stand-alone Windows PowerShell ISE console window.</span></span>

<span data-ttu-id="85648-105">コンソール ウィンドウでコマンドを実行するには、コマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="85648-105">To run a command in the Console Pane, type a command, and then press ENTER.</span></span> <span data-ttu-id="85648-106">順番に実行する複数のコマンドを入力するには、コマンドとコマンドの間で SHIFT キーを押しながら ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="85648-106">To enter multiple commands that you want to execute in sequence, type SHIFT+ENTER between commands.</span></span> <span data-ttu-id="85648-107">コマンドを入力する際の支援機能については、「[スクリプト ウィンドウとコンソール ウィンドウでタブ補完を使用する方法](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="85648-107">See [How to Use Tab Completion in the Script Pane and Console Pane](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md) for help in typing commands.</span></span>

<span data-ttu-id="85648-108">コマンドを停止するには、ツール バーで **[実行を中止]** をクリックするか、または CTRL + BREAK キーを押します。</span><span class="sxs-lookup"><span data-stu-id="85648-108">To stop a command, on the toolbar, click **Stop Operation**, or press CTRL+BREAK.</span></span> <span data-ttu-id="85648-109">コンテキストが明確な場合は、コマンドを停止するために CTRL + C キーを押すこともできます。</span><span class="sxs-lookup"><span data-stu-id="85648-109">You can also use CTRL+C to stop a command if the context is unambiguous.</span></span> <span data-ttu-id="85648-110">たとえば、現在のウィンドウでテキストが選択されている場合、CTRL + C キーはコピー操作にマップされます。</span><span class="sxs-lookup"><span data-stu-id="85648-110">For example, if some text has been selected in the current Pane, then CTRL+C maps to the copy operation.</span></span>

<span data-ttu-id="85648-111">Windows PowerShell v3 以降で、出力ウィンドウがコンソール ウィンドウと結合されました。</span><span class="sxs-lookup"><span data-stu-id="85648-111">Beginning in Windows PowerShell v3, the Output pane was combined with the Console pane.</span></span> <span data-ttu-id="85648-112">これの利点は、スタンドアロンの Windows PowerShell コンソールと同様の動作になったことと、この 2 つが独立していたときに必要だった手順の違いが解消されたことです。</span><span class="sxs-lookup"><span data-stu-id="85648-112">This has the benefit of behaving like the stand-alone Windows PowerShell console and eliminates the differences in procedures that were needed when they were separate.</span></span> <span data-ttu-id="85648-113">次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="85648-113">You can:</span></span>

- <span data-ttu-id="85648-114">コンソール ウィンドウからテキストを選択してクリップボードにコピーし、他の任意のウィンドウに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="85648-114">Select and copy text from the Console pane to the Clipboard for pasting in any other window.</span></span> <span data-ttu-id="85648-115">テキストを選択するには、出力ウィンドウでマウスをクリックし、マウス ボタンを押したまま、取り込みたいテキスト上をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="85648-115">To select text, click and hold the mouse in the output pane while dragging the mouse over the text you want to capture.</span></span> <span data-ttu-id="85648-116">また、**Shift** キーを押しながら方向キーを押して、テキストを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="85648-116">You can also use the cursor arrow keys while holding **SHIFT** to select text.</span></span> <span data-ttu-id="85648-117">その後、CTRL+ C キーを押すか、ツール バーの **[コピー]** アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="85648-117">Then press CTRL+C or click the **Copy** icon in the toolbar.</span></span>

- <span data-ttu-id="85648-118">選択したテキストを現在のカーソル位置に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="85648-118">Paste the selected text at a current cursor position.</span></span> <span data-ttu-id="85648-119">ツール バーの **[貼り付け]** アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="85648-119">Click the **Paste** icon on the toolbar.</span></span>

- <span data-ttu-id="85648-120">コンソール ウィンドウ内のすべてのテキストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="85648-120">Clear all the text in the Console pane.</span></span> <span data-ttu-id="85648-121">コンソール ウィンドウをクリアするには、ツール バーの **[コンソール ウィンドウのクリア]** アイコンをクリックするか、コマンド **Clear-Host** またはそのエイリアスである **cls** を実行します。</span><span class="sxs-lookup"><span data-stu-id="85648-121">To clear the Console pane, you can click the **Clear Console Pane** icon on the toolbar, or run the command **Clear-Host** or its alias, **cls**.</span></span>

## <a name="see-also"></a><span data-ttu-id="85648-122">参照</span><span class="sxs-lookup"><span data-stu-id="85648-122">See Also</span></span>

- [<span data-ttu-id="85648-123">Windows PowerShell ISE の紹介</span><span class="sxs-lookup"><span data-stu-id="85648-123">Introducing the Windows PowerShell ISE</span></span>](Introducing-the-Windows-PowerShell-ISE.md)