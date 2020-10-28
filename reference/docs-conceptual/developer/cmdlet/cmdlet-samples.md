---
ms.date: 09/13/2016
ms.topic: reference
title: コマンドレット サンプル
description: コマンドレット サンプル
ms.openlocfilehash: 6ee149f611e5af5c45a62363e19e66bf200c0c0a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92668254"
---
# <a name="cmdlet-samples"></a><span data-ttu-id="bf278-103">コマンドレット サンプル</span><span class="sxs-lookup"><span data-stu-id="bf278-103">Cmdlet Samples</span></span>

<span data-ttu-id="bf278-104">このセクションでは、Windows PowerShell 2.0 SDK で提供されるサンプル コードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bf278-104">This section describes sample code that is provided in the Windows PowerShell 2.0 SDK.</span></span> <span data-ttu-id="bf278-105">お客様は、このセクションのトピックからコードをコピーするか、SDK と共にインストールされたソース ファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="bf278-105">You can copy code from the topics in this section, or open the source files installed with the SDK.</span></span> <span data-ttu-id="bf278-106">[Windows PowerShell 2.0 Software Development Kit (SDK)](https://www.microsoft.com/download/details.aspx?id=2560) には、ReadMe ファイル、ソース ファイル、および各サンプル用の Visual Studio プロジェクト ファイルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bf278-106">The [Windows PowerShell 2.0 Software Development Kit (SDK)](https://www.microsoft.com/download/details.aspx?id=2560) provides ReadMe files, source files, and Visual Studio project files for each sample.</span></span> <span data-ttu-id="bf278-107">SDK をインストールしたら、サンプルは `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\` フォルダーに配置されます。</span><span class="sxs-lookup"><span data-stu-id="bf278-107">With the SDK installed, you can find the samples under the `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\` folder.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="bf278-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bf278-108">In This Section</span></span>

<span data-ttu-id="bf278-109">[GetProcessSample01 サンプル](./getprocesssample01-sample.md) このサンプルでは、ローカル コンピューター上のプロセスを取得するコマンドレットの記述方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="bf278-109">[GetProcessSample01 Sample](./getprocesssample01-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span>

<span data-ttu-id="bf278-110">[GetProcessSample02 サンプル](./getprocesssample02-sample.md) このサンプルでは、ローカル コンピューター上のプロセスを取得するコマンドレットの記述方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="bf278-110">[GetProcessSample02 Sample](./getprocesssample02-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="bf278-111">取得するプロセスの指定に使用できる Name パラメーターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bf278-111">It provides a Name parameter that can be used to specify the processes to be retrieved.</span></span>

<span data-ttu-id="bf278-112">[GetProcessSample03 サンプル](./getprocesssample03-sample.md) このサンプルでは、ローカル コンピューター上のプロセスを取得するコマンドレットの記述方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="bf278-112">[GetProcessSample03 Sample](./getprocesssample03-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="bf278-113">パイプラインからのオブジェクト、またはプロパティ名がパラメーター名と同じオブジェクトのプロパティの値を受け取ることができる、Name パラメーターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bf278-113">It provides a Name parameter that can accept an object from the pipeline or a value from a property of an object whose property name is the same as the parameter name.</span></span>

<span data-ttu-id="bf278-114">[GetProcessSample04 サンプル](./getprocesssample04-sample.md) このサンプルでは、ローカル コンピューター上のプロセスを取得するコマンドレットの記述方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="bf278-114">[GetProcessSample04 Sample](./getprocesssample04-sample.md) This sample shows how to write a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="bf278-115">プロセスの取得中にエラーが発生した場合、終了しないエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="bf278-115">It generates a nonterminating error if an error occurs while retrieving a process.</span></span>

<span data-ttu-id="bf278-116">[GetProcessSample05 サンプル](./getprocesssample05-sample.md) このサンプルでは、Get-Proc コマンドレットの完全なバージョンが示されます。</span><span class="sxs-lookup"><span data-stu-id="bf278-116">[GetProcessSample05 Sample](./getprocesssample05-sample.md) This sample shows a complete version of the Get-Proc cmdlet.</span></span>

<span data-ttu-id="bf278-117">[StopProcessSample01 サンプル](./stopprocesssample01-sample.md) このサンプルでは、プロセスを停止する前にユーザーからのフィードバックを要求するコマンドレットの記述方法と、コマンドレットからオブジェクトが返されることをユーザーが必要としていることを示す `PassThru` パラメーターの実装方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="bf278-117">[StopProcessSample01 Sample](./stopprocesssample01-sample.md) This sample shows how to write a cmdlet that requests feedback from the user before it attempts to stop a process, and how to implement a `PassThru` parameter that indicates that the user wants the cmdlet to return an object.</span></span>

<span data-ttu-id="bf278-118">[StopProcessSample02 サンプル](./stopprocesssample02-sample.md) このサンプルでは、ローカル コンピューター上のプロセスを停止している間に、デバッグ、詳細、および警告メッセージを書き込むコマンドレットの記述方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="bf278-118">[StopProcessSample02 Sample](./stopprocesssample02-sample.md) This sample shows how to write a cmdlet that writes debug, verbose, and warning messages while stopping processes on the local computer.</span></span>

<span data-ttu-id="bf278-119">[StopProcessSample03 サンプル](./stopprocesssample03-sample.md) このサンプルでは、パラメーターにエイリアスがあり、ワイルドカード文字がサポートされているコマンドレットの記述方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="bf278-119">[StopProcessSample03 Sample](./stopprocesssample03-sample.md) This sample shows how to write a cmdlet whose parameters have aliases and that support wildcard characters.</span></span>

<span data-ttu-id="bf278-120">[StopProcessSample04 サンプル](./stopprocesssample04-sample.md) このサンプルでは、パラメーター セットを宣言し、既定のパラメーター セットを指定し、入力オブジェクトを受け取ることができるコマンドレットの記述方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="bf278-120">[StopProcessSample04 Sample](./stopprocesssample04-sample.md) This sample shows how to write a cmdlet that declares parameter sets, specifies the default parameter set, and can accept an input object.</span></span>

<span data-ttu-id="bf278-121">[Events01 サンプル](./events01-sample.md) このサンプルでは、ユーザーが [System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher) によって発生したイベントに登録できるようにするコマンドレットの記述方法が示されます。</span><span class="sxs-lookup"><span data-stu-id="bf278-121">[Events01 Sample](./events01-sample.md) This sample shows how to create a cmdlet that allows the user to register for events raised by [System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher).</span></span> <span data-ttu-id="bf278-122">このコマンドレットを使用すると、たとえば、特定のディレクトリにファイルが作成されたときに実行するアクションを登録できます。</span><span class="sxs-lookup"><span data-stu-id="bf278-122">With this cmdlet users can, for example, register an action to execute when a file is created under a specific directory.</span></span> <span data-ttu-id="bf278-123">このサンプルは、[Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) 基底クラスから派生しています。</span><span class="sxs-lookup"><span data-stu-id="bf278-123">This sample derives from the [Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) base class.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf278-124">参照</span><span class="sxs-lookup"><span data-stu-id="bf278-124">See Also</span></span>

[<span data-ttu-id="bf278-125">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="bf278-125">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
