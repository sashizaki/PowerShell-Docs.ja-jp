---
title: コマンドレット内でスクリプトを呼び出す方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc0bc6ce-48a5-4d9c-927e-636bca743e9f
caps.latest.revision: 9
ms.openlocfilehash: 7dcb8bc20ab56225764854f9dc6fdfd858ed7451
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364411"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a>コマンドレット内でスクリプトを呼び出す方法

この例は、コマンドレットに指定されたスクリプトを呼び出す方法を示しています。 スクリプトはコマンドレットによって実行され、その結果は、一連の[システム管理](/dotnet/api/System.Management.Automation.PSObject)オブジェクトのコレクションとしてコマンドレットに返されます。

## <a name="to-invoke-a-script-block"></a>スクリプトブロックを呼び出すには

1. コマンドは、スクリプトブロックがコマンドレットに渡されたことを確認します。 スクリプトブロックが指定されている場合、コマンドは、必要なパラメーターを指定してスクリプトブロックを呼び出します。

    ```csharp
    if (script != null)
    {
      WriteDebug("Executing script block.");

      // Invoke the script block with the required arguments.
      Collection<PSObject> PSObjects =
                     script.Invoke(
                                   line,
                                   simpleMatch,
                                   caseSensitive
                                  );
    ```

2. 次に、返された一連の[システム](/dotnet/api/System.Management.Automation.PSObject)オブジェクトを反復処理し、必要な操作を実行します。

    ```c
    foreach (PSObject psObject in psObjects)
    {
      if (LanguagePrimitives.IsTrue(psObject))
      {
        result = new MatchInfo();
        result.Line = line;
        result.IgnoreCase = !caseSensitive;

        break;
      }
    }

    ```

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
