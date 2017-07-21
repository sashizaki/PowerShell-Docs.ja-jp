---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "リスト ボックスから項目を選択する"
ms.assetid: 327c7cc5-21d0-4ace-b151-aa1491d1d3c2
ms.openlocfilehash: 39a5375b7f00c4b8332b28bf6ead011c4b21883e
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="selecting-items-from-a-list-box"></a><span data-ttu-id="f2cbf-103">リスト ボックスから項目を選択する</span><span class="sxs-lookup"><span data-stu-id="f2cbf-103">Selecting Items from a List Box</span></span>
<span data-ttu-id="f2cbf-104">Windows PowerShell 3.0 以降のリリースを使用すると、ユーザーがリスト ボックス コントロールから項目を選択できるダイアログ ボックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-104">Use Windows PowerShell 3.0 and later releases to create a dialog box that lets users select items from a list box control.</span></span>

## <a name="create-a-list-box-control-and-select-items-from-it"></a><span data-ttu-id="f2cbf-105">リスト ボックス コントロールを作成してそこから項目を選択する</span><span class="sxs-lookup"><span data-stu-id="f2cbf-105">Create a list box control, and select items from it</span></span>
<span data-ttu-id="f2cbf-106">以下を Windows PowerShell ISE にコピーしてから貼り付け、Windows PowerShell スクリプト (.ps1) として保存します。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-106">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

```
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object System.Windows.Forms.Form 
$form.Text = "Select a Computer"
$form.Size = New-Object System.Drawing.Size(300,200) 
$form.StartPosition = "CenterScreen"

$OKButton = New-Object System.Windows.Forms.Button
$OKButton.Location = New-Object System.Drawing.Point(75,120)
$OKButton.Size = New-Object System.Drawing.Size(75,23)
$OKButton.Text = "OK"
$OKButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)

$CancelButton = New-Object System.Windows.Forms.Button
$CancelButton.Location = New-Object System.Drawing.Point(150,120)
$CancelButton.Size = New-Object System.Drawing.Size(75,23)
$CancelButton.Text = "Cancel"
$CancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $CancelButton
$form.Controls.Add($CancelButton)

$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20) 
$label.Size = New-Object System.Drawing.Size(280,20) 
$label.Text = "Please select a computer:"
$form.Controls.Add($label) 

$listBox = New-Object System.Windows.Forms.ListBox 
$listBox.Location = New-Object System.Drawing.Point(10,40) 
$listBox.Size = New-Object System.Drawing.Size(260,20) 
$listBox.Height = 80

[void] $listBox.Items.Add("atl-dc-001")
[void] $listBox.Items.Add("atl-dc-002")
[void] $listBox.Items.Add("atl-dc-003")
[void] $listBox.Items.Add("atl-dc-004")
[void] $listBox.Items.Add("atl-dc-005")
[void] $listBox.Items.Add("atl-dc-006")
[void] $listBox.Items.Add("atl-dc-007")

$form.Controls.Add($listBox) 

$form.Topmost = $True

$result = $form.ShowDialog()

if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItem
    $x
}
```

<span data-ttu-id="f2cbf-107">このスクリプトは 2 つの .NET Framework クラス、つまり **System.Drawing** と **System.Windows.Forms** を最初に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-107">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms**.</span></span> <span data-ttu-id="f2cbf-108">次に、.NET Framework クラス **System.Windows.Forms.Form** の新しいインスタンスを開始します。これにより、コントロールの追加を開始する空白のフォームまたはウィンドウが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-108">You then start a new instance of the .NET Framework class **System.Windows.Forms.Form**; that provides a blank form or window to which you can start adding controls.</span></span>

```
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing
```

<span data-ttu-id="f2cbf-109">フォーム クラスのインスタンスを作成したら、このクラスの次の 3 つのプロパティに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-109">After you create an instance of the Form class, assign values to three properties of this class.</span></span>

-   <span data-ttu-id="f2cbf-110">**Text**。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-110">**Text.**</span></span> <span data-ttu-id="f2cbf-111">ウィンドウのタイトルになります。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-111">This becomes the title of the window.</span></span>

-   <span data-ttu-id="f2cbf-112">**Size**。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-112">**Size.**</span></span> <span data-ttu-id="f2cbf-113">フォームのサイズをピクセル単位で表します。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-113">This is the size of the form, in pixels.</span></span> <span data-ttu-id="f2cbf-114">前述のスクリプトにより、幅 300 ピクセル、高さ 200 ピクセルのフォームが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-114">The preceding script creates a form that’s 300 pixels wide by 200 pixels tall.</span></span>

-   <span data-ttu-id="f2cbf-115">**StartingPosition**。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-115">**StartingPosition.**</span></span> <span data-ttu-id="f2cbf-116">前述のスクリプトでは、この省略可能なプロパティは **CenterScreen** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-116">This optional property is set to **CenterScreen** in the preceding script.</span></span> <span data-ttu-id="f2cbf-117">このプロパティを追加しない場合、Windows はフォームを開いたときの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-117">If you don’t add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="f2cbf-118">**StartingPosition** を **CenterScreen** に設定すると、フォームを読み込むたびに、フォームが画面中央に自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-118">By setting the **StartingPosition** to **CenterScreen**, you’re automatically displaying the form in the middle of the screen each time it loads.</span></span>

```
$form.Text = "Select a Computer"
$form.Size = New-Object System.Drawing.Size(300,200) 
$form.StartPosition = "CenterScreen"
```

<span data-ttu-id="f2cbf-119">次に、フォームに **[OK]** ボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-119">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="f2cbf-120">**[OK]** ボタンのサイズと動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-120">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="f2cbf-121">この例では、ボタンの位置は、フォームの上端から 120 ピクセル、左端から 75 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-121">In this example, the button position is 120 pixels from the form’s top edge, and 75 pixels from the left edge.</span></span> <span data-ttu-id="f2cbf-122">ボタンの高さは 23 ピクセル、ボタンの幅は 75 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-122">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="f2cbf-123">スクリプトは、ボタンの動作を決定するために定義済みの Windows フォームの型を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-123">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```
$OKButton = New-Object System.Windows.Forms.Button
$OKButton.Location = New-Object System.Drawing.Point(75,120)
$OKButton.Size = New-Object System.Drawing.Size(75,23)
$OKButton.Text = "OK"
$OKButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)
```

<span data-ttu-id="f2cbf-124">同様に、**[キャンセル]** ボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-124">Similarly, you create a **Cancel** button.</span></span> <span data-ttu-id="f2cbf-125">**[キャンセル]** ボタンの位置は、ウィンドウの最上部から 120 ピクセル、左端から 150 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-125">The **Cancel** button is 120 pixels from the top, but 150 pixels from the left edge of the window.</span></span>

```
$CancelButton = New-Object System.Windows.Forms.Button
$CancelButton.Location = New-Object System.Drawing.Point(150,120)
$CancelButton.Size = New-Object System.Drawing.Size(75,23)
$CancelButton.Text = "Cancel"
$CancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $CancelButton
$form.Controls.Add($CancelButton)
```

<span data-ttu-id="f2cbf-126">次に、ユーザーに提供する情報を記述するラベルのテキストをウィンドウ上に用意します。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-126">Next, provide label text on your window that describes the information you want users to provide.</span></span> <span data-ttu-id="f2cbf-127">この場合は、ユーザーにコンピューターを選択してもらいます。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-127">In this case, you want users to select a computer.</span></span>

```
$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20) 
$label.Size = New-Object System.Drawing.Size(280,20) 
$label.Text = "Please select a computer:"
$form.Controls.Add($label)
```

<span data-ttu-id="f2cbf-128">ラベルのテキストに記述した情報をユーザーに提供するコントロール (この場合はリスト ボックス) を追加します。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-128">Add the control (in this case, a list box) that lets users provide the information you’ve described in your label text.</span></span> <span data-ttu-id="f2cbf-129">リスト ボックスに加えて、他に多数の適用可能なコントロールがあります。その他のコントロールについては、MSDN の「[System.Windows.Forms 名前空間](http://msdn.microsoft.com/library/k50ex0x9(v=vs.110).aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-129">There are many other controls you can apply besides list boxes; for more controls, see [System.Windows.Forms Namespace](http://msdn.microsoft.com/library/k50ex0x9(v=vs.110).aspx) on MSDN.</span></span>

```
$listBox = New-Object System.Windows.Forms.ListBox 
$listBox.Location = New-Object System.Drawing.Point(10,40) 
$listBox.Size = New-Object System.Drawing.Size(260,20) 
$listBox.Height = 80
```

<span data-ttu-id="f2cbf-130">次のセクションでは、リスト ボックスでユーザーに対して表示する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-130">In the next section, you specify the values you want the list box to display to users.</span></span>

> [!NOTE]
> <span data-ttu-id="f2cbf-131">このスクリプトによって作成されるリスト ボックスでは、1 つの選択肢のみが許可されています。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-131">The list box created by this script allows only one selection.</span></span> <span data-ttu-id="f2cbf-132">複数の選択肢を指定できるリスト ボックス コントロールを作成するには、`$listBox.SelectionMode = "MultiExtended"` と同様に **SelectionMode** プロパティの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-132">To create a list box control that allows multiple selections, specify a value for the **SelectionMode** property, similarly to the following:  `$listBox.SelectionMode = "MultiExtended"`.</span></span> <span data-ttu-id="f2cbf-133">詳しくは、「[複数選択のリスト ボックス](Multiple-selection-List-Boxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-133">For more information, see [Multiple-selection List Boxes](Multiple-selection-List-Boxes.md).</span></span>

```
[void] $listBox.Items.Add("atl-dc-001")
[void] $listBox.Items.Add("atl-dc-002")
[void] $listBox.Items.Add("atl-dc-003")
[void] $listBox.Items.Add("atl-dc-004")
[void] $listBox.Items.Add("atl-dc-005")
[void] $listBox.Items.Add("atl-dc-006")
[void] $listBox.Items.Add("atl-dc-007")
```

<span data-ttu-id="f2cbf-134">リスト ボックス コントロールをフォームに追加してから、フォームを開くときに他のウィンドウとダイアログ ボックスの最上部に開くよう、Windows に指示します。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-134">Add the list box control to your form, and instruct Windows to open the form atop other windows and dialog boxes when it’s opened.</span></span>

```
$form.Controls.Add($listBox) 
$form.Topmost = $True
```

<span data-ttu-id="f2cbf-135">次のコード行を追加して、Windows でフォームを表示します。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-135">Add the following line of code to display the form in Windows.</span></span>

```
$result = $form.ShowDialog()
```

<span data-ttu-id="f2cbf-136">最後に、**If** ブロック内のコードは、ユーザーがリスト ボックスからオプションを選択した後のフォームの操作を Windows に指示します。その後、**[OK]** ボタンをクリックするか、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-136">Finally, the code inside the **If** block instructs Windows what to do with the form after users select an option from the list box, and then click the **OK** button or press the **Enter** key.</span></span>

```
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItem
    $x
}
```

## <a name="see-also"></a><span data-ttu-id="f2cbf-137">参照</span><span class="sxs-lookup"><span data-stu-id="f2cbf-137">See Also</span></span>
- [<span data-ttu-id="f2cbf-138">Hey Scripting Guy: これらの PowerShell GUI の例が機能しないのはなぜですか。</span><span class="sxs-lookup"><span data-stu-id="f2cbf-138">Hey Scripting Guy:  Why don’t these PowerShell GUI examples work?</span></span>](http://go.microsoft.com/fwlink/?LinkId=506644)
- [<span data-ttu-id="f2cbf-139">GitHub: Dave Wyatt の WinFormsExampleUpdates</span><span class="sxs-lookup"><span data-stu-id="f2cbf-139">GitHub: Dave Wyatt's WinFormsExampleUpdates</span></span>](https://github.com/dlwyatt/WinFormsExampleUpdates)
- [<span data-ttu-id="f2cbf-140">Windows PowerShell Tip of the Week: リスト ボックスからアイテムを選択する</span><span class="sxs-lookup"><span data-stu-id="f2cbf-140">Windows PowerShell Tip of the Week:  Selecting Items from a List Box</span></span>](http://technet.microsoft.com/library/ff730949.aspx)

