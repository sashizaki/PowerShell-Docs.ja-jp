---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalGroup
ms.openlocfilehash: 6a2f921972fef1794581b301df6e7439e56c7f47
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214675"
---
# <span data-ttu-id="2d612-103">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="2d612-103">Remove-LocalGroup</span></span>

## <span data-ttu-id="2d612-104">概要</span><span class="sxs-lookup"><span data-stu-id="2d612-104">SYNOPSIS</span></span>
<span data-ttu-id="2d612-105">ローカルセキュリティグループを削除します。</span><span class="sxs-lookup"><span data-stu-id="2d612-105">Deletes local security groups.</span></span>

## <span data-ttu-id="2d612-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2d612-106">SYNTAX</span></span>

### <span data-ttu-id="2d612-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="2d612-107">InputObject</span></span>

```
Remove-LocalGroup [-InputObject] <LocalGroup[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2d612-108">Default</span><span class="sxs-lookup"><span data-stu-id="2d612-108">Default</span></span>

```
Remove-LocalGroup [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="2d612-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="2d612-109">SecurityIdentifier</span></span>

```
Remove-LocalGroup [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2d612-110">Description</span><span class="sxs-lookup"><span data-stu-id="2d612-110">DESCRIPTION</span></span>
<span data-ttu-id="2d612-111">**LocalGroup** コマンドレットは、ローカルセキュリティグループを削除します。</span><span class="sxs-lookup"><span data-stu-id="2d612-111">The **Remove-LocalGroup** cmdlet deletes local security groups.</span></span>
<span data-ttu-id="2d612-112">このコマンドレットは、ローカルグループのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="2d612-112">This cmdlet deletes only a local group.</span></span>
<span data-ttu-id="2d612-113">そのグループに属するユーザーアカウント、コンピューターアカウント、またはグループアカウントは削除されません。</span><span class="sxs-lookup"><span data-stu-id="2d612-113">It does not delete the user accounts, computer accounts, or group accounts that belong to that group.</span></span>
<span data-ttu-id="2d612-114">削除されたグループを回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="2d612-114">You cannot recover a deleted group.</span></span>

<span data-ttu-id="2d612-115">グループを削除してから、同じグループ名を持つ別のグループを作成する場合は、新しいグループに新しいアクセス許可を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d612-115">If you delete a group and then create another group that has the same group name, you must set new permissions for the new group.</span></span>
<span data-ttu-id="2d612-116">新しいグループは、そのグループに割り当てられたアクセス許可を継承しません。</span><span class="sxs-lookup"><span data-stu-id="2d612-116">The new group does not inherit the permissions that were assigned to the group.</span></span>

> [!NOTE]
> <span data-ttu-id="2d612-117">64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="2d612-117">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="2d612-118">例</span><span class="sxs-lookup"><span data-stu-id="2d612-118">EXAMPLES</span></span>

### <span data-ttu-id="2d612-119">例 1: セキュリティグループを削除する</span><span class="sxs-lookup"><span data-stu-id="2d612-119">Example 1: Delete a security group</span></span>

```
PS C:\> Remove-LocalGroup -Name "SecurityGroup04"
```

<span data-ttu-id="2d612-120">このコマンドは、SecurityGroup04 という名前のグループを削除します。</span><span class="sxs-lookup"><span data-stu-id="2d612-120">This command deletes the group named SecurityGroup04.</span></span>

## <span data-ttu-id="2d612-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2d612-121">PARAMETERS</span></span>

### <span data-ttu-id="2d612-122">-InputObject</span><span class="sxs-lookup"><span data-stu-id="2d612-122">-InputObject</span></span>
<span data-ttu-id="2d612-123">このコマンドレットが削除するセキュリティグループの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d612-123">Specifies an array of security groups that this cmdlet deletes.</span></span>
<span data-ttu-id="2d612-124">グループを取得するには、Get-LocalGroup コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="2d612-124">To obtain groups, use the Get-LocalGroup cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2d612-125">-Name</span><span class="sxs-lookup"><span data-stu-id="2d612-125">-Name</span></span>
<span data-ttu-id="2d612-126">このコマンドレットが削除するセキュリティグループの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d612-126">Specifies an array of names of the security groups that this cmdlet deletes.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2d612-127">-SID</span><span class="sxs-lookup"><span data-stu-id="2d612-127">-SID</span></span>
<span data-ttu-id="2d612-128">このコマンドレットが削除するセキュリティグループのセキュリティ Id (Sid) の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="2d612-128">Specifies an array of security IDs (SIDs) of security groups that this cmdlet deletes.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="2d612-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2d612-129">-Confirm</span></span>
<span data-ttu-id="2d612-130">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d612-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2d612-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2d612-131">-WhatIf</span></span>
<span data-ttu-id="2d612-132">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="2d612-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2d612-133">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2d612-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2d612-134">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d612-134">CommonParameters</span></span>
<span data-ttu-id="2d612-135">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2d612-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2d612-136">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d612-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2d612-137">入力</span><span class="sxs-lookup"><span data-stu-id="2d612-137">INPUTS</span></span>

### <span data-ttu-id="2d612-138">SecurityAccountsManager、System.string、LocalGroup、SecurityIdentifier のように指定されています。</span><span class="sxs-lookup"><span data-stu-id="2d612-138">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="2d612-139">このコマンドレットには、セキュリティグループ、文字列、または SID をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="2d612-139">You can pipe a security group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="2d612-140">出力</span><span class="sxs-lookup"><span data-stu-id="2d612-140">OUTPUTS</span></span>

### <span data-ttu-id="2d612-141">なし</span><span class="sxs-lookup"><span data-stu-id="2d612-141">None</span></span>
<span data-ttu-id="2d612-142">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="2d612-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="2d612-143">注</span><span class="sxs-lookup"><span data-stu-id="2d612-143">NOTES</span></span>

* <span data-ttu-id="2d612-144">このコマンドレットでは、次の既定のグループを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="2d612-144">This cmdlet cannot delete the following default groups:</span></span>

- <span data-ttu-id="2d612-145">管理者</span><span class="sxs-lookup"><span data-stu-id="2d612-145">Administrators</span></span>
- <span data-ttu-id="2d612-146">Backup Operators</span><span class="sxs-lookup"><span data-stu-id="2d612-146">Backup Operators</span></span>
- <span data-ttu-id="2d612-147">Cryptographic Operators</span><span class="sxs-lookup"><span data-stu-id="2d612-147">Cryptographic Operators</span></span>
- <span data-ttu-id="2d612-148">Distributed COM Users</span><span class="sxs-lookup"><span data-stu-id="2d612-148">Distributed COM Users</span></span>
- <span data-ttu-id="2d612-149">イベント ログ リーダー</span><span class="sxs-lookup"><span data-stu-id="2d612-149">Event Log Readers</span></span>
- <span data-ttu-id="2d612-150">ゲスト</span><span class="sxs-lookup"><span data-stu-id="2d612-150">Guests</span></span>
- <span data-ttu-id="2d612-151">Hyper-V 管理者</span><span class="sxs-lookup"><span data-stu-id="2d612-151">Hyper-V Administrators</span></span>
- <span data-ttu-id="2d612-152">IIS_IUSRS</span><span class="sxs-lookup"><span data-stu-id="2d612-152">IIS_IUSRS</span></span>
- <span data-ttu-id="2d612-153">Network Configuration Operators</span><span class="sxs-lookup"><span data-stu-id="2d612-153">Network Configuration Operators</span></span>
- <span data-ttu-id="2d612-154">パフォーマンス ログ ユーザー</span><span class="sxs-lookup"><span data-stu-id="2d612-154">Performance Log Users</span></span>
- <span data-ttu-id="2d612-155">パフォーマンス モニター ユーザー</span><span class="sxs-lookup"><span data-stu-id="2d612-155">Performance Monitor Users</span></span>
- <span data-ttu-id="2d612-156">Power Users</span><span class="sxs-lookup"><span data-stu-id="2d612-156">Power Users</span></span>
- <span data-ttu-id="2d612-157">Remote Desktop Users</span><span class="sxs-lookup"><span data-stu-id="2d612-157">Remote Desktop Users</span></span>
- <span data-ttu-id="2d612-158">リモート管理ユーザー</span><span class="sxs-lookup"><span data-stu-id="2d612-158">Remote Management Users</span></span>
- <span data-ttu-id="2d612-159">レプリケーター</span><span class="sxs-lookup"><span data-stu-id="2d612-159">Replicator</span></span>
- <span data-ttu-id="2d612-160">ユーザー</span><span class="sxs-lookup"><span data-stu-id="2d612-160">Users</span></span>
- <span data-ttu-id="2d612-161">WinRMRemoteWMIUsers__</span><span class="sxs-lookup"><span data-stu-id="2d612-161">WinRMRemoteWMIUsers__</span></span>

* <span data-ttu-id="2d612-162">**Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="2d612-162">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="2d612-163">考えられるソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="2d612-163">The possible sources are as follows:</span></span>

- <span data-ttu-id="2d612-164">ローカル</span><span class="sxs-lookup"><span data-stu-id="2d612-164">Local</span></span>
- <span data-ttu-id="2d612-165">Active Directory</span><span class="sxs-lookup"><span data-stu-id="2d612-165">Active Directory</span></span>
- <span data-ttu-id="2d612-166">Azure Active Directory グループ</span><span class="sxs-lookup"><span data-stu-id="2d612-166">Azure Active Directory group</span></span>
- <span data-ttu-id="2d612-167">Microsoft アカウント</span><span class="sxs-lookup"><span data-stu-id="2d612-167">Microsoft Account</span></span>

<span data-ttu-id="2d612-168">**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2d612-168">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="2d612-169">以前のバージョンの場合、プロパティは空白になります。</span><span class="sxs-lookup"><span data-stu-id="2d612-169">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="2d612-170">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2d612-170">RELATED LINKS</span></span>

[<span data-ttu-id="2d612-171">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="2d612-171">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="2d612-172">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="2d612-172">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="2d612-173">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="2d612-173">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)

[<span data-ttu-id="2d612-174">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="2d612-174">Set-LocalGroup</span></span>](Set-LocalGroup.md)
