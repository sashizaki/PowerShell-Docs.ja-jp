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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365881"
---
# <a name="cmdlet-samples"></a><span data-ttu-id="f2db1-102">コマンドレット サンプル</span><span class="sxs-lookup"><span data-stu-id="f2db1-102">Cmdlet Samples</span></span>

<span data-ttu-id="f2db1-103">このセクションでは、Windows PowerShell 2.0 SDK で提供されるサンプルコードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f2db1-103">This section describes sample code that is provided in the Windows PowerShell 2.0 SDK.</span></span> <span data-ttu-id="f2db1-104">このセクションのトピックからコードをコピーするか、SDK と共にインストールされたソースファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="f2db1-104">You can copy code from the topics in this section, or open the source files installed with the SDK.</span></span> <span data-ttu-id="f2db1-105">[Windows PowerShell 2.0 ソフトウェア開発キット (SDK)](https://www.microsoft.com/en-us/download/details.aspx?id=2560)には、各サンプルの ReadMe ファイル、ソースファイル、および Visual Studio プロジェクトファイルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f2db1-105">The [Windows PowerShell 2.0 Software Development Kit (SDK)](https://www.microsoft.com/en-us/download/details.aspx?id=2560) provides ReadMe files, source files, and Visual Studio project files for each sample.</span></span> <span data-ttu-id="f2db1-106">SDK がインストールされているので、[`<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\`] フォルダーの下にサンプルを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="f2db1-106">With the SDK installed, you can find the samples under the `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\` folder.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f2db1-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f2db1-107">In This Section</span></span>

<span data-ttu-id="f2db1-108">[GetProcessSample01 サンプル](./getprocesssample01-sample.md)このサンプルでは、ローカルコンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f2db1-108">[GetProcessSample01 Sample](./getprocesssample01-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span>

<span data-ttu-id="f2db1-109">[GetProcessSample02 サンプル](./getprocesssample02-sample.md)このサンプルでは、ローカルコンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f2db1-109">[GetProcessSample02 Sample](./getprocesssample02-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="f2db1-110">これには、取得するプロセスを指定するために使用できる Name パラメーターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f2db1-110">It provides a Name parameter that can be used to specify the processes to be retrieved.</span></span>

<span data-ttu-id="f2db1-111">[GetProcessSample03 サンプル](./getprocesssample03-sample.md)このサンプルでは、ローカルコンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f2db1-111">[GetProcessSample03 Sample](./getprocesssample03-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="f2db1-112">このメソッドは、パイプラインからのオブジェクト、またはプロパティ名がパラメーター名と同じであるオブジェクトのプロパティの値を受け取ることができる Name パラメーターを提供します。</span><span class="sxs-lookup"><span data-stu-id="f2db1-112">It provides a Name parameter that can accept an object from the pipeline or a value from a property of an object whose property name is the same as the parameter name.</span></span>

<span data-ttu-id="f2db1-113">[GetProcessSample04 サンプル](./getprocesssample04-sample.md)このサンプルでは、ローカルコンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f2db1-113">[GetProcessSample04 Sample](./getprocesssample04-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="f2db1-114">プロセスの取得中にエラーが発生した場合、終了しないエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="f2db1-114">It generates a nonterminating error if an error occurs while retrieving a process.</span></span>

<span data-ttu-id="f2db1-115">[GetProcessSample05 サンプル](./getprocesssample05-sample.md)このサンプルでは、Get Proc コマンドレットの完全なバージョンを示します。</span><span class="sxs-lookup"><span data-stu-id="f2db1-115">[GetProcessSample05 Sample](./getprocesssample05-sample.md) This sample shows a complete version of the Get-Proc cmdlet.</span></span>

<span data-ttu-id="f2db1-116">[StopProcessSample01 サンプル](./stopprocesssample01-sample.md)このサンプルでは、プロセスを停止する前にユーザーからのフィードバックを要求するコマンドレットを記述する方法と、ユーザーがコマンドレットにオブジェクトを返すことを示す `PassThru` パラメーターを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f2db1-116">[StopProcessSample01 Sample](./stopprocesssample01-sample.md) This sample shows how to write a cmdlet that requests feedback from the user before it attempts to stop a process, and how to implement a `PassThru` parameter that indicates that the user wants the cmdlet to return an object.</span></span>

<span data-ttu-id="f2db1-117">[StopProcessSample02 サンプル](./stopprocesssample02-sample.md)このサンプルでは、ローカルコンピューター上のプロセスを停止している間に、デバッグメッセージ、詳細メッセージ、警告メッセージを書き込むコマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f2db1-117">[StopProcessSample02 Sample](./stopprocesssample02-sample.md) This sample shows how to write a cmdlet that writes debug, verbose, and warning messages while stopping processes on the local computer.</span></span>

<span data-ttu-id="f2db1-118">[StopProcessSample03 サンプル](./stopprocesssample03-sample.md)このサンプルでは、パラメーターにエイリアスがあり、ワイルドカード文字をサポートするコマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f2db1-118">[StopProcessSample03 Sample](./stopprocesssample03-sample.md) This sample shows how to write a cmdlet whose parameters have aliases and that support wildcard characters.</span></span>

<span data-ttu-id="f2db1-119">[StopProcessSample04 サンプル](./stopprocesssample04-sample.md)このサンプルでは、パラメーターセットを宣言し、既定のパラメーターセットを指定し、入力オブジェクトを受け取ることができるコマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f2db1-119">[StopProcessSample04 Sample](./stopprocesssample04-sample.md) This sample shows how to write a cmdlet that declares parameter sets, specifies the default parameter set, and can accept an input object.</span></span>

<span data-ttu-id="f2db1-120">[Events01 サンプル](./events01-sample.md)このサンプルでは、ユーザーが system.servicemodel[によって](/dotnet/api/System.IO.FileSystemWatcher)発生したイベントに登録できるようにするコマンドレットを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f2db1-120">[Events01 Sample](./events01-sample.md) This sample shows how to create a cmdlet that allows the user to register for events raised by [System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher).</span></span> <span data-ttu-id="f2db1-121">このコマンドレットを使用すると、たとえば、特定のディレクトリにファイルが作成されたときに実行するアクションを登録できます。</span><span class="sxs-lookup"><span data-stu-id="f2db1-121">With this cmdlet users can, for example, register an action to execute when a file is created under a specific directory.</span></span> <span data-ttu-id="f2db1-122">このサンプルは、 [Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase)基底クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="f2db1-122">This sample derives from the [Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) base class.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2db1-123">参照</span><span class="sxs-lookup"><span data-stu-id="f2db1-123">See Also</span></span>

[<span data-ttu-id="f2db1-124">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="f2db1-124">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
