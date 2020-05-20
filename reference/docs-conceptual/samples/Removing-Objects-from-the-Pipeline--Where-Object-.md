---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: パイプラインからオブジェクトを削除する (Where-Object)
ms.openlocfilehash: 370e7745341b70c0794352a690d5750d21f53ac2
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "75737187"
---
# <a name="removing-objects-from-the-pipeline-where-object"></a><span data-ttu-id="faafd-103">パイプラインからオブジェクトを削除する (Where-Object)</span><span class="sxs-lookup"><span data-stu-id="faafd-103">Removing Objects from the Pipeline (Where-Object)</span></span>

<span data-ttu-id="faafd-104">PowerShell では、考えていた数よりも多くのオブジェクトが生成され、パイプラインに渡されることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="faafd-104">In PowerShell, you often generate and pass along more objects to a pipeline than you want.</span></span> <span data-ttu-id="faafd-105">`Format-*` コマンドレットを使用して、特定のオブジェクトのプロパティを指定し、表示することができます。しかし、これはオブジェクト全体を表示から削除するという問題には役立ちません。</span><span class="sxs-lookup"><span data-stu-id="faafd-105">You can specify the properties of particular objects to display by using the `Format-*` cmdlets, but this does not help with the problem of removing entire objects from the display.</span></span> <span data-ttu-id="faafd-106">パイプラインの終了前に、オブジェクトをフィルタリングすることによって、最初に生成されたオブジェクトのサブセット上でのみアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="faafd-106">You may want to filter objects before the end of a pipeline, so you can perform actions on only a subset of the initially-generated objects.</span></span>

<span data-ttu-id="faafd-107">PowerShell には、`Where-Object` コマンドレットがあります。これを使用すると、パイプラインの各オブジェクトをテストし、特定のテスト条件を満たしている場合にのみ、オブジェクトをパイプラインに沿って渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="faafd-107">PowerShell includes a `Where-Object` cmdlet that allows you to test each object in the pipeline and only pass it along the pipeline if it meets a particular test condition.</span></span> <span data-ttu-id="faafd-108">テストを通過しなかったオブジェクトは、パイプラインから削除されます。</span><span class="sxs-lookup"><span data-stu-id="faafd-108">Objects that do not pass the test are removed from the pipeline.</span></span> <span data-ttu-id="faafd-109">テスト条件は、**FilterScript** パラメーターの値として指定します。</span><span class="sxs-lookup"><span data-stu-id="faafd-109">You supply the test condition as the value of the **FilterScript** parameter.</span></span>

## <a name="performing-simple-tests-with-where-object"></a><span data-ttu-id="faafd-110">Where-Object を使用して単純なテストを実行する</span><span class="sxs-lookup"><span data-stu-id="faafd-110">Performing Simple Tests with Where-Object</span></span>

<span data-ttu-id="faafd-111">**FilterScript** の値は、true または false に評価される*スクリプト ブロック* - (中かっこ `{}` で囲まれた 1 つまたは複数の PowerShell コマンド) です。</span><span class="sxs-lookup"><span data-stu-id="faafd-111">The value of **FilterScript** is a *script block* - one or more PowerShell commands surrounded by braces (`{}`) - that evaluates to true or false.</span></span> <span data-ttu-id="faafd-112">これらのスクリプト ブロックはごく単純にすることができますが、作成するには別の PowerShell の概念である比較演算子について知っておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="faafd-112">These script blocks can be very simple, but creating them requires knowing about another PowerShell concept, comparison operators.</span></span> <span data-ttu-id="faafd-113">比較演算子は、演算子の両辺のアイテムを比較します。</span><span class="sxs-lookup"><span data-stu-id="faafd-113">A comparison operator compares the items that appear on each side of it.</span></span> <span data-ttu-id="faafd-114">比較演算子は、ハイフン文字 (`-`) 文字で始まり、名前が続きます。</span><span class="sxs-lookup"><span data-stu-id="faafd-114">Comparison operators begin with a hyphen character (`-`) and are followed by a name.</span></span> <span data-ttu-id="faafd-115">基本的な比較演算子は、ほとんどの種類のオブジェクトで機能します。</span><span class="sxs-lookup"><span data-stu-id="faafd-115">Basic comparison operators work on almost any kind of object.</span></span> <span data-ttu-id="faafd-116">より高度な比較演算子の中には、テキストまたは配列でのみ機能するものもあります。</span><span class="sxs-lookup"><span data-stu-id="faafd-116">The more advanced comparison operators might only work on text or arrays.</span></span>

> [!NOTE]
> <span data-ttu-id="faafd-117">既定では、テキストで使用する場合、PowerShell の比較演算子は大文字小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="faafd-117">By default, when working with text, PowerShell comparison operators are case-insensitive.</span></span>

<span data-ttu-id="faafd-118">解析の考慮事項のため、`<`、`>`、`=` などのシンボルは、比較演算子として使用されません。</span><span class="sxs-lookup"><span data-stu-id="faafd-118">Due to parsing considerations, symbols such as `<`,`>`, and `=` are not used as comparison operators.</span></span> <span data-ttu-id="faafd-119">代わりに、比較演算子は文字で構成されます。</span><span class="sxs-lookup"><span data-stu-id="faafd-119">Instead, comparison operators are comprised of letters.</span></span> <span data-ttu-id="faafd-120">基本的な比較演算子を次の表に挙げます。</span><span class="sxs-lookup"><span data-stu-id="faafd-120">The basic comparison operators are listed in the following table.</span></span>

| <span data-ttu-id="faafd-121">比較演算子</span><span class="sxs-lookup"><span data-stu-id="faafd-121">Comparison Operator</span></span> |                  <span data-ttu-id="faafd-122">意味</span><span class="sxs-lookup"><span data-stu-id="faafd-122">Meaning</span></span>                   |    <span data-ttu-id="faafd-123">例 (true を返す)</span><span class="sxs-lookup"><span data-stu-id="faafd-123">Example (returns true)</span></span>    |
| ------------------- | ------------------------------------------ | ---------------------------- |
| <span data-ttu-id="faafd-124">-eq</span><span class="sxs-lookup"><span data-stu-id="faafd-124">-eq</span></span>                 | <span data-ttu-id="faafd-125">次の値と等しい</span><span class="sxs-lookup"><span data-stu-id="faafd-125">is equal to</span></span>                                | <span data-ttu-id="faafd-126">1 -eq 1</span><span class="sxs-lookup"><span data-stu-id="faafd-126">1 -eq 1</span></span>                      |
| <span data-ttu-id="faafd-127">-ne</span><span class="sxs-lookup"><span data-stu-id="faafd-127">-ne</span></span>                 | <span data-ttu-id="faafd-128">次の値と等しくない</span><span class="sxs-lookup"><span data-stu-id="faafd-128">Is not equal to</span></span>                            | <span data-ttu-id="faafd-129">1 -ne 2</span><span class="sxs-lookup"><span data-stu-id="faafd-129">1 -ne 2</span></span>                      |
| <span data-ttu-id="faafd-130">-lt</span><span class="sxs-lookup"><span data-stu-id="faafd-130">-lt</span></span>                 | <span data-ttu-id="faafd-131">次の値未満</span><span class="sxs-lookup"><span data-stu-id="faafd-131">Is less than</span></span>                               | <span data-ttu-id="faafd-132">1 -lt 2</span><span class="sxs-lookup"><span data-stu-id="faafd-132">1 -lt 2</span></span>                      |
| <span data-ttu-id="faafd-133">-le</span><span class="sxs-lookup"><span data-stu-id="faafd-133">-le</span></span>                 | <span data-ttu-id="faafd-134">次の値以下</span><span class="sxs-lookup"><span data-stu-id="faafd-134">Is less than or equal to</span></span>                   | <span data-ttu-id="faafd-135">1 -le 2</span><span class="sxs-lookup"><span data-stu-id="faafd-135">1 -le 2</span></span>                      |
| <span data-ttu-id="faafd-136">-gt</span><span class="sxs-lookup"><span data-stu-id="faafd-136">-gt</span></span>                 | <span data-ttu-id="faafd-137">次の値より大きい</span><span class="sxs-lookup"><span data-stu-id="faafd-137">Is greater than</span></span>                            | <span data-ttu-id="faafd-138">2 -gt 1</span><span class="sxs-lookup"><span data-stu-id="faafd-138">2 -gt 1</span></span>                      |
| <span data-ttu-id="faafd-139">-ge</span><span class="sxs-lookup"><span data-stu-id="faafd-139">-ge</span></span>                 | <span data-ttu-id="faafd-140">次の値以上</span><span class="sxs-lookup"><span data-stu-id="faafd-140">Is greater than or equal to</span></span>                | <span data-ttu-id="faafd-141">2 -ge 1</span><span class="sxs-lookup"><span data-stu-id="faafd-141">2 -ge 1</span></span>                      |
| <span data-ttu-id="faafd-142">-like</span><span class="sxs-lookup"><span data-stu-id="faafd-142">-like</span></span>               | <span data-ttu-id="faafd-143">次の文字列と類似 (テキストのワイルドカード比較)</span><span class="sxs-lookup"><span data-stu-id="faafd-143">Is like (wildcard comparison for text)</span></span>     | <span data-ttu-id="faafd-144">"file.doc" -like "f\*.do?"</span><span class="sxs-lookup"><span data-stu-id="faafd-144">"file.doc" -like "f\*.do?"</span></span>    |
| <span data-ttu-id="faafd-145">-notlike</span><span class="sxs-lookup"><span data-stu-id="faafd-145">-notlike</span></span>            | <span data-ttu-id="faafd-146">次の文字列と類似していない (テキストのワイルドカード比較)</span><span class="sxs-lookup"><span data-stu-id="faafd-146">Is not like (wildcard comparison for text)</span></span> | <span data-ttu-id="faafd-147">"file.doc" -notlike "p\*.doc"</span><span class="sxs-lookup"><span data-stu-id="faafd-147">"file.doc" -notlike "p\*.doc"</span></span> |
| <span data-ttu-id="faafd-148">-contains</span><span class="sxs-lookup"><span data-stu-id="faafd-148">-contains</span></span>           | <span data-ttu-id="faafd-149">Contains</span><span class="sxs-lookup"><span data-stu-id="faafd-149">Contains</span></span>                                   | <span data-ttu-id="faafd-150">1,2,3 -contains 1</span><span class="sxs-lookup"><span data-stu-id="faafd-150">1,2,3 -contains 1</span></span>            |
| <span data-ttu-id="faafd-151">-notcontains</span><span class="sxs-lookup"><span data-stu-id="faafd-151">-notcontains</span></span>        | <span data-ttu-id="faafd-152">[次の値を含まない]</span><span class="sxs-lookup"><span data-stu-id="faafd-152">Does not contain</span></span>                           | <span data-ttu-id="faafd-153">1,2,3 -notcontains 4</span><span class="sxs-lookup"><span data-stu-id="faafd-153">1,2,3 -notcontains 4</span></span>         |

<span data-ttu-id="faafd-154">`Where-Object` スクリプト ブロックは、パイプライン中の現在のオブジェクトを参照するために、特殊変数 `$_` を使用します。</span><span class="sxs-lookup"><span data-stu-id="faafd-154">`Where-Object` script blocks use the special variable `$_` to refer to the current object in the pipeline.</span></span> <span data-ttu-id="faafd-155">次に挙げるのは、その働きを示す例です。</span><span class="sxs-lookup"><span data-stu-id="faafd-155">Here is an example of how it works.</span></span> <span data-ttu-id="faafd-156">数値の一覧があり、3 未満の値だけを返したい場合、`Where-Object` を使用して、次のように入力して数値を抽出できます。</span><span class="sxs-lookup"><span data-stu-id="faafd-156">If you have a list of numbers, and only want to return the ones that are less than 3, you can use `Where-Object` to filter the numbers by typing:</span></span>

```
1,2,3,4 | Where-Object {$_ -lt 3}
1
2
```

## <a name="filtering-based-on-object-properties"></a><span data-ttu-id="faafd-157">オブジェクトのプロパティに基づくフィルタリング</span><span class="sxs-lookup"><span data-stu-id="faafd-157">Filtering Based on Object Properties</span></span>

<span data-ttu-id="faafd-158">`$_` は、現在のパイプライン オブジェクトを参照するので、テストのためにそのプロパティにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="faafd-158">Since `$_` refers to the current pipeline object, we can access its properties for our tests.</span></span>

<span data-ttu-id="faafd-159">例として、WMI の **Win32_SystemDriver** クラスを取り上げます。</span><span class="sxs-lookup"><span data-stu-id="faafd-159">As an example, we can look at the **Win32_SystemDriver** class in WMI.</span></span> <span data-ttu-id="faafd-160">特定のシステムには、何百ものシステム ドライバーが存在する可能性がありますが、関心を向けるのは、現在実行中のシステム ドライバーなど、システム ドライバーの特定のセットだけの場合があります。</span><span class="sxs-lookup"><span data-stu-id="faafd-160">There might be hundreds of system drivers on a particular system, but you might only be interested in a particular set of the system drivers, such as those which are currently running.</span></span> <span data-ttu-id="faafd-161">**Win32_SystemDriver** クラスの場合、関連するプロパティは **State** です。</span><span class="sxs-lookup"><span data-stu-id="faafd-161">For the **Win32_SystemDriver** class the relevant property is **State**.</span></span> <span data-ttu-id="faafd-162">システム ドライバーをフィルタリングして、次のように入力して実行中のドライバーのみを選択できます。</span><span class="sxs-lookup"><span data-stu-id="faafd-162">You can filter the system drivers, selecting only the running ones by typing:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq 'Running'}
```

<span data-ttu-id="faafd-163">生成されるのは、依然として長い一覧です。</span><span class="sxs-lookup"><span data-stu-id="faafd-163">This still produces a long list.</span></span> <span data-ttu-id="faafd-164">**StartMode** 値を同様にテストして、自動的に起動されるドライバーのセットのみを選択するようフィルタリングすることにします。</span><span class="sxs-lookup"><span data-stu-id="faafd-164">You may want to filter to only select the drivers set to start automatically by testing the **StartMode** value as well:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq "Running"} |
    Where-Object {$_.StartMode -eq "Auto"}
```

```Output
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
...
```

<span data-ttu-id="faafd-165">これにより、もう必要のない数多くの情報が与えられます。それらのドライバーが実行中なのはわかっています。</span><span class="sxs-lookup"><span data-stu-id="faafd-165">This gives us a lot of information we no longer need because we know that the drivers are running.</span></span>
<span data-ttu-id="faafd-166">事実、この時点でおそらく必要とされる情報は、名前と表示名だけです。</span><span class="sxs-lookup"><span data-stu-id="faafd-166">In fact, the only information we probably need at this point are the name and the display name.</span></span> <span data-ttu-id="faafd-167">次のコマンドには、それら 2 つのプロパティのみが含まれており、よりシンプルに結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="faafd-167">The following command includes only those two properties, resulting in much simpler output:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {$_.State -eq "Running"} |
    Where-Object {$_.StartMode -eq "Manual"} |
      Format-Table -Property Name,DisplayName
```

```Output
Name              DisplayName
----              -----------
AsyncMac               RAS Asynchronous Media Driver
bindflt                Windows Bind Filter Driver
bowser                 Browser
CompositeBus           Composite Bus Enumerator Driver
condrv                 Console Driver
HdAudAddService        Microsoft 1.1 UAA Function Driver for High Definition Audio Service
HDAudBus               Microsoft UAA Bus Driver for High Definition Audio
HidUsb                 Microsoft HID Class Driver
HTTP                   HTTP Service
igfx                   igfx
IntcDAud               Intel(R) Display Audio
intelppm               Intel Processor Driver
...
```

<span data-ttu-id="faafd-168">上記のコマンドには `Where-Object` 要素が 2 つありますが、次のように `-and` 論理演算子を使用して、`Where-Object` 要素 1 つで表現することができます。</span><span class="sxs-lookup"><span data-stu-id="faafd-168">There are two `Where-Object` elements in the above command, but they can be expressed in a single `Where-Object` element by using the `-and` logical operator, like this:</span></span>

```powershell
Get-CimInstance -Class Win32_SystemDriver |
  Where-Object {($_.State -eq 'Running') -and ($_.StartMode -eq 'Manual')} |
    Format-Table -Property Name,DisplayName
```

<span data-ttu-id="faafd-169">標準的な論理演算子を次の表に挙げます。</span><span class="sxs-lookup"><span data-stu-id="faafd-169">The standard logical operators are listed in the following table.</span></span>

| <span data-ttu-id="faafd-170">論理演算子</span><span class="sxs-lookup"><span data-stu-id="faafd-170">Logical Operator</span></span> |                 <span data-ttu-id="faafd-171">意味</span><span class="sxs-lookup"><span data-stu-id="faafd-171">Meaning</span></span>                  |  <span data-ttu-id="faafd-172">例 (true を返す)</span><span class="sxs-lookup"><span data-stu-id="faafd-172">Example (returns true)</span></span>  |
| ---------------- | ---------------------------------------- | ------------------------ |
| <span data-ttu-id="faafd-173">-and</span><span class="sxs-lookup"><span data-stu-id="faafd-173">-and</span></span>             | <span data-ttu-id="faafd-174">論理積。両辺が true の場合は true</span><span class="sxs-lookup"><span data-stu-id="faafd-174">Logical and; true if both sides are true</span></span> | <span data-ttu-id="faafd-175">(1 -eq 1) -and (2 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="faafd-175">(1 -eq 1) -and (2 -eq 2)</span></span> |
| <span data-ttu-id="faafd-176">-or</span><span class="sxs-lookup"><span data-stu-id="faafd-176">-or</span></span>              | <span data-ttu-id="faafd-177">論理和。どちらかの辺が true の場合は true</span><span class="sxs-lookup"><span data-stu-id="faafd-177">Logical or; true if either side is true</span></span>  | <span data-ttu-id="faafd-178">(1 -eq 1) -or (1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="faafd-178">(1 -eq 1) -or (1 -eq 2)</span></span>  |
| <span data-ttu-id="faafd-179">-not</span><span class="sxs-lookup"><span data-stu-id="faafd-179">-not</span></span>             | <span data-ttu-id="faafd-180">論理否定。true と false を逆にする</span><span class="sxs-lookup"><span data-stu-id="faafd-180">Logical not; reverses true and false</span></span>     | <span data-ttu-id="faafd-181">-not (1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="faafd-181">-not (1 -eq 2)</span></span>           |
| \!               | <span data-ttu-id="faafd-182">論理否定。true と false を逆にする</span><span class="sxs-lookup"><span data-stu-id="faafd-182">Logical not; reverses true and false</span></span>     | <span data-ttu-id="faafd-183">\!(1 -eq 2)</span><span class="sxs-lookup"><span data-stu-id="faafd-183">\!(1 -eq 2)</span></span>              |
