---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/set-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-LocalGroup
ms.openlocfilehash: 471c3c7bc01bf26dfe9d8eec26e4414464cae02e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215627"
---
# <span data-ttu-id="6d1ab-103">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="6d1ab-103">Set-LocalGroup</span></span>

## <span data-ttu-id="6d1ab-104">概要</span><span class="sxs-lookup"><span data-stu-id="6d1ab-104">SYNOPSIS</span></span>
<span data-ttu-id="6d1ab-105">ローカルセキュリティグループを変更します。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-105">Changes a local security group.</span></span>

## <span data-ttu-id="6d1ab-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6d1ab-106">SYNTAX</span></span>

### <span data-ttu-id="6d1ab-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="6d1ab-107">InputObject</span></span>

```
Set-LocalGroup -Description <String> [-InputObject] <LocalGroup> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6d1ab-108">Default</span><span class="sxs-lookup"><span data-stu-id="6d1ab-108">Default</span></span>

```
Set-LocalGroup -Description <String> [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="6d1ab-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="6d1ab-109">SecurityIdentifier</span></span>

```
Set-LocalGroup -Description <String> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="6d1ab-110">Description</span><span class="sxs-lookup"><span data-stu-id="6d1ab-110">DESCRIPTION</span></span>
<span data-ttu-id="6d1ab-111">**LocalGroup** コマンドレットは、ローカルセキュリティグループを変更します。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-111">The **Set-LocalGroup** cmdlet changes a local security group.</span></span>

## <span data-ttu-id="6d1ab-112">例</span><span class="sxs-lookup"><span data-stu-id="6d1ab-112">EXAMPLES</span></span>

### <span data-ttu-id="6d1ab-113">例 1: グループの説明を変更する</span><span class="sxs-lookup"><span data-stu-id="6d1ab-113">Example 1: Change a group description</span></span>

```
PS C:\> Set-LocalGroup -Name "SecurityGroup04" -Description "This is a sample description."
```

<span data-ttu-id="6d1ab-114">このコマンドは、ローカルグループの説明を変更します。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-114">This command changes the description of a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="6d1ab-115">64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-115">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="6d1ab-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6d1ab-116">PARAMETERS</span></span>

### <span data-ttu-id="6d1ab-117">-Description</span><span class="sxs-lookup"><span data-stu-id="6d1ab-117">-Description</span></span>
<span data-ttu-id="6d1ab-118">グループのコメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-118">Specifies a comment for the group.</span></span>
<span data-ttu-id="6d1ab-119">最大長は48文字です。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-119">The maximum length is 48 characters.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6d1ab-120">-InputObject</span><span class="sxs-lookup"><span data-stu-id="6d1ab-120">-InputObject</span></span>
<span data-ttu-id="6d1ab-121">このコマンドレットが変更するセキュリティグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-121">Specifies the security group that this cmdlet changes.</span></span>
<span data-ttu-id="6d1ab-122">セキュリティグループを取得するには、Get-LocalGroup コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-122">To obtain a security group, use the Get-LocalGroup cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6d1ab-123">-Name</span><span class="sxs-lookup"><span data-stu-id="6d1ab-123">-Name</span></span>
<span data-ttu-id="6d1ab-124">このコマンドレットが変更するセキュリティグループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-124">Specifies the name of the security group that this cmdlet changes.</span></span>

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

### <span data-ttu-id="6d1ab-125">-SID</span><span class="sxs-lookup"><span data-stu-id="6d1ab-125">-SID</span></span>
<span data-ttu-id="6d1ab-126">このコマンドレットが変更するセキュリティグループのセキュリティ ID (SID) を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-126">Specifies the security ID (SID) of the security group that this cmdlet changes.</span></span>

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

### <span data-ttu-id="6d1ab-127">-Confirm</span><span class="sxs-lookup"><span data-stu-id="6d1ab-127">-Confirm</span></span>
<span data-ttu-id="6d1ab-128">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-128">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="6d1ab-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="6d1ab-129">-WhatIf</span></span>
<span data-ttu-id="6d1ab-130">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-130">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="6d1ab-131">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="6d1ab-132">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6d1ab-132">CommonParameters</span></span>
<span data-ttu-id="6d1ab-133">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6d1ab-134">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6d1ab-135">入力</span><span class="sxs-lookup"><span data-stu-id="6d1ab-135">INPUTS</span></span>

### <span data-ttu-id="6d1ab-136">SecurityAccountsManager、System.string、LocalGroup、SecurityIdentifier のように指定されています。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-136">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="6d1ab-137">このコマンドレットには、セキュリティグループ、文字列、または SID をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-137">You can pipe a security group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="6d1ab-138">出力</span><span class="sxs-lookup"><span data-stu-id="6d1ab-138">OUTPUTS</span></span>

### <span data-ttu-id="6d1ab-139">なし</span><span class="sxs-lookup"><span data-stu-id="6d1ab-139">None</span></span>
<span data-ttu-id="6d1ab-140">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-140">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="6d1ab-141">注</span><span class="sxs-lookup"><span data-stu-id="6d1ab-141">NOTES</span></span>

* <span data-ttu-id="6d1ab-142">**Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-142">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="6d1ab-143">考えられるソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-143">The possible sources are as follows:</span></span>

- <span data-ttu-id="6d1ab-144">ローカル</span><span class="sxs-lookup"><span data-stu-id="6d1ab-144">Local</span></span>
- <span data-ttu-id="6d1ab-145">Active Directory</span><span class="sxs-lookup"><span data-stu-id="6d1ab-145">Active Directory</span></span>
- <span data-ttu-id="6d1ab-146">Azure Active Directory グループ</span><span class="sxs-lookup"><span data-stu-id="6d1ab-146">Azure Active Directory group</span></span>
- <span data-ttu-id="6d1ab-147">Microsoft アカウント</span><span class="sxs-lookup"><span data-stu-id="6d1ab-147">Microsoft Account</span></span>

<span data-ttu-id="6d1ab-148">**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-148">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="6d1ab-149">以前のバージョンの場合、プロパティは空白になります。</span><span class="sxs-lookup"><span data-stu-id="6d1ab-149">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="6d1ab-150">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6d1ab-150">RELATED LINKS</span></span>

[<span data-ttu-id="6d1ab-151">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="6d1ab-151">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="6d1ab-152">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="6d1ab-152">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="6d1ab-153">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="6d1ab-153">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="6d1ab-154">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="6d1ab-154">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)
