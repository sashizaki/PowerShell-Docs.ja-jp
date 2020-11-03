---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/1/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Computer
ms.openlocfilehash: 860a5ec4f75136bd53fa5c9621504b1613e9c511
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214528"
---
# <span data-ttu-id="78c5a-103">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="78c5a-103">Rename-Computer</span></span>

## <span data-ttu-id="78c5a-104">概要</span><span class="sxs-lookup"><span data-stu-id="78c5a-104">SYNOPSIS</span></span>
<span data-ttu-id="78c5a-105">コンピューターの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-105">Renames a computer.</span></span>

## <span data-ttu-id="78c5a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="78c5a-106">SYNTAX</span></span>

```
Rename-Computer [-ComputerName <String>] [-PassThru] [-DomainCredential <PSCredential>]
 [-LocalCredential <PSCredential>] [-NewName] <String> [-Force] [-Restart] [-WsmanAuthentication <String>]
 [-Protocol <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="78c5a-107">Description</span><span class="sxs-lookup"><span data-stu-id="78c5a-107">DESCRIPTION</span></span>

<span data-ttu-id="78c5a-108">`Rename-Computer`コマンドレットは、ローカルコンピューターまたはリモートコンピューターの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-108">The `Rename-Computer` cmdlet renames the local computer or a remote computer.</span></span>
<span data-ttu-id="78c5a-109">各コマンドで 1 つのコンピューターの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-109">It renames one computer in each command.</span></span>

<span data-ttu-id="78c5a-110">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="78c5a-110">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="78c5a-111">例</span><span class="sxs-lookup"><span data-stu-id="78c5a-111">EXAMPLES</span></span>

### <span data-ttu-id="78c5a-112">例 1: ローカルコンピューターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="78c5a-112">Example 1: Rename the local computer</span></span>

<span data-ttu-id="78c5a-113">このコマンドは、ローカルコンピューターの名前をに変更し、 `Server044` 再起動して変更を有効にします。</span><span class="sxs-lookup"><span data-stu-id="78c5a-113">This command renames the local computer to `Server044` and then restarts it to make the change effective.</span></span>

```powershell
Rename-Computer -NewName "Server044" -DomainCredential Domain01\Admin01 -Restart
```

### <span data-ttu-id="78c5a-114">例 2: リモートコンピューターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="78c5a-114">Example 2: Rename a remote computer</span></span>

<span data-ttu-id="78c5a-115">このコマンドにより、コンピューターの名前 `Srv01` がに変更さ `Server001` れます。</span><span class="sxs-lookup"><span data-stu-id="78c5a-115">This command renames the `Srv01` computer to `Server001`.</span></span> <span data-ttu-id="78c5a-116">コンピューターは再起動されません。</span><span class="sxs-lookup"><span data-stu-id="78c5a-116">The computer is not restarted.</span></span>

<span data-ttu-id="78c5a-117">**DomainCredential** パラメーターは、ドメイン内のコンピューターの名前を変更するアクセス許可を持つユーザーの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-117">The **DomainCredential** parameter specifies the credentials of a user who has permission to rename computers in the domain.</span></span>

<span data-ttu-id="78c5a-118">**Force** パラメーターを指定すると、確認プロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="78c5a-118">The **Force** parameter suppresses the confirmation prompt.</span></span>

```powershell
Rename-Computer -ComputerName "Srv01" -NewName "Server001" -DomainCredential Domain01\Admin01 -Force
```

## <span data-ttu-id="78c5a-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="78c5a-119">PARAMETERS</span></span>

### <span data-ttu-id="78c5a-120">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="78c5a-120">-ComputerName</span></span>

<span data-ttu-id="78c5a-121">指定したリモート コンピューターの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-121">Renames the specified remote computer.</span></span>
<span data-ttu-id="78c5a-122">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="78c5a-122">The default is the local computer.</span></span>

<span data-ttu-id="78c5a-123">リモート コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-123">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="78c5a-124">ローカルコンピューターを指定するには、コンピューター名、ドット ( `.` )、またはを入力し `localhost` ます。</span><span class="sxs-lookup"><span data-stu-id="78c5a-124">To specify the local computer, type the computer name, a dot (`.`), or `localhost`.</span></span>

<span data-ttu-id="78c5a-125">このパラメーターは、PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="78c5a-125">This parameter does not rely on PowerShell remoting.</span></span>
<span data-ttu-id="78c5a-126">**ComputerName** `Rename-Computer` コンピューターがリモートコマンドを実行するように構成されていない場合でも、の ComputerName パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="78c5a-126">You can use the **ComputerName** parameter of `Rename-Computer` even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local Computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="78c5a-127">-DomainCredential</span><span class="sxs-lookup"><span data-stu-id="78c5a-127">-DomainCredential</span></span>

<span data-ttu-id="78c5a-128">ドメインに接続するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-128">Specifies a user account that has permission to connect to the domain.</span></span>
<span data-ttu-id="78c5a-129">ドメインに参加しているコンピューターの名前を変更するには、明示的な資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="78c5a-129">Explicit credentials are required to rename a computer that is joined to a domain.</span></span>

<span data-ttu-id="78c5a-130">またはなどのユーザー名を入力する `User01` `Domain01\User01` か、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="78c5a-130">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="78c5a-131">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="78c5a-131">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="78c5a-132">**ComputerName** パラメーターで指定されたコンピューターに接続するアクセス許可を持つユーザー アカウントを指定するには、 **LocalCredential** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-132">To specify a user account that has permission to connect to the computer that is specified by the **ComputerName** parameter, use the **LocalCredential** parameter.</span></span>

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

### <span data-ttu-id="78c5a-133">-Force</span><span class="sxs-lookup"><span data-stu-id="78c5a-133">-Force</span></span>

<span data-ttu-id="78c5a-134">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-134">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="78c5a-135">-LocalCredential</span><span class="sxs-lookup"><span data-stu-id="78c5a-135">-LocalCredential</span></span>

<span data-ttu-id="78c5a-136">**ComputerName** パラメーターで指定されたコンピューターに接続するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-136">Specifies a user account that has permission to connect to the computer specified by the **ComputerName** parameter.</span></span> <span data-ttu-id="78c5a-137">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="78c5a-137">The default is the current user.</span></span>

<span data-ttu-id="78c5a-138">またはなどのユーザー名を入力する `User01` `Domain01\User01` か、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="78c5a-138">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="78c5a-139">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="78c5a-139">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="78c5a-140">ドメインに接続するアクセス許可を持つユーザー アカウントを指定するには、 **DomainCredential** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-140">To specify a user account that has permission to connect to the domain, use the **DomainCredential** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current User
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="78c5a-141">-NewName</span><span class="sxs-lookup"><span data-stu-id="78c5a-141">-NewName</span></span>

<span data-ttu-id="78c5a-142">コンピューターの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-142">Specifies a new name for the computer.</span></span>
<span data-ttu-id="78c5a-143">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="78c5a-143">This parameter is required.</span></span>

<span data-ttu-id="78c5a-144">標準名には、文字 ( `a-z` )、( `A-Z` )、数字 ( `0-9` )、ハイフン () を含めることができ `-` ますが、スペースやピリオド () は使用できません `.` 。</span><span class="sxs-lookup"><span data-stu-id="78c5a-144">Standard names may contain letters (`a-z`), (`A-Z`), numbers (`0-9`), and hyphens (`-`), but no spaces or periods (`.`).</span></span> <span data-ttu-id="78c5a-145">名前には数字だけを使用することはできません。また、63文字以内にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="78c5a-145">The name may not consist entirely of digits, and may not be longer than 63 characters</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="78c5a-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="78c5a-146">-PassThru</span></span>

<span data-ttu-id="78c5a-147">コマンドの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-147">Returns the results of the command.</span></span>
<span data-ttu-id="78c5a-148">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="78c5a-148">Otherwise, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="78c5a-149">-Protocol</span><span class="sxs-lookup"><span data-stu-id="78c5a-149">-Protocol</span></span>

<span data-ttu-id="78c5a-150">コンピューターの名前を変更するために使用するプロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-150">Specifies which protocol to use to rename the computer.</span></span>
<span data-ttu-id="78c5a-151">このパラメーターに指定できる値は、WSMan と DCOM です。</span><span class="sxs-lookup"><span data-stu-id="78c5a-151">The acceptable values for this parameter are: WSMan and DCOM.</span></span>
<span data-ttu-id="78c5a-152">既定値は DCOM です。</span><span class="sxs-lookup"><span data-stu-id="78c5a-152">The default value is DCOM.</span></span>

<span data-ttu-id="78c5a-153">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="78c5a-153">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: DCOM, WSMan

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="78c5a-154">-Restart</span><span class="sxs-lookup"><span data-stu-id="78c5a-154">-Restart</span></span>

<span data-ttu-id="78c5a-155">このコマンドレットは、名前が変更されたコンピューターを再起動することを示します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-155">Indicates that this cmdlet restarts the computer that was renamed.</span></span>
<span data-ttu-id="78c5a-156">多くの場合、変更を有効にするには再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="78c5a-156">A restart is often required to make the change effective.</span></span>

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

### <span data-ttu-id="78c5a-157">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="78c5a-157">-WsmanAuthentication</span></span>

<span data-ttu-id="78c5a-158">このコマンドレットで WSMan プロトコルを使用するときに、ユーザー資格情報の認証に使用されるメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-158">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="78c5a-159">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="78c5a-159">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="78c5a-160">**Basic**</span><span class="sxs-lookup"><span data-stu-id="78c5a-160">**Basic**</span></span>
- <span data-ttu-id="78c5a-161">**CredSSP**</span><span class="sxs-lookup"><span data-stu-id="78c5a-161">**CredSSP**</span></span>
- <span data-ttu-id="78c5a-162">**[Default]**</span><span class="sxs-lookup"><span data-stu-id="78c5a-162">**Default**</span></span>
- <span data-ttu-id="78c5a-163">**ダイジェスト**</span><span class="sxs-lookup"><span data-stu-id="78c5a-163">**Digest**</span></span>
- <span data-ttu-id="78c5a-164">**Kerberos**</span><span class="sxs-lookup"><span data-stu-id="78c5a-164">**Kerberos**</span></span>
- <span data-ttu-id="78c5a-165">**ネゴシエーション**</span><span class="sxs-lookup"><span data-stu-id="78c5a-165">**Negotiate**</span></span>

<span data-ttu-id="78c5a-166">既定値は **Default** です。</span><span class="sxs-lookup"><span data-stu-id="78c5a-166">The default value is **Default** .</span></span>

<span data-ttu-id="78c5a-167">このパラメーターの値の詳細については、「 [Authenticationmechanism 列挙型](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78c5a-167">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="78c5a-168">ユーザー資格情報が認証対象のリモートコンピューターに渡される Credential Security Service Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="78c5a-168">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
> <span data-ttu-id="78c5a-169">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="78c5a-169">This mechanism increases the security risk of the remote operation.</span></span>
> <span data-ttu-id="78c5a-170">リモートコンピューターが侵害された場合、そのコンピューターに渡された資格情報を使用して、ネットワークセッション > 制御できます。</span><span class="sxs-lookup"><span data-stu-id="78c5a-170">If the remote computer is compromised, the credentials that are passed to it can be used to control > the network session.</span></span>

<span data-ttu-id="78c5a-171">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="78c5a-171">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Default, Basic, Negotiate, CredSSP, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="78c5a-172">-Confirm</span><span class="sxs-lookup"><span data-stu-id="78c5a-172">-Confirm</span></span>

<span data-ttu-id="78c5a-173">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="78c5a-173">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="78c5a-174">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="78c5a-174">-WhatIf</span></span>

<span data-ttu-id="78c5a-175">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-175">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="78c5a-176">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="78c5a-176">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="78c5a-177">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="78c5a-177">CommonParameters</span></span>

<span data-ttu-id="78c5a-178">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="78c5a-178">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="78c5a-179">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78c5a-179">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="78c5a-180">入力</span><span class="sxs-lookup"><span data-stu-id="78c5a-180">INPUTS</span></span>

### <span data-ttu-id="78c5a-181">なし</span><span class="sxs-lookup"><span data-stu-id="78c5a-181">None</span></span>

<span data-ttu-id="78c5a-182">このコマンドレットには、値による入力を受け取るパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="78c5a-182">This cmdlet does not have parameters that take input by value.</span></span>
<span data-ttu-id="78c5a-183">ただし、パイプを使用してオブジェクトの **ComputerName** および **NewName** プロパティの値をこのコマンドレットに渡すことはできます。</span><span class="sxs-lookup"><span data-stu-id="78c5a-183">However, you can pipe the values of the **ComputerName** and **NewName** properties of objects to this cmdlet.</span></span>

## <span data-ttu-id="78c5a-184">出力</span><span class="sxs-lookup"><span data-stu-id="78c5a-184">OUTPUTS</span></span>

### <span data-ttu-id="78c5a-185">Microsoft. PowerShell. ComputerChangeInfo</span><span class="sxs-lookup"><span data-stu-id="78c5a-185">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="78c5a-186">**PassThru** パラメーターを指定した場合、このコマンドレットは **computerchangeinfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="78c5a-186">This cmdlet returns a **ComputerChangeInfo** object, if you specify the **PassThru** parameter.</span></span>
<span data-ttu-id="78c5a-187">それ以外の場合、出力は返しません。</span><span class="sxs-lookup"><span data-stu-id="78c5a-187">Otherwise, it does not return any output.</span></span>

## <span data-ttu-id="78c5a-188">注</span><span class="sxs-lookup"><span data-stu-id="78c5a-188">NOTES</span></span>

## <span data-ttu-id="78c5a-189">関連リンク</span><span class="sxs-lookup"><span data-stu-id="78c5a-189">RELATED LINKS</span></span>

[<span data-ttu-id="78c5a-190">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="78c5a-190">Add-Computer</span></span>](Add-Computer.md)

[<span data-ttu-id="78c5a-191">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="78c5a-191">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="78c5a-192">Reset-ComputerMachinePassword</span><span class="sxs-lookup"><span data-stu-id="78c5a-192">Reset-ComputerMachinePassword</span></span>](Reset-ComputerMachinePassword.md)

[<span data-ttu-id="78c5a-193">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="78c5a-193">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="78c5a-194">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="78c5a-194">Stop-Computer</span></span>](Stop-Computer.md)