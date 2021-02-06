---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/remove-cimsession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-CimSession
ms.openlocfilehash: a3ff2132c531df1ab19bf7149a55ea0df4a787a8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600573"
---
# <span data-ttu-id="11087-102">Remove-CimSession</span><span class="sxs-lookup"><span data-stu-id="11087-102">Remove-CimSession</span></span>

## <span data-ttu-id="11087-103">概要</span><span class="sxs-lookup"><span data-stu-id="11087-103">SYNOPSIS</span></span>
<span data-ttu-id="11087-104">1つ以上の CIM セッションを削除します。</span><span class="sxs-lookup"><span data-stu-id="11087-104">Removes one or more CIM sessions.</span></span>

## <span data-ttu-id="11087-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="11087-105">SYNTAX</span></span>

### <span data-ttu-id="11087-106">CimSessionSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="11087-106">CimSessionSet (Default)</span></span>

```
Remove-CimSession [-CimSession] <CimSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="11087-107">ComputerNameSet</span><span class="sxs-lookup"><span data-stu-id="11087-107">ComputerNameSet</span></span>

```
Remove-CimSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="11087-108">SessionIdSet</span><span class="sxs-lookup"><span data-stu-id="11087-108">SessionIdSet</span></span>

```
Remove-CimSession [-Id] <UInt32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="11087-109">InstanceIdSet</span><span class="sxs-lookup"><span data-stu-id="11087-109">InstanceIdSet</span></span>

```
Remove-CimSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="11087-110">NameSet</span><span class="sxs-lookup"><span data-stu-id="11087-110">NameSet</span></span>

```
Remove-CimSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="11087-111">Description</span><span class="sxs-lookup"><span data-stu-id="11087-111">DESCRIPTION</span></span>

<span data-ttu-id="11087-112">`Remove-CimSession`コマンドレットでは、ローカルの PowerShell セッションから1つ以上の CIM セッションオブジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="11087-112">The `Remove-CimSession` cmdlet removes one or more CIM session objects from the local PowerShell session.</span></span>

## <span data-ttu-id="11087-113">例</span><span class="sxs-lookup"><span data-stu-id="11087-113">EXAMPLES</span></span>

### <span data-ttu-id="11087-114">例 1: すべての CIM セッションを削除する</span><span class="sxs-lookup"><span data-stu-id="11087-114">Example 1: Remove all the CIM sessions</span></span>

<span data-ttu-id="11087-115">この例では、 [CimSession](Get-CimSession.md) コマンドレットを使用してローカルコンピューター上で使用可能なすべての CIM セッションを取得し、を使用してそれらを削除し `Remove-CimSession` ます。</span><span class="sxs-lookup"><span data-stu-id="11087-115">This example retrieves all the available CIM sessions on the local computer using the [Get-CimSession](Get-CimSession.md) cmdlet, and then removes them using the `Remove-CimSession`.</span></span>

```powershell
Get-CimSession | Remove-CimSession
```

### <span data-ttu-id="11087-116">例 2: 特定の CIM セッションを削除する</span><span class="sxs-lookup"><span data-stu-id="11087-116">Example 2: Remove a specific CIM session</span></span>

<span data-ttu-id="11087-117">この例では、 **Id** 値が5の CIM セッションを削除します。</span><span class="sxs-lookup"><span data-stu-id="11087-117">This example removes the CIM session that has an **Id** value of 5.</span></span>

```powershell
Remove-CimSession -Id 5
```

### <span data-ttu-id="11087-118">例 3: WhatIf パラメーターを使用して削除する CIM セッションの一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="11087-118">Example 3: Show the list of CIM sessions to remove by using the WhatIf parameter</span></span>

<span data-ttu-id="11087-119">この例では、共通パラメーター **WhatIf** を使用して、削除を実行しないように指定していますが、出力されるのは、完了した場合だけです。</span><span class="sxs-lookup"><span data-stu-id="11087-119">This example uses the common parameter **WhatIf** to specify that the removal should not be done, but only output what would happen if it were done.</span></span>

```powershell
Remove-CimSession -Name a* -WhatIf
```

## <span data-ttu-id="11087-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="11087-120">PARAMETERS</span></span>

### <span data-ttu-id="11087-121">-CimSession</span><span class="sxs-lookup"><span data-stu-id="11087-121">-CimSession</span></span>

<span data-ttu-id="11087-122">閉じる CIM セッションのセッションオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="11087-122">Specifies the session objects of the CIM sessions to close.</span></span>

<span data-ttu-id="11087-123">CIM セッションを含む変数、またはやコマンドレットなどの CIM セッションを作成または取得するコマンドを入力し [`New-CimSession`](New-CimSession.md) [`Get-CimSession`](Get-CimSession.md) ます。</span><span class="sxs-lookup"><span data-stu-id="11087-123">Enter a variable that contains the CIM session, or a command that creates or gets the CIM session, such as the [`New-CimSession`](New-CimSession.md) or [`Get-CimSession`](Get-CimSession.md) cmdlets.</span></span>
<span data-ttu-id="11087-124">詳細については、「 [about_CimSessions](../Microsoft.PowerShell.Core/About/about_CimSession.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11087-124">For more information, see [about_CimSessions](../Microsoft.PowerShell.Core/About/about_CimSession.md).</span></span>

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

### <span data-ttu-id="11087-125">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="11087-125">-ComputerName</span></span>

<span data-ttu-id="11087-126">コンピューターの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="11087-126">Specifies an array of names of computers.</span></span> <span data-ttu-id="11087-127">指定したコンピューターに接続するセッションを削除します。</span><span class="sxs-lookup"><span data-stu-id="11087-127">Removes the sessions that connect to the specified computers.</span></span> <span data-ttu-id="11087-128">完全修飾ドメイン名 (FQDN) または NetBIOS 名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="11087-128">You can specify a fully qualified domain name (FQDN) or a NetBIOS name.</span></span>

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

### <span data-ttu-id="11087-129">-Id</span><span class="sxs-lookup"><span data-stu-id="11087-129">-Id</span></span>

<span data-ttu-id="11087-130">削除する CIM セッションの ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="11087-130">Specifies the ID of the CIM session to remove.</span></span> <span data-ttu-id="11087-131">1つ以上の Id をコンマで区切って指定するか、範囲演算子 () を使用して `..` id の範囲を指定します。</span><span class="sxs-lookup"><span data-stu-id="11087-131">Specify one or more IDs separated by commas, or use the range operator (`..`) to specify a range of IDs.</span></span> <span data-ttu-id="11087-132">**Id** は、現在の PowerShell セッションで CIM セッションを一意に識別する整数です。</span><span class="sxs-lookup"><span data-stu-id="11087-132">An **Id** is an integer that uniquely identifies the CIM session in the current PowerShell session.</span></span>

<span data-ttu-id="11087-133">範囲演算子の詳細については、「 [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11087-133">For more information about the range operator, see [about_Operators](../Microsoft.PowerShell.Core/About/about_Operators.md).</span></span>

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

### <span data-ttu-id="11087-134">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="11087-134">-InstanceId</span></span>

<span data-ttu-id="11087-135">削除する CIM セッションのインスタンス ID を指定します。</span><span class="sxs-lookup"><span data-stu-id="11087-135">Specifies the instance ID of the CIM session to remove.</span></span> <span data-ttu-id="11087-136">**InstanceId** は、CIM セッションを一意に識別するグローバル一意識別子 (GUID) です。</span><span class="sxs-lookup"><span data-stu-id="11087-136">**InstanceId** is a Globally Unique Identifier (GUID) that uniquely identifies a CIM session.</span></span> <span data-ttu-id="11087-137">**インスタンス** id は、PowerShell で複数のセッションが実行されている場合でも一意です。</span><span class="sxs-lookup"><span data-stu-id="11087-137">The **InstanceId** is unique, even when you have multiple sessions running in PowerShell.</span></span>

<span data-ttu-id="11087-138">**Instanceid** は、CIM セッションを表すオブジェクトの **instanceid** プロパティに格納されます。</span><span class="sxs-lookup"><span data-stu-id="11087-138">The **InstanceId** is stored in the **InstanceId** property of the object that represents a CIM session.</span></span>

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

### <span data-ttu-id="11087-139">-Name</span><span class="sxs-lookup"><span data-stu-id="11087-139">-Name</span></span>

<span data-ttu-id="11087-140">削除する CIM セッションのフレンドリ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="11087-140">Specifies the friendly name of the CIM session to remove.</span></span> <span data-ttu-id="11087-141">このパラメーターには、ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="11087-141">You can use wildcard characters with this parameter.</span></span>

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

### <span data-ttu-id="11087-142">-Confirm</span><span class="sxs-lookup"><span data-stu-id="11087-142">-Confirm</span></span>

<span data-ttu-id="11087-143">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11087-143">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="11087-144">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="11087-144">-WhatIf</span></span>

<span data-ttu-id="11087-145">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="11087-145">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="11087-146">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="11087-146">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="11087-147">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="11087-147">CommonParameters</span></span>

<span data-ttu-id="11087-148">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="11087-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="11087-149">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11087-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="11087-150">入力</span><span class="sxs-lookup"><span data-stu-id="11087-150">INPUTS</span></span>

### <span data-ttu-id="11087-151">なし</span><span class="sxs-lookup"><span data-stu-id="11087-151">None</span></span>

<span data-ttu-id="11087-152">このコマンドレットは、入力オブジェクトを受け入れません。</span><span class="sxs-lookup"><span data-stu-id="11087-152">This cmdlet accepts no input objects.</span></span>

## <span data-ttu-id="11087-153">出力</span><span class="sxs-lookup"><span data-stu-id="11087-153">OUTPUTS</span></span>

### <span data-ttu-id="11087-154">System.Object</span><span class="sxs-lookup"><span data-stu-id="11087-154">System.Object</span></span>

<span data-ttu-id="11087-155">このコマンドレットは、CIM セッション情報を格納するオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="11087-155">This cmdlet returns an object that contains CIM session information.</span></span>

## <span data-ttu-id="11087-156">注</span><span class="sxs-lookup"><span data-stu-id="11087-156">NOTES</span></span>

## <span data-ttu-id="11087-157">関連リンク</span><span class="sxs-lookup"><span data-stu-id="11087-157">RELATED LINKS</span></span>

[<span data-ttu-id="11087-158">Get-CimSession</span><span class="sxs-lookup"><span data-stu-id="11087-158">Get-CimSession</span></span>](Get-CimSession.md)

[<span data-ttu-id="11087-159">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="11087-159">New-CimSession</span></span>](New-CimSession.md)

[<span data-ttu-id="11087-160">about_CimSession</span><span class="sxs-lookup"><span data-stu-id="11087-160">about_CimSession</span></span>](../Microsoft.PowerShell.Core/About/about_CimSession.md)

