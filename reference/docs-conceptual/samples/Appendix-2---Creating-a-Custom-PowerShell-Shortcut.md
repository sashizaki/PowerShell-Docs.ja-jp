---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: 付録 2 - カスタムの PowerShell ショートカットの作成
ms.assetid: 5d4fd421-5d43-4ec7-86fd-acfe887b066e
ms.openlocfilehash: e8081b7a64d313c8ef4bbccf95f250445dd68ad9
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403374"
---
# <a name="appendix-2---creating-a-custom-powershell-shortcut"></a><span data-ttu-id="8befc-103">付録 2 - カスタムの PowerShell ショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="8befc-103">Appendix 2 - Creating a Custom PowerShell Shortcut</span></span>

<span data-ttu-id="8befc-104">次の手順では、カスタマイズされたいくつかの便利なオプションを備えた Windows PowerShell へのショートカットの作成方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8befc-104">The following procedure describes how to create a shortcut to Windows PowerShell that has several convenient options customized.</span></span>

1. <span data-ttu-id="8befc-105">Powershell.exe へのショートカットを作成します。</span><span class="sxs-lookup"><span data-stu-id="8befc-105">Create a shortcut that points to Powershell.exe.</span></span>

2. <span data-ttu-id="8befc-106">ショートカットを右クリックし、**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8befc-106">Right-click the shortcut, and then click **Properties**.</span></span>

3. <span data-ttu-id="8befc-107">**[オプション]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8befc-107">Click the **Options** tab.</span></span>

4. <span data-ttu-id="8befc-108">**[編集オプション]** セクションの **[簡易編集モード]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8befc-108">In the **Edit Options** section, select the **QuickEdit** check box.</span></span>

    <span data-ttu-id="8befc-109">この設定により、Windows PowerShell のコンソール ウィンドウで、左マウス ボタンをドラッグしてテキストを選択したり、Enter キーを押すかマウスを右クリックすることによってテキストをクリップボードにコピーしたりできるようになります。</span><span class="sxs-lookup"><span data-stu-id="8befc-109">This setting lets you select text in the Windows PowerShell console window by dragging the left mouse button, and it lets you copy text to the clipboard by pressing ENTER or by right-clicking the mouse.</span></span>

5. <span data-ttu-id="8befc-110">**[編集オプション]** セクションの **[挿入モード]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8befc-110">In the **Edit Options** section, select the **Insert Mode** check box.</span></span> <span data-ttu-id="8befc-111">この設定により、コンソール ウィンドウで右クリックすると、クリップボードから自動的にテキストが貼り付けられます。</span><span class="sxs-lookup"><span data-stu-id="8befc-111">This setting lets you right-click in the console window to automatically paste text from the clipboard.</span></span>

6. <span data-ttu-id="8befc-112">**[コマンドの履歴]** セクションの **[バッファー サイズ]** ボックスで、1 から 999 までの数値を入力するか選択します。</span><span class="sxs-lookup"><span data-stu-id="8befc-112">In the **Command History** section, type or select a number between 1 and 999 in the **Buffer Size** box.</span></span> <span data-ttu-id="8befc-113">これにより、コンソール バッファーに保持される、入力されたコマンドの数が設定されます。</span><span class="sxs-lookup"><span data-stu-id="8befc-113">This sets the number of typed commands that will be kept in the console buffer.</span></span>

7. <span data-ttu-id="8befc-114">**[コマンドの履歴]** セクションの **[重複する古い履歴を破棄]** チェック ボックスを選択して、重複するコマンドをコンソール バッファーから排除します。</span><span class="sxs-lookup"><span data-stu-id="8befc-114">In the **Command History** section, select the **Discard Old Duplicates** check box to eliminate repeated commands from the console buffer.</span></span>

8. <span data-ttu-id="8befc-115">**[レイアウト]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8befc-115">Click the **Layout** tab.</span></span>

9. <span data-ttu-id="8befc-116">**[画面バッファーのサイズ]** セクションの **[高さ]** ボックスに、1 から 9999 の数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="8befc-116">In the **Screen Buffer** section, type a number between 1 and 9999 in the **Height** box.</span></span> <span data-ttu-id="8befc-117">この高さは、バッファーに保存される出力の行数を表します。</span><span class="sxs-lookup"><span data-stu-id="8befc-117">The height represents the number of lines of output that are buffered.</span></span> <span data-ttu-id="8befc-118">この数値は、コンソール ウィンドウ内をスクロールする際に表示される最大行数を示します。</span><span class="sxs-lookup"><span data-stu-id="8befc-118">This is the maximum number of lines retained for viewing when you scroll through the console window.</span></span> <span data-ttu-id="8befc-119">この数値が **[ウィンドウのサイズ]** セクションに示される高さよりも小さい場合、同じ値になるようにウィンドウ サイズの高さが自動的に縮小されます。</span><span class="sxs-lookup"><span data-stu-id="8befc-119">If this number is lower than the height shown in the **Window size** section, the window size height will automatically be reduced to the same value.</span></span>

10. <span data-ttu-id="8befc-120">**[ウィンドウのサイズ]** セクションに、幅の値として 1 から 9999 の数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="8befc-120">In the **Window Size** section, type a number between 1 and 9999 for the width.</span></span> <span data-ttu-id="8befc-121">これは、コンソール ウィンドウの 1 行に表示される文字数を表します。</span><span class="sxs-lookup"><span data-stu-id="8befc-121">This represents the number of characters that are displayed across the console window.</span></span> <span data-ttu-id="8befc-122">既定の幅は 80 です。Windows PowerShell の出力形式は、この幅用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="8befc-122">The default width is 80, and Windows PowerShell's output formatting is designed for this width.</span></span>

11. <span data-ttu-id="8befc-123">コンソールが開いたときに、デスクトップの特定の位置にそのコンソールが表示されるようにする場合は、**[ウィンドウの位置]** セクションの **[システム設定を使う]** チェック ボックスをオフにし、**[ウィンドウの位置]** セクションで、**[左]** ボックスと **[上]** ボックスの値を変更します。</span><span class="sxs-lookup"><span data-stu-id="8befc-123">If you want to place the console at a particular point on the desktop when it is opened, clear the **Let system position window** check box in the **Window position** section, and then change the values in the **Left** and **Top** boxes in the **Window position** section.</span></span>

12. <span data-ttu-id="8befc-124">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8befc-124">Click **OK**.</span></span>