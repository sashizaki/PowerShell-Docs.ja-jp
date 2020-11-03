---
external help file: Microsoft.Powershell.LocalAccounts.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.LocalAccounts
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.localaccounts/get-localgroup?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LocalGroup
ms.openlocfilehash: 2cd77c2766840527825b0ccf68abaac3c2ea6c16
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211904"
---
# <span data-ttu-id="0872f-103">Get-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="0872f-103">Get-LocalGroup</span></span>

## <span data-ttu-id="0872f-104">概要</span><span class="sxs-lookup"><span data-stu-id="0872f-104">SYNOPSIS</span></span>
<span data-ttu-id="0872f-105">ローカルセキュリティグループを取得します。</span><span class="sxs-lookup"><span data-stu-id="0872f-105">Gets the local security groups.</span></span>

## <span data-ttu-id="0872f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0872f-106">SYNTAX</span></span>

### <span data-ttu-id="0872f-107">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="0872f-107">Default (Default)</span></span>

```
Get-LocalGroup [[-Name] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="0872f-108">SecurityIdentifier</span><span class="sxs-lookup"><span data-stu-id="0872f-108">SecurityIdentifier</span></span>

```
Get-LocalGroup [[-SID] <SecurityIdentifier[]>] [<CommonParameters>]
```

## <span data-ttu-id="0872f-109">Description</span><span class="sxs-lookup"><span data-stu-id="0872f-109">DESCRIPTION</span></span>
<span data-ttu-id="0872f-110">**LocalGroup** コマンドレットは、セキュリティアカウントマネージャーのローカルセキュリティグループを取得します。</span><span class="sxs-lookup"><span data-stu-id="0872f-110">The **Get-LocalGroup** cmdlet gets local security groups in Security Account Manager.</span></span>
<span data-ttu-id="0872f-111">このコマンドレットは、作成する既定の組み込みグループとローカルセキュリティグループを取得します。</span><span class="sxs-lookup"><span data-stu-id="0872f-111">This cmdlet gets default built-in groups and local security groups that you create.</span></span>

> [!NOTE]
> <span data-ttu-id="0872f-112">64ビットシステムでは、32ビットの PowerShell では、Microsoft. PowerShell. LocalAccounts モジュールは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0872f-112">The Microsoft.PowerShell.LocalAccounts module is not available in 32-bit PowerShell on a 64-bit system.</span></span>

## <span data-ttu-id="0872f-113">例</span><span class="sxs-lookup"><span data-stu-id="0872f-113">EXAMPLES</span></span>

### <span data-ttu-id="0872f-114">例 1: 管理者グループを取得する</span><span class="sxs-lookup"><span data-stu-id="0872f-114">Example 1: Get the Administrators group</span></span>

```
PS C:\> Get-LocalGroup -Name "Administrators"
Name           Description
----           -----------
Administrators Administrators have complete and unrestricted access to the computer/domain
```

<span data-ttu-id="0872f-115">このコマンドは、ローカルの Administrators グループを取得します。</span><span class="sxs-lookup"><span data-stu-id="0872f-115">This command gets the local Administrators group.</span></span>
<span data-ttu-id="0872f-116">コマンドを実行すると、コンソールにグループのプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0872f-116">The command displays properties of the group in the console.</span></span>

## <span data-ttu-id="0872f-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0872f-117">PARAMETERS</span></span>

### <span data-ttu-id="0872f-118">-Name</span><span class="sxs-lookup"><span data-stu-id="0872f-118">-Name</span></span>
<span data-ttu-id="0872f-119">このコマンドレットが取得するセキュリティグループの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="0872f-119">Specifies an array of names of security groups that this cmdlet gets.</span></span>
<span data-ttu-id="0872f-120">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0872f-120">You can use the wildcard character.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="0872f-121">-SID</span><span class="sxs-lookup"><span data-stu-id="0872f-121">-SID</span></span>
<span data-ttu-id="0872f-122">このコマンドレットが取得するセキュリティグループのセキュリティ Id (Sid) の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="0872f-122">Specifies an array of security IDs (SIDs) of security groups that this cmdlet gets.</span></span>

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

### <span data-ttu-id="0872f-123">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="0872f-123">CommonParameters</span></span>
<span data-ttu-id="0872f-124">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="0872f-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0872f-125">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0872f-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0872f-126">入力</span><span class="sxs-lookup"><span data-stu-id="0872f-126">INPUTS</span></span>

### <span data-ttu-id="0872f-127">System.string, SecurityIdentifier (システムのセキュリティ)</span><span class="sxs-lookup"><span data-stu-id="0872f-127">System.String, System.Security.Principal.SecurityIdentifier</span></span>
<span data-ttu-id="0872f-128">このコマンドレットには、文字列または SID をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="0872f-128">You can pipe a string or a SID to this cmdlet.</span></span>

## <span data-ttu-id="0872f-129">出力</span><span class="sxs-lookup"><span data-stu-id="0872f-129">OUTPUTS</span></span>

### <span data-ttu-id="0872f-130">SecurityAccountsManager. LocalGroup (システムの管理)</span><span class="sxs-lookup"><span data-stu-id="0872f-130">System.Management.Automation.SecurityAccountsManager.LocalGroup</span></span>
<span data-ttu-id="0872f-131">このコマンドレットは、ローカルグループを返します。</span><span class="sxs-lookup"><span data-stu-id="0872f-131">This cmdlet returns a local group.</span></span>

## <span data-ttu-id="0872f-132">注</span><span class="sxs-lookup"><span data-stu-id="0872f-132">NOTES</span></span>

* <span data-ttu-id="0872f-133">**Principalsource** プロパティは、オブジェクトのソースを記述する **LocalUser** 、 **LocalGroup** 、および **localprincipal** オブジェクトのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="0872f-133">The **PrincipalSource** property is a property on **LocalUser** , **LocalGroup** , and **LocalPrincipal** objects that describes the source of the object.</span></span> <span data-ttu-id="0872f-134">考えられるソースは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0872f-134">The possible sources are as follows:</span></span>

- <span data-ttu-id="0872f-135">ローカル</span><span class="sxs-lookup"><span data-stu-id="0872f-135">Local</span></span>
- <span data-ttu-id="0872f-136">Active Directory</span><span class="sxs-lookup"><span data-stu-id="0872f-136">Active Directory</span></span>
- <span data-ttu-id="0872f-137">Azure Active Directory グループ</span><span class="sxs-lookup"><span data-stu-id="0872f-137">Azure Active Directory group</span></span>
- <span data-ttu-id="0872f-138">Microsoft アカウント</span><span class="sxs-lookup"><span data-stu-id="0872f-138">Microsoft Account</span></span>

<span data-ttu-id="0872f-139">**Principalsource** は、windows 10、windows Server 2016、およびそれ以降のバージョンの windows オペレーティングシステムでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0872f-139">**PrincipalSource** is supported only by Windows 10, Windows Server 2016, and later versions of the Windows operating system.</span></span> <span data-ttu-id="0872f-140">以前のバージョンの場合、プロパティは空白になります。</span><span class="sxs-lookup"><span data-stu-id="0872f-140">For earlier versions, the property is blank.</span></span>

## <span data-ttu-id="0872f-141">関連リンク</span><span class="sxs-lookup"><span data-stu-id="0872f-141">RELATED LINKS</span></span>

[<span data-ttu-id="0872f-142">New-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="0872f-142">New-LocalGroup</span></span>](New-LocalGroup.md)

[<span data-ttu-id="0872f-143">Remove-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="0872f-143">Remove-LocalGroup</span></span>](Remove-LocalGroup.md)

[<span data-ttu-id="0872f-144">Rename-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="0872f-144">Rename-LocalGroup</span></span>](Rename-LocalGroup.md)

[<span data-ttu-id="0872f-145">Set-LocalGroup</span><span class="sxs-lookup"><span data-stu-id="0872f-145">Set-LocalGroup</span></span>](Set-LocalGroup.md)
