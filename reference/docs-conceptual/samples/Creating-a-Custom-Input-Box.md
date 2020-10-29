---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: ユーザー設定の入力ボックスを作成する
description: この記事では、Windows PowerShell で .NET Framework のフォーム作成機能を使用して、カスタム入力ボックスを作成する方法を示します。
ms.openlocfilehash: 18fba743b169010936d2ea83dca4e95203664fe9
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500557"
---
# <a name="creating-a-custom-input-box"></a><span data-ttu-id="d3927-104">ユーザー設定の入力ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="d3927-104">Creating a Custom Input Box</span></span>

<span data-ttu-id="d3927-105">Windows PowerShell 3.0 以降のリリースで、Microsoft .NET Framework フォーム作成機能を使用してカスタムのグラフィカル入力ボックスをスクリプト化します。</span><span class="sxs-lookup"><span data-stu-id="d3927-105">Script a graphical custom input box by using Microsoft .NET Framework form-building features in Windows PowerShell 3.0 and later releases.</span></span>

## <a name="create-a-custom-graphical-input-box"></a><span data-ttu-id="d3927-106">カスタムのグラフィカル入力ボックスの作成</span><span class="sxs-lookup"><span data-stu-id="d3927-106">Create a custom, graphical input box</span></span>

<span data-ttu-id="d3927-107">以下を Windows PowerShell ISE にコピーしてから貼り付け、Windows PowerShell スクリプト (.ps1) として保存します。</span><span class="sxs-lookup"><span data-stu-id="d3927-107">Copy and then paste the following into Windows PowerShell ISE, and then save it as a Windows PowerShell script (.ps1).</span></span>

```powershell
Add-Type -AssemblyName System.Windows.Forms
Add-Type -AssemblyName System.Drawing

$form = New-Object System.Windows.Forms.Form
$form.Text = 'Data Entry Form'
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
$label.Text = 'Please enter the information in the space below:'
$form.Controls.Add($label)

$textBox = New-Object System.Windows.Forms.TextBox
$textBox.Location = New-Object System.Drawing.Point(10,40)
$textBox.Size = New-Object System.Drawing.Size(260,20)
$form.Controls.Add($textBox)

$form.Topmost = $true

$form.Add_Shown({$textBox.Select()})
$result = $form.ShowDialog()

if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $textBox.Text
    $x
}
```

<span data-ttu-id="d3927-108">このスクリプトは 2 つの .NET Framework クラス、つまり **System.Drawing** と **System.Windows.Forms** を最初に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="d3927-108">The script begins by loading two .NET Framework classes: **System.Drawing** and **System.Windows.Forms** .</span></span> <span data-ttu-id="d3927-109">次に、.NET Framework クラス **System.Windows.Forms.Form** の新しいインスタンスを開始します。これにより、コントロールの追加を開始する空白のフォームまたはウィンドウが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d3927-109">You then start a new instance of the .NET Framework class **System.Windows.Forms.Form** ; that provides a blank form or window to which you can start adding controls.</span></span>

```powershell
$form = New-Object System.Windows.Forms.Form
```

<span data-ttu-id="d3927-110">フォーム クラスのインスタンスを作成したら、このクラスの次の 3 つのプロパティに値を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d3927-110">After you create an instance of the Form class, assign values to three properties of this class.</span></span>

- <span data-ttu-id="d3927-111">**Text** 。</span><span class="sxs-lookup"><span data-stu-id="d3927-111">**Text.**</span></span> <span data-ttu-id="d3927-112">ウィンドウのタイトルになります。</span><span class="sxs-lookup"><span data-stu-id="d3927-112">This becomes the title of the window.</span></span>

- <span data-ttu-id="d3927-113">**Size** 。</span><span class="sxs-lookup"><span data-stu-id="d3927-113">**Size.**</span></span> <span data-ttu-id="d3927-114">フォームのサイズをピクセル単位で表します。</span><span class="sxs-lookup"><span data-stu-id="d3927-114">This is the size of the form, in pixels.</span></span> <span data-ttu-id="d3927-115">前述のスクリプトにより、幅 300 ピクセル、高さ 200 ピクセルのフォームが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d3927-115">The preceding script creates a form that's 300 pixels wide by 200 pixels tall.</span></span>

- <span data-ttu-id="d3927-116">**StartingPosition** 。</span><span class="sxs-lookup"><span data-stu-id="d3927-116">**StartingPosition.**</span></span> <span data-ttu-id="d3927-117">前述のスクリプトでは、この省略可能なプロパティは **CenterScreen** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="d3927-117">This optional property is set to **CenterScreen** in the preceding script.</span></span>
  <span data-ttu-id="d3927-118">このプロパティを追加しない場合は、Windows によりフォームが開かれる場所が選択されます。</span><span class="sxs-lookup"><span data-stu-id="d3927-118">If you don't add this property, Windows selects a location when the form is opened.</span></span> <span data-ttu-id="d3927-119">**StartingPosition** を **CenterScreen** に設定すると、フォームは読み込まれるたびに画面中央に自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d3927-119">By setting the **StartingPosition** to **CenterScreen** , you're automatically displaying the form in the middle of the screen each time it loads.</span></span>

```powershell
$form.Text = 'Data Entry Form'
$form.Size = New-Object System.Drawing.Size(300,200)
$form.StartPosition = 'CenterScreen'
```

<span data-ttu-id="d3927-120">次に、フォームに **[OK]** ボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="d3927-120">Next, create an **OK** button for your form.</span></span> <span data-ttu-id="d3927-121">**[OK]** ボタンのサイズと動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="d3927-121">Specify the size and behavior of the **OK** button.</span></span> <span data-ttu-id="d3927-122">この例では、ボタンの位置は、フォームの上端から 120 ピクセル、左端から 75 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="d3927-122">In this example, the button position is 120 pixels from the form's top edge, and 75 pixels from the left edge.</span></span> <span data-ttu-id="d3927-123">ボタンの高さは 23 ピクセル、ボタンの幅は 75 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="d3927-123">The button height is 23 pixels, while the button length is 75 pixels.</span></span> <span data-ttu-id="d3927-124">スクリプトは、ボタンの動作を決定するために定義済みの Windows フォームの型を使用します。</span><span class="sxs-lookup"><span data-stu-id="d3927-124">The script uses predefined Windows Forms types to determine the button behaviors.</span></span>

```powershell
$okButton = New-Object System.Windows.Forms.Button
$okButton.Location = New-Object System.Drawing.Point(75,120)
$okButton.Size = New-Object System.Drawing.Size(75,23)
$okButton.Text = 'OK'
$okButton.DialogResult = [System.Windows.Forms.DialogResult]::OK
$form.AcceptButton = $OKButton
$form.Controls.Add($OKButton)
```

<span data-ttu-id="d3927-125">同様に、 **[キャンセル]** ボタンを作成します。</span><span class="sxs-lookup"><span data-stu-id="d3927-125">Similarly, you create a **Cancel** button.</span></span> <span data-ttu-id="d3927-126">**[キャンセル]** ボタンの位置は、ウィンドウの最上部から 120 ピクセル、左端から 150 ピクセルです。</span><span class="sxs-lookup"><span data-stu-id="d3927-126">The **Cancel** button is 120 pixels from the top, but 150 pixels from the left edge of the window.</span></span>

```powershell
$cancelButton = New-Object System.Windows.Forms.Button
$cancelButton.Location = New-Object System.Drawing.Point(150,120)
$cancelButton.Size = New-Object System.Drawing.Size(75,23)
$cancelButton.Text = 'Cancel'
$cancelButton.DialogResult = [System.Windows.Forms.DialogResult]::Cancel
$form.CancelButton = $cancelButton
$form.Controls.Add($cancelButton)
```

<span data-ttu-id="d3927-127">次に、ユーザーに提供する情報を記述するラベルのテキストをウィンドウ上に用意します。</span><span class="sxs-lookup"><span data-stu-id="d3927-127">Next, provide label text on your window that describes the information you want users to provide.</span></span>

```powershell
$label = New-Object System.Windows.Forms.Label
$label.Location = New-Object System.Drawing.Point(10,20)
$label.Size = New-Object System.Drawing.Size(280,20)
$label.Text = 'Please enter the information in the space below:'
$form.Controls.Add($label)
```

<span data-ttu-id="d3927-128">ラベルのテキストに記述されている情報をユーザーが提供できるコントロール (この場合はテキスト ボックス) を追加します。</span><span class="sxs-lookup"><span data-stu-id="d3927-128">Add the control (in this case, a text box) that lets users provide the information you've described in your label text.</span></span> <span data-ttu-id="d3927-129">テキスト ボックスに加えて、他に多数の適用可能なコントロールがあります。その他のコントロールについては、MSDN の「[System.Windows.Forms 名前空間](/dotnet/api/system.windows.forms)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d3927-129">There are many other controls you can apply besides text boxes; for more controls, see [System.Windows.Forms Namespace](/dotnet/api/system.windows.forms) on MSDN.</span></span>

```powershell
$textBox = New-Object System.Windows.Forms.TextBox
$textBox.Location = New-Object System.Drawing.Point(10,40)
$textBox.Size = New-Object System.Drawing.Size(260,20)
$form.Controls.Add($textBox)
```

<span data-ttu-id="d3927-130">**Topmost** プロパティを **$true** に設定すると、開いているその他のウィンドウとダイアログ ボックスの最上部にウィンドウが強制的に開きます。</span><span class="sxs-lookup"><span data-stu-id="d3927-130">Set the **Topmost** property to **$true** to force the window to open atop other open windows and dialog boxes.</span></span>

```powershell
$form.Topmost = $true
```

<span data-ttu-id="d3927-131">続いて、次のコード行を追加してフォームをアクティブにするとともに、作成したテキスト ボックスにフォーカスを設定します。</span><span class="sxs-lookup"><span data-stu-id="d3927-131">Next, add this line of code to activate the form, and set the focus to the text box that you created.</span></span>

```powershell
$form.Add_Shown({$textBox.Select()})
```

<span data-ttu-id="d3927-132">次のコード行を追加して、Windows でフォームを表示します。</span><span class="sxs-lookup"><span data-stu-id="d3927-132">Add the following line of code to display the form in Windows.</span></span>

```powershell
$result = $form.ShowDialog()
```

<span data-ttu-id="d3927-133">最後に、 **If** ブロック内のコードは、ユーザーがテキスト ボックスにテキストを入力した後の Windows の動作を指示します。続いて **[OK]** ボタンをクリックするか、 **Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="d3927-133">Finally, the code inside the **If** block instructs Windows what to do with the form after users provide text in the text box, and then click the **OK** button or press the **Enter** key.</span></span>

```powershell
if ($result -eq [System.Windows.Forms.DialogResult]::OK)
{
    $x = $textBox.Text
    $x
}
```

## <a name="see-also"></a><span data-ttu-id="d3927-134">参照</span><span class="sxs-lookup"><span data-stu-id="d3927-134">See Also</span></span>

- <span data-ttu-id="d3927-135">[GitHub: Dave Wyatt の WinFormsExampleUpdates](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730941(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="d3927-135">[GitHub: Dave Wyatt's WinFormsExampleUpdates](/previous-versions/windows/it-pro/windows-powershell-1.0/ff730941(v=technet.10))</span></span>
- [<span data-ttu-id="d3927-136">Windows PowerShell Tip of the Week: ユーザー設定の入力ボックスを作成する</span><span class="sxs-lookup"><span data-stu-id="d3927-136">Windows PowerShell Tip of the Week:  Creating a Custom Input Box</span></span>](https://technet.microsoft.com/library/ff730941.aspx)
