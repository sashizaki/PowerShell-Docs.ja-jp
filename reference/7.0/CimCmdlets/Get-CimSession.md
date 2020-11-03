---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/get-cimsession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-CimSession
ms.openlocfilehash: dbbbb352d1b3af8a0f05d2805fb42b7bb3ed27d3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210739"
---
# <span data-ttu-id="a54d9-103">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="a54d9-103">Get-CimSession</span></span>

## <span data-ttu-id="a54d9-104">概要</span><span class="sxs-lookup"><span data-stu-id="a54d9-104">SYNOPSIS</span></span>
<span data-ttu-id="a54d9-105">現在のセッションから CIM セッションオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="a54d9-105">Gets the CIM session objects from the current session.</span></span>

## <span data-ttu-id="a54d9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a54d9-106">SYNTAX</span></span>

### <span data-ttu-id="a54d9-107">ComputerNameSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="a54d9-107">ComputerNameSet (Default)</span></span>

```
Get-CimSession [[-ComputerName] <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="a54d9-108">SessionIdSet</span><span class="sxs-lookup"><span data-stu-id="a54d9-108">SessionIdSet</span></span>

```
Get-CimSession [-Id] <UInt32[]> [<CommonParameters>]
```

### <span data-ttu-id="a54d9-109">InstanceIdSet</span><span class="sxs-lookup"><span data-stu-id="a54d9-109">InstanceIdSet</span></span>

```
Get-CimSession -InstanceId <Guid[]> [<CommonParameters>]
```

### <span data-ttu-id="a54d9-110">NameSet</span><span class="sxs-lookup"><span data-stu-id="a54d9-110">NameSet</span></span>

```
Get-CimSession -Name <String[]> [<CommonParameters>]
```

## <span data-ttu-id="a54d9-111">Description</span><span class="sxs-lookup"><span data-stu-id="a54d9-111">DESCRIPTION</span></span>

<span data-ttu-id="a54d9-112">既定では、コマンドレットは、現在の PowerShell セッションで作成されたすべての CIM セッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="a54d9-112">By default, the cmdlet gets all of the CIM sessions created in the current PowerShell session.</span></span> <span data-ttu-id="a54d9-113">のパラメーターを使用して、 `Get-CimSession` 特定のコンピューターのセッションを取得したり、名前や他の識別子でセッションを識別したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a54d9-113">You can use the parameters of `Get-CimSession` to get the sessions that are for particular computers, or you can identify sessions by their names or other identifiers.</span></span> <span data-ttu-id="a54d9-114">`Get-CimSession` は、他の PowerShell セッションで作成された、または他のコンピューターで作成された CIM セッションを取得しません。</span><span class="sxs-lookup"><span data-stu-id="a54d9-114">`Get-CimSession` does not get CIM sessions that were created in other PowerShell sessions or that were created on other computers.</span></span>

<span data-ttu-id="a54d9-115">CIM セッションの詳細については、「 [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a54d9-115">For more information about CIM sessions, see [about_CimSession](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

## <span data-ttu-id="a54d9-116">例</span><span class="sxs-lookup"><span data-stu-id="a54d9-116">EXAMPLES</span></span>

### <span data-ttu-id="a54d9-117">例 1: 現在の PowerShell セッションから CIM セッションを取得する</span><span class="sxs-lookup"><span data-stu-id="a54d9-117">Example 1: Get CIM sessions from the current PowerShell session</span></span>

<span data-ttu-id="a54d9-118">この例では、 [CimSession](New-CimSession.md)を使用して cim セッションを作成し、を使用して cim セッションを取得し `Get-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="a54d9-118">This example creates CIM sessions using [New-CimSession](New-CimSession.md), and then gets the CIM sessions using `Get-CimSession`.</span></span>

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

### <span data-ttu-id="a54d9-119">例 2: 特定のコンピューターへの CIM セッションを取得する</span><span class="sxs-lookup"><span data-stu-id="a54d9-119">Example 2: Get the CIM sessions to a specific computer</span></span>

<span data-ttu-id="a54d9-120">この例では、 **Server02** という名前のコンピューターに接続されている CIM セッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="a54d9-120">This example gets the CIM sessions that are connected to the computer named **Server02** .</span></span>

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

### <span data-ttu-id="a54d9-121">例 3: CIM セッションの一覧を取得し、一覧の書式を設定する</span><span class="sxs-lookup"><span data-stu-id="a54d9-121">Example 3: Get a list of CIM sessions and then format the list</span></span>

<span data-ttu-id="a54d9-122">この例では、現在の PowerShell セッションのすべての CIM セッションを取得し、 **ComputerName** プロパティと **InstanceID** プロパティのみを含むテーブルを表示します。</span><span class="sxs-lookup"><span data-stu-id="a54d9-122">This example gets all CIM sessions in the current PowerShell session and displays a table containing only the **ComputerName** and **InstanceID** properties.</span></span>

```powershell
Get-CimSession | Format-Table -Property ComputerName,InstanceId
```

```Output
ComputerName InstanceId
------------ ----------
Server01     d1413bc3-162a-4cb8-9aec-4d2c61253d59
Server02     c0095981-52c5-4e7f-a5bb-c4c680541710
```

### <span data-ttu-id="a54d9-123">例 4: 特定の名前を持つすべての CIM セッションを取得する</span><span class="sxs-lookup"><span data-stu-id="a54d9-123">Example 4: Get all the CIM sessions that have specific names</span></span>

<span data-ttu-id="a54d9-124">この例では、名前が **serv** で始まるすべての CIM セッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="a54d9-124">This example gets all CIM sessions that have names that begin with **serv** .</span></span>

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

### <span data-ttu-id="a54d9-125">例 5: 特定の CIM セッションを取得する</span><span class="sxs-lookup"><span data-stu-id="a54d9-125">Example 5: Get a specific CIM session</span></span>

<span data-ttu-id="a54d9-126">この例では、 **Id** が2の CIM セッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="a54d9-126">This example gets the CIM session that has an **Id** of 2.</span></span>

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

## <span data-ttu-id="a54d9-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a54d9-127">PARAMETERS</span></span>

### <span data-ttu-id="a54d9-128">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="a54d9-128">-ComputerName</span></span>

<span data-ttu-id="a54d9-129">CIM セッションの接続先となるコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a54d9-129">Specifies the name of the computer to get CIM sessions connected to.</span></span> <span data-ttu-id="a54d9-130">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a54d9-130">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a54d9-131">-Id</span><span class="sxs-lookup"><span data-stu-id="a54d9-131">-Id</span></span>

<span data-ttu-id="a54d9-132">取得する CIM セッションの識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="a54d9-132">Specifies the identifier of the CIM session to get.</span></span> <span data-ttu-id="a54d9-133">複数の Id については、コンマを使用して Id を区切るか、範囲演算子 () を使用して `..` id の範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="a54d9-133">For multiple IDs, use commas to separate the IDs or use the range operator (`..`) to specify a range of IDs.</span></span> <span data-ttu-id="a54d9-134">**Id** は、現在の PowerShell セッション内の CIM セッションを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="a54d9-134">An **Id** is an integer that uniquely identifies the CIM session within the current PowerShell session.</span></span>

<span data-ttu-id="a54d9-135">範囲演算子の詳細については、「 [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a54d9-135">For more information about the range operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span></span>

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

### <span data-ttu-id="a54d9-136">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="a54d9-136">-InstanceId</span></span>

<span data-ttu-id="a54d9-137">取得する CIM セッションのインスタンス Id を指定します。</span><span class="sxs-lookup"><span data-stu-id="a54d9-137">Specifies the instance IDs of the CIM session to get.</span></span>

<span data-ttu-id="a54d9-138">**InstanceId** は、CIM セッションを一意に識別するグローバル一意識別子 (GUID) です。</span><span class="sxs-lookup"><span data-stu-id="a54d9-138">**InstanceId** is a globally-unique identifier (GUID) that uniquely identifies a CIM session.</span></span> <span data-ttu-id="a54d9-139">**インスタンス** id は、PowerShell で複数のセッションが実行されている場合でも一意です。</span><span class="sxs-lookup"><span data-stu-id="a54d9-139">The **InstanceId** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="a54d9-140">**Instanceid** は、CIM セッションを表すオブジェクトの **instanceid** プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="a54d9-140">The **InstanceId** is stored in the **InstanceId** property of the object that represents a CIM session.</span></span>

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

### <span data-ttu-id="a54d9-141">-Name</span><span class="sxs-lookup"><span data-stu-id="a54d9-141">-Name</span></span>

<span data-ttu-id="a54d9-142">指定されたフレンドリ名を含む1つ以上の CIM セッションを取得します。</span><span class="sxs-lookup"><span data-stu-id="a54d9-142">Gets one or more CIM sessions which contain the specified friendly names.</span></span> <span data-ttu-id="a54d9-143">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a54d9-143">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a54d9-144">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a54d9-144">CommonParameters</span></span>
<span data-ttu-id="a54d9-145">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a54d9-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a54d9-146">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a54d9-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a54d9-147">入力</span><span class="sxs-lookup"><span data-stu-id="a54d9-147">INPUTS</span></span>

### <span data-ttu-id="a54d9-148">なし</span><span class="sxs-lookup"><span data-stu-id="a54d9-148">None</span></span>

## <span data-ttu-id="a54d9-149">出力</span><span class="sxs-lookup"><span data-stu-id="a54d9-149">OUTPUTS</span></span>

### <span data-ttu-id="a54d9-150">Microsoft.Management.Infrastructure.CimSession</span><span class="sxs-lookup"><span data-stu-id="a54d9-150">Microsoft.Management.Infrastructure.CimSession</span></span>

## <span data-ttu-id="a54d9-151">注</span><span class="sxs-lookup"><span data-stu-id="a54d9-151">NOTES</span></span>

## <span data-ttu-id="a54d9-152">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a54d9-152">RELATED LINKS</span></span>

[<span data-ttu-id="a54d9-153">Format-Table</span><span class="sxs-lookup"><span data-stu-id="a54d9-153">Format-Table</span></span>](../microsoft.powershell.utility/format-table.md)

[<span data-ttu-id="a54d9-154">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="a54d9-154">New-CimSession</span></span>](New-CimSession.md)

[<span data-ttu-id="a54d9-155">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="a54d9-155">Remove-CimSession</span></span>](remove-cimsession.md)

[<span data-ttu-id="a54d9-156">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="a54d9-156">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)