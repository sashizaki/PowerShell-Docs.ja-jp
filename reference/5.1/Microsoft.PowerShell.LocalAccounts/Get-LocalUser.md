---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 02/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localuser?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalUser
ms.openlocfilehash: 34210145bcddc8d9420552d637a6cd6e5f8e61cc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211888"
---
# <span data-ttu-id="60e67-103">Get-LocalUser</span><span class="sxs-lookup"><span data-stu-id="60e67-103">Get-LocalUser</span></span>

## <span data-ttu-id="60e67-104">概要</span><span class="sxs-lookup"><span data-stu-id="60e67-104">SYNOPSIS</span></span>
<span data-ttu-id="60e67-105">ローカルユーザーアカウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="60e67-105">Gets local user accounts.</span></span>

## <span data-ttu-id="60e67-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="60e67-106">SYNTAX</span></span>

### <span data-ttu-id="60e67-107">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="60e67-107">Default (Default)</span></span>

```
Get-LocalUser [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="60e67-108">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="60e67-108">SecurityIdentifier</span></span>

```
Get-LocalUser [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## <span data-ttu-id="60e67-109">Description</span><span class="sxs-lookup"><span data-stu-id="60e67-109">DESCRIPTION</span></span>

<span data-ttu-id="60e67-110">コマンドレットでは、 `Get-LocalUser` ローカルユーザーアカウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="60e67-110">The `Get-LocalUser` cmdlet gets local user accounts.</span></span> <span data-ttu-id="60e67-111">このコマンドレットは、既定の組み込みユーザーアカウント、作成したローカルユーザーアカウント、および Microsoft アカウントに接続したローカルアカウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="60e67-111">This cmdlet gets default built-in user accounts, local user accounts that you created, and local accounts that you connected to Microsoft accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="60e67-112">64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="60e67-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="60e67-113">例</span><span class="sxs-lookup"><span data-stu-id="60e67-113">EXAMPLES</span></span>

### <span data-ttu-id="60e67-114">例 1: 名前を使用してアカウントを取得する</span><span class="sxs-lookup"><span data-stu-id="60e67-114">Example 1: Get an account by using its name</span></span>

<span data-ttu-id="60e67-115">この例では、AdminContoso02 という名前のユーザーアカウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="60e67-115">This example gets a user account named AdminContoso02.</span></span>

```powershell
Get-LocalUser -Name "AdminContoso02"
```

```Output
Name             Enabled Description
----             ------- -----------
AdminContoso02   True    Description of this account.
```

### <span data-ttu-id="60e67-116">例 2: Microsoft アカウントに接続されているアカウントを取得する</span><span class="sxs-lookup"><span data-stu-id="60e67-116">Example 2: Get an account that is connected to a Microsoft account</span></span>

<span data-ttu-id="60e67-117">この例では、Microsoft アカウントに接続されているユーザーアカウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="60e67-117">This example gets a user account that is connected to a Microsoft account.</span></span> <span data-ttu-id="60e67-118">この例では、Outlook.com のアカウントのユーザー名にプレースホルダー値を使用します。</span><span class="sxs-lookup"><span data-stu-id="60e67-118">This example uses a placeholder value for the username of an account at Outlook.com.</span></span>

```powershell
Get-LocalUser -Name "MicrosoftAccount\username@Outlook.com"
```

```Output
Name                                    Enabled  Description
----                                    -------  -----------
MicrosoftAccount\username@outlook.com  True     Description of this account.
```

### <span data-ttu-id="60e67-119">例 3: Microsoft アカウントに接続されているアカウントを取得する</span><span class="sxs-lookup"><span data-stu-id="60e67-119">Example 3: Get an account that is connected to a Microsoft account</span></span>

<span data-ttu-id="60e67-120">この例では、指定された SID を持つローカルユーザーアカウントを取得します。</span><span class="sxs-lookup"><span data-stu-id="60e67-120">This example gets a local user account that has the specified SID.</span></span>

```powershell
Get-LocalUser -SID S-1-5-21-9526073513-1762370368-3942940353-500
```

```Output
Name          Enabled Description
----          ------- -----------
Administrator True    Built-in account for administering the computer/domain
```

## <span data-ttu-id="60e67-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="60e67-121">PARAMETERS</span></span>

### <span data-ttu-id="60e67-122">-Name</span><span class="sxs-lookup"><span data-stu-id="60e67-122">-Name</span></span>

<span data-ttu-id="60e67-123">このコマンドレットが取得するユーザーアカウントの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="60e67-123">Specifies an array of names of user accounts that this cmdlet gets.</span></span> <span data-ttu-id="60e67-124">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="60e67-124">You can use the wildcard character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="60e67-125">-SID</span><span class="sxs-lookup"><span data-stu-id="60e67-125">-SID</span></span>

<span data-ttu-id="60e67-126">このコマンドレットが取得するユーザーアカウントのセキュリティ Id (Sid) の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="60e67-126">Specifies an array of security IDs (SIDs) of user accounts that this cmdlet gets.</span></span>

```yaml
Type: System.Security.Principal.SecurityIdentifier[]
Parameter Sets: SecurityIdentifier
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="60e67-127">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="60e67-127">CommonParameters</span></span>

<span data-ttu-id="60e67-128">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="60e67-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="60e67-129">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60e67-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="60e67-130">入力</span><span class="sxs-lookup"><span data-stu-id="60e67-130">INPUTS</span></span>

### <span data-ttu-id="60e67-131">System.string, SecurityIdentifier (システムのセキュリティ)</span><span class="sxs-lookup"><span data-stu-id="60e67-131">System.String, System.Security.Principal.SecurityIdentifier</span></span>

<span data-ttu-id="60e67-132">このコマンドレットには、文字列または SID をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="60e67-132">You can pipe a string or SID to this cmdlet.</span></span>

## <span data-ttu-id="60e67-133">出力</span><span class="sxs-lookup"><span data-stu-id="60e67-133">OUTPUTS</span></span>

### <span data-ttu-id="60e67-134">SecurityAccountsManager. LocalUser [] です。</span><span class="sxs-lookup"><span data-stu-id="60e67-134">System.Management.Automation.SecurityAccountsManager.LocalUser[]</span></span>

<span data-ttu-id="60e67-135">このコマンドレットは、ローカルユーザーアカウントを返します。</span><span class="sxs-lookup"><span data-stu-id="60e67-135">This cmdlet returns local user accounts.</span></span>

## <span data-ttu-id="60e67-136">注</span><span class="sxs-lookup"><span data-stu-id="60e67-136">NOTES</span></span>

<span data-ttu-id="60e67-137">**LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトの **principalsource** プロパティは、オブジェクトのソースを記述します。</span><span class="sxs-lookup"><span data-stu-id="60e67-137">The **PrincipalSource** property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects describes the source of the object.</span></span> <span data-ttu-id="60e67-138">考えられるソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="60e67-138">The possible sources are as follows:</span></span>

- <span data-ttu-id="60e67-139">ローカル</span><span class="sxs-lookup"><span data-stu-id="60e67-139">Local</span></span>
- <span data-ttu-id="60e67-140">Active Directory</span><span class="sxs-lookup"><span data-stu-id="60e67-140">Active Directory</span></span>
- <span data-ttu-id="60e67-141">Azure Active Directory グループ</span><span class="sxs-lookup"><span data-stu-id="60e67-141">Azure Active Directory group</span></span>
- <span data-ttu-id="60e67-142">Microsoft アカウント</span><span class="sxs-lookup"><span data-stu-id="60e67-142">Microsoft Account</span></span>

<span data-ttu-id="60e67-143">**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="60e67-143">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="60e67-144">以前のバージョンの場合、プロパティは空白になります。</span><span class="sxs-lookup"><span data-stu-id="60e67-144">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="60e67-145">関連リンク</span><span class="sxs-lookup"><span data-stu-id="60e67-145">RELATED LINKS</span></span>

[<span data-ttu-id="60e67-146">Disable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="60e67-146">Disable-LocalUser</span></span>](Disable-LocalUser.md)

[<span data-ttu-id="60e67-147">Enable-LocalUser</span><span class="sxs-lookup"><span data-stu-id="60e67-147">Enable-LocalUser</span></span>](Enable-LocalUser.md)

[<span data-ttu-id="60e67-148">New-LocalUser</span><span class="sxs-lookup"><span data-stu-id="60e67-148">New-LocalUser</span></span>](New-LocalUser.md)

[<span data-ttu-id="60e67-149">Remove-LocalUser</span><span class="sxs-lookup"><span data-stu-id="60e67-149">Remove-LocalUser</span></span>](Remove-LocalUser.md)

[<span data-ttu-id="60e67-150">Rename-LocalUser</span><span class="sxs-lookup"><span data-stu-id="60e67-150">Rename-LocalUser</span></span>](Rename-LocalUser.md)

[<span data-ttu-id="60e67-151">Set-LocalUser</span><span class="sxs-lookup"><span data-stu-id="60e67-151">Set-LocalUser</span></span>](Set-LocalUser.md)
