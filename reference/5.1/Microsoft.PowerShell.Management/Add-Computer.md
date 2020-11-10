---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/add-computer?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Computer
ms.openlocfilehash: e3d1c5c071a334bddbfbc547ef2cc07e9e5c90aa
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388350"
---
# <span data-ttu-id="08b5b-103">Add-Computer</span><span class="sxs-lookup"><span data-stu-id="08b5b-103">Add-Computer</span></span>

## <span data-ttu-id="08b5b-104">概要</span><span class="sxs-lookup"><span data-stu-id="08b5b-104">SYNOPSIS</span></span>
<span data-ttu-id="08b5b-105">ローカル コンピューターをドメインまたはワークグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-105">Add the local computer to a domain or workgroup.</span></span>

## <span data-ttu-id="08b5b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="08b5b-106">SYNTAX</span></span>

### <span data-ttu-id="08b5b-107">ドメイン (既定値)</span><span class="sxs-lookup"><span data-stu-id="08b5b-107">Domain (Default)</span></span>

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>]
 [-UnjoinDomainCredential <PSCredential>] -Credential <PSCredential> [-DomainName] <String> [-OUPath <String>]
 [-Server <String>] [-Unsecure] [-Options <JoinOptions>] [-Restart] [-PassThru] [-NewName <String>] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="08b5b-108">ワークグループ</span><span class="sxs-lookup"><span data-stu-id="08b5b-108">Workgroup</span></span>

```
Add-Computer [-ComputerName <String[]>] [-LocalCredential <PSCredential>] [-Credential <PSCredential>]
 [-WorkgroupName] <String> [-Restart] [-PassThru] [-NewName <String>] [-Force] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="08b5b-109">Description</span><span class="sxs-lookup"><span data-stu-id="08b5b-109">DESCRIPTION</span></span>

<span data-ttu-id="08b5b-110">この `Add-Computer` コマンドレットは、ローカルコンピューターまたはリモートコンピューターをドメインまたはワークグループに追加するか、ドメイン間で移動します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-110">The `Add-Computer` cmdlet adds the local computer or remote computers to a domain or workgroup, or moves them from one domain to another.</span></span> <span data-ttu-id="08b5b-111">また、アカウントなしでドメインに追加されたコンピューターのドメイン アカウントも作成します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-111">It also creates a domain account if the computer is added to the domain without an account.</span></span>

<span data-ttu-id="08b5b-112">このコマンドレットのパラメーターを使用して、組織単位 (OU) およびドメイン コントローラーを指定したり、セキュリティで保護されていない参加を実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="08b5b-112">You can use the parameters of this cmdlet to specify an organizational unit (OU) and domain controller or to perform an unsecure join.</span></span>

<span data-ttu-id="08b5b-113">コマンドの結果を取得するには、 **Verbose** パラメーターと **PassThru** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-113">To get the results of the command, use the **Verbose** and **PassThru** parameters.</span></span>

## <span data-ttu-id="08b5b-114">例</span><span class="sxs-lookup"><span data-stu-id="08b5b-114">EXAMPLES</span></span>

### <span data-ttu-id="08b5b-115">例 1: ドメインにローカルコンピューターを追加し、コンピューターを再起動する</span><span class="sxs-lookup"><span data-stu-id="08b5b-115">Example 1: Add a local computer to a domain then restart the computer</span></span>

```powershell
Add-Computer -DomainName Domain01 -Restart
```

<span data-ttu-id="08b5b-116">このコマンドは、ローカル コンピューターを Domain01 ドメインに追加し、コンピューターを再起動して変更を有効にします。</span><span class="sxs-lookup"><span data-stu-id="08b5b-116">This command adds the local computer to the Domain01 domain and then restarts the computer to make the change effective.</span></span>

### <span data-ttu-id="08b5b-117">例 2: ワークグループにローカルコンピューターを追加する</span><span class="sxs-lookup"><span data-stu-id="08b5b-117">Example 2: Add a local computer to a workgroup</span></span>

```powershell
Add-Computer -WorkgroupName WORKGROUP-A
```

<span data-ttu-id="08b5b-118">このコマンドは、ローカル コンピューターを Workgroup-A ワークグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-118">This command adds the local computer to the Workgroup-A workgroup.</span></span>

### <span data-ttu-id="08b5b-119">例 3: ローカルコンピューターをドメインに追加する</span><span class="sxs-lookup"><span data-stu-id="08b5b-119">Example 3: Add a local computer to a domain</span></span>

```powershell
Add-Computer -DomainName Domain01 -Server Domain01\DC01 -PassThru -Verbose
```

<span data-ttu-id="08b5b-120">このコマンドは、Domain01\DC01 ドメイン コントローラーを使用して、ローカル コンピューターを Domain01 ドメインに追加します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-120">This command adds the local computer to the Domain01 domain by using the Domain01\DC01 domain controller.</span></span>

<span data-ttu-id="08b5b-121">コマンドで **PassThru** パラメーターおよび **Verbose** パラメーターを使用して、コマンドの結果に関する詳細な情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-121">The command uses the **PassThru** and **Verbose** parameters to get detailed information about the results of the command.</span></span>

### <span data-ttu-id="08b5b-122">例 4: OUPath パラメーターを使用してドメインにローカルコンピューターを追加する</span><span class="sxs-lookup"><span data-stu-id="08b5b-122">Example 4: Add a local computer to a domain using the OUPath parameter</span></span>

```powershell
Add-Computer -DomainName Domain02 -OUPath "OU=testOU,DC=domain,DC=Domain,DC=com"
```

<span data-ttu-id="08b5b-123">このコマンドは、ローカル コンピューターを Domain02 ドメインに追加します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-123">This command adds the local computer to the Domain02 domain.</span></span>
<span data-ttu-id="08b5b-124">OUPath パラメーターを使用して、新しいアカウントの組織単位を指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-124">It uses the OUPath parameter to specify the organizational unit for the new accounts.</span></span>

### <span data-ttu-id="08b5b-125">例 5: 資格情報を使用してドメインにローカルコンピューターを追加する</span><span class="sxs-lookup"><span data-stu-id="08b5b-125">Example 5: Add a local computer to a domain using credentials</span></span>

```powershell
Add-Computer -ComputerName Server01 -LocalCredential Server01\Admin01 -DomainName Domain02 -Credential Domain02\Admin02 -Restart -Force
```

<span data-ttu-id="08b5b-126">このコマンドは、Server01 コンピューターを Domain02 ドメインに追加します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-126">This command adds the Server01 computer to the Domain02 domain.</span></span> <span data-ttu-id="08b5b-127">**LocalCredential** パラメーターを使用して、Server01 コンピューターに接続するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-127">It uses the **LocalCredential** parameter to specify a user account that has permission to connect to the Server01 computer.</span></span> <span data-ttu-id="08b5b-128">**Credential** パラメーターを使用して、コンピューターをドメインに追加するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-128">It uses the **Credential** parameter to specify a user account that has permission to join computers to the domain.</span></span> <span data-ttu-id="08b5b-129">**Restart** パラメーターを使用して、参加操作の完了後にコンピューターを再起動し、 **Force** パラメーターを使用して、ユーザーへの確認メッセージが表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="08b5b-129">It uses the **Restart** parameter to restart the computer after the join operation completes and the **Force** parameter to suppress user confirmation messages.</span></span>

### <span data-ttu-id="08b5b-130">例 6: コンピューターのグループを新しいドメインに移動する</span><span class="sxs-lookup"><span data-stu-id="08b5b-130">Example 6: Move a group of computers to a new domain</span></span>

```powershell
Add-Computer -ComputerName Server01, Server02, localhost -DomainName Domain02 -LocalCredential Domain01\User01 -UnjoinDomainCredential Domain01\Admin01 -Credential Domain02\Admin01 -Restart
```

<span data-ttu-id="08b5b-131">このコマンドは、Server01、Server02、およびローカル コンピューターを Domain01 から Domain02 に移動します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-131">This command moves the Server01 and Server02 computers, and the local computer, from Domain01 to Domain02.</span></span>

<span data-ttu-id="08b5b-132">**LocalCredential** パラメーターを使用して、関連する 3 つのコンピューターに接続するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-132">It uses the **LocalCredential** parameter to specify a user account that has permission to connect to the three affected computers.</span></span> <span data-ttu-id="08b5b-133">**UnjoinDomainCredential** パラメーターを使用して、Domain01 ドメインからコンピューターを削除するアクセス許可を持つユーザー アカウントを指定し、 **Credential** パラメーターを使用して、Domain02 ドメインにコンピューターを追加するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-133">It uses the **UnjoinDomainCredential** parameter to specify a user account that has permission to unjoin the computers from the Domain01 domain and the **Credential** parameter to specify a user account that has permission to join the computers to the Domain02 domain.</span></span> <span data-ttu-id="08b5b-134">**Restart** パラメーターを使用して、移動の完了後、3 つのすべてのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-134">It uses the **Restart** parameter to restart all three computers after the move is complete.</span></span>

### <span data-ttu-id="08b5b-135">例 7: コンピューターを新しいドメインに移動し、コンピューターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="08b5b-135">Example 7: Move a computer to a new domain and change the name of the computer</span></span>

```powershell
Add-Computer -ComputerName Server01 -DomainName Domain02 -NewName Server044 -Credential Domain02\Admin01 -Restart
```

<span data-ttu-id="08b5b-136">このコマンドは、Server01 コンピューターを Domain02 に移動し、コンピューター名を Server044 に変更します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-136">This command moves the Server01 computer to the Domain02 and changes the machine name to Server044.</span></span>

<span data-ttu-id="08b5b-137">Server01 コンピューターへの接続には現在のユーザーの資格情報を使用し、このコンピューターを現在のドメインから削除します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-137">The command uses the credential of the current user to connect to the Server01 computer and unjoin it from its current domain.</span></span> <span data-ttu-id="08b5b-138">**Credential** パラメーターを使用して、コンピューターを Domain02 ドメインに参加させるアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-138">It uses the **Credential** parameter to specify a user account that has permission to join the computer to the Domain02 domain.</span></span>

### <span data-ttu-id="08b5b-139">例 8: ファイルに一覧表示されているコンピューターを新しいドメインに追加する</span><span class="sxs-lookup"><span data-stu-id="08b5b-139">Example 8: Add computers listed in a file to a new domain</span></span>

```powershell
Add-Computer -ComputerName (Get-Content Servers.txt) -DomainName Domain02 -Credential Domain02\Admin02 -Options Win9xUpgrade  -Restart
```

<span data-ttu-id="08b5b-140">このコマンドは、Servers.txt ファイルに記載されているコンピューターを Domain02 ドメインに追加します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-140">This command adds the computers that are listed in the Servers.txt file to the Domain02 domain.</span></span> <span data-ttu-id="08b5b-141">**Options** パラメーターを使用して、 **Win9xUpgrade** オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-141">It uses the **Options** parameter to specify the **Win9xUpgrade** option.</span></span> <span data-ttu-id="08b5b-142">**Restart** パラメーターは、参加操作の完了後に、新たに追加されたすべてのコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-142">The **Restart** parameter restarts all of the newly added computers after the join operation completes.</span></span>

### <span data-ttu-id="08b5b-143">例 9: 定義済みのコンピューター資格情報を使用してコンピューターをドメインに追加する</span><span class="sxs-lookup"><span data-stu-id="08b5b-143">Example 9: Add a computer to a domain using predefined computer credentials</span></span>

<span data-ttu-id="08b5b-144">この最初のコマンドは、既にドメインに参加しているコンピューターから管理者が実行する必要があり `Domain03` ます。</span><span class="sxs-lookup"><span data-stu-id="08b5b-144">This first command should be run by an administrator from a computer that is already joined to domain `Domain03`:</span></span>

```powershell
New-ADComputer -Name "Server02" -AccountPassword (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)

# Then this command is run from `Server02` which is not yet domain-joined:

$joinCred = New-Object pscredential -ArgumentList ([pscustomobject]@{
    UserName = $null
    Password = (ConvertTo-SecureString -String 'TempJoinPA$$' -AsPlainText -Force)[0]
})
Add-Computer -Domain "Domain03" -Options UnsecuredJoin,PasswordPass -Credential $joinCred
```

<span data-ttu-id="08b5b-145">このコマンドの組み合わせにより、ドメインに参加している既存のコンピューターを使用して、ドメイン内に事前定義された名前と一時的な参加パスワードを持つ新しいコンピューターアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-145">This combination of commands creates a new computer account with a predefined name and temporary join password in a domain using an existing domain-joined computer.</span></span> <span data-ttu-id="08b5b-146">次に、定義済みの名前を持つコンピューターは、コンピューター名と一時的な参加パスワードのみを使用してドメインに参加します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-146">Then separately, a computer with the predefined name joins the domain using only the computer name and the temporary join password.</span></span>
<span data-ttu-id="08b5b-147">定義済みのパスワードは、結合操作をサポートするためにのみ使用され、コンピューターが結合を完了した後で、通常のコンピューターアカウントの手順の一部として置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="08b5b-147">The predefined password is only used to support the join operation and is replaced as part of normal computer account procedures after the computer completes the join.</span></span>

## <span data-ttu-id="08b5b-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="08b5b-148">PARAMETERS</span></span>

### <span data-ttu-id="08b5b-149">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="08b5b-149">-ComputerName</span></span>

<span data-ttu-id="08b5b-150">ドメインまたはワークグループに追加するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-150">Specifies the computers to add to a domain or workgroup.</span></span>
<span data-ttu-id="08b5b-151">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="08b5b-151">The default is the local computer.</span></span>

<span data-ttu-id="08b5b-152">各リモートコンピューターの NetBIOS 名、インターネットプロトコル (IP) アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-152">Type the NetBIOS name, an Internet Protocol (IP) address, or a fully qualified domain name of each of the remote computers.</span></span> <span data-ttu-id="08b5b-153">ローカルコンピューターを指定するには、コンピューター名、ドット ( `.` )、または "localhost" を入力します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-153">To specify the local computer, type the computer name, a dot (`.`), or "localhost".</span></span>

<span data-ttu-id="08b5b-154">このパラメーターは、Windows PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="08b5b-154">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="08b5b-155">**ComputerName** `Add-Computer` コンピューターがリモートコマンドを実行するように構成されていない場合でも、の ComputerName パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="08b5b-155">You can use the **ComputerName** parameter of `Add-Computer` even if your computer is not configured to run remote commands.</span></span>

<span data-ttu-id="08b5b-156">このパラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="08b5b-156">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="08b5b-157">-Credential</span><span class="sxs-lookup"><span data-stu-id="08b5b-157">-Credential</span></span>

<span data-ttu-id="08b5b-158">新しいドメインにコンピューターを追加するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-158">Specifies a user account that has permission to join the computers to a new domain.</span></span>
<span data-ttu-id="08b5b-159">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="08b5b-159">The default is the current user.</span></span>

<span data-ttu-id="08b5b-160">「User01」や「Domain01\User01」のようなユーザー名を入力するか、 コマンドレットで生成されるような `Get-Credential` オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-160">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="08b5b-161">ユーザー名を入力すると、パスワードの入力を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08b5b-161">If you type a user name, you will be prompted for a password.</span></span>

<span data-ttu-id="08b5b-162">コンピューターを現在のドメインから削除するアクセス許可を持つユーザー アカウントを指定するには、 **UnjoinDomainCredential** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-162">To specify a user account that has permission to remove the computer from its current domain, use the **UnjoinDomainCredential** parameter.</span></span> <span data-ttu-id="08b5b-163">リモート コンピューターに接続するアクセス許可を持つユーザー アカウントを指定するには、 **LocalCredential** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-163">To specify a user account that has permission to connect to a remote computer, use the **LocalCredential** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain, Workgroup
Aliases: DomainCredential

Required: True (Domain), False (Workgroup)
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08b5b-164">-DomainName</span><span class="sxs-lookup"><span data-stu-id="08b5b-164">-DomainName</span></span>

<span data-ttu-id="08b5b-165">コンピューターが追加されるドメインを指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-165">Specifies the domain to which the computers are added.</span></span> <span data-ttu-id="08b5b-166">このパラメーターは、コンピューターをドメインに追加する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="08b5b-166">This parameter is required when adding the computers to a domain.</span></span>

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DN, Domain

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08b5b-167">-Force</span><span class="sxs-lookup"><span data-stu-id="08b5b-167">-Force</span></span>

<span data-ttu-id="08b5b-168">ユーザーへの確認メッセージを表示しないようにします。</span><span class="sxs-lookup"><span data-stu-id="08b5b-168">Suppresses the user confirmation prompt.</span></span> <span data-ttu-id="08b5b-169">このパラメーターを指定しない場合、では、 `Add-Computer` 各コンピューターの追加を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08b5b-169">Without this parameter, `Add-Computer` requires you to confirm the addition of each computer.</span></span>

<span data-ttu-id="08b5b-170">このパラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="08b5b-170">This parameter is introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="08b5b-171">-LocalCredential</span><span class="sxs-lookup"><span data-stu-id="08b5b-171">-LocalCredential</span></span>

<span data-ttu-id="08b5b-172">**ComputerName** パラメーターで指定されたコンピューターに接続するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-172">Specifies a user account that has permission to connect to the computers that are specified by the **ComputerName** parameter.</span></span> <span data-ttu-id="08b5b-173">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="08b5b-173">The default is the current user.</span></span>

<span data-ttu-id="08b5b-174">「User01」や「Domain01\User01」のようなユーザー名を入力するか、 コマンドレットで生成されるような `Get-Credential` オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-174">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="08b5b-175">ユーザー名を入力すると、パスワードの入力を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08b5b-175">If you type a user name, you will be prompted for a password.</span></span>

<span data-ttu-id="08b5b-176">新しいドメインにコンピューターを追加するアクセス許可を持つユーザー アカウントを指定するには、 **Credential** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-176">To specify a user account that has permission to add the computers to a new domain, use the **Credential** parameter.</span></span> <span data-ttu-id="08b5b-177">コンピューターを現在のドメインから削除するアクセス許可を持つユーザー アカウントを指定するには、 **UnjoinDomainCredential** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-177">To specify a user account that has permission to remove the computers from their current domain, use the **UnjoinDomainCredential** parameter.</span></span>

<span data-ttu-id="08b5b-178">このパラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="08b5b-178">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08b5b-179">-NewName</span><span class="sxs-lookup"><span data-stu-id="08b5b-179">-NewName</span></span>

<span data-ttu-id="08b5b-180">新しいドメインでのコンピューターの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-180">Specifies a new name for the computer in the new domain.</span></span> <span data-ttu-id="08b5b-181">このパラメーターは、1 つのコンピューターが追加または移動されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="08b5b-181">This parameter is valid only when one computer is being added or moved.</span></span>

<span data-ttu-id="08b5b-182">このパラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="08b5b-182">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="08b5b-183">-オプション</span><span class="sxs-lookup"><span data-stu-id="08b5b-183">-Options</span></span>

<span data-ttu-id="08b5b-184">**コンピューターの追加** 参加操作の詳細オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-184">Specifies advanced options for the **Add-Computer** join operation.</span></span> <span data-ttu-id="08b5b-185">1 つ以上の値をコンマ区切りの文字列として入力します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-185">Enter one or more values in a comma-separated string.</span></span>

<span data-ttu-id="08b5b-186">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="08b5b-186">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="08b5b-187">**Accountcreate** : ドメインアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-187">**AccountCreate** : Creates a domain account.</span></span> <span data-ttu-id="08b5b-188">コンピューターの **追加** コマンドレットは、ドメインにコンピューターを追加するときに、ドメインアカウントを自動的に作成します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-188">The **Add-Computer** cmdlet automatically creates a domain account when it adds a computer to a domain.</span></span> <span data-ttu-id="08b5b-189">このオプションは、完全を期すために用意されています。</span><span class="sxs-lookup"><span data-stu-id="08b5b-189">This option is included for completeness.</span></span>

- <span data-ttu-id="08b5b-190">**Win9XUpgrade** : 結合操作が Windows オペレーティングシステムのアップグレードの一部であることを示します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-190">**Win9XUpgrade** : Indicates that the join operation is part of a Windows operating system upgrade.</span></span>

- <span data-ttu-id="08b5b-191">**UnsecuredJoin** : セキュリティで保護されていない参加を実行します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-191">**UnsecuredJoin** : Performs an unsecured join.</span></span> <span data-ttu-id="08b5b-192">セキュリティで保護されていない参加を要求するには、 *安全* でないパラメーターまたはこのオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-192">To request an unsecured join, use the *Unsecure* parameter or this option.</span></span> <span data-ttu-id="08b5b-193">コンピューターのパスワードを渡す場合は、このオプションをオプションと組み合わせて使用する必要があり `PasswordPass` ます。</span><span class="sxs-lookup"><span data-stu-id="08b5b-193">If you want to pass a machine password, then you must use this option in combination with `PasswordPass` option.</span></span>

- <span data-ttu-id="08b5b-194">**Passwordpass** : セキュリティで保護されていない参加を実行した後、コンピューターのパスワードを *Credential* (DomainCredential) パラメーターの値に設定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-194">**PasswordPass** : Sets the machine password to the value of the *Credential* (DomainCredential) parameter after performing an unsecured join.</span></span> <span data-ttu-id="08b5b-195">このオプションは、 *Credential* (DomainCredential) パラメーターの値がコンピューターのパスワードであってユーザーのパスワードではないことも示します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-195">This option also indicates that the value of the *Credential* (DomainCredential) parameter is a machine password, not a user password.</span></span> <span data-ttu-id="08b5b-196">このオプションは、 `UnsecuredJoin` オプションが指定されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="08b5b-196">This option is valid only when the `UnsecuredJoin` option is specified.</span></span> <span data-ttu-id="08b5b-197">このオプションを使用する場合、パラメーターに指定する資格情報には `-Credential` null ユーザー名を指定する *必要があり* ます。</span><span class="sxs-lookup"><span data-stu-id="08b5b-197">When using this option, the credential provided to the `-Credential` parameter *must* have a null username.</span></span>

- <span data-ttu-id="08b5b-198">**Joinwithnewname** : 新しいドメイン内のコンピューター名を、 *NewName* パラメーターで指定した名前に変更します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-198">**JoinWithNewName** : Renames the computer name in the new domain to the name specified by the *NewName* parameter.</span></span> <span data-ttu-id="08b5b-199">*NewName* パラメーターを使用すると、このオプションは自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="08b5b-199">When you use the *NewName* parameter, this option is set automatically.</span></span> <span data-ttu-id="08b5b-200">このオプションは、Rename-Computer コマンドレットと共に使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="08b5b-200">This option is designed to be used with the Rename-Computer cmdlet.</span></span> <span data-ttu-id="08b5b-201">コンピューター名の変更 **コマンドレット** を使用してコンピューターの名前を変更しても、コンピューターを再起動せずに変更を有効にした場合は、このパラメーターを使用して、コンピューターを新しい名前でドメインに参加させることができます。</span><span class="sxs-lookup"><span data-stu-id="08b5b-201">If you use the **Rename-Computer** cmdlet to rename the computer, but do not restart the computer to make the change effective, you can use this parameter to join the computer to a domain with its new name.</span></span>

- <span data-ttu-id="08b5b-202">**Joinreadonly** : 既存のコンピューターアカウントを使用して、コンピューターを読み取り専用ドメインコントローラーに参加させます。</span><span class="sxs-lookup"><span data-stu-id="08b5b-202">**JoinReadOnly** : Uses an existing machine account to join the computer to a read-only domain controller.</span></span> <span data-ttu-id="08b5b-203">コンピューターアカウントは、パスワードレプリケーションポリシーの許可リストに追加する必要があります。また、アカウントのパスワードは、参加操作の前に読み取り専用ドメインコントローラーにレプリケートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="08b5b-203">The machine account must be added to the allowed list for password replication policy and the account password must be replicated to the read-only domain controller prior to the join operation.</span></span>

- <span data-ttu-id="08b5b-204">**InstallInvoke** : **Joindomainorworkgroup** メソッドの **fjoinoptions** パラメーターの作成 (0x2) フラグと削除 (0x4) フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-204">**InstallInvoke** : Sets the create (0x2) and delete (0x4) flags of the **FJoinOptions** parameter of the **JoinDomainOrWorkgroup** method.</span></span> <span data-ttu-id="08b5b-205">**Joindomainorworkgroup** メソッドの詳細については、 [Win32_ComputerSystem クラスの Joindomainorworkgroup メソッド](/windows/win32/cimwin32prov/joindomainorworkgroup-method-in-class-win32-computersystem)に関する説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08b5b-205">For more information about the **JoinDomainOrWorkgroup** method, see [JoinDomainOrWorkgroup method of the Win32_ComputerSystem class](/windows/win32/cimwin32prov/joindomainorworkgroup-method-in-class-win32-computersystem).</span></span>
  <span data-ttu-id="08b5b-206">これらのオプションの詳細については、「 [Netjoindomain 関数](/windows/win32/api/lmjoin/nf-lmjoin-netjoindomain)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08b5b-206">For more information about these options, see [NetJoinDomain function](/windows/win32/api/lmjoin/nf-lmjoin-netjoindomain).</span></span>

<span data-ttu-id="08b5b-207">このパラメーターは Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="08b5b-207">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.JoinOptions
Parameter Sets: Domain
Aliases:
Accepted values: AccountCreate, Win9XUpgrade, UnsecuredJoin, PasswordPass, DeferSPNSet, JoinWithNewName, JoinReadOnly, InstallInvoke

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08b5b-208">-OUPath</span><span class="sxs-lookup"><span data-stu-id="08b5b-208">-OUPath</span></span>

<span data-ttu-id="08b5b-209">ドメイン アカウントの組織単位 (OU) を指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-209">Specifies an organizational unit (OU) for the domain account.</span></span> <span data-ttu-id="08b5b-210">OU の完全識別名を引用符で囲んで入力します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-210">Enter the full distinguished name of the OU in quotation marks.</span></span> <span data-ttu-id="08b5b-211">既定値は、ドメイン内で使用されるコンピューター オブジェクトの既定の OU です。</span><span class="sxs-lookup"><span data-stu-id="08b5b-211">The default value is the default OU for machine objects in the domain.</span></span>

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: OU

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08b5b-212">-PassThru</span><span class="sxs-lookup"><span data-stu-id="08b5b-212">-PassThru</span></span>

<span data-ttu-id="08b5b-213">作業中の項目を表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-213">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="08b5b-214">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="08b5b-214">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="08b5b-215">-Restart</span><span class="sxs-lookup"><span data-stu-id="08b5b-215">-Restart</span></span>

<span data-ttu-id="08b5b-216">ドメインまたはワークグループに追加されたコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-216">Restarts the computers that were added to the domain or workgroup.</span></span> <span data-ttu-id="08b5b-217">多くの場合、変更を有効にするには再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="08b5b-217">A restart is often required to make the change effective.</span></span>

<span data-ttu-id="08b5b-218">このパラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="08b5b-218">This parameter is introduced in Windows PowerShell 3.0.</span></span>

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

### <span data-ttu-id="08b5b-219">-Server</span><span class="sxs-lookup"><span data-stu-id="08b5b-219">-Server</span></span>

<span data-ttu-id="08b5b-220">ドメインにコンピューターを追加するドメイン コントローラーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-220">Specifies the name of a domain controller that adds the computer to the domain.</span></span> <span data-ttu-id="08b5b-221">ドメイン名\コンピューター名の形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-221">Enter the name in DomainName\ComputerName format.</span></span> <span data-ttu-id="08b5b-222">既定では、ドメイン コントローラーは指定されません。</span><span class="sxs-lookup"><span data-stu-id="08b5b-222">By default, no domain controller is specified.</span></span>

```yaml
Type: System.String
Parameter Sets: Domain
Aliases: DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08b5b-223">-UnjoinDomainCredential</span><span class="sxs-lookup"><span data-stu-id="08b5b-223">-UnjoinDomainCredential</span></span>

<span data-ttu-id="08b5b-224">コンピューターを現在のドメインから削除するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-224">Specifies a user account that has permission to remove the computers from their current domains.</span></span> <span data-ttu-id="08b5b-225">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="08b5b-225">The default is the current user.</span></span>

<span data-ttu-id="08b5b-226">「User01」や「Domain01\User01」のようなユーザー名を入力するか、 コマンドレットで生成されるような `Get-Credential` オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-226">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="08b5b-227">ユーザー名を入力すると、パスワードの入力を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08b5b-227">If you type a user name, you will be prompted for a password.</span></span>

<span data-ttu-id="08b5b-228">このパラメーターは、コンピューターを別のドメインに移動するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-228">Use this parameter when you are moving computers to a different domain.</span></span> <span data-ttu-id="08b5b-229">新しいドメインに参加するアクセス許可を持つユーザー アカウントを指定するには、 **Credential** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-229">To specify a user account that has permission to join the new domain, use the **Credential** parameter.</span></span> <span data-ttu-id="08b5b-230">リモート コンピューターに接続するアクセス許可を持つユーザー アカウントを指定するには、 **LocalCredential** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-230">To specify a user account that has permission to connect to a remote computer, use the **LocalCredential** parameter.</span></span>

<span data-ttu-id="08b5b-231">このパラメーターは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="08b5b-231">This parameter is introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08b5b-232">-セキュリティ保護なし</span><span class="sxs-lookup"><span data-stu-id="08b5b-232">-Unsecure</span></span>

<span data-ttu-id="08b5b-233">指定されたドメインへのセキュリティで保護されていない参加を行います。</span><span class="sxs-lookup"><span data-stu-id="08b5b-233">Performs an unsecure join to the specified domain.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Domain
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08b5b-234">-ワークスペース</span><span class="sxs-lookup"><span data-stu-id="08b5b-234">-WorkgroupName</span></span>

<span data-ttu-id="08b5b-235">コンピューターを追加するワークグループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-235">Specifies the name of a workgroup to which the computers are added.</span></span> <span data-ttu-id="08b5b-236">既定値は "WORKGROUP" です。</span><span class="sxs-lookup"><span data-stu-id="08b5b-236">The default value is "WORKGROUP".</span></span>

```yaml
Type: System.String
Parameter Sets: Workgroup
Aliases: WGN

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="08b5b-237">-Confirm</span><span class="sxs-lookup"><span data-stu-id="08b5b-237">-Confirm</span></span>

<span data-ttu-id="08b5b-238">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="08b5b-238">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="08b5b-239">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="08b5b-239">-WhatIf</span></span>

<span data-ttu-id="08b5b-240">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-240">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="08b5b-241">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="08b5b-241">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="08b5b-242">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="08b5b-242">CommonParameters</span></span>

<span data-ttu-id="08b5b-243">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="08b5b-243">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="08b5b-244">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="08b5b-244">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="08b5b-245">入力</span><span class="sxs-lookup"><span data-stu-id="08b5b-245">INPUTS</span></span>

### <span data-ttu-id="08b5b-246">System.String</span><span class="sxs-lookup"><span data-stu-id="08b5b-246">System.String</span></span>

<span data-ttu-id="08b5b-247">パイプを使用して、コンピューター名と新しい名前を `Add-Computer` コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-247">You can pipe computer names and new names to the `Add-Computer` Cmdlet.</span></span>

## <span data-ttu-id="08b5b-248">出力</span><span class="sxs-lookup"><span data-stu-id="08b5b-248">OUTPUTS</span></span>

### <span data-ttu-id="08b5b-249">Microsoft. PowerShell. ComputerChangeInfo</span><span class="sxs-lookup"><span data-stu-id="08b5b-249">Microsoft.PowerShell.Commands.ComputerChangeInfo</span></span>

<span data-ttu-id="08b5b-250">**PassThru** パラメーターを使用すると、は `Add-Computer` **computerchangeinfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-250">When you use the **PassThru** parameter, `Add-Computer` returns a **ComputerChangeInfo** object.</span></span>
<span data-ttu-id="08b5b-251">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="08b5b-251">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="08b5b-252">注</span><span class="sxs-lookup"><span data-stu-id="08b5b-252">NOTES</span></span>

- <span data-ttu-id="08b5b-253">Windows PowerShell 2.0 では、 **Server** `Add-Computer` サーバーが存在する場合でも、の server パラメーターは失敗します。</span><span class="sxs-lookup"><span data-stu-id="08b5b-253">In Windows PowerShell 2.0, the **Server** parameter of `Add-Computer` fails even when the server is present.</span></span> <span data-ttu-id="08b5b-254">Windows PowerShell 3.0 では、 **Server** パラメーターが確実に動作するように実装が変更されました。</span><span class="sxs-lookup"><span data-stu-id="08b5b-254">In Windows PowerShell 3.0, the implementation of the **Server** parameter is changed so that it works reliably.</span></span>

## <span data-ttu-id="08b5b-255">関連リンク</span><span class="sxs-lookup"><span data-stu-id="08b5b-255">RELATED LINKS</span></span>

[<span data-ttu-id="08b5b-256">Checkpoint-Computer</span><span class="sxs-lookup"><span data-stu-id="08b5b-256">Checkpoint-Computer</span></span>](Checkpoint-Computer.md)

[<span data-ttu-id="08b5b-257">Remove-Computer</span><span class="sxs-lookup"><span data-stu-id="08b5b-257">Remove-Computer</span></span>](Remove-Computer.md)

[<span data-ttu-id="08b5b-258">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="08b5b-258">Restart-Computer</span></span>](Restart-Computer.md)

[<span data-ttu-id="08b5b-259">Rename-Computer</span><span class="sxs-lookup"><span data-stu-id="08b5b-259">Rename-Computer</span></span>](Rename-Computer.md)

[<span data-ttu-id="08b5b-260">Restore-Computer</span><span class="sxs-lookup"><span data-stu-id="08b5b-260">Restore-Computer</span></span>](Restore-Computer.md)

[<span data-ttu-id="08b5b-261">Stop-Computer</span><span class="sxs-lookup"><span data-stu-id="08b5b-261">Stop-Computer</span></span>](Stop-Computer.md)

[<span data-ttu-id="08b5b-262">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="08b5b-262">Test-Connection</span></span>](Test-Connection.md)
