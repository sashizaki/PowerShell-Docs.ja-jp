---
description: 変数
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_variable_provider?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: 変数プロバイダー
ms.openlocfilehash: 126ba39db4d7f49e1ec405a73ba4da19c7e877ee
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220824"
---
# <a name="variable-provider"></a><span data-ttu-id="9d698-104">変数プロバイダー</span><span class="sxs-lookup"><span data-stu-id="9d698-104">Variable provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="9d698-105">プロバイダー名</span><span class="sxs-lookup"><span data-stu-id="9d698-105">Provider name</span></span>
<span data-ttu-id="9d698-106">変数</span><span class="sxs-lookup"><span data-stu-id="9d698-106">Variable</span></span>

## <a name="drives"></a><span data-ttu-id="9d698-107">ドライブ</span><span class="sxs-lookup"><span data-stu-id="9d698-107">Drives</span></span>

`Variable:`

## <a name="capabilities"></a><span data-ttu-id="9d698-108">機能</span><span class="sxs-lookup"><span data-stu-id="9d698-108">Capabilities</span></span>

<span data-ttu-id="9d698-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="9d698-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="9d698-110">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="9d698-110">Short description</span></span>

<span data-ttu-id="9d698-111">PowerShell 変数とその値へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="9d698-111">Provides access to the PowerShell variables and to their values.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="9d698-112">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="9d698-112">Detailed description</span></span>

<span data-ttu-id="9d698-113">PowerShell **変数** プロバイダーを使用すると、現在のコンソールで powershell 変数を取得、追加、変更、消去、削除できます。</span><span class="sxs-lookup"><span data-stu-id="9d698-113">The PowerShell **Variable** provider lets you get, add, change, clear, and delete PowerShell variables in the current console.</span></span>

<span data-ttu-id="9d698-114">PowerShell **変数** プロバイダーは、powershell によって作成される変数 (自動変数、ユーザー設定変数、作成する変数など) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9d698-114">The PowerShell **Variable** provider supports the variables that PowerShell creates, including the automatic variables, the preference variables, and the variables that you create.</span></span>

<span data-ttu-id="9d698-115">**変数** drive は、変数オブジェクトのみを含むフラットな名前空間です。</span><span class="sxs-lookup"><span data-stu-id="9d698-115">The **Variable** drive is a flat namespace that contains only the variable objects.</span></span> <span data-ttu-id="9d698-116">変数に子項目はありません。</span><span class="sxs-lookup"><span data-stu-id="9d698-116">The variables have no child items.</span></span>

<span data-ttu-id="9d698-117">**変数** プロバイダーは、この記事で説明されている次のコマンドレットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9d698-117">The **Variable** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="9d698-118">Get-Location</span><span class="sxs-lookup"><span data-stu-id="9d698-118">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="9d698-119">Set-Location</span><span class="sxs-lookup"><span data-stu-id="9d698-119">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="9d698-120">Get-Item</span><span class="sxs-lookup"><span data-stu-id="9d698-120">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="9d698-121">New-Item</span><span class="sxs-lookup"><span data-stu-id="9d698-121">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="9d698-122">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="9d698-122">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="9d698-123">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="9d698-123">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

<span data-ttu-id="9d698-124">PowerShell には、変数を表示および変更するために特に設計された一連のコマンドレットも含まれています。</span><span class="sxs-lookup"><span data-stu-id="9d698-124">PowerShell also includes a set of cmdlets designed especially to view and to change variables.</span></span> <span data-ttu-id="9d698-125">**変数** コマンドレットを使用する場合は、名前にドライブを指定する必要はありません `Variable:` 。</span><span class="sxs-lookup"><span data-stu-id="9d698-125">When you use **Variable** cmdlets, you do not need to specify the `Variable:` drive in the name.</span></span> <span data-ttu-id="9d698-126">この記事では、 **変数** コマンドレットの使用については説明しません。</span><span class="sxs-lookup"><span data-stu-id="9d698-126">This article does not cover working with **Variable** cmdlets.</span></span>

- [<span data-ttu-id="9d698-127">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="9d698-127">Get-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Get-Variable)
- [<span data-ttu-id="9d698-128">New-Variable</span><span class="sxs-lookup"><span data-stu-id="9d698-128">New-Variable</span></span>](xref:Microsoft.PowerShell.Utility.New-Variable)
- [<span data-ttu-id="9d698-129">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="9d698-129">Set-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Set-Variable)
- [<span data-ttu-id="9d698-130">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="9d698-130">Remove-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Remove-Variable)
- [<span data-ttu-id="9d698-131">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="9d698-131">Clear-Variable</span></span>](xref:Microsoft.PowerShell.Utility.Clear-Variable)

> [!NOTE]
> <span data-ttu-id="9d698-132">PowerShell 式パーサーを使用して、コマンドレットを使用せずに変数の値を作成、表示、変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="9d698-132">You can also use the PowerShell expression parser to create, view, and change the values of variables without using the cmdlets.</span></span> <span data-ttu-id="9d698-133">変数を直接操作する場合は、ドル記号 () を使用し `$` て変数として名前を指定し、代入演算子 () を使用 `=` してその値を設定および変更します。</span><span class="sxs-lookup"><span data-stu-id="9d698-133">When working with variables directly, use a dollar sign (`$`) to identify the name as a variable and the assignment operator (`=`)to establish and change its value.</span></span> <span data-ttu-id="9d698-134">たとえば、は `$p = Get-Process` 変数を作成 `p` し、そこにコマンドの結果を格納し `Get-Process` ます。</span><span class="sxs-lookup"><span data-stu-id="9d698-134">For example, `$p = Get-Process` creates the `p` variable and stores the results of a `Get-Process` command in it.</span></span>

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="9d698-135">このプロバイダーによって公開される型</span><span class="sxs-lookup"><span data-stu-id="9d698-135">Types exposed by this provider</span></span>

<span data-ttu-id="9d698-136">変数には、いくつかの異なる型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9d698-136">Variables can be one of several different types.</span></span> <span data-ttu-id="9d698-137">ほとんどの変数は、クラスのインスタンスになり `PSVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="9d698-137">Most variables will be instances of the `PSVariable` class.</span></span> <span data-ttu-id="9d698-138">その他の変数とその型を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="9d698-138">Other variables and their types are listed below.</span></span>

- <span data-ttu-id="9d698-139">変数は、 `?` クラスのインスタンスです `QuestionMarkVariable` 。</span><span class="sxs-lookup"><span data-stu-id="9d698-139">The `?` variable is an instance of the `QuestionMarkVariable` class.</span></span>
- <span data-ttu-id="9d698-140">変数は、 `null` クラスのインスタンスです `NullVariable` 。</span><span class="sxs-lookup"><span data-stu-id="9d698-140">The `null` variable is an instance of the `NullVariable` class.</span></span>
- <span data-ttu-id="9d698-141">最大カウント変数は、クラスのインスタンスです `SessionStateCapacityVariable` 。</span><span class="sxs-lookup"><span data-stu-id="9d698-141">The maximum count variables are instances of the `SessionStateCapacityVariable` class.</span></span>
- <span data-ttu-id="9d698-142">`LocalVariable` インスタンスには、現在の実行に関する情報が含まれます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9d698-142">`LocalVariable` instances contain information about current execution, such as:</span></span>
  - `MyInvocation`
  - `PSCommandPath`
  - `PSScriptRoot`
  - `PSBoundParameters`
  - `args`
  - `input`

## <a name="navigating-the-variable-drives"></a><span data-ttu-id="9d698-143">変数ドライブの移動</span><span class="sxs-lookup"><span data-stu-id="9d698-143">Navigating the Variable drives</span></span>

<span data-ttu-id="9d698-144">**変数** プロバイダーは、ドライブ内のデータストアを公開し `Variable:` ます。</span><span class="sxs-lookup"><span data-stu-id="9d698-144">The **Variable** provider exposes its data store in the `Variable:` drive.</span></span> <span data-ttu-id="9d698-145">変数を使用するには、場所を `Variable:` ドライブ () に変更する `Set-Location Variable:` か、他の PowerShell ドライブから作業することができます。</span><span class="sxs-lookup"><span data-stu-id="9d698-145">To work with variables, you can change your location to the `Variable:` drive (`Set-Location Variable:`), or you can work from any other PowerShell drive.</span></span> <span data-ttu-id="9d698-146">別の場所から変数を参照するには、パスのドライブ名 () を使用し `Variable:` ます。</span><span class="sxs-lookup"><span data-stu-id="9d698-146">To reference a variable from another location, use the drive name (`Variable:`) in the path.</span></span>

```powershell
Set-Location Variable:
```

<span data-ttu-id="9d698-147">ファイル システム ドライブに戻るには、ドライブ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9d698-147">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="9d698-148">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="9d698-148">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="9d698-149">その他の PowerShell ドライブから **変数** プロバイダーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9d698-149">You can also work with the **Variable** provider from any other PowerShell drive.</span></span> <span data-ttu-id="9d698-150">別の場所から変数を参照するには、パス内のドライブ名を使用し `Variable:` ます。</span><span class="sxs-lookup"><span data-stu-id="9d698-150">To reference an variable from another location, use the drive name `Variable:` in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="9d698-151">PowerShell では、エイリアスを使用して、プロバイダーパスを操作するための使い慣れた方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d698-151">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="9d698-152">`dir`やなどのコマンド `ls` は、 [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem)のエイリアスです。これ `cd` は、 [Set Location](xref:Microsoft.PowerShell.Management.Set-Location)のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="9d698-152">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="9d698-153">と `pwd` は、 [Get Location](xref:Microsoft.PowerShell.Management.Get-Location)のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="9d698-153">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="displaying-the-value-of-variables"></a><span data-ttu-id="9d698-154">変数の値の表示</span><span class="sxs-lookup"><span data-stu-id="9d698-154">Displaying the value of variables</span></span>

### <a name="get-all-variables-in-the-current-session"></a><span data-ttu-id="9d698-155">現在のセッションのすべての変数を取得します。</span><span class="sxs-lookup"><span data-stu-id="9d698-155">Get all variables in the current session</span></span>

<span data-ttu-id="9d698-156">このコマンドは現在のセッションのすべての変数とその値の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="9d698-156">This command gets the list of all the variables and their values in the current session.</span></span> <span data-ttu-id="9d698-157">このコマンドは、任意の PowerShell ドライブから使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d698-157">You can use this command from any PowerShell drive.</span></span>

```powershell
Get-ChildItem -Path Variable:
```

### <a name="get-a-variable-using-its-provider-path"></a><span data-ttu-id="9d698-158">プロバイダーパスを使用して変数を取得する</span><span class="sxs-lookup"><span data-stu-id="9d698-158">Get a variable using its provider path</span></span>

<span data-ttu-id="9d698-159">このコマンドは、ドル記号 () で始まるプロバイダーパスを使用して、変数値を取得 `$` します。</span><span class="sxs-lookup"><span data-stu-id="9d698-159">This command retrieves a variables value using its provider path prefixed by the dollar sign (`$`).</span></span> <span data-ttu-id="9d698-160">これは、変数名の先頭にドル記号 () を付ける場合と同じ効果があり `$` ます。</span><span class="sxs-lookup"><span data-stu-id="9d698-160">This has the same effect as prefixing the variables name with the dollar sign (`$`).</span></span>

```powershell
$variable:home
```

### <a name="get-variables-using-wildcards"></a><span data-ttu-id="9d698-161">ワイルドカードを使用して変数を取得する</span><span class="sxs-lookup"><span data-stu-id="9d698-161">Get variables using wildcards</span></span>

<span data-ttu-id="9d698-162">このコマンドは「max」で始まる名前を持つ変数を取得します。</span><span class="sxs-lookup"><span data-stu-id="9d698-162">This command gets the variables with names that begin with "max".</span></span> <span data-ttu-id="9d698-163">このコマンドは、任意の PowerShell ドライブから使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d698-163">You can use this command from any PowerShell drive.</span></span>

```powershell
Get-ChildItem -Path Variable:max*
```

### <a name="get-the-value-of-the--variable"></a><span data-ttu-id="9d698-164">の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="9d698-164">Get the value of the ?</span></span> <span data-ttu-id="9d698-165">可変</span><span class="sxs-lookup"><span data-stu-id="9d698-165">variable</span></span>

<span data-ttu-id="9d698-166">このコマンドは、 `-LiteralPath` [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem) のパラメーターを使用して、ドライブ内から変数の値を取得し `?` `Variable:` ます。</span><span class="sxs-lookup"><span data-stu-id="9d698-166">This command uses the `-LiteralPath` parameter of [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem) to get the value of the `?` variable from within the `Variable:` drive.</span></span> <span data-ttu-id="9d698-167">は `?` パス内のワイルドカードですが、 `Get-ChildItem` パラメーターの値ではワイルドカードの解決を試みません `-LiteralPath` 。</span><span class="sxs-lookup"><span data-stu-id="9d698-167">The `?` is a wildcard in paths, but `Get-ChildItem` does not attempt to resolve any wildcards in the values of the `-LiteralPath` parameter.</span></span>

```powershell
Get-ChildItem -Literalpath ?
```

### <a name="get-readonly-and-constant-variables"></a><span data-ttu-id="9d698-168">読み取り専用変数と定数変数を取得する</span><span class="sxs-lookup"><span data-stu-id="9d698-168">Get ReadOnly and Constant variables</span></span>

<span data-ttu-id="9d698-169">このコマンド `ReadOnly` は、Options プロパティにまたはの値を持つ変数を取得し `Constant` ます。 **Options**</span><span class="sxs-lookup"><span data-stu-id="9d698-169">This command gets the variables that have the values of `ReadOnly` or `Constant` for their **Options** property.</span></span>

```powershell
Get-ChildItem -Path Variable: | Where-Object {
   $_.options -Match "Constant" `
   -or $_.options -Match "ReadOnly"
 } | Format-List -Property name, value, options
```

## <a name="creating-variables"></a><span data-ttu-id="9d698-170">変数の作成</span><span class="sxs-lookup"><span data-stu-id="9d698-170">Creating variables</span></span>

### <a name="create-a-new-variable"></a><span data-ttu-id="9d698-171">新しい変数を作成する</span><span class="sxs-lookup"><span data-stu-id="9d698-171">Create a new variable</span></span>

<span data-ttu-id="9d698-172">このコマンドは、 `services` 変数を作成し、その変数にコマンドの結果を格納し `Get-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="9d698-172">This command creates the `services` variable and stores the results of a `Get-Service` command in it.</span></span> <span data-ttu-id="9d698-173">現在の場所はドライブにあるため `Variable:` 、パラメーターの値 `-Path` は、 `.` 現在の場所を表すドット () です。</span><span class="sxs-lookup"><span data-stu-id="9d698-173">Because the current location is in the `Variable:` drive, the value of the `-Path` parameter is a dot (`.`), which represents the current location.</span></span>

<span data-ttu-id="9d698-174">コマンドをかっこで囲んで、 `Get-Service` 変数が作成される前にコマンドが実行されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9d698-174">The parentheses around the `Get-Service` command ensure that the command is executed before the variable is created.</span></span> <span data-ttu-id="9d698-175">括弧がない場合、新しい変数の値は文字列「Get-Service」です。</span><span class="sxs-lookup"><span data-stu-id="9d698-175">Without the parentheses, the value of the new variable is a "Get-Service" string.</span></span>

```powershell
New-Item -Path . -Name services -Value (Get-Service)
```

### <a name="create-a-variable-using-an-absolute-path"></a><span data-ttu-id="9d698-176">絶対パスを使用して変数を作成する</span><span class="sxs-lookup"><span data-stu-id="9d698-176">Create a variable using an absolute path</span></span>

<span data-ttu-id="9d698-177">このコマンドは、 `services` 変数を作成し、その変数にコマンドの結果を格納し `Get-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="9d698-177">This command creates a `services` variable and stores the result of a `Get-Service` command in it.</span></span>

```powershell
New-Item -Path Variable:services -Value Get-Service
```

 <span data-ttu-id="9d698-178">値なしで変数を作成するには、代入演算子を省略します。</span><span class="sxs-lookup"><span data-stu-id="9d698-178">To create a variable without a value, omit the assignment operator.</span></span>

## <a name="changing-variables"></a><span data-ttu-id="9d698-179">変数の変更</span><span class="sxs-lookup"><span data-stu-id="9d698-179">Changing variables</span></span>

### <a name="rename-a-variable"></a><span data-ttu-id="9d698-180">変数名の変更</span><span class="sxs-lookup"><span data-stu-id="9d698-180">Rename a variable</span></span>

<span data-ttu-id="9d698-181">このコマンドは、コマンドレットを使用して、 `Rename-Item` 変数の名前をに変更し `a` `processes` ます。</span><span class="sxs-lookup"><span data-stu-id="9d698-181">This command uses the `Rename-Item` cmdlet to change the name of the `a` variable to `processes`.</span></span>

```powershell
Rename-Item -Path Variable:a -NewName processes
```

### <a name="change-the-value-of-a-variable"></a><span data-ttu-id="9d698-182">変数の値を変更する</span><span class="sxs-lookup"><span data-stu-id="9d698-182">Change the value of a variable</span></span>

<span data-ttu-id="9d698-183">このコマンドは、コマンドレットを使用して、 `Set-Item` 変数の値を `ErrorActionPreference` "Stop" に変更します。</span><span class="sxs-lookup"><span data-stu-id="9d698-183">This command uses the `Set-Item` cmdlet to change the value of the `ErrorActionPreference` variable to "Stop".</span></span>

```powershell
Set-Item -Path Variable:ErrorActionPreference -Value Stop
```

## <a name="copy-a-variable"></a><span data-ttu-id="9d698-184">変数をコピーする</span><span class="sxs-lookup"><span data-stu-id="9d698-184">Copy a variable</span></span>

<span data-ttu-id="9d698-185">このコマンドは、 `Copy-Item` コマンドレットを使用して、変数をにコピーし `processes` `old_processes` ます。</span><span class="sxs-lookup"><span data-stu-id="9d698-185">This command uses the `Copy-Item` cmdlet to copy the `processes` variable to `old_processes`.</span></span> <span data-ttu-id="9d698-186">これにより、変数と同じ値を持つという名前の新しい変数が作成さ `old_processes` `processes` れます。</span><span class="sxs-lookup"><span data-stu-id="9d698-186">This creates a new variable named `old_processes` that has the same value as the `processes` variable.</span></span>

```powershell
Copy-Item -Path Variable:processes -Destination Variable:old_processes
```

## <a name="delete-a-variable"></a><span data-ttu-id="9d698-187">変数の削除</span><span class="sxs-lookup"><span data-stu-id="9d698-187">Delete a variable</span></span>

<span data-ttu-id="9d698-188">このコマンドは、 `serv` 現在のセッションから変数を削除します。</span><span class="sxs-lookup"><span data-stu-id="9d698-188">This command deletes the `serv` variable from the current session.</span></span> <span data-ttu-id="9d698-189">このコマンドは、任意の PowerShell ドライブで使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d698-189">You can use this command in any PowerShell drive.</span></span>

```powershell
Remove-Variable -Path Variable:serv
```

### <a name="delete-variables-using-the--force-parameter"></a><span data-ttu-id="9d698-190">-Force パラメーターを使用して変数を削除する</span><span class="sxs-lookup"><span data-stu-id="9d698-190">Delete variables using the -Force parameter</span></span>

<span data-ttu-id="9d698-191">このコマンドは、 **Options** プロパティの値がである変数を除き、現在のセッションからすべての変数を削除 `Constant` します。</span><span class="sxs-lookup"><span data-stu-id="9d698-191">This command deletes all variables from the current session except for the variables whose **Options** property has a value of `Constant`.</span></span> <span data-ttu-id="9d698-192">パラメーターを指定しない場合、このコマンドでは、 `-Force` **Options** プロパティの値がである変数は削除されません `ReadOnly` 。</span><span class="sxs-lookup"><span data-stu-id="9d698-192">Without the `-Force` parameter, the command does not delete variables whose **Options** property has a value of `ReadOnly`.</span></span>

```powershell
Remove-Item Variable:* -Force
```

## <a name="setting-the-value-of-a-variable-to-null"></a><span data-ttu-id="9d698-193">変数の値を NULL に設定する</span><span class="sxs-lookup"><span data-stu-id="9d698-193">Setting the value of a variable to NULL</span></span>

<span data-ttu-id="9d698-194">このコマンドは、 `Clear-Item` コマンドレットを使用して、変数の値を `processes` NULL に変更します。</span><span class="sxs-lookup"><span data-stu-id="9d698-194">This command uses the `Clear-Item` cmdlet to change the value of the `processes` variable to NULL.</span></span>

```powershell
Clear-Item -Path Variable:processes
```

## <a name="using-the-pipeline"></a><span data-ttu-id="9d698-195">パイプラインの使用</span><span class="sxs-lookup"><span data-stu-id="9d698-195">Using the pipeline</span></span>

<span data-ttu-id="9d698-196">プロバイダーのコマンドレットは、パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="9d698-196">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="9d698-197">パイプラインを使用すると、1つのコマンドレットから別のプロバイダーのコマンドレットにプロバイダーデータを送信することにより、タスクを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9d698-197">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="9d698-198">プロバイダーコマンドレットでパイプラインを使用する方法の詳細については、この記事全体で説明されているコマンドレットリファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d698-198">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="9d698-199">ヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="9d698-199">Getting help</span></span>

<span data-ttu-id="9d698-200">Windows PowerShell 3.0 より、プロバイダー コマンドレットのためにカスタマイズされたヘルプ トピックを取得できます。これはファイル システム ドライブでのプロバイダー コマンドレットの動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="9d698-200">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="9d698-201">ファイルシステムドライブ用にカスタマイズされたヘルプトピックを取得するには、ファイルシステムドライブで [get-help](xref:Microsoft.PowerShell.Core.Get-Help) コマンドを実行するか、 `-Path` [get-help](xref:Microsoft.PowerShell.Core.Get-Help) のパラメーターを使用してファイルシステムドライブを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d698-201">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path variable:
```

## <a name="see-also"></a><span data-ttu-id="9d698-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d698-202">See also</span></span>

[<span data-ttu-id="9d698-203">about_Variables</span><span class="sxs-lookup"><span data-stu-id="9d698-203">about_Variables</span></span>](../About/about_Variables.md)

[<span data-ttu-id="9d698-204">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="9d698-204">about_Automatic_Variables</span></span>](../About/about_Automatic_Variables.md)

[<span data-ttu-id="9d698-205">about_Providers</span><span class="sxs-lookup"><span data-stu-id="9d698-205">about_Providers</span></span>](../About/about_Providers.md)

