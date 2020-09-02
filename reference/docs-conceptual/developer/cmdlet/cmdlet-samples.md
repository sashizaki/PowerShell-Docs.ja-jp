---
title: コマンドレットのサンプル | Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 7a4fb91cb316bf4231df0bb4446b9a7cd54cf647
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "89235984"
---
# <a name="cmdlet-samples"></a>コマンドレット サンプル

このセクションでは、Windows PowerShell 2.0 SDK で提供されるサンプル コードについて説明します。 お客様は、このセクションのトピックからコードをコピーするか、SDK と共にインストールされたソース ファイルを開くことができます。 [Windows PowerShell 2.0 Software Development Kit (SDK)](https://www.microsoft.com/download/details.aspx?id=2560) には、ReadMe ファイル、ソース ファイル、および各サンプル用の Visual Studio プロジェクト ファイルが用意されています。 SDK をインストールしたら、サンプルは `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\` フォルダーに配置されます。

## <a name="in-this-section"></a>このセクションの内容

[GetProcessSample01 サンプル](./getprocesssample01-sample.md) このサンプルでは、ローカル コンピューター上のプロセスを取得するコマンドレットの記述方法が示されます。

[GetProcessSample02 サンプル](./getprocesssample02-sample.md) このサンプルでは、ローカル コンピューター上のプロセスを取得するコマンドレットの記述方法が示されます。 取得するプロセスの指定に使用できる Name パラメーターが用意されています。

[GetProcessSample03 サンプル](./getprocesssample03-sample.md) このサンプルでは、ローカル コンピューター上のプロセスを取得するコマンドレットの記述方法が示されます。 パイプラインからのオブジェクト、またはプロパティ名がパラメーター名と同じオブジェクトのプロパティの値を受け取ることができる、Name パラメーターが用意されています。

[GetProcessSample04 サンプル](./getprocesssample04-sample.md) このサンプルでは、ローカル コンピューター上のプロセスを取得するコマンドレットの記述方法が示されます。 プロセスの取得中にエラーが発生した場合、終了しないエラーが生成されます。

[GetProcessSample05 サンプル](./getprocesssample05-sample.md) このサンプルでは、Get-Proc コマンドレットの完全なバージョンが示されます。

[StopProcessSample01 サンプル](./stopprocesssample01-sample.md) このサンプルでは、プロセスを停止する前にユーザーからのフィードバックを要求するコマンドレットの記述方法と、コマンドレットからオブジェクトが返されることをユーザーが必要としていることを示す `PassThru` パラメーターの実装方法が示されます。

[StopProcessSample02 サンプル](./stopprocesssample02-sample.md) このサンプルでは、ローカル コンピューター上のプロセスを停止している間に、デバッグ、詳細、および警告メッセージを書き込むコマンドレットの記述方法が示されます。

[StopProcessSample03 サンプル](./stopprocesssample03-sample.md) このサンプルでは、パラメーターにエイリアスがあり、ワイルドカード文字がサポートされているコマンドレットの記述方法が示されます。

[StopProcessSample04 サンプル](./stopprocesssample04-sample.md) このサンプルでは、パラメーター セットを宣言し、既定のパラメーター セットを指定し、入力オブジェクトを受け取ることができるコマンドレットの記述方法が示されます。

[Events01 サンプル](./events01-sample.md) このサンプルでは、ユーザーが [System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher) によって発生したイベントに登録できるようにするコマンドレットの記述方法が示されます。 このコマンドレットを使用すると、たとえば、特定のディレクトリにファイルが作成されたときに実行するアクションを登録できます。 このサンプルは、[Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase) 基底クラスから派生しています。

## <a name="see-also"></a>参照

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
