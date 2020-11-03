---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 08/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-process?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Process
ms.openlocfilehash: b6147b35a8818cf448b1e23f5458550d1c6e5c50
ms.sourcegitcommit: 4fc8cf397cb725ae973751d1d5d542f34f0db2d7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2020
ms.locfileid: "93219056"
---
# <span data-ttu-id="aee9b-103">Start-Process</span><span class="sxs-lookup"><span data-stu-id="aee9b-103">Start-Process</span></span>

## <span data-ttu-id="aee9b-104">概要</span><span class="sxs-lookup"><span data-stu-id="aee9b-104">SYNOPSIS</span></span>
<span data-ttu-id="aee9b-105">ローカル コンピューター上の 1 つ以上のプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-105">Starts one or more processes on the local computer.</span></span>

## <span data-ttu-id="aee9b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aee9b-106">SYNTAX</span></span>

### <span data-ttu-id="aee9b-107">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="aee9b-107">Default (Default)</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-Credential <PSCredential>]
 [-WorkingDirectory <String>] [-LoadUserProfile] [-NoNewWindow] [-PassThru]
 [-RedirectStandardError <String>] [-RedirectStandardInput <String>]
 [-RedirectStandardOutput <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [-UseNewEnvironment]
 [<CommonParameters>]
```

### <span data-ttu-id="aee9b-108">UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="aee9b-108">UseShellExecute</span></span>

```
Start-Process [-FilePath] <String> [[-ArgumentList] <String[]>] [-WorkingDirectory <String>]
 [-PassThru] [-Verb <String>] [-WindowStyle <ProcessWindowStyle>] [-Wait] [<CommonParameters>]
```

## <span data-ttu-id="aee9b-109">Description</span><span class="sxs-lookup"><span data-stu-id="aee9b-109">DESCRIPTION</span></span>

<span data-ttu-id="aee9b-110">`Start-Process`コマンドレットにより、ローカルコンピューター上の1つ以上のプロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-110">The `Start-Process` cmdlet starts one or more processes on the local computer.</span></span> <span data-ttu-id="aee9b-111">既定では、は、 `Start-Process` 現在のプロセスで定義されているすべての環境変数を継承する新しいプロセスを作成します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-111">By default, `Start-Process` creates a new process that inherits all the environment variables that are defined in the current process.</span></span>

<span data-ttu-id="aee9b-112">プロセスで実行されるプログラムを指定するには、実行可能ファイルやスクリプト ファイル、またはコンピューター上のプログラムで開くことができるファイルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-112">To specify the program that runs in the process, enter an executable file or script file, or a file that can be opened by using a program on the computer.</span></span> <span data-ttu-id="aee9b-113">実行可能ファイル以外のファイルを指定すると、は、 `Start-Process` コマンドレットと同様に、ファイルに関連付けられているプログラムを起動し `Invoke-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-113">If you specify a non-executable file, `Start-Process` starts the program that is associated with the file, similar to the `Invoke-Item` cmdlet.</span></span>

<span data-ttu-id="aee9b-114">のパラメーターを使用し `Start-Process` て、ユーザープロファイルの読み込み、新しいウィンドウでのプロセスの開始、代替資格情報の使用などのオプションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-114">You can use the parameters of `Start-Process` to specify options, such as loading a user profile, starting the process in a new window, or using alternate credentials.</span></span>

## <span data-ttu-id="aee9b-115">例</span><span class="sxs-lookup"><span data-stu-id="aee9b-115">EXAMPLES</span></span>

### <span data-ttu-id="aee9b-116">例 1: 既定値を使用するプロセスを開始する</span><span class="sxs-lookup"><span data-stu-id="aee9b-116">Example 1: Start a process that uses default values</span></span>

<span data-ttu-id="aee9b-117">この例では、現在のフォルダー内のファイルを使用するプロセスを開始 `Sort.exe` します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-117">This example starts a process that uses the `Sort.exe` file in the current folder.</span></span> <span data-ttu-id="aee9b-118">このコマンドは、既定のウィンドウスタイル、作業フォルダー、資格情報など、すべての既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-118">The command uses all of the default values, including the default window style, working folder, and credentials.</span></span>

```powershell
Start-Process -FilePath "sort.exe"
```

### <span data-ttu-id="aee9b-119">例 2: テキストファイルを印刷する</span><span class="sxs-lookup"><span data-stu-id="aee9b-119">Example 2: Print a text file</span></span>

<span data-ttu-id="aee9b-120">この例では、ファイルを出力するプロセスを開始し `C:\PS-Test\MyFile.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-120">This example starts a process that prints the `C:\PS-Test\MyFile.txt` file.</span></span>

```powershell
Start-Process -FilePath "myfile.txt" -WorkingDirectory "C:\PS-Test" -Verb Print
```

### <span data-ttu-id="aee9b-121">例 3: 新しいファイルに項目を並べ替えるプロセスを開始する</span><span class="sxs-lookup"><span data-stu-id="aee9b-121">Example 3: Start a process to sort items to a new file</span></span>

<span data-ttu-id="aee9b-122">この例では、ファイル内の項目を並べ替え `Testsort.txt` 、ファイル内の並べ替えられた項目を返すプロセスを開始し `Sorted.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-122">This example starts a process that sorts items in the `Testsort.txt` file and returns the sorted items in the `Sorted.txt` files.</span></span> <span data-ttu-id="aee9b-123">エラーはすべてファイルに書き込まれ `SortError.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-123">Any errors are written to the `SortError.txt` file.</span></span>

```powershell
Start-Process -FilePath "Sort.exe" -RedirectStandardInput "Testsort.txt" -RedirectStandardOutput "Sorted.txt" -RedirectStandardError "SortError.txt" -UseNewEnvironment
```

<span data-ttu-id="aee9b-124">**UseNewEnvironment** パラメーターは、プロセスが独自の環境変数で実行されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-124">The **UseNewEnvironment** parameter specifies that the process runs with its own environment variables.</span></span>

### <span data-ttu-id="aee9b-125">例 4: 最大化されるウィンドウでプロセスを開始する</span><span class="sxs-lookup"><span data-stu-id="aee9b-125">Example 4: Start a process in a maximized window</span></span>

<span data-ttu-id="aee9b-126">この例では、プロセスを開始 `Notepad.exe` します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-126">This example starts the `Notepad.exe` process.</span></span> <span data-ttu-id="aee9b-127">ウィンドウが最大化されて、プロセスが完了するまでそのまま維持されます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-127">It maximizes the window and retains the window until the process completes.</span></span>

```powershell
Start-Process -FilePath "notepad" -Wait -WindowStyle Maximized
```

### <span data-ttu-id="aee9b-128">例 5: 管理者として PowerShell を起動する</span><span class="sxs-lookup"><span data-stu-id="aee9b-128">Example 5: Start PowerShell as an administrator</span></span>

<span data-ttu-id="aee9b-129">この例では、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-129">This example starts PowerShell by using the **Run as administrator** option.</span></span>

```powershell
Start-Process -FilePath "powershell" -Verb RunAs
```

### <span data-ttu-id="aee9b-130">例 6: 異なる動詞を使用してプロセスを開始する</span><span class="sxs-lookup"><span data-stu-id="aee9b-130">Example 6: Using different verbs to start a process</span></span>

<span data-ttu-id="aee9b-131">この例では、プロセスの開始時に使用できる動詞を検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-131">This example shows how to find the verbs that can be used when starting a process.</span></span> <span data-ttu-id="aee9b-132">使用可能な動詞は、プロセスで実行されるファイルのファイル名拡張子によって決まります。</span><span class="sxs-lookup"><span data-stu-id="aee9b-132">The available verbs are determined by the filename extension of the file that runs in the process.</span></span>

```powershell
$startExe = New-Object System.Diagnostics.ProcessStartInfo -Args PowerShell.exe
$startExe.verbs
```

```Output
open
runas
runasuser
```

<span data-ttu-id="aee9b-133">この例では、を使用して、 `New-Object` PowerShell プロセスで実行されるファイル **PowerShell.exe** の **ProcessStartInfo** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-133">The example uses `New-Object` to create a **System.Diagnostics.ProcessStartInfo** object for **PowerShell.exe** , the file that runs in the PowerShell process.</span></span> <span data-ttu-id="aee9b-134">**ProcessStartInfo** オブジェクトの **verbs** プロパティは、、、またはファイルを実行するすべてのプロセスで **Open** 動詞と **RunAs** 動詞を使用できることを示して `PowerShell.exe` `.exe` います。</span><span class="sxs-lookup"><span data-stu-id="aee9b-134">The **Verbs** property of the **ProcessStartInfo** object shows that you can use the **Open** and **RunAs** verbs with `PowerShell.exe`, or with any process that runs a `.exe` file.</span></span>

### <span data-ttu-id="aee9b-135">例 7: プロセスに引数を指定する</span><span class="sxs-lookup"><span data-stu-id="aee9b-135">Example 7: Specifying arguments to the process</span></span>

<span data-ttu-id="aee9b-136">どちらのコマンドも、Windows コマンドインタープリターを起動し、 `dir` フォルダーに対してコマンドを発行し `Program Files` ます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-136">Both commands start the Windows command interpreter, issuing a `dir` command on the `Program Files` folder.</span></span> <span data-ttu-id="aee9b-137">この foldername にはスペースが含まれているため、値はエスケープされた引用符で囲まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="aee9b-137">Because this foldername contains a space, the value needs surrounded with escaped quotes.</span></span>
<span data-ttu-id="aee9b-138">最初のコマンドでは、文字列を **ArgumentList** として指定することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="aee9b-138">Note that the first command specifies a string as **ArgumentList**.</span></span> <span data-ttu-id="aee9b-139">2番目のコマンドは文字列配列です。</span><span class="sxs-lookup"><span data-stu-id="aee9b-139">The second command is a string array.</span></span>

```powershell
Start-Process -FilePath "$env:comspec" -ArgumentList "/c dir `"%systemdrive%\program files`""
Start-Process -FilePath "$env:comspec" -ArgumentList "/c","dir","`"%systemdrive%\program files`""
```

## <span data-ttu-id="aee9b-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aee9b-140">PARAMETERS</span></span>

### <span data-ttu-id="aee9b-141">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="aee9b-141">-ArgumentList</span></span>

<span data-ttu-id="aee9b-142">このコマンドレットでプロセスを開始するときに使用するパラメーターまたはパラメーター値を指定します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-142">Specifies parameters or parameter values to use when this cmdlet starts the process.</span></span> <span data-ttu-id="aee9b-143">引数は、スペースで区切られた1つの文字列として、またはコンマで区切られた文字列の配列として受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-143">Arguments can be accepted as a single string with the arguments separated by spaces, or as an array of strings separated by commas.</span></span>

<span data-ttu-id="aee9b-144">パラメーターまたはパラメーターの値にスペースが含まれている場合は、エスケープされた二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="aee9b-144">If parameters or parameter values contain a space, they need to be surrounded with escaped double quotes.</span></span> <span data-ttu-id="aee9b-145">詳細については、「 [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee9b-145">For more information, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="aee9b-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="aee9b-146">-Credential</span></span>

<span data-ttu-id="aee9b-147">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-147">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="aee9b-148">既定では、コマンドレットは現在のユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-148">By default, the cmdlet uses the credentials of the current user.</span></span>

<span data-ttu-id="aee9b-149">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-149">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="aee9b-150">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-150">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="aee9b-151">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-151">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="aee9b-152">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee9b-152">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="aee9b-153">-FilePath</span><span class="sxs-lookup"><span data-stu-id="aee9b-153">-FilePath</span></span>

<span data-ttu-id="aee9b-154">プロセスで実行されるプログラムのパスとファイル名 (省略可能) を指定します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-154">Specifies the optional path and filename of the program that runs in the process.</span></span> <span data-ttu-id="aee9b-155">`.txt` `.doc` コンピューター上のプログラムに関連付けられている実行可能ファイルまたはドキュメント (やファイルなど) の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-155">Enter the name of an executable file or of a document, such as a `.txt` or `.doc` file, that is associated with a program on the computer.</span></span> <span data-ttu-id="aee9b-156">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="aee9b-156">This parameter is required.</span></span>

<span data-ttu-id="aee9b-157">ファイル名のみを指定する場合は、 **WorkingDirectory** パラメーターを使用してパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-157">If you specify only a filename, use the **WorkingDirectory** parameter to specify the path.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="aee9b-158">-Processmodel.loaduserprofile</span><span class="sxs-lookup"><span data-stu-id="aee9b-158">-LoadUserProfile</span></span>

<span data-ttu-id="aee9b-159">このコマンドレットにより、 `HKEY_USERS` 現在のユーザーのレジストリキーに格納されている Windows ユーザープロファイルが読み込まれることを示します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-159">Indicates that this cmdlet loads the Windows user profile stored in the `HKEY_USERS` registry key for the current user.</span></span>

<span data-ttu-id="aee9b-160">このパラメーターは、PowerShell プロファイルには影響しません。</span><span class="sxs-lookup"><span data-stu-id="aee9b-160">This parameter does not affect the PowerShell profiles.</span></span> <span data-ttu-id="aee9b-161">詳細については、「 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee9b-161">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

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

### <span data-ttu-id="aee9b-162">-None Wwindow</span><span class="sxs-lookup"><span data-stu-id="aee9b-162">-NoNewWindow</span></span>

<span data-ttu-id="aee9b-163">現在のコンソール ウィンドウで新しいプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-163">Start the new process in the current console window.</span></span> <span data-ttu-id="aee9b-164">既定では、PowerShell によって新しいウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-164">By default PowerShell opens a new window.</span></span>

<span data-ttu-id="aee9b-165">**NoNewWindow** と **WindowStyle** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="aee9b-165">You cannot use the **NoNewWindow** and **WindowStyle** parameters in the same command.</span></span>

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

### <span data-ttu-id="aee9b-166">-PassThru</span><span class="sxs-lookup"><span data-stu-id="aee9b-166">-PassThru</span></span>

<span data-ttu-id="aee9b-167">コマンドレットが開始した各プロセスのプロセス オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-167">Returns a process object for each process that the cmdlet started.</span></span> <span data-ttu-id="aee9b-168">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="aee9b-168">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="aee9b-169">-RedirectStandardError</span><span class="sxs-lookup"><span data-stu-id="aee9b-169">-RedirectStandardError</span></span>

<span data-ttu-id="aee9b-170">ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-170">Specifies a file.</span></span> <span data-ttu-id="aee9b-171">このコマンドレットは、プロセスによって生成されたすべてのエラーを、指定したファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-171">This cmdlet sends any errors generated by the process to a file that you specify.</span></span>
<span data-ttu-id="aee9b-172">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-172">Enter the path and filename.</span></span> <span data-ttu-id="aee9b-173">既定では、エラーはコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-173">By default, the errors are displayed in the console.</span></span>

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

### <span data-ttu-id="aee9b-174">-RedirectStandardInput</span><span class="sxs-lookup"><span data-stu-id="aee9b-174">-RedirectStandardInput</span></span>

<span data-ttu-id="aee9b-175">ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-175">Specifies a file.</span></span> <span data-ttu-id="aee9b-176">このコマンドレットは、指定されたファイルから入力を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="aee9b-176">This cmdlet reads input from the specified file.</span></span> <span data-ttu-id="aee9b-177">入力ファイルのパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-177">Enter the path and filename of the input file.</span></span> <span data-ttu-id="aee9b-178">既定では、入力はキーボードから取得されます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-178">By default, the process gets its input from the keyboard.</span></span>

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

### <span data-ttu-id="aee9b-179">-RedirectStandardOutput</span><span class="sxs-lookup"><span data-stu-id="aee9b-179">-RedirectStandardOutput</span></span>

<span data-ttu-id="aee9b-180">ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-180">Specifies a file.</span></span> <span data-ttu-id="aee9b-181">このコマンドレットは、プロセスによって生成された出力を、指定したファイルに送信します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-181">This cmdlet sends the output generated by the process to a file that you specify.</span></span>
<span data-ttu-id="aee9b-182">パスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-182">Enter the path and filename.</span></span> <span data-ttu-id="aee9b-183">既定では、出力はコンソールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-183">By default, the output is displayed in the console.</span></span>

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

### <span data-ttu-id="aee9b-184">-UseNewEnvironment</span><span class="sxs-lookup"><span data-stu-id="aee9b-184">-UseNewEnvironment</span></span>

<span data-ttu-id="aee9b-185">このコマンドレットが、プロセスに対して指定された新しい環境変数を使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-185">Indicates that this cmdlet uses new environment variables specified for the process.</span></span> <span data-ttu-id="aee9b-186">既定では、開始されたプロセスは、親プロセスから継承された環境変数を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-186">By default, the started process runs with the environment variables inherited from the parent process.</span></span>

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

### <span data-ttu-id="aee9b-187">-動詞</span><span class="sxs-lookup"><span data-stu-id="aee9b-187">-Verb</span></span>

<span data-ttu-id="aee9b-188">このコマンドレットがプロセスを開始するときに使用する動詞を指定します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-188">Specifies a verb to use when this cmdlet starts the process.</span></span> <span data-ttu-id="aee9b-189">使用可能な動詞は、プロセスで実行されるファイルのファイル名拡張子によって決まります。</span><span class="sxs-lookup"><span data-stu-id="aee9b-189">The verbs that are available are determined by the filename extension of the file that runs in the process.</span></span>

<span data-ttu-id="aee9b-190">次の表に、いくつかの一般的なプロセス ファイルの種類の動詞を示します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-190">The following table shows the verbs for some common process file types.</span></span>

| <span data-ttu-id="aee9b-191">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="aee9b-191">File type</span></span> |                <span data-ttu-id="aee9b-192">動詞</span><span class="sxs-lookup"><span data-stu-id="aee9b-192">Verbs</span></span>                |
| --------- | ----------------------------------- |
| <span data-ttu-id="aee9b-193">.cmd</span><span class="sxs-lookup"><span data-stu-id="aee9b-193">.cmd</span></span>      | <span data-ttu-id="aee9b-194">Edit、Open、Print、RunAs、RunAsUser</span><span class="sxs-lookup"><span data-stu-id="aee9b-194">Edit, Open, Print, RunAs, RunAsUser</span></span> |
| <span data-ttu-id="aee9b-195">.exe</span><span class="sxs-lookup"><span data-stu-id="aee9b-195">.exe</span></span>      | <span data-ttu-id="aee9b-196">Open、RunAs、RunAsUser</span><span class="sxs-lookup"><span data-stu-id="aee9b-196">Open, RunAs, RunAsUser</span></span>              |
| <span data-ttu-id="aee9b-197">.txt</span><span class="sxs-lookup"><span data-stu-id="aee9b-197">.txt</span></span>      | <span data-ttu-id="aee9b-198">Open、Print、PrintTo</span><span class="sxs-lookup"><span data-stu-id="aee9b-198">Open, Print, PrintTo</span></span>                |
| <span data-ttu-id="aee9b-199">.wav</span><span class="sxs-lookup"><span data-stu-id="aee9b-199">.wav</span></span>      | <span data-ttu-id="aee9b-200">開く、再生</span><span class="sxs-lookup"><span data-stu-id="aee9b-200">Open, Play</span></span>                          |

<span data-ttu-id="aee9b-201">プロセスで実行されるファイルと共に使用できる動詞を検索するには、コマンドレットを使用して、 `New-Object` ファイルの **ProcessStartInfo** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-201">To find the verbs that can be used with the file that runs in a process, use the `New-Object` cmdlet to create a **System.Diagnostics.ProcessStartInfo** object for the file.</span></span> <span data-ttu-id="aee9b-202">使用可能な動詞は、 **ProcessStartInfo** オブジェクトの **verb** プロパティにあります。</span><span class="sxs-lookup"><span data-stu-id="aee9b-202">The available verbs are in the **Verbs** property of the **ProcessStartInfo** object.</span></span> <span data-ttu-id="aee9b-203">詳細については、例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee9b-203">For details, see the examples.</span></span>

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

### <span data-ttu-id="aee9b-204">-Wait</span><span class="sxs-lookup"><span data-stu-id="aee9b-204">-Wait</span></span>

<span data-ttu-id="aee9b-205">このコマンドレットが、指定されたプロセスとその子孫が完了するまで待機してから、より多くの入力を受け入れることを示します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-205">Indicates that this cmdlet waits for the specified process and its descendants to complete before accepting more input.</span></span> <span data-ttu-id="aee9b-206">このパラメーターを指定すると、コマンドプロンプトが表示されなくなるか、またはプロセスが終了するまでウィンドウが保持されます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-206">This parameter suppresses the command prompt or retains the window until the processes finish.</span></span>

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

### <span data-ttu-id="aee9b-207">-WindowStyle</span><span class="sxs-lookup"><span data-stu-id="aee9b-207">-WindowStyle</span></span>

<span data-ttu-id="aee9b-208">新しいプロセスに使用するウィンドウの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-208">Specifies the state of the window that is used for the new process.</span></span> <span data-ttu-id="aee9b-209">このパラメーターに指定できる値は、 **Normal** 、 **Hidden** 、 **最小化** 、および **最大化** です。</span><span class="sxs-lookup"><span data-stu-id="aee9b-209">The acceptable values for this parameter are: **Normal** , **Hidden** , **Minimized** , and **Maximized**.</span></span> <span data-ttu-id="aee9b-210">既定値は **Normal** です。</span><span class="sxs-lookup"><span data-stu-id="aee9b-210">The default value is **Normal**.</span></span>

<span data-ttu-id="aee9b-211">**WindowStyle** と **NoNewWindow** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="aee9b-211">You cannot use the **WindowStyle** and **NoNewWindow** parameters in the same command.</span></span>

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

### <span data-ttu-id="aee9b-212">-WorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="aee9b-212">-WorkingDirectory</span></span>

<span data-ttu-id="aee9b-213">新しいプロセスを開始する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="aee9b-213">Specifies the location that the new process should start in.</span></span> <span data-ttu-id="aee9b-214">既定値は、開始する実行可能ファイルまたはドキュメントの場所です。</span><span class="sxs-lookup"><span data-stu-id="aee9b-214">The default is the location of the executable file or document being started.</span></span> <span data-ttu-id="aee9b-215">ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="aee9b-215">Wildcards are not supported.</span></span> <span data-ttu-id="aee9b-216">パス名には、ワイルドカードとして解釈される文字を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="aee9b-216">The path name must not contain characters that would be interpreted as wildcards.</span></span>

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

### <span data-ttu-id="aee9b-217">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="aee9b-217">CommonParameters</span></span>

<span data-ttu-id="aee9b-218">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="aee9b-218">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aee9b-219">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee9b-219">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="aee9b-220">入力</span><span class="sxs-lookup"><span data-stu-id="aee9b-220">INPUTS</span></span>

### <span data-ttu-id="aee9b-221">なし</span><span class="sxs-lookup"><span data-stu-id="aee9b-221">None</span></span>

<span data-ttu-id="aee9b-222">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="aee9b-222">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="aee9b-223">出力</span><span class="sxs-lookup"><span data-stu-id="aee9b-223">OUTPUTS</span></span>

### <span data-ttu-id="aee9b-224">なし、システム。診断プロセス</span><span class="sxs-lookup"><span data-stu-id="aee9b-224">None, System.Diagnostics.Process</span></span>

<span data-ttu-id="aee9b-225">**PassThru** パラメーターを指定した場合、このコマンドレット **では、system.string オブジェクトが** 生成されます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-225">This cmdlet generates a **System.Diagnostics.Process** object, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="aee9b-226">それ以外の場合、このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="aee9b-226">Otherwise, this cmdlet does not return any output.</span></span>

## <span data-ttu-id="aee9b-227">注</span><span class="sxs-lookup"><span data-stu-id="aee9b-227">NOTES</span></span>

- <span data-ttu-id="aee9b-228">このコマンドレットは、 **system.servicemodel クラスの** **Start** メソッドを使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-228">This cmdlet is implemented by using the **Start** method of the **System.Diagnostics.Process** class.</span></span> <span data-ttu-id="aee9b-229">このメソッドの詳細については、「 [Process. Start メソッド](/dotnet/api/system.diagnostics.process.start#overloads)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee9b-229">For more information about this method, see [Process.Start Method](/dotnet/api/system.diagnostics.process.start#overloads).</span></span>

- <span data-ttu-id="aee9b-230">Windows では、 **UseNewEnvironment** を使用すると、新しいプロセスは、 **マシン** スコープに対して定義されている既定の環境変数のみを含むように開始されます。</span><span class="sxs-lookup"><span data-stu-id="aee9b-230">On Windows, when you use **UseNewEnvironment** , the new process starts only containing the default environment variables defined for the **Machine** scope.</span></span> <span data-ttu-id="aee9b-231">これにより、 `$env:USERNAME` が **システム** に設定されているという副作用があります。</span><span class="sxs-lookup"><span data-stu-id="aee9b-231">This has the side affect that the `$env:USERNAME` is set to **SYSTEM**.</span></span> <span data-ttu-id="aee9b-232">**ユーザー** スコープの変数は含まれません。</span><span class="sxs-lookup"><span data-stu-id="aee9b-232">None of the variables from the **User** scope are included.</span></span>

## <span data-ttu-id="aee9b-233">関連リンク</span><span class="sxs-lookup"><span data-stu-id="aee9b-233">RELATED LINKS</span></span>

[<span data-ttu-id="aee9b-234">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="aee9b-234">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="aee9b-235">Debug-Process</span><span class="sxs-lookup"><span data-stu-id="aee9b-235">Debug-Process</span></span>](Debug-Process.md)

[<span data-ttu-id="aee9b-236">Get-Process</span><span class="sxs-lookup"><span data-stu-id="aee9b-236">Get-Process</span></span>](Get-Process.md)

[<span data-ttu-id="aee9b-237">Start-Service</span><span class="sxs-lookup"><span data-stu-id="aee9b-237">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="aee9b-238">Stop-Process</span><span class="sxs-lookup"><span data-stu-id="aee9b-238">Stop-Process</span></span>](Stop-Process.md)

[<span data-ttu-id="aee9b-239">Wait-Process</span><span class="sxs-lookup"><span data-stu-id="aee9b-239">Wait-Process</span></span>](Wait-Process.md)
