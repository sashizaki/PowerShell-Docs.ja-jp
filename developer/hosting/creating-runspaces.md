---
title: 実行空間を作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17f323c3-e873-449e-8a28-477f1c6b5e12
caps.latest.revision: 6
ms.openlocfilehash: b4e61600f68521e4e7ab56ceae3349381e88a70a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857908"
---
# <a name="creating-runspaces"></a><span data-ttu-id="80501-102">実行空間を作成する</span><span class="sxs-lookup"><span data-stu-id="80501-102">Creating Runspaces</span></span>

<span data-ttu-id="80501-103">実行空間は、ホスト アプリケーションによって呼び出されるコマンドの動作環境です。</span><span class="sxs-lookup"><span data-stu-id="80501-103">A runspace is the operating environment for the commands that are invoked by a host application.</span></span> <span data-ttu-id="80501-104">この環境には、コマンドが現在存在するデータと現在適用される言語の制限が含まれています。</span><span class="sxs-lookup"><span data-stu-id="80501-104">This environment includes the commands and data that are currently present, and any language restrictions that currently apply.</span></span>

 <span data-ttu-id="80501-105">ホスト アプリケーションでは、使用可能なコアのすべてのコマンドを含む、Windows PowerShell によって提供される既定の実行空間を使用したり、使用可能なコマンドのサブセットのみが含まれるカスタムの実行空間を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="80501-105">Host applications can use the default runspace that is provided by Windows PowerShell, which includes all available core commands, or create a custom runspace that includes only a subset of the available commands.</span></span> <span data-ttu-id="80501-106">作成するカスタマイズされた実行空間を作成する、 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを実行空間に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="80501-106">To create a customized runspace, you create an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object and assign it to your runspace.</span></span>

## <a name="runspace-tasks"></a><span data-ttu-id="80501-107">タスクの実行空間</span><span class="sxs-lookup"><span data-stu-id="80501-107">Runspace tasks</span></span>

1. [<span data-ttu-id="80501-108">InitialSessionState を作成します。</span><span class="sxs-lookup"><span data-stu-id="80501-108">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

2. [<span data-ttu-id="80501-109">制約付き実行空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="80501-109">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)

3. [<span data-ttu-id="80501-110">複数の実行空間を作成します。</span><span class="sxs-lookup"><span data-stu-id="80501-110">Creating multiple runspaces</span></span>](./creating-multiple-runspaces.md)

## <a name="see-also"></a><span data-ttu-id="80501-111">参照</span><span class="sxs-lookup"><span data-stu-id="80501-111">See Also</span></span>
