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
# <a name="how-to-support-transactions"></a>トランザクションをサポートする方法

この例は、コマンドレットにトランザクションのサポートを追加する基本的なコード要素を示しています。

> [!IMPORTANT]
> Windows PowerShell によるトランザクションの処理方法の詳細については、「[トランザクションについ][about_Transactions]て」を参照してください。

## <a name="to-support-transactions"></a>トランザクションをサポートするには

1. コマンドレットの属性を宣言する場合は、コマンドレットがトランザクションをサポートするように指定します。
   コマンドレットでトランザクションがサポートされている場合、Windows PowerShell を実行すると、コマンドレットに `UseTransaction` パラメーターが追加されます。

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. 入力処理メソッドのいずれかで、`if` ブロックを追加して、トランザクションが使用可能かどうかを確認します。
   @No__t-0 ステートメントが `true` に解決された場合、このステートメント内のアクションは現在のトランザクションのコンテキスト内で実行できます。

    ```csharp
    if (TransactionAvailable())
    {
      using (CurrentPSTransaction)
      {
        WriteObject("Hello " + name + "  from within a transaction.");
      }
    }
    ```

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)

<!-- External URLs -->

[about_Transactions]: /powershell/module/Microsoft.PowerShell.Core/About/about_Transactions
