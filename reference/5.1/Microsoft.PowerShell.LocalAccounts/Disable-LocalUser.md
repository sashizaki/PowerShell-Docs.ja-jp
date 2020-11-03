---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/disable-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-LocalUser
ms.openlocfilehash: a62242251da00688d3299c60e4cdae7aae6f581a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211923"
---
# <span data-ttu-id="407f3-103">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="407f3-103">Disable-LocalUser</span></span>

## <span data-ttu-id="407f3-104">概要</span><span class="sxs-lookup"><span data-stu-id="407f3-104">SYNOPSIS</span></span>
<span data-ttu-id="407f3-105">ローカルユーザーアカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="407f3-105">Disables a local user account.</span></span>

## <span data-ttu-id="407f3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="407f3-106">SYNTAX</span></span>

### <span data-ttu-id="407f3-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="407f3-107">InputObject</span></span>

```
Disable-LocalUser [-InputObject] <LocalUser[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="407f3-108">Default</span><span class="sxs-lookup"><span data-stu-id="407f3-108">Default</span></span>

```
Disable-LocalUser [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="407f3-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="407f3-109">SecurityIdentifier</span></span>

```
Disable-LocalUser [-SID] <SecurityIdentifier[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="407f3-110">Description</span><span class="sxs-lookup"><span data-stu-id="407f3-110">DESCRIPTION</span></span>
<span data-ttu-id="407f3-111">**LocalUser** コマンドレットは、ローカルユーザーアカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="407f3-111">The **Disable-LocalUser** cmdlet disables local user accounts.</span></span>
<span data-ttu-id="407f3-112">ユーザーアカウントが無効になっている場合、ユーザーはログオンできません。</span><span class="sxs-lookup"><span data-stu-id="407f3-112">When a user account is disabled, the user cannot log on.</span></span>
<span data-ttu-id="407f3-113">ユーザーアカウントが有効になっている場合、ユーザーはログオンできます。</span><span class="sxs-lookup"><span data-stu-id="407f3-113">When a user account is enabled, the user can log on.</span></span>

> [!NOTE]
> <span data-ttu-id="407f3-114">64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="407f3-114">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="407f3-115">例</span><span class="sxs-lookup"><span data-stu-id="407f3-115">EXAMPLES</span></span>

### <span data-ttu-id="407f3-116">例 1: 名前を指定してアカウントを無効にする</span><span class="sxs-lookup"><span data-stu-id="407f3-116">Example 1: Disable an account by specifying a name</span></span>

```
PS C:\> Disable-LocalUser -Name "Admin02"
```

<span data-ttu-id="407f3-117">このコマンドは、Admin02 という名前のユーザーアカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="407f3-117">This command disables the user account named Admin02.</span></span>

### <span data-ttu-id="407f3-118">例 2: パイプラインを使用してアカウントを無効にする</span><span class="sxs-lookup"><span data-stu-id="407f3-118">Example 2: Disable an account by using the pipeline</span></span>

```
PS C:\> Get-LocalUser Guest | Disable-LocalUser
```

<span data-ttu-id="407f3-119">このコマンドは、 **LocalUser** を使用して組み込みのゲストアカウントを取得し、パイプライン演算子を使用して現在のコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="407f3-119">This command gets the built-in Guest account by using **Get-LocalUser** , and then passes it to the current cmdlet by using the pipeline operator.</span></span>
<span data-ttu-id="407f3-120">このコマンドレットは、そのアカウントを無効にします。</span><span class="sxs-lookup"><span data-stu-id="407f3-120">That cmdlet disables that account.</span></span>

## <span data-ttu-id="407f3-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="407f3-121">PARAMETERS</span></span>

### <span data-ttu-id="407f3-122">-InputObject</span><span class="sxs-lookup"><span data-stu-id="407f3-122">-InputObject</span></span>
<span data-ttu-id="407f3-123">このコマンドレットで無効にするユーザーアカウントの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="407f3-123">Specifies an array of user accounts that this cmdlet disables.</span></span>
<span data-ttu-id="407f3-124">ユーザーアカウントを取得するには、Get-LocalUser コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="407f3-124">To obtain a user account, use the Get-LocalUser cmdlet.</span></span>

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

### <span data-ttu-id="407f3-125">-Name</span><span class="sxs-lookup"><span data-stu-id="407f3-125">-Name</span></span>
<span data-ttu-id="407f3-126">このコマンドレットで無効にするユーザーアカウントの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="407f3-126">Specifies an array of names of the user accounts that this cmdlet disables.</span></span>

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

### <span data-ttu-id="407f3-127">-SID</span><span class="sxs-lookup"><span data-stu-id="407f3-127">-SID</span></span>
<span data-ttu-id="407f3-128">このコマンドレットで無効にするユーザーアカウントの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="407f3-128">Specifies an array of user accounts that this cmdlet disables.</span></span>

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

### <span data-ttu-id="407f3-129">-Confirm</span><span class="sxs-lookup"><span data-stu-id="407f3-129">-Confirm</span></span>
<span data-ttu-id="407f3-130">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="407f3-130">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="407f3-131">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="407f3-131">-WhatIf</span></span>
<span data-ttu-id="407f3-132">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="407f3-132">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="407f3-133">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="407f3-133">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="407f3-134">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="407f3-134">CommonParameters</span></span>
<span data-ttu-id="407f3-135">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="407f3-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="407f3-136">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="407f3-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="407f3-137">入力</span><span class="sxs-lookup"><span data-stu-id="407f3-137">INPUTS</span></span>

### <span data-ttu-id="407f3-138">SecurityAccountsManager、System.string、LocalUser、SecurityIdentifier のように指定されています。</span><span class="sxs-lookup"><span data-stu-id="407f3-138">System.Management.Automation.SecurityAccountsManager.LocalUser, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="407f3-139">このコマンドレットには、ローカルユーザー、文字列、または SID をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="407f3-139">You can pipe a local user, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="407f3-140">出力</span><span class="sxs-lookup"><span data-stu-id="407f3-140">OUTPUTS</span></span>

### <span data-ttu-id="407f3-141">なし</span><span class="sxs-lookup"><span data-stu-id="407f3-141">None</span></span>
<span data-ttu-id="407f3-142">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="407f3-142">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="407f3-143">注</span><span class="sxs-lookup"><span data-stu-id="407f3-143">NOTES</span></span>

* <span data-ttu-id="407f3-144">**Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="407f3-144">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="407f3-145">考えられるソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="407f3-145">The possible sources are as follows:</span></span>

- <span data-ttu-id="407f3-146">ローカル</span><span class="sxs-lookup"><span data-stu-id="407f3-146">Local</span></span>
- <span data-ttu-id="407f3-147">Active Directory</span><span class="sxs-lookup"><span data-stu-id="407f3-147">Active Directory</span></span>
- <span data-ttu-id="407f3-148">Azure Active Directory グループ</span><span class="sxs-lookup"><span data-stu-id="407f3-148">Azure Active Directory group</span></span>
- <span data-ttu-id="407f3-149">Microsoft アカウント</span><span class="sxs-lookup"><span data-stu-id="407f3-149">Microsoft Account</span></span>

<span data-ttu-id="407f3-150">**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="407f3-150">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="407f3-151">以前のバージョンの場合、プロパティは空白になります。</span><span class="sxs-lookup"><span data-stu-id="407f3-151">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="407f3-152">関連リンク</span><span class="sxs-lookup"><span data-stu-id="407f3-152">RELATED LINKS</span></span>

[<span data-ttu-id="407f3-153">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="407f3-153">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="407f3-154">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="407f3-154">Get-LocalUser</span></span>](Get-LocalUser.md)

[<span data-ttu-id="407f3-155">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="407f3-155">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="407f3-156">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="407f3-156">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="407f3-157">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="407f3-157">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="407f3-158">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="407f3-158">Set-LocalUser</span></span>](Set-LocalUser.md)
