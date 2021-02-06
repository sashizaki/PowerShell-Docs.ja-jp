---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 10/23/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-credential?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Credential
ms.openlocfilehash: 5630c4d09a2806eb117d005466d4925c1740d3a7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602754"
---
# <span data-ttu-id="64be5-102">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="64be5-102">Get-Credential</span></span>

## <span data-ttu-id="64be5-103">概要</span><span class="sxs-lookup"><span data-stu-id="64be5-103">SYNOPSIS</span></span>
<span data-ttu-id="64be5-104">ユーザー名とパスワードに基づいて資格情報オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="64be5-104">Gets a credential object based on a user name and password.</span></span>

## <span data-ttu-id="64be5-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="64be5-105">SYNTAX</span></span>

### <span data-ttu-id="64be5-106">CredentialSet (既定)</span><span class="sxs-lookup"><span data-stu-id="64be5-106">CredentialSet (Default)</span></span>

```
Get-Credential [[-Credential] <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="64be5-107">MessageSet</span><span class="sxs-lookup"><span data-stu-id="64be5-107">MessageSet</span></span>

```
Get-Credential [-Message <String>] [[-UserName] <String>] [-Title <String>] [<CommonParameters>]
```

## <span data-ttu-id="64be5-108">Description</span><span class="sxs-lookup"><span data-stu-id="64be5-108">DESCRIPTION</span></span>

<span data-ttu-id="64be5-109">コマンドレットでは、 `Get-Credential` 指定されたユーザー名とパスワードの資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="64be5-109">The `Get-Credential` cmdlet creates a credential object for a specified user name and password.</span></span> <span data-ttu-id="64be5-110">作成した資格情報オブジェクトは、セキュリティ操作で使用できます。</span><span class="sxs-lookup"><span data-stu-id="64be5-110">You can use the credential object in security operations.</span></span>

<span data-ttu-id="64be5-111">`Get-Credential`コマンドレットは、パスワードまたはユーザー名とパスワードの入力をユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="64be5-111">The `Get-Credential` cmdlet prompts the user for a password or a user name and password.</span></span> <span data-ttu-id="64be5-112">**Message** パラメーターを使用すると、コマンドラインプロンプトでカスタマイズされたメッセージを指定できます。</span><span class="sxs-lookup"><span data-stu-id="64be5-112">You can use the **Message** parameter to specify a customized message in the command line prompt.</span></span>

## <span data-ttu-id="64be5-113">例</span><span class="sxs-lookup"><span data-stu-id="64be5-113">EXAMPLES</span></span>

### <span data-ttu-id="64be5-114">例 1</span><span class="sxs-lookup"><span data-stu-id="64be5-114">Example 1</span></span>

```powershell
$c = Get-Credential
```

<span data-ttu-id="64be5-115">このコマンドは、資格情報オブジェクトを取得し、変数に保存し `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="64be5-115">This command gets a credential object and saves it in the `$c` variable.</span></span>

<span data-ttu-id="64be5-116">コマンドを入力すると、ユーザー名とパスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="64be5-116">When you enter the command, you are prompted for a user name and password.</span></span> <span data-ttu-id="64be5-117">要求された情報を入力すると、コマンドレットは、ユーザーの資格情報を表す **PSCredential** オブジェクトを作成し、変数に保存し `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="64be5-117">When you enter the requested information, the cmdlet creates a **PSCredential** object representing the credentials of the user and saves it in the `$c` variable.</span></span>

<span data-ttu-id="64be5-118">このオブジェクトは、**Credential** パラメーターを持つコマンドレットなど、ユーザー認証を必要とするコマンドレットへの入力として使用できます。</span><span class="sxs-lookup"><span data-stu-id="64be5-118">You can use the object as input to cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span> <span data-ttu-id="64be5-119">ただし、PowerShell でインストールされる一部のプロバイダーでは、 **Credential** パラメーターはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="64be5-119">However, some providers that are installed with PowerShell do not support the **Credential** parameter.</span></span>

### <span data-ttu-id="64be5-120">例 2</span><span class="sxs-lookup"><span data-stu-id="64be5-120">Example 2</span></span>

```powershell
$c = Get-Credential
Get-CimInstance Win32_DiskDrive -ComputerName Server01 -Credential $c
```

<span data-ttu-id="64be5-121">これらのコマンドは、Windows Management Instrumentation (WMI) を使用してコンピューターを管理できるように、コマンドレットから返される資格情報オブジェクトを使用して `Get-Credential` リモートコンピューター上のユーザーを認証します。</span><span class="sxs-lookup"><span data-stu-id="64be5-121">These commands use a credential object that the `Get-Credential` cmdlet returns to authenticate a user on a remote computer so they can use Windows Management Instrumentation (WMI) to manage the computer.</span></span>

<span data-ttu-id="64be5-122">最初のコマンドは、資格情報オブジェクトを取得し、変数に保存し `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="64be5-122">The first command gets a credential object and saves it in the `$c` variable.</span></span> <span data-ttu-id="64be5-123">2番目のコマンドは、コマンドで credential オブジェクトを使用し `Get-CimInstance` ます。</span><span class="sxs-lookup"><span data-stu-id="64be5-123">The second command uses the credential object in a `Get-CimInstance` command.</span></span> <span data-ttu-id="64be5-124">このコマンドは、Server01 コンピューターのディスク ドライブに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="64be5-124">This command gets information about the disk drives on the Server01 computer.</span></span>

### <span data-ttu-id="64be5-125">例 3</span><span class="sxs-lookup"><span data-stu-id="64be5-125">Example 3</span></span>

```powershell
Get-CimInstance Win32_BIOS -ComputerName Server01 -Credential (Get-Credential -Credential Domain01\User01)
```

<span data-ttu-id="64be5-126">このコマンドは、コマンドにコマンドを含める方法を示して `Get-Credential`  `Get-CimInstance` います。</span><span class="sxs-lookup"><span data-stu-id="64be5-126">This command shows how to include a `Get-Credential` command in a  `Get-CimInstance` command.</span></span>

<span data-ttu-id="64be5-127">このコマンドは、コマンドレットを使用して、 `Get-CimInstance` Server01 コンピューター上の BIOS に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="64be5-127">This command uses the `Get-CimInstance` cmdlet to get information about the BIOS on the Server01 computer.</span></span> <span data-ttu-id="64be5-128">**Credential パラメーターを** 使用し `Get-Credential` て、 **credential** パラメーターの値として user、domain01\user01」、および command を認証します。</span><span class="sxs-lookup"><span data-stu-id="64be5-128">It uses the **Credential** parameter to authenticate the user, Domain01\User01, and a `Get-Credential` command as the value of the **Credential** parameter.</span></span>

### <span data-ttu-id="64be5-129">例 4</span><span class="sxs-lookup"><span data-stu-id="64be5-129">Example 4</span></span>

```powershell
$c = Get-Credential -credential User01
$c.Username
User01
```

<span data-ttu-id="64be5-130">この例では、ドメイン名なしのユーザー名を含む資格情報を作成しています。</span><span class="sxs-lookup"><span data-stu-id="64be5-130">This example creates a credential that includes a user name without a domain name.</span></span>

<span data-ttu-id="64be5-131">最初のコマンドは、ユーザー名が User01 の資格情報を取得し、変数に格納し `$c` ます。</span><span class="sxs-lookup"><span data-stu-id="64be5-131">The first command gets a credential with the user name User01 and stores it in the `$c` variable.</span></span>
<span data-ttu-id="64be5-132">2 番目のコマンドは、結果として得られる資格情報オブジェクトの **Username** プロパティの値を表示します。</span><span class="sxs-lookup"><span data-stu-id="64be5-132">The second command displays the value of the **Username** property of the resulting credential object.</span></span>

### <span data-ttu-id="64be5-133">例 5</span><span class="sxs-lookup"><span data-stu-id="64be5-133">Example 5</span></span>

```powershell
$Credential = $host.ui.PromptForCredential("Need credentials", "Please enter your user name and password.", "", "NetBiosUserName")
```

<span data-ttu-id="64be5-134">このコマンドは、 **PromptForCredential** メソッドを使用して、ユーザーにユーザー名とパスワードを入力するよう求めます。</span><span class="sxs-lookup"><span data-stu-id="64be5-134">This command uses the **PromptForCredential** method to prompt the user for their user name and password.</span></span> <span data-ttu-id="64be5-135">このコマンドは、結果として得られる資格情報を変数に保存し `$Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="64be5-135">The command saves the resulting credentials in the `$Credential` variable.</span></span>

<span data-ttu-id="64be5-136">**Promptforcredential** メソッドは、コマンドレットを使用する代わりに使用し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="64be5-136">The **PromptForCredential** method is an alternative to using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="64be5-137">**Promptforcredential** を使用する場合は、プロンプトに表示されるキャプション、メッセージ、およびユーザー名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="64be5-137">When you use **PromptForCredential**, you can specify the caption, messages, and user name that appear in the prompt.</span></span>

<span data-ttu-id="64be5-138">詳細については、SDK の [Promptforcredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64be5-138">For more information, see the [PromptForCredential](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential) documentation in the SDK.</span></span>

### <span data-ttu-id="64be5-139">例 6</span><span class="sxs-lookup"><span data-stu-id="64be5-139">Example 6</span></span>

<span data-ttu-id="64be5-140">この例では、ユーザーにメッセージを表示せずにを返すオブジェクトと同じ資格情報オブジェクトを作成する方法を示し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="64be5-140">This example shows how to create a credential object that is identical to the object that `Get-Credential` returns without prompting the user.</span></span> <span data-ttu-id="64be5-141">このメソッドではプレーンテキスト パスワードが必要ですが、企業によってはセキュリティ標準に違反する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="64be5-141">This method requires a plain text password, which might violate the security standards in some enterprises.</span></span>

```powershell
$User = "Domain01\User01"
$PWord = ConvertTo-SecureString -String "P@sSwOrd" -AsPlainText -Force
$Credential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList $User, $PWord
```

<span data-ttu-id="64be5-142">最初のコマンドは、ユーザーアカウント名をパラメーターに保存し `$User` ます。</span><span class="sxs-lookup"><span data-stu-id="64be5-142">The first command saves the user account name in the `$User` parameter.</span></span> <span data-ttu-id="64be5-143">この値は、"Domain\User" または "ComputerName\User" の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="64be5-143">The value must have the "Domain\User" or "ComputerName\User" format.</span></span>

<span data-ttu-id="64be5-144">2番目のコマンドは、コマンドレットを使用して、 `ConvertTo-SecureString` プレーンテキストパスワードからセキュリティで保護された文字列を作成します。</span><span class="sxs-lookup"><span data-stu-id="64be5-144">The second command uses the `ConvertTo-SecureString` cmdlet to create a secure string from a plain text password.</span></span> <span data-ttu-id="64be5-145">このコマンドは、**AsPlainText** パラメーターを使用して、文字列がプレーンテキストであることを示します。また、**Force** パラメーターを使用して、プレーンテキストの使用に伴うリスクを理解しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="64be5-145">The command uses the **AsPlainText** parameter to indicate that the string is plain text and the **Force** parameter to confirm that you understand the risks of using plain text.</span></span>

<span data-ttu-id="64be5-146">3番目のコマンドは、コマンドレットを使用して、 `New-Object` 変数と変数の値から **PSCredential** オブジェクトを作成し `$User` `$PWord` ます。</span><span class="sxs-lookup"><span data-stu-id="64be5-146">The third command uses the `New-Object` cmdlet to create a **PSCredential** object from the values in the `$User` and `$PWord` variables.</span></span>

### <span data-ttu-id="64be5-147">例 7</span><span class="sxs-lookup"><span data-stu-id="64be5-147">Example 7</span></span>

```powershell
Get-Credential -Message "Credential are required for access to the \\Server1\Scripts file share." -User Server01\PowerUser
```

```Output
PowerShell Credential Request
Credential are required for access to the \\Server1\Scripts file share.
Password for user Server01\PowerUser:
```

<span data-ttu-id="64be5-148">このコマンドは、コマンドレットの **Message** パラメーターと **UserName** パラメーターを使用し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="64be5-148">This command uses the **Message** and **UserName** parameters of the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="64be5-149">このコマンド形式は、共有スクリプトおよび共有関数向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="64be5-149">This command format is designed for shared scripts and functions.</span></span> <span data-ttu-id="64be5-150">この例では、メッセージはユーザーに、資格情報が必要な理由を伝え、要求が正当であるという安心感を与えています。</span><span class="sxs-lookup"><span data-stu-id="64be5-150">In this case, the message tells the user why credentials are needed and gives them confidence that the request is legitimate.</span></span>

### <span data-ttu-id="64be5-151">例 8</span><span class="sxs-lookup"><span data-stu-id="64be5-151">Example 8</span></span>

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

<span data-ttu-id="64be5-152">このコマンドは、Server01 リモート コンピューターから資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="64be5-152">This command gets a credential from the Server01 remote computer.</span></span> <span data-ttu-id="64be5-153">コマンドは、コマンドレットを使用して、 `Invoke-Command` `Get-Credential` リモートコンピューター上でコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="64be5-153">The command uses the `Invoke-Command` cmdlet to run a `Get-Credential` command on the remote computer.</span></span> <span data-ttu-id="64be5-154">出力には、認証プロンプトに含まれるリモートセキュリティメッセージが表示され `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="64be5-154">The output shows the remote security message that `Get-Credential` includes in the authentication prompt.</span></span>

## <span data-ttu-id="64be5-155">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="64be5-155">PARAMETERS</span></span>

### <span data-ttu-id="64be5-156">-Credential</span><span class="sxs-lookup"><span data-stu-id="64be5-156">-Credential</span></span>

<span data-ttu-id="64be5-157">**User01** や **domain01\user01」** など、資格情報のユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="64be5-157">Specifies a user name for the credential, such as **User01** or **Domain01\User01**.</span></span> <span data-ttu-id="64be5-158">パラメーター名は `-Credential` 省略可能です。</span><span class="sxs-lookup"><span data-stu-id="64be5-158">The parameter name, `-Credential`, is optional.</span></span>

<span data-ttu-id="64be5-159">コマンドを送信し、ユーザー名を指定すると、パスワードの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="64be5-159">When you submit the command and specify a user name, you're prompted for a password.</span></span> <span data-ttu-id="64be5-160">このパラメーターを省略すると、ユーザー名とパスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="64be5-160">If you omit this parameter, you're prompted for a user name and a password.</span></span>

<span data-ttu-id="64be5-161">PowerShell 3.0 以降では、ドメインを使用せずにユーザー名を入力すると、 `Get-Credential` 名前の前に円記号が挿入されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="64be5-161">Starting in PowerShell 3.0, if you enter a user name without a domain, `Get-Credential` no longer inserts a backslash before the name.</span></span>

<span data-ttu-id="64be5-162">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="64be5-162">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="64be5-163">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64be5-163">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: CredentialSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64be5-164">-メッセージ</span><span class="sxs-lookup"><span data-stu-id="64be5-164">-Message</span></span>

<span data-ttu-id="64be5-165">認証プロンプトに表示されるメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="64be5-165">Specifies a message that appears in the authentication prompt.</span></span> <span data-ttu-id="64be5-166">このパラメーターは、関数またはスクリプトで使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="64be5-166">This parameter is designed for use in a function or script.</span></span> <span data-ttu-id="64be5-167">メッセージを使用して、資格情報が必要な理由と使用方法をユーザーに説明できます。</span><span class="sxs-lookup"><span data-stu-id="64be5-167">You can use the message to explain to the user why you are requesting credentials and how they will be used.</span></span>

<span data-ttu-id="64be5-168">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="64be5-168">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64be5-169">-Title</span><span class="sxs-lookup"><span data-stu-id="64be5-169">-Title</span></span>

<span data-ttu-id="64be5-170">コンソールで認証プロンプトのタイトル行のテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="64be5-170">Sets the text of the title line for the authentication prompt in the console.</span></span>

<span data-ttu-id="64be5-171">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="64be5-171">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String
Parameter Sets: MessageSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="64be5-172">-UserName</span><span class="sxs-lookup"><span data-stu-id="64be5-172">-UserName</span></span>

<span data-ttu-id="64be5-173">ユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="64be5-173">Specifies a user name.</span></span> <span data-ttu-id="64be5-174">認証プロンプトで、ユーザー名に対応するパスワードの入力が要求されます。</span><span class="sxs-lookup"><span data-stu-id="64be5-174">The authentication prompt requests a password for the user name.</span></span> <span data-ttu-id="64be5-175">既定では、ユーザー名は空白で、認証プロンプトでユーザー名とパスワードの両方が要求されます。</span><span class="sxs-lookup"><span data-stu-id="64be5-175">By default, the user name is blank and the authentication prompt requests both a user name and password.</span></span>

<span data-ttu-id="64be5-176">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="64be5-176">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="64be5-177">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="64be5-177">CommonParameters</span></span>

<span data-ttu-id="64be5-178">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="64be5-178">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="64be5-179">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64be5-179">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="64be5-180">入力</span><span class="sxs-lookup"><span data-stu-id="64be5-180">INPUTS</span></span>

### <span data-ttu-id="64be5-181">なし</span><span class="sxs-lookup"><span data-stu-id="64be5-181">None</span></span>

<span data-ttu-id="64be5-182">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="64be5-182">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="64be5-183">出力</span><span class="sxs-lookup"><span data-stu-id="64be5-183">OUTPUTS</span></span>

### <span data-ttu-id="64be5-184">システム.... PSCredential</span><span class="sxs-lookup"><span data-stu-id="64be5-184">System.Management.Automation.PSCredential</span></span>

<span data-ttu-id="64be5-185">`Get-Credential` 資格情報オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="64be5-185">`Get-Credential` returns a credential object.</span></span>

## <span data-ttu-id="64be5-186">注</span><span class="sxs-lookup"><span data-stu-id="64be5-186">NOTES</span></span>

<span data-ttu-id="64be5-187"> `Get-Credential` ユーザー認証を要求するコマンドレットでを作成する PSCredential オブジェクトを使用できます。たとえば、 **Credential** パラメーターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="64be5-187">You can use the **PSCredential** object that `Get-Credential` creates in cmdlets that request user authentication, such as those with a **Credential** parameter.</span></span>

<span data-ttu-id="64be5-188">**Credential** パラメーターは、PowerShell と共にインストールされるすべてのプロバイダーでサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="64be5-188">The **Credential** parameter is not supported by all providers that are installed with PowerShell.</span></span>
<span data-ttu-id="64be5-189">PowerShell 3.0 以降では、 `Get-Content` コマンドレットやコマンドレットなど、select コマンドレットでサポートされてい `New-PSDrive` ます。</span><span class="sxs-lookup"><span data-stu-id="64be5-189">Beginning in PowerShell 3.0, it is supported on select cmdlets, such as the `Get-Content` and `New-PSDrive` cmdlets.</span></span>

## <span data-ttu-id="64be5-190">関連リンク</span><span class="sxs-lookup"><span data-stu-id="64be5-190">RELATED LINKS</span></span>

[<span data-ttu-id="64be5-191">PromptForCredential</span><span class="sxs-lookup"><span data-stu-id="64be5-191">PromptForCredential</span></span>](/dotnet/api/system.management.automation.host.pshostuserinterface.promptforcredential)
