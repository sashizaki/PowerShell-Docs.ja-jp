---
title: カスタム ホストのサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55aee25b-bbcb-4d41-a4c0-fb8e30c4cdc1
caps.latest.revision: 11
ms.openlocfilehash: 2d88847e17371c4c04b783569fbd983218b6791b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858618"
---
# <a name="custom-host-samples"></a><span data-ttu-id="7c852-102">カスタム ホストのサンプル</span><span class="sxs-lookup"><span data-stu-id="7c852-102">Custom Host Samples</span></span>

<span data-ttu-id="7c852-103">このセクションには、カスタム ホストを作成するためのサンプル コードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7c852-103">This section includes sample code for writing a custom host.</span></span> <span data-ttu-id="7c852-104">Microsoft Visual Studio を使用して、コンソール アプリケーションを作成し、このセクションのトピックから、ホスト アプリケーションにコードをコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="7c852-104">You can use Microsoft Visual Studio to create a console application and then copy the code from the topics in this section into your host application.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7c852-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7c852-105">In This Section</span></span>

 <span data-ttu-id="7c852-106">[Host01 というサンプル](./host01-sample.md)このサンプルは、基本的なカスタム ホストを使用するホスト アプリケーションを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7c852-106">[Host01 Sample](./host01-sample.md) This sample shows how to implement a host application that uses a basic custom host.</span></span>

 <span data-ttu-id="7c852-107">[Host02 サンプル](./host02-sample.md)このサンプルは、カスタム ホストの実装と共に Windows PowerShell ランタイムを使用するホスト アプリケーションを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7c852-107">[Host02 Sample](./host02-sample.md) This sample shows how to write a host application that uses the Windows PowerShell runtime along with a custom host implementation.</span></span> <span data-ttu-id="7c852-108">ホスト アプリケーションは、ドイツ語、実行するホストのカルチャを設定、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットを表示します同じ結果が見るドイツ語で pwrsh.exe、および現在のデータと時刻を出力しを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c852-108">The host application sets the host culture to German, runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet and displays the results as you would see them using pwrsh.exe, and then prints out the current data and time in German.</span></span>
<span data-ttu-id="7c852-109">このサンプルでは、カスタム ホストの実装と共に Windows PowerShell ランタイムを使用するホスト アプリケーションを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7c852-109">This sample shows how to write a host application that uses the Windows PowerShell runtime along with a custom host implementation.</span></span> <span data-ttu-id="7c852-110">ホスト アプリケーションは、ドイツ語、実行するホストのカルチャを設定、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットを表示します同じ結果が見るドイツ語で pwrsh.exe、および現在のデータと時刻を出力しを使用します。</span><span class="sxs-lookup"><span data-stu-id="7c852-110">The host application sets the host culture to German, runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet and displays the results as you would see them using pwrsh.exe, and then prints out the current data and time in German.</span></span>

 <span data-ttu-id="7c852-111">[Host03 サンプル](./host03-sample.md)このサンプルは、コマンドラインからコマンドを読み取ってや、コマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7c852-111">[Host03 Sample](./host03-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>

 <span data-ttu-id="7c852-112">[Host04 サンプル](./host04-sample.md)このサンプルは、コマンドラインからコマンドを読み取ってや、コマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7c852-112">[Host04 Sample](./host04-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="7c852-113">このホスト アプリケーションでは、複数選択を指定するための確認メッセージを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="7c852-113">This host application also supports displaying prompts that allow the user to specify multiple choices.</span></span>

 <span data-ttu-id="7c852-114">[Host05 サンプル](./host05-sample.md)このサンプルは、コマンドラインからコマンドを読み取ってや、コマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7c852-114">[Host05 Sample](./host05-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="7c852-115">このホスト アプリケーションを使用してリモート コンピューターへの呼び出しをサポートすることも、 [Enter-pssession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession)と[Exit-pssession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession)コマンドレットはこのサンプルは、対話型コンソール ベースのホスト アプリケーションを構築する方法を示しています。コマンドを実行し、結果をコンソールに表示をコマンドラインからコマンドを読み取っています。</span><span class="sxs-lookup"><span data-stu-id="7c852-115">This host application also supports calls to remote computers by using the [Enter-PsSession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) and [Exit-PsSession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession) cmdlets This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="7c852-116">このホスト アプリケーションを使用してリモート コンピューターへの呼び出しをサポートすることも、 [Enter-pssession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession)と[Exit-pssession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession)コマンドレット</span><span class="sxs-lookup"><span data-stu-id="7c852-116">This host application also supports calls to remote computers by using the [Enter-PsSession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) and [Exit-PsSession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession) cmdlets</span></span>

 <span data-ttu-id="7c852-117">[Host06 サンプル](./host06-sample.md)このサンプルは、コマンドラインからコマンドを読み取ってや、コマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7c852-117">[Host06 Sample](./host06-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="7c852-118">さらに、このサンプルでは、トークナイザー API を使用して、ユーザーが入力したテキストの色を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c852-118">In addition, this sample uses the Tokenizer APIs to specify the color of the text that is entered by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c852-119">参照</span><span class="sxs-lookup"><span data-stu-id="7c852-119">See Also</span></span>
