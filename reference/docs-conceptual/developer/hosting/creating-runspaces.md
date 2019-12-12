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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367581"
---
# <a name="creating-runspaces"></a><span data-ttu-id="5af24-102">実行空間を作成する</span><span class="sxs-lookup"><span data-stu-id="5af24-102">Creating Runspaces</span></span>

<span data-ttu-id="5af24-103">実行空間は、ホストアプリケーションによって呼び出されるコマンドのオペレーティング環境です。</span><span class="sxs-lookup"><span data-stu-id="5af24-103">A runspace is the operating environment for the commands that are invoked by a host application.</span></span> <span data-ttu-id="5af24-104">この環境には、現在存在しているコマンドとデータ、および現在適用されているすべての言語制限が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5af24-104">This environment includes the commands and data that are currently present, and any language restrictions that currently apply.</span></span>

 <span data-ttu-id="5af24-105">ホストアプリケーションは、使用可能なすべてのコアコマンドを含む、Windows PowerShell によって提供される既定の実行空間を使用することも、使用可能なコマンドのサブセットのみを含むカスタム実行空間を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5af24-105">Host applications can use the default runspace that is provided by Windows PowerShell, which includes all available core commands, or create a custom runspace that includes only a subset of the available commands.</span></span> <span data-ttu-id="5af24-106">カスタマイズされた実行空間を作成するには、 [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトを作成し、それを実行空間に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="5af24-106">To create a customized runspace, you create an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object and assign it to your runspace.</span></span>

## <a name="runspace-tasks"></a><span data-ttu-id="5af24-107">実行空間タスク</span><span class="sxs-lookup"><span data-stu-id="5af24-107">Runspace tasks</span></span>

1. [<span data-ttu-id="5af24-108">InitialSessionState の作成</span><span class="sxs-lookup"><span data-stu-id="5af24-108">Creating an InitialSessionState</span></span>](./creating-an-initialsessionstate.md)

2. [<span data-ttu-id="5af24-109">制約付き実行空間の作成</span><span class="sxs-lookup"><span data-stu-id="5af24-109">Creating a constrained runspace</span></span>](./creating-a-constrained-runspace.md)

3. [<span data-ttu-id="5af24-110">複数の実行空間の作成</span><span class="sxs-lookup"><span data-stu-id="5af24-110">Creating multiple runspaces</span></span>](./creating-multiple-runspaces.md)

## <a name="see-also"></a><span data-ttu-id="5af24-111">参照</span><span class="sxs-lookup"><span data-stu-id="5af24-111">See Also</span></span>
