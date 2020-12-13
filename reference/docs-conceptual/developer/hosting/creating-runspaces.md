---
ms.date: 09/13/2016
ms.topic: reference
title: 実行空間を作成する
description: 実行空間を作成する
ms.openlocfilehash: c6b2c577e435ec88364b189a0c3d065f54f02525
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649351"
---
# <a name="creating-runspaces"></a><span data-ttu-id="85253-103">実行空間を作成する</span><span class="sxs-lookup"><span data-stu-id="85253-103">Creating Runspaces</span></span>

<span data-ttu-id="85253-104">実行空間は、ホストアプリケーションによって呼び出されるコマンドのオペレーティング環境です。</span><span class="sxs-lookup"><span data-stu-id="85253-104">A runspace is the operating environment for the commands that are invoked by a host application.</span></span> <span data-ttu-id="85253-105">この環境には、現在存在しているコマンドとデータ、および現在適用されているすべての言語制限が含まれます。</span><span class="sxs-lookup"><span data-stu-id="85253-105">This environment includes the commands and data that are currently present, and any language restrictions that currently apply.</span></span>

 <span data-ttu-id="85253-106">ホストアプリケーションは、使用可能なすべてのコアコマンドを含む、Windows PowerShell によって提供される既定の実行空間を使用することも、使用可能なコマンドのサブセットのみを含むカスタム実行空間を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="85253-106">Host applications can use the default runspace that is provided by Windows PowerShell, which includes all available core commands, or create a custom runspace that includes only a subset of the available commands.</span></span> <span data-ttu-id="85253-107">カスタマイズされた実行空間を作成するには、 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) オブジェクトを作成し、実行空間に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="85253-107">To create a customized runspace, you create an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object and assign it to your runspace.</span></span>

## <a name="runspace-tasks"></a><span data-ttu-id="85253-108">実行空間タスク</span><span class="sxs-lookup"><span data-stu-id="85253-108">Runspace tasks</span></span>

1. [<span data-ttu-id="85253-109">InitialSessionState を作成する</span><span class="sxs-lookup"><span data-stu-id="85253-109">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

2. [<span data-ttu-id="85253-110">制約付き実行空間を作成する</span><span class="sxs-lookup"><span data-stu-id="85253-110">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)

3. [<span data-ttu-id="85253-111">複数の実行空間を作成する</span><span class="sxs-lookup"><span data-stu-id="85253-111">Creating multiple runspaces</span></span>](./creating-multiple-runspaces.md)

## <a name="see-also"></a><span data-ttu-id="85253-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="85253-112">See Also</span></span>
