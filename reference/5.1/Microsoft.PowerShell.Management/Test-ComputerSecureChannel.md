---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/test-computersecurechannel?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-ComputerSecureChannel
ms.openlocfilehash: 20ea76e725a8ab53d7090078dc819a6297a639ff
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214344"
---
# <span data-ttu-id="8262c-103">Test-ComputerSecureChannel</span><span class="sxs-lookup"><span data-stu-id="8262c-103">Test-ComputerSecureChannel</span></span>

## <span data-ttu-id="8262c-104">概要</span><span class="sxs-lookup"><span data-stu-id="8262c-104">SYNOPSIS</span></span>
<span data-ttu-id="8262c-105">ローカル コンピューターとそのドメインの間のセキュリティで保護されたチャネルをテストして修復します。</span><span class="sxs-lookup"><span data-stu-id="8262c-105">Tests and repairs the secure channel between the local computer and its domain.</span></span>

## <span data-ttu-id="8262c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8262c-106">SYNTAX</span></span>

```
Test-ComputerSecureChannel [-Repair] [-Server <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="8262c-107">Description</span><span class="sxs-lookup"><span data-stu-id="8262c-107">DESCRIPTION</span></span>
<span data-ttu-id="8262c-108">**Test ComputerSecureChannel** コマンドレットは、ローカルコンピューターとそのドメインの間のチャネルが、信頼関係の状態を確認することによって正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8262c-108">The **Test-ComputerSecureChannel** cmdlet verifies that the channel between the local computer and its domain is working correctly by checking the status of its trust relationships.</span></span>
<span data-ttu-id="8262c-109">接続に失敗した場合は、 *Repair* パラメーターを使用して復元を試みることができます。</span><span class="sxs-lookup"><span data-stu-id="8262c-109">If a connection fails, you can use the *Repair* parameter to try to restore it.</span></span>

<span data-ttu-id="8262c-110">**テスト-ComputerSecureChannel** は、チャネルが正常に機能している場合は $True を返し、そうでない場合は $False を返します。</span><span class="sxs-lookup"><span data-stu-id="8262c-110">**Test-ComputerSecureChannel** returns $True if the channel is working correctly and $False if it is not.</span></span>
<span data-ttu-id="8262c-111">この結果を受けて、コマンドレットを関数とスクリプトの条件ステートメントに使用できます。</span><span class="sxs-lookup"><span data-stu-id="8262c-111">This result lets you use the cmdlet in conditional statements in functions and scripts.</span></span>
<span data-ttu-id="8262c-112">詳細なテスト結果を取得するには、 *Verbose* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8262c-112">To get more detailed test results, use the *Verbose* parameter.</span></span>

<span data-ttu-id="8262c-113">このコマンドレットは NetDom.exe と同様に機能します。</span><span class="sxs-lookup"><span data-stu-id="8262c-113">This cmdlet works much like NetDom.exe.</span></span>
<span data-ttu-id="8262c-114">NetDom と **Test ComputerSecureChannel** はどちらも **NetLogon** サービスを使用してアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="8262c-114">Both NetDom and **Test-ComputerSecureChannel** use the **NetLogon** service to perform the actions.</span></span>

## <span data-ttu-id="8262c-115">例</span><span class="sxs-lookup"><span data-stu-id="8262c-115">EXAMPLES</span></span>

### <span data-ttu-id="8262c-116">例 1: ローカルコンピューターとそのドメインの間のチャネルをテストする</span><span class="sxs-lookup"><span data-stu-id="8262c-116">Example 1: Test a channel between the local computer and its domain</span></span>

```
PS C:\> Test-ComputerSecureChannel
True
```

<span data-ttu-id="8262c-117">このコマンドは、ローカルコンピューターと、それが参加しているドメインとの間のチャネルをテストします。</span><span class="sxs-lookup"><span data-stu-id="8262c-117">This command tests the channel between the local computer and the domain to which it is joined.</span></span>

### <span data-ttu-id="8262c-118">例 2: ローカルコンピューターとドメインコントローラーの間でチャネルをテストする</span><span class="sxs-lookup"><span data-stu-id="8262c-118">Example 2: Test a channel between the local computer and a domain controller</span></span>

```
PS C:\> Test-ComputerSecureChannel -Server "DCName.fabrikam.com"
True
```

<span data-ttu-id="8262c-119">このコマンドは、テストで優先的に使用するドメイン コントローラーを指定します。</span><span class="sxs-lookup"><span data-stu-id="8262c-119">This command specifies a preferred domain controller for the test.</span></span>

### <span data-ttu-id="8262c-120">例 3: ローカルコンピューターとそのドメインの間のチャネルをリセットする</span><span class="sxs-lookup"><span data-stu-id="8262c-120">Example 3: Reset the channel between the local computer and its domain</span></span>

```
PS C:\> Test-ComputerSecureChannel -Repair
True
```

<span data-ttu-id="8262c-121">このコマンドは、ローカルコンピューターとそのドメインの間のチャネルをリセットします。</span><span class="sxs-lookup"><span data-stu-id="8262c-121">This command resets the channel between the local computer and its domain.</span></span>

### <span data-ttu-id="8262c-122">例 4: テストに関する詳細情報を表示する</span><span class="sxs-lookup"><span data-stu-id="8262c-122">Example 4: Display detailed information about the test</span></span>

```
PS C:\> Test-ComputerSecureChannel -verbose
VERBOSE: Performing operation "Test-ComputerSecureChannel" on Target "SERVER01".
True
VERBOSE: "The secure channel between 'SERVER01' and 'net.fabrikam.com' is alive and working correctly."
```

<span data-ttu-id="8262c-123">このコマンドは、 *Verbose* 共通パラメーターを使用して、操作に関する詳細なメッセージを要求します。</span><span class="sxs-lookup"><span data-stu-id="8262c-123">This command uses the *Verbose* common parameter to request detailed messages about the operation.</span></span>
<span data-ttu-id="8262c-124">詳細 *については、「* about_CommonParameters」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8262c-124">For more information about *Verbose* , see about_CommonParameters.</span></span>

### <span data-ttu-id="8262c-125">例 5: スクリプトを実行する前に接続をテストする</span><span class="sxs-lookup"><span data-stu-id="8262c-125">Example 5: Test a connection before you run a script</span></span>

```
PS C:\> Set-Alias tcsc Test-ComputerSecureChannel
if (!(tcsc))
{Write-Host "Connection failed. Reconnect and retry."}
else { &(.\Get-Servers.ps1) }
```

<span data-ttu-id="8262c-126">この例では、接続を必要とするスクリプトを実行する前に、 **テスト用の ComputerSecureChannel** を使用して接続をテストする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8262c-126">This example shows how to use **Test-ComputerSecureChannel** to test a connection before you run a script that requires the connection.</span></span>

<span data-ttu-id="8262c-127">最初のコマンドは、Set-Alias コマンドレットを使用してコマンドレット名のエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8262c-127">The first command uses the Set-Alias cmdlet to create an alias for the cmdlet name.</span></span>
<span data-ttu-id="8262c-128">これにより、領域を節約し、入力の間違いを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="8262c-128">This saves space and prevents typing errors.</span></span>

<span data-ttu-id="8262c-129">**If** ステートメントは、スクリプトを実行する前に、 **テストコンピューターの securechannel** が返す値をチェックします。</span><span class="sxs-lookup"><span data-stu-id="8262c-129">The **If** statement checks the value that **Test-ComputerSecureChannel** returns before it runs a script.</span></span>

## <span data-ttu-id="8262c-130">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8262c-130">PARAMETERS</span></span>

### <span data-ttu-id="8262c-131">-Credential</span><span class="sxs-lookup"><span data-stu-id="8262c-131">-Credential</span></span>
<span data-ttu-id="8262c-132">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="8262c-132">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="8262c-133">User01 や Domain01\user01」などのユーザー名を入力するか、Get-Credential コマンドレットが返す **PSCredential** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="8262c-133">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one that the Get-Credential cmdlet returns.</span></span>
<span data-ttu-id="8262c-134">既定では、コマンドレットは現在のユーザーの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="8262c-134">By default, the cmdlet uses the credentials of the current user.</span></span>

<span data-ttu-id="8262c-135">*Credential* パラメーターは、 *repair* パラメーターを使用してコンピューターとドメイン間のチャネルを修復するコマンドで使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="8262c-135">The *Credential* parameter is designed for use in commands that use the *Repair* parameter to repair the channel between the computer and the domain.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="8262c-136">-Repair</span><span class="sxs-lookup"><span data-stu-id="8262c-136">-Repair</span></span>
<span data-ttu-id="8262c-137">このコマンドレットによって、NetLogon サービスによって確立されたチャネルが削除され、再構築されることを示します。</span><span class="sxs-lookup"><span data-stu-id="8262c-137">Indicates that this cmdlet removes and then rebuilds the channel established by the NetLogon service.</span></span>
<span data-ttu-id="8262c-138">テストに失敗した接続の復元を試みるには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="8262c-138">Use this parameter to try to restore a connection that has failed the test.</span></span>

<span data-ttu-id="8262c-139">このパラメーターを使用するには、現在のユーザーは、ローカル コンピューター上の Administrators グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8262c-139">To use this parameter, the current user must be a member of the Administrators group on the local computer.</span></span>

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

### <span data-ttu-id="8262c-140">-Server</span><span class="sxs-lookup"><span data-stu-id="8262c-140">-Server</span></span>
<span data-ttu-id="8262c-141">コマンドを実行するドメインコントローラーを指定します。</span><span class="sxs-lookup"><span data-stu-id="8262c-141">Specifies the domain controller to run the command.</span></span>
<span data-ttu-id="8262c-142">このパラメーターが指定されていない場合、このコマンドレットは操作の既定のドメインコントローラーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8262c-142">If this parameter is not specified, this cmdlet selects a default domain controller for the operation.</span></span>

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

### <span data-ttu-id="8262c-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="8262c-143">-Confirm</span></span>
<span data-ttu-id="8262c-144">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8262c-144">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="8262c-145">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="8262c-145">-WhatIf</span></span>
<span data-ttu-id="8262c-146">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="8262c-146">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="8262c-147">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="8262c-147">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="8262c-148">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8262c-148">CommonParameters</span></span>
<span data-ttu-id="8262c-149">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8262c-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8262c-150">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8262c-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8262c-151">入力</span><span class="sxs-lookup"><span data-stu-id="8262c-151">INPUTS</span></span>

### <span data-ttu-id="8262c-152">なし</span><span class="sxs-lookup"><span data-stu-id="8262c-152">None</span></span>
<span data-ttu-id="8262c-153">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="8262c-153">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="8262c-154">出力</span><span class="sxs-lookup"><span data-stu-id="8262c-154">OUTPUTS</span></span>

### <span data-ttu-id="8262c-155">System.Boolean</span><span class="sxs-lookup"><span data-stu-id="8262c-155">System.Boolean</span></span>
<span data-ttu-id="8262c-156">このコマンドレットは、接続が正常に機能している場合は $True を返し、そうでない場合は $False を返します。</span><span class="sxs-lookup"><span data-stu-id="8262c-156">This cmdlet returns $True if the connection is working correctly and $False if it is not.</span></span>

## <span data-ttu-id="8262c-157">注</span><span class="sxs-lookup"><span data-stu-id="8262c-157">NOTES</span></span>

* <span data-ttu-id="8262c-158">Windows Vista 以降のバージョンの Windows オペレーティングシステムで **テスト用の ComputerSecureChannel** コマンドを実行するには、[管理者として実行] オプションを使用して windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="8262c-158">To run a **Test-ComputerSecureChannel** command on Windows Vista and later versions of the Windows operating system, open Windows PowerShell by using the Run as administrator option.</span></span>
* <span data-ttu-id="8262c-159">**テスト-ComputerSecureChannel** は、Netlogon サービスのさまざまな側面を制御する **I_NetLogonControl2** 関数を使用して実装されます。</span><span class="sxs-lookup"><span data-stu-id="8262c-159">**Test-ComputerSecureChannel** is implemented by using the **I_NetLogonControl2** function, which controls various aspects of the Netlogon service.</span></span>

## <span data-ttu-id="8262c-160">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8262c-160">RELATED LINKS</span></span>

[<span data-ttu-id="8262c-161">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="8262c-161">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="8262c-162">Reset-ComputerMachinePassword</span><span class="sxs-lookup"><span data-stu-id="8262c-162">Reset-ComputerMachinePassword</span></span>](Reset-ComputerMachinePassword.md)

[<span data-ttu-id="8262c-163">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="8262c-163">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="8262c-164">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="8262c-164">Stop-Computer</span></span>](Stop-Computer.md)
