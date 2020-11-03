---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/undo-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Undo-Transaction
ms.openlocfilehash: 1acb06ea7b05a2127b04a22c4c51b92cd68056f2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214339"
---
# <span data-ttu-id="280ce-103">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="280ce-103">Undo-Transaction</span></span>

## <span data-ttu-id="280ce-104">概要</span><span class="sxs-lookup"><span data-stu-id="280ce-104">SYNOPSIS</span></span>
<span data-ttu-id="280ce-105">有効なトランザクションをロールバックします。</span><span class="sxs-lookup"><span data-stu-id="280ce-105">Rolls back the active transaction.</span></span>

## <span data-ttu-id="280ce-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="280ce-106">SYNTAX</span></span>

```
Undo-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="280ce-107">Description</span><span class="sxs-lookup"><span data-stu-id="280ce-107">DESCRIPTION</span></span>
<span data-ttu-id="280ce-108">**Undo transaction** コマンドレットは、アクティブなトランザクションをロールバックします。</span><span class="sxs-lookup"><span data-stu-id="280ce-108">The **Undo-Transaction** cmdlet rolls back the active transaction.</span></span>
<span data-ttu-id="280ce-109">トランザクションをロールバックすると、トランザクション内のコマンドによって行われた変更は破棄され、データは元の形式に復元されます。</span><span class="sxs-lookup"><span data-stu-id="280ce-109">When you roll back a transaction, the changes that were made by the commands in the transaction are discarded and the data is restored to its original form.</span></span>

<span data-ttu-id="280ce-110">トランザクションに複数のサブスクライバーが含まれている場合は、すべてのサブスクライバーについ **てトランザクション全体** がロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="280ce-110">If the transaction includes multiple subscribers, an **Undo-Transaction** command rolls back the whole transaction for all subscribers.</span></span>

<span data-ttu-id="280ce-111">既定では、トランザクション内のいずれかのコマンドでエラーが発生すると、トランザクションは自動的にロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="280ce-111">By default, transactions are rolled back automatically if any command in the transaction generates an error.</span></span>
<span data-ttu-id="280ce-112">ただし、別のロールバック設定を使用してトランザクションを開始できます。また、このコマンドレットを使用すると、アクティブなトランザクションをいつでもロールバックできます。</span><span class="sxs-lookup"><span data-stu-id="280ce-112">However, transactions can be started by using a different rollback preference and you can use this cmdlet to roll back the active transaction at any time.</span></span>

<span data-ttu-id="280ce-113">**Undo Transaction** コマンドレットは、Windows PowerShell のトランザクション機能をサポートする一連のコマンドレットの1つです。</span><span class="sxs-lookup"><span data-stu-id="280ce-113">The **Undo-Transaction** cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="280ce-114">詳細については、「about_Transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="280ce-114">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="280ce-115">例</span><span class="sxs-lookup"><span data-stu-id="280ce-115">EXAMPLES</span></span>

### <span data-ttu-id="280ce-116">例 1: 現在のトランザクションをロールバックする</span><span class="sxs-lookup"><span data-stu-id="280ce-116">Example 1: Roll back the current transaction</span></span>

```
PS C:\> Undo-Transaction
```

<span data-ttu-id="280ce-117">このコマンドは、現在のアクティブなトランザクションをロールバックします。</span><span class="sxs-lookup"><span data-stu-id="280ce-117">This command rolls back the current, active, transaction.</span></span>

### <span data-ttu-id="280ce-118">例 2: トランザクションを開始してロールバックする</span><span class="sxs-lookup"><span data-stu-id="280ce-118">Example 2: Start and roll back a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Undo-Transaction
```

<span data-ttu-id="280ce-119">この例では、トランザクションを開始してからロールバックします。</span><span class="sxs-lookup"><span data-stu-id="280ce-119">This example starts a transaction and then rolls it back.</span></span>
<span data-ttu-id="280ce-120">その結果、レジストリは変更されません。</span><span class="sxs-lookup"><span data-stu-id="280ce-120">As a result, no changes are made to the registry.</span></span>

### <span data-ttu-id="280ce-121">例 3: すべてのサブスクライバーのトランザクションをロールバックする</span><span class="sxs-lookup"><span data-stu-id="280ce-121">Example 3: Roll back a transaction for all subscribers</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> New-Item -Path "ContosoCompany" -UseTransaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                1                 Active

PS HKCU:\Software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                2                 Active

PS HKCU:\Software> Undo-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----
Error                0                 RolledBack
```

<span data-ttu-id="280ce-122">この例では、サブスクライバーがトランザクションをロールバックするときに、すべてのサブスクライバーに対してトランザクション全体がロールバックされることを示します。</span><span class="sxs-lookup"><span data-stu-id="280ce-122">This example demonstrates that when any subscriber rolls back a transaction, the whole transaction is rolled back for all subscribers.</span></span>

<span data-ttu-id="280ce-123">最初のコマンドは、場所を HKCU:\Software レジストリ キーに変更します。</span><span class="sxs-lookup"><span data-stu-id="280ce-123">The first command changes the location to the HKCU:\Software registry key.</span></span>

<span data-ttu-id="280ce-124">2 番目のコマンドは、トランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="280ce-124">The second command starts a transaction.</span></span>

<span data-ttu-id="280ce-125">3 番目のコマンドは、New-Item コマンドレットを使用して新しいレジストリ キーを作成します。</span><span class="sxs-lookup"><span data-stu-id="280ce-125">The third command uses the New-Item cmdlet to create a new registry key.</span></span>
<span data-ttu-id="280ce-126">このコマンドは、 *UseTransaction* パラメーターを使用して変更をトランザクションに含めます。</span><span class="sxs-lookup"><span data-stu-id="280ce-126">The command uses the *UseTransaction* parameter to include the change in the transaction.</span></span>

<span data-ttu-id="280ce-127">4 番目のコマンドは、Get-Transaction コマンドレットを使用して有効なトランザクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="280ce-127">The fourth command uses the Get-Transaction cmdlet to get the active transaction.</span></span>
<span data-ttu-id="280ce-128">ステータスが Active であり、サブスクライバーの数が 1 であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="280ce-128">Notice that the status is Active and the subscriber count is 1.</span></span>

<span data-ttu-id="280ce-129">5 番目のコマンドは、Start-Transaction コマンドを再度使用します。</span><span class="sxs-lookup"><span data-stu-id="280ce-129">The fifth command uses the Start-Transaction command again.</span></span>
<span data-ttu-id="280ce-130">通常、別のトランザクションが実行されている間にトランザクションを開始すると、メイントランザクションで使用されているスクリプトに独自の完全なトランザクションが含まれている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="280ce-130">Typically, starting a transaction while another transaction is in progress occurs when a script that is used by the main transaction includes its own complete transaction.</span></span>
<span data-ttu-id="280ce-131">この例は対話形式で実行されるため、段階的に調べることができます。</span><span class="sxs-lookup"><span data-stu-id="280ce-131">This example is performed interactively so that you can examine it in stages.</span></span>
<span data-ttu-id="280ce-132">別のトランザクションの実行中に **開始トランザクション** コマンドを実行すると、既存のトランザクションが新しいサブスクライバーとして結合され、サブスクライバー数が増加します。</span><span class="sxs-lookup"><span data-stu-id="280ce-132">When you run a **Start-Transaction** command while another transaction is in progress, the commands join the existing transaction as a new subscriber and the subscriber count is incremented.</span></span>

<span data-ttu-id="280ce-133">6番目のコマンドは、 **Get transaction** コマンドレットを使用して、アクティブなトランザクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="280ce-133">The sixth command uses the **Get-Transaction** cmdlet to get the active transaction.</span></span>
<span data-ttu-id="280ce-134">サブスクライバーの数が 2 になったことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="280ce-134">Notice that the subscriber count is now 2.</span></span>

<span data-ttu-id="280ce-135">7番目のコマンドは、トランザクションをロールバックするために、 **元に戻すトランザクション** を使用します。</span><span class="sxs-lookup"><span data-stu-id="280ce-135">The seventh command uses **Undo-Transaction** to roll back the transaction.</span></span>
<span data-ttu-id="280ce-136">このコマンドはオブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="280ce-136">This command does not return any objects.</span></span>

<span data-ttu-id="280ce-137">最後のコマンドは、アクティブな (この場合は最後にアクティブな) トランザクションを取得する **取得トランザクション** コマンドです。</span><span class="sxs-lookup"><span data-stu-id="280ce-137">The final command is a **Get-Transaction** command that gets the active, or in this case, the most recently active, transaction.</span></span>
<span data-ttu-id="280ce-138">トランザクションがロールバックされたことと、サブスクライバーの数が 0 になったことが結果に示されます。つまり、トランザクションがすべてのサブスクライバーに対してロールバックされました。</span><span class="sxs-lookup"><span data-stu-id="280ce-138">The results show that the transaction is rolled back, and that the subscriber count is 0, showing that the transaction was rolled back for all subscribers.</span></span>

## <span data-ttu-id="280ce-139">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="280ce-139">PARAMETERS</span></span>

### <span data-ttu-id="280ce-140">-Confirm</span><span class="sxs-lookup"><span data-stu-id="280ce-140">-Confirm</span></span>
<span data-ttu-id="280ce-141">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="280ce-141">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="280ce-142">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="280ce-142">-WhatIf</span></span>
<span data-ttu-id="280ce-143">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="280ce-143">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="280ce-144">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="280ce-144">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="280ce-145">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="280ce-145">CommonParameters</span></span>
<span data-ttu-id="280ce-146">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="280ce-146">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="280ce-147">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="280ce-147">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="280ce-148">入力</span><span class="sxs-lookup"><span data-stu-id="280ce-148">INPUTS</span></span>

### <span data-ttu-id="280ce-149">なし</span><span class="sxs-lookup"><span data-stu-id="280ce-149">None</span></span>
<span data-ttu-id="280ce-150">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="280ce-150">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="280ce-151">出力</span><span class="sxs-lookup"><span data-stu-id="280ce-151">OUTPUTS</span></span>

### <span data-ttu-id="280ce-152">なし</span><span class="sxs-lookup"><span data-stu-id="280ce-152">None</span></span>
<span data-ttu-id="280ce-153">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="280ce-153">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="280ce-154">注</span><span class="sxs-lookup"><span data-stu-id="280ce-154">NOTES</span></span>

* <span data-ttu-id="280ce-155">コミット済みのトランザクションはロールバックできません。</span><span class="sxs-lookup"><span data-stu-id="280ce-155">You cannot roll back a transaction that has been committed.</span></span>

  <span data-ttu-id="280ce-156">有効でないトランザクションはロールバックできません。</span><span class="sxs-lookup"><span data-stu-id="280ce-156">You cannot roll back any transaction other than the active transaction.</span></span>
<span data-ttu-id="280ce-157">独立した別のトランザクションをロールバックするには、有効なトランザクションを先にコミットするかロールバックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="280ce-157">To roll back a different, independent transaction, you must first commit or roll back the active transaction.</span></span>

  <span data-ttu-id="280ce-158">トランザクションをロールバックすると、そのトランザクションは終了します。</span><span class="sxs-lookup"><span data-stu-id="280ce-158">Rolling back the transaction ends the transaction.</span></span>
<span data-ttu-id="280ce-159">トランザクションを再度使用するには、トランザクションを新たに開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="280ce-159">To use a transaction again, you must start a new transaction.</span></span>

## <span data-ttu-id="280ce-160">関連リンク</span><span class="sxs-lookup"><span data-stu-id="280ce-160">RELATED LINKS</span></span>

[<span data-ttu-id="280ce-161">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="280ce-161">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="280ce-162">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="280ce-162">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="280ce-163">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="280ce-163">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="280ce-164">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="280ce-164">Use-Transaction</span></span>](Use-Transaction.md)
