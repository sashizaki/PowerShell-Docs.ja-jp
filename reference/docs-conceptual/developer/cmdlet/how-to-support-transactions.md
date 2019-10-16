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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365541"
---
# <a name="how-to-support-transactions"></a><span data-ttu-id="ecde9-102">トランザクションをサポートする方法</span><span class="sxs-lookup"><span data-stu-id="ecde9-102">How to Support Transactions</span></span>

<span data-ttu-id="ecde9-103">この例は、コマンドレットにトランザクションのサポートを追加する基本的なコード要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="ecde9-103">This example shows the basic code elements that add support for transactions to a cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ecde9-104">Windows PowerShell によるトランザクションの処理方法の詳細については、「[トランザクションについ][about_Transactions]て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecde9-104">For more information about how Windows PowerShell handles transactions, see [About Transactions][about_Transactions].</span></span>

## <a name="to-support-transactions"></a><span data-ttu-id="ecde9-105">トランザクションをサポートするには</span><span class="sxs-lookup"><span data-stu-id="ecde9-105">To support transactions</span></span>

1. <span data-ttu-id="ecde9-106">コマンドレットの属性を宣言する場合は、コマンドレットがトランザクションをサポートするように指定します。</span><span class="sxs-lookup"><span data-stu-id="ecde9-106">When you declare the Cmdlet attribute, specify that the cmdlet supports transactions.</span></span>
   <span data-ttu-id="ecde9-107">コマンドレットでトランザクションがサポートされている場合、Windows PowerShell を実行すると、コマンドレットに `UseTransaction` パラメーターが追加されます。</span><span class="sxs-lookup"><span data-stu-id="ecde9-107">When the cmdlet supports transactions, Windows PowerShell adds the `UseTransaction` parameter to the cmdlet when it is run.</span></span>

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. <span data-ttu-id="ecde9-108">入力処理メソッドのいずれかで、`if` ブロックを追加して、トランザクションが使用可能かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ecde9-108">Within one of the input processing methods, add an `if` block to determine if a transaction is available.</span></span>
   <span data-ttu-id="ecde9-109">@No__t-0 ステートメントが `true` に解決された場合、このステートメント内のアクションは現在のトランザクションのコンテキスト内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="ecde9-109">If the `if` statement resolves to `true`, the actions within this statement can be performed within the context of the current transaction.</span></span>

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="ecde9-110">参照</span><span class="sxs-lookup"><span data-stu-id="ecde9-110">See Also</span></span>

[<span data-ttu-id="ecde9-111">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="ecde9-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
