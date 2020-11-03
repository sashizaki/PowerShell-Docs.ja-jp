---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalGroupMember
ms.openlocfilehash: 6e6264a65c343657c2f2f87384d76cc3f1554d3d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214680"
---
# <span data-ttu-id="cb3fb-103">Remove-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="cb3fb-103">Remove-LocalGroupMember</span></span>

## <span data-ttu-id="cb3fb-104">概要</span><span class="sxs-lookup"><span data-stu-id="cb3fb-104">SYNOPSIS</span></span>
<span data-ttu-id="cb3fb-105">ローカルグループからメンバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-105">Removes members from a local group.</span></span>

## <span data-ttu-id="cb3fb-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cb3fb-106">SYNTAX</span></span>

### <span data-ttu-id="cb3fb-107">グループ</span><span class="sxs-lookup"><span data-stu-id="cb3fb-107">Group</span></span>

```
Remove-LocalGroupMember [-Group] <LocalGroup> [-Member] <LocalPrincipal[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="cb3fb-108">Default</span><span class="sxs-lookup"><span data-stu-id="cb3fb-108">Default</span></span>

```
Remove-LocalGroupMember [-Member] <LocalPrincipal[]> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cb3fb-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="cb3fb-109">SecurityIdentifier</span></span>

```
Remove-LocalGroupMember [-Member] <LocalPrincipal[]> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="cb3fb-110">Description</span><span class="sxs-lookup"><span data-stu-id="cb3fb-110">DESCRIPTION</span></span>
<span data-ttu-id="cb3fb-111">**LocalGroupMember** コマンドレットは、ローカルグループからユーザーまたはグループを削除します。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-111">The **Remove-LocalGroupMember** cmdlet removes users or groups from a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="cb3fb-112">64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="cb3fb-113">例</span><span class="sxs-lookup"><span data-stu-id="cb3fb-113">EXAMPLES</span></span>

### <span data-ttu-id="cb3fb-114">例 1: Administrators グループからメンバーを削除する</span><span class="sxs-lookup"><span data-stu-id="cb3fb-114">Example 1: Remove members from the Administrators group</span></span>

```
PS C:\> Remove-LocalGroupMember -Group "Administrators" -Member "Admin02", "MicrosoftAccount\username@Outlook.com", "AzureAD\DavidChew@contoso.com", "CONTOSO\Domain Admins"
```

<span data-ttu-id="cb3fb-115">このコマンドは、ローカルの Administrators グループから複数のメンバーを削除します。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-115">This command removes several members from the local Administrators group.</span></span>
<span data-ttu-id="cb3fb-116">このコマンドレットによって削除されるメンバーには、ローカルユーザーアカウント、Microsoft アカウント、Azure Active Directory アカウント、ドメイングループなどがあります。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-116">The members that this cmdlet removes include a local user account, a Microsoft account, an Azure Active Directory account, and a domain group.</span></span>
<span data-ttu-id="cb3fb-117">この例では、Outlook.com のアカウントのユーザー名にプレースホルダー値を使用します。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-117">This example uses a placeholder value for the user name of an account at Outlook.com.</span></span>

## <span data-ttu-id="cb3fb-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cb3fb-118">PARAMETERS</span></span>

### <span data-ttu-id="cb3fb-119">-Group</span><span class="sxs-lookup"><span data-stu-id="cb3fb-119">-Group</span></span>
<span data-ttu-id="cb3fb-120">このコマンドレットがメンバーを削除するセキュリティグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-120">Specifies the security group from which this cmdlet removes members.</span></span>

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

### <span data-ttu-id="cb3fb-121">-メンバー</span><span class="sxs-lookup"><span data-stu-id="cb3fb-121">-Member</span></span>
<span data-ttu-id="cb3fb-122">このコマンドレットによってセキュリティグループから削除されるユーザーまたはグループの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-122">Specifies an array of users or groups that this cmdlet removes from a security group.</span></span>
<span data-ttu-id="cb3fb-123">名前、セキュリティ ID (SID)、または **Localprincipal** オブジェクトを使用して、ユーザーまたはグループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-123">You can specify users or groups by name, security ID (SID), or **LocalPrincipal** objects.</span></span>
<span data-ttu-id="cb3fb-124">S-R-s-s で SID 文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-124">Specify SID strings in S-R-I-S-S .</span></span>
<span data-ttu-id="cb3fb-125">.</span><span class="sxs-lookup"><span data-stu-id="cb3fb-125">.</span></span> <span data-ttu-id="cb3fb-126">.</span><span class="sxs-lookup"><span data-stu-id="cb3fb-126">.</span></span>
<span data-ttu-id="cb3fb-127">(</span><span class="sxs-lookup"><span data-stu-id="cb3fb-127">format.</span></span>

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

### <span data-ttu-id="cb3fb-128">-Name</span><span class="sxs-lookup"><span data-stu-id="cb3fb-128">-Name</span></span>
<span data-ttu-id="cb3fb-129">このコマンドレットでメンバーを削除するセキュリティグループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-129">Specifies the name of the security group from which this cmdlet removes members.</span></span>

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

### <span data-ttu-id="cb3fb-130">-SID</span><span class="sxs-lookup"><span data-stu-id="cb3fb-130">-SID</span></span>
<span data-ttu-id="cb3fb-131">このコマンドレットでメンバーを削除するセキュリティグループのセキュリティ ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-131">Specifies the security ID of the security group from which this cmdlet removes members.</span></span>

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

### <span data-ttu-id="cb3fb-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cb3fb-132">-Confirm</span></span>
<span data-ttu-id="cb3fb-133">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="cb3fb-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cb3fb-134">-WhatIf</span></span>
<span data-ttu-id="cb3fb-135">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-135">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="cb3fb-136">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="cb3fb-137">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="cb3fb-137">CommonParameters</span></span>
<span data-ttu-id="cb3fb-138">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cb3fb-139">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cb3fb-140">入力</span><span class="sxs-lookup"><span data-stu-id="cb3fb-140">INPUTS</span></span>

### <span data-ttu-id="cb3fb-141">SecurityAccountsManager、System.string、SecurityIdentifier のように指定されていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-141">System.Management.Automation.SecurityAccountsManager.LocalPrincipal, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="cb3fb-142">このコマンドレットには、ローカルプリンシパル、文字列、または SID をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-142">You can pipe a local principal, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="cb3fb-143">出力</span><span class="sxs-lookup"><span data-stu-id="cb3fb-143">OUTPUTS</span></span>

### <span data-ttu-id="cb3fb-144">なし</span><span class="sxs-lookup"><span data-stu-id="cb3fb-144">None</span></span>
<span data-ttu-id="cb3fb-145">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-145">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="cb3fb-146">注</span><span class="sxs-lookup"><span data-stu-id="cb3fb-146">NOTES</span></span>

* <span data-ttu-id="cb3fb-147">**Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-147">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="cb3fb-148">考えられるソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-148">The possible sources are as follows:</span></span>

- <span data-ttu-id="cb3fb-149">ローカル</span><span class="sxs-lookup"><span data-stu-id="cb3fb-149">Local</span></span>
- <span data-ttu-id="cb3fb-150">Active Directory</span><span class="sxs-lookup"><span data-stu-id="cb3fb-150">Active Directory</span></span>
- <span data-ttu-id="cb3fb-151">Azure Active Directory グループ</span><span class="sxs-lookup"><span data-stu-id="cb3fb-151">Azure Active Directory group</span></span>
- <span data-ttu-id="cb3fb-152">Microsoft アカウント</span><span class="sxs-lookup"><span data-stu-id="cb3fb-152">Microsoft Account</span></span>

<span data-ttu-id="cb3fb-153">**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-153">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="cb3fb-154">以前のバージョンの場合、プロパティは空白になります。</span><span class="sxs-lookup"><span data-stu-id="cb3fb-154">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="cb3fb-155">関連リンク</span><span class="sxs-lookup"><span data-stu-id="cb3fb-155">RELATED LINKS</span></span>

[<span data-ttu-id="cb3fb-156">Add-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="cb3fb-156">Add-LocalGroupMember</span></span>](Add-LocalGroupMember.md)

[<span data-ttu-id="cb3fb-157">Get-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="cb3fb-157">Get-LocalGroupMember</span></span>](Get-LocalGroupMember.md)

[<span data-ttu-id="cb3fb-158">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="cb3fb-158">New-LocalGroup</span></span>](New-LocalGroup.md)
