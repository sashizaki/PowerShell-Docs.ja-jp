---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/1/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-Computer
ms.openlocfilehash: e2d4f321609a386c6795949a4a706323b4889f69
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216104"
---
# <span data-ttu-id="dc55a-103">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="dc55a-103">Rename-Computer</span></span>

## <span data-ttu-id="dc55a-104">概要</span><span class="sxs-lookup"><span data-stu-id="dc55a-104">SYNOPSIS</span></span>
<span data-ttu-id="dc55a-105">コンピューターの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-105">Renames a computer.</span></span>

## <span data-ttu-id="dc55a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="dc55a-106">SYNTAX</span></span>

```
Rename-Computer [-ComputerName <String>] [-PassThru] [-DomainCredential <PSCredential>]
 [-LocalCredential <PSCredential>] [-NewName] <String> [-Force] [-Restart] [-WsmanAuthentication <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="dc55a-107">Description</span><span class="sxs-lookup"><span data-stu-id="dc55a-107">DESCRIPTION</span></span>

<span data-ttu-id="dc55a-108">`Rename-Computer`コマンドレットは、ローカルコンピューターまたはリモートコンピューターの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-108">The `Rename-Computer` cmdlet renames the local computer or a remote computer.</span></span>
<span data-ttu-id="dc55a-109">各コマンドで 1 つのコンピューターの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-109">It renames one computer in each command.</span></span>

<span data-ttu-id="dc55a-110">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="dc55a-110">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="dc55a-111">例</span><span class="sxs-lookup"><span data-stu-id="dc55a-111">EXAMPLES</span></span>

### <span data-ttu-id="dc55a-112">例 1: ローカルコンピューターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="dc55a-112">Example 1: Rename the local computer</span></span>

<span data-ttu-id="dc55a-113">このコマンドは、ローカルコンピューターの名前をに変更し、 `Server044` 再起動して変更を有効にします。</span><span class="sxs-lookup"><span data-stu-id="dc55a-113">This command renames the local computer to `Server044` and then restarts it to make the change effective.</span></span>

```powershell
Rename-Computer -NewName "Server044" -DomainCredential Domain01\Admin01 -Restart
```

### <span data-ttu-id="dc55a-114">例 2: リモートコンピューターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="dc55a-114">Example 2: Rename a remote computer</span></span>

<span data-ttu-id="dc55a-115">このコマンドにより、コンピューターの名前 `Srv01` がに変更さ `Server001` れます。</span><span class="sxs-lookup"><span data-stu-id="dc55a-115">This command renames the `Srv01` computer to `Server001`.</span></span> <span data-ttu-id="dc55a-116">コンピューターは再起動されません。</span><span class="sxs-lookup"><span data-stu-id="dc55a-116">The computer is not restarted.</span></span>

<span data-ttu-id="dc55a-117">**DomainCredential** パラメーターは、ドメイン内のコンピューターの名前を変更するアクセス許可を持つユーザーの資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-117">The **DomainCredential** parameter specifies the credentials of a user who has permission to rename computers in the domain.</span></span>

<span data-ttu-id="dc55a-118">**Force** パラメーターを指定すると、確認プロンプトは表示されません。</span><span class="sxs-lookup"><span data-stu-id="dc55a-118">The **Force** parameter suppresses the confirmation prompt.</span></span>

```powershell
Rename-Computer -ComputerName "Srv01" -NewName "Server001" -DomainCredential Domain01\Admin01 -Force
```

## <span data-ttu-id="dc55a-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="dc55a-119">PARAMETERS</span></span>

### <span data-ttu-id="dc55a-120">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="dc55a-120">-ComputerName</span></span>

<span data-ttu-id="dc55a-121">指定したリモート コンピューターの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-121">Renames the specified remote computer.</span></span>
<span data-ttu-id="dc55a-122">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="dc55a-122">The default is the local computer.</span></span>

<span data-ttu-id="dc55a-123">リモート コンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-123">Type the NetBIOS name, an IP address, or a fully qualified domain name of a remote computer.</span></span>
<span data-ttu-id="dc55a-124">ローカルコンピューターを指定するには、コンピューター名、ドット ( `.` )、またはを入力し `localhost` ます。</span><span class="sxs-lookup"><span data-stu-id="dc55a-124">To specify the local computer, type the computer name, a dot (`.`), or `localhost`.</span></span>

<span data-ttu-id="dc55a-125">このパラメーターは、PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="dc55a-125">This parameter does not rely on PowerShell remoting.</span></span>
<span data-ttu-id="dc55a-126">**ComputerName** `Rename-Computer` コンピューターがリモートコマンドを実行するように構成されていない場合でも、の ComputerName パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc55a-126">You can use the **ComputerName** parameter of `Rename-Computer` even if your computer is not configured to run remote commands.</span></span>

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

### <span data-ttu-id="dc55a-127">-DomainCredential</span><span class="sxs-lookup"><span data-stu-id="dc55a-127">-DomainCredential</span></span>

<span data-ttu-id="dc55a-128">ドメインに接続するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-128">Specifies a user account that has permission to connect to the domain.</span></span>
<span data-ttu-id="dc55a-129">ドメインに参加しているコンピューターの名前を変更するには、明示的な資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="dc55a-129">Explicit credentials are required to rename a computer that is joined to a domain.</span></span>

<span data-ttu-id="dc55a-130">またはなどのユーザー名を入力する `User01` `Domain01\User01` か、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="dc55a-130">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="dc55a-131">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="dc55a-131">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="dc55a-132">**ComputerName** パラメーターで指定されたコンピューターに接続するアクセス許可を持つユーザー アカウントを指定するには、 **LocalCredential** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-132">To specify a user account that has permission to connect to the computer that is specified by the **ComputerName** parameter, use the **LocalCredential** parameter.</span></span>

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

### <span data-ttu-id="dc55a-133">-Force</span><span class="sxs-lookup"><span data-stu-id="dc55a-133">-Force</span></span>

<span data-ttu-id="dc55a-134">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-134">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="dc55a-135">-LocalCredential</span><span class="sxs-lookup"><span data-stu-id="dc55a-135">-LocalCredential</span></span>

<span data-ttu-id="dc55a-136">**ComputerName** パラメーターで指定されたコンピューターに接続するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-136">Specifies a user account that has permission to connect to the computer specified by the **ComputerName** parameter.</span></span> <span data-ttu-id="dc55a-137">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="dc55a-137">The default is the current user.</span></span>

<span data-ttu-id="dc55a-138">またはなどのユーザー名を入力する `User01` `Domain01\User01` か、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="dc55a-138">Type a user name, such as `User01` or `Domain01\User01`, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="dc55a-139">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="dc55a-139">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="dc55a-140">ドメインに接続するアクセス許可を持つユーザー アカウントを指定するには、 **DomainCredential** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-140">To specify a user account that has permission to connect to the domain, use the **DomainCredential** parameter.</span></span>

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

### <span data-ttu-id="dc55a-141">-NewName</span><span class="sxs-lookup"><span data-stu-id="dc55a-141">-NewName</span></span>

<span data-ttu-id="dc55a-142">コンピューターの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-142">Specifies a new name for the computer.</span></span>
<span data-ttu-id="dc55a-143">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="dc55a-143">This parameter is required.</span></span>

<span data-ttu-id="dc55a-144">標準名には、文字 ( `a-z` )、( `A-Z` )、数字 ( `0-9` )、ハイフン () を含めることができ `-` ますが、スペースやピリオド () は使用できません `.` 。</span><span class="sxs-lookup"><span data-stu-id="dc55a-144">Standard names may contain letters (`a-z`), (`A-Z`), numbers (`0-9`), and hyphens (`-`), but no spaces or periods (`.`).</span></span> <span data-ttu-id="dc55a-145">名前には数字だけを使用することはできません。また、63文字以内にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc55a-145">The name may not consist entirely of digits, and may not be longer than 63 characters</span></span>

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

### <span data-ttu-id="dc55a-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="dc55a-146">-PassThru</span></span>

<span data-ttu-id="dc55a-147">コマンドの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-147">Returns the results of the command.</span></span>
<span data-ttu-id="dc55a-148">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="dc55a-148">Otherwise, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="dc55a-149">-Restart</span><span class="sxs-lookup"><span data-stu-id="dc55a-149">-Restart</span></span>

<span data-ttu-id="dc55a-150">このコマンドレットは、名前が変更されたコンピューターを再起動することを示します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-150">Indicates that this cmdlet restarts the computer that was renamed.</span></span>
<span data-ttu-id="dc55a-151">多くの場合、変更を有効にするには再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="dc55a-151">A restart is often required to make the change effective.</span></span>

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

### <span data-ttu-id="dc55a-152">-WsmanAuthentication</span><span class="sxs-lookup"><span data-stu-id="dc55a-152">-WsmanAuthentication</span></span>

<span data-ttu-id="dc55a-153">このコマンドレットで WSMan プロトコルを使用するときに、ユーザー資格情報の認証に使用されるメカニズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-153">Specifies the mechanism that is used to authenticate the user credentials when this cmdlet uses the WSMan protocol.</span></span> <span data-ttu-id="dc55a-154">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="dc55a-154">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="dc55a-155">**Basic**</span><span class="sxs-lookup"><span data-stu-id="dc55a-155">**Basic**</span></span>
- <span data-ttu-id="dc55a-156">**CredSSP**</span><span class="sxs-lookup"><span data-stu-id="dc55a-156">**CredSSP**</span></span>
- <span data-ttu-id="dc55a-157">**[Default]**</span><span class="sxs-lookup"><span data-stu-id="dc55a-157">**Default**</span></span>
- <span data-ttu-id="dc55a-158">**ダイジェスト**</span><span class="sxs-lookup"><span data-stu-id="dc55a-158">**Digest**</span></span>
- <span data-ttu-id="dc55a-159">**Kerberos**</span><span class="sxs-lookup"><span data-stu-id="dc55a-159">**Kerberos**</span></span>
- <span data-ttu-id="dc55a-160">**ネゴシエーション**</span><span class="sxs-lookup"><span data-stu-id="dc55a-160">**Negotiate**</span></span>

<span data-ttu-id="dc55a-161">既定値は **Default** です。</span><span class="sxs-lookup"><span data-stu-id="dc55a-161">The default value is **Default** .</span></span>

<span data-ttu-id="dc55a-162">このパラメーターの値の詳細については、「 [Authenticationmechanism 列挙型](/dotnet/api/system.management.automation.runspaces.authenticationmechanism)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc55a-162">For more information about the values of this parameter, see [AuthenticationMechanism Enumeration](/dotnet/api/system.management.automation.runspaces.authenticationmechanism).</span></span>

> [!WARNING]
> <span data-ttu-id="dc55a-163">ユーザー資格情報が認証対象のリモートコンピューターに渡される Credential Security Service Provider (CredSSP) 認証は、リモートネットワーク共有へのアクセスなど、複数のリソースでの認証を必要とするコマンド向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="dc55a-163">Credential Security Service Provider (CredSSP) authentication, in which the user credentials are passed to a remote computer to be authenticated, is designed for commands that require authentication on more than one resource, such as accessing a remote network share.</span></span>
> <span data-ttu-id="dc55a-164">このメカニズムを使用すると、リモート操作のセキュリティ リスクが高まります。</span><span class="sxs-lookup"><span data-stu-id="dc55a-164">This mechanism increases the security risk of the remote operation.</span></span>
> <span data-ttu-id="dc55a-165">リモートコンピューターが侵害された場合、そのコンピューターに渡された資格情報を使用して、ネットワークセッション > 制御できます。</span><span class="sxs-lookup"><span data-stu-id="dc55a-165">If the remote computer is compromised, the credentials that are passed to it can be used to control > the network session.</span></span>

<span data-ttu-id="dc55a-166">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="dc55a-166">This parameter was introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="dc55a-167">-Confirm</span><span class="sxs-lookup"><span data-stu-id="dc55a-167">-Confirm</span></span>

<span data-ttu-id="dc55a-168">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc55a-168">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="dc55a-169">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="dc55a-169">-WhatIf</span></span>

<span data-ttu-id="dc55a-170">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-170">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="dc55a-171">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="dc55a-171">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="dc55a-172">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="dc55a-172">CommonParameters</span></span>

<span data-ttu-id="dc55a-173">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="dc55a-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="dc55a-174">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc55a-174">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="dc55a-175">入力</span><span class="sxs-lookup"><span data-stu-id="dc55a-175">INPUTS</span></span>

### <span data-ttu-id="dc55a-176">なし</span><span class="sxs-lookup"><span data-stu-id="dc55a-176">None</span></span>

<span data-ttu-id="dc55a-177">このコマンドレットには、値による入力を受け取るパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="dc55a-177">This cmdlet does not have parameters that take input by value.</span></span>
<span data-ttu-id="dc55a-178">ただし、パイプを使用してオブジェクトの **ComputerName** および **NewName** プロパティの値をこのコマンドレットに渡すことはできます。</span><span class="sxs-lookup"><span data-stu-id="dc55a-178">However, you can pipe the values of the **ComputerName** and **NewName** properties of objects to this cmdlet.</span></span>

## <span data-ttu-id="dc55a-179">出力</span><span class="sxs-lookup"><span data-stu-id="dc55a-179">OUTPUTS</span></span>

### <span data-ttu-id="dc55a-180">Microsoft. PowerShell. ComputerChangeInfo</span><span class="sxs-lookup"><span data-stu-id="dc55a-180">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="dc55a-181">**PassThru** パラメーターを指定した場合、このコマンドレットは **computerchangeinfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="dc55a-181">This cmdlet returns a **ComputerChangeInfo** object, if you specify the **PassThru** parameter.</span></span>
<span data-ttu-id="dc55a-182">それ以外の場合、出力は返しません。</span><span class="sxs-lookup"><span data-stu-id="dc55a-182">Otherwise, it does not return any output.</span></span>

## <span data-ttu-id="dc55a-183">注</span><span class="sxs-lookup"><span data-stu-id="dc55a-183">NOTES</span></span>

## <span data-ttu-id="dc55a-184">関連リンク</span><span class="sxs-lookup"><span data-stu-id="dc55a-184">RELATED LINKS</span></span>

[<span data-ttu-id="dc55a-185">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="dc55a-185">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="dc55a-186">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="dc55a-186">Stop-Computer</span></span>](Stop-Computer.md)
