---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionOption
ms.openlocfilehash: d07942797bad3666a263e017fa8372e672936041
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601817"
---
# <span data-ttu-id="bd6a5-102">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="bd6a5-102">New-PSSessionOption</span></span>

## <span data-ttu-id="bd6a5-103">概要</span><span class="sxs-lookup"><span data-stu-id="bd6a5-103">SYNOPSIS</span></span>
<span data-ttu-id="bd6a5-104">PSSession の詳細設定オプションが格納されたオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-104">Creates an object that contains advanced options for a PSSession.</span></span>

## <span data-ttu-id="bd6a5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bd6a5-105">SYNTAX</span></span>

```
New-PSSessionOption [-MaximumRedirection <Int32>] [-NoCompression] [-NoMachineProfile] [-Culture <CultureInfo>]
 [-UICulture <CultureInfo>] [-MaximumReceivedDataSizePerCommand <Int32>] [-MaximumReceivedObjectSize <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-MaxConnectionRetryCount <Int32>]
 [-ApplicationArguments <PSPrimitiveDictionary>] [-OpenTimeout <Int32>] [-CancelTimeout <Int32>]
 [-IdleTimeout <Int32>] [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <AuthenticationMechanism>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [-IncludePortInSPN] [<CommonParameters>]
```

## <span data-ttu-id="bd6a5-106">Description</span><span class="sxs-lookup"><span data-stu-id="bd6a5-106">DESCRIPTION</span></span>

<span data-ttu-id="bd6a5-107">`New-PSSessionOption`コマンドレットにより、ユーザー管理セッション (**PSSession**) の詳細オプションを含むオブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-107">The `New-PSSessionOption` cmdlet creates an object that contains advanced options for a user-managed session (**PSSession**).</span></span> <span data-ttu-id="bd6a5-108">オブジェクトは、、、などの **PSSession** を作成するコマンドレットの **sessionoption** パラメーターの値として使用でき `New-PSSession` `Enter-PSSession` `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-108">You can use the object as the value of the **SessionOption** parameter of cmdlets that create a **PSSession**, such as `New-PSSession`, `Enter-PSSession`, and `Invoke-Command`.</span></span>

<span data-ttu-id="bd6a5-109">パラメーターを指定しない場合は、 `New-PSSessionOption` すべてのオプションの既定値を含むオブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-109">Without parameters, `New-PSSessionOption` generates an object that contains the default values for all of the options.</span></span> <span data-ttu-id="bd6a5-110">プロパティはすべて編集できるため、結果のオブジェクトをテンプレートとして使用して、会社用の標準的なオプション オブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-110">Because all of the properties can be edited, you can use the resulting object as a template, and create standard option objects for your enterprise.</span></span>

<span data-ttu-id="bd6a5-111">セッションオプションオブジェクトは、ユーザー設定変数に保存することもでき `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-111">You can also save a session option object in the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="bd6a5-112">この変数の値は、セッション オプションの新しい既定値を確立します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-112">The values of this variable establish new default values for the session options.</span></span> <span data-ttu-id="bd6a5-113">これらの値は、セッションに対してセッション オプションが設定されていない場合に有効になり、セッション構成に設定されたオプションよりも優先されます。ただし、セッション オプションを指定するか、セッションを作成するコマンドレットでセッション オプション オブジェクトを作成することによって、これらの値をオーバーライドすることができます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-113">They effective when no session options are set for the session and they take precedence over options set in the session configuration, but you can override them by specifying session options or a session option object in a cmdlet that creates a session.</span></span> <span data-ttu-id="bd6a5-114">ユーザー設定変数の詳細については `$PSSessionOption` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-114">For more information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="bd6a5-115">セッションを作成するコマンドレットでセッション オプション オブジェクトを使用すると、セッション オプション値は、$PSSessionOption ユーザー設定変数およびセッション構成に設定されたセッションの既定値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-115">When you use a session option object in a cmdlet that creates a session, the session option values take precedence over default values for sessions set in the $PSSessionOption preference variable and in the session configuration.</span></span> <span data-ttu-id="bd6a5-116">ただし、セッション構成で設定された最大値、クォータ、または制限よりも優先されることはありません。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-116">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span> <span data-ttu-id="bd6a5-117">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-117">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="bd6a5-118">例</span><span class="sxs-lookup"><span data-stu-id="bd6a5-118">EXAMPLES</span></span>

### <span data-ttu-id="bd6a5-119">例 1: 既定のセッションオプションを作成する</span><span class="sxs-lookup"><span data-stu-id="bd6a5-119">Example 1: Create a default session option</span></span>

<span data-ttu-id="bd6a5-120">このコマンドは、既定値をすべて持つセッションオプションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-120">This command creates a session option object that has all of the default values.</span></span>

```powershell
New-PSSessionOption
```

```Output
MaximumConnectionRedirectionCount : 5
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : IEConfig
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
Culture                           :
UICulture                         :
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         :
ApplicationArguments              :
OpenTimeout                       : 00:03:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : 00:04:00
```

### <span data-ttu-id="bd6a5-121">例 2: セッションオプションオブジェクトを使用してセッションを構成する</span><span class="sxs-lookup"><span data-stu-id="bd6a5-121">Example 2: Configure a session by using a session option object</span></span>

<span data-ttu-id="bd6a5-122">この例では、セッション オプション オブジェクトを使用してセッションを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-122">This example shows how to use a session option object to configure a session.</span></span>

```powershell
$pso = New-PSSessionOption -Culture "fr-fr" -MaximumReceivedObjectSize 10MB
New-PSSession -ComputerName Server01 -SessionOption $pso
```

<span data-ttu-id="bd6a5-123">最初のコマンドは、新しいセッションオプションオブジェクトを作成し、変数の値に保存し `$pso` ます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-123">The first command creates a new session option object and saves it in the value of the `$pso` variable.</span></span> <span data-ttu-id="bd6a5-124">2番目のコマンドは、コマンドレットを使用して、 `New-PSSession` Server01 リモートコンピューター上にセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-124">The second command uses the `New-PSSession` cmdlet to create a session on the Server01 remote computer.</span></span> <span data-ttu-id="bd6a5-125">このコマンドは、変数の値に含まれる session option オブジェクトを、 `$pso` コマンドの **sessionoption** パラメーターの値として使用します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-125">The command uses the session option object in the value of the `$pso` variable as the value of the **SessionOption** parameter of the command.</span></span>

### <span data-ttu-id="bd6a5-126">例 3: 対話型セッションを開始する</span><span class="sxs-lookup"><span data-stu-id="bd6a5-126">Example 3: Start an interactive session</span></span>

<span data-ttu-id="bd6a5-127">このコマンドは、 `Enter-PSSession` コマンドレットを使用して、Server01 コンピューターとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-127">This command uses the `Enter-PSSession` cmdlet to start an interactive session with the Server01 computer.</span></span>

```powershell
Enter-PSSession -ComputerName Server01 -SessionOption (New-PSSessionOption -NoEncryption -NoCompression)
```

<span data-ttu-id="bd6a5-128">**Sessionoption** パラメーターの値は、 `New-PSSessionOption` **Noencryption** および **noencryption** パラメーターを持つコマンドです。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-128">The value of the **SessionOption** parameter is a `New-PSSessionOption` command that has the **NoEncryption** and **NoCompression** parameters.</span></span>

<span data-ttu-id="bd6a5-129">コマンドは、 `New-PSSessionOption` コマンドの前に実行されるように、かっこで囲まれてい `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-129">The `New-PSSessionOption` command is enclosed in parentheses to make sure that it runs before the `Enter-PSSession` command.</span></span>

### <span data-ttu-id="bd6a5-130">例 4: セッションオプションオブジェクトを変更する</span><span class="sxs-lookup"><span data-stu-id="bd6a5-130">Example 4: Modify a session option object</span></span>

<span data-ttu-id="bd6a5-131">この例は、セッションオプションオブジェクトを変更できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-131">This example demonstrates that you can modify the session option object.</span></span> <span data-ttu-id="bd6a5-132">すべてのプロパティは、読み取り/書き込み値を持ちます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-132">All properties have read/write values.</span></span>

```powershell
$a = New-PSSessionOption
$a.OpenTimeout
```

```Output
Days              : 0
Hours             : 0
Minutes           : 3
Seconds           : 0
Milliseconds      : 0
Ticks             : 1800000000
TotalDays         : 0.00208333333333333
TotalHours        : 0.05
TotalMinutes      : 3
TotalSeconds      : 180
TotalMilliseconds : 180000
```

```powershell
$a.UICulture = (Get-UICulture)
$a.OpenTimeout = (New-Timespan -Minutes 4)
$a.MaximumConnectionRedirectionCount = 1
$a
```

```Output
MaximumConnectionRedirectionCount : 1
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : IEConfig
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
Culture                           :
UICulture                         : en-US
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         :
ApplicationArguments              :
OpenTimeout                       : 00:04:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : 00:04:00
```

<span data-ttu-id="bd6a5-133">この方法を使用して、会社の標準のセッション オブジェクトを作成し、特定の用途向けにカスタマイズされたバージョンを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-133">Use this method to create a standard session object for your enterprise, and then create customized versions of it for particular uses.</span></span>

### <span data-ttu-id="bd6a5-134">例 5: ユーザー設定変数を作成する</span><span class="sxs-lookup"><span data-stu-id="bd6a5-134">Example 5: Create a preference variable</span></span>

<span data-ttu-id="bd6a5-135">このコマンドは、ユーザー設定変数を作成し `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-135">This command creates a `$PSSessionOption` preference variable.</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -OpenTimeOut 120000
```

<span data-ttu-id="bd6a5-136">`$PSSessionOption`セッションでユーザー設定変数が発生すると、 `New-PSSession` 、 `Enter-PSSession` 、およびコマンドレットを使用して作成されたセッションのオプションの既定値が確立され `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-136">When the `$PSSessionOption` preference variable occurs in the session, it establishes default values for options in the sessions that are created by using the `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="bd6a5-137">`$PSSessionOption`変数をすべてのセッションで使用できるようにするには、powershell セッションと powershell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-137">To make the `$PSSessionOption` variable available in all sessions, add it to your PowerShell session and to your PowerShell profile.</span></span>

<span data-ttu-id="bd6a5-138">ユーザー設定変数の詳細については `$PSSessionOption` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-138">For more information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="bd6a5-139">プロファイルの詳細については、「[about_Profiles](About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-139">For more information about profiles, see [about_Profiles](About/about_Profiles.md).</span></span>

### <span data-ttu-id="bd6a5-140">例 6: リモートセッション構成の要件を満たす</span><span class="sxs-lookup"><span data-stu-id="bd6a5-140">Example 6: Fulfill the requirements for a remote session configuration</span></span>

<span data-ttu-id="bd6a5-141">この例では、**SessionOption** オブジェクトを使用してリモート セッション構成の要件を満たす方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-141">This example shows how to use a **SessionOption** object to fulfill the requirements for a remote session configuration.</span></span>

```powershell
$skipCN = New-PSSessionOption -SkipCNCheck
New-PSSession -ComputerName 171.09.21.207 -UseSSL -Credential Domain01\User01 -SessionOption $SkipCN
```

<span data-ttu-id="bd6a5-142">最初のコマンドは、 `New-PSSessionOption` コマンドレットを使用して、 **Skipcncheck** プロパティを持つセッションオプションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-142">The first command uses the `New-PSSessionOption` cmdlet to create a session option object that has the **SkipCNCheck** property.</span></span> <span data-ttu-id="bd6a5-143">このコマンドは、結果として得られるセッションオブジェクトを変数に保存し `$skipCN` ます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-143">The command saves the resulting session object in the `$skipCN` variable.</span></span>

<span data-ttu-id="bd6a5-144">2番目のコマンドは、コマンドレットを使用して、 `New-PSSession` リモートコンピューター上に新しいセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-144">The second command uses the `New-PSSession` cmdlet to create a new session on a remote computer.</span></span> <span data-ttu-id="bd6a5-145">`$skipCN`Check 変数は、 **sessionoption** パラメーターの値で使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-145">The `$skipCN` check variable is used in the value of the **SessionOption** parameter.</span></span>

<span data-ttu-id="bd6a5-146">コンピューターは IP アドレスによって識別されるので、 **ComputerName** パラメーターの値は、SECURE SOCKETS LAYER (SSL) に使用されている証明書の共通名のいずれとも一致しません。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-146">Because the computer is identified by its IP address, the value of the **ComputerName** parameter does not match any of the common names in the certificate that is used for Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="bd6a5-147">その結果、**SkipCNCheck** オプションが必要になります。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-147">As a result, the **SkipCNCheck** option is required.</span></span>

### <span data-ttu-id="bd6a5-148">例 7: リモートセッションで引数を使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="bd6a5-148">Example 7: Make arguments available to a remote session</span></span>

<span data-ttu-id="bd6a5-149">この例では、コマンドレットの **Applicationarguments** パラメーターを使用して `New-PSSessionOption` 、リモートセッションで追加のデータを使用できるようにする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-149">This example shows how to use the **ApplicationArguments** parameter of the `New-PSSessionOption` cmdlet to make additional data available to the remote session.</span></span>

```powershell
$team = @{Team="IT"; Use="Testing"}
$TeamOption = New-PSSessionOption -ApplicationArguments $team
$s = New-PSSession -ComputerName Server01 -SessionOption $TeamOption
Invoke-Command -Session $s {$PSSenderInfo.ApplicationArguments}
```

```Output
Name                 Value
----                 -----
Team                 IT
Use                  Testing
PSVersionTable       {CLRVersion, BuildVersion, PSVersion, WSManStackVersion...}
```

```powershell
Invoke-Command -Session $s {
  if ($PSSenderInfo.ApplicationArguments.Use -ne "Testing") {
    .\logFiles.ps1
  }
  else {
    "Just testing."
  }
}
```

```Output
Just testing.
```

<span data-ttu-id="bd6a5-150">最初のコマンドは、 **チーム** と **使用** の2つのキーを持つハッシュテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-150">The first command creates a hash table with two keys, **Team** and **Use**.</span></span> <span data-ttu-id="bd6a5-151">このコマンドは、ハッシュテーブルを変数に保存し `$team` ます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-151">The command saves the hash table in the `$team` variable.</span></span> <span data-ttu-id="bd6a5-152">ハッシュ テーブルの詳細については、「[about_Hash_Tables (ハッシュ テーブルについて)](about/about_Hash_Tables.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-152">For more information about hash tables, see [about_Hash_Tables](about/about_Hash_Tables.md).</span></span>

<span data-ttu-id="bd6a5-153">次に、 `New-PSSessionOption` **applicationarguments** パラメーターを使用してコマンドレットを作成し、変数に保存されたセッションオプションオブジェクトを作成し `$team` ます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-153">Next, the `New-PSSessionOption` cmdlet, using the **ApplicationArguments** parameter, creates a session option object saved in the `$team` variable.</span></span> <span data-ttu-id="bd6a5-154">`New-PSSessionOption`は、セッションオプションオブジェクトを作成するときに、 **applicationarguments** パラメーターの値のハッシュテーブルをプリミティブディクショナリに自動的に変換します。これにより、データが確実にリモートセッションに送信されるようになります。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-154">When `New-PSSessionOption` creates the session option object, it automatically converts the hash table in the value of the **ApplicationArguments** parameter to a primitive dictionary so the data can be reliably transmitted to the remote session.</span></span>

<span data-ttu-id="bd6a5-155">`New-PSSession`コマンドレットは、Server01 コンピューターでセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-155">The `New-PSSession` cmdlet starts a session on the Server01 computer.</span></span> <span data-ttu-id="bd6a5-156">この例では、 **Sessionoption** パラメーターを使用して、変数にオプションを含めて `$teamOption` います。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-156">It uses the **SessionOption** parameter to include the options in the `$teamOption` variable.</span></span>

<span data-ttu-id="bd6a5-157">`Invoke-Command`コマンドレットでは、変数内のデータを `$team` リモートセッションのコマンドで使用できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-157">The `Invoke-Command` cmdlet demonstrates that the data in the `$team` variable is available to commands in the remote session.</span></span> <span data-ttu-id="bd6a5-158">データは、自動変数の **Applicationarguments** プロパティに表示され `$PSSenderInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-158">The data appears in the **ApplicationArguments** property of the `$PSSenderInfo` automatic variable.</span></span>

<span data-ttu-id="bd6a5-159">最後に、 `Invoke-Command` データがどのように使用されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-159">The final `Invoke-Command` shows how the data might be used.</span></span>

## <span data-ttu-id="bd6a5-160">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bd6a5-160">PARAMETERS</span></span>

### <span data-ttu-id="bd6a5-161">-ApplicationArguments</span><span class="sxs-lookup"><span data-stu-id="bd6a5-161">-ApplicationArguments</span></span>

<span data-ttu-id="bd6a5-162">リモート セッションに送信されるプリミティブな辞書を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-162">Specifies a primitive dictionary that is sent to the remote session.</span></span> <span data-ttu-id="bd6a5-163">セッション構成のスタートアップスクリプトを含む、リモートセッションのコマンドとスクリプトは、自動変数の **Applicationarguments** プロパティでこのディクショナリを見つけることができ `$PSSenderInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-163">Commands and scripts in the remote session, including startup scripts in the session configuration, can find this dictionary in the **ApplicationArguments** property of the `$PSSenderInfo` automatic variable.</span></span> <span data-ttu-id="bd6a5-164">このパラメーターを使用すると、リモート セッションにデータを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-164">You can use this parameter to send data to the remote session.</span></span>

<span data-ttu-id="bd6a5-165">詳細については、「 [about_Hash_Tables](about/about_Hash_Tables.md)、 [about_Session_Configurations](About/about_Session_Configurations.md)、および [about_Automatic_Variables](about/about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-165">For more information, see [about_Hash_Tables](about/about_Hash_Tables.md), [about_Session_Configurations](About/about_Session_Configurations.md), and [about_Automatic_Variables](about/about_Automatic_Variables.md).</span></span>

```yaml
Type: System.Management.Automation.PSPrimitiveDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-166">-CancelTimeout</span><span class="sxs-lookup"><span data-stu-id="bd6a5-166">-CancelTimeout</span></span>

<span data-ttu-id="bd6a5-167">PowerShell がキャンセル操作 (CTRL + C) が終了するまで待機する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-167">Determines how long PowerShell waits for a cancel operation (CTRL+C) to finish before ending it.</span></span>
<span data-ttu-id="bd6a5-168">値をミリ秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-168">Enter a value in milliseconds.</span></span>

<span data-ttu-id="bd6a5-169">既定値は 60,000 (1 分) です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-169">The default value is 60000 (one minute).</span></span> <span data-ttu-id="bd6a5-170">値 0 (ゼロ) は、タイムアウトがないことを表します。つまり、コマンドは無期限に続行されます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-170">A value of 0 (zero) means no time-out; the command continues indefinitely.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: CancelTimeoutMSec

Required: False
Position: Named
Default value: 60000
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-171">-Culture</span><span class="sxs-lookup"><span data-stu-id="bd6a5-171">-Culture</span></span>

<span data-ttu-id="bd6a5-172">セッションに使用するカルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-172">Specifies the culture to use for the session.</span></span> <span data-ttu-id="bd6a5-173">カルチャ名を `<languagecode2>-<country/regioncode2>` 形式 (like など `ja-JP` )、 **cultureinfo** オブジェクトを含む変数、または **cultureinfo** オブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-173">Enter a culture name in `<languagecode2>-<country/regioncode2>` format (like `ja-JP`), a variable that contains a **CultureInfo** object, or a command that gets a **CultureInfo** object.</span></span>

<span data-ttu-id="bd6a5-174">既定値はであり、 `$Null` オペレーティングシステムで設定されているカルチャがセッションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-174">The default value is `$Null`, and the culture that is set in the operating system is used in the session.</span></span>

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-175">-IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="bd6a5-175">-IdleTimeout</span></span>

<span data-ttu-id="bd6a5-176">リモートコンピューターがローカルコンピューターから通信を受信していない場合に、セッションが開いたままになる期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-176">Determines how long the session stays open if the remote computer does not receive any communication from the local computer.</span></span> <span data-ttu-id="bd6a5-177">これにはハートビート信号も含まれます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-177">This includes the heartbeat signal.</span></span> <span data-ttu-id="bd6a5-178">この期間が経過すると、セッションは閉じられます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-178">When the interval expires, the session closes.</span></span>

<span data-ttu-id="bd6a5-179">セッションを切断して再接続する場合、アイドルタイムアウト値は非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-179">The idle time-out value is of significant importance if you intend to disconnect and reconnect to a session.</span></span> <span data-ttu-id="bd6a5-180">セッションがタイムアウトしていない場合にのみ再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-180">You can reconnect only if the session has not timed out.</span></span>

<span data-ttu-id="bd6a5-181">値をミリ秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-181">Enter a value in milliseconds.</span></span> <span data-ttu-id="bd6a5-182">最小値は 6万 (1 分) です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-182">The minimum value is 60000 (1 minute).</span></span> <span data-ttu-id="bd6a5-183">最大値は、セッション構成の **MaxIdleTimeoutms** プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-183">The maximum is the value of the **MaxIdleTimeoutms** property of the session configuration.</span></span> <span data-ttu-id="bd6a5-184">既定値の-1 では、アイドルタイムアウトは設定されません。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-184">The default value, -1, does not set an idle time-out.</span></span>

<span data-ttu-id="bd6a5-185">セッションでは、セッションオプションで設定されているアイドルタイムアウトを使用します (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-185">The session uses the idle time-out that is set in the session options, if any.</span></span> <span data-ttu-id="bd6a5-186">何も設定されていない場合 (-1)、セッション構成の **IdleTimeoutMs** プロパティの値、または WSMan シェルのタイムアウト値 ( `WSMan:\<ComputerName>\Shell\IdleTimeout` ) のいずれか短い方が使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-186">If none is set (-1), the session uses the value of the **IdleTimeoutMs** property of the session configuration or the WSMan shell time-out value (`WSMan:\<ComputerName>\Shell\IdleTimeout`), whichever is shortest.</span></span>

<span data-ttu-id="bd6a5-187">セッション オプションに設定されたアイドル タイムアウトがセッション構成の **MaxIdleTimeoutMs** プロパティの値を超える場合、セッション作成するコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-187">If the idle timeout set in the session options exceeds the value of the **MaxIdleTimeoutMs** property of the session configuration, the command to create a session fails.</span></span>

<span data-ttu-id="bd6a5-188">**IdleTimeoutMs** **の既定の** セッション構成の値は720万ミリ秒 (2 時間) です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-188">The **IdleTimeoutMs** value of the default **Microsoft.PowerShell** session configuration is 7200000 milliseconds (2 hours).</span></span> <span data-ttu-id="bd6a5-189">**MaxIdleTimeoutMs** 値は2147483647ミリ秒 ( \> 24 日) です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-189">Its **MaxIdleTimeoutMs** value is 2147483647 milliseconds (\>24 days).</span></span> <span data-ttu-id="bd6a5-190">WSMan シェルのアイドルタイムアウト () の既定値 `WSMan:\<ComputerName>\Shell\IdleTimeout` は720万ミリ秒 (2 時間) です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-190">The default value of the WSMan shell idle time-out (`WSMan:\<ComputerName>\Shell\IdleTimeout`) is 7200000 milliseconds (2 hours).</span></span>

<span data-ttu-id="bd6a5-191">セッションのアイドルタイムアウト値は、セッションから切断するときや、セッションに再接続するときに変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-191">The idle time-out value of a session can also be changed when disconnecting from a session or reconnecting to a session.</span></span> <span data-ttu-id="bd6a5-192">詳細については、次のトピックを参照してください。 `Disconnect-PSSession` および `Connect-PSSession`</span><span class="sxs-lookup"><span data-stu-id="bd6a5-192">For more information, see `Disconnect-PSSession` and `Connect-PSSession`.</span></span>

<span data-ttu-id="bd6a5-193">Windows PowerShell 2.0 では、**IdleTimeout** パラメーターの既定値は 240,000 (4 分) です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-193">In Windows PowerShell 2.0, the default value of the **IdleTimeout** parameter is 240000 (4 minutes).</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: IdleTimeoutMSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-194">-IncludePortInSPN</span><span class="sxs-lookup"><span data-stu-id="bd6a5-194">-IncludePortInSPN</span></span>

<span data-ttu-id="bd6a5-195">Kerberos 認証に使用されるサービスプリンシパル名 (SPN) のポート番号が含まれます。たとえば、のように `HTTP://<ComputerName>:5985` なります。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-195">Includes the port number in the Service Principal Name (SPN) used for Kerberos authentication, for example, `HTTP://<ComputerName>:5985`.</span></span> <span data-ttu-id="bd6a5-196">このオプションを使用すると、クライアントは、既定以外の SPN を使用して、Kerberos 認証を使用するリモート コンピューターに対して認証できます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-196">This option allows a client that uses a non-default SPN to authenticate against a remote computer that uses Kerberos authentication.</span></span>

<span data-ttu-id="bd6a5-197">このオプションは、Kerberos 認証をサポートする複数のサービスが異なるユーザー アカウントで実行されている企業向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-197">The option is designed for enterprises where multiple services that support Kerberos authentication are running under different user accounts.</span></span> <span data-ttu-id="bd6a5-198">たとえば、Kerberos 認証を許可する IIS アプリケーションでは、既定の SPN をコンピューターアカウントとは異なるユーザーアカウントに登録する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-198">For example, an IIS application that allows for Kerberos authentication can require the default SPN to be registered to a user account that differs from the computer account.</span></span> <span data-ttu-id="bd6a5-199">このような場合、PowerShell リモート処理では、コンピューターアカウントに登録されている SPN が必要であるため、認証に Kerberos を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-199">In such cases, PowerShell remoting cannot use Kerberos to authenticate because it requires an SPN that is registered to the computer account.</span></span> <span data-ttu-id="bd6a5-200">この問題を解決するには、管理者は、さまざまなユーザーアカウントに登録されていて、SPN にポート番号を含めることによって異なる Spn を作成できます ( **Setspn.exe** を使用するなど)。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-200">To resolve this problem, administrators can create different SPNs, such as by using **Setspn.exe**, that are registered to different user accounts and can distinguish between them by including the port number in the SPN.</span></span>

<span data-ttu-id="bd6a5-201">詳細については、「 [Setspn の概要](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-201">For more information, see [Setspn Overview](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10)).</span></span>

<span data-ttu-id="bd6a5-202">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-202">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="bd6a5-203">-MaxConnectionRetryCount</span><span class="sxs-lookup"><span data-stu-id="bd6a5-203">-MaxConnectionRetryCount</span></span>

<span data-ttu-id="bd6a5-204">現在の試行がネットワークの問題のために失敗した場合に、PowerShell が対象コンピューターへの接続を試行する回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-204">Specifies the number of times that PowerShell attempts to make a connection to a target machine if the current attempt fails due to network issues.</span></span> <span data-ttu-id="bd6a5-205">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-205">The default value is 5.</span></span>

<span data-ttu-id="bd6a5-206">このパラメーターは、PowerShell バージョン5.0 用に追加されました。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-206">This parameter was added for PowerShell version 5.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-207">-MaximumReceivedDataSizePerCommand</span><span class="sxs-lookup"><span data-stu-id="bd6a5-207">-MaximumReceivedDataSizePerCommand</span></span>

<span data-ttu-id="bd6a5-208">ローカル コンピューターがリモート コンピューターから 1 つのコマンドで受け取ることができる最大バイト数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-208">Specifies the maximum number of bytes that the local computer can receive from the remote computer in a single command.</span></span> <span data-ttu-id="bd6a5-209">値をバイト単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-209">Enter a value in bytes.</span></span> <span data-ttu-id="bd6a5-210">既定では、データのサイズに関する制限はありません。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-210">By default, there is no data size limit.</span></span>

<span data-ttu-id="bd6a5-211">このオプションは、クライアント コンピューター上のリソースを保護するために用意されています。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-211">This option is designed to protect the resources on the client computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-212">-MaximumReceivedObjectSize</span><span class="sxs-lookup"><span data-stu-id="bd6a5-212">-MaximumReceivedObjectSize</span></span>

<span data-ttu-id="bd6a5-213">ローカル コンピューターがリモート コンピューターから受信できるオブジェクトの最大サイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-213">Specifies the maximum size of an object that the local computer can receive from the remote computer.</span></span> <span data-ttu-id="bd6a5-214">このオプションは、クライアント コンピューター上のリソースを保護するために用意されています。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-214">This option is designed to protect the resources on the client computer.</span></span> <span data-ttu-id="bd6a5-215">値をバイト単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-215">Enter a value in bytes.</span></span>

<span data-ttu-id="bd6a5-216">Windows PowerShell 2.0 では、このパラメーターを省略した場合、オブジェクトのサイズに関する制限はありません。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-216">In Windows PowerShell 2.0, if you omit this parameter, there is no object size limit.</span></span> <span data-ttu-id="bd6a5-217">Windows PowerShell 3.0 以降では、このパラメーターを省略した場合、既定値は 200 MB です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-217">Beginning in Windows PowerShell 3.0, if you omit this parameter, the default value is 200 MB.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 200 MB
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-218">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="bd6a5-218">-MaximumRedirection</span></span>

<span data-ttu-id="bd6a5-219">接続に失敗する前に PowerShell が代替 Uniform Resource Identifier (URI) に接続をリダイレクトする回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-219">Determines how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="bd6a5-220">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-220">The default value is 5.</span></span> <span data-ttu-id="bd6a5-221">値 0 (ゼロ) を指定した場合、リダイレクトはまったく行われません。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-221">A value of 0 (zero) prevents all redirection.</span></span>

<span data-ttu-id="bd6a5-222">このオプションは、セッションを作成するコマンドで **Allowredirection** パラメーターが使用されている場合にのみ、セッションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-222">This option is used in the session only when the **AllowRedirection** parameter is used in the command that creates the session.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: 5
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-223">-NoCompression</span><span class="sxs-lookup"><span data-stu-id="bd6a5-223">-NoCompression</span></span>

<span data-ttu-id="bd6a5-224">セッションでのパケットの圧縮を無効にします。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-224">Turns off packet compression in the session.</span></span> <span data-ttu-id="bd6a5-225">圧縮処理には多くのプロセッサ サイクルが使用されますが、転送が高速化されます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-225">Compression uses more processor cycles, but it makes transmission faster.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-226">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="bd6a5-226">-NoEncryption</span></span>

<span data-ttu-id="bd6a5-227">データの暗号化を無効にします。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-227">Turns off data encryption.</span></span>

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

### <span data-ttu-id="bd6a5-228">-NoMachineProfile</span><span class="sxs-lookup"><span data-stu-id="bd6a5-228">-NoMachineProfile</span></span>

<span data-ttu-id="bd6a5-229">ユーザーの Windows ユーザー プロファイルを読み込まないようにします。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-229">Prevents loading the user's Windows user profile.</span></span> <span data-ttu-id="bd6a5-230">その場合、セッションをより高速に作成できる可能性がありますが、ユーザー固有のレジストリ設定、環境変数などの項目、および証明書をセッションで使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-230">As a result, the session might be created faster, but user-specific registry settings, items such as environment variables, and certificates are not available in the session.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-231">-OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="bd6a5-231">-OpenTimeout</span></span>

<span data-ttu-id="bd6a5-232">セッションの接続が確立されるのをクライアント コンピューターが待機する期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-232">Determines how long the client computer waits for the session connection to be established.</span></span> <span data-ttu-id="bd6a5-233">この期間が経過すると、接続を確立するコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-233">When the interval expires, the command to establish the connection fails.</span></span> <span data-ttu-id="bd6a5-234">値をミリ秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-234">Enter a value in milliseconds.</span></span>

<span data-ttu-id="bd6a5-235">既定値は 180,000 (3 分) です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-235">The default value is 180000 (3 minutes).</span></span> <span data-ttu-id="bd6a5-236">値 0 (ゼロ) は、タイムアウトがないことを表します。つまり、コマンドは無期限に続行されます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-236">A value of 0 (zero) means no time-out; the command continues indefinitely.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OpenTimeoutMSec

Required: False
Position: Named
Default value: 180000 (3 minutes)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-237">-OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="bd6a5-237">-OperationTimeout</span></span>

<span data-ttu-id="bd6a5-238">セッションの任意の操作を実行できる最大時間を決定します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-238">Determines the maximum time that any operation in the session can run.</span></span> <span data-ttu-id="bd6a5-239">この期間が経過すると、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-239">When the interval expires, the operation fails.</span></span> <span data-ttu-id="bd6a5-240">値をミリ秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-240">Enter a value in milliseconds.</span></span>

<span data-ttu-id="bd6a5-241">既定値は 180,000 (3 分) です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-241">The default value is 180000 (3 minutes).</span></span> <span data-ttu-id="bd6a5-242">値 0 (ゼロ) は、タイムアウトがないことを表します。つまり、操作は無期限に続行されます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-242">A value of 0 (zero) means no time-out; the operation continues indefinitely.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: OperationTimeoutMSec

Required: False
Position: Named
Default value: 180000 (3 minutes)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-243">-OutputBufferingMode</span><span class="sxs-lookup"><span data-stu-id="bd6a5-243">-OutputBufferingMode</span></span>

<span data-ttu-id="bd6a5-244">出力バッファーがいっぱいになったときに切断されたセッションでコマンドの出力を管理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-244">Determines how command output is managed in disconnected sessions when the output buffer becomes full.</span></span>

<span data-ttu-id="bd6a5-245">出力バッファー モードがセッションまたはセッション構成で設定されていない場合、既定値は **Block** です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-245">If the output buffering mode is not set in the session or in the session configuration, the default value is **Block**.</span></span> <span data-ttu-id="bd6a5-246">ユーザーは、セッションの切断時に出力バッファー モードを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-246">Users can also change the output buffering mode when disconnecting the session.</span></span>

<span data-ttu-id="bd6a5-247">このパラメーターを省略した場合、セッションオプションオブジェクトの **OutputBufferingMode** の値は None になります。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-247">If you omit this parameter, the value of the **OutputBufferingMode** of the session option object is None.</span></span> <span data-ttu-id="bd6a5-248">値 **Block** または **Drop** は、セッション構成に設定された出力バッファー モード トランスポート オプションをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-248">A value of **Block** or **Drop** overrides the output buffering mode transport option set in the session configuration.</span></span> <span data-ttu-id="bd6a5-249">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-249">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bd6a5-250">ブロック。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-250">Block.</span></span> <span data-ttu-id="bd6a5-251">出力バッファーがいっぱいのとき、バッファーが空くまで実行が中断されます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-251">When the output buffer is full, execution is suspended until the buffer is clear.</span></span>
- <span data-ttu-id="bd6a5-252">Drop : </span><span class="sxs-lookup"><span data-stu-id="bd6a5-252">Drop.</span></span> <span data-ttu-id="bd6a5-253">出力バッファーがいっぱいのとき、実行は続行されます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-253">When the output buffer is full, execution continues.</span></span> <span data-ttu-id="bd6a5-254">新しい出力が保存されると、最も古い出力が破棄されます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-254">As new output is saved, the oldest output is discarded.</span></span>
- <span data-ttu-id="bd6a5-255">[なし] :</span><span class="sxs-lookup"><span data-stu-id="bd6a5-255">None.</span></span> <span data-ttu-id="bd6a5-256">出力バッファー モードが指定されません。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-256">No output buffering mode is specified.</span></span>

<span data-ttu-id="bd6a5-257">出力バッファーモードトランスポートオプションの詳細については、「」を参照してください `New-PSTransportOption` 。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-257">For more information about the output buffering mode transport option, see `New-PSTransportOption`.</span></span>

<span data-ttu-id="bd6a5-258">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-258">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.OutputBufferingMode
Parameter Sets: (All)
Aliases:
Accepted values: None, Drop, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-259">-System.management.automation.remoting.proxyaccesstype</span><span class="sxs-lookup"><span data-stu-id="bd6a5-259">-ProxyAccessType</span></span>

<span data-ttu-id="bd6a5-260">ホスト名の解決に使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-260">Determines which mechanism is used to resolve the host name.</span></span> <span data-ttu-id="bd6a5-261">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-261">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="bd6a5-262">IEConfig</span><span class="sxs-lookup"><span data-stu-id="bd6a5-262">IEConfig</span></span>
- <span data-ttu-id="bd6a5-263">WinHttpConfig</span><span class="sxs-lookup"><span data-stu-id="bd6a5-263">WinHttpConfig</span></span>
- <span data-ttu-id="bd6a5-264">AutoDetect</span><span class="sxs-lookup"><span data-stu-id="bd6a5-264">AutoDetect</span></span>
- <span data-ttu-id="bd6a5-265">NoProxyServer</span><span class="sxs-lookup"><span data-stu-id="bd6a5-265">NoProxyServer</span></span>
- <span data-ttu-id="bd6a5-266">なし</span><span class="sxs-lookup"><span data-stu-id="bd6a5-266">None</span></span>

<span data-ttu-id="bd6a5-267">既定値は None です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-267">The default value is None.</span></span>

<span data-ttu-id="bd6a5-268">このパラメーターの値の詳細については、「 [System.management.automation.remoting.proxyaccesstype Enumeration](/dotnet/api/system.management.automation.remoting.proxyaccesstype)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-268">For information about the values of this parameter, see [ProxyAccessType Enumeration](/dotnet/api/system.management.automation.remoting.proxyaccesstype).</span></span>

```yaml
Type: System.Management.Automation.Remoting.ProxyAccessType
Parameter Sets: (All)
Aliases:
Accepted values: None, IEConfig, WinHttpConfig, AutoDetect, NoProxyServer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-269">-ProxyAuthentication</span><span class="sxs-lookup"><span data-stu-id="bd6a5-269">-ProxyAuthentication</span></span>

<span data-ttu-id="bd6a5-270">プロキシの解決に使用する認証方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-270">Specifies the authentication method that is used for proxy resolution.</span></span> <span data-ttu-id="bd6a5-271">このパラメーターに指定できる値は、 **Basic**、 **Digest**、および **Negotiate** です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-271">The acceptable values for this parameter are: **Basic**, **Digest**, and **Negotiate**.</span></span> <span data-ttu-id="bd6a5-272">既定値は **Negotiate** です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-272">The default value is **Negotiate**.</span></span>

<span data-ttu-id="bd6a5-273">このパラメーターの値の詳細については、「 [Authenticationmechanism 列挙型](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-273">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

```yaml
Type: System.Management.Automation.Runspaces.AuthenticationMechanism
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: Negotiate
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-274">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="bd6a5-274">-ProxyCredential</span></span>

<span data-ttu-id="bd6a5-275">プロキシ認証に使用する資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-275">Specifies the credentials to use for proxy authentication.</span></span> <span data-ttu-id="bd6a5-276">**Pscredential** オブジェクトを含む変数、またはコマンドなどの **pscredential** オブジェクトを取得するコマンドを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-276">Enter a variable that contains a **PSCredential** object or a command that gets a **PSCredential** object, such as a `Get-Credential` command.</span></span> <span data-ttu-id="bd6a5-277">このオプションを設定しない場合、資格情報は指定されません。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-277">If this option is not set, no credentials are specified.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-278">-SkipCACheck</span><span class="sxs-lookup"><span data-stu-id="bd6a5-278">-SkipCACheck</span></span>

<span data-ttu-id="bd6a5-279">HTTPS 経由で接続する場合、クライアントは、サーバー証明書が信頼された証明機関 (CA) によって署名されているかどうかを検証しません。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-279">Specifies that when it connects over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>

<span data-ttu-id="bd6a5-280">このオプションは、リモート コンピューターが別のメカニズムを使用して信頼されている場合にのみ使用します。たとえば、リモート コンピューターが物理的に安全であり切り離されているネットワークの一部である場合や、WinRM 構成において信頼されるホストとして記載されている場合が該当します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-280">Use this option only when the remote computer is trusted by using another mechanism, such as when the remote computer is part of a network that is physically secure and isolated or when the remote computer is listed as a trusted host in a WinRM configuration.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-281">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="bd6a5-281">-SkipCNCheck</span></span>

<span data-ttu-id="bd6a5-282">サーバーの証明書の共通名 (CN) がサーバーのホスト名と一致する必要がないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-282">Specifies that the certificate common name (CN) of the server does not have to match the host name of the server.</span></span> <span data-ttu-id="bd6a5-283">このオプションは、HTTPS プロトコルを使用するリモート操作でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-283">This option is used only in remote operations that use the HTTPS protocol.</span></span>

<span data-ttu-id="bd6a5-284">このオプションは、信頼されるコンピューターに対してのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-284">Use this option only for trusted computers.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-285">-SkipRevocationCheck</span><span class="sxs-lookup"><span data-stu-id="bd6a5-285">-SkipRevocationCheck</span></span>

<span data-ttu-id="bd6a5-286">サーバー証明書の失効状態を検証しません。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-286">Does not validate the revocation status of the server certificate.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-287">-UICulture</span><span class="sxs-lookup"><span data-stu-id="bd6a5-287">-UICulture</span></span>

<span data-ttu-id="bd6a5-288">セッションに使用する UI カルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-288">Specifies the UI culture to use for the session.</span></span>

<span data-ttu-id="bd6a5-289">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-289">Valid values include:</span></span>

- <span data-ttu-id="bd6a5-290">形式のカルチャ名 `<languagecode2>-<country/regioncode2>` (など) `ja-JP`</span><span class="sxs-lookup"><span data-stu-id="bd6a5-290">A culture name in `<languagecode2>-<country/regioncode2>` format, such as `ja-JP`</span></span>
- <span data-ttu-id="bd6a5-291">**CultureInfo** オブジェクトを含む変数</span><span class="sxs-lookup"><span data-stu-id="bd6a5-291">A variable that contains a **CultureInfo** object</span></span>
- <span data-ttu-id="bd6a5-292">**CultureInfo** オブジェクトを取得するコマンド (`Get-Culture`</span><span class="sxs-lookup"><span data-stu-id="bd6a5-292">A command that gets a **CultureInfo** object, such as `Get-Culture`</span></span>

<span data-ttu-id="bd6a5-293">既定値は `$null` で、セッションの作成時にオペレーティングシステムで設定された UI カルチャがセッションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-293">The default value is `$null`, and the UI culture that is set in the operating system when the session is created is used in the session.</span></span>

```yaml
Type: System.Globalization.CultureInfo
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="bd6a5-294">-UseUTF16</span><span class="sxs-lookup"><span data-stu-id="bd6a5-294">-UseUTF16</span></span>

<span data-ttu-id="bd6a5-295">このコマンドレットが、要求を UTF8 形式ではなく UTF16 形式でエンコードすることを示します。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-295">Indicates that this cmdlet encodes the request in UTF16 format instead of UTF8 format.</span></span>

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

### <span data-ttu-id="bd6a5-296">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="bd6a5-296">CommonParameters</span></span>

<span data-ttu-id="bd6a5-297">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-297">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bd6a5-298">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-298">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bd6a5-299">入力</span><span class="sxs-lookup"><span data-stu-id="bd6a5-299">INPUTS</span></span>

### <span data-ttu-id="bd6a5-300">なし</span><span class="sxs-lookup"><span data-stu-id="bd6a5-300">None</span></span>

<span data-ttu-id="bd6a5-301">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-301">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="bd6a5-302">出力</span><span class="sxs-lookup"><span data-stu-id="bd6a5-302">OUTPUTS</span></span>

### <span data-ttu-id="bd6a5-303">システムの管理.... PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="bd6a5-303">System.Management.Automation.Remoting.PSSessionOption</span></span>

## <span data-ttu-id="bd6a5-304">注</span><span class="sxs-lookup"><span data-stu-id="bd6a5-304">NOTES</span></span>

<span data-ttu-id="bd6a5-305">**PSSession** を作成するためにコマンドで **sessionoption** パラメーターを使用しない場合、セッションオプションは、設定されている場合は、ユーザー設定変数のプロパティ値によって決まり `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-305">If the **SessionOption** parameter is not used in a command to create a **PSSession**, the session options are determined by the property values of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="bd6a5-306">変数の詳細については `$PSSessionOption` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-306">For more information about the `$PSSessionOption` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="bd6a5-307">セッション構成オブジェクトのプロパティは、セッション構成に設定されているオプションとその値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-307">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="bd6a5-308">また、セッション構成ファイルを使用するセッション構成には追加のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="bd6a5-308">Also, session configurations that use a session configuration file have additional properties.</span></span>

## <span data-ttu-id="bd6a5-309">関連リンク</span><span class="sxs-lookup"><span data-stu-id="bd6a5-309">RELATED LINKS</span></span>

[<span data-ttu-id="bd6a5-310">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="bd6a5-310">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="bd6a5-311">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="bd6a5-311">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="bd6a5-312">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="bd6a5-312">New-PSSession</span></span>](New-PSSession.md)
