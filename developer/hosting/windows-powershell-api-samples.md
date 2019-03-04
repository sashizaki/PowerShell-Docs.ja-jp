---
title: Windows PowerShell API のサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82df2cde-ba12-46d2-b6ec-da5455fd9b57
caps.latest.revision: 8
ms.openlocfilehash: a472f07cb24b0de8e5dcdfcaddd2802575318d7a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860778"
---
# <a name="windows-powershell-api-samples"></a><span data-ttu-id="86cbd-102">Windows PowerShell API サンプル</span><span class="sxs-lookup"><span data-stu-id="86cbd-102">Windows PowerShell API Samples</span></span>

<span data-ttu-id="86cbd-103">このセクションには、機能が制限されている実行空間を作成する方法と、実行空間を指定する実行空間プールを使用してコマンドを非同期的に実行する方法を示すサンプル コードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="86cbd-103">This section includes sample code that shows how to create runspaces that restrict functionality, and how to asynchronously run commands by using a runspace pool to supply the runspaces.</span></span> <span data-ttu-id="86cbd-104">Microsoft Visual Studio を使用して、コンソール アプリケーションを作成し、このセクションのトピックから、ホスト アプリケーションにコードをコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="86cbd-104">You can use Microsoft Visual Studio to create a console application and then copy the code from the topics in this section into your host application.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="86cbd-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="86cbd-105">In This Section</span></span>

<span data-ttu-id="86cbd-106">[PowerShell01 サンプル](./windows-powershell01-sample.md)このサンプルは、使用する方法を示します、 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)実行空間の機能を制限するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="86cbd-106">[PowerShell01 Sample](./windows-powershell01-sample.md) This sample shows how to use an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to limit the functionality of a runspace.</span></span> <span data-ttu-id="86cbd-107">このサンプルの出力は、実行空間、プライベートとしてコマンドレットをマークする方法、追加する方法と削除コマンドレットとプロバイダーの言語モードを制限する方法を示します、プロキシ コマンドを追加する方法。</span><span class="sxs-lookup"><span data-stu-id="86cbd-107">The output of this sample demonstrates how to restrict the language mode of the runspace, how to mark a cmdlet as private, how to add and remove cmdlets and providers, how to add a proxy command, and more.</span></span>

<span data-ttu-id="86cbd-108">[PowerShell02 サンプル](./windows-powershell02-sample.md)実行空間プールの実行空間を使用してコマンドを非同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="86cbd-108">[PowerShell02 Sample](./windows-powershell02-sample.md) This sample shows how to run commands asynchronously by using the runspaces of a runspace pool.</span></span> <span data-ttu-id="86cbd-109">サンプルでは、コマンドの一覧を生成し、必要がある場合、Windows PowerShell エンジンが、プールから、実行空間を開くときにこれらのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="86cbd-109">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>