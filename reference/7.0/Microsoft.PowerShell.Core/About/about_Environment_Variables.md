---
description: PowerShell で Windows 環境変数にアクセスする方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 09/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_environment_variables?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Environment_Variables
ms.openlocfilehash: 44d8a0fc7b1751c8f1b4cde95e84ddbdd65efd7c
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220688"
---
# <a name="about-environment-variables"></a><span data-ttu-id="3cef9-104">環境変数について</span><span class="sxs-lookup"><span data-stu-id="3cef9-104">About Environment Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="3cef9-105">概要</span><span class="sxs-lookup"><span data-stu-id="3cef9-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="3cef9-106">PowerShell で Windows 環境変数にアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-106">Describes how to access Windows environment variables in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="3cef9-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="3cef9-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="3cef9-108">環境変数には、オペレーティングシステム環境に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-108">Environment variables store information about the operating system environment.</span></span> <span data-ttu-id="3cef9-109">この情報には、オペレーティングシステムのパス、オペレーティングシステムによって使用されるプロセッサの数、一時フォルダーの場所などの詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-109">This information includes details such as the operating system path, the number of processors used by the operating system, and the location of temporary folders.</span></span>

<span data-ttu-id="3cef9-110">環境変数には、オペレーティングシステムおよびその他のプログラムによって使用されるデータが格納されます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-110">The environment variables store data that is used by the operating system and other programs.</span></span> <span data-ttu-id="3cef9-111">たとえば、環境変数には、 `WINDIR` Windows インストールディレクトリの場所が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-111">For example, the `WINDIR` environment variable contains the location of the Windows installation directory.</span></span> <span data-ttu-id="3cef9-112">プログラムは、この変数の値を照会して、Windows オペレーティングシステムファイルが配置されている場所を判断できます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-112">Programs can query the value of this variable to determine where Windows operating system files are located.</span></span>

<span data-ttu-id="3cef9-113">PowerShell は、サポートされている任意のオペレーティングシステムプラットフォームで環境変数にアクセスして管理できます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-113">PowerShell can access and manage environment variables in any of the supported operating system platforms.</span></span> <span data-ttu-id="3cef9-114">PowerShell 環境プロバイダーは、環境変数を簡単に表示および変更できるようにすることで、このプロセスを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-114">The PowerShell environment provider simplifies this process by making it easy to view and change environment variables.</span></span>

<span data-ttu-id="3cef9-115">環境変数は、PowerShell の他の種類の変数とは異なり、子プロセス (ローカルのバックグラウンドジョブやモジュールメンバーが実行されるセッションなど) によって継承されます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-115">Environment variables, unlike other types of variables in PowerShell, are inherited by child processes, such as local background jobs and the sessions in which module members run.</span></span> <span data-ttu-id="3cef9-116">これにより、環境変数が、親プロセスと子プロセスの両方に必要な値を格納するために適しています。</span><span class="sxs-lookup"><span data-stu-id="3cef9-116">This makes environment variables well suited to storing values that are needed in both parent and child processes.</span></span>

## <a name="using-and-changing-environment-variables"></a><span data-ttu-id="3cef9-117">環境変数の使用と変更</span><span class="sxs-lookup"><span data-stu-id="3cef9-117">Using and changing environment variables</span></span>

<span data-ttu-id="3cef9-118">Windows では、環境変数は次の3つのスコープで定義できます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-118">On Windows, environment variables can be defined in three scopes:</span></span>

- <span data-ttu-id="3cef9-119">コンピューター (またはシステム) のスコープ</span><span class="sxs-lookup"><span data-stu-id="3cef9-119">Machine (or System) scope</span></span>
- <span data-ttu-id="3cef9-120">ユーザー スコープ</span><span class="sxs-lookup"><span data-stu-id="3cef9-120">User scope</span></span>
- <span data-ttu-id="3cef9-121">プロセススコープ</span><span class="sxs-lookup"><span data-stu-id="3cef9-121">Process scope</span></span>

<span data-ttu-id="3cef9-122">_プロセス_ スコープには、現在のプロセスまたは PowerShell セッションで使用できる環境変数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3cef9-122">The _Process_ scope contains the environment variables available in the current process, or PowerShell session.</span></span> <span data-ttu-id="3cef9-123">この変数の一覧は親プロセスから継承され、 _コンピューター_ と _ユーザー_ スコープの変数から構築されます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-123">This list of variables is inherited from the parent process and is constructed from the variables in the _Machine_ and _User_ scopes.</span></span> <span data-ttu-id="3cef9-124">Unix ベースのプラットフォームには、 _プロセス_ スコープしかありません。</span><span class="sxs-lookup"><span data-stu-id="3cef9-124">Unix-based platforms only have the _Process_ scope.</span></span>

<span data-ttu-id="3cef9-125">環境変数の値を表示および変更するには、環境プロバイダーで変数構文を使用してコマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cef9-125">You can display and change the values of environment variables without using a cmdlet by using a variable syntax with the environment provider.</span></span> <span data-ttu-id="3cef9-126">環境変数の値を表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-126">To display the value of an environment variable, use the following syntax:</span></span>

```
$Env:<variable-name>
```

<span data-ttu-id="3cef9-127">たとえば、環境変数の値を表示するには、 `WINDIR` PowerShell コマンドプロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-127">For example, to display the value of the `WINDIR` environment variable, type the following command at the PowerShell command prompt:</span></span>

```powershell
$Env:windir
```

<span data-ttu-id="3cef9-128">この構文では、ドル記号 ( `$` ) は変数を示し、ドライブ名 ( `Env:` ) は環境変数を示し、その後に変数名 () を指定し `windir` ます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-128">In this syntax, the dollar sign (`$`) indicates a variable, and the drive name (`Env:`) indicates an environment variable followed by the variable name (`windir`).</span></span>

<span data-ttu-id="3cef9-129">PowerShell で環境変数を変更すると、変更は現在のセッションのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-129">When you change environment variables in PowerShell, the change affects only the current session.</span></span> <span data-ttu-id="3cef9-130">この動作は、 `Set` Windows コマンドシェルのコマンドと `Setenv` UNIX ベースの環境でのコマンドの動作に似ています。</span><span class="sxs-lookup"><span data-stu-id="3cef9-130">This behavior resembles the behavior of the `Set` command in the Windows Command Shell and the `Setenv` command in UNIX-based environments.</span></span> <span data-ttu-id="3cef9-131">コンピューターまたはユーザースコープの値を変更するには、 **system.object クラスの** メソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cef9-131">To change values in the Machine or User scopes, you must use the methods of the **System.Environment** class.</span></span>

<span data-ttu-id="3cef9-132">コンピュータースコープの変数に変更を加えるには、にもアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="3cef9-132">To make changes to Machine-scoped variables, must also have permission.</span></span> <span data-ttu-id="3cef9-133">十分な権限を持たない値を変更しようとすると、コマンドは失敗し、PowerShell にはエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-133">If you try to change a value without sufficient permission, the command fails and PowerShell displays an error.</span></span>

<span data-ttu-id="3cef9-134">コマンドレットを使用せずに変数の値を変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-134">You can change the values of variables without using a cmdlet using the following syntax:</span></span>

```powershell
$Env:<variable-name> = "<new-value>"
```

<span data-ttu-id="3cef9-135">たとえば、環境変数の値にを追加するには、 `;c:\temp` 次の構文を使用し `Path` ます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-135">For example, to append `;c:\temp` to the value of the `Path` environment variable, use the following syntax:</span></span>

```powershell
$Env:Path += ";c:\temp"
```

<span data-ttu-id="3cef9-136">Linux または MacOS では、コマンド内のコロン () は、 `:` 新しいパスをリスト内でその前のパスと分離します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-136">On Linux or MacOS, the colon (`:`) in the command separates the new path from the path that precedes it in the list.</span></span>

```powershell
$Env:PATH += ":/usr/local/temp"
```

<span data-ttu-id="3cef9-137">また、、、などの項目のコマンドレットを使用して、 `Set-Item` `Remove-Item` `Copy-Item` 環境変数の値を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-137">You can also use the Item cmdlets, such as `Set-Item`, `Remove-Item`, and `Copy-Item` to change the values of environment variables.</span></span> <span data-ttu-id="3cef9-138">たとえば、コマンドレットを使用して `Set-Item` 環境変数の値にを追加するには、 `;c:\temp` `Path` 次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-138">For example, to use the `Set-Item` cmdlet to append `;c:\temp` to the value of the `Path` environment variable, use the following syntax:</span></span>

```powershell
Set-Item -Path Env:Path -Value ($Env:Path + ";C:\Temp")
```

<span data-ttu-id="3cef9-139">このコマンドでは、値は、1つの単位として解釈されるように、かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="3cef9-139">In this command, the value is enclosed in parentheses so that it is interpreted as a unit.</span></span>

## <a name="environment-variables-that-store-preferences"></a><span data-ttu-id="3cef9-140">基本設定を格納する環境変数</span><span class="sxs-lookup"><span data-stu-id="3cef9-140">Environment variables that store preferences</span></span>

<span data-ttu-id="3cef9-141">PowerShell 機能では、環境変数を使用してユーザー設定を保存できます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-141">PowerShell features can use environment variables to store user preferences.</span></span>
<span data-ttu-id="3cef9-142">これらの変数は、ユーザー設定変数と同じように動作しますが、それらが作成されるセッションの子セッションによって継承されます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-142">These variables work like preference variables, but they are inherited by child sessions of the sessions in which they are created.</span></span> <span data-ttu-id="3cef9-143">ユーザー設定変数の詳細については、「 [about_preference_variables](about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cef9-143">For more information about preference variables, see [about_preference_variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="3cef9-144">設定を格納する環境変数には次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="3cef9-144">The environment variables that store preferences include:</span></span>

- <span data-ttu-id="3cef9-145">PSExecutionPolicyPreference</span><span class="sxs-lookup"><span data-stu-id="3cef9-145">PSExecutionPolicyPreference</span></span>

  <span data-ttu-id="3cef9-146">現在のセッションの実行ポリシーセットを格納します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-146">Stores the execution policy set for the current session.</span></span> <span data-ttu-id="3cef9-147">この環境変数は、1つのセッションの実行ポリシーを設定した場合にのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-147">This environment variable exists only when you set an execution policy for a single session.</span></span>
  <span data-ttu-id="3cef9-148">これは、2つの異なる方法で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-148">You can do this in two different ways.</span></span>

  - <span data-ttu-id="3cef9-149">コマンドラインから **set-executionpolicy** パラメーターを使用してセッションを開始し、セッションの実行ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-149">Start a session from the command line using the **ExecutionPolicy** parameter to set the execution policy for the session.</span></span>

  - <span data-ttu-id="3cef9-150">`Set-ExecutionPolicy` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-150">Use the `Set-ExecutionPolicy` cmdlet.</span></span> <span data-ttu-id="3cef9-151">"Process" という値を持つ Scope パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-151">Use the Scope parameter with a value of "Process".</span></span>

    <span data-ttu-id="3cef9-152">詳細については、「[about_Execution_Policies](about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cef9-152">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

- <span data-ttu-id="3cef9-153">PSModuleAnalysisCachePath</span><span class="sxs-lookup"><span data-stu-id="3cef9-153">PSModuleAnalysisCachePath</span></span>

  <span data-ttu-id="3cef9-154">PowerShell では、モジュールとそのコマンドレットに関するデータをキャッシュするために使用されるファイルを制御できます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-154">PowerShell provides control over the file that is used to cache data about modules and their cmdlets.</span></span> <span data-ttu-id="3cef9-155">キャッシュは、コマンドの検索中に起動時に読み込まれ、モジュールがインポートされた後にバックグラウンドスレッドで書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-155">The cache is read at startup while searching for a command and is written on a background thread sometime after a module is imported.</span></span>

  <span data-ttu-id="3cef9-156">キャッシュの既定の場所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3cef9-156">Default location of the cache is:</span></span>

  - <span data-ttu-id="3cef9-157">Windows PowerShell 5.1: `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell`</span><span class="sxs-lookup"><span data-stu-id="3cef9-157">Windows PowerShell 5.1: `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell`</span></span>
  - <span data-ttu-id="3cef9-158">PowerShell 6.0 以降: `$env:LOCALAPPDATA\Microsoft\PowerShell`</span><span class="sxs-lookup"><span data-stu-id="3cef9-158">PowerShell 6.0 and higher: `$env:LOCALAPPDATA\Microsoft\PowerShell`</span></span>
  - <span data-ttu-id="3cef9-159">Windows 以外の既定: `~/.cache/powershell`</span><span class="sxs-lookup"><span data-stu-id="3cef9-159">Non-Windows default: `~/.cache/powershell`</span></span>

  <span data-ttu-id="3cef9-160">キャッシュの既定のファイル名は、 `ModuleAnalysisCache` です。</span><span class="sxs-lookup"><span data-stu-id="3cef9-160">The default filename for the cache is `ModuleAnalysisCache`.</span></span> <span data-ttu-id="3cef9-161">PowerShell の複数のインスタンスがインストールされている場合、ファイル名には16進数のサフィックスが付いているため、インストールごとに一意のファイル名が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-161">When you have multiple instances of PowerShell installed, the filename includes a hexadecimal suffix so that there is a a unique filename per installation.</span></span>

  > [!NOTE]
  > <span data-ttu-id="3cef9-162">コマンド検出が正常に機能しない場合、Intellisense など、存在しないコマンドが表示される場合は、キャッシュファイルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-162">If command discovery isn't working correctly, for example Intellisense shows commands that don't exist, you can delete the cache file.</span></span> <span data-ttu-id="3cef9-163">キャッシュは、次に PowerShell を起動したときに再作成されます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-163">The cache is recreated the next time you start PowerShell.</span></span>

  <span data-ttu-id="3cef9-164">キャッシュの既定の場所を変更するには、PowerShell を開始する前に環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-164">To change the default location of the cache, set the environment variable before starting PowerShell.</span></span> <span data-ttu-id="3cef9-165">この環境変数への変更は、子プロセスにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-165">Changes to this environment variable only affect child processes.</span></span> <span data-ttu-id="3cef9-166">値には、PowerShell がファイルの作成および書き込みアクセス許可を持つ完全なパス (ファイル名を含む) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cef9-166">The value should name a full path (including filename) that PowerShell has permission to create and write files.</span></span>

  <span data-ttu-id="3cef9-167">ファイル キャッシュを無効にするには、たとえば次のような無効な場所をこの値に設定します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-167">To disable the file cache, set this value to an invalid location, for example:</span></span>

  ```powershell
  # `NUL` here is a special device on Windows that cannot be written to,
  # on non-Windows you would use `/dev/null`
  $env:PSModuleAnalysisCachePath = 'NUL'
  ```

  <span data-ttu-id="3cef9-168">これにより、パスが **NUL** デバイスに設定されます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-168">This sets the path to the **NUL** device.</span></span> <span data-ttu-id="3cef9-169">PowerShell はパスに書き込むことができませんが、エラーは返されません。</span><span class="sxs-lookup"><span data-stu-id="3cef9-169">PowerShell can't write to the path but no error is returned.</span></span> <span data-ttu-id="3cef9-170">トレーサーを使用して報告されたエラーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-170">You can see the errors reported using a tracer:</span></span>

  ```powershell
  Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
  ```

- <span data-ttu-id="3cef9-171">PSDisableModuleAnalysisCacheCleanup</span><span class="sxs-lookup"><span data-stu-id="3cef9-171">PSDisableModuleAnalysisCacheCleanup</span></span>

  <span data-ttu-id="3cef9-172">モジュール分析キャッシュを書き込むときに、PowerShell は、不要な大きなキャッシュを回避するために存在しないモジュールをチェックします。</span><span class="sxs-lookup"><span data-stu-id="3cef9-172">When writing out the module analysis cache, PowerShell checks for modules that no longer exist to avoid an unnecessarily large cache.</span></span> <span data-ttu-id="3cef9-173">このようなチェックが不要な場合もあります。その場合、この環境変数の値をに設定して、これらのチェックをオフにすることができ `1` ます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-173">Sometimes these checks are not desirable, in which case you can turn them off by setting this environment variable value to `1`.</span></span>

  <span data-ttu-id="3cef9-174">この環境変数の設定は、現在のプロセスですぐに有効になります。</span><span class="sxs-lookup"><span data-stu-id="3cef9-174">Setting this environment variable takes effect immediately in the current process.</span></span>

- <span data-ttu-id="3cef9-175">PSModulePath</span><span class="sxs-lookup"><span data-stu-id="3cef9-175">PSModulePath</span></span>

  <span data-ttu-id="3cef9-176">環境変数には、 `$env:PSModulePath` モジュールとリソースを検索するために検索されるフォルダーの場所の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3cef9-176">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span>

  <span data-ttu-id="3cef9-177">既定では、に割り当てられて `$env:PSModulePath` いる有効な場所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3cef9-177">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

  - <span data-ttu-id="3cef9-178">システム全体の場所: これらのフォルダーには、PowerShell に付属しているモジュールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3cef9-178">System-wide locations: These folders contain modules that ship with PowerShell.</span></span> <span data-ttu-id="3cef9-179">モジュールは場所に格納されてい `$PSHOME\Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-179">The modules are store in the `$PSHOME\Modules` location.</span></span> <span data-ttu-id="3cef9-180">また、これは Windows 管理モジュールがインストールされている場所です。</span><span class="sxs-lookup"><span data-stu-id="3cef9-180">Also, This is the location where the Windows management modules are installed.</span></span>

  - <span data-ttu-id="3cef9-181">ユーザーがインストールしたモジュール: これらはユーザーによってインストールされたモジュールです。</span><span class="sxs-lookup"><span data-stu-id="3cef9-181">User-installed modules: These are modules installed by the user.</span></span>
    <span data-ttu-id="3cef9-182">`Install-Module` には、現在のユーザーまたはすべてのユーザーに対してモジュールがインストールされているかどうかを指定できる **スコープ** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="3cef9-182">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="3cef9-183">詳細については、「 [Install-Module](xref:PowerShellGet.Install-Module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cef9-183">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

    - <span data-ttu-id="3cef9-184">Windows では、ユーザー固有の **CurrentUser** スコープの場所は `$HOME\Documents\PowerShell\Modules` フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="3cef9-184">On Windows, the location of the user-specific **CurrentUser** scope is the `$HOME\Documents\PowerShell\Modules` folder.</span></span> <span data-ttu-id="3cef9-185">**AllUsers** スコープの場所は `$env:ProgramFiles\PowerShell\Modules` です。</span><span class="sxs-lookup"><span data-stu-id="3cef9-185">The location of the **AllUsers** scope is `$env:ProgramFiles\PowerShell\Modules`.</span></span>
    - <span data-ttu-id="3cef9-186">Windows 以外のシステムでは、ユーザー固有の **CurrentUser** スコープの場所は `$HOME/.local/share/powershell/Modules` フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="3cef9-186">On non-Windows systems, the location of the user-specific **CurrentUser** scope is the `$HOME/.local/share/powershell/Modules` folder.</span></span> <span data-ttu-id="3cef9-187">**AllUsers** スコープの場所は `/usr/local/share/powershell/Modules` です。</span><span class="sxs-lookup"><span data-stu-id="3cef9-187">The location of the **AllUsers** scope is `/usr/local/share/powershell/Modules`.</span></span>

  <span data-ttu-id="3cef9-188">また、Program Files ディレクトリなど、他のディレクトリにモジュールをインストールするセットアッププログラムでは、の値にその場所を追加でき `$env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-188">In addition, setup programs that install modules in other directories, such as the Program Files directory, can append their locations to the value of `$env:PSModulePath`.</span></span>

  <span data-ttu-id="3cef9-189">詳細については、「 [about_PSModulePath](about_PSModulePath.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cef9-189">For more information, see [about_PSModulePath](about_PSModulePath.md).</span></span>

## <a name="managing-environment-variables"></a><span data-ttu-id="3cef9-190">環境変数の管理</span><span class="sxs-lookup"><span data-stu-id="3cef9-190">Managing environment variables</span></span>

<span data-ttu-id="3cef9-191">PowerShell には、環境変数を管理するためのさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="3cef9-191">PowerShell provides several different methods for managing environment variables.</span></span>

- <span data-ttu-id="3cef9-192">環境プロバイダーのドライブ</span><span class="sxs-lookup"><span data-stu-id="3cef9-192">The Environment provider drive</span></span>
- <span data-ttu-id="3cef9-193">項目のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="3cef9-193">The Item cmdlets</span></span>
- <span data-ttu-id="3cef9-194">**.Net system.servicemodel** クラス</span><span class="sxs-lookup"><span data-stu-id="3cef9-194">The .NET **System.Environment** class</span></span>
- <span data-ttu-id="3cef9-195">Windows の場合、システムコントロールパネル</span><span class="sxs-lookup"><span data-stu-id="3cef9-195">On Windows, the System Control Panel</span></span>

### <a name="using-the-environment-provider"></a><span data-ttu-id="3cef9-196">環境プロバイダーの使用</span><span class="sxs-lookup"><span data-stu-id="3cef9-196">Using the Environment provider</span></span>

<span data-ttu-id="3cef9-197">各環境変数は、system.string **エントリ** クラスのインスタンスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-197">Each environment variable is represented by an instance of the **System.Collections.DictionaryEntry** class.</span></span> <span data-ttu-id="3cef9-198">各 **Dictionaryentry** オブジェクトでは、環境変数の名前はディクショナリキーです。</span><span class="sxs-lookup"><span data-stu-id="3cef9-198">In each **DictionaryEntry** object, the name of the environment variable is the dictionary key.</span></span> <span data-ttu-id="3cef9-199">変数の値はディクショナリ値です。</span><span class="sxs-lookup"><span data-stu-id="3cef9-199">The value of the variable is the dictionary value.</span></span>

<span data-ttu-id="3cef9-200">PowerShell で環境変数を表すオブジェクトのプロパティとメソッドを表示するには、コマンドレットを使用し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-200">To display the properties and methods of the object that represents an environment variable in PowerShell, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="3cef9-201">たとえば、ドライブ内のすべてのオブジェクトのメソッドとプロパティを表示するには、次のように `Env:` 入力します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-201">For example, to display the methods and properties of all the objects in the `Env:` drive, type:</span></span>

```powershell
Get-Item -Path Env:* | Get-Member
```

<span data-ttu-id="3cef9-202">PowerShell 環境プロバイダーを使用すると、PowerShell ドライブ (ドライブ) の環境変数にアクセスでき `Env:` ます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-202">The PowerShell Environment provider lets you access environment variables in a PowerShell drive (the `Env:` drive).</span></span> <span data-ttu-id="3cef9-203">このドライブは、ファイルシステムドライブのように見えます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-203">This drive looks much like a file system drive.</span></span> <span data-ttu-id="3cef9-204">ドライブにアクセスするには `Env:` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-204">To go to the `Env:` drive, type:</span></span>

```powershell
Set-Location Env:
```

<span data-ttu-id="3cef9-205">コンテンツコマンドレットを使用して、環境変数の値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-205">Use the Content cmdlets to get or set the values of an environment variable.</span></span>

```powershell
PS Env:\> Set-Content -Path Test -Value 'Test value'
PS Env:\> Get-Content -Path Test
Test value
```

<span data-ttu-id="3cef9-206">ドライブの環境変数は、 `Env:` 他の PowerShell ドライブから表示できます。ドライブに移動すると、 `Env:` 環境変数を表示したり、変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-206">You can view the environment variables in the `Env:` drive from any other PowerShell drive, and you can go into the `Env:` drive to view and change the environment variables.</span></span>

### <a name="using-item-cmdlets"></a><span data-ttu-id="3cef9-207">Item コマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="3cef9-207">Using Item cmdlets</span></span>

<span data-ttu-id="3cef9-208">環境変数を参照するときは、 `Env:` ドライブ名とその後に変数の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-208">When you refer to an environment variable, type the `Env:` drive name followed by the name of the variable.</span></span> <span data-ttu-id="3cef9-209">たとえば、環境変数の値を表示するには `COMPUTERNAME` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-209">For example, to display the value of the `COMPUTERNAME` environment variable, type:</span></span>

```powershell
Get-ChildItem Env:Computername
```

<span data-ttu-id="3cef9-210">すべての環境変数の値を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-210">To display the values of all the environment variables, type:</span></span>

```powershell
Get-ChildItem Env:
```

<span data-ttu-id="3cef9-211">環境変数には子項目がないため、との `Get-Item` 出力 `Get-ChildItem` は同じです。</span><span class="sxs-lookup"><span data-stu-id="3cef9-211">Because environment variables do not have child items, the output of `Get-Item` and `Get-ChildItem` is the same.</span></span>

<span data-ttu-id="3cef9-212">既定では、PowerShell は、環境変数を取得した順序で表示します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-212">By default, PowerShell displays the environment variables in the order in which it retrieves them.</span></span> <span data-ttu-id="3cef9-213">変数名で環境変数の一覧を並べ替えるには、パイプを使ってコマンドの出力を `Get-ChildItem` コマンドレットに渡し `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-213">To sort the list of environment variables by variable name, pipe the output of a `Get-ChildItem` command to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="3cef9-214">たとえば、任意の PowerShell ドライブから、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-214">For example, from any PowerShell drive, type:</span></span>

```powershell
Get-ChildItem Env: | Sort Name
```

<span data-ttu-id="3cef9-215">また、 `Env:` コマンドレットを使用してドライブにアクセスすることもでき `Set-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-215">You can also go into the `Env:` drive by using the `Set-Location` cmdlet:</span></span>

```powershell
Set-Location Env:
```

<span data-ttu-id="3cef9-216">ドライブにいるときは、 `Env:` `Env:` パスからドライブ名を省略できます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-216">When you are in the `Env:` drive, you can omit the `Env:` drive name from the path.</span></span> <span data-ttu-id="3cef9-217">たとえば、すべての環境変数を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-217">For example, to display all the environment variables, type:</span></span>

```powershell
PS Env:\> Get-ChildItem
```

<span data-ttu-id="3cef9-218">ドライブ内から変数の値を表示するには `COMPUTERNAME` `Env:` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-218">To display the value of the `COMPUTERNAME` variable from within the `Env:` drive, type:</span></span>

```powershell
PS Env:\> Get-ChildItem ComputerName
```

### <a name="saving-changes-to-environment-variables"></a><span data-ttu-id="3cef9-219">環境変数への変更の保存</span><span class="sxs-lookup"><span data-stu-id="3cef9-219">Saving changes to environment variables</span></span>

<span data-ttu-id="3cef9-220">Windows の環境変数に対して永続的な変更を行うには、[システム] コントロールパネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-220">To make a persistent change to an environment variable on Windows, use the System Control Panel.</span></span> <span data-ttu-id="3cef9-221">[ **システムの詳細設定** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3cef9-221">Select **Advanced System Settings**.</span></span> <span data-ttu-id="3cef9-222">[ **詳細設定** ] タブで、[ **環境変数** ] をクリックします。 **ユーザー** および **システム** (コンピューター) のスコープでは、既存の環境変数を追加または編集できます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-222">On the **Advanced** tab, click **Environment Variable...**. You can add or edit existing environment variables in the **User** and **System** (Machine) scopes.</span></span> <span data-ttu-id="3cef9-223">Windows はこれらの値をレジストリに書き込みます。これにより、セッションとシステムの再起動の間で永続化されます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-223">Windows writes these values to the Registry so that they persist across sessions and system restarts.</span></span>

<span data-ttu-id="3cef9-224">または、PowerShell プロファイルで環境変数を追加または変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-224">Alternately, you can add or change environment variables in your PowerShell profile.</span></span> <span data-ttu-id="3cef9-225">この方法は、サポートされている任意のプラットフォーム上の任意のバージョンの PowerShell で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3cef9-225">This method works for any version of PowerShell on any supported platform.</span></span>

### <a name="using-systemenvironment-methods"></a><span data-ttu-id="3cef9-226">System.object メソッドの使用</span><span class="sxs-lookup"><span data-stu-id="3cef9-226">Using System.Environment methods</span></span>

<span data-ttu-id="3cef9-227">GetEnvironmentVariable **クラスに** は、変数のスコープを指定できるようにする、 **GetEnvironmentVariable** メソッドと **SetEnvironmentVariable** メソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3cef9-227">The **System.Environment** class provides **GetEnvironmentVariable** and **SetEnvironmentVariable** methods that allow you to specify the scope of the variable.</span></span>

<span data-ttu-id="3cef9-228">次の例では、 **GetEnvironmentVariable** メソッドを使用してコンピューターの設定を取得し、SetEnvironmentVariable メソッドを使用してその `PSModulePath` パスを値に追加して **SetEnvironmentVariable** `C:\Program Files\Fabrikam\Modules` います。</span><span class="sxs-lookup"><span data-stu-id="3cef9-228">The following example uses the **GetEnvironmentVariable** method to get the machine setting of `PSModulePath` and the **SetEnvironmentVariable** method to add the `C:\Program Files\Fabrikam\Modules` path to the value.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'Machine')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable("PSModulePath", $newpath, 'Machine')
```

<span data-ttu-id="3cef9-229">System.object クラスのメソッドの詳細については、「 [環境メソッド](/dotnet/api/system.environment)」を参照して **ください。**</span><span class="sxs-lookup"><span data-stu-id="3cef9-229">For more information about the methods of the **System.Environment** class, see [Environment Methods](/dotnet/api/system.environment).</span></span>

## <a name="see-also"></a><span data-ttu-id="3cef9-230">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cef9-230">SEE ALSO</span></span>

- [<span data-ttu-id="3cef9-231">環境 (プロバイダー)</span><span class="sxs-lookup"><span data-stu-id="3cef9-231">Environment (provider)</span></span>](../About/about_Environment_Provider.md)
- [<span data-ttu-id="3cef9-232">about_Modules</span><span class="sxs-lookup"><span data-stu-id="3cef9-232">about_Modules</span></span>](about_Modules.md)
