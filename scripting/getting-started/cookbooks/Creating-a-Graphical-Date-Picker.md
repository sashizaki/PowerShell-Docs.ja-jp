---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "グラフィカルな日付の選択を作成する"
ms.assetid: c1cb722c-41e9-4baa-be83-59b4653222e9
ms.openlocfilehash: 5cb952264092d345945318968cf0b3028b11f3e9
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="creating-a-graphical-date-picker"></a><span data-ttu-id="b592b-103">グラフィカルな日付の選択を作成する</span><span class="sxs-lookup"><span data-stu-id="b592b-103">Creating a Graphical Date Picker</span></span>
<span data-ttu-id="b592b-104">ユーザーが日付を選択できる、グラフィカルな予定表スタイルのコントロールを備えたフォームを作成するには、Windows PowerShell 3.0 以降のリリースを使用します。</span><span class="sxs-lookup"><span data-stu-id="b592b-104">Use Windows PowerShell 3.0 and later releases to create a form with a graphical, calendar-style control that lets users select a day of the month.</span></span>

## <a name="create-a-graphical-date-picker-control"></a><span data-ttu-id="b592b-105">グラフィカルな日付の選択コントロールの作成</span><span class="sxs-lookup"><span data-stu-id="b592b-105">Create a graphical date-picker control</span></span>
<span data-ttu-id="b592b-106">以下を Windows PowerShell ISE にコピーしてから貼り付け、Windows PowerShell スクリプト (.ps1) として保存します。</span><span class="sxs-lookup"><span data-stu-id="b592b-106">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

```
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object Windows.Forms.Form 

$form.Text = "Select a Date" 
$form.Size = New-Object Drawing.Size @(243,230) 
$form.StartPosition = "CenterScreen"

$calendar = New-Object System.Windows.Forms.MonthCalendar 
$calendar.ShowTodayCircle = $False
$calendar.MaxSelectionCount = 1
$form.Controls.Add($calendar) 

$OKButton = New-Object System.Windows.Forms.Button
$OKButton.Location = New-Object System.Drawing.Point(38,165)
$OKButton.Size = New-Object System.Drawing.Size(75,23)
$OKButton.Text = "OK"
$OKButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)

$CancelButton = New-Object System.Windows.Forms.Button
$CancelButton.Location = New-Object System.Drawing.Point(113,165)
$CancelButton.Size = New-Object System.Drawing.Size(75,23)
$CancelButton.Text = "Cancel"
$CancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $CancelButton
$form.Controls.Add($CancelButton)

$form.Topmost = $True

$result = $form.ShowDialog() 

if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

<span data-ttu-id="b592b-107">このスクリプトは 2 つの .NET Framework クラス、つまり **System.Drawing** と **System.Windows.Forms** を最初に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="b592b-107">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms**.</span></span> <span data-ttu-id="b592b-108">次に、.NET Framework クラス **Windows.Forms.Form** の新しいインスタンスを開始します。これにより、コントロールの追加を開始する空白のフォームまたはウィンドウが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b592b-108">You then start a new instance of the .NET Framework class **Windows.Forms.Form**; that provides a blank form or window to which you can start adding controls.</span></span>

```
$form = New-Object Windows.Forms.Form
```

<span data-ttu-id="b592b-109">フォーム クラスのインスタンスを作成したら、このクラスの次の 3 つのプロパティに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="b592b-109">After you create an instance of the Form class, assign values to three properties of this class.</span></span>

-   <span data-ttu-id="b592b-110">**Text**。</span><span class="sxs-lookup"><span data-stu-id="b592b-110">**Text.**</span></span> <span data-ttu-id="b592b-111">ウィンドウのタイトルになります。</span><span class="sxs-lookup"><span data-stu-id="b592b-111">This becomes the title of the window.</span></span>

-   <span data-ttu-id="b592b-112">**Size**。</span><span class="sxs-lookup"><span data-stu-id="b592b-112">**Size.**</span></span> <span data-ttu-id="b592b-113">フォームのサイズをピクセル単位で表します。</span><span class="sxs-lookup"><span data-stu-id="b592b-113">This is the size of the form, in pixels.</span></span> <span data-ttu-id="b592b-114">前述のスクリプトにより、幅 243 ピクセル、高さ 230 ピクセルのフォームが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b592b-114">The preceding script creates a form that’s 243 pixels wide by 230 pixels tall.</span></span>

-   <span data-ttu-id="b592b-115">**StartingPosition**。</span><span class="sxs-lookup"><span data-stu-id="b592b-115">**StartingPosition.**</span></span> <span data-ttu-id="b592b-116">前述のスクリプトでは、この省略可能なプロパティは **CenterScreen** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="b592b-116">This optional property is set to **CenterScreen** in the preceding script.</span></span> <span data-ttu-id="b592b-117">このプロパティを追加しない場合、Windows はフォームを開いたときの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="b592b-117">If you don’t add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="b592b-118">**StartingPosition** を **CenterScreen** に設定すると、フォームを読み込むたびに、フォームが画面中央に自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b592b-118">By setting the **StartingPosition** to **CenterScreen**, you’re automatically displaying the form in the middle of the screen each time it loads.</span></span>

```
$form.Text = "Select a Date" 
$form.Size = New-Object Drawing.Size @(243,230) 
$form.StartPosition = "CenterScreen"
```

<span data-ttu-id="b592b-119">次に、作成し、フォームに [カレンダー] コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="b592b-119">Next, create and then add a calendar control in your form.</span></span> <span data-ttu-id="b592b-120">この例では、現在の日付は強調表示されておらず、丸で囲まれてもいません。</span><span class="sxs-lookup"><span data-stu-id="b592b-120">In this example, the current day is not highlighted or circled.</span></span> <span data-ttu-id="b592b-121">ユーザーは、予定表で 1 回に 1 日のみ選択できます。</span><span class="sxs-lookup"><span data-stu-id="b592b-121">Users can select only one day on the calendar at one time.</span></span>

```
$calendar = New-Object System.Windows.Forms.MonthCalendar 
$calendar.ShowTodayCircle = $False
$calendar.MaxSelectionCount = 1
$form.Controls.Add($calendar)
```

<span data-ttu-id="b592b-122">次に、フォームに **[OK]** ボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="b592b-122">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="b592b-123">**[OK]** ボタンのサイズと動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="b592b-123">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="b592b-124">この例では、ボタンの位置は、フォームの上端から 165 ピクセル、左端から 38 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="b592b-124">In this example, the button position is 165 pixels from the form’s top edge, and 38 pixels from the left edge.</span></span> <span data-ttu-id="b592b-125">ボタンの高さは 23 ピクセル、ボタンの幅は 75 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="b592b-125">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="b592b-126">スクリプトは、ボタンの動作を決定するために定義済みの Windows フォームの型を使用します。</span><span class="sxs-lookup"><span data-stu-id="b592b-126">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```
$OKButton = New-Object System.Windows.Forms.Button
$OKButton.Location = New-Object System.Drawing.Point(38,165)
$OKButton.Size = New-Object System.Drawing.Size(75,23)
$OKButton.Text = "OK"
$OKButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)
```

<span data-ttu-id="b592b-127">同様に、**[キャンセル]** ボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="b592b-127">Similarly, you create a **Cancel** button.</span></span> <span data-ttu-id="b592b-128">**[キャンセル]** ボタンの位置は、ウィンドウの最上部から 165 ピクセル、左端から 113 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="b592b-128">The **Cancel** button is 165 pixels from the top, but 113 pixels from the left edge of the window.</span></span>

```
$CancelButton = New-Object System.Windows.Forms.Button
$CancelButton.Location = New-Object System.Drawing.Point(113,165)
$CancelButton.Size = New-Object System.Drawing.Size(75,23)
$CancelButton.Text = "Cancel"
$CancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $CancelButton
$form.Controls.Add($CancelButton)
```

<span data-ttu-id="b592b-129">**Topmost** プロパティを **$True** に設定すると、開いているその他のウィンドウとダイアログ ボックスの最上部にウィンドウが強制的に開きます。</span><span class="sxs-lookup"><span data-stu-id="b592b-129">Set the **Topmost** property to **$True** to force the window to open atop other open windows and dialog boxes.</span></span>

```
$form.Topmost = $True
```

<span data-ttu-id="b592b-130">次のコード行を追加して、Windows でフォームを表示します。</span><span class="sxs-lookup"><span data-stu-id="b592b-130">Add the following line of code to display the form in Windows.</span></span>

```
$result = $form.ShowDialog()
```

<span data-ttu-id="b592b-131">最後に、**If** ブロック内のコードは、ユーザーが予定表で日付を選んだ後のフォームの操作を Windows に指示します。その後、**[OK]** ボタンをクリックするか、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="b592b-131">Finally, the code inside the **If** block instructs Windows what to do with the form after users select a day on the calendar, and then click the **OK** button or press the **Enter** key.</span></span> <span data-ttu-id="b592b-132">Windows PowerShell は、ユーザーに選択された日付を表示します。</span><span class="sxs-lookup"><span data-stu-id="b592b-132">Windows PowerShell displays the selected date to users.</span></span>

```
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $date = $calendar.SelectionStart
    Write-Host "Date selected: $($date.ToShortDateString())"
}
```

## <a name="see-also"></a><span data-ttu-id="b592b-133">参照</span><span class="sxs-lookup"><span data-stu-id="b592b-133">See Also</span></span>
- [<span data-ttu-id="b592b-134">Hey Scripting Guy: これらの PowerShell GUI の例が機能しないのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="b592b-134">Hey Scripting Guy:  Why don’t these PowerShell GUI examples work?</span></span>](http://go.microsoft.com/fwlink/?LinkId=506644)
- [<span data-ttu-id="b592b-135">GitHub: Dave Wyatt の WinFormsExampleUpdates</span><span class="sxs-lookup"><span data-stu-id="b592b-135">GitHub: Dave Wyatt's WinFormsExampleUpdates</span></span>](https://github.com/dlwyatt/WinFormsExampleUpdates)
- [<span data-ttu-id="b592b-136">Windows PowerShell Tip of the Week: グラフィカルな日付の選択を作成する</span><span class="sxs-lookup"><span data-stu-id="b592b-136">Windows PowerShell Tip of the Week:  Creating a Graphical Date Picker</span></span>](http://technet.microsoft.com/library/ff730942.aspx)

