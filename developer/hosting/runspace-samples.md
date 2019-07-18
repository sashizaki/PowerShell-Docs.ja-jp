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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082738"
---
# <a name="runspace-samples"></a>実行空間のサンプル

このセクションには、さまざまな種類の実行空間を使用して、同期および非同期のコマンドを実行する方法を示すサンプル コードが含まれています。 Microsoft Visual Studio を使用して、コンソール アプリケーションを作成し、このセクションのトピックから、ホスト アプリケーションにコードをコピーすることができます。

## <a name="in-this-section"></a>このセクションの内容

> [!NOTE]
> カスタム ホスト インターフェイスを作成するホスト アプリケーションのサンプルは、次を参照してください。[カスタム ホスト サンプル](./custom-host-samples.md)します。

 [Runspace01 サンプル](./runspace01-sample.md)このサンプルは、使用する方法を示します、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)を実行するクラス、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレット同期的に、コンソールでその出力を表示ウィンドウです。

 [Runspace02 サンプル](./runspace02-sample.md)このサンプルは、使用する方法を示します、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)を実行するクラス、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)と[Sort-object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object)コマンドレットに同期的にします。 使用してこれらのコマンドの結果が表示されます、 [System.Windows.Forms.Datagridview](/dotnet/api/System.Windows.Forms.DataGridView)コントロール。

 [Runspace03 サンプル](./runspace03-sample.md)このサンプルは、使用する方法を示します、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)未終了エラーを処理する方法とスクリプトを同期的に実行するクラス。 このスクリプトはプロセス名の一覧を受信し、これらのプロセスを取得します。 スクリプトの実行時に生成された終了しないエラーを含む、スクリプトの結果がコンソール ウィンドウに表示されます。

 [Runspace04 サンプル](./runspace04-sample.md)このサンプルは、使用する方法を示します、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)クラスのコマンドを実行して、コマンドを実行している場合にスローされる終了エラーをキャッチする方法。 2 つのコマンドが実行され、最後のコマンドには無効なパラメーターの引数が渡されます。 その結果オブジェクトは返されず、終了エラーがスローされます。

 [Runspace05 サンプル](./runspace05-sample.md)このサンプルは、スナップインを追加する方法を示します、 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトの実行空間が開いたときに、スナップインのコマンドレットを使用できるようにします。 スナップインで Get-proc コマンドレットを提供します (によって定義された、 [GetProcessSample01 サンプル](../cmdlet/getprocesssample01-sample.md)) を使用して同期的に実行される、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)オブジェクト。

 [Runspace06 サンプル](./runspace06-sample.md)モジュールを追加する方法を示します、 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)オブジェクトの実行空間が開かれたときに、モジュールが読み込まれるようにします。 Get-proc コマンドレットを提供するモジュール (によって定義された、 [GetProcessSample02 サンプル](../cmdlet/getprocesssample02-sample.md)) を使用して同期的に実行される、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)オブジェクト。

 [Runspace07 サンプル](./runspace07-sample.md)実行空間を作成し、その実行空間を使用して、2 つのコマンドレットを使用して、同期的に実行する方法を示します、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)オブジェクト。

 [Runspace08 サンプル](./runspace08-sample.md)このサンプルのパイプラインにコマンドと引数を追加する方法を示しています、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)オブジェクトと同期的に、コマンドを実行する方法。

 [Runspace09 サンプル](./runspace09-sample.md)このサンプルのパイプラインにスクリプトを追加する方法を示しています、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)オブジェクトと、スクリプトを非同期的に実行する方法。 イベントはスクリプトの出力を処理するために使用されます。

 [Runspace10 サンプル](./runspace10-sample.md)このサンプルは、既定の最初のセッション状態を作成する方法を示しています追加のコマンドレットを使用する方法、 [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)、使用する実行空間を作成する方法、。最初のセッションの状態とを使用して、コマンドを実行する方法、 [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell)オブジェクト。

 [Runspace11 サンプル](./runspace11-sample.md)を使用する方法を示します、 [System.Management.Automation.Proxycommand](/dotnet/api/System.Management.Automation.ProxyCommand)クラスを既存のコマンドレットを呼び出しますが、使用可能なパラメーターのセットを制限するプロキシ コマンドを作成します。 このプロキシ コマンドは、制約付き実行空間の作成に使用される最初のセッション状態に追加されます。 つまり、ユーザーはプロキシ コマンドを使用しないとコマンドレットの機能にアクセスできません。

## <a name="see-also"></a>参照
