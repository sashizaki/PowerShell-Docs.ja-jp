---
description: 環境
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_environment_provider?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: 環境プロバイダー
ms.openlocfilehash: ae98e0e8c7d1c4a7e6e975b34e4c6e18b104c01b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223880"
---
# <a name="environment-provider"></a><span data-ttu-id="d7ca4-104">環境プロバイダー</span><span class="sxs-lookup"><span data-stu-id="d7ca4-104">Environment provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="d7ca4-105">プロバイダー名</span><span class="sxs-lookup"><span data-stu-id="d7ca4-105">Provider name</span></span>
<span data-ttu-id="d7ca4-106">環境</span><span class="sxs-lookup"><span data-stu-id="d7ca4-106">Environment</span></span>

## <a name="drives"></a><span data-ttu-id="d7ca4-107">ドライブ</span><span class="sxs-lookup"><span data-stu-id="d7ca4-107">Drives</span></span>

`Env:`

## <a name="capabilities"></a><span data-ttu-id="d7ca4-108">機能</span><span class="sxs-lookup"><span data-stu-id="d7ca4-108">Capabilities</span></span>

<span data-ttu-id="d7ca4-109">**ShouldProcess**</span><span class="sxs-lookup"><span data-stu-id="d7ca4-109">**ShouldProcess**</span></span>

## <a name="short-description"></a><span data-ttu-id="d7ca4-110">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="d7ca4-110">Short description</span></span>

<span data-ttu-id="d7ca4-111">Windows 環境変数へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-111">Provides access to the Windows environment variables.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="d7ca4-112">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="d7ca4-112">Detailed description</span></span>

<span data-ttu-id="d7ca4-113">PowerShell **環境** プロバイダーを使用すると、powershell で環境変数と値を取得、追加、変更、消去、削除できます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-113">The PowerShell **Environment** provider lets you get, add, change, clear, and delete environment variables and values in PowerShell.</span></span>

<span data-ttu-id="d7ca4-114">**環境** 変数は、プログラムが実行される環境を記述する変数として動的に名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-114">**Environment** variables are dynamically named variables that describe the environment in which your programs run.</span></span> <span data-ttu-id="d7ca4-115">Windows と PowerShell は、環境変数を使用して、システムとプロセスの実行に影響を与える永続的な情報を格納します。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-115">Windows and PowerShell use environment variables to store persistent information that affect system and process execution.</span></span> <span data-ttu-id="d7ca4-116">PowerShell 変数とは異なり、環境変数はスコープ制約の対象になりません。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-116">Unlike PowerShell variables, environment variables are not subject to scope constraints.</span></span>

<span data-ttu-id="d7ca4-117">**環境** ドライブは、現在のユーザーのセッションに固有の環境変数を含むフラットな名前空間です。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-117">The **Environment** drive is a flat namespace containing the environment variables specific to the current user's session.</span></span> <span data-ttu-id="d7ca4-118">環境変数に子項目はありません。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-118">The environment variables have no child items.</span></span>

<span data-ttu-id="d7ca4-119">**環境** プロバイダーは、この記事で説明されている次のコマンドレットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-119">The **Environment** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="d7ca4-120">Get-Location</span><span class="sxs-lookup"><span data-stu-id="d7ca4-120">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="d7ca4-121">Set-Location</span><span class="sxs-lookup"><span data-stu-id="d7ca4-121">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="d7ca4-122">Get-Item</span><span class="sxs-lookup"><span data-stu-id="d7ca4-122">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="d7ca4-123">New-Item</span><span class="sxs-lookup"><span data-stu-id="d7ca4-123">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="d7ca4-124">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="d7ca4-124">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="d7ca4-125">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="d7ca4-125">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="d7ca4-126">このプロバイダーによって公開される型</span><span class="sxs-lookup"><span data-stu-id="d7ca4-126">Types exposed by this provider</span></span>

<span data-ttu-id="d7ca4-127">各環境変数は、system.string [エントリ](/dotnet/api/system.collections.dictionaryentry) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-127">Each environment variable is an instance of the [System.Collections.DictionaryEntry](/dotnet/api/system.collections.dictionaryentry) class.</span></span> <span data-ttu-id="d7ca4-128">変数の名前はディクショナリ キーです。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-128">The name of the variable is the dictionary key.</span></span> <span data-ttu-id="d7ca4-129">環境変数の値はディクショナリ値です。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-129">The value of the environment variable is the dictionary value.</span></span>

## <a name="navigating-the-environment-drive"></a><span data-ttu-id="d7ca4-130">環境ドライブ内を移動する</span><span class="sxs-lookup"><span data-stu-id="d7ca4-130">Navigating the Environment drive</span></span>

<span data-ttu-id="d7ca4-131">**環境** プロバイダーは、ドライブ内のデータストアを公開し `Env:` ます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-131">The **Environment** provider exposes its data store in the `Env:` drive.</span></span> <span data-ttu-id="d7ca4-132">環境変数を操作するには、場所を `Env:` ドライブ () に変更するか、別の `Set-Location Env:` PowerShell ドライブから作業します。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-132">To work with environment variables, change your location to the `Env:` drive (`Set-Location Env:`), or work from another PowerShell drive.</span></span> <span data-ttu-id="d7ca4-133">別の場所から環境変数を参照するには、 `Env:` パス内のドライブ名を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-133">To reference an environment variable from another location, use the `Env:` drive name in the path.</span></span>

```powershell
Set-Location Env:
```

<span data-ttu-id="d7ca4-134">ファイル システム ドライブに戻るには、ドライブ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-134">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="d7ca4-135">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-135">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="d7ca4-136">他の PowerShell ドライブから **環境** プロバイダーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-136">You can also work with the **Environment** provider from any other PowerShell drive.</span></span> <span data-ttu-id="d7ca4-137">別の場所から環境変数を参照するには、パス内のドライブ名を使用し `Env:` ます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-137">To reference an environment variable from another location, use the drive name `Env:` in the path.</span></span>

<span data-ttu-id="d7ca4-138">**環境** プロバイダーは、の変数プレフィックスを使用して環境変数も公開し `$env:` ます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-138">The **Environment** provider also exposes environment variables using a variable prefix of `$env:`.</span></span>  <span data-ttu-id="d7ca4-139">次のコマンドは、 **ProgramFiles** 環境変数の内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-139">The following command views the contents of the **ProgramFiles** environment variable.</span></span> <span data-ttu-id="d7ca4-140">`$env:`変数プレフィックスは、任意の PowerShell ドライブから使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-140">The `$env:` variable prefix can be used from any PowerShell drive.</span></span>

```
PS C:\> $env:ProgramFiles
C:\Program Files
```

<span data-ttu-id="d7ca4-141">変数プレフィックスを使用して環境変数の値を変更することもでき `$env:` ます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-141">You can also change the value of an environment variable using the `$env:` variable prefix.</span></span>  <span data-ttu-id="d7ca4-142">変更は、アクティブになっている限り、現在の PowerShell セッションにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-142">Any changes made only pertain to the current PowerShell session for as long as it is active.</span></span>

> [!NOTE]
> <span data-ttu-id="d7ca4-143">PowerShell では、エイリアスを使用して、プロバイダーパスを操作するための使い慣れた方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-143">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="d7ca4-144">`dir`やなどのコマンド `ls` は、 [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem)のエイリアスです。これ `cd` は、 [Set Location](xref:Microsoft.PowerShell.Management.Set-Location)のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-144">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location).</span></span> <span data-ttu-id="d7ca4-145">と `pwd` は、 [Get Location](xref:Microsoft.PowerShell.Management.Get-Location)のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-145">and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

## <a name="getting-environment-variables"></a><span data-ttu-id="d7ca4-146">環境変数の取得</span><span class="sxs-lookup"><span data-stu-id="d7ca4-146">Getting environment variables</span></span>

<span data-ttu-id="d7ca4-147">このコマンドは、現在のセッションのすべての環境変数を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-147">This command lists all the environment variables in the current session.</span></span>

```powershell
Get-Item -Path Env:
```

<span data-ttu-id="d7ca4-148">このコマンドは、任意の PowerShell ドライブから使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-148">You can use this command from any PowerShell drive.</span></span>

<span data-ttu-id="d7ca4-149">環境プロバイダーにはコンテナーがないため、上のコマンドはと共に使用した場合と同じ効果があり `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-149">The Environment provider has no containers, so the above command has the same effect when used with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path Env:
```

### <a name="get-a-selected-environment-variable"></a><span data-ttu-id="d7ca4-150">選択した環境変数を取得します</span><span class="sxs-lookup"><span data-stu-id="d7ca4-150">Get a selected environment variable</span></span>

<span data-ttu-id="d7ca4-151">このコマンドは、 `WINDIR` 環境変数を取得します。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-151">This command gets the `WINDIR` environment Variable.</span></span>

```powershell
Get-ChildItem -Path Env:windir
```

<span data-ttu-id="d7ca4-152">また、変数プレフィックス形式も使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-152">You can also use the variable prefix format as well.</span></span>

```powershell
$env:windir
```

## <a name="create-an-environment-variable"></a><span data-ttu-id="d7ca4-153">環境変数を作成する</span><span class="sxs-lookup"><span data-stu-id="d7ca4-153">Create an environment variable</span></span>

<span data-ttu-id="d7ca4-154">このコマンドは、 `USERMODE` "非管理者" という値を持つ環境変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-154">This command creates the `USERMODE` environment variable with a value of "Non-Admin".</span></span> <span data-ttu-id="d7ca4-155">パラメーター値により、 `-Path` ドライブに新しい項目が作成され `Env:` ます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-155">The `-Path` parameter value creates the new item in the `Env:` drive.</span></span> <span data-ttu-id="d7ca4-156">新しい環境変数は、アクティブである限り、現在の PowerShell セッションでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-156">The new environment variable is only usable in the current PowerShell session for as long as it is active.</span></span>

```powershell
PS C:\> New-Item -Path Env: -Name USERMODE -Value Non-Admin
```

## <a name="changing-an-environment-variable"></a><span data-ttu-id="d7ca4-157">環境変数の変更</span><span class="sxs-lookup"><span data-stu-id="d7ca4-157">Changing an environment variable</span></span>

### <a name="rename-an-environment-variable"></a><span data-ttu-id="d7ca4-158">環境変数の名前を変更する</span><span class="sxs-lookup"><span data-stu-id="d7ca4-158">Rename an environment variable</span></span>

<span data-ttu-id="d7ca4-159">このコマンドは、コマンドレットを使用して、作成した `Rename-Item` 環境変数の名前をに変更し `USERMODE` `USERROLE` ます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-159">This command uses the `Rename-Item` cmdlet to change the name of the `USERMODE` environment variable that you created to `USERROLE`.</span></span> <span data-ttu-id="d7ca4-160">システムが使用する環境変数の名前は変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-160">Do not change the name of an environment variable that the system uses.</span></span> <span data-ttu-id="d7ca4-161">これらの変更は現在のセッションにのみ影響を与えますが、システムまたはプログラムの誤作動の原因になりかねません。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-161">Although these changes affect only the current session, they might cause the system or a program to operate incorrectly.</span></span>

```powershell
Rename-Item -Path Env:USERMODE -NewName USERROLE
```

### <a name="change-an-environment-variable"></a><span data-ttu-id="d7ca4-162">環境変数の変更</span><span class="sxs-lookup"><span data-stu-id="d7ca4-162">Change an environment variable</span></span>

<span data-ttu-id="d7ca4-163">このコマンドは、コマンドレットを使用して `Set-Item` 環境変数の値を `USERROLE` "Administrator" に変更します。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-163">This command uses the `Set-Item` cmdlet to change the value of the `USERROLE` environment variable to "Administrator".</span></span>

```powershell
Set-Item -Path Env:USERROLE -Value Administrator
```

## <a name="copy-an-environment-variable"></a><span data-ttu-id="d7ca4-164">環境変数をコピーする</span><span class="sxs-lookup"><span data-stu-id="d7ca4-164">Copy an environment variable</span></span>

<span data-ttu-id="d7ca4-165">このコマンドは、環境変数の値 `USERROLE` を `USERROLE2` 環境変数にコピーします。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-165">This command copies the value of the `USERROLE` environment variable to the `USERROLE2` environment Variable.</span></span>

```powershell
Copy-Item -Path Env:USERROLE -Destination Env:USERROLE2
```

## <a name="remove-an-environment-variable"></a><span data-ttu-id="d7ca4-166">環境変数を削除する</span><span class="sxs-lookup"><span data-stu-id="d7ca4-166">Remove an environment variable</span></span>

<span data-ttu-id="d7ca4-167">このコマンドは、 `USERROLE2` 現在のセッションから環境変数を削除します。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-167">This command deletes the `USERROLE2` environment variable from the current session.</span></span>

```powershell
Remove-Item -Path Env:USERROLE2
```

## <a name="remove-an-environment-variable-with-clear-item"></a><span data-ttu-id="d7ca4-168">Clear-Item を使用して環境変数を削除する</span><span class="sxs-lookup"><span data-stu-id="d7ca4-168">Remove an environment variable with Clear-Item</span></span>

<span data-ttu-id="d7ca4-169">このコマンドは、 `USERROLE` 値をクリアして環境変数を削除します。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-169">This command deletes the `USERROLE` environment variable by clearing its value.</span></span>

```powershell
Clear-Item -Path Env:USERROLE
```

## <a name="using-the-pipeline"></a><span data-ttu-id="d7ca4-170">パイプラインの使用</span><span class="sxs-lookup"><span data-stu-id="d7ca4-170">Using the pipeline</span></span>

<span data-ttu-id="d7ca4-171">プロバイダーのコマンドレットは、パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-171">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="d7ca4-172">パイプラインを使用すると、1つのコマンドレットから別のプロバイダーのコマンドレットにプロバイダーデータを送信することにより、タスクを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-172">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span>
<span data-ttu-id="d7ca4-173">プロバイダーコマンドレットでパイプラインを使用する方法の詳細については、この記事全体で説明されているコマンドレットリファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-173">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="d7ca4-174">ヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="d7ca4-174">Getting help</span></span>

<span data-ttu-id="d7ca4-175">Windows PowerShell 3.0 より、プロバイダー コマンドレットのためにカスタマイズされたヘルプ トピックを取得できます。これはファイル システム ドライブでのプロバイダー コマンドレットの動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-175">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="d7ca4-176">ファイルシステムドライブ用にカスタマイズされたヘルプトピックを取得するには、ファイルシステムドライブで [get-help](xref:Microsoft.PowerShell.Core.Get-Help) コマンドを実行するか、 `-Path` [get-help](xref:Microsoft.PowerShell.Core.Get-Help) のパラメーターを使用してファイルシステムドライブを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7ca4-176">To get the help topics that are customized for the file system drive, run a [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) command in a file system drive or use the `-Path` parameter of [Get-Help](xref:Microsoft.PowerShell.Core.Get-Help) to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path env:
```

## <a name="see-also"></a><span data-ttu-id="d7ca4-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7ca4-177">See also</span></span>

[<span data-ttu-id="d7ca4-178">about_Providers</span><span class="sxs-lookup"><span data-stu-id="d7ca4-178">about_Providers</span></span>](../About/about_Providers.md)
