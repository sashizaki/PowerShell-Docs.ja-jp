---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/new-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-LocalGroup
ms.openlocfilehash: de66ad724d3cfee2d296d3b431618768a9cd38da
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214688"
---
# <span data-ttu-id="f7a83-103">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="f7a83-103">New-LocalGroup</span></span>

## <span data-ttu-id="f7a83-104">概要</span><span class="sxs-lookup"><span data-stu-id="f7a83-104">SYNOPSIS</span></span>
<span data-ttu-id="f7a83-105">ローカルセキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7a83-105">Creates a local security group.</span></span>

## <span data-ttu-id="f7a83-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f7a83-106">SYNTAX</span></span>

```
New-LocalGroup [-Description <String>] [-Name] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f7a83-107">Description</span><span class="sxs-lookup"><span data-stu-id="f7a83-107">DESCRIPTION</span></span>
<span data-ttu-id="f7a83-108">**LocalGroup** コマンドレットは、セキュリティアカウントマネージャーにローカルセキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7a83-108">The **New-LocalGroup** cmdlet creates a local security group in the Security Account Manager.</span></span>

> [!NOTE]
> <span data-ttu-id="f7a83-109">64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="f7a83-109">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="f7a83-110">例</span><span class="sxs-lookup"><span data-stu-id="f7a83-110">EXAMPLES</span></span>

### <span data-ttu-id="f7a83-111">例 1: セキュリティグループを作成する</span><span class="sxs-lookup"><span data-stu-id="f7a83-111">Example 1: Create a security group</span></span>

```
PS C:\> New-LocalGroup -Name "SecurityGroup04"
```

<span data-ttu-id="f7a83-112">このコマンドは、SecurityGroup04 という名前のグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7a83-112">This command creates a group named SecurityGroup04.</span></span>

## <span data-ttu-id="f7a83-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f7a83-113">PARAMETERS</span></span>

### <span data-ttu-id="f7a83-114">-Description</span><span class="sxs-lookup"><span data-stu-id="f7a83-114">-Description</span></span>
<span data-ttu-id="f7a83-115">グループのコメントを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7a83-115">Specifies a comment for the group.</span></span>
<span data-ttu-id="f7a83-116">最大長は48文字です。</span><span class="sxs-lookup"><span data-stu-id="f7a83-116">The maximum length is 48 characters.</span></span>

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

### <span data-ttu-id="f7a83-117">-Name</span><span class="sxs-lookup"><span data-stu-id="f7a83-117">-Name</span></span>
<span data-ttu-id="f7a83-118">グループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7a83-118">Specifies a name for the group.</span></span>
<span data-ttu-id="f7a83-119">最大長は 256 文字です。</span><span class="sxs-lookup"><span data-stu-id="f7a83-119">The maximum length is 256 characters.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f7a83-120">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f7a83-120">-Confirm</span></span>
<span data-ttu-id="f7a83-121">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f7a83-121">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f7a83-122">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f7a83-122">-WhatIf</span></span>
<span data-ttu-id="f7a83-123">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="f7a83-123">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="f7a83-124">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f7a83-124">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f7a83-125">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7a83-125">CommonParameters</span></span>
<span data-ttu-id="f7a83-126">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f7a83-126">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f7a83-127">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7a83-127">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f7a83-128">入力</span><span class="sxs-lookup"><span data-stu-id="f7a83-128">INPUTS</span></span>

### <span data-ttu-id="f7a83-129">System.String</span><span class="sxs-lookup"><span data-stu-id="f7a83-129">System.String</span></span>
<span data-ttu-id="f7a83-130">パイプを使用してこのコマンドレットに文字列を送ることができます。</span><span class="sxs-lookup"><span data-stu-id="f7a83-130">You can pipe a string to this cmdlet.</span></span>

## <span data-ttu-id="f7a83-131">出力</span><span class="sxs-lookup"><span data-stu-id="f7a83-131">OUTPUTS</span></span>

### <span data-ttu-id="f7a83-132">SecurityAccountsManager. LocalGroup (システムの管理)</span><span class="sxs-lookup"><span data-stu-id="f7a83-132">System.Management.Automation.SecurityAccountsManager.LocalGroup</span></span>
<span data-ttu-id="f7a83-133">このコマンドレットは、セキュリティグループを返します。</span><span class="sxs-lookup"><span data-stu-id="f7a83-133">This cmdlet returns a security group.</span></span>

## <span data-ttu-id="f7a83-134">注</span><span class="sxs-lookup"><span data-stu-id="f7a83-134">NOTES</span></span>

* <span data-ttu-id="f7a83-135">**Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="f7a83-135">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="f7a83-136">考えられるソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f7a83-136">The possible sources are as follows:</span></span>

- <span data-ttu-id="f7a83-137">ローカル</span><span class="sxs-lookup"><span data-stu-id="f7a83-137">Local</span></span>
- <span data-ttu-id="f7a83-138">Active Directory</span><span class="sxs-lookup"><span data-stu-id="f7a83-138">Active Directory</span></span>
- <span data-ttu-id="f7a83-139">Azure Active Directory グループ</span><span class="sxs-lookup"><span data-stu-id="f7a83-139">Azure Active Directory group</span></span>
- <span data-ttu-id="f7a83-140">Microsoft アカウント</span><span class="sxs-lookup"><span data-stu-id="f7a83-140">Microsoft Account</span></span>

<span data-ttu-id="f7a83-141">**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f7a83-141">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="f7a83-142">以前のバージョンの場合、プロパティは空白になります。</span><span class="sxs-lookup"><span data-stu-id="f7a83-142">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="f7a83-143">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f7a83-143">RELATED LINKS</span></span>

[<span data-ttu-id="f7a83-144">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="f7a83-144">Get-LocalGroup</span></span>](Get-LocalGroup.md)

[<span data-ttu-id="f7a83-145">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="f7a83-145">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="f7a83-146">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="f7a83-146">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)

[<span data-ttu-id="f7a83-147">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="f7a83-147">Set-LocalGroup</span></span>](Set-LocalGroup.md)
