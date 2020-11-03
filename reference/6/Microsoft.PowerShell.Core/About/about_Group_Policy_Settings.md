---
description: PowerShell のグループポリシー設定について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 11/28/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_group_policy_settings?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Group_Policy_Settings
ms.openlocfilehash: 1533908be91703efd8509653b30d30de6b7c4a84
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221576"
---
# <a name="about-group-policy-settings"></a><span data-ttu-id="8fcb9-104">グループポリシー設定について</span><span class="sxs-lookup"><span data-stu-id="8fcb9-104">About Group Policy Settings</span></span>

## <a name="short-description"></a><span data-ttu-id="8fcb9-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="8fcb9-105">Short description</span></span>
<span data-ttu-id="8fcb9-106">PowerShell のグループポリシー設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-106">Describes the Group Policy settings for PowerShell</span></span>

## <a name="long-description"></a><span data-ttu-id="8fcb9-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="8fcb9-107">Long description</span></span>

<span data-ttu-id="8fcb9-108">PowerShell には、エンタープライズ環境で Windows コンピューターの一貫した構成値を定義するのに役立つグループポリシー設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-108">PowerShell includes Group Policy settings to help you define consistent configuration values for Windows computers in an enterprise environment.</span></span>

<span data-ttu-id="8fcb9-109">PowerShell のグループポリシー設定は、次のグループポリシーパスにあります。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-109">The PowerShell Group Policy settings are in the following Group Policy paths:</span></span>

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

<span data-ttu-id="8fcb9-110">ユーザー構成パスのグループポリシー設定は、コンピューターの構成パスのグループポリシー設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-110">Group policy settings in the User Configuration path take precedence over Group Policy settings in the Computer Configuration path.</span></span>

<span data-ttu-id="8fcb9-111">テンプレートをインストールしたら、グループポリシーエディター () でこれらの設定を編集でき `gpedit.msc` ます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-111">After installing the templates, you can edit these settings in the Group Policy editor (`gpedit.msc`).</span></span>

<span data-ttu-id="8fcb9-112">ポリシーは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-112">The policies are as follows:</span></span>

- <span data-ttu-id="8fcb9-113">モジュールのログ記録を有効にする: モジュールの **Logpipelineexecutiondetails** プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-113">Turn on Module Logging: Sets the **LogPipelineExecutionDetails** property of modules.</span></span>
- <span data-ttu-id="8fcb9-114">PowerShell スクリプト ブロックのログ記録を有効にする:すべての PowerShell スクリプトの詳細なログ記録を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-114">Turn on PowerShell Script Block Logging: Enables detailed logging of all PowerShell scripts.</span></span>
- <span data-ttu-id="8fcb9-115">スクリプトの実行を有効にする:PowerShell 実行ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-115">Turn on Script Execution: Sets the PowerShell execution policy.</span></span>
- <span data-ttu-id="8fcb9-116">PowerShell トランスクリプションを有効にする: PowerShell コマンドの入出力をテキスト ベースのトランスクリプトにキャプチャできるようにします。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-116">Turn on PowerShell Transcription: enables capturing of input and output of PowerShell commands into text-based transcripts.</span></span>
- <span data-ttu-id="8fcb9-117">の既定のソースパスを設定する `Update-Help` : 更新可能なヘルプのソースを、インターネットではなくディレクトリに設定します。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-117">Set the default source path for `Update-Help`: Sets the source for Updatable Help to a directory, not the Internet.</span></span>

<span data-ttu-id="8fcb9-118">他のテンプレートを取得し、グループポリシーを構成する方法の詳細については、「 [Windows でグループポリシー管理用テンプレートの中央ストアを作成および管理する方法][gpstore]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-118">For more information about acquiring other templates and configuring Group policy, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows][gpstore].</span></span>

## <a name="turn-on-module-logging"></a><span data-ttu-id="8fcb9-119">モジュールログをオンにする</span><span class="sxs-lookup"><span data-stu-id="8fcb9-119">Turn on module logging</span></span>

<span data-ttu-id="8fcb9-120">[ **モジュールログをオンにする** ] ポリシー設定は、選択した PowerShell モジュールのログ記録を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-120">The **Turn on Module Logging** policy setting turns on logging for selected PowerShell modules.</span></span> <span data-ttu-id="8fcb9-121">この設定は、影響を受けるすべてのコンピューター上のすべてのセッションで有効になります。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-121">The setting is effective in all sessions on all affected computers.</span></span>

<span data-ttu-id="8fcb9-122">このポリシー設定を有効にして1つ以上のモジュールを指定した場合、指定されたモジュールのパイプライン実行イベントは、イベントビューアーの Windows PowerShell ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-122">If you enable this policy setting and specify one or more modules, pipeline execution events for the specified modules are recorded in the Windows PowerShell log in Event Viewer.</span></span>

<span data-ttu-id="8fcb9-123">このポリシー設定を無効にした場合、すべての PowerShell モジュールに対して実行イベントのログ記録が無効になります。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-123">If you disable this policy setting, logging of execution events is disabled for all PowerShell modules.</span></span>

<span data-ttu-id="8fcb9-124">このポリシー設定が構成されていない場合、各モジュールの **Logpipelineexecutiondetails** プロパティによって、モジュールの実行イベントがログに記録されるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-124">If this policy setting is not configured, the **LogPipelineExecutionDetails** property of each module determines whether the execution events of a module are logged.</span></span> <span data-ttu-id="8fcb9-125">既定では、すべてのモジュールの **Logpipelineexecutiondetails** プロパティは False に設定されています。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-125">By default, the **LogPipelineExecutionDetails** property of all modules is set to False.</span></span>

<span data-ttu-id="8fcb9-126">モジュールのモジュールログをオンにするには、次のコマンド形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-126">To turn on module logging for a module, use the following command format.</span></span> <span data-ttu-id="8fcb9-127">モジュールをセッションにインポートする必要があります。この設定は、現在のセッションでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-127">The module must be imported into the session and the setting is effective only in the current session.</span></span>

```powershell
Import-Module <Module-Name>
(Get-Module <Module-Name>).LogPipelineExecutionDetails = $true
```

<span data-ttu-id="8fcb9-128">特定のコンピューター上のすべてのセッションのモジュールログをオンにするには、前のコマンドを "すべてのユーザー" PowerShell プロファイル () に追加し `$Profile.AllUsersAllHosts` ます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-128">To turn on module logging for all sessions on a particular computer, add the previous commands to the 'All Users' PowerShell profile (`$Profile.AllUsersAllHosts`).</span></span>

<span data-ttu-id="8fcb9-129">モジュールログの詳細については、「 [about_Modules](about_Modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-129">For more information about module logging, see [about_Modules](about_Modules.md).</span></span>

## <a name="turn-on-powershell-script-block-logging"></a><span data-ttu-id="8fcb9-130">PowerShell スクリプトブロックのログ記録を有効にする</span><span class="sxs-lookup"><span data-stu-id="8fcb9-130">Turn on PowerShell script block logging</span></span>

<span data-ttu-id="8fcb9-131">**[Powershell スクリプトブロックのログ記録を有効に** する] ポリシー設定を使用すると、powershell スクリプトのすべての入力を、Microsoft-Windows Powershell/Operational イベントログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-131">The **Turn on PowerShell Script Block Logging** policy setting enables logging of all PowerShell script input to the Microsoft-Windows-PowerShell/Operational event log.</span></span> <span data-ttu-id="8fcb9-132">このポリシー設定を有効にした場合、PowerShell Core は、対話形式で起動したか、またはオートメーションを使用して、コマンド、スクリプトブロック、関数、およびスクリプトの処理をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-132">If you enable this policy setting, PowerShell Core will log the processing of commands, script blocks, functions, and scripts - whether invoked interactively, or through automation.</span></span>

<span data-ttu-id="8fcb9-133">このポリシー設定を無効にすると、PowerShell スクリプトの入力のログ記録は無効になります。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-133">If you disable this policy setting, logging of PowerShell script input is disabled.</span></span> <span data-ttu-id="8fcb9-134">スクリプト ブロックの呼び出しのログ記録を有効にすると、PowerShell はさらに、コマンド、スクリプト ブロック、関数、またはスクリプトの呼び出しの開始時または停止時にイベントを記録します。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-134">If you enable the Script Block Invocation Logging, PowerShell additionally logs events when invocation of a command, script block, function, or script starts or stops.</span></span> <span data-ttu-id="8fcb9-135">呼び出しのログ記録を有効にすると、大量のイベント ログが生成されます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-135">Enabling Invocation Logging generates a high volume of event logs.</span></span>

## <a name="turn-on-script-execution"></a><span data-ttu-id="8fcb9-136">スクリプトの実行を有効にする</span><span class="sxs-lookup"><span data-stu-id="8fcb9-136">Turn on script execution</span></span>

<span data-ttu-id="8fcb9-137">[ **スクリプトの実行を有効に** する] ポリシー設定では、コンピューターとユーザーの実行ポリシーを設定します。これにより、実行が許可されるスクリプトが決まります。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-137">The **Turn on Script Execution** policy setting sets the execution policy for computers and users, which determines which scripts are permitted to run.</span></span>

<span data-ttu-id="8fcb9-138">ポリシー設定を有効にした場合は、次のポリシー設定の中から選択できます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-138">If you enable the policy setting, you can select from among the following policy settings.</span></span>

- <span data-ttu-id="8fcb9-139">**署名済みスクリプトのみを許可** するスクリプトは、信頼された発行元によって署名されている場合にのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-139">**Allow only signed scripts** allows scripts to execute only if they are signed by a trusted publisher.</span></span> <span data-ttu-id="8fcb9-140">このポリシー設定は、AllSigned 実行ポリシーと同じです。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-140">This policy setting is equivalent to the AllSigned execution policy.</span></span>

- <span data-ttu-id="8fcb9-141">**ローカルスクリプトおよびリモートの署名済みスクリプトを許可すると、** すべてのローカルスクリプトを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-141">**Allow local scripts and remote signed scripts** allows all local scripts to run.</span></span> <span data-ttu-id="8fcb9-142">インターネットからのスクリプトは、信頼された発行元によって署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-142">Scripts that originate from the Internet must be signed by a trusted publisher.</span></span> <span data-ttu-id="8fcb9-143">このポリシー設定は、RemoteSigned 実行ポリシーと同じです。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-143">This policy setting is equivalent to the RemoteSigned execution policy.</span></span>

- <span data-ttu-id="8fcb9-144">**すべてのスクリプトを許可** するすべてのスクリプトの実行を許可します。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-144">**Allow all scripts** allows all scripts to run.</span></span> <span data-ttu-id="8fcb9-145">このポリシー設定は、無制限の実行ポリシーに相当します。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-145">This policy setting is equivalent to the Unrestricted execution policy.</span></span>

<span data-ttu-id="8fcb9-146">このポリシー設定を無効にした場合、スクリプトの実行は一切許可されません。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-146">If you disable this policy setting, no scripts are allowed to run.</span></span> <span data-ttu-id="8fcb9-147">このポリシー設定は、制限された実行ポリシーに相当します。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-147">This policy setting is equivalent to the Restricted execution policy.</span></span>

<span data-ttu-id="8fcb9-148">このポリシー設定を無効にした場合、または構成しなかった場合、コマンドレットによってコンピューターまたはユーザーに設定されている実行ポリシーによって、 `Set-ExecutionPolicy` スクリプトの実行が許可されているかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-148">If you disable or do not configure this policy setting, the execution policy that is set for the computer or user by the `Set-ExecutionPolicy` cmdlet determines whether scripts are permitted to run.</span></span> <span data-ttu-id="8fcb9-149">既定値は Restricted です。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-149">The default value is Restricted.</span></span>

<span data-ttu-id="8fcb9-150">詳細については、「[about_Execution_Policies](about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-150">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

## <a name="turn-on-powershell-transcription"></a><span data-ttu-id="8fcb9-151">Powershell の議事録を有効にする</span><span class="sxs-lookup"><span data-stu-id="8fcb9-151">Turn on powershell transcription</span></span>

<span data-ttu-id="8fcb9-152">**[Powershell のトランスクリプトを有効に** する] ポリシー設定を使用すると、powershell Core コマンドの入力と出力をテキストベースのトランスクリプトにキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-152">The **Turn on PowerShell Transcription** policy setting lets you capture the input and output of PowerShell Core commands into text-based transcripts.</span></span> <span data-ttu-id="8fcb9-153">このポリシー設定を有効にした場合、powershell core と powershell core エンジンを利用するその他のアプリケーションの議事録ログが有効になります。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-153">If you enable this policy setting, PowerShell Core will enable transcription logging for PowerShell Core and any other applications that leverage the PowerShell Core engine.</span></span> <span data-ttu-id="8fcb9-154">既定では、PowerShell Core は各ユーザーの My Documents ディレクトリにトランスクリプト出力を記録します。ファイル名には ' PowerShell_transcript ' が含まれ、コンピューター名と時刻が開始されます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-154">By default, PowerShell Core will record transcript output to each users' My Documents directory, with a file name that includes 'PowerShell_transcript', along with the computer name and time started.</span></span>
<span data-ttu-id="8fcb9-155">このポリシーを有効にすることは、各 PowerShell コアセッションで Start-Transcript コマンドレットを呼び出すことと同じです。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-155">Enabling this policy is equivalent to calling the Start-Transcript cmdlet on each PowerShell Core session.</span></span>

<span data-ttu-id="8fcb9-156">このポリシー設定を無効にした場合、PowerShell ベースのアプリケーションの議事録のログ記録は既定で無効になりますが、Start-Transcript コマンドレットを使用してトランスクリプトを有効にすることはできます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-156">If you disable this policy setting, transcription logging of PowerShell-based applications is disabled by default, although transcripting can still be enabled through the Start-Transcript cmdlet.</span></span>

<span data-ttu-id="8fcb9-157">OutputDirectory 設定を使用して、共有の場所への議事録ログ記録を有効にする場合は、そのディレクトリへのアクセスを制限して、他のユーザーやコンピューターのトランスクリプトをユーザーが表示できないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-157">If you use the OutputDirectory setting to enable transcription logging to a shared location, be sure to limit access to that directory to prevent users from viewing the transcripts of other users or computers.</span></span>

## <a name="set-the-default-source-path-for-update-help"></a><span data-ttu-id="8fcb9-158">Update-Help の既定のソース パスを設定する</span><span class="sxs-lookup"><span data-stu-id="8fcb9-158">Set the default source path for Update-Help</span></span>

<span data-ttu-id="8fcb9-159">Update-help ポリシー設定 **の既定のソースパス** を設定すると、コマンドレットの **SourcePath** パラメーターの既定値が設定され `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-159">The **Set the Default Source Path for Update-Help** policy setting sets a default value for the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span>
<span data-ttu-id="8fcb9-160">この設定は、ユーザーがコマンドレットを使用して `Update-Help` インターネットからヘルプファイルをダウンロードできないようにします。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-160">This setting prevents users from using the `Update-Help` cmdlet to download help files from the Internet.</span></span>

> [!NOTE]
> <span data-ttu-id="8fcb9-161">このグループポリシー設定は、[ **コンピューターの構成** ] と [ユーザーの **構成** ] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-161">This Group Policy setting appears under **Computer Configuration** and **User Configuration**.</span></span> <span data-ttu-id="8fcb9-162">ただし、[ **コンピューターの構成** ] の下のグループポリシー設定のみが有効です。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-162">However, only the Group Policy setting under **Computer Configuration** is effective.</span></span> <span data-ttu-id="8fcb9-163">[ **ユーザーの構成** ] の下のグループポリシー設定は無視されます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-163">The Group Policy setting under **User Configuration** is ignored.</span></span>

<span data-ttu-id="8fcb9-164">`Update-Help`コマンドレットは、PowerShell モジュールの最新のヘルプファイルをダウンロードしてインストールし、コンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-164">The `Update-Help` cmdlet downloads and installs the newest help files for PowerShell modules and installs them on the computer.</span></span> <span data-ttu-id="8fcb9-165">既定では、は、 `Update-Help` モジュールによって指定されたインターネット上の場所から新しいヘルプファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-165">By default, `Update-Help` downloads new help files from an Internet location specified by the module.</span></span>

<span data-ttu-id="8fcb9-166">ただし、コマンドレットを使用し `Save-Help` て、最新のヘルプファイルをネットワーク共有などのファイルシステムの場所にダウンロードしてから、コマンドレットを使用して `Update-Help` ファイルシステムの場所からヘルプファイルを取得し、コンピューターにインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-166">However, you can use the `Save-Help` cmdlet to download the newest help files to a file system location, such as a network share, and then use the `Update-Help` cmdlet to get the help files from the file system location and install them on the computer.</span></span> <span data-ttu-id="8fcb9-167">コマンドレットの **SourcePath** パラメーターは、 `Update-Help` ファイルシステムの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-167">The **SourcePath** parameter of the `Update-Help` cmdlet specifies the file system location.</span></span>

<span data-ttu-id="8fcb9-168">**Sourcepath** パラメーターの既定値を指定すると、このグループポリシー設定によって、 **sourcepath** パラメーターがすべてのコマンドに暗黙的に追加され `Update-Help` ます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-168">By providing a default value for the **SourcePath** parameter, this Group Policy setting implicitly adds the **SourcePath** parameter to all `Update-Help` commands.</span></span> <span data-ttu-id="8fcb9-169">ユーザーは、別のファイルシステムの場所を入力することによって、既定値として指定されている特定のファイルシステムの場所を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-169">Users can override the particular file system location specified as the default value by entering a different file system location.</span></span>
<span data-ttu-id="8fcb9-170">ただし、コマンドから **SourcePath** パラメーターを削除することはできません `Update-Help` 。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-170">But they cannot remove the **SourcePath** parameter from the `Update-Help` command.</span></span>

<span data-ttu-id="8fcb9-171">このポリシー設定を有効にした場合、 **SourcePath** パラメーターの既定値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-171">If you enable this policy setting, you can specify a default value for the **SourcePath** parameter.</span></span> <span data-ttu-id="8fcb9-172">ファイルシステムの場所を入力してください。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-172">Enter a file system location.</span></span>

<span data-ttu-id="8fcb9-173">このポリシー設定を無効にした場合、または構成しなかった場合、コマンドレットの **SourcePath** パラメーターの既定値はありません `Update-Help` 。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-173">If this policy setting is disabled or not configured, there is no default value for the **SourcePath** parameter of the `Update-Help` cmdlet.</span></span> <span data-ttu-id="8fcb9-174">ユーザーは、インターネットまたは任意のファイルシステムの場所からヘルプをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-174">Users can download help from the Internet or from any file system location.</span></span>

<span data-ttu-id="8fcb9-175">詳しくは、「[about_Updatable_Help](about_Updatable_Help.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8fcb9-175">For more information, see [about_Updatable_Help](about_Updatable_Help.md).</span></span>

## <a name="keywords"></a><span data-ttu-id="8fcb9-176">Keywords</span><span class="sxs-lookup"><span data-stu-id="8fcb9-176">Keywords</span></span>

<span data-ttu-id="8fcb9-177">about_Group_Policies about_GroupPolicy</span><span class="sxs-lookup"><span data-stu-id="8fcb9-177">about_Group_Policies about_GroupPolicy</span></span>

## <a name="see-also"></a><span data-ttu-id="8fcb9-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fcb9-178">See also</span></span>

[<span data-ttu-id="8fcb9-179">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="8fcb9-179">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="8fcb9-180">about_Modules</span><span class="sxs-lookup"><span data-stu-id="8fcb9-180">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="8fcb9-181">about_Updatable_Help</span><span class="sxs-lookup"><span data-stu-id="8fcb9-181">about_Updatable_Help</span></span>](about_Updatable_Help.md)

[<span data-ttu-id="8fcb9-182">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="8fcb9-182">Get-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Get-ExecutionPolicy)

[<span data-ttu-id="8fcb9-183">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="8fcb9-183">Set-ExecutionPolicy</span></span>](xref:Microsoft.PowerShell.Security.Set-ExecutionPolicy)

[<span data-ttu-id="8fcb9-184">Get-Module</span><span class="sxs-lookup"><span data-stu-id="8fcb9-184">Get-Module</span></span>](xref:Microsoft.PowerShell.Core.Get-Module)

[<span data-ttu-id="8fcb9-185">Update-Help</span><span class="sxs-lookup"><span data-stu-id="8fcb9-185">Update-Help</span></span>](xref:Microsoft.PowerShell.Core.Update-Help)

[<span data-ttu-id="8fcb9-186">Save-Help</span><span class="sxs-lookup"><span data-stu-id="8fcb9-186">Save-Help</span></span>](xref:Microsoft.PowerShell.Core.Save-Help)

<!-- link references -->
[gpstore]: https://support.microsoft.com/help/3087759
