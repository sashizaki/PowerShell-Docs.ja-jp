---
title: トランザクションをサポートする方法 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 6fda27394091195b589afef5ee53c6d3bec4efc0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786613"
---
# <a name="how-to-support-transactions"></a><span data-ttu-id="ad726-102">トランザクションをサポートする方法</span><span class="sxs-lookup"><span data-stu-id="ad726-102">How to Support Transactions</span></span>

<span data-ttu-id="ad726-103">この例は、コマンドレットにトランザクションのサポートを追加する基本的なコード要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="ad726-103">This example shows the basic code elements that add support for transactions to a cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad726-104">Windows PowerShell によるトランザクションの処理方法の詳細については、「[トランザクションについ][about_Transactions]て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad726-104">For more information about how Windows PowerShell handles transactions, see [About Transactions][about_Transactions].</span></span>

## <a name="to-support-transactions"></a><span data-ttu-id="ad726-105">トランザクションをサポートするには</span><span class="sxs-lookup"><span data-stu-id="ad726-105">To support transactions</span></span>

1. <span data-ttu-id="ad726-106">コマンドレットの属性を宣言する場合は、コマンドレットがトランザクションをサポートするように指定します。</span><span class="sxs-lookup"><span data-stu-id="ad726-106">When you declare the Cmdlet attribute, specify that the cmdlet supports transactions.</span></span>
   <span data-ttu-id="ad726-107">コマンドレットでトランザクションがサポートされている場合は、実行時に Windows PowerShell によって `UseTransaction` コマンドレットにパラメーターが追加されます。</span><span class="sxs-lookup"><span data-stu-id="ad726-107">When the cmdlet supports transactions, Windows PowerShell adds the `UseTransaction` parameter to the cmdlet when it is run.</span></span>

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. <span data-ttu-id="ad726-108">入力処理メソッドの1つで、ブロックを追加して、 `if` トランザクションが使用可能かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad726-108">Within one of the input processing methods, add an `if` block to determine if a transaction is available.</span></span>
   <span data-ttu-id="ad726-109">ステートメントが `if` に解決される場合 `true` 、このステートメント内のアクションは、現在のトランザクションのコンテキスト内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="ad726-109">If the `if` statement resolves to `true`, the actions within this statement can be performed within the context of the current transaction.</span></span>

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a><span data-ttu-id="ad726-110">参照</span><span class="sxs-lookup"><span data-stu-id="ad726-110">See Also</span></span>

[<span data-ttu-id="ad726-111">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="ad726-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
