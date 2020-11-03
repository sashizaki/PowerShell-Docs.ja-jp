---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/remove-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-LocalUser
ms.openlocfilehash: de1054971dab19f8cfae654208488ca9ce5e17e4
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215635"
---
# <span data-ttu-id="a9111-103">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="a9111-103">Remove-LocalUser</span></span>

## <span data-ttu-id="a9111-104">概要</span><span class="sxs-lookup"><span data-stu-id="a9111-104">SYNOPSIS</span></span>
<span data-ttu-id="a9111-105">ローカルユーザーアカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="a9111-105">Deletes local user accounts.</span></span>

## <span data-ttu-id="a9111-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a9111-106">SYNTAX</span></span>

### <span data-ttu-id="a9111-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="a9111-107">InputObject</span></span>

```
Remove-LocalUser [-InputObject] <LocalUser[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a9111-108">Default</span><span class="sxs-lookup"><span data-stu-id="a9111-108">Default</span></span>

```
Remove-LocalUser [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a9111-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="a9111-109">SecurityIdentifier</span></span>

```
Remove-LocalUser [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a9111-110">Description</span><span class="sxs-lookup"><span data-stu-id="a9111-110">DESCRIPTION</span></span>
<span data-ttu-id="a9111-111">**LocalUser** コマンドレットは、ローカルユーザーアカウントを削除します。</span><span class="sxs-lookup"><span data-stu-id="a9111-111">The **Remove-LocalUser** cmdlet deletes local user accounts.</span></span>

## <span data-ttu-id="a9111-112">例</span><span class="sxs-lookup"><span data-stu-id="a9111-112">EXAMPLES</span></span>

### <span data-ttu-id="a9111-113">例 1: ユーザーアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="a9111-113">Example 1: Delete a user account</span></span>

```
PS C:\> Remove-LocalUser -Name "AdminContoso02"
```

<span data-ttu-id="a9111-114">このコマンドを実行すると、AdminContoso02 という名前のユーザーアカウントが削除されます。</span><span class="sxs-lookup"><span data-stu-id="a9111-114">This command deletes the user account named AdminContoso02.</span></span>

> [!NOTE]
> <span data-ttu-id="a9111-115">64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="a9111-115">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="a9111-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a9111-116">PARAMETERS</span></span>

### <span data-ttu-id="a9111-117">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a9111-117">-InputObject</span></span>
<span data-ttu-id="a9111-118">このコマンドレットによって削除されるユーザーアカウントの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9111-118">Specifies an array of user accounts that this cmdlet deletes.</span></span>
<span data-ttu-id="a9111-119">ユーザーアカウントを取得するには、Get-LocalUser コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a9111-119">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalUser[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a9111-120">-Name</span><span class="sxs-lookup"><span data-stu-id="a9111-120">-Name</span></span>
<span data-ttu-id="a9111-121">このコマンドレットによって削除されるユーザーアカウントの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9111-121">Specifies an array of names of the user accounts that this cmdlet deletes.</span></span>

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

### <span data-ttu-id="a9111-122">-SID</span><span class="sxs-lookup"><span data-stu-id="a9111-122">-SID</span></span>
<span data-ttu-id="a9111-123">このコマンドレットによって削除されるユーザーアカウントのセキュリティ Id (Sid) の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="a9111-123">Specifies an array of security IDs (SIDs) of user accounts that this cmdlet deletes.</span></span>

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

### <span data-ttu-id="a9111-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a9111-124">-Confirm</span></span>
<span data-ttu-id="a9111-125">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9111-125">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a9111-126">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a9111-126">-WhatIf</span></span>
<span data-ttu-id="a9111-127">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="a9111-127">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a9111-128">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a9111-128">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a9111-129">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a9111-129">CommonParameters</span></span>
<span data-ttu-id="a9111-130">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a9111-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a9111-131">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a9111-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a9111-132">入力</span><span class="sxs-lookup"><span data-stu-id="a9111-132">INPUTS</span></span>

### <span data-ttu-id="a9111-133">SecurityAccountsManager、System.string、LocalUser、SecurityIdentifier のように指定されています。</span><span class="sxs-lookup"><span data-stu-id="a9111-133">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="a9111-134">このコマンドレットには、ローカルユーザー、文字列、または SID をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="a9111-134">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="a9111-135">出力</span><span class="sxs-lookup"><span data-stu-id="a9111-135">OUTPUTS</span></span>

### <span data-ttu-id="a9111-136">なし</span><span class="sxs-lookup"><span data-stu-id="a9111-136">None</span></span>
<span data-ttu-id="a9111-137">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="a9111-137">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a9111-138">注</span><span class="sxs-lookup"><span data-stu-id="a9111-138">NOTES</span></span>

* <span data-ttu-id="a9111-139">**Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="a9111-139">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="a9111-140">考えられるソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a9111-140">The possible sources are as follows:</span></span>

- <span data-ttu-id="a9111-141">ローカル</span><span class="sxs-lookup"><span data-stu-id="a9111-141">Local</span></span>
- <span data-ttu-id="a9111-142">Active Directory</span><span class="sxs-lookup"><span data-stu-id="a9111-142">Active Directory</span></span>
- <span data-ttu-id="a9111-143">Azure Active Directory グループ</span><span class="sxs-lookup"><span data-stu-id="a9111-143">Azure Active Directory group</span></span>
- <span data-ttu-id="a9111-144">Microsoft アカウント</span><span class="sxs-lookup"><span data-stu-id="a9111-144">Microsoft Account</span></span>

<span data-ttu-id="a9111-145">**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a9111-145">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="a9111-146">以前のバージョンの場合、プロパティは空白になります。</span><span class="sxs-lookup"><span data-stu-id="a9111-146">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="a9111-147">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a9111-147">RELATED LINKS</span></span>

[<span data-ttu-id="a9111-148">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="a9111-148">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="a9111-149">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="a9111-149">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="a9111-150">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="a9111-150">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="a9111-151">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="a9111-151">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="a9111-152">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="a9111-152">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="a9111-153">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="a9111-153">Set-LocalUser</span></span>](Set-LocalUser.md)
