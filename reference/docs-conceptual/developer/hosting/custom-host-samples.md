---
ms.date: 09/13/2016
ms.topic: reference
title: カスタム ホストのサンプル
description: カスタム ホストのサンプル
ms.openlocfilehash: 939b9f5d6bbc3ccf1ac95343e897ecffef0a2f42
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649320"
---
# <a name="custom-host-samples"></a><span data-ttu-id="bdb69-103">カスタム ホストのサンプル</span><span class="sxs-lookup"><span data-stu-id="bdb69-103">Custom Host Samples</span></span>

<span data-ttu-id="bdb69-104">このセクションには、カスタムホストを作成するためのサンプルコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bdb69-104">This section includes sample code for writing a custom host.</span></span> <span data-ttu-id="bdb69-105">Microsoft Visual Studio を使用してコンソールアプリケーションを作成し、このセクションのトピックからホストアプリケーションにコードをコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="bdb69-105">You can use Microsoft Visual Studio to create a console application and then copy the code from the topics in this section into your host application.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="bdb69-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bdb69-106">In This Section</span></span>

 <span data-ttu-id="bdb69-107">[Vmhost01 サンプル](./host01-sample.md) このサンプルでは、基本的なカスタムホストを使用するホストアプリケーションを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bdb69-107">[Host01 Sample](./host01-sample.md) This sample shows how to implement a host application that uses a basic custom host.</span></span>

 <span data-ttu-id="bdb69-108">[Host02 サンプル](./host02-sample.md) このサンプルでは、Windows PowerShell ランタイムをカスタムホスト実装と共に使用するホストアプリケーションを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bdb69-108">[Host02 Sample](./host02-sample.md) This sample shows how to write a host application that uses the Windows PowerShell runtime along with a custom host implementation.</span></span> <span data-ttu-id="bdb69-109">ホストアプリケーションはホストカルチャをドイツ語に設定し、 [Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) コマンドレットを実行して、pwrsh.exe を使用して表示されるように結果を表示します。次に、現在のデータと時刻をドイツ語で印刷します。</span><span class="sxs-lookup"><span data-stu-id="bdb69-109">The host application sets the host culture to German, runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet and displays the results as you would see them using pwrsh.exe, and then prints out the current data and time in German.</span></span>

 <span data-ttu-id="bdb69-110">[Host03 サンプル](./host03-sample.md) このサンプルでは、コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソールベースのホストアプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bdb69-110">[Host03 Sample](./host03-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>

 <span data-ttu-id="bdb69-111">[Host04 サンプル](./host04-sample.md) このサンプルでは、コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソールベースのホストアプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bdb69-111">[Host04 Sample](./host04-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="bdb69-112">このホスト アプリケーションでは、複数選択を指定するための確認メッセージを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="bdb69-112">This host application also supports displaying prompts that allow the user to specify multiple choices.</span></span>

 <span data-ttu-id="bdb69-113">[Host05 サンプル](./host05-sample.md) このサンプルでは、コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソールベースのホストアプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bdb69-113">[Host05 Sample](./host05-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="bdb69-114">このホストアプリケーションは、次のコマンドレットを使用し[て、リモート](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession)コンピューターへの呼び出しもサポート[します。](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession)</span><span class="sxs-lookup"><span data-stu-id="bdb69-114">This host application also supports calls to remote computers by using the [Enter-PsSession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) and [Exit-PsSession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession) cmdlets</span></span>

 <span data-ttu-id="bdb69-115">[Host06 サンプル](./host06-sample.md) このサンプルでは、コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソールベースのホストアプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bdb69-115">[Host06 Sample](./host06-sample.md) This sample shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span> <span data-ttu-id="bdb69-116">さらに、このサンプルでは、トークナイザー API を使用して、ユーザーが入力したテキストの色を指定します。</span><span class="sxs-lookup"><span data-stu-id="bdb69-116">In addition, this sample uses the Tokenizer APIs to specify the color of the text that is entered by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="bdb69-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="bdb69-117">See Also</span></span>
