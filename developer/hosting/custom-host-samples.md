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
ms.openlocfilehash: 1e58b74cf1c37c70ebfb0f4970cfbf8a8263ec5c
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794146"
---
# <a name="custom-host-samples"></a><span data-ttu-id="5e9be-102">カスタム ホストのサンプル</span><span class="sxs-lookup"><span data-stu-id="5e9be-102">Custom Host Samples</span></span>

<span data-ttu-id="5e9be-103">このセクションには、カスタム ホストを作成するためのサンプル コードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5e9be-103">This section includes sample code for writing a custom host.</span></span> <span data-ttu-id="5e9be-104">Microsoft Visual Studio を使用して、コンソール アプリケーションを作成し、このセクションのトピックから、ホスト アプリケーションにコードをコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="5e9be-104">You can use Microsoft Visual Studio to create a console application and then copy the code from the topics in this section into your host application.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="5e9be-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5e9be-105">In This Section</span></span>

 <span data-ttu-id="5e9be-106">[Host01 というサンプル](./host01-sample.md)このサンプルは、基本的なカスタム ホストを使用するホスト アプリケーションを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5e9be-106">[Host01 Sample](./host01-sample.md) This sample shows how to implement a host application that uses a basic custom host.</span></span>

 <span data-ttu-id="5e9be-107">[Host02 サンプル](./host02-sample.md)このサンプルは、カスタム ホストの実装と共に Windows PowerShell ランタイムを使用するホスト アプリケーションを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5e9be-107">[Host02 Sample](./host02-sample.md) This sample shows how to write a host application that uses the Windows PowerShell runtime along with a custom host implementation.</span></span> <span data-ttu-id="5e9be-108">ホスト アプリケーションは、ドイツ語、実行するホストのカルチャを設定、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットを表示します同じ結果が見るドイツ語で pwrsh.exe、および現在のデータと時刻を出力しを使用します。</span><span class="sxs-lookup"><span data-stu-id="5e9be-108">The host application sets the host culture to German, runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet and displays the results as you would see them using pwrsh.exe, and then prints out the current data and time in German.</span></span>

 <span data-ttu-id="5e9be-109">[Host03 サンプル](./host03-sample.md)このサンプルは、コマンドラインからコマンドを読み取ってや、コマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5e9be-109">[Host03 Sample](./host03-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>

 <span data-ttu-id="5e9be-110">[Host04 サンプル](./host04-sample.md)このサンプルは、コマンドラインからコマンドを読み取ってや、コマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5e9be-110">[Host04 Sample](./host04-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="5e9be-111">このホスト アプリケーションでは、複数選択を指定するための確認メッセージを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="5e9be-111">This host application also supports displaying prompts that allow the user to specify multiple choices.</span></span>

 <span data-ttu-id="5e9be-112">[Host05 サンプル](./host05-sample.md)このサンプルは、コマンドラインからコマンドを読み取ってや、コマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5e9be-112">[Host05 Sample](./host05-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="5e9be-113">このホスト アプリケーションを使用してリモート コンピューターへの呼び出しをサポートすることも、 [Enter-pssession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession)と[Exit-pssession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession)コマンドレット</span><span class="sxs-lookup"><span data-stu-id="5e9be-113">This host application also supports calls to remote computers by using the [Enter-PsSession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) and [Exit-PsSession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession) cmdlets</span></span>

 <span data-ttu-id="5e9be-114">[Host06 サンプル](./host06-sample.md)このサンプルは、コマンドラインからコマンドを読み取ってや、コマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5e9be-114">[Host06 Sample](./host06-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="5e9be-115">さらに、このサンプルでは、トークナイザー API を使用して、ユーザーが入力したテキストの色を指定します。</span><span class="sxs-lookup"><span data-stu-id="5e9be-115">In addition, this sample uses the Tokenizer APIs to specify the color of the text that is entered by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e9be-116">参照</span><span class="sxs-lookup"><span data-stu-id="5e9be-116">See Also</span></span>
