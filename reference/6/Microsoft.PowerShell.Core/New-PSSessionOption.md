---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 02/07/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionoption?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionOption
ms.openlocfilehash: 10f086c3fc2090681f669d481eb880d81ea9d245
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216408"
---
# <span data-ttu-id="f3f59-103">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="f3f59-103">New-PSSessionOption</span></span>

## <span data-ttu-id="f3f59-104">概要</span><span class="sxs-lookup"><span data-stu-id="f3f59-104">SYNOPSIS</span></span>
<span data-ttu-id="f3f59-105">PSSession の詳細設定オプションが格納されたオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-105">Creates an object that contains advanced options for a PSSession.</span></span>

## <span data-ttu-id="f3f59-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f3f59-106">SYNTAX</span></span>

```
New-PSSessionOption [-MaximumRedirection <Int32>] [-NoCompression] [-NoMachineProfile] [-Culture <CultureInfo>]
 [-UICulture <CultureInfo>] [-MaximumReceivedDataSizePerCommand <Int32>] [-MaximumReceivedObjectSize <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [-MaxConnectionRetryCount <Int32>]
 [-ApplicationArguments <PSPrimitiveDictionary>] [-OpenTimeout <Int32>] [-CancelTimeout <Int32>]
 [-IdleTimeout <Int32>] [-ProxyAccessType <ProxyAccessType>] [-ProxyAuthentication <AuthenticationMechanism>]
 [-ProxyCredential <PSCredential>] [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck]
 [-OperationTimeout <Int32>] [-NoEncryption] [-UseUTF16] [-IncludePortInSPN] [<CommonParameters>]
```

## <span data-ttu-id="f3f59-107">Description</span><span class="sxs-lookup"><span data-stu-id="f3f59-107">DESCRIPTION</span></span>

<span data-ttu-id="f3f59-108">`New-PSSessionOption`コマンドレットにより、ユーザー管理セッション ( **PSSession** ) の詳細オプションを含むオブジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-108">The `New-PSSessionOption` cmdlet creates an object that contains advanced options for a user-managed session ( **PSSession** ).</span></span> <span data-ttu-id="f3f59-109">オブジェクトは、、、などの **PSSession** を作成するコマンドレットの **sessionoption** パラメーターの値として使用でき `New-PSSession` `Enter-PSSession` `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-109">You can use the object as the value of the **SessionOption** parameter of cmdlets that create a **PSSession** , such as `New-PSSession`, `Enter-PSSession`, and `Invoke-Command`.</span></span>

<span data-ttu-id="f3f59-110">パラメーターを指定しない場合は、 `New-PSSessionOption` すべてのオプションの既定値を含むオブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-110">Without parameters, `New-PSSessionOption` generates an object that contains the default values for all of the options.</span></span> <span data-ttu-id="f3f59-111">プロパティはすべて編集できるため、結果のオブジェクトをテンプレートとして使用して、会社用の標準的なオプション オブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-111">Because all of the properties can be edited, you can use the resulting object as a template, and create standard option objects for your enterprise.</span></span>

<span data-ttu-id="f3f59-112">セッションオプションオブジェクトは、ユーザー設定変数に保存することもでき `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-112">You can also save a session option object in the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="f3f59-113">この変数の値は、セッション オプションの新しい既定値を確立します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-113">The values of this variable establish new default values for the session options.</span></span> <span data-ttu-id="f3f59-114">これらの値は、セッションに対してセッション オプションが設定されていない場合に有効になり、セッション構成に設定されたオプションよりも優先されます。ただし、セッション オプションを指定するか、セッションを作成するコマンドレットでセッション オプション オブジェクトを作成することによって、これらの値をオーバーライドすることができます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-114">They effective when no session options are set for the session and they take precedence over options set in the session configuration, but you can override them by specifying session options or a session option object in a cmdlet that creates a session.</span></span> <span data-ttu-id="f3f59-115">ユーザー設定変数の詳細については `$PSSessionOption` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3f59-115">For more information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="f3f59-116">セッションを作成するコマンドレットでセッション オプション オブジェクトを使用すると、セッション オプション値は、$PSSessionOption ユーザー設定変数およびセッション構成に設定されたセッションの既定値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-116">When you use a session option object in a cmdlet that creates a session, the session option values take precedence over default values for sessions set in the $PSSessionOption preference variable and in the session configuration.</span></span> <span data-ttu-id="f3f59-117">ただし、セッション構成で設定された最大値、クォータ、または制限よりも優先されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f3f59-117">However, they do not take precedence over maximum values, quotas or limits set in the session configuration.</span></span> <span data-ttu-id="f3f59-118">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3f59-118">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

## <span data-ttu-id="f3f59-119">例</span><span class="sxs-lookup"><span data-stu-id="f3f59-119">EXAMPLES</span></span>

### <span data-ttu-id="f3f59-120">例 1: 既定のセッションオプションを作成する</span><span class="sxs-lookup"><span data-stu-id="f3f59-120">Example 1: Create a default session option</span></span>

<span data-ttu-id="f3f59-121">このコマンドは、既定値をすべて持つセッションオプションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-121">This command creates a session option object that has all of the default values.</span></span>

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

### <span data-ttu-id="f3f59-122">例 2: セッションオプションオブジェクトを使用してセッションを構成する</span><span class="sxs-lookup"><span data-stu-id="f3f59-122">Example 2: Configure a session by using a session option object</span></span>

<span data-ttu-id="f3f59-123">この例では、セッション オプション オブジェクトを使用してセッションを構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-123">This example shows how to use a session option object to configure a session.</span></span>

```powershell
$pso = New-PSSessionOption -Culture "fr-fr" -MaximumReceivedObjectSize 10MB
New-PSSession -ComputerName Server01 -SessionOption $pso
```

<span data-ttu-id="f3f59-124">最初のコマンドは、新しいセッションオプションオブジェクトを作成し、変数の値に保存し `$pso` ます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-124">The first command creates a new session option object and saves it in the value of the `$pso` variable.</span></span> <span data-ttu-id="f3f59-125">2番目のコマンドは、コマンドレットを使用して、 `New-PSSession` Server01 リモートコンピューター上にセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-125">The second command uses the `New-PSSession` cmdlet to create a session on the Server01 remote computer.</span></span> <span data-ttu-id="f3f59-126">このコマンドは、変数の値に含まれる session option オブジェクトを、 `$pso` コマンドの **sessionoption** パラメーターの値として使用します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-126">The command uses the session option object in the value of the `$pso` variable as the value of the **SessionOption** parameter of the command.</span></span>

### <span data-ttu-id="f3f59-127">例 3: 対話型セッションを開始する</span><span class="sxs-lookup"><span data-stu-id="f3f59-127">Example 3: Start an interactive session</span></span>

<span data-ttu-id="f3f59-128">このコマンドは、 `Enter-PSSession` コマンドレットを使用して、Server01 コンピューターとの対話型セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-128">This command uses the `Enter-PSSession` cmdlet to start an interactive session with the Server01 computer.</span></span>

```powershell
Enter-PSSession -ComputerName Server01 -SessionOption (New-PSSessionOption -NoEncryption -NoCompression)
```

<span data-ttu-id="f3f59-129">**Sessionoption** パラメーターの値は、 `New-PSSessionOption` **Noencryption** および **noencryption** パラメーターを持つコマンドです。</span><span class="sxs-lookup"><span data-stu-id="f3f59-129">The value of the **SessionOption** parameter is a `New-PSSessionOption` command that has the **NoEncryption** and **NoCompression** parameters.</span></span>

<span data-ttu-id="f3f59-130">コマンドは、 `New-PSSessionOption` コマンドの前に実行されるように、かっこで囲まれてい `Enter-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-130">The `New-PSSessionOption` command is enclosed in parentheses to make sure that it runs before the `Enter-PSSession` command.</span></span>

### <span data-ttu-id="f3f59-131">例 4: セッションオプションオブジェクトを変更する</span><span class="sxs-lookup"><span data-stu-id="f3f59-131">Example 4: Modify a session option object</span></span>

<span data-ttu-id="f3f59-132">この例は、セッションオプションオブジェクトを変更できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="f3f59-132">This example demonstrates that you can modify the session option object.</span></span> <span data-ttu-id="f3f59-133">すべてのプロパティは、読み取り/書き込み値を持ちます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-133">All properties have read/write values.</span></span>

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

<span data-ttu-id="f3f59-134">この方法を使用して、会社の標準のセッション オブジェクトを作成し、特定の用途向けにカスタマイズされたバージョンを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-134">Use this method to create a standard session object for your enterprise, and then create customized versions of it for particular uses.</span></span>

### <span data-ttu-id="f3f59-135">例 5: ユーザー設定変数を作成する</span><span class="sxs-lookup"><span data-stu-id="f3f59-135">Example 5: Create a preference variable</span></span>

<span data-ttu-id="f3f59-136">このコマンドは、ユーザー設定変数を作成し `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-136">This command creates a `$PSSessionOption` preference variable.</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -OpenTimeOut 120000
```

<span data-ttu-id="f3f59-137">`$PSSessionOption`セッションでユーザー設定変数が発生すると、 `New-PSSession` 、 `Enter-PSSession` 、およびコマンドレットを使用して作成されたセッションのオプションの既定値が確立され `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-137">When the `$PSSessionOption` preference variable occurs in the session, it establishes default values for options in the sessions that are created by using the `New-PSSession`, `Enter-PSSession`, and `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="f3f59-138">`$PSSessionOption`変数をすべてのセッションで使用できるようにするには、powershell セッションと powershell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-138">To make the `$PSSessionOption` variable available in all sessions, add it to your PowerShell session and to your PowerShell profile.</span></span>

<span data-ttu-id="f3f59-139">ユーザー設定変数の詳細については `$PSSessionOption` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3f59-139">For more information about the `$PSSessionOption` preference variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>
<span data-ttu-id="f3f59-140">プロファイルの詳細については、「[about_Profiles](About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3f59-140">For more information about profiles, see [about_Profiles](About/about_Profiles.md).</span></span>

### <span data-ttu-id="f3f59-141">例 6: リモートセッション構成の要件を満たす</span><span class="sxs-lookup"><span data-stu-id="f3f59-141">Example 6: Fulfill the requirements for a remote session configuration</span></span>

<span data-ttu-id="f3f59-142">この例では、 **SessionOption** オブジェクトを使用してリモート セッション構成の要件を満たす方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-142">This example shows how to use a **SessionOption** object to fulfill the requirements for a remote session configuration.</span></span>

```powershell
$skipCN = New-PSSessionOption -SkipCNCheck
New-PSSession -ComputerName 171.09.21.207 -UseSSL -Credential Domain01\User01 -SessionOption $SkipCN
```

<span data-ttu-id="f3f59-143">最初のコマンドは、 `New-PSSessionOption` コマンドレットを使用して、 **Skipcncheck** プロパティを持つセッションオプションオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-143">The first command uses the `New-PSSessionOption` cmdlet to create a session option object that has the **SkipCNCheck** property.</span></span> <span data-ttu-id="f3f59-144">このコマンドは、結果として得られるセッションオブジェクトを変数に保存し `$skipCN` ます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-144">The command saves the resulting session object in the `$skipCN` variable.</span></span>

<span data-ttu-id="f3f59-145">2番目のコマンドは、コマンドレットを使用して、 `New-PSSession` リモートコンピューター上に新しいセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-145">The second command uses the `New-PSSession` cmdlet to create a new session on a remote computer.</span></span> <span data-ttu-id="f3f59-146">`$skipCN`Check 変数は、 **sessionoption** パラメーターの値で使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-146">The `$skipCN` check variable is used in the value of the **SessionOption** parameter.</span></span>

<span data-ttu-id="f3f59-147">コンピューターは IP アドレスによって識別されるので、 **ComputerName** パラメーターの値は、SECURE SOCKETS LAYER (SSL) に使用されている証明書の共通名のいずれとも一致しません。</span><span class="sxs-lookup"><span data-stu-id="f3f59-147">Because the computer is identified by its IP address, the value of the **ComputerName** parameter does not match any of the common names in the certificate that is used for Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="f3f59-148">その結果、 **SkipCNCheck** オプションが必要になります。</span><span class="sxs-lookup"><span data-stu-id="f3f59-148">As a result, the **SkipCNCheck** option is required.</span></span>

### <span data-ttu-id="f3f59-149">例 7: リモートセッションで引数を使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="f3f59-149">Example 7: Make arguments available to a remote session</span></span>

<span data-ttu-id="f3f59-150">この例では、コマンドレットの **Applicationarguments** パラメーターを使用して `New-PSSessionOption` 、リモートセッションで追加のデータを使用できるようにする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-150">This example shows how to use the **ApplicationArguments** parameter of the `New-PSSessionOption` cmdlet to make additional data available to the remote session.</span></span>

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

<span data-ttu-id="f3f59-151">最初のコマンドは、 **チーム** と **使用** の2つのキーを持つハッシュテーブルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-151">The first command creates a hash table with two keys, **Team** and **Use** .</span></span> <span data-ttu-id="f3f59-152">このコマンドは、ハッシュテーブルを変数に保存し `$team` ます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-152">The command saves the hash table in the `$team` variable.</span></span> <span data-ttu-id="f3f59-153">ハッシュ テーブルの詳細については、「[about_Hash_Tables (ハッシュ テーブルについて)](about/about_Hash_Tables.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f3f59-153">For more information about hash tables, see [about_Hash_Tables](about/about_Hash_Tables.md).</span></span>

<span data-ttu-id="f3f59-154">次に、 `New-PSSessionOption` **applicationarguments** パラメーターを使用してコマンドレットを作成し、変数に保存されたセッションオプションオブジェクトを作成し `$team` ます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-154">Next, the `New-PSSessionOption` cmdlet, using the **ApplicationArguments** parameter, creates a session option object saved in the `$team` variable.</span></span> <span data-ttu-id="f3f59-155">`New-PSSessionOption`は、セッションオプションオブジェクトを作成するときに、 **applicationarguments** パラメーターの値のハッシュテーブルをプリミティブディクショナリに自動的に変換します。これにより、データが確実にリモートセッションに送信されるようになります。</span><span class="sxs-lookup"><span data-stu-id="f3f59-155">When `New-PSSessionOption` creates the session option object, it automatically converts the hash table in the value of the **ApplicationArguments** parameter to a primitive dictionary so the data can be reliably transmitted to the remote session.</span></span>

<span data-ttu-id="f3f59-156">`New-PSSession`コマンドレットは、Server01 コンピューターでセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-156">The `New-PSSession` cmdlet starts a session on the Server01 computer.</span></span> <span data-ttu-id="f3f59-157">この例では、 **Sessionoption** パラメーターを使用して、変数にオプションを含めて `$teamOption` います。</span><span class="sxs-lookup"><span data-stu-id="f3f59-157">It uses the **SessionOption** parameter to include the options in the `$teamOption` variable.</span></span>

<span data-ttu-id="f3f59-158">`Invoke-Command`コマンドレットでは、変数内のデータを `$team` リモートセッションのコマンドで使用できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="f3f59-158">The `Invoke-Command` cmdlet demonstrates that the data in the `$team` variable is available to commands in the remote session.</span></span> <span data-ttu-id="f3f59-159">データは、自動変数の **Applicationarguments** プロパティに表示され `$PSSenderInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-159">The data appears in the **ApplicationArguments** property of the `$PSSenderInfo` automatic variable.</span></span>

<span data-ttu-id="f3f59-160">最後に、 `Invoke-Command` データがどのように使用されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-160">The final `Invoke-Command` shows how the data might be used.</span></span>

## <span data-ttu-id="f3f59-161">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f3f59-161">PARAMETERS</span></span>

### <span data-ttu-id="f3f59-162">-ApplicationArguments</span><span class="sxs-lookup"><span data-stu-id="f3f59-162">-ApplicationArguments</span></span>

<span data-ttu-id="f3f59-163">リモート セッションに送信されるプリミティブな辞書を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-163">Specifies a primitive dictionary that is sent to the remote session.</span></span> <span data-ttu-id="f3f59-164">セッション構成のスタートアップスクリプトを含む、リモートセッションのコマンドとスクリプトは、自動変数の **Applicationarguments** プロパティでこのディクショナリを見つけることができ `$PSSenderInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-164">Commands and scripts in the remote session, including startup scripts in the session configuration, can find this dictionary in the **ApplicationArguments** property of the `$PSSenderInfo` automatic variable.</span></span> <span data-ttu-id="f3f59-165">このパラメーターを使用すると、リモート セッションにデータを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-165">You can use this parameter to send data to the remote session.</span></span>

<span data-ttu-id="f3f59-166">詳細については、「 [about_Hash_Tables](about/about_Hash_Tables.md)、 [about_Session_Configurations](About/about_Session_Configurations.md)、および [about_Automatic_Variables](about/about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3f59-166">For more information, see [about_Hash_Tables](about/about_Hash_Tables.md), [about_Session_Configurations](About/about_Session_Configurations.md), and [about_Automatic_Variables](about/about_Automatic_Variables.md).</span></span>

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

### <span data-ttu-id="f3f59-167">-CancelTimeout</span><span class="sxs-lookup"><span data-stu-id="f3f59-167">-CancelTimeout</span></span>

<span data-ttu-id="f3f59-168">PowerShell がキャンセル操作 (CTRL + C) が終了するまで待機する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-168">Determines how long PowerShell waits for a cancel operation (CTRL+C) to finish before ending it.</span></span>
<span data-ttu-id="f3f59-169">値をミリ秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-169">Enter a value in milliseconds.</span></span>

<span data-ttu-id="f3f59-170">既定値は 60,000 (1 分) です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-170">The default value is 60000 (one minute).</span></span> <span data-ttu-id="f3f59-171">値 0 (ゼロ) は、タイムアウトがないことを表します。つまり、コマンドは無期限に続行されます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-171">A value of 0 (zero) means no time-out; the command continues indefinitely.</span></span>

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

### <span data-ttu-id="f3f59-172">-Culture</span><span class="sxs-lookup"><span data-stu-id="f3f59-172">-Culture</span></span>

<span data-ttu-id="f3f59-173">セッションに使用するカルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-173">Specifies the culture to use for the session.</span></span> <span data-ttu-id="f3f59-174">カルチャ名を `<languagecode2>-<country/regioncode2>` 形式 (like など `ja-JP` )、 **cultureinfo** オブジェクトを含む変数、または **cultureinfo** オブジェクトを取得するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-174">Enter a culture name in `<languagecode2>-<country/regioncode2>` format (like `ja-JP`), a variable that contains a **CultureInfo** object, or a command that gets a **CultureInfo** object.</span></span>

<span data-ttu-id="f3f59-175">既定値はであり、 `$Null` オペレーティングシステムで設定されているカルチャがセッションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-175">The default value is `$Null`, and the culture that is set in the operating system is used in the session.</span></span>

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

### <span data-ttu-id="f3f59-176">-IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="f3f59-176">-IdleTimeout</span></span>

<span data-ttu-id="f3f59-177">リモートコンピューターがローカルコンピューターから通信を受信していない場合に、セッションが開いたままになる期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-177">Determines how long the session stays open if the remote computer does not receive any communication from the local computer.</span></span> <span data-ttu-id="f3f59-178">これにはハートビート信号も含まれます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-178">This includes the heartbeat signal.</span></span> <span data-ttu-id="f3f59-179">この期間が経過すると、セッションは閉じられます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-179">When the interval expires, the session closes.</span></span>

<span data-ttu-id="f3f59-180">セッションを切断して再接続する場合、アイドルタイムアウト値は非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-180">The idle time-out value is of significant importance if you intend to disconnect and reconnect to a session.</span></span> <span data-ttu-id="f3f59-181">セッションがタイムアウトしていない場合にのみ再接続することができます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-181">You can reconnect only if the session has not timed out.</span></span>

<span data-ttu-id="f3f59-182">値をミリ秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-182">Enter a value in milliseconds.</span></span> <span data-ttu-id="f3f59-183">最小値は 6万 (1 分) です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-183">The minimum value is 60000 (1 minute).</span></span> <span data-ttu-id="f3f59-184">最大値は、セッション構成の **MaxIdleTimeoutms** プロパティの値です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-184">The maximum is the value of the **MaxIdleTimeoutms** property of the session configuration.</span></span> <span data-ttu-id="f3f59-185">既定値の-1 では、アイドルタイムアウトは設定されません。</span><span class="sxs-lookup"><span data-stu-id="f3f59-185">The default value, -1, does not set an idle time-out.</span></span>

<span data-ttu-id="f3f59-186">セッションでは、セッションオプションで設定されているアイドルタイムアウトを使用します (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="f3f59-186">The session uses the idle time-out that is set in the session options, if any.</span></span> <span data-ttu-id="f3f59-187">何も設定されていない場合 (-1)、セッション構成の **IdleTimeoutMs** プロパティの値、または WSMan シェルのタイムアウト値 ( `WSMan:\<ComputerName>\Shell\IdleTimeout` ) のいずれか短い方が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-187">If none is set (-1), the session uses the value of the **IdleTimeoutMs** property of the session configuration or the WSMan shell time-out value (`WSMan:\<ComputerName>\Shell\IdleTimeout`), whichever is shortest.</span></span>

<span data-ttu-id="f3f59-188">セッション オプションに設定されたアイドル タイムアウトがセッション構成の **MaxIdleTimeoutMs** プロパティの値を超える場合、セッション作成するコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-188">If the idle timeout set in the session options exceeds the value of the **MaxIdleTimeoutMs** property of the session configuration, the command to create a session fails.</span></span>

<span data-ttu-id="f3f59-189">**IdleTimeoutMs** **の既定の** セッション構成の値は720万ミリ秒 (2 時間) です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-189">The **IdleTimeoutMs** value of the default **Microsoft.PowerShell** session configuration is 7200000 milliseconds (2 hours).</span></span> <span data-ttu-id="f3f59-190">**MaxIdleTimeoutMs** 値は2147483647ミリ秒 ( \> 24 日) です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-190">Its **MaxIdleTimeoutMs** value is 2147483647 milliseconds (\>24 days).</span></span> <span data-ttu-id="f3f59-191">WSMan シェルのアイドルタイムアウト () の既定値 `WSMan:\<ComputerName>\Shell\IdleTimeout` は720万ミリ秒 (2 時間) です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-191">The default value of the WSMan shell idle time-out (`WSMan:\<ComputerName>\Shell\IdleTimeout`) is 7200000 milliseconds (2 hours).</span></span>

<span data-ttu-id="f3f59-192">セッションのアイドルタイムアウト値は、セッションから切断するときや、セッションに再接続するときに変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-192">The idle time-out value of a session can also be changed when disconnecting from a session or reconnecting to a session.</span></span> <span data-ttu-id="f3f59-193">詳細については、次のトピックを参照してください。 `Disconnect-PSSession` および `Connect-PSSession`</span><span class="sxs-lookup"><span data-stu-id="f3f59-193">For more information, see `Disconnect-PSSession` and `Connect-PSSession`.</span></span>

<span data-ttu-id="f3f59-194">Windows PowerShell 2.0 では、 **IdleTimeout** パラメーターの既定値は 240,000 (4 分) です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-194">In Windows PowerShell 2.0, the default value of the **IdleTimeout** parameter is 240000 (4 minutes).</span></span>

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

### <span data-ttu-id="f3f59-195">-IncludePortInSPN</span><span class="sxs-lookup"><span data-stu-id="f3f59-195">-IncludePortInSPN</span></span>

<span data-ttu-id="f3f59-196">Kerberos 認証に使用されるサービスプリンシパル名 (SPN) のポート番号が含まれます。たとえば、のように `HTTP://<ComputerName>:5985` なります。</span><span class="sxs-lookup"><span data-stu-id="f3f59-196">Includes the port number in the Service Principal Name (SPN) used for Kerberos authentication, for example, `HTTP://<ComputerName>:5985`.</span></span> <span data-ttu-id="f3f59-197">このオプションを使用すると、クライアントは、既定以外の SPN を使用して、Kerberos 認証を使用するリモート コンピューターに対して認証できます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-197">This option allows a client that uses a non-default SPN to authenticate against a remote computer that uses Kerberos authentication.</span></span>

<span data-ttu-id="f3f59-198">このオプションは、Kerberos 認証をサポートする複数のサービスが異なるユーザー アカウントで実行されている企業向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="f3f59-198">The option is designed for enterprises where multiple services that support Kerberos authentication are running under different user accounts.</span></span> <span data-ttu-id="f3f59-199">たとえば、Kerberos 認証を許可する IIS アプリケーションでは、既定の SPN をコンピューターアカウントとは異なるユーザーアカウントに登録する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3f59-199">For example, an IIS application that allows for Kerberos authentication can require the default SPN to be registered to a user account that differs from the computer account.</span></span> <span data-ttu-id="f3f59-200">このような場合、PowerShell リモート処理では、コンピューターアカウントに登録されている SPN が必要であるため、認証に Kerberos を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f3f59-200">In such cases, PowerShell remoting cannot use Kerberos to authenticate because it requires an SPN that is registered to the computer account.</span></span> <span data-ttu-id="f3f59-201">この問題を解決するには、管理者は、さまざまなユーザーアカウントに登録されていて、SPN にポート番号を含めることによって異なる Spn を作成できます ( **Setspn.exe** を使用するなど)。</span><span class="sxs-lookup"><span data-stu-id="f3f59-201">To resolve this problem, administrators can create different SPNs, such as by using **Setspn.exe** , that are registered to different user accounts and can distinguish between them by including the port number in the SPN.</span></span>

<span data-ttu-id="f3f59-202">詳細については、「 [Setspn の概要](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3f59-202">For more information, see [Setspn Overview](/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10)).</span></span>

<span data-ttu-id="f3f59-203">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f3f59-203">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f3f59-204">-MaxConnectionRetryCount</span><span class="sxs-lookup"><span data-stu-id="f3f59-204">-MaxConnectionRetryCount</span></span>

<span data-ttu-id="f3f59-205">現在の試行がネットワークの問題のために失敗した場合に、PowerShell が対象コンピューターへの接続を試行する回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-205">Specifies the number of times that PowerShell attempts to make a connection to a target machine if the current attempt fails due to network issues.</span></span> <span data-ttu-id="f3f59-206">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-206">The default value is 5.</span></span>

<span data-ttu-id="f3f59-207">このパラメーターは、PowerShell バージョン5.0 用に追加されました。</span><span class="sxs-lookup"><span data-stu-id="f3f59-207">This parameter was added for PowerShell version 5.0.</span></span>

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

### <span data-ttu-id="f3f59-208">-MaximumReceivedDataSizePerCommand</span><span class="sxs-lookup"><span data-stu-id="f3f59-208">-MaximumReceivedDataSizePerCommand</span></span>

<span data-ttu-id="f3f59-209">ローカル コンピューターがリモート コンピューターから 1 つのコマンドで受け取ることができる最大バイト数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-209">Specifies the maximum number of bytes that the local computer can receive from the remote computer in a single command.</span></span> <span data-ttu-id="f3f59-210">値をバイト単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-210">Enter a value in bytes.</span></span> <span data-ttu-id="f3f59-211">既定では、データのサイズに関する制限はありません。</span><span class="sxs-lookup"><span data-stu-id="f3f59-211">By default, there is no data size limit.</span></span>

<span data-ttu-id="f3f59-212">このオプションは、クライアント コンピューター上のリソースを保護するために用意されています。</span><span class="sxs-lookup"><span data-stu-id="f3f59-212">This option is designed to protect the resources on the client computer.</span></span>

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

### <span data-ttu-id="f3f59-213">-MaximumReceivedObjectSize</span><span class="sxs-lookup"><span data-stu-id="f3f59-213">-MaximumReceivedObjectSize</span></span>

<span data-ttu-id="f3f59-214">ローカル コンピューターがリモート コンピューターから受信できるオブジェクトの最大サイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-214">Specifies the maximum size of an object that the local computer can receive from the remote computer.</span></span> <span data-ttu-id="f3f59-215">このオプションは、クライアント コンピューター上のリソースを保護するために用意されています。</span><span class="sxs-lookup"><span data-stu-id="f3f59-215">This option is designed to protect the resources on the client computer.</span></span> <span data-ttu-id="f3f59-216">値をバイト単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-216">Enter a value in bytes.</span></span>

<span data-ttu-id="f3f59-217">Windows PowerShell 2.0 では、このパラメーターを省略した場合、オブジェクトのサイズに関する制限はありません。</span><span class="sxs-lookup"><span data-stu-id="f3f59-217">In Windows PowerShell 2.0, if you omit this parameter, there is no object size limit.</span></span> <span data-ttu-id="f3f59-218">Windows PowerShell 3.0 以降では、このパラメーターを省略した場合、既定値は 200 MB です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-218">Beginning in Windows PowerShell 3.0, if you omit this parameter, the default value is 200 MB.</span></span>

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

### <span data-ttu-id="f3f59-219">-MaximumRedirection</span><span class="sxs-lookup"><span data-stu-id="f3f59-219">-MaximumRedirection</span></span>

<span data-ttu-id="f3f59-220">接続に失敗する前に PowerShell が代替 Uniform Resource Identifier (URI) に接続をリダイレクトする回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-220">Determines how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="f3f59-221">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-221">The default value is 5.</span></span> <span data-ttu-id="f3f59-222">値 0 (ゼロ) を指定した場合、リダイレクトはまったく行われません。</span><span class="sxs-lookup"><span data-stu-id="f3f59-222">A value of 0 (zero) prevents all redirection.</span></span>

<span data-ttu-id="f3f59-223">このオプションは、セッションを作成するコマンドで **Allowredirection** パラメーターが使用されている場合にのみ、セッションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-223">This option is used in the session only when the **AllowRedirection** parameter is used in the command that creates the session.</span></span>

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

### <span data-ttu-id="f3f59-224">-NoCompression</span><span class="sxs-lookup"><span data-stu-id="f3f59-224">-NoCompression</span></span>

<span data-ttu-id="f3f59-225">セッションでのパケットの圧縮を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f3f59-225">Turns off packet compression in the session.</span></span> <span data-ttu-id="f3f59-226">圧縮処理には多くのプロセッサ サイクルが使用されますが、転送が高速化されます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-226">Compression uses more processor cycles, but it makes transmission faster.</span></span>

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

### <span data-ttu-id="f3f59-227">-NoEncryption</span><span class="sxs-lookup"><span data-stu-id="f3f59-227">-NoEncryption</span></span>

<span data-ttu-id="f3f59-228">データの暗号化を無効にします。</span><span class="sxs-lookup"><span data-stu-id="f3f59-228">Turns off data encryption.</span></span>

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

### <span data-ttu-id="f3f59-229">-NoMachineProfile</span><span class="sxs-lookup"><span data-stu-id="f3f59-229">-NoMachineProfile</span></span>

<span data-ttu-id="f3f59-230">ユーザーの Windows ユーザー プロファイルを読み込まないようにします。</span><span class="sxs-lookup"><span data-stu-id="f3f59-230">Prevents loading the user's Windows user profile.</span></span> <span data-ttu-id="f3f59-231">その場合、セッションをより高速に作成できる可能性がありますが、ユーザー固有のレジストリ設定、環境変数などの項目、および証明書をセッションで使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="f3f59-231">As a result, the session might be created faster, but user-specific registry settings, items such as environment variables, and certificates are not available in the session.</span></span>

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

### <span data-ttu-id="f3f59-232">-OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="f3f59-232">-OpenTimeout</span></span>

<span data-ttu-id="f3f59-233">セッションの接続が確立されるのをクライアント コンピューターが待機する期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-233">Determines how long the client computer waits for the session connection to be established.</span></span> <span data-ttu-id="f3f59-234">この期間が経過すると、接続を確立するコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-234">When the interval expires, the command to establish the connection fails.</span></span> <span data-ttu-id="f3f59-235">値をミリ秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-235">Enter a value in milliseconds.</span></span>

<span data-ttu-id="f3f59-236">既定値は 180,000 (3 分) です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-236">The default value is 180000 (3 minutes).</span></span> <span data-ttu-id="f3f59-237">値 0 (ゼロ) は、タイムアウトがないことを表します。つまり、コマンドは無期限に続行されます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-237">A value of 0 (zero) means no time-out; the command continues indefinitely.</span></span>

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

### <span data-ttu-id="f3f59-238">-OperationTimeout</span><span class="sxs-lookup"><span data-stu-id="f3f59-238">-OperationTimeout</span></span>

<span data-ttu-id="f3f59-239">セッションの任意の操作を実行できる最大時間を決定します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-239">Determines the maximum time that any operation in the session can run.</span></span> <span data-ttu-id="f3f59-240">この期間が経過すると、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-240">When the interval expires, the operation fails.</span></span> <span data-ttu-id="f3f59-241">値をミリ秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-241">Enter a value in milliseconds.</span></span>

<span data-ttu-id="f3f59-242">既定値は 180,000 (3 分) です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-242">The default value is 180000 (3 minutes).</span></span> <span data-ttu-id="f3f59-243">値 0 (ゼロ) は、タイムアウトがないことを表します。つまり、操作は無期限に続行されます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-243">A value of 0 (zero) means no time-out; the operation continues indefinitely.</span></span>

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

### <span data-ttu-id="f3f59-244">-OutputBufferingMode</span><span class="sxs-lookup"><span data-stu-id="f3f59-244">-OutputBufferingMode</span></span>

<span data-ttu-id="f3f59-245">出力バッファーがいっぱいになったときに切断されたセッションでコマンドの出力を管理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-245">Determines how command output is managed in disconnected sessions when the output buffer becomes full.</span></span>

<span data-ttu-id="f3f59-246">出力バッファー モードがセッションまたはセッション構成で設定されていない場合、既定値は **Block** です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-246">If the output buffering mode is not set in the session or in the session configuration, the default value is **Block** .</span></span> <span data-ttu-id="f3f59-247">ユーザーは、セッションの切断時に出力バッファー モードを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-247">Users can also change the output buffering mode when disconnecting the session.</span></span>

<span data-ttu-id="f3f59-248">このパラメーターを省略した場合、セッションオプションオブジェクトの **OutputBufferingMode** の値は None になります。</span><span class="sxs-lookup"><span data-stu-id="f3f59-248">If you omit this parameter, the value of the **OutputBufferingMode** of the session option object is None.</span></span> <span data-ttu-id="f3f59-249">値 **Block** または **Drop** は、セッション構成に設定された出力バッファー モード トランスポート オプションをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="f3f59-249">A value of **Block** or **Drop** overrides the output buffering mode transport option set in the session configuration.</span></span> <span data-ttu-id="f3f59-250">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f3f59-250">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f3f59-251">ブロック。</span><span class="sxs-lookup"><span data-stu-id="f3f59-251">Block.</span></span> <span data-ttu-id="f3f59-252">出力バッファーがいっぱいのとき、バッファーが空くまで実行が中断されます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-252">When the output buffer is full, execution is suspended until the buffer is clear.</span></span>
- <span data-ttu-id="f3f59-253">Drop : </span><span class="sxs-lookup"><span data-stu-id="f3f59-253">Drop.</span></span> <span data-ttu-id="f3f59-254">出力バッファーがいっぱいのとき、実行は続行されます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-254">When the output buffer is full, execution continues.</span></span> <span data-ttu-id="f3f59-255">新しい出力が保存されると、最も古い出力が破棄されます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-255">As new output is saved, the oldest output is discarded.</span></span>
- <span data-ttu-id="f3f59-256">なし。</span><span class="sxs-lookup"><span data-stu-id="f3f59-256">None.</span></span> <span data-ttu-id="f3f59-257">出力バッファー モードが指定されません。</span><span class="sxs-lookup"><span data-stu-id="f3f59-257">No output buffering mode is specified.</span></span>

<span data-ttu-id="f3f59-258">出力バッファーモードトランスポートオプションの詳細については、「」を参照してください `New-PSTransportOption` 。</span><span class="sxs-lookup"><span data-stu-id="f3f59-258">For more information about the output buffering mode transport option, see `New-PSTransportOption`.</span></span>

<span data-ttu-id="f3f59-259">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f3f59-259">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="f3f59-260">-System.management.automation.remoting.proxyaccesstype</span><span class="sxs-lookup"><span data-stu-id="f3f59-260">-ProxyAccessType</span></span>

<span data-ttu-id="f3f59-261">ホスト名の解決に使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-261">Determines which mechanism is used to resolve the host name.</span></span> <span data-ttu-id="f3f59-262">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f3f59-262">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f3f59-263">IEConfig</span><span class="sxs-lookup"><span data-stu-id="f3f59-263">IEConfig</span></span>
- <span data-ttu-id="f3f59-264">WinHttpConfig</span><span class="sxs-lookup"><span data-stu-id="f3f59-264">WinHttpConfig</span></span>
- <span data-ttu-id="f3f59-265">AutoDetect</span><span class="sxs-lookup"><span data-stu-id="f3f59-265">AutoDetect</span></span>
- <span data-ttu-id="f3f59-266">NoProxyServer</span><span class="sxs-lookup"><span data-stu-id="f3f59-266">NoProxyServer</span></span>
- <span data-ttu-id="f3f59-267">なし</span><span class="sxs-lookup"><span data-stu-id="f3f59-267">None</span></span>

<span data-ttu-id="f3f59-268">既定値は None です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-268">The default value is None.</span></span>

<span data-ttu-id="f3f59-269">このパラメーターの値の詳細については、「 [System.management.automation.remoting.proxyaccesstype Enumeration](/dotnet/api/system.management.automation.remoting.proxyaccesstype?redirectedfrom=MSDN&view=powershellsdk-1.1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3f59-269">For information about the values of this parameter, see [ProxyAccessType Enumeration](/dotnet/api/system.management.automation.remoting.proxyaccesstype?redirectedfrom=MSDN&view=powershellsdk-1.1.0).</span></span>

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

### <span data-ttu-id="f3f59-270">-ProxyAuthentication</span><span class="sxs-lookup"><span data-stu-id="f3f59-270">-ProxyAuthentication</span></span>

<span data-ttu-id="f3f59-271">プロキシの解決に使用する認証方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-271">Specifies the authentication method that is used for proxy resolution.</span></span> <span data-ttu-id="f3f59-272">このパラメーターに指定できる値は、 **Basic** 、 **Digest** 、および **Negotiate** です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-272">The acceptable values for this parameter are: **Basic** , **Digest** , and **Negotiate** .</span></span> <span data-ttu-id="f3f59-273">既定値は **Negotiate** です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-273">The default value is **Negotiate** .</span></span>

<span data-ttu-id="f3f59-274">このパラメーターの値の詳細については、「 [Authenticationmechanism 列挙型](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?redirectedfrom=MSDN&view=powershellsdk-1.1.0)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3f59-274">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism?redirectedfrom=MSDN&view=powershellsdk-1.1.0).</span></span>

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

### <span data-ttu-id="f3f59-275">-ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="f3f59-275">-ProxyCredential</span></span>

<span data-ttu-id="f3f59-276">プロキシ認証に使用する資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-276">Specifies the credentials to use for proxy authentication.</span></span> <span data-ttu-id="f3f59-277">**Pscredential** オブジェクトを含む変数、またはコマンドなどの **pscredential** オブジェクトを取得するコマンドを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-277">Enter a variable that contains a **PSCredential** object or a command that gets a **PSCredential** object, such as a `Get-Credential` command.</span></span> <span data-ttu-id="f3f59-278">このオプションを設定しない場合、資格情報は指定されません。</span><span class="sxs-lookup"><span data-stu-id="f3f59-278">If this option is not set, no credentials are specified.</span></span>

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

### <span data-ttu-id="f3f59-279">-SkipCACheck</span><span class="sxs-lookup"><span data-stu-id="f3f59-279">-SkipCACheck</span></span>

<span data-ttu-id="f3f59-280">HTTPS 経由で接続する場合、クライアントは、サーバー証明書が信頼された証明機関 (CA) によって署名されているかどうかを検証しません。</span><span class="sxs-lookup"><span data-stu-id="f3f59-280">Specifies that when it connects over HTTPS, the client does not validate that the server certificate is signed by a trusted certification authority (CA).</span></span>

<span data-ttu-id="f3f59-281">このオプションは、リモート コンピューターが別のメカニズムを使用して信頼されている場合にのみ使用します。たとえば、リモート コンピューターが物理的に安全であり切り離されているネットワークの一部である場合や、WinRM 構成において信頼されるホストとして記載されている場合が該当します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-281">Use this option only when the remote computer is trusted by using another mechanism, such as when the remote computer is part of a network that is physically secure and isolated or when the remote computer is listed as a trusted host in a WinRM configuration.</span></span>

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

### <span data-ttu-id="f3f59-282">-SkipCNCheck</span><span class="sxs-lookup"><span data-stu-id="f3f59-282">-SkipCNCheck</span></span>

<span data-ttu-id="f3f59-283">サーバーの証明書の共通名 (CN) がサーバーのホスト名と一致する必要がないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-283">Specifies that the certificate common name (CN) of the server does not have to match the host name of the server.</span></span> <span data-ttu-id="f3f59-284">このオプションは、HTTPS プロトコルを使用するリモート操作でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-284">This option is used only in remote operations that use the HTTPS protocol.</span></span>

<span data-ttu-id="f3f59-285">このオプションは、信頼されるコンピューターに対してのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-285">Use this option only for trusted computers.</span></span>

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

### <span data-ttu-id="f3f59-286">-SkipRevocationCheck</span><span class="sxs-lookup"><span data-stu-id="f3f59-286">-SkipRevocationCheck</span></span>

<span data-ttu-id="f3f59-287">サーバー証明書の失効状態を検証しません。</span><span class="sxs-lookup"><span data-stu-id="f3f59-287">Does not validate the revocation status of the server certificate.</span></span>

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

### <span data-ttu-id="f3f59-288">-UICulture</span><span class="sxs-lookup"><span data-stu-id="f3f59-288">-UICulture</span></span>

<span data-ttu-id="f3f59-289">セッションに使用する UI カルチャを指定します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-289">Specifies the UI culture to use for the session.</span></span>

<span data-ttu-id="f3f59-290">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f3f59-290">Valid values include:</span></span>

- <span data-ttu-id="f3f59-291">形式のカルチャ名 `<languagecode2>-<country/regioncode2>` (など) `ja-JP`</span><span class="sxs-lookup"><span data-stu-id="f3f59-291">A culture name in `<languagecode2>-<country/regioncode2>` format, such as `ja-JP`</span></span>
- <span data-ttu-id="f3f59-292">**CultureInfo** オブジェクトを含む変数</span><span class="sxs-lookup"><span data-stu-id="f3f59-292">A variable that contains a **CultureInfo** object</span></span>
- <span data-ttu-id="f3f59-293">**CultureInfo** オブジェクトを取得するコマンド (`Get-Culture`</span><span class="sxs-lookup"><span data-stu-id="f3f59-293">A command that gets a **CultureInfo** object, such as `Get-Culture`</span></span>

<span data-ttu-id="f3f59-294">既定値は `$null` で、セッションの作成時にオペレーティングシステムで設定された UI カルチャがセッションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-294">The default value is `$null`, and the UI culture that is set in the operating system when the session is created is used in the session.</span></span>

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

### <span data-ttu-id="f3f59-295">-UseUTF16</span><span class="sxs-lookup"><span data-stu-id="f3f59-295">-UseUTF16</span></span>

<span data-ttu-id="f3f59-296">このコマンドレットが、要求を UTF8 形式ではなく UTF16 形式でエンコードすることを示します。</span><span class="sxs-lookup"><span data-stu-id="f3f59-296">Indicates that this cmdlet encodes the request in UTF16 format instead of UTF8 format.</span></span>

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

### <span data-ttu-id="f3f59-297">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f3f59-297">CommonParameters</span></span>

<span data-ttu-id="f3f59-298">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f3f59-298">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f3f59-299">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3f59-299">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f3f59-300">入力</span><span class="sxs-lookup"><span data-stu-id="f3f59-300">INPUTS</span></span>

### <span data-ttu-id="f3f59-301">なし</span><span class="sxs-lookup"><span data-stu-id="f3f59-301">None</span></span>

<span data-ttu-id="f3f59-302">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="f3f59-302">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="f3f59-303">出力</span><span class="sxs-lookup"><span data-stu-id="f3f59-303">OUTPUTS</span></span>

### <span data-ttu-id="f3f59-304">システムの管理.... PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="f3f59-304">System.Management.Automation.Remoting.PSSessionOption</span></span>

## <span data-ttu-id="f3f59-305">注</span><span class="sxs-lookup"><span data-stu-id="f3f59-305">NOTES</span></span>

<span data-ttu-id="f3f59-306">**PSSession** を作成するためにコマンドで **sessionoption** パラメーターを使用しない場合、セッションオプションは、設定されている場合は、ユーザー設定変数のプロパティ値によって決まり `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="f3f59-306">If the **SessionOption** parameter is not used in a command to create a **PSSession** , the session options are determined by the property values of the `$PSSessionOption` preference variable, if it is set.</span></span> <span data-ttu-id="f3f59-307">変数の詳細については `$PSSessionOption` 、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3f59-307">For more information about the `$PSSessionOption` variable, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="f3f59-308">セッション構成オブジェクトのプロパティは、セッション構成に設定されているオプションとその値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f3f59-308">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="f3f59-309">また、セッション構成ファイルを使用するセッション構成には追加のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="f3f59-309">Also, session configurations that use a session configuration file have additional properties.</span></span>

## <span data-ttu-id="f3f59-310">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f3f59-310">RELATED LINKS</span></span>

[<span data-ttu-id="f3f59-311">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="f3f59-311">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="f3f59-312">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="f3f59-312">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="f3f59-313">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="f3f59-313">New-PSSession</span></span>](New-PSSession.md)
