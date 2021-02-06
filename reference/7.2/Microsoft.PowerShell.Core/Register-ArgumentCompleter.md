---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 05/20/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/register-argumentcompleter?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Register-ArgumentCompleter
ms.openlocfilehash: e98de608630a59ff77ca701876986ffb29780a4a
ms.sourcegitcommit: 9a86cac80402d8193147058d4ba50e07b26059dd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "99602198"
---
# <span data-ttu-id="ca0b2-102">Register-ArgumentCompleter</span><span class="sxs-lookup"><span data-stu-id="ca0b2-102">Register-ArgumentCompleter</span></span>

## <span data-ttu-id="ca0b2-103">概要</span><span class="sxs-lookup"><span data-stu-id="ca0b2-103">SYNOPSIS</span></span>

<span data-ttu-id="ca0b2-104">カスタム引数 completer を登録します。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-104">Registers a custom argument completer.</span></span>

## <span data-ttu-id="ca0b2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ca0b2-105">SYNTAX</span></span>

### <span data-ttu-id="ca0b2-106">このセット</span><span class="sxs-lookup"><span data-stu-id="ca0b2-106">NativeSet</span></span>

```
Register-ArgumentCompleter -CommandName <String[]> -ScriptBlock <ScriptBlock> [-Native]
 [<CommonParameters>]
```

### <span data-ttu-id="ca0b2-107">PowerShellSet</span><span class="sxs-lookup"><span data-stu-id="ca0b2-107">PowerShellSet</span></span>

```
Register-ArgumentCompleter [-CommandName <String[]>] -ParameterName <String>
 -ScriptBlock <ScriptBlock> [<CommonParameters>]
```

## <span data-ttu-id="ca0b2-108">Description</span><span class="sxs-lookup"><span data-stu-id="ca0b2-108">DESCRIPTION</span></span>

<span data-ttu-id="ca0b2-109">コマンドレットにより、 `Register-ArgumentCompleter` カスタム引数 completer が登録されます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-109">The `Register-ArgumentCompleter` cmdlet registers a custom argument completer.</span></span> <span data-ttu-id="ca0b2-110">引数 completer を使用すると、指定した任意のコマンドに対して、実行時に動的にタブ補完を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-110">An argument completer allows you to provide dynamic tab completion, at run time for any command that you specify.</span></span>

## <span data-ttu-id="ca0b2-111">例</span><span class="sxs-lookup"><span data-stu-id="ca0b2-111">EXAMPLES</span></span>

### <span data-ttu-id="ca0b2-112">例 1: カスタム引数 completer を登録する</span><span class="sxs-lookup"><span data-stu-id="ca0b2-112">Example 1: Register a custom argument completer</span></span>

<span data-ttu-id="ca0b2-113">次の例では、コマンドレットの **Id** パラメーターに completer 引数を登録し `Set-TimeZone` ます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-113">The following example registers an argument completer for the **Id** parameter of the `Set-TimeZone` cmdlet.</span></span>

```powershell
$scriptBlock = {
    param($commandName, $parameterName, $wordToComplete, $commandAst, $fakeBoundParameters)

    (Get-TimeZone -ListAvailable).Id | Where-Object {
        $_ -like "$wordToComplete*"
    } | ForEach-Object {
          "'$_'"
    }
}
Register-ArgumentCompleter -CommandName Set-TimeZone -ParameterName Id -ScriptBlock $scriptBlock
```

<span data-ttu-id="ca0b2-114">最初のコマンドは、ユーザーが <kbd>Tab キー</kbd>を押したときに渡される必須パラメーターを受け取るスクリプトブロックを作成します。詳細については、 **ScriptBlock** パラメーターの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-114">The first command creates a script block which takes the required parameters which are passed in when the user presses <kbd>Tab</kbd>. For more information, see the **ScriptBlock** parameter description.</span></span>

<span data-ttu-id="ca0b2-115">スクリプトブロック内では、 **Id** に使用できる値はコマンドレットを使用して取得され `Get-TimeZone` ます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-115">Within the script block, the available values for **Id** are retrieved using the `Get-TimeZone` cmdlet.</span></span> <span data-ttu-id="ca0b2-116">各タイムゾーンの **Id** プロパティは、パイプを使用してコマンドレットに渡され `Where-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-116">The **Id** property for each Time Zone is piped to the `Where-Object` cmdlet.</span></span> <span data-ttu-id="ca0b2-117">`Where-Object`コマンドレットは、によって指定された値で始まらない id をフィルターで除外します `$wordToComplete` 。これは、 <kbd>Tab キー</kbd>を押す前にユーザーが入力したテキストを表します。フィルター選択された id は、 `ForEach-Object` 値にスペースが含まれている場合に、各値が引用符で囲まれたコマンドレットにパイプされます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-117">The `Where-Object` cmdlet filters out any ids that do not start with the value provided by `$wordToComplete`, which represents the text the user typed before they pressed <kbd>Tab</kbd>. The filtered ids are piped to the `ForEach-Object` cmdlet which encloses each value in quotes, should the value contain spaces.</span></span>

<span data-ttu-id="ca0b2-118">2番目のコマンドは、scriptblock、 **ParameterName** **Id** 、および **CommandName** を渡して、引数 completer を登録し `Set-TimeZone` ます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-118">The second command registers the argument completer by passing the scriptblock, the **ParameterName** **Id** and the **CommandName** `Set-TimeZone`.</span></span>

### <span data-ttu-id="ca0b2-119">例 2: タブ補完の値に詳細を追加する</span><span class="sxs-lookup"><span data-stu-id="ca0b2-119">Example 2: Add details to your tab completion values</span></span>

<span data-ttu-id="ca0b2-120">次の例では、コマンドレットの **Name** パラメーターのタブ補完を上書き `Stop-Service` し、実行中のサービスだけを返します。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-120">The following example overwrites tab completion for the **Name** parameter of the `Stop-Service` cmdlet and only returns running services.</span></span>

```powershell
$s = {
    param($commandName, $parameterName, $wordToComplete, $commandAst, $fakeBoundParameters)
    $services = Get-Service | Where-Object {$_.Status -eq "Running" -and $_.Name -like "$wordToComplete*"}
    $services | ForEach-Object {
        New-Object -Type System.Management.Automation.CompletionResult -ArgumentList $_.Name,
            $_.Name,
            "ParameterValue",
            $_.Name
    }
}
Register-ArgumentCompleter -CommandName Stop-Service -ParameterName Name -ScriptBlock $s
```

<span data-ttu-id="ca0b2-121">最初のコマンドは、ユーザーが <kbd>Tab キー</kbd>を押したときに渡される必須パラメーターを受け取るスクリプトブロックを作成します。詳細については、 **ScriptBlock** パラメーターの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-121">The first command creates a script block which takes the required parameters which are passed in when the user presses <kbd>Tab</kbd>. For more information, see the **ScriptBlock** parameter description.</span></span>

<span data-ttu-id="ca0b2-122">スクリプトブロック内では、最初のコマンドは、コマンドレットを使用して実行中のすべてのサービスを取得し `Where-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-122">Within the script block, the first command retrieves all running services using the `Where-Object` cmdlet.</span></span> <span data-ttu-id="ca0b2-123">サービスは、パイプを介してコマンドレットに渡され `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-123">The services are piped to the `ForEach-Object` cmdlet.</span></span> <span data-ttu-id="ca0b2-124">`ForEach-Object`このコマンドレットは、新しい system.servicemodel オブジェクトを作成し、現在のサービスの名前 (パイプライン変数によって表されます) を設定し[ます。](/dotnet/api/system.management.automation.completionresult) `$_.Name`</span><span class="sxs-lookup"><span data-stu-id="ca0b2-124">The `ForEach-Object` cmdlet creates a new [System.Management.Automation.CompletionResult](/dotnet/api/system.management.automation.completionresult) object and populates it with the name of the current service (represented by the pipeline variable `$_.Name`).</span></span>

<span data-ttu-id="ca0b2-125">入力 **可能オブジェクトを使用すると、** 返される各値に追加の詳細を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-125">The **CompletionResult** object allows you to provide additional details to each returned value:</span></span>

- <span data-ttu-id="ca0b2-126">入力候補 **テキスト**(String)-オートコンプリートの結果として使用されるテキスト。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-126">**completionText** (String) - The text to be used as the auto completion result.</span></span> <span data-ttu-id="ca0b2-127">これは、コマンドに送信される値です。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-127">This is the value sent to the command.</span></span>
- <span data-ttu-id="ca0b2-128">**listitemtext** (String)-ユーザーが <kbd>Ctrl</kbd> + <kbd>Space</kbd>キーを押したときなど、一覧に表示されるテキスト。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-128">**listItemText** (String) - The text to be displayed in a list, such as when the user presses <kbd>Ctrl</kbd>+<kbd>Space</kbd>.</span></span> <span data-ttu-id="ca0b2-129">これは表示のみに使用され、選択された場合はコマンドに渡されません。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-129">This is used for display only and is not passed to the command when selected.</span></span>
- <span data-ttu-id="ca0b2-130">**resultType** ([入力](/dotnet/api/system.management.automation.completionresulttype)候補)-完了結果の型。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-130">**resultType** ([CompletionResultType](/dotnet/api/system.management.automation.completionresulttype)) - The type of completion result.</span></span>
- <span data-ttu-id="ca0b2-131">**tooltip** (String)-オブジェクトについての詳細情報が表示されたツールヒントのテキスト。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-131">**toolTip** (String) - The text for the tooltip with details to be displayed about the object.</span></span>
  <span data-ttu-id="ca0b2-132">これは、ユーザーが<kbd>Ctrl</kbd>Space キーを押した後に項目を選択したときに表示され + <kbd></kbd>ます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-132">This is visible when the user selects an item after pressing <kbd>Ctrl</kbd>+<kbd>Space</kbd>.</span></span>

<span data-ttu-id="ca0b2-133">最後のコマンドは、停止したサービスをコマンドレットに手動で渡すことができることを示して `Stop-Service` います。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-133">The last command demonstrates that stopped services can still be passed in manually to the `Stop-Service` cmdlet.</span></span> <span data-ttu-id="ca0b2-134">影響を受けるのは、タブ補完だけです。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-134">The tab completion is the only aspect affected.</span></span>

### <span data-ttu-id="ca0b2-135">例 3: カスタムネイティブ引数 completer を登録する</span><span class="sxs-lookup"><span data-stu-id="ca0b2-135">Example 3: Register a custom Native argument completer</span></span>

<span data-ttu-id="ca0b2-136">**ネイティブパラメーターを** 使用すると、ネイティブコマンドのタブ補完を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-136">You can use the **Native** parameter to provide tab-completion for a native command.</span></span> <span data-ttu-id="ca0b2-137">次の例では、 `dotnet` コマンドラインインターフェイス (CLI) のタブ補完を追加します。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-137">The following example adds tab-completion for the `dotnet` Command Line Interface (CLI).</span></span>

> [!NOTE]
> <span data-ttu-id="ca0b2-138">`dotnet complete`コマンドは、バージョン2.0 以降の dotnet cli でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-138">The `dotnet complete` command is only available in version 2.0 and greater of the dotnet cli.</span></span>

```powershell
$scriptblock = {
    param($wordToComplete, $commandAst, $cursorPosition)
        dotnet complete --position $cursorPosition $commandAst.ToString() | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
        }
}
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock $scriptblock
```

<span data-ttu-id="ca0b2-139">最初のコマンドは、ユーザーが <kbd>Tab キー</kbd>を押したときに渡される必須パラメーターを受け取るスクリプトブロックを作成します。詳細については、 **ScriptBlock** パラメーターの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-139">The first command creates a script block which takes the required parameters which are passed in when the user presses <kbd>Tab</kbd>. For more information, see the **ScriptBlock** parameter description.</span></span>

<span data-ttu-id="ca0b2-140">スクリプトブロック内では、 `dotnet complete` タブ補完を実行するためにコマンドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-140">Within the script block, the `dotnet complete` command is used to perform the tab completion.</span></span>
<span data-ttu-id="ca0b2-141">結果はパイプを使用してコマンドレットに渡されます。この `ForEach-Object` コマンドレット [は、](/dotnet/api/system.management.automation.completionresult)値ごとに新しい "**補完結果**" オブジェクトを作成するために、このクラスの **新しい** 静的メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-141">The results are piped to the `ForEach-Object` cmdlet which use the **new** static method of the [System.Management.Automation.CompletionResult](/dotnet/api/system.management.automation.completionresult) class to create a new **CompletionResult** object for each value.</span></span>

## <span data-ttu-id="ca0b2-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ca0b2-142">PARAMETERS</span></span>

### <span data-ttu-id="ca0b2-143">-CommandName</span><span class="sxs-lookup"><span data-stu-id="ca0b2-143">-CommandName</span></span>

<span data-ttu-id="ca0b2-144">コマンドの名前を配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-144">Specifies the name of the commands as an array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NativeSet, PowerShellSet
Aliases:

Required: True (NativeSet), False (PowerShellSet)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca0b2-145">-ネイティブ</span><span class="sxs-lookup"><span data-stu-id="ca0b2-145">-Native</span></span>

<span data-ttu-id="ca0b2-146">引数 completer が、PowerShell がパラメーター名を完了できないネイティブコマンド用であることを示します。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-146">Indicates that the argument completer is for a native command where PowerShell cannot complete parameter names.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NativeSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca0b2-147">-ParameterName</span><span class="sxs-lookup"><span data-stu-id="ca0b2-147">-ParameterName</span></span>

<span data-ttu-id="ca0b2-148">引数を完了するパラメーターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-148">Specifies the name of the parameter whose argument is being completed.</span></span> <span data-ttu-id="ca0b2-149">指定されたパラメーター名に、コマンドレットの **ForegroundColor** パラメーターなどの列挙値を指定することはできません `Write-Host` 。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-149">The parameter name specified cannot be an enumerated value, such as the **ForegroundColor** parameter of the `Write-Host` cmdlet.</span></span>

<span data-ttu-id="ca0b2-150">列挙型の詳細については、「 [about_Enum](./About/about_Enum.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-150">For more information on enums, see [about_Enum](./About/about_Enum.md).</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca0b2-151">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="ca0b2-151">-ScriptBlock</span></span>

<span data-ttu-id="ca0b2-152">タブ補完を実行するために実行するコマンドを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-152">Specifies the commands to run to perform tab completion.</span></span> <span data-ttu-id="ca0b2-153">指定したスクリプトブロックは、入力を完了する値を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-153">The script block you provide should return the values that complete the input.</span></span> <span data-ttu-id="ca0b2-154">スクリプトブロックは、パイプライン ( `ForEach-Object` 、など `Where-Object` )、または別の適切なメソッドを使用して、値のロールアウトを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-154">The script block must unroll the values using the pipeline (`ForEach-Object`, `Where-Object`, etc.), or another suitable method.</span></span> <span data-ttu-id="ca0b2-155">値の配列を返すと、PowerShell は配列全体を **1 つ** のタブ補完値として扱います。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-155">Returning an array of values causes PowerShell to treat the entire array as **one** tab completion value.</span></span>

<span data-ttu-id="ca0b2-156">スクリプトブロックでは、以下のパラメーターを以下の順序で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-156">The script block must accept the following parameters in the order specified below.</span></span> <span data-ttu-id="ca0b2-157">PowerShell では位置によって値が渡されるため、パラメーターの名前は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-157">The names of the parameters aren't important because PowerShell passes in the values by position.</span></span>

- <span data-ttu-id="ca0b2-158">`$commandName` (位置 0)-このパラメーターには、スクリプトブロックがタブ補完を提供するコマンドの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-158">`$commandName` (Position 0) - This parameter is set to the name of the command for which the script block is providing tab completion.</span></span>
- <span data-ttu-id="ca0b2-159">`$parameterName` (位置 1)-このパラメーターは、値にタブ補完が必要なパラメーターに設定されています。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-159">`$parameterName` (Position 1) - This parameter is set to the parameter whose value requires tab completion.</span></span>
- <span data-ttu-id="ca0b2-160">`$wordToComplete` (位置 2)-このパラメーターは、 <kbd>Tab キー</kbd>を押す前にユーザーが指定した値に設定されます。スクリプトブロックは、この値を使用してタブ補完の値を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-160">`$wordToComplete` (Position 2) - This parameter is set to value the user has provided before they pressed <kbd>Tab</kbd>. Your script block should use this value to determine tab completion values.</span></span>
- <span data-ttu-id="ca0b2-161">`$commandAst` (位置 3)-このパラメーターは、現在の入力行の抽象構文ツリー (AST) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-161">`$commandAst` (Position 3) - This parameter is set to the Abstract Syntax Tree (AST) for the current input line.</span></span> <span data-ttu-id="ca0b2-162">詳細については、「 [Ast クラス](/dotnet/api/system.management.automation.language.ast)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-162">For more information, see [Ast Class](/dotnet/api/system.management.automation.language.ast).</span></span>
- <span data-ttu-id="ca0b2-163">`$fakeBoundParameters` (位置 4)-このパラメーターは、 `$PSBoundParameters` ユーザーが <kbd>Tab キー</kbd>を押した前に、コマンドレットのを含むハッシュテーブルに設定されます。詳細については、「 [about_Automatic_Variables](./About/about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-163">`$fakeBoundParameters` (Position 4) - This parameter is set to a hashtable containing the `$PSBoundParameters` for the cmdlet, before the user pressed <kbd>Tab</kbd>. For more information, see [about_Automatic_Variables](./About/about_Automatic_Variables.md).</span></span>

<span data-ttu-id="ca0b2-164">**ネイティブ** パラメーターを指定する場合、スクリプトブロックは、指定された順序で次のパラメーターを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-164">When you specify the **Native** parameter, the script block must take the following parameters in the specified order.</span></span> <span data-ttu-id="ca0b2-165">PowerShell では位置によって値が渡されるため、パラメーターの名前は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-165">The names of the parameters aren't important because PowerShell passes in the values by position.</span></span>

- <span data-ttu-id="ca0b2-166">`$wordToComplete` (位置 0)-このパラメーターは、 <kbd>Tab キー</kbd>を押す前にユーザーが指定した値に設定されます。スクリプトブロックは、この値を使用してタブ補完の値を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-166">`$wordToComplete` (Position 0) - This parameter is set to value the user has provided before they pressed <kbd>Tab</kbd>. Your script block should use this value to determine tab completion values.</span></span>
- <span data-ttu-id="ca0b2-167">`$commandAst` (Position 1)-このパラメーターは、現在の入力行の抽象構文ツリー (AST) に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-167">`$commandAst` (Position 1) - This parameter is set to the Abstract Syntax Tree (AST) for the current input line.</span></span> <span data-ttu-id="ca0b2-168">詳細については、「 [Ast クラス](/dotnet/api/system.management.automation.language.ast)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-168">For more information, see [Ast Class](/dotnet/api/system.management.automation.language.ast).</span></span>
- <span data-ttu-id="ca0b2-169">`$cursorPosition` (位置 2)-このパラメーターは、ユーザーが <kbd>Tab キー</kbd>を押したときのカーソルの位置に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-169">`$cursorPosition` (Position 2) - This parameter is set to the position of the cursor when the user pressed <kbd>Tab</kbd>.</span></span>

<span data-ttu-id="ca0b2-170">パラメーター属性として **ArgumentCompleter** を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-170">You can also provide an **ArgumentCompleter** as a parameter attribute.</span></span> <span data-ttu-id="ca0b2-171">詳細については、「 [about_Functions_Advanced_Parameters](./About/about_Functions_Advanced_Parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-171">For more information, see [about_Functions_Advanced_Parameters](./About/about_Functions_Advanced_Parameters.md).</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ca0b2-172">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ca0b2-172">CommonParameters</span></span>

<span data-ttu-id="ca0b2-173">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ca0b2-174">詳細については、「[about_CommonParameters](./About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-174">For more information, see [about_CommonParameters](./About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="ca0b2-175">入力</span><span class="sxs-lookup"><span data-stu-id="ca0b2-175">INPUTS</span></span>

### <span data-ttu-id="ca0b2-176">なし</span><span class="sxs-lookup"><span data-stu-id="ca0b2-176">None</span></span>

<span data-ttu-id="ca0b2-177">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-177">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="ca0b2-178">出力</span><span class="sxs-lookup"><span data-stu-id="ca0b2-178">OUTPUTS</span></span>

### <span data-ttu-id="ca0b2-179">なし</span><span class="sxs-lookup"><span data-stu-id="ca0b2-179">None</span></span>

<span data-ttu-id="ca0b2-180">このコマンドレットは、出力を返しません。</span><span class="sxs-lookup"><span data-stu-id="ca0b2-180">This cmdlet returns no output.</span></span>

## <span data-ttu-id="ca0b2-181">注</span><span class="sxs-lookup"><span data-stu-id="ca0b2-181">NOTES</span></span>

## <span data-ttu-id="ca0b2-182">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ca0b2-182">RELATED LINKS</span></span>

