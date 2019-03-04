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
ms.openlocfilehash: 4b4d5645785b751eb1390e196f5b9437b4a1e13b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855838"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a>コマンドレット内でスクリプトを呼び出す方法

この例では、コマンドレットに指定されているスクリプトを呼び出す方法を示します。 スクリプトは、コマンドレットによって実行され、結果は、のコレクションとしてコマンドレットに返されます[System.Management.Automation.Psobject](/dotnet/api/System.Management.Automation.PSObject)オブジェクト。

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

2. スクリプトがの返されたコレクションを反復処理し、 [System.Management.Automation.Psobject](/dotnet/api/System.Management.Automation.PSObject)オブジェクトし、必要な操作を実行します。

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
