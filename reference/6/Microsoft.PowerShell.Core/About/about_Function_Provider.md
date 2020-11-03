---
description: 機能
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_function_provider?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: 関数プロバイダー
ms.openlocfilehash: 0323433d5ab9114dd1bb21afc47b7fa7db3d6f8f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221616"
---
# <a name="function-provider"></a><span data-ttu-id="4b3c8-104">関数プロバイダー</span><span class="sxs-lookup"><span data-stu-id="4b3c8-104">Function provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="4b3c8-105">プロバイダー名</span><span class="sxs-lookup"><span data-stu-id="4b3c8-105">Provider name</span></span>
<span data-ttu-id="4b3c8-106">機能</span><span class="sxs-lookup"><span data-stu-id="4b3c8-106">Function</span></span>

## <a name="drives"></a><span data-ttu-id="4b3c8-107">ドライブ</span><span class="sxs-lookup"><span data-stu-id="4b3c8-107">Drives</span></span>

`Function:`

## <a name="capabilities"></a><span data-ttu-id="4b3c8-108">機能</span><span class="sxs-lookup"><span data-stu-id="4b3c8-108">Capabilities</span></span>

<span data-ttu-id="4b3c8-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="4b3c8-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="4b3c8-110">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="4b3c8-110">Short description</span></span>

<span data-ttu-id="4b3c8-111">PowerShell で定義されている関数へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-111">Provides access to the functions defined in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="4b3c8-112">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="4b3c8-112">Detailed description</span></span>

<span data-ttu-id="4b3c8-113">Powershell **関数** プロバイダーを使用すると、powershell で関数とフィルターを取得、追加、変更、消去、削除できます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-113">The PowerShell **Function** provider lets you get, add, change, clear, and delete the functions and filters in PowerShell.</span></span>

<span data-ttu-id="4b3c8-114">関数とは、アクションを実行するコードのブロックに名前が付けられたものです。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-114">A function is a named block of code that performs an action.</span></span> <span data-ttu-id="4b3c8-115">関数名を入力すると、関数のコードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-115">When you type the function name, the code in the function runs.</span></span> <span data-ttu-id="4b3c8-116">フィルターとは、アクションの条件を確立するコードのブロックに名前が付けられたものです。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-116">A filter is a named block of code that establishes conditions for an action.</span></span> <span data-ttu-id="4b3c8-117">コマンドのように、条件の代わりにフィルターの名前を入力でき `Where-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-117">You can type the name of the filter in place of the condition, such as in a `Where-Object` command.</span></span>

<span data-ttu-id="4b3c8-118">**関数** ドライブは、関数オブジェクトとフィルターオブジェクトのみを含むフラットな名前空間です。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-118">The **Function** drive is a flat namespace that contains only the function and filter objects.</span></span> <span data-ttu-id="4b3c8-119">関数にもフィルターにも子項目はありません。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-119">Neither functions nor filters have child items.</span></span>

<span data-ttu-id="4b3c8-120">**関数** プロバイダーは、この記事で説明されている次のコマンドレットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-120">The **Function** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="4b3c8-121">Get-Location</span><span class="sxs-lookup"><span data-stu-id="4b3c8-121">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="4b3c8-122">Set-Location</span><span class="sxs-lookup"><span data-stu-id="4b3c8-122">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="4b3c8-123">Get-Item</span><span class="sxs-lookup"><span data-stu-id="4b3c8-123">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="4b3c8-124">New-Item</span><span class="sxs-lookup"><span data-stu-id="4b3c8-124">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="4b3c8-125">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="4b3c8-125">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="4b3c8-126">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="4b3c8-126">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="4b3c8-127">このプロバイダーによって公開される型</span><span class="sxs-lookup"><span data-stu-id="4b3c8-127">Types exposed by this provider</span></span>

<span data-ttu-id="4b3c8-128">それぞれの関数は、system.servicemodel クラスのインスタンスに[なります。](/dotnet/api/system.management.automation.functioninfo)</span><span class="sxs-lookup"><span data-stu-id="4b3c8-128">Each function is an instance of the [System.Management.Automation.FunctionInfo](/dotnet/api/system.management.automation.functioninfo) class.</span></span> <span data-ttu-id="4b3c8-129">各フィルターは、 [System. Automation. FilterInfo](/dotnet/api/system.management.automation.filterinfo) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-129">Each filter is an instance of the [System.Management.Automation.FilterInfo](/dotnet/api/system.management.automation.filterinfo) class.</span></span>

## <a name="navigating-the-function-drive"></a><span data-ttu-id="4b3c8-130">関数ドライブの移動</span><span class="sxs-lookup"><span data-stu-id="4b3c8-130">Navigating the Function drive</span></span>

<span data-ttu-id="4b3c8-131">**関数** プロバイダーは、ドライブ内のデータストアを公開し `Function:` ます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-131">The **Function** provider exposes its data store in the `Function:` drive.</span></span> <span data-ttu-id="4b3c8-132">関数を操作するには、場所を `Function:` ドライブ () に変更し `Set-Location Function:` ます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-132">To work with functions, you can change your location to the `Function:` drive (`Set-Location Function:`).</span></span> <span data-ttu-id="4b3c8-133">または、別の PowerShell ドライブから作業することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-133">Or, you can work from another PowerShell drive.</span></span> <span data-ttu-id="4b3c8-134">別の場所から関数を参照するには、パスのドライブ名 () を使用し `Function:` ます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-134">To reference a function from another location, use the drive name (`Function:`) in the path.</span></span>

```powershell
Set-Location Function:
```

<span data-ttu-id="4b3c8-135">ファイル システム ドライブに戻るには、ドライブ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-135">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="4b3c8-136">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-136">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="4b3c8-137">また、その他の PowerShell ドライブから **関数** プロバイダーを操作することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-137">You can also work with the **Function** provider from any other PowerShell drive.</span></span> <span data-ttu-id="4b3c8-138">別の場所から関数を参照するには、パス内のドライブ名を使用し `Function:` ます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-138">To reference an function from another location, use the drive name `Function:` in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="4b3c8-139">PowerShell では、エイリアスを使用して、プロバイダーパスを操作するための使い慣れた方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-139">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="4b3c8-140">`dir`やなどのコマンド `ls` は、 [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem)のエイリアスです。これ `cd` は、 [Set Location](xref:Microsoft.PowerShell.Management.Set-Location)のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-140">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="4b3c8-141">と `pwd` は、 [Get Location](xref:Microsoft.PowerShell.Management.Get-Location)のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-141">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="getting-functions"></a><span data-ttu-id="4b3c8-142">関数の取得</span><span class="sxs-lookup"><span data-stu-id="4b3c8-142">Getting functions</span></span>

<span data-ttu-id="4b3c8-143">このコマンドは現在のセッションのすべての関数の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-143">This command gets the list of all the functions in the current session.</span></span> <span data-ttu-id="4b3c8-144">このコマンドは、任意の PowerShell ドライブから使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-144">You can use this command from any PowerShell drive.</span></span>

```powershell
Get-ChildItem -Path Function:
```

<span data-ttu-id="4b3c8-145">関数プロバイダーにはコンテナーがないため、上のコマンドはと共に使用した場合と同じ効果があり `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-145">The Function provider has no containers, so the above command has the same effect when used with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path Function:
```

<span data-ttu-id="4b3c8-146">次に示すように、 **定義** プロパティにアクセスすることによって、関数の定義を取得できます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-146">You can retrieve a function's definition by accessing the **Definition** property, as shown below.</span></span>

```powershell
(Get-Item -Path function:more).Definition
```

<span data-ttu-id="4b3c8-147">また、ドル記号 () で始まるプロバイダーパスを使用して、関数の定義を取得することもでき `$` ます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-147">You can also retrieve a function's definition using its provider path prefixed by the dollar sign (`$`).</span></span>

```powershell
$function:more
```

### <a name="getting-selected-functions"></a><span data-ttu-id="4b3c8-148">選択した関数の取得</span><span class="sxs-lookup"><span data-stu-id="4b3c8-148">Getting selected functions</span></span>

<span data-ttu-id="4b3c8-149">このコマンドは、 `man` ドライブから関数を取得し `Function:` ます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-149">This command gets the `man` function from the `Function:` drive.</span></span> <span data-ttu-id="4b3c8-150">コマンドレットを使用して `Get-Item` 関数を取得します。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-150">It uses the `Get-Item` cmdlet to get the function.</span></span> <span data-ttu-id="4b3c8-151">パイプライン演算子 () は、 `|` 結果をに送信し `Format-Table` ます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-151">The pipeline operator (`|`) sends the result to `Format-Table`.</span></span> <span data-ttu-id="4b3c8-152">パラメーターは、 `-Wrap` 行に収まりきらないテキストを次の行にリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-152">The `-Wrap` parameter directs text that does not fit on the line onto the next line.</span></span> <span data-ttu-id="4b3c8-153">パラメーターを指定すると、 `-Autosize` テーブルの列のサイズがテキストに合わせて変更されます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-153">The `-Autosize` parameter resizes the table columns to accommodate the text.</span></span>

```powershell
Get-Item -Path man | Format-Table -Wrap -Autosize
```

### <a name="working-with-function-provider-paths"></a><span data-ttu-id="4b3c8-154">関数プロバイダーパスの操作</span><span class="sxs-lookup"><span data-stu-id="4b3c8-154">Working with Function provider paths</span></span>

<span data-ttu-id="4b3c8-155">これらのコマンドはどちらもという名前の関数を取得 `c:` します。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-155">These commands both get the function named `c:`.</span></span> <span data-ttu-id="4b3c8-156">最初のコマンドはすべてのドライブで使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-156">The first command can be used in any drive.</span></span> <span data-ttu-id="4b3c8-157">2番目のコマンドはドライブで使用され `Function:` ます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-157">The second command is used in the `Function:` drive.</span></span> <span data-ttu-id="4b3c8-158">ドライブの構文であり、名前がコロンで終わるため、ドライブ名でパスを修飾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-158">Because the name ends in a colon, which is the syntax for a drive, you must qualify the path with the drive name.</span></span> <span data-ttu-id="4b3c8-159">ドライブ内では、どちらの形式でも `Function:` 使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-159">Within the `Function:` drive, you can use either format.</span></span> <span data-ttu-id="4b3c8-160">2番目のコマンドでは、ドット ( `.` ) は現在の場所を表します。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-160">In the second command, the dot (`.`) represents the current location.</span></span>

```
PS C:\> Get-Item -Path Function:c:
PS Function:\> Get-Item -Path .\c:
```

## <a name="creating-a-function"></a><span data-ttu-id="4b3c8-161">関数の作成</span><span class="sxs-lookup"><span data-stu-id="4b3c8-161">Creating a function</span></span>

<span data-ttu-id="4b3c8-162">このコマンドは、コマンドレットを使用して `New-Item` 、という名前の関数を作成 `Win32:` します。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-162">This command uses the `New-Item` cmdlet to create a function called `Win32:`.</span></span>
<span data-ttu-id="4b3c8-163">括弧で囲まれた式は関数名により表されるスクリプト ブロックです。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-163">The expression in braces is the script block that is represented by the function name.</span></span>

```powershell
New-Item -Path Function:Win32: -Value {Set-Location C:\Windows\System32}
```

<span data-ttu-id="4b3c8-164">関数は、PowerShell コマンドラインで入力することによって作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-164">You can also create a function by typing it at the PowerShell command line.</span></span> <span data-ttu-id="4b3c8-165">たとえば、tpe `Function:Win32: {Set-Location C:\Windows\System32}` です。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-165">For example, tpe `Function:Win32: {Set-Location C:\Windows\System32}`.</span></span> <span data-ttu-id="4b3c8-166">ドライブにいる場合は、 `Function:` ドライブ名を省略できます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-166">If you are in the `Function:` drive, you can omit the drive name.</span></span>

## <a name="deleting-a-function"></a><span data-ttu-id="4b3c8-167">関数の削除</span><span class="sxs-lookup"><span data-stu-id="4b3c8-167">Deleting a function</span></span>

<span data-ttu-id="4b3c8-168">このコマンドは、 `more:` 現在のセッションから関数を削除します。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-168">This command deletes the `more:` function from the current session.</span></span>

```powershell
Remove-Item Function:more:
```

## <a name="changing-a-function"></a><span data-ttu-id="4b3c8-169">関数の変更</span><span class="sxs-lookup"><span data-stu-id="4b3c8-169">Changing a function</span></span>

<span data-ttu-id="4b3c8-170">このコマンドは、 `Set-Item` コマンドレットを使用して、 `prompt` パスの前の時間を表示するように関数を変更します。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-170">This command uses the `Set-Item` cmdlet to change the `prompt` function so that it displays the time before the path.</span></span>

```powershell
Set-Item -Path Function:prompt -Value {
  'PS '+ (Get-Date -Format t) + " " + (Get-Location) + '> '
  }
```

### <a name="rename-a-function"></a><span data-ttu-id="4b3c8-171">関数の名前を変更する</span><span class="sxs-lookup"><span data-stu-id="4b3c8-171">Rename a function</span></span>

<span data-ttu-id="4b3c8-172">このコマンドは、コマンドレットを使用して `Rename-Item` 関数の名前をに変更し `help` `gh` ます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-172">This command uses the `Rename-Item` cmdlet to change the name of the `help` function to `gh`.</span></span>

```powershell
Rename-Item -Path Function:help -NewName gh
```

## <a name="copying-a-function"></a><span data-ttu-id="4b3c8-173">関数のコピー</span><span class="sxs-lookup"><span data-stu-id="4b3c8-173">Copying a function</span></span>

<span data-ttu-id="4b3c8-174">このコマンドは、 `prompt` 関数をにコピーし `oldPrompt` 、prompt 関数に関連付けられているスクリプトブロックの新しい名前を効果的に作成します。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-174">This command copies the `prompt` function to `oldPrompt`, effectively creating a new name for the script block that is associated with the prompt function.</span></span>
<span data-ttu-id="4b3c8-175">これを利用し、変更予定のプロンプト関数のオリジナルを保存できます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-175">You can use this to save the original prompt function if you plan to change it.</span></span>
<span data-ttu-id="4b3c8-176">新しい関数の **Options** プロパティの値は `None` です。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-176">The **Options** property of the new function has a value of `None`.</span></span> <span data-ttu-id="4b3c8-177">**Options** プロパティの値を変更するには、を使用 `Set-Item` します。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-177">To change the value of the **Options** property, use `Set-Item`.</span></span>

```powershell
Copy-Item -Path Function:prompt -Destination Function:oldPrompt
```

## <a name="dynamic-parameters"></a><span data-ttu-id="4b3c8-178">動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="4b3c8-178">Dynamic parameters</span></span>

<span data-ttu-id="4b3c8-179">動的パラメーターは、PowerShell プロバイダーによって追加されるコマンドレットパラメーターであり、プロバイダーに対応したドライブでコマンドレットが使用されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-179">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="options-systemmanagementautomationscopeditemoptions"></a><span data-ttu-id="4b3c8-180">オプション < [ScopedItemOptions] > を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-180">Options <[System.Management.Automation.ScopedItemOptions]></span></span>

<span data-ttu-id="4b3c8-181">関数の **Options** プロパティの値を決定します。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-181">Determines the value of the **Options** property of a function.</span></span>

- <span data-ttu-id="4b3c8-182">`None`: オプションがありません。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-182">`None`: No options.</span></span> <span data-ttu-id="4b3c8-183">`None` は既定値です。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-183">`None` is the default.</span></span>
- <span data-ttu-id="4b3c8-184">`Constant`: 関数を削除することはできません。また、そのプロパティを変更することもできません。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-184">`Constant`: The function cannot be deleted, and its properties cannot be changed.</span></span> <span data-ttu-id="4b3c8-185">`Constant` は、関数を作成する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-185">`Constant` is available only when you are creating a function.</span></span>
  <span data-ttu-id="4b3c8-186">既存の関数のオプションをに変更することはできません `Constant` 。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-186">You cannot change the option of an existing function to `Constant`.</span></span>
- <span data-ttu-id="4b3c8-187">`Private`: 関数は、現在のスコープでのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-187">`Private`: The function is visible only in the current scope</span></span>
- <span data-ttu-id="4b3c8-188">(子スコープ内にありません)。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-188">(not in child scopes).</span></span>
- <span data-ttu-id="4b3c8-189">`ReadOnly`: パラメーターを使用しない限り、関数のプロパティを変更することはできません `-Force` 。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-189">`ReadOnly`: The properties of the function cannot be changed except by using the `-Force` parameter.</span></span> <span data-ttu-id="4b3c8-190">を使用すると `Remove-Item` 、関数を削除できます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-190">You can use `Remove-Item` to delete the function.</span></span>
- <span data-ttu-id="4b3c8-191">`AllScope`: 関数は、作成された新しいスコープにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-191">`AllScope`: The function is copied to any new scopes that are created.</span></span>

### <a name="cmdlets-supported"></a><span data-ttu-id="4b3c8-192">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="4b3c8-192">Cmdlets supported</span></span>

- [<span data-ttu-id="4b3c8-193">New-Item</span><span class="sxs-lookup"><span data-stu-id="4b3c8-193">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)

- [<span data-ttu-id="4b3c8-194">Set-Item</span><span class="sxs-lookup"><span data-stu-id="4b3c8-194">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="4b3c8-195">パイプラインの使用</span><span class="sxs-lookup"><span data-stu-id="4b3c8-195">Using the pipeline</span></span>

<span data-ttu-id="4b3c8-196">プロバイダーのコマンドレットは、パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-196">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="4b3c8-197">パイプラインを使用すると、1つのコマンドレットから別のプロバイダーのコマンドレットにプロバイダーデータを送信することにより、タスクを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-197">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="4b3c8-198">プロバイダーコマンドレットでパイプラインを使用する方法の詳細については、この記事全体で説明されているコマンドレットリファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-198">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="4b3c8-199">ヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="4b3c8-199">Getting help</span></span>

<span data-ttu-id="4b3c8-200">Windows PowerShell 3.0 より、プロバイダー コマンドレットのためにカスタマイズされたヘルプ トピックを取得できます。これはファイル システム ドライブでのプロバイダー コマンドレットの動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-200">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="4b3c8-201">ファイルシステムドライブ用にカスタマイズされたヘルプトピックを取得するには、ファイルシステムドライブで [get-help](xref:Microsoft.PowerShell.Core.Get-Help) コマンドを実行するか、 `-Path` [get-help](xref:Microsoft.PowerShell.Core.Get-Help) のパラメーターを使用してファイルシステムドライブを指定します。</span><span class="sxs-lookup"><span data-stu-id="4b3c8-201">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path function:
```

## <a name="see-also"></a><span data-ttu-id="4b3c8-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b3c8-202">See also</span></span>

[<span data-ttu-id="4b3c8-203">about_Functions</span><span class="sxs-lookup"><span data-stu-id="4b3c8-203">about_Functions</span></span>](../About/about_Functions.md)

[<span data-ttu-id="4b3c8-204">about_Providers</span><span class="sxs-lookup"><span data-stu-id="4b3c8-204">about_Providers</span></span>](../About/about_Providers.md)
