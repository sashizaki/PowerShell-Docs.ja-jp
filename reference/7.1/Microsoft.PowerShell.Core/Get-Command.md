---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-command?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Command
ms.openlocfilehash: 60b6d2e380685650a86f74056a992afb4051ddc1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217728"
---
# <span data-ttu-id="85c5a-103">Get-Command</span><span class="sxs-lookup"><span data-stu-id="85c5a-103">Get-Command</span></span>

## <span data-ttu-id="85c5a-104">概要</span><span class="sxs-lookup"><span data-stu-id="85c5a-104">SYNOPSIS</span></span>
<span data-ttu-id="85c5a-105">すべてのコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-105">Gets all commands.</span></span>

## <span data-ttu-id="85c5a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="85c5a-106">SYNTAX</span></span>

### <span data-ttu-id="85c5a-107">設定します (既定)。</span><span class="sxs-lookup"><span data-stu-id="85c5a-107">CmdletSet (Default)</span></span>

```
Get-Command [-Verb <String[]>] [-Noun <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-TotalCount <Int32>] [-Syntax] [-ShowCommandInfo]
 [[-ArgumentList] <Object[]>] [-All] [-ListImported] [-ParameterName <String[]>]
 [-ParameterType <PSTypeName[]>] [<CommonParameters>]
```

### <span data-ttu-id="85c5a-108">AllCommandSet</span><span class="sxs-lookup"><span data-stu-id="85c5a-108">AllCommandSet</span></span>

```
Get-Command [[-Name] <String[]>] [-Module <String[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [-CommandType <CommandTypes>] [-TotalCount <Int32>]
 [-Syntax] [-ShowCommandInfo] [[-ArgumentList] <Object[]>] [-All] [-ListImported]
 [-ParameterName <String[]>] [-ParameterType <PSTypeName[]>] [-UseFuzzyMatching]
 [-UseAbbreviationExpansion] [<CommonParameters>]
```

## <span data-ttu-id="85c5a-109">Description</span><span class="sxs-lookup"><span data-stu-id="85c5a-109">DESCRIPTION</span></span>

<span data-ttu-id="85c5a-110">コマンドレットは、コマンド `Get-Command` レット、エイリアス、関数、フィルター、スクリプト、アプリケーションなど、コンピューターにインストールされているすべてのコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-110">The `Get-Command` cmdlet gets all commands that are installed on the computer, including cmdlets, aliases, functions, filters, scripts, and applications.</span></span> <span data-ttu-id="85c5a-111">`Get-Command` 他のセッションからインポートされた PowerShell モジュールとコマンドからコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-111">`Get-Command` gets the commands from PowerShell modules and commands that were imported from other sessions.</span></span> <span data-ttu-id="85c5a-112">現在のセッションにインポートされているコマンドのみを取得するには、 **ListImported** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-112">To get only commands that have been imported into the current session, use the **ListImported** parameter.</span></span>

<span data-ttu-id="85c5a-113">パラメーターを指定しない場合、 `Get-Command` コンピューターにインストールされているすべてのコマンドレット、関数、およびエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-113">Without parameters, `Get-Command` gets all of the cmdlets, functions, and aliases installed on the computer.</span></span> <span data-ttu-id="85c5a-114">`Get-Command *` Path 環境変数 () 内のすべての非 PowerShell ファイルを含むすべての種類のコマンドを取得し `$env:Path` ます。この変数は、アプリケーションコマンドの種類で一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-114">`Get-Command *` gets all types of commands, including all of the non-PowerShell files in the Path environment variable (`$env:Path`), which it lists in the Application command type.</span></span>

<span data-ttu-id="85c5a-115">`Get-Command` ワイルドカード文字を使用せずにコマンドの正確な名前を使用すると、コマンドを含むモジュールが自動的にインポートされ、コマンドをすぐに使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="85c5a-115">`Get-Command` that uses the exact name of the command, without wildcard characters, automatically imports the module that contains the command so that you can use the command immediately.</span></span> <span data-ttu-id="85c5a-116">モジュールの自動インポートを有効または無効にして構成するには、ユーザー設定変数を使用し `$PSModuleAutoLoadingPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-116">To enable, disable, and configure automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="85c5a-117">詳細については、「 [about_Preference_Variables](About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85c5a-117">For more information, see [about_Preference_Variables](About/about_Preference_Variables.md).</span></span>

<span data-ttu-id="85c5a-118">`Get-Command``Get-Help`ヘルプトピックから情報を取得するとは異なり、コマンドコードから直接データを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-118">`Get-Command` gets its data directly from the command code, unlike `Get-Help`, which gets its information from help topics.</span></span>

<span data-ttu-id="85c5a-119">Windows PowerShell 5.0 以降では、コマンドレットの結果に `Get-Command` より、既定で **バージョン** 列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-119">Starting in Windows PowerShell 5.0, results of the `Get-Command` cmdlet display a **Version** column by default.</span></span> <span data-ttu-id="85c5a-120">新しい **Version** プロパティが **commandinfo** クラスに追加されました。</span><span class="sxs-lookup"><span data-stu-id="85c5a-120">A new **Version** property has been added to the **CommandInfo** class.</span></span>

## <span data-ttu-id="85c5a-121">例</span><span class="sxs-lookup"><span data-stu-id="85c5a-121">EXAMPLES</span></span>

### <span data-ttu-id="85c5a-122">例 1: コマンドレット、関数、およびエイリアスを取得する</span><span class="sxs-lookup"><span data-stu-id="85c5a-122">Example 1: Get cmdlets, functions, and aliases</span></span>

<span data-ttu-id="85c5a-123">このコマンドは、コンピューターにインストールされている PowerShell コマンドレット、関数、およびエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-123">This command gets the PowerShell cmdlets, functions, and aliases that are installed on the computer.</span></span>

```powershell
Get-Command
```

### <span data-ttu-id="85c5a-124">例 2: 現在のセッションでコマンドを取得する</span><span class="sxs-lookup"><span data-stu-id="85c5a-124">Example 2: Get commands in the current session</span></span>

<span data-ttu-id="85c5a-125">このコマンドは、 **ListImported** パラメーターを使用して、現在のセッション内のコマンドのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-125">This command uses the **ListImported** parameter to get only the commands in the current session.</span></span>

```powershell
Get-Command -ListImported
```

### <span data-ttu-id="85c5a-126">例 3: コマンドレットを取得し、順番に表示する</span><span class="sxs-lookup"><span data-stu-id="85c5a-126">Example 3: Get cmdlets and display them in order</span></span>

<span data-ttu-id="85c5a-127">このコマンドは、すべてのコマンドレットを取得し、それらをコマンドレット名内の名詞によるアルファベット順で並べ替え、その後、名詞に基づくグループとして表示します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-127">This command gets all of the cmdlets, sorts them alphabetically by the noun in the cmdlet name, and then displays them in noun-based groups.</span></span> <span data-ttu-id="85c5a-128">この表示は、タスクのコマンドレットの検索に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-128">This display can help you find the cmdlets for a task.</span></span>

```powershell
Get-Command -Type Cmdlet | Sort-Object -Property Noun | Format-Table -GroupBy Noun
```

### <span data-ttu-id="85c5a-129">例 4: モジュール内のコマンドを取得する</span><span class="sxs-lookup"><span data-stu-id="85c5a-129">Example 4: Get commands in a module</span></span>

<span data-ttu-id="85c5a-130">このコマンドは、 **Module** パラメーターを使用して、Microsoft. Powershell および Microsoft. Powershell. Utility モジュール内のコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-130">This command uses the **Module** parameter to get the commands in the Microsoft.PowerShell.Security and Microsoft.PowerShell.Utility modules.</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Security, Microsoft.PowerShell.Utility
```

### <span data-ttu-id="85c5a-131">例 5: コマンドレットに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="85c5a-131">Example 5: Get information about a cmdlet</span></span>

<span data-ttu-id="85c5a-132">このコマンドは、コマンドレットに関する情報を取得し `Get-AppLockerPolicy` ます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-132">This command gets information about the `Get-AppLockerPolicy` cmdlet.</span></span> <span data-ttu-id="85c5a-133">また、 **AppLocker** モジュールをインポートして、 **AppLocker** モジュール内のすべてのコマンドを現在のセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-133">It also imports the **AppLocker** module, which adds all of the commands in the **AppLocker** module to the current session.</span></span>

```powershell
Get-Command Get-AppLockerPolicy
```

<span data-ttu-id="85c5a-134">モジュールが自動的にインポートされる場合、結果は Import-Module コマンドレットを使用した場合と同じになります。</span><span class="sxs-lookup"><span data-stu-id="85c5a-134">When a module is imported automatically, the effect is the same as using the Import-Module cmdlet.</span></span>
<span data-ttu-id="85c5a-135">モジュールは、コマンド、型、および書式設定ファイルを追加し、セッションでスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-135">The module can add commands, types and formatting files, and run scripts in the session.</span></span> <span data-ttu-id="85c5a-136">モジュールの自動インポートを有効化、無効化、および構成するには、ユーザー設定変数を使用し `$PSModuleAutoLoadingPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-136">To enable, disable, and configuration automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="85c5a-137">詳細については、「 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85c5a-137">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

### <span data-ttu-id="85c5a-138">例 6: コマンドレットの構文を取得する</span><span class="sxs-lookup"><span data-stu-id="85c5a-138">Example 6: Get the syntax of a cmdlet</span></span>

<span data-ttu-id="85c5a-139">このコマンドは、 **ArgumentList** パラメーターと **構文** パラメーターを使用して、 `Get-ChildItem` Cert: ドライブで使用されているときにコマンドレットの構文を取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-139">This command uses the **ArgumentList** and **Syntax** parameters to get the syntax of the `Get-ChildItem` cmdlet when it is used in the Cert: drive.</span></span> <span data-ttu-id="85c5a-140">Cert: ドライブは、証明書プロバイダーによってセッションに追加される PowerShell ドライブです。</span><span class="sxs-lookup"><span data-stu-id="85c5a-140">The Cert: drive is a PowerShell drive that the Certificate Provider adds to the session.</span></span>

```powershell
Get-Command  -Name Get-Childitem -Args Cert: -Syntax
```

<span data-ttu-id="85c5a-141">出力に表示される構文と、 **Args** ( **ArgumentList** ) パラメーターを省略したときに表示される構文を比較すると、 **証明書プロバイダー** によって動的パラメーター **codesigningcert** がコマンドレットに追加されることがわかります `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="85c5a-141">When you compare the syntax displayed in the output with the syntax that is displayed when you omit the **Args** ( **ArgumentList** ) parameter, you'll see that the **Certificate provider** adds a dynamic parameter, **CodeSigningCert** , to the `Get-ChildItem` cmdlet.</span></span>

<span data-ttu-id="85c5a-142">証明書プロバイダーの詳細については、「 [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85c5a-142">For more information about the Certificate provider, see [about_Certificate_Provider](../Microsoft.PowerShell.Security/About/about_Certificate_Provider.md).</span></span>

### <span data-ttu-id="85c5a-143">例 7: 動的パラメーターを取得する</span><span class="sxs-lookup"><span data-stu-id="85c5a-143">Example 7: Get dynamic parameters</span></span>

<span data-ttu-id="85c5a-144">この例のコマンドは、関数を使用して、 `Get-DynamicParameters` 証明書プロバイダーが `Get-ChildItem` Cert: ドライブで使用されているときにコマンドレットに追加する動的パラメーターを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-144">The command in the example uses the `Get-DynamicParameters` function to get the dynamic parameters that the Certificate provider adds to the `Get-ChildItem` cmdlet when it is used in the Cert: drive.</span></span>

```powershell
function Get-DynamicParameters
{
    param ($Cmdlet, $PSDrive)
    (Get-Command -Name $Cmdlet -ArgumentList $PSDrive).ParameterSets | ForEach-Object {$_.Parameters} | Where-Object { $_.IsDynamic } | Select-Object -Property Name -Unique
}
Get-DynamicParameters -Cmdlet Get-ChildItem -PSDrive Cert:
```

```Output
Name
----
CodeSigningCert
```

<span data-ttu-id="85c5a-145">`Get-DynamicParameters`この例の関数は、コマンドレットの動的パラメーターを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-145">The `Get-DynamicParameters` function in this example gets the dynamic parameters of a cmdlet.</span></span> <span data-ttu-id="85c5a-146">これは、前の例で使用されたメソッドの代替です。</span><span class="sxs-lookup"><span data-stu-id="85c5a-146">This is an alternative to the method used in the previous example.</span></span> <span data-ttu-id="85c5a-147">動的パラメーターは、別のコマンドレットまたはプロバイダーによって、コマンドレットに追加できます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-147">Dynamic parameter can be added to a cmdlet by another cmdlet or a provider.</span></span>

### <span data-ttu-id="85c5a-148">例 8: すべての型のすべてのコマンドを取得する</span><span class="sxs-lookup"><span data-stu-id="85c5a-148">Example 8: Get all commands of all types</span></span>

<span data-ttu-id="85c5a-149">このコマンドは、 **Path** 環境変数 () のパスにある実行可能ファイルを含め、ローカルコンピューター上のすべての種類のすべてのコマンドを取得し `$env:path` ます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-149">This command gets all commands of all types on the local computer, including executable files in the paths of the **Path** environment variable (`$env:path`).</span></span>

```powershell
Get-Command *
```

<span data-ttu-id="85c5a-150">このコマンドは、 **FileInfo** オブジェクト (System.IO.FileInfo) ではなく、各ファイルの **ApplicationInfo** オブジェクト (System.Management.Automation.ApplicationInfo) を返します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-150">It returns an **ApplicationInfo** object (System.Management.Automation.ApplicationInfo) for each file, not a **FileInfo** object (System.IO.FileInfo).</span></span>

### <span data-ttu-id="85c5a-151">例 9: パラメーター名と型を使用してコマンドレットを取得する</span><span class="sxs-lookup"><span data-stu-id="85c5a-151">Example 9: Get cmdlets by using a parameter name and type</span></span>

<span data-ttu-id="85c5a-152">このコマンドは、名前に Auth を含むパラメーターがあり、その型が **Authenticationmechanism** であるコマンドレットを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-152">This command gets cmdlets that have a parameter whose name includes Auth and whose type is **AuthenticationMechanism**.</span></span>

```powershell
Get-Command -ParameterName *Auth* -ParameterType AuthenticationMechanism
```

<span data-ttu-id="85c5a-153">ユーザーの認証に使用されるメソッドを指定するためのコマンドレットを検索するために、次のようなコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-153">You can use a command like this one to find cmdlets that let you specify the method that is used to authenticate the user.</span></span>

<span data-ttu-id="85c5a-154">**ParameterType** パラメーターは、パラメーターが同じ名前の場合でも、 **AuthenticationMechanism** 値を受け取るパラメーターと、 **AuthenticationLevel** パラメーターを受け取るパラメーターを区別します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-154">The **ParameterType** parameter distinguishes parameters that take an **AuthenticationMechanism** value from those that take an **AuthenticationLevel** parameter, even when they have similar names.</span></span>

### <span data-ttu-id="85c5a-155">例 10: エイリアスを取得する</span><span class="sxs-lookup"><span data-stu-id="85c5a-155">Example 10: Get an alias</span></span>

<span data-ttu-id="85c5a-156">この例では、 `Get-Command` コマンドレットをエイリアスと共に使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-156">This example shows how to use the `Get-Command` cmdlet with an alias.</span></span>

```powershell
Get-Command Name dir
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Alias           dir -> Get-ChildItem
```

<span data-ttu-id="85c5a-157">通常はコマンドレットと関数で使用され `Get-Command` ますが、スクリプト、関数、エイリアス、および実行可能ファイルも取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-157">Although it is typically used on cmdlets and functions, `Get-Command` also gets scripts, functions, aliases, and executable files.</span></span>

<span data-ttu-id="85c5a-158">コマンドの出力は、エイリアスの **Name** プロパティの値の特別な表示を示しています。</span><span class="sxs-lookup"><span data-stu-id="85c5a-158">The output of the command shows the special view of the **Name** property value for aliases.</span></span> <span data-ttu-id="85c5a-159">この表示は、エイリアスとコマンドのフルネームを示しています。</span><span class="sxs-lookup"><span data-stu-id="85c5a-159">The view shows the alias and the full command name.</span></span>

### <span data-ttu-id="85c5a-160">例 11: 別名から構文を取得する</span><span class="sxs-lookup"><span data-stu-id="85c5a-160">Example 11: Get Syntax from an alias</span></span>

<span data-ttu-id="85c5a-161">この例では、エイリアスの標準名と共に構文を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-161">This example shows how to get the syntax along with the standard name of an alias.</span></span>

<span data-ttu-id="85c5a-162">このコマンドの出力では、標準名のラベルが付いたエイリアスと、その後に構文が表示されます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-162">The output of the command shows the labeled alias with the standard name, followed by the syntax.</span></span>

```powershell
Get-Command -Name dir -Syntax
```

```Output
dir (alias) -> Get-ChildItem

dir [[-Path] <string[]>] [[-Filter] <string>] [-Include <string[]>] [-Exclude <string[]>] [-Recurse] [-Depth <uint>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]

dir [[-Filter] <string>] -LiteralPath <string[]> [-Include <string[]>] [-Exclude <string[]>] [-Recurse] [-Depth <uint>] [-Force] [-Name] [-Attributes <FlagsExpression[FileAttributes]>] [-FollowSymlink] [-Directory] [-File] [-Hidden] [-ReadOnly] [-System] [<CommonParameters>]
```

### <span data-ttu-id="85c5a-163">例 12: メモ帳コマンドのすべてのインスタンスを取得する</span><span class="sxs-lookup"><span data-stu-id="85c5a-163">Example 12: Get all instances of the Notepad command</span></span>

<span data-ttu-id="85c5a-164">この例では、コマンドレットの **all** パラメーターを使用して、 `Get-Command` ローカルコンピューター上のコマンドのすべてのインスタンスを表示し `Notepad` ます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-164">This example uses the **All** parameter of the `Get-Command` cmdlet to show all instances of the `Notepad` command on the local computer.</span></span>

```powershell
Get-Command Notepad -All | Format-Table CommandType, Name, Definition
```

```Output
CommandType     Name           Definition
-----------     ----           ----------
Application     notepad.exe    C:\WINDOWS\system32\notepad.exe
Application     NOTEPAD.EXE    C:\WINDOWS\NOTEPAD.EXE
```

<span data-ttu-id="85c5a-165">**All** パラメーターは、セッションで同じ名前のコマンドが複数ある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-165">The **All** parameter is useful when there is more than one command with the same name in the session.</span></span>

<span data-ttu-id="85c5a-166">Windows PowerShell 3.0 以降では、セッションに同じ名前の複数のコマンドが含まれる場合、既定では、 `Get-Command` コマンド名を入力したときに実行されるコマンドのみが取得されます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-166">Beginning in Windows PowerShell 3.0, by default, when the session includes multiple commands with the same name, `Get-Command` gets only the command that runs when you type the command name.</span></span> <span data-ttu-id="85c5a-167">**All** パラメーターを使用して、指定した `Get-Command` 名前のすべてのコマンドを取得し、実行の優先順位で返します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-167">With the **All** parameter, `Get-Command` gets all commands with the specified name and returns them in execution precedence order.</span></span> <span data-ttu-id="85c5a-168">一覧で最初のコマンドではなく、他のコマンドを実行するには、コマンドへの完全修飾パスを入力します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-168">To run a command other than the first one in the list, type the fully qualified path to the command.</span></span>

<span data-ttu-id="85c5a-169">コマンドの優先順位の詳細については、「 [about_Command_Precedence](About/about_Command_Precedence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85c5a-169">For more information about command precedence, see [about_Command_Precedence](About/about_Command_Precedence.md).</span></span>

### <span data-ttu-id="85c5a-170">例 13: コマンドレットを含むモジュールの名前を取得する</span><span class="sxs-lookup"><span data-stu-id="85c5a-170">Example 13: Get the name of a module that contains a cmdlet</span></span>

<span data-ttu-id="85c5a-171">このコマンドは、コマンドレットが生成されたモジュールの名前を取得し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-171">This command gets the name of the module in which the `Get-Date` cmdlet originated.</span></span>
<span data-ttu-id="85c5a-172">コマンドは、すべてのコマンドの **ModuleName** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-172">The command uses the **ModuleName** property of all commands.</span></span>

```powershell
(Get-Command Get-Date).ModuleName
```

```Output
Microsoft.PowerShell.Utility
```

<span data-ttu-id="85c5a-173">このコマンド形式は、セッションにインポートされていない場合でも、PowerShell モジュールのコマンドに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-173">This command format works on commands in PowerShell modules, even if they are not imported into the session.</span></span>

### <span data-ttu-id="85c5a-174">例 14: 出力の種類がのコマンドレットと関数を取得する</span><span class="sxs-lookup"><span data-stu-id="85c5a-174">Example 14: Get cmdlets and functions that have an output type</span></span>

```powershell
Get-Command -Type Cmdlet | Where-Object OutputType | Format-List -Property Name, OutputType
```

<span data-ttu-id="85c5a-175">このコマンドは、出力の種類とオブジェクトの種類を返す、コマンドレットと関数を取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-175">This command gets the cmdlets and functions that have an output type and the type of objects that they return.</span></span>

<span data-ttu-id="85c5a-176">コマンドの最初の部分は、すべてのコマンドレットを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-176">The first part of the command gets all cmdlets.</span></span> <span data-ttu-id="85c5a-177">パイプライン演算子 () は、コマンドレットをコマンドレットに送信します。このコマンドレットは、 `|` `Where-Object` **OutputType** プロパティが設定されているコマンドレットだけを選択します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-177">A pipeline operator (`|`) sends the cmdlets to the `Where-Object` cmdlet, which selects only the ones in which the **OutputType** property is populated.</span></span> <span data-ttu-id="85c5a-178">もう1つのパイプライン演算子は、選択したコマンドレットオブジェクトをコマンドレットに送信します。このコマンドレットは、 `Format-List` リスト内の各コマンドレットの名前と出力の種類を表示します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-178">Another pipeline operator sends the selected cmdlet objects to the `Format-List` cmdlet, which displays the name and output type of each cmdlet in a list.</span></span>

<span data-ttu-id="85c5a-179">**CommandInfo** オブジェクトの **OutputType** プロパティは、コマンドレット コードがコマンドレットの **OutputType** 属性を定義する場合にのみ、NULL 以外の値を保持します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-179">The **OutputType** property of a **CommandInfo** object has a non-null value only when the cmdlet code defines the **OutputType** attribute for the cmdlet.</span></span>

### <span data-ttu-id="85c5a-180">例 15: 特定のオブジェクトの種類を入力として受け取るコマンドレットを取得する</span><span class="sxs-lookup"><span data-stu-id="85c5a-180">Example 15: Get cmdlets that take a specific object type as input</span></span>

```powershell
Get-Command -ParameterType (((Get-NetAdapter)[0]).PSTypeNames)
```

```Output
CommandType     Name                                               ModuleName
-----------     ----                                               ----------
Function        Disable-NetAdapter                                 NetAdapter
Function        Enable-NetAdapter                                  NetAdapter
Function        Rename-NetAdapter                                  NetAdapter
Function        Restart-NetAdapter                                 NetAdapter
Function        Set-NetAdapter                                     NetAdapter
```

<span data-ttu-id="85c5a-181">このコマンドは、ネット アダプター オブジェクトを入力として受け取るコマンドレットを検索します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-181">This command finds cmdlets that take net adapter objects as input.</span></span> <span data-ttu-id="85c5a-182">このコマンド形式を使用して、いずれかのコマンドによって返されるオブジェクトの種類を受け取るコマンドレットを検索できます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-182">You can use this command format to find the cmdlets that accept the type of objects that any command returns.</span></span>

<span data-ttu-id="85c5a-183">コマンドは、すべてのオブジェクトの **PSTypeNames** 組み込みプロパティを使用して、オブジェクトを記述する型を取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-183">The command uses the **PSTypeNames** intrinsic property of all objects, which gets the types that describe the object.</span></span> <span data-ttu-id="85c5a-184">ネット アダプターの **PSTypeNames** プロパティを取得し、ネット アダプターのコレクションの **PSTypeNames** プロパティを除外するために、コマンドは、配列表記を使用して、コマンドレットが返す最初のネット アダプターを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-184">To get the **PSTypeNames** property of a net adapter, and not the **PSTypeNames** property of a collection of net adapters, the command uses array notation to get the first net adapter that the cmdlet returns.</span></span>

### <span data-ttu-id="85c5a-185">例 16: あいまい一致を使用してコマンドを取得する</span><span class="sxs-lookup"><span data-stu-id="85c5a-185">Example 16: Get commands using a fuzzy match</span></span>

<span data-ttu-id="85c5a-186">この例では、コマンドの名前は、意図的に ' get-commnd ' として指定されています。</span><span class="sxs-lookup"><span data-stu-id="85c5a-186">In this example, the name of the command deliberately has a typo as 'get-commnd'.</span></span>
<span data-ttu-id="85c5a-187">スイッチを使用すると `-UseFuzzyMatching` 、コマンドレットは、一致と見なさ `Get-Command` れたシステム上の他のネイティブコマンドが最も一致したものであると判断しました。</span><span class="sxs-lookup"><span data-stu-id="85c5a-187">Using the `-UseFuzzyMatching` switch, the cmdlet determined that the best match was `Get-Command` followed by other native commands on the system that were a similar match.</span></span>

```powershell
Get-Command get-commnd -UseFuzzyMatching
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Get-Command                                        6.2.0.0    Microsoft.PowerShell.Core
Application     getconf                                            0.0.0.0    /usr/bin/getconf
Application     command                                            0.0.0.0    /usr/bin/command
```

## <span data-ttu-id="85c5a-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="85c5a-188">PARAMETERS</span></span>

### <span data-ttu-id="85c5a-189">-All</span><span class="sxs-lookup"><span data-stu-id="85c5a-189">-All</span></span>

<span data-ttu-id="85c5a-190">このコマンドレットが、同じ名前を持つ同じ種類のコマンドを含む、すべてのコマンドを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-190">Indicates that this cmdlet gets all commands, including commands of the same type that have the same name.</span></span> <span data-ttu-id="85c5a-191">既定では、 `Get-Command` コマンド名を入力したときに実行されるコマンドのみが取得されます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-191">By default, `Get-Command` gets only the commands that run when you type the command name.</span></span>

<span data-ttu-id="85c5a-192">複数のコマンドが同じ名前の場合に実行するコマンドを PowerShell で選択する方法の詳細については、「 [about_Command_Precedence](About/about_Command_Precedence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85c5a-192">For more information about the method that PowerShell uses to select the command to run when multiple commands have the same name, see [about_Command_Precedence](About/about_Command_Precedence.md).</span></span>
<span data-ttu-id="85c5a-193">名前の競合が原因で既定で実行されないモジュール修飾コマンド名と実行中のコマンドの詳細については、「 [about_Modules](About/about_Modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85c5a-193">For information about module-qualified command names and running commands that do not run by default because of a name conflict, see [about_Modules](About/about_Modules.md).</span></span>

<span data-ttu-id="85c5a-194">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="85c5a-194">This parameter was introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="85c5a-195">Windows PowerShell 2.0 では、 `Get-Command` 既定ですべてのコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-195">In Windows PowerShell 2.0, `Get-Command` gets all commands by default.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="85c5a-196">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="85c5a-196">-ArgumentList</span></span>

<span data-ttu-id="85c5a-197">引数の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-197">Specifies an array of arguments.</span></span> <span data-ttu-id="85c5a-198">このコマンドレットは、指定されたパラメーター ("arguments") と共に使用された場合に、コマンドレットまたは関数に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-198">This cmdlet gets information about a cmdlet or function when it is used with the specified parameters ("arguments").</span></span> <span data-ttu-id="85c5a-199">**ArgumentList** のエイリアスは、 **Args** です。</span><span class="sxs-lookup"><span data-stu-id="85c5a-199">The alias for **ArgumentList** is **Args**.</span></span>

<span data-ttu-id="85c5a-200">特定の他のパラメーターが使用されている場合にのみ使用可能な動的パラメーターを検出するには、 **ArgumentList** の値を動的パラメーターをトリガーするパラメーターに設定します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-200">To detect dynamic parameters that are available only when certain other parameters are used, set the value of **ArgumentList** to the parameters that trigger the dynamic parameters.</span></span>

<span data-ttu-id="85c5a-201">プロバイダーがコマンドレットに追加する動的パラメーターを検出するには、 **ArgumentList** パラメーターの値を、WSMan:、HKLM:、Cert: などのプロバイダードライブのパスに設定します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-201">To detect the dynamic parameters that a provider adds to a cmdlet, set the value of the **ArgumentList** parameter to a path in the provider drive, such as WSMan:, HKLM:, or Cert:.</span></span> <span data-ttu-id="85c5a-202">コマンドが PowerShell プロバイダーコマンドレットの場合は、各コマンドでパスを1つだけ入力します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-202">When the command is a PowerShell provider cmdlet, enter only one path in each command.</span></span> <span data-ttu-id="85c5a-203">プロバイダーのコマンドレットは、 **ArgumentList** の値の最初のパスの動的パラメーターのみを返します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-203">The provider cmdlets return only the dynamic parameters for the first path the value of **ArgumentList**.</span></span> <span data-ttu-id="85c5a-204">プロバイダーコマンドレットの詳細については、「 [about_Providers](About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85c5a-204">For information about the provider cmdlets, see [about_Providers](About/about_Providers.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85c5a-205">-CommandType</span><span class="sxs-lookup"><span data-stu-id="85c5a-205">-CommandType</span></span>

<span data-ttu-id="85c5a-206">このコマンドレットが取得するコマンドの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-206">Specifies the types of commands that this cmdlet gets.</span></span> <span data-ttu-id="85c5a-207">1 つまたは複数のコマンドの種類を入力します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-207">Enter one or more command types.</span></span> <span data-ttu-id="85c5a-208">**CommandType** またはそのエイリアスの **Type** を使用します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-208">Use **CommandType** or its alias, **Type**.</span></span> <span data-ttu-id="85c5a-209">既定では、は `Get-Command` すべてのコマンドレット、関数、およびエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-209">By default, `Get-Command` gets all cmdlets, functions, and aliases.</span></span>

<span data-ttu-id="85c5a-210">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="85c5a-210">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="85c5a-211">エイリアス.</span><span class="sxs-lookup"><span data-stu-id="85c5a-211">Alias.</span></span> <span data-ttu-id="85c5a-212">すべての PowerShell コマンドのエイリアスを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-212">Gets the aliases of all PowerShell commands.</span></span> <span data-ttu-id="85c5a-213">詳細については、「 [about_Aliases](About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85c5a-213">For more information, see [about_Aliases](About/about_Aliases.md).</span></span>
- <span data-ttu-id="85c5a-214">すべて。</span><span class="sxs-lookup"><span data-stu-id="85c5a-214">All.</span></span> <span data-ttu-id="85c5a-215">すべてのコマンドの種類を取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-215">Gets all command types.</span></span> <span data-ttu-id="85c5a-216">このパラメーター値は、に相当し `Get-Command *` ます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-216">This parameter value is the equivalent of `Get-Command *`.</span></span>
- <span data-ttu-id="85c5a-217">アプリケーション をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85c5a-217">Application.</span></span> <span data-ttu-id="85c5a-218">.Txt、.exe、.dll ファイルなど、 **Path** 環境変数 ($env:p a) に一覧表示されているパス内の PowerShell 以外のファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-218">Gets non-PowerShell files in paths listed in the **Path** environment variable ($env:path), including .txt, .exe, and .dll files.</span></span> <span data-ttu-id="85c5a-219">**Path** 環境変数の詳細については、「about_Environment_Variables」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85c5a-219">For more information about the **Path** environment variable, see about_Environment_Variables.</span></span>
- <span data-ttu-id="85c5a-220">コマンドレット.</span><span class="sxs-lookup"><span data-stu-id="85c5a-220">Cmdlet.</span></span> <span data-ttu-id="85c5a-221">すべてのコマンドレットを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-221">Gets all cmdlets.</span></span>
- <span data-ttu-id="85c5a-222">ExternalScript。</span><span class="sxs-lookup"><span data-stu-id="85c5a-222">ExternalScript.</span></span> <span data-ttu-id="85c5a-223">**Path** 環境変数 ($env:path) に列挙されるパス内のすべての .ps1 ファイルを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-223">Gets all .ps1 files in the paths listed in the **Path** environment variable ($env:path).</span></span>
- <span data-ttu-id="85c5a-224">フィルターと関数。</span><span class="sxs-lookup"><span data-stu-id="85c5a-224">Filter and Function.</span></span> <span data-ttu-id="85c5a-225">すべての PowerShell advanced および simple 関数とフィルターを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-225">Gets all PowerShell advanced and simple functions and filters.</span></span>
- <span data-ttu-id="85c5a-226">スクリプティング。</span><span class="sxs-lookup"><span data-stu-id="85c5a-226">Script.</span></span> <span data-ttu-id="85c5a-227">すべてのスクリプト ブロックを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-227">Gets all script blocks.</span></span> <span data-ttu-id="85c5a-228">PowerShell スクリプト (ps1 ファイル) を取得するには、ExternalScript 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-228">To get PowerShell scripts (.ps1 files), use the ExternalScript value.</span></span>

```yaml
Type: System.Management.Automation.CommandTypes
Parameter Sets: AllCommandSet
Aliases: Type
Accepted values: Alias, Function, Filter, Cmdlet, ExternalScript, Application, Script, Workflow, Configuration, All

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="85c5a-229">-FullyQualifiedModule</span><span class="sxs-lookup"><span data-stu-id="85c5a-229">-FullyQualifiedModule</span></span>

<span data-ttu-id="85c5a-230">**Modulの** 特定の [コンストラクター (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_)の **「解説** 」で説明されている、名前付きモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-230">Specifies modules with names that are specified in the form of **ModuleSpecification** objects, described in the **Remarks** section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>
<span data-ttu-id="85c5a-231">たとえば、 **FullyQualifiedModule** パラメーターは、次のいずれかの形式で指定されたモジュール名を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-231">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in one of the following formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="85c5a-232">**ModuleName** と **ModuleVersion** は必須ですが、 **Guid** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="85c5a-232">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span>

<span data-ttu-id="85c5a-233">**モジュール** パラメーターと同じコマンドで **FullyQualifiedModule** パラメーターを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="85c5a-233">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="85c5a-234">2つのパラメーターは相互に排他的です。</span><span class="sxs-lookup"><span data-stu-id="85c5a-234">The two parameters are mutually exclusive.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="85c5a-235">-ListImported</span><span class="sxs-lookup"><span data-stu-id="85c5a-235">-ListImported</span></span>

<span data-ttu-id="85c5a-236">このコマンドレットが現在のセッションのコマンドのみを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-236">Indicates that this cmdlet gets only commands in the current session.</span></span>

<span data-ttu-id="85c5a-237">PowerShell 3.0 以降では、既定では、 `Get-Command` 現在のセッションのコマンドに限定されるのではなく、インストールされているすべてのコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-237">Starting in PowerShell 3.0, by default, `Get-Command` gets all installed commands, including, but not limited to, the commands in the current session.</span></span> <span data-ttu-id="85c5a-238">PowerShell 2.0 では、現在のセッションのコマンドのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-238">In PowerShell 2.0, it gets only commands in the current session.</span></span>

<span data-ttu-id="85c5a-239">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="85c5a-239">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="85c5a-240">-モジュール</span><span class="sxs-lookup"><span data-stu-id="85c5a-240">-Module</span></span>

<span data-ttu-id="85c5a-241">モジュールの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-241">Specifies an array of modules.</span></span> <span data-ttu-id="85c5a-242">このコマンドレットは、指定されたモジュールからのコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-242">This cmdlet gets the commands that came from the specified modules.</span></span>
<span data-ttu-id="85c5a-243">モジュールまたはモジュールオブジェクトの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-243">Enter the names of modules or module objects.</span></span>

<span data-ttu-id="85c5a-244">このパラメーターは文字列値を受け取りますが、このパラメーターの値は、およびコマンドレットが返すオブジェクトなどの **PSModuleInfo** オブジェクトにすることもでき `Get-Module` `Import-PSSession` ます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-244">This parameter takes string values, but the value of this parameter can also be a **PSModuleInfo** object, such as the objects that the `Get-Module` and `Import-PSSession` cmdlets return.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSSnapin

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="85c5a-245">-Name</span><span class="sxs-lookup"><span data-stu-id="85c5a-245">-Name</span></span>

<span data-ttu-id="85c5a-246">名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-246">Specifies an array of names.</span></span> <span data-ttu-id="85c5a-247">このコマンドレットは、指定された名前のコマンドのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-247">This cmdlet gets only commands that have the specified name.</span></span> <span data-ttu-id="85c5a-248">名前または名前パターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-248">Enter a name or name pattern.</span></span> <span data-ttu-id="85c5a-249">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-249">Wildcard characters are permitted.</span></span>

<span data-ttu-id="85c5a-250">同じ名前のコマンドを取得するには、 **All** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-250">To get commands that have the same name, use the **All** parameter.</span></span> <span data-ttu-id="85c5a-251">2つのコマンドの名前が同じ場合、既定では、 `Get-Command` コマンド名を入力したときに実行されるコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-251">When two commands have the same name, by default, `Get-Command` gets the command that runs when you type the command name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="85c5a-252">-名詞</span><span class="sxs-lookup"><span data-stu-id="85c5a-252">-Noun</span></span>

<span data-ttu-id="85c5a-253">コマンドの名詞の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-253">Specifies an array of command nouns.</span></span> <span data-ttu-id="85c5a-254">このコマンドレットは、指定された名詞を含む名前を持つコマンドレット、関数、およびエイリアスを含むコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-254">This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified noun.</span></span> <span data-ttu-id="85c5a-255">1 つまたは複数の名詞または名詞のパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-255">Enter one or more nouns or noun patterns.</span></span> <span data-ttu-id="85c5a-256">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-256">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CmdletSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="85c5a-257">-ParameterName</span><span class="sxs-lookup"><span data-stu-id="85c5a-257">-ParameterName</span></span>

<span data-ttu-id="85c5a-258">パラメーター名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-258">Specifies an array of parameter names.</span></span> <span data-ttu-id="85c5a-259">このコマンドレットは、指定されたパラメーターを持つセッション内のコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-259">This cmdlet gets commands in the session that have the specified parameters.</span></span> <span data-ttu-id="85c5a-260">パラメーター名またはパラメーターの別名を入力します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-260">Enter parameter names or parameter aliases.</span></span> <span data-ttu-id="85c5a-261">ワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="85c5a-261">Wildcard characters are supported.</span></span>

<span data-ttu-id="85c5a-262">**ParameterName** および **ParameterType** 　パラメーターは、現在のセッションのコマンドのみを検索します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-262">The **ParameterName** and **ParameterType** parameters search only commands in the current session.</span></span>

<span data-ttu-id="85c5a-263">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="85c5a-263">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="85c5a-264">-ParameterType</span><span class="sxs-lookup"><span data-stu-id="85c5a-264">-ParameterType</span></span>

<span data-ttu-id="85c5a-265">パラメーター名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-265">Specifies an array of parameter names.</span></span> <span data-ttu-id="85c5a-266">このコマンドレットは、指定された型のパラメーターを持つ、セッション内のコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-266">This cmdlet gets commands in the session that have parameters of the specified type.</span></span> <span data-ttu-id="85c5a-267">パラメーターの型のフルネームまたは部分的な名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-267">Enter the full name or partial name of a parameter type.</span></span> <span data-ttu-id="85c5a-268">ワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="85c5a-268">Wildcard characters are supported.</span></span>

<span data-ttu-id="85c5a-269">**ParameterName** および **ParameterType** 　パラメーターは、現在のセッションのコマンドのみを検索します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-269">The **ParameterName** and **ParameterType** parameters search only commands in the current session.</span></span>

<span data-ttu-id="85c5a-270">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="85c5a-270">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSTypeName[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="85c5a-271">-ShowCommandInfo</span><span class="sxs-lookup"><span data-stu-id="85c5a-271">-ShowCommandInfo</span></span>

<span data-ttu-id="85c5a-272">このコマンドレットによってコマンド情報が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-272">Indicates that this cmdlet displays command information.</span></span>

<span data-ttu-id="85c5a-273">このパラメーターは、Windows PowerShell 5.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="85c5a-273">This parameter was introduced in Windows PowerShell 5.0.</span></span>

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

### <span data-ttu-id="85c5a-274">-構文</span><span class="sxs-lookup"><span data-stu-id="85c5a-274">-Syntax</span></span>

<span data-ttu-id="85c5a-275">このコマンドレットが、コマンドに関する次の指定されたデータのみを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-275">Indicates that this cmdlet gets only the following specified data about the command:</span></span>

- <span data-ttu-id="85c5a-276">エイリアス.</span><span class="sxs-lookup"><span data-stu-id="85c5a-276">Aliases.</span></span> <span data-ttu-id="85c5a-277">標準の名前と構文を取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-277">Gets the standard name and syntax.</span></span>
- <span data-ttu-id="85c5a-278">レット.</span><span class="sxs-lookup"><span data-stu-id="85c5a-278">Cmdlets.</span></span> <span data-ttu-id="85c5a-279">構文を取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-279">Gets the syntax.</span></span>
- <span data-ttu-id="85c5a-280">関数とフィルター。</span><span class="sxs-lookup"><span data-stu-id="85c5a-280">Functions and filters.</span></span> <span data-ttu-id="85c5a-281">関数定義を取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-281">Gets the function definition.</span></span>
- <span data-ttu-id="85c5a-282">スクリプト、アプリケーション、またはファイル。</span><span class="sxs-lookup"><span data-stu-id="85c5a-282">Scripts and applications or files.</span></span> <span data-ttu-id="85c5a-283">パスとファイル名を取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-283">Gets the path and filename.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="85c5a-284">-TotalCount</span><span class="sxs-lookup"><span data-stu-id="85c5a-284">-TotalCount</span></span>

<span data-ttu-id="85c5a-285">取得するコマンドの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-285">Specifies the number of commands to get.</span></span> <span data-ttu-id="85c5a-286">このパラメーターを使用すると、コマンドの出力を制限できます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-286">You can use this parameter to limit the output of a command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="85c5a-287">-UseAbbreviationExpansion</span><span class="sxs-lookup"><span data-stu-id="85c5a-287">-UseAbbreviationExpansion</span></span>

<span data-ttu-id="85c5a-288">コマンド内の文字の照合を使用して、コマンド内の大文字で検索することを示します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-288">Indicates using matching of the characters in the command to find with uppercase characters in a command.</span></span> <span data-ttu-id="85c5a-289">たとえば、は、 `i-psdf` `Import-PowerShellDataFile` 検索する各文字が結果の大文字と一致すると見なされます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-289">For example, `i-psdf` would match `Import-PowerShellDataFile` as each of the characters to find matches an uppercase character in the result.</span></span> <span data-ttu-id="85c5a-290">この種類の一致を使用すると、ワイルドカードの結果は一致しません。</span><span class="sxs-lookup"><span data-stu-id="85c5a-290">When using this type of match, any wildcards will result in no matches.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="85c5a-291">-UseFuzzyMatching</span><span class="sxs-lookup"><span data-stu-id="85c5a-291">-UseFuzzyMatching</span></span>

<span data-ttu-id="85c5a-292">コマンドを検索するときに、あいまい一致アルゴリズムを使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-292">Indicates using a fuzzy matching algorithm when finding commands.</span></span> <span data-ttu-id="85c5a-293">出力の順序は、最も近い一致から最も一致しないものになります。</span><span class="sxs-lookup"><span data-stu-id="85c5a-293">The order of the output is from closest match to least likely match.</span></span> <span data-ttu-id="85c5a-294">ワイルドカードは、ワイルドカード文字を含む可能性のあるコマンドを照合しようとするため、あいまい一致では使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="85c5a-294">Wildcards should not be used with fuzzy matching as it will attempt to match commands that may contain those wildcard characters.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: AllCommandSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="85c5a-295">-動詞</span><span class="sxs-lookup"><span data-stu-id="85c5a-295">-Verb</span></span>

<span data-ttu-id="85c5a-296">コマンド動詞の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-296">Specifies an array of command verbs.</span></span> <span data-ttu-id="85c5a-297">このコマンドレットは、指定された動詞を含む名前を持つコマンドレット、関数、およびエイリアスを含むコマンドを取得します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-297">This cmdlet gets commands, which include cmdlets, functions, and aliases, that have names that include the specified verb.</span></span> <span data-ttu-id="85c5a-298">1 つまたは複数の動詞または動詞パターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-298">Enter one or more verbs or verb patterns.</span></span> <span data-ttu-id="85c5a-299">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-299">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CmdletSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="85c5a-300">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="85c5a-300">CommonParameters</span></span>

<span data-ttu-id="85c5a-301">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="85c5a-301">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="85c5a-302">詳細については、「[about_CommonParameters](About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85c5a-302">For more information, see [about_CommonParameters](About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="85c5a-303">入力</span><span class="sxs-lookup"><span data-stu-id="85c5a-303">INPUTS</span></span>

### <span data-ttu-id="85c5a-304">System.String</span><span class="sxs-lookup"><span data-stu-id="85c5a-304">System.String</span></span>

<span data-ttu-id="85c5a-305">パイプを使用してコマンド名をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-305">You can pipe command names to this cmdlet.</span></span>

## <span data-ttu-id="85c5a-306">出力</span><span class="sxs-lookup"><span data-stu-id="85c5a-306">OUTPUTS</span></span>

### <span data-ttu-id="85c5a-307">システムの管理. CommandInfo</span><span class="sxs-lookup"><span data-stu-id="85c5a-307">System.Management.Automation.CommandInfo</span></span>

<span data-ttu-id="85c5a-308">このコマンドレットは、 **Commandinfo** クラスから派生したオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-308">This cmdlet returns objects derived from the **CommandInfo** class.</span></span> <span data-ttu-id="85c5a-309">返されるオブジェクトの型は、が取得するコマンドの型によって異なり `Get-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-309">The type of object that is returned depends on the type of command that `Get-Command` gets.</span></span>

### <span data-ttu-id="85c5a-310">システム管理. エイリアス情報</span><span class="sxs-lookup"><span data-stu-id="85c5a-310">System.Management.Automation.AliasInfo</span></span>

<span data-ttu-id="85c5a-311">エイリアスを表します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-311">Represents aliases.</span></span>

### <span data-ttu-id="85c5a-312">システム管理. ApplicationInfo</span><span class="sxs-lookup"><span data-stu-id="85c5a-312">System.Management.Automation.ApplicationInfo</span></span>

<span data-ttu-id="85c5a-313">アプリケーションとファイルを表します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-313">Represents applications and files.</span></span>

### <span data-ttu-id="85c5a-314">システムの管理.......</span><span class="sxs-lookup"><span data-stu-id="85c5a-314">System.Management.Automation.CmdletInfo</span></span>

<span data-ttu-id="85c5a-315">コマンドレットを表します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-315">Represents cmdlets.</span></span>

### <span data-ttu-id="85c5a-316">システム管理. FunctionInfo</span><span class="sxs-lookup"><span data-stu-id="85c5a-316">System.Management.Automation.FunctionInfo</span></span>

<span data-ttu-id="85c5a-317">関数とフィルターを表します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-317">Represents functions and filters.</span></span>

## <span data-ttu-id="85c5a-318">注</span><span class="sxs-lookup"><span data-stu-id="85c5a-318">NOTES</span></span>

* <span data-ttu-id="85c5a-319">セッションで同じ名前を持つ複数のコマンドを使用できる場合は、 `Get-Command` コマンド名を入力すると実行されるコマンドが返されます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-319">When more than one command that has the same name is available to the session, `Get-Command` returns the command that runs when you type the command name.</span></span> <span data-ttu-id="85c5a-320">同じ名前を持つコマンドを実行順序で表示するには、 **All** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="85c5a-320">To get commands that have the same name, listed in run order, use the **All** parameter.</span></span> <span data-ttu-id="85c5a-321">詳細については、「[about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md)」(コマンドの優先順位について) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85c5a-321">For more information, see [about_Command_Precedence](../Microsoft.PowerShell.Core/About/about_Command_Precedence.md).</span></span>
* <span data-ttu-id="85c5a-322">モジュールが自動的にインポートされる場合、結果はコマンドレットを使用した場合と同じになり `Import-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-322">When a module is imported automatically, the effect is the same as using the `Import-Module` cmdlet.</span></span> <span data-ttu-id="85c5a-323">モジュールは、コマンド、型、および書式設定ファイルを追加し、セッションでスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-323">The module can add commands, types and formatting files, and run scripts in the session.</span></span>
  <span data-ttu-id="85c5a-324">モジュールの自動インポートを有効化、無効化、および構成するには、ユーザー設定変数を使用し `$PSModuleAutoLoadingPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="85c5a-324">To enable, disable, and configuration automatic importing of modules, use the `$PSModuleAutoLoadingPreference` preference variable.</span></span> <span data-ttu-id="85c5a-325">詳細については、「 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85c5a-325">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="85c5a-326">関連リンク</span><span class="sxs-lookup"><span data-stu-id="85c5a-326">RELATED LINKS</span></span>

[<span data-ttu-id="85c5a-327">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="85c5a-327">Export-PSSession</span></span>](../Microsoft.PowerShell.Utility/Export-PSSession.md)

[<span data-ttu-id="85c5a-328">Get-Help</span><span class="sxs-lookup"><span data-stu-id="85c5a-328">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="85c5a-329">Get-Member</span><span class="sxs-lookup"><span data-stu-id="85c5a-329">Get-Member</span></span>](../Microsoft.PowerShell.Utility/Get-Member.md)

[<span data-ttu-id="85c5a-330">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="85c5a-330">Get-PSDrive</span></span>](../Microsoft.PowerShell.Management/Get-PSDrive.md)

[<span data-ttu-id="85c5a-331">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="85c5a-331">Import-PSSession</span></span>](../Microsoft.PowerShell.Utility/Import-PSSession.md)

[<span data-ttu-id="85c5a-332">about_Command_Precedence</span><span class="sxs-lookup"><span data-stu-id="85c5a-332">about_Command_Precedence</span></span>](About/about_Command_Precedence.md)

