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
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a><span data-ttu-id="17f1c-102">コマンドレット内でスクリプトを呼び出す方法</span><span class="sxs-lookup"><span data-stu-id="17f1c-102">How to Invoke Scripts Within a Cmdlet</span></span>

<span data-ttu-id="17f1c-103">この例は、コマンドレットに指定されたスクリプトを呼び出す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="17f1c-103">This example shows how to invoke a script that is supplied to a cmdlet.</span></span> <span data-ttu-id="17f1c-104">スクリプトはコマンドレットによって実行され、その結果は、一連の[システム管理](/dotnet/api/System.Management.Automation.PSObject)オブジェクトのコレクションとしてコマンドレットに返されます。</span><span class="sxs-lookup"><span data-stu-id="17f1c-104">The script is executed by the cmdlet, and its results are returned to the cmdlet as a collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects.</span></span>

## <a name="to-invoke-a-script-block"></a><span data-ttu-id="17f1c-105">スクリプトブロックを呼び出すには</span><span class="sxs-lookup"><span data-stu-id="17f1c-105">To invoke a script block</span></span>

1. <span data-ttu-id="17f1c-106">コマンドは、スクリプトブロックがコマンドレットに渡されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="17f1c-106">The command verifies that a script block was supplied to the cmdlet.</span></span> <span data-ttu-id="17f1c-107">スクリプトブロックが指定されている場合、コマンドは、必要なパラメーターを指定してスクリプトブロックを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="17f1c-107">If a script block was supplied, the command invokes the script block with its required parameters.</span></span>

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

2. <span data-ttu-id="17f1c-108">次に、返された一連の[システム](/dotnet/api/System.Management.Automation.PSObject)オブジェクトを反復処理し、必要な操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="17f1c-108">Then, the script iterates through the returned collection of [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects and perform the necessary operations.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="17f1c-109">参照</span><span class="sxs-lookup"><span data-stu-id="17f1c-109">See Also</span></span>

[<span data-ttu-id="17f1c-110">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="17f1c-110">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
