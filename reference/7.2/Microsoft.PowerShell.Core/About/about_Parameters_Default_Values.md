---
description: コマンドレットパラメーターおよび高度な関数のカスタムの既定値を設定する方法について説明します。
Locale: en-US
ms.date: 05/31/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parameters_default_values?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parameters_Default_Values
ms.openlocfilehash: 102f163287717f7c9cd4f430704cc27ddea7ff4c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600816"
---
# <a name="about-parameters-default-values"></a><span data-ttu-id="294d6-103">パラメーターの既定値について</span><span class="sxs-lookup"><span data-stu-id="294d6-103">About Parameters Default Values</span></span>

## <a name="short-description"></a><span data-ttu-id="294d6-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="294d6-104">Short description</span></span>

<span data-ttu-id="294d6-105">コマンドレットパラメーターおよび高度な関数のカスタムの既定値を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="294d6-105">Describes how to set custom default values for cmdlet parameters and advanced functions.</span></span>

## <a name="long-description"></a><span data-ttu-id="294d6-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="294d6-106">Long description</span></span>

<span data-ttu-id="294d6-107">`$PSDefaultParameterValues`ユーザー設定変数を使用すると、任意のコマンドレットまたは高度な関数に対してカスタムの既定値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="294d6-107">The `$PSDefaultParameterValues` preference variable lets you specify custom default values for any cmdlet or advanced function.</span></span> <span data-ttu-id="294d6-108">コマンドレットと高度な関数では、コマンドで別の値を指定しない限り、カスタムの既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="294d6-108">Cmdlets and advanced functions use the custom default value unless you specify another value in the command.</span></span>

<span data-ttu-id="294d6-109">コマンドレットと高度な関数の作成者は、パラメーターに標準の既定値を設定します。</span><span class="sxs-lookup"><span data-stu-id="294d6-109">The authors of cmdlets and advanced functions set standard default values for their parameters.</span></span> <span data-ttu-id="294d6-110">通常、標準の既定値は役に立ちますが、すべての環境に適しているとは限りません。</span><span class="sxs-lookup"><span data-stu-id="294d6-110">Typically, the standard default values are useful, but they might not be appropriate for all environments.</span></span>

<span data-ttu-id="294d6-111">この機能は、コマンドを使用するたびにほぼ同じ代替パラメーター値を指定する必要がある場合や、電子メールサーバー名やプロジェクト GUID など、特定のパラメーター値が覚えにくい場合に特に便利です。</span><span class="sxs-lookup"><span data-stu-id="294d6-111">This feature is especially useful when you must specify the same alternate parameter value nearly every time you use the command or when a particular parameter value is difficult to remember, such as an email server name or project GUID.</span></span>

<span data-ttu-id="294d6-112">目的の既定値が予想どおりに変化する場合は、異なる条件下でパラメーターに異なる既定値を提供するスクリプトブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="294d6-112">If the desired default value varies predictably, you can specify a script block that provides different default values for a parameter under different conditions.</span></span>

<span data-ttu-id="294d6-113">`$PSDefaultParameterValues` は、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="294d6-113">`$PSDefaultParameterValues` was introduced in PowerShell 3.0.</span></span>

## <a name="syntax"></a><span data-ttu-id="294d6-114">構文</span><span class="sxs-lookup"><span data-stu-id="294d6-114">Syntax</span></span>

<span data-ttu-id="294d6-115">`$PSDefaultParameterValues`変数は、キーの形式を、 **System. DefaultParameterDictionary** のオブジェクトの種類として検証するハッシュテーブルです。</span><span class="sxs-lookup"><span data-stu-id="294d6-115">The `$PSDefaultParameterValues` variable is a hash table that validates the format of keys as an object type of **System.Management.Automation.DefaultParameterDictionary**.</span></span> <span data-ttu-id="294d6-116">ハッシュテーブルには、 **キーと値** のペアが含まれています。</span><span class="sxs-lookup"><span data-stu-id="294d6-116">The hash table contains **Key/Value** pairs.</span></span> <span data-ttu-id="294d6-117">**キー** の形式は `CmdletName:ParameterName` です。</span><span class="sxs-lookup"><span data-stu-id="294d6-117">A **Key** is in the format `CmdletName:ParameterName`.</span></span> <span data-ttu-id="294d6-118">**値** は、キーに割り当てられた **DefaultValue** または **ScriptBlock** です。</span><span class="sxs-lookup"><span data-stu-id="294d6-118">A **Value** is the **DefaultValue** or **ScriptBlock** assigned to the key.</span></span>

<span data-ttu-id="294d6-119">ユーザー `$PSDefaultParameterValues` 設定変数の構文は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="294d6-119">The syntax of the `$PSDefaultParameterValues` preference variable is as follows:</span></span>

```
$PSDefaultParameterValues=@{"CmdletName:ParameterName"="DefaultValue"}

$PSDefaultParameterValues=@{ "CmdletName:ParameterName"={{ScriptBlock}} }

$PSDefaultParameterValues["Disabled"]=$True | $False
```

<span data-ttu-id="294d6-120">入力文字列の **名前** と **ParameterName** の値には、ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="294d6-120">Wildcard characters are permitted in the **CmdletName** and **ParameterName** values.</span></span>

<span data-ttu-id="294d6-121">から特定の **キーと値** のペアを設定、変更、追加、または削除するには、 `$PSDefaultParameterValues` メソッドを使用して標準のハッシュテーブルを編集します。</span><span class="sxs-lookup"><span data-stu-id="294d6-121">To set, change, add, or remove a specific **Key/Value** pair from `$PSDefaultParameterValues`, use the methods to edit a standard hash table.</span></span> <span data-ttu-id="294d6-122">たとえば、 **Add** メソッドと **Remove** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="294d6-122">For example, the **Add** and **Remove** methods.</span></span> <span data-ttu-id="294d6-123">これらのメソッドでは、ハッシュテーブル内の他の値は上書きされません。</span><span class="sxs-lookup"><span data-stu-id="294d6-123">These methods don't overwrite other values in the hash table.</span></span>

<span data-ttu-id="294d6-124">既存のハッシュテーブルを上書きしないもう1つの構文があり `$PSDefaultParameterValues` ます。</span><span class="sxs-lookup"><span data-stu-id="294d6-124">There's another syntax that doesn't overwrite an existing `$PSDefaultParameterValues` hash table.</span></span> <span data-ttu-id="294d6-125">特定の **キーと値** のペアを追加または変更するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="294d6-125">To add or change a specific **Key/Value** pair, use the following syntax:</span></span>

```
$PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

<span data-ttu-id="294d6-126">コマンドレット **名** は、コマンドレットの名前であるか、またはコマンドレット **バインド** 属性を使用する高度な関数の名前である必要があります。</span><span class="sxs-lookup"><span data-stu-id="294d6-126">The **CmdletName** must be the name of a cmdlet or the name of an advanced function that uses the **CmdletBinding** attribute.</span></span> <span data-ttu-id="294d6-127">を使用し `$PSDefaultParameterValues` て、スクリプトまたは単純な関数の既定値を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="294d6-127">You can't use `$PSDefaultParameterValues` to specify default values for scripts or simple functions.</span></span>

<span data-ttu-id="294d6-128">**DefaultValue** には、オブジェクトまたはスクリプトブロックを指定できます。</span><span class="sxs-lookup"><span data-stu-id="294d6-128">The **DefaultValue** can be an object or a script block.</span></span> <span data-ttu-id="294d6-129">値がスクリプトブロックの場合、PowerShell はスクリプトブロックを評価し、結果をパラメーター値として使用します。</span><span class="sxs-lookup"><span data-stu-id="294d6-129">If the value is a script block, PowerShell evaluates the script block and uses the result as the parameter value.</span></span> <span data-ttu-id="294d6-130">指定されたパラメーターがスクリプトブロックの値を受け入れる場合は、次のように、スクリプトブロックの値を2番目のかっこのセットで囲みます。</span><span class="sxs-lookup"><span data-stu-id="294d6-130">When the specified parameter accepts a script block value, enclose the script block value in a second set of braces, such as:</span></span>

```powershell
$PSDefaultParameterValues=@{ "Invoke-Command:ScriptBlock"={{Get-Process}} }
```

<span data-ttu-id="294d6-131">詳細については、以下のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="294d6-131">For more information, see the following documents:</span></span>

- [<span data-ttu-id="294d6-132">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="294d6-132">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="294d6-133">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="294d6-133">about_Script_Blocks</span></span>](about_Script_Blocks.md)
- [<span data-ttu-id="294d6-134">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="294d6-134">about_Preference_Variables</span></span>](about_Preference_Variables.md)

## <a name="examples"></a><span data-ttu-id="294d6-135">例</span><span class="sxs-lookup"><span data-stu-id="294d6-135">Examples</span></span>

### <a name="how-to-set-psdefaultparametervalues"></a><span data-ttu-id="294d6-136">PSDefaultParameterValues を設定する方法 \$</span><span class="sxs-lookup"><span data-stu-id="294d6-136">How to set \$PSDefaultParameterValues</span></span>

<span data-ttu-id="294d6-137">`$PSDefaultParameterValues` はユーザー設定変数なので、設定されているセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="294d6-137">`$PSDefaultParameterValues` is a preference variable, so it exists only in the session in which it's set.</span></span> <span data-ttu-id="294d6-138">既定値はありません。</span><span class="sxs-lookup"><span data-stu-id="294d6-138">It has no default value.</span></span>

<span data-ttu-id="294d6-139">を設定するには `$PSDefaultParameterValues` 、変数名と、1つまたは複数の **キーと値** のペアを入力します。</span><span class="sxs-lookup"><span data-stu-id="294d6-139">To set `$PSDefaultParameterValues`, type the variable name and one or more **Key/Value** pairs.</span></span> <span data-ttu-id="294d6-140">別のコマンドを実行すると `$PSDefaultParameterValues` 、既存のハッシュテーブルが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="294d6-140">If you run another `$PSDefaultParameterValues` command, it overwrites the existing hash table.</span></span>

<span data-ttu-id="294d6-141">既存のハッシュテーブル値を上書きせずに **キーと値** のペアを変更する方法の例については、「 [ \$ PSDefaultParameterValues に値を追加する方法](#how-to-add-values-to-psdefaultparametervalues) 」または「 [ \$ PSDefaultParameterValues で値を変更する](#how-to-change-values-in-psdefaultparametervalues)方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="294d6-141">For examples about how to change **Key/Value** pairs without overwriting existing hash table values, see [How to add values to \$PSDefaultParameterValues](#how-to-add-values-to-psdefaultparametervalues) or [How to change values in \$PSDefaultParameterValues](#how-to-change-values-in-psdefaultparametervalues).</span></span>

<span data-ttu-id="294d6-142">`$PSDefaultParameterValues`今後のセッションのために保存するには、 `$PSDefaultParameterValues` PowerShell プロファイルにコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="294d6-142">To save `$PSDefaultParameterValues` for future sessions, add a `$PSDefaultParameterValues` command to your PowerShell profile.</span></span> <span data-ttu-id="294d6-143">詳細については、「 [about_Profiles](about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="294d6-143">For more information, see [about_Profiles](about_Profiles.md).</span></span>

#### <a name="set-a-custom-default-value"></a><span data-ttu-id="294d6-144">カスタムの既定値を設定する</span><span class="sxs-lookup"><span data-stu-id="294d6-144">Set a custom default value</span></span>

<span data-ttu-id="294d6-145">**キーと値** のペアは、 `Send-MailMessage:SmtpServer` キーをカスタムの既定値 **server123 to you** に設定します。</span><span class="sxs-lookup"><span data-stu-id="294d6-145">The **Key/Value** pair sets the `Send-MailMessage:SmtpServer` key to a custom default value of **Server123**.</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
}
```

#### <a name="set-default-values-for-multiple-parameters"></a><span data-ttu-id="294d6-146">複数のパラメーターの既定値を設定する</span><span class="sxs-lookup"><span data-stu-id="294d6-146">Set default values for multiple parameters</span></span>

<span data-ttu-id="294d6-147">複数のパラメーターの既定値を設定するには、各 **キーと値** のペアをセミコロン () で区切り `;` ます。</span><span class="sxs-lookup"><span data-stu-id="294d6-147">To set default values for multiple parameters, separate each **Key/Value** pair with a semicolon (`;`).</span></span> <span data-ttu-id="294d6-148">`Send-MailMessage:SmtpServer`キーと `Get-WinEvent:LogName` キーは、カスタムの既定値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="294d6-148">The `Send-MailMessage:SmtpServer` and `Get-WinEvent:LogName` keys are set to custom default values.</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123";
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
}
```

#### <a name="use-wildcards-and-switch-parameters"></a><span data-ttu-id="294d6-149">ワイルドカードとスイッチパラメーターを使用する</span><span class="sxs-lookup"><span data-stu-id="294d6-149">Use wildcards and switch parameters</span></span>

<span data-ttu-id="294d6-150">コマンドレットとパラメーター名には、ワイルドカード文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="294d6-150">The cmdlet and parameter names can contain wildcard characters.</span></span> <span data-ttu-id="294d6-151">およびを使用し `$True` `$False` て、 **詳細** などのスイッチパラメーターの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="294d6-151">Use `$True` and `$False` to set values for switch parameters, such as **Verbose**.</span></span> <span data-ttu-id="294d6-152">共通パラメーターの **Verbose** パラメーターは、 `$True` すべてのコマンドに対してに設定されます。</span><span class="sxs-lookup"><span data-stu-id="294d6-152">The common parameter's **Verbose** parameter is set to `$True` for all commands.</span></span>

```powershell
$PSDefaultParameterValues = @{"*:Verbose"=$True}
```

#### <a name="use-an-array-for-the-default-value"></a><span data-ttu-id="294d6-153">既定値に配列を使用する</span><span class="sxs-lookup"><span data-stu-id="294d6-153">Use an array for the default value</span></span>

<span data-ttu-id="294d6-154">パラメーターが複数の値 (配列) を受け取ることができる場合は、複数の値を既定値として設定できます。</span><span class="sxs-lookup"><span data-stu-id="294d6-154">If a parameter can accept multiple values, an array, you can set multiple values as the default values.</span></span> <span data-ttu-id="294d6-155">キーの既定値 `Invoke-Command:ComputerName` は、 **Server01** および **Server02** の配列値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="294d6-155">The default value of the `Invoke-Command:ComputerName` key is set to an array value of **Server01** and **Server02**.</span></span>

```powershell
$PSDefaultParameterValues = @{
  "Invoke-Command:ComputerName"="Server01","Server02"
}
```

#### <a name="use-a-script-block"></a><span data-ttu-id="294d6-156">スクリプトブロックを使用する</span><span class="sxs-lookup"><span data-stu-id="294d6-156">Use a script block</span></span>

<span data-ttu-id="294d6-157">スクリプトブロックを使用して、さまざまな条件下でパラメーターに異なる既定値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="294d6-157">You can use a script block to specify different default values for a parameter under different conditions.</span></span> <span data-ttu-id="294d6-158">PowerShell はスクリプトブロックを評価し、結果を既定のパラメーター値として使用します。</span><span class="sxs-lookup"><span data-stu-id="294d6-158">PowerShell evaluates the script block and uses the result as the default parameter value.</span></span>

<span data-ttu-id="294d6-159">この `Format-Table:AutoSize` キーは、スイッチパラメーターを既定値の **True** に設定します。</span><span class="sxs-lookup"><span data-stu-id="294d6-159">The `Format-Table:AutoSize` key sets that switch parameter to a default value of **True**.</span></span> <span data-ttu-id="294d6-160">ステートメントには `If` 、が `$host.Name` PowerShell コンソール **consolehost** である必要があるという条件が含まれています。</span><span class="sxs-lookup"><span data-stu-id="294d6-160">The `If` statement contains a condition that the `$host.Name` must be the PowerShell console, **ConsoleHost**.</span></span>

```powershell
$PSDefaultParameterValues=@{
  "Format-Table:AutoSize"={if ($host.Name -eq "ConsoleHost"){$True}}
}
```

<span data-ttu-id="294d6-161">パラメーターがスクリプトブロックの値を受け入れる場合は、スクリプトブロックを中かっこのセットで囲みます。</span><span class="sxs-lookup"><span data-stu-id="294d6-161">If a parameter accepts a script block value, enclose the script block in an extra set of braces.</span></span> <span data-ttu-id="294d6-162">PowerShell が外側のスクリプトブロックを評価すると、結果は内部スクリプトブロックになり、既定のパラメーター値として設定されます。</span><span class="sxs-lookup"><span data-stu-id="294d6-162">When PowerShell evaluates the outer script block, the result is the inner script block, and that is set as the default parameter value.</span></span>

<span data-ttu-id="294d6-163">`Invoke-Command:ScriptBlock`スクリプトブロックが2番目の中かっこで囲まれているため、**システムイベントログ** の既定値に設定されたキー。</span><span class="sxs-lookup"><span data-stu-id="294d6-163">The `Invoke-Command:ScriptBlock` key set to a default value of the **System event log** because the script block is enclosed in a second set of braces.</span></span> <span data-ttu-id="294d6-164">スクリプトブロックの結果がコマンドレットに渡され `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="294d6-164">The result of the script block is passed to the `Invoke-Command` cmdlet.</span></span>

```powershell
$PSDefaultParameterValues=@{
  "Invoke-Command:ScriptBlock"={{Get-EventLog -Log System}}
}
```

### <a name="how-to-get-psdefaultparametervalues"></a><span data-ttu-id="294d6-165">PSDefaultParameterValues を取得する方法 \$</span><span class="sxs-lookup"><span data-stu-id="294d6-165">How to get \$PSDefaultParameterValues</span></span>

<span data-ttu-id="294d6-166">ハッシュテーブルの値は、PowerShell プロンプトで「」と入力すると表示され `$PSDefaultParameterValues` ます。</span><span class="sxs-lookup"><span data-stu-id="294d6-166">The hash table values are displayed by entering `$PSDefaultParameterValues` at the PowerShell prompt.</span></span>

<span data-ttu-id="294d6-167">`$PSDefaultParameterValues`ハッシュテーブルは、3つの **キーと値** のペアで設定されます。</span><span class="sxs-lookup"><span data-stu-id="294d6-167">A `$PSDefaultParameterValues` hash table is set with three **Key/Value** pairs.</span></span>
<span data-ttu-id="294d6-168">次の例では、このハッシュテーブルを使用して、の値を追加、変更、および削除する方法について説明し `$PSDefaultParameterValues` ます。</span><span class="sxs-lookup"><span data-stu-id="294d6-168">This hash table is used in the following examples that describe how to add, change, and remove values from `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues = @{
  "Send-MailMessage:SmtpServer"="Server123"
  "Get-WinEvent:LogName"="Microsoft-Windows-PrintService/Operational"
  "Get-*:Verbose"=$True
}

PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

<span data-ttu-id="294d6-169">特定のキーの値を取得するには `CmdletName:ParameterName` 、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="294d6-169">To get the value of a specific `CmdletName:ParameterName` key, use the following syntax:</span></span>

```
$PSDefaultParameterValues["CmdletName:ParameterName"]
```

<span data-ttu-id="294d6-170">たとえば、キーの値を取得し `Send-MailMessage:SmtpServer` ます。</span><span class="sxs-lookup"><span data-stu-id="294d6-170">For example, to get the value for the `Send-MailMessage:SmtpServer` key.</span></span>

```
PS> $PSDefaultParameterValues["Send-MailMessage:SmtpServer"]
Server123
```

### <a name="how-to-add-values-to-psdefaultparametervalues"></a><span data-ttu-id="294d6-171">PSDefaultParameterValues に値を追加する方法 \$</span><span class="sxs-lookup"><span data-stu-id="294d6-171">How to add values to \$PSDefaultParameterValues</span></span>

<span data-ttu-id="294d6-172">に値を追加するには、 `$PSDefaultParameterValues` **add** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="294d6-172">To add a value to `$PSDefaultParameterValues`, use the **Add** method.</span></span> <span data-ttu-id="294d6-173">値を追加しても、ハッシュテーブルの既存の値には影響しません。</span><span class="sxs-lookup"><span data-stu-id="294d6-173">Adding a value doesn't affect the hash table's existing values.</span></span>

<span data-ttu-id="294d6-174">`,`**キー** を **値** から区切るには、コンマ () を使用します。</span><span class="sxs-lookup"><span data-stu-id="294d6-174">Use a comma (`,`) to separate the **Key** from the **Value**.</span></span> <span data-ttu-id="294d6-175">次の構文は、の **Add** メソッドを使用する方法を示して `$PSDefaultParameterValues` います。</span><span class="sxs-lookup"><span data-stu-id="294d6-175">The following syntax shows how to use the **Add** method for `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues.Add("CmdletName:ParameterName", "DefaultValue")
```

<span data-ttu-id="294d6-176">前の例で作成したハッシュテーブルは、新しい **キーと値** のペアで更新されます。</span><span class="sxs-lookup"><span data-stu-id="294d6-176">The hash table created in the prior example is updated with a new **Key/Value** pair.</span></span> <span data-ttu-id="294d6-177">**Add** メソッドは、 `Get-Process:Name` キーを値 **PowerShell** に設定します。</span><span class="sxs-lookup"><span data-stu-id="294d6-177">The **Add** method sets the `Get-Process:Name` key to the value **PowerShell**.</span></span>

```powershell
$PSDefaultParameterValues.Add("Get-Process:Name", "PowerShell")
```

<span data-ttu-id="294d6-178">次の構文では、同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="294d6-178">The following syntax accomplishes the same result.</span></span>

```powershell
$PSDefaultParameterValues["Get-Process:Name"]="PowerShell"
```

<span data-ttu-id="294d6-179">変数は、 `$PSDefaultParameterValues` 更新されたハッシュテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="294d6-179">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="294d6-180">`Get-Process:Name`キーが追加されました。</span><span class="sxs-lookup"><span data-stu-id="294d6-180">The `Get-Process:Name` key was added.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-Process:Name               PowerShell
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-remove-values-from-psdefaultparametervalues"></a><span data-ttu-id="294d6-181">PSDefaultParameterValues から値を削除する方法 \$</span><span class="sxs-lookup"><span data-stu-id="294d6-181">How to remove values from \$PSDefaultParameterValues</span></span>

<span data-ttu-id="294d6-182">から値を削除するには `$PSDefaultParameterValues` 、ハッシュテーブルの **remove** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="294d6-182">To remove a value from `$PSDefaultParameterValues`, use the **Remove** method of hash tables.</span></span> <span data-ttu-id="294d6-183">値を削除しても、ハッシュテーブルの既存の値には影響しません。</span><span class="sxs-lookup"><span data-stu-id="294d6-183">Removing a value doesn't affect the hash table's existing values.</span></span>

<span data-ttu-id="294d6-184">次の構文は、で **Remove** メソッドを使用する方法を示して `$PSDefaultParameterValues` います。</span><span class="sxs-lookup"><span data-stu-id="294d6-184">The following syntax shows how to use the **Remove** method on `$PSDefaultParameterValues`.</span></span>

```
PS> $PSDefaultParameterValues.Remove("CmdletName:ParameterName")
```

<span data-ttu-id="294d6-185">この例では、前の例で作成したハッシュテーブルを更新して、 **キーと値** のペアを削除します。</span><span class="sxs-lookup"><span data-stu-id="294d6-185">In this example, the hash table created in the prior example is updated to remove a **Key/Value** pair.</span></span> <span data-ttu-id="294d6-186">**Remove** メソッドは、キーを削除し `Get-Process:Name` ます。</span><span class="sxs-lookup"><span data-stu-id="294d6-186">The **Remove** method removes the `Get-Process:Name` key.</span></span>

```powershell
$PSDefaultParameterValues.Remove("Get-Process:Name")
```

<span data-ttu-id="294d6-187">変数は、 `$PSDefaultParameterValues` 更新されたハッシュテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="294d6-187">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="294d6-188">`Get-Process:Name`キーが削除されました。</span><span class="sxs-lookup"><span data-stu-id="294d6-188">The `Get-Process:Name` key was removed.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    Server123
```

### <a name="how-to-change-values-in-psdefaultparametervalues"></a><span data-ttu-id="294d6-189">PSDefaultParameterValues の値を変更する方法 \$</span><span class="sxs-lookup"><span data-stu-id="294d6-189">How to change values in \$PSDefaultParameterValues</span></span>

<span data-ttu-id="294d6-190">特定の値を変更しても、既存のハッシュテーブルの値には影響しません。</span><span class="sxs-lookup"><span data-stu-id="294d6-190">Changes to a specific value don't affect existing hash table values.</span></span> <span data-ttu-id="294d6-191">で特定の **キーと値** のペアを変更するには `$PSDefaultParameterValues` 、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="294d6-191">To change a specific **Key/Value** pair in `$PSDefaultParameterValues`, use the following syntax:</span></span>

```
PS> $PSDefaultParameterValues["CmdletName:ParameterName"]="DefaultValue"
```

<span data-ttu-id="294d6-192">この例では、前の例で作成したハッシュテーブルを更新して、 **キーと値** のペアを変更します。</span><span class="sxs-lookup"><span data-stu-id="294d6-192">In this example, the hash table created in the prior example is updated to change a **Key/Value** pair.</span></span> <span data-ttu-id="294d6-193">次のコマンドを実行 `Send-MailMessage:SmtpServer` すると、キーが **serverxyz** の新しい値に変更されます。</span><span class="sxs-lookup"><span data-stu-id="294d6-193">The following command changes the `Send-MailMessage:SmtpServer` key to a new value of **ServerXYZ**.</span></span>

```powershell
$PSDefaultParameterValues["Send-MailMessage:SmtpServer"]="ServerXYZ"
```

<span data-ttu-id="294d6-194">変数は、 `$PSDefaultParameterValues` 更新されたハッシュテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="294d6-194">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="294d6-195">`Send-MailMessage:SmtpServer`キーが新しい値に変更されました。</span><span class="sxs-lookup"><span data-stu-id="294d6-195">The `Send-MailMessage:SmtpServer` key was changed to a new value.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

### <a name="how-to-disable-and-re-enable-psdefaultparametervalues"></a><span data-ttu-id="294d6-196">PSDefaultParameterValues を無効にしてから再度有効にする方法 \$</span><span class="sxs-lookup"><span data-stu-id="294d6-196">How to disable and re-enable \$PSDefaultParameterValues</span></span>

<span data-ttu-id="294d6-197">を一時的に無効にしてから再び有効にすることができ `$PSDefaultParameterValues` ます。</span><span class="sxs-lookup"><span data-stu-id="294d6-197">You can temporarily disable and then re-enable `$PSDefaultParameterValues`.</span></span>
<span data-ttu-id="294d6-198">`$PSDefaultParameterValues`異なる既定のパラメーター値を必要とするスクリプトを実行している場合は、無効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="294d6-198">Disabling `$PSDefaultParameterValues` is useful if you're running scripts that need different default parameter values.</span></span>

<span data-ttu-id="294d6-199">を無効にするには `$PSDefaultParameterValues` 、値が True のキーを追加し `Disabled` ます。 </span><span class="sxs-lookup"><span data-stu-id="294d6-199">To disable `$PSDefaultParameterValues`, add a key of `Disabled` with a value of **True**.</span></span> <span data-ttu-id="294d6-200">の値は `$PSDefaultParameterValues` 保持されますが、有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="294d6-200">The values in `$PSDefaultParameterValues` are preserved, but aren't effective.</span></span>

```
PS> $PSDefaultParameterValues.Add("Disabled", $True)
```

<span data-ttu-id="294d6-201">次の構文では、同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="294d6-201">The following syntax accomplishes the same result.</span></span>

```
PS> $PSDefaultParameterValues["Disabled"]=$True
```

<span data-ttu-id="294d6-202">変数は、 `$PSDefaultParameterValues` 更新されたハッシュテーブルをキーの値と共に表示し `Disabled` ます。</span><span class="sxs-lookup"><span data-stu-id="294d6-202">The `$PSDefaultParameterValues` variable displays the updated hash table with the value for the `Disabled` key.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       True
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

<span data-ttu-id="294d6-203">再度有効にするに `$PSDefaultParameterValues` は、 **無効になっ** ているキーを削除するか、 **無効になっ** ているキーの値をに変更し `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="294d6-203">To re-enable `$PSDefaultParameterValues`, remove the **Disabled** key or change the value of the **Disabled** key to `$False`.</span></span> <span data-ttu-id="294d6-204">の前の値 `$PSDefaultParameterValues` は再び有効になります。</span><span class="sxs-lookup"><span data-stu-id="294d6-204">The previous value of `$PSDefaultParameterValues` is effective again.</span></span>

```
PS> $PSDefaultParameterValues.Remove("Disabled")
```

<span data-ttu-id="294d6-205">次の構文では、同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="294d6-205">The following syntax accomplishes the same result.</span></span>

```
PS> $PSDefaultParameterValues["Disabled"]=$False
```

<span data-ttu-id="294d6-206">変数は、 `$PSDefaultParameterValues` 更新されたハッシュテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="294d6-206">The `$PSDefaultParameterValues` variable displays the updated hash table.</span></span> <span data-ttu-id="294d6-207">**Remove** メソッドを使用すると、 `Disabled` キーは出力から削除されます。</span><span class="sxs-lookup"><span data-stu-id="294d6-207">When the **Remove** method is used, the `Disabled` key is removed from the output.</span></span>
<span data-ttu-id="294d6-208">代替構文を使用して再度有効にした場合、 `$PSDefaultParameterValues` `Disabled` キーは **False** として表示されます。</span><span class="sxs-lookup"><span data-stu-id="294d6-208">If the alternate syntax was used to re-enable `$PSDefaultParameterValues`, the `Disabled` key is displayed as **False**.</span></span>

```
PS> $PSDefaultParameterValues

Name                           Value
----                           -----
Disabled                       False
Get-WinEvent:LogName           Microsoft-Windows-PrintService/Operational
Get-*:Verbose                  True
Send-MailMessage:SmtpServer    ServerXYZ
```

## <a name="see-also"></a><span data-ttu-id="294d6-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="294d6-209">See also</span></span>

[<span data-ttu-id="294d6-210">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="294d6-210">about_CommonParameters</span></span>](https://go.microsoft.com/fwlink/?LinkID=113216)

[<span data-ttu-id="294d6-211">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="294d6-211">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="294d6-212">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="294d6-212">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="294d6-213">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="294d6-213">about_Hash_Tables</span></span>](about_Hash_Tables.md)

[<span data-ttu-id="294d6-214">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="294d6-214">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="294d6-215">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="294d6-215">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="294d6-216">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="294d6-216">about_Script_Blocks</span></span>](about_Script_Blocks.md)

