---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 5/16/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/update-help?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Help
ms.openlocfilehash: 4ef0865e81e01746fed77b73e265e68086a7a9e1
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "93219120"
---
# <span data-ttu-id="30e75-103">Update-Help</span><span class="sxs-lookup"><span data-stu-id="30e75-103">Update-Help</span></span>

## <span data-ttu-id="30e75-104">概要</span><span class="sxs-lookup"><span data-stu-id="30e75-104">SYNOPSIS</span></span>
<span data-ttu-id="30e75-105">最新のヘルプ ファイルをダウンロードしてコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="30e75-105">Downloads and installs the newest help files on your computer.</span></span>

## <span data-ttu-id="30e75-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="30e75-106">SYNTAX</span></span>

### <span data-ttu-id="30e75-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="30e75-107">Path (Default)</span></span>

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [[-SourcePath] <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="30e75-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="30e75-108">LiteralPath</span></span>

```
Update-Help [[-Module] <String[]>] [-FullyQualifiedModule <ModuleSpecification[]>]
 [-LiteralPath <String[]>] [-Recurse] [[-UICulture] <CultureInfo[]>] [-Credential <PSCredential>]
 [-UseDefaultCredentials] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="30e75-109">Description</span><span class="sxs-lookup"><span data-stu-id="30e75-109">DESCRIPTION</span></span>

<span data-ttu-id="30e75-110">`Update-Help`コマンドレットにより、PowerShell モジュールの最新のヘルプファイルがダウンロードされ、コンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="30e75-110">The `Update-Help` cmdlet downloads the newest help files for PowerShell modules and installs them on your computer.</span></span> <span data-ttu-id="30e75-111">変更を有効にするには、PowerShell を再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="30e75-111">You need not restart PowerShell to make the change effective.</span></span> <span data-ttu-id="30e75-112">コマンドレットを使用して、 `Get-Help` 新しいヘルプファイルをすぐに表示できます。</span><span class="sxs-lookup"><span data-stu-id="30e75-112">You can use the `Get-Help` cmdlet to view the new help files immediately.</span></span>

<span data-ttu-id="30e75-113">`Update-Help` コンピューター上のヘルプファイルのバージョンを確認します。</span><span class="sxs-lookup"><span data-stu-id="30e75-113">`Update-Help` checks the version of the help files on your computer.</span></span> <span data-ttu-id="30e75-114">モジュールのヘルプファイルがない場合、またはヘルプファイルが古くなっている場合は、に `Update-Help` よって最新のヘルプファイルがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="30e75-114">If you don't have help files for a module or if your help files are outdated, `Update-Help` downloads the newest help files.</span></span> <span data-ttu-id="30e75-115">ヘルプファイルは、インターネットまたはファイル共有からダウンロードしてインストールできます。</span><span class="sxs-lookup"><span data-stu-id="30e75-115">The help files can be downloaded and installed from the internet or a file share.</span></span>

<span data-ttu-id="30e75-116">パラメーターを指定しない場合、は、 `Update-Help` セッション内のモジュールのヘルプファイルと、更新可能なヘルプをサポートするすべてのインストール済みモジュールのヘルプファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="30e75-116">Without parameters, `Update-Help` updates the help files for modules in the session and for all installed modules that support Updatable Help.</span></span> <span data-ttu-id="30e75-117">インストールされているが現在のセッションに読み込まれていないモジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="30e75-117">Modules that are installed but not loaded in the current session are included.</span></span> <span data-ttu-id="30e75-118">PowerShell モジュールは、環境変数に示されている場所に格納され `$env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-118">PowerShell modules are stored in a location listed in the `$env:PSModulePath` environment variable.</span></span> <span data-ttu-id="30e75-119">詳しくは、「[about_Updatable_Help](./About/about_Updatable_Help.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="30e75-119">For more information, see [about_Updatable_Help](./About/about_Updatable_Help.md).</span></span>

<span data-ttu-id="30e75-120">**Module** パラメーターを使用して、特定のモジュールのヘルプファイルを更新できます。</span><span class="sxs-lookup"><span data-stu-id="30e75-120">You can use the **Module** parameter to update help files for a particular module.</span></span> <span data-ttu-id="30e75-121">複数の言語およびロケールのヘルプファイルをダウンロードするには、 **UICulture** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="30e75-121">Use the **UICulture** parameter to download help files in multiple languages and locales.</span></span>

<span data-ttu-id="30e75-122">また `Update-Help` 、インターネットに接続されていないコンピューターでを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="30e75-122">You can also use `Update-Help` on computers that are not connected to the internet.</span></span> <span data-ttu-id="30e75-123">まず、コマンドレットを使用して、 `Save-Help` インターネットからヘルプファイルをダウンロードし、インターネットに接続されていないシステムからアクセスできる共有フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="30e75-123">First, use the `Save-Help`cmdlet to download help files from the internet and save them in a shared folder that is accessible to the system not connected to the internet.</span></span> <span data-ttu-id="30e75-124">次に、の **SourcePath** パラメーターを使用して `Update-Help` 、更新されたヘルプファイルを共有からダウンロードし、コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="30e75-124">Then use the **SourcePath** parameter of `Update-Help` to download the updated help files from the shared and install them on the computer.</span></span>

<span data-ttu-id="30e75-125">PowerShell プロファイルにコマンドレットを追加することで、ヘルプの更新を自動化でき `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-125">You can automate help updates by adding the `Update-Help` cmdlet to your PowerShell profile.</span></span> <span data-ttu-id="30e75-126">既定では、は `Update-Help` 各コンピューターで1日1回だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="30e75-126">By default, `Update-Help` runs only one time per day on each computer.</span></span> <span data-ttu-id="30e75-127">1 日に 1 回という制限をオーバーライドするには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="30e75-127">To override the once-per-day limit, use the **Force** parameter.</span></span>

<span data-ttu-id="30e75-128">この `Update-Help` コマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="30e75-128">The `Update-Help` cmdlet was introduced in Windows PowerShell 3.0.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30e75-129">`Update-Help` 管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="30e75-129">`Update-Help` requires administrative privileges.</span></span>
>
> <span data-ttu-id="30e75-130">PowerShell コアモジュールのヘルプファイルを更新するには、コンピューターの Administrators グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="30e75-130">You must be a member of the Administrators group on the computer to update the help files for the PowerShell Core modules.</span></span>
>
> <span data-ttu-id="30e75-131">Powershell のコアモジュールを含む、PowerShell のインストールディレクトリ () のモジュールのヘルプファイルをダウンロードまたは更新するには、 `$PSHOME\Modules` [管理者として実行] オプションを使用して powershell を起動します。</span><span class="sxs-lookup"><span data-stu-id="30e75-131">To download or update the help files for modules in the PowerShell installation directory (`$PSHOME\Modules`), including the PowerShell Core modules, start PowerShell by using the Run as administrator option.</span></span>
> <span data-ttu-id="30e75-132">(例: `Start-Process powershell.exe -Verb RunAs`)。</span><span class="sxs-lookup"><span data-stu-id="30e75-132">For example: `Start-Process powershell.exe -Verb RunAs`.</span></span>
>
> <span data-ttu-id="30e75-133">Windows PowerShell Integrated Scripting Environment (ISE) の [ヘルプ] メニューの [Windows PowerShell の更新] を使用して、ヘルプファイルを更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="30e75-133">You can also update help files by using the Update Windows PowerShell Help menu item in the Help menu in Windows PowerShell Integrated Scripting Environment (ISE).</span></span>
>
> <span data-ttu-id="30e75-134">Windows PowerShell の更新のヘルプ項目は、 `Update-Help` パラメーターを指定せずにコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="30e75-134">The Update Windows PowerShell Help item runs an `Update-Help` cmdlet without parameters.</span></span>
> <span data-ttu-id="30e75-135">ディレクトリ内のモジュールのヘルプを更新するには、 `$PSHOME` [管理者として実行] オプションを使用して Windows PowerShell ISE を開始します。</span><span class="sxs-lookup"><span data-stu-id="30e75-135">To update help for modules in the `$PSHOME` directory, start Windows PowerShell ISE by using the Run as administrator option.</span></span>

## <span data-ttu-id="30e75-136">例</span><span class="sxs-lookup"><span data-stu-id="30e75-136">EXAMPLES</span></span>

### <span data-ttu-id="30e75-137">例 1: すべてのモジュールのヘルプファイルを更新する</span><span class="sxs-lookup"><span data-stu-id="30e75-137">Example 1: Update help files for all modules</span></span>

<span data-ttu-id="30e75-138">コマンドレットは、更新 `Update-Help` 可能なヘルプをサポートするインストール済みモジュールのヘルプファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="30e75-138">The `Update-Help` cmdlet updates help files for installed modules that support Updatable Help.</span></span> <span data-ttu-id="30e75-139">ユーザーインターフェイス (UI) カルチャ言語は、オペレーティングシステムで設定されます。</span><span class="sxs-lookup"><span data-stu-id="30e75-139">The user-interface (UI) culture language is set in the operating system.</span></span>

```powershell
Update-Help
```

### <span data-ttu-id="30e75-140">例 2: 指定したモジュールのヘルプファイルを更新する</span><span class="sxs-lookup"><span data-stu-id="30e75-140">Example 2: Update help files for specified modules</span></span>

<span data-ttu-id="30e75-141">`Update-Help`コマンドレットは、 **Microsoft. PowerShell** で始まるモジュール名のヘルプファイルのみを更新します。</span><span class="sxs-lookup"><span data-stu-id="30e75-141">The `Update-Help` cmdlet updates help files only for module names that begin with **Microsoft.PowerShell**.</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell*
```

### <span data-ttu-id="30e75-142">例 3: さまざまな言語のヘルプファイルを更新する</span><span class="sxs-lookup"><span data-stu-id="30e75-142">Example 3: Update help files for different languages</span></span>

<span data-ttu-id="30e75-143">この `Update-Help` コマンドレットは、すべてのモジュールの日本語 (ja-jp) と英語 (en-us) のヘルプファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="30e75-143">The `Update-Help` cmdlet updates the Japanese (ja-JP) and English (en-US) help files for all modules.</span></span>

<span data-ttu-id="30e75-144">指定した UI カルチャのヘルプファイルがモジュールで提供されていない場合は、モジュールと UI カルチャのエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30e75-144">If a module doesn't provide help files for a specified UI culture, an error message is displayed for the module and UI culture.</span></span> <span data-ttu-id="30e75-145">この例では、エラーメッセージは、モジュールの **Microsoft. PowerShell. ユーティリティ** に対して **ja-jp** ヘルプファイルが見つからなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="30e75-145">In this example, the error message indicates that the **ja-JP** help files were not found for module **Microsoft.PowerShell.Utility**.</span></span>

```powershell
Update-Help -UICulture ja-JP, en-US
```

```Output
Update-Help : Failed to update Help for the module(s) 'Microsoft.PowerShell.Utility' with UI culture(s) {ja-JP}
No UI culture was found that matches the following pattern: ja-JP.
```

### <span data-ttu-id="30e75-146">例 4: ヘルプファイルを自動的に更新する</span><span class="sxs-lookup"><span data-stu-id="30e75-146">Example 4: Update help files automatically</span></span>

<span data-ttu-id="30e75-147">この例では、毎日 3:00 AM にすべてのモジュールのヘルプを更新するスケジュールされたジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="30e75-147">This example creates a scheduled job that updates help for all modules every day at 3:00 AM.</span></span>

```powershell
$jobParams = @{
  Name = 'UpdateHelpJob'
  Credential = 'Domain01\User01'
  ScriptBlock = '{Update-Help}'
  Trigger = (New-JobTrigger -Daily -At "3 AM")
}
Register-ScheduledJob @jobParams
```

```Output
Id         Name            JobTriggers     Command                                  Enabled
--         ----            -----------     -------                                  -------
1          UpdateHelpJob   1               Update-Help                              True
```

<span data-ttu-id="30e75-148">`Register-ScheduledJob`コマンドレットは、コマンドを実行するスケジュールされたジョブを作成し `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-148">The `Register-ScheduledJob` cmdlet creates a scheduled job that runs an `Update-Help` command.</span></span> <span data-ttu-id="30e75-149">このコマンドは、 **Credential** パラメーターを使用し `Update-Help` て、コンピューター上の Administrators グループのメンバーの資格情報を使用して実行します。</span><span class="sxs-lookup"><span data-stu-id="30e75-149">The command uses the **Credential** parameter to run `Update-Help` by using the credentials of a member of the Administrators group on the computer.</span></span> <span data-ttu-id="30e75-150">**Trigger** パラメーターの値は、 `New-JobTrigger` 毎日 3:00 AM にジョブを開始するジョブトリガーを作成するコマンドです。</span><span class="sxs-lookup"><span data-stu-id="30e75-150">The value of the **Trigger** parameter is a `New-JobTrigger` command that creates a job trigger that starts the job every day at 3:00 AM.</span></span>

<span data-ttu-id="30e75-151">コマンドを実行するに `Register-ScheduledJob` は、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="30e75-151">To run the `Register-ScheduledJob` command, start PowerShell by using the **Run as administrator** option.</span></span> <span data-ttu-id="30e75-152">PowerShell は、 **Credential** パラメーターで指定されたユーザーのパスワードの入力を求めます。</span><span class="sxs-lookup"><span data-stu-id="30e75-152">PowerShell prompts you for the password of the user specified in the **Credential** parameter.</span></span> <span data-ttu-id="30e75-153">資格情報は、スケジュールされたジョブと共に保存されます。</span><span class="sxs-lookup"><span data-stu-id="30e75-153">The credentials are stored with the scheduled job.</span></span> <span data-ttu-id="30e75-154">ジョブの実行時にメッセージが表示されることはありません。</span><span class="sxs-lookup"><span data-stu-id="30e75-154">You aren't prompted when the job runs.</span></span>

<span data-ttu-id="30e75-155">コマンドレットを使用してスケジュールされたジョブを表示し、 `Get-ScheduledJob` コマンドレットを使用してジョブを変更し、コマンドレットを使用してジョブを削除することができ `Set-ScheduledJob` `Unregister-ScheduledJob` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-155">You can use the `Get-ScheduledJob` cmdlet to view the scheduled job, use the `Set-ScheduledJob` cmdlet to change it, and use the `Unregister-ScheduledJob` cmdlet to delete it.</span></span> <span data-ttu-id="30e75-156">また、次に示すパス内のタスク スケジューラでスケジュール済みジョブの表示と管理ができます:</span><span class="sxs-lookup"><span data-stu-id="30e75-156">You can also view and manage the scheduled job in Task Scheduler in the following path:</span></span>

<span data-ttu-id="30e75-157">`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs`.</span><span class="sxs-lookup"><span data-stu-id="30e75-157">`Task Scheduler Library\Microsoft\Windows\PowerShell\ScheduledJobs`.</span></span>

### <span data-ttu-id="30e75-158">例 5: ファイル共有から複数のコンピューターのヘルプファイルを更新する</span><span class="sxs-lookup"><span data-stu-id="30e75-158">Example 5: Update help files on multiple computers from a file share</span></span>

<span data-ttu-id="30e75-159">この例では、更新されたヘルプファイルをインターネットからダウンロードし、ファイル共有に保存します。</span><span class="sxs-lookup"><span data-stu-id="30e75-159">In this example, updated help files are downloaded from the internet and saved in a file share.</span></span> <span data-ttu-id="30e75-160">ユーザーの資格情報は、ファイル共有にアクセスして更新プログラムをインストールするためのアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="30e75-160">User credentials are needed that have permissions to access the file share and install updates.</span></span> <span data-ttu-id="30e75-161">ファイル共有を使用すると、ファイアウォールの背後にあるコンピューターや、インターネットに接続されていないコンピューターを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="30e75-161">When a file share is used, it's possible to update computers that are behind firewalls or aren't connected to the internet.</span></span>

```powershell
Save-Help -DestinationPath \\Server01\Share\PSHelp -Credential Domain01\Admin01
Invoke-Command -ComputerName (Get-Content Servers.txt) -ScriptBlock {
     Update-Help -SourcePath \\Server01\Share\PSHelp -Credential Domain01\Admin01
}
```

<span data-ttu-id="30e75-162">この `Save-Help` コマンドは、更新可能なヘルプをサポートするすべてのモジュールの最新のヘルプファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="30e75-162">The `Save-Help` command downloads the newest help files for all modules that support Updatable Help.</span></span>
<span data-ttu-id="30e75-163">**DestinationPath** パラメーターを指定すると、ファイル共有にファイルが保存され `\\Server01\Share\PSHelp` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-163">The **DestinationPath** parameter saves the files in the `\\Server01\Share\PSHelp` file share.</span></span> <span data-ttu-id="30e75-164">**Credential** パラメーターは、ファイル共有にアクセスする権限を持つユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="30e75-164">The **Credential** parameter specifies a user who has permission to access the file share.</span></span>

<span data-ttu-id="30e75-165">`Invoke-Command`コマンドレットは、 `Update-Help` 複数のコンピューターでリモートコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="30e75-165">The `Invoke-Command` cmdlet runs remote `Update-Help` commands on multiple computers.</span></span> <span data-ttu-id="30e75-166">**ComputerName** パラメーターは、 **Servers.txt** ファイルからリモートコンピューターの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="30e75-166">The **ComputerName** parameter gets a list of remote computers from the **Servers.txt** file.</span></span> <span data-ttu-id="30e75-167">**ScriptBlock** パラメーターはコマンドを実行 `Update-Help` し、 **SourcePath** パラメーターを使用して、更新されたヘルプファイルを含むファイル共有を指定します。</span><span class="sxs-lookup"><span data-stu-id="30e75-167">The **ScriptBlock** parameter runs the `Update-Help` command and uses the **SourcePath** parameter to specify the file share that contains the updated help files.</span></span> <span data-ttu-id="30e75-168">**Credential** パラメーターは、ファイル共有にアクセスしてリモートコマンドを実行できるユーザーを指定し `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-168">The **Credential** parameter specifies a user who can access the file share and run the remote `Update-Help` command.</span></span>

### <span data-ttu-id="30e75-169">例 6: 更新されたヘルプファイルの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="30e75-169">Example 6: Get a list of updated help files</span></span>

<span data-ttu-id="30e75-170">`Update-Help`コマンドレットは、指定されたモジュールのヘルプを更新します。</span><span class="sxs-lookup"><span data-stu-id="30e75-170">The `Update-Help` cmdlet updates help for a specified module.</span></span> <span data-ttu-id="30e75-171">コマンドレットでは、 **Verbose** 共通パラメーターを使用して、更新されたヘルプファイルの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="30e75-171">The cmdlet uses the **Verbose** common parameter to display the list of help files that were updated.</span></span> <span data-ttu-id="30e75-172">**Verbose** を使用して、特定のモジュールのすべてのヘルプファイルまたはヘルプファイルの出力を表示できます。</span><span class="sxs-lookup"><span data-stu-id="30e75-172">You can use **Verbose** to view output for all help files or help files for a specific module.</span></span>

<span data-ttu-id="30e75-173">**Verbose** パラメーターを指定しない場合、 `Update-Help` コマンドの結果は表示されません。</span><span class="sxs-lookup"><span data-stu-id="30e75-173">Without the **Verbose** parameter, `Update-Help` doesn't display the results of the command.</span></span> <span data-ttu-id="30e75-174">**Verbose** パラメーターの出力は、ヘルプファイルが更新されたこと、または最新バージョンがインストールされているかどうかを確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="30e75-174">The **Verbose** parameter output is useful to verify that the help files were updated or if the latest version is installed.</span></span>

```powershell
Update-Help -Module Microsoft.PowerShell.Utility -Verbose
```

### <span data-ttu-id="30e75-175">例 7: 更新可能なヘルプをサポートするモジュールを検索する</span><span class="sxs-lookup"><span data-stu-id="30e75-175">Example 7: Find modules that support Updatable Help</span></span>

<span data-ttu-id="30e75-176">この例では、更新可能なヘルプをサポートするモジュールを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="30e75-176">This example lists modules that support Updatable Help.</span></span> <span data-ttu-id="30e75-177">このコマンドは、モジュールの **Helpinfouri** プロパティを使用して、更新可能なヘルプをサポートするモジュールを識別します。</span><span class="sxs-lookup"><span data-stu-id="30e75-177">The command uses the module's **HelpInfoUri** property to identify modules that support Updatable Help.</span></span> <span data-ttu-id="30e75-178">**Helpinfouri** プロパティには、コマンドレットの実行時にリダイレクトされるアドレスが含まれてい `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-178">The **HelpInfoUri** property contains an address that is redirected when the `Update-Help` cmdlet is run.</span></span>

```powershell
Get-Module -ListAvailable | Where-Object -Property HelpInfoUri
```

```output
   Directory: C:\program files\powershell\6\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   6.1.0.0    CimCmdlets                          Core      {Get-CimAssociatedInstance... }
Manifest   1.2.2.0    Microsoft.PowerShell.Archive        Desk      {Compress-Archive... }
Manifest   6.1.0.0    Microsoft.PowerShell.Diagnostics    Core      {Get-WinEvent, New-WinEvent}

    Directory: C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules

ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   2.0.1.0    Appx                                Core,Desk {Add-AppxPackage, ... }
Script     1.0.0.0    AssignedAccess                      Core,Desk {Clear-AssignedAccess, ... }
Manifest   1.0.0.0    BitLocker                           Core,Desk {Unlock-BitLocker, ... }
```

### <span data-ttu-id="30e75-179">例 8: 更新されたヘルプファイルをインベントリする</span><span class="sxs-lookup"><span data-stu-id="30e75-179">Example 8: Inventory updated help files</span></span>

<span data-ttu-id="30e75-180">この例では、スクリプトによって、 `Get-UpdateHelpVersion.ps1` 各モジュールの更新可能なヘルプファイルとそのバージョン番号のインベントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="30e75-180">In this example, the script `Get-UpdateHelpVersion.ps1` creates an inventory of the Updatable Help files for each module and their version numbers.</span></span>

<span data-ttu-id="30e75-181">このスクリプトは、モジュールの **Helpinfouri** プロパティを使用して、更新可能なヘルプをサポートするモジュールを識別します。</span><span class="sxs-lookup"><span data-stu-id="30e75-181">The script identifies modules that support Updatable Help by using the **HelpInfoUri** property of modules.</span></span> <span data-ttu-id="30e75-182">更新可能なヘルプをサポートするモジュールの場合、スクリプトはヘルプ情報ファイル (\* helpinfo.xml) を検索して解析し、最新のバージョン番号を検索します。</span><span class="sxs-lookup"><span data-stu-id="30e75-182">For modules that support Updatable Help, the script looks for and parses the help information file (\*helpinfo.xml) to find the latest version number.</span></span>

<span data-ttu-id="30e75-183">このスクリプトでは、 **Pscustomobject** いうクラスとハッシュテーブルを使用して、カスタム出力オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="30e75-183">The script uses the **PSCustomObject** class and a hash table to create a custom output object.</span></span>

```powershell
# Get-UpdateHelpVersion.ps1
Param(
    [parameter(Mandatory=$False)]
    [String[]]
    $Module
)
$HelpInfoNamespace = @{helpInfo='http://schemas.microsoft.com/powershell/help/2010/05'}

if ($Module) { $Modules = Get-Module $Module -ListAvailable | where {$_.HelpInfoUri} }
else { $Modules = Get-Module -ListAvailable | where {$_.HelpInfoUri} }

foreach ($mModule in $Modules)
{
    $mDir = $mModule.ModuleBase

    if (Test-Path $mdir\*helpinfo.xml)
    {
        $mName=$mModule.Name
        $mNodes = dir $mdir\*helpinfo.xml -ErrorAction SilentlyContinue |
            Select-Xml -Namespace $HelpInfoNamespace -XPath "//helpInfo:UICulture"
        foreach ($mNode in $mNodes)
        {
            $mCulture=$mNode.Node.UICultureName
            $mVer=$mNode.Node.UICultureVersion

            [PSCustomObject]@{"ModuleName"=$mName; "Culture"=$mCulture; "Version"=$mVer}
        }
    }
}
```

```Output
ModuleName                              Culture                                 Version
----------                              -------                                 -------
ActiveDirectory                         en-US                                   3.0.0.0
ADCSAdministration                      en-US                                   3.0.0.0
ADCSDeployment                          en-US                                   3.0.0.0
ADDSDeployment                          en-US                                   3.0.0.0
ADFS                                    en-US                                   3.0.0.0
```

## <span data-ttu-id="30e75-184">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="30e75-184">PARAMETERS</span></span>

### <span data-ttu-id="30e75-185">-Credential</span><span class="sxs-lookup"><span data-stu-id="30e75-185">-Credential</span></span>

<span data-ttu-id="30e75-186">**SourcePath** によって指定されたファイルシステムの場所にアクセスする権限を持つユーザーの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="30e75-186">Specifies credentials of a user who has permission to access the file system location specified by **SourcePath**.</span></span> <span data-ttu-id="30e75-187">このパラメーターは、コマンドに **SourcePath** または **LiteralPath** パラメーターが使用されている場合に限り有効です。</span><span class="sxs-lookup"><span data-stu-id="30e75-187">This parameter is valid only when the **SourcePath** or **LiteralPath** parameter is used in the command.</span></span>

<span data-ttu-id="30e75-188">**Credential** パラメーターを使用すると、 `Update-Help` リモートコンピューター上で **SourcePath** パラメーターを使用してコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="30e75-188">The **Credential** parameter enables you to run `Update-Help` commands with the **SourcePath** parameter on remote computers.</span></span> <span data-ttu-id="30e75-189">明示的な資格情報を指定することにより、リモートコンピューターでコマンドを実行し、アクセス拒否エラーが発生しないか、CredSSP 認証を使用して資格情報を委任することなく、3台目のコンピューター上のファイル共有にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="30e75-189">By providing explicit credentials, you can run the command on a remote computer and access a file share on a third computer without encountering an access denied error or using CredSSP authentication to delegate credentials.</span></span>

<span data-ttu-id="30e75-190">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-190">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="30e75-191">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="30e75-191">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="30e75-192">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="30e75-192">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="30e75-193">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30e75-193">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30e75-194">-Force</span><span class="sxs-lookup"><span data-stu-id="30e75-194">-Force</span></span>

<span data-ttu-id="30e75-195">このコマンドレットが1日に1回の制限に従っていないことを示し、バージョンチェックをスキップし、1 GB の制限を超えるファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="30e75-195">Indicates that this cmdlet doesn't follow the once-per-day limitation, skips version checking, and downloads files that exceed the 1 GB limit.</span></span>

<span data-ttu-id="30e75-196">このパラメーターを指定しないと、は `Update-Help` 24 時間ごとに1回だけ実行されます。</span><span class="sxs-lookup"><span data-stu-id="30e75-196">Without this parameter, `Update-Help` runs only once in each 24-hour period.</span></span> <span data-ttu-id="30e75-197">ダウンロードは、モジュールあたり 1 GB の圧縮されていないコンテンツに制限されており、ヘルプファイルはコンピューター上の既存のファイルより新しい場合にのみインストールされます。</span><span class="sxs-lookup"><span data-stu-id="30e75-197">Downloads are limited to 1 GB of uncompressed content per module and help files are only installed when they're newer than the existing files on the computer.</span></span>

<span data-ttu-id="30e75-198">1日に1回の制限により、ヘルプファイルをホストするサーバーが保護され、 `Update-Help` 接続やダウンロードが繰り返されるリソースコストを発生させることなく、PowerShell プロファイルにコマンドを追加することが実用的になります。</span><span class="sxs-lookup"><span data-stu-id="30e75-198">The once-per-day limit protects the servers that host the help files and makes it practical for you to add an `Update-Help` command to your PowerShell profile without incurring the resource cost of repeated connections or downloads.</span></span>

<span data-ttu-id="30e75-199">**Force** パラメーターを使用しないで、複数の UI カルチャ内のモジュールのヘルプを更新するには、次のように、同じコマンドの中にすべての UI カルチャを含めます。</span><span class="sxs-lookup"><span data-stu-id="30e75-199">To update help for a module in multiple UI cultures without the **Force** parameter, include all UI cultures in the same command, such as:</span></span>

`Update-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30e75-200">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="30e75-200">-FullyQualifiedModule</span></span>

<span data-ttu-id="30e75-201">**Modul特定** のオブジェクトの形式で指定された名前を持つモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="30e75-201">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span>
<span data-ttu-id="30e75-202">これらのモジュールについては、「 [modulの通知コンストラクター (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_)」の「解説」で説明されています。</span><span class="sxs-lookup"><span data-stu-id="30e75-202">These modules are described in the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="30e75-203">たとえば、 **FullyQualifiedModule** パラメーターは、次の形式で指定されたモジュール名を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="30e75-203">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in the format:</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"}`

<span data-ttu-id="30e75-204">or</span><span class="sxs-lookup"><span data-stu-id="30e75-204">or</span></span>

`@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}.`

<span data-ttu-id="30e75-205">**ModuleName** と **ModuleVersion** は必須ですが、 **Guid** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="30e75-205">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="30e75-206">**モジュール** パラメーターと同じコマンドで **FullyQualifiedModule** パラメーターを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="30e75-206">You can't specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="30e75-207">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="30e75-207">-LiteralPath</span></span>

<span data-ttu-id="30e75-208">更新されたヘルプファイルをインターネットからダウンロードするのではなく、そのフォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="30e75-208">Specifies the folder for updated help files instead of downloading them from the internet.</span></span> <span data-ttu-id="30e75-209">コマンドレットを使用してヘルプファイルをディレクトリにダウンロードした場合は、このパラメーターまたは **SourcePath** を使用し `Save-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-209">Use this parameter or **SourcePath** if you've used the `Save-Help` cmdlet to download help files to a directory.</span></span>

<span data-ttu-id="30e75-210">またはコマンドレットなどのディレクトリオブジェクトをにパイプライン `Get-Item` でき `Get-ChildItem` `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-210">You can pipeline a directory object, such as from the `Get-Item` or `Get-ChildItem` cmdlets, to `Update-Help`.</span></span>

<span data-ttu-id="30e75-211">**SourcePath** の値とは異なり、 **LiteralPath** の値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="30e75-211">Unlike the value of **SourcePath** , the value of **LiteralPath** is used exactly as it's typed.</span></span> <span data-ttu-id="30e75-212">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="30e75-212">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="30e75-213">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="30e75-213">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="30e75-214">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="30e75-214">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="30e75-215">-モジュール</span><span class="sxs-lookup"><span data-stu-id="30e75-215">-Module</span></span>

<span data-ttu-id="30e75-216">指定したモジュールのヘルプを更新します。</span><span class="sxs-lookup"><span data-stu-id="30e75-216">Updates help for the specified modules.</span></span> <span data-ttu-id="30e75-217">1つ以上のモジュール名または名前パターンをコンマ区切りのリストで入力するか、各行に1つのモジュール名を一覧表示するファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="30e75-217">Enter one or more module names or name patterns in a comma-separated list, or specify a file that lists one module name on each line.</span></span> <span data-ttu-id="30e75-218">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="30e75-218">Wildcard characters are permitted.</span></span> <span data-ttu-id="30e75-219">コマンドレットからコマンドレットにモジュールをパイプラインすることができ `Get-Module` `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-219">You can pipeline modules from the `Get-Module` cmdlet to the `Update-Help` cmdlet.</span></span>

<span data-ttu-id="30e75-220">指定するモジュールはコンピューターにインストールする必要がありますが、現在のセッションにインポートする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="30e75-220">The modules that you specify must be installed on the computer, but they don't have to be imported into the current session.</span></span> <span data-ttu-id="30e75-221">セッション内の任意のモジュール、または環境変数に示されている場所にインストールされている任意のモジュールを指定でき `$env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-221">You can specify any module in the session or any module that is installed in a location listed in the `$env:PSModulePath` environment variable.</span></span>

<span data-ttu-id="30e75-222">(すべて) の値は、 `*` コンピューターにインストールされているすべてのモジュールのヘルプを更新しようとします。</span><span class="sxs-lookup"><span data-stu-id="30e75-222">A value of `*` (all) attempts to update help for all modules that are installed on the computer.</span></span>
<span data-ttu-id="30e75-223">更新可能なヘルプをサポートしていないモジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="30e75-223">Modules that don't support Updatable Help are included.</span></span> <span data-ttu-id="30e75-224">この値は、コマンドで更新可能なヘルプをサポートしていないモジュールが検出された場合にエラーを生成することがあります。</span><span class="sxs-lookup"><span data-stu-id="30e75-224">This value might generate errors when the command encounters modules that don't support Updatable Help.</span></span> <span data-ttu-id="30e75-225">代わりに、 `Update-Help` パラメーターを指定せずにを実行します。</span><span class="sxs-lookup"><span data-stu-id="30e75-225">Instead, run `Update-Help` without parameters.</span></span>

<span data-ttu-id="30e75-226">コマンドレットの **module** パラメーターは、 `Update-Help` モジュールファイルまたはモジュールマニフェストファイルの完全なパスを受け入れません。</span><span class="sxs-lookup"><span data-stu-id="30e75-226">The **Module** parameter of the `Update-Help` cmdlet doesn't accept the full path of a module file or module manifest file.</span></span> <span data-ttu-id="30e75-227">場所にないモジュールのヘルプを更新するには、 `$env:PSModulePath` コマンドを実行する前に、現在のセッションにモジュールをインポートし `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-227">To update help for a module that isn't in a `$env:PSModulePath` location, import the module into the current session before you run the `Update-Help` command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="30e75-228">-再帰</span><span class="sxs-lookup"><span data-stu-id="30e75-228">-Recurse</span></span>

<span data-ttu-id="30e75-229">指定されたディレクトリ内のヘルプファイルに対して再帰的な検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="30e75-229">Performs a recursive search for help files in the specified directory.</span></span> <span data-ttu-id="30e75-230">このパラメーターは、コマンドで **SourcePath** パラメーターが使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="30e75-230">This parameter is valid only when the command uses the **SourcePath** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30e75-231">-SourcePath</span><span class="sxs-lookup"><span data-stu-id="30e75-231">-SourcePath</span></span>

<span data-ttu-id="30e75-232">が `Update-Help` インターネットからダウンロードするのではなく、更新されたヘルプファイルを取得するファイルシステムフォルダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="30e75-232">Specifies a file system folder where `Update-Help` gets updated help files, instead of downloading them from the internet.</span></span> <span data-ttu-id="30e75-233">フォルダーのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="30e75-233">Enter the path of a folder.</span></span> <span data-ttu-id="30e75-234">ファイル名またはファイル名拡張子を指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="30e75-234">Don't specify a file name or file name extension.</span></span> <span data-ttu-id="30e75-235">またはコマンドレットのようなフォルダーをにパイプライン `Get-Item` でき `Get-ChildItem` `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-235">You can pipeline a folder, such as one from the `Get-Item` or `Get-ChildItem` cmdlets, to `Update-Help`.</span></span>

<span data-ttu-id="30e75-236">既定では、は、 `Update-Help` 更新されたヘルプファイルをインターネットからダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="30e75-236">By default, `Update-Help` downloads updated help files from the internet.</span></span> <span data-ttu-id="30e75-237">コマンドレットを使用して、更新されたヘルプファイルをディレクトリにダウンロードした場合は、 **SourcePath** を使用し `Save-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-237">Use **SourcePath** when you've used the `Save-Help` cmdlet to download updated help files to a directory.</span></span>

<span data-ttu-id="30e75-238">**SourcePath** の既定値を指定するには、[ **グループポリシー** ]、[ **コンピューターの構成** ] にアクセスし、[update-help] **の既定のソースパスを設定** します。</span><span class="sxs-lookup"><span data-stu-id="30e75-238">To specify a default value for **SourcePath** , go to **Group Policy** , **Computer Configuration** , and **Set the default source path for Update-Help**.</span></span> <span data-ttu-id="30e75-239">このグループポリシー設定は、ユーザーがを使用して `Update-Help` インターネットからヘルプファイルをダウンロードできないようにします。</span><span class="sxs-lookup"><span data-stu-id="30e75-239">This Group Policy setting prevents users from using `Update-Help` to download help files from the internet.</span></span>
<span data-ttu-id="30e75-240">詳細については、「[about_Group_Policy_Settings](./About/about_Group_Policy_Settings.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="30e75-240">For more information, see [about_Group_Policy_Settings](./About/about_Group_Policy_Settings.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30e75-241">-UICulture</span><span class="sxs-lookup"><span data-stu-id="30e75-241">-UICulture</span></span>

<span data-ttu-id="30e75-242">が `Update-Help` 更新されたヘルプファイルを取得するために使用する UI カルチャの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="30e75-242">Specifies UI culture values that `Update-Help` uses to get updated help files.</span></span> <span data-ttu-id="30e75-243">**Es** 、カルチャオブジェクトを含む変数、 `Get-Culture` またはコマンドやコマンドなどのカルチャオブジェクトを取得するコマンドなど、1つまたは複数の言語コードを入力し `Get-UICulture` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-243">Enter one or more language codes, such as **es-ES** , a variable that contains culture objects, or a command that gets culture objects, such as a `Get-Culture` or `Get-UICulture` command.</span></span> <span data-ttu-id="30e75-244">ワイルドカード文字は使用できません。また、 **de** などの部分言語コードを送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="30e75-244">Wildcard characters aren't permitted and you can't submit a partial language code, such as **de**.</span></span>

<span data-ttu-id="30e75-245">既定では、は、 `Update-Help` オペレーティングシステム用に設定された UI カルチャのヘルプファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="30e75-245">By default, `Update-Help` gets help files in the UI culture set for the operating system.</span></span> <span data-ttu-id="30e75-246">**UICulture** パラメーターを指定すると、は `Update-Help` 指定された UI カルチャに対してのみヘルプを検索します。</span><span class="sxs-lookup"><span data-stu-id="30e75-246">If you specify the **UICulture** parameter, `Update-Help` looks for help only for the specified UI culture.</span></span>

<span data-ttu-id="30e75-247">**UICulture** パラメーターを使用するコマンドは、指定した UI カルチャのヘルプ ファイルをモジュールが提供する場合に限り、成功します。</span><span class="sxs-lookup"><span data-stu-id="30e75-247">Commands that use the **UICulture** parameter succeed only when the module provides help files for the specified UI culture.</span></span> <span data-ttu-id="30e75-248">指定された UI カルチャがサポートされていないためにコマンドが失敗した場合は、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30e75-248">If the command fails because the specified UI culture isn't supported, an error message is displayed.</span></span>

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30e75-249">-UseDefaultCredentials</span><span class="sxs-lookup"><span data-stu-id="30e75-249">-UseDefaultCredentials</span></span>

<span data-ttu-id="30e75-250">は、 `Update-Help` 現在のユーザーの資格情報を使用して、インターネットダウンロードなどのコマンドを実行することを示します。</span><span class="sxs-lookup"><span data-stu-id="30e75-250">Indicates that `Update-Help` runs the command, including the internet download, by using the credentials of the current user.</span></span> <span data-ttu-id="30e75-251">既定では、コマンドは明示的な資格情報がない状態で実行されます。</span><span class="sxs-lookup"><span data-stu-id="30e75-251">By default, the command runs without explicit credentials.</span></span>

<span data-ttu-id="30e75-252">このパラメーターは、web ダウンロードで NT LAN Manager (NTLM)、negotiate、または Kerberos ベースの認証が使用されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="30e75-252">This parameter is effective only when the web download uses NT LAN Manager (NTLM), negotiate, or Kerberos-based authentication.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30e75-253">-Confirm</span><span class="sxs-lookup"><span data-stu-id="30e75-253">-Confirm</span></span>

<span data-ttu-id="30e75-254">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30e75-254">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30e75-255">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="30e75-255">-WhatIf</span></span>

<span data-ttu-id="30e75-256">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="30e75-256">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="30e75-257">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="30e75-257">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="30e75-258">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="30e75-258">CommonParameters</span></span>

<span data-ttu-id="30e75-259">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="30e75-259">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="30e75-260">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30e75-260">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="30e75-261">入力</span><span class="sxs-lookup"><span data-stu-id="30e75-261">INPUTS</span></span>

### <span data-ttu-id="30e75-262">DirectoryInfo</span><span class="sxs-lookup"><span data-stu-id="30e75-262">System.IO.DirectoryInfo</span></span>

<span data-ttu-id="30e75-263">パイプを使用してディレクトリパスをにパイプすることができ `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-263">You can pipe a directory path to `Update-Help`.</span></span>

### <span data-ttu-id="30e75-264">PSModuleInfo (システム管理)</span><span class="sxs-lookup"><span data-stu-id="30e75-264">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="30e75-265">パイプを使用して、モジュールオブジェクトをコマンドレットからにパイプすることができ `Get-Module` `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-265">You can pipe a module object from the `Get-Module` cmdlet to `Update-Help`.</span></span>

## <span data-ttu-id="30e75-266">出力</span><span class="sxs-lookup"><span data-stu-id="30e75-266">OUTPUTS</span></span>

### <span data-ttu-id="30e75-267">なし</span><span class="sxs-lookup"><span data-stu-id="30e75-267">None</span></span>

<span data-ttu-id="30e75-268">`Update-Help` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="30e75-268">`Update-Help` doesn't generate any output.</span></span>

## <span data-ttu-id="30e75-269">注</span><span class="sxs-lookup"><span data-stu-id="30e75-269">NOTES</span></span>

<span data-ttu-id="30e75-270">Powershell を使用してインストールされたコマンド、またはディレクトリ内の任意のモジュールを含む PowerShell コアモジュールのヘルプを更新するには、 `$PSHOME\Modules` **管理者として実行** するオプションを使用して powershell を起動します。</span><span class="sxs-lookup"><span data-stu-id="30e75-270">To update help for the PowerShell Core modules, that contain the commands that are installed with PowerShell, or any module in the `$PSHOME\Modules` directory, start PowerShell with the option to **Run as administrator**.</span></span>

<span data-ttu-id="30e75-271">PowerShell コアモジュールのヘルプ、PowerShell と共にインストールされるコマンド、およびフォルダー内のモジュールのヘルプを更新できるのは、コンピューターの Administrators グループのメンバーだけ `$PSHOME\Modules` です。</span><span class="sxs-lookup"><span data-stu-id="30e75-271">Only members of the Administrators group on the computer can update help for the PowerShell Core modules, the commands that are installed together with PowerShell, and for modules in the `$PSHOME\Modules` folder.</span></span> <span data-ttu-id="30e75-272">ヘルプファイルを更新するアクセス許可がない場合は、オンラインでヘルプファイルを読むことができます。</span><span class="sxs-lookup"><span data-stu-id="30e75-272">If you don't have permission to update help files, you can read the help files online.</span></span> <span data-ttu-id="30e75-273">たとえば、「 `Get-Help Update-Help -Online` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="30e75-273">For example, `Get-Help Update-Help -Online`.</span></span>

<span data-ttu-id="30e75-274">モジュールは、更新可能なヘルプの最小単位です。</span><span class="sxs-lookup"><span data-stu-id="30e75-274">Modules are the smallest unit of updatable help.</span></span> <span data-ttu-id="30e75-275">特定のコマンドレットのヘルプを更新することはできません。</span><span class="sxs-lookup"><span data-stu-id="30e75-275">You can't update help for a particular cmdlet.</span></span> <span data-ttu-id="30e75-276">特定のコマンドレットを含むモジュールを検索するには、コマンドレットの **ModuleName** プロパティを使用し `Get-Command` ます。たとえば、のように `(Get-Command Update-Help).ModuleName` します。</span><span class="sxs-lookup"><span data-stu-id="30e75-276">To find the module that contains a particular cmdlet, use the **ModuleName** property of the `Get-Command` cmdlet, for example, `(Get-Command Update-Help).ModuleName`.</span></span>

<span data-ttu-id="30e75-277">ヘルプファイルはモジュールディレクトリにインストールされるため、 `Update-Help` コマンドレットはコンピューターにインストールされているモジュールに対してのみ、更新されたヘルプファイルをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="30e75-277">Because help files are installed in the module directory, the `Update-Help` cmdlet can install updated help file only for modules that are installed on the computer.</span></span> <span data-ttu-id="30e75-278">ただし、この `Save-Help` コマンドレットを使用すると、コンピューターにインストールされていないモジュールのヘルプを保存できます。</span><span class="sxs-lookup"><span data-stu-id="30e75-278">However, the `Save-Help` cmdlet can save help for modules that aren't installed on the computer.</span></span>

<span data-ttu-id="30e75-279">に `Update-Help` よって、モジュールの更新されたヘルプファイルが見つからない場合、または指定された言語で更新されたヘルプが見つからない場合は、エラーメッセージを表示せずに、警告なしで続行されます。</span><span class="sxs-lookup"><span data-stu-id="30e75-279">If `Update-Help` can't find updated help files for a module, or can't find updated help in the specified language, it continues silently without displaying an error message.</span></span> <span data-ttu-id="30e75-280">状態や進捗状況の詳細を確認するには、 **Verbose** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="30e75-280">To see status and progress details, use the **Verbose** parameter.</span></span>

<span data-ttu-id="30e75-281">この `Update-Help` コマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="30e75-281">The `Update-Help` cmdlet was introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="30e75-282">以前のバージョンの PowerShell では機能しません。</span><span class="sxs-lookup"><span data-stu-id="30e75-282">It doesn't work in earlier versions of PowerShell.</span></span> <span data-ttu-id="30e75-283">Windows PowerShell 2.0 と Windows PowerShell 3.0 の両方がインストールされているコンピューターでは、 `Update-Help` Windows powershell 3.0 セッションのコマンドレットを使用してヘルプファイルをダウンロードし、更新します。</span><span class="sxs-lookup"><span data-stu-id="30e75-283">On computers that have both Windows PowerShell 2.0 and Windows PowerShell 3.0, use the `Update-Help` cmdlet in a Windows PowerShell 3.0 session to download and update help files.</span></span> <span data-ttu-id="30e75-284">ヘルプファイルは、Windows PowerShell 2.0 と Windows PowerShell 3.0 の両方で使用できます。</span><span class="sxs-lookup"><span data-stu-id="30e75-284">The help files are available to both Windows PowerShell 2.0 and Windows PowerShell 3.0.</span></span>

<span data-ttu-id="30e75-285">`Update-Help`およびコマンドレットは、次のポートを使用して `Save-Help` ヘルプファイルをダウンロードします。 HTTP の場合はポート80、HTTPS の場合はポート443を使用します。</span><span class="sxs-lookup"><span data-stu-id="30e75-285">The `Update-Help` and `Save-Help` cmdlets use the following ports to download help files: Port 80 for HTTP and port 443 for HTTPS.</span></span>

<span data-ttu-id="30e75-286">`Update-Help` では、すべてのモジュールと PowerShell Core スナップインがサポートされています。その他のスナップインはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="30e75-286">`Update-Help` supports all modules and the PowerShell Core snap-ins. It doesn't support any other snap-ins.</span></span>

<span data-ttu-id="30e75-287">環境変数に一覧表示されていない場所にあるモジュールのヘルプを更新するには、 `$env:PSModulePath` 現在のセッションにモジュールをインポートしてから、コマンドを実行し `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="30e75-287">To update help for a module in a location that isn't listed in the `$env:PSModulePath` environment variable, import the module into the current session and then run an `Update-Help` command.</span></span> <span data-ttu-id="30e75-288">`Update-Help`パラメーターを指定せずに実行するか、 **module** パラメーターを使用してモジュール名を指定します。</span><span class="sxs-lookup"><span data-stu-id="30e75-288">Run `Update-Help` without parameters or use the **Module** parameter to specify the module name.</span></span> <span data-ttu-id="30e75-289">およびコマンドレットの **module** パラメーターは、 `Update-Help` `Save-Help` モジュールファイルまたはモジュールマニフェストファイルの完全パスを受け入れません。</span><span class="sxs-lookup"><span data-stu-id="30e75-289">The **Module** parameter of the `Update-Help` and `Save-Help` cmdlets doesn't accept the full path of a module file or module manifest file.</span></span>

<span data-ttu-id="30e75-290">モジュールはすべて、更新可能なヘルプをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="30e75-290">Any module can support Updatable Help.</span></span> <span data-ttu-id="30e75-291">作成したモジュールの更新可能なヘルプをサポートする手順については、「 [更新可能なヘルプのサポート](/powershell/scripting/developer/module/supporting-updatable-help)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30e75-291">For instructions for supporting Updatable Help in the modules that you author, see [Supporting Updatable Help](/powershell/scripting/developer/module/supporting-updatable-help).</span></span>

<span data-ttu-id="30e75-292">`Update-Help`および `Save-Help` コマンドレットは、Windows プレインストール環境 (Windows PE) ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="30e75-292">The `Update-Help` and `Save-Help` cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="30e75-293">関連リンク</span><span class="sxs-lookup"><span data-stu-id="30e75-293">RELATED LINKS</span></span>

[<span data-ttu-id="30e75-294">Get-Culture</span><span class="sxs-lookup"><span data-stu-id="30e75-294">Get-Culture</span></span>](../Microsoft.PowerShell.Utility/Get-Culture.md)

[<span data-ttu-id="30e75-295">Get-Help</span><span class="sxs-lookup"><span data-stu-id="30e75-295">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="30e75-296">Get-Module</span><span class="sxs-lookup"><span data-stu-id="30e75-296">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="30e75-297">Get-UICulture</span><span class="sxs-lookup"><span data-stu-id="30e75-297">Get-UICulture</span></span>](../Microsoft.PowerShell.Utility/Get-UICulture.md)

[<span data-ttu-id="30e75-298">Start-Job</span><span class="sxs-lookup"><span data-stu-id="30e75-298">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="30e75-299">Save-Help</span><span class="sxs-lookup"><span data-stu-id="30e75-299">Save-Help</span></span>](Save-Help.md)
