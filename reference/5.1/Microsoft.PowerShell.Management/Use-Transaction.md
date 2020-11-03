---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/use-transaction?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Use-Transaction
ms.openlocfilehash: db8423aef6dc4b25c4ddd13f9b29b774463c6a6c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214355"
---
# <span data-ttu-id="d901e-103">Use-Transaction</span><span class="sxs-lookup"><span data-stu-id="d901e-103">Use-Transaction</span></span>

## <span data-ttu-id="d901e-104">概要</span><span class="sxs-lookup"><span data-stu-id="d901e-104">SYNOPSIS</span></span>
<span data-ttu-id="d901e-105">スクリプト ブロックを有効なトランザクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="d901e-105">Adds the script block to the active transaction.</span></span>

## <span data-ttu-id="d901e-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d901e-106">SYNTAX</span></span>

```
Use-Transaction [-TransactedScript] <ScriptBlock> [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="d901e-107">Description</span><span class="sxs-lookup"><span data-stu-id="d901e-107">DESCRIPTION</span></span>
<span data-ttu-id="d901e-108">**トランザクションの使用** コマンドレットは、アクティブなトランザクションにスクリプトブロックを追加します。</span><span class="sxs-lookup"><span data-stu-id="d901e-108">The **Use-Transaction** cmdlet adds a script block to an active transaction.</span></span>
<span data-ttu-id="d901e-109">これにより、トランザクション対応の Microsoft .NET Framework オブジェクトを使用して、トランザクションスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="d901e-109">This enables you to do transacted scripting by using transaction-enabled Microsoft .NET Framework objects.</span></span>
<span data-ttu-id="d901e-110">スクリプト ブロックに格納できるのは、Microsoft.PowerShell.Commands.Management.TransactedString クラスのインスタンスなど、トランザクション対応の .NET Framework オブジェクトだけです。</span><span class="sxs-lookup"><span data-stu-id="d901e-110">The script block can contain only transaction-enabled .NET Framework objects, such as instances of the Microsoft.PowerShell.Commands.Management.TransactedString class.</span></span>

<span data-ttu-id="d901e-111">このコマンドレットを使用する場合は、ほとんどのコマンドレットで省略可能な *UseTransaction* パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="d901e-111">The *UseTransaction* parameter, which is optional for most cmdlets, is required when you use this cmdlet.</span></span>

<span data-ttu-id="d901e-112">**Transaction** は、Windows PowerShell のトランザクション機能をサポートする一連のコマンドレットの1つです。</span><span class="sxs-lookup"><span data-stu-id="d901e-112">**Use-Transaction** is one of a set of cmdlets that support the transactions feature in Windows PowerShell.</span></span>
<span data-ttu-id="d901e-113">詳細については、「about_Transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d901e-113">For more information, see about_Transactions.</span></span>

## <span data-ttu-id="d901e-114">例</span><span class="sxs-lookup"><span data-stu-id="d901e-114">EXAMPLES</span></span>

### <span data-ttu-id="d901e-115">例 1: トランザクション対応オブジェクトを使用してスクリプトを作成する</span><span class="sxs-lookup"><span data-stu-id="d901e-115">Example 1: Script by using a transaction-enabled object</span></span>

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> $transactedString.ToString()
Hello
PS C:\> Use-Transaction -TransactedScript { $transactedString.ToString() } -UseTransaction
Hello, World
PS C:\> Complete-Transaction
PS C:\> $transactedString.ToString()
Hello, World
```

<span data-ttu-id="d901e-116">この例 **では、** transaction を使用して、トランザクションが有効な .NET Framework オブジェクトに対してスクリプトを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d901e-116">This example shows how to use **Use-Transaction** to script against a transaction-enabled .NET Framework object.</span></span>
<span data-ttu-id="d901e-117">この場合、オブジェクトは **TransactedString** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="d901e-117">In this case, the object is a **TransactedString** object.</span></span>

<span data-ttu-id="d901e-118">最初のコマンドは、Start-Transaction コマンドレットを使用してトランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="d901e-118">The first command uses the Start-Transaction cmdlet to start a transaction.</span></span>

<span data-ttu-id="d901e-119">2番目のコマンドは、New-Object コマンドを使用して、 **TransactedString** オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="d901e-119">The second command uses the New-Object command to create a **TransactedString** object.</span></span>
<span data-ttu-id="d901e-120">オブジェクトは $TransactedString 変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="d901e-120">It stores the object in the $TransactedString variable.</span></span>

<span data-ttu-id="d901e-121">3番目と4番目のコマンドはどちらも、 **TransactedString** オブジェクトの **Append** メソッドを使用して、$TransactedString の値にテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="d901e-121">The third and fourth commands both use the **Append** method of the **TransactedString** object to add text to the value of $TransactedString.</span></span>
<span data-ttu-id="d901e-122">1つのコマンドは、トランザクションの一部です。</span><span class="sxs-lookup"><span data-stu-id="d901e-122">One command is part of the transaction.</span></span>
<span data-ttu-id="d901e-123">その他のコマンドはではありません。</span><span class="sxs-lookup"><span data-stu-id="d901e-123">The other command is not.</span></span>

<span data-ttu-id="d901e-124">3番目のコマンドは、トランザクション文字列の **Append** メソッドを使用して、$TransactedString の値に Hello を追加します。</span><span class="sxs-lookup"><span data-stu-id="d901e-124">The third command uses the **Append** method of the transacted string to add Hello to the value of $TransactedString.</span></span>
<span data-ttu-id="d901e-125">このコマンドはトランザクションの一部ではないので、変更内容は直ちに反映されます。</span><span class="sxs-lookup"><span data-stu-id="d901e-125">Because the command is not part of the transaction, the change is applied immediately.</span></span>

<span data-ttu-id="d901e-126">4番目のコマンドは、transaction を **使用** して、トランザクション内の文字列にテキストを追加します。</span><span class="sxs-lookup"><span data-stu-id="d901e-126">The fourth command uses **Use-Transaction** to add text to the string in the transaction.</span></span>
<span data-ttu-id="d901e-127">このコマンドは、 **Append** メソッドを使用して、", World" を $TransactedString の値に追加します。</span><span class="sxs-lookup"><span data-stu-id="d901e-127">The command uses the **Append** method to add ", World" to the value of $TransactedString.</span></span>
<span data-ttu-id="d901e-128">コマンドは、スクリプトブロックにするために中かっこ () で囲まれ {} ています。</span><span class="sxs-lookup"><span data-stu-id="d901e-128">The command is enclosed in braces ( {} ) to make it a script block.</span></span>
<span data-ttu-id="d901e-129">このコマンドでは、 *UseTransaction* パラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="d901e-129">The *UseTransaction* parameter is required in this command.</span></span>

<span data-ttu-id="d901e-130">5番目と6番目のコマンドは、 **TransactedString** オブジェクトの **ToString** メソッドを使用して、 **TransactedString** の値を文字列として表示します。</span><span class="sxs-lookup"><span data-stu-id="d901e-130">The fifth and sixth commands use the **ToString** method of the **TransactedString** object to display the value of the **TransactedString** as a string.</span></span>
<span data-ttu-id="d901e-131">ここでも、1つのコマンドはトランザクションの一部です。</span><span class="sxs-lookup"><span data-stu-id="d901e-131">Again, one command is part of the transaction.</span></span>
<span data-ttu-id="d901e-132">もう一方のトランザクションがではありません。</span><span class="sxs-lookup"><span data-stu-id="d901e-132">The other transaction is not.</span></span>

<span data-ttu-id="d901e-133">5番目のコマンドは、 **ToString** メソッドを使用して、$TransactedString 変数の現在の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="d901e-133">The fifth command uses the **ToString** method to display the current value of the $TransactedString variable.</span></span>
<span data-ttu-id="d901e-134">このコマンドはトランザクションの一部ではないので、文字列の現在の状態のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="d901e-134">Because it is not part of the transaction, it displays only the current state of the string.</span></span>

<span data-ttu-id="d901e-135">6番目のコマンドは、トランザクションで同じコマンドを実行するために、 **transaction を使用** します。</span><span class="sxs-lookup"><span data-stu-id="d901e-135">The sixth command uses **Use-Transaction** to run the same command in the transaction.</span></span>
<span data-ttu-id="d901e-136">コマンドはトランザクションの一部であるため、トランザクションの文字列の現在の値が表示されます。これは、トランザクションの変更のプレビューに似ています。</span><span class="sxs-lookup"><span data-stu-id="d901e-136">Because the command is part of the transaction, it displays the current value of the string in the transaction, much like a preview of the transaction changes.</span></span>

<span data-ttu-id="d901e-137">7 番目のコマンドは、Complete-Transaction コマンドレットを使用してトランザクションをコミットします。</span><span class="sxs-lookup"><span data-stu-id="d901e-137">The seventh command uses the Complete-Transaction cmdlet to commit the transaction.</span></span>

<span data-ttu-id="d901e-138">最後のコマンドは、 **ToString** メソッドを使用して、結果として得られる変数の値を文字列として表示します。</span><span class="sxs-lookup"><span data-stu-id="d901e-138">The final command uses the **ToString** method to display the resulting value of the variable as a string.</span></span>

### <span data-ttu-id="d901e-139">例 2: トランザクションをロールバックする</span><span class="sxs-lookup"><span data-stu-id="d901e-139">Example 2: Roll back a transaction</span></span>

```
PS C:\> Start-Transaction
PS C:\> $transactedString = New-Object Microsoft.PowerShell.Commands.Management.TransactedString
PS C:\> $transactedString.Append("Hello")
PS C:\> Use-Transaction -TransactedScript { $transactedString.Append(", World") } -UseTransaction
PS C:\> Undo-Transaction
PS C:\> $transactedString.ToString()
Hello
```

<span data-ttu-id="d901e-140">この例では、トランザクションの **使用** コマンドを含むトランザクションをロールバックした場合の効果を示します。</span><span class="sxs-lookup"><span data-stu-id="d901e-140">This example shows the effect of rolling back a transaction that includes **Use-Transaction** commands.</span></span>
<span data-ttu-id="d901e-141">トランザクション内のすべてのコマンドと同様に、トランザクションをロールバックすると、トランザクションされた変更内容は破棄され、データは変更されません。</span><span class="sxs-lookup"><span data-stu-id="d901e-141">Like all commands in a transaction, when the transaction is rolled back, the transacted changes are discarded and the data is unchanged.</span></span>

<span data-ttu-id="d901e-142">最初のコマンドは、 **開始トランザクション** を使用してトランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="d901e-142">The first command uses **Start-Transaction** to start a transaction.</span></span>

<span data-ttu-id="d901e-143">2番目のコマンドは、 **TransactedString** オブジェクトを作成するために、 **New-オブジェクト** を使用します。</span><span class="sxs-lookup"><span data-stu-id="d901e-143">The second command uses **New-Object** to create a **TransactedString** object.</span></span>
<span data-ttu-id="d901e-144">オブジェクトは $TransactedString 変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="d901e-144">It stores the object in the $TransactedString variable.</span></span>

<span data-ttu-id="d901e-145">トランザクションの一部ではない3番目のコマンドは、 **Append** メソッドを使用して、"Hello" を $TransactedString の値に追加します。</span><span class="sxs-lookup"><span data-stu-id="d901e-145">The third command, which is not part of the transaction, uses the **Append** method to add "Hello" to the value of $TransactedString.</span></span>

<span data-ttu-id="d901e-146">4番目のコマンドは、トランザクションで **Append** メソッドを使用する別のコマンドを実行するために、 **transaction を使用** します。</span><span class="sxs-lookup"><span data-stu-id="d901e-146">The fourth command uses **Use-Transaction** to run another command that uses the **Append** method in the transaction.</span></span>
<span data-ttu-id="d901e-147">このコマンドは、 **Append** メソッドを使用して、", World" を $TransactedString の値に追加します。</span><span class="sxs-lookup"><span data-stu-id="d901e-147">The command uses the **Append** method to add ", World" to the value of $TransactedString.</span></span>

<span data-ttu-id="d901e-148">5 番目のコマンドは、Undo-Transaction コマンドレットを使用してトランザクションをロールバックします。</span><span class="sxs-lookup"><span data-stu-id="d901e-148">The fifth command uses the Undo-Transaction cmdlet to roll back the transaction.</span></span>
<span data-ttu-id="d901e-149">その結果、トランザクションで実行されるすべてのコマンドが元に戻されます。</span><span class="sxs-lookup"><span data-stu-id="d901e-149">As a result, all commands performed in the transaction are reversed.</span></span>

<span data-ttu-id="d901e-150">最後のコマンドは、 **ToString** メソッドを使用して、結果として得られる $TransactedString の値を文字列として表示します。</span><span class="sxs-lookup"><span data-stu-id="d901e-150">The final command uses the **ToString** method to display the resulting value of $TransactedString as a string.</span></span>
<span data-ttu-id="d901e-151">結果には、トランザクションの外部で行われた変更のみがオブジェクトに適用されたことが示されます。</span><span class="sxs-lookup"><span data-stu-id="d901e-151">The results show that only the changes that were made outside the transaction were applied to the object.</span></span>

## <span data-ttu-id="d901e-152">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d901e-152">PARAMETERS</span></span>

### <span data-ttu-id="d901e-153">-TransactedScript</span><span class="sxs-lookup"><span data-stu-id="d901e-153">-TransactedScript</span></span>
<span data-ttu-id="d901e-154">トランザクションで実行されるスクリプト ブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="d901e-154">Specifies the script block that is run in the transaction.</span></span>
<span data-ttu-id="d901e-155">有効なスクリプト ブロックを中かっこ ( { } ) で囲んで入力します。</span><span class="sxs-lookup"><span data-stu-id="d901e-155">Enter any valid script block enclosed in braces ( { } ).</span></span>
<span data-ttu-id="d901e-156">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="d901e-156">This parameter is required.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d901e-157">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="d901e-157">-UseTransaction</span></span>
<span data-ttu-id="d901e-158">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d901e-158">Includes the command in the active transaction.</span></span>
<span data-ttu-id="d901e-159">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="d901e-159">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="d901e-160">詳細については、「about_transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d901e-160">For more information, see about_transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d901e-161">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d901e-161">CommonParameters</span></span>
<span data-ttu-id="d901e-162">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d901e-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d901e-163">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d901e-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d901e-164">入力</span><span class="sxs-lookup"><span data-stu-id="d901e-164">INPUTS</span></span>

### <span data-ttu-id="d901e-165">なし</span><span class="sxs-lookup"><span data-stu-id="d901e-165">None</span></span>
<span data-ttu-id="d901e-166">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="d901e-166">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="d901e-167">出力</span><span class="sxs-lookup"><span data-stu-id="d901e-167">OUTPUTS</span></span>

### <span data-ttu-id="d901e-168">PSObject</span><span class="sxs-lookup"><span data-stu-id="d901e-168">PSObject</span></span>
<span data-ttu-id="d901e-169">このコマンドレットは、トランザクションの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="d901e-169">This cmdlet returns the result of the transaction.</span></span>

## <span data-ttu-id="d901e-170">注</span><span class="sxs-lookup"><span data-stu-id="d901e-170">NOTES</span></span>

* <span data-ttu-id="d901e-171">*UseTransaction* パラメーターには、アクティブなトランザクションにコマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d901e-171">The *UseTransaction* parameter includes the command in the active transaction.</span></span> <span data-ttu-id="d901e-172">トランザクションで **使用** するコマンドレットは常にトランザクションで使用されるため、このパラメーターは、 **トランザクションを使用** するコマンドを有効にするために必要です。</span><span class="sxs-lookup"><span data-stu-id="d901e-172">Because the **Use-Transaction** cmdlet is always used in transactions, this parameter is required to make any **Use-Transaction** command effective.</span></span>

*

## <span data-ttu-id="d901e-173">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d901e-173">RELATED LINKS</span></span>

[<span data-ttu-id="d901e-174">Complete-Transaction</span><span class="sxs-lookup"><span data-stu-id="d901e-174">Complete-Transaction</span></span>](Complete-Transaction.md)

[<span data-ttu-id="d901e-175">Get-Transaction</span><span class="sxs-lookup"><span data-stu-id="d901e-175">Get-Transaction</span></span>](Get-Transaction.md)

[<span data-ttu-id="d901e-176">Start-Transaction</span><span class="sxs-lookup"><span data-stu-id="d901e-176">Start-Transaction</span></span>](Start-Transaction.md)

[<span data-ttu-id="d901e-177">Undo-Transaction</span><span class="sxs-lookup"><span data-stu-id="d901e-177">Undo-Transaction</span></span>](Undo-Transaction.md)
