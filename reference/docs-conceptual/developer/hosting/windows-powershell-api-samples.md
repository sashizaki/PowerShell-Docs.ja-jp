---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell API サンプル
description: Windows PowerShell API サンプル
ms.openlocfilehash: b6336ae7a2abb98cbbaa69bf6c9455f893db2d94
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92657544"
---
# <a name="windows-powershell-api-samples"></a><span data-ttu-id="8b2bf-103">Windows PowerShell API サンプル</span><span class="sxs-lookup"><span data-stu-id="8b2bf-103">Windows PowerShell API Samples</span></span>

<span data-ttu-id="8b2bf-104">このセクションには、機能を制限する実行空間を作成する方法と、実行空間プールを使用して実行空間を提供するコマンドを非同期で実行する方法を示すサンプルコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8b2bf-104">This section includes sample code that shows how to create runspaces that restrict functionality, and how to asynchronously run commands by using a runspace pool to supply the runspaces.</span></span> <span data-ttu-id="8b2bf-105">Microsoft Visual Studio を使用してコンソールアプリケーションを作成し、このセクションのトピックからホストアプリケーションにコードをコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="8b2bf-105">You can use Microsoft Visual Studio to create a console application and then copy the code from the topics in this section into your host application.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8b2bf-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8b2bf-106">In This Section</span></span>

<span data-ttu-id="8b2bf-107">[PowerShell01 サンプル](./windows-powershell01-sample.md) このサンプルでは、 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) オブジェクトを使用して、実行空間の機能を制限する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8b2bf-107">[PowerShell01 Sample](./windows-powershell01-sample.md) This sample shows how to use an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to limit the functionality of a runspace.</span></span> <span data-ttu-id="8b2bf-108">このサンプルの出力では、実行空間の言語モードを制限する方法、コマンドレットをプライベートとしてマークする方法、コマンドレットとプロバイダーを追加および削除する方法、プロキシコマンドを追加する方法などについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8b2bf-108">The output of this sample demonstrates how to restrict the language mode of the runspace, how to mark a cmdlet as private, how to add and remove cmdlets and providers, how to add a proxy command, and more.</span></span>

<span data-ttu-id="8b2bf-109">[PowerShell02 サンプル](./windows-powershell02-sample.md) このサンプルでは、実行空間プールの実行空間を使用して、コマンドを非同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8b2bf-109">[PowerShell02 Sample](./windows-powershell02-sample.md) This sample shows how to run commands asynchronously by using the runspaces of a runspace pool.</span></span> <span data-ttu-id="8b2bf-110">このサンプルでは、コマンドの一覧を生成し、それらのコマンドを実行します。 Windows PowerShell エンジンは、必要に応じて、プールから実行空間を開きます。</span><span class="sxs-lookup"><span data-stu-id="8b2bf-110">The sample generates a list of commands, and then runs those commands while the Windows PowerShell engine opens a runspace from the pool when it is needed.</span></span>
