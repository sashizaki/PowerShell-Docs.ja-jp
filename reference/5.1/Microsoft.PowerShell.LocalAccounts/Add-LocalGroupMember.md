---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 04/09/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/add-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-LocalGroupMember
ms.openlocfilehash: 06993c8f6618472f4809e37fbf83d298d13ae515
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211928"
---
# <span data-ttu-id="2e605-103">Add-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="2e605-103">Add-LocalGroupMember</span></span>

## <span data-ttu-id="2e605-104">概要</span><span class="sxs-lookup"><span data-stu-id="2e605-104">SYNOPSIS</span></span>
<span data-ttu-id="2e605-105">ローカルグループにメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2e605-105">Adds members to a local group.</span></span>

## <span data-ttu-id="2e605-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2e605-106">SYNTAX</span></span>

### <span data-ttu-id="2e605-107">グループ</span><span class="sxs-lookup"><span data-stu-id="2e605-107">Group</span></span>

```
Add-LocalGroupMember [-Group] <LocalGroup> [-Member] <LocalPrincipal[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="2e605-108">Default</span><span class="sxs-lookup"><span data-stu-id="2e605-108">Default</span></span>

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2e605-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="2e605-109">SecurityIdentifier</span></span>

```
Add-LocalGroupMember [-Member] <LocalPrincipal[]> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="2e605-110">Description</span><span class="sxs-lookup"><span data-stu-id="2e605-110">DESCRIPTION</span></span>

<span data-ttu-id="2e605-111">`Add-LocalGroupMember`コマンドレットでは、ユーザーまたはグループをローカルセキュリティグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="2e605-111">The `Add-LocalGroupMember` cmdlet adds users or groups to a local security group.</span></span> <span data-ttu-id="2e605-112">グループに割り当てられているすべての権利とアクセス許可が、そのグループのすべてのメンバーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="2e605-112">All the rights and permissions that are assigned to a group are assigned to all members of that group.</span></span>

<span data-ttu-id="2e605-113">ローカル コンピューター上の Administrators グループのメンバーはそのコンピューター上でフル コントロールのアクセス許可を持ちます。</span><span class="sxs-lookup"><span data-stu-id="2e605-113">Members of the Administrators group on a local computer have Full Control permissions on that computer.</span></span> <span data-ttu-id="2e605-114">Administrators グループのユーザー数を制限します。</span><span class="sxs-lookup"><span data-stu-id="2e605-114">Limit the number of users in the Administrators group.</span></span>

<span data-ttu-id="2e605-115">コンピューターがドメインに参加している場合、そのドメインと信頼される側のドメインから、ユーザー アカウント、コンピューター アカウント、およびグループ アカウントをローカル グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="2e605-115">If the computer is joined to a domain, you can add user accounts, computer accounts, and group accounts from that domain and from trusted domains to a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="2e605-116">コンピューターがドメインに参加していて、ドメインのメンバーと同じ名前を持つローカルユーザーを追加しようとすると、ドメインメンバーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="2e605-116">If the computer is joined to a domain and you try to add a local user that has the same name as a member of the domain it adds the domain member.</span></span>

## <span data-ttu-id="2e605-117">例</span><span class="sxs-lookup"><span data-stu-id="2e605-117">EXAMPLES</span></span>

### <span data-ttu-id="2e605-118">例 1: Administrators グループにメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="2e605-118">Example 1: Add members to the Administrators group</span></span>

<span data-ttu-id="2e605-119">このコマンドは、ローカルの Administrators グループに複数のメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2e605-119">This command adds several members to the local Administrators group.</span></span> <span data-ttu-id="2e605-120">新しいメンバーには、ローカルユーザーアカウント、Microsoft アカウント、Azure Active Directory アカウント、ドメイングループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2e605-120">The new members include a local user account, a Microsoft account, an Azure Active Directory account, and a domain group.</span></span> <span data-ttu-id="2e605-121">この例では、Outlook.com のアカウントのユーザー名にプレースホルダー値を使用します。</span><span class="sxs-lookup"><span data-stu-id="2e605-121">This example uses a placeholder value for the user name of an account at Outlook.com.</span></span>

```powershell
Add-LocalGroupMember -Group "Administrators" -Member "Admin02", "MicrosoftAccount\username@Outlook.com", "AzureAD\DavidChew@contoso.com", "CONTOSO\Domain Admins"
```

## <span data-ttu-id="2e605-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2e605-122">PARAMETERS</span></span>

### <span data-ttu-id="2e605-123">-Group</span><span class="sxs-lookup"><span data-stu-id="2e605-123">-Group</span></span>

<span data-ttu-id="2e605-124">このコマンドレットがメンバーを追加するセキュリティグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="2e605-124">Specifies the security group to which this cmdlet adds members.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e605-125">-メンバー</span><span class="sxs-lookup"><span data-stu-id="2e605-125">-Member</span></span>

<span data-ttu-id="2e605-126">このコマンドレットによってセキュリティグループに追加されるユーザーまたはグループの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e605-126">Specifies an array of users or groups that this cmdlet adds to a security group.</span></span> <span data-ttu-id="2e605-127">名前、セキュリティ ID (SID)、または **Localprincipal** オブジェクトを使用して、ユーザーまたはグループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2e605-127">You can specify users or groups by name, security ID (SID), or **LocalPrincipal** objects.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalPrincipal[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2e605-128">-Name</span><span class="sxs-lookup"><span data-stu-id="2e605-128">-Name</span></span>

<span data-ttu-id="2e605-129">このコマンドレットがメンバーを追加するセキュリティグループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e605-129">Specifies the name of the security group to which this cmdlet adds members.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e605-130">-SID</span><span class="sxs-lookup"><span data-stu-id="2e605-130">-SID</span></span>

<span data-ttu-id="2e605-131">このコマンドレットがメンバーを追加するセキュリティグループのセキュリティ ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="2e605-131">Specifies the security ID of the security group to which this cmdlet adds members.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2e605-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2e605-132">-Confirm</span></span>

<span data-ttu-id="2e605-133">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e605-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2e605-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2e605-134">-WhatIf</span></span>

<span data-ttu-id="2e605-135">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="2e605-135">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2e605-136">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2e605-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2e605-137">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e605-137">CommonParameters</span></span>

<span data-ttu-id="2e605-138">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2e605-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2e605-139">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e605-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2e605-140">入力</span><span class="sxs-lookup"><span data-stu-id="2e605-140">INPUTS</span></span>

### <span data-ttu-id="2e605-141">SecurityAccountsManager、System.string、LocalGroup、SecurityIdentifier のように指定されています。</span><span class="sxs-lookup"><span data-stu-id="2e605-141">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>

<span data-ttu-id="2e605-142">このコマンドレットには、ローカルプリンシパル、文字列、または SID をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="2e605-142">You can pipe a local principal, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="2e605-143">出力</span><span class="sxs-lookup"><span data-stu-id="2e605-143">OUTPUTS</span></span>

### <span data-ttu-id="2e605-144">なし</span><span class="sxs-lookup"><span data-stu-id="2e605-144">None</span></span>

<span data-ttu-id="2e605-145">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="2e605-145">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2e605-146">注</span><span class="sxs-lookup"><span data-stu-id="2e605-146">NOTES</span></span>

<span data-ttu-id="2e605-147">64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="2e605-147">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

<span data-ttu-id="2e605-148">**Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="2e605-148">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="2e605-149">考えられるソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2e605-149">The possible sources are as follows:</span></span>

- <span data-ttu-id="2e605-150">ローカル</span><span class="sxs-lookup"><span data-stu-id="2e605-150">Local</span></span>
- <span data-ttu-id="2e605-151">Active Directory</span><span class="sxs-lookup"><span data-stu-id="2e605-151">Active Directory</span></span>
- <span data-ttu-id="2e605-152">Azure Active Directory グループ</span><span class="sxs-lookup"><span data-stu-id="2e605-152">Azure Active Directory group</span></span>
- <span data-ttu-id="2e605-153">Microsoft アカウント</span><span class="sxs-lookup"><span data-stu-id="2e605-153">Microsoft Account</span></span>

<span data-ttu-id="2e605-154">**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2e605-154">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="2e605-155">以前のバージョンの場合、プロパティは空白になります。</span><span class="sxs-lookup"><span data-stu-id="2e605-155">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="2e605-156">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2e605-156">RELATED LINKS</span></span>

[<span data-ttu-id="2e605-157">Get-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="2e605-157">Get-LocalGroupMember</span></span>](Get-LocalGroupMember.md)

[<span data-ttu-id="2e605-158">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="2e605-158">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="2e605-159">Remove-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="2e605-159">Remove-LocalGroupMember</span></span>](Remove-LocalGroupMember.md)
