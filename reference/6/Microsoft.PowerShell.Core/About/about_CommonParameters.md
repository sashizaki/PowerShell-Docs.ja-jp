---
description: 任意のコマンドレットで使用できるパラメーターについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_commonparameters?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_CommonParameters
ms.openlocfilehash: c0e995e4677d235e7f218267162c15d7f1693e06
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221755"
---
# <a name="about-commonparameters"></a><span data-ttu-id="f7206-104">CommonParameters について</span><span class="sxs-lookup"><span data-stu-id="f7206-104">About CommonParameters</span></span>

## <a name="short-description"></a><span data-ttu-id="f7206-105">概要</span><span class="sxs-lookup"><span data-stu-id="f7206-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="f7206-106">任意のコマンドレットで使用できるパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f7206-106">Describes the parameters that can be used with any cmdlet.</span></span>

## <a name="long-description"></a><span data-ttu-id="f7206-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="f7206-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="f7206-108">共通パラメーターは、すべてのコマンドレットで使用できるコマンドレットパラメーターのセットです。</span><span class="sxs-lookup"><span data-stu-id="f7206-108">The common parameters are a set of cmdlet parameters that you can use with any cmdlet.</span></span> <span data-ttu-id="f7206-109">これらは、コマンドレットの開発者ではなく、PowerShell によって実装され、任意のコマンドレットで自動的に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f7206-109">They're implemented by PowerShell, not by the cmdlet developer, and they're automatically available to any cmdlet.</span></span>

<span data-ttu-id="f7206-110">共通パラメーターは任意のコマンドレットと共に使用できますが、すべてのコマンドレットに影響を与えない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7206-110">You can use the common parameters with any cmdlet, but they might not have an effect on all cmdlets.</span></span> <span data-ttu-id="f7206-111">たとえば、コマンドレットで詳細出力が生成されない場合、 **verbose** 共通パラメーターを使用しても効果はありません。</span><span class="sxs-lookup"><span data-stu-id="f7206-111">For example, if a cmdlet doesn't generate any verbose output, using the **Verbose** common parameter has no effect.</span></span>

<span data-ttu-id="f7206-112">一般的なパラメーターは、表示可能な **バインド** 属性または **Parameter** 属性を使用する高度な関数でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7206-112">The common parameters are also available on advanced functions that use the **CmdletBinding** attribute or the **Parameter** attribute.</span></span>

<span data-ttu-id="f7206-113">いくつかの一般的なパラメーターでは、システムの既定値や、PowerShell ユーザー設定変数を使用して設定した設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="f7206-113">Several common parameters override system defaults or preferences that you set by using the PowerShell preference variables.</span></span> <span data-ttu-id="f7206-114">ユーザー設定変数とは異なり、共通パラメーターは、使用されるコマンドにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="f7206-114">Unlike the preference variables, the common parameters affect only the commands in which they're used.</span></span>

<span data-ttu-id="f7206-115">詳細については、「 [about_Preference_Variables](./about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7206-115">For more information, see [about_Preference_Variables](./about_Preference_Variables.md).</span></span>

<span data-ttu-id="f7206-116">共通パラメーターの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f7206-116">The following list displays the common parameters.</span></span> <span data-ttu-id="f7206-117">これらのエイリアスは、かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="f7206-117">Their aliases are listed in parentheses.</span></span>

- <span data-ttu-id="f7206-118">**Debug** (db)</span><span class="sxs-lookup"><span data-stu-id="f7206-118">**Debug** (db)</span></span>
- <span data-ttu-id="f7206-119">**Erroraction** (ea)</span><span class="sxs-lookup"><span data-stu-id="f7206-119">**ErrorAction** (ea)</span></span>
- <span data-ttu-id="f7206-120">**Errorvariable** (ev)</span><span class="sxs-lookup"><span data-stu-id="f7206-120">**ErrorVariable** (ev)</span></span>
- <span data-ttu-id="f7206-121">**Informationaction** (infa)</span><span class="sxs-lookup"><span data-stu-id="f7206-121">**InformationAction** (infa)</span></span>
- <span data-ttu-id="f7206-122">**Informationvariable** (iv)</span><span class="sxs-lookup"><span data-stu-id="f7206-122">**InformationVariable** (iv)</span></span>
- <span data-ttu-id="f7206-123">**Outvariable** (ov-es)</span><span class="sxs-lookup"><span data-stu-id="f7206-123">**OutVariable** (ov)</span></span>
- <span data-ttu-id="f7206-124">**Outbuffer** (ob)</span><span class="sxs-lookup"><span data-stu-id="f7206-124">**OutBuffer** (ob)</span></span>
- <span data-ttu-id="f7206-125">**PipelineVariable** (pv)</span><span class="sxs-lookup"><span data-stu-id="f7206-125">**PipelineVariable** (pv)</span></span>
- <span data-ttu-id="f7206-126">**Verbose** (vb)</span><span class="sxs-lookup"><span data-stu-id="f7206-126">**Verbose** (vb)</span></span>
- <span data-ttu-id="f7206-127">**警告動作** (wa)</span><span class="sxs-lookup"><span data-stu-id="f7206-127">**WarningAction** (wa)</span></span>
- <span data-ttu-id="f7206-128">**警告変数** (wv)</span><span class="sxs-lookup"><span data-stu-id="f7206-128">**WarningVariable** (wv)</span></span>

<span data-ttu-id="f7206-129">**アクション** パラメーターは **actionpreference** 型の値です。</span><span class="sxs-lookup"><span data-stu-id="f7206-129">The **Action** parameters are **ActionPreference** type values.</span></span>
<span data-ttu-id="f7206-130">**Actionpreference** は、次の値を持つ列挙体です。</span><span class="sxs-lookup"><span data-stu-id="f7206-130">**ActionPreference** is an enumeration with the following values:</span></span>

| <span data-ttu-id="f7206-131">Name</span><span class="sxs-lookup"><span data-stu-id="f7206-131">Name</span></span>             | <span data-ttu-id="f7206-132">値</span><span class="sxs-lookup"><span data-stu-id="f7206-132">Value</span></span> |
|------------------|-------|
| <span data-ttu-id="f7206-133">[中断]</span><span class="sxs-lookup"><span data-stu-id="f7206-133">Suspend</span></span>          | <span data-ttu-id="f7206-134">5</span><span class="sxs-lookup"><span data-stu-id="f7206-134">5</span></span>     |
| <span data-ttu-id="f7206-135">Ignore</span><span class="sxs-lookup"><span data-stu-id="f7206-135">Ignore</span></span>           | <span data-ttu-id="f7206-136">4</span><span class="sxs-lookup"><span data-stu-id="f7206-136">4</span></span>     |
| <span data-ttu-id="f7206-137">照会</span><span class="sxs-lookup"><span data-stu-id="f7206-137">Inquire</span></span>          | <span data-ttu-id="f7206-138">3</span><span class="sxs-lookup"><span data-stu-id="f7206-138">3</span></span>     |
| <span data-ttu-id="f7206-139">続行</span><span class="sxs-lookup"><span data-stu-id="f7206-139">Continue</span></span>         | <span data-ttu-id="f7206-140">2</span><span class="sxs-lookup"><span data-stu-id="f7206-140">2</span></span>     |
| <span data-ttu-id="f7206-141">Stop</span><span class="sxs-lookup"><span data-stu-id="f7206-141">Stop</span></span>             | <span data-ttu-id="f7206-142">1</span><span class="sxs-lookup"><span data-stu-id="f7206-142">1</span></span>     |
| <span data-ttu-id="f7206-143">SilentlyContinue</span><span class="sxs-lookup"><span data-stu-id="f7206-143">SilentlyContinue</span></span> | <span data-ttu-id="f7206-144">0</span><span class="sxs-lookup"><span data-stu-id="f7206-144">0</span></span>     |

<span data-ttu-id="f7206-145">パラメーターと共に名前または値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7206-145">You may use the name or the value with the parameter.</span></span>

<span data-ttu-id="f7206-146">共通パラメーターに加えて、多くのコマンドレットには、リスク軽減パラメーターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f7206-146">In addition to the common parameters, many cmdlets offer risk mitigation parameters.</span></span> <span data-ttu-id="f7206-147">システムまたはユーザーデータに対するリスクが含まれるコマンドレットは、通常、これらのパラメーターを提供します。</span><span class="sxs-lookup"><span data-stu-id="f7206-147">Cmdlets that involve risk to the system or to user data usually offer these parameters.</span></span>

<span data-ttu-id="f7206-148">リスク軽減のパラメーターは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f7206-148">The risk mitigation parameters are:</span></span>

- <span data-ttu-id="f7206-149">**WhatIf** (wi-fi)</span><span class="sxs-lookup"><span data-stu-id="f7206-149">**WhatIf** (wi)</span></span>
- <span data-ttu-id="f7206-150">**確認** (cf)</span><span class="sxs-lookup"><span data-stu-id="f7206-150">**Confirm** (cf)</span></span>

### <a name="common-parameter-descriptions"></a><span data-ttu-id="f7206-151">共通パラメーターの説明</span><span class="sxs-lookup"><span data-stu-id="f7206-151">COMMON PARAMETER DESCRIPTIONS</span></span>

#### <a name="debug"></a><span data-ttu-id="f7206-152">デバッグ</span><span class="sxs-lookup"><span data-stu-id="f7206-152">Debug</span></span>

<span data-ttu-id="f7206-153">コマンドによって実行される操作に関するプログラマレベルの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="f7206-153">Displays programmer-level detail about the operation done by the command.</span></span> <span data-ttu-id="f7206-154">このパラメーターは、コマンドによってデバッグメッセージが生成された場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="f7206-154">This parameter works only when the command generates a debugging message.</span></span> <span data-ttu-id="f7206-155">たとえば、コマンドにコマンドレットが含まれている場合、このパラメーターは機能し `Write-Debug` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-155">For example, this parameter works when a command contains the `Write-Debug` cmdlet.</span></span>

```yaml
Type: SwitchParameter
Aliases: db

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="f7206-156">既定では、変数の値 `$DebugPreference` が **SilentlyContinue** であるため、デバッグメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="f7206-156">By default, debugging messages aren't displayed because the value of the `$DebugPreference` variable is **SilentlyContinue**.</span></span>

<span data-ttu-id="f7206-157">対話モードでは、 **Debug** パラメーターによって現在のコマンドの変数の値が上書きされ `$DebugPreference` 、の値が `$DebugPreference` **Inquire** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f7206-157">In interactive mode, the **Debug** parameter overrides the value of the `$DebugPreference` variable for the current command, setting the value of `$DebugPreference` to **Inquire**.</span></span>

<span data-ttu-id="f7206-158">非対話モードでは、 **Debug** パラメーターによって現在のコマンドの変数の値が上書きされ `$DebugPreference` 、の値 `$DebugPreference` が **Continue** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f7206-158">In non-interactive mode, the **Debug** parameter overrides the value of the `$DebugPreference` variable for the current command, setting the value of `$DebugPreference` to **Continue**.</span></span>

<span data-ttu-id="f7206-159">`-Debug:$true` と同じ効果があり `-Debug` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-159">`-Debug:$true` has the same effect as `-Debug`.</span></span> <span data-ttu-id="f7206-160">`-Debug:$false` `$DebugPreference` が **SilentlyContinue** ではない場合 (既定)、を使用して、デバッグメッセージの表示を抑制します。</span><span class="sxs-lookup"><span data-stu-id="f7206-160">Use `-Debug:$false` to suppress the display of debugging messages when `$DebugPreference` isn't **SilentlyContinue** , which is the default.</span></span>

#### <a name="erroraction"></a><span data-ttu-id="f7206-161">ErrorAction</span><span class="sxs-lookup"><span data-stu-id="f7206-161">ErrorAction</span></span>

<span data-ttu-id="f7206-162">コマンドレットが、コマンドから終了しないエラーに応答する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="f7206-162">Determines how the cmdlet responds to a non-terminating error from the command.</span></span>
<span data-ttu-id="f7206-163">このパラメーターは、コマンドがコマンドレットなどの終了しないエラーを生成した場合にのみ機能し `Write-Error` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-163">This parameter works only when the command generates a non-terminating error, such as those from the `Write-Error` cmdlet.</span></span>

```yaml
Type: ActionPreference
Aliases: ea
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="f7206-164">**Erroraction** パラメーターは、現在のコマンドの変数の値よりも優先され `$ErrorActionPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-164">The **ErrorAction** parameter overrides the value of the `$ErrorActionPreference` variable for the current command.</span></span> <span data-ttu-id="f7206-165">変数の既定値 `$ErrorActionPreference` は **続行** されるため、 **erroraction** パラメーターを使用しない限り、エラーメッセージが表示され、実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="f7206-165">Because the default value of the `$ErrorActionPreference` variable is **Continue** , error messages are displayed and execution continues unless you use the **ErrorAction** parameter.</span></span>

<span data-ttu-id="f7206-166">**Erroraction** パラメーターは、コマンドが正常に完了しないようにする、不足しているデータ、無効なパラメーター、権限の不足などの終了エラーには影響しません。</span><span class="sxs-lookup"><span data-stu-id="f7206-166">The **ErrorAction** parameter has no effect on terminating errors (such as missing data, parameters that aren't valid, or insufficient permissions) that prevent a command from completing successfully.</span></span>

<span data-ttu-id="f7206-167">`-ErrorAction:Continue` エラーメッセージを表示し、コマンドの実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="f7206-167">`-ErrorAction:Continue` display the error message and continues executing the command.</span></span> <span data-ttu-id="f7206-168">`Continue` は既定値です。</span><span class="sxs-lookup"><span data-stu-id="f7206-168">`Continue` is the default.</span></span>

<span data-ttu-id="f7206-169">`-ErrorAction:Ignore` エラーメッセージを表示せずに、コマンドの実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="f7206-169">`-ErrorAction:Ignore` suppresses the error message and continues executing the command.</span></span> <span data-ttu-id="f7206-170">**SilentlyContinue** とは異なり、 **Ignore** ではエラーメッセージが自動変数に追加されません `$Error` 。</span><span class="sxs-lookup"><span data-stu-id="f7206-170">Unlike **SilentlyContinue** , **Ignore** doesn't add the error message to the `$Error` automatic variable.</span></span> <span data-ttu-id="f7206-171">**Ignore** 値は、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f7206-171">The **Ignore** value is introduced in PowerShell 3.0.</span></span>

<span data-ttu-id="f7206-172">`-ErrorAction:Inquire` エラーメッセージを表示し、実行を続行する前に確認メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="f7206-172">`-ErrorAction:Inquire` displays the error message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="f7206-173">この値はほとんど使用されません。</span><span class="sxs-lookup"><span data-stu-id="f7206-173">This value is rarely used.</span></span>

<span data-ttu-id="f7206-174">`-ErrorAction:SilentlyContinue` エラーメッセージを表示せずに、コマンドの実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="f7206-174">`-ErrorAction:SilentlyContinue` suppresses the error message and continues executing the command.</span></span>

<span data-ttu-id="f7206-175">`-ErrorAction:Stop` エラーメッセージを表示し、コマンドの実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="f7206-175">`-ErrorAction:Stop` displays the error message and stops executing the command.</span></span>

<span data-ttu-id="f7206-176">`-ErrorAction:Suspend` は、PowerShell 6 以降ではサポートされていないワークフローでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f7206-176">`-ErrorAction:Suspend` is only available for workflows which aren't supported in PowerShell 6 and beyond.</span></span>

> [!NOTE]
> <span data-ttu-id="f7206-177">**Erroraction** パラメーターはをオーバーライドしますが、 `$ErrorAction` スクリプトまたは関数を実行するためにコマンドでパラメーターを使用する場合は、ユーザー設定変数の値を置き換えません。</span><span class="sxs-lookup"><span data-stu-id="f7206-177">The **ErrorAction** parameter overrides, but does not replace the value of the `$ErrorAction` preference variable when the parameter is used in a command to run a script or function.</span></span>

#### <a name="errorvariable"></a><span data-ttu-id="f7206-178">ErrorVariable</span><span class="sxs-lookup"><span data-stu-id="f7206-178">ErrorVariable</span></span>

<span data-ttu-id="f7206-179">**Errorvariable** は、コマンドに関するエラーメッセージを指定された変数と自動変数に格納し `$Error` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-179">**ErrorVariable** stores error messages about the command in the specified variable and in the `$Error` automatic variable.</span></span> <span data-ttu-id="f7206-180">詳細については、「」を参照してください [about_Automatic_Variables](about_Automatic_Variables.md)</span><span class="sxs-lookup"><span data-stu-id="f7206-180">For more information, see [about_Automatic_Variables](about_Automatic_Variables.md)</span></span>

```yaml
Type: String
Aliases: ev

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="f7206-181">既定では、新しいエラーメッセージは、変数に既に格納されているエラーメッセージを上書きします。</span><span class="sxs-lookup"><span data-stu-id="f7206-181">By default, new error messages overwrite error messages that are already stored in the variable.</span></span> <span data-ttu-id="f7206-182">変数の内容にエラーメッセージを追加するには、 `+` 変数名の前にプラス記号 () を入力します。</span><span class="sxs-lookup"><span data-stu-id="f7206-182">To append the error message to the variable content, type a plus sign (`+`) before the variable name.</span></span>

<span data-ttu-id="f7206-183">たとえば、次のコマンドは変数を作成し、 `$a` エラーを格納します。</span><span class="sxs-lookup"><span data-stu-id="f7206-183">For example, the following command creates the `$a` variable and then stores any errors in it:</span></span>

```powershell
Get-Process -Id 6 -ErrorVariable a
```

<span data-ttu-id="f7206-184">次のコマンドを実行すると、エラーメッセージが変数に追加され `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-184">The following command adds any error messages to the `$a` variable:</span></span>

```powershell
Get-Process -Id 2 -ErrorVariable +a
```

<span data-ttu-id="f7206-185">次のコマンドを実行すると、の内容が表示され `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-185">The following command displays the contents of `$a`:</span></span>

```powershell
$a
```

<span data-ttu-id="f7206-186">このパラメーターを使用すると、特定のコマンドからのエラーメッセージのみを含む変数を作成でき `$Error` ます。自動変数の動作には影響しません。</span><span class="sxs-lookup"><span data-stu-id="f7206-186">You can use this parameter to create a variable that contains only error messages from specific commands and does not affect the behavior of the `$Error` automatic variable.</span></span> <span data-ttu-id="f7206-187">自動変数には、 `$Error` セッション内のすべてのコマンドからのエラーメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7206-187">The `$Error` automatic variable contains error messages from all the commands in the session.</span></span> <span data-ttu-id="f7206-188">やなどの配列表記を使用して、 `$a[0]` `$error[1,2]` 変数に格納されている特定のエラーを参照することができます。</span><span class="sxs-lookup"><span data-stu-id="f7206-188">You can use array notation, such as `$a[0]` or `$error[1,2]` to refer to specific errors stored in the variables.</span></span>

> [!NOTE]
> <span data-ttu-id="f7206-189">カスタムエラー変数には、入れ子になった関数またはスクリプトの呼び出しからのエラーを含め、コマンドによって生成されたすべてのエラーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f7206-189">The custom error variable contains all errors generated by the command, including errors from calls to nested functions or scripts.</span></span>

#### <a name="informationaction"></a><span data-ttu-id="f7206-190">InformationAction</span><span class="sxs-lookup"><span data-stu-id="f7206-190">InformationAction</span></span>

<span data-ttu-id="f7206-191">PowerShell 5.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f7206-191">Introduced in PowerShell 5.0.</span></span> <span data-ttu-id="f7206-192">使用されているコマンドまたはスクリプト内で、 **Informationaction** 共通パラメーターは、 `$InformationPreference` 既定では **SilentlyContinue** に設定されているユーザー設定変数の値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="f7206-192">Within the command or script in which it's used, the **InformationAction** common parameter overrides the value of the `$InformationPreference` preference variable, which by default is set to **SilentlyContinue**.</span></span> <span data-ttu-id="f7206-193">`Write-Information` **Informationaction** を含むスクリプトでを使用すると、 `Write-Information` **informationaction** パラメーターの値に応じて値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7206-193">When you use `Write-Information` in a script with **InformationAction** , `Write-Information` values are shown depending on the value of the **InformationAction** parameter.</span></span> <span data-ttu-id="f7206-194">の詳細について `$InformationPreference` は、「 [about_Preference_Variables](./about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7206-194">For more information about `$InformationPreference`, see [about_Preference_Variables](./about_Preference_Variables.md).</span></span>

```yaml
Type: ActionPreference
Aliases: ia
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="f7206-195">`-InformationAction:Stop` コマンドが発生したときに、コマンドまたはスクリプトを停止し `Write-Information` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-195">`-InformationAction:Stop` stops a command or script at an occurrence of the `Write-Information` command.</span></span>

<span data-ttu-id="f7206-196">`-InformationAction:Ignore` 情報メッセージを表示せずに、コマンドの実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="f7206-196">`-InformationAction:Ignore` suppresses the informational message and continues running the command.</span></span> <span data-ttu-id="f7206-197">**SilentlyContinue** とは異なり、情報メッセージを完全には **無視** します。情報メッセージは情報ストリームに追加されません。</span><span class="sxs-lookup"><span data-stu-id="f7206-197">Unlike **SilentlyContinue** , **Ignore** completely forgets the informational message; it doesn't add the informational message to the information stream.</span></span>

<span data-ttu-id="f7206-198">`-InformationAction:Inquire` コマンドで指定した情報メッセージを表示し、 `Write-Information` 続行するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7206-198">`-InformationAction:Inquire` displays the informational message that you specify in a `Write-Information` command, then asks whether you want to continue.</span></span>

<span data-ttu-id="f7206-199">`-InformationAction:Continue` 情報メッセージを表示し、実行を継続します。</span><span class="sxs-lookup"><span data-stu-id="f7206-199">`-InformationAction:Continue` displays the informational message, and continues running.</span></span>

<span data-ttu-id="f7206-200">`-InformationAction:Suspend` は、ワークフローでのみ使用できるため、PowerShell Core ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f7206-200">`-InformationAction:Suspend` isn't supported on PowerShell Core as it is only available for workflows.</span></span>

<span data-ttu-id="f7206-201">`-InformationAction:SilentlyContinue` 情報メッセージが (既定値) 表示されないため、スクリプトは中断されることなく続行されます。</span><span class="sxs-lookup"><span data-stu-id="f7206-201">`-InformationAction:SilentlyContinue` no effect as the informational message aren't (Default) displayed, and the script continues without interruption.</span></span>

> [!NOTE]
> <span data-ttu-id="f7206-202">**Informationaction** パラメーターはをオーバーライドしますが、 `$InformationAction` スクリプトまたは関数を実行するためにコマンドでパラメーターを使用する場合は、ユーザー設定変数の値を置き換えません。</span><span class="sxs-lookup"><span data-stu-id="f7206-202">The **InformationAction** parameter overrides, but does not replace the value of the `$InformationAction` preference variable when the parameter is used in a command to run a script or function.</span></span>

#### <a name="informationvariable"></a><span data-ttu-id="f7206-203">InformationVariable</span><span class="sxs-lookup"><span data-stu-id="f7206-203">InformationVariable</span></span>

<span data-ttu-id="f7206-204">PowerShell 5.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f7206-204">Introduced in PowerShell 5.0.</span></span> <span data-ttu-id="f7206-205">使用されているコマンドまたはスクリプト内で、 **informationvariable** 共通パラメーターは、コマンドを追加して指定した文字列を変数に格納し `Write-Information` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-205">Within the command or script in which it's used, the **InformationVariable** common parameter stores in a variable a string that you specify by adding the `Write-Information` command.</span></span> <span data-ttu-id="f7206-206">`Write-Information` 値は、 **Informationaction** 共通パラメーターの値に応じて表示されます。 **Informationaction** 共通パラメーターを追加しない場合は、ユーザー `Write-Information` 設定変数の値に応じて文字列が表示され `$InformationPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-206">`Write-Information` values are shown depending on the value of the **InformationAction** common parameter; if you don't add the **InformationAction** common parameter, `Write-Information` strings are shown depending on the value of the `$InformationPreference` preference variable.</span></span> <span data-ttu-id="f7206-207">の詳細について `$InformationPreference` は、「 [about_Preference_Variables](./about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7206-207">For more information about `$InformationPreference`, see [about_Preference_Variables](./about_Preference_Variables.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f7206-208">情報変数には、入れ子になった関数またはスクリプトの呼び出しからの情報メッセージを含め、コマンドによって生成されたすべての情報メッセージが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f7206-208">The information variable contains all information messages generated by the command, including information messages from calls to nested functions or scripts.</span></span>

```yaml
Type: String
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

#### <a name="outbuffer"></a><span data-ttu-id="f7206-209">OutBuffer</span><span class="sxs-lookup"><span data-stu-id="f7206-209">OutBuffer</span></span>

<span data-ttu-id="f7206-210">オブジェクトがパイプラインを介して送信される前に、バッファーに蓄積されるオブジェクトの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="f7206-210">Determines the number of objects to accumulate in a buffer before any objects are sent through the pipeline.</span></span> <span data-ttu-id="f7206-211">このパラメーターを省略すると、オブジェクトは生成時に送信されます。</span><span class="sxs-lookup"><span data-stu-id="f7206-211">If you omit this parameter, objects are sent as they're generated.</span></span>

```yaml
Type: Int32
Aliases: ob

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="f7206-212">このリソース管理パラメーターは、上級ユーザー向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="f7206-212">This resource management parameter is designed for advanced users.</span></span> <span data-ttu-id="f7206-213">このパラメーターを使用すると、PowerShell はのバッチで次のコマンドレットにデータを送信 `OutBuffer + 1` します。</span><span class="sxs-lookup"><span data-stu-id="f7206-213">When you use this parameter, PowerShell sends data to the next cmdlet in batches of `OutBuffer + 1`.</span></span>

<span data-ttu-id="f7206-214">次の例では、コマンドレットを使用するプロセスブロックとの間でが交互に表示され `ForEach-Object` `Write-Host` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-214">The following example alternates displays between to `ForEach-Object` process blocks that use the `Write-Host` cmdlet.</span></span> <span data-ttu-id="f7206-215">ディスプレイは、2またはのバッチで交互に表示され `OutBuffer + 1` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-215">The display alternates in batches of 2 or `OutBuffer + 1`.</span></span>

```powershell
1..4 | ForEach-Object {
        Write-Host "$($_): First"; $_
      } -OutBuffer 1 | ForEach-Object {
                        Write-Host "$($_): Second" }
```

```Output
1: First
2: First
1: Second
2: Second
3: First
4: First
3: Second
4: Second
```

#### <a name="outvariable"></a><span data-ttu-id="f7206-216">OutVariable</span><span class="sxs-lookup"><span data-stu-id="f7206-216">OutVariable</span></span>

<span data-ttu-id="f7206-217">パイプラインに沿って出力を送信するだけでなく、指定した変数のコマンドからの出力オブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="f7206-217">Stores output objects from the command in the specified variable in addition to sending the output along the pipeline.</span></span>

```yaml
Type: String
Aliases: ov

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="f7206-218">出力を変数に追加するには、既に格納されている可能性のある出力を置き換えるのではなく、 `+` 変数名の前にプラス記号 () を入力します。</span><span class="sxs-lookup"><span data-stu-id="f7206-218">To add the output to the variable, instead of replacing any output that might already be stored there, type a plus sign (`+`) before the variable name.</span></span>

<span data-ttu-id="f7206-219">たとえば、次のコマンドは、変数を作成 `$out` し、その中に process オブジェクトを格納します。</span><span class="sxs-lookup"><span data-stu-id="f7206-219">For example, the following command creates the `$out` variable and stores the process object in it:</span></span>

```powershell
Get-Process PowerShell -OutVariable out
```

<span data-ttu-id="f7206-220">次のコマンドを実行すると、process オブジェクトが変数に追加され `$out` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-220">The following command adds the process object to the `$out` variable:</span></span>

```powershell
Get-Process iexplore -OutVariable +out
```

<span data-ttu-id="f7206-221">次のコマンドを実行すると、変数の内容が表示され `$out` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-221">The following command displays the contents of the `$out` variable:</span></span>

```powershell
$out
```

> [!NOTE]
> <span data-ttu-id="f7206-222">**Outvariable** パラメーターによって作成された変数は `[System.Collections.ArrayList]` です。</span><span class="sxs-lookup"><span data-stu-id="f7206-222">The variable created by the **OutVariable** parameter is a `[System.Collections.ArrayList]`.</span></span>

#### <a name="pipelinevariable"></a><span data-ttu-id="f7206-223">PipelineVariable</span><span class="sxs-lookup"><span data-stu-id="f7206-223">PipelineVariable</span></span>

<span data-ttu-id="f7206-224">**PipelineVariable** は、現在のパイプライン要素の値を変数として格納します。これは、パイプラインを介してフローする任意の名前付きコマンドに使用します。</span><span class="sxs-lookup"><span data-stu-id="f7206-224">**PipelineVariable** stores the value of the current pipeline element as a variable, for any named command as it flows through the pipeline.</span></span>

```yaml
Type: String
Aliases: pv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="f7206-225">有効な値は文字列で、任意の変数名と同じです。</span><span class="sxs-lookup"><span data-stu-id="f7206-225">Valid values are strings, the same as for any variable names.</span></span>

<span data-ttu-id="f7206-226">**PipelineVariable** の動作の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f7206-226">The following is an example of how **PipelineVariable** works.</span></span> <span data-ttu-id="f7206-227">この例では、 **PipelineVariable** コマンド `Foreach-Object` の結果を変数に格納するために、PipelineVariable パラメーターがコマンドに追加されています。</span><span class="sxs-lookup"><span data-stu-id="f7206-227">In this example, the **PipelineVariable** parameter is added to a `Foreach-Object` command to store the results of the command in variables.</span></span> <span data-ttu-id="f7206-228">1 ~ 10 の範囲の数値は最初のコマンドにパイプされ `Foreach-Object` 、その結果は **Left** という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="f7206-228">A range of numbers, 1 to 10, are piped into the first `Foreach-Object` command, the results of which are stored in a variable named **Left**.</span></span>

<span data-ttu-id="f7206-229">最初のコマンドの結果は、 `Foreach-Object` 2 番目のコマンドにパイプされ `Foreach-Object` ます。このコマンドは、最初のコマンドによって返されたオブジェクトをフィルター処理し `Foreach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-229">The results of the first `Foreach-Object` command are piped into a second `Foreach-Object` command, which filters the objects returned by the first `Foreach-Object` command.</span></span> <span data-ttu-id="f7206-230">2番目のコマンドの結果は、 **Right** という名前の変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="f7206-230">The results of the second command are stored in a variable named **Right**.</span></span>

<span data-ttu-id="f7206-231">3番目のコマンドでは、 `Foreach-Object` 変数によって表される最初の2つのパイプされたコマンドの結果 `Foreach-Object` が、乗算演算子を使用して処理されます。 **Left** **Right**</span><span class="sxs-lookup"><span data-stu-id="f7206-231">In the third `Foreach-Object` command, the results of the first two `Foreach-Object` piped commands, represented by the variables **Left** and **Right** , are processed by using a multiplication operator.</span></span> <span data-ttu-id="f7206-232">このコマンドは、 **左** と **右** の変数に格納されているオブジェクトに乗算するように指示し、結果を "左辺の範囲メンバー \* 右範囲メンバー = 製品" として表示するように指定します。</span><span class="sxs-lookup"><span data-stu-id="f7206-232">The command instructs objects stored in the **Left** and **Right** variables to be multiplied, and specifies that the results should be displayed as "Left range member \* Right range member = product".</span></span>

```powershell
1..10 | Foreach-Object -PipelineVariable Left -Process { $_ } |
  Foreach-Object -PV Right -Process { 1..10 } |
  Foreach-Object -Process { "$Left * $Right = " + ($Left*$Right) }
```

```output
1 * 1 = 1
1 * 2 = 2
1 * 3 = 3
1 * 4 = 4
1 * 5 = 5
...
```

#### <a name="verbose"></a><span data-ttu-id="f7206-233">"詳細"</span><span class="sxs-lookup"><span data-stu-id="f7206-233">Verbose</span></span>

<span data-ttu-id="f7206-234">コマンドによって実行された操作に関する詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f7206-234">Displays detailed information about the operation done by the command.</span></span> <span data-ttu-id="f7206-235">この情報は、トレースまたはトランザクションログの情報に似ています。</span><span class="sxs-lookup"><span data-stu-id="f7206-235">This information resembles the information in a trace or in a transaction log.</span></span> <span data-ttu-id="f7206-236">このパラメーターは、コマンドによって詳細メッセージが生成された場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="f7206-236">This parameter works only when the command generates a verbose message.</span></span> <span data-ttu-id="f7206-237">たとえば、コマンドにコマンドレットが含まれている場合、このパラメーターは機能し `Write-Verbose` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-237">For example, this parameter works when a command contains the `Write-Verbose` cmdlet.</span></span>

```yaml
Type: SwitchParameter
Aliases: vb

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="f7206-238">**Verbose** パラメーターは、現在のコマンドの変数の値よりも優先され `$VerbosePreference` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-238">The **Verbose** parameter overrides the value of the `$VerbosePreference` variable for the current command.</span></span> <span data-ttu-id="f7206-239">変数の既定値 `$VerbosePreference` は **SilentlyContinue** であるため、詳細メッセージは既定では表示されません。</span><span class="sxs-lookup"><span data-stu-id="f7206-239">Because the default value of the `$VerbosePreference` variable is **SilentlyContinue** , verbose messages aren't displayed by default.</span></span>

<span data-ttu-id="f7206-240">`-Verbose:$true` と同じ効果があります。 `-Verbose`</span><span class="sxs-lookup"><span data-stu-id="f7206-240">`-Verbose:$true` has the same effect as `-Verbose`</span></span>

<span data-ttu-id="f7206-241">`-Verbose:$false` 詳細メッセージの表示を抑制します。</span><span class="sxs-lookup"><span data-stu-id="f7206-241">`-Verbose:$false` suppresses the display of verbose messages.</span></span> <span data-ttu-id="f7206-242">の値が SilentlyContinue (既定値) でない場合に、このパラメーターを使用し `$VerbosePreference` ます。 **SilentlyContinue**</span><span class="sxs-lookup"><span data-stu-id="f7206-242">Use this parameter when the value of `$VerbosePreference` isn't **SilentlyContinue** (the default).</span></span>

#### <a name="warningaction"></a><span data-ttu-id="f7206-243">WarningAction</span><span class="sxs-lookup"><span data-stu-id="f7206-243">WarningAction</span></span>

<span data-ttu-id="f7206-244">コマンドレットがコマンドからの警告に応答する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="f7206-244">Determines how the cmdlet responds to a warning from the command.</span></span> <span data-ttu-id="f7206-245">**Continue** が既定値です。</span><span class="sxs-lookup"><span data-stu-id="f7206-245">**Continue** is the default value.</span></span> <span data-ttu-id="f7206-246">このパラメーターは、コマンドで警告メッセージが生成された場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="f7206-246">This parameter works only when the command generates a warning message.</span></span> <span data-ttu-id="f7206-247">たとえば、コマンドにコマンドレットが含まれている場合、このパラメーターは機能し `Write-Warning` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-247">For example, this parameter works when a command contains the `Write-Warning` cmdlet.</span></span>

```yaml
Type: ActionPreference
Aliases: wa
Accepted values: Suspend, Ignore, Inquire, Continue, Stop, SilentlyContinue

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="f7206-248">**Warnings action** パラメーターは、現在のコマンドの変数の値よりも優先され `$WarningPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-248">The **WarningAction** parameter overrides the value of the `$WarningPreference` variable for the current command.</span></span> <span data-ttu-id="f7206-249">変数の既定値 `$WarningPreference` は **Continue** であるため、 **warnings action** パラメーターを使用しない限り、警告が表示され、実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="f7206-249">Because the default value of the `$WarningPreference` variable is **Continue** , warnings are displayed and execution continues unless you use the **WarningAction** parameter.</span></span>

<span data-ttu-id="f7206-250">`-WarningAction:Continue` 警告メッセージを表示し、コマンドの実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="f7206-250">`-WarningAction:Continue` displays the warning messages and continues executing the command.</span></span> <span data-ttu-id="f7206-251">`Continue` は既定値です。</span><span class="sxs-lookup"><span data-stu-id="f7206-251">`Continue` is the default.</span></span>

<span data-ttu-id="f7206-252">`-WarningAction:Inquire` 警告メッセージを表示し、実行を続行する前に確認メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="f7206-252">`-WarningAction:Inquire` displays the warning message and prompts you for confirmation before continuing execution.</span></span> <span data-ttu-id="f7206-253">この値はほとんど使用されません。</span><span class="sxs-lookup"><span data-stu-id="f7206-253">This value is rarely used.</span></span>

<span data-ttu-id="f7206-254">`-WarningAction:SilentlyContinue` 警告メッセージを表示せずに、コマンドの実行を続行します。</span><span class="sxs-lookup"><span data-stu-id="f7206-254">`-WarningAction:SilentlyContinue` suppresses the warning message and continues executing the command.</span></span>

<span data-ttu-id="f7206-255">`-WarningAction:Stop` 警告メッセージを表示し、コマンドの実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="f7206-255">`-WarningAction:Stop` displays the warning message and stops executing the command.</span></span>

> [!NOTE]
> <span data-ttu-id="f7206-256">**警告動作** パラメーターはをオーバーライドしますが、 `$WarningAction` スクリプトまたは関数を実行するためにコマンドでパラメーターを使用する場合は、ユーザー設定変数の値を置き換えません。</span><span class="sxs-lookup"><span data-stu-id="f7206-256">The **WarningAction** parameter overrides, but does not replace the value of the `$WarningAction` preference variable when the parameter is used in a command to run a script or function.</span></span>

#### <a name="warningvariable"></a><span data-ttu-id="f7206-257">WarningVariable</span><span class="sxs-lookup"><span data-stu-id="f7206-257">WarningVariable</span></span>

<span data-ttu-id="f7206-258">指定された変数にコマンドに関する警告を格納します。</span><span class="sxs-lookup"><span data-stu-id="f7206-258">Stores warnings about the command in the specified variable.</span></span>

```yaml
Type: String
Aliases: wv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="f7206-259">警告がユーザーに表示されない場合でも、生成されたすべての警告は変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="f7206-259">All generated warnings are saved in the variable even if the warnings aren't displayed to the user.</span></span>

<span data-ttu-id="f7206-260">警告を変数の内容に追加するには、既に格納されている可能性のある警告を置き換えるのではなく、 `+` 変数名の前にプラス記号 () を入力します。</span><span class="sxs-lookup"><span data-stu-id="f7206-260">To append the warnings to the variable content, instead of replacing any warnings that might already be stored there, type a plus sign (`+`) before the variable name.</span></span>

<span data-ttu-id="f7206-261">たとえば、次のコマンドは変数を作成し、 `$a` 警告を格納します。</span><span class="sxs-lookup"><span data-stu-id="f7206-261">For example, the following command creates the `$a` variable and then stores any warnings in it:</span></span>

```powershell
Get-Process -Id 6 -WarningVariable a
```

<span data-ttu-id="f7206-262">次のコマンドは、変数に警告を追加し `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-262">The following command adds any warnings to the `$a` variable:</span></span>

```powershell
Get-Process -Id 2 -WarningVariable +a
```

<span data-ttu-id="f7206-263">次のコマンドを実行すると、の内容が表示され `$a` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-263">The following command displays the contents of `$a`:</span></span>

```powershell
$a
```

<span data-ttu-id="f7206-264">このパラメーターを使用すると、特定のコマンドからの警告のみを含む変数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="f7206-264">You can use this parameter to create a variable that contains only warnings from specific commands.</span></span> <span data-ttu-id="f7206-265">やなどの配列表記を使用して、 `$a[0]` `$warning[1,2]` 変数に格納されている特定の警告を参照することができます。</span><span class="sxs-lookup"><span data-stu-id="f7206-265">You can use array notation, such as `$a[0]` or `$warning[1,2]` to refer to specific warnings stored in the variable.</span></span>

> [!NOTE]
> <span data-ttu-id="f7206-266">警告変数には、入れ子になった関数またはスクリプトの呼び出しからの警告など、コマンドによって生成されるすべての警告が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f7206-266">The warning variable contains all warnings generated by the command, including warnings from calls to nested functions or scripts.</span></span>

### <a name="risk-management-parameter-descriptions"></a><span data-ttu-id="f7206-267">リスク管理のパラメーターの説明</span><span class="sxs-lookup"><span data-stu-id="f7206-267">Risk Management Parameter Descriptions</span></span>

#### <a name="whatif"></a><span data-ttu-id="f7206-268">WhatIf</span><span class="sxs-lookup"><span data-stu-id="f7206-268">WhatIf</span></span>

<span data-ttu-id="f7206-269">コマンドを実行する代わりに、コマンドの効果を説明するメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="f7206-269">Displays a message that describes the effect of the command, instead of executing the command.</span></span>

```yaml
Type: SwitchParameter
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="f7206-270">**WhatIf** パラメーターは、現在のコマンドの変数の値よりも優先され `$WhatIfPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-270">The **WhatIf** parameter overrides the value of the `$WhatIfPreference` variable for the current command.</span></span> <span data-ttu-id="f7206-271">変数の既定値 `$WhatIfPreference` は 0 (無効) であるため、whatif パラメーターを指定しない **WhatIf** と **whatif** 動作は実行されません。</span><span class="sxs-lookup"><span data-stu-id="f7206-271">Because the default value of the `$WhatIfPreference` variable is 0 (disabled), **WhatIf** behavior isn't done without the **WhatIf** parameter.</span></span> <span data-ttu-id="f7206-272">詳細については、「」を参照してください [about_Preference_Variables](about_Preference_Variables.md)</span><span class="sxs-lookup"><span data-stu-id="f7206-272">For more information, see [about_Preference_Variables](about_Preference_Variables.md)</span></span>

<span data-ttu-id="f7206-273">`-WhatIf:$true` と同じ効果があり `-WhatIf` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-273">`-WhatIf:$true` has the same effect as `-WhatIf`.</span></span>

<span data-ttu-id="f7206-274">`-WhatIf:$false` 変数の値が1の場合に生成される自動 WhatIf 動作を抑制し `$WhatIfPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-274">`-WhatIf:$false` suppresses the automatic WhatIf behavior that results when the value of the `$WhatIfPreference` variable is 1.</span></span>

<span data-ttu-id="f7206-275">たとえば、次のコマンドでは、 `-WhatIf` コマンドでパラメーターを使用し `Remove-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-275">For example, the following command uses the `-WhatIf` parameter in a `Remove-Item` command:</span></span>

```powershell
Remove-Item Date.csv -WhatIf
```

<span data-ttu-id="f7206-276">PowerShell では、項目を削除する代わりに、実行する操作と影響を受ける項目が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7206-276">Instead of removing the item, PowerShell lists the operations it would do and the items that would be affected.</span></span> <span data-ttu-id="f7206-277">このコマンドでは次の出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="f7206-277">This command produces the following output:</span></span>

```output
What if: Performing operation "Remove File" on
Target "C:\ps-test\date.csv".
```

#### <a name="confirm"></a><span data-ttu-id="f7206-278">Confirm</span><span class="sxs-lookup"><span data-stu-id="f7206-278">Confirm</span></span>

<span data-ttu-id="f7206-279">コマンドを実行する前に確認メッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="f7206-279">Prompts you for confirmation before executing the command.</span></span>

```yaml
Type: SwitchParameter
Aliases: cf

Required: False
Position: Named
Default value: Depends on preference variable
Accept pipeline input: False
Accept wildcard characters: False
```

<span data-ttu-id="f7206-280">**Confirm** パラメーターは、現在のコマンドの変数の値よりも優先され `$ConfirmPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-280">The **Confirm** parameter overrides the value of the `$ConfirmPreference` variable for the current command.</span></span> <span data-ttu-id="f7206-281">既定値は、true です。</span><span class="sxs-lookup"><span data-stu-id="f7206-281">The default value is true.</span></span> <span data-ttu-id="f7206-282">詳細については、「」を参照してください [about_Preference_Variables](about_Preference_Variables.md)</span><span class="sxs-lookup"><span data-stu-id="f7206-282">For more information, see [about_Preference_Variables](about_Preference_Variables.md)</span></span>

<span data-ttu-id="f7206-283">`-Confirm:$true` と同じ効果があり `-Confirm` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-283">`-Confirm:$true` has the same effect as `-Confirm`.</span></span>

<span data-ttu-id="f7206-284">`-Confirm:$false` 自動確認を抑制します。これは、の値 `$ConfirmPreference` がコマンドレットの推定リスク以下である場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="f7206-284">`-Confirm:$false` suppresses automatic confirmation, which occurs when the value of `$ConfirmPreference` is less than or equal to the estimated risk of the cmdlet.</span></span>

<span data-ttu-id="f7206-285">たとえば、次のコマンドでは、 **Confirm** パラメーターをコマンドと共に使用し `Remove-Item` ます。</span><span class="sxs-lookup"><span data-stu-id="f7206-285">For example, the following command uses the **Confirm** parameter with a `Remove-Item` command.</span></span> <span data-ttu-id="f7206-286">項目を削除する前に、PowerShell によって実行される操作と影響を受ける項目が一覧表示され、承認が求められます。</span><span class="sxs-lookup"><span data-stu-id="f7206-286">Before removing the item, PowerShell lists the operations it would do and the items that would be affected, and asks for approval.</span></span>

```
PS C:\ps-test> Remove-Item tmp*.txt -Confirm

Confirm
Are you sure you want to perform this action?
Performing operation "Remove File" on Target " C:\ps-test\tmp1.txt
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend
[?] Help (default is "Y"):
```

<span data-ttu-id="f7206-287">Confirm response オプションは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f7206-287">The Confirm response options are as follows:</span></span>

|<span data-ttu-id="f7206-288">Response</span><span class="sxs-lookup"><span data-stu-id="f7206-288">Response</span></span>       |<span data-ttu-id="f7206-289">結果</span><span class="sxs-lookup"><span data-stu-id="f7206-289">Result</span></span>                                                     |
|---------------|-----------------------------------------------------------|
|<span data-ttu-id="f7206-290">はい (Y)</span><span class="sxs-lookup"><span data-stu-id="f7206-290">Yes (Y)</span></span>        |<span data-ttu-id="f7206-291">アクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7206-291">Perform the action.</span></span>                                        |
|<span data-ttu-id="f7206-292">すべてはい (A)</span><span class="sxs-lookup"><span data-stu-id="f7206-292">Yes to All (A)</span></span> |<span data-ttu-id="f7206-293">すべてのアクションを実行し、後続のクエリの確認を抑制する</span><span class="sxs-lookup"><span data-stu-id="f7206-293">Perform all actions and suppress subsequent Confirm queries</span></span>|
|               |<span data-ttu-id="f7206-294">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="f7206-294">for this command.</span></span>                                          |
|<span data-ttu-id="f7206-295">いいえ (N):</span><span class="sxs-lookup"><span data-stu-id="f7206-295">No (N):</span></span>        |<span data-ttu-id="f7206-296">操作は実行しないでください。</span><span class="sxs-lookup"><span data-stu-id="f7206-296">Do not perform the action.</span></span>                                 |
|<span data-ttu-id="f7206-297">すべていいえ (L):</span><span class="sxs-lookup"><span data-stu-id="f7206-297">No to All (L):</span></span> |<span data-ttu-id="f7206-298">アクションを実行せず、その後の確認を抑制する</span><span class="sxs-lookup"><span data-stu-id="f7206-298">Do not perform any actions and suppress subsequent Confirm</span></span> |
|               |<span data-ttu-id="f7206-299">このコマンドを照会します。</span><span class="sxs-lookup"><span data-stu-id="f7206-299">queries for this command.</span></span>                                  |
|<span data-ttu-id="f7206-300">中断 (S):</span><span class="sxs-lookup"><span data-stu-id="f7206-300">Suspend (S):</span></span>   |<span data-ttu-id="f7206-301">コマンドを一時停止し、一時的なセッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7206-301">Pause the command and create a temporary session.</span></span>          |
|<span data-ttu-id="f7206-302">ヘルプ (?)</span><span class="sxs-lookup"><span data-stu-id="f7206-302">Help (?)</span></span>       |<span data-ttu-id="f7206-303">これらのオプションのヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="f7206-303">Display help for these options.</span></span>                            |

<span data-ttu-id="f7206-304">**Suspend** オプションを指定すると、コマンドが保留状態になり、一時的な入れ子になったセッションが作成されます。このセッションでは、[ **確認** ] オプションを選択する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="f7206-304">The **Suspend** option places the command on hold and creates a temporary nested session in which you can work until you're ready to choose a **Confirm** option.</span></span> <span data-ttu-id="f7206-305">入れ子になったセッションのコマンドプロンプトには、元の親コマンドの子操作であることを示すために、2つの追加のキャレット (>>) があります。</span><span class="sxs-lookup"><span data-stu-id="f7206-305">The command prompt for the nested session has two extra carets (>>) to indicate that it's a child operation of the original parent command.</span></span> <span data-ttu-id="f7206-306">入れ子になったセッションでは、コマンドとスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f7206-306">You can run commands and scripts in the nested session.</span></span> <span data-ttu-id="f7206-307">入れ子になったセッションを終了し、元のコマンドの Confirm オプションに戻るには、「exit」と入力します。</span><span class="sxs-lookup"><span data-stu-id="f7206-307">To end the nested session and return to the Confirm options for the original command, type "exit".</span></span>

<span data-ttu-id="f7206-308">次の例では、ユーザーがコマンドパラメーターのヘルプを確認している間に、 **Suspend** オプションを使用してコマンドを一時的に停止しています。</span><span class="sxs-lookup"><span data-stu-id="f7206-308">In the following example, the **Suspend** option (S) is used to halt a command temporarily while the user checks the help for a command parameter.</span></span> <span data-ttu-id="f7206-309">ユーザーは必要な情報を取得した後、"exit" を入力して入れ子になったプロンプトを終了し、確認クエリに対して [はい] (y) の応答を選択します。</span><span class="sxs-lookup"><span data-stu-id="f7206-309">After obtaining the needed information, the user types "exit" to end the nested prompt and then selects the Yes (y) response to the Confirm query.</span></span>

```
PS C:\ps-test> New-Item -ItemType File -Name Test.txt -Confirm

Confirm
Are you sure you want to perform this action?

Performing operation "Create File" on Target "Destination:
C:\ps-test\test.txt".
[Y] Yes [A] Yes to All [N] No [L] No to All [S] Suspend [?] Help (default
is "Y"): s

PS C:\ps-test> Get-Help New-Item -Parameter ItemType

-ItemType <string>
Specifies the provider-specified type of the new item.

Required?                    false
Position?                    named
Default value
Accept pipeline input?       true (ByPropertyName)
Accept wildcard characters?  false

PS C:\ps-test> exit

Confirm
Are you sure you want to perform this action?
Performing operation "Create File" on Target "Destination: C:\ps-test\test
.txt".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (defau
lt is "Y"): y

Directory: C:\ps-test

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---         8/27/2010   2:41 PM          0 test.txt
```

## <a name="keywords"></a><span data-ttu-id="f7206-310">KEYWORDS</span><span class="sxs-lookup"><span data-stu-id="f7206-310">KEYWORDS</span></span>

<span data-ttu-id="f7206-311">about_Common_Parameters</span><span class="sxs-lookup"><span data-stu-id="f7206-311">about_Common_Parameters</span></span>

## <a name="see-also"></a><span data-ttu-id="f7206-312">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7206-312">SEE ALSO</span></span>

[<span data-ttu-id="f7206-313">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="f7206-313">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="f7206-314">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="f7206-314">Write-Debug</span></span>](xref:Microsoft.PowerShell.Utility.Write-Debug)

[<span data-ttu-id="f7206-315">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="f7206-315">Write-Warning</span></span>](xref:Microsoft.PowerShell.Utility.Write-Warning)

[<span data-ttu-id="f7206-316">書き込み-エラー</span><span class="sxs-lookup"><span data-stu-id="f7206-316">Write-Error</span></span>](xref:Microsoft.PowerShell.Utility.Write-Error)

[<span data-ttu-id="f7206-317">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="f7206-317">Write-Verbose</span></span>](xref:Microsoft.PowerShell.Utility.Write-Verbose)
