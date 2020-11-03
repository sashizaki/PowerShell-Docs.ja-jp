---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroupmember?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroupMember
ms.openlocfilehash: 200368c5d13bd027302ad824533e6c187906ed0f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211891"
---
# <span data-ttu-id="5411d-103">Get-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="5411d-103">Get-LocalGroupMember</span></span>

## <span data-ttu-id="5411d-104">概要</span><span class="sxs-lookup"><span data-stu-id="5411d-104">SYNOPSIS</span></span>
<span data-ttu-id="5411d-105">ローカルグループからメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="5411d-105">Gets members from a local group.</span></span>

## <span data-ttu-id="5411d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5411d-106">SYNTAX</span></span>

### <span data-ttu-id="5411d-107">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="5411d-107">Default (Default)</span></span>

```
Get-LocalGroupMember [[-Member] <String>] [-Name] <String> [<CommonParameters>]
```

### <span data-ttu-id="5411d-108">グループ</span><span class="sxs-lookup"><span data-stu-id="5411d-108">Group</span></span>

```
Get-LocalGroupMember [-Group] <LocalGroup> [[-Member] <String>] [<CommonParameters>]
```

### <span data-ttu-id="5411d-109">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="5411d-109">SecurityIdentifier</span></span>

```
Get-LocalGroupMember [[-Member] <String>] [-SID] <SecurityIdentifier> [<CommonParameters>]
```

## <span data-ttu-id="5411d-110">Description</span><span class="sxs-lookup"><span data-stu-id="5411d-110">DESCRIPTION</span></span>
<span data-ttu-id="5411d-111">**LocalGroupMember** コマンドレットは、ローカルグループからメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="5411d-111">The **Get-LocalGroupMember** cmdlet gets members from a local group.</span></span>

> [!NOTE]
> <span data-ttu-id="5411d-112">64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5411d-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="5411d-113">例</span><span class="sxs-lookup"><span data-stu-id="5411d-113">EXAMPLES</span></span>

### <span data-ttu-id="5411d-114">例 1: Administrators グループのすべてのメンバーを取得する</span><span class="sxs-lookup"><span data-stu-id="5411d-114">Example 1: Get all members of the Administrators group</span></span>

```
PS C:\> Get-LocalGroupMember -Group "Administrators"
ObjectClass Name                    PrincipalSource
----------- ----                    ---------------
User        CONTOSOPC\Administrator Local
User        CONTOSOPC\LocalAdmin    Local
```

<span data-ttu-id="5411d-115">このコマンドは、ローカルの Administrators グループのすべてのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="5411d-115">This command gets all the members of the local Administrators group.</span></span>

## <span data-ttu-id="5411d-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5411d-116">PARAMETERS</span></span>

### <span data-ttu-id="5411d-117">-Group</span><span class="sxs-lookup"><span data-stu-id="5411d-117">-Group</span></span>
<span data-ttu-id="5411d-118">このコマンドレットがメンバーを取得するセキュリティグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="5411d-118">Specifies the security group from which this cmdlet gets members.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.LocalGroup
Parameter Sets: Group
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5411d-119">-メンバー</span><span class="sxs-lookup"><span data-stu-id="5411d-119">-Member</span></span>
<span data-ttu-id="5411d-120">このコマンドレットがセキュリティグループから取得するユーザーまたはグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="5411d-120">Specifies a user or group that this cmdlet gets from a security group.</span></span>
<span data-ttu-id="5411d-121">名前またはセキュリティ ID (SID) を使用して、ユーザーまたはグループを指定できます。</span><span class="sxs-lookup"><span data-stu-id="5411d-121">You can specify users or groups by name or security ID (SID).</span></span>
<span data-ttu-id="5411d-122">S-R-s-s で SID 文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="5411d-122">Specify SID strings in S-R-I-S-S .</span></span>
<span data-ttu-id="5411d-123">.</span><span class="sxs-lookup"><span data-stu-id="5411d-123">.</span></span> <span data-ttu-id="5411d-124">.</span><span class="sxs-lookup"><span data-stu-id="5411d-124">.</span></span>
<span data-ttu-id="5411d-125">(</span><span class="sxs-lookup"><span data-stu-id="5411d-125">format.</span></span>
<span data-ttu-id="5411d-126">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5411d-126">You can use wildcard characters.</span></span>
<span data-ttu-id="5411d-127">このパラメーターを指定しない場合、コマンドレットはグループのすべてのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="5411d-127">If you do not specify this parameter, the cmdlet gets all members of the group.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5411d-128">-Name</span><span class="sxs-lookup"><span data-stu-id="5411d-128">-Name</span></span>
<span data-ttu-id="5411d-129">このコマンドレットがメンバーを取得するセキュリティグループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5411d-129">Specifies the name of the security group from which this cmdlet gets members.</span></span>

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

### <span data-ttu-id="5411d-130">-SID</span><span class="sxs-lookup"><span data-stu-id="5411d-130">-SID</span></span>
<span data-ttu-id="5411d-131">このコマンドレットがメンバーを取得するセキュリティグループのセキュリティ ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="5411d-131">Specifies the security ID of the security group from which this cmdlet gets members.</span></span>

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

### <span data-ttu-id="5411d-132">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5411d-132">CommonParameters</span></span>
<span data-ttu-id="5411d-133">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5411d-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5411d-134">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5411d-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5411d-135">入力</span><span class="sxs-lookup"><span data-stu-id="5411d-135">INPUTS</span></span>

### <span data-ttu-id="5411d-136">SecurityAccountsManager、System.string、LocalGroup、SecurityIdentifier のように指定されています。</span><span class="sxs-lookup"><span data-stu-id="5411d-136">System.Management.Automation.SecurityAccountsManager.LocalGroup, System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="5411d-137">このコマンドレットには、ローカルグループ、文字列、または SID をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="5411d-137">You can pipe a local group, a string, or a SID to this cmdlet.</span></span>

## <span data-ttu-id="5411d-138">出力</span><span class="sxs-lookup"><span data-stu-id="5411d-138">OUTPUTS</span></span>

### <span data-ttu-id="5411d-139">SecurityAccountsManager. LocalPrincipal</span><span class="sxs-lookup"><span data-stu-id="5411d-139">Microsoft.SecurityAccountsManager.LocalPrincipal</span></span>
<span data-ttu-id="5411d-140">このコマンドレットは、ローカルプリンシパルを返します。</span><span class="sxs-lookup"><span data-stu-id="5411d-140">This cmdlet returns local principals.</span></span>

## <span data-ttu-id="5411d-141">注</span><span class="sxs-lookup"><span data-stu-id="5411d-141">NOTES</span></span>

* <span data-ttu-id="5411d-142">**Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="5411d-142">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="5411d-143">考えられるソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5411d-143">The possible sources are as follows:</span></span>

- <span data-ttu-id="5411d-144">ローカル</span><span class="sxs-lookup"><span data-stu-id="5411d-144">Local</span></span>
- <span data-ttu-id="5411d-145">Active Directory</span><span class="sxs-lookup"><span data-stu-id="5411d-145">Active Directory</span></span>
- <span data-ttu-id="5411d-146">Azure Active Directory グループ</span><span class="sxs-lookup"><span data-stu-id="5411d-146">Azure Active Directory group</span></span>
- <span data-ttu-id="5411d-147">Microsoft アカウント</span><span class="sxs-lookup"><span data-stu-id="5411d-147">Microsoft Account</span></span>

<span data-ttu-id="5411d-148">**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5411d-148">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="5411d-149">以前のバージョンの場合、プロパティは空白になります。</span><span class="sxs-lookup"><span data-stu-id="5411d-149">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="5411d-150">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5411d-150">RELATED LINKS</span></span>

[<span data-ttu-id="5411d-151">Add-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="5411d-151">Add-LocalGroupMember</span></span>](Add-LocalGroupMember.md)

[<span data-ttu-id="5411d-152">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="5411d-152">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="5411d-153">Remove-LocalGroupMember</span><span class="sxs-lookup"><span data-stu-id="5411d-153">Remove-LocalGroupMember</span></span>](Remove-LocalGroupMember.md)
