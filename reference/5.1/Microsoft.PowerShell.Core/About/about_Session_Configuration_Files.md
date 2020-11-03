---
description: セッション構成を使用するセッションの環境を定義するためにセッション構成 ("エンドポイント" とも呼ばれます) で使用されるセッション構成ファイルについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configuration_files?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configuration_Files
ms.openlocfilehash: 198a0aeb667c3c947bc7e202bc3c0d9832195b91
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222528"
---
# <a name="about-session-configuration-files"></a><span data-ttu-id="e8b25-104">セッション構成ファイルについて</span><span class="sxs-lookup"><span data-stu-id="e8b25-104">About Session Configuration Files</span></span>

## <a name="short-description"></a><span data-ttu-id="e8b25-105">概要</span><span class="sxs-lookup"><span data-stu-id="e8b25-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="e8b25-106">セッション構成を使用するセッションの環境を定義するためにセッション構成 ("エンドポイント" とも呼ばれます) で使用されるセッション構成ファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-106">Describes session configuration files, which are used in a session configuration (also known as an "endpoint") to define the environment of sessions that use the session configuration.</span></span>

## <a name="long-description"></a><span data-ttu-id="e8b25-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="e8b25-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="e8b25-108">"セッション構成ファイル" は、セッション構成のプロパティと値のハッシュテーブルを含む、.pssc ファイル名拡張子を持つテキストファイルです。</span><span class="sxs-lookup"><span data-stu-id="e8b25-108">A "session configuration file" is a text file with a .pssc file name extension that contains a hash table of session configuration properties and values.</span></span> <span data-ttu-id="e8b25-109">セッション構成ファイルを使用すると、セッション構成のプロパティを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-109">You can use a session configuration file to set the properties of a session configuration.</span></span> <span data-ttu-id="e8b25-110">これにより、そのセッション構成を使用するすべての Windows PowerShell セッションの環境が定義されます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-110">Doing so defines the environment of any Windows PowerShell sessions that use that session configuration.</span></span>

<span data-ttu-id="e8b25-111">セッション構成ファイルを使用すると、複雑な C# アセンブリまたはスクリプトを使用しなくても、カスタムセッション構成を簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-111">Session configuration files make it easy to create custom session configurations without using complex C# assemblies or scripts.</span></span>

<span data-ttu-id="e8b25-112">"セッション構成" または "エンドポイント" とは、コンピューター上でセッションを作成できるユーザーを決定する、ローカルコンピューターの設定のコレクションです。これらのセッションでユーザーが実行できるコマンドまた、セッションを特権仮想アカウントとして実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-112">A "session configuration" or "endpoint" is a collection of local computer settings that determine such things as which users can create sessions on the computer; which commands users can run in those sessions; and whether the session should run as a privileged virtual account.</span></span> <span data-ttu-id="e8b25-113">セッション構成の詳細については、「 [about_Session_Configurations](about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8b25-113">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

<span data-ttu-id="e8b25-114">セッション構成は Windows PowerShell 2.0 で導入され、セッション構成ファイルは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e8b25-114">Session configurations were introduced in Windows PowerShell 2.0, and session configuration files were introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="e8b25-115">セッション構成ファイルをセッション構成に含めるには、Windows PowerShell 3.0 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8b25-115">You must use Windows PowerShell 3.0 to include a session configuration file in a session configuration.</span></span> <span data-ttu-id="e8b25-116">ただし、Windows PowerShell 2.0 (以降) のユーザーは、セッション構成の設定の影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-116">However, users of Windows PowerShell 2.0 (and later) are affected by the settings in the session configuration.</span></span>

## <a name="creating-custom-sessions"></a><span data-ttu-id="e8b25-117">カスタムセッションの作成</span><span class="sxs-lookup"><span data-stu-id="e8b25-117">Creating Custom Sessions</span></span>

<span data-ttu-id="e8b25-118">セッション構成でセッションのプロパティを指定することで、Windows PowerShell セッションの多くの機能をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-118">You can customize many features of a Windows PowerShell session by specifying session properties in a session configuration.</span></span> <span data-ttu-id="e8b25-119">セッションをカスタマイズするには、カスタム実行空間を定義する C# プログラムを作成するか、セッション構成ファイルを使用して、セッション構成を使用して作成されたセッションのプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-119">You can customize a session by writing a C# program that defines a custom runspace, or you can use a session configuration file to define the properties of sessions created by using the session configuration.</span></span> <span data-ttu-id="e8b25-120">一般的な規則として、C# プログラムを記述するよりも、セッション構成ファイルを使用する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="e8b25-120">As a general rule, it is easier to use the session configuration file than to write a C# program.</span></span>

<span data-ttu-id="e8b25-121">セッション構成ファイルを使用すると、高度に信頼されたユーザーのために、完全に機能するセッションなどの項目を作成できます。最小限のアクセスを許可するロックダウンされたセッション特に設計されたセッション。これらのタスクに必要なモジュールのみが含まれています。特権のないユーザーが特定のコマンドを特権アカウントとしてのみ実行できるようにするセッション。</span><span class="sxs-lookup"><span data-stu-id="e8b25-121">You can use a session configuration file to create items such as fully-functioning sessions for highly trusted users; locked-down sessions that allow minimal access; sessions designed for particular and that contain only the modules required for those tasks; and sessions where unprivileged users can only run specific commands as a privileged account.</span></span>

<span data-ttu-id="e8b25-122">さらに、セッションのユーザーが Windows PowerShell の言語要素 (スクリプトブロックなど) を使用できるかどうかや、コマンドを実行できるかどうかを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-122">In addition to that, you can manage whether users of the session can use Windows PowerShell language elements such as script blocks, or whether they can only run commands.</span></span> <span data-ttu-id="e8b25-123">セッションで実行できる Windows PowerShell ユーザーのバージョンを管理できます。どのモジュールをセッションにインポートするかを管理します。また、ユーザーが実行できるコマンドレット、関数、およびエイリアスを管理します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-123">You can manage the version of Windows PowerShell users can run in the session; manage which modules are imported into the session; and manage which cmdlets, functions, and aliases session users can run.</span></span> <span data-ttu-id="e8b25-124">RoleDefinitions フィールドを使用すると、グループのメンバーシップに基づいて、ユーザーにセッションのさまざまな機能を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-124">When using the RoleDefinitions field, you can give users different capabilities in the session based on group membership.</span></span>

<span data-ttu-id="e8b25-125">RoleDefinitions とこの値の定義方法の詳細については、New-PSRoleCapabilityFile コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8b25-125">For more information about RoleDefinitions and how to define this Value, see the help topic for the New-PSRoleCapabilityFile Cmdlet.</span></span>

## <a name="creating-a-session-configuration-file"></a><span data-ttu-id="e8b25-126">セッション構成ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="e8b25-126">Creating a Session Configuration File</span></span>

<span data-ttu-id="e8b25-127">セッション構成ファイルを作成する最も簡単な方法は、New-PSSessionConfigurationFile コマンドレットを使用することです。</span><span class="sxs-lookup"><span data-stu-id="e8b25-127">The easiest way to create a session configuration file is by using the New-PSSessionConfigurationFile cmdlet.</span></span> <span data-ttu-id="e8b25-128">このコマンドレットは、正しい構文と形式を使用し、構成ファイルのプロパティ値の多くを自動的に検証するファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-128">This cmdlet generates a file that uses the correct syntax and format, and that automatically verifies many of the configuration file property values.</span></span>

<span data-ttu-id="e8b25-129">セッション構成ファイルで設定できるプロパティの詳細については、New-PSSessionConfigurationFile コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8b25-129">For detailed descriptions of the properties that you can set in a session configuration file, see the help topic for the New-PSSessionConfigurationFile cmdlet.</span></span>

<span data-ttu-id="e8b25-130">次のコマンドは、既定値を使用するセッション構成ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-130">The following command creates a session configuration file that uses the default values.</span></span> <span data-ttu-id="e8b25-131">パスパラメーター (ファイルパスを指定する) 以外のパラメーターが含まれていないため、結果の構成ファイルでは既定値のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-131">The resulting configuration file uses only the default values because no parameters other than the Path parameter (which specifies the file path) are included:</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\Defaults.pssc
```

<span data-ttu-id="e8b25-132">既定のテキストエディターで新しい構成ファイルを表示するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-132">To view the new configuration file in your default text editor, use the following command:</span></span>

```powershell
Invoke-Item -Path .\Defaults.pssc
```

<span data-ttu-id="e8b25-133">ユーザーがコマンドを実行でき、Windows PowerShell 言語の他の要素を使用しないセッションのセッション構成を作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-133">To create a session configuration for sessions in which user can run commands, but not use other elements of the Windows PowerShell language, type:</span></span>

```powershell
New-PSSessionConfigurationFile -LanguageMode NoLanguage
-Path .\NoLanguage.pssc
```

<span data-ttu-id="e8b25-134">前のコマンドで、LanguageMode パラメーターを NoLanguage に設定すると、ユーザーはスクリプトの記述や実行、変数の使用などを実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="e8b25-134">In the preceding command, setting the LanguageMode parameter to NoLanguage prevents users from doing such things as writing or running scripts, or using variables.</span></span>

<span data-ttu-id="e8b25-135">ユーザーが Get コマンドレットのみを使用できるセッションのセッション構成を作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-135">To create a session configuration for sessions in which users can use only Get cmdlets, type:</span></span>

```powershell
New-PSSessionConfigurationFile -VisibleCmdlets Get-*
-Path .\GetSessions.pssc
```

<span data-ttu-id="e8b25-136">前の例では、VisibleCmdlets パラメーターを Get-\* に設定すると、ユーザーは、文字列値 "Get-" で始まる名前を持つコマンドレットに制限されます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-136">In the preceding example, setting the VisibleCmdlets parameter to Get-\* limits users to cmdlets that have names that start with the string value "Get-".</span></span>

<span data-ttu-id="e8b25-137">ユーザーの資格情報ではなく、特権のある仮想アカウントで実行されるセッションのセッション構成を作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-137">To create a session configuration for sessions that run under a privileged virtual account instead of the user's credentials, type:</span></span>

```powershell
New-PSSessionConfigurationFile -RunAsVirtualAccount
-Path .\VirtualAccount.pssc
```

<span data-ttu-id="e8b25-138">ユーザーに表示されるコマンドがロール機能ファイルに指定されているセッションのセッション構成を作成するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-138">To create a session configuration for sessions in which the commands visible to the user are specified in a role capabilities file, type:</span></span>

```powershell
New-PSSessionConfigurationFile -RoleDefinitions
@{ 'CONTOSO\User' = @{ RoleCapabilities = 'Maintenance' }}
-Path .\Maintenance.pssc
```

### <a name="using-a-session-configuration-file"></a><span data-ttu-id="e8b25-139">セッション構成ファイルの使用</span><span class="sxs-lookup"><span data-stu-id="e8b25-139">Using a Session Configuration File</span></span>

<span data-ttu-id="e8b25-140">セッション構成を作成するとき、または追加するときに、セッション構成ファイルを含めることができます。後でセッション構成にファイルを追加できます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-140">You can include a session configuration file when you create a session configuration or add you can add a file to the session configuration at a later time.</span></span>

<span data-ttu-id="e8b25-141">セッション構成を作成するときにセッション構成ファイルを含めるには、Register-PSSessionConfiguration コマンドレットの Path パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-141">To include a session configuration file when creating a session configuration, use the Path parameter of the Register-PSSessionConfiguration cmdlet.</span></span>

<span data-ttu-id="e8b25-142">たとえば、次のコマンドでは、nolanguage セッション構成を作成するときに、.pssc ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-142">For example, the following command uses the NoLanguage.pssc file when it creates a NoLanguage session configuration.</span></span>

```powershell
Register-PSSessionConfiguration -Name NoLanguage
-Path .\NoLanguage.pssc
```

<span data-ttu-id="e8b25-143">新しい NoLanguage セッションが開始されると、ユーザーは Windows PowerShell コマンドにのみアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="e8b25-143">When a new NoLanguage session starts, users will only have access to Windows PowerShell commands.</span></span>

<span data-ttu-id="e8b25-144">セッション構成ファイルを既存のセッション構成に追加するには、Set-PSSessionConfiguration コマンドレットと Path パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-144">To add a session configuration file to an existing session configuration, use the Set-PSSessionConfiguration cmdlet and the Path parameter.</span></span> <span data-ttu-id="e8b25-145">これは、指定されたセッション構成で作成された新しいセッションに影響します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-145">This affects any new sessions created with the specified session configuration.</span></span> <span data-ttu-id="e8b25-146">Set-PSSessionConfiguration コマンドレットはセッション自体を変更し、セッション構成ファイルは変更しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e8b25-146">Note that the Set-PSSessionConfiguration cmdlet changes the session itself and does not modify the session configuration file.</span></span>

<span data-ttu-id="e8b25-147">たとえば、次のコマンドは、LockedDown セッション構成に NoLanguage ファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-147">For example, the following command adds the NoLanguage.pssc file to the LockedDown session configuration.</span></span>

```powershell
Set-PSSessionConfiguration -Name LockedDown
-Path .\NoLanguage.pssc
```

<span data-ttu-id="e8b25-148">ユーザーは、LockedDown セッション構成を使用してセッションを作成するときに、コマンドレットを実行できますが、変数の作成または使用、値の割り当て、または他の Windows PowerShell 言語要素の使用はできません。</span><span class="sxs-lookup"><span data-stu-id="e8b25-148">When users use the LockedDown session configuration to create a session, they will be able to run cmdlets but they will not be able to create or use variables, assign values, or use other Windows PowerShell language elements.</span></span>

<span data-ttu-id="e8b25-149">次のコマンドは、New-PSSession コマンドレットを使用して、LockedDown セッション構成を使用するコンピューター Srv01 上にセッションを作成し、そのセッションへのオブジェクト参照を $s 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-149">The following command uses the New-PSSession cmdlet to create a session on the computer Srv01 that uses the LockedDown session configuration, saving an object reference to the session in the $s variable.</span></span> <span data-ttu-id="e8b25-150">セッション構成の ACL (アクセス制御リスト) は、セッションの作成に使用できるユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-150">The ACL (access control list) of the session configuration determines who can use it to create a session.</span></span>

```powershell
$s = New-PSSession -ComputerName Srv01
-ConfigurationName LockedDown
```

<span data-ttu-id="e8b25-151">NoLanguage 制約は LockedDown セッション構成に追加されたため、LockedDown セッションのユーザーは Windows PowerShell コマンドとコマンドレットのみを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-151">Because the NoLanguage constraints were added to the LockedDown session configuration, users in LockedDown sessions will only be able to run Windows PowerShell commands and cmdlets.</span></span> <span data-ttu-id="e8b25-152">たとえば、次の2つのコマンドでは、Invoke-Command コマンドレットを使用して、$s 変数で参照されているセッションでコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-152">For example, the following two commands use the Invoke-Command cmdlet to run commands in the session referenced in the $s variable.</span></span> <span data-ttu-id="e8b25-153">最初のコマンドは、Get-UICulture コマンドレットを実行し、どの変数も使用しません。</span><span class="sxs-lookup"><span data-stu-id="e8b25-153">The first command, which runs the Get-UICulture cmdlet and does not use any variables, succeeds.</span></span> <span data-ttu-id="e8b25-154">$PSUICulture 変数の値を取得する2番目のコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-154">The second command, which gets the value of the $PSUICulture variable, fails.</span></span>

```
Invoke-Command -Session $s {Get-UICulture}
en-US

Invoke-Command -Session $s {$PSUICulture}
The syntax is not supported by this runspace. This might be
because it is in no-language mode.
+ CategoryInfo          : ParserError: ($PSUICulture:String) [],
ParseException
+ FullyQualifiedErrorId : ScriptsNotAllowed
```

## <a name="editing-a-session-configuration-file"></a><span data-ttu-id="e8b25-155">セッション構成ファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="e8b25-155">Editing a Session Configuration File</span></span>

<span data-ttu-id="e8b25-156">RunAsVirtualAccount および RunAsVirtualAccountGroups を除くセッション構成のすべての設定は、セッション構成で使用されるセッション構成ファイルを編集することによって変更できます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-156">All settings in a session configuration except for RunAsVirtualAccount and RunAsVirtualAccountGroups can be modified by editing the session configuration file used by the session configuration.</span></span> <span data-ttu-id="e8b25-157">これを行うには、まず、セッション構成ファイルのアクティブなコピーを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-157">To do this, begin by locating the active copy of the session configuration file.</span></span>

<span data-ttu-id="e8b25-158">セッション構成でセッション構成ファイルを使用すると、Windows PowerShell によってセッション構成ファイルのアクティブなコピーが作成され、 \$ \\ ローカルコンピューターの pshome sessionconfig ディレクトリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-158">When you use a session configuration file in a session configuration, Windows PowerShell creates an active copy of the session configuration file and stores it in the \$pshome\\SessionConfig directory on the local computer.</span></span>

<span data-ttu-id="e8b25-159">セッション構成ファイルのアクティブなコピーの場所は、セッション構成オブジェクトの ConfigFilePath プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-159">The location of the active copy of a session configuration file is stored in the ConfigFilePath property of the session configuration object.</span></span>

<span data-ttu-id="e8b25-160">次のコマンドは、NoLanguage セッション構成のセッション構成ファイルの場所を取得します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-160">The following command gets the location of the session configuration file for the NoLanguage session configuration.</span></span>

```powershell
(Get-PSSessionConfiguration -Name NoLanguage).ConfigFilePath
```

<span data-ttu-id="e8b25-161">このコマンドは、次のようなファイルパスを返します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-161">That command returns a file path similar to the following:</span></span>

```
C:\WINDOWS\System32\WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

<span data-ttu-id="e8b25-162">.Pssc ファイルは、任意のテキストエディターで編集できます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-162">You can edit the .pssc file in any text editor.</span></span> <span data-ttu-id="e8b25-163">ファイルが保存されると、そのセッション構成を使用する新しいセッションによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-163">After the file is saved it will be employed by any new sessions that use the session configuration.</span></span>

<span data-ttu-id="e8b25-164">RunAsVirtualAccount または RunAsVirtualAccountGroups の設定を変更する必要がある場合は、セッション構成を登録解除し、編集した値を含むセッション構成ファイルを再登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8b25-164">If you need to modify the RunAsVirtualAccount or the RunAsVirtualAccountGroups settings, you must un-register the session configuration and re-register a session configuration file that includes the edited values.</span></span>

## <a name="testing-a-session-configuration-file"></a><span data-ttu-id="e8b25-165">セッション構成ファイルをテストする</span><span class="sxs-lookup"><span data-stu-id="e8b25-165">Testing a Session Configuration File</span></span>

<span data-ttu-id="e8b25-166">Test-PSSessionConfigurationFile コマンドレットを使用して、手動で編集されたセッション構成ファイルをテストします。</span><span class="sxs-lookup"><span data-stu-id="e8b25-166">Use the Test-PSSessionConfigurationFile cmdlet to test manually edited session configuration files.</span></span> <span data-ttu-id="e8b25-167">これは重要なことです。ファイルの構文と値が有効でない場合、ユーザーはセッション構成を使用してセッションを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="e8b25-167">That's important: if the file syntax and values are not valid users will not be able to use the session configuration to create a session.</span></span>

<span data-ttu-id="e8b25-168">たとえば、次のコマンドは、NoLanguage セッション構成のアクティブなセッション構成ファイルをテストします。</span><span class="sxs-lookup"><span data-stu-id="e8b25-168">For example, the following command tests the active session configuration file of the NoLanguage session configuration.</span></span>

```powershell
Test-PSSessionConfigurationFile -Path C:\WINDOWS\System32\
WindowsPowerShell\v1.0\SessionConfig\
NoLanguage_0c115179-ff2a-4f66-a5eb-e56e5692ba22.pssc
```

<span data-ttu-id="e8b25-169">構成ファイルの構文と値が有効な場合 Test-PSSessionConfigurationFile は True を返します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-169">If the syntax and values in the configuration file are valid Test-PSSessionConfigurationFile returns True.</span></span> <span data-ttu-id="e8b25-170">構文と値が有効でない場合、コマンドレットは False を返します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-170">If the syntax and values are not valid then the cmdlet returns False.</span></span>

<span data-ttu-id="e8b25-171">Test-PSSessionConfigurationFile を使用すると、New-PSSessionConfiguration のコマンドレットによって作成されたファイルを含む、任意のセッション構成ファイルをテストできます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-171">You can use Test-PSSessionConfigurationFile to test any session configuration file, including files that the New-PSSessionConfiguration cmdlet creates.</span></span> <span data-ttu-id="e8b25-172">詳細については、Test-PSSessionConfigurationFile コマンドレットのヘルプトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8b25-172">For more information, see the help topic for the Test-PSSessionConfigurationFile cmdlet.</span></span>

## <a name="removing-a-session-configuration-file"></a><span data-ttu-id="e8b25-173">セッション構成ファイルの削除</span><span class="sxs-lookup"><span data-stu-id="e8b25-173">Removing a Session Configuration File</span></span>

<span data-ttu-id="e8b25-174">セッション構成からセッション構成ファイルを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="e8b25-174">You cannot remove a session configuration file from a session configuration.</span></span>
<span data-ttu-id="e8b25-175">ただし、ファイルは、既定の設定を使用する新しいファイルに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-175">However, you can replace the file with a new file that uses the default settings.</span></span> <span data-ttu-id="e8b25-176">これにより、元の構成ファイルで使用されている設定が実質的にキャンセルされます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-176">This effectively cancels the settings used by the original configuration file.</span></span>

<span data-ttu-id="e8b25-177">セッション構成ファイルを置き換えるには、既定の設定を使用する新しいセッション構成ファイルを作成し、Set-PSSessionConfiguration コマンドレットを使用してカスタムセッション構成ファイルを新しいファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-177">To replace a session configuration file, create a new session configuration file that uses the default settings, then use the Set-PSSessionConfiguration cmdlet to replace the custom session configuration file with the new file.</span></span>

<span data-ttu-id="e8b25-178">たとえば、次のコマンドを使用すると、既定のセッション構成ファイルが作成され、NoLanguage セッション構成のアクティブなセッション構成ファイルが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-178">For example, the following commands create a Default session configuration file and then replace the active session configuration file in the NoLanguage session configuration.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\Default.pssc
Set-PSSessionConfiguration -Name NoLanguage
-Path .\Default.pssc
```

<span data-ttu-id="e8b25-179">これらのコマンドが完了すると、NoLanguage セッション構成では、そのセッション構成を使用して作成されたすべてのセッションに対して、完全な言語サポート (既定の設定) が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-179">When these commands finish, the NoLanguage session configuration will actually provide full language support (the default setting) for all sessions created with that session configuration.</span></span>

<span data-ttu-id="e8b25-180">セッション構成のプロパティの表示セッション構成ファイルを使用してセッション構成を表すセッション構成オブジェクトには、セッション構成を簡単に検出して分析できるようにする追加のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="e8b25-180">Viewing the Properties of a Session Configuration The session configuration objects that represent session configurations using session configuration files have additional properties that make it easy to discover and analyze the session configuration.</span></span> <span data-ttu-id="e8b25-181">(次に示す型名には、書式設定されたビュー定義が含まれていることに注意してください)。Get-PSSessionConfiguration コマンドレットを実行してプロパティを表示し、返されたデータを Get-Member コマンドレットにパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-181">(Note that the type name shown below includes a formatted view definition.) You can view the properties by running the Get-PSSessionConfiguration cmdlet and piping the returned data to the Get-Member cmdlet:</span></span>

```powershell
Get-PSSessionConfiguration NoLanguage | Get-Member
```

```output
TypeName: Microsoft.PowerShell.Commands.PSSessionConfigurationCommands
#PSSessionConfiguration

Name                          MemberType     Definition
----                          ----------     ----------
Equals                        Method         bool Equals(System.O...
GetHashCode                   Method         int GetHashCode()
GetType                       Method         type GetType()
ToString                      Method         string ToString()
Architecture                  NoteProperty   System.String Archit...
Author                        NoteProperty   System.String Author...
AutoRestart                   NoteProperty   System.String AutoRe...
Capability                    NoteProperty   System.Object[] Capa...
CompanyName                   NoteProperty   System.String Compan...
configfilepath                NoteProperty   System.String config...
Copyright                     NoteProperty   System.String Copyri...
Enabled                       NoteProperty   System.String Enable...
ExactMatch                    NoteProperty   System.String ExactM...
ExecutionPolicy               NoteProperty   System.String Execut...
Filename                      NoteProperty   System.String Filena...
GUID                          NoteProperty   System.String GUID=0...
ProcessIdleTimeoutSec         NoteProperty   System.String Proces...
IdleTimeoutms                 NoteProperty   System.String IdleTi...
lang                          NoteProperty   System.String lang=e...
LanguageMode                  NoteProperty   System.String Langua...
MaxConcurrentCommandsPerShell NoteProperty   System.String MaxCon...
MaxConcurrentUsers            NoteProperty   System.String MaxCon...
MaxIdleTimeoutms              NoteProperty   System.String MaxIdl...
MaxMemoryPerShellMB           NoteProperty   System.String MaxMem...
MaxProcessesPerShell          NoteProperty   System.String MaxPro...
MaxShells                     NoteProperty   System.String MaxShells
MaxShellsPerUser              NoteProperty   System.String MaxShe...
Name                          NoteProperty   System.String Name=N...
PSVersion                     NoteProperty   System.String PSVersion
ResourceUri                   NoteProperty   System.String Resour...
RunAsPassword                 NoteProperty   System.String RunAsP...
RunAsUser                     NoteProperty   System.String RunAsUser
SchemaVersion                 NoteProperty   System.String Schema...
SDKVersion                    NoteProperty   System.String SDKVer...
OutputBufferingMode           NoteProperty   System.String Output...
SessionType                   NoteProperty   System.String Sessio...
UseSharedProcess              NoteProperty   System.String UseSha...
SupportsOptions               NoteProperty   System.String Suppor...
xmlns                         NoteProperty   System.String xmlns=...
XmlRenderingType              NoteProperty   System.String XmlRen...
Permission                    ScriptProperty System.Object Permis...
```

<span data-ttu-id="e8b25-182">これらのプロパティを使用すると、特定のセッション構成を簡単に検索できます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-182">These properties make it easy to search for specific session configurations.</span></span>
<span data-ttu-id="e8b25-183">たとえば、Set-executionpolicy プロパティを使用して、RemoteSigned 実行ポリシーを持つセッションをサポートするセッション構成を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-183">For example, you can use the ExecutionPolicy property to find a session configuration that supports sessions with the RemoteSigned execution policy.</span></span>
<span data-ttu-id="e8b25-184">Set-executionpolicy プロパティは、セッション構成ファイルを使用するセッションにのみ存在するため、適合するすべてのセッション構成が返されない場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e8b25-184">Note that, because the ExecutionPolicy property exists only on sessions that use session configuration files, the command might not return all qualifying session configurations.</span></span>

```powershell
Get-PSSessionConfiguration |
where {$_.ExecutionPolicy -eq "RemoteSigned"}
```

<span data-ttu-id="e8b25-185">次のコマンドは、RunAsUser が Exchange 管理者であるセッション構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-185">The following command gets session configurations in which the RunAsUser is the Exchange administrator.</span></span>

```powershell
 Get-PSSessionConfiguration |
where {$_.RunAsUser -eq "Exchange01\Admin01"}
```

<span data-ttu-id="e8b25-186">構成に関連付けられているロールの定義に関する情報を表示するには、Get-PSSessionCapability コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-186">To view information about the role definitions associated with a configuration use the Get-PSSessionCapability cmdlet.</span></span> <span data-ttu-id="e8b25-187">このコマンドレットを使用すると、特定のエンドポイント内の特定のユーザーが使用できるコマンドと環境を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-187">This cmdlet enables you to determine the commands and environment available to specific users in specific endpoints.</span></span>

## <a name="notes"></a><span data-ttu-id="e8b25-188">注</span><span class="sxs-lookup"><span data-stu-id="e8b25-188">NOTES</span></span>

<span data-ttu-id="e8b25-189">セッション構成では、"空の" セッションと呼ばれる種類のセッションもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-189">Session configurations also support a type of session known as an "empty" session.</span></span> <span data-ttu-id="e8b25-190">空のセッションの種類を使用すると、選択したコマンドでカスタムセッションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e8b25-190">An Empty session type enables you to create custom sessions with selected commands.</span></span> <span data-ttu-id="e8b25-191">モジュール、関数、またはスクリプトを空のセッションに追加しない場合、セッションは式に限定され、実用的に使用されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e8b25-191">If you do not add modules, functions, or scripts to an empty session, the session is limited to expressions and might not be of any practical use.</span></span> <span data-ttu-id="e8b25-192">SessionType プロパティは、空のセッションを使用しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e8b25-192">The SessionType property tells you whether or not you are working with an empty session.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8b25-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8b25-193">SEE ALSO</span></span>

[<span data-ttu-id="e8b25-194">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="e8b25-194">about_Session_Configurations</span></span>](about_Session_Configurations.md)

[<span data-ttu-id="e8b25-195">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="e8b25-195">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="e8b25-196">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="e8b25-196">Disable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[<span data-ttu-id="e8b25-197">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="e8b25-197">Enable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[<span data-ttu-id="e8b25-198">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="e8b25-198">Get-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[<span data-ttu-id="e8b25-199">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="e8b25-199">New-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[<span data-ttu-id="e8b25-200">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="e8b25-200">Register-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[<span data-ttu-id="e8b25-201">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="e8b25-201">Set-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[<span data-ttu-id="e8b25-202">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="e8b25-202">Test-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[<span data-ttu-id="e8b25-203">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="e8b25-203">Unregister-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)

[<span data-ttu-id="e8b25-204">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="e8b25-204">Get-PSSessionCapability</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionCapability)

[<span data-ttu-id="e8b25-205">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="e8b25-205">New-PSRoleCapabilityFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSRoleCapabilityFile)
