---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/rename-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-LocalUser
ms.openlocfilehash: fc5740e52e08ad2146981799a4e1659cd420b321
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215632"
---
# <span data-ttu-id="ab6e4-103">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ab6e4-103">Rename-LocalUser</span></span>

## <span data-ttu-id="ab6e4-104">概要</span><span class="sxs-lookup"><span data-stu-id="ab6e4-104">SYNOPSIS</span></span>
<span data-ttu-id="ab6e4-105">ローカルユーザーアカウントの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-105">Renames a local user account.</span></span>

## <span data-ttu-id="ab6e4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="ab6e4-106">SYNTAX</span></span>

### <span data-ttu-id="ab6e4-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="ab6e4-107">InputObject</span></span>

```
Rename-LocalUser [-InputObject] <LocalUser> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ab6e4-108">Default</span><span class="sxs-lookup"><span data-stu-id="ab6e4-108">Default</span></span>

```
Rename-LocalUser [-Name] <String> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="ab6e4-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="ab6e4-109">SecurityIdentifier</span></span>

```
Rename-LocalUser [-NewName] <String> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="ab6e4-110">Description</span><span class="sxs-lookup"><span data-stu-id="ab6e4-110">DESCRIPTION</span></span>
<span data-ttu-id="ab6e4-111">LocalUser コマンドレットは、ローカルユーザーアカウントの名前を **変更** します。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-111">The **Rename-LocalUser** cmdlet renames a local user account.</span></span>

> [!NOTE]
> <span data-ttu-id="ab6e4-112">64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="ab6e4-113">例</span><span class="sxs-lookup"><span data-stu-id="ab6e4-113">EXAMPLES</span></span>

### <span data-ttu-id="ab6e4-114">例 1: ユーザーアカウントの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="ab6e4-114">Example 1: Rename a user account</span></span>

```
PS C:\> Rename-LocalUser -Name "Admin02" -NewName "AdminContoso02"
```

<span data-ttu-id="ab6e4-115">このコマンドは、Admin02 という名前のユーザーアカウントの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-115">This command renames the user account named Admin02.</span></span>

## <span data-ttu-id="ab6e4-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="ab6e4-116">PARAMETERS</span></span>

### <span data-ttu-id="ab6e4-117">-InputObject</span><span class="sxs-lookup"><span data-stu-id="ab6e4-117">-InputObject</span></span>
<span data-ttu-id="ab6e4-118">このコマンドレットの名前を変更するユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-118">Specifies the user account that this cmdlet renames.</span></span>
<span data-ttu-id="ab6e4-119">ユーザーアカウントを取得するには、Get-LocalUser コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-119">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalUser
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ab6e4-120">-Name</span><span class="sxs-lookup"><span data-stu-id="ab6e4-120">-Name</span></span>
<span data-ttu-id="ab6e4-121">このコマンドレットの名前を変更するユーザーアカウントの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-121">Specifies the name of the user account that this cmdlet renames.</span></span>

```yaml
Type: System.String
Parameter Sets: Default
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ab6e4-122">-NewName</span><span class="sxs-lookup"><span data-stu-id="ab6e4-122">-NewName</span></span>
<span data-ttu-id="ab6e4-123">ユーザーアカウントの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-123">Specifies a new name for the user account.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="ab6e4-124">-SID</span><span class="sxs-lookup"><span data-stu-id="ab6e4-124">-SID</span></span>
<span data-ttu-id="ab6e4-125">このコマンドレットの名前を変更するユーザーアカウントのセキュリティ ID (SID) を指定します。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-125">Specifies the security ID (SID) of a user accounts that this cmdlet renames.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier
Parameter Sets: SecurityIdentifier
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="ab6e4-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="ab6e4-126">-Confirm</span></span>
<span data-ttu-id="ab6e4-127">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="ab6e4-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="ab6e4-128">-WhatIf</span></span>
<span data-ttu-id="ab6e4-129">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="ab6e4-130">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="ab6e4-131">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="ab6e4-131">CommonParameters</span></span>
<span data-ttu-id="ab6e4-132">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="ab6e4-133">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="ab6e4-134">入力</span><span class="sxs-lookup"><span data-stu-id="ab6e4-134">INPUTS</span></span>

### <span data-ttu-id="ab6e4-135">SecurityAccountsManager、System.string、LocalUser、SecurityIdentifier のように指定されています。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-135">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="ab6e4-136">このコマンドレットには、ローカルユーザー、文字列、または SID をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-136">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="ab6e4-137">出力</span><span class="sxs-lookup"><span data-stu-id="ab6e4-137">OUTPUTS</span></span>

### <span data-ttu-id="ab6e4-138">なし</span><span class="sxs-lookup"><span data-stu-id="ab6e4-138">None</span></span>
<span data-ttu-id="ab6e4-139">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-139">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="ab6e4-140">注</span><span class="sxs-lookup"><span data-stu-id="ab6e4-140">NOTES</span></span>

* <span data-ttu-id="ab6e4-141">**Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-141">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="ab6e4-142">考えられるソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-142">The possible sources are as follows:</span></span>

- <span data-ttu-id="ab6e4-143">ローカル</span><span class="sxs-lookup"><span data-stu-id="ab6e4-143">Local</span></span>
- <span data-ttu-id="ab6e4-144">Active Directory</span><span class="sxs-lookup"><span data-stu-id="ab6e4-144">Active Directory</span></span>
- <span data-ttu-id="ab6e4-145">Azure Active Directory グループ</span><span class="sxs-lookup"><span data-stu-id="ab6e4-145">Azure Active Directory group</span></span>
- <span data-ttu-id="ab6e4-146">Microsoft アカウント</span><span class="sxs-lookup"><span data-stu-id="ab6e4-146">Microsoft Account</span></span>

<span data-ttu-id="ab6e4-147">**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-147">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="ab6e4-148">以前のバージョンの場合、プロパティは空白になります。</span><span class="sxs-lookup"><span data-stu-id="ab6e4-148">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="ab6e4-149">関連リンク</span><span class="sxs-lookup"><span data-stu-id="ab6e4-149">RELATED LINKS</span></span>

[<span data-ttu-id="ab6e4-150">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ab6e4-150">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="ab6e4-151">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ab6e4-151">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="ab6e4-152">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ab6e4-152">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="ab6e4-153">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ab6e4-153">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="ab6e4-154">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ab6e4-154">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="ab6e4-155">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="ab6e4-155">Set-LocalUser</span></span>](Set-LocalUser.md)
