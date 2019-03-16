---
title: コマンドレットのサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b99d53fc-0af9-426b-82ce-09955e031d4b
caps.latest.revision: 13
ms.openlocfilehash: 0fa4a5f804586c51ae6a36121f9aab041b0989cc
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58058047"
---
# <a name="cmdlet-samples"></a><span data-ttu-id="c6e93-102">コマンドレット サンプル</span><span class="sxs-lookup"><span data-stu-id="c6e93-102">Cmdlet Samples</span></span>

<span data-ttu-id="c6e93-103">このセクションでは、Windows PowerShell 2.0 SDK で提供されているサンプル コードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c6e93-103">This section describes sample code that is provided in the Windows PowerShell 2.0 SDK.</span></span> <span data-ttu-id="c6e93-104">このセクションのトピックでコードをコピーまたは SDK がインストールされたソース ファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="c6e93-104">You can copy code from the topics in this section, or open the source files installed with the SDK.</span></span> <span data-ttu-id="c6e93-105">[Windows PowerShell 2.0 ソフトウェア開発キット (SDK)](https://www.microsoft.com/en-us/download/details.aspx?id=2560) ReadMe ファイル、ソース ファイル、および各サンプルの Visual Studio プロジェクト ファイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="c6e93-105">The [Windows PowerShell 2.0 Software Development Kit (SDK)](https://www.microsoft.com/en-us/download/details.aspx?id=2560) provides ReadMe files, source files, and Visual Studio project files for each sample.</span></span> <span data-ttu-id="c6e93-106">インストールされている sdk では、下のサンプルを見つけることができます、`<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\`フォルダー。</span><span class="sxs-lookup"><span data-stu-id="c6e93-106">With the SDK installed, you can find the samples under the `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\` folder.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c6e93-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c6e93-107">In This Section</span></span>

<span data-ttu-id="c6e93-108">[GetProcessSample01 サンプル](./getprocesssample01-sample.md)このサンプルは、ローカル コンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6e93-108">[GetProcessSample01 Sample](./getprocesssample01-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span>

<span data-ttu-id="c6e93-109">[GetProcessSample02 サンプル](./getprocesssample02-sample.md)このサンプルは、ローカル コンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6e93-109">[GetProcessSample02 Sample](./getprocesssample02-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="c6e93-110">取得するプロセスを指定するために使用する Name パラメーターを提供します。</span><span class="sxs-lookup"><span data-stu-id="c6e93-110">It provides a Name parameter that can be used to specify the processes to be retrieved.</span></span>

<span data-ttu-id="c6e93-111">[GetProcessSample03 サンプル](./getprocesssample03-sample.md)このサンプルは、ローカル コンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6e93-111">[GetProcessSample03 Sample](./getprocesssample03-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="c6e93-112">パイプラインからオブジェクトまたはプロパティの名前は、パラメーター名と同じオブジェクトのプロパティの値を受け入れることができる、名前のパラメーターを提供します。</span><span class="sxs-lookup"><span data-stu-id="c6e93-112">It provides a Name parameter that can accept an object from the pipeline or a value from a property of an object whose property name is the same as the parameter name.</span></span>

<span data-ttu-id="c6e93-113">[GetProcessSample04 サンプル](./getprocesssample04-sample.md)このサンプルは、ローカル コンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6e93-113">[GetProcessSample04 Sample](./getprocesssample04-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="c6e93-114">プロセスの取得中にエラーが発生した場合、終了しないエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c6e93-114">It generates a nonterminating error if an error occurs while retrieving a process.</span></span>

<span data-ttu-id="c6e93-115">[GetProcessSample05 サンプル](./getprocesssample05-sample.md)Get-proc コマンドレットの完全なバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="c6e93-115">[GetProcessSample05 Sample](./getprocesssample05-sample.md) This sample shows a complete version of the Get-Proc cmdlet.</span></span>

<span data-ttu-id="c6e93-116">[StopProcessSample01 サンプル](./stopprocesssample01-sample.md)このサンプルを実装する方法と、プロセスを停止しようとする前に、ユーザーからフィードバックを要求するコマンドレットを記述する方法を示しています、`PassThru`ユーザーを返す、コマンドレットを示すパラメーターです、オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c6e93-116">[StopProcessSample01 Sample](./stopprocesssample01-sample.md) This sample shows how to write a cmdlet that requests feedback from the user before it attempts to stop a process, and how to implement a `PassThru` parameter that indicates that the user wants the cmdlet to return an object.</span></span>

<span data-ttu-id="c6e93-117">[StopProcessSample02 サンプル](./stopprocesssample02-sample.md)をローカル コンピューターのプロセスの停止中に、デバッグ、verbose、および警告メッセージを書き込むためのコマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6e93-117">[StopProcessSample02 Sample](./stopprocesssample02-sample.md) This sample shows how to write a cmdlet that writes debug, verbose, and warning messages while stopping processes on the local computer.</span></span>

<span data-ttu-id="c6e93-118">[StopProcessSample03 サンプル](./stopprocesssample03-sample.md)このサンプルは、パラメーターがあるエイリアスとするコマンドレットを記述する方法を示しています。 ワイルドカード文字をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c6e93-118">[StopProcessSample03 Sample](./stopprocesssample03-sample.md) This sample shows how to write a cmdlet whose parameters have aliases and that support wildcard characters.</span></span>

<span data-ttu-id="c6e93-119">[StopProcessSample04 サンプル](./stopprocesssample04-sample.md)パラメーター セットを宣言で、既定のパラメーターの設定、および入力オブジェクトを受け取ることができますを指定するコマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6e93-119">[StopProcessSample04 Sample](./stopprocesssample04-sample.md) This sample shows how to write a cmdlet that declares parameter sets, specifies the default parameter set, and can accept an input object.</span></span>

<span data-ttu-id="c6e93-120">[Events01 サンプル](./events01-sample.md)によって生成されるイベントを登録するユーザーのためのコマンドレットを作成する方法を示します[System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher)します。</span><span class="sxs-lookup"><span data-stu-id="c6e93-120">[Events01 Sample](./events01-sample.md) This sample shows how to create a cmdlet that allows the user to register for events raised by [System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher).</span></span> <span data-ttu-id="c6e93-121">このコマンドレットを使用した、ユーザーは、特定のディレクトリの下のファイルが作成されるときに実行するアクションを登録することができますなど。</span><span class="sxs-lookup"><span data-stu-id="c6e93-121">With this cmdlet users can, for example, register an action to execute when a file is created under a specific directory.</span></span> <span data-ttu-id="c6e93-122">このサンプルはから派生した、 [Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase)基本クラス。</span><span class="sxs-lookup"><span data-stu-id="c6e93-122">This sample derives from the [Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) base class.</span></span>

## <a name="see-also"></a><span data-ttu-id="c6e93-123">参照</span><span class="sxs-lookup"><span data-stu-id="c6e93-123">See Also</span></span>

[<span data-ttu-id="c6e93-124">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="c6e93-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
