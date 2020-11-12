---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-process?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Process
ms.openlocfilehash: 75f0b0bed808efbe31254fcd04662ddef2f3a22c
ms.sourcegitcommit: aac365f7813756e16b59322832a904e703e0465b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "94524741"
---
# <span data-ttu-id="b4d1c-103">Start-Process</span><span class="sxs-lookup"><span data-stu-id="b4d1c-103">Start-Process</span></span>

## <span data-ttu-id="b4d1c-104">概要</span><span class="sxs-lookup"><span data-stu-id="b4d1c-104">SYNOPSIS</span></span>
<span data-ttu-id="b4d1c-105">ローカル コンピューター上の 1 つ以上のプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-105">Starts one or more processes on the local computer.</span></span>

## <span data-ttu-id="b4d1c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b4d1c-106">SYNTAX</span></span>

### <span data-ttu-id="b4d1c-107">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="b4d1c-107">Default (Default)</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-Credential <PSCredential>]
 [-WorkingDirectory <String>] [-LoadUserProfile] [-NoNewWindow] [-PassThru]
 [-RedirectStandardError <String>] [-RedirectStandardInput <String>]
 [-RedirectStandardOutput <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-UseNewEnvironment]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="b4d1c-108">UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="b4d1c-108">UseShellExecute</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-WorkingDirectory <String>]
 [-PassThru] [-Verb <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="b4d1c-109">Description</span><span class="sxs-lookup"><span data-stu-id="b4d1c-109">DESCRIPTION</span></span>

<span data-ttu-id="b4d1c-110">`Start-Process`コマンドレットにより、ローカルコンピューター上の1つ以上のプロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-110">The `Start-Process` cmdlet starts one or more processes on the local computer.</span></span> <span data-ttu-id="b4d1c-111">既定では、は、 `Start-Process` 現在のプロセスで定義されているすべての環境変数を継承する新しいプロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-111">By default, `Start-Process` creates a new process that inherits all the environment variables that are defined in the current process.</span></span>

<span data-ttu-id="b4d1c-112">プロセスで実行されるプログラムを指定するには、実行可能ファイルやスクリプト ファイル、またはコンピューター上のプログラムで開くことができるファイルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-112">To specify the program that runs in the process, enter an executable file or script file, or a file that can be opened by using a program on the computer.</span></span> <span data-ttu-id="b4d1c-113">実行可能ファイル以外のファイルを指定すると、は、 `Start-Process` コマンドレットと同様に、ファイルに関連付けられているプログラムを起動し `Invoke-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-113">If you specify a non-executable file, `Start-Process` starts the program that is associated with the file, similar to the `Invoke-Item` cmdlet.</span></span>

<span data-ttu-id="b4d1c-114">のパラメーターを使用し `Start-Process` て、ユーザープロファイルの読み込み、新しいウィンドウでのプロセスの開始、代替資格情報の使用などのオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-114">You can use the parameters of `Start-Process` to specify options, such as loading a user profile, starting the process in a new window, or using alternate credentials.</span></span>

## <span data-ttu-id="b4d1c-115">例</span><span class="sxs-lookup"><span data-stu-id="b4d1c-115">EXAMPLES</span></span>

### <span data-ttu-id="b4d1c-116">例 1: 既定値を使用するプロセスを開始する</span><span class="sxs-lookup"><span data-stu-id="b4d1c-116">Example 1: Start a process that uses default values</span></span>

<span data-ttu-id="b4d1c-117">この例では、現在のフォルダー内のファイルを使用するプロセスを開始 `Sort.exe` します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-117">This example starts a process that uses the `Sort.exe` file in the current folder.</span></span> <span data-ttu-id="b4d1c-118">このコマンドは、既定のウィンドウスタイル、作業フォルダー、資格情報など、すべての既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-118">The command uses all of the default values, including the default window style, working folder, and credentials.</span></span>

```powershell
Start-Process -FilePath "sort.exe"
```

### <span data-ttu-id="b4d1c-119">例 2: テキストファイルを印刷する</span><span class="sxs-lookup"><span data-stu-id="b4d1c-119">Example 2: Print a text file</span></span>

<span data-ttu-id="b4d1c-120">この例では、ファイルを出力するプロセスを開始し `C:\PS-Test\MyFile.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-120">This example starts a process that prints the `C:\PS-Test\MyFile.txt` file.</span></span>

```powershell
Start-Process -FilePath "myfile.txt" -WorkingDirectory "C:\PS-Test" -Verb Print
```

### <span data-ttu-id="b4d1c-121">例 3: 新しいファイルに項目を並べ替えるプロセスを開始する</span><span class="sxs-lookup"><span data-stu-id="b4d1c-121">Example 3: Start a process to sort items to a new file</span></span>

<span data-ttu-id="b4d1c-122">この例では、ファイル内の項目を並べ替え `Testsort.txt` 、ファイル内の並べ替えられた項目を返すプロセスを開始し `Sorted.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-122">This example starts a process that sorts items in the `Testsort.txt` file and returns the sorted items in the `Sorted.txt` files.</span></span> <span data-ttu-id="b4d1c-123">エラーはすべてファイルに書き込まれ `SortError.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-123">Any errors are written to the `SortError.txt` file.</span></span>

```powershell
Start-Process -FilePath "Sort.exe" -RedirectStandardInput "Testsort.txt" -RedirectStandardOutput "Sorted.txt" -RedirectStandardError "SortError.txt" -UseNewEnvironment
```

<span data-ttu-id="b4d1c-124">**UseNewEnvironment** パラメーターは、プロセスが独自の環境変数で実行されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-124">The **UseNewEnvironment** parameter specifies that the process runs with its own environment variables.</span></span>

### <span data-ttu-id="b4d1c-125">例 4: 最大化されるウィンドウでプロセスを開始する</span><span class="sxs-lookup"><span data-stu-id="b4d1c-125">Example 4: Start a process in a maximized window</span></span>

<span data-ttu-id="b4d1c-126">この例では、プロセスを開始 `Notepad.exe` します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-126">This example starts the `Notepad.exe` process.</span></span> <span data-ttu-id="b4d1c-127">ウィンドウが最大化されて、プロセスが完了するまでそのまま維持されます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-127">It maximizes the window and retains the window until the process completes.</span></span>

```powershell
Start-Process -FilePath "notepad" -Wait -WindowStyle Maximized
```

### <span data-ttu-id="b4d1c-128">例 5: 管理者として PowerShell を起動する</span><span class="sxs-lookup"><span data-stu-id="b4d1c-128">Example 5: Start PowerShell as an administrator</span></span>

<span data-ttu-id="b4d1c-129">この例では、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-129">This example starts PowerShell by using the **Run as administrator** option.</span></span>

```powershell
Start-Process -FilePath "powershell" -Verb RunAs
```

### <span data-ttu-id="b4d1c-130">例 6: 異なる動詞を使用してプロセスを開始する</span><span class="sxs-lookup"><span data-stu-id="b4d1c-130">Example 6: Using different verbs to start a process</span></span>

<span data-ttu-id="b4d1c-131">この例では、プロセスの開始時に使用できる動詞を検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-131">This example shows how to find the verbs that can be used when starting a process.</span></span> <span data-ttu-id="b4d1c-132">使用可能な動詞は、プロセスで実行されるファイルのファイル名拡張子によって決まります。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-132">The available verbs are determined by the filename extension of the file that runs in the process.</span></span>

```powershell
$startExe = New-Object System.Diagnostics.ProcessStartInfo -Args PowerShell.exe
$startExe.verbs
```

```Output
open
runas
runasuser
```

<span data-ttu-id="b4d1c-133">この例では、を使用して、 `New-Object` PowerShell プロセスで実行されるファイル **PowerShell.exe** の **ProcessStartInfo** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-133">The example uses `New-Object` to create a **System.Diagnostics.ProcessStartInfo** object for **PowerShell.exe** , the file that runs in the PowerShell process.</span></span> <span data-ttu-id="b4d1c-134">**ProcessStartInfo** オブジェクトの **verbs** プロパティは、、、またはファイルを実行するすべてのプロセスで **Open** 動詞と **RunAs** 動詞を使用できることを示して `PowerShell.exe` `.exe` います。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-134">The **Verbs** property of the **ProcessStartInfo** object shows that you can use the **Open** and **RunAs** verbs with `PowerShell.exe`, or with any process that runs a `.exe` file.</span></span>

### <span data-ttu-id="b4d1c-135">例 7: プロセスに引数を指定する</span><span class="sxs-lookup"><span data-stu-id="b4d1c-135">Example 7: Specifying arguments to the process</span></span>

<span data-ttu-id="b4d1c-136">どちらのコマンドも、Windows コマンドインタープリターを起動し、 `dir` フォルダーに対してコマンドを発行し `Program Files` ます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-136">Both commands start the Windows command interpreter, issuing a `dir` command on the `Program Files` folder.</span></span> <span data-ttu-id="b4d1c-137">この foldername にはスペースが含まれているため、値はエスケープされた引用符で囲まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-137">Because this foldername contains a space, the value needs surrounded with escaped quotes.</span></span>
<span data-ttu-id="b4d1c-138">最初のコマンドでは、文字列を **ArgumentList** として指定することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-138">Note that the first command specifies a string as **ArgumentList**.</span></span> <span data-ttu-id="b4d1c-139">2番目のコマンドは文字列配列です。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-139">The second command is a string array.</span></span>

```powershell
Start-Process -FilePath "$env:comspec" -ArgumentList "/c dir `"%systemdrive%\program files`""
Start-Process -FilePath "$env:comspec" -ArgumentList "/c","dir","`"%systemdrive%\program files`""
```

### <span data-ttu-id="b4d1c-140">例 8: デタッチされたプロセスを Linux で作成する</span><span class="sxs-lookup"><span data-stu-id="b4d1c-140">Example 8: Create a detached process on Linux</span></span>

<span data-ttu-id="b4d1c-141">Windows では、は、 `Start-Process` 起動中のシェルとは無関係に実行される独立したプロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-141">On Windows, `Start-Process` creates an independent process that remains running independently of the launching shell.</span></span> <span data-ttu-id="b4d1c-142">Windows 以外のプラットフォームでは、新しく起動されたプロセスは、を起動したシェルにアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-142">On non-Windows platforms, the newly started process is attached to the shell that launched.</span></span> <span data-ttu-id="b4d1c-143">起動中のシェルを閉じると、子プロセスは終了します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-143">If the launching shell is closed, the child process is terminated.</span></span>

<span data-ttu-id="b4d1c-144">Unix のようなプラットフォームで子プロセスを終了しないようにするには、とを組み合わせることができ `Start-Process` `nohup` ます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-144">To avoid terminating the child process on Unix-like platforms, you can combine `Start-Process` with `nohup`.</span></span> <span data-ttu-id="b4d1c-145">次の例では、起動中のセッションを閉じた後でも、Linux で PowerShell のバックグラウンドインスタンスを起動して、そのままにします。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-145">The following example launches a background instance of PowerShell on Linux that stays alive even after you close the launching session.</span></span> <span data-ttu-id="b4d1c-146">コマンドは、 `nohup` 現在のディレクトリ内のファイルの出力を収集し `nohup.out` ます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-146">The `nohup` command collects output in file `nohup.out` in the current directory.</span></span>

```powershell
# Runs for 2 minutes and appends output to ./nohup.out
Start-Process nohup 'pwsh -noprofile -c "1..120 | % { Write-Host . -NoNewline; sleep 1 }"'
```

<span data-ttu-id="b4d1c-147">この例で `Start-Process` は、は、デタッチされ `nohup` `pwsh` たプロセスとして起動する Linux コマンドを実行しています。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-147">In this example, `Start-Process` is running the Linux `nohup` command, which launches `pwsh` as a detached process.</span></span> <span data-ttu-id="b4d1c-148">詳細については、 [nohup](https://linux.die.net/man/1/nohup)の man ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-148">For more information, see the man page for [nohup](https://linux.die.net/man/1/nohup).</span></span>

## <span data-ttu-id="b4d1c-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b4d1c-149">PARAMETERS</span></span>

### <span data-ttu-id="b4d1c-150">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="b4d1c-150">-ArgumentList</span></span>

<span data-ttu-id="b4d1c-151">このコマンドレットでプロセスを開始するときに使用するパラメーターまたはパラメーター値を指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-151">Specifies parameters or parameter values to use when this cmdlet starts the process.</span></span> <span data-ttu-id="b4d1c-152">引数は、スペースで区切られた1つの文字列として、またはコンマで区切られた文字列の配列として受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-152">Arguments can be accepted as a single string with the arguments separated by spaces, or as an array of strings separated by commas.</span></span>

<span data-ttu-id="b4d1c-153">パラメーターまたはパラメーターの値にスペースが含まれている場合は、エスケープされた二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-153">If parameters or parameter values contain a space, they need to be surrounded with escaped double quotes.</span></span> <span data-ttu-id="b4d1c-154">詳細については、「 [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-154">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b4d1c-155">-Credential</span><span class="sxs-lookup"><span data-stu-id="b4d1c-155">-Credential</span></span>

<span data-ttu-id="b4d1c-156">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-156">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="b4d1c-157">既定では、コマンドレットは現在のユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-157">By default, the cmdlet uses the credentials of the current user.</span></span>

<span data-ttu-id="b4d1c-158">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-158">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="b4d1c-159">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-159">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="b4d1c-160">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-160">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="b4d1c-161">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-161">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Default
Aliases: RunAs

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b4d1c-162">-FilePath</span><span class="sxs-lookup"><span data-stu-id="b4d1c-162">-FilePath</span></span>

<span data-ttu-id="b4d1c-163">プロセスで実行されるプログラムのパスとファイル名 (省略可能) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-163">Specifies the optional path and filename of the program that runs in the process.</span></span> <span data-ttu-id="b4d1c-164">`.txt` `.doc` コンピューター上のプログラムに関連付けられている実行可能ファイルまたはドキュメント (やファイルなど) の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-164">Enter the name of an executable file or of a document, such as a `.txt` or `.doc` file, that is associated with a program on the computer.</span></span> <span data-ttu-id="b4d1c-165">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-165">This parameter is required.</span></span>

<span data-ttu-id="b4d1c-166">ファイル名のみを指定する場合は、 **WorkingDirectory** パラメーターを使用してパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-166">If you specify only a filename, use the **WorkingDirectory** parameter to specify the path.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath, Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b4d1c-167">-Processmodel.loaduserprofile</span><span class="sxs-lookup"><span data-stu-id="b4d1c-167">-LoadUserProfile</span></span>

<span data-ttu-id="b4d1c-168">このコマンドレットにより、 `HKEY_USERS` 現在のユーザーのレジストリキーに格納されている Windows ユーザープロファイルが読み込まれることを示します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-168">Indicates that this cmdlet loads the Windows user profile stored in the `HKEY_USERS` registry key for the current user.</span></span> <span data-ttu-id="b4d1c-169">このパラメーターは、Windows 以外のシステムには適用されません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-169">The parameter does not apply for non-Windows systems.</span></span>

<span data-ttu-id="b4d1c-170">このパラメーターは、PowerShell プロファイルには影響しません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-170">This parameter does not affect the PowerShell profiles.</span></span> <span data-ttu-id="b4d1c-171">詳細については、「 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-171">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: Lup

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b4d1c-172">-None Wwindow</span><span class="sxs-lookup"><span data-stu-id="b4d1c-172">-NoNewWindow</span></span>

<span data-ttu-id="b4d1c-173">現在のコンソール ウィンドウで新しいプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-173">Start the new process in the current console window.</span></span> <span data-ttu-id="b4d1c-174">Windows の既定では、PowerShell によって新しいウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-174">By default on Windows, PowerShell opens a new window.</span></span> <span data-ttu-id="b4d1c-175">Windows 以外のシステムでは、新しいターミナルウィンドウは表示されません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-175">On non-Windows systems, you never get a new terminal window.</span></span>

<span data-ttu-id="b4d1c-176">**NoNewWindow** と **WindowStyle** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-176">You cannot use the **NoNewWindow** and **WindowStyle** parameters in the same command.</span></span>

<span data-ttu-id="b4d1c-177">このパラメーターは、Windows 以外のシステムには適用されません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-177">The parameter does not apply for non-Windows systems.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases: nnw

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b4d1c-178">-PassThru</span><span class="sxs-lookup"><span data-stu-id="b4d1c-178">-PassThru</span></span>

<span data-ttu-id="b4d1c-179">コマンドレットが開始した各プロセスのプロセス オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-179">Returns a process object for each process that the cmdlet started.</span></span> <span data-ttu-id="b4d1c-180">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-180">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="b4d1c-181">-RedirectStandardError</span><span class="sxs-lookup"><span data-stu-id="b4d1c-181">-RedirectStandardError</span></span>

<span data-ttu-id="b4d1c-182">ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-182">Specifies a file.</span></span> <span data-ttu-id="b4d1c-183">このコマンドレットは、プロセスによって生成されたすべてのエラーを、指定したファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-183">This cmdlet sends any errors generated by the process to a file that you specify.</span></span>
<span data-ttu-id="b4d1c-184">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-184">Enter the path and filename.</span></span> <span data-ttu-id="b4d1c-185">既定では、エラーはコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-185">By default, the errors are displayed in the console.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSE

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b4d1c-186">-RedirectStandardInput</span><span class="sxs-lookup"><span data-stu-id="b4d1c-186">-RedirectStandardInput</span></span>

<span data-ttu-id="b4d1c-187">ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-187">Specifies a file.</span></span> <span data-ttu-id="b4d1c-188">このコマンドレットは、指定されたファイルから入力を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-188">This cmdlet reads input from the specified file.</span></span> <span data-ttu-id="b4d1c-189">入力ファイルのパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-189">Enter the path and filename of the input file.</span></span> <span data-ttu-id="b4d1c-190">既定では、入力はキーボードから取得されます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-190">By default, the process gets its input from the keyboard.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b4d1c-191">-RedirectStandardOutput</span><span class="sxs-lookup"><span data-stu-id="b4d1c-191">-RedirectStandardOutput</span></span>

<span data-ttu-id="b4d1c-192">ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-192">Specifies a file.</span></span> <span data-ttu-id="b4d1c-193">このコマンドレットは、プロセスによって生成された出力を、指定したファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-193">This cmdlet sends the output generated by the process to a file that you specify.</span></span>
<span data-ttu-id="b4d1c-194">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-194">Enter the path and filename.</span></span> <span data-ttu-id="b4d1c-195">既定では、出力はコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-195">By default, the output is displayed in the console.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases: RSO

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b4d1c-196">-UseNewEnvironment</span><span class="sxs-lookup"><span data-stu-id="b4d1c-196">-UseNewEnvironment</span></span>

<span data-ttu-id="b4d1c-197">このコマンドレットが、プロセスに対して指定された新しい環境変数を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-197">Indicates that this cmdlet uses new environment variables specified for the process.</span></span> <span data-ttu-id="b4d1c-198">既定では、開始されたプロセスは、親プロセスから継承された環境変数を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-198">By default, the started process runs with the environment variables inherited from the parent process.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Default
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b4d1c-199">-動詞</span><span class="sxs-lookup"><span data-stu-id="b4d1c-199">-Verb</span></span>

<span data-ttu-id="b4d1c-200">このコマンドレットがプロセスを開始するときに使用する動詞を指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-200">Specifies a verb to use when this cmdlet starts the process.</span></span> <span data-ttu-id="b4d1c-201">使用可能な動詞は、プロセスで実行されるファイルのファイル名拡張子によって決まります。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-201">The verbs that are available are determined by the filename extension of the file that runs in the process.</span></span>

<span data-ttu-id="b4d1c-202">次の表に、いくつかの一般的なプロセス ファイルの種類の動詞を示します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-202">The following table shows the verbs for some common process file types.</span></span>

| <span data-ttu-id="b4d1c-203">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="b4d1c-203">File type</span></span> |                <span data-ttu-id="b4d1c-204">動詞</span><span class="sxs-lookup"><span data-stu-id="b4d1c-204">Verbs</span></span>                |
| --------- | ----------------------------------- |
| <span data-ttu-id="b4d1c-205">.cmd</span><span class="sxs-lookup"><span data-stu-id="b4d1c-205">.cmd</span></span>      | <span data-ttu-id="b4d1c-206">Edit、Open、Print、RunAs、RunAsUser</span><span class="sxs-lookup"><span data-stu-id="b4d1c-206">Edit, Open, Print, RunAs, RunAsUser</span></span> |
| <span data-ttu-id="b4d1c-207">.exe</span><span class="sxs-lookup"><span data-stu-id="b4d1c-207">.exe</span></span>      | <span data-ttu-id="b4d1c-208">Open、RunAs、RunAsUser</span><span class="sxs-lookup"><span data-stu-id="b4d1c-208">Open, RunAs, RunAsUser</span></span>              |
| <span data-ttu-id="b4d1c-209">.txt</span><span class="sxs-lookup"><span data-stu-id="b4d1c-209">.txt</span></span>      | <span data-ttu-id="b4d1c-210">Open、Print、PrintTo</span><span class="sxs-lookup"><span data-stu-id="b4d1c-210">Open, Print, PrintTo</span></span>                |
| <span data-ttu-id="b4d1c-211">.wav</span><span class="sxs-lookup"><span data-stu-id="b4d1c-211">.wav</span></span>      | <span data-ttu-id="b4d1c-212">開く、再生</span><span class="sxs-lookup"><span data-stu-id="b4d1c-212">Open, Play</span></span>                          |

<span data-ttu-id="b4d1c-213">プロセスで実行されるファイルと共に使用できる動詞を検索するには、コマンドレットを使用して、 `New-Object` ファイルの **ProcessStartInfo** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-213">To find the verbs that can be used with the file that runs in a process, use the `New-Object` cmdlet to create a **System.Diagnostics.ProcessStartInfo** object for the file.</span></span> <span data-ttu-id="b4d1c-214">使用可能な動詞は、 **ProcessStartInfo** オブジェクトの **verb** プロパティにあります。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-214">The available verbs are in the **Verbs** property of the **ProcessStartInfo** object.</span></span> <span data-ttu-id="b4d1c-215">詳細については、例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-215">For details, see the examples.</span></span>

<span data-ttu-id="b4d1c-216">このパラメーターは、Windows 以外のシステムには適用されません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-216">The parameter does not apply for non-Windows systems.</span></span>

```yaml
Type: System.String
Parameter Sets: UseShellExecute
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b4d1c-217">-Wait</span><span class="sxs-lookup"><span data-stu-id="b4d1c-217">-Wait</span></span>

<span data-ttu-id="b4d1c-218">このコマンドレットが、指定されたプロセスとその子孫が完了するまで待機してから、より多くの入力を受け入れることを示します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-218">Indicates that this cmdlet waits for the specified process and its descendants to complete before accepting more input.</span></span> <span data-ttu-id="b4d1c-219">このパラメーターを指定すると、コマンドプロンプトが表示されなくなるか、またはプロセスが終了するまでウィンドウが保持されます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-219">This parameter suppresses the command prompt or retains the window until the processes finish.</span></span>

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

### <span data-ttu-id="b4d1c-220">-WindowStyle</span><span class="sxs-lookup"><span data-stu-id="b4d1c-220">-WindowStyle</span></span>

<span data-ttu-id="b4d1c-221">新しいプロセスに使用するウィンドウの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-221">Specifies the state of the window that is used for the new process.</span></span> <span data-ttu-id="b4d1c-222">このパラメーターに指定できる値は、 **Normal** 、 **Hidden** 、 **最小化** 、および **最大化** です。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-222">The acceptable values for this parameter are: **Normal** , **Hidden** , **Minimized** , and **Maximized**.</span></span> <span data-ttu-id="b4d1c-223">既定値は **Normal** です。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-223">The default value is **Normal**.</span></span>

<span data-ttu-id="b4d1c-224">**WindowStyle** と **NoNewWindow** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-224">You cannot use the **WindowStyle** and **NoNewWindow** parameters in the same command.</span></span>

<span data-ttu-id="b4d1c-225">このパラメーターは、Windows 以外のシステムには適用されません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-225">The parameter does not apply for non-Windows systems.</span></span>

```yaml
Type: System.Diagnostics.ProcessWindowStyle
Parameter Sets: (All)
Aliases:
Accepted values: Normal, Hidden, Minimized, Maximized

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b4d1c-226">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="b4d1c-226">-WorkingDirectory</span></span>

<span data-ttu-id="b4d1c-227">新しいプロセスを開始する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-227">Specifies the location that the new process should start in.</span></span> <span data-ttu-id="b4d1c-228">既定値は、開始する実行可能ファイルまたはドキュメントの場所です。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-228">The default is the location of the executable file or document being started.</span></span> <span data-ttu-id="b4d1c-229">ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-229">Wildcards are not supported.</span></span> <span data-ttu-id="b4d1c-230">パス名には、ワイルドカードとして解釈される文字を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-230">The path name must not contain characters that would be interpreted as wildcards.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b4d1c-231">-Confirm</span><span class="sxs-lookup"><span data-stu-id="b4d1c-231">-Confirm</span></span>

<span data-ttu-id="b4d1c-232">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-232">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b4d1c-233">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="b4d1c-233">-WhatIf</span></span>

<span data-ttu-id="b4d1c-234">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-234">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="b4d1c-235">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-235">The cmdlet is not run.</span></span>

<span data-ttu-id="b4d1c-236">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-236">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b4d1c-237">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b4d1c-237">CommonParameters</span></span>

<span data-ttu-id="b4d1c-238">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-238">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b4d1c-239">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-239">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b4d1c-240">入力</span><span class="sxs-lookup"><span data-stu-id="b4d1c-240">INPUTS</span></span>

### <span data-ttu-id="b4d1c-241">なし</span><span class="sxs-lookup"><span data-stu-id="b4d1c-241">None</span></span>

<span data-ttu-id="b4d1c-242">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-242">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="b4d1c-243">出力</span><span class="sxs-lookup"><span data-stu-id="b4d1c-243">OUTPUTS</span></span>

### <span data-ttu-id="b4d1c-244">なし、システム。診断プロセス</span><span class="sxs-lookup"><span data-stu-id="b4d1c-244">None, System.Diagnostics.Process</span></span>

<span data-ttu-id="b4d1c-245">**PassThru** パラメーターを指定した場合、このコマンドレット **では、system.string オブジェクトが** 生成されます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-245">This cmdlet generates a **System.Diagnostics.Process** object, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="b4d1c-246">それ以外の場合、このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-246">Otherwise, this cmdlet does not return any output.</span></span>

## <span data-ttu-id="b4d1c-247">注</span><span class="sxs-lookup"><span data-stu-id="b4d1c-247">NOTES</span></span>

- <span data-ttu-id="b4d1c-248">このコマンドレットは、 **system.servicemodel クラスの** **Start** メソッドを使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-248">This cmdlet is implemented by using the **Start** method of the **System.Diagnostics.Process** class.</span></span> <span data-ttu-id="b4d1c-249">このメソッドの詳細については、「 [Process. Start メソッド](/dotnet/api/system.diagnostics.process.start#overloads)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-249">For more information about this method, see [Process.Start Method](/dotnet/api/system.diagnostics.process.start#overloads).</span></span>

- <span data-ttu-id="b4d1c-250">Windows では、 **UseNewEnvironment** を使用すると、新しいプロセスは、 **マシン** スコープに対して定義されている既定の環境変数のみを含むように開始されます。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-250">On Windows, when you use **UseNewEnvironment** , the new process starts only containing the default environment variables defined for the **Machine** scope.</span></span> <span data-ttu-id="b4d1c-251">これにより、 `$env:USERNAME` が **システム** に設定されているという副作用があります。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-251">This has the side affect that the `$env:USERNAME` is set to **SYSTEM**.</span></span> <span data-ttu-id="b4d1c-252">**ユーザー** スコープの変数は含まれません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-252">None of the variables from the **User** scope are included.</span></span>

- <span data-ttu-id="b4d1c-253">Windows では、の最も一般的なユースケース `Start-Process` は、新しいプロセスが終了するまで、 **Wait** パラメーターを使用して進行状況をブロックすることです。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-253">On Windows, the most common use case for `Start-Process` is to use the **Wait** parameter to block progress until the new process exits.</span></span> <span data-ttu-id="b4d1c-254">Windows 以外のシステムでは、コマンドラインアプリケーションの既定の動作はと同じであるため、これはほとんど必要あり `Start-Process -Wait` ません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-254">On non-Windows system, this is rarely needed since the default behavior for command-line applications is equivalent to `Start-Process -Wait`.</span></span>

- <span data-ttu-id="b4d1c-255">Windows 以外のシステムでを使用する場合 `Start-Process` 、新しいターミナルウィンドウは表示されません。</span><span class="sxs-lookup"><span data-stu-id="b4d1c-255">When using `Start-Process` on non-Windows systems, you never get a new terminal window.</span></span>

## <span data-ttu-id="b4d1c-256">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b4d1c-256">RELATED LINKS</span></span>

[<span data-ttu-id="b4d1c-257">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="b4d1c-257">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="b4d1c-258">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="b4d1c-258">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="b4d1c-259">Get-Process</span><span class="sxs-lookup"><span data-stu-id="b4d1c-259">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="b4d1c-260">Start-Service</span><span class="sxs-lookup"><span data-stu-id="b4d1c-260">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="b4d1c-261">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="b4d1c-261">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="b4d1c-262">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="b4d1c-262">Wait-Process</span></span>](Wait-Process.md)
