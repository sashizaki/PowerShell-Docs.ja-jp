---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/rename-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Rename-LocalGroup
ms.openlocfilehash: 566d33bdeb52323cca41fa9757d36334b40f1654
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215624"
---
# <span data-ttu-id="c175e-103">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="c175e-103">Rename-LocalGroup</span></span>

## <span data-ttu-id="c175e-104">概要</span><span class="sxs-lookup"><span data-stu-id="c175e-104">SYNOPSIS</span></span>
<span data-ttu-id="c175e-105">ローカルセキュリティグループの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="c175e-105">Renames a local security group.</span></span>

## <span data-ttu-id="c175e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c175e-106">SYNTAX</span></span>

### <span data-ttu-id="c175e-107">InputObject</span><span class="sxs-lookup"><span data-stu-id="c175e-107">InputObject</span></span>

```
Rename-LocalGroup [-InputObject] <LocalGroup> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c175e-108">Default</span><span class="sxs-lookup"><span data-stu-id="c175e-108">Default</span></span>

```
Rename-LocalGroup [-Name] <String> [-NewName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c175e-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="c175e-109">SecurityIdentifier</span></span>

```
Rename-LocalGroup [-NewName] <String> [-SID] <SecurityIdentifier> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c175e-110">Description</span><span class="sxs-lookup"><span data-stu-id="c175e-110">DESCRIPTION</span></span>
<span data-ttu-id="c175e-111">LocalGroup コマンドレットは、ローカルセキュリティグループの名前を **変更** します。</span><span class="sxs-lookup"><span data-stu-id="c175e-111">The **Rename-LocalGroup** cmdlet renames a local security group.</span></span>

> [!NOTE]
> <span data-ttu-id="c175e-112">64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c175e-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="c175e-113">例</span><span class="sxs-lookup"><span data-stu-id="c175e-113">EXAMPLES</span></span>

### <span data-ttu-id="c175e-114">例 1: グループの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="c175e-114">Example 1: Change the name of a group</span></span>

```
PS C:\> Rename-LocalGroup -Name "SecurityGroup" -NewName "SecurityGroup04"
```

<span data-ttu-id="c175e-115">このコマンドは、SecurityGroup という名前のセキュリティグループの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="c175e-115">This command renames a security group named SecurityGroup.</span></span>

## <span data-ttu-id="c175e-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c175e-116">PARAMETERS</span></span>

### <span data-ttu-id="c175e-117">-InputObject</span><span class="sxs-lookup"><span data-stu-id="c175e-117">-InputObject</span></span>
<span data-ttu-id="c175e-118">このコマンドレットの名前を変更するセキュリティグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="c175e-118">Specifies the security group that this cmdlet renames.</span></span>
<span data-ttu-id="c175e-119">セキュリティグループを取得するには、Get-LocalGroup コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c175e-119">To obtain a security group, use the Get-LocalGroup cmdlet.</span></span>

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

### <span data-ttu-id="c175e-120">-Name</span><span class="sxs-lookup"><span data-stu-id="c175e-120">-Name</span></span>
<span data-ttu-id="c175e-121">このコマンドレットの名前を変更するセキュリティグループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c175e-121">Specifies the name of the security group that this cmdlet renames.</span></span>

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

### <span data-ttu-id="c175e-122">-NewName</span><span class="sxs-lookup"><span data-stu-id="c175e-122">-NewName</span></span>
<span data-ttu-id="c175e-123">セキュリティグループの新しい名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c175e-123">Specifies a new name for the security group.</span></span>

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

### <span data-ttu-id="c175e-124">-SID</span><span class="sxs-lookup"><span data-stu-id="c175e-124">-SID</span></span>
<span data-ttu-id="c175e-125">このコマンドレットの名前を変更するセキュリティグループのセキュリティ ID (SID) を指定します。</span><span class="sxs-lookup"><span data-stu-id="c175e-125">Specifies the security ID (SID) of a security group that this cmdlet renames.</span></span>

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

### <span data-ttu-id="c175e-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c175e-126">-Confirm</span></span>
<span data-ttu-id="c175e-127">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c175e-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c175e-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c175e-128">-WhatIf</span></span>
<span data-ttu-id="c175e-129">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="c175e-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c175e-130">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c175e-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c175e-131">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c175e-131">CommonParameters</span></span>
<span data-ttu-id="c175e-132">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c175e-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c175e-133">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c175e-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c175e-134">入力</span><span class="sxs-lookup"><span data-stu-id="c175e-134">INPUTS</span></span>

### <span data-ttu-id="c175e-135">SecurityAccountsManager、System.string、LocalGroup、SecurityIdentifier のように指定されています。</span><span class="sxs-lookup"><span data-stu-id="c175e-135">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="c175e-136">このコマンドレットには、セキュリティグループ、文字列、または SID をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="c175e-136">You can pipe a security group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="c175e-137">出力</span><span class="sxs-lookup"><span data-stu-id="c175e-137">OUTPUTS</span></span>

### <span data-ttu-id="c175e-138">なし</span><span class="sxs-lookup"><span data-stu-id="c175e-138">None</span></span>
<span data-ttu-id="c175e-139">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="c175e-139">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c175e-140">注</span><span class="sxs-lookup"><span data-stu-id="c175e-140">NOTES</span></span>

* <span data-ttu-id="c175e-141">**Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="c175e-141">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="c175e-142">考えられるソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c175e-142">The possible sources are as follows:</span></span>

- <span data-ttu-id="c175e-143">ローカル</span><span class="sxs-lookup"><span data-stu-id="c175e-143">Local</span></span>
- <span data-ttu-id="c175e-144">Active Directory</span><span class="sxs-lookup"><span data-stu-id="c175e-144">Active Directory</span></span>
- <span data-ttu-id="c175e-145">Azure Active Directory グループ</span><span class="sxs-lookup"><span data-stu-id="c175e-145">Azure Active Directory group</span></span>
- <span data-ttu-id="c175e-146">Microsoft アカウント</span><span class="sxs-lookup"><span data-stu-id="c175e-146">Microsoft Account</span></span>

<span data-ttu-id="c175e-147">**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c175e-147">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="c175e-148">以前のバージョンの場合、プロパティは空白になります。</span><span class="sxs-lookup"><span data-stu-id="c175e-148">For earlier  versions, the property is blank.</span></span>

## <span data-ttu-id="c175e-149">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c175e-149">RELATED LINKS</span></span>

[<span data-ttu-id="c175e-150">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="c175e-150">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="c175e-151">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="c175e-151">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="c175e-152">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="c175e-152">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="c175e-153">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="c175e-153">Set-LocalGroup</span></span>](Set-LocalGroup.md)
