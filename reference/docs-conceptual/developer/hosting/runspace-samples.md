---
title: 実行空間のサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c92a6d3d-8d34-4a76-bdc3-dea923d9858e
caps.latest.revision: 17
ms.openlocfilehash: e24d40746da91f60aaf2af655ddcadc88ab6a4db
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72361001"
---
# <a name="runspace-samples"></a><span data-ttu-id="782fe-102">実行空間のサンプル</span><span class="sxs-lookup"><span data-stu-id="782fe-102">Runspace Samples</span></span>

<span data-ttu-id="782fe-103">このセクションには、さまざまな種類の実行空間を使用してコマンドを同期および非同期で実行する方法を示すサンプルコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="782fe-103">This section includes sample code that shows how to use different types of runspaces to run commands synchronously and asynchronously.</span></span> <span data-ttu-id="782fe-104">Microsoft Visual Studio を使用してコンソールアプリケーションを作成し、このセクションのトピックからホストアプリケーションにコードをコピーすることができます。</span><span class="sxs-lookup"><span data-stu-id="782fe-104">You can use Microsoft Visual Studio to create a console application and then copy the code from the topics in this section into your host application.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="782fe-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="782fe-105">In This Section</span></span>

> [!NOTE]
> <span data-ttu-id="782fe-106">カスタムホストインターフェイスを作成するホストアプリケーションのサンプルについては、「[カスタムホストのサンプル](./custom-host-samples.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="782fe-106">For samples of host applications that create custom host interfaces, see [Custom Host Samples](./custom-host-samples.md).</span></span>

 <span data-ttu-id="782fe-107">[Runspace01 サンプル](./runspace01-sample.md)このサンプルでは、 [System. Powershell](/dotnet/api/system.management.automation.powershell)クラスを使用して、 [Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットを同期的に実行し、出力をコンソールウィンドウに表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="782fe-107">[Runspace01 Sample](./runspace01-sample.md) This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet synchronously and display its output in a console window.</span></span>

 <span data-ttu-id="782fe-108">[Runspace02 サンプル](./runspace02-sample.md)このサンプル[では、system.servicemodel クラスを](/dotnet/api/system.management.automation.powershell)使用して、 [Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)および[Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object)コマンドレットを同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="782fe-108">[Runspace02 Sample](./runspace02-sample.md) This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlets synchronously.</span></span> <span data-ttu-id="782fe-109">これらのコマンドの結果[は、system.string コントロールを](/dotnet/api/System.Windows.Forms.DataGridView)使用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="782fe-109">The results of these commands is displayed by using a [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView) control.</span></span>

 <span data-ttu-id="782fe-110">[Runspace03 サンプル](./runspace03-sample.md)このサンプルでは、 [System. Powershell](/dotnet/api/system.management.automation.powershell)クラスを使用してスクリプトを同期的に実行する方法と、終了しないエラーを処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="782fe-110">[Runspace03 Sample](./runspace03-sample.md) This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run a script synchronously, and how to handle non-terminating errors.</span></span> <span data-ttu-id="782fe-111">このスクリプトはプロセス名の一覧を受信し、これらのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="782fe-111">The script receives a list of process names and then retrieves those processes.</span></span> <span data-ttu-id="782fe-112">スクリプトの実行時に生成された終了しないエラーを含む、スクリプトの結果がコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="782fe-112">The results of the script, including any non-terminating errors that were generated when running the script, are displayed in a console window.</span></span>

 <span data-ttu-id="782fe-113">[Runspace04 サンプル](./runspace04-sample.md)このサンプルでは、 [Powershell](/dotnet/api/system.management.automation.powershell)クラスを使用してコマンドを実行する方法と、コマンドの実行時にスローされる終了エラーをキャッチする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="782fe-113">[Runspace04 Sample](./runspace04-sample.md) This sample shows how to use the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) class to run commands, and how to catch terminating errors that are thrown when running the commands.</span></span> <span data-ttu-id="782fe-114">2 つのコマンドが実行され、最後のコマンドには無効なパラメーターの引数が渡されます。</span><span class="sxs-lookup"><span data-stu-id="782fe-114">Two commands are run, and the last command is passed a parameter argument that is not valid.</span></span> <span data-ttu-id="782fe-115">その結果、オブジェクトは返されず、終了エラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="782fe-115">As a result no objects are returned and a terminating error is thrown.</span></span>

 <span data-ttu-id="782fe-116">[Runspace05 サンプル](./runspace05-sample.md)このサンプルでは、 [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトにスナップインを追加して、実行空間を開いたときにスナップインのコマンドレットを使用できるようにする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="782fe-116">[Runspace05 Sample](./runspace05-sample.md) This sample shows how to add a snap-in to an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object so that the cmdlet of the snap-in is available when the runspace is opened.</span></span> <span data-ttu-id="782fe-117">スナップインには、 [GetProcessSample01 サンプル](../cmdlet/getprocesssample01-sample.md)で定義されている Get Proc コマンドレットが用意されています。このコマンドレットは、 [System. Powershell](/dotnet/api/system.management.automation.powershell)オブジェクトを使用して同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="782fe-117">The snap-in provides a Get-Proc cmdlet (defined by the [GetProcessSample01 Sample](../cmdlet/getprocesssample01-sample.md)) that is run synchronously using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

 <span data-ttu-id="782fe-118">[Runspace06 サンプル](./runspace06-sample.md)このサンプルでは、実行空間が開かれたときにモジュールが読み込まれるように、 [Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトにモジュールを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="782fe-118">[Runspace06 Sample](./runspace06-sample.md) This sample shows how to add a module to an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object so that the module is loaded when the runspace is opened.</span></span> <span data-ttu-id="782fe-119">モジュールは、 [GetProcessSample02 サンプル](../cmdlet/getprocesssample02-sample.md)で定義されている Get Proc コマンドレットを提供します。これ[は、オブジェクトを](/dotnet/api/system.management.automation.powershell)使用して同期的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="782fe-119">The module provides a Get-Proc cmdlet (defined by the [GetProcessSample02 Sample](../cmdlet/getprocesssample02-sample.md)) that is run synchronously using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

 <span data-ttu-id="782fe-120">[Runspace07 サンプル](./runspace07-sample.md)このサンプルでは、実行空間を作成し、その実行空間を使用して、[複数のコマンド](/dotnet/api/system.management.automation.powershell)レットを同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="782fe-120">[Runspace07 Sample](./runspace07-sample.md) This sample shows how to create a runspace, and then use that runspace to run two cmdlets synchronously by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

 <span data-ttu-id="782fe-121">[Runspace08 サンプル](./runspace08-sample.md)このサンプルでは、コマンドと引数を、[システムの管理](/dotnet/api/system.management.automation.powershell)オブジェクトのパイプラインに追加する方法と、コマンドを同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="782fe-121">[Runspace08 Sample](./runspace08-sample.md) This sample shows how to add commands and arguments to the pipeline of a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object and how to run the commands synchronously.</span></span>

 <span data-ttu-id="782fe-122">[Runspace09 サンプル](./runspace09-sample.md)このサンプルでは、スクリプトを[システム](/dotnet/api/system.management.automation.powershell)のパイプラインに追加する方法と、スクリプトを非同期で実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="782fe-122">[Runspace09 Sample](./runspace09-sample.md) This sample shows how to add a script to the pipeline of a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object and how to run the script asynchronously.</span></span> <span data-ttu-id="782fe-123">イベントはスクリプトの出力を処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="782fe-123">Events are used to handle the output of the script.</span></span>

 <span data-ttu-id="782fe-124">[Runspace10 サンプル](./runspace10-sample.md)このサンプルでは、初期セッションの既定の状態を作成する方法、コマンドレットを[Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)に追加する方法、初期セッション状態を使用する実行空間を作成する方法、およびを使用してコマンドを実行する方法を示します。[System. Automation. Powershell](/dotnet/api/system.management.automation.powershell)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="782fe-124">[Runspace10 Sample](./runspace10-sample.md) This sample shows how to create a default initial session state, how to add a cmdlet to the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState), how to create a runspace that uses the initial session state, and how to run the command by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

 <span data-ttu-id="782fe-125">[Runspace11 サンプル](./runspace11-sample.md)これは、既存のコマンドレットを呼び出すが、使用可能なパラメーターのセットを制限するプロキシコマンドを作成するために、 [system.object クラスを](/dotnet/api/System.Management.Automation.ProxyCommand)使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="782fe-125">[Runspace11 Sample](./runspace11-sample.md) This shows how to use the [System.Management.Automation.Proxycommand](/dotnet/api/System.Management.Automation.ProxyCommand) class to create a proxy command that calls an existing cmdlet, but restricts the set of available parameters.</span></span> <span data-ttu-id="782fe-126">このプロキシ コマンドは、制約付き実行空間の作成に使用される最初のセッション状態に追加されます。</span><span class="sxs-lookup"><span data-stu-id="782fe-126">The proxy command is then added to an initial session state that is used to create a constrained runspace.</span></span> <span data-ttu-id="782fe-127">つまり、ユーザーはプロキシ コマンドを使用しないとコマンドレットの機能にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="782fe-127">This means that the user can access the functionality of the cmdlet only through the proxy command.</span></span>

## <a name="see-also"></a><span data-ttu-id="782fe-128">参照</span><span class="sxs-lookup"><span data-stu-id="782fe-128">See Also</span></span>