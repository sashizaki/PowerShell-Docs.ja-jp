---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/complete-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Complete-Transaction
ms.openlocfilehash: 20fbdd86aab07dda065492eff2da4f358fb2ffca
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215555"
---
# <span data-ttu-id="11b33-103">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="11b33-103">Complete-Transaction</span></span>

## <span data-ttu-id="11b33-104">概要</span><span class="sxs-lookup"><span data-stu-id="11b33-104">SYNOPSIS</span></span>
<span data-ttu-id="11b33-105">有効なトランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="11b33-105">Commits the active transaction.</span></span>

## <span data-ttu-id="11b33-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="11b33-106">SYNTAX</span></span>

```
Complete-Transaction [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="11b33-107">Description</span><span class="sxs-lookup"><span data-stu-id="11b33-107">DESCRIPTION</span></span>
<span data-ttu-id="11b33-108">**Complete transaction** コマンドレットは、アクティブなトランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="11b33-108">The **Complete-Transaction** cmdlet commits an active transaction.</span></span>
<span data-ttu-id="11b33-109">トランザクションをコミットすると、トランザクション内のコマンドの最終処理が実行され、コマンドの対象のデータが変更されます。</span><span class="sxs-lookup"><span data-stu-id="11b33-109">When you commit a transaction, the commands in the transaction are finalized and the data affected by the commands is changed.</span></span>

<span data-ttu-id="11b33-110">トランザクションに複数のサブスクライバーが含まれている場合、トランザクションをコミットするには、すべての Start-Transaction コマンドに対して1つの **トランザクション完了** コマンドを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11b33-110">If the transaction includes multiple subscribers, to commit the transaction, you must enter one **Complete-Transaction** command for every Start-Transaction command.</span></span>

<span data-ttu-id="11b33-111">**Complete Transaction** コマンドレットは、Windows PowerShell のトランザクション機能をサポートする一連のコマンドレットの1つです。</span><span class="sxs-lookup"><span data-stu-id="11b33-111">The **Complete-Transaction** cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="11b33-112">詳細については、「about_Transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11b33-112">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="11b33-113">例</span><span class="sxs-lookup"><span data-stu-id="11b33-113">EXAMPLES</span></span>

### <span data-ttu-id="11b33-114">例 1: トランザクションをコミットする</span><span class="sxs-lookup"><span data-stu-id="11b33-114">Example 1: Commit a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}
```

<span data-ttu-id="11b33-115">この例では、 **Complete transaction** コマンドレットを使用してトランザクションをコミットした場合の動作を示します。</span><span class="sxs-lookup"><span data-stu-id="11b33-115">This example shows what happens when you use the **Complete-Transaction** cmdlet to commit a transaction.</span></span>

<span data-ttu-id="11b33-116">トランザクションの **開始** コマンドは、トランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="11b33-116">The **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="11b33-117">New-Item コマンドは、 *UseTransaction* パラメーターを使用して、トランザクションにコマンドを含めます。</span><span class="sxs-lookup"><span data-stu-id="11b33-117">The New-Item command uses the *UseTransaction* parameter to include the command in the transaction.</span></span>

<span data-ttu-id="11b33-118">最初の dir (Get-childitem) コマンドは、新しい項目がまだレジストリに追加されていないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="11b33-118">The first dir (Get-ChildItem) command shows that the new item has not yet been added to the registry.</span></span>

<span data-ttu-id="11b33-119">**Complete transaction** コマンドは、トランザクションをコミットします。これにより、レジストリの変更が有効になります。</span><span class="sxs-lookup"><span data-stu-id="11b33-119">The **Complete-Transaction** command commits the transaction, which makes the registry change effective.</span></span>
<span data-ttu-id="11b33-120">その結果、2番目の dir コマンドはレジストリが変更されたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="11b33-120">As a result, the second dir command shows that the registry is changed.</span></span>

### <span data-ttu-id="11b33-121">例 2: 複数のサブスクライバーを持つトランザクションをコミットする</span><span class="sxs-lookup"><span data-stu-id="11b33-121">Example 2: Commit a transaction that has more than one subscriber</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
0   0 MyCompany                      {}

PS HKCU:\software> Start-Transaction
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                2                Active

PS HKCU:\software> New-ItemProperty -Path MyCompany -Name MyKey -Value -UseTransaction

MyKey
-----
123

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Get-Transaction

RollbackPreference   SubscriberCount  Status
------------------   ---------------  ------
Error                1                Active

PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   1 MyCompany                      {MyKey}
```

<span data-ttu-id="11b33-122">この例では、 **Complete transaction** を使用して、複数のサブスクライバーを持つトランザクションをコミットする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="11b33-122">This example shows how to use **Complete-Transaction** to commit a transaction that has more than one subscriber.</span></span>

<span data-ttu-id="11b33-123">マルチサブスクライバートランザクションをコミットするには、すべてのトランザクションの **開始** コマンドに対して1つの **完全なトランザクション** コマンドを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11b33-123">To commit a multi-subscriber transaction, you must enter one **Complete-Transaction** command for every **Start-Transaction** command.</span></span>
<span data-ttu-id="11b33-124">データが変更されるのは、最後の **Complete Transaction** コマンドが送信されたときだけです。</span><span class="sxs-lookup"><span data-stu-id="11b33-124">The data is changed only when the final **Complete-Transaction** command is submitted.</span></span>

<span data-ttu-id="11b33-125">具体的な方法を示すために、この例ではコマンド ラインに入力される一連のコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="11b33-125">For demonstration purposes, this example shows a series of commands entered at the command line.</span></span>
<span data-ttu-id="11b33-126">実際には通常、トランザクションはスクリプト内で実行され、メイン スクリプトによって呼び出される関数または補助的なスクリプトによって実行される 2 次的なトランザクションを伴います。</span><span class="sxs-lookup"><span data-stu-id="11b33-126">In practice, transactions are likely to be run in scripts, with the secondary transaction being run by a function or helper script that is called by the main script.</span></span>

<span data-ttu-id="11b33-127">この例では、 **開始トランザクション** コマンドによってトランザクションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="11b33-127">In this example, a **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="11b33-128">*UseTransaction* パラメーターが指定された **新しい項目** のコマンドは、MyCompany キーをソフトウェアキーに追加します。</span><span class="sxs-lookup"><span data-stu-id="11b33-128">A **New-Item** command with the *UseTransaction* parameter adds the MyCompany key to the Software key.</span></span>
<span data-ttu-id="11b33-129">**新しい項目** のコマンドレットはキーオブジェクトを返しますが、レジストリ内のデータはまだ変更されていません。</span><span class="sxs-lookup"><span data-stu-id="11b33-129">Although the **New-Item** cmdlet returns a key object, the data in the registry is not yet changed.</span></span>

<span data-ttu-id="11b33-130">2番目の **トランザクションの開始** コマンドは、既存のトランザクションに2番目のサブスクライバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="11b33-130">A second **Start-Transaction** command adds a second subscriber to the existing transaction.</span></span>
<span data-ttu-id="11b33-131">**Get Transaction** コマンドレットは、サブスクライバー数が2であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="11b33-131">The **Get-Transaction** cmdlet confirms that the subscriber count is 2.</span></span>
<span data-ttu-id="11b33-132">*UseTransaction* パラメーターを指定した New-ItemProperty コマンドは、新しい MyCompany キーにレジストリエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="11b33-132">A New-ItemProperty command with the *UseTransaction* parameter adds a registry entry to the new MyCompany key.</span></span>
<span data-ttu-id="11b33-133">再びコマンドから値が返されますが、レジストリは変更されません。</span><span class="sxs-lookup"><span data-stu-id="11b33-133">Again, the command returns a value, but the registry is not changed.</span></span>

<span data-ttu-id="11b33-134">最初の **Complete Transaction** コマンドは、サブスクライバーの数を1つ減らします。</span><span class="sxs-lookup"><span data-stu-id="11b33-134">The first **Complete-Transaction** command reduces the subscriber count by 1.</span></span>
<span data-ttu-id="11b33-135">これは、 **Get Transaction** コマンドによって確認されます。</span><span class="sxs-lookup"><span data-stu-id="11b33-135">This is confirmed by a **Get-Transaction** command.</span></span>
<span data-ttu-id="11b33-136">ただし、dir m \* ( **get-childitem** ) コマンドでは、データは変更されません。</span><span class="sxs-lookup"><span data-stu-id="11b33-136">However, no data is changed, as evidenced by a dir m\* ( **Get-ChildItem** ) command.</span></span>

<span data-ttu-id="11b33-137">2番目の **Complete transaction** コマンドは、トランザクション全体をコミットし、レジストリ内のデータを変更します。</span><span class="sxs-lookup"><span data-stu-id="11b33-137">The second **Complete-Transaction** command commits the entire transaction and changes the data in the registry.</span></span>
<span data-ttu-id="11b33-138">これは、変更を示す2番目の dir m \* コマンドによって確認されます。</span><span class="sxs-lookup"><span data-stu-id="11b33-138">This is confirmed by a second dir m\* command, which shows the changes.</span></span>

### <span data-ttu-id="11b33-139">例 3: データを変更しないトランザクションを実行する</span><span class="sxs-lookup"><span data-stu-id="11b33-139">Example 3: Perform a transaction that does not change any data</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item MyCompany -UseTransaction
PS HKCU:\software> dir m*
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}

PS HKCU:\software> dir m* -UseTransaction
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
82   1 Microsoft                      {(default)}
0   0 MyCompany                      {}

PS HKCU:\software> Complete-Transaction
```

<span data-ttu-id="11b33-140">この例では、トランザクションで Get コマンドを使用し \* た値と、データを変更しないその他のコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="11b33-140">This example shows the value of using Get-\* commands, and other commands that do not change data, in a transaction.</span></span>
<span data-ttu-id="11b33-141">トランザクションで Get コマンドを使用すると、 \* トランザクションの一部であるオブジェクトが取得されます。</span><span class="sxs-lookup"><span data-stu-id="11b33-141">When a Get-\* command is used in a transaction, it gets the objects that are part of the transaction.</span></span>
<span data-ttu-id="11b33-142">これによって、変更をコミットする前にトランザクション内の変更をプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="11b33-142">This allows you to preview the changes in the transaction before the changes are committed.</span></span>

<span data-ttu-id="11b33-143">この例では、トランザクションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="11b33-143">In this example, a transaction is started.</span></span>
<span data-ttu-id="11b33-144">*UseTransaction* パラメーターを指定した New-Item コマンドは、トランザクションの一部として新しいキーをレジストリに追加します。</span><span class="sxs-lookup"><span data-stu-id="11b33-144">A New-Item command with the *UseTransaction* parameter adds a new key to the registry as part of the transaction.</span></span>

<span data-ttu-id="11b33-145">新しいレジストリキーは、 **Complete Transaction** コマンドが実行されるまでレジストリに追加されないため、単純な Dir ( **get-childitem** ) コマンドは、新しいキーなしでレジストリを表示します。</span><span class="sxs-lookup"><span data-stu-id="11b33-145">Because the new registry key is not added to the registry until the **Complete-Transaction** command is run, a simple dir ( **Get-ChildItem** ) command shows the registry without the new key.</span></span>

<span data-ttu-id="11b33-146">ただし、dir コマンドに *UseTransaction* パラメーターを追加すると、コマンドはトランザクションの一部になり、トランザクション内の項目がまだデータに追加されていない場合でも取得されます。</span><span class="sxs-lookup"><span data-stu-id="11b33-146">However, when you add the *UseTransaction* parameter to the dir command, the command becomes part of the transaction, and it gets the items in the transaction even if they are not yet added to the data.</span></span>

## <span data-ttu-id="11b33-147">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="11b33-147">PARAMETERS</span></span>

### <span data-ttu-id="11b33-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="11b33-148">-Confirm</span></span>
<span data-ttu-id="11b33-149">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11b33-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="11b33-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="11b33-150">-WhatIf</span></span>
<span data-ttu-id="11b33-151">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="11b33-151">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="11b33-152">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="11b33-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="11b33-153">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="11b33-153">CommonParameters</span></span>
<span data-ttu-id="11b33-154">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="11b33-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="11b33-155">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11b33-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="11b33-156">入力</span><span class="sxs-lookup"><span data-stu-id="11b33-156">INPUTS</span></span>

### <span data-ttu-id="11b33-157">なし</span><span class="sxs-lookup"><span data-stu-id="11b33-157">None</span></span>
<span data-ttu-id="11b33-158">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="11b33-158">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="11b33-159">出力</span><span class="sxs-lookup"><span data-stu-id="11b33-159">OUTPUTS</span></span>

### <span data-ttu-id="11b33-160">なし</span><span class="sxs-lookup"><span data-stu-id="11b33-160">None</span></span>
<span data-ttu-id="11b33-161">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="11b33-161">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="11b33-162">注</span><span class="sxs-lookup"><span data-stu-id="11b33-162">NOTES</span></span>

* <span data-ttu-id="11b33-163">コミットされたトランザクションのロールバック、またはロールバックされたトランザクションのコミットを行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="11b33-163">You cannot roll back a transaction that has been committed, or commit a transaction that has been rolled back.</span></span>

  <span data-ttu-id="11b33-164">有効でないトランザクションはロールバックできません。</span><span class="sxs-lookup"><span data-stu-id="11b33-164">You cannot roll back any transaction other than the active transaction.</span></span>
<span data-ttu-id="11b33-165">別のトランザクションをロールバックするには、有効なトランザクションを先にコミットするかロールバックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="11b33-165">To roll back a different transaction, you must first commit or roll back the active transaction.</span></span>

  <span data-ttu-id="11b33-166">既定では、トランザクションのコマンドのエラーなどでトランザクションの一部をコミットできない場合、トランザクション全体がロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="11b33-166">By default, if any part of a transaction cannot be committed, such as when a command in the transaction results in an error, the entire transaction is rolled back.</span></span>

*

## <span data-ttu-id="11b33-167">関連リンク</span><span class="sxs-lookup"><span data-stu-id="11b33-167">RELATED LINKS</span></span>

[<span data-ttu-id="11b33-168">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="11b33-168">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="11b33-169">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="11b33-169">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="11b33-170">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="11b33-170">Undo-Transaction</span></span>](Undo-Transaction.md)

[<span data-ttu-id="11b33-171">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="11b33-171">Use-Transaction</span></span>](Use-Transaction.md)

[<span data-ttu-id="11b33-172">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="11b33-172">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="11b33-173">New-Item</span><span class="sxs-lookup"><span data-stu-id="11b33-173">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="11b33-174">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="11b33-174">New-ItemProperty</span></span>](New-ItemProperty.md)
