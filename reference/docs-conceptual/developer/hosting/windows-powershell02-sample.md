---
title: Windows PowerShell02 サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 92492a7e-257d-47d3-b119-89df3c5545e8
caps.latest.revision: 9
ms.openlocfilehash: db7ff3a2dbd92f562379d206db494ab92ef08736
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367301"
---
# <a name="windows-powershell02-sample"></a><span data-ttu-id="3872a-102">Windows PowerShell02 サンプル</span><span class="sxs-lookup"><span data-stu-id="3872a-102">Windows PowerShell02 Sample</span></span>

<span data-ttu-id="3872a-103">このサンプルでは、実行空間プールの実行空間を使用して、コマンドを非同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3872a-103">This sample shows how to run commands asynchronously by using the runspaces of a runspace pool.</span></span> <span data-ttu-id="3872a-104">このサンプルでは、コマンドの一覧を生成し、それらのコマンドを実行します。 Windows PowerShell エンジンは、必要に応じて、プールから実行空間を開きます。</span><span class="sxs-lookup"><span data-stu-id="3872a-104">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>

## <a name="requirements"></a><span data-ttu-id="3872a-105">要件</span><span class="sxs-lookup"><span data-stu-id="3872a-105">Requirements</span></span>

- <span data-ttu-id="3872a-106">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="3872a-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="3872a-107">使用例</span><span class="sxs-lookup"><span data-stu-id="3872a-107">Demonstrates</span></span>

<span data-ttu-id="3872a-108">このサンプルは、次の操作方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3872a-108">This sample demonstrates the following:</span></span>

- <span data-ttu-id="3872a-109">実行空間の最小数と最大数を指定して RunspacePool オブジェクトを作成し、同時に開くことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="3872a-109">Creating a RunspacePool object with a minimum and maximum number of runspaces allowed to be open at the same time.</span></span>

- <span data-ttu-id="3872a-110">コマンドの一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="3872a-110">Creating a list of commands.</span></span>

- <span data-ttu-id="3872a-111">コマンドを非同期に実行します。</span><span class="sxs-lookup"><span data-stu-id="3872a-111">Running the commands asynchronously.</span></span>

- <span data-ttu-id="3872a-112">[Runspacepool. Getavailablerunspaces \*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces)メソッドを呼び出して、解放されている実行空間の数を確認します。</span><span class="sxs-lookup"><span data-stu-id="3872a-112">Calling the [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces\*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) method to see how many runspaces are free.</span></span>

- <span data-ttu-id="3872a-113">コマンドの出力を、system.servicemodel [\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke)メソッドを使用してキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="3872a-113">Capturing the command output with the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

## <a name="example"></a><span data-ttu-id="3872a-114">例</span><span class="sxs-lookup"><span data-stu-id="3872a-114">Example</span></span>

<span data-ttu-id="3872a-115">このサンプルでは、実行空間プールの実行空間を開く方法と、それらの実行空間でコマンドを非同期に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3872a-115">This sample shows how to open the runspaces of a runspace pool, and how to asynchronously run commands in those runspaces.</span></span>

[!code-csharp[PowerShell02.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs#L11-L96 "PowerShell02.cs")]

## <a name="see-also"></a><span data-ttu-id="3872a-116">参照</span><span class="sxs-lookup"><span data-stu-id="3872a-116">See Also</span></span>

[<span data-ttu-id="3872a-117">Windows PowerShell ホストアプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="3872a-117">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
