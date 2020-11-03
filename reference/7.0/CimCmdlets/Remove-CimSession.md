---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/remove-cimsession?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CimSession
ms.openlocfilehash: 729b0d1c860d29190ab4b87b818dd7b89018bfd7
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210051"
---
# <span data-ttu-id="c3f98-103">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="c3f98-103">Remove-CimSession</span></span>

## <span data-ttu-id="c3f98-104">概要</span><span class="sxs-lookup"><span data-stu-id="c3f98-104">SYNOPSIS</span></span>
<span data-ttu-id="c3f98-105">1つ以上の CIM セッションを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3f98-105">Removes one or more CIM sessions.</span></span>

## <span data-ttu-id="c3f98-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c3f98-106">SYNTAX</span></span>

### <span data-ttu-id="c3f98-107">CimSessionSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="c3f98-107">CimSessionSet (Default)</span></span>

```
Remove-CimSession [-CimSession] <CimSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c3f98-108">ComputerNameSet</span><span class="sxs-lookup"><span data-stu-id="c3f98-108">ComputerNameSet</span></span>

```
Remove-CimSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c3f98-109">SessionIdSet</span><span class="sxs-lookup"><span data-stu-id="c3f98-109">SessionIdSet</span></span>

```
Remove-CimSession [-Id] <UInt32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c3f98-110">InstanceIdSet</span><span class="sxs-lookup"><span data-stu-id="c3f98-110">InstanceIdSet</span></span>

```
Remove-CimSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c3f98-111">NameSet</span><span class="sxs-lookup"><span data-stu-id="c3f98-111">NameSet</span></span>

```
Remove-CimSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c3f98-112">Description</span><span class="sxs-lookup"><span data-stu-id="c3f98-112">DESCRIPTION</span></span>

<span data-ttu-id="c3f98-113">`Remove-CimSession`コマンドレットでは、ローカルの PowerShell セッションから1つ以上の CIM セッションオブジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3f98-113">The `Remove-CimSession` cmdlet removes one or more CIM session objects from the local PowerShell session.</span></span>

## <span data-ttu-id="c3f98-114">例</span><span class="sxs-lookup"><span data-stu-id="c3f98-114">EXAMPLES</span></span>

### <span data-ttu-id="c3f98-115">例 1: すべての CIM セッションを削除する</span><span class="sxs-lookup"><span data-stu-id="c3f98-115">Example 1: Remove all the CIM sessions</span></span>

<span data-ttu-id="c3f98-116">この例では、 [CimSession](Get-CimSession.md) コマンドレットを使用してローカルコンピューター上で使用可能なすべての CIM セッションを取得し、を使用してそれらを削除し `Remove-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="c3f98-116">This example retrieves all the available CIM sessions on the local computer using the [Get-CimSession](Get-CimSession.md) cmdlet, and then removes them using the `Remove-CimSession`.</span></span>

```powershell
Get-CimSession | Remove-CimSession
```

### <span data-ttu-id="c3f98-117">例 2: 特定の CIM セッションを削除する</span><span class="sxs-lookup"><span data-stu-id="c3f98-117">Example 2: Remove a specific CIM session</span></span>

<span data-ttu-id="c3f98-118">この例では、 **Id** 値が5の CIM セッションを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3f98-118">This example removes the CIM session that has an **Id** value of 5.</span></span>

```powershell
Remove-CimSession -Id 5
```

### <span data-ttu-id="c3f98-119">例 3: WhatIf パラメーターを使用して削除する CIM セッションの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="c3f98-119">Example 3: Show the list of CIM sessions to remove by using the WhatIf parameter</span></span>

<span data-ttu-id="c3f98-120">この例では、共通パラメーター **WhatIf** を使用して、削除を実行しないように指定していますが、出力されるのは、完了した場合だけです。</span><span class="sxs-lookup"><span data-stu-id="c3f98-120">This example uses the common parameter **WhatIf** to specify that the removal should not be done, but only output what would happen if it were done.</span></span>

```powershell
Remove-CimSession -Name a* -WhatIf
```

## <span data-ttu-id="c3f98-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c3f98-121">PARAMETERS</span></span>

### <span data-ttu-id="c3f98-122">-CimSession</span><span class="sxs-lookup"><span data-stu-id="c3f98-122">-CimSession</span></span>

<span data-ttu-id="c3f98-123">閉じる CIM セッションのセッションオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3f98-123">Specifies the session objects of the CIM sessions to close.</span></span>

<span data-ttu-id="c3f98-124">CIM セッションを含む変数、またはやコマンドレットなどの CIM セッションを作成または取得するコマンドを入力し [`New-CimSession`](New-CimSession.md) [`Get-CimSession`](Get-CimSession.md) ます。</span><span class="sxs-lookup"><span data-stu-id="c3f98-124">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the [`New-CimSession`](New-CimSession.md) or [`Get-CimSession`](Get-CimSession.md) cmdlets.</span></span>
<span data-ttu-id="c3f98-125">詳細については、「 [about_CimSessions](../Microsoft.PowerShell.Core/About/about_CimSession.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3f98-125">For more information, see [about_CimSessions](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c3f98-126">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="c3f98-126">-ComputerName</span></span>

<span data-ttu-id="c3f98-127">コンピューターの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3f98-127">Specifies an array of names of computers.</span></span> <span data-ttu-id="c3f98-128">指定したコンピューターに接続するセッションを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3f98-128">Removes the sessions that connect to the specified computers.</span></span> <span data-ttu-id="c3f98-129">完全修飾ドメイン名 (FQDN) または NetBIOS 名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c3f98-129">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="c3f98-130">-Id</span><span class="sxs-lookup"><span data-stu-id="c3f98-130">-Id</span></span>

<span data-ttu-id="c3f98-131">削除する CIM セッションの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3f98-131">Specifies the ID of the CIM session to remove.</span></span> <span data-ttu-id="c3f98-132">1つ以上の Id をコンマで区切って指定するか、範囲演算子 () を使用して `..` id の範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3f98-132">Specify one or more IDs separated by commas, or use the range operator (`..`) to specify a range of IDs.</span></span> <span data-ttu-id="c3f98-133">**Id** は、現在の PowerShell セッションで CIM セッションを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="c3f98-133">An **Id** is an integer that uniquely identifies the CIM session in the current PowerShell session.</span></span>

<span data-ttu-id="c3f98-134">範囲演算子の詳細については、「 [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3f98-134">For more information about the range operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span></span>

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

### <span data-ttu-id="c3f98-135">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="c3f98-135">-InstanceId</span></span>

<span data-ttu-id="c3f98-136">削除する CIM セッションのインスタンス ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3f98-136">Specifies the instance ID of the CIM session to remove.</span></span> <span data-ttu-id="c3f98-137">**InstanceId** は、CIM セッションを一意に識別するグローバル一意識別子 (GUID) です。</span><span class="sxs-lookup"><span data-stu-id="c3f98-137">**InstanceId** is a Globally Unique Identifier (GUID) that uniquely identifies a CIM session.</span></span> <span data-ttu-id="c3f98-138">**インスタンス** id は、PowerShell で複数のセッションが実行されている場合でも一意です。</span><span class="sxs-lookup"><span data-stu-id="c3f98-138">The **InstanceId** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="c3f98-139">**Instanceid** は、CIM セッションを表すオブジェクトの **instanceid** プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="c3f98-139">The **InstanceId** is stored in the **InstanceId** property of the object that represents a CIM session.</span></span>

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

### <span data-ttu-id="c3f98-140">-Name</span><span class="sxs-lookup"><span data-stu-id="c3f98-140">-Name</span></span>

<span data-ttu-id="c3f98-141">削除する CIM セッションのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3f98-141">Specifies the friendly name of the CIM session to remove.</span></span> <span data-ttu-id="c3f98-142">このパラメーターには、ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c3f98-142">You can use wildcard characters with this parameter.</span></span>

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

### <span data-ttu-id="c3f98-143">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c3f98-143">-Confirm</span></span>

<span data-ttu-id="c3f98-144">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3f98-144">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c3f98-145">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c3f98-145">-WhatIf</span></span>

<span data-ttu-id="c3f98-146">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="c3f98-146">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="c3f98-147">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c3f98-147">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c3f98-148">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c3f98-148">CommonParameters</span></span>

<span data-ttu-id="c3f98-149">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c3f98-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c3f98-150">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3f98-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c3f98-151">入力</span><span class="sxs-lookup"><span data-stu-id="c3f98-151">INPUTS</span></span>

### <span data-ttu-id="c3f98-152">なし</span><span class="sxs-lookup"><span data-stu-id="c3f98-152">None</span></span>

<span data-ttu-id="c3f98-153">このコマンドレットは、入力オブジェクトを受け入れません。</span><span class="sxs-lookup"><span data-stu-id="c3f98-153">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="c3f98-154">出力</span><span class="sxs-lookup"><span data-stu-id="c3f98-154">OUTPUTS</span></span>

### <span data-ttu-id="c3f98-155">System.Object</span><span class="sxs-lookup"><span data-stu-id="c3f98-155">System.Object</span></span>

<span data-ttu-id="c3f98-156">このコマンドレットは、CIM セッション情報を格納するオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c3f98-156">This cmdlet returns an object that contains CIM session information.</span></span>

## <span data-ttu-id="c3f98-157">注</span><span class="sxs-lookup"><span data-stu-id="c3f98-157">NOTES</span></span>

## <span data-ttu-id="c3f98-158">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c3f98-158">RELATED LINKS</span></span>

[<span data-ttu-id="c3f98-159">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="c3f98-159">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="c3f98-160">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="c3f98-160">New-CimSession</span></span>](New-CimSession.md)

[<span data-ttu-id="c3f98-161">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="c3f98-161">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)
