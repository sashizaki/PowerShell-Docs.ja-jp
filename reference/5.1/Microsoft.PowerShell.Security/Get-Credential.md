---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-credential?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Credential
ms.openlocfilehash: 26c4f8c8dcc1fbd56e29f55a6a8c2e6aa37a2842
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "93225203"
---
# <span data-ttu-id="efb4d-103">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="efb4d-103">Get-Credential</span></span>

## <span data-ttu-id="efb4d-104">概要</span><span class="sxs-lookup"><span data-stu-id="efb4d-104">SYNOPSIS</span></span>
<span data-ttu-id="efb4d-105">ユーザー名とパスワードに基づいて資格情報オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-105">Gets a credential object based on a user name and password.</span></span>

## <span data-ttu-id="efb4d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="efb4d-106">SYNTAX</span></span>

### <span data-ttu-id="efb4d-107">CredentialSet (既定)</span><span class="sxs-lookup"><span data-stu-id="efb4d-107">CredentialSet (Default)</span></span>

```
Get-Credential [-Credential] <PSCredential> [<CommonParameters>]
```

### <span data-ttu-id="efb4d-108">MessageSet</span><span class="sxs-lookup"><span data-stu-id="efb4d-108">MessageSet</span></span>

```
Get-Credential -Message <String> [[-UserName] <String>] [<CommonParameters>]
```

## <span data-ttu-id="efb4d-109">Description</span><span class="sxs-lookup"><span data-stu-id="efb4d-109">DESCRIPTION</span></span>

<span data-ttu-id="efb4d-110">コマンドレットでは、 `Get-Credential` 指定されたユーザー名とパスワードの資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-110">The `Get-Credential` cmdlet creates a credential object for a specified user name and password.</span></span> <span data-ttu-id="efb4d-111">作成した資格情報オブジェクトは、セキュリティ操作で使用できます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-111">You can use the credential object in security operations.</span></span>

<span data-ttu-id="efb4d-112">PowerShell 3.0 以降では、 **message** パラメーターを使用して、ユーザーに名前とパスワードの入力を求めるダイアログボックスでカスタマイズされたメッセージを指定できます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-112">Beginning in PowerShell 3.0, you can use the **Message** parameter to specify a customized message on the dialog box that prompts the user for their name and password.</span></span>

<span data-ttu-id="efb4d-113">`Get-Credential`コマンドレットは、パスワードまたはユーザー名とパスワードの入力をユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-113">The `Get-Credential` cmdlet prompts the user for a password or a user name and password.</span></span> <span data-ttu-id="efb4d-114">既定では、ユーザーに入力を求める認証ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-114">By default, an authentication dialog box appears to prompt the user.</span></span> <span data-ttu-id="efb4d-115">ただし、PowerShell コンソールなどの一部のホストプログラムでは、レジストリエントリを変更することで、コマンドラインでユーザーにプロンプトを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-115">However, in some host programs, such as the PowerShell console, you can prompt the user at the command line by changing a registry entry.</span></span> <span data-ttu-id="efb4d-116">このレジストリ エントリの詳細については、注記と例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb4d-116">For more information about this registry entry, see the notes and examples.</span></span>

## <span data-ttu-id="efb4d-117">例</span><span class="sxs-lookup"><span data-stu-id="efb4d-117">EXAMPLES</span></span>

### <span data-ttu-id="efb4d-118">例 1</span><span class="sxs-lookup"><span data-stu-id="efb4d-118">Example 1</span></span>

```powershell
$c = Get-Credential
```

<span data-ttu-id="efb4d-119">このコマンドは、資格情報オブジェクトを取得し、変数に保存し `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-119">This command gets a credential object and saves it in the `$c` variable.</span></span>

<span data-ttu-id="efb4d-120">このコマンドを入力すると、ユーザー名とパスワードの入力を求めるダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-120">When you enter the command, a dialog box appears requesting a user name and password.</span></span> <span data-ttu-id="efb4d-121">要求された情報を入力すると、コマンドレットは、ユーザーの資格情報を表す **PSCredential** オブジェクトを作成し、変数に保存し `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-121">When you enter the requested information, the cmdlet creates a **PSCredential** object representing the credentials of the user and saves it in the `$c` variable.</span></span>

<span data-ttu-id="efb4d-122">このオブジェクトは、 **Credential** パラメーターを持つコマンドレットなど、ユーザー認証を必要とするコマンドレットへの入力として使用できます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-122">You can use the object as input to cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span> <span data-ttu-id="efb4d-123">ただし、PowerShell でインストールされる一部のプロバイダーでは、 **Credential** パラメーターはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="efb4d-123">However, some providers that are installed with PowerShell do not support the **Credential** parameter.</span></span>

### <span data-ttu-id="efb4d-124">例 2</span><span class="sxs-lookup"><span data-stu-id="efb4d-124">Example 2</span></span>

```powershell
$c = Get-Credential
Get-CimInstance Win32_DiskDrive -ComputerName Server01 -Credential $c
```

<span data-ttu-id="efb4d-125">これらのコマンドは、Windows Management Instrumentation (WMI) を使用してコンピューターを管理できるように、コマンドレットから返される資格情報オブジェクトを使用して `Get-Credential` リモートコンピューター上のユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-125">These commands use a credential object that the `Get-Credential` cmdlet returns to authenticate a user on a remote computer so they can use Windows Management Instrumentation (WMI) to manage the computer.</span></span>

<span data-ttu-id="efb4d-126">最初のコマンドは、資格情報オブジェクトを取得し、変数に保存し `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-126">The first command gets a credential object and saves it in the `$c` variable.</span></span> <span data-ttu-id="efb4d-127">2番目のコマンドは、コマンドで credential オブジェクトを使用し `Get-CimInstance` ます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-127">The second command uses the credential object in a `Get-CimInstance` command.</span></span> <span data-ttu-id="efb4d-128">このコマンドは、Server01 コンピューターのディスク ドライブに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-128">This command gets information about the disk drives on the Server01 computer.</span></span>

### <span data-ttu-id="efb4d-129">例 3</span><span class="sxs-lookup"><span data-stu-id="efb4d-129">Example 3</span></span>

```powershell
Get-CimInstance Win32_BIOS -ComputerName Server01 -Credential (Get-Credential -Credential Domain01\User01)
```

<span data-ttu-id="efb4d-130">このコマンドは、コマンドにコマンドを含める方法を示して `Get-Credential`  `Get-CimInstance` います。</span><span class="sxs-lookup"><span data-stu-id="efb4d-130">This command shows how to include a `Get-Credential` command in a  `Get-CimInstance` command.</span></span>

<span data-ttu-id="efb4d-131">このコマンドは、コマンドレットを使用して、 `Get-CimInstance` Server01 コンピューター上の BIOS に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-131">This command uses the `Get-CimInstance` cmdlet to get information about the BIOS on the Server01 computer.</span></span> <span data-ttu-id="efb4d-132">**Credential パラメーターを** 使用し `Get-Credential` て、 **credential** パラメーターの値として user、domain01\user01」、および command を認証します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-132">It uses the **Credential** parameter to authenticate the user, Domain01\User01, and a `Get-Credential` command as the value of the **Credential** parameter.</span></span>

### <span data-ttu-id="efb4d-133">例 4</span><span class="sxs-lookup"><span data-stu-id="efb4d-133">Example 4</span></span>

```powershell
$c = Get-Credential -credential User01
$c.Username
User01
```

<span data-ttu-id="efb4d-134">この例では、ドメイン名なしのユーザー名を含む資格情報を作成しています。</span><span class="sxs-lookup"><span data-stu-id="efb4d-134">This example creates a credential that includes a user name without a domain name.</span></span>

<span data-ttu-id="efb4d-135">最初のコマンドは、ユーザー名が User01 の資格情報を取得し、変数に格納し `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-135">The first command gets a credential with the user name User01 and stores it in the `$c` variable.</span></span>
<span data-ttu-id="efb4d-136">2 番目のコマンドは、結果として得られる資格情報オブジェクトの **Username** プロパティの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-136">The second command displays the value of the **Username** property of the resulting credential object.</span></span>

### <span data-ttu-id="efb4d-137">例 5</span><span class="sxs-lookup"><span data-stu-id="efb4d-137">Example 5</span></span>

```powershell
$Credential = $host.ui.PromptForCredential("Need credentials", "Please enter your user name and password.", "", "NetBiosUserName")
```

<span data-ttu-id="efb4d-138">このコマンドは、 **PromptForCredential** メソッドを使用して、ユーザーにユーザー名とパスワードを入力するよう求めます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-138">This command uses the **PromptForCredential** method to prompt the user for their user name and password.</span></span> <span data-ttu-id="efb4d-139">このコマンドは、結果として得られる資格情報を変数に保存し `$Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-139">The command saves the resulting credentials in the `$Credential` variable.</span></span>

<span data-ttu-id="efb4d-140">**Promptforcredential** メソッドは、コマンドレットを使用する代わりに使用し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-140">The **PromptForCredential** method is an alternative to using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="efb4d-141">**PromptForCredential** を使用すると、メッセージ ボックスに表示されるキャプション、メッセージ、およびユーザー名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-141">When you use **PromptForCredential** , you can specify the caption, messages, and user name that appear in the message box.</span></span>

<span data-ttu-id="efb4d-142">詳細については、SDK の [Promptforcredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb4d-142">For more information, see the [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) documentation in the SDK.</span></span>

### <span data-ttu-id="efb4d-143">例 6</span><span class="sxs-lookup"><span data-stu-id="efb4d-143">Example 6</span></span>

```powershell
Set-ItemProperty "HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds" -Name ConsolePrompting -Value $true
```

<span data-ttu-id="efb4d-144">この例は、ダイアログ ボックスを使用する代わりに、コマンドラインでユーザーに入力が要求されるように、レジストリを変更する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="efb4d-144">This example shows how to modify the registry so that the user is prompted at the command line, instead of by using a dialog box.</span></span>

<span data-ttu-id="efb4d-145">このコマンドは、 **ConsolePrompting** レジストリ エントリを作成して、値を True に設定します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-145">The command creates the **ConsolePrompting** registry entry and sets its value to True.</span></span> <span data-ttu-id="efb4d-146">このコマンドを実行するには、[管理者として実行] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-146">To run this command, start PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="efb4d-147">プロンプトにダイアログボックスを使用するには、ConsolePrompting の値を false ($false) に設定するか、コマンドレットを使用し `Remove-ItemProperty` て削除します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-147">To use a dialog box for prompting, set the value of the ConsolePrompting to false ($false) or use the `Remove-ItemProperty` cmdlet to delete it.</span></span>

<span data-ttu-id="efb4d-148">ConsolePrompting のレジストリエントリは、PowerShell コンソールなどの一部のホストプログラムで機能します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-148">The ConsolePrompting registry entry works in some host programs, such as the PowerShell console.</span></span> <span data-ttu-id="efb4d-149">すべてのホスト プログラムで機能するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="efb4d-149">It might not work in all host programs.</span></span>

### <span data-ttu-id="efb4d-150">例 7</span><span class="sxs-lookup"><span data-stu-id="efb4d-150">Example 7</span></span>

<span data-ttu-id="efb4d-151">この例では、ユーザーにメッセージを表示せずにを返すオブジェクトと同じ資格情報オブジェクトを作成する方法を示し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-151">This example shows how to create a credential object that is identical to the object that `Get-Credential` returns without prompting the user.</span></span> <span data-ttu-id="efb4d-152">このメソッドではプレーンテキスト パスワードが必要ですが、企業によってはセキュリティ標準に違反する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="efb4d-152">This method requires a plain text password, which might violate the security standards in some enterprises.</span></span>

```powershell
$User = "Domain01\User01"
$PWord = ConvertTo-SecureString -String "P@sSwOrd" -AsPlainText -Force
$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $PWord
```

<span data-ttu-id="efb4d-153">最初のコマンドは、ユーザーアカウント名をパラメーターに保存し `$User` ます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-153">The first command saves the user account name in the `$User` parameter.</span></span> <span data-ttu-id="efb4d-154">この値は、"Domain\User" または "ComputerName\User" の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="efb4d-154">The value must have the "Domain\User" or "ComputerName\User" format.</span></span>

<span data-ttu-id="efb4d-155">2番目のコマンドは、コマンドレットを使用して、 `ConvertTo-SecureString` プレーンテキストパスワードからセキュリティで保護された文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-155">The second command uses the `ConvertTo-SecureString` cmdlet to create a secure string from a plain text password.</span></span> <span data-ttu-id="efb4d-156">このコマンドは、 **AsPlainText** パラメーターを使用して、文字列がプレーンテキストであることを示します。また、 **Force** パラメーターを使用して、プレーンテキストの使用に伴うリスクを理解しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-156">The command uses the **AsPlainText** parameter to indicate that the string is plain text and the **Force** parameter to confirm that you understand the risks of using plain text.</span></span>

<span data-ttu-id="efb4d-157">3番目のコマンドは、コマンドレットを使用して、 `New-Object` 変数と変数の値から **PSCredential** オブジェクトを作成し `$User` `$PWord` ます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-157">The third command uses the `New-Object` cmdlet to create a **PSCredential** object from the values in the `$User` and `$PWord` variables.</span></span>

### <span data-ttu-id="efb4d-158">例 8</span><span class="sxs-lookup"><span data-stu-id="efb4d-158">Example 8</span></span>

```powershell
Get-Credential -Message "Credential are required for access to the \\Server1\Scripts file share." -User Server01\PowerUser
```

```Output
PowerShell Credential Request
Credential are required for access to the \\Server1\Scripts file share.
Password for user Server01\PowerUser:
```

<span data-ttu-id="efb4d-159">このコマンドは、コマンドレットの **Message** パラメーターと **UserName** パラメーターを使用し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-159">This command uses the **Message** and **UserName** parameters of the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="efb4d-160">このコマンド形式は、共有スクリプトおよび共有関数向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="efb4d-160">This command format is designed for shared scripts and functions.</span></span> <span data-ttu-id="efb4d-161">この例では、メッセージはユーザーに、資格情報が必要な理由を伝え、要求が正当であるという安心感を与えています。</span><span class="sxs-lookup"><span data-stu-id="efb4d-161">In this case, the message tells the user why credentials are needed and gives them confidence that the request is legitimate.</span></span>

### <span data-ttu-id="efb4d-162">例 9</span><span class="sxs-lookup"><span data-stu-id="efb4d-162">Example 9</span></span>

```powershell
Invoke-Command -ComputerName Server01 {Get-Credential Domain01\User02}
```

```Output
PowerShell Credential Request : PowerShell Credential Request
Warning: This credential is being requested by a script or application on the SERVER01 remote computer. Enter your credentials only if you
 trust the remote computer and the application or script requesting it.

Enter your credentials.
Password for user Domain01\User02: ***************

PSComputerName     : Server01
RunspaceId         : 422bdf52-9886-4ada-ab2f-130497c6777f
PSShowComputerName : True
UserName           : Domain01\User01
Password           : System.Security.SecureString
```

<span data-ttu-id="efb4d-163">このコマンドは、Server01 リモート コンピューターから資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-163">This command gets a credential from the Server01 remote computer.</span></span> <span data-ttu-id="efb4d-164">コマンドは、コマンドレットを使用して、 `Invoke-Command` `Get-Credential` リモートコンピューター上でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-164">The command uses the `Invoke-Command` cmdlet to run a `Get-Credential` command on the remote computer.</span></span> <span data-ttu-id="efb4d-165">出力には、認証プロンプトに含まれるリモートセキュリティメッセージが表示され `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-165">The output shows the remote security message that `Get-Credential` includes in the authentication prompt.</span></span>

## <span data-ttu-id="efb4d-166">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="efb4d-166">PARAMETERS</span></span>

### <span data-ttu-id="efb4d-167">-Credential</span><span class="sxs-lookup"><span data-stu-id="efb4d-167">-Credential</span></span>

<span data-ttu-id="efb4d-168">**User01** や **domain01\user01」** など、資格情報のユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-168">Specifies a user name for the credential, such as **User01** or **Domain01\User01**.</span></span> <span data-ttu-id="efb4d-169">パラメーター名は `-Credential` 省略可能です。</span><span class="sxs-lookup"><span data-stu-id="efb4d-169">The parameter name, `-Credential`, is optional.</span></span>

<span data-ttu-id="efb4d-170">コマンドを送信し、ユーザー名を指定すると、パスワードの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-170">When you submit the command and specify a user name, you're prompted for a password.</span></span> <span data-ttu-id="efb4d-171">このパラメーターを省略すると、ユーザー名とパスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-171">If you omit this parameter, you're prompted for a user name and a password.</span></span>

<span data-ttu-id="efb4d-172">PowerShell 3.0 以降では、ドメインを使用せずにユーザー名を入力すると、 `Get-Credential` 名前の前に円記号が挿入されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="efb4d-172">Starting in PowerShell 3.0, if you enter a user name without a domain, `Get-Credential` no longer inserts a backslash before the name.</span></span>

<span data-ttu-id="efb4d-173">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-173">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="efb4d-174">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb4d-174">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="efb4d-175">-メッセージ</span><span class="sxs-lookup"><span data-stu-id="efb4d-175">-Message</span></span>

<span data-ttu-id="efb4d-176">認証プロンプトに表示されるメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-176">Specifies a message that appears in the authentication prompt.</span></span> <span data-ttu-id="efb4d-177">このパラメーターは、関数またはスクリプトで使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="efb4d-177">This parameter is designed for use in a function or script.</span></span> <span data-ttu-id="efb4d-178">メッセージを使用して、資格情報が必要な理由と使用方法をユーザーに説明できます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-178">You can use the message to explain to the user why you are requesting credentials and how they will be used.</span></span>

<span data-ttu-id="efb4d-179">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="efb4d-179">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="efb4d-180">-UserName</span><span class="sxs-lookup"><span data-stu-id="efb4d-180">-UserName</span></span>

<span data-ttu-id="efb4d-181">ユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-181">Specifies a user name.</span></span> <span data-ttu-id="efb4d-182">認証プロンプトで、ユーザー名に対応するパスワードの入力が要求されます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-182">The authentication prompt requests a password for the user name.</span></span> <span data-ttu-id="efb4d-183">既定では、ユーザー名は空白で、認証プロンプトでユーザー名とパスワードの両方が要求されます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-183">By default, the user name is blank and the authentication prompt requests both a user name and password.</span></span>

<span data-ttu-id="efb4d-184">認証プロンプトがダイアログ ボックスに表示される場合は、ユーザーは指定されたユーザー名を編集できます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-184">When the authentication prompt appears in a dialog box, the user can edit the specified user name.</span></span>
<span data-ttu-id="efb4d-185">一方、認証プロンプトがコマンドラインに表示された場合は、ユーザーはユーザー名を変更できません。</span><span class="sxs-lookup"><span data-stu-id="efb4d-185">However, the user cannot change the user name when the prompt appears at the command line.</span></span> <span data-ttu-id="efb4d-186">共有関数または共有スクリプトでこのパラメーターを使用する場合は、可能性のあるすべての表示内容を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="efb4d-186">When using this parameter in a shared function or script, consider all possible presentations.</span></span>

<span data-ttu-id="efb4d-187">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="efb4d-187">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: 1
Default value: None (blank)
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="efb4d-188">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="efb4d-188">CommonParameters</span></span>

<span data-ttu-id="efb4d-189">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="efb4d-189">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="efb4d-190">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb4d-190">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="efb4d-191">入力</span><span class="sxs-lookup"><span data-stu-id="efb4d-191">INPUTS</span></span>

### <span data-ttu-id="efb4d-192">なし</span><span class="sxs-lookup"><span data-stu-id="efb4d-192">None</span></span>

<span data-ttu-id="efb4d-193">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="efb4d-193">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="efb4d-194">出力</span><span class="sxs-lookup"><span data-stu-id="efb4d-194">OUTPUTS</span></span>

### <span data-ttu-id="efb4d-195">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="efb4d-195">System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="efb4d-196">`Get-Credential` 資格情報オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-196">`Get-Credential` returns a credential object.</span></span>

## <span data-ttu-id="efb4d-197">注</span><span class="sxs-lookup"><span data-stu-id="efb4d-197">NOTES</span></span>

<span data-ttu-id="efb4d-198">**PSCredential** `Get-Credential` ユーザー認証を要求するコマンドレットでを作成する PSCredential オブジェクトを使用できます。たとえば、 **Credential** パラメーターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-198">You can use the **PSCredential** object that `Get-Credential` creates in cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span>

<span data-ttu-id="efb4d-199">既定では、認証プロンプトはダイアログ ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-199">By default, the authentication prompt appears in a dialog box.</span></span> <span data-ttu-id="efb4d-200">コマンドラインで認証プロンプトを表示するには、 **consoleprompting** レジストリエントリ () を追加 `HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\ConsolePrompting` し、その値を **True** に設定します。</span><span class="sxs-lookup"><span data-stu-id="efb4d-200">To display the authentication prompt at the command line, add the **ConsolePrompting** registry entry (`HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\ConsolePrompting`) and set its value to **True**.</span></span>
<span data-ttu-id="efb4d-201">**ConsolePrompting** レジストリ エントリが存在しないか、値が False に設定されている場合、認証プロンプトはダイアログ ボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-201">If the **ConsolePrompting** registry entry does not exist or if its value is False, the authentication prompt appears in a dialog box.</span></span> <span data-ttu-id="efb4d-202">手順については、例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb4d-202">For instructions, see the examples.</span></span>

<span data-ttu-id="efb4d-203">**Consoleprompting** のレジストリエントリは、PowerShell コンソールで動作しますが、すべてのホストプログラムでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="efb4d-203">The **ConsolePrompting** registry entry works in the PowerShell console, but it does not work in all host programs.</span></span>

<span data-ttu-id="efb4d-204">たとえば、PowerShell Integrated Scripting Environment (ISE) には影響しません。</span><span class="sxs-lookup"><span data-stu-id="efb4d-204">For example, it has no effect in the PowerShell Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="efb4d-205">**ConsolePrompting** レジストリ エントリの影響の詳細については、ホスト プログラムのヘルプ トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="efb4d-205">For information about the effect of the **ConsolePrompting** registry entry, see the help topics for the host program.</span></span>

<span data-ttu-id="efb4d-206">**Credential** パラメーターは、PowerShell と共にインストールされるすべてのプロバイダーでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="efb4d-206">The **Credential** parameter is not supported by all providers that are installed with PowerShell.</span></span>
<span data-ttu-id="efb4d-207">PowerShell 3.0 以降では、 `Get-Content` コマンドレットやコマンドレットなど、select コマンドレットでサポートされてい `New-PSDrive` ます。</span><span class="sxs-lookup"><span data-stu-id="efb4d-207">Beginning in PowerShell 3.0, it is supported on select cmdlets, such as the `Get-Content` and `New-PSDrive` cmdlets.</span></span>

## <span data-ttu-id="efb4d-208">関連リンク</span><span class="sxs-lookup"><span data-stu-id="efb4d-208">RELATED LINKS</span></span>

[<span data-ttu-id="efb4d-209">PromptForCredential</span><span class="sxs-lookup"><span data-stu-id="efb4d-209">PromptForCredential</span></span>](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential)
