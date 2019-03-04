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
ms.openlocfilehash: 89ad17257ebac56105a93672317a149515e80d32
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861068"
---
# <a name="windows-powershell02-sample"></a><span data-ttu-id="1ea16-102">Windows PowerShell02 サンプル</span><span class="sxs-lookup"><span data-stu-id="1ea16-102">Windows PowerShell02 Sample</span></span>

<span data-ttu-id="1ea16-103">このサンプルでは、実行空間プールの実行空間を使用してコマンドを非同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ea16-103">This sample shows how to run commands asynchronously by using the runspaces of a runspace pool.</span></span> <span data-ttu-id="1ea16-104">サンプルでは、コマンドの一覧を生成し、必要がある場合、Windows PowerShell エンジンが、プールから、実行空間を開くときにこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1ea16-104">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>

## <a name="requirements"></a><span data-ttu-id="1ea16-105">要件</span><span class="sxs-lookup"><span data-stu-id="1ea16-105">Requirements</span></span>

- <span data-ttu-id="1ea16-106">このサンプルでは、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="1ea16-106">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="1ea16-107">使用例</span><span class="sxs-lookup"><span data-stu-id="1ea16-107">Demonstrates</span></span>

<span data-ttu-id="1ea16-108">このサンプルでは、次の項目を示しています。</span><span class="sxs-lookup"><span data-stu-id="1ea16-108">This sample demonstrates the following:</span></span>

- <span data-ttu-id="1ea16-109">実行空間を同時に開く許可の数が最小値と最大 RunspacePool オブジェクトを作成しています。</span><span class="sxs-lookup"><span data-stu-id="1ea16-109">Creating a RunspacePool object with a minimum and maximum number of runspaces allowed to be open at the same time.</span></span>

- <span data-ttu-id="1ea16-110">コマンドの一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="1ea16-110">Creating a list of commands.</span></span>

- <span data-ttu-id="1ea16-111">コマンドを非同期的に実行します。</span><span class="sxs-lookup"><span data-stu-id="1ea16-111">Running the commands asynchronously.</span></span>

- <span data-ttu-id="1ea16-112">呼び出す、 [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces\*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces)メソッドをいくつ実行空間は無料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ea16-112">Calling the [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces\*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) method to see how many runspaces are free.</span></span>

- <span data-ttu-id="1ea16-113">コマンドの出力をキャプチャ、 [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke)メソッド。</span><span class="sxs-lookup"><span data-stu-id="1ea16-113">Capturing the command output with the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

## <a name="example"></a><span data-ttu-id="1ea16-114">例</span><span class="sxs-lookup"><span data-stu-id="1ea16-114">Example</span></span>

<span data-ttu-id="1ea16-115">このサンプルでは、実行空間プールの実行空間を開く方法と非同期的にこれらの実行空間でのコマンドを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1ea16-115">This sample shows how to open the runspaces of a runspace pool, and how to asynchronously run commands in those runspaces.</span></span>

[!code-csharp[PowerShell02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs#L11-L96 "PowerShell02.cs")]

## <a name="see-also"></a><span data-ttu-id="1ea16-116">参照</span><span class="sxs-lookup"><span data-stu-id="1ea16-116">See Also</span></span>

[<span data-ttu-id="1ea16-117">Windows PowerShell ホスト アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="1ea16-117">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)