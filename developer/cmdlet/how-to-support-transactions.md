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
# <a name="how-to-support-transactions"></a>トランザクションをサポートする方法

この例では、トランザクションのサポートをコマンドレットに追加する基本的なコード要素を示します。

> [!IMPORTANT]
> Windows PowerShell がトランザクションを処理する方法の詳細については、次を参照してください。[に関するトランザクション][about_Transactions]します。

## <a name="to-support-transactions"></a>トランザクションをサポートするには

1. コマンドレットの属性を宣言するときに、コマンドレットは、トランザクションをサポートしていることを指定します。
   Windows PowerShell コマンドレットでは、トランザクションをサポートするときに追加します、`UseTransaction`パラメーターをコマンドレットを実行した場合。

    ```csharp
    [Cmdlet(VerbsCommunications.Send, "GreetingTx",
            SupportsTransactions=true )]
    ```

2. 入力処理メソッドのいずれか、追加、`if`ブロック トランザクションが使用可能なかどうかを判断します。
   場合、`if`ステートメントに解決`true`、現在のトランザクションのコンテキスト内でこのステートメント内でアクションを実行できます。

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
