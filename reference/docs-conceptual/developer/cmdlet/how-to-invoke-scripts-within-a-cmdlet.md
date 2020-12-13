---
ms.date: 09/13/2016
ms.topic: reference
title: コマンドレット内でスクリプトを呼び出す方法
description: コマンドレット内でスクリプトを呼び出す方法
ms.openlocfilehash: f4a43a1e1240854e57deac5721e1e070c1a45a51
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667030"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a><span data-ttu-id="e6bc8-103">コマンドレット内でスクリプトを呼び出す方法</span><span class="sxs-lookup"><span data-stu-id="e6bc8-103">How to Invoke Scripts Within a Cmdlet</span></span>

<span data-ttu-id="e6bc8-104">この例は、コマンドレットに指定されたスクリプトを呼び出す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e6bc8-104">This example shows how to invoke a script that is supplied to a cmdlet.</span></span> <span data-ttu-id="e6bc8-105">スクリプトはコマンドレットによって実行され、その結果は、一連の [システム管理](/dotnet/api/System.Management.Automation.PSObject) オブジェクトのコレクションとしてコマンドレットに返されます。</span><span class="sxs-lookup"><span data-stu-id="e6bc8-105">The script is executed by the cmdlet, and its results are returned to the cmdlet as a collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects.</span></span>

## <a name="to-invoke-a-script-block"></a><span data-ttu-id="e6bc8-106">スクリプトブロックを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="e6bc8-106">To invoke a script block</span></span>

1. <span data-ttu-id="e6bc8-107">コマンドは、スクリプトブロックがコマンドレットに渡されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6bc8-107">The command verifies that a script block was supplied to the cmdlet.</span></span> <span data-ttu-id="e6bc8-108">スクリプトブロックが指定されている場合、コマンドは、必要なパラメーターを指定してスクリプトブロックを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e6bc8-108">If a script block was supplied, the command invokes the script block with its required parameters.</span></span>

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

2. <span data-ttu-id="e6bc8-109">次に、返された一連の [システム](/dotnet/api/System.Management.Automation.PSObject) オブジェクトを反復処理し、必要な操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="e6bc8-109">Then, the script iterates through the returned collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects and perform the necessary operations.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e6bc8-110">参照</span><span class="sxs-lookup"><span data-stu-id="e6bc8-110">See Also</span></span>

[<span data-ttu-id="e6bc8-111">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="e6bc8-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
