---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Transaction
ms.openlocfilehash: bb8e9e1f204c67207f31613181f856d3bcaf8dc3
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209023"
---
# <span data-ttu-id="4e89a-103">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="4e89a-103">Get-Transaction</span></span>

## <span data-ttu-id="4e89a-104">概要</span><span class="sxs-lookup"><span data-stu-id="4e89a-104">SYNOPSIS</span></span>
<span data-ttu-id="4e89a-105">現在の (有効な) トランザクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-105">Gets the current (active) transaction.</span></span>

## <span data-ttu-id="4e89a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4e89a-106">SYNTAX</span></span>

```
Get-Transaction [<CommonParameters>]
```

## <span data-ttu-id="4e89a-107">Description</span><span class="sxs-lookup"><span data-stu-id="4e89a-107">DESCRIPTION</span></span>
<span data-ttu-id="4e89a-108">**Get transaction** コマンドレットは、セッションの現在のトランザクションを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-108">The **Get-Transaction** cmdlet gets an object that represents the current transaction in the session.</span></span>

<span data-ttu-id="4e89a-109">有効なトランザクションは一度に 1 つしかないので、このコマンドレットが複数のオブジェクトを返すことはありません。</span><span class="sxs-lookup"><span data-stu-id="4e89a-109">This cmdlet never returns more than one object, because only one transaction is active at a time.</span></span>
<span data-ttu-id="4e89a-110">(開始トランザクションの独立したパラメーターを使用して) 1 つまたは複数の独立したトランザクションを開始すると、最も最近開始されたトランザクションがアクティブになり **、トランザクションが返され** ます。</span><span class="sxs-lookup"><span data-stu-id="4e89a-110">If you start one or more independent transactions (by using the Independent parameter of Start-Transaction), the most recently started transaction is active, and that is the transaction that **Get-Transaction** returns.</span></span>

<span data-ttu-id="4e89a-111">すべてのアクティブなトランザクションがロールバックまたはコミットされている場合、このコマンドレットは、セッションで最後にアクティブになったトランザクションを表示します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-111">When all active transactions have either been rolled back or committed, this cmdlet shows the transaction that was most recently active in the session.</span></span>

<span data-ttu-id="4e89a-112">このコマンドレットは、Windows PowerShell のトランザクション機能をサポートする一連のコマンドレットの1つです。</span><span class="sxs-lookup"><span data-stu-id="4e89a-112">This cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="4e89a-113">詳細については、「about_Transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e89a-113">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="4e89a-114">例</span><span class="sxs-lookup"><span data-stu-id="4e89a-114">EXAMPLES</span></span>

### <span data-ttu-id="4e89a-115">例 1: 現在のトランザクションを取得する</span><span class="sxs-lookup"><span data-stu-id="4e89a-115">Example 1: Get the current transaction</span></span>

```
PS C:\> Start-Transaction
PS C:\> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="4e89a-116">このコマンドは、Get-Transaction コマンドレットを使用して現在のトランザクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-116">This command uses the Get-Transaction cmdlet to get the current transaction.</span></span>

### <span data-ttu-id="4e89a-117">例 2: トランザクションオブジェクトのプロパティとメソッドを表示する</span><span class="sxs-lookup"><span data-stu-id="4e89a-117">Example 2: Show the properties and methods of the transaction object</span></span>

```
PS C:\> Get-Transaction | Get-Member

Name               MemberType Definition
----               ---------- ----------
Dispose            Method     System.Void Dispose(), System.Void Dispose(Boolean disposing)
Equals             Method     System.Boolean Equals(Object obj)
GetHashCode        Method     System.Int32 GetHashCode()
GetType            Method     System.Type GetType()
ToString           Method     System.String ToString()
IsCommitted        Property   System.Boolean IsCommitted {get;}
IsRolledBack       Property   System.Boolean IsRolledBack {get;}
RollbackPreference Property   System.Management.Automation.RollbackSeverity RollbackPreference {get;}
SubscriberCount    Property   System.Int32 SubscriberCount {get;set;}
```

<span data-ttu-id="4e89a-118">このコマンドは、Get-Member コマンドレットを使用してトランザクション オブジェクトのプロパティとメソッドを表示します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-118">This command uses the Get-Member cmdlet to show the properties and methods of the transaction object.</span></span>

### <span data-ttu-id="4e89a-119">例 3: ロールバックされたトランザクションのプロパティ値を表示する</span><span class="sxs-lookup"><span data-stu-id="4e89a-119">Example 3: Show the property values of a rolled back transaction</span></span>

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Undo-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ----------
Error                0                 RolledBack
```

<span data-ttu-id="4e89a-120">このコマンドは、ロールバックしたトランザクションのトランザクション オブジェクトのプロパティ値を表示します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-120">This command shows the property values of a transaction object for a transaction that has been rolled back.</span></span>

### <span data-ttu-id="4e89a-121">例 4: コミットされたトランザクションのプロパティ値を表示する</span><span class="sxs-lookup"><span data-stu-id="4e89a-121">Example 4: Show the property values of a committed transaction</span></span>

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

<span data-ttu-id="4e89a-122">このコマンドは、コミットしたトランザクションのトランザクション オブジェクトのプロパティ値を表示します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-122">This command shows the property values of a transaction object for a transaction that has been committed.</span></span>

### <span data-ttu-id="4e89a-123">例 5: トランザクションを別の処理中に開始する</span><span class="sxs-lookup"><span data-stu-id="4e89a-123">Example 5: Start a transaction while another is in progress</span></span>

```
PS C:\> cd hklm:\software
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany -UseTransaction
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> New-Item MyCompany2 -UseTransaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ---------
Error                1                 Committed
```

<span data-ttu-id="4e89a-124">この例は、別のトランザクションが進行しているときにトランザクションを開始したときのトランザクション オブジェクトにおける影響を示します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-124">This example shows the effect on the transaction object of starting a transaction while another transaction is in progress.</span></span>
<span data-ttu-id="4e89a-125">通常、これはトランザクションを実行するスクリプトが関数を含む場合、または別の完全なトランザクションを含むスクリプトを呼び出す場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-125">Typically, this happens when a script that runs a transaction includes a function or calls a script that contains another complete transaction.</span></span>

<span data-ttu-id="4e89a-126">2番目の **開始トランザクション** コマンドに *独立* したパラメーターが含まれていない限り、 **開始トランザクション** では新しいトランザクションは作成されません。</span><span class="sxs-lookup"><span data-stu-id="4e89a-126">Unless the second **Start-Transaction** command includes the *Independent* parameter, **Start-Transaction** does not create a new transaction.</span></span>
<span data-ttu-id="4e89a-127">代わりに、元のトランザクションに第 2 のサブスクライバーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="4e89a-127">Instead, it adds a second subscriber to the original transaction.</span></span>

<span data-ttu-id="4e89a-128">最初の **トランザクションの開始** コマンドは、トランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-128">The first **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="4e89a-129">*UseTransaction* パラメーターが指定された New-Item コマンドは、トランザクションの一部です。</span><span class="sxs-lookup"><span data-stu-id="4e89a-129">A New-Item command with the *UseTransaction* parameter is part of the transaction.</span></span>

<span data-ttu-id="4e89a-130">2番目の **トランザクションの開始** コマンドは、トランザクションにサブスクライバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-130">A second **Start-Transaction** command adds a subscriber to the transaction.</span></span>
<span data-ttu-id="4e89a-131">その次の New-Item コマンドもトランザクションの一部です。</span><span class="sxs-lookup"><span data-stu-id="4e89a-131">The next New-Item command is also part of the transaction.</span></span>

<span data-ttu-id="4e89a-132">最初の **トランザクションの取得** コマンドは、マルチサブスクライバートランザクションを示します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-132">The first **Get-Transaction** command shows the multi-subscriber transaction.</span></span>
<span data-ttu-id="4e89a-133">サブスクライバーの数が 2 であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4e89a-133">Notice that the subscriber count is 2.</span></span>

<span data-ttu-id="4e89a-134">最初の Complete-Transaction コマンドはトランザクションをコミットしませんが、サブスクライバーの数を 1 に減らします。</span><span class="sxs-lookup"><span data-stu-id="4e89a-134">The first Complete-Transaction command does not commit the transaction, but it reduces the subscriber count to 1.</span></span>

<span data-ttu-id="4e89a-135">2番目の **Complete transaction** コマンドは、トランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="4e89a-135">The second **Complete-Transaction** command commits the transaction.</span></span>

### <span data-ttu-id="4e89a-136">例 6: 別のトランザクションが進行中のときに独立したトランザクションを開始する</span><span class="sxs-lookup"><span data-stu-id="4e89a-136">Example 6: Start an independent transaction while another is in progress</span></span>

```
PS C:\>
HKLM:\SOFTWARE> Start-Transaction
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Start-Transaction -Independent
HKLM:\SOFTWARE> Get-Transaction

RollbackPreference   SubscriberCount   IsRolledBack   IsCommitted
------------------   ---------------   ------------   -----------
Error                1                 False          False

HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
HKLM:\SOFTWARE> Complete-Transaction
HKLM:\SOFTWARE> Get-Transaction
```

<span data-ttu-id="4e89a-137">この例は、別のトランザクションが進行しているときに独立したトランザクションを開始したときのトランザクション オブジェクトにおける影響を示します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-137">This example shows the effect on the transaction object of starting an independent transaction while another transaction is in progress.</span></span>

<span data-ttu-id="4e89a-138">最初の **トランザクションの開始** コマンドは、トランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-138">The first **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="4e89a-139">*UseTransaction* パラメーターが指定された **新しい項目** のコマンドは、トランザクションの一部です。</span><span class="sxs-lookup"><span data-stu-id="4e89a-139">A **New-Item** command with the *UseTransaction* parameter is part of the transaction.</span></span>

<span data-ttu-id="4e89a-140">2番目の **トランザクションの開始** コマンドは、トランザクションにサブスクライバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-140">A second **Start-Transaction** command adds a subscriber to the transaction.</span></span>
<span data-ttu-id="4e89a-141">次の **新しい項目** コマンドは、トランザクションの一部でもあります。</span><span class="sxs-lookup"><span data-stu-id="4e89a-141">The next **New-Item** command is also part of the transaction.</span></span>

<span data-ttu-id="4e89a-142">最初の **トランザクションの取得** コマンドは、マルチサブスクライバートランザクションを示します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-142">The first **Get-Transaction** command shows the multi-subscriber transaction.</span></span>
<span data-ttu-id="4e89a-143">サブスクライバーの数が 2 であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4e89a-143">Note that the subscriber count is 2.</span></span>

<span data-ttu-id="4e89a-144">**Complete transaction** コマンドを実行すると、サブスクライバー数が1に減少しますが、トランザクションはコミットされません。</span><span class="sxs-lookup"><span data-stu-id="4e89a-144">The **Complete-Transaction** command reduces the subscriber count to 1, but it does not commit the transaction.</span></span>

<span data-ttu-id="4e89a-145">2番目の **Complete transaction** コマンドは、トランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="4e89a-145">The second **Complete-Transaction** command commits the transaction.</span></span>

## <span data-ttu-id="4e89a-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4e89a-146">PARAMETERS</span></span>

### <span data-ttu-id="4e89a-147">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4e89a-147">CommonParameters</span></span>
<span data-ttu-id="4e89a-148">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4e89a-148">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4e89a-149">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e89a-149">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4e89a-150">入力</span><span class="sxs-lookup"><span data-stu-id="4e89a-150">INPUTS</span></span>

### <span data-ttu-id="4e89a-151">なし</span><span class="sxs-lookup"><span data-stu-id="4e89a-151">None</span></span>
<span data-ttu-id="4e89a-152">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="4e89a-152">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="4e89a-153">出力</span><span class="sxs-lookup"><span data-stu-id="4e89a-153">OUTPUTS</span></span>

### <span data-ttu-id="4e89a-154">PSTransaction (システム管理)</span><span class="sxs-lookup"><span data-stu-id="4e89a-154">System.Management.Automation.PSTransaction</span></span>
<span data-ttu-id="4e89a-155">このコマンドレットは、現在のトランザクションを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="4e89a-155">This cmdlet returns an object that represents the current transaction.</span></span>

## <span data-ttu-id="4e89a-156">注</span><span class="sxs-lookup"><span data-stu-id="4e89a-156">NOTES</span></span>

## <span data-ttu-id="4e89a-157">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4e89a-157">RELATED LINKS</span></span>

[<span data-ttu-id="4e89a-158">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="4e89a-158">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="4e89a-159">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="4e89a-159">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="4e89a-160">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="4e89a-160">Undo-Transaction</span></span>](Undo-Transaction.md)

[<span data-ttu-id="4e89a-161">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="4e89a-161">Use-Transaction</span></span>](Use-Transaction.md)

[<span data-ttu-id="4e89a-162">New-Item</span><span class="sxs-lookup"><span data-stu-id="4e89a-162">New-Item</span></span>](New-Item.md)
