---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: パイプラインからオブジェクトを削除する (Where-Object)
ms.assetid: 01df8b22-2d22-4e2c-a18d-c004cd3cc284
ms.openlocfilehash: c060b93a3823be26ad6c7757acc633bb4fc2fcfa
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403261"
---
# <a name="removing-objects-from-the-pipeline-where-object"></a><span data-ttu-id="64db3-103">パイプラインからオブジェクトを削除する (Where-Object)</span><span class="sxs-lookup"><span data-stu-id="64db3-103">Removing Objects from the Pipeline (Where-Object)</span></span>

<span data-ttu-id="64db3-104">Windows PowerShell では、考えていた数よりも多くのオブジェクトが生成され、パイプラインに渡されることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="64db3-104">In Windows PowerShell, you often generate and pass along more objects to a pipeline than you want.</span></span> <span data-ttu-id="64db3-105">**Format** コマンドレットを使用して、特定のオブジェクトのプロパティを指定し、表示することができます。しかし、これはオブジェクト全体を表示から削除するという問題には役立ちません。</span><span class="sxs-lookup"><span data-stu-id="64db3-105">You can specify the properties of particular objects to display by using the **Format** cmdlets, but this does not help with the problem of removing entire objects from the display.</span></span> <span data-ttu-id="64db3-106">パイプラインの終了前に、オブジェクトをフィルタリングすることによって、最初に生成されたオブジェクトのサブセット上でのみアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="64db3-106">You may want to filter objects before the end of a pipeline, so you can perform actions on only a subset of the initially-generated objects.</span></span>

<span data-ttu-id="64db3-107">Windows PowerShell には、`Where-Object` コマンドレットがあります。これを使用すると、パイプラインの各オブジェクトをテストし、特定のテスト条件を満たしている場合にのみ、オブジェクトをパイプラインに沿って渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="64db3-107">Windows PowerShell includes a `Where-Object` cmdlet that allows you to test each object in the pipeline and only pass it along the pipeline if it meets a particular test condition.</span></span> <span data-ttu-id="64db3-108">テストを通過しなかったオブジェクトは、パイプラインから削除されます。</span><span class="sxs-lookup"><span data-stu-id="64db3-108">Objects that do not pass the test are removed from the pipeline.</span></span> <span data-ttu-id="64db3-109">テスト条件は、`Where-Object` **FilterScript** パラメーターの値として指定します。</span><span class="sxs-lookup"><span data-stu-id="64db3-109">You supply the test condition as the value of the `Where-Object` **FilterScript** parameter.</span></span>

### <a name="performing-simple-tests-with-where-object"></a><span data-ttu-id="64db3-110">Where-Object を使用して単純なテストを実行する</span><span class="sxs-lookup"><span data-stu-id="64db3-110">Performing Simple Tests with Where-Object</span></span>

<span data-ttu-id="64db3-111">**FilterScript** の値は、true または false に評価される*スクリプト ブロック* - (中かっこ {} で囲まれた 1 つまたは複数の Windows PowerShell コマンド) です。</span><span class="sxs-lookup"><span data-stu-id="64db3-111">The value of **FilterScript** is a *script block* -  one or more Windows PowerShell commands surrounded by braces {} - that evaluates to true or false.</span></span> <span data-ttu-id="64db3-112">これらのスクリプト ブロックはごく単純にすることができますが、作成するには別の Windows PowerShell の概念である比較演算子について知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="64db3-112">These script blocks can be very simple, but creating them requires knowing about another Windows PowerShell concept, comparison operators.</span></span> <span data-ttu-id="64db3-113">比較演算子は、演算子の両辺のアイテムを比較します。</span><span class="sxs-lookup"><span data-stu-id="64db3-113">A comparison operator compares the items that appear on each side of it.</span></span> <span data-ttu-id="64db3-114">比較演算子は、'-' 文字で始まり、名前が続きます。</span><span class="sxs-lookup"><span data-stu-id="64db3-114">Comparison operators begin with a '-' character and are followed by a name.</span></span> <span data-ttu-id="64db3-115">基本的な比較演算子は、ほとんどの種類のオブジェクトで機能します。</span><span class="sxs-lookup"><span data-stu-id="64db3-115">Basic comparison operators work on almost any kind of object.</span></span> <span data-ttu-id="64db3-116">より高度な比較演算子の中には、テキストまたは配列でのみ機能するものもあります。</span><span class="sxs-lookup"><span data-stu-id="64db3-116">The more advanced comparison operators might only work on text or arrays.</span></span>

> [!NOTE]
> <span data-ttu-id="64db3-117">既定では、テキストで使用する場合、Windows PowerShell の比較演算子は大文字小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="64db3-117">By default, when working with text, Windows PowerShell comparison operators are case-insensitive.</span></span>

<span data-ttu-id="64db3-118">解析の考慮事項のため、<、>、= などのシンボルは、比較演算子として使用されません。</span><span class="sxs-lookup"><span data-stu-id="64db3-118">Due to parsing considerations, symbols such as <,>, and = are not used as comparison operators.</span></span> <span data-ttu-id="64db3-119">代わりに、比較演算子は文字で構成されます。</span><span class="sxs-lookup"><span data-stu-id="64db3-119">Instead, comparison operators are comprised of letters.</span></span> <span data-ttu-id="64db3-120">基本的な比較演算子を次の表に挙げます。</span><span class="sxs-lookup"><span data-stu-id="64db3-120">The basic comparison operators are listed in the following table.</span></span>

|<span data-ttu-id="64db3-121">比較演算子</span><span class="sxs-lookup"><span data-stu-id="64db3-121">Comparison Operator</span></span>|<span data-ttu-id="64db3-122">意味</span><span class="sxs-lookup"><span data-stu-id="64db3-122">Meaning</span></span>|<span data-ttu-id="64db3-123">例 (true を返す)</span><span class="sxs-lookup"><span data-stu-id="64db3-123">Example (returns true)</span></span>|
|-----------------------|-----------|--------------------------|
|<span data-ttu-id="64db3-124">-eq</span><span class="sxs-lookup"><span data-stu-id="64db3-124">-eq</span></span>|<span data-ttu-id="64db3-125">次の値と等しい</span><span class="sxs-lookup"><span data-stu-id="64db3-125">is equal to</span></span>|<span data-ttu-id="64db3-126">1 -eq 1</span><span class="sxs-lookup"><span data-stu-id="64db3-126">1 -eq 1</span></span>|
|<span data-ttu-id="64db3-127">-ne</span><span class="sxs-lookup"><span data-stu-id="64db3-127">-ne</span></span>|<span data-ttu-id="64db3-128">次の値と等しくない</span><span class="sxs-lookup"><span data-stu-id="64db3-128">Is not equal to</span></span>|<span data-ttu-id="64db3-129">1 -ne 2</span><span class="sxs-lookup"><span data-stu-id="64db3-129">1 -ne 2</span></span>|
|<span data-ttu-id="64db3-130">-lt</span><span class="sxs-lookup"><span data-stu-id="64db3-130">-lt</span></span>|<span data-ttu-id="64db3-131">次の値未満</span><span class="sxs-lookup"><span data-stu-id="64db3-131">Is less than</span></span>|<span data-ttu-id="64db3-132">1 -lt 2</span><span class="sxs-lookup"><span data-stu-id="64db3-132">1 -lt 2</span></span>|
|<span data-ttu-id="64db3-133">-le</span><span class="sxs-lookup"><span data-stu-id="64db3-133">-le</span></span>|<span data-ttu-id="64db3-134">次の値以下</span><span class="sxs-lookup"><span data-stu-id="64db3-134">Is less than or equal to</span></span>|<span data-ttu-id="64db3-135">1 -le 2</span><span class="sxs-lookup"><span data-stu-id="64db3-135">1 -le 2</span></span>|
|<span data-ttu-id="64db3-136">-gt</span><span class="sxs-lookup"><span data-stu-id="64db3-136">-gt</span></span>|<span data-ttu-id="64db3-137">次の値より大きい</span><span class="sxs-lookup"><span data-stu-id="64db3-137">Is greater than</span></span>|<span data-ttu-id="64db3-138">2 -gt 1</span><span class="sxs-lookup"><span data-stu-id="64db3-138">2 -gt 1</span></span>|
|<span data-ttu-id="64db3-139">-ge</span><span class="sxs-lookup"><span data-stu-id="64db3-139">-ge</span></span>|<span data-ttu-id="64db3-140">次の値以上</span><span class="sxs-lookup"><span data-stu-id="64db3-140">Is greater than or equal to</span></span>|<span data-ttu-id="64db3-141">2 -ge 1</span><span class="sxs-lookup"><span data-stu-id="64db3-141">2 -ge 1</span></span>|
|<span data-ttu-id="64db3-142">-like</span><span class="sxs-lookup"><span data-stu-id="64db3-142">-like</span></span>|<span data-ttu-id="64db3-143">次の文字列と類似 (テキストのワイルドカード比較)</span><span class="sxs-lookup"><span data-stu-id="64db3-143">Is like (wildcard comparison for text)</span></span>|<span data-ttu-id="64db3-144">"file.doc" -like "f\*.do?"</span><span class="sxs-lookup"><span data-stu-id="64db3-144">"file.doc" -like "f\*.do?"</span></span>|
|<span data-ttu-id="64db3-145">-notlike</span><span class="sxs-lookup"><span data-stu-id="64db3-145">-notlike</span></span>|<span data-ttu-id="64db3-146">次の文字列と類似していない (テキストのワイルドカード比較)</span><span class="sxs-lookup"><span data-stu-id="64db3-146">Is not like (wildcard comparison for text)</span></span>|<span data-ttu-id="64db3-147">"file.doc" -notlike "p\*.doc"</span><span class="sxs-lookup"><span data-stu-id="64db3-147">"file.doc" -notlike "p\*.doc"</span></span>|
|<span data-ttu-id="64db3-148">-contains</span><span class="sxs-lookup"><span data-stu-id="64db3-148">-contains</span></span>|<span data-ttu-id="64db3-149">[内容]</span><span class="sxs-lookup"><span data-stu-id="64db3-149">Contains</span></span>|<span data-ttu-id="64db3-150">1,2,3 -contains 1</span><span class="sxs-lookup"><span data-stu-id="64db3-150">1,2,3 -contains 1</span></span>|
|<span data-ttu-id="64db3-151">-notcontains</span><span class="sxs-lookup"><span data-stu-id="64db3-151">-notcontains</span></span>|<span data-ttu-id="64db3-152">[次の値を含まない]</span><span class="sxs-lookup"><span data-stu-id="64db3-152">Does not contain</span></span>|<span data-ttu-id="64db3-153">1,2,3 -notcontains 4</span><span class="sxs-lookup"><span data-stu-id="64db3-153">1,2,3 -notcontains 4</span></span>|

<span data-ttu-id="64db3-154">Where-Object スクリプト ブロックは、パイプライン中の現在のオブジェクトを参照するために、特殊変数 `$_` を使用します。</span><span class="sxs-lookup"><span data-stu-id="64db3-154">Where-Object script blocks use the special variable `$_` to refer to the current object in the pipeline.</span></span> <span data-ttu-id="64db3-155">次に挙げるのは、その働きを示す例です。</span><span class="sxs-lookup"><span data-stu-id="64db3-155">Here is an example of how it works.</span></span> <span data-ttu-id="64db3-156">数値の一覧があり、3 未満の値だけを返したい場合、Where-Object を使用して、次のように入力して数値を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="64db3-156">If you have a list of numbers, and only want to return the ones that are less than 3, you can use Where-Object to filter the numbers by typing:</span></span>

```
PS> 1,2,3,4 | Where-Object -FilterScript {$_ -lt 3}
1
2
```

### <a name="filtering-based-on-object-properties"></a><span data-ttu-id="64db3-157">オブジェクトのプロパティに基づくフィルタリング</span><span class="sxs-lookup"><span data-stu-id="64db3-157">Filtering Based on Object Properties</span></span>

<span data-ttu-id="64db3-158">`$_` は、現在のパイプライン オブジェクトを参照するので、テストのためにそのプロパティにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="64db3-158">Since `$_` refers to the current pipeline object, we can access its properties for our tests.</span></span>

<span data-ttu-id="64db3-159">例として、WMI の Win32_SystemDriver クラスを取り上げます。</span><span class="sxs-lookup"><span data-stu-id="64db3-159">As an example, we can look at the Win32_SystemDriver class in WMI.</span></span> <span data-ttu-id="64db3-160">特定のシステムには、何百ものシステム ドライバーが存在する可能性がありますが、関心を向けるのは、現在実行中のシステム ドライバーなど、システム ドライバーの特定のセットだけの場合があります。</span><span class="sxs-lookup"><span data-stu-id="64db3-160">There might be hundreds of system drivers on a particular system, but you might only be interested in a particular set of the system drivers, such as those which are currently running.</span></span> <span data-ttu-id="64db3-161">Get-Member を使用して、Win32_SystemDriver メンバーを表示する場合 (**Get-WmiObject -Class Win32_SystemDriver | Get-Member -MemberType Property**)、関連するプロパティは State に、ドライバーが実行中であればその値は "Running" になります。</span><span class="sxs-lookup"><span data-stu-id="64db3-161">If you use Get-Member to view Win32_SystemDriver members (**Get-WmiObject -Class Win32_SystemDriver | Get-Member -MemberType Property**) you will see that the relevant property is State, and that it has a value of "Running" when the driver is running.</span></span> <span data-ttu-id="64db3-162">システム ドライバーをフィルタリングして、次のように入力して実行中のドライバーのみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="64db3-162">You can filter the system drivers, selecting only the running ones by typing:</span></span>

```powershell
Get-WmiObject -Class Win32_SystemDriver | Where-Object -FilterScript {$_.State -eq 'Running'}
```

<span data-ttu-id="64db3-163">生成されるのは、依然として長い一覧です。</span><span class="sxs-lookup"><span data-stu-id="64db3-163">This still produces a long list.</span></span> <span data-ttu-id="64db3-164">StartMode 値を同様にテストして、自動的に起動されるドライバーのセットのみを選択するようフィルタリングすることにします。</span><span class="sxs-lookup"><span data-stu-id="64db3-164">You may want to filter to only select the drivers set to start automatically by testing the StartMode value as well:</span></span>

```
PS> Get-WmiObject -Class Win32_SystemDriver | Where-Object -FilterScript {$_.State -eq "Running"} | Where-Object -FilterScript {$_.StartMode -eq "Auto"}

DisplayName : RAS Asynchronous Media Driver
Name        : AsyncMac
State       : Running
Status      : OK
Started     : True

DisplayName : Audio Stub Driver
Name        : audstub
State       : Running
Status      : OK
Started     : True
```

<span data-ttu-id="64db3-165">これにより、もう必要のない数多くの情報が与えられます。それらのドライバーが実行中なのはわかっています。</span><span class="sxs-lookup"><span data-stu-id="64db3-165">This gives us a lot of information we no longer need because we know that the drivers are running.</span></span> <span data-ttu-id="64db3-166">事実、この時点でおそらく必要とされる情報は、名前と表示名だけです。</span><span class="sxs-lookup"><span data-stu-id="64db3-166">In fact, the only information we probably need at this point are the name and the display name.</span></span> <span data-ttu-id="64db3-167">次のコマンドには、それら 2 つのプロパティのみが含まれており、よりシンプルに結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="64db3-167">The following command includes only those two properties, resulting in much simpler output:</span></span>

```
PS> Get-WmiObject -Class Win32_SystemDriver | Where-Object -FilterScript {$_.State -eq "Running"} | Where-Object -FilterScript {$_.StartMode -eq "Manual"} | Format-Table -Property Name,DisplayName

Name                                    DisplayName
----                                    -----------
AsyncMac                                RAS Asynchronous Media Driver
Fdc                                     Floppy Disk Controller Driver
Flpydisk                                Floppy Disk Driver
Gpc                                     Generic Packet Classifier
IpNat                                   IP Network Address Translator
mouhid                                  Mouse HID Driver
MRxDAV                                  WebDav Client Redirector
mssmbios                                Microsoft System Management BIOS Driver
```

<span data-ttu-id="64db3-168">上記のコマンドには Where-Object 要素が 2 つありますが、次のように -and 論理演算子を使用して、Where-Object 要素 1 つで表現することができます。</span><span class="sxs-lookup"><span data-stu-id="64db3-168">There are two Where-Object elements in the above command, but they can be expressed in a single Where-Object element by using the -and logical operator, like this:</span></span>

```powershell
Get-WmiObject -Class Win32_SystemDriver | Where-Object -FilterScript { ($_.State -eq 'Running') -and ($_.StartMode -eq 'Manual') } | Format-Table -Property Name,DisplayName
```

<span data-ttu-id="64db3-169">標準的な論理演算子を次の表に挙げます。</span><span class="sxs-lookup"><span data-stu-id="64db3-169">The standard logical operators are listed in the following table.</span></span>

|<span data-ttu-id="64db3-170">論理演算子</span><span class="sxs-lookup"><span data-stu-id="64db3-170">Logical Operator</span></span>|<span data-ttu-id="64db3-171">意味</span><span class="sxs-lookup"><span data-stu-id="64db3-171">Meaning</span></span>|<span data-ttu-id="64db3-172">例 (true を返す)</span><span class="sxs-lookup"><span data-stu-id="64db3-172">Example (returns true)</span></span>|
|--------------------|-----------|--------------------------|
|<span data-ttu-id="64db3-173">-and</span><span class="sxs-lookup"><span data-stu-id="64db3-173">-and</span></span>|<span data-ttu-id="64db3-174">論理積。両辺が true の場合は true</span><span class="sxs-lookup"><span data-stu-id="64db3-174">Logical and; true if both sides are true</span></span>|<span data-ttu-id="64db3-175">(1 -eq 1) -and (2 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="64db3-175">(1 -eq 1) -and (2 -eq 2)</span></span>|
|<span data-ttu-id="64db3-176">-or</span><span class="sxs-lookup"><span data-stu-id="64db3-176">-or</span></span>|<span data-ttu-id="64db3-177">論理和。どちらかの辺が true の場合は true</span><span class="sxs-lookup"><span data-stu-id="64db3-177">Logical or; true if either side is true</span></span>|<span data-ttu-id="64db3-178">(1 -eq 1) -or (1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="64db3-178">(1 -eq 1) -or (1 -eq 2)</span></span>|
|<span data-ttu-id="64db3-179">-not</span><span class="sxs-lookup"><span data-stu-id="64db3-179">-not</span></span>|<span data-ttu-id="64db3-180">論理否定。true と false を逆にする</span><span class="sxs-lookup"><span data-stu-id="64db3-180">Logical not; reverses true and false</span></span>|<span data-ttu-id="64db3-181">-not (1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="64db3-181">-not (1 -eq 2)</span></span>|
|\!|<span data-ttu-id="64db3-182">論理否定。true と false を逆にする</span><span class="sxs-lookup"><span data-stu-id="64db3-182">Logical not; reverses true and false</span></span>|<span data-ttu-id="64db3-183">\!(1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="64db3-183">\!(1 -eq 2)</span></span>|
