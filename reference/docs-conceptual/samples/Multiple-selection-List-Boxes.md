---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: 複数選択のリスト ボックス
description: この記事では、Windows PowerShell で .NET Framework フォーム作成機能を使用して、複数選択のリスト ボックス コントロールを作成する方法を示します。
ms.openlocfilehash: 2724188695f054d1115b385987cda8a578c102de
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94391529"
---
# <a name="multiple-selection-list-boxes"></a><span data-ttu-id="e2c3a-104">複数選択のリスト ボックス</span><span class="sxs-lookup"><span data-stu-id="e2c3a-104">Multiple-selection List Boxes</span></span>

<span data-ttu-id="e2c3a-105">Windows PowerShell 3.0 と以降のリリースを使用すると、カスタム Windows フォームで複数選択のリスト ボックス コントロールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-105">Use Windows PowerShell 3.0 and later releases to create a multiple-selection list box control in a custom Windows Form.</span></span>

## <a name="create-list-box-controls-that-allow-multiple-selections"></a><span data-ttu-id="e2c3a-106">複数選択ができるようにするリスト ボックス コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-106">Create list box controls that allow multiple selections</span></span>

<span data-ttu-id="e2c3a-107">以下を Windows PowerShell ISE にコピーしてから貼り付け、Windows PowerShell スクリプト (.ps1) として保存します。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-107">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object System.Windows.Forms.Form
$form.Text = 'Data Entry Form'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'

$OKButton = New-Object System.Windows.Forms.Button
$OKButton.Location = New-Object System.Drawing.Point(75,120)
$OKButton.Size = New-Object System.Drawing.Size(75,23)
$OKButton.Text = 'OK'
$OKButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)

$CancelButton = New-Object System.Windows.Forms.Button
$CancelButton.Location = New-Object System.Drawing.Point(150,120)
$CancelButton.Size = New-Object System.Drawing.Size(75,23)
$CancelButton.Text = 'Cancel'
$CancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $CancelButton
$form.Controls.Add($CancelButton)

$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please make a selection from the list below:'
$form.Controls.Add($label)

$listBox = New-Object System.Windows.Forms.Listbox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)

$listBox.SelectionMode = 'MultiExtended'

[void] $listBox.Items.Add('Item 1')
[void] $listBox.Items.Add('Item 2')
[void] $listBox.Items.Add('Item 3')
[void] $listBox.Items.Add('Item 4')
[void] $listBox.Items.Add('Item 5')

$listBox.Height = 70
$form.Controls.Add($listBox)
$form.Topmost = $true

$result = $form.ShowDialog()

if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItems
    $x
}
```

<span data-ttu-id="e2c3a-108">このスクリプトは 2 つの .NET Framework クラス、つまり **System.Drawing** と **System.Windows.Forms** を最初に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-108">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms**.</span></span> <span data-ttu-id="e2c3a-109">次に、.NET Framework クラス **System.Windows.Forms.Form** の新しいインスタンスを開始します。これにより、コントロールの追加を開始する空白のフォームまたはウィンドウが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-109">You then start a new instance of the .NET Framework class **System.Windows.Forms.Form**; that provides a blank form or window to which you can start adding controls.</span></span>

```powershell
$form = New-Object System.Windows.Forms.Form
```

<span data-ttu-id="e2c3a-110">フォーム クラスのインスタンスを作成したら、このクラスの次の 3 つのプロパティに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-110">After you create an instance of the Form class, assign values to three properties of this class.</span></span>

- <span data-ttu-id="e2c3a-111">**Text**。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-111">**Text.**</span></span> <span data-ttu-id="e2c3a-112">ウィンドウのタイトルになります。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-112">This becomes the title of the window.</span></span>

- <span data-ttu-id="e2c3a-113">**Size**。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-113">**Size.**</span></span> <span data-ttu-id="e2c3a-114">フォームのサイズをピクセル単位で表します。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-114">This is the size of the form, in pixels.</span></span> <span data-ttu-id="e2c3a-115">前述のスクリプトにより、幅 300 ピクセル、高さ 200 ピクセルのフォームが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-115">The preceding script creates a form that's 300 pixels wide by 200 pixels tall.</span></span>

- <span data-ttu-id="e2c3a-116">**StartingPosition**。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-116">**StartingPosition.**</span></span> <span data-ttu-id="e2c3a-117">前述のスクリプトでは、この省略可能なプロパティは **CenterScreen** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-117">This optional property is set to **CenterScreen** in the preceding script.</span></span>
  <span data-ttu-id="e2c3a-118">このプロパティを追加しない場合は、Windows によりフォームが開かれる場所が選択されます。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-118">If you don't add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="e2c3a-119">**StartingPosition** を **CenterScreen** に設定すると、フォームは読み込まれるたびに画面中央に自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-119">By setting the **StartingPosition** to **CenterScreen**, you're automatically displaying the form in the middle of the screen each time it loads.</span></span>

```powershell
$form.Text = 'Data Entry Form'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'
```

<span data-ttu-id="e2c3a-120">次に、フォームに **[OK]** ボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-120">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="e2c3a-121">**[OK]** ボタンのサイズと動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-121">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="e2c3a-122">この例では、ボタンの位置は、フォームの上端から 120 ピクセル、左端から 75 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-122">In this example, the button position is 120 pixels from the form's top edge, and 75 pixels from the left edge.</span></span> <span data-ttu-id="e2c3a-123">ボタンの高さは 23 ピクセル、ボタンの幅は 75 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-123">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="e2c3a-124">スクリプトは、ボタンの動作を決定するために定義済みの Windows フォームの型を使用します。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-124">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```powershell
$OKButton = New-Object System.Windows.Forms.Button
$OKButton.Location = New-Object System.Drawing.Size(75,120)
$OKButton.Size = New-Object System.Drawing.Size(75,23)
$OKButton.Text = 'OK'
$OKButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)
```

<span data-ttu-id="e2c3a-125">同様に、 **[キャンセル]** ボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-125">Similarly, you create a **Cancel** button.</span></span> <span data-ttu-id="e2c3a-126">**[キャンセル]** ボタンの位置は、ウィンドウの最上部から 120 ピクセル、左端から 150 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-126">The **Cancel** button is 120 pixels from the top, but 150 pixels from the left edge of the window.</span></span>

```powershell
$CancelButton = New-Object System.Windows.Forms.Button
$CancelButton.Location = New-Object System.Drawing.Point(150,120)
$CancelButton.Size = New-Object System.Drawing.Size(75,23)
$CancelButton.Text = 'Cancel'
$CancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $CancelButton
$form.Controls.Add($CancelButton)
```

<span data-ttu-id="e2c3a-127">次に、ユーザーに提供する情報を記述するラベルのテキストをウィンドウ上に用意します。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-127">Next, provide label text on your window that describes the information you want users to provide.</span></span>

```powershell
$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please make a selection from the list below:'
$form.Controls.Add($label)
```

<span data-ttu-id="e2c3a-128">ラベルのテキストに記述されている情報をユーザーが提供できるコントロール (この場合はリスト ボックス) を追加します。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-128">Add the control (in this case, a list box) that lets users provide the information you've described in your label text.</span></span> <span data-ttu-id="e2c3a-129">テキスト ボックスに加えて、他に多数の適用可能なコントロールがあります。その他のコントロールについては、「[System.Windows.Forms 名前空間](/dotnet/api/system.windows.forms)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-129">There are many other controls you can apply besides text boxes; for more controls, see [System.Windows.Forms Namespace](/dotnet/api/system.windows.forms).</span></span>

```powershell
$listBox = New-Object System.Windows.Forms.Listbox
$listBox.Location = New-Object System.Drawing.Point(10,40)
$listBox.Size = New-Object System.Drawing.Size(260,20)
```

<span data-ttu-id="e2c3a-130">ユーザーが一覧から複数の値を選択できるよう指定する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-130">Here's how you specify that you want to allow users to select multiple values from the list.</span></span>

```powershell
$listBox.SelectionMode = 'MultiExtended'
```

<span data-ttu-id="e2c3a-131">次のセクションでは、リスト ボックスでユーザーに対して表示する値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-131">In the next section, you specify the values you want the list box to display to users.</span></span>

```powershell
[void] $listBox.Items.Add('Item 1')
[void] $listBox.Items.Add('Item 2')
[void] $listBox.Items.Add('Item 3')
[void] $listBox.Items.Add('Item 4')
[void] $listBox.Items.Add('Item 5')
```

<span data-ttu-id="e2c3a-132">リスト ボックス コントロールの高さの最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-132">Specify the maximum height of the list box control.</span></span>

```powershell
$listBox.Height = 70
```

<span data-ttu-id="e2c3a-133">リスト ボックス コントロールをフォームに追加してから、フォームを開くときに他のウィンドウやダイアログ ボックスより前面に開くよう、Windows に指示します。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-133">Add the list box control to your form, and instruct Windows to open the form atop other windows and dialog boxes when it's opened.</span></span>

```powershell
$form.Controls.Add($listBox)
$form.Topmost = $true
```

<span data-ttu-id="e2c3a-134">次のコード行を追加して、Windows でフォームを表示します。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-134">Add the following line of code to display the form in Windows.</span></span>

```powershell
$result = $form.ShowDialog()
```

<span data-ttu-id="e2c3a-135">最後に、**If** ブロック内のコードは、ユーザーがリスト ボックスから 1 つ以上のオプションを選んだ後のフォームの操作を Windows に指示します。その後、 **[OK]** ボタンをクリックするか、**Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e2c3a-135">Finally, the code inside the **If** block instructs Windows what to do with the form after users select one or more options from the list box, and then click the **OK** button or press the **Enter** key.</span></span>

```powershell
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $listBox.SelectedItems
    $x
}
```

## <a name="see-also"></a><span data-ttu-id="e2c3a-136">参照</span><span class="sxs-lookup"><span data-stu-id="e2c3a-136">See Also</span></span>

- [<span data-ttu-id="e2c3a-137">週末スクリプト作成者: PowerShell GUI の修正の例</span><span class="sxs-lookup"><span data-stu-id="e2c3a-137">Weekend Scripter: Fixing PowerShell GUI Examples</span></span>](https://devblogs.microsoft.com/scripting/weekend-scripter-fixing-powershell-gui-examples/)
- [<span data-ttu-id="e2c3a-138">GitHub: Dave Wyatt の WinFormsExampleUpdates</span><span class="sxs-lookup"><span data-stu-id="e2c3a-138">GitHub: Dave Wyatt's WinFormsExampleUpdates</span></span>](https://github.com/dlwyatt/WinFormsExampleUpdates)
- <span data-ttu-id="e2c3a-139">[Windows PowerShell Tip of the Week:オプションの複数選択リスト - その他](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730950(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="e2c3a-139">[Windows PowerShell Tip of the Week: Multi-Select List Boxes - And More!](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730950(v=technet.10))</span></span>
