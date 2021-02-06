---
description: PowerShell で Windows 環境変数にアクセスする方法について説明します。
Locale: en-US
ms.date: 09/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_environment_variables?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Environment_Variables
ms.openlocfilehash: 66d2bcd76651a7231a670ee5b02b99d6edd63a72
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602025"
---
# <a name="about-environment-variables"></a><span data-ttu-id="c17a9-103">環境変数について</span><span class="sxs-lookup"><span data-stu-id="c17a9-103">About Environment Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="c17a9-104">概要</span><span class="sxs-lookup"><span data-stu-id="c17a9-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="c17a9-105">PowerShell で Windows 環境変数にアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-105">Describes how to access Windows environment variables in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="c17a9-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="c17a9-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="c17a9-107">環境変数には、オペレーティングシステム環境に関する情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-107">Environment variables store information about the operating system environment.</span></span> <span data-ttu-id="c17a9-108">この情報には、オペレーティングシステムのパス、オペレーティングシステムによって使用されるプロセッサの数、一時フォルダーの場所などの詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-108">This information includes details such as the operating system path, the number of processors used by the operating system, and the location of temporary folders.</span></span>

<span data-ttu-id="c17a9-109">環境変数には、オペレーティングシステムおよびその他のプログラムによって使用されるデータが格納されます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-109">The environment variables store data that is used by the operating system and other programs.</span></span> <span data-ttu-id="c17a9-110">たとえば、環境変数には、 `WINDIR` Windows インストールディレクトリの場所が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-110">For example, the `WINDIR` environment variable contains the location of the Windows installation directory.</span></span> <span data-ttu-id="c17a9-111">プログラムは、この変数の値を照会して、Windows オペレーティングシステムファイルが配置されている場所を判断できます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-111">Programs can query the value of this variable to determine where Windows operating system files are located.</span></span>

<span data-ttu-id="c17a9-112">PowerShell は、サポートされている任意のオペレーティングシステムプラットフォームで環境変数にアクセスして管理できます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-112">PowerShell can access and manage environment variables in any of the supported operating system platforms.</span></span> <span data-ttu-id="c17a9-113">PowerShell 環境プロバイダーは、環境変数を簡単に表示および変更できるようにすることで、このプロセスを簡略化します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-113">The PowerShell environment provider simplifies this process by making it easy to view and change environment variables.</span></span>

<span data-ttu-id="c17a9-114">環境変数は、PowerShell の他の種類の変数とは異なり、子プロセス (ローカルのバックグラウンドジョブやモジュールメンバーが実行されるセッションなど) によって継承されます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-114">Environment variables, unlike other types of variables in PowerShell, are inherited by child processes, such as local background jobs and the sessions in which module members run.</span></span> <span data-ttu-id="c17a9-115">これにより、環境変数が、親プロセスと子プロセスの両方に必要な値を格納するために適しています。</span><span class="sxs-lookup"><span data-stu-id="c17a9-115">This makes environment variables well suited to storing values that are needed in both parent and child processes.</span></span>

## <a name="using-and-changing-environment-variables"></a><span data-ttu-id="c17a9-116">環境変数の使用と変更</span><span class="sxs-lookup"><span data-stu-id="c17a9-116">Using and changing environment variables</span></span>

<span data-ttu-id="c17a9-117">Windows では、環境変数は次の3つのスコープで定義できます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-117">On Windows, environment variables can be defined in three scopes:</span></span>

- <span data-ttu-id="c17a9-118">コンピューター (またはシステム) のスコープ</span><span class="sxs-lookup"><span data-stu-id="c17a9-118">Machine (or System) scope</span></span>
- <span data-ttu-id="c17a9-119">ユーザー スコープ</span><span class="sxs-lookup"><span data-stu-id="c17a9-119">User scope</span></span>
- <span data-ttu-id="c17a9-120">プロセススコープ</span><span class="sxs-lookup"><span data-stu-id="c17a9-120">Process scope</span></span>

<span data-ttu-id="c17a9-121">_プロセス_ スコープには、現在のプロセスまたは PowerShell セッションで使用できる環境変数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c17a9-121">The _Process_ scope contains the environment variables available in the current process, or PowerShell session.</span></span> <span data-ttu-id="c17a9-122">この変数の一覧は親プロセスから継承され、 _コンピューター_ と _ユーザー_ スコープの変数から構築されます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-122">This list of variables is inherited from the parent process and is constructed from the variables in the _Machine_ and _User_ scopes.</span></span> <span data-ttu-id="c17a9-123">Unix ベースのプラットフォームには、 _プロセス_ スコープしかありません。</span><span class="sxs-lookup"><span data-stu-id="c17a9-123">Unix-based platforms only have the _Process_ scope.</span></span>

<span data-ttu-id="c17a9-124">環境変数の値を表示および変更するには、環境プロバイダーで変数構文を使用してコマンドレットを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c17a9-124">You can display and change the values of environment variables without using a cmdlet by using a variable syntax with the environment provider.</span></span> <span data-ttu-id="c17a9-125">環境変数の値を表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-125">To display the value of an environment variable, use the following syntax:</span></span>

```
$Env:<variable-name>
```

<span data-ttu-id="c17a9-126">たとえば、環境変数の値を表示するには、 `WINDIR` PowerShell コマンドプロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-126">For example, to display the value of the `WINDIR` environment variable, type the following command at the PowerShell command prompt:</span></span>

```powershell
$Env:windir
```

<span data-ttu-id="c17a9-127">この構文では、ドル記号 ( `$` ) は変数を示し、ドライブ名 ( `Env:` ) は環境変数を示し、その後に変数名 () を指定し `windir` ます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-127">In this syntax, the dollar sign (`$`) indicates a variable, and the drive name (`Env:`) indicates an environment variable followed by the variable name (`windir`).</span></span>

<span data-ttu-id="c17a9-128">PowerShell で環境変数を変更すると、変更は現在のセッションのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-128">When you change environment variables in PowerShell, the change affects only the current session.</span></span> <span data-ttu-id="c17a9-129">この動作は、 `Set` Windows コマンドシェルのコマンドと `Setenv` UNIX ベースの環境でのコマンドの動作に似ています。</span><span class="sxs-lookup"><span data-stu-id="c17a9-129">This behavior resembles the behavior of the `Set` command in the Windows Command Shell and the `Setenv` command in UNIX-based environments.</span></span> <span data-ttu-id="c17a9-130">コンピューターまたはユーザースコープの値を変更するには、 **system.object クラスの** メソッドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c17a9-130">To change values in the Machine or User scopes, you must use the methods of the **System.Environment** class.</span></span>

<span data-ttu-id="c17a9-131">コンピュータースコープの変数に変更を加えるには、にもアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="c17a9-131">To make changes to Machine-scoped variables, must also have permission.</span></span> <span data-ttu-id="c17a9-132">十分な権限を持たない値を変更しようとすると、コマンドは失敗し、PowerShell にはエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-132">If you try to change a value without sufficient permission, the command fails and PowerShell displays an error.</span></span>

<span data-ttu-id="c17a9-133">コマンドレットを使用せずに変数の値を変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-133">You can change the values of variables without using a cmdlet using the following syntax:</span></span>

```powershell
$Env:<variable-name> = "<new-value>"
```

<span data-ttu-id="c17a9-134">たとえば、環境変数の値にを追加するには、 `;c:\temp` 次の構文を使用し `Path` ます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-134">For example, to append `;c:\temp` to the value of the `Path` environment variable, use the following syntax:</span></span>

```powershell
$Env:Path += ";c:\temp"
```

<span data-ttu-id="c17a9-135">Linux または MacOS では、コマンド内のコロン () は、 `:` 新しいパスをリスト内でその前のパスと分離します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-135">On Linux or MacOS, the colon (`:`) in the command separates the new path from the path that precedes it in the list.</span></span>

```powershell
$Env:PATH += ":/usr/local/temp"
```

<span data-ttu-id="c17a9-136">また、、、などの項目のコマンドレットを使用して、 `Set-Item` `Remove-Item` `Copy-Item` 環境変数の値を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-136">You can also use the Item cmdlets, such as `Set-Item`, `Remove-Item`, and `Copy-Item` to change the values of environment variables.</span></span> <span data-ttu-id="c17a9-137">たとえば、コマンドレットを使用して `Set-Item` 環境変数の値にを追加するには、 `;c:\temp` `Path` 次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-137">For example, to use the `Set-Item` cmdlet to append `;c:\temp` to the value of the `Path` environment variable, use the following syntax:</span></span>

```powershell
Set-Item -Path Env:Path -Value ($Env:Path + ";C:\Temp")
```

<span data-ttu-id="c17a9-138">このコマンドでは、値は、1つの単位として解釈されるように、かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="c17a9-138">In this command, the value is enclosed in parentheses so that it is interpreted as a unit.</span></span>

## <a name="environment-variables-that-store-preferences"></a><span data-ttu-id="c17a9-139">基本設定を格納する環境変数</span><span class="sxs-lookup"><span data-stu-id="c17a9-139">Environment variables that store preferences</span></span>

<span data-ttu-id="c17a9-140">PowerShell 機能では、環境変数を使用してユーザー設定を保存できます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-140">PowerShell features can use environment variables to store user preferences.</span></span>
<span data-ttu-id="c17a9-141">これらの変数は、ユーザー設定変数と同じように動作しますが、それらが作成されるセッションの子セッションによって継承されます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-141">These variables work like preference variables, but they are inherited by child sessions of the sessions in which they are created.</span></span> <span data-ttu-id="c17a9-142">ユーザー設定変数の詳細については、「 [about_preference_variables](about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c17a9-142">For more information about preference variables, see [about_preference_variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="c17a9-143">設定を格納する環境変数には次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="c17a9-143">The environment variables that store preferences include:</span></span>

- <span data-ttu-id="c17a9-144">PSExecutionPolicyPreference</span><span class="sxs-lookup"><span data-stu-id="c17a9-144">PSExecutionPolicyPreference</span></span>

  <span data-ttu-id="c17a9-145">現在のセッションの実行ポリシーセットを格納します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-145">Stores the execution policy set for the current session.</span></span> <span data-ttu-id="c17a9-146">この環境変数は、1つのセッションの実行ポリシーを設定した場合にのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-146">This environment variable exists only when you set an execution policy for a single session.</span></span>
  <span data-ttu-id="c17a9-147">これは、2つの異なる方法で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-147">You can do this in two different ways.</span></span>

  - <span data-ttu-id="c17a9-148">コマンドラインから **set-executionpolicy** パラメーターを使用してセッションを開始し、セッションの実行ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-148">Start a session from the command line using the **ExecutionPolicy** parameter to set the execution policy for the session.</span></span>

  - <span data-ttu-id="c17a9-149">`Set-ExecutionPolicy` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-149">Use the `Set-ExecutionPolicy` cmdlet.</span></span> <span data-ttu-id="c17a9-150">"Process" という値を持つ Scope パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-150">Use the Scope parameter with a value of "Process".</span></span>

    <span data-ttu-id="c17a9-151">詳細については、「[about_Execution_Policies](about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c17a9-151">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

- <span data-ttu-id="c17a9-152">PSModuleAnalysisCachePath</span><span class="sxs-lookup"><span data-stu-id="c17a9-152">PSModuleAnalysisCachePath</span></span>

  <span data-ttu-id="c17a9-153">PowerShell では、モジュールとそのコマンドレットに関するデータをキャッシュするために使用されるファイルを制御できます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-153">PowerShell provides control over the file that is used to cache data about modules and their cmdlets.</span></span> <span data-ttu-id="c17a9-154">キャッシュは、コマンドの検索中に起動時に読み込まれ、モジュールがインポートされた後にバックグラウンドスレッドで書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-154">The cache is read at startup while searching for a command and is written on a background thread sometime after a module is imported.</span></span>

  <span data-ttu-id="c17a9-155">キャッシュの既定の場所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c17a9-155">Default location of the cache is:</span></span>

  - <span data-ttu-id="c17a9-156">Windows PowerShell 5.1: `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell`</span><span class="sxs-lookup"><span data-stu-id="c17a9-156">Windows PowerShell 5.1: `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell`</span></span>
  - <span data-ttu-id="c17a9-157">PowerShell 6.0 以降: `$env:LOCALAPPDATA\Microsoft\PowerShell`</span><span class="sxs-lookup"><span data-stu-id="c17a9-157">PowerShell 6.0 and higher: `$env:LOCALAPPDATA\Microsoft\PowerShell`</span></span>
  - <span data-ttu-id="c17a9-158">Windows 以外の既定: `~/.cache/powershell`</span><span class="sxs-lookup"><span data-stu-id="c17a9-158">Non-Windows default: `~/.cache/powershell`</span></span>

  <span data-ttu-id="c17a9-159">キャッシュの既定のファイル名は、 `ModuleAnalysisCache` です。</span><span class="sxs-lookup"><span data-stu-id="c17a9-159">The default filename for the cache is `ModuleAnalysisCache`.</span></span> <span data-ttu-id="c17a9-160">PowerShell の複数のインスタンスがインストールされている場合、ファイル名には16進数のサフィックスが付いているため、インストールごとに一意のファイル名が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-160">When you have multiple instances of PowerShell installed, the filename includes a hexadecimal suffix so that there is a a unique filename per installation.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c17a9-161">コマンド検出が正常に機能しない場合、Intellisense など、存在しないコマンドが表示される場合は、キャッシュファイルを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-161">If command discovery isn't working correctly, for example Intellisense shows commands that don't exist, you can delete the cache file.</span></span> <span data-ttu-id="c17a9-162">キャッシュは、次に PowerShell を起動したときに再作成されます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-162">The cache is recreated the next time you start PowerShell.</span></span>

  <span data-ttu-id="c17a9-163">キャッシュの既定の場所を変更するには、PowerShell を開始する前に環境変数を設定します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-163">To change the default location of the cache, set the environment variable before starting PowerShell.</span></span> <span data-ttu-id="c17a9-164">この環境変数への変更は、子プロセスにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-164">Changes to this environment variable only affect child processes.</span></span> <span data-ttu-id="c17a9-165">値には、PowerShell がファイルの作成および書き込みアクセス許可を持つ完全なパス (ファイル名を含む) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c17a9-165">The value should name a full path (including filename) that PowerShell has permission to create and write files.</span></span>

  <span data-ttu-id="c17a9-166">ファイル キャッシュを無効にするには、たとえば次のような無効な場所をこの値に設定します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-166">To disable the file cache, set this value to an invalid location, for example:</span></span>

  ```powershell
  # `NUL` here is a special device on Windows that cannot be written to,
  # on non-Windows you would use `/dev/null`
  $env:PSModuleAnalysisCachePath = 'NUL'
  ```

  <span data-ttu-id="c17a9-167">これにより、パスが **NUL** デバイスに設定されます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-167">This sets the path to the **NUL** device.</span></span> <span data-ttu-id="c17a9-168">PowerShell はパスに書き込むことができませんが、エラーは返されません。</span><span class="sxs-lookup"><span data-stu-id="c17a9-168">PowerShell can't write to the path but no error is returned.</span></span> <span data-ttu-id="c17a9-169">トレーサーを使用して報告されたエラーを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-169">You can see the errors reported using a tracer:</span></span>

  ```powershell
  Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
  ```

- <span data-ttu-id="c17a9-170">PSDisableModuleAnalysisCacheCleanup</span><span class="sxs-lookup"><span data-stu-id="c17a9-170">PSDisableModuleAnalysisCacheCleanup</span></span>

  <span data-ttu-id="c17a9-171">モジュール分析キャッシュを書き込むときに、PowerShell は、不要な大きなキャッシュを回避するために存在しないモジュールをチェックします。</span><span class="sxs-lookup"><span data-stu-id="c17a9-171">When writing out the module analysis cache, PowerShell checks for modules that no longer exist to avoid an unnecessarily large cache.</span></span> <span data-ttu-id="c17a9-172">このようなチェックが不要な場合もあります。その場合、この環境変数の値をに設定して、これらのチェックをオフにすることができ `1` ます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-172">Sometimes these checks are not desirable, in which case you can turn them off by setting this environment variable value to `1`.</span></span>

  <span data-ttu-id="c17a9-173">この環境変数の設定は、現在のプロセスですぐに有効になります。</span><span class="sxs-lookup"><span data-stu-id="c17a9-173">Setting this environment variable takes effect immediately in the current process.</span></span>

- <span data-ttu-id="c17a9-174">PSModulePath</span><span class="sxs-lookup"><span data-stu-id="c17a9-174">PSModulePath</span></span>

  <span data-ttu-id="c17a9-175">環境変数には、 `$env:PSModulePath` モジュールとリソースを検索するために検索されるフォルダーの場所の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c17a9-175">The `$env:PSModulePath` environment variable contains a list of folder locations that are searched to find modules and resources.</span></span>

  <span data-ttu-id="c17a9-176">既定では、に割り当てられて `$env:PSModulePath` いる有効な場所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c17a9-176">By default, the effective locations assigned to `$env:PSModulePath` are:</span></span>

  - <span data-ttu-id="c17a9-177">システム全体の場所: これらのフォルダーには、PowerShell に付属しているモジュールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c17a9-177">System-wide locations: These folders contain modules that ship with PowerShell.</span></span> <span data-ttu-id="c17a9-178">モジュールは場所に格納されてい `$PSHOME\Modules` ます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-178">The modules are store in the `$PSHOME\Modules` location.</span></span> <span data-ttu-id="c17a9-179">また、これは Windows 管理モジュールがインストールされている場所です。</span><span class="sxs-lookup"><span data-stu-id="c17a9-179">Also, This is the location where the Windows management modules are installed.</span></span>

  - <span data-ttu-id="c17a9-180">ユーザーがインストールしたモジュール: これらはユーザーによってインストールされたモジュールです。</span><span class="sxs-lookup"><span data-stu-id="c17a9-180">User-installed modules: These are modules installed by the user.</span></span>
    <span data-ttu-id="c17a9-181">`Install-Module` には、現在のユーザーまたはすべてのユーザーに対してモジュールがインストールされているかどうかを指定できる **スコープ** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="c17a9-181">`Install-Module` has a **Scope** parameter that allows you to specify whether the module is installed for the current user or for all users.</span></span> <span data-ttu-id="c17a9-182">詳細については、「 [Install-Module](xref:PowerShellGet.Install-Module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c17a9-182">For more information, see [Install-Module](xref:PowerShellGet.Install-Module).</span></span>

    - <span data-ttu-id="c17a9-183">Windows では、ユーザー固有の **CurrentUser** スコープの場所は `$HOME\Documents\PowerShell\Modules` フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="c17a9-183">On Windows, the location of the user-specific **CurrentUser** scope is the `$HOME\Documents\PowerShell\Modules` folder.</span></span> <span data-ttu-id="c17a9-184">**AllUsers** スコープの場所は `$env:ProgramFiles\PowerShell\Modules` です。</span><span class="sxs-lookup"><span data-stu-id="c17a9-184">The location of the **AllUsers** scope is `$env:ProgramFiles\PowerShell\Modules`.</span></span>
    - <span data-ttu-id="c17a9-185">Windows 以外のシステムでは、ユーザー固有の **CurrentUser** スコープの場所は `$HOME/.local/share/powershell/Modules` フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="c17a9-185">On non-Windows systems, the location of the user-specific **CurrentUser** scope is the `$HOME/.local/share/powershell/Modules` folder.</span></span> <span data-ttu-id="c17a9-186">**AllUsers** スコープの場所は `/usr/local/share/powershell/Modules` です。</span><span class="sxs-lookup"><span data-stu-id="c17a9-186">The location of the **AllUsers** scope is `/usr/local/share/powershell/Modules`.</span></span>

  <span data-ttu-id="c17a9-187">また、Program Files ディレクトリなど、他のディレクトリにモジュールをインストールするセットアッププログラムでは、の値にその場所を追加でき `$env:PSModulePath` ます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-187">In addition, setup programs that install modules in other directories, such as the Program Files directory, can append their locations to the value of `$env:PSModulePath`.</span></span>

  <span data-ttu-id="c17a9-188">詳細については、「 [about_PSModulePath](about_PSModulePath.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c17a9-188">For more information, see [about_PSModulePath](about_PSModulePath.md).</span></span>

## <a name="managing-environment-variables"></a><span data-ttu-id="c17a9-189">環境変数の管理</span><span class="sxs-lookup"><span data-stu-id="c17a9-189">Managing environment variables</span></span>

<span data-ttu-id="c17a9-190">PowerShell には、環境変数を管理するためのさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="c17a9-190">PowerShell provides several different methods for managing environment variables.</span></span>

- <span data-ttu-id="c17a9-191">環境プロバイダーのドライブ</span><span class="sxs-lookup"><span data-stu-id="c17a9-191">The Environment provider drive</span></span>
- <span data-ttu-id="c17a9-192">項目のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="c17a9-192">The Item cmdlets</span></span>
- <span data-ttu-id="c17a9-193">**.Net system.servicemodel** クラス</span><span class="sxs-lookup"><span data-stu-id="c17a9-193">The .NET **System.Environment** class</span></span>
- <span data-ttu-id="c17a9-194">Windows の場合、システムコントロールパネル</span><span class="sxs-lookup"><span data-stu-id="c17a9-194">On Windows, the System Control Panel</span></span>

### <a name="using-the-environment-provider"></a><span data-ttu-id="c17a9-195">環境プロバイダーの使用</span><span class="sxs-lookup"><span data-stu-id="c17a9-195">Using the Environment provider</span></span>

<span data-ttu-id="c17a9-196">各環境変数は、system.string **エントリ** クラスのインスタンスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-196">Each environment variable is represented by an instance of the **System.Collections.DictionaryEntry** class.</span></span> <span data-ttu-id="c17a9-197">各 **Dictionaryentry** オブジェクトでは、環境変数の名前はディクショナリキーです。</span><span class="sxs-lookup"><span data-stu-id="c17a9-197">In each **DictionaryEntry** object, the name of the environment variable is the dictionary key.</span></span> <span data-ttu-id="c17a9-198">変数の値はディクショナリ値です。</span><span class="sxs-lookup"><span data-stu-id="c17a9-198">The value of the variable is the dictionary value.</span></span>

<span data-ttu-id="c17a9-199">PowerShell で環境変数を表すオブジェクトのプロパティとメソッドを表示するには、コマンドレットを使用し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-199">To display the properties and methods of the object that represents an environment variable in PowerShell, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="c17a9-200">たとえば、ドライブ内のすべてのオブジェクトのメソッドとプロパティを表示するには、次のように `Env:` 入力します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-200">For example, to display the methods and properties of all the objects in the `Env:` drive, type:</span></span>

```powershell
Get-Item -Path Env:* | Get-Member
```

<span data-ttu-id="c17a9-201">PowerShell 環境プロバイダーを使用すると、PowerShell ドライブ (ドライブ) の環境変数にアクセスでき `Env:` ます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-201">The PowerShell Environment provider lets you access environment variables in a PowerShell drive (the `Env:` drive).</span></span> <span data-ttu-id="c17a9-202">このドライブは、ファイルシステムドライブのように見えます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-202">This drive looks much like a file system drive.</span></span> <span data-ttu-id="c17a9-203">ドライブにアクセスするには `Env:` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-203">To go to the `Env:` drive, type:</span></span>

```powershell
Set-Location Env:
```

<span data-ttu-id="c17a9-204">コンテンツコマンドレットを使用して、環境変数の値を取得または設定します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-204">Use the Content cmdlets to get or set the values of an environment variable.</span></span>

```powershell
PS Env:\> Set-Content -Path Test -Value 'Test value'
PS Env:\> Get-Content -Path Test
Test value
```

<span data-ttu-id="c17a9-205">ドライブの環境変数は、 `Env:` 他の PowerShell ドライブから表示できます。ドライブに移動すると、 `Env:` 環境変数を表示したり、変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-205">You can view the environment variables in the `Env:` drive from any other PowerShell drive, and you can go into the `Env:` drive to view and change the environment variables.</span></span>

### <a name="using-item-cmdlets"></a><span data-ttu-id="c17a9-206">Item コマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="c17a9-206">Using Item cmdlets</span></span>

<span data-ttu-id="c17a9-207">環境変数を参照するときは、 `Env:` ドライブ名とその後に変数の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-207">When you refer to an environment variable, type the `Env:` drive name followed by the name of the variable.</span></span> <span data-ttu-id="c17a9-208">たとえば、環境変数の値を表示するには `COMPUTERNAME` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-208">For example, to display the value of the `COMPUTERNAME` environment variable, type:</span></span>

```powershell
Get-ChildItem Env:Computername
```

<span data-ttu-id="c17a9-209">すべての環境変数の値を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-209">To display the values of all the environment variables, type:</span></span>

```powershell
Get-ChildItem Env:
```

<span data-ttu-id="c17a9-210">環境変数には子項目がないため、との `Get-Item` 出力 `Get-ChildItem` は同じです。</span><span class="sxs-lookup"><span data-stu-id="c17a9-210">Because environment variables do not have child items, the output of `Get-Item` and `Get-ChildItem` is the same.</span></span>

<span data-ttu-id="c17a9-211">既定では、PowerShell は、環境変数を取得した順序で表示します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-211">By default, PowerShell displays the environment variables in the order in which it retrieves them.</span></span> <span data-ttu-id="c17a9-212">変数名で環境変数の一覧を並べ替えるには、パイプを使ってコマンドの出力を `Get-ChildItem` コマンドレットに渡し `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-212">To sort the list of environment variables by variable name, pipe the output of a `Get-ChildItem` command to the `Sort-Object` cmdlet.</span></span> <span data-ttu-id="c17a9-213">たとえば、任意の PowerShell ドライブから、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-213">For example, from any PowerShell drive, type:</span></span>

```powershell
Get-ChildItem Env: | Sort Name
```

<span data-ttu-id="c17a9-214">また、 `Env:` コマンドレットを使用してドライブにアクセスすることもでき `Set-Location` ます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-214">You can also go into the `Env:` drive by using the `Set-Location` cmdlet:</span></span>

```powershell
Set-Location Env:
```

<span data-ttu-id="c17a9-215">ドライブにいるときは、 `Env:` `Env:` パスからドライブ名を省略できます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-215">When you are in the `Env:` drive, you can omit the `Env:` drive name from the path.</span></span> <span data-ttu-id="c17a9-216">たとえば、すべての環境変数を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-216">For example, to display all the environment variables, type:</span></span>

```powershell
PS Env:\> Get-ChildItem
```

<span data-ttu-id="c17a9-217">ドライブ内から変数の値を表示するには `COMPUTERNAME` `Env:` 、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-217">To display the value of the `COMPUTERNAME` variable from within the `Env:` drive, type:</span></span>

```powershell
PS Env:\> Get-ChildItem ComputerName
```

### <a name="saving-changes-to-environment-variables"></a><span data-ttu-id="c17a9-218">環境変数への変更の保存</span><span class="sxs-lookup"><span data-stu-id="c17a9-218">Saving changes to environment variables</span></span>

<span data-ttu-id="c17a9-219">Windows の環境変数に対して永続的な変更を行うには、[システム] コントロールパネルを使用します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-219">To make a persistent change to an environment variable on Windows, use the System Control Panel.</span></span> <span data-ttu-id="c17a9-220">[ **システムの詳細設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c17a9-220">Select **Advanced System Settings**.</span></span> <span data-ttu-id="c17a9-221">[ **詳細設定** ] タブで、[ **環境変数**] をクリックします。 **ユーザー** および **システム** (コンピューター) のスコープでは、既存の環境変数を追加または編集できます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-221">On the **Advanced** tab, click **Environment Variable...**. You can add or edit existing environment variables in the **User** and **System** (Machine) scopes.</span></span> <span data-ttu-id="c17a9-222">Windows はこれらの値をレジストリに書き込みます。これにより、セッションとシステムの再起動の間で永続化されます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-222">Windows writes these values to the Registry so that they persist across sessions and system restarts.</span></span>

<span data-ttu-id="c17a9-223">または、PowerShell プロファイルで環境変数を追加または変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-223">Alternately, you can add or change environment variables in your PowerShell profile.</span></span> <span data-ttu-id="c17a9-224">この方法は、サポートされている任意のプラットフォーム上の任意のバージョンの PowerShell で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c17a9-224">This method works for any version of PowerShell on any supported platform.</span></span>

### <a name="using-systemenvironment-methods"></a><span data-ttu-id="c17a9-225">System.object メソッドの使用</span><span class="sxs-lookup"><span data-stu-id="c17a9-225">Using System.Environment methods</span></span>

<span data-ttu-id="c17a9-226">GetEnvironmentVariable **クラスに** は、変数のスコープを指定できるようにする、 メソッドと **SetEnvironmentVariable** メソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c17a9-226">The **System.Environment** class provides **GetEnvironmentVariable** and **SetEnvironmentVariable** methods that allow you to specify the scope of the variable.</span></span>

<span data-ttu-id="c17a9-227">次の例では、 **GetEnvironmentVariable** メソッドを使用してコンピューターの設定を取得し、SetEnvironmentVariable メソッドを使用してその `PSModulePath` パスを値に追加して `C:\Program Files\Fabrikam\Modules` います。</span><span class="sxs-lookup"><span data-stu-id="c17a9-227">The following example uses the **GetEnvironmentVariable** method to get the machine setting of `PSModulePath` and the **SetEnvironmentVariable** method to add the `C:\Program Files\Fabrikam\Modules` path to the value.</span></span>

```powershell
$path = [Environment]::GetEnvironmentVariable('PSModulePath', 'Machine')
$newpath = $path + ';C:\Program Files\Fabrikam\Modules'
[Environment]::SetEnvironmentVariable("PSModulePath", $newpath, 'Machine')
```

<span data-ttu-id="c17a9-228">System.object クラスのメソッドの詳細については、「[環境メソッド](/dotnet/api/system.environment)」を参照して **ください。**</span><span class="sxs-lookup"><span data-stu-id="c17a9-228">For more information about the methods of the **System.Environment** class, see [Environment Methods](/dotnet/api/system.environment).</span></span>

## <a name="see-also"></a><span data-ttu-id="c17a9-229">関連項目</span><span class="sxs-lookup"><span data-stu-id="c17a9-229">SEE ALSO</span></span>

- [<span data-ttu-id="c17a9-230">環境 (プロバイダー)</span><span class="sxs-lookup"><span data-stu-id="c17a9-230">Environment (provider)</span></span>](../About/about_Environment_Provider.md)
- [<span data-ttu-id="c17a9-231">about_Modules</span><span class="sxs-lookup"><span data-stu-id="c17a9-231">about_Modules</span></span>](about_Modules.md)

