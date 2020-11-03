---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/get-executionpolicy?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExecutionPolicy
ms.openlocfilehash: d33961d9c0b1980d84d35a33c45d965e84231914
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217496"
---
# <span data-ttu-id="57be1-103">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="57be1-103">Get-ExecutionPolicy</span></span>

## <span data-ttu-id="57be1-104">概要</span><span class="sxs-lookup"><span data-stu-id="57be1-104">SYNOPSIS</span></span>
<span data-ttu-id="57be1-105">現在のセッションの実行ポリシーを取得します。</span><span class="sxs-lookup"><span data-stu-id="57be1-105">Gets the execution policies for the current session.</span></span>

## <span data-ttu-id="57be1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="57be1-106">SYNTAX</span></span>

### <span data-ttu-id="57be1-107">All</span><span class="sxs-lookup"><span data-stu-id="57be1-107">All</span></span>

```
Get-ExecutionPolicy [[-Scope] <ExecutionPolicyScope>] [-List] [<CommonParameters>]
```

## <span data-ttu-id="57be1-108">Description</span><span class="sxs-lookup"><span data-stu-id="57be1-108">DESCRIPTION</span></span>

<span data-ttu-id="57be1-109">各スコープの実行ポリシーを優先順位に従って表示するには、を使用 `Get-ExecutionPolicy -List` します。</span><span class="sxs-lookup"><span data-stu-id="57be1-109">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="57be1-110">PowerShell セッションの有効な実行ポリシーを確認するには、 `Get-ExecutionPolicy` パラメーターなしで使用します。</span><span class="sxs-lookup"><span data-stu-id="57be1-110">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

<span data-ttu-id="57be1-111">有効な実行ポリシーは、およびグループポリシー設定によって設定される実行ポリシーによって決定され `Set-ExecutionPolicy` ます。</span><span class="sxs-lookup"><span data-stu-id="57be1-111">The effective execution policy is determined by execution policies that are set by `Set-ExecutionPolicy` and Group Policy settings.</span></span>

<span data-ttu-id="57be1-112">詳細については、「[about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57be1-112">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

## <span data-ttu-id="57be1-113">例</span><span class="sxs-lookup"><span data-stu-id="57be1-113">EXAMPLES</span></span>

### <span data-ttu-id="57be1-114">例 1: すべての実行ポリシーを取得する</span><span class="sxs-lookup"><span data-stu-id="57be1-114">Example 1: Get all execution policies</span></span>

<span data-ttu-id="57be1-115">このコマンドは、各スコープの実行ポリシーを優先順位順に表示します。</span><span class="sxs-lookup"><span data-stu-id="57be1-115">This command displays the execution policies for each scope in the order of precedence.</span></span>

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

<span data-ttu-id="57be1-116">この `Get-ExecutionPolicy` コマンドレットは、 **List** パラメーターを使用して、各スコープの実行ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="57be1-116">The `Get-ExecutionPolicy` cmdlet uses the **List** parameter to display each scope's execution policy.</span></span>

### <span data-ttu-id="57be1-117">例 2: 実行ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="57be1-117">Example 2: Set an execution policy</span></span>

<span data-ttu-id="57be1-118">この例では、ローカルコンピューターの実行ポリシーを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="57be1-118">This example shows how to set an execution policy for the local computer.</span></span>

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

<span data-ttu-id="57be1-119">コマンドレットでは、 `Set-ExecutionPolicy` **set-executionpolicy** パラメーターを使用して、 **RemoteSigned** ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="57be1-119">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="57be1-120">**Scope** パラメーターは、既定のスコープ値である **LocalMachine** を指定します。</span><span class="sxs-lookup"><span data-stu-id="57be1-120">The **Scope** parameter specifies the default scope value, **LocalMachine**.</span></span> <span data-ttu-id="57be1-121">実行ポリシー設定を表示するには、 `Get-ExecutionPolicy` コマンドレットを **List** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="57be1-121">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="57be1-122">例 3: 有効な実行ポリシーを取得する</span><span class="sxs-lookup"><span data-stu-id="57be1-122">Example 3: Get the effective execution policy</span></span>

<span data-ttu-id="57be1-123">この例では、PowerShell セッションの有効な実行ポリシーを表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="57be1-123">This example shows how to display the effective execution policy for a PowerShell session.</span></span>

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

<span data-ttu-id="57be1-124">この `Get-ExecutionPolicy` コマンドレットは、 **List** パラメーターを使用して、各スコープの実行ポリシーを表示します。</span><span class="sxs-lookup"><span data-stu-id="57be1-124">The `Get-ExecutionPolicy` cmdlet uses the **List** parameter to display each scope's execution policy.</span></span> <span data-ttu-id="57be1-125">`Get-ExecutionPolicy`コマンドレットは、有効な実行ポリシー **AllSigned** を表示するパラメーターなしで実行されます。</span><span class="sxs-lookup"><span data-stu-id="57be1-125">The `Get-ExecutionPolicy` cmdlet is run without a parameter to display the effective execution policy, **AllSigned**.</span></span>

### <span data-ttu-id="57be1-126">例 4: 実行ポリシーを変更せずにスクリプトを実行するためのブロックを解除する</span><span class="sxs-lookup"><span data-stu-id="57be1-126">Example 4: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="57be1-127">この例では、 **RemoteSigned** 実行ポリシーを使用して、署名されていないスクリプトを実行できないようにする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="57be1-127">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="57be1-128">コマンドレットを使用 **する前** に、スクリプトのコードを読み取って安全であることを確認することをお勧めし `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="57be1-128">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="57be1-129">コマンドレットを実行すると、スクリプトのブロックが解除され `Unblock-File` ますが、実行ポリシーは変更されません。</span><span class="sxs-lookup"><span data-stu-id="57be1-129">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

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

<span data-ttu-id="57be1-130">は、 `Set-ExecutionPolicy` **set-executionpolicy** パラメーターを使用して **RemoteSigned** ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="57be1-130">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="57be1-131">ポリシーは、既定のスコープである **LocalMachine** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="57be1-131">The policy is set for the default scope, **LocalMachine**.</span></span>

<span data-ttu-id="57be1-132">この `Get-ExecutionPolicy` コマンドレットは、 **RemoteSigned** が現在の PowerShell セッションの有効な実行ポリシーであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="57be1-132">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="57be1-133">**Start-ActivityTracker.ps1** スクリプトが現在のディレクトリから実行されます。</span><span class="sxs-lookup"><span data-stu-id="57be1-133">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="57be1-134">スクリプトがデジタル署名されていないため、スクリプトは **RemoteSigned** によってブロックされます。</span><span class="sxs-lookup"><span data-stu-id="57be1-134">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="57be1-135">この例では、スクリプトのコードが確認され、実行の安全性が確認されています。</span><span class="sxs-lookup"><span data-stu-id="57be1-135">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="57be1-136">コマンドレットでは、 `Unblock-File` **Path** パラメーターを使用してスクリプトのブロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="57be1-136">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="57be1-137">が実行ポリシーを変更していないことを確認するには `Unblock-File` 、 `Get-ExecutionPolicy` 有効な実行ポリシー **RemoteSigned** を表示します。</span><span class="sxs-lookup"><span data-stu-id="57be1-137">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned**.</span></span>

<span data-ttu-id="57be1-138">スクリプト **Start-ActivityTracker.ps1** は、現在のディレクトリから実行されます。</span><span class="sxs-lookup"><span data-stu-id="57be1-138">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="57be1-139">スクリプトは、コマンドレットによってブロック解除されたため、実行を開始し `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="57be1-139">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="57be1-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="57be1-140">PARAMETERS</span></span>

### <span data-ttu-id="57be1-141">-List</span><span class="sxs-lookup"><span data-stu-id="57be1-141">-List</span></span>

<span data-ttu-id="57be1-142">セッションのすべての実行ポリシー値を取得し、優先順位順に一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="57be1-142">Gets all execution policy values for the session listed in precedence order.</span></span> <span data-ttu-id="57be1-143">既定では、は `Get-ExecutionPolicy` 有効な実行ポリシーのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="57be1-143">By default, `Get-ExecutionPolicy` gets only the effective execution policy.</span></span>

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

### <span data-ttu-id="57be1-144">-スコープ</span><span class="sxs-lookup"><span data-stu-id="57be1-144">-Scope</span></span>

<span data-ttu-id="57be1-145">実行ポリシーの影響を受けるスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="57be1-145">Specifies the scope that is affected by an execution policy.</span></span>

<span data-ttu-id="57be1-146">有効な実行ポリシーは、次のように優先順位によって決まります。</span><span class="sxs-lookup"><span data-stu-id="57be1-146">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="57be1-147">**Machinepolicy** 。</span><span class="sxs-lookup"><span data-stu-id="57be1-147">**MachinePolicy**.</span></span> <span data-ttu-id="57be1-148">コンピューターのすべてのユーザーに対してグループポリシーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="57be1-148">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="57be1-149">**Userpolicy** 。</span><span class="sxs-lookup"><span data-stu-id="57be1-149">**UserPolicy**.</span></span> <span data-ttu-id="57be1-150">コンピューターの現在のユーザーのグループポリシーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="57be1-150">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="57be1-151">**プロセス** 。</span><span class="sxs-lookup"><span data-stu-id="57be1-151">**Process**.</span></span> <span data-ttu-id="57be1-152">現在の PowerShell セッションにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="57be1-152">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="57be1-153">**CurrentUser** 。</span><span class="sxs-lookup"><span data-stu-id="57be1-153">**CurrentUser**.</span></span> <span data-ttu-id="57be1-154">現在のユーザーのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="57be1-154">Affects only the current user.</span></span>
- <span data-ttu-id="57be1-155">**LocalMachine** 。</span><span class="sxs-lookup"><span data-stu-id="57be1-155">**LocalMachine**.</span></span> <span data-ttu-id="57be1-156">コンピューターのすべてのユーザーに影響する既定のスコープ。</span><span class="sxs-lookup"><span data-stu-id="57be1-156">Default scope that affects all users of the computer.</span></span>

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

### <span data-ttu-id="57be1-157">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="57be1-157">CommonParameters</span></span>

<span data-ttu-id="57be1-158">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="57be1-158">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="57be1-159">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57be1-159">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="57be1-160">入力</span><span class="sxs-lookup"><span data-stu-id="57be1-160">INPUTS</span></span>

### <span data-ttu-id="57be1-161">なし</span><span class="sxs-lookup"><span data-stu-id="57be1-161">None</span></span>

<span data-ttu-id="57be1-162">`Get-ExecutionPolicy` は、パイプラインからの入力を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="57be1-162">`Get-ExecutionPolicy` doesn't accept input from the pipeline.</span></span>

## <span data-ttu-id="57be1-163">出力</span><span class="sxs-lookup"><span data-stu-id="57be1-163">OUTPUTS</span></span>

### <span data-ttu-id="57be1-164">Microsoft.PowerShell.ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="57be1-164">Microsoft.PowerShell.ExecutionPolicy</span></span>

## <span data-ttu-id="57be1-165">注</span><span class="sxs-lookup"><span data-stu-id="57be1-165">NOTES</span></span>

<span data-ttu-id="57be1-166">実行ポリシーは、PowerShell のセキュリティ戦略の一部です。</span><span class="sxs-lookup"><span data-stu-id="57be1-166">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="57be1-167">実行ポリシーは、PowerShell プロファイルなどの構成ファイルを読み込むか、スクリプトを実行できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="57be1-167">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="57be1-168">また、スクリプトを実行する前に、そのスクリプトをデジタル署名する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="57be1-168">And, whether scripts must be digitally signed before they are run.</span></span>

## <span data-ttu-id="57be1-169">関連リンク</span><span class="sxs-lookup"><span data-stu-id="57be1-169">RELATED LINKS</span></span>

[<span data-ttu-id="57be1-170">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="57be1-170">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)

[<span data-ttu-id="57be1-171">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="57be1-171">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="57be1-172">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="57be1-172">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="57be1-173">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="57be1-173">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="57be1-174">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="57be1-174">Set-ExecutionPolicy</span></span>](Set-ExecutionPolicy.md)

