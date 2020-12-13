---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell02 サンプル
description: Windows PowerShell02 サンプル
ms.openlocfilehash: 61dedd72d93d4000edf9a12f12bbb49fbaeb9f3c
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657363"
---
# <a name="windows-powershell02-sample"></a><span data-ttu-id="15056-103">Windows PowerShell02 サンプル</span><span class="sxs-lookup"><span data-stu-id="15056-103">Windows PowerShell02 Sample</span></span>

<span data-ttu-id="15056-104">このサンプルでは、実行空間プールの実行空間を使用して、コマンドを非同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="15056-104">This sample shows how to run commands asynchronously using the runspaces of a runspace pool.</span></span> <span data-ttu-id="15056-105">このサンプルでは、コマンドの一覧を生成し、それらのコマンドを実行します。 Windows PowerShell エンジンは、必要に応じて、プールから実行空間を開きます。</span><span class="sxs-lookup"><span data-stu-id="15056-105">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>

## <a name="requirements"></a><span data-ttu-id="15056-106">要件</span><span class="sxs-lookup"><span data-stu-id="15056-106">Requirements</span></span>

- <span data-ttu-id="15056-107">このサンプルには、Windows PowerShell 2.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="15056-107">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="15056-108">対象</span><span class="sxs-lookup"><span data-stu-id="15056-108">Demonstrates</span></span>

<span data-ttu-id="15056-109">このサンプルでは、次の方法を示します。</span><span class="sxs-lookup"><span data-stu-id="15056-109">This sample demonstrates the following:</span></span>

- <span data-ttu-id="15056-110">実行空間の最小数と最大数を指定して RunspacePool オブジェクトを作成し、同時に開くことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="15056-110">Creating a RunspacePool object with a minimum and maximum number of runspaces allowed to be open at the same time.</span></span>
- <span data-ttu-id="15056-111">コマンドの一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="15056-111">Creating a list of commands.</span></span>
- <span data-ttu-id="15056-112">コマンドを非同期に実行します。</span><span class="sxs-lookup"><span data-stu-id="15056-112">Running the commands asynchronously.</span></span>
- <span data-ttu-id="15056-113">[Runspacepool. Getavailablerunspaces \*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces)メソッドを呼び出して、解放されている実行空間の数を確認します。</span><span class="sxs-lookup"><span data-stu-id="15056-113">Calling the [System.Management.Automation.Runspaces.Runspacepool.Getavailablerunspaces\*](/dotnet/api/System.Management.Automation.Runspaces.RunspacePool.GetAvailableRunspaces) method to see how many runspaces are free.</span></span>
- <span data-ttu-id="15056-114">コマンドの出力を、system.servicemodel [\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) メソッドを使用してキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="15056-114">Capturing the command output with the [System.Management.Automation.Powershell.Endinvoke\*](/dotnet/api/System.Management.Automation.PowerShell.EndInvoke) method.</span></span>

## <a name="example"></a><span data-ttu-id="15056-115">例</span><span class="sxs-lookup"><span data-stu-id="15056-115">Example</span></span>

<span data-ttu-id="15056-116">このサンプルでは、実行空間プールの実行空間を開く方法と、それらの実行空間でコマンドを非同期に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="15056-116">This sample shows how to open the runspaces of a runspace pool, and how to asynchronously run commands in those runspaces.</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/PowerShell02/PowerShell02.cs" range="11-96":::

## <a name="see-also"></a><span data-ttu-id="15056-117">参照</span><span class="sxs-lookup"><span data-stu-id="15056-117">See Also</span></span>

[<span data-ttu-id="15056-118">Windows PowerShell ホスト アプリケーションを記述する</span><span class="sxs-lookup"><span data-stu-id="15056-118">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
