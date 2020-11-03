---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 3/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ExecutionPolicy
ms.openlocfilehash: f8575c97c4279f285598e2b1bdf94786d92c841a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216880"
---
# <span data-ttu-id="a5d6f-103">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="a5d6f-103">Set-ExecutionPolicy</span></span>

## <span data-ttu-id="a5d6f-104">概要</span><span class="sxs-lookup"><span data-stu-id="a5d6f-104">SYNOPSIS</span></span>
<span data-ttu-id="a5d6f-105">Windows コンピューターの PowerShell 実行ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-105">Sets the PowerShell execution policies for Windows computers.</span></span>

## <span data-ttu-id="a5d6f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a5d6f-106">SYNTAX</span></span>

### <span data-ttu-id="a5d6f-107">All</span><span class="sxs-lookup"><span data-stu-id="a5d6f-107">All</span></span>

```
Set-ExecutionPolicy [-ExecutionPolicy] <ExecutionPolicy> [[-Scope] <ExecutionPolicyScope>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a5d6f-108">Description</span><span class="sxs-lookup"><span data-stu-id="a5d6f-108">DESCRIPTION</span></span>

<span data-ttu-id="a5d6f-109">コマンドレットでは、 `Set-ExecutionPolicy` Windows コンピューターの PowerShell 実行ポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-109">The `Set-ExecutionPolicy` cmdlet changes PowerShell execution policies for Windows computers.</span></span> <span data-ttu-id="a5d6f-110">詳細については、「[about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-110">For more information, see [about_Execution_Policies](../Microsoft.PowerShell.Core/about/about_Execution_Policies.md).</span></span>

<span data-ttu-id="a5d6f-111">Windows 以外のコンピューターの PowerShell 6.0 以降では、既定の実行ポリシーは **無制限** であり、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-111">Beginning in PowerShell 6.0 for non-Windows computers, the default execution policy is **Unrestricted** and can't be changed.</span></span> <span data-ttu-id="a5d6f-112">`Set-ExecutionPolicy`コマンドレットは使用できますが、PowerShell にはサポートされていないコンソールメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-112">The `Set-ExecutionPolicy` cmdlet is available, but PowerShell displays a console message that it's not supported.</span></span>

<span data-ttu-id="a5d6f-113">実行ポリシーは、PowerShell のセキュリティ戦略の一部です。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-113">An execution policy is part of the PowerShell security strategy.</span></span> <span data-ttu-id="a5d6f-114">実行ポリシーは、PowerShell プロファイルなどの構成ファイルを読み込むか、スクリプトを実行できるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-114">Execution policies determine whether you can load configuration files, such as your PowerShell profile, or run scripts.</span></span> <span data-ttu-id="a5d6f-115">また、スクリプトを実行する前に、そのスクリプトをデジタル署名する必要があるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-115">And, whether scripts must be digitally signed before they are run.</span></span>

<span data-ttu-id="a5d6f-116">`Set-ExecutionPolicy`コマンドレットの既定のスコープは **LocalMachine** で、コンピューターを使用するすべてのユーザーに影響します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-116">The `Set-ExecutionPolicy` cmdlet's default scope is **LocalMachine** , which affects everyone who uses the computer.</span></span> <span data-ttu-id="a5d6f-117">**LocalMachine** の実行ポリシーを変更するには、[ **管理者として実行** ] で PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-117">To change the execution policy for **LocalMachine** , start PowerShell with **Run as Administrator** .</span></span>

<span data-ttu-id="a5d6f-118">各スコープの実行ポリシーを優先順位に従って表示するには、を使用 `Get-ExecutionPolicy -List` します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-118">To display the execution policies for each scope in the order of precedence, use `Get-ExecutionPolicy -List`.</span></span> <span data-ttu-id="a5d6f-119">PowerShell セッションの有効な実行ポリシーを確認するには、 `Get-ExecutionPolicy` パラメーターなしで使用します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-119">To see the effective execution policy for your PowerShell session use `Get-ExecutionPolicy` with no parameters.</span></span>

## <span data-ttu-id="a5d6f-120">例</span><span class="sxs-lookup"><span data-stu-id="a5d6f-120">EXAMPLES</span></span>

### <span data-ttu-id="a5d6f-121">例 1: 実行ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="a5d6f-121">Example 1: Set an execution policy</span></span>

<span data-ttu-id="a5d6f-122">この例では、ローカルコンピューターの実行ポリシーを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-122">This example shows how to set the execution policy for the local computer.</span></span>

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
  CurrentUser    RemoteSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="a5d6f-123">コマンドレットでは、 `Set-ExecutionPolicy` **set-executionpolicy** パラメーターを使用して、 **RemoteSigned** ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-123">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="a5d6f-124">**Scope** パラメーターは、既定のスコープ値である **LocalMachine** を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-124">The **Scope** parameter specifies the default scope value, **LocalMachine** .</span></span> <span data-ttu-id="a5d6f-125">実行ポリシー設定を表示するには、 `Get-ExecutionPolicy` コマンドレットを **List** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-125">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="a5d6f-126">例 2: グループポリシーと競合する実行ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="a5d6f-126">Example 2: Set an execution policy that conflicts with a Group Policy</span></span>

<span data-ttu-id="a5d6f-127">このコマンドは、 **LocalMachine** スコープの実行ポリシーを **Restricted** に設定しようとします。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-127">This command attempts to set the **LocalMachine** scope's execution policy to **Restricted** .</span></span>
<span data-ttu-id="a5d6f-128">**LocalMachine** はより制限されていますが、グループポリシーと競合するため、有効なポリシーではありません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-128">**LocalMachine** is more restrictive, but isn't the effective policy because it conflicts with a Group Policy.</span></span> <span data-ttu-id="a5d6f-129">**制限** されたポリシーは、レジストリハイブ **HKEY_LOCAL_MACHINE** に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-129">The **Restricted** policy is written to the registry hive **HKEY_LOCAL_MACHINE** .</span></span>

```
PS> Set-ExecutionPolicy -ExecutionPolicy Restricted -Scope LocalMachine

Set-ExecutionPolicy : PowerShell updated your local preference successfully, but the setting is
overridden by the Group Policy applied to your system. Due to the override, your shell will retain
its current effective execution policy of "AllSigned". Contact your Group Policy administrator for
more information. At line:1 char:20 + Set-ExecutionPolicy <<<< restricted

PS> Get-ChildItem -Path HKLM:\SOFTWARE\Microsoft\PowerShell\1\ShellIds

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\PowerShell\1\ShellIds

Name                    Property
----                    --------
Microsoft.PowerShell    Path            : C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
                        ExecutionPolicy : Restricted
ScriptedDiagnostics     ExecutionPolicy : Unrestricted
```

<span data-ttu-id="a5d6f-130">コマンドレットでは、 `Set-ExecutionPolicy` **set-executionpolicy** パラメーターを使用して **制限** されたポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-130">The `Set-ExecutionPolicy` cmdlet uses the **ExecutionPolicy** parameter to specify the **Restricted** policy.</span></span> <span data-ttu-id="a5d6f-131">**Scope** パラメーターは、既定のスコープ値である **LocalMachine** を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-131">The **Scope** parameter specifies the default scope value, **LocalMachine** .</span></span>
<span data-ttu-id="a5d6f-132">コマンドレットでは、 `Get-ChildItem` **Path** パラメーターを **HKLM** プロバイダーと共に使用して、レジストリの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-132">The `Get-ChildItem` cmdlet uses the **Path** parameter with the **HKLM** provider to specify registry location.</span></span>

### <span data-ttu-id="a5d6f-133">例 3: リモートコンピューターからローカルコンピューターに実行ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="a5d6f-133">Example 3: Apply the execution policy from a remote computer to a local computer</span></span>

<span data-ttu-id="a5d6f-134">このコマンドは、リモートコンピューターから実行ポリシーオブジェクトを取得し、ローカルコンピューターのポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-134">This command gets the execution policy object from a remote computer and sets the policy on the local computer.</span></span> <span data-ttu-id="a5d6f-135">`Get-ExecutionPolicy`**Microsoft.PowerShell.ExecutionPolicy** オブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-135">`Get-ExecutionPolicy` sends a **Microsoft.PowerShell.ExecutionPolicy** object down the pipeline.</span></span> <span data-ttu-id="a5d6f-136">`Set-ExecutionPolicy` パイプラインの入力を受け入れ、 **set-executionpolicy** パラメーターを必要としません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-136">`Set-ExecutionPolicy` accepts pipeline input and doesn't require the **ExecutionPolicy** parameter.</span></span>

```
PS> Invoke-Command -ComputerName Server01 -ScriptBlock { Get-ExecutionPolicy } | Set-ExecutionPolicy
```

<span data-ttu-id="a5d6f-137">`Invoke-Command`コマンドレットは、ローカルコンピューターで実行され、リモートコンピューターに **ScriptBlock** を送信します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-137">The `Invoke-Command` cmdlet is executed at the local computer and sends the **ScriptBlock** to the remote computer.</span></span> <span data-ttu-id="a5d6f-138">**ComputerName** パラメーターは、リモートコンピューター **Server01** を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-138">The **ComputerName** parameter specifies the remote computer, **Server01** .</span></span> <span data-ttu-id="a5d6f-139">**ScriptBlock** パラメーターは、 `Get-ExecutionPolicy` リモートコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-139">The **ScriptBlock** parameter runs `Get-ExecutionPolicy` on the remote computer.</span></span> <span data-ttu-id="a5d6f-140">`Get-ExecutionPolicy`オブジェクトは、パイプライン内でに送信され `Set-ExecutionPolicy` ます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-140">The `Get-ExecutionPolicy` object is sent down the pipeline to the `Set-ExecutionPolicy`.</span></span>
<span data-ttu-id="a5d6f-141">`Set-ExecutionPolicy` ローカルコンピューターの既定のスコープである **LocalMachine** に実行ポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-141">`Set-ExecutionPolicy` applies the execution policy to the local computer's default scope, **LocalMachine** .</span></span>

### <span data-ttu-id="a5d6f-142">例 4: 実行ポリシーのスコープを設定する</span><span class="sxs-lookup"><span data-stu-id="a5d6f-142">Example 4: Set the scope for an execution policy</span></span>

<span data-ttu-id="a5d6f-143">この例では、指定されたスコープ ( **CurrentUser** ) の実行ポリシーを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-143">This example shows how to set an execution policy for a specified scope, **CurrentUser** .</span></span> <span data-ttu-id="a5d6f-144">**CurrentUser** スコープは、このスコープを設定したユーザーにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-144">The **CurrentUser** scope only affects the user who sets this scope.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope CurrentUser
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

<span data-ttu-id="a5d6f-145">`Set-ExecutionPolicy`**set-executionpolicy** パラメーターを使用して、 **AllSigned** ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-145">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span>
<span data-ttu-id="a5d6f-146">**スコープ** パラメーターで **CurrentUser** を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-146">The **Scope** parameter specifies the **CurrentUser** .</span></span> <span data-ttu-id="a5d6f-147">実行ポリシー設定を表示するには、 `Get-ExecutionPolicy` コマンドレットを **List** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-147">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

<span data-ttu-id="a5d6f-148">ユーザーの有効な実行ポリシーが **AllSigned** になります。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-148">The effective execution policy for the user becomes **AllSigned** .</span></span>

### <span data-ttu-id="a5d6f-149">例 5: 現在のユーザーの実行ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="a5d6f-149">Example 5: Remove the execution policy for the current user</span></span>

<span data-ttu-id="a5d6f-150">この例では、 **未定義** の実行ポリシーを使用して、指定されたスコープの実行ポリシーを削除する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-150">This example shows how use the **Undefined** execution policy to remove an execution policy for a specified scope.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy Undefined -Scope CurrentUser
Get-ExecutionPolicy -List
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       Undefined
 LocalMachine    RemoteSigned
```

<span data-ttu-id="a5d6f-151">`Set-ExecutionPolicy`**set-executionpolicy** パラメーターを使用して、 **未定義** のポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-151">`Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **Undefined** policy.</span></span>
<span data-ttu-id="a5d6f-152">**スコープ** パラメーターで **CurrentUser** を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-152">The **Scope** parameter specifies the **CurrentUser** .</span></span> <span data-ttu-id="a5d6f-153">実行ポリシー設定を表示するには、 `Get-ExecutionPolicy` コマンドレットを **List** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-153">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="a5d6f-154">例 6: 現在の PowerShell セッションの実行ポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="a5d6f-154">Example 6: Set the execution policy for the current PowerShell session</span></span>

<span data-ttu-id="a5d6f-155">**プロセス** のスコープは、現在の PowerShell セッションにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-155">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="a5d6f-156">実行ポリシーは環境変数に保存され、 `$env:PSExecutionPolicyPreference` セッションが閉じられると削除されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-156">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference` and is deleted when the session is closed.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy AllSigned -Scope Process
```

```Output
        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       AllSigned
  CurrentUser    RemoteSigned
 LocalMachine    RemoteSigned
```

<span data-ttu-id="a5d6f-157">は、 `Set-ExecutionPolicy` **set-executionpolicy** パラメーターを使用して **AllSigned** ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-157">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **AllSigned** policy.</span></span> <span data-ttu-id="a5d6f-158">**スコープ** のパラメーターは、値の **処理** を指定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-158">The **Scope** parameter specifies the value **Process** .</span></span> <span data-ttu-id="a5d6f-159">実行ポリシー設定を表示するには、 `Get-ExecutionPolicy` コマンドレットを **List** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-159">To view the execution policy settings, use the `Get-ExecutionPolicy` cmdlet with the **List** parameter.</span></span>

### <span data-ttu-id="a5d6f-160">例 7: 実行ポリシーを変更せずにスクリプトを実行するためのブロックを解除する</span><span class="sxs-lookup"><span data-stu-id="a5d6f-160">Example 7: Unblock a script to run it without changing the execution policy</span></span>

<span data-ttu-id="a5d6f-161">この例では、 **RemoteSigned** 実行ポリシーを使用して、署名されていないスクリプトを実行できないようにする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-161">This example shows how the **RemoteSigned** execution policy prevents you from running unsigned scripts.</span></span>

<span data-ttu-id="a5d6f-162">コマンドレットを使用 **する前** に、スクリプトのコードを読み取って安全であることを確認することをお勧めし `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-162">A best practice is to read the script's code and verify it's safe **before** using the `Unblock-File` cmdlet.</span></span> <span data-ttu-id="a5d6f-163">コマンドレットを実行すると、スクリプトのブロックが解除され `Unblock-File` ますが、実行ポリシーは変更されません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-163">The `Unblock-File` cmdlet unblocks scripts so they can run, but doesn't change the execution policy.</span></span>

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

<span data-ttu-id="a5d6f-164">は、 `Set-ExecutionPolicy` **set-executionpolicy** パラメーターを使用して **RemoteSigned** ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-164">The `Set-ExecutionPolicy` uses the **ExecutionPolicy** parameter to specify the **RemoteSigned** policy.</span></span> <span data-ttu-id="a5d6f-165">ポリシーは、既定のスコープである **LocalMachine** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-165">The policy is set for the default scope, **LocalMachine** .</span></span>

<span data-ttu-id="a5d6f-166">この `Get-ExecutionPolicy` コマンドレットは、 **RemoteSigned** が現在の PowerShell セッションの有効な実行ポリシーであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-166">The `Get-ExecutionPolicy` cmdlet shows that **RemoteSigned** is the effective execution policy for the current PowerShell session.</span></span>

<span data-ttu-id="a5d6f-167">**Start-ActivityTracker.ps1** スクリプトが現在のディレクトリから実行されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-167">The **Start-ActivityTracker.ps1** script is executed from the current directory.</span></span> <span data-ttu-id="a5d6f-168">スクリプトがデジタル署名されていないため、スクリプトは **RemoteSigned** によってブロックされます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-168">The script is blocked by **RemoteSigned** because the script isn't digitally signed.</span></span>

<span data-ttu-id="a5d6f-169">この例では、スクリプトのコードが確認され、実行の安全性が確認されています。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-169">For this example, the script's code was reviewed and verified as safe to run.</span></span> <span data-ttu-id="a5d6f-170">コマンドレットでは、 `Unblock-File` **Path** パラメーターを使用してスクリプトのブロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-170">The `Unblock-File` cmdlet uses the **Path** parameter to unblock the script.</span></span>

<span data-ttu-id="a5d6f-171">が実行ポリシーを変更していないことを確認するには `Unblock-File` 、 `Get-ExecutionPolicy` 有効な実行ポリシー **RemoteSigned** を表示します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-171">To verify that `Unblock-File` didn't change the execution policy, `Get-ExecutionPolicy` displays the effective execution policy, **RemoteSigned** .</span></span>

<span data-ttu-id="a5d6f-172">スクリプト **Start-ActivityTracker.ps1** は、現在のディレクトリから実行されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-172">The script, **Start-ActivityTracker.ps1** is executed from the current directory.</span></span> <span data-ttu-id="a5d6f-173">スクリプトは、コマンドレットによってブロック解除されたため、実行を開始し `Unblock-File` ます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-173">The script begins to run because it was unblocked by the `Unblock-File` cmdlet.</span></span>

## <span data-ttu-id="a5d6f-174">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a5d6f-174">PARAMETERS</span></span>

### <span data-ttu-id="a5d6f-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a5d6f-175">-Confirm</span></span>

<span data-ttu-id="a5d6f-176">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-176">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a5d6f-177">-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="a5d6f-177">-ExecutionPolicy</span></span>

<span data-ttu-id="a5d6f-178">実行ポリシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-178">Specifies the execution policy.</span></span> <span data-ttu-id="a5d6f-179">グループポリシーがなく、各スコープの実行ポリシーが **Undefined** に設定されている場合は、すべてのユーザーに対して有効なポリシー **になります** 。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-179">If there are no Group Policies and each scope's execution policy is set to **Undefined** , then **Restricted** becomes the effective policy for all users.</span></span>

<span data-ttu-id="a5d6f-180">許容される実行ポリシーの値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-180">The acceptable execution policy values are as follows:</span></span>

- <span data-ttu-id="a5d6f-181">**AllSigned** 。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-181">**AllSigned** .</span></span> <span data-ttu-id="a5d6f-182">では、すべてのスクリプトと構成ファイルが、信頼された発行元によって署名されている必要があります (ローカルコンピューターで作成されたスクリプトを含む)。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-182">Requires that all scripts and configuration files are signed by a trusted publisher, including scripts written on the local computer.</span></span>
- <span data-ttu-id="a5d6f-183">**バイパス** 。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-183">**Bypass** .</span></span> <span data-ttu-id="a5d6f-184">何もブロックされず、警告やプロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-184">Nothing is blocked and there are no warnings or prompts.</span></span>
- <span data-ttu-id="a5d6f-185">**Default** 。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-185">**Default** .</span></span> <span data-ttu-id="a5d6f-186">既定の実行ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-186">Sets the default execution policy.</span></span> <span data-ttu-id="a5d6f-187">Windows クライアントの場合は、Windows サーバーの場合は **RemoteSigned** に **制限** されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-187">**Restricted** for Windows clients or **RemoteSigned** for Windows servers.</span></span>
- <span data-ttu-id="a5d6f-188">**RemoteSigned** 。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-188">**RemoteSigned** .</span></span> <span data-ttu-id="a5d6f-189">では、インターネットからダウンロードしたすべてのスクリプトと構成ファイルが信頼された発行元によって署名されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-189">Requires that all scripts and configuration files downloaded from the Internet are signed by a trusted publisher.</span></span> <span data-ttu-id="a5d6f-190">Windows server コンピューターの既定の実行ポリシー。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-190">The default execution policy for Windows server computers.</span></span>
- <span data-ttu-id="a5d6f-191">**制限付き** 。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-191">**Restricted** .</span></span> <span data-ttu-id="a5d6f-192">構成ファイルの読み込みやスクリプトの実行を行いません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-192">Doesn't load configuration files or run scripts.</span></span> <span data-ttu-id="a5d6f-193">既定の実行ポリシー Windows クライアントコンピューター。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-193">The default execution policy Windows client computers.</span></span>
- <span data-ttu-id="a5d6f-194">**未定義** 。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-194">**Undefined** .</span></span> <span data-ttu-id="a5d6f-195">スコープに対して実行ポリシーが設定されていません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-195">No execution policy is set for the scope.</span></span> <span data-ttu-id="a5d6f-196">グループポリシーによって設定されていないスコープから、割り当てられた実行ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-196">Removes an assigned execution policy from a scope that is not set by a Group Policy.</span></span> <span data-ttu-id="a5d6f-197">すべてのスコープの実行ポリシーが **定義** されていない場合は、有効な実行ポリシーが **制限** されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-197">If the execution policy in all scopes is **Undefined** , the effective execution policy is **Restricted** .</span></span>
- <span data-ttu-id="a5d6f-198">**無制限** 。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-198">**Unrestricted** .</span></span> <span data-ttu-id="a5d6f-199">PowerShell 6.0 以降では、これは Windows 以外のコンピューターの既定の実行ポリシーであり、変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-199">Beginning in PowerShell 6.0, this is the default execution policy for non-Windows computers and can't be changed.</span></span> <span data-ttu-id="a5d6f-200">すべての構成ファイルを読み込んで、すべてのスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-200">Loads all configuration files and runs all scripts.</span></span> <span data-ttu-id="a5d6f-201">インターネットからダウンロードした未署名のスクリプトを実行すると、実行前にアクセス許可を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-201">If you run an unsigned script that was downloaded from the internet, you're prompted for permission before it runs.</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicy
Parameter Sets: (All)
Aliases:
Accepted values: AllSigned, Bypass, Default, RemoteSigned, Restricted, Undefined, Unrestricted

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a5d6f-202">-Force</span><span class="sxs-lookup"><span data-stu-id="a5d6f-202">-Force</span></span>

<span data-ttu-id="a5d6f-203">すべての確認プロンプトを表示しないようにします。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-203">Suppresses all the confirmation prompts.</span></span> <span data-ttu-id="a5d6f-204">予期しない結果が発生しないようにするには、このパラメーターで注意してください。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-204">Use caution with this parameter to avoid unexpected results.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a5d6f-205">-スコープ</span><span class="sxs-lookup"><span data-stu-id="a5d6f-205">-Scope</span></span>

<span data-ttu-id="a5d6f-206">実行ポリシーの影響を受けるスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-206">Specifies the scope that is affected by an execution policy.</span></span> <span data-ttu-id="a5d6f-207">既定のスコープは **LocalMachine** です。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-207">The default scope is **LocalMachine** .</span></span>

<span data-ttu-id="a5d6f-208">有効な実行ポリシーは、次のように優先順位によって決まります。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-208">The effective execution policy is determined by the order of precedence as follows:</span></span>

- <span data-ttu-id="a5d6f-209">**Machinepolicy** 。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-209">**MachinePolicy** .</span></span> <span data-ttu-id="a5d6f-210">コンピューターのすべてのユーザーに対してグループポリシーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-210">Set by a Group Policy for all users of the computer.</span></span>
- <span data-ttu-id="a5d6f-211">**Userpolicy** 。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-211">**UserPolicy** .</span></span> <span data-ttu-id="a5d6f-212">コンピューターの現在のユーザーのグループポリシーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-212">Set by a Group Policy for the current user of the computer.</span></span>
- <span data-ttu-id="a5d6f-213">**プロセス** 。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-213">**Process** .</span></span> <span data-ttu-id="a5d6f-214">現在の PowerShell セッションにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-214">Affects only the current PowerShell session.</span></span>
- <span data-ttu-id="a5d6f-215">**CurrentUser** 。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-215">**CurrentUser** .</span></span> <span data-ttu-id="a5d6f-216">現在のユーザーのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-216">Affects only the current user.</span></span>
- <span data-ttu-id="a5d6f-217">**LocalMachine** 。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-217">**LocalMachine** .</span></span> <span data-ttu-id="a5d6f-218">コンピューターのすべてのユーザーに影響する既定のスコープ。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-218">Default scope that affects all users of the computer.</span></span>

<span data-ttu-id="a5d6f-219">**プロセス** のスコープは、現在の PowerShell セッションにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-219">The **Process** scope only affects the current PowerShell session.</span></span> <span data-ttu-id="a5d6f-220">実行ポリシーは、レジストリではなく、環境変数に保存され `$env:PSExecutionPolicyPreference` ます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-220">The execution policy is saved in the environment variable `$env:PSExecutionPolicyPreference`, rather than the registry.</span></span> <span data-ttu-id="a5d6f-221">PowerShell セッションが終了すると、変数と値が削除されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-221">When the PowerShell session is closed, the variable and value are deleted.</span></span>

<span data-ttu-id="a5d6f-222">**CurrentUser** スコープの実行ポリシーは、レジストリハイブ **HKEY_LOCAL_USER** に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-222">Execution policies for the **CurrentUser** scope are written to the registry hive **HKEY_LOCAL_USER** .</span></span>

<span data-ttu-id="a5d6f-223">**LocalMachine** スコープの実行ポリシーは、レジストリハイブ **HKEY_LOCAL_MACHINE** に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-223">Execution policies for the **LocalMachine** scope are written to the registry hive **HKEY_LOCAL_MACHINE** .</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicyScope
Parameter Sets: (All)
Aliases:
Accepted values: CurrentUser, LocalMachine, MachinePolicy, Process, UserPolicy

Required: False
Position: 1
Default value: LocalMachine
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a5d6f-224">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a5d6f-224">-WhatIf</span></span>

<span data-ttu-id="a5d6f-225">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-225">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a5d6f-226">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-226">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a5d6f-227">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a5d6f-227">CommonParameters</span></span>

<span data-ttu-id="a5d6f-228">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-228">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a5d6f-229">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-229">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a5d6f-230">入力</span><span class="sxs-lookup"><span data-stu-id="a5d6f-230">INPUTS</span></span>

### <span data-ttu-id="a5d6f-231">Microsoft.PowerShell.ExecutionPolicy、System.string</span><span class="sxs-lookup"><span data-stu-id="a5d6f-231">Microsoft.PowerShell.ExecutionPolicy, System.String</span></span>

<span data-ttu-id="a5d6f-232">パイプを使用して、実行ポリシーオブジェクトまたは実行ポリシーの名前を含む文字列をにパイプすることができ `Set-ExecutionPolicy` ます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-232">You can pipe an execution policy object or a string that contains the name of an execution policy to `Set-ExecutionPolicy`.</span></span>

## <span data-ttu-id="a5d6f-233">出力</span><span class="sxs-lookup"><span data-stu-id="a5d6f-233">OUTPUTS</span></span>

### <span data-ttu-id="a5d6f-234">なし</span><span class="sxs-lookup"><span data-stu-id="a5d6f-234">None</span></span>

<span data-ttu-id="a5d6f-235">`Set-ExecutionPolicy` は出力を返しません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-235">`Set-ExecutionPolicy` doesn't return any output.</span></span>

## <span data-ttu-id="a5d6f-236">注</span><span class="sxs-lookup"><span data-stu-id="a5d6f-236">NOTES</span></span>

<span data-ttu-id="a5d6f-237">`Set-ExecutionPolicy`**machinepolicy** および **userpolicy** スコープは、グループポリシーによって設定されているため、変更しません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-237">`Set-ExecutionPolicy` doesn't change the **MachinePolicy** and **UserPolicy** scopes because they are set by Group Policies.</span></span>

<span data-ttu-id="a5d6f-238">`Set-ExecutionPolicy` では、ユーザー設定がポリシーよりも制限が厳しい場合でも、グループポリシーはオーバーライドされません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-238">`Set-ExecutionPolicy` doesn't override a Group Policy, even if the user preference is more restrictive than the policy.</span></span>

<span data-ttu-id="a5d6f-239">コンピューターまたはユーザーに対してグループポリシーの **スクリプト実行** を有効にすると、ユーザー設定は保存されますが、有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-239">If the Group Policy **Turn on Script Execution** is enabled for the computer or user, the user preference is saved, but it is not effective.</span></span> <span data-ttu-id="a5d6f-240">PowerShell では、競合について説明するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a5d6f-240">PowerShell displays a message that explains the conflict.</span></span>

## <span data-ttu-id="a5d6f-241">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a5d6f-241">RELATED LINKS</span></span>

[<span data-ttu-id="a5d6f-242">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="a5d6f-242">about_Execution_Policies</span></span>](../Microsoft.PowerShell.Core/About/about_Execution_Policies.md)

[<span data-ttu-id="a5d6f-243">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="a5d6f-243">about_Group_Policy_Settings</span></span>](../Microsoft.PowerShell.Core/About/about_Group_Policy_Settings.md)

[<span data-ttu-id="a5d6f-244">about_Providers</span><span class="sxs-lookup"><span data-stu-id="a5d6f-244">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="a5d6f-245">Get-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="a5d6f-245">Get-AuthenticodeSignature</span></span>](Get-AuthenticodeSignature.md)

[<span data-ttu-id="a5d6f-246">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="a5d6f-246">Get-ChildItem</span></span>](../Microsoft.PowerShell.Management/Get-ChildItem.md)

[<span data-ttu-id="a5d6f-247">Get-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="a5d6f-247">Get-ExecutionPolicy</span></span>](Get-ExecutionPolicy.md)

[<span data-ttu-id="a5d6f-248">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="a5d6f-248">Invoke-Command</span></span>](../Microsoft.PowerShell.Core/Invoke-Command.md)

[<span data-ttu-id="a5d6f-249">Set-AuthenticodeSignature</span><span class="sxs-lookup"><span data-stu-id="a5d6f-249">Set-AuthenticodeSignature</span></span>](Set-AuthenticodeSignature.md)

[<span data-ttu-id="a5d6f-250">Unblock-File</span><span class="sxs-lookup"><span data-stu-id="a5d6f-250">Unblock-File</span></span>](../Microsoft.PowerShell.Utility/Unblock-File.md)
