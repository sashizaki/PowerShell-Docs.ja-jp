---
ms.date: 12/31/2019
keywords: powershell,コマンドレット
title: Windows PowerShell ISE スクリプト オブジェクト モデルの目的
ms.openlocfilehash: 1f48df112bd19297baa311116e79d3d7603d7c81
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809748"
---
# <a name="purpose-of-the-windows-powershell-ise-scripting-object-model"></a><span data-ttu-id="c20eb-103">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="c20eb-103">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>

<span data-ttu-id="c20eb-104">オブジェクトは、Windows PowerShell Integrated Scripting Environment (ISE) のフォームと機能に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="c20eb-104">Objects are associated with the form and function of Windows PowerShell Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="c20eb-105">オブジェクト モデル リファレンスは、これらのオブジェクトが公開するメンバー プロパティとメソッドに関する詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-105">The object model reference provides details about the member properties and methods that these objects expose.</span></span> <span data-ttu-id="c20eb-106">これらのメソッドとプロパティに直接アクセスするためのスクリプトを使用する方法を示す例が提供されています。</span><span class="sxs-lookup"><span data-stu-id="c20eb-106">Examples are provided to show how you can use scripts to directly access these methods and properties.</span></span> <span data-ttu-id="c20eb-107">スクリプト オブジェクト モデルを使用すると、次のさまざまなタスクが容易になります。</span><span class="sxs-lookup"><span data-stu-id="c20eb-107">The scripting object model makes the following range of tasks easier.</span></span>

## <a name="customizing-the-appearance-of-windows-powershell-ise"></a><span data-ttu-id="c20eb-108">Windows PowerShell ISE の外観のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="c20eb-108">Customizing the appearance of Windows PowerShell ISE</span></span>

<span data-ttu-id="c20eb-109">オブジェクト モデルを使用して、アプリケーションの設定およびオプションを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="c20eb-109">You can use the object model to modify the application settings and options.</span></span> <span data-ttu-id="c20eb-110">たとえば、次のように変更できます。</span><span class="sxs-lookup"><span data-stu-id="c20eb-110">For example, you can modify them as follows:</span></span>

- <span data-ttu-id="c20eb-111">エラー、警告、詳細出力、デバッグ出力の色を変更します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-111">Change the color of errors, warnings, verbose outputs, and debug outputs.</span></span>
- <span data-ttu-id="c20eb-112">コマンド ウィンドウ、出力ウィンドウ、スクリプト ウィンドウの背景色を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-112">Get or set the background colors for the Command pane, the Output pane, and the Script pane.</span></span>
- <span data-ttu-id="c20eb-113">出力ウィンドウの前景色を設定します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-113">Set the foreground color for the Output pane.</span></span>
- <span data-ttu-id="c20eb-114">Windows PowerShell ISE のフォント名とフォント サイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-114">Set the font name and font size for Windows PowerShell ISE.</span></span>
- <span data-ttu-id="c20eb-115">警告を構成します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-115">Configure warnings.</span></span> <span data-ttu-id="c20eb-116">この設定には、複数の PowerShell タブでファイルが開かれている場合や、ファイルが保存される前にそのファイル内のスクリプトを実行する場合に発行される警告が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c20eb-116">This setting includes warnings that are issued when a file is opened in multiple PowerShell tabs or when a script in the file is run before the file has been saved.</span></span>
- <span data-ttu-id="c20eb-117">スクリプト ウィンドウと出力ウィンドウが並べて表示されるビューと、スクリプト ウィンドウが出力ウィンドウの上に表示されるビューを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="c20eb-117">Switch between a view where the Script pane and the Output pane are side-by-side and a view where the Script pane is on top of the Output pane.</span></span>
- <span data-ttu-id="c20eb-118">コマンド ウィンドウは、出力ウィンドウの上部または下部にドッキングします。</span><span class="sxs-lookup"><span data-stu-id="c20eb-118">Dock the Command pane to the bottom or the top of the Output pane.</span></span>

## <a name="enhancing-the-functionality-of-windows-powershell-ise"></a><span data-ttu-id="c20eb-119">Windows PowerShell ISE の機能の拡張</span><span class="sxs-lookup"><span data-stu-id="c20eb-119">Enhancing the functionality of Windows PowerShell ISE</span></span>

<span data-ttu-id="c20eb-120">オブジェクト モデルを使用して、Windows PowerShell ISE の機能を拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="c20eb-120">You can use the object model to enhance the functionality of Windows PowerShell ISE.</span></span> <span data-ttu-id="c20eb-121">たとえば、次のように操作できます。</span><span class="sxs-lookup"><span data-stu-id="c20eb-121">For example, you can:</span></span>

- <span data-ttu-id="c20eb-122">Windows PowerShell ISE 自体のインスタンスを追加して変更します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-122">Add and modify the instance of Windows PowerShell ISE itself.</span></span> <span data-ttu-id="c20eb-123">たとえば、新しいメニュー項目を追加し、そのメニュー項目をスクリプトにマップして、メニューを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="c20eb-123">For example, to change the menus, you can add new menu items and map the new menu items to scripts.</span></span>
- <span data-ttu-id="c20eb-124">Windows PowerShell ISE のメニュー コマンドやボタンを使用して実行できる一部のタスクを実行するスクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-124">Create scripts that perform some of the tasks that you can perform by using the menu commands and buttons in Windows PowerShell ISE.</span></span> <span data-ttu-id="c20eb-125">たとえば、PowerShell タブの追加、削除、選択をすることができます。</span><span class="sxs-lookup"><span data-stu-id="c20eb-125">For example, you can add, remove, or select a PowerShell tab.</span></span>
- <span data-ttu-id="c20eb-126">メニュー コマンドやボタンを使用して実行できるタスクを補完します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-126">Complement tasks that can be performed by using menu commands and buttons.</span></span> <span data-ttu-id="c20eb-127">たとえば、PowerShell タブの名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="c20eb-127">For example, you can rename a PowerShell tab.</span></span>
- <span data-ttu-id="c20eb-128">ファイルに関連付けられているコマンド ウィンドウ、出力ウィンドウ、スクリプト ウィンドウのテキスト バッファーを操作します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-128">Manipulate text buffers for the Command pane, the Output pane, and the Script pane that are associated with a file.</span></span> <span data-ttu-id="c20eb-129">たとえば、次のように操作できます。</span><span class="sxs-lookup"><span data-stu-id="c20eb-129">For example, you can:</span></span>
  - <span data-ttu-id="c20eb-130">すべてのテキストを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-130">Get or set all text.</span></span>
  - <span data-ttu-id="c20eb-131">選択テキストを取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-131">Get or set a text selection.</span></span>
  - <span data-ttu-id="c20eb-132">スクリプトまたはスクリプトの選択した部分を実行します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-132">Run a script or run a selected portion of a script.</span></span>
  - <span data-ttu-id="c20eb-133">行をスクロールして表示します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-133">Scroll a line into view.</span></span>
  - <span data-ttu-id="c20eb-134">カーソル位置にテキストを挿入します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-134">Insert text at a caret position.</span></span>
  - <span data-ttu-id="c20eb-135">テキストのブロックを選択します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-135">Select a block of text.</span></span>
  - <span data-ttu-id="c20eb-136">最後の行番号を取得します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-136">Get the last line number.</span></span>
- <span data-ttu-id="c20eb-137">ファイル操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-137">Perform file operations.</span></span> <span data-ttu-id="c20eb-138">たとえば、次のように操作できます。</span><span class="sxs-lookup"><span data-stu-id="c20eb-138">For example, you can:</span></span>
  - <span data-ttu-id="c20eb-139">ファイルを開いたり、ファイルを保存したり、別の名前を使用してファイルを保存したりします。</span><span class="sxs-lookup"><span data-stu-id="c20eb-139">Open a file, save a file, or save a file by using a different name.</span></span>
  - <span data-ttu-id="c20eb-140">最後に保存された後、ファイルが変更されたかどうかを判別します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-140">Determine whether a file has been changed after it was last saved.</span></span>
  - <span data-ttu-id="c20eb-141">ファイル名を取得します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-141">Get the file name.</span></span>
  - <span data-ttu-id="c20eb-142">ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="c20eb-142">Select a file.</span></span>

## <a name="automating-tasks"></a><span data-ttu-id="c20eb-143">タスクの自動化</span><span class="sxs-lookup"><span data-stu-id="c20eb-143">Automating tasks</span></span>

<span data-ttu-id="c20eb-144">スクリプト オブジェクト モデルを使用して、よく行う操作のキーボード ショートカットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="c20eb-144">You can use the scripting object model to create keyboard shortcuts for frequent operations.</span></span>

## <a name="see-also"></a><span data-ttu-id="c20eb-145">参照</span><span class="sxs-lookup"><span data-stu-id="c20eb-145">See also</span></span>

- [<span data-ttu-id="c20eb-146">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="c20eb-146">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)