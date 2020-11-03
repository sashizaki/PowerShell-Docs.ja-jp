---
description: PowerShell でのトランザクション操作の管理方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_transactions?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Transactions
ms.openlocfilehash: 522e0f727754b0b0153571039f3bf3966d0abf20
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222480"
---
# <a name="about-transactions"></a><span data-ttu-id="986f4-104">トランザクションについて</span><span class="sxs-lookup"><span data-stu-id="986f4-104">About Transactions</span></span>

## <a name="short-description"></a><span data-ttu-id="986f4-105">概要</span><span class="sxs-lookup"><span data-stu-id="986f4-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="986f4-106">PowerShell でのトランザクション操作の管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="986f4-106">Describes how to manage transacted operations in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="986f4-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="986f4-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="986f4-108">Powershell 2.0 以降の PowerShell では、トランザクションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="986f4-108">Transactions are supported in PowerShell beginning in PowerShell 2.0.</span></span> <span data-ttu-id="986f4-109">この機能を使用すると、トランザクションを開始して、トランザクションの一部であるコマンドを示すことや、トランザクションをコミットまたはロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="986f4-109">This feature enables you to start a transaction, to indicate which commands are part of the transaction, and to commit or roll back a transaction.</span></span>

## <a name="about-transactions"></a><span data-ttu-id="986f4-110">トランザクションについて</span><span class="sxs-lookup"><span data-stu-id="986f4-110">ABOUT TRANSACTIONS</span></span>

<span data-ttu-id="986f4-111">PowerShell では、トランザクションは1つ以上のコマンドのセットであり、論理ユニットとして管理されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-111">In PowerShell, a transaction is a set of one or more commands that are managed as a logical unit.</span></span> <span data-ttu-id="986f4-112">トランザクションを完了 ("コミット済み") できます。これにより、トランザクションの影響を受けたデータが変更されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-112">A transaction can be completed ("committed"), which changes data affected by the transaction.</span></span> <span data-ttu-id="986f4-113">または、トランザクションによって影響を受けるデータが変更されないように、トランザクションを完全に元に戻す ("ロールバック") こともできます。</span><span class="sxs-lookup"><span data-stu-id="986f4-113">Or, a transaction can be completely undone ("rolled back") so that the affected data is not changed by the transaction.</span></span>

<span data-ttu-id="986f4-114">トランザクション内のコマンドは1つの単位として管理されるので、すべてのコマンドがコミットされるか、すべてのコマンドがロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="986f4-114">Because the commands in a transaction are managed as a unit, either all commands are committed, or all commands are rolled back.</span></span>

<span data-ttu-id="986f4-115">トランザクションはデータ処理で広く使用されており、特にデータベース操作や財務トランザクションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-115">Transactions are widely used in data processing, most notably in database operations and for financial transactions.</span></span> <span data-ttu-id="986f4-116">トランザクションは、コマンドセットの最悪のシナリオでは、すべてが失敗するわけではありませんが、一部のコマンドは正常に実行されますが、他のコマンドは失敗し、破損、false、または解釈不可能な状態になることがあります。</span><span class="sxs-lookup"><span data-stu-id="986f4-116">Transactions are most often used when the worst-case scenario for a set of commands is not that they all fail, but that some commands succeed while others fail, leaving the system in a damaged, false, or uninterpretable state that is difficult to repair.</span></span>

## <a name="transaction-cmdlets"></a><span data-ttu-id="986f4-117">トランザクションのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="986f4-117">TRANSACTION CMDLETS</span></span>

<span data-ttu-id="986f4-118">PowerShell には、トランザクションを管理するためのコマンドレットがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="986f4-118">PowerShell includes several cmdlets designed for managing transactions.</span></span>

- <span data-ttu-id="986f4-119">開始トランザクション: 新しいトランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="986f4-119">Start-Transaction: Starts a new transaction.</span></span>
- <span data-ttu-id="986f4-120">トランザクションの使用: コマンドまたは式をトランザクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="986f4-120">Use-Transaction: Adds a command or expression to the transaction.</span></span> <span data-ttu-id="986f4-121">コマンドでは、トランザクション対応オブジェクトを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="986f4-121">The command must use transaction-enabled objects.</span></span>
- <span data-ttu-id="986f4-122">元に戻す-トランザクション: トランザクションによってデータが変更されないように、トランザクションをロールバックします。</span><span class="sxs-lookup"><span data-stu-id="986f4-122">Undo-Transaction: Rolls back the transaction so that no data is changed by the transaction.</span></span>
- <span data-ttu-id="986f4-123">Complete-Transaction: トランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="986f4-123">Complete-Transaction: Commits the transaction.</span></span> <span data-ttu-id="986f4-124">トランザクションの影響を受けたデータは変更されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-124">The data affected by the transaction is changed.</span></span>
- <span data-ttu-id="986f4-125">トランザクションの取得: アクティブなトランザクションに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="986f4-125">Get-Transaction: Gets information about the active transaction.</span></span>

<span data-ttu-id="986f4-126">トランザクションコマンドレットの一覧を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="986f4-126">For a list of transaction cmdlets, type:</span></span>

```powershell
get-command *transaction
```

<span data-ttu-id="986f4-127">コマンドレットの詳細については、次のように入力してください。</span><span class="sxs-lookup"><span data-stu-id="986f4-127">For detailed information about the cmdlets, type:</span></span>

```powershell
get-help use-transaction -detailed
```

## <a name="transaction-enabled-elements"></a><span data-ttu-id="986f4-128">トランザクション対応の要素</span><span class="sxs-lookup"><span data-stu-id="986f4-128">TRANSACTION-ENABLED ELEMENTS</span></span>

<span data-ttu-id="986f4-129">トランザクションに参加するには、コマンドレットとプロバイダーの両方でトランザクションがサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="986f4-129">To participate in a transaction, both the cmdlet and the provider must support transactions.</span></span> <span data-ttu-id="986f4-130">この機能は、トランザクションによって影響を受けるオブジェクトに組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="986f4-130">This feature is built in to the objects that are affected by the transaction.</span></span>

<span data-ttu-id="986f4-131">PowerShell レジストリプロバイダーは、Windows Vista のトランザクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="986f4-131">The PowerShell Registry provider supports transactions in Windows Vista.</span></span> <span data-ttu-id="986f4-132">TransactedString オブジェクト (TransactedString) は、PowerShell を実行するすべてのオペレーティングシステムで動作します。</span><span class="sxs-lookup"><span data-stu-id="986f4-132">The TransactedString object (Microsoft.PowerShell.Commands.Management.TransactedString) works with any operating system that runs PowerShell.</span></span>

<span data-ttu-id="986f4-133">他の PowerShell プロバイダーはトランザクションをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="986f4-133">Other PowerShell providers can support transactions.</span></span> <span data-ttu-id="986f4-134">トランザクションをサポートするセッションで PowerShell プロバイダーを検索するには、次のコマンドを使用して、providers の Capabilities プロパティの "transaction" 値を検索します。</span><span class="sxs-lookup"><span data-stu-id="986f4-134">To find the PowerShell providers in your session that support transactions, use the following command to find the "Transactions" value in the Capabilities property of providers:</span></span>

```powershell
get-psprovider | where {$_.Capabilities -like "*transactions*"}
```

<span data-ttu-id="986f4-135">プロバイダーの詳細については、プロバイダーのヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="986f4-135">For more information about a provider, see the Help for the provider.</span></span> <span data-ttu-id="986f4-136">プロバイダーのヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="986f4-136">To get provider Help, type:</span></span>

```
get-help <provider-name>
```

<span data-ttu-id="986f4-137">たとえば、Registry プロバイダーのヘルプを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="986f4-137">For example, to get Help for the Registry provider, type:</span></span>

```powershell
get-help registry
```

## <a name="the-usetransaction-parameter"></a><span data-ttu-id="986f4-138">USETRANSACTION パラメーター</span><span class="sxs-lookup"><span data-stu-id="986f4-138">THE USETRANSACTION PARAMETER</span></span>

<span data-ttu-id="986f4-139">トランザクションをサポートするコマンドレットには、UseTransaction パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="986f4-139">Cmdlets that can support transactions have a UseTransaction parameter.</span></span> <span data-ttu-id="986f4-140">このパラメーターには、アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="986f4-140">This parameter includes the command in the active transaction.</span></span> <span data-ttu-id="986f4-141">完全なパラメーター名またはそのエイリアスである "usetx" を使用できます。</span><span class="sxs-lookup"><span data-stu-id="986f4-141">You can use the full parameter name or its alias, "usetx".</span></span>

<span data-ttu-id="986f4-142">パラメーターは、セッションにアクティブなトランザクションが含まれている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="986f4-142">The parameter can be used only when the session contains an active transaction.</span></span> <span data-ttu-id="986f4-143">アクティブなトランザクションが存在しないときに UseTransaction パラメーターを指定してコマンドを入力すると、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="986f4-143">If you enter a command with the UseTransaction parameter when there is no active transaction, the command fails.</span></span>

<span data-ttu-id="986f4-144">UseTransaction パラメーターを使用してコマンドレットを検索するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="986f4-144">To find cmdlets with the UseTransaction parameter, type:</span></span>

```powershell
get-help * -parameter UseTransaction
```

<span data-ttu-id="986f4-145">PowerShell core では、PowerShell プロバイダーと連携するように設計されたすべてのコマンドレットがトランザクションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="986f4-145">In PowerShell core, all of the cmdlets designed to work with PowerShell providers support transactions.</span></span> <span data-ttu-id="986f4-146">その結果、プロバイダーのコマンドレットを使用してトランザクションを管理できます。</span><span class="sxs-lookup"><span data-stu-id="986f4-146">As a result, you can use the provider cmdlets to manage transactions.</span></span>

<span data-ttu-id="986f4-147">PowerShell プロバイダーの詳細については、「 [about_Providers](about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="986f4-147">For more information about PowerShell providers, see [about_Providers](about_Providers.md).</span></span>

## <a name="the-transaction-object"></a><span data-ttu-id="986f4-148">トランザクションオブジェクト</span><span class="sxs-lookup"><span data-stu-id="986f4-148">THE TRANSACTION OBJECT</span></span>

<span data-ttu-id="986f4-149">トランザクションは、PowerShell でトランザクションオブジェクトである system.string によって表されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-149">Transactions are represented in PowerShell by a transaction object, System.Management.Automation.Transaction.</span></span>

<span data-ttu-id="986f4-150">このオブジェクトには、以下のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="986f4-150">The object has the following properties:</span></span>

- <span data-ttu-id="986f4-151">RollbackPreference: 現在のトランザクションのロールバック設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="986f4-151">RollbackPreference: Contains the rollback preference set for the current transaction.</span></span> <span data-ttu-id="986f4-152">Start-Transaction を使用してトランザクションを開始するときに、ロールバックの設定を設定できます。</span><span class="sxs-lookup"><span data-stu-id="986f4-152">You can set the rollback preference when you use Start-Transaction to start the transaction.</span></span>

  <span data-ttu-id="986f4-153">ロールバックの設定によって、トランザクションが自動的にロールバックされる条件が決まります。</span><span class="sxs-lookup"><span data-stu-id="986f4-153">The rollback preference determines the conditions under which the transaction is rolled back automatically.</span></span> <span data-ttu-id="986f4-154">有効な値は、エラー、エラーの発生、および Never です。</span><span class="sxs-lookup"><span data-stu-id="986f4-154">Valid values are Error, TerminatingError, and Never.</span></span> <span data-ttu-id="986f4-155">既定値は Error です。</span><span class="sxs-lookup"><span data-stu-id="986f4-155">The default value is Error.</span></span>

- <span data-ttu-id="986f4-156">Status: トランザクションの現在の状態が含まれます。</span><span class="sxs-lookup"><span data-stu-id="986f4-156">Status: Contains the current status of the transaction.</span></span> <span data-ttu-id="986f4-157">有効な値は、"アクティブ"、"コミット"、および "ロールバック" です。</span><span class="sxs-lookup"><span data-stu-id="986f4-157">Valid values are Active, Committed, and RolledBack.</span></span>

- <span data-ttu-id="986f4-158">[登録回数数: トランザクションに対するサブスクライバーの数が含まれます。</span><span class="sxs-lookup"><span data-stu-id="986f4-158">SubscriberCount: Contains the number of subscribers to the transaction.</span></span> <span data-ttu-id="986f4-159">別のトランザクションの進行中にトランザクションを開始すると、サブスクライバーがトランザクションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-159">A subscriber is added to a transaction when you start a transaction while another transaction is in progress.</span></span> <span data-ttu-id="986f4-160">サブスクライバーがトランザクションをコミットすると、サブスクライバーの数が減少します。</span><span class="sxs-lookup"><span data-stu-id="986f4-160">The subscriber count is decremented when a subscriber commits the transaction.</span></span>

## <a name="active-transactions"></a><span data-ttu-id="986f4-161">アクティブなトランザクション</span><span class="sxs-lookup"><span data-stu-id="986f4-161">ACTIVE TRANSACTIONS</span></span>

<span data-ttu-id="986f4-162">PowerShell では、一度にアクティブなトランザクションは1つだけです。また、アクティブなトランザクションのみを管理できます。</span><span class="sxs-lookup"><span data-stu-id="986f4-162">In PowerShell, only one transaction is active at a time, and you can manage only the active transaction.</span></span> <span data-ttu-id="986f4-163">同じセッションで複数のトランザクションを同時に実行することはできますが、最も最近開始されたトランザクションのみがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="986f4-163">Multiple transactions can be in progress in the same session at the same time, but only the most-recently started transaction is active.</span></span>

<span data-ttu-id="986f4-164">このため、トランザクションコマンドレットを使用する場合、特定のトランザクションを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="986f4-164">As a result, you cannot specify a particular transaction when using the transaction cmdlets.</span></span> <span data-ttu-id="986f4-165">コマンドは、常にアクティブなトランザクションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-165">Commands always apply to the active transaction.</span></span>

<span data-ttu-id="986f4-166">これは、Get-Transaction コマンドレットの動作で最も顕著です。</span><span class="sxs-lookup"><span data-stu-id="986f4-166">This is most evident in the behavior of the Get-Transaction cmdlet.</span></span> <span data-ttu-id="986f4-167">Get-Transaction コマンドを入力すると、Get-Transaction は常に1つのトランザクションオブジェクトのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="986f4-167">When you enter a Get-Transaction command, Get-Transaction always gets only one transaction object.</span></span> <span data-ttu-id="986f4-168">このオブジェクトは、アクティブなトランザクションを表すオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="986f4-168">This object is the object that represents the active transaction.</span></span>

<span data-ttu-id="986f4-169">別のトランザクションを管理するには、まずアクティブなトランザクションをコミットするか、ロールバックすることによって完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="986f4-169">To manage a different transaction, you must first finish the active transaction, either by committing it or rolling it back.</span></span> <span data-ttu-id="986f4-170">これを行うと、前のトランザクションが自動的にアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="986f4-170">When you do this, the previous transaction becomes active automatically.</span></span> <span data-ttu-id="986f4-171">トランザクションは、開始された順番とは逆にアクティブになり、最後に開始されたトランザクションが常にアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="986f4-171">Transactions become active in the reverse of order of which they are started, so that the most recently started transaction is always active.</span></span>

## <a name="subscribers-and-independent-transactions"></a><span data-ttu-id="986f4-172">サブスクライバーと独立したトランザクション</span><span class="sxs-lookup"><span data-stu-id="986f4-172">SUBSCRIBERS AND INDEPENDENT TRANSACTIONS</span></span>

<span data-ttu-id="986f4-173">別のトランザクションの進行中にトランザクションを開始した場合、既定では、PowerShell は新しいトランザクションを開始しません。</span><span class="sxs-lookup"><span data-stu-id="986f4-173">If you start a transaction while another transaction is in progress, by default, PowerShell does not start a new transaction.</span></span> <span data-ttu-id="986f4-174">代わりに、現在のトランザクションに "subscriber" を追加します。</span><span class="sxs-lookup"><span data-stu-id="986f4-174">Instead, it adds a "subscriber" to the current transaction.</span></span>

<span data-ttu-id="986f4-175">トランザクションに複数のサブスクライバーがある場合、任意のポイントで1つの Undo-Transaction コマンドを実行すると、すべてのサブスクライバーのトランザクション全体がロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="986f4-175">When a transaction has multiple subscribers, a single Undo-Transaction command at any point rolls back the entire transaction for all subscribers.</span></span> <span data-ttu-id="986f4-176">ただし、トランザクションをコミットするには、すべてのサブスクライバーに対して Complete-Transaction コマンドを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="986f4-176">However, to commit the transaction, you must enter a Complete-Transaction command for every subscriber.</span></span>

<span data-ttu-id="986f4-177">トランザクションに対するサブスクライバーの数を調べるには、トランザクションオブジェクトの "参照カウント" プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="986f4-177">To find the number of subscribers to a transaction, check the SubscriberCount property of the transaction object.</span></span> <span data-ttu-id="986f4-178">たとえば、次のコマンドでは、Get-Transaction コマンドレットを使用して、アクティブなトランザクションの "/" プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="986f4-178">For example, the following command uses the Get-Transaction cmdlet to get the value of the SubscriberCount property of the active transaction:</span></span>

```powershell
(Get-Transaction).SubscriberCount
```

<span data-ttu-id="986f4-179">サブスクライバーの追加は既定の動作です。これは、別のトランザクションの実行中に開始されるトランザクションのほとんどが、元のトランザクションに関連付けられるためです。</span><span class="sxs-lookup"><span data-stu-id="986f4-179">Adding a subscriber is the default behavior because most transactions that are started while another transaction is in progress are related to the original transaction.</span></span> <span data-ttu-id="986f4-180">一般的なモデルでは、トランザクションを含むスクリプトは、独自のトランザクションを含むヘルパースクリプトを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="986f4-180">In the typical model, a script that contains a transaction calls a helper script that contains its own transaction.</span></span> <span data-ttu-id="986f4-181">トランザクションは関連しているため、ロールバックするか、1つの単位としてコミットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="986f4-181">Because the transactions are related, they should be rolled back or committed as a unit.</span></span>

<span data-ttu-id="986f4-182">ただし、Start-Transaction コマンドレットの独立したパラメーターを使用して、現在のトランザクションから独立したトランザクションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="986f4-182">However, you can start a transaction that is independent of the current transaction by using the Independent parameter of the Start-Transaction cmdlet.</span></span>

<span data-ttu-id="986f4-183">独立したトランザクションを開始すると、Start-Transaction によって新しいトランザクションオブジェクトが作成され、新しいトランザクションがアクティブなトランザクションになります。</span><span class="sxs-lookup"><span data-stu-id="986f4-183">When you start an independent transaction, Start-Transaction creates a new transaction object, and the new transaction becomes the active transaction.</span></span>
<span data-ttu-id="986f4-184">元のトランザクションに影響を与えることなく、独立したトランザクションをコミットまたはロールバックできます。</span><span class="sxs-lookup"><span data-stu-id="986f4-184">The independent transaction can be committed or rolled back without affecting the original transaction.</span></span>

<span data-ttu-id="986f4-185">独立したトランザクションが完了 (コミットまたはロールバック) されると、元のトランザクションは再びアクティブなトランザクションになります。</span><span class="sxs-lookup"><span data-stu-id="986f4-185">When the independent transaction is finished (committed or rolled back), the original transaction becomes the active transaction again.</span></span>

## <a name="changing-data"></a><span data-ttu-id="986f4-186">データの変更</span><span class="sxs-lookup"><span data-stu-id="986f4-186">CHANGING DATA</span></span>

<span data-ttu-id="986f4-187">トランザクションを使用してデータを変更する場合、トランザクションの影響を受けるデータは、トランザクションをコミットするまで変更されません。</span><span class="sxs-lookup"><span data-stu-id="986f4-187">When you use transactions to change data, the data that is affected by the transaction is not changed until you commit the transaction.</span></span> <span data-ttu-id="986f4-188">ただし、トランザクションに含まれていないコマンドでも同じデータを変更できます。</span><span class="sxs-lookup"><span data-stu-id="986f4-188">However, the same data can be changed by commands that are not part of the transaction.</span></span>

<span data-ttu-id="986f4-189">トランザクションを使用して共有データを管理する場合は、この点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="986f4-189">Keep this in mind when you are using transactions to manage shared data.</span></span>
<span data-ttu-id="986f4-190">通常、データベースには、作業中にデータをロックし、他のユーザーやその他のコマンド、スクリプト、および関数を変更できないようにするメカニズムがあります。</span><span class="sxs-lookup"><span data-stu-id="986f4-190">Typically, databases have mechanisms that lock the data while you are working on it, preventing other users, and other commands, scripts, and functions, from changing it.</span></span>

<span data-ttu-id="986f4-191">ただし、ロックはデータベースの機能です。</span><span class="sxs-lookup"><span data-stu-id="986f4-191">However, the lock is a feature of the database.</span></span> <span data-ttu-id="986f4-192">トランザクションに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="986f4-192">It is not related to transactions.</span></span> <span data-ttu-id="986f4-193">トランザクション対応のファイルシステムまたはその他のデータストアで作業している場合は、トランザクションの進行中にデータを変更できます。</span><span class="sxs-lookup"><span data-stu-id="986f4-193">If you are working in a transaction-enabled file system or other data store, the data can be changed while the transaction is in progress.</span></span>

## <a name="examples"></a><span data-ttu-id="986f4-194">例</span><span class="sxs-lookup"><span data-stu-id="986f4-194">EXAMPLES</span></span>

<span data-ttu-id="986f4-195">このセクションの例では、PowerShell レジストリプロバイダーを使用します。このプロバイダーについて理解していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="986f4-195">The examples in this section use the PowerShell Registry provider and assume that you are familiar with it.</span></span> <span data-ttu-id="986f4-196">レジストリプロバイダーの詳細については、「get-help Registry」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="986f4-196">For information about the Registry provider, type "get-help registry".</span></span>

### <a name="example-1-committing-a-transaction"></a><span data-ttu-id="986f4-197">例 1: トランザクションをコミットする</span><span class="sxs-lookup"><span data-stu-id="986f4-197">EXAMPLE 1: COMMITTING A TRANSACTION</span></span>

<span data-ttu-id="986f4-198">トランザクションを作成するには、Start-Transaction コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="986f4-198">To create a transaction, use the Start-Transaction cmdlet.</span></span> <span data-ttu-id="986f4-199">次のコマンドは、既定の設定を使用してトランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="986f4-199">The following command starts a transaction with the default settings.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="986f4-200">コマンドをトランザクションに含めるには、コマンドレットの UseTransaction パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="986f4-200">To include commands in the transaction, use the UseTransaction parameter of the cmdlet.</span></span> <span data-ttu-id="986f4-201">既定では、コマンドはトランザクションに含まれていません。</span><span class="sxs-lookup"><span data-stu-id="986f4-201">By default, commands are not included in the transaction,</span></span>

<span data-ttu-id="986f4-202">たとえば、次のコマンドは、HKCU: ドライブのソフトウェアキーの現在の場所を設定しますが、トランザクションには含まれていません。</span><span class="sxs-lookup"><span data-stu-id="986f4-202">For example, the following command, which sets the current location in the Software key of the HKCU: drive, is not included in the transaction.</span></span>

```powershell
cd hkcu:\Software
```

<span data-ttu-id="986f4-203">MyCompany キーを作成する次のコマンドは、New-Item コマンドレットの UseTransaction パラメーターを使用して、アクティブなトランザクションにコマンドを含めます。</span><span class="sxs-lookup"><span data-stu-id="986f4-203">The following command, which creates the MyCompany key, uses the UseTransaction parameter of the New-Item cmdlet to include the command in the active transaction.</span></span>

```powershell
new-item MyCompany -UseTransaction
```

<span data-ttu-id="986f4-204">このコマンドは、新しいキーを表すオブジェクトを返しますが、このコマンドはトランザクションの一部であるため、レジストリはまだ変更されていません。</span><span class="sxs-lookup"><span data-stu-id="986f4-204">The command returns an object that represents the new key, but because the command is part of the transaction, the registry is not yet changed.</span></span>

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyCompany                      {}
```

<span data-ttu-id="986f4-205">トランザクションをコミットするには、Complete-Transaction コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="986f4-205">To commit the transaction, use the Complete-Transaction cmdlet.</span></span> <span data-ttu-id="986f4-206">常にアクティブなトランザクションに影響するため、トランザクションを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="986f4-206">Because it always affects the active transaction, you cannot specify the transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="986f4-207">その結果、MyCompany キーがレジストリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-207">As a result, the MyCompany key is added to the registry.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-2-rolling-back-a-transaction"></a><span data-ttu-id="986f4-208">例 2: トランザクションをロールバックする</span><span class="sxs-lookup"><span data-stu-id="986f4-208">EXAMPLE 2: ROLLING BACK A TRANSACTION</span></span>

<span data-ttu-id="986f4-209">トランザクションを作成するには、Start-Transaction コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="986f4-209">To create a transaction, use the Start-Transaction cmdlet.</span></span> <span data-ttu-id="986f4-210">次のコマンドは、既定の設定を使用してトランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="986f4-210">The following command starts a transaction with the default settings.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="986f4-211">次のコマンドでは、MyOtherCompany キーを作成し、New-Item コマンドレットの UseTransaction パラメーターを使用して、アクティブなトランザクションにコマンドを含めます。</span><span class="sxs-lookup"><span data-stu-id="986f4-211">The following command, which creates the MyOtherCompany key, uses the UseTransaction parameter of the New-Item cmdlet to include the command in the active transaction.</span></span>

```powershell
new-item MyOtherCompany -UseTransaction
```

<span data-ttu-id="986f4-212">このコマンドは、新しいキーを表すオブジェクトを返しますが、このコマンドはトランザクションの一部であるため、レジストリはまだ変更されていません。</span><span class="sxs-lookup"><span data-stu-id="986f4-212">The command returns an object that represents the new key, but because the command is part of the transaction, the registry is not yet changed.</span></span>

```
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
  0   0 MyOtherCompany                 {}
```

<span data-ttu-id="986f4-213">トランザクションをロールバックするには、Undo-Transaction コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="986f4-213">To roll back the transaction, use the Undo-Transaction cmdlet.</span></span> <span data-ttu-id="986f4-214">常にアクティブなトランザクションに影響するため、トランザクションは指定しません。</span><span class="sxs-lookup"><span data-stu-id="986f4-214">Because it always affects the active transaction, you do not specify the transaction.</span></span>

```powershell
Undo-transaction
```

<span data-ttu-id="986f4-215">その結果、MyOtherCompany キーはレジストリに追加されません。</span><span class="sxs-lookup"><span data-stu-id="986f4-215">The result is that the MyOtherCompany key is not added to the registry.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

### <a name="example-3-previewing-a-transaction"></a><span data-ttu-id="986f4-216">例 3: トランザクションのプレビュー</span><span class="sxs-lookup"><span data-stu-id="986f4-216">EXAMPLE 3: PREVIEWING A TRANSACTION</span></span>

<span data-ttu-id="986f4-217">通常、トランザクションで使用されるコマンドは、データを変更します。</span><span class="sxs-lookup"><span data-stu-id="986f4-217">Typically, the commands used in a transaction change data.</span></span> <span data-ttu-id="986f4-218">ただし、トランザクション内でデータを取得するため、データを取得するコマンドも便利です。</span><span class="sxs-lookup"><span data-stu-id="986f4-218">However, the commands that get data are useful in a transaction, too, because they get data inside of the transaction.</span></span> <span data-ttu-id="986f4-219">これにより、トランザクションのコミットによって発生する変更のプレビューが提供されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-219">This provides a preview of the changes that committing the transaction would cause.</span></span>

<span data-ttu-id="986f4-220">次の例では、Get-ChildItem コマンド (別名は "dir") を使用して、トランザクションの変更をプレビューする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="986f4-220">The following example shows how to use the Get-ChildItem command (the alias is "dir") to preview the changes in a transaction.</span></span>

<span data-ttu-id="986f4-221">次のコマンドを実行すると、トランザクションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-221">The following command starts a transaction.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="986f4-222">次のコマンドでは、New-ItemProperty コマンドレットを使用して、MyCompany キーに MyKey レジストリエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="986f4-222">The following command uses the New-ItemProperty cmdlet to add the MyKey registry entry to the MyCompany key.</span></span> <span data-ttu-id="986f4-223">このコマンドは、UseTransaction パラメーターを使用して、コマンドをトランザクションに含めます。</span><span class="sxs-lookup"><span data-stu-id="986f4-223">The command uses the UseTransaction parameter to include the command in the transaction.</span></span>

```powershell
new-itemproperty -path MyCompany -Name MyKey -value 123 -UseTransaction
```

<span data-ttu-id="986f4-224">このコマンドは、新しいレジストリエントリを表すオブジェクトを返しますが、レジストリエントリは変更されません。</span><span class="sxs-lookup"><span data-stu-id="986f4-224">The command returns an object representing the new registry entry, but the registry entry is not changed.</span></span>

```
MyKey
-----
123
```

<span data-ttu-id="986f4-225">現在レジストリにある項目を取得するには、UseTransaction パラメーターを指定せずに Get-ChildItem コマンド ("dir") を使用します。</span><span class="sxs-lookup"><span data-stu-id="986f4-225">To get the items that are currently in the registry, use a Get-ChildItem command ("dir") without the UseTransaction parameter.</span></span> <span data-ttu-id="986f4-226">次のコマンドは、"M" で始まる項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="986f4-226">The following command gets items that begin with "M."</span></span>

```powershell
dir m*
```

<span data-ttu-id="986f4-227">結果には、MyCompany キーにまだエントリが追加されていないことが示されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-227">The result shows that no entries have yet been added to the MyCompany key.</span></span>

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

<span data-ttu-id="986f4-228">トランザクションのコミットの効果をプレビューするには、UseTransaction パラメーターを使用して Get-ChildItem ("dir") コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="986f4-228">To preview the effect of committing the transaction, enter a Get-ChildItem ("dir") command with the UseTransaction parameter.</span></span> <span data-ttu-id="986f4-229">このコマンドには、トランザクション内のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-229">This command has a view of the data from within the transaction.</span></span>

```powershell
dir m* -useTransaction
```

<span data-ttu-id="986f4-230">この結果、トランザクションがコミットされると、MyKey エントリが MyCompany キーに追加されることがわかります。</span><span class="sxs-lookup"><span data-stu-id="986f4-230">The result shows that, if the transaction is committed, the MyKey entry will be added to the MyCompany key.</span></span>

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   1 MyCompany                      {MyKey}
```

### <a name="example-4-combining-transacted-and-non-transacted-commands"></a><span data-ttu-id="986f4-231">例 4: トランザクションコマンドと非トランザクションコマンドの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="986f4-231">EXAMPLE 4: COMBINING TRANSACTED AND NON-TRANSACTED COMMANDS</span></span>

<span data-ttu-id="986f4-232">トランザクションの実行中は、非トランザクションコマンドを入力できます。</span><span class="sxs-lookup"><span data-stu-id="986f4-232">You can enter non-transacted commands during a transaction.</span></span> <span data-ttu-id="986f4-233">非トランザクションコマンドはデータに直ちに影響しますが、トランザクションには影響しません。</span><span class="sxs-lookup"><span data-stu-id="986f4-233">The non-transacted commands affect the data immediately, but they do not affect the transaction.</span></span>
<span data-ttu-id="986f4-234">次のコマンドを実行すると、HKCU:\ Software レジストリキーのトランザクションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-234">The following command starts a transaction in the HKCU:\Software registry key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="986f4-235">次の3つのコマンドは、New-Item コマンドレットを使用して、レジストリにキーを追加します。</span><span class="sxs-lookup"><span data-stu-id="986f4-235">The next three commands use the New-Item cmdlet to add keys to the registry.</span></span>
<span data-ttu-id="986f4-236">1番目と3番目のコマンドは、UseTransaction パラメーターを使用して、トランザクションにコマンドを含めます。</span><span class="sxs-lookup"><span data-stu-id="986f4-236">The first and third commands use the UseTransaction parameter to include the commands in the transaction.</span></span> <span data-ttu-id="986f4-237">2番目のコマンドは、パラメーターを省略します。</span><span class="sxs-lookup"><span data-stu-id="986f4-237">The second command omits the parameter.</span></span> <span data-ttu-id="986f4-238">2番目のコマンドはトランザクションに含まれていないため、すぐに有効になります。</span><span class="sxs-lookup"><span data-stu-id="986f4-238">Because the second command is not included in the transaction, it is effective immediately.</span></span>

```powershell
new-item MyCompany1 -UseTransaction
new-item MyCompany2
new-item MyCompany3 -UseTransaction
```

<span data-ttu-id="986f4-239">レジストリの現在の状態を表示するには、UseTransaction パラメーターを指定せずに Get-ChildItem ("dir") コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="986f4-239">To view the current state of the registry, use a Get-ChildItem ("dir") command without the UseTransaction parameter.</span></span> <span data-ttu-id="986f4-240">このコマンドは、"M" で始まる項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="986f4-240">This command gets items that begin with "M."</span></span>

```powershell
dir m*
```

<span data-ttu-id="986f4-241">結果は、MyCompany2 キーがレジストリに追加されたことを示していますが、トランザクションの一部である MyCompany1 および MyCompany3 キーは追加されていません。</span><span class="sxs-lookup"><span data-stu-id="986f4-241">The result shows that the MyCompany2 key is added to the registry, but the MyCompany1 and MyCompany3 keys, which are part of the transaction, are not added.</span></span>

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0    0 MyCompany2                     {}
```

<span data-ttu-id="986f4-242">次のコマンドは、トランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="986f4-242">The following command commits the transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="986f4-243">これで、トランザクションの一部として追加されたキーがレジストリに表示されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-243">Now, the keys that were added as part of the transaction appear in the registry.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
83   1 Microsoft                      {(default)}
0    0 MyCompany1                     {}
0    0 MyCompany2                     {}
0    0 MyCompany3                     {}
```

### <a name="example-5-using-automatic-rollback"></a><span data-ttu-id="986f4-244">例 5: 自動ロールバックの使用</span><span class="sxs-lookup"><span data-stu-id="986f4-244">EXAMPLE 5: USING AUTOMATIC ROLLBACK</span></span>

<span data-ttu-id="986f4-245">トランザクション内のコマンドが任意の種類のエラーを生成すると、トランザクションは自動的にロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="986f4-245">When a command in a transaction generates an error of any kind, the transaction is automatically rolled back.</span></span>

<span data-ttu-id="986f4-246">この既定の動作は、トランザクションを実行するスクリプト向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="986f4-246">This default behavior is designed for scripts that run transactions.</span></span> <span data-ttu-id="986f4-247">通常、スクリプトは適切にテストされ、エラー処理ロジックを含んでいるため、エラーは想定されず、トランザクションを終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="986f4-247">Scripts are typically well tested and include error-handling logic, so errors are not expected and should terminate the transaction.</span></span>

<span data-ttu-id="986f4-248">最初のコマンドは、HKCU: \ Software レジストリキーでトランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="986f4-248">The first command starts a transaction in the HKCU:\Software registry key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="986f4-249">次のコマンドでは、New-Item コマンドレットを使用して、レジストリに MyCompany キーを追加します。</span><span class="sxs-lookup"><span data-stu-id="986f4-249">The following command uses the New-Item cmdlet to add the MyCompany key to the registry.</span></span> <span data-ttu-id="986f4-250">このコマンドは、UseTransaction パラメーター (エイリアスは "usetx") を使用して、トランザクションにコマンドを含めます。</span><span class="sxs-lookup"><span data-stu-id="986f4-250">The command uses the UseTransaction parameter (the alias is "usetx") to include the command in the transaction.</span></span>

```powershell
New-Item MyCompany -UseTX
```

<span data-ttu-id="986f4-251">MyCompany キーはレジストリに既に存在するため、コマンドは失敗し、トランザクションはロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="986f4-251">Because the MyCompany key already exists in the registry, the command fails, and the transaction is rolled back.</span></span>

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

<span data-ttu-id="986f4-252">Get-Transaction コマンドを実行すると、トランザクションがロールバックされたこと、およびそのサブスクライバー数が0であることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-252">A Get-Transaction command confirms that the transaction has been rolled back and that the SubscriberCount is 0.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 RolledBack
```

### <a name="example-6-changing-the-rollback-preference"></a><span data-ttu-id="986f4-253">例 6: ロールバック設定を変更する</span><span class="sxs-lookup"><span data-stu-id="986f4-253">EXAMPLE 6: CHANGING THE ROLLBACK PREFERENCE</span></span>

<span data-ttu-id="986f4-254">トランザクションのエラートレラントを向上させるには、Start-Transaction の RollbackPreference パラメーターを使用して、優先順位を変更します。</span><span class="sxs-lookup"><span data-stu-id="986f4-254">If you want the transaction to be more error tolerant, you can use the RollbackPreference parameter of Start-Transaction to change the preference.</span></span>

<span data-ttu-id="986f4-255">次のコマンドは、ロールバックの設定を "Never" にしてトランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="986f4-255">The following command starts a transaction with a rollback preference of "Never".</span></span>

```powershell
start-transaction -rollbackpreference Never
```

<span data-ttu-id="986f4-256">この場合、コマンドが失敗すると、トランザクションは自動的にロールバックされません。</span><span class="sxs-lookup"><span data-stu-id="986f4-256">In this case, when the command fails, the transaction is not automatically rolled back.</span></span>

```powershell
New-Item MyCompany -UseTX
```

```output
New-Item : A key at this path already exists
At line:1 char:9
+ new-item <<<<  MyCompany -usetx
```

<span data-ttu-id="986f4-257">トランザクションがまだアクティブであるため、トランザクションの一部としてコマンドを再送信できます。</span><span class="sxs-lookup"><span data-stu-id="986f4-257">Because the transaction is still active, you can resubmit the command as part of the transaction.</span></span>

```powershell
New-Item MyOtherCompany -UseTX
```

### <a name="example-7-using-the-use-transaction-cmdlet"></a><span data-ttu-id="986f4-258">例 7: USE TRANSACTION コマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="986f4-258">EXAMPLE 7: USING THE USE-TRANSACTION CMDLET</span></span>

<span data-ttu-id="986f4-259">Use-Transaction コマンドレットを使用すると、トランザクション対応の Microsoft .NET フレームワークオブジェクトに対して直接スクリプトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="986f4-259">The Use-Transaction cmdlet enables you to do direct scripting against transaction-enabled Microsoft .NET Framework objects.</span></span> <span data-ttu-id="986f4-260">Use-Transaction は、トランザクションが有効な .NET Framework オブジェクト (TransactedString クラスのインスタンスなど) を使用するコマンドおよび式のみを含むスクリプトブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="986f4-260">Use-Transaction takes a script block that can only contain commands and expressions that use transaction-enabled .NET Framework objects, such as instances of the Microsoft.PowerShell.Commands.Management.TransactedString class.</span></span>

<span data-ttu-id="986f4-261">次のコマンドを実行すると、トランザクションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-261">The following command starts a transaction.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="986f4-262">次の New-Object コマンドは、TransactedString クラスのインスタンスを作成し、$t 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="986f4-262">The following New-Object command creates an instance of the TransactedString class and saves it in the $t variable.</span></span>

```powershell
$t = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
```

<span data-ttu-id="986f4-263">次のコマンドは、TransactedString オブジェクトの Append メソッドを使用して、文字列にテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="986f4-263">The following command uses the Append method of the TransactedString object to add text to the string.</span></span> <span data-ttu-id="986f4-264">コマンドはトランザクションの一部ではないため、変更はすぐに有効になります。</span><span class="sxs-lookup"><span data-stu-id="986f4-264">Because the command is not part of the transaction, the change is effective immediately.</span></span>

```powershell
$t.append("Windows")
```

<span data-ttu-id="986f4-265">次のコマンドでは、同じ Append メソッドを使用してテキストを追加しますが、テキストはトランザクションの一部として追加されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-265">The following command uses the same Append method to add text, but it adds the text as part of the transaction.</span></span> <span data-ttu-id="986f4-266">コマンドは中かっこで囲まれ、使用される ScriptBlock パラメーターの値として設定されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-266">The command is enclosed in braces, and it is set as the value of the ScriptBlock parameter of Use-Transaction.</span></span> <span data-ttu-id="986f4-267">UseTransaction パラメーター (UseTx) が必要です。</span><span class="sxs-lookup"><span data-stu-id="986f4-267">The UseTransaction parameter (UseTx) is required.</span></span>

```powershell
use-transaction {$t.append(" PowerShell")} -usetx
```

<span data-ttu-id="986f4-268">$T でトランザクション処理された文字列の現在の内容を表示するには、TransactedString オブジェクトの ToString メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="986f4-268">To see the current content of the transacted string in $t, use the ToString method of the TransactedString object.</span></span>

```powershell
$t.tostring()
```

<span data-ttu-id="986f4-269">出力には、トランザクション以外の変更のみが有効であることが示されています。</span><span class="sxs-lookup"><span data-stu-id="986f4-269">The output shows that only the non-transacted changes are effective.</span></span>

```output
Windows
```

<span data-ttu-id="986f4-270">トランザクション内から $t のトランザクション処理された文字列の現在の内容を表示するには、Use-Transaction コマンドに式を埋め込みます。</span><span class="sxs-lookup"><span data-stu-id="986f4-270">To see the current content of the transacted string in $t from within the transaction, embed the expression in a Use-Transaction command.</span></span>

```powershell
use-transaction {$s.tostring()} -usetx
```

<span data-ttu-id="986f4-271">出力には、トランザクションビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-271">The output shows the transaction view.</span></span>

```output
PowerShell
```

<span data-ttu-id="986f4-272">次のコマンドは、トランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="986f4-272">The following command commits the transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="986f4-273">最後の文字列を表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="986f4-273">To see the final string:</span></span>

```
$t.tostring()
PowerShell
```

### <a name="example-8-managing-multi-subscriber-transactions"></a><span data-ttu-id="986f4-274">例 8: マルチサブスクライバートランザクションを管理する</span><span class="sxs-lookup"><span data-stu-id="986f4-274">EXAMPLE 8: MANAGING MULTI-SUBSCRIBER TRANSACTIONS</span></span>

<span data-ttu-id="986f4-275">別のトランザクションの進行中にトランザクションを開始しても、既定では2番目のトランザクションは作成されません。</span><span class="sxs-lookup"><span data-stu-id="986f4-275">When you start a transaction while another transaction is in progress, PowerShell does not create a second transaction by default.</span></span> <span data-ttu-id="986f4-276">代わりに、現在のトランザクションにサブスクライバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="986f4-276">Instead, it adds a subscriber to the current transaction.</span></span>

<span data-ttu-id="986f4-277">この例では、マルチサブスクライバートランザクションを表示および管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="986f4-277">This example shows how to view and manage a multi-subscriber transaction.</span></span>

<span data-ttu-id="986f4-278">まず、HKCU: \ Software キーでトランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="986f4-278">Begin by starting a transaction in the HKCU:\Software key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="986f4-279">次のコマンドでは、Get-Transaction コマンドを使用して、アクティブなトランザクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="986f4-279">The following command uses the Get-Transaction command to get the active transaction.</span></span>

```powershell
get-transaction
```

<span data-ttu-id="986f4-280">結果には、アクティブなトランザクションを表すオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-280">The result shows the object that represents the active transaction.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="986f4-281">MyCompany キーをレジストリに追加するコマンドを次に示します。</span><span class="sxs-lookup"><span data-stu-id="986f4-281">The following command adds the MyCompany key to the registry.</span></span> <span data-ttu-id="986f4-282">このコマンドは、UseTransaction パラメーターを使用して、コマンドをトランザクションに含めます。</span><span class="sxs-lookup"><span data-stu-id="986f4-282">The command uses the UseTransaction parameter to include the command in the transaction.</span></span>

```powershell
new-item MyCompany -UseTransaction
```

<span data-ttu-id="986f4-283">次のコマンドでは、Start-Transaction コマンドを使用してトランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="986f4-283">The following command uses the Start-Transaction command to start a transaction.</span></span> <span data-ttu-id="986f4-284">このコマンドはコマンドプロンプトで入力しますが、トランザクションを含むスクリプトを実行すると発生する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="986f4-284">Although this command is typed at the command prompt, this scenario is more likely to happen when you run a script that contains a transaction.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="986f4-285">Get-Transaction コマンドは、トランザクションオブジェクトのサブスクライバー数がインクリメントされることを示します。</span><span class="sxs-lookup"><span data-stu-id="986f4-285">A Get-Transaction command shows that the subscriber count on the transaction object is incremented.</span></span> <span data-ttu-id="986f4-286">値は2になりました。</span><span class="sxs-lookup"><span data-stu-id="986f4-286">The value is now 2.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                2                 Active
```

<span data-ttu-id="986f4-287">次のコマンドは、New-ItemProperty コマンドレットを使用して、MyCompany キーに MyKey レジストリエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="986f4-287">The next command uses the New-ItemProperty cmdlet to add the MyKey registry entry to the MyCompany key.</span></span> <span data-ttu-id="986f4-288">UseTransaction パラメーターを使用して、トランザクションにコマンドを含めます。</span><span class="sxs-lookup"><span data-stu-id="986f4-288">It uses the UseTransaction parameter to include the command in the transaction.</span></span>

```powershell
new-itemproperty -path MyCompany -name MyKey -UseTransaction
```

<span data-ttu-id="986f4-289">MyCompany キーはレジストリに存在しませんが、2つのコマンドが同じトランザクションの一部であるため、このコマンドは成功します。</span><span class="sxs-lookup"><span data-stu-id="986f4-289">The MyCompany key does not exist in the registry, but this command succeeds because the two commands are part of the same transaction.</span></span>

<span data-ttu-id="986f4-290">次のコマンドは、トランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="986f4-290">The following command commits the transaction.</span></span> <span data-ttu-id="986f4-291">トランザクションがロールバックされた場合、トランザクションはすべてのサブスクライバーに対してロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="986f4-291">If it rolled back the transaction, the transaction would be rolled back for all the subscribers.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="986f4-292">Get-Transaction コマンドは、トランザクションオブジェクトのサブスクライバー数が1であることを示していますが、Status の値がアクティブ (コミットされていません) であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="986f4-292">A Get-Transaction command shows that the subscriber count on the transaction object is 1, but the value of Status is still Active (not Committed).</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="986f4-293">トランザクションのコミットを完了するには、2番目のトランザクションの完了コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="986f4-293">To finish committing the transaction, enter a second Complete- Transaction command.</span></span> <span data-ttu-id="986f4-294">マルチサブスクライバートランザクションをコミットするには、Start-Transaction コマンドごとに1つの Complete-Transaction コマンドを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="986f4-294">To commit a multi-subscriber transaction, you must enter one Complete-Transaction command for each Start-Transaction command.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="986f4-295">もう1つの Get-Transaction コマンドは、トランザクションがコミットされたことを示します。</span><span class="sxs-lookup"><span data-stu-id="986f4-295">Another Get-Transaction command shows that the transaction has been committed.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                0                 Committed
```

### <a name="example-9-managing-independent-transactions"></a><span data-ttu-id="986f4-296">例 9: 独立したトランザクションの管理</span><span class="sxs-lookup"><span data-stu-id="986f4-296">EXAMPLE 9: MANAGING INDEPENDENT TRANSACTIONS</span></span>

<span data-ttu-id="986f4-297">別のトランザクションの進行中にトランザクションを開始すると、Start-Transaction の独立したパラメーターを使用して、元のトランザクションとは無関係に新しいトランザクションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="986f4-297">When you start a transaction while another transaction is in progress, you can use the Independent parameter of Start-Transaction to make the new transaction independent of the original transaction.</span></span>

<span data-ttu-id="986f4-298">この操作を実行すると、Start-Transaction によって新しいトランザクションオブジェクトが作成され、新しいトランザクションがアクティブなトランザクションになります。</span><span class="sxs-lookup"><span data-stu-id="986f4-298">When you do, Start-Transaction creates a new transaction object and makes the new transaction the active transaction.</span></span>

<span data-ttu-id="986f4-299">まず、HKCU: Software キーでトランザクションを開始し \\ ます。</span><span class="sxs-lookup"><span data-stu-id="986f4-299">Begin by starting a transaction in the HKCU:\\Software key.</span></span>

```powershell
start-transaction
```

<span data-ttu-id="986f4-300">次のコマンドでは、Get-Transaction コマンドを使用して、アクティブなトランザクションを取得します。</span><span class="sxs-lookup"><span data-stu-id="986f4-300">The following command uses the Get-Transaction command to get the active transaction.</span></span>

```powershell
get-transaction
```

<span data-ttu-id="986f4-301">結果には、アクティブなトランザクションを表すオブジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-301">The result shows the object that represents the active transaction.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="986f4-302">次のコマンドは、トランザクションの一部として MyCompany レジストリキーを追加します。</span><span class="sxs-lookup"><span data-stu-id="986f4-302">The following command adds the MyCompany registry key as part of the transaction.</span></span> <span data-ttu-id="986f4-303">UseTransaction パラメーター (UseTx) を使用して、アクティブなトランザクションにコマンドを含めます。</span><span class="sxs-lookup"><span data-stu-id="986f4-303">It uses the UseTransaction parameter (UseTx) to include the command in the active transaction.</span></span>

```powershell
new-item MyCompany -use
```

<span data-ttu-id="986f4-304">次のコマンドを実行すると、新しいトランザクションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-304">The following command starts a new transaction.</span></span> <span data-ttu-id="986f4-305">このコマンドは、独立したパラメーターを使用して、このトランザクションがアクティブなトランザクションに対するサブスクライバーではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="986f4-305">The command uses the Independent parameter to indicate that this transaction is not a subscriber to the active transaction.</span></span>

```powershell
start-transaction -independent
```

<span data-ttu-id="986f4-306">独立したトランザクションを作成すると、新しい (最近作成された) トランザクションがアクティブなトランザクションになります。</span><span class="sxs-lookup"><span data-stu-id="986f4-306">When you create an independent transaction, the new (most-recently created) transaction becomes the active transaction.</span></span> <span data-ttu-id="986f4-307">Get-Transaction コマンドを使用して、アクティブなトランザクションを取得できます。</span><span class="sxs-lookup"><span data-stu-id="986f4-307">You can use a Get-Transaction command to get the active transaction.</span></span>

```powershell
get-transaction
```

<span data-ttu-id="986f4-308">トランザクションのサブスクライバー数が1であることに注意してください。これは、他のサブスクライバーが存在せず、トランザクションが新しいものであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="986f4-308">Note that the SubscriberCount of the transaction is 1, indicating that there are no other subscribers and that the transaction is new.</span></span>

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="986f4-309">元のトランザクションを管理する前に、新しいトランザクションを完了する (コミットまたはロールバックする) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="986f4-309">The new transaction must be finished (either committed or rolled back) before you can manage the original transaction.</span></span>

<span data-ttu-id="986f4-310">次のコマンドを実行すると、MyOtherCompany キーがレジストリに追加されます。</span><span class="sxs-lookup"><span data-stu-id="986f4-310">The following command adds the MyOtherCompany key to the registry.</span></span> <span data-ttu-id="986f4-311">UseTransaction パラメーター (UseTx) を使用して、アクティブなトランザクションにコマンドを含めます。</span><span class="sxs-lookup"><span data-stu-id="986f4-311">It uses the UseTransaction parameter (UseTx) to include the command in the active transaction.</span></span>

```powershell
new-item MyOtherCompany -usetx
```

<span data-ttu-id="986f4-312">次に、トランザクションをロールバックします。</span><span class="sxs-lookup"><span data-stu-id="986f4-312">Now, roll back the transaction.</span></span> <span data-ttu-id="986f4-313">2つのサブスクライバーを持つ1つのトランザクションがある場合、トランザクションをロールバックすると、すべてのサブスクライバーのトランザクション全体がロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="986f4-313">If there were a single transaction with two subscribers, rolling back the transaction would roll back the entire transaction for all the subscribers.</span></span>

<span data-ttu-id="986f4-314">ただし、これらのトランザクションは独立しているため、最新のトランザクションをロールバックすると、レジストリの変更が取り消され、元のトランザクションがアクティブなトランザクションになります。</span><span class="sxs-lookup"><span data-stu-id="986f4-314">However, because these transactions are independent, rolling back the newest transaction cancels the registry changes and makes the original transaction the active transaction.</span></span>

```powershell
undo-transaction
```

<span data-ttu-id="986f4-315">Get-Transaction コマンドは、元のトランザクションがセッションでアクティブなままであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="986f4-315">A Get-Transaction command confirms that the original transaction is still active in the session.</span></span>

```powershell
get-transaction
```

```output
RollbackPreference   SubscriberCount   Status
------------------   ---------------   ------
Error                1                 Active
```

<span data-ttu-id="986f4-316">次のコマンドは、アクティブなトランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="986f4-316">The following command commits the active transaction.</span></span>

```powershell
complete-transaction
```

<span data-ttu-id="986f4-317">Get-ChildItem のコマンドは、レジストリが変更されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="986f4-317">A Get-ChildItem command shows that the registry has been changed.</span></span>

```powershell
dir m*
```

```output
Hive: HKEY_CURRENT_USER\Software

SKC  VC Name                           Property
---  -- ----                           --------
 83   1 Microsoft                      {(default)}
  0   0 MyCompany                      {}
```

## <a name="see-also"></a><span data-ttu-id="986f4-318">関連項目</span><span class="sxs-lookup"><span data-stu-id="986f4-318">SEE ALSO</span></span>

[<span data-ttu-id="986f4-319">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="986f4-319">Start-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Start-Transaction)

[<span data-ttu-id="986f4-320">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="986f4-320">Get-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Get-Transaction)

[<span data-ttu-id="986f4-321">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="986f4-321">Complete-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Complete-Transaction)

[<span data-ttu-id="986f4-322">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="986f4-322">Undo-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Undo-Transaction)

[<span data-ttu-id="986f4-323">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="986f4-323">Use-Transaction</span></span>](xref:Microsoft.PowerShell.Management.Use-Transaction)

[<span data-ttu-id="986f4-324">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="986f4-324">Get-PSProvider</span></span>](xref:Microsoft.PowerShell.Management.Get-PSProvider)

[<span data-ttu-id="986f4-325">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="986f4-325">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)

[<span data-ttu-id="986f4-326">about_Providers</span><span class="sxs-lookup"><span data-stu-id="986f4-326">about_Providers</span></span>](about_Providers.md)
