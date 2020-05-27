---
ms.date: 01/02/2020
keywords: powershell,コマンドレット
title: Windows PowerShell ISE でコンソール ウィンドウを使用する方法
ms.openlocfilehash: f0ef07e410ed494f5732eab360c4e050c9c09a7f
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83808728"
---
# <a name="how-to-use-the-console-pane-in-the-windows-powershell-ise"></a><span data-ttu-id="e9151-103">Windows PowerShell ISE でコンソール ウィンドウを使用する方法</span><span class="sxs-lookup"><span data-stu-id="e9151-103">How to Use the Console Pane in the Windows PowerShell ISE</span></span>

<span data-ttu-id="e9151-104">Windows PowerShell Integrated Scripting Environment (ISE) のコンソール ウィンドウは、スタンドアロンの Windows PowerShell ISE コンソール ウィンドウとまったく同じ動作をします。</span><span class="sxs-lookup"><span data-stu-id="e9151-104">The Console pane in the Windows PowerShell Integrated Scripting Environment (ISE) operates exactly like the stand-alone Windows PowerShell ISE console window.</span></span>

<span data-ttu-id="e9151-105">コンソール ウィンドウでコマンドを実行するには、コマンドを入力し、<kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e9151-105">To run a command in the Console Pane, type a command, and then press <kbd>ENTER</kbd>.</span></span> <span data-ttu-id="e9151-106">順番に実行する複数のコマンドを入力するには、コマンドとコマンドの間で <kbd>Shift</kbd> + <kbd>Enter</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e9151-106">To enter multiple commands that you want to execute in sequence, type <kbd>SHIFT</kbd>+<kbd>ENTER</kbd> between commands.</span></span> <span data-ttu-id="e9151-107">コマンドを入力する際の支援機能については、「[スクリプト ウィンドウとコンソール ウィンドウでタブ補完を使用する方法](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e9151-107">See [How to Use Tab Completion in the Script Pane and Console Pane](How-to-Use-Tab-Completion-in-the-Script-Pane-and-Console-Pane.md) for help in typing commands.</span></span>

<span data-ttu-id="e9151-108">コマンドを停止するには、ツール バーで **[実行を中止]** をクリックするか、または <kbd>Ctrl</kbd> + <kbd>Break</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e9151-108">To stop a command, on the toolbar, click **Stop Operation**, or press <kbd>CTRL</kbd>+<kbd>BREAK</kbd>.</span></span> <span data-ttu-id="e9151-109">コンテキストが明確な場合は、<kbd>Ctrl</kbd> + <kbd>C</kbd> キーを押してコマンドを停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9151-109">You can also use <kbd>CTRL</kbd>+<kbd>C</kbd> to stop a command if the context is unambiguous.</span></span> <span data-ttu-id="e9151-110">たとえば、現在のウィンドウでテキストが選択されている場合、<kbd>Ctrl</kbd> + <kbd>C</kbd> キーはコピー操作にマップされます。</span><span class="sxs-lookup"><span data-stu-id="e9151-110">For example, if some text has been selected in the current Pane, then <kbd>CTRL</kbd>+<kbd>C</kbd> maps to the copy operation.</span></span>

<span data-ttu-id="e9151-111">Windows PowerShell v3 以降で、出力ウィンドウがコンソール ウィンドウと結合されました。</span><span class="sxs-lookup"><span data-stu-id="e9151-111">Beginning in Windows PowerShell v3, the Output pane was combined with the Console pane.</span></span> <span data-ttu-id="e9151-112">これの利点は、スタンドアロンの Windows PowerShell コンソールと同様の動作になったことと、この 2 つが独立していたときに必要だった手順の違いが解消されたことです。</span><span class="sxs-lookup"><span data-stu-id="e9151-112">This has the benefit of behaving like the stand-alone Windows PowerShell console and eliminates the differences in procedures that were needed when they were separate.</span></span> <span data-ttu-id="e9151-113">次のようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9151-113">You can:</span></span>

- <span data-ttu-id="e9151-114">コンソール ウィンドウからテキストを選択してクリップボードにコピーし、他の任意のウィンドウに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e9151-114">Select and copy text from the Console pane to the Clipboard for pasting in any other window.</span></span> <span data-ttu-id="e9151-115">テキストを選択するには、出力ウィンドウでマウスをクリックし、マウス ボタンを押したまま、取り込みたいテキスト上をドラッグします。</span><span class="sxs-lookup"><span data-stu-id="e9151-115">To select text, click and hold the mouse in the output pane while dragging the mouse over the text you want to capture.</span></span> <span data-ttu-id="e9151-116">また、<kbd>Shift</kbd> キーを押しながら方向キーを押して、テキストを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9151-116">You can also use the cursor arrow keys while holding <kbd>SHIFT</kbd> to select text.</span></span> <span data-ttu-id="e9151-117">その後、<kbd>Ctrl</kbd> + <kbd>C</kbd> キーを押すか、ツール バーの **[コピー]** アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9151-117">Then press <kbd>CTRL</kbd>+<kbd>C</kbd> or click the **Copy** icon in the toolbar.</span></span>

- <span data-ttu-id="e9151-118">選択したテキストを現在のカーソル位置に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e9151-118">Paste the selected text at a current cursor position.</span></span> <span data-ttu-id="e9151-119">ツール バーの **[貼り付け]** アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e9151-119">Click the **Paste** icon on the toolbar.</span></span>

- <span data-ttu-id="e9151-120">コンソール ウィンドウ内のすべてのテキストをクリアします。</span><span class="sxs-lookup"><span data-stu-id="e9151-120">Clear all the text in the Console pane.</span></span> <span data-ttu-id="e9151-121">コンソール ウィンドウをクリアするには、ツール バーの **[コンソール ウィンドウのクリア]** アイコンをクリックするか、コマンド `Clear-Host` またはそのエイリアスである `cls` を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9151-121">To clear the Console pane, you can click the **Clear Console Pane** icon on the toolbar, or run the command `Clear-Host` or its alias, `cls`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9151-122">参照</span><span class="sxs-lookup"><span data-stu-id="e9151-122">See Also</span></span>

- [<span data-ttu-id="e9151-123">Windows PowerShell ISE の紹介</span><span class="sxs-lookup"><span data-stu-id="e9151-123">Introducing the Windows PowerShell ISE</span></span>](Introducing-the-Windows-PowerShell-ISE.md)
