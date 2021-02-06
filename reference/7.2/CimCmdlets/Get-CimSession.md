---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimsession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimSession
ms.openlocfilehash: 0e531b3cc072b7cc1efe0ef06fb741326bf3a72b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602181"
---
# <span data-ttu-id="8fe6a-102">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="8fe6a-102">Get-CimSession</span></span>

## <span data-ttu-id="8fe6a-103">概要</span><span class="sxs-lookup"><span data-stu-id="8fe6a-103">SYNOPSIS</span></span>
<span data-ttu-id="8fe6a-104">現在のセッションから CIM セッションオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-104">Gets the CIM session objects from the current session.</span></span>

## <span data-ttu-id="8fe6a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8fe6a-105">SYNTAX</span></span>

### <span data-ttu-id="8fe6a-106">ComputerNameSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="8fe6a-106">ComputerNameSet (Default)</span></span>

```
Get-CimSession [[-ComputerName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="8fe6a-107">SessionIdSet</span><span class="sxs-lookup"><span data-stu-id="8fe6a-107">SessionIdSet</span></span>

```
Get-CimSession [-Id] <UInt32[]> [<CommonParameters>]
```

### <span data-ttu-id="8fe6a-108">InstanceIdSet</span><span class="sxs-lookup"><span data-stu-id="8fe6a-108">InstanceIdSet</span></span>

```
Get-CimSession -InstanceId <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="8fe6a-109">NameSet</span><span class="sxs-lookup"><span data-stu-id="8fe6a-109">NameSet</span></span>

```
Get-CimSession -Name <String[]> [<CommonParameters>]
```

## <span data-ttu-id="8fe6a-110">Description</span><span class="sxs-lookup"><span data-stu-id="8fe6a-110">DESCRIPTION</span></span>

<span data-ttu-id="8fe6a-111">既定では、コマンドレットは、現在の PowerShell セッションで作成されたすべての CIM セッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-111">By default, the cmdlet gets all of the CIM sessions created in the current PowerShell session.</span></span> <span data-ttu-id="8fe6a-112">のパラメーターを使用して、 `Get-CimSession` 特定のコンピューターのセッションを取得したり、名前や他の識別子でセッションを識別したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-112">You can use the parameters of `Get-CimSession` to get the sessions that are for particular computers, or you can identify sessions by their names or other identifiers.</span></span> <span data-ttu-id="8fe6a-113">`Get-CimSession` は、他の PowerShell セッションで作成された、または他のコンピューターで作成された CIM セッションを取得しません。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-113">`Get-CimSession` does not get CIM sessions that were created in other PowerShell sessions or that were created on other computers.</span></span>

<span data-ttu-id="8fe6a-114">CIM セッションの詳細については、「 [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-114">For more information about CIM sessions, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

## <span data-ttu-id="8fe6a-115">例</span><span class="sxs-lookup"><span data-stu-id="8fe6a-115">EXAMPLES</span></span>

### <span data-ttu-id="8fe6a-116">例 1: 現在の PowerShell セッションから CIM セッションを取得する</span><span class="sxs-lookup"><span data-stu-id="8fe6a-116">Example 1: Get CIM sessions from the current PowerShell session</span></span>

<span data-ttu-id="8fe6a-117">この例では、 [CimSession](New-CimSession.md)を使用して cim セッションを作成し、を使用して cim セッションを取得し `Get-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-117">This example creates CIM sessions using [New-CimSession](New-CimSession.md), and then gets the CIM sessions using `Get-CimSession`.</span></span>

```powershell
New-CimSession -ComputerName Server01,Server02
Get-CimSession
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : d1413bc3-162a-4cb8-9aec-4d2c61253d59
ComputerName : Server01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### <span data-ttu-id="8fe6a-118">例 2: 特定のコンピューターへの CIM セッションを取得する</span><span class="sxs-lookup"><span data-stu-id="8fe6a-118">Example 2: Get the CIM sessions to a specific computer</span></span>

<span data-ttu-id="8fe6a-119">この例では、 **Server02** という名前のコンピューターに接続されている CIM セッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-119">This example gets the CIM sessions that are connected to the computer named **Server02**.</span></span>

```powershell
Get-CimSession -ComputerName Server02
```

```Output
Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### <span data-ttu-id="8fe6a-120">例 3: CIM セッションの一覧を取得し、一覧の書式を設定する</span><span class="sxs-lookup"><span data-stu-id="8fe6a-120">Example 3: Get a list of CIM sessions and then format the list</span></span>

<span data-ttu-id="8fe6a-121">この例では、現在の PowerShell セッションのすべての CIM セッションを取得し、 **ComputerName** プロパティと **InstanceID** プロパティのみを含むテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-121">This example gets all CIM sessions in the current PowerShell session and displays a table containing only the **ComputerName** and **InstanceID** properties.</span></span>

```powershell
Get-CimSession | Format-Table -Property ComputerName,InstanceId
```

```Output
ComputerName InstanceId
------------ ----------
Server01     d1413bc3-162a-4cb8-9aec-4d2c61253d59
Server02     c0095981-52c5-4e7f-a5bb-c4c680541710
```

### <span data-ttu-id="8fe6a-122">例 4: 特定の名前を持つすべての CIM セッションを取得する</span><span class="sxs-lookup"><span data-stu-id="8fe6a-122">Example 4: Get all the CIM sessions that have specific names</span></span>

<span data-ttu-id="8fe6a-123">この例では、名前が **serv** で始まるすべての CIM セッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-123">This example gets all CIM sessions that have names that begin with **serv**.</span></span>

```powershell
Get-CimSession -ComputerName Serv*
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : d1413bc-162a-4cb8-9aec-4d2c61253d59
ComputerName : Server01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

### <span data-ttu-id="8fe6a-124">例 5: 特定の CIM セッションを取得する</span><span class="sxs-lookup"><span data-stu-id="8fe6a-124">Example 5: Get a specific CIM session</span></span>

<span data-ttu-id="8fe6a-125">この例では、 **Id** が2の CIM セッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-125">This example gets the CIM session that has an **Id** of 2.</span></span>

```powershell
Get-CimSession -ID 2
```

```Output
Id           : 2
Name         : CimSession2
InstanceId   : c0095981-52c5-4e7f-a5bb-c4c680541710
ComputerName : Server02
Protocol     : WSMAN
```

## <span data-ttu-id="8fe6a-126">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8fe6a-126">PARAMETERS</span></span>

### <span data-ttu-id="8fe6a-127">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="8fe6a-127">-ComputerName</span></span>

<span data-ttu-id="8fe6a-128">CIM セッションの接続先となるコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-128">Specifies the name of the computer to get CIM sessions connected to.</span></span> <span data-ttu-id="8fe6a-129">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-129">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="8fe6a-130">-Id</span><span class="sxs-lookup"><span data-stu-id="8fe6a-130">-Id</span></span>

<span data-ttu-id="8fe6a-131">取得する CIM セッションの識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-131">Specifies the identifier of the CIM session to get.</span></span> <span data-ttu-id="8fe6a-132">複数の Id については、コンマを使用して Id を区切るか、範囲演算子 () を使用して `..` id の範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-132">For multiple IDs, use commas to separate the IDs or use the range operator (`..`) to specify a range of IDs.</span></span> <span data-ttu-id="8fe6a-133">**Id** は、現在の PowerShell セッション内の CIM セッションを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-133">An **Id** is an integer that uniquely identifies the CIM session within the current PowerShell session.</span></span>

<span data-ttu-id="8fe6a-134">範囲演算子の詳細については、「 [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-134">For more information about the range operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span></span>

```yaml
Type: System.UInt32[]
Parameter Sets: SessionIdSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8fe6a-135">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="8fe6a-135">-InstanceId</span></span>

<span data-ttu-id="8fe6a-136">取得する CIM セッションのインスタンス Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-136">Specifies the instance IDs of the CIM session to get.</span></span>

<span data-ttu-id="8fe6a-137">**InstanceId** は、CIM セッションを一意に識別するグローバル一意識別子 (GUID) です。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-137">**InstanceId** is a globally-unique identifier (GUID) that uniquely identifies a CIM session.</span></span> <span data-ttu-id="8fe6a-138">**インスタンス** id は、PowerShell で複数のセッションが実行されている場合でも一意です。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-138">The **InstanceId** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="8fe6a-139">**Instanceid** は、CIM セッションを表すオブジェクトの **instanceid** プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-139">The **InstanceId** is stored in the **InstanceId** property of the object that represents a CIM session.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="8fe6a-140">-Name</span><span class="sxs-lookup"><span data-stu-id="8fe6a-140">-Name</span></span>

<span data-ttu-id="8fe6a-141">指定されたフレンドリ名を含む1つ以上の CIM セッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-141">Gets one or more CIM sessions which contain the specified friendly names.</span></span> <span data-ttu-id="8fe6a-142">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-142">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="8fe6a-143">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8fe6a-143">CommonParameters</span></span>
<span data-ttu-id="8fe6a-144">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8fe6a-145">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fe6a-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8fe6a-146">入力</span><span class="sxs-lookup"><span data-stu-id="8fe6a-146">INPUTS</span></span>

### <span data-ttu-id="8fe6a-147">なし</span><span class="sxs-lookup"><span data-stu-id="8fe6a-147">None</span></span>

## <span data-ttu-id="8fe6a-148">出力</span><span class="sxs-lookup"><span data-stu-id="8fe6a-148">OUTPUTS</span></span>

### <span data-ttu-id="8fe6a-149">Microsoft.Management.Infrastructure.CimSession</span><span class="sxs-lookup"><span data-stu-id="8fe6a-149">Microsoft.Management.Infrastructure.CimSession</span></span>

## <span data-ttu-id="8fe6a-150">注</span><span class="sxs-lookup"><span data-stu-id="8fe6a-150">NOTES</span></span>

## <span data-ttu-id="8fe6a-151">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8fe6a-151">RELATED LINKS</span></span>

[<span data-ttu-id="8fe6a-152">Format-Table</span><span class="sxs-lookup"><span data-stu-id="8fe6a-152">Format-Table</span></span>](../microsoft.powershell.utility/format-table.md)

[<span data-ttu-id="8fe6a-153">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="8fe6a-153">New-CimSession</span></span>](New-CimSession.md)

[<span data-ttu-id="8fe6a-154">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="8fe6a-154">Remove-CimSession</span></span>](remove-cimsession.md)

[<span data-ttu-id="8fe6a-155">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="8fe6a-155">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)

