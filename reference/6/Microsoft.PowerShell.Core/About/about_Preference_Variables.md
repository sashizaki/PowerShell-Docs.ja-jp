---
description: PowerShell の動作をカスタマイズする変数。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 04/22/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_preference_variables?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Preference_Variables
ms.openlocfilehash: 6f23e016131901ed78b223a4d23dfa12416d970b
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221371"
---
# <a name="about-preference-variables"></a><span data-ttu-id="6b9ee-104">ユーザー設定変数について</span><span class="sxs-lookup"><span data-stu-id="6b9ee-104">About Preference Variables</span></span>

## <a name="short-description"></a><span data-ttu-id="6b9ee-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="6b9ee-105">Short description</span></span>

<span data-ttu-id="6b9ee-106">PowerShell の動作をカスタマイズする変数。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-106">Variables that customize the behavior of PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="6b9ee-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="6b9ee-107">Long description</span></span>

<span data-ttu-id="6b9ee-108">PowerShell には、その動作をカスタマイズできるようにする一連の変数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-108">PowerShell includes a set of variables that enable you to customize its behavior.</span></span> <span data-ttu-id="6b9ee-109">これらのユーザー設定変数は、GUI ベースのシステムのオプションと同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-109">These preference variables work like the options in GUI-based systems.</span></span>

<span data-ttu-id="6b9ee-110">ユーザー設定変数は PowerShell オペレーティング環境に影響し、すべてのコマンドは環境内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-110">The preference variables affect the PowerShell operating environment and all commands run in the environment.</span></span> <span data-ttu-id="6b9ee-111">多くの場合、コマンドレットには、特定のコマンドの基本設定の動作をオーバーライドするために使用できるパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-111">In many cases, the cmdlets have parameters that you can use to override the preference behavior for a specific command.</span></span>

<span data-ttu-id="6b9ee-112">次の表に、ユーザー設定変数とその既定値を示します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-112">The following table lists the preference variables and their default values.</span></span>

|             <span data-ttu-id="6b9ee-113">変数</span><span class="sxs-lookup"><span data-stu-id="6b9ee-113">Variable</span></span>             |       <span data-ttu-id="6b9ee-114">Default value</span><span class="sxs-lookup"><span data-stu-id="6b9ee-114">Default Value</span></span>       |
| -------------------------------- | ------------------------- |
| `$ConfirmPreference`             | <span data-ttu-id="6b9ee-115">高</span><span class="sxs-lookup"><span data-stu-id="6b9ee-115">High</span></span>                      |
| `$DebugPreference`               | <span data-ttu-id="6b9ee-116">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="6b9ee-116">SilentlyContinue</span></span>          |
| `$ErrorActionPreference`         | <span data-ttu-id="6b9ee-117">Continue</span><span class="sxs-lookup"><span data-stu-id="6b9ee-117">Continue</span></span>                  |
| `$ErrorView`                     | <span data-ttu-id="6b9ee-118">NormalView</span><span class="sxs-lookup"><span data-stu-id="6b9ee-118">NormalView</span></span>                |
| `$FormatEnumerationLimit`        | <span data-ttu-id="6b9ee-119">4</span><span class="sxs-lookup"><span data-stu-id="6b9ee-119">4</span></span>                         |
| `$InformationPreference`         | <span data-ttu-id="6b9ee-120">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="6b9ee-120">SilentlyContinue</span></span>          |
| `$LogCommandHealthEvent`         | <span data-ttu-id="6b9ee-121">False (ログに記録されません)</span><span class="sxs-lookup"><span data-stu-id="6b9ee-121">False (not logged)</span></span>        |
| `$LogCommandLifecycleEvent`      | <span data-ttu-id="6b9ee-122">False (ログに記録されません)</span><span class="sxs-lookup"><span data-stu-id="6b9ee-122">False (not logged)</span></span>        |
| `$LogEngineHealthEvent`          | <span data-ttu-id="6b9ee-123">True (ログ記録)</span><span class="sxs-lookup"><span data-stu-id="6b9ee-123">True (logged)</span></span>             |
| `$LogEngineLifecycleEvent`       | <span data-ttu-id="6b9ee-124">True (ログ記録)</span><span class="sxs-lookup"><span data-stu-id="6b9ee-124">True (logged)</span></span>             |
| `$LogProviderLifecycleEvent`     | <span data-ttu-id="6b9ee-125">True (ログ記録)</span><span class="sxs-lookup"><span data-stu-id="6b9ee-125">True (logged)</span></span>             |
| `$LogProviderHealthEvent`        | <span data-ttu-id="6b9ee-126">True (ログ記録)</span><span class="sxs-lookup"><span data-stu-id="6b9ee-126">True (logged)</span></span>             |
| `$MaximumHistoryCount`           | <span data-ttu-id="6b9ee-127">4096</span><span class="sxs-lookup"><span data-stu-id="6b9ee-127">4096</span></span>                      |
| `$OFS`                           | <span data-ttu-id="6b9ee-128">(スペース文字 ( `" "` ))</span><span class="sxs-lookup"><span data-stu-id="6b9ee-128">(Space character (`" "`))</span></span> |
| `$OutputEncoding`                | <span data-ttu-id="6b9ee-129">**UTF8Encoding** オブジェクト</span><span class="sxs-lookup"><span data-stu-id="6b9ee-129">**UTF8Encoding** object</span></span>   |
| `$ProgressPreference`            | <span data-ttu-id="6b9ee-130">続行</span><span class="sxs-lookup"><span data-stu-id="6b9ee-130">Continue</span></span>                  |
| `$PSDefaultParameterValues`      | <span data-ttu-id="6b9ee-131">(なし-空のハッシュテーブル)</span><span class="sxs-lookup"><span data-stu-id="6b9ee-131">(None - empty hash table)</span></span> |
| `$PSEmailServer`                 | <span data-ttu-id="6b9ee-132">(なし)</span><span class="sxs-lookup"><span data-stu-id="6b9ee-132">(None)</span></span>                    |
| `$PSModuleAutoLoadingPreference` | <span data-ttu-id="6b9ee-133">All</span><span class="sxs-lookup"><span data-stu-id="6b9ee-133">All</span></span>                       |
| `$PSSessionApplicationName`      | <span data-ttu-id="6b9ee-134">wsman</span><span class="sxs-lookup"><span data-stu-id="6b9ee-134">wsman</span></span>                     |
| `$PSSessionConfigurationName`    | `http://schemas.microsoft.com/powershell/Microsoft.PowerShell` |
| `$PSSessionOption`               | <span data-ttu-id="6b9ee-135">「」を参照してください [$PSSessionOption](#pssessionoption)</span><span class="sxs-lookup"><span data-stu-id="6b9ee-135">See [$PSSessionOption](#pssessionoption)</span></span> |
| `$Transcript`                    | <span data-ttu-id="6b9ee-136">(なし)</span><span class="sxs-lookup"><span data-stu-id="6b9ee-136">(none)</span></span>                    |
| `$VerbosePreference`             | <span data-ttu-id="6b9ee-137">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="6b9ee-137">SilentlyContinue</span></span>          |
| `$WarningPreference`             | <span data-ttu-id="6b9ee-138">Continue</span><span class="sxs-lookup"><span data-stu-id="6b9ee-138">Continue</span></span>                  |
| `$WhatIfPreference`              | <span data-ttu-id="6b9ee-139">False</span><span class="sxs-lookup"><span data-stu-id="6b9ee-139">False</span></span>                     |

<span data-ttu-id="6b9ee-140">PowerShell には、ユーザー設定を格納する次の環境変数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-140">PowerShell includes the following environment variables that store user preferences.</span></span> <span data-ttu-id="6b9ee-141">これらの環境変数の詳細については、「 [about_Environment_Variables](about_Environment_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-141">For more information about these environment variables, see [about_Environment_Variables](about_Environment_Variables.md).</span></span>

- `env:PSExecutionPolicyPreference`
- `$env:PSModulePath`

> [!NOTE]
> <span data-ttu-id="6b9ee-142">優先変数に加えた変更は、これらのスクリプトまたは関数が、preference が使用されたスコープと同じスコープで定義されている場合にのみ、スクリプトと関数で有効になります。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-142">Changes to preference variable only take effect in scripts and functions if those scripts or functions are defined in the same scope as the scope in which preference was used.</span></span> <span data-ttu-id="6b9ee-143">詳細については、「 [about_Scopes](about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-143">For more information, see [about_Scopes](about_Scopes.md).</span></span>

## <a name="working-with-preference-variables"></a><span data-ttu-id="6b9ee-144">ユーザー設定変数の使用</span><span class="sxs-lookup"><span data-stu-id="6b9ee-144">Working with preference variables</span></span>

<span data-ttu-id="6b9ee-145">このドキュメントでは、各ユーザー設定変数について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-145">This document describes each of the preference variables.</span></span>

<span data-ttu-id="6b9ee-146">特定のユーザー設定変数の現在の値を表示するには、変数の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-146">To display the current value of a specific preference variable, type the variable's name.</span></span> <span data-ttu-id="6b9ee-147">たとえば、次のコマンドは、 `$ConfirmPreference` 変数の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-147">For example, the following command displays the `$ConfirmPreference` variable's value.</span></span>

```powershell
 $ConfirmPreference
```

```Output
High
```

<span data-ttu-id="6b9ee-148">変数の値を変更するには、代入ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-148">To change a variable's value, use an assignment statement.</span></span> <span data-ttu-id="6b9ee-149">たとえば、次のステートメントでは、 `$ConfirmPreference` パラメーターの値が **Medium** に変更されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-149">For example, the following statement changes the `$ConfirmPreference` parameter's value to **Medium**.</span></span>

```powershell
$ConfirmPreference = "Medium"
```

<span data-ttu-id="6b9ee-150">設定する値は、現在の PowerShell セッションに固有です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-150">The values that you set are specific to the current PowerShell session.</span></span> <span data-ttu-id="6b9ee-151">すべての PowerShell セッションで変数を有効にするには、PowerShell プロファイルに変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-151">To make variables effective in all PowerShell sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="6b9ee-152">詳細については、「 [about_Profiles](about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-152">For more information, see [about_Profiles](about_Profiles.md).</span></span>

## <a name="working-remotely"></a><span data-ttu-id="6b9ee-153">リモートでの作業</span><span class="sxs-lookup"><span data-stu-id="6b9ee-153">Working remotely</span></span>

<span data-ttu-id="6b9ee-154">リモートコンピューターでコマンドを実行する場合、リモートコマンドは、リモートコンピューターの PowerShell クライアントで設定された設定の対象になります。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-154">When you run commands on a remote computer, the remote commands are only subject to the preferences set in the remote computer's PowerShell client.</span></span> <span data-ttu-id="6b9ee-155">たとえば、リモートコマンドを実行すると、リモートコンピューターの変数の値によって、 `$DebugPreference` PowerShell がデバッグメッセージに応答する方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-155">For example, when you run a remote command, the value of the remote computer's `$DebugPreference` variable determines how PowerShell responds to debugging messages.</span></span>

<span data-ttu-id="6b9ee-156">リモートコマンドの詳細については、「 [about_Remote](about_Remote.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-156">For more information about remote commands, see [about_Remote](about_Remote.md).</span></span>

### <a name="confirmpreference"></a><span data-ttu-id="6b9ee-157">\$ConfirmPreference</span><span class="sxs-lookup"><span data-stu-id="6b9ee-157">\$ConfirmPreference</span></span>

<span data-ttu-id="6b9ee-158">コマンドレットまたは関数を実行する前に、PowerShell によって確認メッセージが自動的に表示されるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-158">Determines whether PowerShell automatically prompts you for confirmation before running a cmdlet or function.</span></span>

<span data-ttu-id="6b9ee-159">`$ConfirmPreference`変数の有効な値は、 **High** 、 **Medium** 、または **Low** です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-159">The `$ConfirmPreference` variable's valid values are **High** , **Medium** , or **Low**.</span></span> <span data-ttu-id="6b9ee-160">コマンドレットと関数には、 **高** 、 **中** 、 **低** のリスクが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-160">Cmdlets and functions are assigned a risk of **High** , **Medium** , or **Low**.</span></span> <span data-ttu-id="6b9ee-161">変数の値 `$ConfirmPreference` がコマンドレットまたは関数に割り当てられたリスク以下である場合、PowerShell はコマンドレットまたは関数を実行する前に自動的に確認を求めます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-161">When the value of the `$ConfirmPreference` variable is less than or equal to the risk assigned to a cmdlet or function, PowerShell automatically prompts you for confirmation before running the cmdlet or function.</span></span>

<span data-ttu-id="6b9ee-162">変数の値 `$ConfirmPreference` が **None** の場合は、コマンドレットまたは関数を実行する前に、PowerShell によって自動的にプロンプトが表示されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-162">If the value of the `$ConfirmPreference` variable is **None** , PowerShell never automatically prompts you before running a cmdlet or function.</span></span>

<span data-ttu-id="6b9ee-163">セッション内のすべてのコマンドレットと関数の確認動作を変更するには、 `$ConfirmPreference` 変数の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-163">To change the confirming behavior for all cmdlets and functions in the session, change `$ConfirmPreference` variable's value.</span></span>

<span data-ttu-id="6b9ee-164">`$ConfirmPreference`1 つのコマンドのをオーバーライドするには、コマンドレットまたは関数の **Confirm** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-164">To override the `$ConfirmPreference` for a single command, use a cmdlet's or function's **Confirm** parameter.</span></span> <span data-ttu-id="6b9ee-165">確認を要求するには、を使用 `-Confirm` します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-165">To request confirmation, use `-Confirm`.</span></span> <span data-ttu-id="6b9ee-166">確認を抑制するには、を使用 `-Confirm:$false` します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-166">To suppress confirmation, use `-Confirm:$false`.</span></span>

<span data-ttu-id="6b9ee-167">有効な値 `$ConfirmPreference` :</span><span class="sxs-lookup"><span data-stu-id="6b9ee-167">Valid values of `$ConfirmPreference`:</span></span>

- <span data-ttu-id="6b9ee-168">**なし** : PowerShell は自動的にプロンプトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-168">**None** : PowerShell doesn't prompt automatically.</span></span> <span data-ttu-id="6b9ee-169">特定のコマンドの確認を要求するには、コマンドレットまたは関数の **Confirm** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-169">To request confirmation of a particular command, use the **Confirm** parameter of the cmdlet or function.</span></span>
- <span data-ttu-id="6b9ee-170">[ **低** ]: PowerShell で、低、中、または高リスクのコマンドレットまたは関数を実行する前に、確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-170">**Low** : PowerShell prompts for confirmation before running cmdlets or functions with a low, medium, or high risk.</span></span>
- <span data-ttu-id="6b9ee-171">[ **中** ]: PowerShell でコマンドレットまたは関数を実行する前に、中程度のリスクがあるかどうかを確認するプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-171">**Medium** : PowerShell prompts for confirmation before running cmdlets or functions with a medium, or high risk.</span></span>
- <span data-ttu-id="6b9ee-172">**High** : コマンドレットまたは関数を高いリスクで実行する前に、PowerShell に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-172">**High** : PowerShell prompts for confirmation before running cmdlets or functions with a high risk.</span></span>

#### <a name="detailed-explanation"></a><span data-ttu-id="6b9ee-173">詳細な説明</span><span class="sxs-lookup"><span data-stu-id="6b9ee-173">Detailed explanation</span></span>

<span data-ttu-id="6b9ee-174">PowerShell では、アクションを実行する前に自動的に確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-174">PowerShell can automatically prompt you for confirmation before doing an action.</span></span> <span data-ttu-id="6b9ee-175">たとえば、コマンドレットまたは関数がシステムに大きな影響を及ぼしてデータを削除したり、大量のシステムリソースを使用したりした場合などです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-175">For example, when cmdlet or function significantly affects the system to delete data or use a significant amount of system resources.</span></span>

```powershell
Remove-Item -Path C:\file.txt
```

```Output
Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target "C:\file.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"):
```

<span data-ttu-id="6b9ee-176">リスクの推定値は、コマンドレットまたは **Confirmimpact** と呼ばれる関数の属性です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-176">The estimate of the risk is an attribute of the cmdlet or function known as its **ConfirmImpact**.</span></span> <span data-ttu-id="6b9ee-177">ユーザーはそれを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-177">Users can't change it.</span></span>

<span data-ttu-id="6b9ee-178">システムへのリスクが生じる可能性のあるコマンドレットと関数には、1つのコマンドの確認を要求または抑制するために使用できる **Confirm** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-178">Cmdlets and functions that might pose a risk to the system have a **Confirm** parameter that you can use to request or suppress confirmation for a single command.</span></span>

<span data-ttu-id="6b9ee-179">ほとんどのコマンドレットと関数は、既定のリスク値である **Confirmimpact** を使用し、は **Medium** で、既定値 `$ConfirmPreference` は **high** であるため、自動確認はほとんど発生しません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-179">Because most cmdlets and functions use the default risk value, **ConfirmImpact** , of **Medium** , and the default value of `$ConfirmPreference` is **High** , automatic confirmation rarely occurs.</span></span> <span data-ttu-id="6b9ee-180">ただし、の値を [中] または [低] に変更すると、自動確認を有効にすることができ `$ConfirmPreference` ます。 **Medium** **Low**</span><span class="sxs-lookup"><span data-stu-id="6b9ee-180">However, you can activate automatic confirmation by changing the value of `$ConfirmPreference` to **Medium** or **Low**.</span></span>

#### <a name="examples"></a><span data-ttu-id="6b9ee-181">例</span><span class="sxs-lookup"><span data-stu-id="6b9ee-181">Examples</span></span>

<span data-ttu-id="6b9ee-182">この例は、 `$ConfirmPreference` 変数の既定値 **High** の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-182">This example shows the effect of the `$ConfirmPreference` variable's default value, **High**.</span></span> <span data-ttu-id="6b9ee-183">**高い** 値は、危険度の高いコマンドレットと関数を確認するだけです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-183">The **High** value only confirms high-risk cmdlets and functions.</span></span> <span data-ttu-id="6b9ee-184">ほとんどのコマンドレットと関数は、危険度が中程度であるため、自動的に確認されず `Remove-Item` 、ファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-184">Since most cmdlets and functions are medium risk, they aren't automatically confirmed and `Remove-Item` deletes the file.</span></span> <span data-ttu-id="6b9ee-185">`-Confirm`コマンドにを追加すると、ユーザーに確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-185">Adding `-Confirm` to the command prompts the user for confirmation.</span></span>

```powershell
$ConfirmPreference
```

```Output
High
```

```powershell
Remove-Item -Path C:\temp1.txt
```

<span data-ttu-id="6b9ee-186">`-Confirm`確認を要求するために使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-186">Use `-Confirm` to request confirmation.</span></span>

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

<span data-ttu-id="6b9ee-187">次の例は、の値を Medium に変更した場合の効果を示して `$ConfirmPreference` います。 **Medium**</span><span class="sxs-lookup"><span data-stu-id="6b9ee-187">The following example shows the effect of changing the value of `$ConfirmPreference` to **Medium**.</span></span> <span data-ttu-id="6b9ee-188">ほとんどのコマンドレットと関数は中程度のリスクであるため、自動的に確認されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-188">Because most cmdlets and function are medium risk, they're automatically confirmed.</span></span> <span data-ttu-id="6b9ee-189">1つのコマンドに対して確認プロンプトを表示しないようにするには、値がで **Confirm** パラメーターを使用し `$false` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-189">To suppress the confirmation prompt for a single command, use the **Confirm** parameter with a value of `$false`.</span></span>

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

### <a name="debugpreference"></a><span data-ttu-id="6b9ee-190">\$DebugPreference</span><span class="sxs-lookup"><span data-stu-id="6b9ee-190">\$DebugPreference</span></span>

<span data-ttu-id="6b9ee-191">スクリプト、コマンドレット、またはプロバイダーによって生成されたデバッグメッセージ、またはコマンドラインでコマンドを実行して、PowerShell がどのように応答するかを指定し `Write-Debug` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-191">Determines how PowerShell responds to debugging messages generated by a script, cmdlet or provider, or by a `Write-Debug` command at the command line.</span></span>

<span data-ttu-id="6b9ee-192">一部のコマンドレットでは、デバッグメッセージが表示されます。これは通常、プログラマやテクニカルサポートプロフェッショナル向けに設計されたテクニカルメッセージです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-192">Some cmdlets display debugging messages, which are typically technical messages designed for programmers and technical support professionals.</span></span> <span data-ttu-id="6b9ee-193">既定では、デバッグメッセージは表示されませんが、の値を変更することで、デバッグメッセージを表示でき `$DebugPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-193">By default, debugging messages aren't displayed, but you can display debugging messages by changing the value of `$DebugPreference`.</span></span>

<span data-ttu-id="6b9ee-194">コマンドレットの **Debug** 共通パラメーターを使用して、特定のコマンドのデバッグメッセージを表示または非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-194">You can use the **Debug** common parameter of a cmdlet to display or hide the debugging messages for a specific command.</span></span> <span data-ttu-id="6b9ee-195">詳細については、「[about_CommonParameters](about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-195">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="6b9ee-196">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-196">The valid values are as follows:</span></span>

- <span data-ttu-id="6b9ee-197">[ **停止** ]: デバッグメッセージを表示し、実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-197">**Stop** : Displays the debug message and stops executing.</span></span> <span data-ttu-id="6b9ee-198">コンソールにエラーを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-198">Writes an error to the console.</span></span>
- <span data-ttu-id="6b9ee-199">**Inquire** : デバッグメッセージを表示し、続行するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-199">**Inquire** : Displays the debug message and asks you whether you want to continue.</span></span> <span data-ttu-id="6b9ee-200">**デバッグ** 共通パラメーターをコマンドに追加すると、コマンドがデバッグメッセージを生成するように構成されている場合に、 `$DebugPreference` **Inquire** に対して変数の値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-200">Adding the **Debug** common parameter to a command, when the command is configured to generate a debugging message, changes the value of the `$DebugPreference` variable to **Inquire**.</span></span>
- <span data-ttu-id="6b9ee-201">**Continue** : デバッグメッセージを表示し、実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-201">**Continue** : Displays the debug message and continues with execution.</span></span>
- <span data-ttu-id="6b9ee-202">**SilentlyContinue** : (既定) 効果はありません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-202">**SilentlyContinue** : (Default) No effect.</span></span> <span data-ttu-id="6b9ee-203">デバッグメッセージは表示されず、実行は中断されることなく続行されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-203">The debug message isn't displayed and execution continues without interruption.</span></span>

#### <a name="examples"></a><span data-ttu-id="6b9ee-204">例</span><span class="sxs-lookup"><span data-stu-id="6b9ee-204">Examples</span></span>

<span data-ttu-id="6b9ee-205">次の例は、コマンド `$DebugPreference` `Write-Debug` がコマンドラインで入力されたときのの値を変更した場合の影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-205">The following examples show the effect of changing the values of `$DebugPreference` when a `Write-Debug` command is entered at the command line.</span></span>
<span data-ttu-id="6b9ee-206">この変更は、コマンドレットおよびスクリプトによって生成されるメッセージを含む、すべてのデバッグメッセージに影響します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-206">The change affects all debugging messages, including messages generated by cmdlets and scripts.</span></span> <span data-ttu-id="6b9ee-207">この例は、1つのコマンドに関連するデバッグメッセージを表示または非表示にする **Debug** パラメーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-207">The examples show the **Debug** parameter, which displays or hides the debugging messages related to a single command.</span></span>

<span data-ttu-id="6b9ee-208">この例は、 `$DebugPreference` 変数の既定値 **SilentlyContinue** の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-208">This example shows the effect of the `$DebugPreference` variable's default value, **SilentlyContinue**.</span></span> <span data-ttu-id="6b9ee-209">既定では、 `Write-Debug` コマンドレットのデバッグメッセージは表示されず、処理は続行されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-209">By default, the `Write-Debug` cmdlet's debug message isn't displayed and processing continues.</span></span> <span data-ttu-id="6b9ee-210">**Debug** パラメーターを使用すると、1つのコマンドの設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-210">When the **Debug** parameter is used, it overrides the preference for a single command.</span></span> <span data-ttu-id="6b9ee-211">デバッグメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-211">The debug message is displayed.</span></span>

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

<span data-ttu-id="6b9ee-212">この例では、 `$DebugPreference` **Continue** 値を使用した場合のの効果を示します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-212">This example shows the effect of `$DebugPreference` with the **Continue** value.</span></span> <span data-ttu-id="6b9ee-213">デバッグメッセージが表示され、コマンドが処理を続行します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-213">The debug message is displayed and the command continues to process.</span></span>

```powershell
$DebugPreference = "Continue"
Write-Debug -Message "Hello, World"
```

```Output
DEBUG: Hello, World
```

<span data-ttu-id="6b9ee-214">この例では、 **Debug** パラメーターを値と共に使用して、 `$false` 1 つのコマンドのメッセージを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-214">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="6b9ee-215">デバッグメッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-215">The debug message isn't displayed.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="6b9ee-216">この例は、が `$DebugPreference` **停止** 値に設定された場合の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-216">This example shows the effect of `$DebugPreference` being set to the **Stop** value.</span></span> <span data-ttu-id="6b9ee-217">デバッグメッセージが表示され、コマンドが停止します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-217">The debug message is displayed and the command is stopped.</span></span>

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

<span data-ttu-id="6b9ee-218">この例では、 **Debug** パラメーターを値と共に使用して、 `$false` 1 つのコマンドのメッセージを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-218">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="6b9ee-219">デバッグメッセージは表示されず、処理は停止されません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-219">The debug message isn't displayed and processing isn't stopped.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

<span data-ttu-id="6b9ee-220">この例は、 `$DebugPreference` **Inquire** 値に設定された効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-220">This example shows the effect of `$DebugPreference` being set to the **Inquire** value.</span></span> <span data-ttu-id="6b9ee-221">デバッグメッセージが表示され、ユーザーに確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-221">The debug message is displayed and the user is prompted for confirmation.</span></span>

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

<span data-ttu-id="6b9ee-222">この例では、 **Debug** パラメーターを値と共に使用して、 `$false` 1 つのコマンドのメッセージを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-222">This example uses the **Debug** parameter with a value of `$false` to suppress the message for a single command.</span></span> <span data-ttu-id="6b9ee-223">デバッグメッセージが表示されず、処理が続行されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-223">The debug message isn't displayed and processing continues.</span></span>

```powershell
Write-Debug -Message "Hello, World" -Debug:$false
```

### <a name="erroractionpreference"></a><span data-ttu-id="6b9ee-224">\$ErrorActionPreference</span><span class="sxs-lookup"><span data-stu-id="6b9ee-224">\$ErrorActionPreference</span></span>

<span data-ttu-id="6b9ee-225">PowerShell が終了しないエラーに応答する方法を決定します。このエラーは、コマンドレットの処理を停止しません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-225">Determines how PowerShell responds to a non-terminating error, an error that doesn't stop the cmdlet processing.</span></span> <span data-ttu-id="6b9ee-226">たとえば、コマンドライン、スクリプト、コマンドレット、またはプロバイダー (コマンドレットによって生成されたエラーなど) `Write-Error` です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-226">For example, at the command line or in a script, cmdlet, or provider, such as the errors generated by the `Write-Error` cmdlet.</span></span>

<span data-ttu-id="6b9ee-227">コマンドレットの **Erroraction** 共通パラメーターを使用して、特定のコマンドの設定をオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-227">You can use a cmdlet's **ErrorAction** common parameter to override the preference for a specific command.</span></span>

<span data-ttu-id="6b9ee-228">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-228">The valid values are as follows:</span></span>

- <span data-ttu-id="6b9ee-229">**続行** : (既定) エラーメッセージを表示し、実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-229">**Continue** : (Default) Displays the error message and continues executing.</span></span>
- <span data-ttu-id="6b9ee-230">**Ignore** : エラーメッセージを表示せず、コマンドの実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-230">**Ignore** : Suppresses the error message and continues to execute the command.</span></span> <span data-ttu-id="6b9ee-231">**Ignore** 値は、保存された設定として使用するのではなく、コマンドごとの使用を目的としています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-231">The **Ignore** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="6b9ee-232">**Ignore** は、変数の有効な値ではありません `$ErrorActionPreference` 。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-232">**Ignore** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>
- <span data-ttu-id="6b9ee-233">**Inquire** : エラーメッセージを表示し、続行するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-233">**Inquire** : Displays the error message and asks you whether you want to continue.</span></span>
- <span data-ttu-id="6b9ee-234">**SilentlyContinue** : 何の効果もありません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-234">**SilentlyContinue** : No effect.</span></span> <span data-ttu-id="6b9ee-235">エラーメッセージは表示されず、実行は中断されることなく続行されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-235">The error message isn't displayed and execution continues without interruption.</span></span>
- <span data-ttu-id="6b9ee-236">[ **停止** ]: エラーメッセージを表示し、実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-236">**Stop** : Displays the error message and stops executing.</span></span> <span data-ttu-id="6b9ee-237">**Stop** 値は、生成されたエラーに加えて、エラーストリームに ActionPreferenceStopException オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-237">In addition to the error generated, the **Stop** value generates an ActionPreferenceStopException object to the error stream.</span></span>
  <span data-ttu-id="6b9ee-238">ストリーム (stream)</span><span class="sxs-lookup"><span data-stu-id="6b9ee-238">stream</span></span>
- <span data-ttu-id="6b9ee-239">**中断** : ワークフロージョブを自動的に中断し、さらに調査できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-239">**Suspend** : Automatically suspends a workflow job to allow for further investigation.</span></span> <span data-ttu-id="6b9ee-240">調査後、ワークフローを再開できます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-240">After investigation, the workflow can be resumed.</span></span> <span data-ttu-id="6b9ee-241">**Suspend** の値は、保存された設定としてではなく、コマンドごとの使用を目的としています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-241">The **Suspend** value is intended for per-command use, not for use as saved preference.</span></span> <span data-ttu-id="6b9ee-242">**中断** は、変数の有効な値ではありません `$ErrorActionPreference` 。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-242">**Suspend** isn't a valid value for the `$ErrorActionPreference` variable.</span></span>

<span data-ttu-id="6b9ee-243">`$ErrorActionPreference`**Erroraction** パラメーターは、コマンドレットの処理を停止するエラーを終了するために PowerShell がどのように応答するかに影響しません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-243">`$ErrorActionPreference` and the **ErrorAction** parameter don't affect how PowerShell responds to terminating errors that stop cmdlet processing.</span></span> <span data-ttu-id="6b9ee-244">**Erroraction** 共通パラメーターの詳細については、「 [about_CommonParameters](about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-244">For more information about the **ErrorAction** common parameter, see [about_CommonParameters](about_CommonParameters.md).</span></span>

#### <a name="examples"></a><span data-ttu-id="6b9ee-245">例</span><span class="sxs-lookup"><span data-stu-id="6b9ee-245">Examples</span></span>

<span data-ttu-id="6b9ee-246">これらの例は、変数の異なる値の効果を示して `$ErrorActionPreference` います。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-246">These examples show the effect of the different values of the `$ErrorActionPreference` variable.</span></span> <span data-ttu-id="6b9ee-247">**Erroraction** パラメーターは、値をオーバーライドするために使用され `$ErrorActionPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-247">The **ErrorAction** parameter is used to override the `$ErrorActionPreference` value.</span></span>

<span data-ttu-id="6b9ee-248">この例では、 `$ErrorActionPreference` 既定値の [ **続行** ] を示します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-248">This example shows the `$ErrorActionPreference` default value, **Continue**.</span></span> <span data-ttu-id="6b9ee-249">終了しないエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-249">A non-terminating error is generated.</span></span> <span data-ttu-id="6b9ee-250">メッセージが表示され、処理が続行されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-250">The message is displayed and processing continues.</span></span>

```powershell
# Change the ErrorActionPreference to 'Continue'
$ErrorActionPreference = 'Continue'
# Generate a non-terminating error and continue processing the script.
Write-Error -Message  'Test Error' ; Write-Host 'Hello World'
```

```Output
Write-Error -Message  'Test Error' ; Write-Host 'Hello World' : Test Error
    + CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
    + FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException

Hello World
```

<span data-ttu-id="6b9ee-251">この例は、 `$ErrorActionPreference` 既定値の **Inquire** を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-251">This example shows the `$ErrorActionPreference` default value, **Inquire**.</span></span> <span data-ttu-id="6b9ee-252">エラーが生成され、アクションのプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-252">An error is generated and a prompt for action is shown.</span></span>

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

<span data-ttu-id="6b9ee-253">この例では、 `$ErrorActionPreference` を **SilentlyContinue** に設定しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-253">This example shows the `$ErrorActionPreference` set to **SilentlyContinue**.</span></span>
<span data-ttu-id="6b9ee-254">エラーメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-254">The error message is suppressed.</span></span>

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

<span data-ttu-id="6b9ee-255">`$ErrorActionPreference`**停止** するように設定する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-255">This example shows the `$ErrorActionPreference` set to **Stop**.</span></span> <span data-ttu-id="6b9ee-256">また、変数に対して生成された追加のオブジェクトも表示され `$Error` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-256">It also shows the extra object generated to the `$Error` variable.</span></span>

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
Write-Error -Message 'Test Error' ; Write-Host 'Hello World' : Test Error
At line:1 char:1
+ Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
    + FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException

The running command stopped because the preference variable "ErrorActionPreference"
or common parameter is set to Stop: Test Error

Write-Error -Message 'Test Error' ; Write-Host 'Hello World' : Test Error
At line:1 char:1
+ Write-Error -Message 'Test Error' ; Write-Host 'Hello World'
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [Write-Error], WriteErrorException
    + FullyQualifiedErrorId : Microsoft.PowerShell.Commands.WriteErrorException
```

### <a name="errorview"></a><span data-ttu-id="6b9ee-257">\$ErrorView</span><span class="sxs-lookup"><span data-stu-id="6b9ee-257">\$ErrorView</span></span>

<span data-ttu-id="6b9ee-258">PowerShell でのエラーメッセージの表示形式を決定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-258">Determines the display format of error messages in PowerShell.</span></span>

<span data-ttu-id="6b9ee-259">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-259">The valid values are as follows:</span></span>

- <span data-ttu-id="6b9ee-260">**Normalview** : (既定) ほとんどのユーザー向けに設計された詳細ビュー。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-260">**NormalView** : (Default) A detailed view designed for most users.</span></span> <span data-ttu-id="6b9ee-261">エラーの説明とエラーに関係するオブジェクトの名前で構成されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-261">Consists of a description of the error and the name of the object involved in the error.</span></span>
- <span data-ttu-id="6b9ee-262">**カテゴリビュー** : 運用環境向けに設計された簡潔で構造化されたビューです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-262">**CategoryView** : A succinct, structured view designed for production environments.</span></span> <span data-ttu-id="6b9ee-263">その形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-263">The format is as follows:</span></span>

  <span data-ttu-id="6b9ee-264">{Category}: ({TargetName}: {TargetType}): [{Activity}], {Reason}</span><span class="sxs-lookup"><span data-stu-id="6b9ee-264">{Category}: ({TargetName}:{TargetType}):[{Activity}], {Reason}</span></span>

<span data-ttu-id="6b9ee-265">**カテゴリビュー** のフィールドの詳細については、「 [errorのカテゴリ情報](/dotnet/api/system.management.automation.errorcategoryinfo)クラス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-265">For more information about the fields in **CategoryView** , see [ErrorCategoryInfo](/dotnet/api/system.management.automation.errorcategoryinfo) class.</span></span>

#### <a name="examples"></a><span data-ttu-id="6b9ee-266">例</span><span class="sxs-lookup"><span data-stu-id="6b9ee-266">Examples</span></span>

<span data-ttu-id="6b9ee-267">この例は、の値 `$ErrorView` が既定の **normalview** である場合にエラーがどのように表示されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-267">This example shows how an error appears when the value of `$ErrorView` is the default, **NormalView**.</span></span> <span data-ttu-id="6b9ee-268">`Get-ChildItem` は、存在しないファイルを検索するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-268">`Get-ChildItem` is used to find a non-existent file.</span></span>

```powershell
Get-ChildItem -Path C:\nofile.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\nofile.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path C:\nofile.txt
```

<span data-ttu-id="6b9ee-269">この例は、の値 `$ErrorView` が **カテゴリビュー** に変更された場合に、同じエラーがどのように表示されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-269">This example shows how the same error appears when the value of `$ErrorView` is changed to **CategoryView**.</span></span>

```powershell
$ErrorView = "CategoryView"
Get-ChildItem -Path C:\nofile.txt
```

```Output
ObjectNotFound: (C:\nofile.txt:String) [Get-ChildItem], ItemNotFoundException
```

<span data-ttu-id="6b9ee-270">この例では、の値が `$ErrorView` エラー表示にのみ影響することを示しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-270">This example demonstrates that the value of `$ErrorView` only affects the error display.</span></span> <span data-ttu-id="6b9ee-271">自動変数に格納されているエラーオブジェクトの構造は変更されません `$Error` 。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-271">It doesn't change the structure of the error object that is stored in the `$Error` automatic variable.</span></span> <span data-ttu-id="6b9ee-272">自動変数の詳細については `$Error` 、「 [about_automatic_variables](about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-272">For information about the `$Error` automatic variable, see [about_automatic_variables](about_Automatic_Variables.md).</span></span>

<span data-ttu-id="6b9ee-273">次のコマンドは、エラー配列内の最新のエラーに関連付けられた **Errorrecord** オブジェクトを取得し、 **要素 0** を使用して、リスト内のすべてのエラーオブジェクトのプロパティを書式設定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-273">The following command takes the **ErrorRecord** object associated with the most recent error in the error array, **element 0** , and formats all the error object's properties in a list.</span></span>

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

### <a name="formatenumerationlimit"></a><span data-ttu-id="6b9ee-274">\$FormatEnumerationLimit</span><span class="sxs-lookup"><span data-stu-id="6b9ee-274">\$FormatEnumerationLimit</span></span>

<span data-ttu-id="6b9ee-275">表示に含める列挙された項目の数を決定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-275">Determines how many enumerated items are included in a display.</span></span> <span data-ttu-id="6b9ee-276">この変数は、基になるオブジェクトには影響しません。表示のみです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-276">This variable doesn't affect the underlying objects, only the display.</span></span> <span data-ttu-id="6b9ee-277">の値 `$FormatEnumerationLimit` が列挙された項目の数よりも小さい場合は、 `...` 表示されていない項目を示す省略記号 () が PowerShell によって追加されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-277">When the value of `$FormatEnumerationLimit` is fewer than the number of enumerated items, PowerShell adds an ellipsis (`...`) to indicate items not shown.</span></span>

<span data-ttu-id="6b9ee-278">**有効な値** : 整数 ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="6b9ee-278">**Valid values** : Integers (`Int32`)</span></span>

<span data-ttu-id="6b9ee-279">**既定値** : 4</span><span class="sxs-lookup"><span data-stu-id="6b9ee-279">**Default value** : 4</span></span>

#### <a name="examples"></a><span data-ttu-id="6b9ee-280">例</span><span class="sxs-lookup"><span data-stu-id="6b9ee-280">Examples</span></span>

<span data-ttu-id="6b9ee-281">この例では、変数を使用して、列挙され `$FormatEnumerationLimit` た項目の表示を改善する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-281">This example shows how to use the `$FormatEnumerationLimit` variable to improve the display of enumerated items.</span></span>

<span data-ttu-id="6b9ee-282">この例のコマンドは、コンピューター上で実行されているすべてのサービスを一覧表示するテーブルを生成します。1つはサービスの **実行** 用で、もう1つは **停止** したサービス用です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-282">The command in this example generates a table that lists all the services running on the computer in two groups: one for **running** services and one for **stopped** services.</span></span> <span data-ttu-id="6b9ee-283">コマンドを使用して `Get-Service` すべてのサービスを取得し、パイプラインを介して結果をコマンドレットに送信し `Group-Object` ます。これにより、結果がサービスの状態別にグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-283">It uses a `Get-Service` command to get all the services, and then sends the results through the pipeline to the `Group-Object` cmdlet, which groups the results by the service status.</span></span>

<span data-ttu-id="6b9ee-284">その結果、[ **名前** ] 列の状態と [ **グループ]** 列のプロセスが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-284">The result is a table that lists the status in the **Name** column, and the processes in the **Group** column.</span></span> <span data-ttu-id="6b9ee-285">列ラベルを変更するには、「 [about_Hash_Tables](about_Hash_Tables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-285">To change the column labels, use a hash table, see [about_Hash_Tables](about_Hash_Tables.md).</span></span> <span data-ttu-id="6b9ee-286">詳細については、「 [形式テーブル](xref:Microsoft.PowerShell.Utility.Format-Table)」の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-286">For more information, see the examples in [Format-Table](xref:Microsoft.PowerShell.Utility.Format-Table).</span></span>

<span data-ttu-id="6b9ee-287">の現在の値を検索 `$FormatEnumerationLimit` します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-287">Find the current value of `$FormatEnumerationLimit`.</span></span>

```powershell
$FormatEnumerationLimit
```

```Output
4
```

<span data-ttu-id="6b9ee-288">**状態** 別にグループ化されたすべてのサービスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-288">List all services grouped by **Status**.</span></span> <span data-ttu-id="6b9ee-289">各状態の [ **グループ]** 列には、の値が4であるため、最大4つのサービスが表示され `$FormatEnumerationLimit` ます。 **4**</span><span class="sxs-lookup"><span data-stu-id="6b9ee-289">There are a maximum of four services listed in the **Group** column for each status because `$FormatEnumerationLimit` has a value of **4**.</span></span>

```powershell
Get-Service | Group-Object -Property Status
```

```Output
Count  Name       Group
-----  ----       -----
60     Running    {AdtAgent, ALG, Ati HotKey Poller, AudioSrv...}
41     Stopped    {Alerter, AppMgmt, aspnet_state, ATI Smart...}
```

<span data-ttu-id="6b9ee-290">表示される項目の数を増やすには、の値を `$FormatEnumerationLimit` **1000** に増やします。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-290">To increase the number of items listed, increase the value of `$FormatEnumerationLimit` to **1000**.</span></span> <span data-ttu-id="6b9ee-291">`Get-Service` `Group-Object` サービスを表示するには、およびを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-291">Use `Get-Service` and `Group-Object` to display the services.</span></span>

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

<span data-ttu-id="6b9ee-292">`Format-Table` **Wrap** パラメーターと共にを使用して、サービスの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-292">Use `Format-Table` with the **Wrap** parameter to display the list of services.</span></span>

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

### <a name="informationpreference"></a><span data-ttu-id="6b9ee-293">\$Informationpreference は</span><span class="sxs-lookup"><span data-stu-id="6b9ee-293">\$InformationPreference</span></span>

<span data-ttu-id="6b9ee-294">`$InformationPreference`変数を使用すると、ユーザーに表示する情報ストリームの設定を設定できます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-294">The `$InformationPreference` variable lets you set information stream preferences that you want displayed to users.</span></span> <span data-ttu-id="6b9ee-295">具体的には、 [書き込み情報](xref:Microsoft.PowerShell.Utility.Write-Information) のコマンドレットを追加して、コマンドまたはスクリプトに追加した情報メッセージです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-295">Specifically, informational messages that you added to commands or scripts by adding the [Write-Information](xref:Microsoft.PowerShell.Utility.Write-Information) cmdlet.</span></span> <span data-ttu-id="6b9ee-296">**Informationaction** パラメーターが使用されている場合、その値は変数の値よりも優先され `$InformationPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-296">If the **InformationAction** parameter is used, its value overrides the value of the `$InformationPreference` variable.</span></span> <span data-ttu-id="6b9ee-297">`Write-Information` は、PowerShell 5.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-297">`Write-Information` was introduced in PowerShell 5.0.</span></span>

<span data-ttu-id="6b9ee-298">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-298">The valid values are as follows:</span></span>

- <span data-ttu-id="6b9ee-299">**Stop** : コマンドの発生時に、コマンドまたはスクリプトを停止し `Write-Information` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-299">**Stop** : Stops a command or script at an occurrence of the `Write-Information` command.</span></span>
- <span data-ttu-id="6b9ee-300">**Inquire** : コマンドで指定した情報メッセージを表示し `Write-Information` 、続行するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-300">**Inquire** : Displays the informational message that you specify in a `Write-Information` command, then asks whether you want to continue.</span></span>
- <span data-ttu-id="6b9ee-301">[ **続行** ]: 情報メッセージを表示し、実行を継続します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-301">**Continue** : Displays the informational message, and continues running.</span></span>
- <span data-ttu-id="6b9ee-302">**Suspend** は、PowerShell 6 以降ではサポートされていないワークフローでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-302">**Suspend** is only available for workflows which aren't supported in PowerShell 6 and beyond.</span></span>
- <span data-ttu-id="6b9ee-303">**SilentlyContinue** : (既定) 効果はありません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-303">**SilentlyContinue** : (Default) No effect.</span></span> <span data-ttu-id="6b9ee-304">情報メッセージは表示されず、スクリプトは中断されることなく続行されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-304">The informational messages aren't displayed, and the script continues without interruption.</span></span>

### <a name="logevent"></a><span data-ttu-id="6b9ee-305">\$Log \* イベント</span><span class="sxs-lookup"><span data-stu-id="6b9ee-305">\$Log\*Event</span></span>

<span data-ttu-id="6b9ee-306">**Log \* イベント** ユーザー設定変数は、イベントビューアーで PowerShell イベントログに書き込まれるイベントの種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-306">The **Log\*Event** preference variables determine which types of events are written to the PowerShell event log in Event Viewer.</span></span> <span data-ttu-id="6b9ee-307">既定では、エンジンイベントとプロバイダーイベントのみがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-307">By default, only engine and provider events are logged.</span></span> <span data-ttu-id="6b9ee-308">ただし、 **log \* イベント** ユーザー設定変数を使用して、コマンドに関するイベントのログ記録などのログをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-308">But, you can use the **Log\*Event** preference variables to customize your log, such as logging events about commands.</span></span>

<span data-ttu-id="6b9ee-309">**Log \* イベント** ユーザー設定変数は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-309">The **Log\*Event** preference variables are as follows:</span></span>

- <span data-ttu-id="6b9ee-310">`$LogCommandHealthEvent`: コマンドの初期化および処理中に発生したエラーと例外をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-310">`$LogCommandHealthEvent`: Logs errors and exceptions in command initialization and processing.</span></span> <span data-ttu-id="6b9ee-311">既定値は `$false` (ログに記録されません) です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-311">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="6b9ee-312">`$LogCommandLifecycleEvent`: コマンド検出のコマンドとコマンドパイプラインおよびセキュリティ例外の開始と停止をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-312">`$LogCommandLifecycleEvent`: Logs the starting and stopping of commands and command pipelines and security exceptions in command discovery.</span></span> <span data-ttu-id="6b9ee-313">既定値は `$false` (ログに記録されません) です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-313">The default is `$false` (not logged).</span></span>
- <span data-ttu-id="6b9ee-314">`$LogEngineHealthEvent`: セッションのエラーとエラーをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-314">`$LogEngineHealthEvent`: Logs errors and failures of sessions.</span></span> <span data-ttu-id="6b9ee-315">既定値は `$true` (ログに記録されます) です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-315">The default is `$true` (logged).</span></span>
- <span data-ttu-id="6b9ee-316">`$LogEngineLifecycleEvent`: セッションの開始と終了をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-316">`$LogEngineLifecycleEvent`: Logs the opening and closing of sessions.</span></span> <span data-ttu-id="6b9ee-317">既定値は `$true` (ログに記録されます) です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-317">The default is `$true` (logged).</span></span>
- <span data-ttu-id="6b9ee-318">`$LogProviderHealthEvent`: 読み取りおよび書き込みエラー、参照エラー、呼び出しエラーなど、プロバイダーのエラーをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-318">`$LogProviderHealthEvent`: Logs provider errors, such as read and write errors, lookup errors, and invocation errors.</span></span> <span data-ttu-id="6b9ee-319">既定値は `$true` (ログに記録されます) です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-319">The default is `$true` (logged).</span></span>
- <span data-ttu-id="6b9ee-320">`$LogProviderLifecycleEvent`: PowerShell プロバイダーの追加と削除をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-320">`$LogProviderLifecycleEvent`: Logs adding and removing of PowerShell providers.</span></span> <span data-ttu-id="6b9ee-321">既定値は `$true` (ログに記録されます) です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-321">The default is `$true` (logged).</span></span> <span data-ttu-id="6b9ee-322">PowerShell プロバイダーの詳細については、「 [about_Providers](about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-322">For information about PowerShell providers, see [about_Providers](about_Providers.md).</span></span>

<span data-ttu-id="6b9ee-323">**Log \* イベント** を有効にするには、次の例のように、値を持つ変数を入力し `$true` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-323">To enable a **Log\*Event** , type the variable with a value of `$true`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $true
```

<span data-ttu-id="6b9ee-324">イベントの種類を無効にするには、という値を持つ変数を入力し `$false` ます。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-324">To disable an event type, type the variable with a value of `$false`, for example:</span></span>

```powershell
$LogCommandLifeCycleEvent = $false
```

<span data-ttu-id="6b9ee-325">有効にするイベントは、現在の PowerShell コンソールでのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-325">The events that you enable are effective only for the current PowerShell console.</span></span> <span data-ttu-id="6b9ee-326">すべてのコンソールに構成を適用するには、PowerShell プロファイルに変数の設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-326">To apply the configuration to all consoles, save the variable settings in your PowerShell profile.</span></span> <span data-ttu-id="6b9ee-327">詳細については、「 [about_Profiles](about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-327">For more information, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="maximumhistorycount"></a><span data-ttu-id="6b9ee-328">\$Maximumhistorycount ユーザー</span><span class="sxs-lookup"><span data-stu-id="6b9ee-328">\$MaximumHistoryCount</span></span>

<span data-ttu-id="6b9ee-329">現在のセッションのコマンド履歴に保存されているコマンドの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-329">Determines how many commands are saved in the command history for the current session.</span></span>

<span data-ttu-id="6b9ee-330">**有効な値** : 1-32768 ( `Int32` )</span><span class="sxs-lookup"><span data-stu-id="6b9ee-330">**Valid values** : 1 - 32768 (`Int32`)</span></span>

<span data-ttu-id="6b9ee-331">**既定値** : 4096</span><span class="sxs-lookup"><span data-stu-id="6b9ee-331">**Default** : 4096</span></span>

<span data-ttu-id="6b9ee-332">コマンド履歴に現在保存されているコマンドの数を確認するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-332">To determine the number of commands current saved in the command history, type:</span></span>

```powershell
(Get-History).Count
```

<span data-ttu-id="6b9ee-333">セッションの履歴に保存されているコマンドを確認するには、コマンドレットを使用し `Get-History` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-333">To see the commands saved in your session history, use the `Get-History` cmdlet.</span></span> <span data-ttu-id="6b9ee-334">詳細については、「 [about_History](about_History.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-334">For more information, see [about_History](about_History.md).</span></span>

### <a name="ofs"></a><span data-ttu-id="6b9ee-335">\$.OFS</span><span class="sxs-lookup"><span data-stu-id="6b9ee-335">\$OFS</span></span>

<span data-ttu-id="6b9ee-336">出力フィールド区切り記号 (OFS) は、文字列に変換される配列の要素を区切る文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-336">The Output Field Separator (OFS) specifies the character that separates the elements of an array that is converted to a string.</span></span>

<span data-ttu-id="6b9ee-337">**有効な値** : 任意の文字列。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-337">**Valid values** : Any string.</span></span>

<span data-ttu-id="6b9ee-338">**既定値** : Space</span><span class="sxs-lookup"><span data-stu-id="6b9ee-338">**Default** : Space</span></span>

<span data-ttu-id="6b9ee-339">既定では、変数は存在せず、 `$OFS` 出力ファイルの区切り記号は空白ですが、この変数を追加して任意の文字列に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-339">By default, the `$OFS` variable doesn't exist and the output file separator is a space, but you can add this variable and set it to any string.</span></span> <span data-ttu-id="6b9ee-340">セッションのの値を変更する `$OFS` には、「」と入力 `$OFS="<value>"` します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-340">You can change the value of `$OFS` in your session, by typing `$OFS="<value>"`.</span></span>

> [!NOTE]
> <span data-ttu-id="6b9ee-341">`" "`スクリプト、モジュール、または構成の出力で空白 () の既定値が予想される場合は、 `$OFS` 既定値がコード内の他の場所で変更されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-341">If you're expecting the default value of a space (`" "`) in your script, module, or configuration output, be careful that the `$OFS` default value hasn't been changed elsewhere in your code.</span></span>

#### <a name="examples"></a><span data-ttu-id="6b9ee-342">例</span><span class="sxs-lookup"><span data-stu-id="6b9ee-342">Examples</span></span>

<span data-ttu-id="6b9ee-343">この例は、配列が文字列に変換されるときに、値を区切るためにスペースを使用することを示しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-343">This example shows that a space is used to separate the values when an array is converted to a string.</span></span> <span data-ttu-id="6b9ee-344">この場合、整数の配列は変数に格納され、変数は文字列としてキャストされます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-344">In this case, an array of integers is stored in a variable and then the variable is cast as a string.</span></span>

```powershell
$array = 1,2,3,4
[string]$array
```

```Output
1 2 3 4
```

<span data-ttu-id="6b9ee-345">区切り記号を変更するには、 `$OFS` 変数に値を代入して変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-345">To change the separator, add the `$OFS` variable by assigning a value to it.</span></span>
<span data-ttu-id="6b9ee-346">変数はという名前にする必要があり `$OFS` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-346">The variable must be named `$OFS`.</span></span>

```powershell
$OFS = "+"
[string]$array
```

```Output
1+2+3+4
```

<span data-ttu-id="6b9ee-347">既定の動作を復元するには、 `" "` の値に空白 () を割り当てる `$OFS` か、変数を削除します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-347">To restore the default behavior, you can assign a space (`" "`) to the value of `$OFS` or delete the variable.</span></span> <span data-ttu-id="6b9ee-348">次のコマンドは、変数を削除し、区切り記号がスペースであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-348">The following commands delete the variable and then verify that the separator is a space.</span></span>

```powershell
Remove-Variable OFS
[string]$array
```

```Output
1 2 3 4
```

### <a name="outputencoding"></a><span data-ttu-id="6b9ee-349">\$OutputEncoding</span><span class="sxs-lookup"><span data-stu-id="6b9ee-349">\$OutputEncoding</span></span>

<span data-ttu-id="6b9ee-350">他のアプリケーションにテキストを送信するときに PowerShell が使用する文字エンコード方式を決定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-350">Determines the character encoding method that PowerShell uses when it sends text to other applications.</span></span>

<span data-ttu-id="6b9ee-351">たとえば、アプリケーションが Unicode 文字列を PowerShell に返す場合、値を **UnicodeEncoding** に変更して文字を正しく送信することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-351">For example, if an application returns Unicode strings to PowerShell, you might need to change the value to **UnicodeEncoding** to send the characters correctly.</span></span>

<span data-ttu-id="6b9ee-352">有効な値は次のとおりです。 **ASCIIEncoding** 、 **SBCSCodePageEncoding** 、 **UTF7Encoding** 、 **UTF8Encoding** 、 **UTF32Encoding** 、 **UnicodeEncoding** などのエンコーディングクラスから派生したオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-352">The valid values are as follows: Objects derived from an Encoding class, such as **ASCIIEncoding** , **SBCSCodePageEncoding** , **UTF7Encoding** , **UTF8Encoding** , **UTF32Encoding** , and **UnicodeEncoding**.</span></span>

<span data-ttu-id="6b9ee-353">**既定値** : UTF8Encoding Object (UTF8Encoding)</span><span class="sxs-lookup"><span data-stu-id="6b9ee-353">**Default** : UTF8Encoding object (System.Text.UTF8Encoding)</span></span>

#### <a name="examples"></a><span data-ttu-id="6b9ee-354">例</span><span class="sxs-lookup"><span data-stu-id="6b9ee-354">Examples</span></span>

<span data-ttu-id="6b9ee-355">この例では、中国語などの Unicode 文字を使用する言語用にローカライズされたコンピューターで Windows **findstr.exe** コマンドを PowerShell で動作させる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-355">This example shows how to make the Windows **findstr.exe** command work in PowerShell on a computer that is localized for a language that uses Unicode characters, such as Chinese.</span></span>

<span data-ttu-id="6b9ee-356">最初のコマンドは、の値を検索し `$OutputEncoding` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-356">The first command finds the value of `$OutputEncoding`.</span></span> <span data-ttu-id="6b9ee-357">値はエンコーディングオブジェクトであるため、 **encoding.encodingname** プロパティのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-357">Because the value is an encoding object, display only its **EncodingName** property.</span></span>

```powershell
$OutputEncoding.EncodingName
```

<span data-ttu-id="6b9ee-358">この例では、 **findstr.exe** コマンドを使用して、ファイル内に存在する2つの中国語文字を検索し `Test.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-358">In this example, a **findstr.exe** command is used to search for two Chinese characters that are present in the `Test.txt` file.</span></span> <span data-ttu-id="6b9ee-359">この **findstr.exe** コマンドを Windows コマンドプロンプト ( **cmd.exe** ) で実行すると、 **findstr.exe** によってテキストファイル内の文字が検索されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-359">When this **findstr.exe** command is run in the Windows Command Prompt ( **cmd.exe** ), **findstr.exe** finds the characters in the text file.</span></span> <span data-ttu-id="6b9ee-360">ただし、PowerShell で同じ **findstr.exe** コマンドを実行した場合、文字は検出されません。これは、Powershell が Unicode テキストではなく ASCII テキストで **findstr.exe** に送信するためです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-360">However, when you run the same **findstr.exe** command in PowerShell, the characters aren't found because the PowerShell sends them to **findstr.exe** in ASCII text, instead of in Unicode text.</span></span>

```powershell
findstr <Unicode-characters>
```

<span data-ttu-id="6b9ee-361">PowerShell でコマンドが動作するようにするには、の値 `$OutputEncoding` をコンソールの **outputencoding** プロパティの値に設定します。これは、Windows で選択されているロケールに基づいています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-361">To make the command work in PowerShell, set the value of `$OutputEncoding` to the value of the **OutputEncoding** property of the console, that is based on the locale selected for Windows.</span></span> <span data-ttu-id="6b9ee-362">**Outputencoding** はコンソールの静的プロパティであるため、コマンドで二重コロン () を使用し `::` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-362">Because **OutputEncoding** is a static property of the console, use double-colons (`::`) in the command.</span></span>

```powershell
$OutputEncoding = [console]::OutputEncoding
$OutputEncoding.EncodingName
```

```Output
OEM United States
```

<span data-ttu-id="6b9ee-363">エンコードを変更すると、 **findstr.exe** コマンドによって Unicode 文字が検索されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-363">After the encoding change, the **findstr.exe** command finds the Unicode characters.</span></span>

```powershell
findstr <Unicode-characters>
```

```Output
test.txt:         <Unicode-characters>
```

### <a name="progresspreference"></a><span data-ttu-id="6b9ee-364">\$ProgressPreference</span><span class="sxs-lookup"><span data-stu-id="6b9ee-364">\$ProgressPreference</span></span>

<span data-ttu-id="6b9ee-365">PowerShell が、スクリプト、コマンドレット、またはプロバイダーによって生成された進行状況の更新に応答する方法を決定します。たとえば、 [書き込みの進行状況](xref:Microsoft.PowerShell.Utility.Write-Progress) のコマンドレットによって生成された進行状況バーなどです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-365">Determines how PowerShell responds to progress updates generated by a script, cmdlet, or provider, such as the progress bars generated by the [Write-Progress](xref:Microsoft.PowerShell.Utility.Write-Progress) cmdlet.</span></span>
<span data-ttu-id="6b9ee-366">`Write-Progress`コマンドレットは、コマンドの状態を示す進行状況バーを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-366">The `Write-Progress` cmdlet creates progress bars that show a command's status.</span></span>

<span data-ttu-id="6b9ee-367">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-367">The valid values are as follows:</span></span>

- <span data-ttu-id="6b9ee-368">[ **停止** : 進行状況バーを表示しません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-368">**Stop** : Doesn't display the progress bar.</span></span> <span data-ttu-id="6b9ee-369">代わりに、エラーメッセージが表示され、実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-369">Instead, it displays an error message and stops executing.</span></span>
- <span data-ttu-id="6b9ee-370">**Inquire** : 進行状況バーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-370">**Inquire** : Doesn't display the progress bar.</span></span> <span data-ttu-id="6b9ee-371">続行するためのアクセス許可を要求します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-371">Prompts for permission to continue.</span></span> <span data-ttu-id="6b9ee-372">またはで返信すると `Y` `A` 、進行状況バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-372">If you reply with `Y` or `A`, it displays the progress bar.</span></span>
- <span data-ttu-id="6b9ee-373">**続行** : (既定) 進行状況バーを表示し、実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-373">**Continue** : (Default) Displays the progress bar and continues with execution.</span></span>
- <span data-ttu-id="6b9ee-374">**SilentlyContinue** : コマンドを実行しますが、進行状況バーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-374">**SilentlyContinue** : Executes the command, but doesn't display the progress bar.</span></span>

### <a name="psemailserver"></a><span data-ttu-id="6b9ee-375">\$PSEmailServer</span><span class="sxs-lookup"><span data-stu-id="6b9ee-375">\$PSEmailServer</span></span>

<span data-ttu-id="6b9ee-376">電子メールメッセージの送信に使用する既定の電子メールサーバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-376">Specifies the default e-mail server that is used to send email messages.</span></span> <span data-ttu-id="6b9ee-377">このユーザー設定変数は、電子メールを送信するコマンドレット ( [send-mailmessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) コマンドレットなど) によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-377">This preference variable is used by cmdlets that send email, such as the [Send-MailMessage](xref:Microsoft.PowerShell.Utility.Send-MailMessage) cmdlet.</span></span>

### <a name="psdefaultparametervalues"></a><span data-ttu-id="6b9ee-378">\$PSDefaultParameterValues</span><span class="sxs-lookup"><span data-stu-id="6b9ee-378">\$PSDefaultParameterValues</span></span>

<span data-ttu-id="6b9ee-379">コマンドレットおよび高度な関数のパラメーターの既定値を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-379">Specifies default values for the parameters of cmdlets and advanced functions.</span></span>
<span data-ttu-id="6b9ee-380">の値 `$PSDefaultParameterValues` はハッシュテーブルです。キーはコマンドレット名とパラメーター名で構成され、コロン () で区切られ `:` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-380">The value of `$PSDefaultParameterValues` is a hash table where the key consists of the cmdlet name and parameter name separated by a colon (`:`).</span></span> <span data-ttu-id="6b9ee-381">値は、ユーザーが指定するカスタムの既定値です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-381">The value is a custom default value that you specify.</span></span>

<span data-ttu-id="6b9ee-382">`$PSDefaultParameterValues` は、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-382">`$PSDefaultParameterValues` was introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="6b9ee-383">このユーザー設定変数の詳細については、「 [about_Parameters_Default_Values](about_Parameters_Default_Values.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-383">For more information about this preference variable, see [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span></span>

### <a name="psmoduleautoloadingpreference"></a><span data-ttu-id="6b9ee-384">\$PSModuleAutoloadingPreference</span><span class="sxs-lookup"><span data-stu-id="6b9ee-384">\$PSModuleAutoloadingPreference</span></span>

<span data-ttu-id="6b9ee-385">セッションのモジュールの自動インポートを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-385">Enables and disables automatic importing of modules in the session.</span></span> <span data-ttu-id="6b9ee-386">**All** が既定値です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-386">**All** is the default.</span></span> <span data-ttu-id="6b9ee-387">変数の値に関係なく、モジュールをインポート [するには、モジュールを](xref:Microsoft.PowerShell.Core.Import-Module) インポートします。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-387">Regardless of the variable's value, you can use [Import-Module](xref:Microsoft.PowerShell.Core.Import-Module) to import a module.</span></span>

<span data-ttu-id="6b9ee-388">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-388">Valid values are:</span></span>

- <span data-ttu-id="6b9ee-389">**すべて** : モジュールは初回使用時に自動的にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-389">**All** : Modules are imported automatically on first-use.</span></span> <span data-ttu-id="6b9ee-390">モジュールをインポートするには、モジュール内の任意のコマンドを取得または使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-390">To import a module, get or use any command in the module.</span></span> <span data-ttu-id="6b9ee-391">たとえば、 `Get-Command`を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-391">For example, use `Get-Command`.</span></span>
- <span data-ttu-id="6b9ee-392">**Modulの** 修飾: モジュールは、ユーザーがモジュール内のコマンドのモジュール修飾名を使用した場合にのみ、自動的にインポートされます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-392">**ModuleQualified** : Modules are imported automatically only when a user uses the module-qualified name of a command in the module.</span></span> <span data-ttu-id="6b9ee-393">たとえば、ユーザーがと入力すると、 `MyModule\MyCommand` PowerShell は **MyModule** モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-393">For example, if the user types `MyModule\MyCommand`, PowerShell imports the **MyModule** module.</span></span>
- <span data-ttu-id="6b9ee-394">**なし** : モジュールの自動インポートがセッションで無効になっています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-394">**None** : Automatic importing of modules is disabled in the session.</span></span> <span data-ttu-id="6b9ee-395">モジュールをインポートするには、 `Import-Module` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-395">To import a module, use the `Import-Module` cmdlet.</span></span>

<span data-ttu-id="6b9ee-396">モジュールの自動インポートの詳細については、「 [about_Modules](about_Modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-396">For more information about automatic importing of modules, see [about_Modules](about_Modules.md).</span></span>

### <a name="pssessionapplicationname"></a><span data-ttu-id="6b9ee-397">\$Pssessionapplicationname ユーザー</span><span class="sxs-lookup"><span data-stu-id="6b9ee-397">\$PSSessionApplicationName</span></span>

<span data-ttu-id="6b9ee-398">Web Services for Management (WS-MANAGEMENT) テクノロジを使用するリモートコマンドの既定のアプリケーション名を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-398">Specifies the default application name for a remote command that uses Web Services for Management (WS-Management) technology.</span></span> <span data-ttu-id="6b9ee-399">詳細については、「 [Windows リモート管理につい](/windows/win32/winrm/about-windows-remote-management)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-399">For more information, see [About Windows Remote Management](/windows/win32/winrm/about-windows-remote-management).</span></span>

<span data-ttu-id="6b9ee-400">システムの既定のアプリケーション名はです `WSMAN` が、このユーザー設定変数を使用して既定値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-400">The system default application name is `WSMAN`, but you can use this preference variable to change the default.</span></span>

<span data-ttu-id="6b9ee-401">アプリケーション名は、接続 URI の最後のノードです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-401">The application name is the last node in a connection URI.</span></span> <span data-ttu-id="6b9ee-402">たとえば、次の URI の例では、アプリケーション名が `WSMAN` です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-402">For example, the application name in the following sample URI is `WSMAN`.</span></span>

`http://Server01:8080/WSMAN`

<span data-ttu-id="6b9ee-403">既定のアプリケーション名は、リモートコマンドで接続 URI またはアプリケーション名が指定されていない場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-403">The default application name is used when the remote command doesn't specify a connection URI or an application name.</span></span>

<span data-ttu-id="6b9ee-404">**WinRM** サービスは、アプリケーション名を使用して、接続要求を処理するリスナーを選択します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-404">The **WinRM** service uses the application name to select a listener to service the connection request.</span></span> <span data-ttu-id="6b9ee-405">パラメーターの値は、リモートコンピューター上のリスナーの **Urlprefix** プロパティの値と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-405">The parameter's value should match the value of the **URLPrefix** property of a listener on the remote computer.</span></span>

<span data-ttu-id="6b9ee-406">システムの既定値とこの変数の値を上書きし、特定のセッションに対して別のアプリケーション名を選択するには、 [新しい PSSession](xref:Microsoft.PowerShell.Core.New-PSSession)、 [Enter-pssession](xref:Microsoft.PowerShell.Core.Enter-PSSession)、または [Invoke コマンド](xref:Microsoft.PowerShell.Core.Invoke-Command)レットの **connectionuri** または **ApplicationName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-406">To override the system default and the value of this variable, and select a different application name for a particular session, use the **ConnectionURI** or **ApplicationName** parameters of the [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession), or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command) cmdlets.</span></span>

<span data-ttu-id="6b9ee-407">ユーザー設定 `$PSSessionApplicationName` 変数はローカルコンピューターで設定されますが、リモートコンピューター上のリスナーを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-407">The `$PSSessionApplicationName` preference variable is set on the local computer, but it specifies a listener on the remote computer.</span></span> <span data-ttu-id="6b9ee-408">指定したアプリケーション名がリモートコンピューター上に存在しない場合、セッションを確立するコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-408">If the application name that you specify doesn't exist on the remote computer, the command to establish the session fails.</span></span>

### <a name="pssessionconfigurationname"></a><span data-ttu-id="6b9ee-409">\$Pssessionconfigurationname ユーザー</span><span class="sxs-lookup"><span data-stu-id="6b9ee-409">\$PSSessionConfigurationName</span></span>

<span data-ttu-id="6b9ee-410">現在のセッション **で作成された** pssession に使用される既定のセッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-410">Specifies the default session configuration that is used for **PSSessions** created in the current session.</span></span>

<span data-ttu-id="6b9ee-411">このユーザー設定変数はローカルコンピューターで設定されますが、リモートコンピューター上にあるセッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-411">This preference variable is set on the local computer, but it specifies a session configuration that's located on the remote computer.</span></span>

<span data-ttu-id="6b9ee-412">変数の値 `$PSSessionConfigurationName` は、完全修飾リソース URI です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-412">The value of the `$PSSessionConfigurationName` variable is a fully qualified resource URI.</span></span>

<span data-ttu-id="6b9ee-413">既定値は、 `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` リモートコンピューター上の **Microsoft PowerShell** セッション構成を示します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-413">The default value `http://schemas.microsoft.com/PowerShell/microsoft.PowerShell` indicates the **Microsoft.PowerShell** session configuration on the remote computer.</span></span>

<span data-ttu-id="6b9ee-414">構成名だけを指定した場合は、次のスキーマ URI が前に付加されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-414">If you specify only a configuration name, the following schema URI is prepended:</span></span>

`http://schemas.microsoft.com/PowerShell/`

<span data-ttu-id="6b9ee-415">**ConfigurationName** `New-PSSession` 、、 `Enter-PSSession` またはコマンドレットの ConfigurationName パラメーターを使用して、既定値を上書きし、特定のセッションに対して別のセッション構成を選択することができ `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-415">You can override the default and select a different session configuration for a particular session by using the **ConfigurationName** parameter of the `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` cmdlets.</span></span>

<span data-ttu-id="6b9ee-416">この変数の値はいつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-416">You can change the value of this variable at any time.</span></span> <span data-ttu-id="6b9ee-417">この場合は、選択したセッション構成がリモートコンピューターに存在する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-417">When you do, remember that the session configuration that you select must exist on the remote computer.</span></span> <span data-ttu-id="6b9ee-418">そうでない場合、セッション構成を使用するセッションを作成するコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-418">If it doesn't, the command to create a session that uses the session configuration fails.</span></span>

<span data-ttu-id="6b9ee-419">このユーザー設定変数は、リモートユーザーがこのコンピューターに接続するセッションを作成するときに使用されるローカルセッション構成を決定しません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-419">This preference variable doesn't determine which local session configurations are used when remote users create a session that connects to this computer.</span></span>
<span data-ttu-id="6b9ee-420">ただし、ローカルセッション構成のアクセス許可を使用して、使用できるユーザーを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-420">However, you can use the permissions for the local session configurations to determine which users may use them.</span></span>

### <a name="pssessionoption"></a><span data-ttu-id="6b9ee-421">\$PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="6b9ee-421">\$PSSessionOption</span></span>

<span data-ttu-id="6b9ee-422">リモートセッションでの高度なユーザーオプションの既定値を設定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-422">Establishes the default values for advanced user options in a remote session.</span></span>
<span data-ttu-id="6b9ee-423">これらのオプションの設定は、セッションオプションのシステムの既定値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-423">These option preferences override the system default values for session options.</span></span>

<span data-ttu-id="6b9ee-424">変数には、 `$PSSessionOption` **Pssessionoption** オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-424">The `$PSSessionOption` variable contains a **PSSessionOption** object.</span></span> <span data-ttu-id="6b9ee-425">詳細については、「system.string [オプション](/dotnet/api/system.management.automation.remoting.pssessionoption)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-425">For more information, see [System.Management.Automation.Remoting.PSSessionOption](/dotnet/api/system.management.automation.remoting.pssessionoption).</span></span>
<span data-ttu-id="6b9ee-426">オブジェクトの各プロパティは、セッションオプションを表します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-426">Each property of the object represents a session option.</span></span> <span data-ttu-id="6b9ee-427">たとえば、 **Nocompression** プロパティは、セッション中のデータ圧縮を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-427">For example, the **NoCompression** property turns of data compression during the session.</span></span>

<span data-ttu-id="6b9ee-428">既定では、変数には、 `$PSSessionOption` 次に示すように、すべてのオプションの既定値を持つ **Pssessionoption** オブジェクトが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-428">By default, the `$PSSessionOption` variable contains a **PSSessionOption** object with the default values for all options, as shown below.</span></span>

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

<span data-ttu-id="6b9ee-429">これらのオプションの説明と詳細については、「 [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-429">For descriptions of these options and more information, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span> <span data-ttu-id="6b9ee-430">リモートコマンドとセッションの詳細については、「 [about_Remote](about_Remote.md) 」および「 [about_PSSessions](about_PSSessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-430">For more information about remote commands and sessions, see [about_Remote](about_Remote.md) and [about_PSSessions](about_PSSessions.md).</span></span>

<span data-ttu-id="6b9ee-431">ユーザー設定変数の値を変更するには、コマンドレットを使用して、 `$PSSessionOption` `New-PSSessionOption` 必要なオプション値を指定した **pssessionoption** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-431">To change the value of the `$PSSessionOption` preference variable, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object with the option values you prefer.</span></span> <span data-ttu-id="6b9ee-432">という変数に出力を保存 `$PSSessionOption` します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-432">Save the output in a variable called `$PSSessionOption`.</span></span>

```powershell
$PSSessionOption = New-PSSessionOption -NoCompression
```

<span data-ttu-id="6b9ee-433">`$PSSessionOption`すべての powershell セッションでユーザー設定変数を使用するには、 `New-PSSessionOption` powershell プロファイルに変数を作成するコマンドを追加し `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-433">To use the `$PSSessionOption` preference variable in every PowerShell session, add a `New-PSSessionOption` command that creates the `$PSSessionOption` variable to your PowerShell profile.</span></span> <span data-ttu-id="6b9ee-434">詳細については、「 [about_Profiles](about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-434">For more information, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="6b9ee-435">特定のリモートセッションに対してカスタムオプションを設定できます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-435">You can set custom options for a particular remote session.</span></span> <span data-ttu-id="6b9ee-436">設定するオプションは、システムの既定値とユーザー設定変数の値よりも優先され `$PSSessionOption` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-436">The options that you set take precedence over the system defaults and the value of the `$PSSessionOption` preference variable.</span></span>

<span data-ttu-id="6b9ee-437">カスタムセッションオプションを設定するには、コマンドレットを使用して `New-PSSessionOption` **Pssessionoption** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-437">To set custom session options, use the `New-PSSessionOption` cmdlet to create a **PSSessionOption** object.</span></span> <span data-ttu-id="6b9ee-438">次に、、、などのセッションを作成するコマンドレットの **sessionoption** パラメーターの値として **pssessionoption** オブジェクトを使用し `New-PSSession` `Enter-PSSession` `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-438">Then, use the **PSSessionOption** object as the value of the **SessionOption** parameter in cmdlets that create a session, such as `New-PSSession`, `Enter-PSSession`, and `Invoke-Command`.</span></span>

### <a name="transcript"></a><span data-ttu-id="6b9ee-439">$Transcript</span><span class="sxs-lookup"><span data-stu-id="6b9ee-439">$Transcript</span></span>

<span data-ttu-id="6b9ee-440">`Start-Transcript`トランスクリプトファイルの名前と場所を指定するために、によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-440">Used by `Start-Transcript` to specify the name and location of the transcript file.</span></span> <span data-ttu-id="6b9ee-441">**Path** パラメーターの値を指定しない場合、は `Start-Transcript` グローバル変数の値のパスを使用し `$Transcript` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-441">If you do not specify a value for the **Path** parameter, `Start-Transcript` uses the path in the value of the `$Transcript` global variable.</span></span> <span data-ttu-id="6b9ee-442">この変数を作成していない場合は、によっ `Start-Transcript` `$Home\My Documents` てファイルとしてディレクトリにトランスクリプトが保存され `\PowerShell_transcript.<time-stamp>.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-442">If you have not created this variable, `Start-Transcript` stores the transcripts in the `$Home\My Documents` directory as `\PowerShell_transcript.<time-stamp>.txt` files.</span></span>

### <a name="verbosepreference"></a><span data-ttu-id="6b9ee-443">\$VerbosePreference</span><span class="sxs-lookup"><span data-stu-id="6b9ee-443">\$VerbosePreference</span></span>

<span data-ttu-id="6b9ee-444">PowerShell が、スクリプト、コマンドレット、またはプロバイダーによって生成される詳細メッセージに応答する方法を決定します。これには、 [書き込み/詳細](xref:Microsoft.PowerShell.Utility.Write-Verbose) コマンドレットによって生成されるメッセージなどがあります。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-444">Determines how PowerShell responds to verbose messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Verbose](xref:Microsoft.PowerShell.Utility.Write-Verbose) cmdlet.</span></span>
<span data-ttu-id="6b9ee-445">詳細メッセージには、コマンドを実行するために実行されるアクションが記述されています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-445">Verbose messages describe the actions performed to execute a command.</span></span>

<span data-ttu-id="6b9ee-446">既定では、詳細メッセージは表示されませんが、の値を変更することでこの動作を変更でき `$VerbosePreference` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-446">By default, verbose messages aren't displayed, but you can change this behavior by changing the value of `$VerbosePreference`.</span></span>

<span data-ttu-id="6b9ee-447">コマンドレットの **verbose** 共通パラメーターを使用して、特定のコマンドの詳細メッセージを表示または非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-447">You can use the **Verbose** common parameter of a cmdlet to display or hide the verbose messages for a specific command.</span></span> <span data-ttu-id="6b9ee-448">詳細については、「[about_CommonParameters](about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-448">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="6b9ee-449">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-449">The valid values are as follows:</span></span>

- <span data-ttu-id="6b9ee-450">[ **停止** ]: 詳細メッセージとエラーメッセージを表示し、実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-450">**Stop** : Displays the verbose message and an error message and then stops executing.</span></span>
- <span data-ttu-id="6b9ee-451">[ **Inquire** ]: 詳細メッセージが表示され、続行するかどうかを確認するプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-451">**Inquire** : Displays the verbose message and then displays a prompt that asks you whether you want to continue.</span></span>
- <span data-ttu-id="6b9ee-452">**続行** : 詳細メッセージを表示し、実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-452">**Continue** : Displays the verbose message and then continues with execution.</span></span>
- <span data-ttu-id="6b9ee-453">**SilentlyContinue** : (既定) では、詳細メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-453">**SilentlyContinue** : (Default) Doesn't display the verbose message.</span></span> <span data-ttu-id="6b9ee-454">実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-454">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="6b9ee-455">例</span><span class="sxs-lookup"><span data-stu-id="6b9ee-455">Examples</span></span>

<span data-ttu-id="6b9ee-456">これらの例では、の異なる値の効果 `$VerbosePreference` と **Verbose** パラメーターを指定して、優先順位の値をオーバーライドしています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-456">These examples show the effect of the different values of `$VerbosePreference` and the **Verbose** parameter to override the preference value.</span></span>

<span data-ttu-id="6b9ee-457">この例は、既定の **SilentlyContinue** 値の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-457">This example shows the effect of the **SilentlyContinue** value, that is the default.</span></span> <span data-ttu-id="6b9ee-458">このコマンドでは、 **message** パラメーターを使用しますが、PowerShell コンソールにはメッセージは書き込まれません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-458">The command uses the **Message** parameter, but doesn't write a message to the PowerShell console.</span></span>

```powershell
Write-Verbose -Message "Verbose message test."
```

<span data-ttu-id="6b9ee-459">**Verbose** パラメーターを使用すると、メッセージが書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-459">When the **Verbose** parameter is used, the message is written.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="6b9ee-460">この例は、 **Continue** 値の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-460">This example shows the effect of the **Continue** value.</span></span> <span data-ttu-id="6b9ee-461">`$VerbosePreference`変数が **Continue** に設定され、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-461">The `$VerbosePreference` variable is set to **Continue** and the message is displayed.</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose -Message "Verbose message test."
```

```Output
VERBOSE: Verbose message test.
```

<span data-ttu-id="6b9ee-462">この例では **Verbose** 、 `$false` **Continue** 値をオーバーライドするの値を持つ Verbose パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-462">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Continue** value.</span></span> <span data-ttu-id="6b9ee-463">メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-463">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="6b9ee-464">この例は、 **Stop** 値の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-464">This example shows the effect of the **Stop** value.</span></span> <span data-ttu-id="6b9ee-465">`$VerbosePreference`変数が **Stop** に設定され、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-465">The `$VerbosePreference` variable is set to **Stop** and the message is displayed.</span></span> <span data-ttu-id="6b9ee-466">コマンドは停止しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-466">The command is stopped.</span></span>

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

<span data-ttu-id="6b9ee-467">この例では **Verbose** 、 `$false` **Stop** 値をオーバーライドするの値を持つ Verbose パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-467">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Stop** value.</span></span> <span data-ttu-id="6b9ee-468">メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-468">The message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

<span data-ttu-id="6b9ee-469">この例は、 **Inquire** 値の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-469">This example shows the effect of the **Inquire** value.</span></span> <span data-ttu-id="6b9ee-470">`$VerbosePreference`変数は **Inquire** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-470">The `$VerbosePreference` variable is set to **Inquire**.</span></span> <span data-ttu-id="6b9ee-471">メッセージが表示され、ユーザーに確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-471">The message is displayed and the user is prompted for confirmation.</span></span>

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

<span data-ttu-id="6b9ee-472">この例では **Verbose** 、 `$false` **Inquire** 値をオーバーライドするの値を持つ Verbose パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-472">This example uses the **Verbose** parameter with a value of `$false` that overrides the **Inquire** value.</span></span> <span data-ttu-id="6b9ee-473">ユーザーにプロンプトが表示されず、メッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-473">The user isn't prompted and the message isn't displayed.</span></span>

```powershell
Write-Verbose -Message "Verbose message test." -Verbose:$false
```

### <a name="warningpreference"></a><span data-ttu-id="6b9ee-474">\$WarningPreference</span><span class="sxs-lookup"><span data-stu-id="6b9ee-474">\$WarningPreference</span></span>

<span data-ttu-id="6b9ee-475">スクリプト、コマンドレット、またはプロバイダーによって生成される警告メッセージ ( [書き込み警告](xref:Microsoft.PowerShell.Utility.Write-Warning) コマンドレットによって生成されるメッセージなど) に対して PowerShell が応答する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-475">Determines how PowerShell responds to warning messages generated by a script, cmdlet, or provider, such as the messages generated by the [Write-Warning](xref:Microsoft.PowerShell.Utility.Write-Warning) cmdlet.</span></span>

<span data-ttu-id="6b9ee-476">既定では、警告メッセージが表示され、実行が続行されますが、の値を変更することでこの動作を変更でき `$WarningPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-476">By default, warning messages are displayed and execution continues, but you can change this behavior by changing the value of `$WarningPreference`.</span></span>

<span data-ttu-id="6b9ee-477">コマンドレットの **Warnings action** 共通パラメーターを使用して、PowerShell が特定のコマンドからの警告に応答する方法を決定できます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-477">You can use the **WarningAction** common parameter of a cmdlet to determine how PowerShell responds to warnings from a particular command.</span></span> <span data-ttu-id="6b9ee-478">詳細については、「[about_CommonParameters](about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-478">For more information, see [about_CommonParameters](about_CommonParameters.md).</span></span>

<span data-ttu-id="6b9ee-479">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-479">The valid values are as follows:</span></span>

- <span data-ttu-id="6b9ee-480">[ **停止** ]: 警告メッセージとエラーメッセージを表示し、実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-480">**Stop** : Displays the warning message and an error message and then stops executing.</span></span>
- <span data-ttu-id="6b9ee-481">**Inquire** : 警告メッセージを表示し、続行するためのアクセス許可を要求します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-481">**Inquire** : Displays the warning message and then prompts for permission to continue.</span></span>
- <span data-ttu-id="6b9ee-482">**続行** : (既定) 警告メッセージを表示し、実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-482">**Continue** : (Default) Displays the warning message and then continues executing.</span></span>
- <span data-ttu-id="6b9ee-483">**SilentlyContinue** : 警告メッセージが表示されません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-483">**SilentlyContinue** : Doesn't display the warning message.</span></span> <span data-ttu-id="6b9ee-484">実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-484">Continues executing.</span></span>

#### <a name="examples"></a><span data-ttu-id="6b9ee-485">例</span><span class="sxs-lookup"><span data-stu-id="6b9ee-485">Examples</span></span>

<span data-ttu-id="6b9ee-486">これらの例は、のさまざまな値の効果を示して `$WarningPreference` います。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-486">These examples show the effect of the different values of `$WarningPreference`.</span></span>
<span data-ttu-id="6b9ee-487">**Warnings action** パラメーターは、基本設定値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-487">The **WarningAction** parameter overrides the preference value.</span></span>

<span data-ttu-id="6b9ee-488">この例は、既定値の効果を示しています。 **続行** します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-488">This example shows the effect of the default value, **Continue**.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m
```

```Output
WARNING: This action can delete data.
```

<span data-ttu-id="6b9ee-489">この例では、 **SilentlyContinue** 値を指定した **warnings action** パラメーターを使用して、警告を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-489">This example uses the **WarningAction** parameter with the value **SilentlyContinue** to suppress the warning.</span></span> <span data-ttu-id="6b9ee-490">メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-490">The message isn't displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="6b9ee-491">この例では、 `$WarningPreference` 変数を **SilentlyContinue** 値に変更します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-491">This example changes the `$WarningPreference` variable to the **SilentlyContinue** value.</span></span> <span data-ttu-id="6b9ee-492">メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-492">The message isn't displayed.</span></span>

```powershell
$WarningPreference = "SilentlyContinue"
$m = "This action can delete data."
Write-Warning -Message $m
```

<span data-ttu-id="6b9ee-493">この例では、警告が生成されたときに、 **Warnings action** パラメーターを使用して停止します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-493">This example uses the **WarningAction** parameter to stop when a warning is generated.</span></span>

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

<span data-ttu-id="6b9ee-494">この例では、 `$WarningPreference` 変数を **Inquire** 値に変更します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-494">This example changes the `$WarningPreference` variable to the **Inquire** value.</span></span> <span data-ttu-id="6b9ee-495">ユーザーに確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-495">The user is prompted for confirmation.</span></span>

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

<span data-ttu-id="6b9ee-496">この例では、 **SilentlyContinue** という値を指定して **warnings action** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-496">This example uses the **WarningAction** parameter with the value **SilentlyContinue**.</span></span> <span data-ttu-id="6b9ee-497">コマンドは引き続き実行され、メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-497">The command continues to execute and no message is displayed.</span></span>

```powershell
$m = "This action can delete data."
Write-Warning -Message $m -WarningAction SilentlyContinue
```

<span data-ttu-id="6b9ee-498">この例では、 `$WarningPreference` 値を **Stop** に変更します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-498">This example changes the `$WarningPreference` value to **Stop**.</span></span>

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

<span data-ttu-id="6b9ee-499">この例では、 **Inquire** 値を指定して **warnings アクション** を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-499">This example uses the **WarningAction** with the **Inquire** value.</span></span> <span data-ttu-id="6b9ee-500">警告が発生すると、ユーザーに対してメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-500">The user is prompted when a warning occurs.</span></span>

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

### <a name="whatifpreference"></a><span data-ttu-id="6b9ee-501">\$WhatIfPreference</span><span class="sxs-lookup"><span data-stu-id="6b9ee-501">\$WhatIfPreference</span></span>

<span data-ttu-id="6b9ee-502">サポートされているすべてのコマンドに対して **WhatIf** を自動的に有効にするかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-502">Determines whether **WhatIf** is automatically enabled for every command that supports it.</span></span> <span data-ttu-id="6b9ee-503">**WhatIf** が有効になっている場合、コマンドレットはコマンドの予想される効果を報告しますが、コマンドを実行しません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-503">When **WhatIf** is enabled, the cmdlet reports the expected effect of the command, but doesn't execute the command.</span></span>

<span data-ttu-id="6b9ee-504">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-504">The valid values are as follows:</span></span>

- <span data-ttu-id="6b9ee-505">**False** ( **0** 、有効でない): (既定値) **WhatIf** が自動的に有効になることはありません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-505">**False** ( **0** , not enabled): (Default) **WhatIf** isn't automatically enabled.</span></span> <span data-ttu-id="6b9ee-506">手動で有効にするには、コマンドレットの **WhatIf** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-506">To enable it manually, use the cmdlet's **WhatIf** parameter.</span></span>
- <span data-ttu-id="6b9ee-507">**True** ( **1** 、有効): **WhatIf** は、それをサポートするすべてのコマンドで自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-507">**True** ( **1** , enabled): **WhatIf** is automatically enabled on any command that supports it.</span></span> <span data-ttu-id="6b9ee-508">ユーザーは、 **WhatIf** パラメーターを値 **False** と共に使用して、などのように手動で無効にすることができ `-WhatIf:$false` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-508">Users can use the **WhatIf** parameter with a value of **False** to disable it manually, such as `-WhatIf:$false`.</span></span>

#### <a name="examples"></a><span data-ttu-id="6b9ee-509">例</span><span class="sxs-lookup"><span data-stu-id="6b9ee-509">Examples</span></span>

<span data-ttu-id="6b9ee-510">これらの例は、のさまざまな値の効果を示して `$WhatIfPreference` います。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-510">These examples show the effect of the different values of `$WhatIfPreference`.</span></span>
<span data-ttu-id="6b9ee-511">この例では、 **WhatIf** パラメーターを使用して、特定のコマンドの設定値をオーバーライドする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-511">They show how to use the **WhatIf** parameter to override the preference value for a specific command.</span></span>

<span data-ttu-id="6b9ee-512">この例は、 `$WhatIfPreference` 変数が既定値の **False** に設定された場合の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-512">This example shows the effect of the `$WhatIfPreference` variable set to the default value, **False**.</span></span> <span data-ttu-id="6b9ee-513">`Get-ChildItem`ファイルが存在することを確認するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-513">Use `Get-ChildItem` to verify that the file exists.</span></span>
<span data-ttu-id="6b9ee-514">`Remove-Item` ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-514">`Remove-Item` deletes the file.</span></span> <span data-ttu-id="6b9ee-515">ファイルが削除されたら、で削除を確認でき `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-515">After the file is deleted, you can verify the deletion with `Get-ChildItem`.</span></span>

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

<span data-ttu-id="6b9ee-516">この例は、の値が False の場合に **WhatIf** パラメーターを使用した場合の効果を示して `$WhatIfPreference` います。 **False**</span><span class="sxs-lookup"><span data-stu-id="6b9ee-516">This example shows the effect of using the **WhatIf** parameter when the value of `$WhatIfPreference` is **False**.</span></span>

<span data-ttu-id="6b9ee-517">ファイルが存在することを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-517">Verify that the file exists.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="6b9ee-518">**WhatIf** パラメーターを使用して、ファイルを削除しようとした結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-518">Use the **WhatIf** parameter to determine the result of attempting to delete the file.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
``````

<span data-ttu-id="6b9ee-519">ファイルが削除されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-519">Verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="6b9ee-520">この例では、変数の `$WhatIfPreference` 値が **True** に設定された場合の効果を示します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-520">This example shows the effect of the `$WhatIfPreference` variable set to the value, **True**.</span></span> <span data-ttu-id="6b9ee-521">を使用してファイルを削除すると、ファイル `Remove-Item` のパスが表示されますが、ファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-521">When you use `Remove-Item` to delete a file, the file's path is displayed, but the file isn't deleted.</span></span>

<span data-ttu-id="6b9ee-522">ファイルを削除しようとしました。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-522">Attempt to delete a file.</span></span> <span data-ttu-id="6b9ee-523">が実行された場合に何が起こるかについてのメッセージが表示され `Remove-Item` ますが、ファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-523">A message is displayed about what would happen if `Remove-Item` was run, but the file isn't deleted.</span></span>

```powershell
$WhatIfPreference = "True"
Remove-Item -Path .\test2.txt
```

```Output
What if: Performing the operation "Remove File" on target "C:\Test\test2.txt".
```

<span data-ttu-id="6b9ee-524">`Get-ChildItem`ファイルが削除されていないことを確認するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-524">Use `Get-ChildItem` to verify that the file wasn't deleted.</span></span>

```powershell
Get-ChildItem -Path .\test2.txt
```

```Output
    Directory: C:\Test

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2/28/2019    17:06             12 test2.txt
```

<span data-ttu-id="6b9ee-525">この例では、の値が True の場合にファイルを削除する方法を示し `$WhatIfPreference` ます。 **True**</span><span class="sxs-lookup"><span data-stu-id="6b9ee-525">This example shows how to delete a file when the value of `$WhatIfPreference` is **True**.</span></span> <span data-ttu-id="6b9ee-526">この例では、 **WhatIf** パラメーターに値を指定 `$false` しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-526">It uses the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="6b9ee-527">`Get-ChildItem`ファイルが削除されたことを確認するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-527">Use `Get-ChildItem` to verify the file was deleted.</span></span>

```powershell
Remove-Item -Path .\test2.txt -WhatIf:$false
Get-ChildItem -Path .\test2.txt
```

```Output
Get-ChildItem : Cannot find path 'C:\Test\test2.txt' because it does not exist.
At line:1 char:1
+ Get-ChildItem -Path .\test2.txt
```

<span data-ttu-id="6b9ee-528">Whatif をサポートしていない whatif をサポートしているコマンドレットの例を次に示します `Get-Process` **WhatIf** `Stop-Process` 。 **WhatIf**</span><span class="sxs-lookup"><span data-stu-id="6b9ee-528">The following are examples of the `Get-Process` cmdlet that doesn't support **WhatIf** and `Stop-Process` that does support **WhatIf**.</span></span> <span data-ttu-id="6b9ee-529">`$WhatIfPreference`変数の値は **True** です。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-529">The `$WhatIfPreference` variable's value is **True**.</span></span>

<span data-ttu-id="6b9ee-530">`Get-Process`**WhatIf** はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-530">`Get-Process` doesn't support **WhatIf**.</span></span> <span data-ttu-id="6b9ee-531">コマンドが実行されると、 **winword.exe** プロセスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-531">When the command is executed, it displays the **Winword** process.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
    130   119.84     173.38       8.39   15024   4 WINWORD
```

<span data-ttu-id="6b9ee-532">`Stop-Process` は **WhatIf** をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-532">`Stop-Process` does support **WhatIf**.</span></span> <span data-ttu-id="6b9ee-533">**Winword.exe** プロセスは停止されていません。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-533">The **Winword** process isn't stopped.</span></span>

```powershell
Stop-Process -Name Winword
```

```Output
What if: Performing the operation "Stop-Process" on target "WINWORD (15024)".
```

<span data-ttu-id="6b9ee-534">Whatif 動作をオーバーライドするには、 `Stop-Process` **WhatIf** **whatif** パラメーターに値を指定し `$false` ます。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-534">You can override the `Stop-Process` **WhatIf** behavior by using the **WhatIf** parameter with a value of `$false`.</span></span> <span data-ttu-id="6b9ee-535">**Winword.exe** プロセスは停止しています。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-535">The **Winword** process is stopped.</span></span>

```powershell
Stop-Process -Name Winword -WhatIf:$false
```

<span data-ttu-id="6b9ee-536">**Winword.exe** プロセスが停止したことを確認するには、を使用 `Get-Process` します。</span><span class="sxs-lookup"><span data-stu-id="6b9ee-536">To verify that the **Winword** process was stopped, use `Get-Process`.</span></span>

```powershell
Get-Process -Name Winword
```

```Output
Get-Process : Cannot find a process with the name "Winword".
  Verify the process name and call the cmdlet again.
At line:1 char:1
+ Get-Process -Name Winword
```

## <a name="see-also"></a><span data-ttu-id="6b9ee-537">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b9ee-537">See also</span></span>

[<span data-ttu-id="6b9ee-538">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="6b9ee-538">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="6b9ee-539">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6b9ee-539">about_CommonParameters</span></span>](about_CommonParameters.md)

[<span data-ttu-id="6b9ee-540">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="6b9ee-540">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="6b9ee-541">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="6b9ee-541">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="6b9ee-542">about_Remote</span><span class="sxs-lookup"><span data-stu-id="6b9ee-542">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="6b9ee-543">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="6b9ee-543">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="6b9ee-544">about_Variables</span><span class="sxs-lookup"><span data-stu-id="6b9ee-544">about_Variables</span></span>](about_Variables.md)