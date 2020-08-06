---
title: コマンドレット内でスクリプトを呼び出す方法 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 248ad7e2e35fe53682836d094a391023007fa0b7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784131"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a><span data-ttu-id="93679-102">コマンドレット内でスクリプトを呼び出す方法</span><span class="sxs-lookup"><span data-stu-id="93679-102">How to Invoke Scripts Within a Cmdlet</span></span>

<span data-ttu-id="93679-103">この例は、コマンドレットに指定されたスクリプトを呼び出す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="93679-103">This example shows how to invoke a script that is supplied to a cmdlet.</span></span> <span data-ttu-id="93679-104">スクリプトはコマンドレットによって実行され、その結果は、一連の[システム管理](/dotnet/api/System.Management.Automation.PSObject)オブジェクトのコレクションとしてコマンドレットに返されます。</span><span class="sxs-lookup"><span data-stu-id="93679-104">The script is executed by the cmdlet, and its results are returned to the cmdlet as a collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects.</span></span>

## <a name="to-invoke-a-script-block"></a><span data-ttu-id="93679-105">スクリプトブロックを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="93679-105">To invoke a script block</span></span>

1. <span data-ttu-id="93679-106">コマンドは、スクリプトブロックがコマンドレットに渡されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="93679-106">The command verifies that a script block was supplied to the cmdlet.</span></span> <span data-ttu-id="93679-107">スクリプトブロックが指定されている場合、コマンドは、必要なパラメーターを指定してスクリプトブロックを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="93679-107">If a script block was supplied, the command invokes the script block with its required parameters.</span></span>

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

2. <span data-ttu-id="93679-108">次に、返された一連の[システム](/dotnet/api/System.Management.Automation.PSObject)オブジェクトを反復処理し、必要な操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="93679-108">Then, the script iterates through the returned collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects and perform the necessary operations.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="93679-109">参照</span><span class="sxs-lookup"><span data-stu-id="93679-109">See Also</span></span>

[<span data-ttu-id="93679-110">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="93679-110">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
