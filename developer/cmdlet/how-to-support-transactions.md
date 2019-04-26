---
title: トランザクションをサポートする方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4732e38c-b1a0-4de7-b6de-75dbde850488
caps.latest.revision: 8
ms.openlocfilehash: c5eea216efd8048aee5768c78c0b48617670f091
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067860"
---
# <a name="how-to-support-transactions"></a><span data-ttu-id="cfda4-102">トランザクションをサポートする方法</span><span class="sxs-lookup"><span data-stu-id="cfda4-102">How to Support Transactions</span></span>

<span data-ttu-id="cfda4-103">この例では、トランザクションのサポートをコマンドレットに追加する基本的なコード要素を示します。</span><span class="sxs-lookup"><span data-stu-id="cfda4-103">This example shows the basic code elements that add support for transactions to a cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cfda4-104">Windows PowerShell がトランザクションを処理する方法の詳細については、次を参照してください。[に関するトランザクション][about_Transactions]します。</span><span class="sxs-lookup"><span data-stu-id="cfda4-104">For more information about how Windows PowerShell handles transactions, see [About Transactions][about_Transactions].</span></span>

## <a name="to-support-transactions"></a><span data-ttu-id="cfda4-105">トランザクションをサポートするには</span><span class="sxs-lookup"><span data-stu-id="cfda4-105">To support transactions</span></span>

1. <span data-ttu-id="cfda4-106">コマンドレットの属性を宣言するときに、コマンドレットは、トランザクションをサポートしていることを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfda4-106">When you declare the Cmdlet attribute, specify that the cmdlet supports transactions.</span></span>
   <span data-ttu-id="cfda4-107">Windows PowerShell コマンドレットでは、トランザクションをサポートするときに追加します、`UseTransaction`パラメーターをコマンドレットを実行した場合。</span><span class="sxs-lookup"><span data-stu-id="cfda4-107">When the cmdlet supports transactions, Windows PowerShell adds the `UseTransaction` parameter to the cmdlet when it is run.</span></span>

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. <span data-ttu-id="cfda4-108">入力処理メソッドのいずれか、追加、`if`ブロック トランザクションが使用可能なかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="cfda4-108">Within one of the input processing methods, add an `if` block to determine if a transaction is available.</span></span>
   <span data-ttu-id="cfda4-109">場合、`if`ステートメントに解決`true`、現在のトランザクションのコンテキスト内でこのステートメント内でアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="cfda4-109">If the `if` statement resolves to `true`, the actions within this statement can be performed within the context of the current transaction.</span></span>

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="cfda4-110">参照</span><span class="sxs-lookup"><span data-stu-id="cfda4-110">See Also</span></span>

[<span data-ttu-id="cfda4-111">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="cfda4-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
