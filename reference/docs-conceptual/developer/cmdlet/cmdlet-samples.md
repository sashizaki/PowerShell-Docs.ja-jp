---
title: コマンドレットのサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 633e4a5108673b09a92679c7992421b6b3405b72
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774747"
---
# <a name="cmdlet-samples"></a>コマンドレット サンプル

このセクションでは、Windows PowerShell 2.0 SDK で提供されるサンプルコードについて説明します。 このセクションのトピックからコードをコピーするか、SDK と共にインストールされたソースファイルを開くことができます。 [Windows PowerShell 2.0 ソフトウェア開発キット (SDK)](https://www.microsoft.com/en-us/download/details.aspx?id=2560)には、各サンプルの ReadMe ファイル、ソースファイル、および Visual Studio プロジェクトファイルが用意されています。 SDK がインストールされているので、このフォルダーの下にサンプルを見つけることができ `<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\` ます。

## <a name="in-this-section"></a>このセクションの内容

[GetProcessSample01 サンプル](./getprocesssample01-sample.md)このサンプルでは、ローカルコンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。

[GetProcessSample02 サンプル](./getprocesssample02-sample.md)このサンプルでは、ローカルコンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。 これには、取得するプロセスを指定するために使用できる Name パラメーターが用意されています。

[GetProcessSample03 サンプル](./getprocesssample03-sample.md)このサンプルでは、ローカルコンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。 このメソッドは、パイプラインからのオブジェクト、またはプロパティ名がパラメーター名と同じであるオブジェクトのプロパティの値を受け取ることができる Name パラメーターを提供します。

[GetProcessSample04 サンプル](./getprocesssample04-sample.md)このサンプルでは、ローカルコンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。 プロセスの取得中にエラーが発生した場合、終了しないエラーが生成されます。

[GetProcessSample05 サンプル](./getprocesssample05-sample.md)このサンプルでは、Get Proc コマンドレットの完全なバージョンを示します。

[StopProcessSample01 サンプル](./stopprocesssample01-sample.md)このサンプルでは、プロセスを停止する前にユーザーからのフィードバックを要求するコマンドレットを記述する方法と、 `PassThru` ユーザーがコマンドレットにオブジェクトを返すことを示すパラメーターを実装する方法を示します。

[StopProcessSample02 サンプル](./stopprocesssample02-sample.md)このサンプルでは、ローカルコンピューター上のプロセスを停止している間に、デバッグメッセージ、詳細メッセージ、警告メッセージを書き込むコマンドレットを記述する方法を示します。

[StopProcessSample03 サンプル](./stopprocesssample03-sample.md)このサンプルでは、パラメーターにエイリアスがあり、ワイルドカード文字をサポートするコマンドレットを記述する方法を示します。

[StopProcessSample04 サンプル](./stopprocesssample04-sample.md)このサンプルでは、パラメーターセットを宣言し、既定のパラメーターセットを指定し、入力オブジェクトを受け取ることができるコマンドレットを記述する方法を示します。

[Events01 サンプル](./events01-sample.md)このサンプルでは、ユーザーが system.servicemodel[によって](/dotnet/api/System.IO.FileSystemWatcher)発生したイベントに登録できるようにするコマンドレットを作成する方法を示します。 このコマンドレットを使用すると、たとえば、特定のディレクトリにファイルが作成されたときに実行するアクションを登録できます。 このサンプルは、 [Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase)基底クラスから派生します。

## <a name="see-also"></a>参照

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
