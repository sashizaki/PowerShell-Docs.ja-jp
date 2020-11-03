---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-psrolecapabilityfile?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSRoleCapabilityFile
ms.openlocfilehash: 3dca5f922f31690bb78ccc610b4ed44b7423ca47
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212856"
---
# <span data-ttu-id="31aa6-103">New-PSRoleCapabilityFile</span><span class="sxs-lookup"><span data-stu-id="31aa6-103">New-PSRoleCapabilityFile</span></span>

## <span data-ttu-id="31aa6-104">概要</span><span class="sxs-lookup"><span data-stu-id="31aa6-104">SYNOPSIS</span></span>
<span data-ttu-id="31aa6-105">セッション構成を通じて公開される一連の機能を定義するファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-105">Creates a file that defines a set of capabilities to be exposed through a session configuration.</span></span>

## <span data-ttu-id="31aa6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="31aa6-106">SYNTAX</span></span>

```
New-PSRoleCapabilityFile [-Path] <String> [-Guid <Guid>] [-Author <String>] [-Description <String>]
 [-CompanyName <String>] [-Copyright <String>] [-ModulesToImport <Object[]>] [-VisibleAliases <String[]>]
 [-VisibleCmdlets <Object[]>] [-VisibleFunctions <Object[]>] [-VisibleExternalCommands <String[]>]
 [-VisibleProviders <String[]>] [-ScriptsToProcess <String[]>] [-AliasDefinitions <IDictionary[]>]
 [-FunctionDefinitions <IDictionary[]>] [-VariableDefinitions <Object>] [-EnvironmentVariables <IDictionary>]
 [-TypesToProcess <String[]>] [-FormatsToProcess <String[]>] [-AssembliesToLoad <String[]>]
 [<CommonParameters>]
```

## <span data-ttu-id="31aa6-107">Description</span><span class="sxs-lookup"><span data-stu-id="31aa6-107">DESCRIPTION</span></span>

<span data-ttu-id="31aa6-108">コマンドレットでは、 `New-PSRoleCapabilityFile` セッション構成ファイルを通じて公開できる一連のユーザー機能を定義するファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-108">The `New-PSRoleCapabilityFile` cmdlet creates a file that defines a set of user capabilities that can be exposed through session configuration files.</span></span> <span data-ttu-id="31aa6-109">これには、ユーザーが使用できるコマンドレット、関数、およびスクリプトの決定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-109">This includes determining which cmdlets, functions, and scripts are available to users.</span></span> <span data-ttu-id="31aa6-110">機能ファイルは、セッション構成のプロパティと値のハッシュテーブルを含む、人間が判読できるテキストファイルです。</span><span class="sxs-lookup"><span data-stu-id="31aa6-110">The capability file is a human-readable text file that contains a hash table of session configuration properties and values.</span></span> <span data-ttu-id="31aa6-111">ファイルの拡張子は psrc で、複数のセッション構成で使用できます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-111">The file has a .psrc file name extension, and can be used by more than one session configuration.</span></span>

<span data-ttu-id="31aa6-112">のすべてのパラメーター `New-PSRoleCapabilityFile` は省略可能です。 **path** パラメーターを除き、ファイルのファイルパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-112">All the parameters of `New-PSRoleCapabilityFile` are optional except for the **Path** parameter, which specifies the file path for the file.</span></span> <span data-ttu-id="31aa6-113">コマンドレットを実行するときにパラメーターを含めない場合、パラメーターの説明に示されている場合を除き、セッション構成ファイル内の対応するキーがコメントアウトされます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-113">If you do not include a parameter when you run the cmdlet, the corresponding key in the session configuration file is commented-out, except where noted in the parameter description.</span></span> <span data-ttu-id="31aa6-114">たとえば、 **AssembliesToLoad** パラメーターを含めない場合、セッション構成ファイルのそのセクションはコメントアウトされます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-114">For example, if you do not include the **AssembliesToLoad** parameter then that section of the session configuration file is commented out.</span></span>

<span data-ttu-id="31aa6-115">セッション構成でロール機能ファイルを使用するには、まず、有効な PowerShell モジュールフォルダーの **RoleCapabilities** サブフォルダーにファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-115">To use the role capability file in a session configuration, first place the file in a **RoleCapabilities** subfolder of a valid PowerShell module folder.</span></span> <span data-ttu-id="31aa6-116">次に、PowerShell セッション構成 (.pssc) ファイルの **Roledefinitions** フィールドで、名前を指定してファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-116">Then reference the file by name in the **RoleDefinitions** field in a PowerShell Session Configuration (.pssc) file.</span></span>

<span data-ttu-id="31aa6-117">このコマンドレットは、Windows PowerShell 5.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="31aa6-117">This cmdlet was introduced in Windows PowerShell 5.0.</span></span>

## <span data-ttu-id="31aa6-118">例</span><span class="sxs-lookup"><span data-stu-id="31aa6-118">EXAMPLES</span></span>

### <span data-ttu-id="31aa6-119">例 1: 空のロール機能ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="31aa6-119">Example 1: Create a blank role capability file</span></span>

<span data-ttu-id="31aa6-120">この例では、既定値 (空白) を使用する新しいロール機能ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-120">This example creates a new role capability file that uses the default (blank) values.</span></span> <span data-ttu-id="31aa6-121">後でこのファイルをテキストエディターで編集して、これらの構成設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-121">The file can later be edited in a text editor to change these configuration settings.</span></span>

```powershell
New-PSRoleCapabilityFile -Path ".\ExampleFile.psrc"
```

### <span data-ttu-id="31aa6-122">例 2: ロール機能ファイルを作成し、ユーザーがサービスと VDI コンピューターを再起動できるようにする</span><span class="sxs-lookup"><span data-stu-id="31aa6-122">Example 2: Create a role capability file allowing users to restart services and any VDI computer</span></span>

<span data-ttu-id="31aa6-123">この例では、ユーザーが特定の名前パターンに一致するサービスとコンピューターを再起動できるようにする、サンプルのロール機能ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-123">This example creates a sample role capability file that enables users to restart services and computers that match a specific name pattern.</span></span> <span data-ttu-id="31aa6-124">名前のフィルター処理は、 **Validatepattern** パラメーターを正規表現に設定することによって定義され `VDI\d+` ます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-124">Name filtering is defined by setting the **ValidatePattern** parameter to the regular expression `VDI\d+`.</span></span>

```powershell
$roleParameters = @{
    Path = ".\Maintenance.psrc"
    Author = "User01"
    CompanyName = "Fabrikam Corporation"
    Description = "This role enables users to restart any service and restart any VDI computer."
    ModulesToImport = "Microsoft.PowerShell.Core"
    VisibleCmdlets = "Restart-Service", @{
                      Name = "Restart-Computer"
                      Parameters = @{ Name = "ComputerName"; ValidatePattern = "VDI\d+" }
    }
}
New-PSRoleCapabilityFile @roleParameters
```

## <span data-ttu-id="31aa6-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="31aa6-125">PARAMETERS</span></span>

### <span data-ttu-id="31aa6-126">-エイリアスの定義</span><span class="sxs-lookup"><span data-stu-id="31aa6-126">-AliasDefinitions</span></span>

<span data-ttu-id="31aa6-127">ロール機能ファイルを使用するセッションに、指定されたエイリアスを追加します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-127">Adds the specified aliases to sessions that use the role capability file.</span></span> <span data-ttu-id="31aa6-128">ハッシュ テーブルに次のキーを入力します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-128">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="31aa6-129">名前。</span><span class="sxs-lookup"><span data-stu-id="31aa6-129">Name.</span></span> <span data-ttu-id="31aa6-130">エイリアスの名前。</span><span class="sxs-lookup"><span data-stu-id="31aa6-130">Name of the alias.</span></span> <span data-ttu-id="31aa6-131">このキーは必須です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-131">This key is required.</span></span>
- <span data-ttu-id="31aa6-132">Value。</span><span class="sxs-lookup"><span data-stu-id="31aa6-132">Value.</span></span> <span data-ttu-id="31aa6-133">エイリアスが表すコマンド。</span><span class="sxs-lookup"><span data-stu-id="31aa6-133">The command that the alias represents.</span></span> <span data-ttu-id="31aa6-134">このキーは必須です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-134">This key is required.</span></span>
- <span data-ttu-id="31aa6-135">説明</span><span class="sxs-lookup"><span data-stu-id="31aa6-135">Description.</span></span> <span data-ttu-id="31aa6-136">エイリアスを説明するテキスト文字列。</span><span class="sxs-lookup"><span data-stu-id="31aa6-136">A text string that describes the alias.</span></span> <span data-ttu-id="31aa6-137">このキーはオプションです。</span><span class="sxs-lookup"><span data-stu-id="31aa6-137">This key is optional.</span></span>
- <span data-ttu-id="31aa6-138">オプション。</span><span class="sxs-lookup"><span data-stu-id="31aa6-138">Options.</span></span> <span data-ttu-id="31aa6-139">エイリアスのオプション。</span><span class="sxs-lookup"><span data-stu-id="31aa6-139">Alias options.</span></span> <span data-ttu-id="31aa6-140">このキーはオプションです。</span><span class="sxs-lookup"><span data-stu-id="31aa6-140">This key is optional.</span></span> <span data-ttu-id="31aa6-141">既定値は None です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-141">The default value is None.</span></span> <span data-ttu-id="31aa6-142">このパラメーターに指定できる値は、None、ReadOnly、Constant、Private、または AllScope です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-142">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="31aa6-143">例: `@{Name="hlp";Value="Get-Help";Description="Gets help";Options="ReadOnly"}`</span><span class="sxs-lookup"><span data-stu-id="31aa6-143">For example: `@{Name="hlp";Value="Get-Help";Description="Gets help";Options="ReadOnly"}`</span></span>

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-144">-AssembliesToLoad</span><span class="sxs-lookup"><span data-stu-id="31aa6-144">-AssembliesToLoad</span></span>

<span data-ttu-id="31aa6-145">ロール機能ファイルを使用するセッションに読み込むアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-145">Specifies the assemblies to load into the sessions that use the role capability file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-146">-作成者</span><span class="sxs-lookup"><span data-stu-id="31aa6-146">-Author</span></span>

<span data-ttu-id="31aa6-147">ロール機能ファイルを作成したユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-147">Specifies the user that created the role capability file.</span></span>

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

### <span data-ttu-id="31aa6-148">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="31aa6-148">-CompanyName</span></span>

<span data-ttu-id="31aa6-149">ロール機能ファイルを作成した会社を識別します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-149">Identifies the company that created the role capability file.</span></span>
<span data-ttu-id="31aa6-150">既定値は Unknown です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-150">The default value is Unknown.</span></span>

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

### <span data-ttu-id="31aa6-151">-Copyright</span><span class="sxs-lookup"><span data-stu-id="31aa6-151">-Copyright</span></span>

<span data-ttu-id="31aa6-152">ロール機能ファイルの著作権を指定します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-152">Specifies a copyright for the role capability file.</span></span> <span data-ttu-id="31aa6-153">このパラメーターを省略すると、は `New-PSRoleCapabilityFile` **Author** パラメーターの値を使用して著作権情報ステートメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-153">If you omit this parameter, `New-PSRoleCapabilityFile` generates a copyright statement by using the value of the **Author** parameter.</span></span>

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

### <span data-ttu-id="31aa6-154">-Description</span><span class="sxs-lookup"><span data-stu-id="31aa6-154">-Description</span></span>

<span data-ttu-id="31aa6-155">ロール機能ファイルの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-155">Specifies a description for the role capability file.</span></span>

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

### <span data-ttu-id="31aa6-156">-EnvironmentVariables</span><span class="sxs-lookup"><span data-stu-id="31aa6-156">-EnvironmentVariables</span></span>

<span data-ttu-id="31aa6-157">このロール機能ファイルを公開するセッションの環境変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-157">Specifies the environment variables for sessions that expose this role capability file.</span></span> <span data-ttu-id="31aa6-158">キーが環境変数名で、値が環境変数値のハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-158">Enter a hash table in which the keys are the environment variable names and the values are the environment variable values.</span></span>

<span data-ttu-id="31aa6-159">例: `EnvironmentVariables=@{TestShare="\\\\Server01\TestShare"}`</span><span class="sxs-lookup"><span data-stu-id="31aa6-159">For example: `EnvironmentVariables=@{TestShare="\\\\Server01\TestShare"}`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-160">-FormatsToProcess</span><span class="sxs-lookup"><span data-stu-id="31aa6-160">-FormatsToProcess</span></span>

<span data-ttu-id="31aa6-161">ロール機能ファイルを使用するセッションで実行される書式設定ファイル (types.ps1xml) を指定します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-161">Specifies the formatting files (.ps1xml) that run in sessions that use the role capability file.</span></span> <span data-ttu-id="31aa6-162">このパラメーターの値は、書式設定ファイルの完全パスまたは絶対パスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="31aa6-162">The value of this parameter must be a full or absolute path of the formatting files.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-163">-FunctionDefinitions</span><span class="sxs-lookup"><span data-stu-id="31aa6-163">-FunctionDefinitions</span></span>

<span data-ttu-id="31aa6-164">ロール機能を公開するセッションに、指定された関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-164">Adds the specified functions to sessions that expose the role capability.</span></span> <span data-ttu-id="31aa6-165">ハッシュ テーブルに次のキーを入力します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-165">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="31aa6-166">名前。</span><span class="sxs-lookup"><span data-stu-id="31aa6-166">Name.</span></span> <span data-ttu-id="31aa6-167">関数の名前です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-167">Name of the function.</span></span> <span data-ttu-id="31aa6-168">このキーは必須です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-168">This key is required.</span></span>
- <span data-ttu-id="31aa6-169">Process.</span><span class="sxs-lookup"><span data-stu-id="31aa6-169">ScriptBlock.</span></span> <span data-ttu-id="31aa6-170">関数の本体。</span><span class="sxs-lookup"><span data-stu-id="31aa6-170">Function body.</span></span> <span data-ttu-id="31aa6-171">スクリプト ブロックを入力します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-171">Enter a script block.</span></span> <span data-ttu-id="31aa6-172">このキーは必須です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-172">This key is required.</span></span>
- <span data-ttu-id="31aa6-173">オプション。</span><span class="sxs-lookup"><span data-stu-id="31aa6-173">Options.</span></span> <span data-ttu-id="31aa6-174">関数のオプション。</span><span class="sxs-lookup"><span data-stu-id="31aa6-174">Function options.</span></span> <span data-ttu-id="31aa6-175">このキーはオプションです。</span><span class="sxs-lookup"><span data-stu-id="31aa6-175">This key is optional.</span></span> <span data-ttu-id="31aa6-176">既定値は None です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-176">The default value is None.</span></span> <span data-ttu-id="31aa6-177">このパラメーターに指定できる値は、None、ReadOnly、Constant、Private、または AllScope です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-177">The acceptable values for this parameter are: are None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="31aa6-178">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-178">For example:</span></span>

`@{Name="Get-PowerShellProcess";ScriptBlock={Get-Process PowerShell};Options="AllScope"}`

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-179">-Guid</span><span class="sxs-lookup"><span data-stu-id="31aa6-179">-Guid</span></span>

<span data-ttu-id="31aa6-180">ロール機能ファイルの一意の識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-180">Specifies a unique identifier for the role capability file.</span></span> <span data-ttu-id="31aa6-181">このパラメーターを省略すると、に `New-PSRoleCapabilityFile` よってファイルの GUID が生成されます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-181">If you omit this parameter, `New-PSRoleCapabilityFile` generates a GUID for the file.</span></span> <span data-ttu-id="31aa6-182">PowerShell で新しい GUID を作成するには、「」と入力 `[guid]::NewGuid()` します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-182">To create a new GUID in PowerShell, type `[guid]::NewGuid()`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-183">-ModulesToImport</span><span class="sxs-lookup"><span data-stu-id="31aa6-183">-ModulesToImport</span></span>

<span data-ttu-id="31aa6-184">ロール機能ファイルを使用するセッションに自動的にインポートされるモジュールを指定します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-184">Specifies the modules that are automatically imported into sessions that use the role capability file.</span></span> <span data-ttu-id="31aa6-185">既定では、一覧表示されているモジュールのすべてのコマンドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-185">By default, all the commands in listed modules are visible.</span></span> <span data-ttu-id="31aa6-186">**VisibleCmdlets** または **VisibleFunctions** と共に使用すると、指定したモジュールから表示されるコマンドを制限できます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-186">When used with **VisibleCmdlets** or **VisibleFunctions** , the commands visible from the specified modules can be restricted.</span></span>

<span data-ttu-id="31aa6-187">このパラメーターの値で使用される各モジュールは、文字列またはハッシュテーブルで表すことができます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-187">Each module used in the value of this parameter can be represented by a string or by a hash table.</span></span> <span data-ttu-id="31aa6-188">モジュール文字列は、モジュールの名前のみで構成されています。</span><span class="sxs-lookup"><span data-stu-id="31aa6-188">A module string consists only of the name of the module.</span></span> <span data-ttu-id="31aa6-189">モジュールハッシュテーブルには、 **ModuleName** 、 **ModuleVersion** 、および **GUID** キーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-189">A module hash table can include **ModuleName** , **ModuleVersion** , and **GUID** keys.</span></span> <span data-ttu-id="31aa6-190">**ModuleName** キーのみが必須です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-190">Only the **ModuleName** key is required.</span></span>

<span data-ttu-id="31aa6-191">たとえば、次の値は文字列とハッシュ テーブルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-191">For example, the following value consists of a string and a hash table.</span></span> <span data-ttu-id="31aa6-192">任意の順序での文字列とハッシュ テーブルの組み合わせは有効です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-192">Any combination of strings and hash tables, in any order, is valid.</span></span>

`"TroubleshootingPack", @{ModuleName="PSDiagnostics"; ModuleVersion="1.0.0.0";GUID="c61d6278-02a3-4618-ae37-a524d40a7f44"}`

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-193">-Path</span><span class="sxs-lookup"><span data-stu-id="31aa6-193">-Path</span></span>

<span data-ttu-id="31aa6-194">ロール機能ファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-194">Specifies the path and filename of the role capability file.</span></span> <span data-ttu-id="31aa6-195">ファイルにはファイル `.psrc` 名拡張子が必要です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-195">The file must have a `.psrc` filename extension.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-196">-ScriptsToProcess</span><span class="sxs-lookup"><span data-stu-id="31aa6-196">-ScriptsToProcess</span></span>

<span data-ttu-id="31aa6-197">ロール機能ファイルを使用するセッションに追加するスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-197">Specifies scripts to add to sessions that use the role capability file.</span></span> <span data-ttu-id="31aa6-198">スクリプトのパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-198">Enter the path and file names of the scripts.</span></span> <span data-ttu-id="31aa6-199">このパラメーターの値には、スクリプトファイル名の完全パスまたは絶対パスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31aa6-199">The value of this parameter must be a full or absolute path of the script file names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-200">-TypesToProcess</span><span class="sxs-lookup"><span data-stu-id="31aa6-200">-TypesToProcess</span></span>

<span data-ttu-id="31aa6-201">ロール機能ファイルを使用するセッションに追加する型ファイル (types.ps1xml) を指定します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-201">Specifies type files (.ps1xml) to add to sessions that use the role capability file.</span></span> <span data-ttu-id="31aa6-202">種類のファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-202">Enter the type filenames.</span></span> <span data-ttu-id="31aa6-203">このパラメーターの値には、型のファイル名の完全パスまたは絶対パスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31aa6-203">The value of this parameter must be a full or absolute path of the type filenames.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-204">-変数の定義</span><span class="sxs-lookup"><span data-stu-id="31aa6-204">-VariableDefinitions</span></span>

<span data-ttu-id="31aa6-205">ロール機能ファイルを使用するセッションに追加する変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-205">Specifies variables to add to sessions that use the role capability file.</span></span> <span data-ttu-id="31aa6-206">ハッシュ テーブルに次のキーを入力します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-206">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="31aa6-207">名前。</span><span class="sxs-lookup"><span data-stu-id="31aa6-207">Name.</span></span> <span data-ttu-id="31aa6-208">変数名。</span><span class="sxs-lookup"><span data-stu-id="31aa6-208">Name of the variable.</span></span> <span data-ttu-id="31aa6-209">このキーは必須です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-209">This key is required.</span></span>
- <span data-ttu-id="31aa6-210">Value。</span><span class="sxs-lookup"><span data-stu-id="31aa6-210">Value.</span></span> <span data-ttu-id="31aa6-211">変数の値。</span><span class="sxs-lookup"><span data-stu-id="31aa6-211">Variable value.</span></span> <span data-ttu-id="31aa6-212">このキーは必須です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-212">This key is required.</span></span>
- <span data-ttu-id="31aa6-213">オプション。</span><span class="sxs-lookup"><span data-stu-id="31aa6-213">Options.</span></span> <span data-ttu-id="31aa6-214">変数のオプション。</span><span class="sxs-lookup"><span data-stu-id="31aa6-214">Variable options.</span></span> <span data-ttu-id="31aa6-215">このキーはオプションです。</span><span class="sxs-lookup"><span data-stu-id="31aa6-215">This key is optional.</span></span> <span data-ttu-id="31aa6-216">既定値は None です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-216">The default value is None.</span></span> <span data-ttu-id="31aa6-217">このパラメーターに指定できる値は、None、ReadOnly、Constant、Private、または AllScope です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-217">The acceptable values for this parameter are: are None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="31aa6-218">例: `@{Name="WarningPreference";Value="SilentlyContinue";Options="AllScope"}`</span><span class="sxs-lookup"><span data-stu-id="31aa6-218">For example: `@{Name="WarningPreference";Value="SilentlyContinue";Options="AllScope"}`</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-219">-VisibleAliases</span><span class="sxs-lookup"><span data-stu-id="31aa6-219">-VisibleAliases</span></span>

<span data-ttu-id="31aa6-220">セッションのエイリアスを、このパラメーターの値に指定されたエイリアスと、エイリアス **定義** パラメーターで定義した別名に限定します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-220">Limits the aliases in the session to those aliases specified in the value of this parameter, plus any aliases that you define in the **AliasDefinition** parameter.</span></span> <span data-ttu-id="31aa6-221">ワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="31aa6-221">Wildcard characters are supported.</span></span>
<span data-ttu-id="31aa6-222">既定では、PowerShell エンジンによって定義されたすべてのエイリアスとモジュールがエクスポートするすべてのエイリアスがセッションで表示されます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-222">By default, all aliases that are defined by the PowerShell engine and all aliases that modules export are visible in the session.</span></span>

<span data-ttu-id="31aa6-223">たとえば、使用可能なエイリアスを gm と gcm に限定するには、次の構文を使用します。 `VisibleAliases="gcm", "gp"`</span><span class="sxs-lookup"><span data-stu-id="31aa6-223">For example, to limit the available aliases to gm and gcm use this syntax: `VisibleAliases="gcm", "gp"`</span></span>

<span data-ttu-id="31aa6-224">ロール機能ファイルに **表示** されるパラメーターが含まれている場合、PowerShell は `Import-Module` コマンドレットとその `ipmo` エイリアスをセッションから削除します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-224">When any **Visible** parameter is included in the role capability file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="31aa6-225">-VisibleCmdlets</span><span class="sxs-lookup"><span data-stu-id="31aa6-225">-VisibleCmdlets</span></span>

<span data-ttu-id="31aa6-226">セッションのコマンドレットを、このパラメーターの値に指定されたコマンドレットに制限します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-226">Limits the cmdlets in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="31aa6-227">ワイルドカード文字とモジュール修飾名がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="31aa6-227">Wildcard characters and Module Qualified Names are supported.</span></span>

<span data-ttu-id="31aa6-228">既定では、セッション内のモジュールがエクスポートするすべてのコマンドレットが、セッションで表示されます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-228">By default, all cmdlets that the modules in the session export are visible in the session.</span></span> <span data-ttu-id="31aa6-229">**SessionType** および **ModulesToImport** パラメーターを使用して、どのモジュールとスナップインをセッションにインポートするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-229">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span> <span data-ttu-id="31aa6-230">**ModulesToImport** 内のモジュールがコマンドレットを公開していない場合、は `New-PSRoleCapabilityFile` 適切なモジュールの読み込みを試みます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-230">If no modules in **ModulesToImport** expose the cmdlet, `New-PSRoleCapabilityFile` tries to load the appropriate module.</span></span>

<span data-ttu-id="31aa6-231">セッション構成ファイルに **表示** されているパラメーターがある場合は、PowerShell によって `Import-Module` コマンドレットとそのエイリアスがセッションから削除され `ipmo` ます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-231">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="31aa6-232">-VisibleExternalCommands</span><span class="sxs-lookup"><span data-stu-id="31aa6-232">-VisibleExternalCommands</span></span>

<span data-ttu-id="31aa6-233">セッションで実行できる外部バイナリ、スクリプト、およびコマンドを、このパラメーターの値で指定されているものに制限します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-233">Limits the external binaries, scripts and commands that can be executed in the session to those specified in the value of this parameter.</span></span>

<span data-ttu-id="31aa6-234">既定では、このセッションでは外部コマンドは表示されません。</span><span class="sxs-lookup"><span data-stu-id="31aa6-234">By default, no external commands are visible in this session.</span></span>

<span data-ttu-id="31aa6-235">セッション構成ファイルに **表示** されているパラメーターがある場合は、PowerShell によって `Import-Module` コマンドレットとそのエイリアスがセッションから削除され `ipmo` ます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-235">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="31aa6-236">-VisibleFunctions</span><span class="sxs-lookup"><span data-stu-id="31aa6-236">-VisibleFunctions</span></span>

<span data-ttu-id="31aa6-237">セッションの関数を、このパラメーターの値に指定された関数と、 **Functiondefinitions** パラメーターで定義したすべての関数に制限します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-237">Limits the functions in the session to those specified in the value of this parameter, plus any functions that you define in the **FunctionDefinitions** parameter.</span></span> <span data-ttu-id="31aa6-238">ワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="31aa6-238">Wildcard characters are supported.</span></span>

<span data-ttu-id="31aa6-239">既定では、セッションのモジュールによってエクスポートされたすべての関数は、そのセッションで表示されます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-239">By default, all functions exported by modules in the session are visible in that session.</span></span> <span data-ttu-id="31aa6-240">セッションにインポートするモジュールを特定するには、 **Sessiontype** パラメーターと **ModulesToImport** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-240">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="31aa6-241">セッション構成ファイルに **表示** されているパラメーターがある場合は、PowerShell によって `Import-Module` コマンドレットとそのエイリアスがセッションから削除され `ipmo` ます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-241">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="31aa6-242">-VisibleProviders</span><span class="sxs-lookup"><span data-stu-id="31aa6-242">-VisibleProviders</span></span>

<span data-ttu-id="31aa6-243">セッション内の PowerShell プロバイダーを、このパラメーターの値に指定されているものに制限します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-243">Limits the PowerShell providers in the session to those specified in the value of this parameter.</span></span>
<span data-ttu-id="31aa6-244">ワイルドカード文字がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="31aa6-244">Wildcard characters are supported.</span></span>

<span data-ttu-id="31aa6-245">既定では、セッションのモジュールによってエクスポートされたすべてのプロバイダーがセッションで表示されます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-245">By default, all providers exported by a module in the session are visible in the session.</span></span> <span data-ttu-id="31aa6-246">セッションにインポートするモジュールを特定するには、 **Sessiontype** パラメーターと **ModulesToImport** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="31aa6-246">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="31aa6-247">セッション構成ファイルに **表示** されているパラメーターがある場合は、PowerShell によって `Import-Module` コマンドレットとそのエイリアスがセッションから削除され `ipmo` ます。</span><span class="sxs-lookup"><span data-stu-id="31aa6-247">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

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

### <span data-ttu-id="31aa6-248">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="31aa6-248">CommonParameters</span></span>

<span data-ttu-id="31aa6-249">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="31aa6-249">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="31aa6-250">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31aa6-250">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="31aa6-251">入力</span><span class="sxs-lookup"><span data-stu-id="31aa6-251">INPUTS</span></span>

## <span data-ttu-id="31aa6-252">出力</span><span class="sxs-lookup"><span data-stu-id="31aa6-252">OUTPUTS</span></span>

## <span data-ttu-id="31aa6-253">注</span><span class="sxs-lookup"><span data-stu-id="31aa6-253">NOTES</span></span>

## <span data-ttu-id="31aa6-254">関連リンク</span><span class="sxs-lookup"><span data-stu-id="31aa6-254">RELATED LINKS</span></span>

[<span data-ttu-id="31aa6-255">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="31aa6-255">New-PSSessionConfigurationFile</span></span>](New-PSSessionConfigurationFile.md)

[<span data-ttu-id="31aa6-256">Get-PSSessionCapability</span><span class="sxs-lookup"><span data-stu-id="31aa6-256">Get-PSSessionCapability</span></span>](Get-PSSessionCapability.md)
