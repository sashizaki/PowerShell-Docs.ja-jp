---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: グラフィカルな日付の選択を作成する
description: この記事では、Windows PowerShell で .NET Framework のフォーム作成機能を使用して、カレンダー スタイルのカスタム コントロールを作成する方法を示します。
ms.openlocfilehash: b73c9ba78817af7c38c20642402752765a7a3674
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500506"
---
# <a name="creating-a-graphical-date-picker"></a><span data-ttu-id="a3a7f-104">グラフィカルな日付の選択を作成する</span><span class="sxs-lookup"><span data-stu-id="a3a7f-104">Creating a Graphical Date Picker</span></span>

<span data-ttu-id="a3a7f-105">ユーザーが日付を選択できる、グラフィカルな予定表スタイルのコントロールを備えたフォームを作成するには、Windows PowerShell 3.0 以降のリリースを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-105">Use Windows PowerShell 3.0 and later releases to create a form with a graphical, calendar-style control that lets users select a day of the month.</span></span>

## <a name="create-a-graphical-date-picker-control"></a><span data-ttu-id="a3a7f-106">グラフィカルな日付の選択コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="a3a7f-106">Create a graphical date-picker control</span></span>

<span data-ttu-id="a3a7f-107">以下を Windows PowerShell ISE にコピーしてから貼り付け、Windows PowerShell スクリプト (.ps1) として保存します。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-107">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object Windows.Forms.Form -Property @{
    StartPosition = [Windows.Forms.FormStartPosition]::CenterScreen
    Size          = New-Object Drawing.Size 243, 230
    Text          = 'Select a Date'
    Topmost       = $true
}

$calendar = New-Object Windows.Forms.MonthCalendar -Property @{
    ShowTodayCircle   = $false
    MaxSelectionCount = 1
}
$form.Controls.Add($calendar)

$okButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 38, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'OK'
    DialogResult = [Windows.Forms.DialogResult]::OK
}
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)

$cancelButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 113, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'Cancel'
    DialogResult = [Windows.Forms.DialogResult]::Cancel
}
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)

$result = $form.ShowDialog()

if ($result -eq [Windows.Forms.DialogResult]::OK) {
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

<span data-ttu-id="a3a7f-108">このスクリプトは 2 つの .NET Framework クラス、つまり **System.Drawing** と **System.Windows.Forms** を最初に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-108">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms** .</span></span> <span data-ttu-id="a3a7f-109">次に、.NET Framework クラス **Windows.Forms.Form** の新しいインスタンスを開始します。これにより、コントロールの追加を開始する空白のフォームまたはウィンドウが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-109">You then start a new instance of the .NET Framework class **Windows.Forms.Form** ; that provides a blank form or window to which you can start adding controls.</span></span>

```powershell
$form = New-Object Windows.Forms.Form -Property @{
    StartPosition = [Windows.Forms.FormStartPosition]::CenterScreen
    Size          = New-Object Drawing.Size 243, 230
    Text          = 'Select a Date'
    Topmost       = $true
}
```

<span data-ttu-id="a3a7f-110">この例では、 **Property** プロパティとハッシュ テーブルを使って、このクラスの 4 つのプロパティに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-110">This example assigns values to four properties of this class by using the **Property** property and hashtable.</span></span>

1. <span data-ttu-id="a3a7f-111">**StartPosition** :このプロパティを追加しない場合は、Windows によりフォームが開かれる場所が選択されます。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-111">**StartPosition** : If you don't add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="a3a7f-112">このプロパティを **CenterScreen** に設定すると、フォームは読み込まれるたびに画面中央に自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-112">By setting this property to **CenterScreen** , you're automatically displaying the form in the middle of the screen each time it loads.</span></span>

2. <span data-ttu-id="a3a7f-113">**Size** :フォームのサイズをピクセル単位で表します。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-113">**Size** : This is the size of the form, in pixels.</span></span>
   <span data-ttu-id="a3a7f-114">前述のスクリプトにより、幅 243 ピクセル、高さ 230 ピクセルのフォームが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-114">The preceding script creates a form that's 243 pixels wide by 230 pixels tall.</span></span>

3. <span data-ttu-id="a3a7f-115">**Text** :ウィンドウのタイトルになります。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-115">**Text** : This becomes the title of the window.</span></span>

4. <span data-ttu-id="a3a7f-116">**Topmost** :このプロパティを `$true` に設定すると、開いているその他のウィンドウとダイアログ ボックスの最上部にウィンドウが強制的に開きます。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-116">**Topmost** : By setting this property to `$true`, you can force the window to open atop other open windows and dialog boxes.</span></span>

<span data-ttu-id="a3a7f-117">次に、作成し、フォームに [カレンダー] コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-117">Next, create and then add a calendar control in your form.</span></span>
<span data-ttu-id="a3a7f-118">この例では、現在の日付は強調表示されておらず、丸で囲まれてもいません。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-118">In this example, the current day is not highlighted or circled.</span></span>
<span data-ttu-id="a3a7f-119">ユーザーは、予定表で 1 回に 1 日のみ選択できます。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-119">Users can select only one day on the calendar at one time.</span></span>

```powershell
$calendar = New-Object Windows.Forms.MonthCalendar -Property @{
    ShowTodayCircle   = $false
    MaxSelectionCount = 1
}
$form.Controls.Add($calendar)
```

<span data-ttu-id="a3a7f-120">次に、フォームに **[OK]** ボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-120">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="a3a7f-121">**[OK]** ボタンのサイズと動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-121">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="a3a7f-122">この例では、ボタンの位置は、フォームの上端から 165 ピクセル、左端から 38 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-122">In this example, the button position is 165 pixels from the form's top edge, and 38 pixels from the left edge.</span></span> <span data-ttu-id="a3a7f-123">ボタンの高さは 23 ピクセル、ボタンの幅は 75 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-123">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="a3a7f-124">スクリプトは、ボタンの動作を決定するために定義済みの Windows フォームの型を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-124">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```powershell
$okButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 38, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'OK'
    DialogResult = [Windows.Forms.DialogResult]::OK
}
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)
```

<span data-ttu-id="a3a7f-125">同様に、 **[キャンセル]** ボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-125">Similarly, you create a **Cancel** button.</span></span>
<span data-ttu-id="a3a7f-126">**[キャンセル]** ボタンの位置は、ウィンドウの最上部から 165 ピクセル、左端から 113 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-126">The **Cancel** button is 165 pixels from the top, but 113 pixels from the left edge of the window.</span></span>

```powershell
$cancelButton = New-Object Windows.Forms.Button -Property @{
    Location     = New-Object Drawing.Point 113, 165
    Size         = New-Object Drawing.Size 75, 23
    Text         = 'Cancel'
    DialogResult = [Windows.Forms.DialogResult]::Cancel
}
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)
```

<span data-ttu-id="a3a7f-127">次のコード行を追加して、Windows でフォームを表示します。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-127">Add the following line of code to display the form in Windows.</span></span>

```powershell
$result = $form.ShowDialog()
```

<span data-ttu-id="a3a7f-128">最後に、`if` ブロック内のコードにより、ユーザーがカレンダーで日付を選んでから、 **[OK]** ボタンをクリックするか **Enter** キーを押した後のフォームの操作を Windows に指示します。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-128">Finally, the code inside the `if` block instructs Windows what to do with the form after users select a day on the calendar, and then click the **OK** button or press the **Enter** key.</span></span> <span data-ttu-id="a3a7f-129">Windows PowerShell は、ユーザーに選択された日付を表示します。</span><span class="sxs-lookup"><span data-stu-id="a3a7f-129">Windows PowerShell displays the selected date to users.</span></span>

```powershell
if ($result -eq [Windows.Forms.DialogResult]::OK) {
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

## <a name="see-also"></a><span data-ttu-id="a3a7f-130">参照</span><span class="sxs-lookup"><span data-stu-id="a3a7f-130">See Also</span></span>

- [<span data-ttu-id="a3a7f-131">GitHub: Dave Wyatt の WinFormsExampleUpdates</span><span class="sxs-lookup"><span data-stu-id="a3a7f-131">GitHub: Dave Wyatt's WinFormsExampleUpdates</span></span>](https://github.com/dlwyatt/WinFormsExampleUpdates)
- <span data-ttu-id="a3a7f-132">[Windows PowerShell Tip of the Week: グラフィカルな日付の選択を作成する](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730942(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="a3a7f-132">[Windows PowerShell Tip of the Week:  Creating a Graphical Date Picker](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730942(v=technet.10))</span></span>
