---
description: PowerShell でスクリプトを実行および記述する方法について説明します。
Locale: en-US
ms.date: 10/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_scripts?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Scripts
ms.openlocfilehash: 2fc81d1d43b8cdddaacb917deaa5d58536a541cb
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602212"
---
# <a name="about-scripts"></a><span data-ttu-id="edeca-103">スクリプトについて</span><span class="sxs-lookup"><span data-stu-id="edeca-103">About Scripts</span></span>

## <a name="short-description"></a><span data-ttu-id="edeca-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="edeca-104">Short description</span></span>
<span data-ttu-id="edeca-105">PowerShell でスクリプトを実行および記述する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="edeca-105">Describes how to run and write scripts in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="edeca-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="edeca-106">Long description</span></span>

<span data-ttu-id="edeca-107">スクリプトは、1つまたは複数の PowerShell コマンドを含むプレーンテキストファイルです。</span><span class="sxs-lookup"><span data-stu-id="edeca-107">A script is a plain text file that contains one or more PowerShell commands.</span></span>
<span data-ttu-id="edeca-108">PowerShell スクリプトにはファイル拡張子が付いてい `.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="edeca-108">PowerShell scripts have a `.ps1` file extension.</span></span>

<span data-ttu-id="edeca-109">スクリプトの実行は、コマンドレットの実行とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="edeca-109">Running a script is a lot like running a cmdlet.</span></span> <span data-ttu-id="edeca-110">スクリプトのパスとファイル名を入力し、パラメーターを使用してデータを送信し、オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="edeca-110">You type the path and file name of the script and use parameters to submit data and set options.</span></span> <span data-ttu-id="edeca-111">スクリプトは、コンピューター上または別のコンピューター上のリモートセッションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="edeca-111">You can run scripts on your computer or in a remote session on a different computer.</span></span>

<span data-ttu-id="edeca-112">スクリプトを記述すると、後で使用できるようにコマンドが保存され、他のユーザーと簡単に共有できるようになります。</span><span class="sxs-lookup"><span data-stu-id="edeca-112">Writing a script saves a command for later use and makes it easy to share with others.</span></span> <span data-ttu-id="edeca-113">最も重要なのは、スクリプトパスとファイル名を入力するだけでコマンドを実行できることです。</span><span class="sxs-lookup"><span data-stu-id="edeca-113">Most importantly, it lets you run the commands simply by typing the script path and the filename.</span></span> <span data-ttu-id="edeca-114">スクリプトは、ファイル内の1つのコマンドとして簡単に行うことも、複雑なプログラムとして拡張することもできます。</span><span class="sxs-lookup"><span data-stu-id="edeca-114">Scripts can be as simple as a single command in a file or as extensive as a complex program.</span></span>

<span data-ttu-id="edeca-115">スクリプトには、 `#Requires` 特別なコメント、パラメーターの使用、データセクションのサポート、セキュリティのデジタル署名などの追加機能があります。</span><span class="sxs-lookup"><span data-stu-id="edeca-115">Scripts have additional features, such as the `#Requires` special comment, the use of parameters, support for data sections, and digital signing for security.</span></span>
<span data-ttu-id="edeca-116">スクリプトのヘルプトピックや関数を記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="edeca-116">You can also write Help topics for scripts and for any functions in the script.</span></span>

## <a name="how-to-run-a-script"></a><span data-ttu-id="edeca-117">スクリプトを実行する方法</span><span class="sxs-lookup"><span data-stu-id="edeca-117">How to run a script</span></span>

<span data-ttu-id="edeca-118">Windows でスクリプトを実行する前に、既定の PowerShell 実行ポリシーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edeca-118">Before you can run a script on Windows, you need to change the default PowerShell execution policy.</span></span> <span data-ttu-id="edeca-119">実行ポリシーは、Windows 以外のプラットフォームで実行されている PowerShell には適用されません。</span><span class="sxs-lookup"><span data-stu-id="edeca-119">Execution policy does not apply to PowerShell running on non-Windows platforms.</span></span>

<span data-ttu-id="edeca-120">既定の実行ポリシーでは、 `Restricted` ローカルコンピューター上に作成したスクリプトを含め、すべてのスクリプトの実行を禁止します。</span><span class="sxs-lookup"><span data-stu-id="edeca-120">The default execution policy, `Restricted`, prevents all scripts from running, including scripts that you write on the local computer.</span></span> <span data-ttu-id="edeca-121">詳細については、「[about_Execution_Policies](about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edeca-121">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="edeca-122">実行ポリシーはレジストリに保存されるため、各コンピューターで1回だけ変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edeca-122">The execution policy is saved in the registry, so you need to change it only once on each computer.</span></span>

<span data-ttu-id="edeca-123">実行ポリシーを変更するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="edeca-123">To change the execution policy, use the following procedure.</span></span>

<span data-ttu-id="edeca-124">コマンド プロンプトに、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="edeca-124">At the command prompt, type:</span></span>

```powershell
Set-ExecutionPolicy AllSigned
```

<span data-ttu-id="edeca-125">または</span><span class="sxs-lookup"><span data-stu-id="edeca-125">or</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```

<span data-ttu-id="edeca-126">変更はすぐに有効になります。</span><span class="sxs-lookup"><span data-stu-id="edeca-126">The change is effective immediately.</span></span>

<span data-ttu-id="edeca-127">スクリプトを実行するには、スクリプトファイルの完全な名前と完全なパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="edeca-127">To run a script, type the full name and the full path to the script file.</span></span>

<span data-ttu-id="edeca-128">たとえば、Get-ServiceLog.ps1 スクリプトを C:\Scripts ディレクトリで実行するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="edeca-128">For example, to run the Get-ServiceLog.ps1 script in the C:\Scripts directory, type:</span></span>

```powershell
C:\Scripts\Get-ServiceLog.ps1
```

<span data-ttu-id="edeca-129">現在のディレクトリでスクリプトを実行するには、現在のディレクトリへのパスを入力するか、ドットを使用して現在のディレクトリを表し、その後にパスバックスラッシュ () を入力し `.\` ます。</span><span class="sxs-lookup"><span data-stu-id="edeca-129">To run a script in the current directory, type the path to the current directory, or use a dot to represent the current directory, followed by a path backslash (`.\`).</span></span>

<span data-ttu-id="edeca-130">たとえば、ローカルディレクトリで ServicesLog.ps1 スクリプトを実行するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="edeca-130">For example, to run the ServicesLog.ps1 script in the local directory, type:</span></span>

```powershell
.\Get-ServiceLog.ps1
```

<span data-ttu-id="edeca-131">スクリプトにパラメーターがある場合は、スクリプトファイル名の後にパラメーターとパラメーター値を入力します。</span><span class="sxs-lookup"><span data-stu-id="edeca-131">If the script has parameters, type the parameters and parameter values after the script filename.</span></span>

<span data-ttu-id="edeca-132">たとえば、次のコマンドは、Get-ServiceLog スクリプトの ServiceName パラメーターを使用して、WinRM サービスアクティビティのログを要求します。</span><span class="sxs-lookup"><span data-stu-id="edeca-132">For example, the following command uses the ServiceName parameter of the Get-ServiceLog script to request a log of WinRM service activity.</span></span>

```powershell
.\Get-ServiceLog.ps1 -ServiceName WinRM
```

<span data-ttu-id="edeca-133">セキュリティ機能として、エクスプローラーでスクリプトアイコンをダブルクリックした場合や、スクリプトが現在のディレクトリにある場合でもスクリプト名を完全なパスなしで入力した場合、PowerShell ではスクリプトが実行されません。</span><span class="sxs-lookup"><span data-stu-id="edeca-133">As a security feature, PowerShell does not run scripts when you double-click the script icon in File Explorer or when you type the script name without a full path, even when the script is in the current directory.</span></span> <span data-ttu-id="edeca-134">PowerShell でコマンドとスクリプトを実行する方法の詳細については、「 [about_Command_Precedence](about_Command_Precedence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edeca-134">For more information about running commands and scripts in PowerShell, see [about_Command_Precedence](about_Command_Precedence.md).</span></span>

### <a name="run-with-powershell"></a><span data-ttu-id="edeca-135">PowerShell を使用しての実行</span><span class="sxs-lookup"><span data-stu-id="edeca-135">Run with PowerShell</span></span>

<span data-ttu-id="edeca-136">PowerShell 3.0 以降では、エクスプローラーからスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="edeca-136">Beginning in PowerShell 3.0, you can run scripts from File Explorer.</span></span>

<span data-ttu-id="edeca-137">"PowerShell で実行" 機能を使用するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="edeca-137">To use the "Run with PowerShell" feature:</span></span>

<span data-ttu-id="edeca-138">ファイルエクスプローラーを実行し、スクリプトファイル名を右クリックして、[PowerShell で実行] を選択します。</span><span class="sxs-lookup"><span data-stu-id="edeca-138">Run File Explorer, right-click the script filename and then select "Run with PowerShell".</span></span>

<span data-ttu-id="edeca-139">"PowerShell を使用して実行" 機能は、必要なパラメーターを持たず、コマンドプロンプトに出力を返さないスクリプトを実行するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="edeca-139">The "Run with PowerShell" feature is designed to run scripts that do not have required parameters and do not return output to the command prompt.</span></span>

<span data-ttu-id="edeca-140">詳細については、「[about_Run_With_PowerShell](about_Run_With_PowerShell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edeca-140">For more information, see [about_Run_With_PowerShell](about_Run_With_PowerShell.md).</span></span>

### <a name="running-scripts-on-other-computers"></a><span data-ttu-id="edeca-141">他のコンピューターでのスクリプトの実行</span><span class="sxs-lookup"><span data-stu-id="edeca-141">Running scripts on other computers</span></span>

<span data-ttu-id="edeca-142">1つまたは複数のリモートコンピューターでスクリプトを実行するには、コマンドレットの **FilePath** パラメーターを使用し `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="edeca-142">To run a script on one or more remote computers, use the **FilePath** parameter of the `Invoke-Command` cmdlet.</span></span>

<span data-ttu-id="edeca-143">**FilePath** パラメーターの値として、スクリプトのパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="edeca-143">Enter the path and filename of the script as the value of the **FilePath** parameter.</span></span> <span data-ttu-id="edeca-144">スクリプトは、ローカル コンピューター上か、またはローカル コンピューターがアクセスできるディレクトリ内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edeca-144">The script must reside on the local computer or in a directory that the local computer can access.</span></span>

<span data-ttu-id="edeca-145">次のコマンドは、 `Get-ServiceLog.ps1` Server01 と Server02 という名前のリモートコンピューター上でスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="edeca-145">The following command runs the `Get-ServiceLog.ps1` script on the remote computers named Server01 and Server02.</span></span>

```powershell
Invoke-Command -ComputerName Server01,Server02 -FilePath `
  C:\Scripts\Get-ServiceLog.ps1
```

## <a name="get-help-for-scripts"></a><span data-ttu-id="edeca-146">スクリプトのヘルプを取得する</span><span class="sxs-lookup"><span data-stu-id="edeca-146">Get help for scripts</span></span>

<span data-ttu-id="edeca-147">Get-Help コマンドレットは、スクリプトのヘルプトピックや、コマンドレットやその他の種類のコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="edeca-147">The Get-Help cmdlet gets the help topics for scripts as well as for cmdlets and other types of commands.</span></span> <span data-ttu-id="edeca-148">スクリプトのヘルプトピックを取得するには、 `Get-Help` スクリプトのパスとファイル名を続けて入力します。</span><span class="sxs-lookup"><span data-stu-id="edeca-148">To get the help topic for a script, type `Get-Help` followed by the path and filename of the script.</span></span> <span data-ttu-id="edeca-149">スクリプトのパスが環境変数にある場合は、 `Path` パスを省略できます。</span><span class="sxs-lookup"><span data-stu-id="edeca-149">If the script path is in your `Path` environment variable, you can omit the path.</span></span>

<span data-ttu-id="edeca-150">たとえば、ServicesLog.ps1 スクリプトのヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="edeca-150">For example, to get help for the ServicesLog.ps1 script, type:</span></span>

```powershell
get-help C:\admin\scripts\ServicesLog.ps1
```

## <a name="how-to-write-a-script"></a><span data-ttu-id="edeca-151">スクリプトを記述する方法</span><span class="sxs-lookup"><span data-stu-id="edeca-151">How to write a script</span></span>

<span data-ttu-id="edeca-152">スクリプトには、任意の有効な PowerShell コマンドを含めることができます。これには、1つのコマンド、パイプライン、関数、および If ステートメントや For ループなどの制御構造を使用するコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="edeca-152">A script can contain any valid PowerShell commands, including single commands, commands that use the pipeline, functions, and control structures such as If statements and For loops.</span></span>

<span data-ttu-id="edeca-153">スクリプトを作成するには、テキストエディターで新しいファイルを開き、コマンドを入力して、ファイル拡張子がの有効なファイル名を持つファイルに保存し `.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="edeca-153">To write a script, open a new file in a text editor, type the commands, and save them in a file with a valid filename with the `.ps1` file extension.</span></span>

<span data-ttu-id="edeca-154">次の例は、現在のシステムで実行されているサービスを取得し、ログファイルに保存する単純なスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="edeca-154">The following example is a simple script that gets the services that are running on the current system and saves them to a log file.</span></span> <span data-ttu-id="edeca-155">ログファイル名は、現在の日付から作成されます。</span><span class="sxs-lookup"><span data-stu-id="edeca-155">The log filename is created from the current date.</span></span>

```powershell
$date = (get-date).dayofyear
get-service | out-file "$date.log"
```

<span data-ttu-id="edeca-156">このスクリプトを作成するには、テキストエディターまたはスクリプトエディターを開き、これらのコマンドを入力して、という名前のファイルに保存し `ServiceLog.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="edeca-156">To create this script, open a text editor or a script editor, type these commands, and then save them in a file named `ServiceLog.ps1`.</span></span>

### <a name="parameters-in-scripts"></a><span data-ttu-id="edeca-157">スクリプトのパラメーター</span><span class="sxs-lookup"><span data-stu-id="edeca-157">Parameters in scripts</span></span>

<span data-ttu-id="edeca-158">スクリプトでパラメーターを定義するには、Param ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="edeca-158">To define parameters in a script, use a Param statement.</span></span> <span data-ttu-id="edeca-159">ステートメントは、 `Param` スクリプト内の最初のステートメントである必要があります。ただし、コメントとステートメントは除き `#Require` ます。</span><span class="sxs-lookup"><span data-stu-id="edeca-159">The `Param` statement must be the first statement in a script, except for comments and any `#Require` statements.</span></span>

<span data-ttu-id="edeca-160">スクリプトパラメーターは、関数パラメーターと同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="edeca-160">Script parameters work like function parameters.</span></span> <span data-ttu-id="edeca-161">パラメーター値は、スクリプト内のすべてのコマンドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="edeca-161">The parameter values are available to all of the commands in the script.</span></span> <span data-ttu-id="edeca-162">パラメーター属性とその名前付き引数を含む、関数パラメーターのすべての機能は、スクリプトでも有効です。</span><span class="sxs-lookup"><span data-stu-id="edeca-162">All of the features of function parameters, including the Parameter attribute and its named arguments, are also valid in scripts.</span></span>

<span data-ttu-id="edeca-163">スクリプトを実行すると、スクリプトユーザーは、スクリプト名の後にパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="edeca-163">When running the script, script users type the parameters after the script name.</span></span>

<span data-ttu-id="edeca-164">次の例は、 `Test-Remote.ps1` **ComputerName** パラメーターを持つスクリプトを示しています。</span><span class="sxs-lookup"><span data-stu-id="edeca-164">The following example shows a `Test-Remote.ps1` script that has a **ComputerName** parameter.</span></span> <span data-ttu-id="edeca-165">両方のスクリプト関数が **ComputerName** パラメーター値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="edeca-165">Both of the script functions can access the **ComputerName** parameter value.</span></span>

```powershell
param ($ComputerName = $(throw "ComputerName parameter is required."))

function CanPing {
   $error.clear()
   $tmp = test-connection $computername -erroraction SilentlyContinue

   if (!$?)
       {write-host "Ping failed: $ComputerName."; return $false}
   else
       {write-host "Ping succeeded: $ComputerName"; return $true}
}

function CanRemote {
    $s = new-pssession $computername -erroraction SilentlyContinue

    if ($s -is [System.Management.Automation.Runspaces.PSSession])
        {write-host "Remote test succeeded: $ComputerName."}
    else
        {write-host "Remote test failed: $ComputerName."}
}

if (CanPing $computername) {CanRemote $computername}
```

<span data-ttu-id="edeca-166">このスクリプトを実行するには、スクリプト名の後にパラメーター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="edeca-166">To run this script, type the parameter name after the script name.</span></span> <span data-ttu-id="edeca-167">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="edeca-167">For example:</span></span>

```powershell
C:\PS> .\test-remote.ps1 -computername Server01

Ping succeeded: Server01
Remote test failed: Server01
```

<span data-ttu-id="edeca-168">Param ステートメントと関数のパラメーターの詳細については、「 [about_Functions](about_Functions.md) 」および「 [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edeca-168">For more information about the Param statement and the function parameters, see [about_Functions](about_Functions.md) and [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="writing-help-for-scripts"></a><span data-ttu-id="edeca-169">スクリプトのヘルプの作成</span><span class="sxs-lookup"><span data-stu-id="edeca-169">Writing help for scripts</span></span>

<span data-ttu-id="edeca-170">スクリプトのヘルプトピックを作成するには、次の2つの方法のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="edeca-170">You can write a help topic for a script by using either of the two following methods:</span></span>

- <span data-ttu-id="edeca-171">スクリプトの Comment-Based ヘルプ</span><span class="sxs-lookup"><span data-stu-id="edeca-171">Comment-Based Help for Scripts</span></span>

  <span data-ttu-id="edeca-172">コメントに特殊なキーワードを使用して、ヘルプトピックを作成します。</span><span class="sxs-lookup"><span data-stu-id="edeca-172">Create a Help topic by using special keywords in the comments.</span></span> <span data-ttu-id="edeca-173">スクリプトのコメントベースのヘルプを作成するには、スクリプトファイルの先頭または末尾にコメントを配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edeca-173">To create comment-based Help for a script, the comments must be placed at the beginning or end of the script file.</span></span> <span data-ttu-id="edeca-174">コメントベースのヘルプの詳細については、「 [about_Comment_Based_Help](about_Comment_Based_Help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edeca-174">For more information about comment-based Help, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span>

- <span data-ttu-id="edeca-175">スクリプトの XML-Based ヘルプ</span><span class="sxs-lookup"><span data-stu-id="edeca-175">XML-Based Help  for Scripts</span></span>

  <span data-ttu-id="edeca-176">コマンドレットに対して通常作成される型など、XML ベースのヘルプトピックを作成します。</span><span class="sxs-lookup"><span data-stu-id="edeca-176">Create an XML-based Help topic, such as the type that is typically created for cmdlets.</span></span> <span data-ttu-id="edeca-177">ヘルプトピックを複数の言語に翻訳する場合は、XML ベースのヘルプが必要です。</span><span class="sxs-lookup"><span data-stu-id="edeca-177">XML-based Help is required if you are translating Help topics into multiple languages.</span></span>

<span data-ttu-id="edeca-178">スクリプトを XML ベースのヘルプトピックに関連付けるには、を使用します。ExternalHelp ヘルプコメントキーワード。</span><span class="sxs-lookup"><span data-stu-id="edeca-178">To associate the script with the XML-based Help topic, use the .ExternalHelp Help comment keyword.</span></span> <span data-ttu-id="edeca-179">ExternalHelp キーワードの詳細については、「 [about_Comment_Based_Help](about_Comment_Based_Help.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edeca-179">For more information about the ExternalHelp keyword, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span> <span data-ttu-id="edeca-180">XML ベースのヘルプの詳細については、「 [How To Write Cmdlet help](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edeca-180">For more information about XML-based help, see [How to Write Cmdlet Help](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

### <a name="returning-an-exit-value"></a><span data-ttu-id="edeca-181">終了値を返す</span><span class="sxs-lookup"><span data-stu-id="edeca-181">Returning an exit value</span></span>

<span data-ttu-id="edeca-182">既定では、スクリプトはスクリプトの終了時に終了状態を返しません。</span><span class="sxs-lookup"><span data-stu-id="edeca-182">By default, scripts do not return an exit status when the script ends.</span></span> <span data-ttu-id="edeca-183">`exit`スクリプトから終了コードを返すには、ステートメントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="edeca-183">You must use the `exit` statement to return an exit code from a script.</span></span> <span data-ttu-id="edeca-184">既定では、 `exit` ステートメントはを返し `0` ます。</span><span class="sxs-lookup"><span data-stu-id="edeca-184">By default, the `exit` statement returns `0`.</span></span> <span data-ttu-id="edeca-185">数値を指定すると、別の終了ステータスを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="edeca-185">You can provide a numeric value to return a different exit status.</span></span> <span data-ttu-id="edeca-186">ゼロ以外の終了コードは、通常、エラーを通知します。</span><span class="sxs-lookup"><span data-stu-id="edeca-186">A nonzero exit code typically signals a failure.</span></span>

<span data-ttu-id="edeca-187">Windows では、との間に任意の数の数値を `[int]::MinValue` `[int]::MaxValue` 指定できます。</span><span class="sxs-lookup"><span data-stu-id="edeca-187">On Windows, any number between `[int]::MinValue` and `[int]::MaxValue` is allowed.</span></span>

<span data-ttu-id="edeca-188">Unix で `[byte]::MinValue` は、(0) から (255) までの正の数値のみ `[byte]::MaxValue` が許可されます。</span><span class="sxs-lookup"><span data-stu-id="edeca-188">On Unix, only positive numbers between `[byte]::MinValue` (0) and `[byte]::MaxValue` (255) are allowed.</span></span> <span data-ttu-id="edeca-189">からまでの範囲の負の数値は、を `-1` `-255` 追加することにより、自動的に正の数値に変換されます。</span><span class="sxs-lookup"><span data-stu-id="edeca-189">A negative number in the range of `-1` through `-255` is automatically translated into a positive number by adding</span></span>
256. <span data-ttu-id="edeca-190">たとえば、 `-2` はに変換され `254` ます。</span><span class="sxs-lookup"><span data-stu-id="edeca-190">For example, `-2` is transformed to `254`.</span></span>

<span data-ttu-id="edeca-191">PowerShell では、ステートメントによって `exit` 変数の値が設定され `$LASTEXITCODE` ます。</span><span class="sxs-lookup"><span data-stu-id="edeca-191">In PowerShell, the `exit` statement sets the value of the `$LASTEXITCODE` variable.</span></span> <span data-ttu-id="edeca-192">Windows コマンドシェル (cmd.exe) では、exit ステートメントによって環境変数の値が設定され `%ERRORLEVEL%` ます。</span><span class="sxs-lookup"><span data-stu-id="edeca-192">In the Windows Command Shell (cmd.exe), the exit statement sets the value of the `%ERRORLEVEL%` environment variable.</span></span>

<span data-ttu-id="edeca-193">数値以外、またはプラットフォーム固有の範囲外の引数は、の値に変換され `0` ます。</span><span class="sxs-lookup"><span data-stu-id="edeca-193">Any argument that is non-numeric or outside the platform-specific range is translated to the value of `0`.</span></span>

## <a name="script-scope-and-dot-sourcing"></a><span data-ttu-id="edeca-194">スクリプトスコープとドットソーシング</span><span class="sxs-lookup"><span data-stu-id="edeca-194">Script scope and dot sourcing</span></span>

<span data-ttu-id="edeca-195">各スクリプトは、独自のスコープで実行されます。</span><span class="sxs-lookup"><span data-stu-id="edeca-195">Each script runs in its own scope.</span></span> <span data-ttu-id="edeca-196">スクリプトで作成された関数、変数、エイリアス、およびドライブは、スクリプトスコープにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="edeca-196">The functions, variables, aliases, and drives that are created in the script exist only in the script scope.</span></span> <span data-ttu-id="edeca-197">スクリプトが実行されているスコープ内のこれらのアイテムや値にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="edeca-197">You cannot access these items or their values in the scope in which the script runs.</span></span>

<span data-ttu-id="edeca-198">別のスコープでスクリプトを実行するには、グローバルまたはローカルなどのスコープを指定するか、スクリプトをドットソースにすることができます。</span><span class="sxs-lookup"><span data-stu-id="edeca-198">To run a script in a different scope, you can specify a scope, such as Global or Local, or you can dot source the script.</span></span>

<span data-ttu-id="edeca-199">ドットソーシング機能を使用すると、スクリプトのスコープ内ではなく、現在のスコープでスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="edeca-199">The dot sourcing feature lets you run a script in the current scope instead of in the script scope.</span></span> <span data-ttu-id="edeca-200">ドットソースのスクリプトを実行すると、スクリプト内のコマンドは、コマンドプロンプトで入力した場合と同じように実行されます。</span><span class="sxs-lookup"><span data-stu-id="edeca-200">When you run a script that is dot sourced, the commands in the script run as though you had typed them at the command prompt.</span></span> <span data-ttu-id="edeca-201">スクリプトによって作成される関数、変数、エイリアス、およびドライブは、作業中のスコープ内に作成されます。</span><span class="sxs-lookup"><span data-stu-id="edeca-201">The functions, variables, aliases, and drives that the script creates are created in the scope in which you are working.</span></span> <span data-ttu-id="edeca-202">スクリプトの実行後、作成した項目を使用して、セッションの値にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="edeca-202">After the script runs, you can use the created items and access their values in your session.</span></span>

<span data-ttu-id="edeca-203">ドットソーススクリプトを作成するには、スクリプトパスの前にドット (.) とスペースを入力します。</span><span class="sxs-lookup"><span data-stu-id="edeca-203">To dot source a script, type a dot (.) and a space before the script path.</span></span>

<span data-ttu-id="edeca-204">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="edeca-204">For example:</span></span>

```powershell
. C:\scripts\UtilityFunctions.ps1
```

<span data-ttu-id="edeca-205">or</span><span class="sxs-lookup"><span data-stu-id="edeca-205">or</span></span>

```powershell
. .\UtilityFunctions.ps1
```

<span data-ttu-id="edeca-206">スクリプトを実行すると、スクリプトによって `UtilityFunctions.ps1` 作成される関数と変数が現在のスコープに追加されます。</span><span class="sxs-lookup"><span data-stu-id="edeca-206">After the `UtilityFunctions.ps1` script runs, the functions and variables that the script creates are added to the current scope.</span></span>

<span data-ttu-id="edeca-207">たとえば、スクリプトによって `UtilityFunctions.ps1` 関数と変数が作成され `New-Profile` `$ProfileName` ます。</span><span class="sxs-lookup"><span data-stu-id="edeca-207">For example, the `UtilityFunctions.ps1` script creates the `New-Profile` function and the `$ProfileName` variable.</span></span>

```powershell
#In UtilityFunctions.ps1

function New-Profile
{
  Write-Host "Running New-Profile function"
  $profileName = split-path $profile -leaf

  if (test-path $profile)
    {write-error "Profile $profileName already exists on this computer."}
  else
    {new-item -type file -path $profile -force }
}
```

<span data-ttu-id="edeca-208">スクリプトを独自の `UtilityFunctions.ps1` スクリプトスコープで実行した場合、 `New-Profile` 関数と変数は、 `$ProfileName` スクリプトの実行中にのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="edeca-208">If you run the `UtilityFunctions.ps1` script in its own script scope, the `New-Profile` function and the `$ProfileName` variable exist only while the script is running.</span></span> <span data-ttu-id="edeca-209">スクリプトが終了すると、次の例に示すように、関数と変数が削除されます。</span><span class="sxs-lookup"><span data-stu-id="edeca-209">When the script exits, the function and variable are removed, as shown in the following example.</span></span>

```powershell
C:\PS> .\UtilityFunctions.ps1

C:\PS> New-Profile
The term 'new-profile' is not recognized as a cmdlet, function, operable
program, or script file. Verify the term and try again.
At line:1 char:12
+ new-profile <<<<
   + CategoryInfo          : ObjectNotFound: (new-profile:String) [],
   + FullyQualifiedErrorId : CommandNotFoundException

C:\PS> $profileName
C:\PS>
```

<span data-ttu-id="edeca-210">スクリプトをドットで変換して実行すると、スクリプトによって、 `New-Profile` `$ProfileName` スコープ内のセッションに関数と変数が作成されます。</span><span class="sxs-lookup"><span data-stu-id="edeca-210">When you dot source the script and run it, the script creates the `New-Profile` function and the `$ProfileName` variable in your session in your scope.</span></span> <span data-ttu-id="edeca-211">スクリプトの実行後、 `New-Profile` 次の例に示すように、関数をセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="edeca-211">After the script runs, you can use the `New-Profile` function in your session, as shown in the following example.</span></span>

```powershell
C:\PS> . .\UtilityFunctions.ps1

C:\PS> New-Profile

    Directory: C:\Users\juneb\Documents\WindowsPowerShell

    Mode    LastWriteTime     Length Name
    ----    -------------     ------ ----
    -a---   1/14/2009 3:08 PM      0 Microsoft.PowerShellISE_profile.ps1

C:\PS> $profileName
Microsoft.PowerShellISE_profile.ps1
```

<span data-ttu-id="edeca-212">スコープの詳細については、「about_Scopes」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edeca-212">For more information about scope, see about_Scopes.</span></span>

## <a name="scripts-in-modules"></a><span data-ttu-id="edeca-213">モジュール内のスクリプト</span><span class="sxs-lookup"><span data-stu-id="edeca-213">Scripts in modules</span></span>

<span data-ttu-id="edeca-214">モジュールは、一連の関連する PowerShell リソースであり、1つの単位として配布できます。</span><span class="sxs-lookup"><span data-stu-id="edeca-214">A module is a set of related PowerShell resources that can be distributed as a unit.</span></span> <span data-ttu-id="edeca-215">モジュールを使用して、スクリプト、関数、およびその他のリソースを整理することができます。</span><span class="sxs-lookup"><span data-stu-id="edeca-215">You can use modules to organize your scripts, functions, and other resources.</span></span> <span data-ttu-id="edeca-216">モジュールを使用して、コードを他のユーザーに配布したり、信頼されたソースからコードを取得したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="edeca-216">You can also use modules to distribute your code to others, and to get code from trusted sources.</span></span>

<span data-ttu-id="edeca-217">モジュールにスクリプトを含めることも、スクリプトモジュールを作成することもできます。スクリプトモジュールは、スクリプトとサポートリソースの全体または主に構成されているモジュールです。</span><span class="sxs-lookup"><span data-stu-id="edeca-217">You can include scripts in your modules, or you can create a script module, which is a module that consists entirely or primarily of a script and supporting resources.</span></span> <span data-ttu-id="edeca-218">スクリプトモジュールは、hbase-runner.psm1 ファイル拡張子を持つスクリプトにすぎません。</span><span class="sxs-lookup"><span data-stu-id="edeca-218">A script module is just a script with a .psm1 file extension.</span></span>

<span data-ttu-id="edeca-219">モジュールの詳細については、「 [about_Modules](about_Modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edeca-219">For more information about modules, see [about_Modules](about_Modules.md).</span></span>

## <a name="other-script-features"></a><span data-ttu-id="edeca-220">その他のスクリプト機能</span><span class="sxs-lookup"><span data-stu-id="edeca-220">Other script features</span></span>

<span data-ttu-id="edeca-221">PowerShell には、スクリプトで使用できる便利な機能が多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="edeca-221">PowerShell has many useful features that you can use in scripts.</span></span>

- <span data-ttu-id="edeca-222">`#Requires` -ステートメントを使用し `#Requires` て、指定されたモジュールまたはスナップインと PowerShell のバージョンが指定されていない場合にスクリプトが実行されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="edeca-222">`#Requires` - You can use a `#Requires` statement to prevent a script from running without specified modules or snap-ins and a specified version of PowerShell.</span></span> <span data-ttu-id="edeca-223">詳細については、「about_Requires」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edeca-223">For more information, see about_Requires.</span></span>

- <span data-ttu-id="edeca-224">`$PSCommandPath` -実行されているスクリプトの完全なパスと名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="edeca-224">`$PSCommandPath` - Contains the full path and name of the script that is being run.</span></span> <span data-ttu-id="edeca-225">このパラメーターは、すべてのスクリプトで有効です。</span><span class="sxs-lookup"><span data-stu-id="edeca-225">This parameter is valid in all scripts.</span></span> <span data-ttu-id="edeca-226">この自動変数は、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="edeca-226">This automatic variable is introduced in PowerShell 3.0.</span></span>

- <span data-ttu-id="edeca-227">`$PSScriptRoot` -スクリプトの実行元のディレクトリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="edeca-227">`$PSScriptRoot` - Contains the directory from which a script is being run.</span></span> <span data-ttu-id="edeca-228">PowerShell 2.0 では、この変数はスクリプトモジュール () でのみ有効です `.psm1` 。</span><span class="sxs-lookup"><span data-stu-id="edeca-228">In PowerShell 2.0, this variable is valid only in script modules (`.psm1`).</span></span>
  <span data-ttu-id="edeca-229">PowerShell 3.0 以降では、すべてのスクリプトで有効になっています。</span><span class="sxs-lookup"><span data-stu-id="edeca-229">Beginning in PowerShell 3.0, it is valid in all scripts.</span></span>

- <span data-ttu-id="edeca-230">`$MyInvocation` -自動変数には、 `$MyInvocation` 現在のスクリプトに関する情報が含まれています。これには、その開始方法や "呼び出し" に関する情報も含まれます。</span><span class="sxs-lookup"><span data-stu-id="edeca-230">`$MyInvocation` - The `$MyInvocation` automatic variable contains information about the current script, including information about how it was started or "invoked."</span></span> <span data-ttu-id="edeca-231">この変数とそのプロパティを使用して、実行中のスクリプトに関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="edeca-231">You can use this variable and its properties to get information about the script while it is running.</span></span> <span data-ttu-id="edeca-232">たとえば、のように `$MyInvocation` なります。MyCommand. Path 変数には、スクリプトのパスとファイル名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="edeca-232">For example, the `$MyInvocation`.MyCommand.Path variable contains the path and filename of the script.</span></span> <span data-ttu-id="edeca-233">`$MyInvocation`.行には、すべてのパラメーターと値を含む、スクリプトを開始したコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="edeca-233">`$MyInvocation`.Line contains the command that started the script, including all parameters and values.</span></span>

  <span data-ttu-id="edeca-234">PowerShell 3.0 以降、には、 `$MyInvocation` 現在のスクリプトを呼び出したスクリプトまたは呼び出されたスクリプトに関する情報を提供する2つの新しいプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="edeca-234">Beginning in PowerShell 3.0, `$MyInvocation` has two new properties that provide information about the script that called or invoked the current script.</span></span> <span data-ttu-id="edeca-235">これらのプロパティの値は、呼び出し元または呼び出し元がスクリプトの場合にのみ設定されます。</span><span class="sxs-lookup"><span data-stu-id="edeca-235">The values of these properties are populated only when the invoker or caller is a script.</span></span>

  - <span data-ttu-id="edeca-236">**Pscommandpath** には、現在のスクリプトを呼び出した、または呼び出されたスクリプトの完全なパスと名前が含まれています。</span><span class="sxs-lookup"><span data-stu-id="edeca-236">**PSCommandPath** contains the full path and name of the script that called or invoked the current script.</span></span>

  - <span data-ttu-id="edeca-237">**Psscriptroot** には、現在のスクリプトを呼び出した、または呼び出されたスクリプトのディレクトリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="edeca-237">**PSScriptRoot** contains the directory of the script that called or invoked the current script.</span></span>

  <span data-ttu-id="edeca-238">現在の `$PSCommandPath` `$PSScriptRoot` スクリプトに関する情報を含むおよび自動変数とは異なり、変数の **Pscommandpath** および **pscommandpath** プロパティには、 `$MyInvocation` 現在のスクリプトを呼び出したスクリプトに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="edeca-238">Unlike the `$PSCommandPath` and `$PSScriptRoot` automatic variables, which contain information about the current script, the **PSCommandPath** and **PSScriptRoot** properties of the `$MyInvocation` variable contain information about the script that called the current script.</span></span>

- <span data-ttu-id="edeca-239">データセクション-キーワードを使用して、 `Data` スクリプト内のロジックとデータを分けることができます。</span><span class="sxs-lookup"><span data-stu-id="edeca-239">Data sections - You can use the `Data` keyword to separate data from logic in scripts.</span></span> <span data-ttu-id="edeca-240">データセクションでも、ローカライズが容易になります。</span><span class="sxs-lookup"><span data-stu-id="edeca-240">Data sections can also make localization easier.</span></span> <span data-ttu-id="edeca-241">詳細については、「 [about_Data_Sections](about_Data_Sections.md) 」および「 [about_Script_Internationalization](about_Script_Internationalization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edeca-241">For more information, see [about_Data_Sections](about_Data_Sections.md) and [about_Script_Internationalization](about_Script_Internationalization.md).</span></span>

- <span data-ttu-id="edeca-242">スクリプトの署名-デジタル署名をスクリプトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="edeca-242">Script Signing - You can add a digital signature to a script.</span></span> <span data-ttu-id="edeca-243">実行ポリシーによっては、デジタル署名を使用して、安全でないコマンドを含む可能性のあるスクリプトの実行を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="edeca-243">Depending on the execution policy, you can use digital signatures to restrict the running of scripts that could include unsafe commands.</span></span> <span data-ttu-id="edeca-244">詳細については、「 [about_Execution_Policies](about_Execution_Policies.md) 」および「 [about_Signing](about_Signing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="edeca-244">For more information, see [about_Execution_Policies](about_Execution_Policies.md) and [about_Signing](about_Signing.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="edeca-245">関連項目</span><span class="sxs-lookup"><span data-stu-id="edeca-245">See also</span></span>

[<span data-ttu-id="edeca-246">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="edeca-246">about_Command_Precedence</span></span>](about_Command_Precedence.md)

[<span data-ttu-id="edeca-247">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="edeca-247">about_Comment_Based_Help</span></span>](about_Comment_Based_Help.md)

[<span data-ttu-id="edeca-248">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="edeca-248">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="edeca-249">about_Functions</span><span class="sxs-lookup"><span data-stu-id="edeca-249">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="edeca-250">about_Modules</span><span class="sxs-lookup"><span data-stu-id="edeca-250">about_Modules</span></span>](about_Modules.md)

[<span data-ttu-id="edeca-251">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="edeca-251">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="edeca-252">about_Requires</span><span class="sxs-lookup"><span data-stu-id="edeca-252">about_Requires</span></span>](about_Requires.md)

[<span data-ttu-id="edeca-253">about_Run_With_PowerShell</span><span class="sxs-lookup"><span data-stu-id="edeca-253">about_Run_With_PowerShell</span></span>](about_Run_With_PowerShell.md)

[<span data-ttu-id="edeca-254">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="edeca-254">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="edeca-255">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="edeca-255">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="edeca-256">about_Signing</span><span class="sxs-lookup"><span data-stu-id="edeca-256">about_Signing</span></span>](about_Signing.md)

[<span data-ttu-id="edeca-257">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="edeca-257">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)
