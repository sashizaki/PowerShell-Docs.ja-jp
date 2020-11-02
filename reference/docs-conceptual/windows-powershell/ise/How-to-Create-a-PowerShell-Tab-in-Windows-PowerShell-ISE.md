---
ms.date: 01/02/2020
title: Windows PowerShell ISE で PowerShell タブを作成する方法
description: Windows PowerShell Integrated Scripting Environment (ISE) のタブを使うと、同じアプリケーション内で複数の実行環境を同時に作成して使用することができます。 PowerShell の各タブは、独立した実行環境またはセッションに対応します。
ms.openlocfilehash: 62054014be9890b3fa0296f717f65a85534628d8
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663774"
---
# <a name="how-to-create-a-powershell-tab-in-windows-powershell-ise"></a><span data-ttu-id="9390d-104">Windows PowerShell ISE で PowerShell タブを作成する方法</span><span class="sxs-lookup"><span data-stu-id="9390d-104">How to Create a PowerShell Tab in Windows PowerShell ISE</span></span>

<span data-ttu-id="9390d-105">Windows PowerShell Integrated Scripting Environment (ISE) のタブを使うと、同じアプリケーション内で複数の実行環境を同時に作成して使用することができます。</span><span class="sxs-lookup"><span data-stu-id="9390d-105">Tabs in the Windows PowerShell Integrated Scripting Environment (ISE) allow you to simultaneously create and use several execution environments within the same application.</span></span> <span data-ttu-id="9390d-106">PowerShell の各タブは、独立した実行環境またはセッションに対応します。</span><span class="sxs-lookup"><span data-stu-id="9390d-106">Each PowerShell tab corresponds to a separate execution environment or session.</span></span>

> [!NOTE]
> <span data-ttu-id="9390d-107">1 つのタブで作成した変数、関数、別名が、他のタブに引き継がれることはありません。</span><span class="sxs-lookup"><span data-stu-id="9390d-107">Variables, functions, and aliases that you create in one tab do not carry over to another.</span></span> <span data-ttu-id="9390d-108">それらのタブは、別々の Windows PowerShell セッションです。</span><span class="sxs-lookup"><span data-stu-id="9390d-108">They are different Windows PowerShell sessions.</span></span>

<span data-ttu-id="9390d-109">Windows PowerShell でタブを開いたり閉じたりするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9390d-109">Use the following steps to open or close a tab in Windows PowerShell.</span></span> <span data-ttu-id="9390d-110">タブの名前を変更するには、Windows PowerShell タブのスクリプト オブジェクトで [DisplayName](object-model/The-PowerShellTab-Object.md#displayname) プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="9390d-110">To rename a tab, set the [DisplayName](object-model/The-PowerShellTab-Object.md#displayname) property on the Windows PowerShell Tab scripting object.</span></span>

## <a name="to-create-and-use-a-new-powershell-tab"></a><span data-ttu-id="9390d-111">新しい PowerShell タブを作成して使用するには</span><span class="sxs-lookup"><span data-stu-id="9390d-111">To create and use a new PowerShell Tab</span></span>

<span data-ttu-id="9390d-112">**[ファイル]** メニューで、 **[PowerShell タブの新規作成]** をクリックします。新しい PowerShell タブは、常にアクティブなウィンドウとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="9390d-112">On the **File** menu, click **New PowerShell Tab** . The new PowerShell tab always opens as the active window.</span></span> <span data-ttu-id="9390d-113">PowerShell のタブには、開かれた順に番号が付けられます。</span><span class="sxs-lookup"><span data-stu-id="9390d-113">PowerShell tabs are incrementally numbered in the order that they are opened.</span></span> <span data-ttu-id="9390d-114">各タブは、それぞれ独自の Windows PowerShell コンソール ウィンドウに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="9390d-114">Each tab is associated with its own Windows PowerShell console window.</span></span> <span data-ttu-id="9390d-115">独自のセッションを持つ PowerShell タブは、最大 32 個まで (Windows PowerShell ISE 2.0 では 8 個まで) を同時に開くことができます。</span><span class="sxs-lookup"><span data-stu-id="9390d-115">You can have up to 32 PowerShell tabs with their own session open at a time (this is limited to 8 on Windows PowerShell ISE 2.0.)</span></span>

<span data-ttu-id="9390d-116">なお、ツール バーの **[新規作成]** または **[開く]** アイコンをクリックしても、新しいタブで別のセッションを作成できないことにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="9390d-116">Note that clicking the **New** or **Open** icons on the toolbar does not create a new tab with a separate session.</span></span> <span data-ttu-id="9390d-117">代わりに、これらのボタンを使うと、セッションを持つ現在アクティブなタブ上で、新規または既存のスクリプト ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="9390d-117">Instead, those buttons open a new or existing script file on the currently active tab with a session.</span></span> <span data-ttu-id="9390d-118">各タブおよびセッションでは、複数のスクリプト ファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="9390d-118">You can have multiple script files open with each tab and session.</span></span> <span data-ttu-id="9390d-119">セッションのスクリプト タブは、関連付けられたセッションがアクティブな場合にのみ、セッションのタブの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9390d-119">The script tabs for a session only appear below the session tabs when the associated session is active.</span></span>

<span data-ttu-id="9390d-120">PowerShell タブをアクティブにするには、タブをクリックします。開かれているすべての PowerShell タブの中から選択するには、 **[表示]** メニューで、使う PowerShell タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9390d-120">To make a PowerShell tab active, click the tab. To select from all PowerShell tabs that are open, on the **View** menu, click the PowerShell tab you want to use.</span></span>

## <a name="to-create-and-use-a-new-remote-powershell-tab"></a><span data-ttu-id="9390d-121">新しいリモート PowerShell タブを作成して使用するには</span><span class="sxs-lookup"><span data-stu-id="9390d-121">To create and use a new Remote PowerShell tab</span></span>

<span data-ttu-id="9390d-122">**[ファイル]** メニューの **[リモート PowerShell タブの新規作成]** をクリックすると、リモート コンピューターでセッションが確立されます。</span><span class="sxs-lookup"><span data-stu-id="9390d-122">On the **File** menu, click **New Remote PowerShell Tab** to establish a session on a remote computer.</span></span> <span data-ttu-id="9390d-123">ダイアログ ボックスが表示され、リモート接続を確立するために必要な詳細情報を入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="9390d-123">A dialog box appears and prompts you to enter details required to establish the remote connection.</span></span> <span data-ttu-id="9390d-124">リモート タブの機能はローカルの PowerShell タブと同様ですが、コマンドとスクリプトはリモート コンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="9390d-124">The remote tab functions just like a local PowerShell tab, but the commands and scripts are run on the remote computer.</span></span>

## <a name="to-close-a-powershell-tab"></a><span data-ttu-id="9390d-125">PowerShell タブを閉じるには</span><span class="sxs-lookup"><span data-stu-id="9390d-125">To close a PowerShell Tab</span></span>

<span data-ttu-id="9390d-126">タブを閉じるには、次の手法のいずれかを使います。</span><span class="sxs-lookup"><span data-stu-id="9390d-126">To close a tab, you can use any of the following techniques:</span></span>

- <span data-ttu-id="9390d-127">終了するタブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9390d-127">Click the tab that you want to close.</span></span>

- <span data-ttu-id="9390d-128">**[ファイル]** メニューの **[PowerShell タブを閉じる]** をクリックするか、アクティブなタブの閉じるボタン **[X]** をクリックして、タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="9390d-128">On the **File** menu, click **Close PowerShell Tab** , or click the Close button ( **X** ) on an active tab to close the tab.</span></span>

<span data-ttu-id="9390d-129">閉じようとしている PowerShell タブに未保存のファイルがあると、そのファイルを保存するか破棄するかを求められます。</span><span class="sxs-lookup"><span data-stu-id="9390d-129">If you have unsaved files open in the PowerShell tab that you are closing, you are prompted to save or discard them.</span></span> <span data-ttu-id="9390d-130">スクリプトを保存する方法について詳しくは、「[スクリプトを保存する方法](How-to-Write-and-Run-Scripts-in-the-Windows-PowerShell-ISE.md#how-to-save-a-script)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9390d-130">For more information about how to save a script, see [How to Save a Script](How-to-Write-and-Run-Scripts-in-the-Windows-PowerShell-ISE.md#how-to-save-a-script).</span></span>

## <a name="see-also"></a><span data-ttu-id="9390d-131">参照</span><span class="sxs-lookup"><span data-stu-id="9390d-131">See Also</span></span>

- [<span data-ttu-id="9390d-132">Windows PowerShell ISE の紹介</span><span class="sxs-lookup"><span data-stu-id="9390d-132">Introducing the Windows PowerShell ISE</span></span>](Introducing-the-Windows-PowerShell-ISE.md)
- [<span data-ttu-id="9390d-133">Windows PowerShell ISE でコンソール ウィンドウを使用する方法</span><span class="sxs-lookup"><span data-stu-id="9390d-133">How to Use the Console Pane in the Windows PowerShell ISE</span></span>](How-to-Use-the-Console-Pane-in-the-Windows-PowerShell-ISE.md)
