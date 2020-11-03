---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itemproperty?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemProperty
ms.openlocfilehash: b2c5b8596da085fab3af7a1545569dd65931a5f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215419"
---
# <span data-ttu-id="befda-103">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="befda-103">Get-ItemProperty</span></span>

## <span data-ttu-id="befda-104">概要</span><span class="sxs-lookup"><span data-stu-id="befda-104">SYNOPSIS</span></span>
<span data-ttu-id="befda-105">指定した項目のプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="befda-105">Gets the properties of a specified item.</span></span>

## <span data-ttu-id="befda-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="befda-106">SYNTAX</span></span>

### <span data-ttu-id="befda-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="befda-107">Path (Default)</span></span>

```
Get-ItemProperty [-Path] <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="befda-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="befda-108">LiteralPath</span></span>

```
Get-ItemProperty -LiteralPath <String[]> [[-Name] <String[]>] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="befda-109">Description</span><span class="sxs-lookup"><span data-stu-id="befda-109">DESCRIPTION</span></span>

<span data-ttu-id="befda-110">`Get-ItemProperty`コマンドレットは、指定された項目のプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="befda-110">The `Get-ItemProperty` cmdlet gets the properties of the specified items.</span></span>
<span data-ttu-id="befda-111">たとえば、このコマンドレットを使用すると、ファイルオブジェクトの LastAccessTime プロパティの値を取得できます。</span><span class="sxs-lookup"><span data-stu-id="befda-111">For example, you can use this cmdlet to get the value of the LastAccessTime property of a file object.</span></span>
<span data-ttu-id="befda-112">このコマンドレットを使用して、レジストリエントリとその値を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="befda-112">You can also use this cmdlet to view registry entries and their values.</span></span>

## <span data-ttu-id="befda-113">例</span><span class="sxs-lookup"><span data-stu-id="befda-113">EXAMPLES</span></span>

### <span data-ttu-id="befda-114">例 1: 特定のディレクトリに関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="befda-114">Example 1: Get information about a specific directory</span></span>

<span data-ttu-id="befda-115">このコマンドは、"C:\Windows" ディレクトリに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="befda-115">This command gets information about the "C:\Windows" directory.</span></span>

```powershell
Get-ItemProperty C:\Windows
```

### <span data-ttu-id="befda-116">例 2: 特定のファイルのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="befda-116">Example 2: Get the properties of a specific file</span></span>

<span data-ttu-id="befda-117">このコマンドは、"C:\Test\Weather.xls" ファイルのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="befda-117">This command gets the properties of the "C:\Test\Weather.xls" file.</span></span>
<span data-ttu-id="befda-118">結果は、 `Format-List` 出力を一覧として表示するためにコマンドレットにパイプされます。</span><span class="sxs-lookup"><span data-stu-id="befda-118">The result is piped to the `Format-List` cmdlet to display the output as a list.</span></span>

```powershell
Get-ItemProperty C:\Test\Weather.xls | Format-List
```

### <span data-ttu-id="befda-119">例 3: レジストリサブキーにレジストリエントリの値名とデータを表示する</span><span class="sxs-lookup"><span data-stu-id="befda-119">Example 3: Display the value name and data of registry entries in a registry subkey</span></span>

<span data-ttu-id="befda-120">このコマンドは、"CurrentVersion" レジストリサブキーに格納されている各レジストリエントリの値の名前とデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="befda-120">This command displays the value name and data of each of the registry entries contained in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="befda-121">このコマンドでは、という名前の PowerShell ドライブが `HKLM:` レジストリの "HKEY_LOCAL_MACHINE" ハイブにマップされている必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="befda-121">Note that the command requires that there is a PowerShell drive named `HKLM:` that is mapped to the "HKEY_LOCAL_MACHINE" hive of the registry.</span></span>
<span data-ttu-id="befda-122">既定では、その名前とマッピングを持つドライブが PowerShell で使用できます。</span><span class="sxs-lookup"><span data-stu-id="befda-122">A drive with that name and mapping is available in PowerShell by default.</span></span>
<span data-ttu-id="befda-123">また、プロバイダー名の後に 2 つのコロンを続けた以下の代替パスを使用して、このレジストリ サブキーのパスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="befda-123">Alternatively, the path to this registry subkey can be specified by using the following alternative path that begins with the provider name followed by two colons:</span></span>

<span data-ttu-id="befda-124">"Registry:: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion"。</span><span class="sxs-lookup"><span data-stu-id="befda-124">"Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion".</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

### <span data-ttu-id="befda-125">例 4: レジストリサブキーのレジストリエントリの値の名前とデータを取得する</span><span class="sxs-lookup"><span data-stu-id="befda-125">Example 4: Get the value name and data of a registry entry in a registry subkey</span></span>

<span data-ttu-id="befda-126">このコマンドは、"CurrentVersion" レジストリサブキーの "ProgramFilesDir" レジストリエントリの値の名前とデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="befda-126">This command gets the value name and data of the "ProgramFilesDir" registry entry in the "CurrentVersion" registry subkey.</span></span>
<span data-ttu-id="befda-127">このコマンドは、 **Path** パラメーターを使用してサブキーを指定し、Name パラメーターを使用してエントリの値名を指定します。</span><span class="sxs-lookup"><span data-stu-id="befda-127">The command uses the **Path** parameter to specify the subkey and the Name parameter to specify the value name of the entry.</span></span>

<span data-ttu-id="befda-128">このコマンドは、バックチックまたはアクサングラーブ () (PowerShell の継続文字) を使用して、 \` 2 行目でコマンドを続行します。</span><span class="sxs-lookup"><span data-stu-id="befda-128">The command uses a back tick or grave accent (\`), the PowerShell continuation character, to continue the command on the second line.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name "ProgramFilesDir"
```

### <span data-ttu-id="befda-129">例 5: レジストリキー内のレジストリエントリの値の名前とデータを取得する</span><span class="sxs-lookup"><span data-stu-id="befda-129">Example 5: Get the value names and data of registry entries in a registry key</span></span>

<span data-ttu-id="befda-130">このコマンドは、"PowerShellEngine" レジストリキーのレジストリエントリの値の名前とデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="befda-130">This command gets the value names and data of the registry entries in the "PowerShellEngine" registry key.</span></span>
<span data-ttu-id="befda-131">次のサンプル出力に結果を示します。</span><span class="sxs-lookup"><span data-stu-id="befda-131">The results are shown in the following sample output.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\PowerShellEngine
```

```output
ApplicationBase         : C:\Windows\system32\WindowsPowerShell\v1.0\
ConsoleHostAssemblyName : Microsoft.PowerShell.ConsoleHost, Version=1.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, ProcessorArchitecture=msil
PowerShellVersion       : 2.0
RuntimeVersion          : v2.0.50727
CTPVersion              : 5
PSCompatibleVersion     : 1.0,2.0
```

### <span data-ttu-id="befda-132">例 6: レジストリ値とデータの結果を取得、書式設定、および表示する</span><span class="sxs-lookup"><span data-stu-id="befda-132">Example 6: Get, format, and display the results of registry values and data</span></span>

<span data-ttu-id="befda-133">この例では、 `Get-ItemProperty` レジストリ値とデータを見やすくし、結果を簡単に解釈できるように、一覧内のコマンドの出力を書式設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="befda-133">This example shows how to format the output of a `Get-ItemProperty` command in a list to make it easy to see the registry values and data and to make it easy to interpret the results.</span></span>

<span data-ttu-id="befda-134">最初のコマンドは、 `Get-ItemProperty` コマンドレットを使用して、 **Microsoft PowerShell** サブキーのレジストリエントリを取得します。</span><span class="sxs-lookup"><span data-stu-id="befda-134">The first command uses the `Get-ItemProperty` cmdlet to get the registry entries in the **Microsoft.PowerShell** subkey.</span></span>
<span data-ttu-id="befda-135">このサブキーには、PowerShell の既定のシェルのオプションが格納されます。</span><span class="sxs-lookup"><span data-stu-id="befda-135">This subkey stores options for the default shell for PowerShell.</span></span>
<span data-ttu-id="befda-136">次のサンプル出力に結果を示します。</span><span class="sxs-lookup"><span data-stu-id="befda-136">The results are shown in the following sample output.</span></span>

<span data-ttu-id="befda-137">出力には、"Path" と "Set-executionpolicy" という2つのレジストリエントリがあることが示されています。</span><span class="sxs-lookup"><span data-stu-id="befda-137">The output shows that there are two registry entries, "Path" and "ExecutionPolicy".</span></span>
<span data-ttu-id="befda-138">レジストリ キーに含まれるエントリが 5 つよりも少ない場合、既定では表形式で表示されますが、通常は一覧形式の方がわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="befda-138">When a registry key contains fewer than five entries, by default it is displayed in a table, but it is often easier to view in a list.</span></span>

<span data-ttu-id="befda-139">2番目のコマンドは、同じコマンドを使用し `Get-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="befda-139">The second command uses the same `Get-ItemProperty` command.</span></span>
<span data-ttu-id="befda-140">ただし今回は、コマンドはパイプライン演算子 () を使用して `|` コマンドの結果をコマンドレットに送信し `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="befda-140">However, this time, the command uses a pipeline operator (`|`) to send the results of the command to the `Format-List` cmdlet.</span></span>
<span data-ttu-id="befda-141">このコマンドでは、 `Format-List` Property パラメーターを値 ' \* ' (all) と共に使用して、リスト内のオブジェクトのすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="befda-141">The `Format-List` command uses the Property parameter with a value of '\*' (all) to display all of the properties of the objects in a list.</span></span>
<span data-ttu-id="befda-142">次のサンプル出力に結果を示します。</span><span class="sxs-lookup"><span data-stu-id="befda-142">The results are shown in the following sample output.</span></span>

<span data-ttu-id="befda-143">結果の表示には、"Path" および "Set-executionpolicy" レジストリエントリと、レジストリキーオブジェクトのいくつかのあまり知られていないプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="befda-143">The resulting display shows the "Path" and "ExecutionPolicy" registry entries, along with several less familiar properties of the registry key object.</span></span>
<span data-ttu-id="befda-144">PS というプレフィックスが付いたその他のプロパティは、レジストリキーを表すオブジェクトなど、PowerShell カスタムオブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="befda-144">The other properties, prefixed with PS, are properties of PowerShell custom objects, such as the objects that represent the registry keys.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell
```

```output
Path                                                        ExecutionPolicy
----                                                        ---------------
C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe   RemoteSigned
```

```powershell
Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds\Microsoft.PowerShell | Format-List -Property *
```

```output
PSPath          : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds\Micro
soft.PowerShell
PSParentPath    : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\Microsoft\PowerShell\1\ShellIds
PSChildName     : Microsoft.PowerShell
PSDrive         : HKLM
PSProvider      : Microsoft.PowerShell.Core\Registry
Path            : C:\Windows\system32\WindowsPowerShell\v1.0\powershell.exe
ExecutionPolicy : RemoteSigned
```

## <span data-ttu-id="befda-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="befda-145">PARAMETERS</span></span>

### <span data-ttu-id="befda-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="befda-146">-Credential</span></span>

<span data-ttu-id="befda-147">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="befda-147">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="befda-148">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="befda-148">The default is the current user.</span></span>

<span data-ttu-id="befda-149">「User01」や「Domain01\User01」のようなユーザー名を入力するか、  コマンドレットで生成されるような `Get-Credential` オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="befda-149">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="befda-150">ユーザー名を入力すると、パスワードの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="befda-150">If you type a user name, you are prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="befda-151">このパラメーターは、Windows PowerShell でインストールされるプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="befda-151">This parameter is not supported by any providers installed with Windows PowerShell.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="befda-152">-除外</span><span class="sxs-lookup"><span data-stu-id="befda-152">-Exclude</span></span>

<span data-ttu-id="befda-153">このコマンドレットによって操作から除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="befda-153">Specifies, as a string array, an item or items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="befda-154">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="befda-154">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="befda-155">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="befda-155">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="befda-156">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="befda-156">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="befda-157">-Filter</span><span class="sxs-lookup"><span data-stu-id="befda-157">-Filter</span></span>

<span data-ttu-id="befda-158">プロバイダーの形式または言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="befda-158">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="befda-159">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="befda-159">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="befda-160">ワイルドカード文字の使用など、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="befda-160">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="befda-161">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="befda-161">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="befda-162">-Include</span><span class="sxs-lookup"><span data-stu-id="befda-162">-Include</span></span>

<span data-ttu-id="befda-163">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="befda-163">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="befda-164">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="befda-164">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="befda-165">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="befda-165">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="befda-166">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="befda-166">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="befda-167">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="befda-167">-LiteralPath</span></span>

<span data-ttu-id="befda-168">プロパティの現在の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="befda-168">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="befda-169">**Path** パラメーターと異なり、 **LiteralPath** の値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="befda-169">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="befda-170">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="befda-170">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="befda-171">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="befda-171">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="befda-172">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="befda-172">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="befda-173">-Name</span><span class="sxs-lookup"><span data-stu-id="befda-173">-Name</span></span>

<span data-ttu-id="befda-174">取得するプロパティの名前を 1 つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="befda-174">Specifies the name of the property or properties to retrieve.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="befda-175">-Path</span><span class="sxs-lookup"><span data-stu-id="befda-175">-Path</span></span>

<span data-ttu-id="befda-176">項目のパスを 1 つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="befda-176">Specifies the path to the item or items.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="befda-177">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="befda-177">-UseTransaction</span></span>

<span data-ttu-id="befda-178">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="befda-178">Includes the command in the active transaction.</span></span>
<span data-ttu-id="befda-179">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="befda-179">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="befda-180">詳細については、「アクティブなトランザクションにコマンドを含める」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="befda-180">For more information, see Includes the command in the active transaction.</span></span>
<span data-ttu-id="befda-181">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="befda-181">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="befda-182">詳細については、「[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="befda-182">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="befda-183">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="befda-183">CommonParameters</span></span>

<span data-ttu-id="befda-184">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="befda-184">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="befda-185">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="befda-185">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="befda-186">入力</span><span class="sxs-lookup"><span data-stu-id="befda-186">INPUTS</span></span>

### <span data-ttu-id="befda-187">System.String</span><span class="sxs-lookup"><span data-stu-id="befda-187">System.String</span></span>

<span data-ttu-id="befda-188">パイプを使用して、パスを含む文字列をにパイプすることができ `Get-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="befda-188">You can pipe a string that contains a path to `Get-ItemProperty`.</span></span>

## <span data-ttu-id="befda-189">出力</span><span class="sxs-lookup"><span data-stu-id="befda-189">OUTPUTS</span></span>

### <span data-ttu-id="befda-190">System.string、System.string、System.string です。</span><span class="sxs-lookup"><span data-stu-id="befda-190">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="befda-191">`Get-ItemProperty` 取得する項目プロパティごとにオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="befda-191">`Get-ItemProperty` returns an object for each item property that it gets.</span></span>
<span data-ttu-id="befda-192">オブジェクトの型は、取得するオブジェクトによって異なります。</span><span class="sxs-lookup"><span data-stu-id="befda-192">The object type depends on the object that is retrieved.</span></span>
<span data-ttu-id="befda-193">たとえば、ファイル システム ドライブでは、ファイルまたはフォルダーが返されます。</span><span class="sxs-lookup"><span data-stu-id="befda-193">For example, in a file system drive, it might return a file or folder.</span></span>

## <span data-ttu-id="befda-194">注</span><span class="sxs-lookup"><span data-stu-id="befda-194">NOTES</span></span>

<span data-ttu-id="befda-195">`Get-ItemProperty`コマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="befda-195">The `Get-ItemProperty` cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="befda-196">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力し `Get-PSProvider` ます。</span><span class="sxs-lookup"><span data-stu-id="befda-196">To list the providers available in your session, type "`Get-PSProvider`".</span></span> <span data-ttu-id="befda-197">詳細については、「about_Providers」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="befda-197">For more information, see about_Providers.</span></span>

## <span data-ttu-id="befda-198">関連リンク</span><span class="sxs-lookup"><span data-stu-id="befda-198">RELATED LINKS</span></span>

[<span data-ttu-id="befda-199">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="befda-199">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="befda-200">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="befda-200">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="befda-201">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="befda-201">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="befda-202">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="befda-202">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="befda-203">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="befda-203">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="befda-204">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="befda-204">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="befda-205">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="befda-205">Set-ItemProperty</span></span>](Set-ItemProperty.md)
