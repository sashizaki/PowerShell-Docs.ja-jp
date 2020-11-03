---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Transaction
ms.openlocfilehash: 53be131f45f15e5d2053b183040dc7b3dca4a14c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214392"
---
# <span data-ttu-id="1f1e3-103">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="1f1e3-103">Start-Transaction</span></span>

## <span data-ttu-id="1f1e3-104">概要</span><span class="sxs-lookup"><span data-stu-id="1f1e3-104">SYNOPSIS</span></span>
<span data-ttu-id="1f1e3-105">トランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-105">Starts a transaction.</span></span>

## <span data-ttu-id="1f1e3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1f1e3-106">SYNTAX</span></span>

```
Start-Transaction [-Timeout <Int32>] [-Independent] [-RollbackPreference <RollbackSeverity>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1f1e3-107">Description</span><span class="sxs-lookup"><span data-stu-id="1f1e3-107">DESCRIPTION</span></span>
<span data-ttu-id="1f1e3-108">**開始トランザクション** コマンドレットは、1つの単位として管理される一連のコマンドであるトランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-108">The **Start-Transaction** cmdlet starts a transaction, which is a series of commands that are managed as a unit.</span></span>
<span data-ttu-id="1f1e3-109">トランザクションは、完了するかコミットすることができます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-109">A transaction can be completed, or committed.</span></span>
<span data-ttu-id="1f1e3-110">または、トランザクションによって変更されたデータが元の状態に復元されるように、完全に元に戻したり、ロールバックしたりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-110">Alternatively, it can be completely undone, or rolled back, so that any data changed by the transaction is restored to its original state.</span></span>
<span data-ttu-id="1f1e3-111">1 つのトランザクション内の一連のコマンドは 1 つの単位として管理されるので、コマンドはすべてコミットされるか、すべてロールバックされるかのいずれかとなります。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-111">Because the commands in a transaction are managed as a unit, either all commands are committed or all commands are rolled back.</span></span>

<span data-ttu-id="1f1e3-112">既定では、トランザクション内のいずれかのコマンドがエラーを生成すると、トランザクションは自動的にロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-112">By default, if any command in the transaction generates an error, transactions are rolled back automatically.</span></span>
<span data-ttu-id="1f1e3-113">*RollbackPreference* パラメーターを使用して、この動作を変更できます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-113">You can use the *RollbackPreference* parameter to change this behavior.</span></span>

<span data-ttu-id="1f1e3-114">トランザクションで使用するコマンドレットは、トランザクションをサポートするように設計されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-114">The cmdlets used in a transaction must be designed to support transactions.</span></span>
<span data-ttu-id="1f1e3-115">トランザクションをサポートするコマンドレットには、 *UseTransaction* パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-115">Cmdlets that support transactions have a *UseTransaction* parameter.</span></span>
<span data-ttu-id="1f1e3-116">1 つのプロバイダーで複数のトランザクションを実行するには、プロバイダーがトランザクションをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-116">To perform transactions in a provider, the provider must support transactions.</span></span>
<span data-ttu-id="1f1e3-117">Windows Vista 以降のバージョンの windows オペレーティングシステムの Windows PowerShell レジストリプロバイダーは、トランザクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-117">The Windows PowerShell Registry provider in Windows Vista and later versions of the Windows operating system supports transactions.</span></span>
<span data-ttu-id="1f1e3-118">また、 **TransactedString** クラスを使用して、windows PowerShell をサポートする任意のバージョンの windows システムのトランザクションに式を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-118">You can also use the **Microsoft.PowerShell.Commands.Management.TransactedString** class to include expressions in transactions on any version of the Windows system that supports Windows PowerShell.</span></span>
<span data-ttu-id="1f1e3-119">他の Windows PowerShell プロバイダーもトランザクションをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-119">Other Windows PowerShell providers can also support transactions.</span></span>

<span data-ttu-id="1f1e3-120">一度に複数のトランザクションを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-120">Only one transaction can be active at a time.</span></span>
<span data-ttu-id="1f1e3-121">トランザクションの進行中に新しい独立したトランザクションを開始すると、新しいトランザクションがアクティブなトランザクションになり、元のトランザクションを変更する前に、新しいトランザクションをコミットまたはロールバックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-121">If you start a new, independent transaction while a transaction is in progress, the new transaction becomes the active transaction, and you must commit or roll back the new transaction before you make any changes to the original transaction.</span></span>

<span data-ttu-id="1f1e3-122">**開始トランザクション** コマンドレットは、Windows PowerShell のトランザクション機能をサポートする一連のコマンドレットの1つです。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-122">**Start-Transaction** cmdlet is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="1f1e3-123">詳細については、「about_Transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-123">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="1f1e3-124">例</span><span class="sxs-lookup"><span data-stu-id="1f1e3-124">EXAMPLES</span></span>

### <span data-ttu-id="1f1e3-125">例 1: トランザクションを開始してロールバックする</span><span class="sxs-lookup"><span data-stu-id="1f1e3-125">Example 1: Start and roll back a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Undo-Transaction
```

<span data-ttu-id="1f1e3-126">これらのコマンドは、トランザクションを開始してからロールバックします。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-126">These commands start and then roll back a transaction.</span></span>
<span data-ttu-id="1f1e3-127">トランザクションはロールバックされるので、レジストリは変更されません。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-127">Because the transaction is rolled back, no changes are made to the registry.</span></span>

### <span data-ttu-id="1f1e3-128">例 2: トランザクションを開始して完了する</span><span class="sxs-lookup"><span data-stu-id="1f1e3-128">Example 2: Start and complete a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> New-ItemProperty "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
```

<span data-ttu-id="1f1e3-129">これらのコマンドは、トランザクションを開始して完了します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-129">These commands start and then complete a transaction.</span></span>
<span data-ttu-id="1f1e3-130">**Complete Transaction** コマンドが使用されるまで、レジストリは変更されません。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-130">No changes are made to the registry until the **Complete-Transaction** command is used.</span></span>

### <span data-ttu-id="1f1e3-131">例 3: 異なるロールバック設定を使用する</span><span class="sxs-lookup"><span data-stu-id="1f1e3-131">Example 3: Use different rollback preferences</span></span>

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

# Start-Transaction (-rollbackpreference error)

PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction
New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name ContosoCompany -UseTransaction

PS HKCU:\software> New-Item -Path . -Name "Contoso" -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  -Path . -Name ContosoCompany -UseTransaction

# Start-Transaction (-rollbackpreference never)

PS HKCU:\software> Start-Transaction -RollbackPreference never
PS HKCU:\software> New-Item -Path "NoPath" -Name "ContosoCompany" -UseTransaction

New-Item : The registry key at the specified path does not exist.
At line:1 char:9
+ new-item <<<<  -Path NoPath -Name "ContosoCompany" -UseTransaction
PS HKCU:\software> New-Item -Path . -Name "ContosoCompany" -UseTransaction

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany                 {}
PS HKCU:\Software> Complete-Transaction

# Succeeds
```

<span data-ttu-id="1f1e3-132">この例では、 *RollbackPreference* パラメーター値を変更した場合の影響を示します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-132">This example demonstrates the effect of changing the *RollbackPreference* parameter value.</span></span>

<span data-ttu-id="1f1e3-133">最初のコマンドセット **では、** *RollbackPreference* は使用されません。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-133">In the first set of commands, **Start-Transaction** does not use *RollbackPreference* .</span></span>
<span data-ttu-id="1f1e3-134">その結果、既定値 (Error) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-134">As a result, the default value (Error) is used.</span></span>
<span data-ttu-id="1f1e3-135">トランザクションコマンドでエラーが発生した場合 (指定されたパスが存在しない場合)、トランザクションは自動的にロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-135">When an error occurs in a transaction command, that is, the specified path does not exist, the transaction is automatically rolled back.</span></span>

<span data-ttu-id="1f1e3-136">2番目のコマンドのセット **では、** *RollbackPreference* は、値が Never であることを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-136">In the second set of commands, **Start-Transaction** uses *RollbackPreference* with a value of Never.</span></span>
<span data-ttu-id="1f1e3-137">その結果、トランザクション コマンドでエラーが発生しても、トランザクションは有効のままであり、正常に完了できます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-137">As a result, when an error occurs in a transaction command, the transaction is still active and can be completed successfully.</span></span>

<span data-ttu-id="1f1e3-138">ほとんどのトランザクションはエラーなしで実行する必要があるため、通常は *RollbackPreference* の既定値を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-138">Because most transactions must be performed without error, the default value of *RollbackPreference* is typically preferred.</span></span>

### <span data-ttu-id="1f1e3-139">例 4: トランザクションの実行中にこのコマンドレットを使用する</span><span class="sxs-lookup"><span data-stu-id="1f1e3-139">Example 4: Use this cmdlet while a transaction is in progress</span></span>

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction
PS HKCU:\software> Get-Transaction
PS HKCU:\software> New-Item "ContosoCompany2" -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\Software> Get-Transaction
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

<span data-ttu-id="1f1e3-140">この例は、トランザクションの実行中に **開始トランザクション** を使用した場合の影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-140">This example shows the effect of using **Start-Transaction** while a transaction is in progress.</span></span>
<span data-ttu-id="1f1e3-141">結果は、進行中のトランザクションを追加した場合とほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-141">The effect is much like joining the transaction in progress.</span></span>

<span data-ttu-id="1f1e3-142">これは簡略化されたコマンドですが、このシナリオは、トランザクションが完全なトランザクションを含むスクリプトを実行する場合に頻繁に発生します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-142">Although this is a simplified command, this scenario frequently occurs when the transaction involves running a script that includes a complete transaction.</span></span>

<span data-ttu-id="1f1e3-143">最初の **トランザクションの開始** コマンドは、トランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-143">The first **Start-Transaction** command starts the transaction.</span></span>
<span data-ttu-id="1f1e3-144">最初の **新しい項目** のコマンドは、トランザクションの一部です。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-144">The first **New-Item** command is part of the transaction.</span></span>

<span data-ttu-id="1f1e3-145">2番目の **トランザクションの開始** コマンドは、新しいサブスクライバーをトランザクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-145">The second **Start-Transaction** command adds a new subscriber to the transaction.</span></span>
<span data-ttu-id="1f1e3-146">次に、 **Get transaction** コマンドで、サブスクライバー数が2のトランザクションが返されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-146">The **Get-Transaction** command now returns a transaction with a subscriber count of 2.</span></span>
<span data-ttu-id="1f1e3-147">2番目の **新しい項目** コマンドは、同じトランザクションの一部です。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-147">The second **New-Item** command is part of the same transaction.</span></span>

<span data-ttu-id="1f1e3-148">トランザクション全体が完了するまで、レジストリは変更されません。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-148">No changes are made to the registry until the whole transaction is completed.</span></span>
<span data-ttu-id="1f1e3-149">トランザクションを完了するには、サブスクライバーごとに1つずつ、2つの **トランザクションの完全** なコマンドを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-149">To complete the transaction, you must enter two **Complete-Transaction** commands, one for each subscriber.</span></span>
<span data-ttu-id="1f1e3-150">トランザクションを任意の時点でロールバックすると、すべてのトランザクションが両方のサブスクライバーに対してロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-150">If you were to roll back the transaction at any point, all the transaction would be rolled back for both subscribers.</span></span>

### <span data-ttu-id="1f1e3-151">例 5: 1 つの処理中に独立したトランザクションを開始する</span><span class="sxs-lookup"><span data-stu-id="1f1e3-151">Example 5: Start an independent transaction while one is in progress</span></span>

```
PS C:\> cd HKCU:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany" -UseTransaction
PS HKCU:\software> Start-Transaction -Independent
PS HKCU:\software> Get-Transaction
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
PS HKCU:\software> Undo-Transaction
PS HKCU:\software> New-ItemProperty -Path "ContosoCompany" -Name "MyKey" -Value 123 -UseTransaction
MyKey
-----
123
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   1 MyCompany                      {MyKey}
```

<span data-ttu-id="1f1e3-152">この例では、別のトランザクションの進行中にトランザクションを開始するために、 **開始トランザクション** の *独立* パラメーターを使用した場合の効果を示します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-152">This example shows the effect of using the *Independent* parameter of **Start-Transaction** to start a transaction while another transaction is in progress.</span></span>
<span data-ttu-id="1f1e3-153">この場合、新しいトランザクションは、元のトランザクションに影響を及ぼすことなくロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-153">In this case, the new transaction is rolled back without affecting the original transaction.</span></span>

<span data-ttu-id="1f1e3-154">これらのトランザクションは論理的に独立していますが、一度に複数のトランザクションを有効にすることはできないので、元のトランザクションに対する作業を再開するには、その前に新しいトランザクションをロールバックするかコミットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-154">Although the transactions are logically independent, because only one transaction can be active at a time, you must roll back or commit the newest transaction before resuming work on the original transaction.</span></span>

<span data-ttu-id="1f1e3-155">最初のコマンド セットを実行すると、トランザクションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-155">The first set of commands starts a transaction.</span></span>
<span data-ttu-id="1f1e3-156">**新しい項目** のコマンドは、最初のトランザクションの一部です。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-156">The **New-Item** command is part of the first transaction.</span></span>

<span data-ttu-id="1f1e3-157">2番目のコマンドセットでは、 **トランザクションの開始** コマンドは、 *独立* したパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-157">In the second set of commands, the **Start-Transaction** command uses the *Independent* parameter.</span></span>
<span data-ttu-id="1f1e3-158">次に示す **Get transaction** コマンドは、アクティブなトランザクションのトランザクションオブジェクトを示しています。これは、最新のものです。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-158">The **Get-Transaction** command that follows shows the transaction object for the active transaction, which is the newest one.</span></span>
<span data-ttu-id="1f1e3-159">サブスクライバーの数は1になります。これは、トランザクションが無関係であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-159">The subscriber count is equal to 1, that shows that the transactions are unrelated.</span></span>

<span data-ttu-id="1f1e3-160">トランザクションを **元に戻す** コマンドを使用してアクティブなトランザクションがロールバックされると、元のトランザクションは再びアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-160">When the active transaction is rolled back by using an **Undo-Transaction** command, the original transaction becomes active again.</span></span>

<span data-ttu-id="1f1e3-161">元のトランザクションの一部である **get-itemproperty** コマンドは、エラーが発生することなく終了します。また、元のトランザクションは、 **Complete transaction** コマンドを使用して完了できます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-161">The **New-ItemProperty** command, which is part of the original transaction, finishes without error, and the original transaction can be completed by using the **Complete-Transaction** command.</span></span>
<span data-ttu-id="1f1e3-162">その結果、レジストリが変更されます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-162">As a result, the registry is changed.</span></span>

### <span data-ttu-id="1f1e3-163">例 6: トランザクションの一部ではないコマンドを実行する</span><span class="sxs-lookup"><span data-stu-id="1f1e3-163">Example 6: Run commands that are not part of a transaction</span></span>

```
PS C:\> cd hkcu:\software
PS HKCU:\software> Start-Transaction
PS HKCU:\software> New-Item "ContosoCompany1" -UseTransaction
PS HKCU:\software> New-Item "ContosoCompany2"
PS HKCU:\software> New-Item "ContosoCompany3" -UseTransaction
PS HKCU:\software> dir contoso*
PS HKCU:\software> Complete-Transaction
PS HKCU:\software> dir contoso*
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany2                {}

PS HKCU:\Software> Complete-Transaction
PS HKCU:\Software> dir contoso*

Hive: HKEY_CURRENT_USER\Software
SKC  VC Name                           Property
---  -- ----                           --------
0   0 ContosoCompany1                     {}
0   0 ContosoCompany2                     {}
0   0 ContosoCompany3                     {}
```

<span data-ttu-id="1f1e3-164">この例は、トランザクションの進行中に実行されたコマンドをトランザクションに含めることができるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-164">This example demonstrates that commands that are submitted while a transaction is in progress can be included in the transaction or not included.</span></span>
<span data-ttu-id="1f1e3-165">トランザクションの一部として使用されるのは、 *UseTransaction* パラメーターを使用するコマンドだけです。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-165">Only commands that use the *UseTransaction* parameter are part of the transaction.</span></span>

<span data-ttu-id="1f1e3-166">1番目と3番目の **新しい項目** コマンドでは、 *UseTransaction* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-166">The first and third **New-Item** commands use the *UseTransaction* parameter.</span></span>
<span data-ttu-id="1f1e3-167">これらのコマンドはトランザクションの一部です。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-167">These commands are part of the transaction.</span></span>
<span data-ttu-id="1f1e3-168">**2 番目の** *UseTransaction* コマンドでは、パラメーターを使用しないので、トランザクションの一部ではありません。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-168">Because the second **New-Item** command does not use the *UseTransaction* parameter, it is not part of the transaction.</span></span>

<span data-ttu-id="1f1e3-169">最初の dir コマンドは、効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-169">The first dir command shows the effect.</span></span>
<span data-ttu-id="1f1e3-170">2番目の **新しい項目** のコマンドはすぐに完了しますが、最初と3番目の **新しい項目** のコマンドは、トランザクションがコミットされるまで有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-170">The second **New-Item** command is completed immediately, but the first and third **New-Item** commands are not effective until the transaction is committed.</span></span>

<span data-ttu-id="1f1e3-171">**Complete transaction** コマンドは、トランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-171">The **Complete-Transaction** command commits the transaction.</span></span>
<span data-ttu-id="1f1e3-172">その結果、2番目の dir コマンドは、新しい項目がすべてレジストリに追加されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-172">As a result, the second dir command shows that all of the new items are added to the registry.</span></span>

### <span data-ttu-id="1f1e3-173">例 7: 指定した時間内に終了しないトランザクションをロールバックする</span><span class="sxs-lookup"><span data-stu-id="1f1e3-173">Example 7: Roll back a transaction that does not finish in a specified time</span></span>

```
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> Get-Transaction
PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction
PS C:\> Start-Transaction -Timeout 2

# Wait two minutes...

PS C:\> > Get-Transaction

RollbackPreference   SubscriberCount   Status
------------------   ---------------   -----------
Error                1                 RolledBack

PS C:\> New-Item HKCU:\Software\ContosoCompany -UseTransaction

New-Item : Cannot use transaction. The transaction has been rolled back or has timed out.
At line:1 char:9
+ new-item <<<<  MyCompany -UseTransaction
```

<span data-ttu-id="1f1e3-174">このコマンドは、 **開始トランザクション** の *Timeout* パラメーターを使用して、2分以内に完了する必要があるトランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-174">This command uses the *Timeout* parameter of **Start-Transaction** to start a transaction that must be completed within two minutes.</span></span>
<span data-ttu-id="1f1e3-175">タイムアウトが経過してもトランザクションが完了していない場合は、自動的にロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-175">If the transaction is not finished when the time-out expires, it is rolled back automatically.</span></span>

<span data-ttu-id="1f1e3-176">タイムアウトが経過すると通知されませんが、トランザクションオブジェクトの **Status** プロパティは *rolUseTransaction* に設定され、このパラメーターを使用するコマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-176">When the time-out expires, you are not notified, but the **Status** property of the transaction object is set to RolledBack and commands that use the *UseTransaction* parameter fail.</span></span>

## <span data-ttu-id="1f1e3-177">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1f1e3-177">PARAMETERS</span></span>

### <span data-ttu-id="1f1e3-178">-非依存</span><span class="sxs-lookup"><span data-stu-id="1f1e3-178">-Independent</span></span>
<span data-ttu-id="1f1e3-179">このコマンドレットが、進行中のトランザクションから独立したトランザクションを開始することを示します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-179">Indicates that this cmdlet starts a transaction that is independent of any transactions in progress.</span></span>
<span data-ttu-id="1f1e3-180">既定では、別のトランザクションの実行中に **開始トランザクション** を使用すると、進行中のトランザクションに新しいサブスクライバーが追加されます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-180">By default, if you use **Start-Transaction** while another transaction is in progress, a new subscriber is added to the transaction in progress.</span></span>
<span data-ttu-id="1f1e3-181">このパラメーターが影響を及ぼすのは、トランザクションがセッション内で既に進行中の場合のみです。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-181">This parameter has an effect only when a transaction is already in progress in the session.</span></span>

<span data-ttu-id="1f1e3-182">トランザクションの進行中に **開始トランザクション** を使用すると、既定では、既存のトランザクションオブジェクトが再利用され、サブスクライバー数が増加します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-182">By default, if you use **Start-Transaction** while a transaction is in progress, the existing transaction object is reused and the subscriber count is incremented.</span></span>
<span data-ttu-id="1f1e3-183">結果は、元のトランザクションの追加とほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-183">The effect is much like joining the original transaction.</span></span>
<span data-ttu-id="1f1e3-184">Undo-Transaction コマンドを実行すると、トランザクション全体がロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-184">An Undo-Transaction command rolls back the whole the transaction.</span></span>
<span data-ttu-id="1f1e3-185">トランザクションを完了するには、各サブスクライバーに対して Complete-Transaction コマンドを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-185">To complete the transaction, you must enter a Complete-Transaction command for each subscriber.</span></span>
<span data-ttu-id="1f1e3-186">同時に進行している大半のトランザクションは互いに関連しているので、ほとんどの場合、既定の設定で十分です。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-186">Because most transactions that are in progress at the same time are related, the default is sufficient for most uses.</span></span>

<span data-ttu-id="1f1e3-187">*独立* したパラメーターを指定した場合、このコマンドレットは、元のトランザクションに影響を与えずに完了または元に戻すことができる新しいトランザクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-187">If you specify the *Independent* parameter, this cmdlet creates a new transaction that can be completed or undone without affecting the original transaction.</span></span>
<span data-ttu-id="1f1e3-188">ただし、一度に複数のトランザクションを有効にすることはできないので、元のトランザクションに対する作業を再開するには、その前に新しいトランザクションを完了するか、ロールバックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-188">However, because only one transaction can be active at a time, you must complete or roll back the new transaction before resuming work on the original transaction.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f1e3-189">-RollbackPreference</span><span class="sxs-lookup"><span data-stu-id="1f1e3-189">-RollbackPreference</span></span>
<span data-ttu-id="1f1e3-190">トランザクションが自動的にロールバックされる条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-190">Specifies the conditions under which a transaction is automatically rolled back.</span></span>
<span data-ttu-id="1f1e3-191">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-191">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="1f1e3-192">エラー。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-192">Error.</span></span>
<span data-ttu-id="1f1e3-193">終了エラーまたは未終了エラーが発生すると、トランザクションが自動的にロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-193">The transaction is rolled back automatically if a terminating or non-terminating error occurs.</span></span>
- <span data-ttu-id="1f1e3-194">エラーを発生しています。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-194">TerminatingError.</span></span>
<span data-ttu-id="1f1e3-195">終了エラーが発生すると、トランザクションが自動的にロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-195">The transaction is rolled back automatically if a terminating error occurs.</span></span>
- <span data-ttu-id="1f1e3-196">不可</span><span class="sxs-lookup"><span data-stu-id="1f1e3-196">Never.</span></span>
<span data-ttu-id="1f1e3-197">トランザクションは自動的にロールバックされません。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-197">The transaction is never rolled back automatically.</span></span>

<span data-ttu-id="1f1e3-198">既定値は Error です。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-198">The default value is Error.</span></span>

```yaml
Type: System.Management.Automation.RollbackSeverity
Parameter Sets: (All)
Aliases:
Accepted values: Error, TerminatingError, Never

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f1e3-199">-タイムアウト</span><span class="sxs-lookup"><span data-stu-id="1f1e3-199">-Timeout</span></span>
<span data-ttu-id="1f1e3-200">トランザクションが有効である最大時間を分単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-200">Specifies the maximum time, in minutes, that the transaction is active.</span></span>
<span data-ttu-id="1f1e3-201">タイムアウトを過ぎると、トランザクションは自動的にロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-201">When the time-out expires, the transaction is automatically rolled back.</span></span>

<span data-ttu-id="1f1e3-202">既定では、コマンド ラインで開始されたトランザクションにタイムアウトはありません。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-202">By default, there is no time-out for transactions that are started at the command line.</span></span>
<span data-ttu-id="1f1e3-203">トランザクションがスクリプトによって開始された場合、既定のタイムアウトは 30 分です。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-203">When transactions are started by a script, the default time-out is 30 minutes.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: TimeoutMins

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f1e3-204">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1f1e3-204">-Confirm</span></span>
<span data-ttu-id="1f1e3-205">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-205">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1f1e3-206">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1f1e3-206">-WhatIf</span></span>
<span data-ttu-id="1f1e3-207">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-207">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="1f1e3-208">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-208">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1f1e3-209">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1f1e3-209">CommonParameters</span></span>
<span data-ttu-id="1f1e3-210">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-210">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1f1e3-211">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-211">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1f1e3-212">入力</span><span class="sxs-lookup"><span data-stu-id="1f1e3-212">INPUTS</span></span>

### <span data-ttu-id="1f1e3-213">なし</span><span class="sxs-lookup"><span data-stu-id="1f1e3-213">None</span></span>
<span data-ttu-id="1f1e3-214">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-214">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="1f1e3-215">出力</span><span class="sxs-lookup"><span data-stu-id="1f1e3-215">OUTPUTS</span></span>

### <span data-ttu-id="1f1e3-216">なし</span><span class="sxs-lookup"><span data-stu-id="1f1e3-216">None</span></span>
<span data-ttu-id="1f1e3-217">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="1f1e3-217">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="1f1e3-218">注</span><span class="sxs-lookup"><span data-stu-id="1f1e3-218">NOTES</span></span>

## <span data-ttu-id="1f1e3-219">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1f1e3-219">RELATED LINKS</span></span>

[<span data-ttu-id="1f1e3-220">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="1f1e3-220">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="1f1e3-221">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="1f1e3-221">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="1f1e3-222">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="1f1e3-222">Undo-Transaction</span></span>](Undo-Transaction.md)

[<span data-ttu-id="1f1e3-223">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="1f1e3-223">Use-Transaction</span></span>](Use-Transaction.md)
