---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/04/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Computer
ms.openlocfilehash: 89e43220a8d5ac675ea232db09cf3edec2ca2b97
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214560"
---
# <span data-ttu-id="c18b7-103">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="c18b7-103">Remove-Computer</span></span>

## <span data-ttu-id="c18b7-104">概要</span><span class="sxs-lookup"><span data-stu-id="c18b7-104">SYNOPSIS</span></span>
<span data-ttu-id="c18b7-105">ドメインからローカル コンピューターを削除します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-105">Removes the local computer from its domain.</span></span>

## <span data-ttu-id="c18b7-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c18b7-106">SYNTAX</span></span>

### <span data-ttu-id="c18b7-107">Local (既定値)</span><span class="sxs-lookup"><span data-stu-id="c18b7-107">Local (Default)</span></span>

```
Remove-Computer [[-UnjoinDomainCredential] <PSCredential>] [-Restart] [-Force] [-PassThru]
 [-WorkgroupName <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c18b7-108">リモート</span><span class="sxs-lookup"><span data-stu-id="c18b7-108">Remote</span></span>

```
Remove-Computer -UnjoinDomainCredential <PSCredential> [-LocalCredential <PSCredential>] [-Restart]
 [-ComputerName <String[]>] [-Force] [-PassThru] [-WorkgroupName <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="c18b7-109">Description</span><span class="sxs-lookup"><span data-stu-id="c18b7-109">DESCRIPTION</span></span>

<span data-ttu-id="c18b7-110">コマンドレットでは、 `Remove-Computer` ローカルコンピューターとリモートコンピューターを現在のドメインから削除します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-110">The `Remove-Computer` cmdlet removes the local computer and remote computers from their current domains.</span></span>

<span data-ttu-id="c18b7-111">ドメインからコンピューターを削除すると、によって、 `Remove-Computer` コンピューターのドメインアカウントも無効になります。</span><span class="sxs-lookup"><span data-stu-id="c18b7-111">When you remove a computer from a domain, `Remove-Computer` also disables the domain account of the computer.</span></span> <span data-ttu-id="c18b7-112">現在のユーザーの資格情報であっても、ドメインからコンピューターを切断するには、明示的な資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c18b7-112">You must provide explicit credentials to unjoin the computer from its domain, even when they are the credentials of the current user.</span></span> <span data-ttu-id="c18b7-113">変更を有効にするには、コンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c18b7-113">You must restart the computer to make the change effective.</span></span> <span data-ttu-id="c18b7-114">ドメインからコンピューターを削除する際に、コンピューターをワークグループに移動する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="c18b7-114">Also, when you remove a computer from a domain, you must move it to a workgroup.</span></span> <span data-ttu-id="c18b7-115">**WorkgroupName** パラメーターを使用して、ワークグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-115">Use the **WorkgroupName** parameter to specify the workgroup.</span></span>

<span data-ttu-id="c18b7-116">ワークグループからドメイン、あるワークグループから別のワークグループ、またはあるドメインから別のドメインにコンピューターを移動するには、`Add-Computer` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-116">To move a computer from a workgroup to a domain, from one workgroup to another, or from one domain to another, use the `Add-Computer` cmdlet.</span></span>

<span data-ttu-id="c18b7-117">コマンドの結果を取得するには、 **Verbose** パラメーターと **PassThru** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-117">To get the results of the command, use the **Verbose** and **PassThru** parameters.</span></span> <span data-ttu-id="c18b7-118">ユーザー プロンプトが表示されないようにするには、 **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-118">To suppress the user prompt, use the **Force** parameter.</span></span>

<span data-ttu-id="c18b7-119">`Remove-Computer` ローカルコンピューターとリモートコンピューターをドメインから削除します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-119">`Remove-Computer` removes the local computer and remote computers from domains.</span></span> <span data-ttu-id="c18b7-120">このコマンドレットには、リモート コンピューターに接続してドメインから削除するための代替資格情報を指定する資格情報パラメーター、影響を受けたコンピューターを再起動する **Restart** パラメーター、コンピューターの追加先のワークグループ名を指定する **WorkgroupName** パラメーターなどのパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="c18b7-120">It includes credential parameters that specify alternate credentials for connecting to remote computers, and unjoining from a domain, a **Restart** parameter for restarting the affected computers, and a **WorkgroupName** parameter for specifying the name of the workgroup to which computers are added.</span></span>

## <span data-ttu-id="c18b7-121">例</span><span class="sxs-lookup"><span data-stu-id="c18b7-121">EXAMPLES</span></span>

### <span data-ttu-id="c18b7-122">例 1: ローカルコンピューターをドメインから削除する</span><span class="sxs-lookup"><span data-stu-id="c18b7-122">Example 1: Remove the local computer from its domain</span></span>

<span data-ttu-id="c18b7-123">この例では、ローカルコンピューターが参加先のドメインから削除されます。</span><span class="sxs-lookup"><span data-stu-id="c18b7-123">This example removes the local computer from the domain to which it is joined.</span></span>

```powershell
Remove-Computer -UnjoinDomaincredential Domain01\Admin01 -PassThru -Verbose -Restart
```

<span data-ttu-id="c18b7-124">**UnjoinDomainCredential** パラメーターは、ドメイン管理者の資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-124">The **UnjoinDomainCredential** parameter provides the credentials of a domain administrator.</span></span> <span data-ttu-id="c18b7-125">**PassThru** および **Verbose** 共通パラメーターには、コマンドの成功または失敗に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c18b7-125">The **PassThru** and the **Verbose** common parameters display information about the success or failure of the command.</span></span> <span data-ttu-id="c18b7-126">**Restart** パラメーターを指定すると、コンピューターが再起動され、削除操作が完了します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-126">The **Restart** parameter restarts the computer to complete the remove operation.</span></span>

<span data-ttu-id="c18b7-127">ワークグループ名が指定されていない場合、コンピューターはドメインから削除された後、という名前のワークグループに移動されます。</span><span class="sxs-lookup"><span data-stu-id="c18b7-127">When no workgroup name is specified, the computer is moved to the workgroup named after it is removed from its domain.</span></span>

### <span data-ttu-id="c18b7-128">例 2: 従来のワークグループに複数のコンピューターを移動する</span><span class="sxs-lookup"><span data-stu-id="c18b7-128">Example 2: Move several computers to a legacy workgroup</span></span>

<span data-ttu-id="c18b7-129">この例では、ファイルに一覧表示されているすべてのコンピューターを `OldServers.txt` ドメインから削除し、 **従来** のワークグループに移動します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-129">This example removes all the computers listed in the `OldServers.txt` file from their domains and moves them into the **Legacy** workgroup.</span></span>

```powershell
Remove-Computer -ComputerName (Get-Content OldServers.txt) -LocalCredential Domain01\Admin01 -UnJoinDomainCredential Domain01\Admin01 -WorkgroupName "Legacy" -Force -Restart
```

<span data-ttu-id="c18b7-130">**Localcredential** パラメーターは、リモートコンピューターに接続するアクセス許可を持つユーザーの資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-130">The **LocalCredential** parameter provides the credentials of a user who has permission to connect to remote computers.</span></span> <span data-ttu-id="c18b7-131">**UnjoinDomainCredential** パラメーターは、ドメインからコンピューターを削除するアクセス許可を持つユーザーの資格情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-131">The **UnjoinDomainCredential** parameter provides the credentials of a user who has permission to remove the computers from their domains.</span></span> <span data-ttu-id="c18b7-132">**Force** パラメーターを指定すると、各コンピューターの確認プロンプトが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="c18b7-132">The **Force** parameter suppresses the confirmation prompts for each computer.</span></span> <span data-ttu-id="c18b7-133">**Restart** パラメーターを指定すると、各コンピューターがドメインから削除された後に再起動されます。</span><span class="sxs-lookup"><span data-stu-id="c18b7-133">The **Restart** parameter restarts each of the computers after it is removed from its domain.</span></span>

### <span data-ttu-id="c18b7-134">例 3: 確認せずにワークグループからコンピューターを削除する</span><span class="sxs-lookup"><span data-stu-id="c18b7-134">Example 3: Remove computers from a workgroup without confirmation</span></span>

<span data-ttu-id="c18b7-135">この例では、リモートコンピューター、Server01、およびローカルコンピューターをドメインから削除し、 **ローカル** ワークグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-135">This example removes the remote computer, Server01, and the local computer from their domains and adds them to the **Local** workgroup.</span></span>

```powershell
Remove-Computer -ComputerName "Server01", "localhost" -UnjoinDomainCredential Domain01\Admin01 -WorkgroupName "Local" -Restart -Force
```

<span data-ttu-id="c18b7-136">**Force** パラメーターを指定すると、各コンピューターの確認プロンプトが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="c18b7-136">The **Force** parameter suppresses the confirmation prompt for each computer.</span></span> <span data-ttu-id="c18b7-137">**Restart** パラメーターを使用すると、コンピューターが再起動され、変更が有効になります。</span><span class="sxs-lookup"><span data-stu-id="c18b7-137">The **Restart** parameter restarts the computers to make the change effective.</span></span>

## <span data-ttu-id="c18b7-138">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c18b7-138">PARAMETERS</span></span>

### <span data-ttu-id="c18b7-139">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="c18b7-139">-ComputerName</span></span>

<span data-ttu-id="c18b7-140">ドメインから削除するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-140">Specifies the computers to be removed from their domains.</span></span> <span data-ttu-id="c18b7-141">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="c18b7-141">The default is the local computer.</span></span>

<span data-ttu-id="c18b7-142">リモートコンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-142">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of the remote computers.</span></span> <span data-ttu-id="c18b7-143">ローカルコンピューターを指定するには、コンピューター名、ドット (.)、または localhost を入力します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-143">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="c18b7-144">このパラメーターは、PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="c18b7-144">This parameter does not rely on PowerShell remoting.</span></span> <span data-ttu-id="c18b7-145">**ComputerName** `Remove-Computer` コンピューターがリモートコマンドを実行するように構成されていない場合でも、の ComputerName パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c18b7-145">You can use the **ComputerName** parameter of `Remove-Computer` even if your computer is not configured to run remote commands.</span></span>

<span data-ttu-id="c18b7-146">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c18b7-146">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c18b7-147">-Force</span><span class="sxs-lookup"><span data-stu-id="c18b7-147">-Force</span></span>

<span data-ttu-id="c18b7-148">ユーザー プロンプトが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="c18b7-148">Suppresses the user prompt.</span></span> <span data-ttu-id="c18b7-149">既定では、 `Remove-Computer` 各コンピューターを削除する前に、確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c18b7-149">By default, `Remove-Computer` prompts you for confirmation before removing each computer.</span></span>

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

### <span data-ttu-id="c18b7-150">-LocalCredential</span><span class="sxs-lookup"><span data-stu-id="c18b7-150">-LocalCredential</span></span>

<span data-ttu-id="c18b7-151">**ComputerName** パラメーターによって指定されたコンピューターに接続するためのアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-151">Specifies a user account that has permission to connect to the computers that the **ComputerName** parameter specifies.</span></span> <span data-ttu-id="c18b7-152">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="c18b7-152">The default is the current user.</span></span>

<span data-ttu-id="c18b7-153">またはなどのユーザー名を入力する `User01` `Domain01\User01` か、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="c18b7-153">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="c18b7-154">ユーザー名を入力すると、コマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="c18b7-154">If you type a user name, the cmdlet prompts you for a password.</span></span> <span data-ttu-id="c18b7-155">コンピューターを現在のドメインから削除するアクセス許可を持つユーザー アカウントを指定するには、 **UnjoinDomainCredential** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-155">To specify a user account that has permission to remove the computer from its current domain, use the **UnjoinDomainCredential** parameter.</span></span>

<span data-ttu-id="c18b7-156">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c18b7-156">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Remote
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c18b7-157">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c18b7-157">-PassThru</span></span>

<span data-ttu-id="c18b7-158">コマンドの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-158">Returns the results of the command.</span></span> <span data-ttu-id="c18b7-159">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="c18b7-159">Otherwise, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="c18b7-160">-Restart</span><span class="sxs-lookup"><span data-stu-id="c18b7-160">-Restart</span></span>

<span data-ttu-id="c18b7-161">このコマンドレットにより、削除されているコンピューターが再起動されることを示します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-161">Indicates that this cmdlet restarts the computers that are being removed.</span></span> <span data-ttu-id="c18b7-162">多くの場合、変更を有効にするには再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="c18b7-162">A restart is often required to make the change effective.</span></span>

<span data-ttu-id="c18b7-163">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c18b7-163">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c18b7-164">-UnjoinDomainCredential</span><span class="sxs-lookup"><span data-stu-id="c18b7-164">-UnjoinDomainCredential</span></span>

<span data-ttu-id="c18b7-165">コンピューターを現在のドメインから削除するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-165">Specifies a user account that has permission to remove the computers from their current domains.</span></span>
<span data-ttu-id="c18b7-166">ドメインからリモート コンピューターを削除するには、このパラメーターに資格情報を、それが現在のユーザーの資格情報であっても明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c18b7-166">Explicit credentials, as provided by this parameter, are required to remove remote computers from a domain, even when the value is the credentials of the current user.</span></span>

<span data-ttu-id="c18b7-167">User01 や Domain01\user01」などのユーザー名を入力するか、によって生成された **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="c18b7-167">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by `Get-Credential`.</span></span> <span data-ttu-id="c18b7-168">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="c18b7-168">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="c18b7-169">リモート コンピューターに接続するアクセス許可を持つユーザー アカウントを指定するには、 **LocalCredential** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-169">To specify a user account that has permission to connect to the remote computers, use the **LocalCredential** parameter.</span></span>

<span data-ttu-id="c18b7-170">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c18b7-170">This parameter was introduced in PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Local, Remote
Aliases: Credential

Required: False (Local), True (Remote)
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c18b7-171">-ワークスペース</span><span class="sxs-lookup"><span data-stu-id="c18b7-171">-WorkgroupName</span></span>

<span data-ttu-id="c18b7-172">ドメインから削除したコンピューターの追加先ワークグループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-172">Specifies the name of a workgroup to which the computers are added when they are removed from their domains.</span></span> <span data-ttu-id="c18b7-173">既定値は **WORKGROUP** です。</span><span class="sxs-lookup"><span data-stu-id="c18b7-173">The default value is **WORKGROUP** .</span></span> <span data-ttu-id="c18b7-174">ドメインからコンピューターを削除する際に、コンピューターをワークグループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c18b7-174">When you remove a computer from a domain, you must add it to a workgroup.</span></span>

<span data-ttu-id="c18b7-175">このパラメーターは、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c18b7-175">This parameter was introduced in PowerShell 3.0.</span></span>

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

### <span data-ttu-id="c18b7-176">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c18b7-176">-Confirm</span></span>

<span data-ttu-id="c18b7-177">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c18b7-177">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c18b7-178">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c18b7-178">-WhatIf</span></span>

<span data-ttu-id="c18b7-179">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-179">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="c18b7-180">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c18b7-180">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c18b7-181">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c18b7-181">CommonParameters</span></span>

<span data-ttu-id="c18b7-182">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c18b7-182">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c18b7-183">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c18b7-183">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c18b7-184">入力</span><span class="sxs-lookup"><span data-stu-id="c18b7-184">INPUTS</span></span>

### <span data-ttu-id="c18b7-185">System.String</span><span class="sxs-lookup"><span data-stu-id="c18b7-185">System.String</span></span>

<span data-ttu-id="c18b7-186">パイプを使用してコンピューター名を thiscmdlet に送ることができます。</span><span class="sxs-lookup"><span data-stu-id="c18b7-186">You can pipe computer names to thiscmdlet.</span></span>

## <span data-ttu-id="c18b7-187">出力</span><span class="sxs-lookup"><span data-stu-id="c18b7-187">OUTPUTS</span></span>

### <span data-ttu-id="c18b7-188">Microsoft. PowerShell. ComputerChangeInfo</span><span class="sxs-lookup"><span data-stu-id="c18b7-188">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="c18b7-189">**PassThru** パラメーターを使用すると、は `Remove-Computer` **computerchangeinfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c18b7-189">When you use the **PassThru** parameter, `Remove-Computer` returns a **ComputerChangeInfo** object.</span></span>
<span data-ttu-id="c18b7-190">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="c18b7-190">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c18b7-191">注</span><span class="sxs-lookup"><span data-stu-id="c18b7-191">NOTES</span></span>

<span data-ttu-id="c18b7-192">このコマンドレットは、コンピューターをワークグループから削除しません。</span><span class="sxs-lookup"><span data-stu-id="c18b7-192">This cmdlet does not remove computers from workgroups.</span></span>

## <span data-ttu-id="c18b7-193">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c18b7-193">RELATED LINKS</span></span>

[<span data-ttu-id="c18b7-194">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="c18b7-194">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="c18b7-195">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="c18b7-195">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="c18b7-196">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="c18b7-196">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="c18b7-197">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="c18b7-197">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="c18b7-198">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="c18b7-198">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="c18b7-199">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="c18b7-199">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="c18b7-200">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="c18b7-200">Stop-Computer</span></span>](Stop-Computer.md)

[<span data-ttu-id="c18b7-201">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="c18b7-201">Test-Connection</span></span>](Test-Connection.md)
