---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 03/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-executionpolicy?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExecutionPolicy
ms.openlocfilehash: d6555f1abc824add4613654461106af34045e1a3
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602755"
---
# <span data-ttu-id="ff046-102">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="ff046-102">Get-ExecutionPolicy</span></span>

## <span data-ttu-id="ff046-103">概要</span><span class="sxs-lookup"><span data-stu-id="ff046-103">SYNOPSIS</span></span>
<span data-ttu-id="ff046-104">現在のセッションの実行ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="ff046-104">Gets the execution policies for the current session.</span></span>

## <span data-ttu-id="ff046-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ff046-105">SYNTAX</span></span>

### <span data-ttu-id="ff046-106">すべて</span><span class="sxs-lookup"><span data-stu-id="ff046-106">All</span></span>

```
Get-ExecutionPolicy [[-Scope] <ExecutionPolicyScope>] [-List] [<CommonParameters>]
```

## <span data-ttu-id="ff046-107">Description</span><span class="sxs-lookup"><span data-stu-id="ff046-107">DESCRIPTION</span></span>

<span data-ttu-id="ff046-108">各スコープの実行ポリシーを優先順位に従って表示するには、を使用 `Get-ExecutionPolicy -List` します。</span><span class="sxs-lookup"><span data-stu-id="ff046-108">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="ff046-109">PowerShell セッションの有効な実行ポリシーを確認するには、 `Get-ExecutionPolicy` パラメーターなしで使用します。</span><span class="sxs-lookup"><span data-stu-id="ff046-109">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

<span data-ttu-id="ff046-110">有効な実行ポリシーは、およびグループポリシー設定によって設定される実行ポリシーによって決定され `Set-ExecutionPolicy` ます。</span><span class="sxs-lookup"><span data-stu-id="ff046-110">The effective execution policy is determined by execution policies that are set by `Set-ExecutionPolicy` and Group Policy settings.</span></span>

<span data-ttu-id="ff046-111">詳細については、「[about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff046-111">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="ff046-112">例</span><span class="sxs-lookup"><span data-stu-id="ff046-112">EXAMPLES</span></span>

### <span data-ttu-id="ff046-113">例 1: すべての実行ポリシーを取得する</span><span class="sxs-lookup"><span data-stu-id="ff046-113">Example 1: Get all execution policies</span></span>

<span data-ttu-id="ff046-114">このコマンドは、各スコープの実行ポリシーを優先順位順に表示します。</span><span class="sxs-lookup"><span data-stu-id="ff046-114">This command displays the execution policies for each scope in the order of precedence.</span></span>

```powershell
Get-ExecutionPolicy -List
```

```Output
Scope          ExecutionPolicy
-----          ---------------
MachinePolicy  Undefined
UserPolicy     Undefined
Process        Undefined
CurrentUser    AllSigned
LocalMachine   Undefined
```

<span data-ttu-id="ff046-115">この `Get-ExecutionPolicy` コマンドレットは、 **List** パラメーターを使用して、各スコープの実行ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="ff046-115">The `Get-ExecutionPolicy` cmdlet uses the **List** parameter to display each scope's execution policy.</span></span>

### <span data-ttu-id="ff046-116">例 2: 実行ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="ff046-116">Example 2: Set an execution policy</span></span>

<span data-ttu-id="ff046-117">この例では、ローカルコンピューターの実行ポリシーを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ff046-117">This example shows how to set an execution policy for the local computer.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="ff046-118">コマンドレットでは、 `Set-ExecutionPolicy` **set-executionpolicy** パラメーターを使用して、 **RemoteSigned** ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="ff046-118">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="ff046-119">**Scope** パラメーターは、既定のスコープ値である **LocalMachine** を指定します。</span><span class="sxs-lookup"><span data-stu-id="ff046-119">The **Scope** parameter specifies the default scope value, **LocalMachine**.</span></span> <span data-ttu-id="ff046-120">実行ポリシー設定を表示するには、 `Get-ExecutionPolicy` コマンドレットを **List** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="ff046-120">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="ff046-121">例 3: 有効な実行ポリシーを取得する</span><span class="sxs-lookup"><span data-stu-id="ff046-121">Example 3: Get the effective execution policy</span></span>

<span data-ttu-id="ff046-122">この例では、PowerShell セッションの有効な実行ポリシーを表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ff046-122">This example shows how to display the effective execution policy for a PowerShell session.</span></span>

```
PS> Get-ExecutionPolicy -List

        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       AllSigned
 LocalMachine    RemoteSigned

PS> Get-ExecutionPolicy

AllSigned
```

<span data-ttu-id="ff046-123">この `Get-ExecutionPolicy` コマンドレットは、 **List** パラメーターを使用して、各スコープの実行ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="ff046-123">The `Get-ExecutionPolicy` cmdlet uses the **List** parameter to display each scope's execution policy.</span></span> <span data-ttu-id="ff046-124">`Get-ExecutionPolicy`コマンドレットは、有効な実行ポリシー **AllSigned** を表示するパラメーターなしで実行されます。</span><span class="sxs-lookup"><span data-stu-id="ff046-124">The `Get-ExecutionPolicy` cmdlet is run without a parameter to display the effective execution policy, **AllSigned**.</span></span>

### <span data-ttu-id="ff046-125">例 4: 実行ポリシーを変更せずにスクリプトを実行するためのブロックを解除する</span><span class="sxs-lookup"><span data-stu-id="ff046-125">Example 4: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="ff046-126">この例では、 **RemoteSigned** 実行ポリシーを使用して、署名されていないスクリプトを実行できないようにする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ff046-126">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="ff046-127">コマンドレットを使用 **する前** に、スクリプトのコードを読み取って安全であることを確認することをお勧めし `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="ff046-127">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="ff046-128">コマンドレットを実行すると、スクリプトのブロックが解除され `Unblock-File` ますが、実行ポリシーは変更されません。</span><span class="sxs-lookup"><span data-stu-id="ff046-128">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

```
PS> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope LocalMachine

PS> Get-ExecutionPolicy

RemoteSigned

PS> .\Start-ActivityTracker.ps1

.\Start-ActivityTracker.ps1 : File .\Start-ActivityTracker.ps1 cannot be loaded.
The file .\Start-ActivityTracker.ps1 is not digitally signed.
The script will not execute on the system.
For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ .\Start-ActivityTracker.ps1
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : NotSpecified: (:) [], PSSecurityException
+ FullyQualifiedErrorId : UnauthorizedAccess

PS> Unblock-File -Path .\Start-ActivityTracker.ps1

PS> Get-ExecutionPolicy

RemoteSigned

PS> .\Start-ActivityTracker.ps1

Task 1:
```

<span data-ttu-id="ff046-129">は、 `Set-ExecutionPolicy` **set-executionpolicy** パラメーターを使用して **RemoteSigned** ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="ff046-129">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="ff046-130">ポリシーは、既定のスコープである **LocalMachine** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="ff046-130">The policy is set for the default scope, **LocalMachine**.</span></span>

<span data-ttu-id="ff046-131">この `Get-ExecutionPolicy` コマンドレットは、 **RemoteSigned** が現在の PowerShell セッションの有効な実行ポリシーであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="ff046-131">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="ff046-132">**Start-ActivityTracker.ps1** スクリプトが現在のディレクトリから実行されます。</span><span class="sxs-lookup"><span data-stu-id="ff046-132">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="ff046-133">スクリプトがデジタル署名されていないため、スクリプトは **RemoteSigned** によってブロックされます。</span><span class="sxs-lookup"><span data-stu-id="ff046-133">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="ff046-134">この例では、スクリプトのコードが確認され、実行の安全性が確認されています。</span><span class="sxs-lookup"><span data-stu-id="ff046-134">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="ff046-135">コマンドレットでは、 `Unblock-File` **Path** パラメーターを使用してスクリプトのブロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="ff046-135">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="ff046-136">が実行ポリシーを変更していないことを確認するには `Unblock-File` 、 `Get-ExecutionPolicy` 有効な実行ポリシー **RemoteSigned** を表示します。</span><span class="sxs-lookup"><span data-stu-id="ff046-136">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned**.</span></span>

<span data-ttu-id="ff046-137">スクリプト **Start-ActivityTracker.ps1** は、現在のディレクトリから実行されます。</span><span class="sxs-lookup"><span data-stu-id="ff046-137">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="ff046-138">スクリプトは、コマンドレットによってブロック解除されたため、実行を開始し `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="ff046-138">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="ff046-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ff046-139">PARAMETERS</span></span>

### <span data-ttu-id="ff046-140">-List</span><span class="sxs-lookup"><span data-stu-id="ff046-140">-List</span></span>

<span data-ttu-id="ff046-141">セッションのすべての実行ポリシー値を取得し、優先順位順に一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="ff046-141">Gets all execution policy values for the session listed in precedence order.</span></span> <span data-ttu-id="ff046-142">既定では、は `Get-ExecutionPolicy` 有効な実行ポリシーのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="ff046-142">By default, `Get-ExecutionPolicy` gets only the effective execution policy.</span></span>

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

### <span data-ttu-id="ff046-143">-スコープ</span><span class="sxs-lookup"><span data-stu-id="ff046-143">-Scope</span></span>

<span data-ttu-id="ff046-144">実行ポリシーの影響を受けるスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="ff046-144">Specifies the scope that is affected by an execution policy.</span></span>

<span data-ttu-id="ff046-145">有効な実行ポリシーは、次のように優先順位によって決まります。</span><span class="sxs-lookup"><span data-stu-id="ff046-145">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="ff046-146">**Machinepolicy**。</span><span class="sxs-lookup"><span data-stu-id="ff046-146">**MachinePolicy**.</span></span> <span data-ttu-id="ff046-147">コンピューターのすべてのユーザーに対してグループポリシーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="ff046-147">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="ff046-148">**Userpolicy**。</span><span class="sxs-lookup"><span data-stu-id="ff046-148">**UserPolicy**.</span></span> <span data-ttu-id="ff046-149">コンピューターの現在のユーザーのグループポリシーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="ff046-149">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="ff046-150">**プロセス**。</span><span class="sxs-lookup"><span data-stu-id="ff046-150">**Process**.</span></span> <span data-ttu-id="ff046-151">現在の PowerShell セッションにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="ff046-151">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="ff046-152">**CurrentUser**。</span><span class="sxs-lookup"><span data-stu-id="ff046-152">**CurrentUser**.</span></span> <span data-ttu-id="ff046-153">現在のユーザーのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="ff046-153">Affects only the current user.</span></span>
- <span data-ttu-id="ff046-154">**LocalMachine**。</span><span class="sxs-lookup"><span data-stu-id="ff046-154">**LocalMachine**.</span></span> <span data-ttu-id="ff046-155">コンピューターのすべてのユーザーに影響する既定のスコープ。</span><span class="sxs-lookup"><span data-stu-id="ff046-155">Default scope that affects all users of the computer.</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicyScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine, MachinePolicy, Process, UserPolicy

Required: False
Position: 0
Default value: Effective execution policy
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="ff046-156">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ff046-156">CommonParameters</span></span>

<span data-ttu-id="ff046-157">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ff046-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ff046-158">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ff046-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ff046-159">入力</span><span class="sxs-lookup"><span data-stu-id="ff046-159">INPUTS</span></span>

### <span data-ttu-id="ff046-160">なし</span><span class="sxs-lookup"><span data-stu-id="ff046-160">None</span></span>

<span data-ttu-id="ff046-161">`Get-ExecutionPolicy` は、パイプラインからの入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="ff046-161">`Get-ExecutionPolicy` doesn't accept input from the pipeline.</span></span>

## <span data-ttu-id="ff046-162">出力</span><span class="sxs-lookup"><span data-stu-id="ff046-162">OUTPUTS</span></span>

### <span data-ttu-id="ff046-163">Microsoft.PowerShell.ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="ff046-163">Microsoft.PowerShell.ExecutionPolicy</span></span>

<span data-ttu-id="ff046-164">コマンドレットは、Linux および macOS プラットフォームでは常に **無制限** を返します。</span><span class="sxs-lookup"><span data-stu-id="ff046-164">The cmdlet always returns **Unrestricted** on Linux and macOS platforms.</span></span>

## <span data-ttu-id="ff046-165">注</span><span class="sxs-lookup"><span data-stu-id="ff046-165">NOTES</span></span>

<span data-ttu-id="ff046-166">実行ポリシーは、PowerShell のセキュリティ戦略の一部です。</span><span class="sxs-lookup"><span data-stu-id="ff046-166">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="ff046-167">実行ポリシーは、PowerShell プロファイルなどの構成ファイルを読み込むか、スクリプトを実行できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ff046-167">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="ff046-168">また、スクリプトを実行する前に、そのスクリプトをデジタル署名する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ff046-168">And, whether scripts must be digitally signed before they are run.</span></span>

## <span data-ttu-id="ff046-169">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ff046-169">RELATED LINKS</span></span>

[<span data-ttu-id="ff046-170">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="ff046-170">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)

[<span data-ttu-id="ff046-171">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="ff046-171">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="ff046-172">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="ff046-172">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="ff046-173">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="ff046-173">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="ff046-174">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="ff046-174">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)
