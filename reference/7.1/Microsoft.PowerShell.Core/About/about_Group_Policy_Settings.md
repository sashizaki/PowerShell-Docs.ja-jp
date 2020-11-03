---
description: PowerShell のグループポリシー設定について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 03/25/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_group_policy_settings?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Group_Policy_Settings
ms.openlocfilehash: df2a3e9349dd3afbe621bd11b92ac5cdf552492a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220899"
---
# <a name="about-group-policy-settings"></a><span data-ttu-id="b2937-104">グループポリシー設定について</span><span class="sxs-lookup"><span data-stu-id="b2937-104">About Group Policy Settings</span></span>

## <a name="short-description"></a><span data-ttu-id="b2937-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="b2937-105">Short description</span></span>
<span data-ttu-id="b2937-106">PowerShell のグループポリシー設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="b2937-106">Describes the Group Policy settings for PowerShell</span></span>

## <a name="long-description"></a><span data-ttu-id="b2937-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="b2937-107">Long description</span></span>

<span data-ttu-id="b2937-108">PowerShell には、エンタープライズ環境で Windows コンピューターの一貫した構成値を定義するのに役立つグループポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b2937-108">PowerShell includes Group Policy settings to help you define consistent configuration values for Windows computers in an enterprise environment.</span></span>

<span data-ttu-id="b2937-109">PowerShell のグループポリシー設定は、次のグループポリシーパスにあります。</span><span class="sxs-lookup"><span data-stu-id="b2937-109">The PowerShell Group Policy settings are in the following Group Policy paths:</span></span>

```
Computer Configuration\
  Administrative Templates\
    PowerShell Core

User Configuration\
  Administrative Templates\
    PowerShell Core
```

<span data-ttu-id="b2937-110">ユーザー構成パスのグループポリシー設定は、コンピューターの構成パスのグループポリシー設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="b2937-110">Group policy settings in the User Configuration path take precedence over Group Policy settings in the Computer Configuration path.</span></span>

<span data-ttu-id="b2937-111">PowerShell 7 では、グループ ポリシーのテンプレートとインストール スクリプトが `$PSHOME` に含まれています。</span><span class="sxs-lookup"><span data-stu-id="b2937-111">PowerShell 7 includes Group Policy templates and an installation script in `$PSHOME`.</span></span>

<span data-ttu-id="b2937-112">グループ ポリシー ツールでは、管理用テンプレート ファイル (`.admx`、`.adml`) を使用して、ユーザー インターフェイスにポリシー設定を追加できます。</span><span class="sxs-lookup"><span data-stu-id="b2937-112">Group Policy tools use administrative template files (`.admx`, `.adml`) to populate policy settings in the user interface.</span></span> <span data-ttu-id="b2937-113">これにより、管理者はレジストリ ベースのポリシー設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="b2937-113">This allows administrators to manage registry-based policy settings.</span></span> <span data-ttu-id="b2937-114">このスクリプトにより、 `InstallPSCorePolicyDefinitions.ps1` **PowerShell Core 管理用テンプレート** がローカルコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b2937-114">The `InstallPSCorePolicyDefinitions.ps1` script installs **PowerShell Core Administrative Templates** on the local machine.</span></span>

```powershell
Get-ChildItem -Path $PSHOME -Filter *Core*Policy*
```

```Output
    Directory: C:\Program Files\PowerShell\7

Mode       LastWriteTime         Length Name
----       -------------         ------ ----
-a---      2/27/2020 12:38 AM     15861 InstallPSCorePolicyDefinitions.ps1
-a---      2/27/2020 12:28 AM      9675 PowerShellCoreExecutionPolicy.adml
-a---      2/27/2020 12:28 AM      6201 PowerShellCoreExecutionPolicy.admx
```

<span data-ttu-id="b2937-115">テンプレートをインストールしたら、グループポリシーエディター () でこれらの設定を編集でき `gpedit.msc` ます。</span><span class="sxs-lookup"><span data-stu-id="b2937-115">After installing the templates, you can edit these settings in the Group Policy editor (`gpedit.msc`).</span></span>

<span data-ttu-id="b2937-116">ポリシーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b2937-116">The policies are as follows:</span></span>

- <span data-ttu-id="b2937-117">コンソール セッションの構成:PowerShell を実行する構成エンドポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="b2937-117">Console session configuration: Sets a configuration endpoint in which PowerShell is run.</span></span>
- <span data-ttu-id="b2937-118">モジュールのログ記録を有効にする: モジュールの **Logpipelineexecutiondetails** プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="b2937-118">Turn on Module Logging: Sets the **LogPipelineExecutionDetails** property of modules.</span></span>
- <span data-ttu-id="b2937-119">PowerShell スクリプト ブロックのログ記録を有効にする:すべての PowerShell スクリプトの詳細なログ記録を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b2937-119">Turn on PowerShell Script Block Logging: Enables detailed logging of all PowerShell scripts.</span></span>
- <span data-ttu-id="b2937-120">スクリプトの実行を有効にする:PowerShell 実行ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="b2937-120">Turn on Script Execution: Sets the PowerShell execution policy.</span></span>
- <span data-ttu-id="b2937-121">PowerShell トランスクリプションを有効にする: PowerShell コマンドの入出力をテキスト ベースのトランスクリプトにキャプチャできるようにします。</span><span class="sxs-lookup"><span data-stu-id="b2937-121">Turn on PowerShell Transcription: enables capturing of input and output of PowerShell commands into text-based transcripts.</span></span>
- <span data-ttu-id="b2937-122">の既定のソースパスを設定する `Update-Help` : 更新可能なヘルプのソースを、インターネットではなくディレクトリに設定します。</span><span class="sxs-lookup"><span data-stu-id="b2937-122">Set the default source path for `Update-Help`: Sets the source for Updatable Help to a directory, not the Internet.</span></span>

<span data-ttu-id="b2937-123">各 PowerShell グループポリシー設定には、次のグループポリシーパスにある同様の Windows PowerShell グループポリシー設定の値を使用するオプション ([Windows PowerShell ポリシー設定を使用する] フィールド) があります。</span><span class="sxs-lookup"><span data-stu-id="b2937-123">Each PowerShell Group Policy setting has an option ('Use Windows PowerShell Policy setting' field) to use the value from a similar Windows PowerShell Group Policy setting that is located in the following Group Policy paths:</span></span>

```
Computer Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell

User Configuration\
  Administrative Templates\
    Windows Components\
      Windows PowerShell
```

> [!NOTE]
> <span data-ttu-id="b2937-124">これらの **Powershell Core 管理用テンプレート** には、Windows powershell の設定は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="b2937-124">These **PowerShell Core Administrative Templates** do not include settings for Windows PowerShell.</span></span> <span data-ttu-id="b2937-125">他のテンプレートを取得し、グループポリシーを構成する方法の詳細については、「 [Windows でグループポリシー管理用テンプレートの中央ストアを作成および管理する方法][gpstore]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2937-125">For more information about acquiring other templates and configuring Group policy, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows][gpstore].</span></span>

## <a name="console-session-configuration"></a><span data-ttu-id="b2937-126">コンソールセッションの構成</span><span class="sxs-lookup"><span data-stu-id="b2937-126">Console session configuration</span></span>

<span data-ttu-id="b2937-127">**コンソールセッション構成** ポリシーの設定では、PowerShell を実行する構成エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="b2937-127">The **Console session configuration** policy setting specifies a configuration endpoint in which PowerShell is run.</span></span> <span data-ttu-id="b2937-128">これには、ローカルコンピューターに登録されている任意のエンドポイントを指定できます。これには、既定の PowerShell リモート処理エンドポイントや、特定のユーザーロール機能を持つカスタムエンドポイントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b2937-128">This can be any endpoint registered on the local machine including the default PowerShell remoting endpoints or a custom endpoint having specific user role capabilities.</span></span>

## <a name="turn-on-module-logging"></a><span data-ttu-id="b2937-129">モジュールログをオンにする</span><span class="sxs-lookup"><span data-stu-id="b2937-129">Turn on module logging</span></span>

<span data-ttu-id="b2937-130">[ **モジュールログをオンにする** ] ポリシー設定は、選択した PowerShell モジュールのログ記録を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b2937-130">The **Turn on Module Logging** policy setting turns on logging for selected PowerShell modules.</span></span> <span data-ttu-id="b2937-131">この設定は、影響を受けるすべてのコンピューター上のすべてのセッションで有効になります。</span><span class="sxs-lookup"><span data-stu-id="b2937-131">The setting is effective in all sessions on all affected computers.</span></span>

<span data-ttu-id="b2937-132">このポリシー設定を有効にして1つ以上のモジュールを指定した場合、指定されたモジュールのパイプライン実行イベントは、イベントビューアーの Windows PowerShell ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="b2937-132">If you enable this policy setting and specify one or more modules, pipeline execution events for the specified modules are recorded in the Windows PowerShell log in Event Viewer.</span></span>

<span data-ttu-id="b2937-133">このポリシー設定を無効にした場合、すべての PowerShell モジュールに対して実行イベントのログ記録が無効になります。</span><span class="sxs-lookup"><span data-stu-id="b2937-133">If you disable this policy setting, logging of execution events is disabled for all PowerShell modules.</span></span>

<span data-ttu-id="b2937-134">このポリシー設定が構成されていない場合、各モジュールの **Logpipelineexecutiondetails** プロパティによって、モジュールの実行イベントがログに記録されるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="b2937-134">If this policy setting is not configured, the **LogPipelineExecutionDetails** property of each module determines whether the execution events of a module are logged.</span></span> <span data-ttu-id="b2937-135">既定では、すべてのモジュールの **Logpipelineexecutiondetails** プロパティは False に設定されています。</span><span class="sxs-lookup"><span data-stu-id="b2937-135">By default, the **LogPipelineExecutionDetails** property of all modules is set to False.</span></span>

<span data-ttu-id="b2937-136">モジュールのモジュールログをオンにするには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="b2937-136">To turn on module logging for a module, use the following command format.</span></span> <span data-ttu-id="b2937-137">モジュールをセッションにインポートする必要があります。この設定は、現在のセッションでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="b2937-137">The module must be imported into the session and the setting is effective only in the current session.</span></span>

```powershell
Import-Module <Module-Name>
(Get-Module <Module-Name>).LogPipelineExecutionDetails = $true
```

<span data-ttu-id="b2937-138">特定のコンピューター上のすべてのセッションのモジュールログをオンにするには、前のコマンドを "すべてのユーザー" PowerShell プロファイル () に追加し `$Profile.AllUsersAllHosts` ます。</span><span class="sxs-lookup"><span data-stu-id="b2937-138">To turn on module logging for all sessions on a particular computer, add the previous commands to the 'All Users' PowerShell profile (`$Profile.AllUsersAllHosts`).</span></span>

<span data-ttu-id="b2937-139">モジュールログの詳細については、「 [about_Modules](about_Modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2937-139">For more information about module logging, see [about_Modules](about_Modules.md).</span></span>

## <a name="turn-on-powershell-script-block-logging"></a><span data-ttu-id="b2937-140">PowerShell スクリプトブロックのログ記録を有効にする</span><span class="sxs-lookup"><span data-stu-id="b2937-140">Turn on PowerShell script block logging</span></span>

<span data-ttu-id="b2937-141">**[Powershell スクリプトブロックのログ記録を有効に** する] ポリシー設定を使用すると、powershell スクリプトのすべての入力を、Microsoft-Windows Powershell/Operational イベントログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="b2937-141">The **Turn on PowerShell Script Block Logging** policy setting enables logging of all PowerShell script input to the Microsoft-Windows-PowerShell/Operational event log.</span></span> <span data-ttu-id="b2937-142">このポリシー設定を有効にした場合、PowerShell Core は、対話形式で起動したか、またはオートメーションを使用して、コマンド、スクリプトブロック、関数、およびスクリプトの処理をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="b2937-142">If you enable this policy setting, PowerShell Core will log the processing of commands, script blocks, functions, and scripts - whether invoked interactively, or through automation.</span></span>

<span data-ttu-id="b2937-143">このポリシー設定を無効にすると、PowerShell スクリプトの入力のログ記録は無効になります。</span><span class="sxs-lookup"><span data-stu-id="b2937-143">If you disable this policy setting, logging of PowerShell script input is disabled.</span></span> <span data-ttu-id="b2937-144">スクリプト ブロックの呼び出しのログ記録を有効にすると、PowerShell はさらに、コマンド、スクリプト ブロック、関数、またはスクリプトの呼び出しの開始時または停止時にイベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="b2937-144">If you enable the Script Block Invocation Logging, PowerShell additionally logs events when invocation of a command, script block, function, or script starts or stops.</span></span> <span data-ttu-id="b2937-145">呼び出しのログ記録を有効にすると、大量のイベント ログが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b2937-145">Enabling Invocation Logging generates a high volume of event logs.</span></span>

## <a name="turn-on-script-execution"></a><span data-ttu-id="b2937-146">スクリプトの実行を有効にする</span><span class="sxs-lookup"><span data-stu-id="b2937-146">Turn on script execution</span></span>

<span data-ttu-id="b2937-147">[ **スクリプトの実行を有効に** する] ポリシー設定では、コンピューターとユーザーの実行ポリシーを設定します。これにより、実行が許可されるスクリプトが決まります。</span><span class="sxs-lookup"><span data-stu-id="b2937-147">The **Turn on Script Execution** policy setting sets the execution policy for computers and users, which determines which scripts are permitted to run.</span></span>

<span data-ttu-id="b2937-148">ポリシー設定を有効にした場合は、次のポリシー設定の中から選択できます。</span><span class="sxs-lookup"><span data-stu-id="b2937-148">If you enable the policy setting, you can select from among the following policy settings.</span></span>

- <span data-ttu-id="b2937-149">**署名済みスクリプトのみを許可** するスクリプトは、信頼された発行元によって署名されている場合にのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="b2937-149">**Allow only signed scripts** allows scripts to execute only if they are signed by a trusted publisher.</span></span> <span data-ttu-id="b2937-150">このポリシー設定は、AllSigned 実行ポリシーと同じです。</span><span class="sxs-lookup"><span data-stu-id="b2937-150">This policy setting is equivalent to the AllSigned execution policy.</span></span>

- <span data-ttu-id="b2937-151">**ローカルスクリプトおよびリモートの署名済みスクリプトを許可すると、** すべてのローカルスクリプトを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b2937-151">**Allow local scripts and remote signed scripts** allows all local scripts to run.</span></span> <span data-ttu-id="b2937-152">インターネットからのスクリプトは、信頼された発行元によって署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2937-152">Scripts that originate from the Internet must be signed by a trusted publisher.</span></span> <span data-ttu-id="b2937-153">このポリシー設定は、RemoteSigned 実行ポリシーと同じです。</span><span class="sxs-lookup"><span data-stu-id="b2937-153">This policy setting is equivalent to the RemoteSigned execution policy.</span></span>

- <span data-ttu-id="b2937-154">**すべてのスクリプトを許可** するすべてのスクリプトの実行を許可します。</span><span class="sxs-lookup"><span data-stu-id="b2937-154">**Allow all scripts** allows all scripts to run.</span></span> <span data-ttu-id="b2937-155">このポリシー設定は、無制限の実行ポリシーに相当します。</span><span class="sxs-lookup"><span data-stu-id="b2937-155">This policy setting is equivalent to the Unrestricted execution policy.</span></span>

<span data-ttu-id="b2937-156">このポリシー設定を無効にした場合、スクリプトの実行は一切許可されません。</span><span class="sxs-lookup"><span data-stu-id="b2937-156">If you disable this policy setting, no scripts are allowed to run.</span></span> <span data-ttu-id="b2937-157">このポリシー設定は、制限された実行ポリシーに相当します。</span><span class="sxs-lookup"><span data-stu-id="b2937-157">This policy setting is equivalent to the Restricted execution policy.</span></span>

<span data-ttu-id="b2937-158">このポリシー設定を無効にした場合、または構成しなかった場合、コマンドレットによってコンピューターまたはユーザーに設定されている実行ポリシーによって、 `Set-ExecutionPolicy` スクリプトの実行が許可されているかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="b2937-158">If you disable or do not configure this policy setting, the execution policy that is set for the computer or user by the `Set-ExecutionPolicy` cmdlet determines whether scripts are permitted to run.</span></span> <span data-ttu-id="b2937-159">既定値は Restricted です。</span><span class="sxs-lookup"><span data-stu-id="b2937-159">The default value is Restricted.</span></span>

<span data-ttu-id="b2937-160">詳細については、「[about_Execution_Policies](about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2937-160">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

## <a name="turn-on-powershell-transcription"></a><span data-ttu-id="b2937-161">Powershell の議事録を有効にする</span><span class="sxs-lookup"><span data-stu-id="b2937-161">Turn on powershell transcription</span></span>

<span data-ttu-id="b2937-162">**[Powershell のトランスクリプトを有効に** する] ポリシー設定を使用すると、powershell Core コマンドの入力と出力をテキストベースのトランスクリプトにキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="b2937-162">The **Turn on PowerShell Transcription** policy setting lets you capture the input and output of PowerShell Core commands into text-based transcripts.</span></span> <span data-ttu-id="b2937-163">このポリシー設定を有効にした場合、powershell core と powershell core エンジンを利用するその他のアプリケーションの議事録ログが有効になります。</span><span class="sxs-lookup"><span data-stu-id="b2937-163">If you enable this policy setting, PowerShell Core will enable transcription logging for PowerShell Core and any other applications that leverage the PowerShell Core engine.</span></span> <span data-ttu-id="b2937-164">既定では、PowerShell Core は各ユーザーの My Documents ディレクトリにトランスクリプト出力を記録します。ファイル名には ' PowerShell_transcript ' が含まれ、コンピューター名と時刻が開始されます。</span><span class="sxs-lookup"><span data-stu-id="b2937-164">By default, PowerShell Core will record transcript output to each users' My Documents directory, with a file name that includes 'PowerShell_transcript', along with the computer name and time started.</span></span>
<span data-ttu-id="b2937-165">このポリシーを有効にすることは、各 PowerShell コアセッションで Start-Transcript コマンドレットを呼び出すことと同じです。</span><span class="sxs-lookup"><span data-stu-id="b2937-165">Enabling this policy is equivalent to calling the Start-Transcript cmdlet on each PowerShell Core session.</span></span>

<span data-ttu-id="b2937-166">このポリシー設定を無効にした場合、PowerShell ベースのアプリケーションの議事録のログ記録は既定で無効になりますが、Start-Transcript コマンドレットを使用してトランスクリプトを有効にすることはできます。</span><span class="sxs-lookup"><span data-stu-id="b2937-166">If you disable this policy setting, transcription logging of PowerShell-based applications is disabled by default, although transcripting can still be enabled through the Start-Transcript cmdlet.</span></span>

<span data-ttu-id="b2937-167">OutputDirectory 設定を使用して、共有の場所への議事録ログ記録を有効にする場合は、そのディレクトリへのアクセスを制限して、他のユーザーやコンピューターのトランスクリプトをユーザーが表示できないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="b2937-167">If you use the OutputDirectory setting to enable transcription logging to a shared location, be sure to limit access to that directory to prevent users from viewing the transcripts of other users or computers.</span></span>

## <a name="set-the-default-source-path-for-update-help"></a><span data-ttu-id="b2937-168">Update-Help の既定のソース パスを設定する</span><span class="sxs-lookup"><span data-stu-id="b2937-168">Set the default source path for Update-Help</span></span>

<span data-ttu-id="b2937-169">Update-help ポリシー設定 **の既定のソースパス** を設定すると、コマンドレットの **SourcePath** パラメーターの既定値が設定され `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="b2937-169">The **Set the Default Source Path for Update-Help** policy setting sets a default value for the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span>
<span data-ttu-id="b2937-170">この設定は、ユーザーがコマンドレットを使用して `Update-Help` インターネットからヘルプファイルをダウンロードできないようにします。</span><span class="sxs-lookup"><span data-stu-id="b2937-170">This setting prevents users from using the `Update-Help` cmdlet to download help files from the Internet.</span></span>

> [!NOTE]
> <span data-ttu-id="b2937-171">このグループポリシー設定は、[ **コンピューターの構成** ] と [ユーザーの **構成** ] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2937-171">This Group Policy setting appears under **Computer Configuration** and **User Configuration**.</span></span> <span data-ttu-id="b2937-172">ただし、[ **コンピューターの構成** ] の下のグループポリシー設定のみが有効です。</span><span class="sxs-lookup"><span data-stu-id="b2937-172">However, only the Group Policy setting under **Computer Configuration** is effective.</span></span> <span data-ttu-id="b2937-173">[ **ユーザーの構成** ] の下のグループポリシー設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="b2937-173">The Group Policy setting under **User Configuration** is ignored.</span></span>

<span data-ttu-id="b2937-174">`Update-Help`コマンドレットは、PowerShell モジュールの最新のヘルプファイルをダウンロードしてインストールし、コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="b2937-174">The `Update-Help` cmdlet downloads and installs the newest help files for PowerShell modules and installs them on the computer.</span></span> <span data-ttu-id="b2937-175">既定では、は、 `Update-Help` モジュールによって指定されたインターネット上の場所から新しいヘルプファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b2937-175">By default, `Update-Help` downloads new help files from an Internet location specified by the module.</span></span>

<span data-ttu-id="b2937-176">ただし、コマンドレットを使用し `Save-Help` て、最新のヘルプファイルをネットワーク共有などのファイルシステムの場所にダウンロードしてから、コマンドレットを使用して `Update-Help` ファイルシステムの場所からヘルプファイルを取得し、コンピューターにインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="b2937-176">However, you can use the `Save-Help` cmdlet to download the newest help files to a file system location, such as a network share, and then use the `Update-Help` cmdlet to get the help files from the file system location and install them on the computer.</span></span> <span data-ttu-id="b2937-177">コマンドレットの **SourcePath** パラメーターは、 `Update-Help` ファイルシステムの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="b2937-177">The **SourcePath** parameter of the `Update-Help` cmdlet specifies the file system location.</span></span>

<span data-ttu-id="b2937-178">**Sourcepath** パラメーターの既定値を指定すると、このグループポリシー設定によって、 **sourcepath** パラメーターがすべてのコマンドに暗黙的に追加され `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="b2937-178">By providing a default value for the **SourcePath** parameter, this Group Policy setting implicitly adds the **SourcePath** parameter to all `Update-Help` commands.</span></span> <span data-ttu-id="b2937-179">ユーザーは、別のファイルシステムの場所を入力することによって、既定値として指定されている特定のファイルシステムの場所を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="b2937-179">Users can override the particular file system location specified as the default value by entering a different file system location.</span></span>
<span data-ttu-id="b2937-180">ただし、コマンドから **SourcePath** パラメーターを削除することはできません `Update-Help` 。</span><span class="sxs-lookup"><span data-stu-id="b2937-180">But they cannot remove the **SourcePath** parameter from the `Update-Help` command.</span></span>

<span data-ttu-id="b2937-181">このポリシー設定を有効にした場合、 **SourcePath** パラメーターの既定値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b2937-181">If you enable this policy setting, you can specify a default value for the **SourcePath** parameter.</span></span> <span data-ttu-id="b2937-182">ファイルシステムの場所を入力してください。</span><span class="sxs-lookup"><span data-stu-id="b2937-182">Enter a file system location.</span></span>

<span data-ttu-id="b2937-183">このポリシー設定を無効にした場合、または構成しなかった場合、コマンドレットの **SourcePath** パラメーターの既定値はありません `Update-Help` 。</span><span class="sxs-lookup"><span data-stu-id="b2937-183">If this policy setting is disabled or not configured, there is no default value for the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span> <span data-ttu-id="b2937-184">ユーザーは、インターネットまたは任意のファイルシステムの場所からヘルプをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="b2937-184">Users can download help from the Internet or from any file system location.</span></span>

<span data-ttu-id="b2937-185">詳しくは、「[about_Updatable_Help](about_Updatable_Help.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b2937-185">For more information, see [about_Updatable_Help](about_Updatable_Help.md).</span></span>

## <a name="keywords"></a><span data-ttu-id="b2937-186">Keywords</span><span class="sxs-lookup"><span data-stu-id="b2937-186">Keywords</span></span>

<span data-ttu-id="b2937-187">about_Group_Policies about_GroupPolicy</span><span class="sxs-lookup"><span data-stu-id="b2937-187">about_Group_Policies about_GroupPolicy</span></span>

## <a name="see-also"></a><span data-ttu-id="b2937-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2937-188">See also</span></span>

[<span data-ttu-id="b2937-189">PowerShell Core ポリシー RFC</span><span class="sxs-lookup"><span data-stu-id="b2937-189">PowerShell Core Policy RFC</span></span>](https://github.com/PowerShell/PowerShell-RFC/blob/master/4-Experimental-Accepted/RFC0041-Policy.md)

[<span data-ttu-id="b2937-190">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="b2937-190">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="b2937-191">about_Modules</span><span class="sxs-lookup"><span data-stu-id="b2937-191">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="b2937-192">about_Updatable_Help</span><span class="sxs-lookup"><span data-stu-id="b2937-192">about_Updatable_Help</span></span>](about_Updatable_Help.md)

[<span data-ttu-id="b2937-193">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="b2937-193">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="b2937-194">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="b2937-194">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="b2937-195">Get-Module</span><span class="sxs-lookup"><span data-stu-id="b2937-195">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="b2937-196">Update-Help</span><span class="sxs-lookup"><span data-stu-id="b2937-196">Update-Help</span></span>](xref:Microsoft.PowerShell.Core.Update-Help)

[<span data-ttu-id="b2937-197">Save-Help</span><span class="sxs-lookup"><span data-stu-id="b2937-197">Save-Help</span></span>](xref:Microsoft.PowerShell.Core.Save-Help)

<!-- link references -->
[gpstore]: https://support.microsoft.com/help/3087759

