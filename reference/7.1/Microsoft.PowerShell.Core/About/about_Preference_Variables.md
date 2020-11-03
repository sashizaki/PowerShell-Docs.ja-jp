---
description: PowerShell の動作をカスタマイズする変数。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_preference_variables?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Preference_Variables
ms.openlocfilehash: c844a76183461f388aa83c6dfe4bc3eb36c89590
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93224048"
---
# <a name="about-preference-variables"></a><span data-ttu-id="7102d-104">ユーザー設定変数について</span><span class="sxs-lookup"><span data-stu-id="7102d-104">About Preference Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="7102d-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="7102d-105">Short description</span></span>

<span data-ttu-id="7102d-106">PowerShell の動作をカスタマイズする変数。</span><span class="sxs-lookup"><span data-stu-id="7102d-106">Variables that customize the behavior of PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="7102d-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="7102d-107">Long description</span></span>

<span data-ttu-id="7102d-108">PowerShell には、その動作をカスタマイズできるようにする一連の変数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7102d-108">PowerShell includes a set of variables that enable you to customize its behavior.</span></span> <span data-ttu-id="7102d-109">これらのユーザー設定変数は、GUI ベースのシステムのオプションと同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="7102d-109">These preference variables work like the options in GUI-based systems.</span></span>

<span data-ttu-id="7102d-110">ユーザー設定変数は PowerShell オペレーティング環境に影響し、すべてのコマンドは環境内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-110">The preference variables affect the PowerShell operating environment and all commands run in the environment.</span></span> <span data-ttu-id="7102d-111">多くの場合、コマンドレットには、特定のコマンドの基本設定の動作をオーバーライドするために使用できるパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="7102d-111">In many cases, the cmdlets have parameters that you can use to override the preference behavior for a specific command.</span></span>

<span data-ttu-id="7102d-112">次の表に、ユーザー設定変数とその既定値を示します。</span><span class="sxs-lookup"><span data-stu-id="7102d-112">The following table lists the preference variables and their default values.</span></span>

|             <span data-ttu-id="7102d-113">変数</span><span class="sxs-lookup"><span data-stu-id="7102d-113">Variable</span></span>             |       <span data-ttu-id="7102d-114">Default value</span><span class="sxs-lookup"><span data-stu-id="7102d-114">Default Value</span></span>       |
| -------------------------------- | ------------------------- |
| `$ConfirmPreference`             | <span data-ttu-id="7102d-115">高</span><span class="sxs-lookup"><span data-stu-id="7102d-115">High</span></span>                      |
| `$DebugPreference`               | <span data-ttu-id="7102d-116">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="7102d-116">SilentlyContinue</span></span>          |
| `$ErrorActionPreference`         | <span data-ttu-id="7102d-117">Continue</span><span class="sxs-lookup"><span data-stu-id="7102d-117">Continue</span></span>                  |
| `$ErrorView`                     | <span data-ttu-id="7102d-118">ConciseView</span><span class="sxs-lookup"><span data-stu-id="7102d-118">ConciseView</span></span>               |
| `$FormatEnumerationLimit`        | <span data-ttu-id="7102d-119">4</span><span class="sxs-lookup"><span data-stu-id="7102d-119">4</span></span>                         |
| `$InformationPreference`         | <span data-ttu-id="7102d-120">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="7102d-120">SilentlyContinue</span></span>          |
| `$LogCommandHealthEvent`         | <span data-ttu-id="7102d-121">False (ログに記録されません)</span><span class="sxs-lookup"><span data-stu-id="7102d-121">False (not logged)</span></span>        |
| `$LogCommandLifecycleEvent`      | <span data-ttu-id="7102d-122">False (ログに記録されません)</span><span class="sxs-lookup"><span data-stu-id="7102d-122">False (not logged)</span></span>        |
| `$LogEngineHealthEvent`          | <span data-ttu-id="7102d-123">True (ログ記録)</span><span class="sxs-lookup"><span data-stu-id="7102d-123">True (logged)</span></span>             |
| `$LogEngineLifecycleEvent`       | <span data-ttu-id="7102d-124">True (ログ記録)</span><span class="sxs-lookup"><span data-stu-id="7102d-124">True (logged)</span></span>             |
| `$LogProviderLifecycleEvent`     | <span data-ttu-id="7102d-125">True (ログ記録)</span><span class="sxs-lookup"><span data-stu-id="7102d-125">True (logged)</span></span>             |
| `$LogProviderHealthEvent`        | <span data-ttu-id="7102d-126">True (ログ記録)</span><span class="sxs-lookup"><span data-stu-id="7102d-126">True (logged)</span></span>             |
| `$MaximumHistoryCount`           | <span data-ttu-id="7102d-127">4096</span><span class="sxs-lookup"><span data-stu-id="7102d-127">4096</span></span>                      |
| `$OFS`                           | <span data-ttu-id="7102d-128">(スペース文字 ( `" "` ))</span><span class="sxs-lookup"><span data-stu-id="7102d-128">(Space character (`" "`))</span></span> |
| `$OutputEncoding`                | <span data-ttu-id="7102d-129">UTF8Encoding オブジェクト</span><span class="sxs-lookup"><span data-stu-id="7102d-129">UTF8Encoding object</span></span>       |
| `$ProgressPreference`            | <span data-ttu-id="7102d-130">続行</span><span class="sxs-lookup"><span data-stu-id="7102d-130">Continue</span></span>                  |
| `$PSDefaultParameterValues`      | <span data-ttu-id="7102d-131">(なし-空のハッシュテーブル)</span><span class="sxs-lookup"><span data-stu-id="7102d-131">(None - empty hash table)</span></span> |
| `$PSEmailServer`                 | <span data-ttu-id="7102d-132">(なし)</span><span class="sxs-lookup"><span data-stu-id="7102d-132">(None)</span></span>                    |
| `$PSModuleAutoLoadingPreference` | <span data-ttu-id="7102d-133">All</span><span class="sxs-lookup"><span data-stu-id="7102d-133">All</span></span>                       |
| `$PSSessionApplicationName`      | <span data-ttu-id="7102d-134">wsman</span><span class="sxs-lookup"><span data-stu-id="7102d-134">wsman</span></span>                     |
| `$PSSessionConfigurationName`    | `http://schemas.microsoft.com/powershell/Microsoft.PowerShell` |
| `$PSSessionOption`               | <span data-ttu-id="7102d-135">「」を参照してください [$PSSessionOption](#pssessionoption)</span><span class="sxs-lookup"><span data-stu-id="7102d-135">See [$PSSessionOption](#pssessionoption)</span></span> |
| `$Transcript`                    | <span data-ttu-id="7102d-136">(なし)</span><span class="sxs-lookup"><span data-stu-id="7102d-136">(none)</span></span>                    |
| `$VerbosePreference`             | <span data-ttu-id="7102d-137">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="7102d-137">SilentlyContinue</span></span>          |
| `$WarningPreference`             | <span data-ttu-id="7102d-138">Continue</span><span class="sxs-lookup"><span data-stu-id="7102d-138">Continue</span></span>                  |
| `$WhatIfPreference`              | <span data-ttu-id="7102d-139">False</span><span class="sxs-lookup"><span data-stu-id="7102d-139">False</span></span>                     |

<span data-ttu-id="7102d-140">PowerShell には、ユーザー設定を格納する次の環境変数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7102d-140">PowerShell includes the following environment variables that store user preferences.</span></span> <span data-ttu-id="7102d-141">これらの環境変数の詳細については、「 [about_Environment_Variables](about_Environment_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-141">For more information about these environment variables, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

- `env:PSExecutionPolicyPreference`
- `$env:PSModulePath`

> [!NOTE]
> <span data-ttu-id="7102d-142">優先変数に加えた変更は、これらのスクリプトまたは関数が、preference が使用されたスコープと同じスコープで定義されている場合にのみ、スクリプトと関数で有効になります。</span><span class="sxs-lookup"><span data-stu-id="7102d-142">Changes to preference variable only take effect in scripts and functions if those scripts or functions are defined in the same scope as the scope in which preference was used.</span></span> <span data-ttu-id="7102d-143">詳細については、「 [about_Scopes](about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-143">For more information, see [about_Scopes](about_Scopes.md).</span></span>

## <a name="working-with-preference-variables"></a><span data-ttu-id="7102d-144">ユーザー設定変数の使用</span><span class="sxs-lookup"><span data-stu-id="7102d-144">Working with preference variables</span></span>

<span data-ttu-id="7102d-145">このドキュメントでは、各ユーザー設定変数について説明します。</span><span class="sxs-lookup"><span data-stu-id="7102d-145">This document describes each of the preference variables.</span></span>

<span data-ttu-id="7102d-146">特定のユーザー設定変数の現在の値を表示するには、変数の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="7102d-146">To display the current value of a specific preference variable, type the variable's name.</span></span> <span data-ttu-id="7102d-147">たとえば、次のコマンドは、 `$ConfirmPreference` 変数の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="7102d-147">For example, the following command displays the `$ConfirmPreference` variable's value.</span></span>

```powershell
 $ConfirmPreference
```

```Output
High
```

<span data-ttu-id="7102d-148">変数の値を変更するには、代入ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-148">To change a variable's value, use an assignment statement.</span></span> <span data-ttu-id="7102d-149">たとえば、次のステートメントでは、 `$ConfirmPreference` パラメーターの値が **Medium** に変更されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-149">For example, the following statement changes the `$ConfirmPreference` parameter's value to **Medium**.</span></span>

```powershell
$ConfirmPreference = "Medium"
```

<span data-ttu-id="7102d-150">設定する値は、現在の PowerShell セッションに固有です。</span><span class="sxs-lookup"><span data-stu-id="7102d-150">The values that you set are specific to the current PowerShell session.</span></span> <span data-ttu-id="7102d-151">すべての PowerShell セッションで変数を有効にするには、PowerShell プロファイルに変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="7102d-151">To make variables effective in all PowerShell sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="7102d-152">詳細については、「 [about_Profiles](about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-152">For more information, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="working-remotely"></a><span data-ttu-id="7102d-153">リモートでの作業</span><span class="sxs-lookup"><span data-stu-id="7102d-153">Working remotely</span></span>

<span data-ttu-id="7102d-154">リモートコンピューターでコマンドを実行する場合、リモートコマンドは、リモートコンピューターの PowerShell クライアントで設定された設定の対象になります。</span><span class="sxs-lookup"><span data-stu-id="7102d-154">When you run commands on a remote computer, the remote commands are only subject to the preferences set in the remote computer's PowerShell client.</span></span> <span data-ttu-id="7102d-155">たとえば、リモートコマンドを実行すると、リモートコンピューターの変数の値によって、 `$DebugPreference` PowerShell がデバッグメッセージに応答する方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="7102d-155">For example, when you run a remote command, the value of the remote computer's `$DebugPreference` variable determines how PowerShell responds to debugging messages.</span></span>

<span data-ttu-id="7102d-156">リモートコマンドの詳細については、「 [about_Remote](about_Remote.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-156">For more information about remote commands, see [about_Remote](about_Remote.md).</span></span>

### <a name="confirmpreference"></a><span data-ttu-id="7102d-157">\$ConfirmPreference</span><span class="sxs-lookup"><span data-stu-id="7102d-157">\$ConfirmPreference</span></span>

<span data-ttu-id="7102d-158">コマンドレットまたは関数を実行する前に、PowerShell によって確認メッセージが自動的に表示されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-158">Determines whether PowerShell automatically prompts you for confirmation before running a cmdlet or function.</span></span>

<span data-ttu-id="7102d-159">`$ConfirmPreference`変数の有効な値は、 **High** 、 **Medium** 、または **Low** です。</span><span class="sxs-lookup"><span data-stu-id="7102d-159">The `$ConfirmPreference` variable's valid values are **High** , **Medium** , or **Low**.</span></span> <span data-ttu-id="7102d-160">コマンドレットと関数には、 **高** 、 **中** 、 **低** のリスクが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="7102d-160">Cmdlets and functions are assigned a risk of **High** , **Medium** , or **Low**.</span></span> <span data-ttu-id="7102d-161">変数の値 `$ConfirmPreference` がコマンドレットまたは関数に割り当てられたリスク以下である場合、PowerShell はコマンドレットまたは関数を実行する前に自動的に確認を求めます。</span><span class="sxs-lookup"><span data-stu-id="7102d-161">When the value of the `$ConfirmPreference` variable is less than or equal to the risk assigned to a cmdlet or function, PowerShell automatically prompts you for confirmation before running the cmdlet or function.</span></span>

<span data-ttu-id="7102d-162">変数の値 `$ConfirmPreference` が **None** の場合は、コマンドレットまたは関数を実行する前に、PowerShell によって自動的にプロンプトが表示されることはありません。</span><span class="sxs-lookup"><span data-stu-id="7102d-162">If the value of the `$ConfirmPreference` variable is **None** , PowerShell never automatically prompts you before running a cmdlet or function.</span></span>

<span data-ttu-id="7102d-163">セッション内のすべてのコマンドレットと関数の確認動作を変更するには、 `$ConfirmPreference` 変数の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="7102d-163">To change the confirming behavior for all cmdlets and functions in the session, change `$ConfirmPreference` variable's value.</span></span>

<span data-ttu-id="7102d-164">`$ConfirmPreference`1 つのコマンドのをオーバーライドするには、コマンドレットまたは関数の **Confirm** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-164">To override the `$ConfirmPreference` for a single command, use a cmdlet's or function's **Confirm** parameter.</span></span> <span data-ttu-id="7102d-165">確認を要求するには、を使用 `-Confirm` します。</span><span class="sxs-lookup"><span data-stu-id="7102d-165">To request confirmation, use `-Confirm`.</span></span> <span data-ttu-id="7102d-166">確認を抑制するには、を使用 `-Confirm:$false` します。</span><span class="sxs-lookup"><span data-stu-id="7102d-166">To suppress confirmation, use `-Confirm:$false`.</span></span>

<span data-ttu-id="7102d-167">有効な値 `$ConfirmPreference` :</span><span class="sxs-lookup"><span data-stu-id="7102d-167">Valid values of `$ConfirmPreference`:</span></span>

- <span data-ttu-id="7102d-168">**なし** : PowerShell は自動的にプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="7102d-168">**None** : PowerShell doesn't prompt automatically.</span></span> <span data-ttu-id="7102d-169">特定のコマンドの確認を要求するには、コマンドレットまたは関数の **Confirm** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-169">To request confirmation of a particular command, use the **Confirm** parameter of the cmdlet or function.</span></span>
- <span data-ttu-id="7102d-170">[ **低** ]: PowerShell で、低、中、または高リスクのコマンドレットまたは関数を実行する前に、確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-170">**Low** : PowerShell prompts for confirmation before running cmdlets or functions with a low, medium, or high risk.</span></span>
- <span data-ttu-id="7102d-171">[ **中** ]: PowerShell でコマンドレットまたは関数を実行する前に、中程度のリスクがあるかどうかを確認するプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-171">**Medium** : PowerShell prompts for confirmation before running cmdlets or functions with a medium, or high risk.</span></span>
- <span data-ttu-id="7102d-172">**High** : コマンドレットまたは関数を高いリスクで実行する前に、PowerShell に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-172">**High** : PowerShell prompts for confirmation before running cmdlets or functions with a high risk.</span></span>

#### <a name="detailed-explanation"></a><span data-ttu-id="7102d-173">詳細な説明</span><span class="sxs-lookup"><span data-stu-id="7102d-173">Detailed explanation</span></span>

<span data-ttu-id="7102d-174">PowerShell では、アクションを実行する前に自動的に確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-174">PowerShell can automatically prompt you for confirmation before doing an action.</span></span> <span data-ttu-id="7102d-175">たとえば、コマンドレットまたは関数がシステムに大きな影響を及ぼしてデータを削除したり、大量のシステムリソースを使用したりした場合などです。</span><span class="sxs-lookup"><span data-stu-id="7102d-175">For example, when cmdlet or function significantly affects the system to delete data or use a significant amount of system resources.</span></span>

```powershell
Remove-Item -Path C:\file.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\file.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
```

<span data-ttu-id="7102d-176">リスクの推定値は、コマンドレットまたは **Confirmimpact** と呼ばれる関数の属性です。</span><span class="sxs-lookup"><span data-stu-id="7102d-176">The estimate of the risk is an attribute of the cmdlet or function known as its **ConfirmImpact**.</span></span> <span data-ttu-id="7102d-177">ユーザーはそれを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="7102d-177">Users can't change it.</span></span>

<span data-ttu-id="7102d-178">システムへのリスクが生じる可能性のあるコマンドレットと関数には、1つのコマンドの確認を要求または抑制するために使用できる **Confirm** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="7102d-178">Cmdlets and functions that might pose a risk to the system have a **Confirm** parameter that you can use to request or suppress confirmation for a single command.</span></span>

<span data-ttu-id="7102d-179">ほとんどのコマンドレットと関数は、既定のリスク値である **Confirmimpact** を使用し、は **Medium** で、既定値 `$ConfirmPreference` は **high** であるため、自動確認はほとんど発生しません。</span><span class="sxs-lookup"><span data-stu-id="7102d-179">Because most cmdlets and functions use the default risk value, **ConfirmImpact** , of **Medium** , and the default value of `$ConfirmPreference` is **High** , automatic confirmation rarely occurs.</span></span> <span data-ttu-id="7102d-180">ただし、の値を [中] または [低] に変更すると、自動確認を有効にすることができ `$ConfirmPreference` ます。 **Medium** **Low**</span><span class="sxs-lookup"><span data-stu-id="7102d-180">However, you can activate automatic confirmation by changing the value of `$ConfirmPreference` to **Medium** or **Low**.</span></span>

#### <a name="examples"></a><span data-ttu-id="7102d-181">例</span><span class="sxs-lookup"><span data-stu-id="7102d-181">Examples</span></span>

<span data-ttu-id="7102d-182">この例は、 `$ConfirmPreference` 変数の既定値 **High** の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-182">This example shows the effect of the `$ConfirmPreference` variable's default value, **High**.</span></span> <span data-ttu-id="7102d-183">**高い** 値は、危険度の高いコマンドレットと関数を確認するだけです。</span><span class="sxs-lookup"><span data-stu-id="7102d-183">The **High** value only confirms high-risk cmdlets and functions.</span></span> <span data-ttu-id="7102d-184">ほとんどのコマンドレットと関数は、危険度が中程度であるため、自動的に確認されず `Remove-Item` 、ファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-184">Since most cmdlets and functions are medium risk, they aren't automatically confirmed and `Remove-Item` deletes the file.</span></span> <span data-ttu-id="7102d-185">`-Confirm`コマンドにを追加すると、ユーザーに確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-185">Adding `-Confirm` to the command prompts the user for confirmation.</span></span>

```powershell
$ConfirmPreference
```

```Output
High
```

```powershell
Remove-Item -Path C:\temp1.txt
```

<span data-ttu-id="7102d-186">`-Confirm`確認を要求するために使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-186">Use `-Confirm` to request confirmation.</span></span>

```powershell
Remove-Item -Path C:\temp2.txt -Confirm
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All
[?] Help (default is "Y"):
```

<span data-ttu-id="7102d-187">次の例は、の値を Medium に変更した場合の効果を示して `$ConfirmPreference` います。 **Medium**</span><span class="sxs-lookup"><span data-stu-id="7102d-187">The following example shows the effect of changing the value of `$ConfirmPreference` to **Medium**.</span></span> <span data-ttu-id="7102d-188">ほとんどのコマンドレットと関数は中程度のリスクであるため、自動的に確認されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-188">Because most cmdlets and function are medium risk, they're automatically confirmed.</span></span> <span data-ttu-id="7102d-189">1つのコマンドに対して確認プロンプトを表示しないようにするには、値がで **Confirm** パラメーターを使用し `$false` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-189">To suppress the confirmation prompt for a single command, use the **Confirm** parameter with a value of `$false`.</span></span>

```powershell
$ConfirmPreference = "Medium"
Remove-Item -Path C:\temp2.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\temp2.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All
[?] Help (default is "Y"):
```

```powershell
Remove-Item -Path C:\temp3.txt -Confirm:$false
```

### <a name="debugpreference"></a><span data-ttu-id="7102d-190">\$DebugPreference</span><span class="sxs-lookup"><span data-stu-id="7102d-190">\$DebugPreference</span></span>

<span data-ttu-id="7102d-191">スクリプト、コマンドレット、またはプロバイダーによって生成されたデバッグメッセージ、またはコマンドラインでコマンドを実行して、PowerShell がどのように応答するかを指定し `Write-Debug` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-191">Determines how PowerShell responds to debugging messages generated by a script, cmdlet or provider, or by a `Write-Debug` command at the command line.</span></span>

<span data-ttu-id="7102d-192">一部のコマンドレットでは、デバッグメッセージが表示されます。これは通常、プログラマやテクニカルサポートプロフェッショナル向けに設計されたテクニカルメッセージです。</span><span class="sxs-lookup"><span data-stu-id="7102d-192">Some cmdlets display debugging messages, which are typically technical messages designed for programmers and technical support professionals.</span></span> <span data-ttu-id="7102d-193">既定では、デバッグメッセージは表示されませんが、の値を変更することで、デバッグメッセージを表示でき `$DebugPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-193">By default, debugging messages aren't displayed, but you can display debugging messages by changing the value of `$DebugPreference`.</span></span>

<span data-ttu-id="7102d-194">コマンドレットの **Debug** 共通パラメーターを使用して、特定のコマンドのデバッグメッセージを表示または非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7102d-194">You can use the **Debug** common parameter of a cmdlet to display or hide the debugging messages for a specific command.</span></span> <span data-ttu-id="7102d-195">詳細については、「[about_CommonParameters](about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-195">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="7102d-196">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7102d-196">The valid values are as follows:</span></span>

- <span data-ttu-id="7102d-197">[ **停止** ]: デバッグメッセージを表示し、実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="7102d-197">**Stop** : Displays the debug message and stops executing.</span></span> <span data-ttu-id="7102d-198">コンソールにエラーを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="7102d-198">Writes an error to the console.</span></span>
- <span data-ttu-id="7102d-199">**Inquire** : デバッグメッセージを表示し、続行するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7102d-199">**Inquire** : Displays the debug message and asks you whether you want to continue.</span></span> <span data-ttu-id="7102d-200">**デバッグ** 共通パラメーターをコマンドに追加すると、コマンドがデバッグメッセージを生成するように構成されている場合に、 `$DebugPreference` **Inquire** に対して変数の値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-200">Adding the **Debug** common parameter to a command, when the command is configured to generate a debugging message, changes the value of the `$DebugPreference` variable to **Inquire**.</span></span>
- <span data-ttu-id="7102d-201">**Continue** : デバッグメッセージを表示し、実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="7102d-201">**Continue** : Displays the debug message and continues with execution.</span></span>
- <span data-ttu-id="7102d-202">**SilentlyContinue** : (既定) 効果はありません。</span><span class="sxs-lookup"><span data-stu-id="7102d-202">**SilentlyContinue** : (Default) No effect.</span></span> <span data-ttu-id="7102d-203">デバッグメッセージは表示されず、実行は中断されることなく続行されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-203">The debug message isn't displayed and execution continues without interruption.</span></span>

#### <a name="examples"></a><span data-ttu-id="7102d-204">例</span><span class="sxs-lookup"><span data-stu-id="7102d-204">Examples</span></span>

<span data-ttu-id="7102d-205">次の例は、コマンド `$DebugPreference` `Write-Debug` がコマンドラインで入力されたときのの値を変更した場合の影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-205">The following examples show the effect of changing the values of `$DebugPreference` when a `Write-Debug` command is entered at the command line.</span></span>
<span data-ttu-id="7102d-206">この変更は、コマンドレットおよびスクリプトによって生成されるメッセージを含む、すべてのデバッグメッセージに影響します。</span><span class="sxs-lookup"><span data-stu-id="7102d-206">The change affects all debugging messages, including messages generated by cmdlets and scripts.</span></span> <span data-ttu-id="7102d-207">この例は、1つのコマンドに関連するデバッグメッセージを表示または非表示にする **Debug** パラメーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-207">The examples show the **Debug** parameter, which displays or hides the debugging messages related to a single command.</span></span>

<span data-ttu-id="7102d-208">この例は、 `$DebugPreference` 変数の既定値 **SilentlyContinue** の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-208">This example shows the effect of the `$DebugPreference` variable's default value, **SilentlyContinue**.</span></span> <span data-ttu-id="7102d-209">既定では、 `Write-Debug` コマンドレットのデバッグメッセージは表示されず、処理は続行されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-209">By default, the `Write-Debug` cmdlet's debug message isn't displayed and processing continues.</span></span> <span data-ttu-id="7102d-210">**Debug** パラメーターを使用すると、1つのコマンドの設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="7102d-210">When the **Debug** parameter is used, it overrides the preference for a single command.</span></span> <span data-ttu-id="7102d-211">デバッグメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-211">The debug message is displayed.</span></span>

```powershell
$DebugPreference
```

```Output
SilentlyContinue
```

```powershell
Write-Debug -Message "Hello, World"
```

```powershell
Write-Debug -Message "Hello, World" -Debug
```

```Output
DEBUG: Hello, World
```

<span data-ttu-id="7102d-212">この例では、 `$DebugPreference` **Continue** 値を使用した場合のの効果を示します。</span><span class="sxs-lookup"><span data-stu-id="7102d-212">This example shows the effect of `$DebugPreference` with the **Continue** value.</span></span> <span data-ttu-id="7102d-213">デバッグメッセージが表示され、コマンドが処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="7102d-213">The debug message is displayed and the command continues to process.</span></span>

```powershell
$DebugPreference = "Continue"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
```

<span data-ttu-id="7102d-214">この例では、 **Debug** パラメーターを値と共に使用して、 `$false` 1 つのコマンドのメッセージを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="7102d-214">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="7102d-215">デバッグメッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="7102d-215">The debug message isn't displayed.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="7102d-216">この例は、が `$DebugPreference` **停止** 値に設定された場合の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-216">This example shows the effect of `$DebugPreference` being set to the **Stop** value.</span></span> <span data-ttu-id="7102d-217">デバッグメッセージが表示され、コマンドが停止します。</span><span class="sxs-lookup"><span data-stu-id="7102d-217">The debug message is displayed and the command is stopped.</span></span>

```powershell
$DebugPreference = "Stop"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
Write-Debug : The running command stopped because the preference variable
 "DebugPreference" or common parameter is set to Stop: Hello, World
At line:1 char:1
+ Write-Debug -Message "Hello, World"
```

<span data-ttu-id="7102d-218">この例では、 **Debug** パラメーターを値と共に使用して、 `$false` 1 つのコマンドのメッセージを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="7102d-218">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="7102d-219">デバッグメッセージは表示されず、処理は停止されません。</span><span class="sxs-lookup"><span data-stu-id="7102d-219">The debug message isn't displayed and processing isn't stopped.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="7102d-220">この例は、 `$DebugPreference` **Inquire** 値に設定された効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-220">This example shows the effect of `$DebugPreference` being set to the **Inquire** value.</span></span> <span data-ttu-id="7102d-221">デバッグメッセージが表示され、ユーザーに確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-221">The debug message is displayed and the user is prompted for confirmation.</span></span>

```powershell
$DebugPreference = "Inquire"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

<span data-ttu-id="7102d-222">この例では、 **Debug** パラメーターを値と共に使用して、 `$false` 1 つのコマンドのメッセージを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="7102d-222">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="7102d-223">デバッグメッセージが表示されず、処理が続行されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-223">The debug message isn't displayed and processing continues.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

### <a name="erroractionpreference"></a><span data-ttu-id="7102d-224">\$ErrorActionPreference</span><span class="sxs-lookup"><span data-stu-id="7102d-224">\$ErrorActionPreference</span></span>

<span data-ttu-id="7102d-225">PowerShell が終了しないエラーに応答する方法を決定します。このエラーは、コマンドレットの処理を停止しません。</span><span class="sxs-lookup"><span data-stu-id="7102d-225">Determines how PowerShell responds to a non-terminating error, an error that doesn't stop the cmdlet processing.</span></span> <span data-ttu-id="7102d-226">たとえば、コマンドライン、スクリプト、コマンドレット、またはプロバイダー (コマンドレットによって生成されたエラーなど) `Write-Error` です。</span><span class="sxs-lookup"><span data-stu-id="7102d-226">For example, at the command line or in a script, cmdlet, or provider, such as the errors generated by the `Write-Error` cmdlet.</span></span>

<span data-ttu-id="7102d-227">コマンドレットの **Erroraction** 共通パラメーターを使用して、特定のコマンドの設定をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="7102d-227">You can use a cmdlet's **ErrorAction** common parameter to override the preference for a specific command.</span></span>

<span data-ttu-id="7102d-228">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7102d-228">The valid values are as follows:</span></span>

- <span data-ttu-id="7102d-229">**Break** -エラーが発生したとき、または例外が発生したときにデバッガーを入力します。</span><span class="sxs-lookup"><span data-stu-id="7102d-229">**Break** - Enter the debugger when an error occurs or when an exception is raised.</span></span>
- <span data-ttu-id="7102d-230">**続行** : (既定) エラーメッセージを表示し、実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="7102d-230">**Continue** : (Default) Displays the error message and continues executing.</span></span>
- <span data-ttu-id="7102d-231">**Ignore** : エラーメッセージを表示せず、コマンドの実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="7102d-231">**Ignore** : Suppresses the error message and continues to execute the command.</span></span> <span data-ttu-id="7102d-232">**Ignore** 値は、保存された設定として使用するのではなく、コマンドごとの使用を目的としています。</span><span class="sxs-lookup"><span data-stu-id="7102d-232">The **Ignore** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="7102d-233">**Ignore** は、変数の有効な値ではありません `$ErrorActionPreference` 。</span><span class="sxs-lookup"><span data-stu-id="7102d-233">**Ignore** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>
- <span data-ttu-id="7102d-234">**Inquire** : エラーメッセージを表示し、続行するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7102d-234">**Inquire** : Displays the error message and asks you whether you want to continue.</span></span>
- <span data-ttu-id="7102d-235">**SilentlyContinue** : 何の効果もありません。</span><span class="sxs-lookup"><span data-stu-id="7102d-235">**SilentlyContinue** : No effect.</span></span> <span data-ttu-id="7102d-236">エラーメッセージは表示されず、実行は中断されることなく続行されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-236">The error message isn't displayed and execution continues without interruption.</span></span>
- <span data-ttu-id="7102d-237">[ **停止** ]: エラーメッセージを表示し、実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="7102d-237">**Stop** : Displays the error message and stops executing.</span></span> <span data-ttu-id="7102d-238">**Stop** 値は、生成されたエラーに加えて、エラーストリームに ActionPreferenceStopException オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="7102d-238">In addition to the error generated, the **Stop** value generates an ActionPreferenceStopException object to the error stream.</span></span>
  <span data-ttu-id="7102d-239">ストリーム (stream)</span><span class="sxs-lookup"><span data-stu-id="7102d-239">stream</span></span>
- <span data-ttu-id="7102d-240">**中断** : ワークフロージョブを自動的に中断し、さらに調査できるようにします。</span><span class="sxs-lookup"><span data-stu-id="7102d-240">**Suspend** : Automatically suspends a workflow job to allow for further investigation.</span></span> <span data-ttu-id="7102d-241">調査後、ワークフローを再開できます。</span><span class="sxs-lookup"><span data-stu-id="7102d-241">After investigation, the workflow can be resumed.</span></span> <span data-ttu-id="7102d-242">**Suspend** の値は、保存された設定としてではなく、コマンドごとの使用を目的としています。</span><span class="sxs-lookup"><span data-stu-id="7102d-242">The **Suspend** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="7102d-243">**中断** は、変数の有効な値ではありません `$ErrorActionPreference` 。</span><span class="sxs-lookup"><span data-stu-id="7102d-243">**Suspend** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>

<span data-ttu-id="7102d-244">`$ErrorActionPreference`**Erroraction** パラメーターは、コマンドレットの処理を停止するエラーを終了するために PowerShell がどのように応答するかに影響しません。</span><span class="sxs-lookup"><span data-stu-id="7102d-244">`$ErrorActionPreference` and the **ErrorAction** parameter don't affect how PowerShell responds to terminating errors that stop cmdlet processing.</span></span> <span data-ttu-id="7102d-245">**Erroraction** 共通パラメーターの詳細については、「 [about_CommonParameters](about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-245">For more information about the **ErrorAction** common parameter, see [about_CommonParameters](about_CommonParameters.md).</span></span>

#### <a name="examples"></a><span data-ttu-id="7102d-246">例</span><span class="sxs-lookup"><span data-stu-id="7102d-246">Examples</span></span>

<span data-ttu-id="7102d-247">これらの例は、変数の異なる値の効果を示して `$ErrorActionPreference` います。</span><span class="sxs-lookup"><span data-stu-id="7102d-247">These examples show the effect of the different values of the `$ErrorActionPreference` variable.</span></span> <span data-ttu-id="7102d-248">**Erroraction** パラメーターは、値をオーバーライドするために使用され `$ErrorActionPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-248">The **ErrorAction** parameter is used to override the `$ErrorActionPreference` value.</span></span>

<span data-ttu-id="7102d-249">この例では、 `$ErrorActionPreference` 既定値の [ **続行** ] を示します。</span><span class="sxs-lookup"><span data-stu-id="7102d-249">This example shows the `$ErrorActionPreference` default value, **Continue**.</span></span> <span data-ttu-id="7102d-250">終了しないエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-250">A non-terminating error is generated.</span></span> <span data-ttu-id="7102d-251">メッセージが表示され、処理が続行されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-251">The message is displayed and processing continues.</span></span>

```powershell
# Change the ErrorActionPreference to 'Continue'
$ErrorActionPreference = 'Continue'
# Generate a non-terminating error and continue processing the script.
Write-Error -Message  'Test Error' ; Write-Host 'Hello World'
```

```Output
Write-Error: Test Error
Hello World
```

<span data-ttu-id="7102d-252">この例は、 `$ErrorActionPreference` 既定値の **Inquire** を示しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-252">This example shows the `$ErrorActionPreference` default value, **Inquire**.</span></span> <span data-ttu-id="7102d-253">エラーが生成され、アクションのプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-253">An error is generated and a prompt for action is shown.</span></span>

```powershell
# Change the ErrorActionPreference to 'Inquire'
$ErrorActionPreference = 'Inquire'
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
```

```Output
Confirm
Test Error
[Y] Yes  [A] Yes to All  [H] Halt Command  [S] Suspend  [?] Help (default is "Y"):
```

<span data-ttu-id="7102d-254">この例では、 `$ErrorActionPreference` を **SilentlyContinue** に設定しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-254">This example shows the `$ErrorActionPreference` set to **SilentlyContinue**.</span></span>
<span data-ttu-id="7102d-255">エラーメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="7102d-255">The error message is suppressed.</span></span>

```powershell
# Change the ErrorActionPreference to 'SilentlyContinue'
$ErrorActionPreference = 'SilentlyContinue'
# Generate an error message
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
# Error message is suppressed and script continues processing
```

```Output
Hello World
```

<span data-ttu-id="7102d-256">`$ErrorActionPreference`**停止** するように設定する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7102d-256">This example shows the `$ErrorActionPreference` set to **Stop**.</span></span> <span data-ttu-id="7102d-257">また、変数に対して生成された追加のオブジェクトも表示され `$Error` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-257">It also shows the extra object generated to the `$Error` variable.</span></span>

```powershell
# Change the ErrorActionPreference to 'Stop'
$ErrorActionPreference = 'Stop'
# Error message is is generated and script stops processing
Write-Error -Message 'Test Error' ; Write-Host 'Hello World'

# Show the ActionPreferenceStopException and the error generated
$Error[0]
$Error[1]
```

```Output
Write-Error: Test Error

ErrorRecord                 : Test Error
WasThrownFromThrowStatement : False
TargetSite                  : System.Collections.ObjectModel.Collection`1[System.Management.Automation.PSObject]
                              Invoke(System.Collections.IEnumerable)
StackTrace                  :    at System.Management.Automation.Runspaces.PipelineBase.Invoke(IEnumerable input)
                                 at Microsoft.PowerShell.Executor.ExecuteCommandHelper(Pipeline tempPipeline,
                              Exception& exceptionThrown, ExecutionOptions options)
Message                     : The running command stopped because the preference variable "ErrorActionPreference" or
                              common parameter is set to Stop: Test Error
Data                        : {System.Management.Automation.Interpreter.InterpretedFrameInfo}
InnerException              :
HelpLink                    :
Source                      : System.Management.Automation
HResult                     : -2146233087

Write-Error: Test Error
```

### <a name="errorview"></a><span data-ttu-id="7102d-258">\$ErrorView</span><span class="sxs-lookup"><span data-stu-id="7102d-258">\$ErrorView</span></span>

<span data-ttu-id="7102d-259">PowerShell でのエラーメッセージの表示形式を決定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-259">Determines the display format of error messages in PowerShell.</span></span>

<span data-ttu-id="7102d-260">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7102d-260">The valid values are as follows:</span></span>

- <span data-ttu-id="7102d-261">**ConciseView** : (既定値) 簡潔なエラーメッセージと、高度なモジュールビルダーのリファクタリングされたビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="7102d-261">**ConciseView** : (Default) Provides a concise error message and a refactored view for advanced module builders.</span></span> <span data-ttu-id="7102d-262">エラーがコマンドラインからのものである場合は、単一行のエラーメッセージです。</span><span class="sxs-lookup"><span data-stu-id="7102d-262">If the error is from command line it's a single line error message.</span></span> <span data-ttu-id="7102d-263">それ以外の場合は、エラーを含む複数行のエラーメッセージと、その行のどこに発生しているかを示すエラーへのポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7102d-263">Otherwise, you receive a multiline error message that contains the error and a pointer to the error showing where it occurs in that line.</span></span> <span data-ttu-id="7102d-264">ターミナルで仮想端末がサポートされている場合は、ANSI カラーコードを使用してカラーアクセントが提供されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-264">If the terminal supports Virtual Terminal, then ANSI color codes are used to provide color accent.</span></span> <span data-ttu-id="7102d-265">アクセントの色はで変更でき `$Host.PrivateData.ErrorAccentColor` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-265">The Accent color can be changed at `$Host.PrivateData.ErrorAccentColor`.</span></span> <span data-ttu-id="7102d-266">`Get-Error`内部例外を含む完全修飾エラーの包括的な詳細ビューを使用するには、コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-266">Use `Get-Error` cmdlet for a comprehensive detailed view of the fully qualified error, including inner exceptions.</span></span>

  <span data-ttu-id="7102d-267">PowerShell 7 で **ConciseView** が追加されました。</span><span class="sxs-lookup"><span data-stu-id="7102d-267">**ConciseView** was added in PowerShell 7.</span></span>

- <span data-ttu-id="7102d-268">**Normalview** : ほとんどのユーザー向けに設計された詳細なビューです。</span><span class="sxs-lookup"><span data-stu-id="7102d-268">**NormalView** : A detailed view designed for most users.</span></span> <span data-ttu-id="7102d-269">エラーの説明とエラーに関係するオブジェクトの名前で構成されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-269">Consists of a description of the error and the name of the object involved in the error.</span></span>

- <span data-ttu-id="7102d-270">**カテゴリビュー** : 運用環境向けに設計された簡潔で構造化されたビューです。</span><span class="sxs-lookup"><span data-stu-id="7102d-270">**CategoryView** : A succinct, structured view designed for production environments.</span></span> <span data-ttu-id="7102d-271">その形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7102d-271">The format is as follows:</span></span>

  <span data-ttu-id="7102d-272">{Category}: ({TargetName}: {TargetType}): [{Activity}], {Reason}</span><span class="sxs-lookup"><span data-stu-id="7102d-272">{Category}: ({TargetName}:{TargetType}):[{Activity}], {Reason}</span></span>

<span data-ttu-id="7102d-273">**カテゴリビュー** のフィールドの詳細については、「 [errorのカテゴリ情報](/dotnet/api/system.management.automation.errorcategoryinfo)クラス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-273">For more information about the fields in **CategoryView** , see [ErrorCategoryInfo](/dotnet/api/system.management.automation.errorcategoryinfo) class.</span></span>

#### <a name="examples"></a><span data-ttu-id="7102d-274">例</span><span class="sxs-lookup"><span data-stu-id="7102d-274">Examples</span></span>

<span data-ttu-id="7102d-275">この例では、の値が既定の ConciseView である場合に、エラーがどのように表示されるかを示し `$ErrorView` ます。 **ConciseView**</span><span class="sxs-lookup"><span data-stu-id="7102d-275">This example shows how an error appears when the value of `$ErrorView` is the default, **ConciseView**.</span></span> <span data-ttu-id="7102d-276">`Get-ChildItem` は、存在しないディレクトリを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-276">`Get-ChildItem` is used to find a non-existent directory.</span></span>

```powershell
Get-ChildItem -path 'C:\NoRealDirectory'
```

```Output
Get-ChildItem: Cannot find path 'C:\NoRealDirectory' because it does not exist.
```

<span data-ttu-id="7102d-277">この例では、の値が既定の ConciseView である場合に、エラーがどのように表示されるかを示し `$ErrorView` ます。 **ConciseView**</span><span class="sxs-lookup"><span data-stu-id="7102d-277">This example shows how an error appears when the value of `$ErrorView` is the default, **ConciseView**.</span></span> <span data-ttu-id="7102d-278">`Script.ps1` が実行され、ステートメントからエラーがスローされ `Get-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-278">`Script.ps1` is run and throws an error from `Get-Item` statement.</span></span>

```powershell
./Script.ps1
```

```Output
Get-Item: C:\Script.ps1
Line |
  11 | Get-Item -Path .\stuff
     | ^ Cannot find path 'C:\demo\stuff' because it does not exist.
```

<span data-ttu-id="7102d-279">この例では、の値 `$ErrorView` が **normalview** に変更されたときにエラーがどのように表示されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="7102d-279">This example shows how an error appears when the value of `$ErrorView` is changed to **NormalView**.</span></span> <span data-ttu-id="7102d-280">`Get-ChildItem` は、存在しないファイルを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-280">`Get-ChildItem` is used to find a non-existent file.</span></span>

```powershell
Get-ChildItem -Path C:\nofile.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\nofile.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path C:\nofile.txt
```

<span data-ttu-id="7102d-281">この例は、の値 `$ErrorView` が **カテゴリビュー** に変更された場合に、同じエラーがどのように表示されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-281">This example shows how the same error appears when the value of `$ErrorView` is changed to **CategoryView**.</span></span>

```powershell
$ErrorView = "CategoryView"
Get-ChildItem -Path C:\nofile.txt
```

```Output
ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem], ItemNotFoundException
```

<span data-ttu-id="7102d-282">この例では、の値が `$ErrorView` エラー表示にのみ影響することを示しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-282">This example demonstrates that the value of `$ErrorView` only affects the error display.</span></span> <span data-ttu-id="7102d-283">自動変数に格納されているエラーオブジェクトの構造は変更されません `$Error` 。</span><span class="sxs-lookup"><span data-stu-id="7102d-283">It doesn't change the structure of the error object that is stored in the `$Error` automatic variable.</span></span> <span data-ttu-id="7102d-284">自動変数の詳細については `$Error` 、「 [about_automatic_variables](about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-284">For information about the `$Error` automatic variable, see [about_automatic_variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="7102d-285">次のコマンドは、エラー配列内の最新のエラーに関連付けられた **Errorrecord** オブジェクトを取得し、 **要素 0** を使用して、リスト内のすべてのエラーオブジェクトのプロパティを書式設定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-285">The following command takes the **ErrorRecord** object associated with the most recent error in the error array, **element 0** , and formats all the error object's properties in a list.</span></span>

```powershell
$Error[0] | Format-List -Property * -Force
```

```Output
PSMessageDetails      :
Exception             : System.Management.Automation.ItemNotFoundException:
                          Cannot find path 'C:\nofile.txt' because it does
                          not exist.
                        at System.Management.Automation.SessionStateInternal.
                          GetChildItems(String path, Boolean recurse, UInt32
                          depth, CmdletProviderContext context)
                        at System.Management.Automation.ChildItemCmdlet
                          ProviderIntrinsics.Get(String path, Boolean
                          recurse, UInt32 depth, CmdletProviderContext context)
                        at Microsoft.PowerShell.Commands.GetChildItemCommand.
                          ProcessRecord()
TargetObject          : C:\nofile.txt
CategoryInfo          : ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem],
                          ItemNotFoundException
FullyQualifiedErrorId : PathNotFound,
                          Microsoft.PowerShell.Commands.GetChildItemCommand
ErrorDetails          :
InvocationInfo        : System.Management.Automation.InvocationInfo
ScriptStackTrace      : at <ScriptBlock>, <No file>: line 1
PipelineIterationInfo : {0, 1}
```

### <a name="formatenumerationlimit"></a><span data-ttu-id="7102d-286">\$FormatEnumerationLimit</span><span class="sxs-lookup"><span data-stu-id="7102d-286">\$FormatEnumerationLimit</span></span>

<span data-ttu-id="7102d-287">表示に含める列挙された項目の数を決定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-287">Determines how many enumerated items are included in a display.</span></span> <span data-ttu-id="7102d-288">この変数は、基になるオブジェクトには影響しません。表示のみです。</span><span class="sxs-lookup"><span data-stu-id="7102d-288">This variable doesn't affect the underlying objects, only the display.</span></span> <span data-ttu-id="7102d-289">の値 `$FormatEnumerationLimit` が列挙された項目の数よりも小さい場合は、 `...` 表示されていない項目を示す省略記号 () が PowerShell によって追加されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-289">When the value of `$FormatEnumerationLimit` is fewer than the number of enumerated items, PowerShell adds an ellipsis (`...`) to indicate items not shown.</span></span>

<span data-ttu-id="7102d-290">**有効な値** : 整数 ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="7102d-290">**Valid values** : Integers (`Int32`)</span></span>

<span data-ttu-id="7102d-291">**既定値** : 4</span><span class="sxs-lookup"><span data-stu-id="7102d-291">**Default value** : 4</span></span>

#### <a name="examples"></a><span data-ttu-id="7102d-292">例</span><span class="sxs-lookup"><span data-stu-id="7102d-292">Examples</span></span>

<span data-ttu-id="7102d-293">この例では、変数を使用して、列挙され `$FormatEnumerationLimit` た項目の表示を改善する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7102d-293">This example shows how to use the `$FormatEnumerationLimit` variable to improve the display of enumerated items.</span></span>

<span data-ttu-id="7102d-294">この例のコマンドは、コンピューター上で実行されているすべてのサービスを一覧表示するテーブルを生成します。1つはサービスの **実行** 用で、もう1つは **停止** したサービス用です。</span><span class="sxs-lookup"><span data-stu-id="7102d-294">The command in this example generates a table that lists all the services running on the computer in two groups: one for **running** services and one for **stopped** services.</span></span> <span data-ttu-id="7102d-295">コマンドを使用して `Get-Service` すべてのサービスを取得し、パイプラインを介して結果をコマンドレットに送信し `Group-Object` ます。これにより、結果がサービスの状態別にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-295">It uses a `Get-Service` command to get all the services, and then sends the results through the pipeline to the `Group-Object` cmdlet, which groups the results by the service status.</span></span>

<span data-ttu-id="7102d-296">その結果、[ **名前** ] 列の状態と [ **グループ]** 列のプロセスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-296">The result is a table that lists the status in the **Name** column, and the processes in the **Group** column.</span></span> <span data-ttu-id="7102d-297">列ラベルを変更するには、「 [about_Hash_Tables](about_Hash_Tables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-297">To change the column labels, use a hash table, see [about_Hash_Tables](about_Hash_Tables.md).</span></span> <span data-ttu-id="7102d-298">詳細については、「 [形式テーブル](xref:Microsoft.PowerShell.Utility.Format-Table)」の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-298">For more information, see the examples in [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

<span data-ttu-id="7102d-299">の現在の値を検索 `$FormatEnumerationLimit` します。</span><span class="sxs-lookup"><span data-stu-id="7102d-299">Find the current value of `$FormatEnumerationLimit`.</span></span>

```powershell
$FormatEnumerationLimit
```

```Output
4
```

<span data-ttu-id="7102d-300">**状態** 別にグループ化されたすべてのサービスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7102d-300">List all services grouped by **Status**.</span></span> <span data-ttu-id="7102d-301">各状態の [ **グループ]** 列には、の値が4であるため、最大4つのサービスが表示され `$FormatEnumerationLimit` ます。 **4**</span><span class="sxs-lookup"><span data-stu-id="7102d-301">There are a maximum of four services listed in the **Group** column for each status because `$FormatEnumerationLimit` has a value of **4**.</span></span>

```powershell
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv...}
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart...}
```

<span data-ttu-id="7102d-302">表示される項目の数を増やすには、の値を `$FormatEnumerationLimit` **1000** に増やします。</span><span class="sxs-lookup"><span data-stu-id="7102d-302">To increase the number of items listed, increase the value of `$FormatEnumerationLimit` to **1000**.</span></span> <span data-ttu-id="7102d-303">`Get-Service` `Group-Object` サービスを表示するには、およびを使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-303">Use `Get-Service` and `Group-Object` to display the services.</span></span>

```powershell
$FormatEnumerationLimit = 1000
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv, BITS, CcmExec...
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart, Browser, CiSvc...
```

<span data-ttu-id="7102d-304">`Format-Table` **Wrap** パラメーターと共にを使用して、サービスの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="7102d-304">Use `Format-Table` with the **Wrap** parameter to display the list of services.</span></span>

```powershell
Get-Service | Group-Object -Property Status | Format-Table -Wrap
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv, BITS, CcmExec,
                  Client for NFS, CryptSvc, DcomLaunch, Dhcp, dmserver,
                  Dnscache, ERSvc, Eventlog, EventSystem, FwcAgent, helpsvc,
                  HidServ, IISADMIN, InoRPC, InoRT, InoTask, lanmanserver,
                  lanmanworkstation, LmHosts, MDM, Netlogon, Netman, Nla,
                  NtLmSsp, PlugPlay, PolicyAgent, ProtectedStorage, RasMan,
                  RemoteRegistry, RpcSs, SamSs, Schedule, seclogon, SENS,
                  SharedAccess, ShellHWDetection, SMT PSVC, Spooler,
                  srservice, SSDPSRV, stisvc, TapiSrv, TermService, Themes,
                  TrkWks, UMWdf, W32Time, W3SVC, WebClient, winmgmt, wscsvc,
                  wuauserv, WZCSVC, zzInterix}

41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart, Browser, CiSvc,
                  ClipSrv, clr_optimization_v2.0.50727_32, COMSysApp,
                  CronService, dmadmin, FastUserSwitchingCompatibility,
                  HTTPFilter, ImapiService, Mapsvc, Messenger, mnmsrvc,
                  MSDTC, MSIServer, msvsmon80, NetDDE, NetDDEdsdm, NtmsSvc,
                  NVSvc, ose, RasAuto, RDSessMgr, RemoteAccess, RpcLocator,
                  SCardSvr, SwPrv, SysmonLog, TlntSvr, upnphost, UPS, VSS,
                  WmdmPmSN, Wmi, WmiApSrv, xmlprov}
```

### <a name="informationpreference"></a><span data-ttu-id="7102d-305">\$Informationpreference は</span><span class="sxs-lookup"><span data-stu-id="7102d-305">\$InformationPreference</span></span>

<span data-ttu-id="7102d-306">`$InformationPreference`変数を使用すると、ユーザーに表示する情報ストリームの設定を設定できます。</span><span class="sxs-lookup"><span data-stu-id="7102d-306">The `$InformationPreference` variable lets you set information stream preferences that you want displayed to users.</span></span> <span data-ttu-id="7102d-307">具体的には、 [書き込み情報](xref:Microsoft.PowerShell.Utility.Write-Information) のコマンドレットを追加して、コマンドまたはスクリプトに追加した情報メッセージです。</span><span class="sxs-lookup"><span data-stu-id="7102d-307">Specifically, informational messages that you added to commands or scripts by adding the [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) cmdlet.</span></span> <span data-ttu-id="7102d-308">**Informationaction** パラメーターが使用されている場合、その値は変数の値よりも優先され `$InformationPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-308">If the **InformationAction** parameter is used, its value overrides the value of the `$InformationPreference` variable.</span></span> <span data-ttu-id="7102d-309">`Write-Information` は、PowerShell 5.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7102d-309">`Write-Information` was introduced in PowerShell 5.0.</span></span>

<span data-ttu-id="7102d-310">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7102d-310">The valid values are as follows:</span></span>

- <span data-ttu-id="7102d-311">**Stop** : コマンドの発生時に、コマンドまたはスクリプトを停止し `Write-Information` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-311">**Stop** : Stops a command or script at an occurrence of the `Write-Information` command.</span></span>
- <span data-ttu-id="7102d-312">**Inquire** : コマンドで指定した情報メッセージを表示し `Write-Information` 、続行するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7102d-312">**Inquire** : Displays the informational message that you specify in a `Write-Information` command, then asks whether you want to continue.</span></span>
- <span data-ttu-id="7102d-313">[ **続行** ]: 情報メッセージを表示し、実行を継続します。</span><span class="sxs-lookup"><span data-stu-id="7102d-313">**Continue** : Displays the informational message, and continues running.</span></span>
- <span data-ttu-id="7102d-314">**Suspend** は、PowerShell 6 以降ではサポートされていないワークフローでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7102d-314">**Suspend** is only available for workflows which aren't supported in PowerShell 6 and beyond.</span></span>
- <span data-ttu-id="7102d-315">**SilentlyContinue** : (既定) 効果はありません。</span><span class="sxs-lookup"><span data-stu-id="7102d-315">**SilentlyContinue** : (Default) No effect.</span></span> <span data-ttu-id="7102d-316">情報メッセージは表示されず、スクリプトは中断されることなく続行されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-316">The informational messages aren't displayed, and the script continues without interruption.</span></span>

### <a name="logevent"></a><span data-ttu-id="7102d-317">\$Log \* イベント</span><span class="sxs-lookup"><span data-stu-id="7102d-317">\$Log\*Event</span></span>

<span data-ttu-id="7102d-318">**Log \* イベント** ユーザー設定変数は、イベントビューアーで PowerShell イベントログに書き込まれるイベントの種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-318">The **Log\*Event** preference variables determine which types of events are written to the PowerShell event log in Event Viewer.</span></span> <span data-ttu-id="7102d-319">既定では、エンジンイベントとプロバイダーイベントのみがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-319">By default, only engine and provider events are logged.</span></span> <span data-ttu-id="7102d-320">ただし、 **log \* イベント** ユーザー設定変数を使用して、コマンドに関するイベントのログ記録などのログをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="7102d-320">But, you can use the **Log\*Event** preference variables to customize your log, such as logging events about commands.</span></span>

<span data-ttu-id="7102d-321">**Log \* イベント** ユーザー設定変数は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7102d-321">The **Log\*Event** preference variables are as follows:</span></span>

- <span data-ttu-id="7102d-322">`$LogCommandHealthEvent`: コマンドの初期化および処理中に発生したエラーと例外をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="7102d-322">`$LogCommandHealthEvent`: Logs errors and exceptions in command initialization and processing.</span></span> <span data-ttu-id="7102d-323">既定値は `$false` (ログに記録されません) です。</span><span class="sxs-lookup"><span data-stu-id="7102d-323">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="7102d-324">`$LogCommandLifecycleEvent`: コマンド検出のコマンドとコマンドパイプラインおよびセキュリティ例外の開始と停止をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="7102d-324">`$LogCommandLifecycleEvent`: Logs the starting and stopping of commands and command pipelines and security exceptions in command discovery.</span></span> <span data-ttu-id="7102d-325">既定値は `$false` (ログに記録されません) です。</span><span class="sxs-lookup"><span data-stu-id="7102d-325">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="7102d-326">`$LogEngineHealthEvent`: セッションのエラーとエラーをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="7102d-326">`$LogEngineHealthEvent`: Logs errors and failures of sessions.</span></span> <span data-ttu-id="7102d-327">既定値は `$true` (ログに記録されます) です。</span><span class="sxs-lookup"><span data-stu-id="7102d-327">The default is `$true` (logged).</span></span>
- <span data-ttu-id="7102d-328">`$LogEngineLifecycleEvent`: セッションの開始と終了をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="7102d-328">`$LogEngineLifecycleEvent`: Logs the opening and closing of sessions.</span></span> <span data-ttu-id="7102d-329">既定値は `$true` (ログに記録されます) です。</span><span class="sxs-lookup"><span data-stu-id="7102d-329">The default is `$true` (logged).</span></span>
- <span data-ttu-id="7102d-330">`$LogProviderHealthEvent`: 読み取りおよび書き込みエラー、参照エラー、呼び出しエラーなど、プロバイダーのエラーをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="7102d-330">`$LogProviderHealthEvent`: Logs provider errors, such as read and write errors, lookup errors, and invocation errors.</span></span> <span data-ttu-id="7102d-331">既定値は `$true` (ログに記録されます) です。</span><span class="sxs-lookup"><span data-stu-id="7102d-331">The default is `$true` (logged).</span></span>
- <span data-ttu-id="7102d-332">`$LogProviderLifecycleEvent`: PowerShell プロバイダーの追加と削除をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="7102d-332">`$LogProviderLifecycleEvent`: Logs adding and removing of PowerShell providers.</span></span> <span data-ttu-id="7102d-333">既定値は `$true` (ログに記録されます) です。</span><span class="sxs-lookup"><span data-stu-id="7102d-333">The default is `$true` (logged).</span></span> <span data-ttu-id="7102d-334">PowerShell プロバイダーの詳細については、「 [about_Providers](about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-334">For information about PowerShell providers, see [about_Providers](about_Providers.md).</span></span>

<span data-ttu-id="7102d-335">**Log \* イベント** を有効にするには、次の例のように、値を持つ変数を入力し `$true` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-335">To enable a **Log\*Event** , type the variable with a value of `$true`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $true
```

<span data-ttu-id="7102d-336">イベントの種類を無効にするには、という値を持つ変数を入力し `$false` ます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7102d-336">To disable an event type, type the variable with a value of `$false`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $false
```

<span data-ttu-id="7102d-337">有効にするイベントは、現在の PowerShell コンソールでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="7102d-337">The events that you enable are effective only for the current PowerShell console.</span></span> <span data-ttu-id="7102d-338">すべてのコンソールに構成を適用するには、PowerShell プロファイルに変数の設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="7102d-338">To apply the configuration to all consoles, save the variable settings in your PowerShell profile.</span></span> <span data-ttu-id="7102d-339">詳細については、「 [about_Profiles](about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-339">For more information, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="maximumhistorycount"></a><span data-ttu-id="7102d-340">\$Maximumhistorycount ユーザー</span><span class="sxs-lookup"><span data-stu-id="7102d-340">\$MaximumHistoryCount</span></span>

<span data-ttu-id="7102d-341">現在のセッションのコマンド履歴に保存されているコマンドの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-341">Determines how many commands are saved in the command history for the current session.</span></span>

<span data-ttu-id="7102d-342">**有効な値** : 1-32768 ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="7102d-342">**Valid values** : 1 - 32768 (`Int32`)</span></span>

<span data-ttu-id="7102d-343">**既定値** : 4096</span><span class="sxs-lookup"><span data-stu-id="7102d-343">**Default** : 4096</span></span>

<span data-ttu-id="7102d-344">コマンド履歴に現在保存されているコマンドの数を確認するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7102d-344">To determine the number of commands current saved in the command history, type:</span></span>

```powershell
(Get-History).Count
```

<span data-ttu-id="7102d-345">セッションの履歴に保存されているコマンドを確認するには、コマンドレットを使用し `Get-History` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-345">To see the commands saved in your session history, use the `Get-History` cmdlet.</span></span> <span data-ttu-id="7102d-346">詳細については、「 [about_History](about_History.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-346">For more information, see [about_History](about_History.md).</span></span>

### <a name="ofs"></a><span data-ttu-id="7102d-347">\$.OFS</span><span class="sxs-lookup"><span data-stu-id="7102d-347">\$OFS</span></span>

<span data-ttu-id="7102d-348">出力フィールド区切り記号 (OFS) は、文字列に変換される配列の要素を区切る文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-348">The Output Field Separator (OFS) specifies the character that separates the elements of an array that is converted to a string.</span></span>

<span data-ttu-id="7102d-349">**有効な値** : 任意の文字列。</span><span class="sxs-lookup"><span data-stu-id="7102d-349">**Valid values** : Any string.</span></span>

<span data-ttu-id="7102d-350">**既定値** : Space</span><span class="sxs-lookup"><span data-stu-id="7102d-350">**Default** : Space</span></span>

<span data-ttu-id="7102d-351">既定では、変数は存在せず、 `$OFS` 出力ファイルの区切り記号は空白ですが、この変数を追加して任意の文字列に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="7102d-351">By default, the `$OFS` variable doesn't exist and the output file separator is a space, but you can add this variable and set it to any string.</span></span> <span data-ttu-id="7102d-352">セッションのの値を変更する `$OFS` には、「」と入力 `$OFS="<value>"` します。</span><span class="sxs-lookup"><span data-stu-id="7102d-352">You can change the value of `$OFS` in your session, by typing `$OFS="<value>"`.</span></span>

> [!NOTE]
> <span data-ttu-id="7102d-353">`" "`スクリプト、モジュール、または構成の出力で空白 () の既定値が予想される場合は、 `$OFS` 既定値がコード内の他の場所で変更されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-353">If you're expecting the default value of a space (`" "`) in your script, module, or configuration output, be careful that the `$OFS` default value hasn't been changed elsewhere in your code.</span></span>

#### <a name="examples"></a><span data-ttu-id="7102d-354">例</span><span class="sxs-lookup"><span data-stu-id="7102d-354">Examples</span></span>

<span data-ttu-id="7102d-355">この例は、配列が文字列に変換されるときに、値を区切るためにスペースを使用することを示しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-355">This example shows that a space is used to separate the values when an array is converted to a string.</span></span> <span data-ttu-id="7102d-356">この場合、整数の配列は変数に格納され、変数は文字列としてキャストされます。</span><span class="sxs-lookup"><span data-stu-id="7102d-356">In this case, an array of integers is stored in a variable and then the variable is cast as a string.</span></span>

```powershell
$array = 1,2,3,4
[string]$array
```

```Output
1 2 3 4
```

<span data-ttu-id="7102d-357">区切り記号を変更するには、 `$OFS` 変数に値を代入して変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="7102d-357">To change the separator, add the `$OFS` variable by assigning a value to it.</span></span>
<span data-ttu-id="7102d-358">変数はという名前にする必要があり `$OFS` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-358">The variable must be named `$OFS`.</span></span>

```powershell
$OFS = "+"
[string]$array
```

```Output
1+2+3+4
```

<span data-ttu-id="7102d-359">既定の動作を復元するには、 `" "` の値に空白 () を割り当てる `$OFS` か、変数を削除します。</span><span class="sxs-lookup"><span data-stu-id="7102d-359">To restore the default behavior, you can assign a space (`" "`) to the value of `$OFS` or delete the variable.</span></span> <span data-ttu-id="7102d-360">次のコマンドは、変数を削除し、区切り記号がスペースであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7102d-360">The following commands delete the variable and then verify that the separator is a space.</span></span>

```powershell
Remove-Variable OFS
[string]$array
```

```Output
1 2 3 4
```

### <a name="outputencoding"></a><span data-ttu-id="7102d-361">\$OutputEncoding</span><span class="sxs-lookup"><span data-stu-id="7102d-361">\$OutputEncoding</span></span>

<span data-ttu-id="7102d-362">他のアプリケーションにテキストを送信するときに PowerShell が使用する文字エンコード方式を決定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-362">Determines the character encoding method that PowerShell uses when it sends text to other applications.</span></span>

<span data-ttu-id="7102d-363">たとえば、アプリケーションが Unicode 文字列を PowerShell に返す場合、値を **UnicodeEncoding** に変更して文字を正しく送信することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7102d-363">For example, if an application returns Unicode strings to PowerShell, you might need to change the value to **UnicodeEncoding** to send the characters correctly.</span></span>

<span data-ttu-id="7102d-364">有効な値は次のとおりです。 **ASCIIEncoding** 、 **SBCSCodePageEncoding** 、 **UTF7Encoding** 、 **UTF8Encoding** 、 **UTF32Encoding** 、 **UnicodeEncoding** などのエンコーディングクラスから派生したオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7102d-364">The valid values are as follows: Objects derived from an Encoding class, such as **ASCIIEncoding** , **SBCSCodePageEncoding** , **UTF7Encoding** , **UTF8Encoding** , **UTF32Encoding** , and **UnicodeEncoding**.</span></span>

<span data-ttu-id="7102d-365">**既定値** : UTF8Encoding Object (UTF8Encoding)</span><span class="sxs-lookup"><span data-stu-id="7102d-365">**Default** : UTF8Encoding object (System.Text.UTF8Encoding)</span></span>

#### <a name="examples"></a><span data-ttu-id="7102d-366">例</span><span class="sxs-lookup"><span data-stu-id="7102d-366">Examples</span></span>

<span data-ttu-id="7102d-367">この例では、中国語などの Unicode 文字を使用する言語用にローカライズされたコンピューターで Windows **findstr.exe** コマンドを PowerShell で動作させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7102d-367">This example shows how to make the Windows **findstr.exe** command work in PowerShell on a computer that is localized for a language that uses Unicode characters, such as Chinese.</span></span>

<span data-ttu-id="7102d-368">最初のコマンドは、の値を検索し `$OutputEncoding` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-368">The first command finds the value of `$OutputEncoding`.</span></span> <span data-ttu-id="7102d-369">値はエンコーディングオブジェクトであるため、 **encoding.encodingname** プロパティのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="7102d-369">Because the value is an encoding object, display only its **EncodingName** property.</span></span>

```powershell
$OutputEncoding.EncodingName
```

<span data-ttu-id="7102d-370">この例では、 **findstr.exe** コマンドを使用して、ファイル内に存在する2つの中国語文字を検索し `Test.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-370">In this example, a **findstr.exe** command is used to search for two Chinese characters that are present in the `Test.txt` file.</span></span> <span data-ttu-id="7102d-371">この **findstr.exe** コマンドを Windows コマンドプロンプト ( **cmd.exe** ) で実行すると、 **findstr.exe** によってテキストファイル内の文字が検索されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-371">When this **findstr.exe** command is run in the Windows Command Prompt ( **cmd.exe** ), **findstr.exe** finds the characters in the text file.</span></span> <span data-ttu-id="7102d-372">ただし、PowerShell で同じ **findstr.exe** コマンドを実行した場合、文字は検出されません。これは、Powershell が Unicode テキストではなく ASCII テキストで **findstr.exe** に送信するためです。</span><span class="sxs-lookup"><span data-stu-id="7102d-372">However, when you run the same **findstr.exe** command in PowerShell, the characters aren't found because the PowerShell sends them to **findstr.exe** in ASCII text, instead of in Unicode text.</span></span>

```powershell
findstr <Unicode-characters>
```

<span data-ttu-id="7102d-373">PowerShell でコマンドが動作するようにするには、の値 `$OutputEncoding` をコンソールの **outputencoding** プロパティの値に設定します。これは、Windows で選択されているロケールに基づいています。</span><span class="sxs-lookup"><span data-stu-id="7102d-373">To make the command work in PowerShell, set the value of `$OutputEncoding` to the value of the **OutputEncoding** property of the console, that is based on the locale selected for Windows.</span></span> <span data-ttu-id="7102d-374">**Outputencoding** はコンソールの静的プロパティであるため、コマンドで二重コロン () を使用し `::` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-374">Because **OutputEncoding** is a static property of the console, use double-colons (`::`) in the command.</span></span>

```powershell
$OutputEncoding = [console]::OutputEncoding
$OutputEncoding.EncodingName
```

```Output
OEM United States
```

<span data-ttu-id="7102d-375">エンコードを変更すると、 **findstr.exe** コマンドによって Unicode 文字が検索されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-375">After the encoding change, the **findstr.exe** command finds the Unicode characters.</span></span>

```powershell
findstr <Unicode-characters>
```

```Output
test.txt:         <Unicode-characters>
```

### <a name="progresspreference"></a><span data-ttu-id="7102d-376">\$ProgressPreference</span><span class="sxs-lookup"><span data-stu-id="7102d-376">\$ProgressPreference</span></span>

<span data-ttu-id="7102d-377">PowerShell が、スクリプト、コマンドレット、またはプロバイダーによって生成された進行状況の更新に応答する方法を決定します。たとえば、 [書き込みの進行状況](xref:Microsoft.PowerShell.Utility.Write-Progress) のコマンドレットによって生成された進行状況バーなどです。</span><span class="sxs-lookup"><span data-stu-id="7102d-377">Determines how PowerShell responds to progress updates generated by a script, cmdlet, or provider, such as the progress bars generated by the [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress) cmdlet.</span></span>
<span data-ttu-id="7102d-378">`Write-Progress`コマンドレットは、コマンドの状態を示す進行状況バーを作成します。</span><span class="sxs-lookup"><span data-stu-id="7102d-378">The `Write-Progress` cmdlet creates progress bars that show a command's status.</span></span>

<span data-ttu-id="7102d-379">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7102d-379">The valid values are as follows:</span></span>

- <span data-ttu-id="7102d-380">[ **停止** : 進行状況バーを表示しません。</span><span class="sxs-lookup"><span data-stu-id="7102d-380">**Stop** : Doesn't display the progress bar.</span></span> <span data-ttu-id="7102d-381">代わりに、エラーメッセージが表示され、実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="7102d-381">Instead, it displays an error message and stops executing.</span></span>
- <span data-ttu-id="7102d-382">**Inquire** : 進行状況バーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="7102d-382">**Inquire** : Doesn't display the progress bar.</span></span> <span data-ttu-id="7102d-383">続行するためのアクセス許可を要求します。</span><span class="sxs-lookup"><span data-stu-id="7102d-383">Prompts for permission to continue.</span></span> <span data-ttu-id="7102d-384">またはで返信すると `Y` `A` 、進行状況バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-384">If you reply with `Y` or `A`, it displays the progress bar.</span></span>
- <span data-ttu-id="7102d-385">**続行** : (既定) 進行状況バーを表示し、実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="7102d-385">**Continue** : (Default) Displays the progress bar and continues with execution.</span></span>
- <span data-ttu-id="7102d-386">**SilentlyContinue** : コマンドを実行しますが、進行状況バーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="7102d-386">**SilentlyContinue** : Executes the command, but doesn't display the progress bar.</span></span>

### <a name="psemailserver"></a><span data-ttu-id="7102d-387">\$PSEmailServer</span><span class="sxs-lookup"><span data-stu-id="7102d-387">\$PSEmailServer</span></span>

<span data-ttu-id="7102d-388">電子メールメッセージの送信に使用する既定の電子メールサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-388">Specifies the default e-mail server that is used to send email messages.</span></span> <span data-ttu-id="7102d-389">このユーザー設定変数は、電子メールを送信するコマンドレット ( [send-mailmessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) コマンドレットなど) によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-389">This preference variable is used by cmdlets that send email, such as the [Send-MailMessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) cmdlet.</span></span>

### <a name="psdefaultparametervalues"></a><span data-ttu-id="7102d-390">\$PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="7102d-390">\$PSDefaultParameterValues</span></span>

<span data-ttu-id="7102d-391">コマンドレットおよび高度な関数のパラメーターの既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-391">Specifies default values for the parameters of cmdlets and advanced functions.</span></span>
<span data-ttu-id="7102d-392">の値 `$PSDefaultParameterValues` はハッシュテーブルです。キーはコマンドレット名とパラメーター名で構成され、コロン () で区切られ `:` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-392">The value of `$PSDefaultParameterValues` is a hash table where the key consists of the cmdlet name and parameter name separated by a colon (`:`).</span></span> <span data-ttu-id="7102d-393">値は、ユーザーが指定するカスタムの既定値です。</span><span class="sxs-lookup"><span data-stu-id="7102d-393">The value is a custom default value that you specify.</span></span>

<span data-ttu-id="7102d-394">`$PSDefaultParameterValues` は、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="7102d-394">`$PSDefaultParameterValues` was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="7102d-395">このユーザー設定変数の詳細については、「 [about_Parameters_Default_Values](about_Parameters_Default_Values.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-395">For more information about this preference variable, see [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span></span>

### <a name="psmoduleautoloadingpreference"></a><span data-ttu-id="7102d-396">\$PSModuleAutoloadingPreference</span><span class="sxs-lookup"><span data-stu-id="7102d-396">\$PSModuleAutoloadingPreference</span></span>

<span data-ttu-id="7102d-397">セッションのモジュールの自動インポートを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="7102d-397">Enables and disables automatic importing of modules in the session.</span></span> <span data-ttu-id="7102d-398">**All** が既定値です。</span><span class="sxs-lookup"><span data-stu-id="7102d-398">**All** is the default.</span></span> <span data-ttu-id="7102d-399">変数の値に関係なく、モジュールをインポート [するには、モジュールを](xref:Microsoft.PowerShell.Core.Import-Module) インポートします。</span><span class="sxs-lookup"><span data-stu-id="7102d-399">Regardless of the variable's value, you can use [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) to import a module.</span></span>

<span data-ttu-id="7102d-400">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7102d-400">Valid values are:</span></span>

- <span data-ttu-id="7102d-401">**すべて** : モジュールは初回使用時に自動的にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="7102d-401">**All** : Modules are imported automatically on first-use.</span></span> <span data-ttu-id="7102d-402">モジュールをインポートするには、モジュール内の任意のコマンドを取得または使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-402">To import a module, get or use any command in the module.</span></span> <span data-ttu-id="7102d-403">たとえば、 `Get-Command`を使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-403">For example, use `Get-Command`.</span></span>
- <span data-ttu-id="7102d-404">**Modulの** 修飾: モジュールは、ユーザーがモジュール内のコマンドのモジュール修飾名を使用した場合にのみ、自動的にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="7102d-404">**ModuleQualified** : Modules are imported automatically only when a user uses the module-qualified name of a command in the module.</span></span> <span data-ttu-id="7102d-405">たとえば、ユーザーがと入力すると、 `MyModule\MyCommand` PowerShell は **MyModule** モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="7102d-405">For example, if the user types `MyModule\MyCommand`, PowerShell imports the **MyModule** module.</span></span>
- <span data-ttu-id="7102d-406">**なし** : モジュールの自動インポートがセッションで無効になっています。</span><span class="sxs-lookup"><span data-stu-id="7102d-406">**None** : Automatic importing of modules is disabled in the session.</span></span> <span data-ttu-id="7102d-407">モジュールをインポートするには、 `Import-Module` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-407">To import a module, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="7102d-408">モジュールの自動インポートの詳細については、「 [about_Modules](about_Modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-408">For more information about automatic importing of modules, see [about_Modules](about_Modules.md).</span></span>

### <a name="pssessionapplicationname"></a><span data-ttu-id="7102d-409">\$Pssessionapplicationname ユーザー</span><span class="sxs-lookup"><span data-stu-id="7102d-409">\$PSSessionApplicationName</span></span>

<span data-ttu-id="7102d-410">Web Services for Management (WS-MANAGEMENT) テクノロジを使用するリモートコマンドの既定のアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-410">Specifies the default application name for a remote command that uses Web Services for Management (WS-Management) technology.</span></span> <span data-ttu-id="7102d-411">詳細については、「 [Windows リモート管理につい](/windows/win32/winrm/about-windows-remote-management)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-411">For more information, see [About Windows Remote Management](/windows/win32/winrm/about-windows-remote-management).</span></span>

<span data-ttu-id="7102d-412">システムの既定のアプリケーション名はです `WSMAN` が、このユーザー設定変数を使用して既定値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="7102d-412">The system default application name is `WSMAN`, but you can use this preference variable to change the default.</span></span>

<span data-ttu-id="7102d-413">アプリケーション名は、接続 URI の最後のノードです。</span><span class="sxs-lookup"><span data-stu-id="7102d-413">The application name is the last node in a connection URI.</span></span> <span data-ttu-id="7102d-414">たとえば、次の URI の例では、アプリケーション名が `WSMAN` です。</span><span class="sxs-lookup"><span data-stu-id="7102d-414">For example, the application name in the following sample URI is `WSMAN`.</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="7102d-415">既定のアプリケーション名は、リモートコマンドで接続 URI またはアプリケーション名が指定されていない場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-415">The default application name is used when the remote command doesn't specify a connection URI or an application name.</span></span>

<span data-ttu-id="7102d-416">**WinRM** サービスは、アプリケーション名を使用して、接続要求を処理するリスナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="7102d-416">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="7102d-417">パラメーターの値は、リモートコンピューター上のリスナーの **Urlprefix** プロパティの値と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7102d-417">The parameter's value should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

<span data-ttu-id="7102d-418">システムの既定値とこの変数の値を上書きし、特定のセッションに対して別のアプリケーション名を選択するには、 [新しい PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)、 [Enter-pssession](xref:Microsoft.PowerShell.Core.Enter-PSSession)、または [Invoke コマンド](xref:Microsoft.PowerShell.Core.Invoke-Command)レットの **connectionuri** または **ApplicationName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-418">To override the system default and the value of this variable, and select a different application name for a particular session, use the **ConnectionURI** or **ApplicationName** parameters of the [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession), or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) cmdlets.</span></span>

<span data-ttu-id="7102d-419">ユーザー設定 `$PSSessionApplicationName` 変数はローカルコンピューターで設定されますが、リモートコンピューター上のリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-419">The `$PSSessionApplicationName` preference variable is set on the local computer, but it specifies a listener on the remote computer.</span></span> <span data-ttu-id="7102d-420">指定したアプリケーション名がリモートコンピューター上に存在しない場合、セッションを確立するコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="7102d-420">If the application name that you specify doesn't exist on the remote computer, the command to establish the session fails.</span></span>

### <a name="pssessionconfigurationname"></a><span data-ttu-id="7102d-421">\$Pssessionconfigurationname ユーザー</span><span class="sxs-lookup"><span data-stu-id="7102d-421">\$PSSessionConfigurationName</span></span>

<span data-ttu-id="7102d-422">現在のセッション **で作成された** pssession に使用される既定のセッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-422">Specifies the default session configuration that is used for **PSSessions** created in the current session.</span></span>

<span data-ttu-id="7102d-423">このユーザー設定変数はローカルコンピューターで設定されますが、リモートコンピューター上にあるセッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-423">This preference variable is set on the local computer, but it specifies a session configuration that's located on the remote computer.</span></span>

<span data-ttu-id="7102d-424">変数の値 `$PSSessionConfigurationName` は、完全修飾リソース URI です。</span><span class="sxs-lookup"><span data-stu-id="7102d-424">The value of the `$PSSessionConfigurationName` variable is a fully qualified resource URI.</span></span>

<span data-ttu-id="7102d-425">既定値は、 `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` リモートコンピューター上の **Microsoft PowerShell** セッション構成を示します。</span><span class="sxs-lookup"><span data-stu-id="7102d-425">The default value `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` indicates the **Microsoft.PowerShell** session configuration on the remote computer.</span></span>

<span data-ttu-id="7102d-426">構成名だけを指定した場合は、次のスキーマ URI が前に付加されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-426">If you specify only a configuration name, the following schema URI is prepended:</span></span>

`http://schemas.microsoft.com/PowerShell/`

<span data-ttu-id="7102d-427">**ConfigurationName** `New-PSSession` 、、 `Enter-PSSession` またはコマンドレットの ConfigurationName パラメーターを使用して、既定値を上書きし、特定のセッションに対して別のセッション構成を選択することができ `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-427">You can override the default and select a different session configuration for a particular session by using the **ConfigurationName** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="7102d-428">この変数の値はいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="7102d-428">You can change the value of this variable at any time.</span></span> <span data-ttu-id="7102d-429">この場合は、選択したセッション構成がリモートコンピューターに存在する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-429">When you do, remember that the session configuration that you select must exist on the remote computer.</span></span> <span data-ttu-id="7102d-430">そうでない場合、セッション構成を使用するセッションを作成するコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="7102d-430">If it doesn't, the command to create a session that uses the session configuration fails.</span></span>

<span data-ttu-id="7102d-431">このユーザー設定変数は、リモートユーザーがこのコンピューターに接続するセッションを作成するときに使用されるローカルセッション構成を決定しません。</span><span class="sxs-lookup"><span data-stu-id="7102d-431">This preference variable doesn't determine which local session configurations are used when remote users create a session that connects to this computer.</span></span>
<span data-ttu-id="7102d-432">ただし、ローカルセッション構成のアクセス許可を使用して、使用できるユーザーを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="7102d-432">However, you can use the permissions for the local session configurations to determine which users may use them.</span></span>

### <a name="pssessionoption"></a><span data-ttu-id="7102d-433">\$PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="7102d-433">\$PSSessionOption</span></span>

<span data-ttu-id="7102d-434">リモートセッションでの高度なユーザーオプションの既定値を設定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-434">Establishes the default values for advanced user options in a remote session.</span></span>
<span data-ttu-id="7102d-435">これらのオプションの設定は、セッションオプションのシステムの既定値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-435">These option preferences override the system default values for session options.</span></span>

<span data-ttu-id="7102d-436">変数には、 `$PSSessionOption` **Pssessionoption** オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7102d-436">The `$PSSessionOption` variable contains a **PSSessionOption** object.</span></span> <span data-ttu-id="7102d-437">詳細については、「system.string [オプション](/dotnet/api/system.management.automation.remoting.pssessionoption)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-437">For more information, see [System.Management.Automation.Remoting.PSSessionOption](/dotnet/api/system.management.automation.remoting.pssessionoption).</span></span>
<span data-ttu-id="7102d-438">オブジェクトの各プロパティは、セッションオプションを表します。</span><span class="sxs-lookup"><span data-stu-id="7102d-438">Each property of the object represents a session option.</span></span> <span data-ttu-id="7102d-439">たとえば、 **Nocompression** プロパティは、セッション中のデータ圧縮を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7102d-439">For example, the **NoCompression** property turns of data compression during the session.</span></span>

<span data-ttu-id="7102d-440">既定では、変数には、 `$PSSessionOption` 次に示すように、すべてのオプションの既定値を持つ **Pssessionoption** オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7102d-440">By default, the `$PSSessionOption` variable contains a **PSSessionOption** object with the default values for all options, as shown below.</span></span>

```Output
MaximumConnectionRedirectionCount : 5
NoCompression                     : False
NoMachineProfile                  : False
ProxyAccessType                   : None
ProxyAuthentication               : Negotiate
ProxyCredential                   :
SkipCACheck                       : False
SkipCNCheck                       : False
SkipRevocationCheck               : False
OperationTimeout                  : 00:03:00
NoEncryption                      : False
UseUTF16                          : False
IncludePortInSPN                  : False
OutputBufferingMode               : None
Culture                           :
UICulture                         :
MaximumReceivedDataSizePerCommand :
MaximumReceivedObjectSize         : 209715200
ApplicationArguments              :
OpenTimeout                       : 00:03:00
CancelTimeout                     : 00:01:00
IdleTimeout                       : -00:00:00.0010000
```

<span data-ttu-id="7102d-441">これらのオプションの説明と詳細については、「 [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-441">For descriptions of these options and more information, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span> <span data-ttu-id="7102d-442">リモートコマンドとセッションの詳細については、「 [about_Remote](about_Remote.md) 」および「 [about_PSSessions](about_PSSessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-442">For more information about remote commands and sessions, see [about_Remote](about_Remote.md) and [about_PSSessions](about_PSSessions.md).</span></span>

<span data-ttu-id="7102d-443">ユーザー設定変数の値を変更するには、コマンドレットを使用して、 `$PSSessionOption` `New-PSSessionOption` 必要なオプション値を指定した **pssessionoption** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="7102d-443">To change the value of the `$PSSessionOption` preference variable, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object with the option values you prefer.</span></span> <span data-ttu-id="7102d-444">という変数に出力を保存 `$PSSessionOption` します。</span><span class="sxs-lookup"><span data-stu-id="7102d-444">Save the output in a variable called `$PSSessionOption`.</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -NoCompression
```

<span data-ttu-id="7102d-445">`$PSSessionOption`すべての powershell セッションでユーザー設定変数を使用するには、 `New-PSSessionOption` powershell プロファイルに変数を作成するコマンドを追加し `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-445">To use the `$PSSessionOption` preference variable in every PowerShell session, add a `New-PSSessionOption` command that creates the `$PSSessionOption` variable to your PowerShell profile.</span></span> <span data-ttu-id="7102d-446">詳細については、「 [about_Profiles](about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-446">For more information, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="7102d-447">特定のリモートセッションに対してカスタムオプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="7102d-447">You can set custom options for a particular remote session.</span></span> <span data-ttu-id="7102d-448">設定するオプションは、システムの既定値とユーザー設定変数の値よりも優先され `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-448">The options that you set take precedence over the system defaults and the value of the `$PSSessionOption` preference variable.</span></span>

<span data-ttu-id="7102d-449">カスタムセッションオプションを設定するには、コマンドレットを使用して `New-PSSessionOption` **Pssessionoption** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="7102d-449">To set custom session options, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object.</span></span> <span data-ttu-id="7102d-450">次に、、、などのセッションを作成するコマンドレットの **sessionoption** パラメーターの値として **pssessionoption** オブジェクトを使用し `New-PSSession` `Enter-PSSession` `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-450">Then, use the **PSSessionOption** object as the value of the **SessionOption** parameter in cmdlets that create a session, such as `New-PSSession`, `Enter-PSSession`, and `Invoke-Command`.</span></span>

### <a name="transcript"></a><span data-ttu-id="7102d-451">$Transcript</span><span class="sxs-lookup"><span data-stu-id="7102d-451">$Transcript</span></span>

<span data-ttu-id="7102d-452">`Start-Transcript`トランスクリプトファイルの名前と場所を指定するために、によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-452">Used by `Start-Transcript` to specify the name and location of the transcript file.</span></span> <span data-ttu-id="7102d-453">**Path** パラメーターの値を指定しない場合、は `Start-Transcript` グローバル変数の値のパスを使用し `$Transcript` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-453">If you do not specify a value for the **Path** parameter, `Start-Transcript` uses the path in the value of the `$Transcript` global variable.</span></span> <span data-ttu-id="7102d-454">この変数を作成していない場合は、によっ `Start-Transcript` `$Home\My Documents` てファイルとしてディレクトリにトランスクリプトが保存され `\PowerShell_transcript.<time-stamp>.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-454">If you have not created this variable, `Start-Transcript` stores the transcripts in the `$Home\My Documents` directory as `\PowerShell_transcript.<time-stamp>.txt` files.</span></span>

### <a name="verbosepreference"></a><span data-ttu-id="7102d-455">\$VerbosePreference</span><span class="sxs-lookup"><span data-stu-id="7102d-455">\$VerbosePreference</span></span>

<span data-ttu-id="7102d-456">PowerShell が、スクリプト、コマンドレット、またはプロバイダーによって生成される詳細メッセージに応答する方法を決定します。これには、 [書き込み/詳細](xref:Microsoft.PowerShell.Utility.Write-Verbose) コマンドレットによって生成されるメッセージなどがあります。</span><span class="sxs-lookup"><span data-stu-id="7102d-456">Determines how PowerShell responds to verbose messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose) cmdlet.</span></span>
<span data-ttu-id="7102d-457">詳細メッセージには、コマンドを実行するために実行されるアクションが記述されています。</span><span class="sxs-lookup"><span data-stu-id="7102d-457">Verbose messages describe the actions performed to execute a command.</span></span>

<span data-ttu-id="7102d-458">既定では、詳細メッセージは表示されませんが、の値を変更することでこの動作を変更でき `$VerbosePreference` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-458">By default, verbose messages aren't displayed, but you can change this behavior by changing the value of `$VerbosePreference`.</span></span>

<span data-ttu-id="7102d-459">コマンドレットの **verbose** 共通パラメーターを使用して、特定のコマンドの詳細メッセージを表示または非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="7102d-459">You can use the **Verbose** common parameter of a cmdlet to display or hide the verbose messages for a specific command.</span></span> <span data-ttu-id="7102d-460">詳細については、「[about_CommonParameters](about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-460">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="7102d-461">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7102d-461">The valid values are as follows:</span></span>

- <span data-ttu-id="7102d-462">[ **停止** ]: 詳細メッセージとエラーメッセージを表示し、実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="7102d-462">**Stop** : Displays the verbose message and an error message and then stops executing.</span></span>
- <span data-ttu-id="7102d-463">[ **Inquire** ]: 詳細メッセージが表示され、続行するかどうかを確認するプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-463">**Inquire** : Displays the verbose message and then displays a prompt that asks you whether you want to continue.</span></span>
- <span data-ttu-id="7102d-464">**続行** : 詳細メッセージを表示し、実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="7102d-464">**Continue** : Displays the verbose message and then continues with execution.</span></span>
- <span data-ttu-id="7102d-465">**SilentlyContinue** : (既定) では、詳細メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="7102d-465">**SilentlyContinue** : (Default) Doesn't display the verbose message.</span></span> <span data-ttu-id="7102d-466">実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="7102d-466">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="7102d-467">例</span><span class="sxs-lookup"><span data-stu-id="7102d-467">Examples</span></span>

<span data-ttu-id="7102d-468">これらの例では、の異なる値の効果 `$VerbosePreference` と **Verbose** パラメーターを指定して、優先順位の値をオーバーライドしています。</span><span class="sxs-lookup"><span data-stu-id="7102d-468">These examples show the effect of the different values of `$VerbosePreference` and the **Verbose** parameter to override the preference value.</span></span>

<span data-ttu-id="7102d-469">この例は、既定の **SilentlyContinue** 値の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-469">This example shows the effect of the **SilentlyContinue** value, that is the default.</span></span> <span data-ttu-id="7102d-470">このコマンドでは、 **message** パラメーターを使用しますが、PowerShell コンソールにはメッセージは書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="7102d-470">The command uses the **Message** parameter, but doesn't write a message to the PowerShell console.</span></span>

```powershell
Write-Verbose -Message "Verbose message test."
```

<span data-ttu-id="7102d-471">**Verbose** パラメーターを使用すると、メッセージが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="7102d-471">When the **Verbose** parameter is used, the message is written.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="7102d-472">この例は、 **Continue** 値の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-472">This example shows the effect of the **Continue** value.</span></span> <span data-ttu-id="7102d-473">`$VerbosePreference`変数が **Continue** に設定され、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-473">The `$VerbosePreference` variable is set to **Continue** and the message is displayed.</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="7102d-474">この例では **Verbose** 、 `$false` **Continue** 値をオーバーライドするの値を持つ Verbose パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-474">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Continue** value.</span></span> <span data-ttu-id="7102d-475">メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="7102d-475">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="7102d-476">この例は、 **Stop** 値の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-476">This example shows the effect of the **Stop** value.</span></span> <span data-ttu-id="7102d-477">`$VerbosePreference`変数が **Stop** に設定され、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-477">The `$VerbosePreference` variable is set to **Stop** and the message is displayed.</span></span> <span data-ttu-id="7102d-478">コマンドは停止しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-478">The command is stopped.</span></span>

```powershell
$VerbosePreference = "Stop"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
Write-Verbose : The running command stopped because the preference variable
  "VerbosePreference" or common parameter is set to Stop: Verbose message test.
At line:1 char:1
+ Write-Verbose -Message "Verbose message test."
```

<span data-ttu-id="7102d-479">この例では **Verbose** 、 `$false` **Stop** 値をオーバーライドするの値を持つ Verbose パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-479">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Stop** value.</span></span> <span data-ttu-id="7102d-480">メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="7102d-480">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="7102d-481">この例は、 **Inquire** 値の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-481">This example shows the effect of the **Inquire** value.</span></span> <span data-ttu-id="7102d-482">`$VerbosePreference`変数は **Inquire** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="7102d-482">The `$VerbosePreference` variable is set to **Inquire**.</span></span> <span data-ttu-id="7102d-483">メッセージが表示され、ユーザーに確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-483">The message is displayed and the user is prompted for confirmation.</span></span>

```powershell
$VerbosePreference = "Inquire"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

<span data-ttu-id="7102d-484">この例では **Verbose** 、 `$false` **Inquire** 値をオーバーライドするの値を持つ Verbose パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-484">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Inquire** value.</span></span> <span data-ttu-id="7102d-485">ユーザーにプロンプトが表示されず、メッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="7102d-485">The user isn't prompted and the message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

### <a name="warningpreference"></a><span data-ttu-id="7102d-486">\$WarningPreference</span><span class="sxs-lookup"><span data-stu-id="7102d-486">\$WarningPreference</span></span>

<span data-ttu-id="7102d-487">スクリプト、コマンドレット、またはプロバイダーによって生成される警告メッセージ ( [書き込み警告](xref:Microsoft.PowerShell.Utility.Write-Warning) コマンドレットによって生成されるメッセージなど) に対して PowerShell が応答する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-487">Determines how PowerShell responds to warning messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) cmdlet.</span></span>

<span data-ttu-id="7102d-488">既定では、警告メッセージが表示され、実行が続行されますが、の値を変更することでこの動作を変更でき `$WarningPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-488">By default, warning messages are displayed and execution continues, but you can change this behavior by changing the value of `$WarningPreference`.</span></span>

<span data-ttu-id="7102d-489">コマンドレットの **Warnings action** 共通パラメーターを使用して、PowerShell が特定のコマンドからの警告に応答する方法を決定できます。</span><span class="sxs-lookup"><span data-stu-id="7102d-489">You can use the **WarningAction** common parameter of a cmdlet to determine how PowerShell responds to warnings from a particular command.</span></span> <span data-ttu-id="7102d-490">詳細については、「[about_CommonParameters](about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-490">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="7102d-491">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7102d-491">The valid values are as follows:</span></span>

- <span data-ttu-id="7102d-492">[ **停止** ]: 警告メッセージとエラーメッセージを表示し、実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="7102d-492">**Stop** : Displays the warning message and an error message and then stops executing.</span></span>
- <span data-ttu-id="7102d-493">**Inquire** : 警告メッセージを表示し、続行するためのアクセス許可を要求します。</span><span class="sxs-lookup"><span data-stu-id="7102d-493">**Inquire** : Displays the warning message and then prompts for permission to continue.</span></span>
- <span data-ttu-id="7102d-494">**続行** : (既定) 警告メッセージを表示し、実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="7102d-494">**Continue** : (Default) Displays the warning message and then continues executing.</span></span>
- <span data-ttu-id="7102d-495">**SilentlyContinue** : 警告メッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="7102d-495">**SilentlyContinue** : Doesn't display the warning message.</span></span> <span data-ttu-id="7102d-496">実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="7102d-496">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="7102d-497">例</span><span class="sxs-lookup"><span data-stu-id="7102d-497">Examples</span></span>

<span data-ttu-id="7102d-498">これらの例は、のさまざまな値の効果を示して `$WarningPreference` います。</span><span class="sxs-lookup"><span data-stu-id="7102d-498">These examples show the effect of the different values of `$WarningPreference`.</span></span>
<span data-ttu-id="7102d-499">**Warnings action** パラメーターは、基本設定値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-499">The **WarningAction** parameter overrides the preference value.</span></span>

<span data-ttu-id="7102d-500">この例は、既定値の効果を示しています。 **続行** します。</span><span class="sxs-lookup"><span data-stu-id="7102d-500">This example shows the effect of the default value, **Continue**.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
```

<span data-ttu-id="7102d-501">この例では、 **SilentlyContinue** 値を指定した **warnings action** パラメーターを使用して、警告を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="7102d-501">This example uses the **WarningAction** parameter with the value **SilentlyContinue** to suppress the warning.</span></span> <span data-ttu-id="7102d-502">メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="7102d-502">The message isn't displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="7102d-503">この例では、 `$WarningPreference` 変数を **SilentlyContinue** 値に変更します。</span><span class="sxs-lookup"><span data-stu-id="7102d-503">This example changes the `$WarningPreference` variable to the **SilentlyContinue** value.</span></span> <span data-ttu-id="7102d-504">メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="7102d-504">The message isn't displayed.</span></span>

```powershell
$WarningPreference = "SilentlyContinue"
$m = "This action can delete data."
Write-Warning -Message $m
```

<span data-ttu-id="7102d-505">この例では、警告が生成されたときに、 **Warnings action** パラメーターを使用して停止します。</span><span class="sxs-lookup"><span data-stu-id="7102d-505">This example uses the **WarningAction** parameter to stop when a warning is generated.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Stop
```

```Output
WARNING: This action can delete data.
Write-Warning : The running command stopped because the preference variable
  "WarningPreference" or common parameter is set to Stop:
    This action can delete data.
At line:1 char:1
+ Write-Warning -Message $m -WarningAction Stop
```

<span data-ttu-id="7102d-506">この例では、 `$WarningPreference` 変数を **Inquire** 値に変更します。</span><span class="sxs-lookup"><span data-stu-id="7102d-506">This example changes the `$WarningPreference` variable to the **Inquire** value.</span></span> <span data-ttu-id="7102d-507">ユーザーに確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-507">The user is prompted for confirmation.</span></span>

```powershell
$WarningPreference = "Inquire"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

<span data-ttu-id="7102d-508">この例では、 **SilentlyContinue** という値を指定して **warnings action** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-508">This example uses the **WarningAction** parameter with the value **SilentlyContinue**.</span></span> <span data-ttu-id="7102d-509">コマンドは引き続き実行され、メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="7102d-509">The command continues to execute and no message is displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="7102d-510">この例では、 `$WarningPreference` 値を **Stop** に変更します。</span><span class="sxs-lookup"><span data-stu-id="7102d-510">This example changes the `$WarningPreference` value to **Stop**.</span></span>

```powershell
$WarningPreference = "Stop"
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
Write-Warning : The running command stopped because the preference variable
  "WarningPreference" or common parameter is set to Stop:
    This action can delete data.
At line:1 char:1
+ Write-Warning -Message $m
```

<span data-ttu-id="7102d-511">この例では、 **Inquire** 値を指定して **warnings アクション** を使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-511">This example uses the **WarningAction** with the **Inquire** value.</span></span> <span data-ttu-id="7102d-512">警告が発生すると、ユーザーに対してメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-512">The user is prompted when a warning occurs.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction Inquire
```

```Output
WARNING: This action can delete data.

Confirm
Continue with this operation?
[Y] Yes  [A] Yes to All  [H] Halt Command  [?] Help (default is "Y"):
```

### <a name="whatifpreference"></a><span data-ttu-id="7102d-513">\$WhatIfPreference</span><span class="sxs-lookup"><span data-stu-id="7102d-513">\$WhatIfPreference</span></span>

<span data-ttu-id="7102d-514">サポートされているすべてのコマンドに対して **WhatIf** を自動的に有効にするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="7102d-514">Determines whether **WhatIf** is automatically enabled for every command that supports it.</span></span> <span data-ttu-id="7102d-515">**WhatIf** が有効になっている場合、コマンドレットはコマンドの予想される効果を報告しますが、コマンドを実行しません。</span><span class="sxs-lookup"><span data-stu-id="7102d-515">When **WhatIf** is enabled, the cmdlet reports the expected effect of the command, but doesn't execute the command.</span></span>

<span data-ttu-id="7102d-516">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7102d-516">The valid values are as follows:</span></span>

- <span data-ttu-id="7102d-517">**False** ( **0** 、有効でない): (既定値) **WhatIf** が自動的に有効になることはありません。</span><span class="sxs-lookup"><span data-stu-id="7102d-517">**False** ( **0** , not enabled): (Default) **WhatIf** isn't automatically enabled.</span></span> <span data-ttu-id="7102d-518">手動で有効にするには、コマンドレットの **WhatIf** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-518">To enable it manually, use the cmdlet's **WhatIf** parameter.</span></span>
- <span data-ttu-id="7102d-519">**True** ( **1** 、有効): **WhatIf** は、それをサポートするすべてのコマンドで自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="7102d-519">**True** ( **1** , enabled): **WhatIf** is automatically enabled on any command that supports it.</span></span> <span data-ttu-id="7102d-520">ユーザーは、 **WhatIf** パラメーターを値 **False** と共に使用して、などのように手動で無効にすることができ `-WhatIf:$false` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-520">Users can use the **WhatIf** parameter with a value of **False** to disable it manually, such as `-WhatIf:$false`.</span></span>

#### <a name="examples"></a><span data-ttu-id="7102d-521">例</span><span class="sxs-lookup"><span data-stu-id="7102d-521">Examples</span></span>

<span data-ttu-id="7102d-522">これらの例は、のさまざまな値の効果を示して `$WhatIfPreference` います。</span><span class="sxs-lookup"><span data-stu-id="7102d-522">These examples show the effect of the different values of `$WhatIfPreference`.</span></span>
<span data-ttu-id="7102d-523">この例では、 **WhatIf** パラメーターを使用して、特定のコマンドの設定値をオーバーライドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7102d-523">They show how to use the **WhatIf** parameter to override the preference value for a specific command.</span></span>

<span data-ttu-id="7102d-524">この例は、 `$WhatIfPreference` 変数が既定値の **False** に設定された場合の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-524">This example shows the effect of the `$WhatIfPreference` variable set to the default value, **False**.</span></span> <span data-ttu-id="7102d-525">`Get-ChildItem`ファイルが存在することを確認するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-525">Use `Get-ChildItem` to verify that the file exists.</span></span>
<span data-ttu-id="7102d-526">`Remove-Item` ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="7102d-526">`Remove-Item` deletes the file.</span></span> <span data-ttu-id="7102d-527">ファイルが削除されたら、で削除を確認でき `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-527">After the file is deleted, you can verify the deletion with `Get-ChildItem`.</span></span>

```powershell
Get-ChildItem -Path .\test.txt
Remove-Item -Path ./test.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           9/13/2019    10:53             10 test.txt
```

```powershell
Get-ChildItem -Path .\test.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -File test.txt
```

<span data-ttu-id="7102d-528">この例は、の値が False の場合に **WhatIf** パラメーターを使用した場合の効果を示して `$WhatIfPreference` います。 **False**</span><span class="sxs-lookup"><span data-stu-id="7102d-528">This example shows the effect of using the **WhatIf** parameter when the value of `$WhatIfPreference` is **False**.</span></span>

<span data-ttu-id="7102d-529">ファイルが存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7102d-529">Verify that the file exists.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="7102d-530">**WhatIf** パラメーターを使用して、ファイルを削除しようとした結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="7102d-530">Use the **WhatIf** parameter to determine the result of attempting to delete the file.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
``````

<span data-ttu-id="7102d-531">ファイルが削除されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7102d-531">Verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="7102d-532">この例では、変数の `$WhatIfPreference` 値が **True** に設定された場合の効果を示します。</span><span class="sxs-lookup"><span data-stu-id="7102d-532">This example shows the effect of the `$WhatIfPreference` variable set to the value, **True**.</span></span> <span data-ttu-id="7102d-533">を使用してファイルを削除すると、ファイル `Remove-Item` のパスが表示されますが、ファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="7102d-533">When you use `Remove-Item` to delete a file, the file's path is displayed, but the file isn't deleted.</span></span>

<span data-ttu-id="7102d-534">ファイルを削除しようとしました。</span><span class="sxs-lookup"><span data-stu-id="7102d-534">Attempt to delete a file.</span></span> <span data-ttu-id="7102d-535">が実行された場合に何が起こるかについてのメッセージが表示され `Remove-Item` ますが、ファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="7102d-535">A message is displayed about what would happen if `Remove-Item` was run, but the file isn't deleted.</span></span>

```powershell
$WhatIfPreference = "True"
Remove-Item -Path .\test2.txt
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
```

<span data-ttu-id="7102d-536">`Get-ChildItem`ファイルが削除されていないことを確認するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-536">Use `Get-ChildItem` to verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="7102d-537">この例では、の値が True の場合にファイルを削除する方法を示し `$WhatIfPreference` ます。 **True**</span><span class="sxs-lookup"><span data-stu-id="7102d-537">This example shows how to delete a file when the value of `$WhatIfPreference` is **True**.</span></span> <span data-ttu-id="7102d-538">この例では、 **WhatIf** パラメーターに値を指定 `$false` しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-538">It uses the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="7102d-539">`Get-ChildItem`ファイルが削除されたことを確認するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="7102d-539">Use `Get-ChildItem` to verify the file was deleted.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf:$false
Get-ChildItem -Path .\test2.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test2.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path .\test2.txt
```

<span data-ttu-id="7102d-540">Whatif をサポートしていない whatif をサポートしているコマンドレットの例を次に示します `Get-Process` **WhatIf** `Stop-Process` 。 **WhatIf**</span><span class="sxs-lookup"><span data-stu-id="7102d-540">The following are examples of the `Get-Process` cmdlet that doesn't support **WhatIf** and `Stop-Process` that does support **WhatIf**.</span></span> <span data-ttu-id="7102d-541">`$WhatIfPreference`変数の値は **True** です。</span><span class="sxs-lookup"><span data-stu-id="7102d-541">The `$WhatIfPreference` variable's value is **True**.</span></span>

<span data-ttu-id="7102d-542">`Get-Process`**WhatIf** はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7102d-542">`Get-Process` doesn't support **WhatIf**.</span></span> <span data-ttu-id="7102d-543">コマンドが実行されると、 **winword.exe** プロセスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7102d-543">When the command is executed, it displays the **Winword** process.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    130   119.84     173.38       8.39   15024   4 WINWORD
```

<span data-ttu-id="7102d-544">`Stop-Process` は **WhatIf** をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7102d-544">`Stop-Process` does support **WhatIf**.</span></span> <span data-ttu-id="7102d-545">**Winword.exe** プロセスは停止されていません。</span><span class="sxs-lookup"><span data-stu-id="7102d-545">The **Winword** process isn't stopped.</span></span>

```powershell
Stop-Process -Name Winword
```

```Output
What if: Performing the operation "Stop-Process" on target "WINWORD (15024)".
```

<span data-ttu-id="7102d-546">Whatif 動作をオーバーライドするには、 `Stop-Process` **WhatIf** **whatif** パラメーターに値を指定し `$false` ます。</span><span class="sxs-lookup"><span data-stu-id="7102d-546">You can override the `Stop-Process` **WhatIf** behavior by using the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="7102d-547">**Winword.exe** プロセスは停止しています。</span><span class="sxs-lookup"><span data-stu-id="7102d-547">The **Winword** process is stopped.</span></span>

```powershell
Stop-Process -Name Winword -WhatIf:$false
```

<span data-ttu-id="7102d-548">**Winword.exe** プロセスが停止したことを確認するには、を使用 `Get-Process` します。</span><span class="sxs-lookup"><span data-stu-id="7102d-548">To verify that the **Winword** process was stopped, use `Get-Process`.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
Get-Process : Cannot find a process with the name "Winword".
  Verify the process name and call the cmdlet again.
At line:1 char:1
+ Get-Process -Name Winword
```

## <a name="see-also"></a><span data-ttu-id="7102d-549">関連項目</span><span class="sxs-lookup"><span data-stu-id="7102d-549">See also</span></span>

[<span data-ttu-id="7102d-550">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="7102d-550">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="7102d-551">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="7102d-551">about_CommonParameters</span></span>](about_CommonParameters.md)

[<span data-ttu-id="7102d-552">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="7102d-552">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="7102d-553">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="7102d-553">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="7102d-554">about_Remote</span><span class="sxs-lookup"><span data-stu-id="7102d-554">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="7102d-555">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="7102d-555">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="7102d-556">about_Variables</span><span class="sxs-lookup"><span data-stu-id="7102d-556">about_Variables</span></span>](about_Variables.md)

