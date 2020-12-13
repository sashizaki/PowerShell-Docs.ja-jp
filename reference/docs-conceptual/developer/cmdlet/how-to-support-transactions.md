---
ms.date: 09/13/2016
ms.topic: reference
title: トランザクションをサポートする方法
description: トランザクションをサポートする方法
ms.openlocfilehash: 5691c246830dab9f4808801c04353ebfb2c3e981
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666962"
---
# <a name="how-to-support-transactions"></a><span data-ttu-id="b6219-103">トランザクションをサポートする方法</span><span class="sxs-lookup"><span data-stu-id="b6219-103">How to Support Transactions</span></span>

<span data-ttu-id="b6219-104">この例は、コマンドレットにトランザクションのサポートを追加する基本的なコード要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="b6219-104">This example shows the basic code elements that add support for transactions to a cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6219-105">Windows PowerShell によるトランザクションの処理方法の詳細については、「 [トランザクションについ][about_Transactions]て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6219-105">For more information about how Windows PowerShell handles transactions, see [About Transactions][about_Transactions].</span></span>

## <a name="to-support-transactions"></a><span data-ttu-id="b6219-106">トランザクションをサポートするには</span><span class="sxs-lookup"><span data-stu-id="b6219-106">To support transactions</span></span>

1. <span data-ttu-id="b6219-107">コマンドレットの属性を宣言する場合は、コマンドレットがトランザクションをサポートするように指定します。</span><span class="sxs-lookup"><span data-stu-id="b6219-107">When you declare the Cmdlet attribute, specify that the cmdlet supports transactions.</span></span>
   <span data-ttu-id="b6219-108">コマンドレットでトランザクションがサポートされている場合は、実行時に Windows PowerShell によって `UseTransaction` コマンドレットにパラメーターが追加されます。</span><span class="sxs-lookup"><span data-stu-id="b6219-108">When the cmdlet supports transactions, Windows PowerShell adds the `UseTransaction` parameter to the cmdlet when it is run.</span></span>

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. <span data-ttu-id="b6219-109">入力処理メソッドの1つで、ブロックを追加して、 `if` トランザクションが使用可能かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6219-109">Within one of the input processing methods, add an `if` block to determine if a transaction is available.</span></span>
   <span data-ttu-id="b6219-110">ステートメントが `if` に解決される場合 `true` 、このステートメント内のアクションは、現在のトランザクションのコンテキスト内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="b6219-110">If the `if` statement resolves to `true`, the actions within this statement can be performed within the context of the current transaction.</span></span>

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="b6219-111">参照</span><span class="sxs-lookup"><span data-stu-id="b6219-111">See Also</span></span>

[<span data-ttu-id="b6219-112">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="b6219-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
