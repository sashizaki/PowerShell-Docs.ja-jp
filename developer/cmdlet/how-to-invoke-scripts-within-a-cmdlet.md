---
title: コマンドレット内でスクリプトを起動する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc0bc6ce-48a5-4d9c-927e-636bca743e9f
caps.latest.revision: 9
ms.openlocfilehash: 7dcb8bc20ab56225764854f9dc6fdfd858ed7451
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067877"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a>コマンドレット内でスクリプトを呼び出す方法

この例では、コマンドレットに指定されているスクリプトを呼び出す方法を示します。 スクリプトは、コマンドレットによって実行され、結果は、のコレクションとしてコマンドレットに返されます[System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject)オブジェクト。

## <a name="to-invoke-a-script-block"></a>スクリプト ブロックを呼び出す

1. コマンドは、スクリプト ブロックをコマンドレットに渡されたことを確認します。 スクリプト ブロックが指定された場合、コマンドは、必要なパラメーターを持つスクリプト ブロックを起動します。

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

2. スクリプトがの返されたコレクションを反復処理し、 [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject)オブジェクトし、必要な操作を実行します。

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
