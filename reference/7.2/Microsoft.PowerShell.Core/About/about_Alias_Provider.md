---
description: エイリアス
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_alias_provider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: エイリアス プロバイダー
ms.openlocfilehash: d6bfbaf878a6d971b1e01d963faec8c8ece5d1fc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601426"
---
# <a name="alias-provider"></a><span data-ttu-id="595e9-103">エイリアスプロバイダー</span><span class="sxs-lookup"><span data-stu-id="595e9-103">Alias provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="595e9-104">プロバイダー名</span><span class="sxs-lookup"><span data-stu-id="595e9-104">Provider name</span></span>
<span data-ttu-id="595e9-105">エイリアス</span><span class="sxs-lookup"><span data-stu-id="595e9-105">Alias</span></span>

## <a name="drives"></a><span data-ttu-id="595e9-106">ドライブ</span><span class="sxs-lookup"><span data-stu-id="595e9-106">Drives</span></span>

`Alias:`

## <a name="capabilities"></a><span data-ttu-id="595e9-107">機能</span><span class="sxs-lookup"><span data-stu-id="595e9-107">Capabilities</span></span>

<span data-ttu-id="595e9-108">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="595e9-108">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="595e9-109">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="595e9-109">Short description</span></span>

<span data-ttu-id="595e9-110">PowerShell エイリアスとそれが表す値へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="595e9-110">Provides access to the PowerShell aliases and the values that they represent.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="595e9-111">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="595e9-111">Detailed description</span></span>

<span data-ttu-id="595e9-112">PowerShell **エイリアス** プロバイダーを使用すると、powershell のエイリアスを取得、追加、変更、消去、削除できます。</span><span class="sxs-lookup"><span data-stu-id="595e9-112">The PowerShell **Alias** provider lets you get, add, change, clear, and delete aliases in PowerShell.</span></span>

<span data-ttu-id="595e9-113">エイリアスは、コマンドレット、関数、およびスクリプトを含む実行可能ファイルの代替名です。</span><span class="sxs-lookup"><span data-stu-id="595e9-113">An alias is an alternate name for a cmdlet, function, executable file, including scripts.</span></span> <span data-ttu-id="595e9-114">PowerShell には、一連の組み込みエイリアスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="595e9-114">PowerShell includes a set of built-in aliases.</span></span> <span data-ttu-id="595e9-115">独自のエイリアスを現在のセッションと PowerShell プロファイルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="595e9-115">You can add your own aliases to the current session and to your PowerShell profile.</span></span>

<span data-ttu-id="595e9-116">**エイリアス** ドライブは、エイリアスオブジェクトのみを含むフラットな名前空間です。</span><span class="sxs-lookup"><span data-stu-id="595e9-116">The **Alias** drive is a flat namespace that contains only the alias objects.</span></span>
<span data-ttu-id="595e9-117">エイリアスに子項目はありません。</span><span class="sxs-lookup"><span data-stu-id="595e9-117">The aliases have no child items.</span></span>

<span data-ttu-id="595e9-118">**エイリアス** プロバイダーは、この記事で説明されている次のコマンドレットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="595e9-118">The **Alias** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="595e9-119">Get-Location</span><span class="sxs-lookup"><span data-stu-id="595e9-119">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="595e9-120">Set-Location</span><span class="sxs-lookup"><span data-stu-id="595e9-120">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="595e9-121">Get-Item</span><span class="sxs-lookup"><span data-stu-id="595e9-121">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="595e9-122">New-Item</span><span class="sxs-lookup"><span data-stu-id="595e9-122">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="595e9-123">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="595e9-123">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="595e9-124">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="595e9-124">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

<span data-ttu-id="595e9-125">PowerShell には、エイリアスの表示と変更を行うための一連のコマンドレットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="595e9-125">PowerShell includes a set of cmdlets that are designed to view and to change aliases.</span></span> <span data-ttu-id="595e9-126">**Alias** コマンドレットを使用する場合は、名前にドライブを指定する必要はありません `Alias:` 。</span><span class="sxs-lookup"><span data-stu-id="595e9-126">When you use **Alias** cmdlets, you do not need to specify the `Alias:` drive in the name.</span></span> <span data-ttu-id="595e9-127">この記事では、 **エイリアス** コマンドレットの使用については説明しません。</span><span class="sxs-lookup"><span data-stu-id="595e9-127">This article does not cover working with **Alias** cmdlets.</span></span>

- [<span data-ttu-id="595e9-128">Export-Alias</span><span class="sxs-lookup"><span data-stu-id="595e9-128">Export-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Export-Alias)
- [<span data-ttu-id="595e9-129">Get-Alias</span><span class="sxs-lookup"><span data-stu-id="595e9-129">Get-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Get-Alias)
- [<span data-ttu-id="595e9-130">Import-Alias</span><span class="sxs-lookup"><span data-stu-id="595e9-130">Import-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Import-Alias)
- [<span data-ttu-id="595e9-131">New-Alias</span><span class="sxs-lookup"><span data-stu-id="595e9-131">New-Alias</span></span>](xref:Microsoft.PowerShell.Utility.New-Alias)
- [<span data-ttu-id="595e9-132">Set-Alias</span><span class="sxs-lookup"><span data-stu-id="595e9-132">Set-Alias</span></span>](xref:Microsoft.PowerShell.Utility.Set-Alias)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="595e9-133">このプロバイダーによって公開される型</span><span class="sxs-lookup"><span data-stu-id="595e9-133">Types exposed by this provider</span></span>

<span data-ttu-id="595e9-134">各エイリアスは、 [System. Automation. エイリアス情報](/dotnet/api/system.management.automation.aliasinfo) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="595e9-134">Each alias is an instance of the [System.Management.Automation.AliasInfo](/dotnet/api/system.management.automation.aliasinfo) class.</span></span>

## <a name="navigating-the-alias-drive"></a><span data-ttu-id="595e9-135">エイリアスドライブの移動</span><span class="sxs-lookup"><span data-stu-id="595e9-135">Navigating the Alias drive</span></span>

<span data-ttu-id="595e9-136">**エイリアス** プロバイダーは、ドライブ内のそのデータストアを公開し `Alias:` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-136">The **Alias** provider exposes its data store in the `Alias:` drive.</span></span> <span data-ttu-id="595e9-137">エイリアスを使用するには、 `Alias:` 次のコマンドを使用して場所をドライブに変更します。</span><span class="sxs-lookup"><span data-stu-id="595e9-137">To work with aliases, you can change your location to the `Alias:` drive by using the following command:</span></span>

```powershell
Set-Location Alias:
```

<span data-ttu-id="595e9-138">ファイル システム ドライブに戻るには、ドライブ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="595e9-138">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="595e9-139">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="595e9-139">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="595e9-140">エイリアスプロバイダーは、他の PowerShell ドライブからも使用できます。</span><span class="sxs-lookup"><span data-stu-id="595e9-140">You can also work with the Alias provider from any other PowerShell drive.</span></span> <span data-ttu-id="595e9-141">別の場所からエイリアスを参照するには、 `Alias:` パス内のドライブ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="595e9-141">To reference an alias from another location, use the `Alias:` drive name in the path.</span></span>

> [!NOTE]
> <span data-ttu-id="595e9-142">PowerShell では、エイリアスを使用して、プロバイダーパスを操作するための使い慣れた方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="595e9-142">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="595e9-143">`dir`やなどのコマンド `ls` は、 [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem)のエイリアスです。これ `cd` は、 [Set Location](xref:Microsoft.PowerShell.Management.Set-Location)のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="595e9-143">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="595e9-144">と `pwd` は、 [Get Location](xref:Microsoft.PowerShell.Management.Get-Location)のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="595e9-144">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

### <a name="displaying-the-contents-of-the-alias-drive"></a><span data-ttu-id="595e9-145">Alias: ドライブの内容を表示しています</span><span class="sxs-lookup"><span data-stu-id="595e9-145">Displaying the Contents of the Alias: drive</span></span>

<span data-ttu-id="595e9-146">このコマンドは、現在の場所がドライブである場合に、すべてのエイリアスの一覧を取得し `Alias:` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-146">This command gets the list of all the aliases when the current location is the `Alias:` drive.</span></span> <span data-ttu-id="595e9-147">`*`現在の場所のすべての内容を示すために、ワイルドカード文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="595e9-147">It uses a wildcard character `*` to indicate all the contents of the current location.</span></span>

```powershell
PS Alias:\> Get-Item -Path *
```

<span data-ttu-id="595e9-148">ドライブでは、 `Alias:` 現在の `.` 場所を表すドットと、 `*` 現在の場所にあるすべての項目を表すワイルドカード文字が同じ効果を持ちます。</span><span class="sxs-lookup"><span data-stu-id="595e9-148">In the `Alias:` drive, a dot `.`, which represents the current location, and a wildcard character `*`, which represents all items in the current location, have the same effect.</span></span> <span data-ttu-id="595e9-149">たとえば、 `Get-Item -Path .` またはは `Get-Item \*` 同じ結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="595e9-149">For example, `Get-Item -Path .` or `Get-Item \*` produce the same result.</span></span>

<span data-ttu-id="595e9-150">エイリアスプロバイダーにはコンテナーがないため、上のコマンドはと共に使用する場合と同じ効果があり `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-150">The Alias provider has no containers, so the above command has the same effect when used with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path Alias:
```

### <a name="get-a-selected-alias"></a><span data-ttu-id="595e9-151">選択したエイリアスを取得します</span><span class="sxs-lookup"><span data-stu-id="595e9-151">Get a selected alias</span></span>

<span data-ttu-id="595e9-152">このコマンドは、エイリアスを取得し `ls` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-152">This command gets the `ls` alias.</span></span>
<span data-ttu-id="595e9-153">パスが含まれているため、任意の PowerShell ドライブで使用できます。</span><span class="sxs-lookup"><span data-stu-id="595e9-153">Because it includes the path, you can use it in any PowerShell drive.</span></span>

```powershell
Get-Item -Path Alias:ls
```

<span data-ttu-id="595e9-154">ドライブにいる場合は、 `Alias:` パスからドライブ名を省略できます。</span><span class="sxs-lookup"><span data-stu-id="595e9-154">If you are in the `Alias:` drive, you can omit the drive name from the path.</span></span>

<span data-ttu-id="595e9-155">プロバイダーのパスにドル記号 () を付けることによって、エイリアスの定義を取得することもでき `$` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-155">You can also retrieve the definition for an alias by prefixing the provider path with the dollar sign (`$`).</span></span>

```powershell
$Alias:ls
```

### <a name="get-all-aliases-for-a-specific-cmdlet"></a><span data-ttu-id="595e9-156">特定のコマンドレットのすべてのエイリアスを取得する</span><span class="sxs-lookup"><span data-stu-id="595e9-156">Get all aliases for a specific cmdlet</span></span>

<span data-ttu-id="595e9-157">このコマンドは、コマンドレットに関連付けられているエイリアスの一覧を取得し `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-157">This command gets a list of the aliases that are associated with the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="595e9-158">この例では、コマンドレット名を格納する **Definition** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="595e9-158">It uses the **Definition** property, which stores the cmdlet name.</span></span>

```powershell
Get-Item -Path Alias:* | Where-Object {$_.Definition -eq "Get-ChildItem"}
```

## <a name="creating-aliases"></a><span data-ttu-id="595e9-159">エイリアスの作成</span><span class="sxs-lookup"><span data-stu-id="595e9-159">Creating aliases</span></span>

### <a name="create-an-alias-from-the-alias-drive"></a><span data-ttu-id="595e9-160">Alias: ドライブからエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="595e9-160">Create an alias from the Alias: drive</span></span>

<span data-ttu-id="595e9-161">このコマンドは、 `serv` コマンドレットのエイリアスを作成し `Get-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-161">This command creates the `serv` alias for the `Get-Service` cmdlet.</span></span> <span data-ttu-id="595e9-162">現在の場所はドライブにあるため `Alias:` 、 `-Path` パラメーターは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="595e9-162">Because the current location is in the `Alias:` drive, the `-Path` parameter is not needed.</span></span>

<span data-ttu-id="595e9-163">また、このコマンドは動的パラメーターを使用して、 `-Options` エイリアスの **allscope** オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="595e9-163">This command also uses the `-Options` dynamic parameter to set the **AllScope** option on the alias.</span></span> <span data-ttu-id="595e9-164">パラメーターは、 `-Options` `New-Item` ドライブ内にある場合にのみ、コマンドレットで使用でき `Alias:` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-164">The `-Options` parameter is available in the `New-Item` cmdlet only when you are in the `Alias:` drive.</span></span> <span data-ttu-id="595e9-165">ドット () は、 `.` 現在のディレクトリ (エイリアスドライブ) を示します。</span><span class="sxs-lookup"><span data-stu-id="595e9-165">The dot (`.`) indicates the current directory, which is the alias drive.</span></span>

```
PS Alias:\> New-Item -Path . -Name serv -Value Get-Service -Options "AllScope"
```

### <a name="create-an-alias-with-an-absolute-path"></a><span data-ttu-id="595e9-166">絶対パスを使用してエイリアスを作成する</span><span class="sxs-lookup"><span data-stu-id="595e9-166">Create an alias with an absolute path</span></span>

<span data-ttu-id="595e9-167">コマンドを呼び出す項目にエイリアスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="595e9-167">You can create an alias for any item that invokes a command.</span></span>
<span data-ttu-id="595e9-168">このコマンドは、 `np` の別名を作成し `Notepad.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-168">This command creates the `np` alias for `Notepad.exe`.</span></span>

```powershell
New-Item -Path Alias:np -Value c:\windows\notepad.exe
```

### <a name="create-an-alias-to-a-new-function"></a><span data-ttu-id="595e9-169">新しい関数のエイリアスを作成する</span><span class="sxs-lookup"><span data-stu-id="595e9-169">Create an alias to a new function</span></span>

<span data-ttu-id="595e9-170">あらゆる関数にエイリアスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="595e9-170">You can create an alias for any function.</span></span> <span data-ttu-id="595e9-171">この機能を利用し、コマンドレットとそのパラメーターの両方を含むエイリアスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="595e9-171">You can use this feature to create an alias that includes both a cmdlet and its parameters.</span></span>

<span data-ttu-id="595e9-172">最初のコマンドは、 `CD32` 現在のディレクトリをディレクトリに変更する関数を作成し `System32` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-172">The first command creates the `CD32` function, which changes the current directory to the `System32` directory.</span></span> <span data-ttu-id="595e9-173">2番目のコマンドは、 `go` 関数のエイリアスを作成し `CD32` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-173">The second command creates the `go` alias for the `CD32` function.</span></span>

<span data-ttu-id="595e9-174">コマンドが完了すると、 `CD32` またはのいずれか `go` を使用して関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="595e9-174">When the command is complete, you can use either `CD32` or `go` to invoke the function.</span></span>

```powershell
function CD32 {Set-Location -Path c:\windows\system32}
Set-Item -Path Alias:go -Value CD32
```

## <a name="changing-aliases"></a><span data-ttu-id="595e9-175">変更 (エイリアスを)</span><span class="sxs-lookup"><span data-stu-id="595e9-175">Changing aliases</span></span>

### <a name="change-the-options-of-an-alias"></a><span data-ttu-id="595e9-176">エイリアスのオプションを変更する</span><span class="sxs-lookup"><span data-stu-id="595e9-176">Change the options of an alias</span></span>

<span data-ttu-id="595e9-177">`Set-Item`コマンドレットを動的パラメーターと共に使用して、 `-Options` エイリアスのプロパティの値を変更でき `-Options` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-177">You can use the `Set-Item` cmdlet with the `-Options` dynamic parameter to change the value of the `-Options` property of an alias.</span></span>

<span data-ttu-id="595e9-178">このコマンドは、エイリアスの **Allscope** オプションと **ReadOnly** オプションを設定し `dir` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-178">This command sets the **AllScope** and **ReadOnly** options for the `dir` alias.</span></span> <span data-ttu-id="595e9-179">コマンドは、コマンド `-Options` レットの動的パラメーターを使用し `Set-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-179">The command uses the `-Options` dynamic parameter of the `Set-Item` cmdlet.</span></span> <span data-ttu-id="595e9-180">パラメーターは、 `-Options` `Set-Item` **エイリアス** または **関数** プロバイダーと共に使用するときにで使用できます。</span><span class="sxs-lookup"><span data-stu-id="595e9-180">The `-Options` parameter is available in `Set-Item` when you use it with the **Alias** or **Function** provider.</span></span>

```powershell
Set-Item -Path Alias:dir -Options "AllScope,ReadOnly"
```

### <a name="change-an-aliases-referenced-command"></a><span data-ttu-id="595e9-181">エイリアス参照コマンドの変更</span><span class="sxs-lookup"><span data-stu-id="595e9-181">Change an aliases referenced command</span></span>

<span data-ttu-id="595e9-182">このコマンドは、コマンドレットを使用して、コマンドレットではなくコマンドレットを `Set-Item` 表すようにエイリアスを変更し `gp` `Get-Process` `Get-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-182">This command uses the `Set-Item` cmdlet to change the `gp` alias so that it represents the `Get-Process` cmdlet instead of the `Get-ItemProperty` cmdlet.</span></span>
<span data-ttu-id="595e9-183">`-Force`エイリアスの **Options** プロパティの値 `gp` がに設定されているため、パラメーターが必要です `ReadOnly` 。</span><span class="sxs-lookup"><span data-stu-id="595e9-183">The `-Force` parameter is required because the value of the **Options** property of the `gp` alias is set to `ReadOnly`.</span></span> <span data-ttu-id="595e9-184">コマンドはドライブ内から送信されるため、 `Alias:` ドライブはパスに指定されていません。</span><span class="sxs-lookup"><span data-stu-id="595e9-184">Because the command is submitted from within the `Alias:` drive, the drive is not specified in the path.</span></span>

```powershell
Set-Item -Path gp -Value Get-Process -Force
```

<span data-ttu-id="595e9-185">この変更は、エイリアスとコマンドの関係を定義する 4 つのプロパティに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="595e9-185">The change affects the four properties that define the association between the alias and the command.</span></span> <span data-ttu-id="595e9-186">変更の効果を表示するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="595e9-186">To view the effect of the change, type the following command:</span></span>

```powershell
Get-Item -Path gp | Format-List -Property *
```

### <a name="rename-an-alias"></a><span data-ttu-id="595e9-187">エイリアスの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="595e9-187">Rename an alias</span></span>

<span data-ttu-id="595e9-188">このコマンドは、コマンドレットを使用して `Rename-Item` 、エイリアスをに変更し `popd` `pop` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-188">This command uses the `Rename-Item` cmdlet to change the `popd` alias to `pop`.</span></span>

```powershell
Rename-Item -Path Alias:popd -NewName pop
```

## <a name="copying-an-alias"></a><span data-ttu-id="595e9-189">エイリアスのコピー</span><span class="sxs-lookup"><span data-stu-id="595e9-189">Copying an alias</span></span>

<span data-ttu-id="595e9-190">このコマンドは、 `pushd` `push` コマンドレットに対して新しいエイリアスが作成されるようにエイリアスをコピーし `Push-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-190">This command copies the `pushd` alias so that a new `push` alias is created for the `Push-Location` cmdlet.</span></span>

<span data-ttu-id="595e9-191">新しいエイリアスが作成されると、その **Description** プロパティの値は null になります。</span><span class="sxs-lookup"><span data-stu-id="595e9-191">When the new alias is created, its **Description** property has a null value.</span></span>
<span data-ttu-id="595e9-192">また、その **Option** プロパティの値は `None` です。</span><span class="sxs-lookup"><span data-stu-id="595e9-192">And, its **Option** property has a value of `None`.</span></span> <span data-ttu-id="595e9-193">コマンドがドライブ内から発行されている場合は、 `Alias:` パラメーターの値からドライブ名を省略でき `-Path` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-193">If the command is issued from within the `Alias:` drive, you can omit the drive name from the value of the `-Path` parameter.</span></span>

```powershell
Copy-Item -Path Alias:pushd -Destination Alias:push
```

## <a name="deleting-an-alias"></a><span data-ttu-id="595e9-194">エイリアスの削除</span><span class="sxs-lookup"><span data-stu-id="595e9-194">Deleting an alias</span></span>

<span data-ttu-id="595e9-195">このコマンドは、 `serv` 現在のセッションからエイリアスを削除します。</span><span class="sxs-lookup"><span data-stu-id="595e9-195">This command deletes the `serv` alias from the current session.</span></span>
<span data-ttu-id="595e9-196">このコマンドは、任意の PowerShell ドライブで使用できます。</span><span class="sxs-lookup"><span data-stu-id="595e9-196">You can use this command in any PowerShell drive.</span></span>

```powershell
Remove-Item -Path Alias:serv
```

<span data-ttu-id="595e9-197">このコマンドは「s」で始まるエイリアスを削除します。</span><span class="sxs-lookup"><span data-stu-id="595e9-197">This command deletes aliases that begin with "s".</span></span>
<span data-ttu-id="595e9-198">読み取り専用のエイリアスは削除されません。</span><span class="sxs-lookup"><span data-stu-id="595e9-198">It does not delete read-only aliases.</span></span>

```powershell
Clear-Item -Path Alias:s*
```

### <a name="delete-read-only-aliases"></a><span data-ttu-id="595e9-199">読み取り専用エイリアスの削除</span><span class="sxs-lookup"><span data-stu-id="595e9-199">Delete read-only aliases</span></span>

<span data-ttu-id="595e9-200">このコマンドは、Options プロパティの値がであるものを除き、現在のセッションからすべてのエイリアスを削除し `Constant` ます。 </span><span class="sxs-lookup"><span data-stu-id="595e9-200">This command deletes all aliases from the current session, except those with a value of `Constant` for their **Options** property.</span></span> <span data-ttu-id="595e9-201">`-Force`パラメーターを使用すると、 **Options** プロパティの値がであるエイリアスをコマンドで削除でき `ReadOnly` ます。</span><span class="sxs-lookup"><span data-stu-id="595e9-201">The `-Force` parameter allows the command to delete aliases whose **Options** property has a value of `ReadOnly`.</span></span>

```powershell
Remove-Item Alias:* -Force
```

## <a name="dynamic-parameters"></a><span data-ttu-id="595e9-202">動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="595e9-202">Dynamic parameters</span></span>

<span data-ttu-id="595e9-203">動的パラメーターは、PowerShell プロバイダーによって追加されるコマンドレットパラメーターであり、プロバイダーに対応したドライブでコマンドレットが使用されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="595e9-203">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="options-systemmanagementautomationscopeditemoptions"></a><span data-ttu-id="595e9-204">オプション ([ScopedItemOptions])</span><span class="sxs-lookup"><span data-stu-id="595e9-204">Options [System.Management.Automation.ScopedItemOptions]</span></span>

<span data-ttu-id="595e9-205">エイリアスの **Options** プロパティの値を決定します。</span><span class="sxs-lookup"><span data-stu-id="595e9-205">Determines the value of the **Options** property of an alias.</span></span>

- <span data-ttu-id="595e9-206">**None**: オプションはありません。</span><span class="sxs-lookup"><span data-stu-id="595e9-206">**None**: No options.</span></span> <span data-ttu-id="595e9-207">この値は既定値です。</span><span class="sxs-lookup"><span data-stu-id="595e9-207">This value is the default.</span></span>
- <span data-ttu-id="595e9-208">**定数**: エイリアスを削除することはできません。また、そのプロパティを変更することもできません。</span><span class="sxs-lookup"><span data-stu-id="595e9-208">**Constant**:The alias cannot be deleted and its properties cannot be changed.</span></span>
  <span data-ttu-id="595e9-209">**定数** は、エイリアスを作成した場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="595e9-209">**Constant** is available only when you create an alias.</span></span> <span data-ttu-id="595e9-210">既存の別名のオプションを **定数** に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="595e9-210">You cannot change the option of an existing alias to **Constant**.</span></span>
- <span data-ttu-id="595e9-211">**プライベート**: 別名は、子スコープではなく、現在のスコープでのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="595e9-211">**Private**:The alias is visible only in the current scope, not in the child  scopes.</span></span>
- <span data-ttu-id="595e9-212">**ReadOnly**: パラメーターを使用する場合を除き、別名のプロパティを変更することはできません `-Force` 。</span><span class="sxs-lookup"><span data-stu-id="595e9-212">**ReadOnly**:The properties of the alias cannot be changed except by using the `-Force` parameter.</span></span> <span data-ttu-id="595e9-213">を使用し `Remove-Item` てエイリアスを削除できます。</span><span class="sxs-lookup"><span data-stu-id="595e9-213">You can use `Remove-Item` to delete the alias.</span></span>
- <span data-ttu-id="595e9-214">**Allscope**: 作成された新しいスコープにエイリアスがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="595e9-214">**AllScope**:The alias is copied to any new scopes that are created.</span></span>

#### <a name="cmdlets-supported"></a><span data-ttu-id="595e9-215">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="595e9-215">Cmdlets supported</span></span>

- [<span data-ttu-id="595e9-216">New-Item</span><span class="sxs-lookup"><span data-stu-id="595e9-216">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="595e9-217">Set-Item</span><span class="sxs-lookup"><span data-stu-id="595e9-217">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)

## <a name="using-the-pipeline"></a><span data-ttu-id="595e9-218">パイプラインの使用</span><span class="sxs-lookup"><span data-stu-id="595e9-218">Using the pipeline</span></span>

<span data-ttu-id="595e9-219">プロバイダーのコマンドレットは、パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="595e9-219">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="595e9-220">パイプラインを使用すると、1つのコマンドレットから別のプロバイダーのコマンドレットにプロバイダーデータを送信することにより、タスクを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="595e9-220">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="595e9-221">プロバイダーコマンドレットでパイプラインを使用する方法の詳細については、この記事全体で説明されているコマンドレットリファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="595e9-221">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="595e9-222">ヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="595e9-222">Getting help</span></span>

<span data-ttu-id="595e9-223">Windows PowerShell 3.0 より、プロバイダー コマンドレットのためにカスタマイズされたヘルプ トピックを取得できます。これはファイル システム ドライブでのプロバイダー コマンドレットの動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="595e9-223">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="595e9-224">ファイルシステムドライブ用にカスタマイズされたヘルプトピックを取得するには、ファイルシステムドライブで [get-help](xref:Microsoft.PowerShell.Core.Get-Help) コマンドを実行するか、 `-Path` [get-help](xref:Microsoft.PowerShell.Core.Get-Help) のパラメーターを使用してファイルシステムドライブを指定します。</span><span class="sxs-lookup"><span data-stu-id="595e9-224">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path alias:
```

## <a name="see-also"></a><span data-ttu-id="595e9-225">関連項目</span><span class="sxs-lookup"><span data-stu-id="595e9-225">See also</span></span>

[<span data-ttu-id="595e9-226">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="595e9-226">about_Aliases</span></span>](../About/about_Aliases.md)

[<span data-ttu-id="595e9-227">about_Providers</span><span class="sxs-lookup"><span data-stu-id="595e9-227">about_Providers</span></span>](../About/about_Providers.md)

