---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 6/17/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-computer?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Computer
ms.openlocfilehash: 2d5df7926ab65f45a4d56d84b1f25919bcdb8c41
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345206"
---
# <span data-ttu-id="0ccf9-103">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="0ccf9-103">Restart-Computer</span></span>

## <span data-ttu-id="0ccf9-104">概要</span><span class="sxs-lookup"><span data-stu-id="0ccf9-104">SYNOPSIS</span></span>
<span data-ttu-id="0ccf9-105">ローカルコンピューターとリモートコンピューターのオペレーティングシステムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-105">Restarts the operating system on local and remote computers.</span></span>

## <span data-ttu-id="0ccf9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0ccf9-106">SYNTAX</span></span>

### <span data-ttu-id="0ccf9-107">DefaultSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="0ccf9-107">DefaultSet (Default)</span></span>

```
Restart-Computer [-WsmanAuthentication <String>] [[-ComputerName] <String[]>]
 [[-Credential]<PSCredential>] [-Force] [-Wait] [-Timeout <Int32>] [-For <WaitForServiceTypes>]
 [-Delay <Int16>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="0ccf9-108">Description</span><span class="sxs-lookup"><span data-stu-id="0ccf9-108">DESCRIPTION</span></span>

<span data-ttu-id="0ccf9-109">コマンドレットにより、 `Restart-Computer` ローカルコンピューターとリモートコンピューターのオペレーティングシステムが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-109">The `Restart-Computer` cmdlet restarts the operating system on the local and remote computers.</span></span>

<span data-ttu-id="0ccf9-110">のパラメーターを使用して、 `Restart-Computer` 再起動操作を実行し、認証レベルと代替資格情報を指定し、同時に実行される操作を制限し、即時再起動を強制することができます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-110">You can use the parameters of `Restart-Computer` to run the restart operations, to specify the authentication levels and alternate credentials, to limit the operations that run at the same time, and to force an immediate restart.</span></span>

<span data-ttu-id="0ccf9-111">Windows PowerShell 3.0 以降では、再起動が完了するのを待ってから、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-111">Starting in Windows PowerShell 3.0, you can wait for the restart to complete before you run the next command.</span></span> <span data-ttu-id="0ccf9-112">待機中のタイムアウトとクエリ間隔を指定し、再起動されたコンピューターで特定のサービスが利用可能になるまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-112">Specify a waiting time-out and query interval, and wait for particular services to be available on the restarted computer.</span></span> <span data-ttu-id="0ccf9-113">この機能により、スクリプトや関数でを使用することが実用的になり `Restart-Computer` ます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-113">This feature makes it practical to use `Restart-Computer` in scripts and functions.</span></span>

## <span data-ttu-id="0ccf9-114">例</span><span class="sxs-lookup"><span data-stu-id="0ccf9-114">EXAMPLES</span></span>

### <span data-ttu-id="0ccf9-115">例 1: ローカルコンピューターを再起動する</span><span class="sxs-lookup"><span data-stu-id="0ccf9-115">Example 1: Restart the local computer</span></span>

<span data-ttu-id="0ccf9-116">`Restart-Computer` ローカルコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-116">`Restart-Computer` restarts the local computer.</span></span>

```powershell
Restart-Computer
```

### <span data-ttu-id="0ccf9-117">例 2: 複数のコンピューターを再起動する</span><span class="sxs-lookup"><span data-stu-id="0ccf9-117">Example 2: Restart multiple computers</span></span>

<span data-ttu-id="0ccf9-118">`Restart-Computer` リモートコンピューターとローカルコンピューターを再起動できます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-118">`Restart-Computer` can restart remote and local computers.</span></span> <span data-ttu-id="0ccf9-119">**ComputerName** パラメーターは、コンピューター名の配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-119">The **ComputerName** parameter accepts an array of computer names.</span></span>

```powershell
Restart-Computer -ComputerName Server01, Server02, localhost
```

### <span data-ttu-id="0ccf9-120">例 3: テキストファイルからコンピューター名を取得する</span><span class="sxs-lookup"><span data-stu-id="0ccf9-120">Example 3: Get computer names from a text file</span></span>

<span data-ttu-id="0ccf9-121">`Restart-Computer` テキストファイルからコンピューター名の一覧を取得し、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-121">`Restart-Computer` gets a list of computer names from a text file and restarts the computers.</span></span> <span data-ttu-id="0ccf9-122">**ComputerName** パラメーターが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-122">The **ComputerName** parameter isn't specified.</span></span> <span data-ttu-id="0ccf9-123">ただし、これは最初の位置パラメーターなので、パイプラインで送信されるテキストファイルのコンピューター名を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-123">But because it's the first position parameter, it accepts the computer names from the text file that are sent down the pipeline.</span></span>

```powershell
Get-Content -Path C:\Domain01.txt | Restart-Computer
```

<span data-ttu-id="0ccf9-124">`Get-Content`**Path** パラメーターを使用して、 **Domain01.txt** テキストファイルからコンピューター名の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-124">`Get-Content` uses the **Path** parameter to get a list of computer names from a text file, **Domain01.txt**.</span></span> <span data-ttu-id="0ccf9-125">コンピューター名は、パイプラインによって送信されます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-125">The computer names are sent down the pipeline.</span></span> <span data-ttu-id="0ccf9-126">`Restart-Computer` 各コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-126">`Restart-Computer` restarts each computer.</span></span>

### <span data-ttu-id="0ccf9-127">例 4: テキストファイルに一覧表示されているコンピューターを強制的に再起動する</span><span class="sxs-lookup"><span data-stu-id="0ccf9-127">Example 4: Force restart of computers listed in a text file</span></span>

<span data-ttu-id="0ccf9-128">この例では、ファイルに一覧表示されているコンピューターを直ちに再起動 `Domain01.txt` します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-128">This example forces an immediate restart of the computers listed in the `Domain01.txt` file.</span></span> <span data-ttu-id="0ccf9-129">テキストファイルからのコンピューター名は、変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-129">The computer names from the text file are stored in a variable.</span></span> <span data-ttu-id="0ccf9-130">**Force** パラメーターを指定すると、即時再起動が強制されます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-130">The **Force** parameter forces an immediate restart.</span></span>

```powershell
$Names = Get-Content -Path C:\Domain01.txt
$Creds = Get-Credential
Restart-Computer -ComputerName $Names -Credential $Creds -Force
```

<span data-ttu-id="0ccf9-131">`Get-Content`**Path** パラメーターを使用して、 **Domain01.txt** テキストファイルからコンピューター名の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-131">`Get-Content` uses the **Path** parameter to get a list of computer names from a text file, **Domain01.txt**.</span></span> <span data-ttu-id="0ccf9-132">コンピューター名は変数に格納され `$Names` ます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-132">The computer names are stored in the variable `$Names`.</span></span> <span data-ttu-id="0ccf9-133">`Get-Credential` ユーザー名とパスワードの入力を求め、変数に値を格納し `$Creds` ます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-133">`Get-Credential` prompts you for a username and password and stores the values in the variable `$Creds`.</span></span> <span data-ttu-id="0ccf9-134">`Restart-Computer` では、 **ComputerName** パラメーターと **Credential** パラメーターをその変数と共に使用します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-134">`Restart-Computer` uses the **ComputerName** and **Credential** parameters with their variables.</span></span> <span data-ttu-id="0ccf9-135">**Force** パラメーターを指定すると、各コンピューターが直ちに再起動されます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-135">The **Force** parameter causes an immediate restart of each computer.</span></span>

### <span data-ttu-id="0ccf9-136">例 6: リモートコンピューターを再起動し、PowerShell を待機する</span><span class="sxs-lookup"><span data-stu-id="0ccf9-136">Example 6: Restart a remote computer and wait for PowerShell</span></span>

<span data-ttu-id="0ccf9-137">`Restart-Computer` リモートコンピューターを再起動してから、再起動されたコンピューターで PowerShell が使用できるようになるまで最大5分 (300 秒) 待機してから続行します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-137">`Restart-Computer` restarts the remote computer and then waits up to 5 minutes (300 seconds) for PowerShell to become available on the restarted computer before it continues.</span></span>

```powershell
Restart-Computer -ComputerName Server01 -Wait -For PowerShell -Timeout 300 -Delay 2
```

<span data-ttu-id="0ccf9-138">`Restart-Computer`**ComputerName** パラメーターを使用して **Server01** を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-138">`Restart-Computer` uses the **ComputerName** parameter to specify **Server01**.</span></span> <span data-ttu-id="0ccf9-139">**Wait** パラメーターは、再起動が完了するまで待機します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-139">The **Wait** parameter waits for the restart to finish.</span></span> <span data-ttu-id="0ccf9-140">**の** は、PowerShell がリモートコンピューターでコマンドを実行できることを指定します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-140">The **For** specifies that PowerShell can run commands on the remote computer.</span></span> <span data-ttu-id="0ccf9-141">**Timeout** パラメーターは、5分間の待機を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-141">The **Timeout** parameter specifies a five-minute wait.</span></span> <span data-ttu-id="0ccf9-142">**Delay** パラメータは、リモートコンピュータを再起動するかどうかを確認するために、2秒ごとにクエリを行います。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-142">The **Delay** parameter queries the remote computer every two seconds to determine whether it's restarted.</span></span>

### <span data-ttu-id="0ccf9-143">例 7: WsmanAuthentication を使用してコンピューターを再起動する</span><span class="sxs-lookup"><span data-stu-id="0ccf9-143">Example 7: Restart a computer by using WsmanAuthentication</span></span>

<span data-ttu-id="0ccf9-144">`Restart-Computer`**WsmanAuthentication** メカニズムを使用してリモートコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-144">`Restart-Computer` restarts the remote computer using the **WsmanAuthentication** mechanism.</span></span>
<span data-ttu-id="0ccf9-145">Kerberos 認証は、現在のユーザーがリモートコンピューターを再起動するアクセス許可を持っているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-145">Kerberos authentication determines whether the current user has permission to restart the remote computer.</span></span> <span data-ttu-id="0ccf9-146">詳細については、「 [Authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-146">For more information, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

```powershell
Restart-Computer -ComputerName Server01 -WsmanAuthentication Kerberos
```

<span data-ttu-id="0ccf9-147">`Restart-Computer`**ComputerName** パラメーターを使用して、リモートコンピューター **Server01** を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-147">`Restart-Computer` uses the **ComputerName** parameter to specify the remote computer, **Server01**.</span></span>
<span data-ttu-id="0ccf9-148">**WsmanAuthentication** パラメーターは、認証方法を **Kerberos** として指定します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-148">The **WsmanAuthentication** parameter specifies the authentication method as **Kerberos**.</span></span>

## <span data-ttu-id="0ccf9-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0ccf9-149">PARAMETERS</span></span>

### <span data-ttu-id="0ccf9-150">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="0ccf9-150">-ComputerName</span></span>

<span data-ttu-id="0ccf9-151">1つのコンピューター名、またはコンピューター名のコンマ区切りの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-151">Specifies one computer name or a comma-separated array of computer names.</span></span> <span data-ttu-id="0ccf9-152">`Restart-Computer` パイプラインまたは変数から **ComputerName** オブジェクトを受け入れます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-152">`Restart-Computer` accepts **ComputerName** objects from the pipeline or variables.</span></span>

<span data-ttu-id="0ccf9-153">リモート コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-153">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span> <span data-ttu-id="0ccf9-154">ローカルコンピューターを指定するには、コンピューター名、ドット `.` 、または localhost を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-154">To specify the local computer, type the computer name, a dot `.`, or localhost.</span></span>

<span data-ttu-id="0ccf9-155">このパラメーターは、PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-155">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="0ccf9-156">コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-156">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

<span data-ttu-id="0ccf9-157">**ComputerName** パラメーターが指定されていない場合、は `Restart-Computer` ローカルコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-157">If the **ComputerName** parameter isn't specified, `Restart-Computer` restarts the local computer.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: CN, __SERVER, Server, IPAddress

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0ccf9-158">-Credential</span><span class="sxs-lookup"><span data-stu-id="0ccf9-158">-Credential</span></span>

<span data-ttu-id="0ccf9-159">このアクションを実行するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-159">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="0ccf9-160">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-160">The default is the current user.</span></span>

<span data-ttu-id="0ccf9-161">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-161">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="0ccf9-162">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-162">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="0ccf9-163">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-163">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="0ccf9-164">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-164">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ccf9-165">-Delay</span><span class="sxs-lookup"><span data-stu-id="0ccf9-165">-Delay</span></span>

<span data-ttu-id="0ccf9-166">クエリの頻度を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-166">Specifies the frequency of queries, in seconds.</span></span> <span data-ttu-id="0ccf9-167">PowerShell は、For パラメーターによって指定されたサービスに **対し** てクエリを実行し、コンピューターの再起動後にサービスを使用できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-167">PowerShell queries the service specified by the **For** parameter to determine whether the service is available after the computer is restarted.</span></span>

<span data-ttu-id="0ccf9-168">このパラメーターは、 **Wait** パラメーターと **For** パラメーターと共に使用する場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-168">This parameter is valid only together with the **Wait** and **For** parameters.</span></span>

<span data-ttu-id="0ccf9-169">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-169">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="0ccf9-170">**Delay** パラメーターが指定されていない場合、で `Restart-Computer` は5秒の遅延が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-170">If the **Delay** parameter isn't specified, `Restart-Computer` uses a five second delay.</span></span>

```yaml
Type: System.Int16
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ccf9-171">-の場合</span><span class="sxs-lookup"><span data-stu-id="0ccf9-171">-For</span></span>

<span data-ttu-id="0ccf9-172">コンピューターの再起動後に、指定されたサービスまたは機能が使用可能になるのを待機するときの PowerShell の動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-172">Specifies the behavior of PowerShell as it waits for the specified service or feature to become available after the computer restarts.</span></span> <span data-ttu-id="0ccf9-173">このパラメーターは、 **Wait** パラメーターでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-173">This parameter is only valid with the **Wait** parameter.</span></span>

<span data-ttu-id="0ccf9-174">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-174">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="0ccf9-175">**既定値** : PowerShell が再開されるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-175">**Default** : Waits for PowerShell to restart.</span></span>
- <span data-ttu-id="0ccf9-176">**Powershell** : コンピューター上の powershell リモートセッションでコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-176">**PowerShell** : Can run commands in a PowerShell remote session on the computer.</span></span>
- <span data-ttu-id="0ccf9-177">**WMI** : コンピューターの Win32_ComputerSystem クエリへの応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-177">**WMI** : Receives a reply to a Win32_ComputerSystem query for the computer.</span></span>
- <span data-ttu-id="0ccf9-178">**WinRM** : ws-management を使用して、コンピューターへのリモートセッションを確立できます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-178">**WinRM** : Can establish a remote session to the computer by using WS-Management.</span></span>

<span data-ttu-id="0ccf9-179">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-179">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WaitForServiceTypes
Parameter Sets: (All)
Aliases:
Accepted values: Wmi, WinRM, PowerShell

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ccf9-180">-Force</span><span class="sxs-lookup"><span data-stu-id="0ccf9-180">-Force</span></span>

<span data-ttu-id="0ccf9-181">コンピューターの即時再起動を強制します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-181">Forces an immediate restart of the computer.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ccf9-182">-タイムアウト</span><span class="sxs-lookup"><span data-stu-id="0ccf9-182">-Timeout</span></span>

<span data-ttu-id="0ccf9-183">待機期間を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-183">Specifies the duration of the wait, in seconds.</span></span> <span data-ttu-id="0ccf9-184">タイムアウトが経過すると、 `Restart-Computer` コンピューターが再起動されていない場合でも、はコマンドプロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-184">When the timeout elapses, `Restart-Computer` returns to the command prompt, even if the computers aren't restarted.</span></span>

<span data-ttu-id="0ccf9-185">**Timeout** パラメーターは、 **Wait** パラメーターと共にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-185">The **Timeout** parameter is only valid with the **Wait** parameter.</span></span> <span data-ttu-id="0ccf9-186">**Timeout** は、 **待機** パラメーターの無期限の待機期間をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-186">**Timeout** overrides the **Wait** parameter's indefinite waiting period.</span></span>

<span data-ttu-id="0ccf9-187">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-187">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutSec

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ccf9-188">-Wait</span><span class="sxs-lookup"><span data-stu-id="0ccf9-188">-Wait</span></span>

<span data-ttu-id="0ccf9-189">`Restart-Computer` PowerShell プロンプトを非表示にし、コンピューターが再起動されるまでパイプラインをブロックします。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-189">`Restart-Computer` suppresses the PowerShell prompt and blocks the pipeline until the computers have restarted.</span></span> <span data-ttu-id="0ccf9-190">このパラメーターをスクリプトで使用すると、コンピューターを再起動し、再起動が完了したときに処理を続行できます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-190">You can use this parameter in a script to restart computers and then continue to process when the restart is finished.</span></span>

<span data-ttu-id="0ccf9-191">**Wait** パラメーターは、コンピューターが再起動するまで無期限に待機します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-191">The **Wait** parameter waits indefinitely for the computers to restart.</span></span> <span data-ttu-id="0ccf9-192">**タイムアウト** を使用してタイミングを調整し、 **For** および **Delay** パラメーターを使用して、再起動されたコンピューターで特定のサービスが利用可能になるまで待機することができます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-192">You can use **Timeout** to adjust the timing and the **For** and **Delay** parameters to wait for particular services to become available on the restarted computers.</span></span>

<span data-ttu-id="0ccf9-193">ローカルコンピューターを再起動する場合、 **Wait** パラメーターは無効です。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-193">The **Wait** parameter isn't valid when you're restarting the local computer.</span></span> <span data-ttu-id="0ccf9-194">**ComputerName** パラメーターの値にリモートコンピューターとローカルコンピューターの名前が含まれている場合、は、 `Restart-Computer` ローカルコンピューターの **待機** に対して終了しないエラーを生成しますが、リモートコンピューターの再起動を待機します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-194">If the value of the **ComputerName** parameter contains the names of remote computers and the local computer, `Restart-Computer` generates a non-terminating error for **Wait** on the local computer, but waits for the remote computers to restart.</span></span>

<span data-ttu-id="0ccf9-195">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-195">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="0ccf9-196">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="0ccf9-196">-WsmanAuthentication</span></span>

<span data-ttu-id="0ccf9-197">ユーザー資格情報の認証に使用するメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-197">Specifies the mechanism that is used to authenticate the user credentials.</span></span> <span data-ttu-id="0ccf9-198">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-198">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="0ccf9-199">このパラメーターに指定できる値は、 **Basic** 、 **CredSSP** 、 **Default** 、 **Digest** 、 **Kerberos** 、および **Negotiate** です。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-199">The acceptable values for this parameter are: **Basic** , **CredSSP** , **Default** , **Digest** , **Kerberos** , and **Negotiate**.</span></span>

<span data-ttu-id="0ccf9-200">詳細については、「 [Authenticationmechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-200">For more information, see [AuthenticationMechanism](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="0ccf9-201">ユーザー資格情報が認証対象のリモートコンピューターに渡される Credential Security Service Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-201">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span> <span data-ttu-id="0ccf9-202">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-202">This mechanism increases the security risk of the remote operation.</span></span> <span data-ttu-id="0ccf9-203">リモート コンピューターのセキュリティが低下している場合は、そのリモート コンピューターに渡される資格情報を使用してネットワーク セッションが制御される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-203">If the remote computer is compromised, the credentials that are passed to it can be used to control the network session.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Basic, CredSSP, Default, Digest, Kerberos, Negotiate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0ccf9-204">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0ccf9-204">-Confirm</span></span>

<span data-ttu-id="0ccf9-205">実行前に確認メッセージを表示 `Restart-Computer` します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-205">Prompts you for confirmation before running `Restart-Computer`.</span></span>

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

### <span data-ttu-id="0ccf9-206">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0ccf9-206">-WhatIf</span></span>

<span data-ttu-id="0ccf9-207">が実行された場合に何が起こるかを示し `Restart-Computer` ます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-207">Shows what would happen if the `Restart-Computer` runs.</span></span> <span data-ttu-id="0ccf9-208">`Restart-Computer`コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-208">The `Restart-Computer` cmdlet isn't run.</span></span>

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

### <span data-ttu-id="0ccf9-209">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="0ccf9-209">CommonParameters</span></span>

<span data-ttu-id="0ccf9-210">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-210">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0ccf9-211">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-211">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0ccf9-212">入力</span><span class="sxs-lookup"><span data-stu-id="0ccf9-212">INPUTS</span></span>

### <span data-ttu-id="0ccf9-213">System.String</span><span class="sxs-lookup"><span data-stu-id="0ccf9-213">System.String</span></span>

<span data-ttu-id="0ccf9-214">`Restart-Computer` パイプラインまたは変数のコンピューター名を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-214">`Restart-Computer` accepts computer names from the pipeline or variables.</span></span>

## <span data-ttu-id="0ccf9-215">出力</span><span class="sxs-lookup"><span data-stu-id="0ccf9-215">OUTPUTS</span></span>

### <span data-ttu-id="0ccf9-216">なし</span><span class="sxs-lookup"><span data-stu-id="0ccf9-216">None</span></span>

<span data-ttu-id="0ccf9-217">`Restart-Computer` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-217">`Restart-Computer` doesn't generate any output.</span></span>

## <span data-ttu-id="0ccf9-218">注</span><span class="sxs-lookup"><span data-stu-id="0ccf9-218">NOTES</span></span>

<span data-ttu-id="0ccf9-219">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-219">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="0ccf9-220">`Restart-Computer` は Windows を実行しているコンピューターでのみ機能し、ローカルシステムを含むシステムをシャットダウンするには、WinRM と WMI が必要です。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-220">`Restart-Computer` only works on computers running Windows and requires WinRM and WMI to shutdown a system, including the local system.</span></span>
- <span data-ttu-id="0ccf9-221">`Restart-Computer`Windows Management Instrumentation (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem)クラスの[Win32Shutdown メソッド](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem)を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-221">`Restart-Computer` uses the [Win32Shutdown method](/windows/desktop/CIMWin32Prov/win32shutdown-method-in-class-win32-operatingsystem) of the Windows Management Instrumentation (WMI) [Win32_OperatingSystem](/windows/desktop/CIMWin32Prov/win32-operatingsystem) class.</span></span> <span data-ttu-id="0ccf9-222">この方法では、コンピューターの再起動に使用するユーザーアカウントに対して、 **Seshutdownprivilege** 特権を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ccf9-222">This method requires the **SeShutdownPrivilege** privilege be enabled for the user account used to restart the machine.</span></span>

## <span data-ttu-id="0ccf9-223">関連リンク</span><span class="sxs-lookup"><span data-stu-id="0ccf9-223">RELATED LINKS</span></span>

[<span data-ttu-id="0ccf9-224">Windows リモート管理について</span><span class="sxs-lookup"><span data-stu-id="0ccf9-224">About Windows Remote Management</span></span>](/windows/desktop/WinRM/about-windows-remote-management)

[<span data-ttu-id="0ccf9-225">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="0ccf9-225">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="0ccf9-226">WS-Management Protocol (WS-Management プロトコル)</span><span class="sxs-lookup"><span data-stu-id="0ccf9-226">WS-Management Protocol</span></span>](/windows/desktop/WinRM/ws-management-protocol)
