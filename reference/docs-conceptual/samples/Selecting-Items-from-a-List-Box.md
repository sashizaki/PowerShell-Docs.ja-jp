---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: リスト ボックスから項目を選択する
description: この記事では、Windows PowerShell で .NET Framework のフォーム作成機能を使用して、リスト ボックス コントロールを作成する方法を示します。
ms.openlocfilehash: d6f881f0b92f294da105ae7df5e25e8c20ce5094
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391240"
---
# <a name="selecting-items-from-a-list-box"></a><span data-ttu-id="3be92-104">リスト ボックスから項目を選択する</span><span class="sxs-lookup"><span data-stu-id="3be92-104">Selecting Items from a List Box</span></span>

<span data-ttu-id="3be92-105">Windows PowerShell 3.0 以降のリリースを使用すると、ユーザーがリスト ボックス コントロールから項目を選択できるダイアログ ボックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3be92-105">Use Windows PowerShell 3.0 and later releases to create a dialog box that lets users select items from a list box control.</span></span>

## <a name="create-a-list-box-control-and-select-items-from-it"></a><span data-ttu-id="3be92-106">リスト ボックス コントロールを作成してそこから項目を選択する</span><span class="sxs-lookup"><span data-stu-id="3be92-106">Create a list box control, and select items from it</span></span>

<span data-ttu-id="3be92-107">以下を Windows PowerShell ISE にコピーしてから貼り付け、Windows PowerShell スクリプト (.ps1) として保存します。</span><span class="sxs-lookup"><span data-stu-id="3be92-107">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object System.Windows.Forms.Form
$form.Text = 'Select a Computer'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'

$okButton = New-Object System.Windows.Forms.Button
$okButton.Location = New-Object System.Drawing.Point(75,120)
$okButton.Size = New-Object System.Drawing.Size(75,23)
$okButton.Text = 'OK'
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)

$cancelButton = New-Object System.Windows.Forms.Button
$cancelButton.Location = New-Object System.Drawing.Point(150,120)
$cancelButton.Size = New-Object System.Drawing.Size(75,23)
$cancelButton.Text = 'Cancel'
$cancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)

$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please select a computer:'
$form.Controls.Add($label)

$listBox = New-Object System.Windows.Forms.ListBox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)
$listBox.Height = 80

[void] $listBox.Items.Add('atl-dc-001')
[void] $listBox.Items.Add('atl-dc-002')
[void] $listBox.Items.Add('atl-dc-003')
[void] $listBox.Items.Add('atl-dc-004')
[void] $listBox.Items.Add('atl-dc-005')
[void] $listBox.Items.Add('atl-dc-006')
[void] $listBox.Items.Add('atl-dc-007')

$form.Controls.Add($listBox)

$form.Topmost = $true

$result = $form.ShowDialog()

if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItem
    $x
}
```

<span data-ttu-id="3be92-108">このスクリプトは 2 つの .NET Framework クラス、つまり **System.Drawing** と **System.Windows.Forms** を最初に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="3be92-108">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms**.</span></span> <span data-ttu-id="3be92-109">次に、.NET Framework クラス **System.Windows.Forms.Form** の新しいインスタンスを開始します。これにより、コントロールの追加を開始する空白のフォームまたはウィンドウが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3be92-109">You then start a new instance of the .NET Framework class **System.Windows.Forms.Form**; that provides a blank form or window to which you can start adding controls.</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing
```

<span data-ttu-id="3be92-110">フォーム クラスのインスタンスを作成したら、このクラスの次の 3 つのプロパティに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3be92-110">After you create an instance of the Form class, assign values to three properties of this class.</span></span>

- <span data-ttu-id="3be92-111">**Text**。</span><span class="sxs-lookup"><span data-stu-id="3be92-111">**Text.**</span></span> <span data-ttu-id="3be92-112">ウィンドウのタイトルになります。</span><span class="sxs-lookup"><span data-stu-id="3be92-112">This becomes the title of the window.</span></span>

- <span data-ttu-id="3be92-113">**Size**。</span><span class="sxs-lookup"><span data-stu-id="3be92-113">**Size.**</span></span> <span data-ttu-id="3be92-114">フォームのサイズをピクセル単位で表します。</span><span class="sxs-lookup"><span data-stu-id="3be92-114">This is the size of the form, in pixels.</span></span> <span data-ttu-id="3be92-115">前述のスクリプトにより、幅 300 ピクセル、高さ 200 ピクセルのフォームが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3be92-115">The preceding script creates a form that's 300 pixels wide by 200 pixels tall.</span></span>

- <span data-ttu-id="3be92-116">**StartingPosition**。</span><span class="sxs-lookup"><span data-stu-id="3be92-116">**StartingPosition.**</span></span> <span data-ttu-id="3be92-117">前述のスクリプトでは、この省略可能なプロパティは **CenterScreen** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="3be92-117">This optional property is set to **CenterScreen** in the preceding script.</span></span>
  <span data-ttu-id="3be92-118">このプロパティを追加しない場合は、Windows によりフォームが開かれる場所が選択されます。</span><span class="sxs-lookup"><span data-stu-id="3be92-118">If you don't add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="3be92-119">**StartingPosition** を **CenterScreen** に設定すると、フォームは読み込まれるたびに画面中央に自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3be92-119">By setting the **StartingPosition** to **CenterScreen**, you're automatically displaying the form in the middle of the screen each time it loads.</span></span>

```powershell
$form.Text = 'Select a Computer'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'
```

<span data-ttu-id="3be92-120">次に、フォームに **[OK]** ボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="3be92-120">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="3be92-121">**[OK]** ボタンのサイズと動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="3be92-121">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="3be92-122">この例では、ボタンの位置は、フォームの上端から 120 ピクセル、左端から 75 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="3be92-122">In this example, the button position is 120 pixels from the form's top edge, and 75 pixels from the left edge.</span></span> <span data-ttu-id="3be92-123">ボタンの高さは 23 ピクセル、ボタンの幅は 75 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="3be92-123">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="3be92-124">スクリプトは、ボタンの動作を決定するために定義済みの Windows フォームの型を使用します。</span><span class="sxs-lookup"><span data-stu-id="3be92-124">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```powershell
$okButton = New-Object System.Windows.Forms.Button
$okButton.Location = New-Object System.Drawing.Point(75,120)
$okButton.Size = New-Object System.Drawing.Size(75,23)
$okButton.Text = 'OK'
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $okButton
$form.Controls.Add($okButton)
```

<span data-ttu-id="3be92-125">同様に、 **[キャンセル]** ボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="3be92-125">Similarly, you create a **Cancel** button.</span></span> <span data-ttu-id="3be92-126">**[キャンセル]** ボタンの位置は、ウィンドウの最上部から 120 ピクセル、左端から 150 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="3be92-126">The **Cancel** button is 120 pixels from the top, but 150 pixels from the left edge of the window.</span></span>

```powershell
$cancelButton = New-Object System.Windows.Forms.Button
$cancelButton.Location = New-Object System.Drawing.Point(150,120)
$cancelButton.Size = New-Object System.Drawing.Size(75,23)
$cancelButton.Text = 'Cancel'
$cancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)
```

<span data-ttu-id="3be92-127">次に、ユーザーに提供する情報を記述するラベルのテキストをウィンドウ上に用意します。</span><span class="sxs-lookup"><span data-stu-id="3be92-127">Next, provide label text on your window that describes the information you want users to provide.</span></span> <span data-ttu-id="3be92-128">この場合は、ユーザーにコンピューターを選択してもらいます。</span><span class="sxs-lookup"><span data-stu-id="3be92-128">In this case, you want users to select a computer.</span></span>

```powershell
$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please select a computer:'
$form.Controls.Add($label)
```

<span data-ttu-id="3be92-129">ラベルのテキストに記述されている情報をユーザーが提供できるコントロール (この場合はリスト ボックス) を追加します。</span><span class="sxs-lookup"><span data-stu-id="3be92-129">Add the control (in this case, a list box) that lets users provide the information you've described in your label text.</span></span> <span data-ttu-id="3be92-130">リスト ボックスに加えて、他に多数の適用可能なコントロールがあります。その他のコントロールについては、「[System.Windows.Forms 名前空間](/dotnet/api/system.windows.forms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be92-130">There are many other controls you can apply besides list boxes; for more controls, see [System.Windows.Forms Namespace](/dotnet/api/system.windows.forms).</span></span>

```powershell
$listBox = New-Object System.Windows.Forms.ListBox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)
$listBox.Height = 80
```

<span data-ttu-id="3be92-131">次のセクションでは、リスト ボックスでユーザーに対して表示する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="3be92-131">In the next section, you specify the values you want the list box to display to users.</span></span>

> [!NOTE]
> <span data-ttu-id="3be92-132">このスクリプトによって作成されるリスト ボックスでは、1 つの選択肢のみが許可されています。</span><span class="sxs-lookup"><span data-stu-id="3be92-132">The list box created by this script allows only one selection.</span></span> <span data-ttu-id="3be92-133">複数選択が可能なリスト ボックス コントロールを作成するには、次のように **SelectionMode** プロパティの値を指定します: `$listBox.SelectionMode = 'MultiExtended'`。</span><span class="sxs-lookup"><span data-stu-id="3be92-133">To create a list box control that allows multiple selections, specify a value for the **SelectionMode** property, similarly to the following: `$listBox.SelectionMode = 'MultiExtended'`.</span></span> <span data-ttu-id="3be92-134">詳しくは、「[複数選択のリスト ボックス](Multiple-selection-List-Boxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be92-134">For more information, see [Multiple-selection List Boxes](Multiple-selection-List-Boxes.md).</span></span>

```powershell
[void] $listBox.Items.Add('atl-dc-001')
[void] $listBox.Items.Add('atl-dc-002')
[void] $listBox.Items.Add('atl-dc-003')
[void] $listBox.Items.Add('atl-dc-004')
[void] $listBox.Items.Add('atl-dc-005')
[void] $listBox.Items.Add('atl-dc-006')
[void] $listBox.Items.Add('atl-dc-007')
```

<span data-ttu-id="3be92-135">リスト ボックス コントロールをフォームに追加してから、フォームを開くときに他のウィンドウやダイアログ ボックスより前面に開くよう、Windows に指示します。</span><span class="sxs-lookup"><span data-stu-id="3be92-135">Add the list box control to your form, and instruct Windows to open the form atop other windows and dialog boxes when it's opened.</span></span>

```powershell
$form.Controls.Add($listBox)
$form.Topmost = $true
```

<span data-ttu-id="3be92-136">次のコード行を追加して、Windows でフォームを表示します。</span><span class="sxs-lookup"><span data-stu-id="3be92-136">Add the following line of code to display the form in Windows.</span></span>

```powershell
$result = $form.ShowDialog()
```

<span data-ttu-id="3be92-137">最後に、**If** ブロック内のコードは、ユーザーがリスト ボックスからオプションを選択した後のフォームの操作を Windows に指示します。その後、**[OK]** ボタンをクリックするか、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3be92-137">Finally, the code inside the **If** block instructs Windows what to do with the form after users select an option from the list box, and then click the **OK** button or press the **Enter** key.</span></span>

```powershell
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItem
    $x
}
```

## <a name="see-also"></a><span data-ttu-id="3be92-138">参照</span><span class="sxs-lookup"><span data-stu-id="3be92-138">See Also</span></span>

- [<span data-ttu-id="3be92-139">GitHub: Dave Wyatt の WinFormsExampleUpdates</span><span class="sxs-lookup"><span data-stu-id="3be92-139">GitHub: Dave Wyatt's WinFormsExampleUpdates</span></span>](https://github.com/dlwyatt/WinFormsExampleUpdates)
- <span data-ttu-id="3be92-140">[Windows PowerShell Tip of the Week:リスト ボックスから項目を選択する](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730949(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="3be92-140">[Windows PowerShell Tip of the Week: Selecting Items from a List Box](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730949(v=technet.10))</span></span>
