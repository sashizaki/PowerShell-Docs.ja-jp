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
# <a name="cmdlet-samples"></a>コマンドレット サンプル

このセクションでは、Windows PowerShell 2.0 SDK で提供されているサンプル コードについて説明します。 このセクションのトピックでコードをコピーまたは SDK がインストールされたソース ファイルを開くことができます。 [Windows PowerShell 2.0 ソフトウェア開発キット (SDK)](https://www.microsoft.com/en-us/download/details.aspx?id=2560) ReadMe ファイル、ソース ファイル、および各サンプルの Visual Studio プロジェクト ファイルを提供します。 インストールされている sdk では、下のサンプルを見つけることができます、`<Drive>:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\`フォルダー。

## <a name="in-this-section"></a>このセクションの内容

[GetProcessSample01 サンプル](./getprocesssample01-sample.md)このサンプルは、ローカル コンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。

[GetProcessSample02 サンプル](./getprocesssample02-sample.md)このサンプルは、ローカル コンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。 取得するプロセスを指定するために使用する Name パラメーターを提供します。

[GetProcessSample03 サンプル](./getprocesssample03-sample.md)このサンプルは、ローカル コンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。 パイプラインからオブジェクトまたはプロパティの名前は、パラメーター名と同じオブジェクトのプロパティの値を受け入れることができる、名前のパラメーターを提供します。

[GetProcessSample04 サンプル](./getprocesssample04-sample.md)このサンプルは、ローカル コンピューター上のプロセスを取得するコマンドレットを記述する方法を示します。 プロセスの取得中にエラーが発生した場合、終了しないエラーが生成されます。

[GetProcessSample05 サンプル](./getprocesssample05-sample.md)Get-proc コマンドレットの完全なバージョンを示します。

[StopProcessSample01 サンプル](./stopprocesssample01-sample.md)このサンプルを実装する方法と、プロセスを停止しようとする前に、ユーザーからフィードバックを要求するコマンドレットを記述する方法を示しています、`PassThru`ユーザーを返す、コマンドレットを示すパラメーターです、オブジェクト。

[StopProcessSample02 サンプル](./stopprocesssample02-sample.md)をローカル コンピューターのプロセスの停止中に、デバッグ、verbose、および警告メッセージを書き込むためのコマンドレットを記述する方法を示します。

[StopProcessSample03 サンプル](./stopprocesssample03-sample.md)このサンプルは、パラメーターがあるエイリアスとするコマンドレットを記述する方法を示しています。 ワイルドカード文字をサポートします。

[StopProcessSample04 サンプル](./stopprocesssample04-sample.md)パラメーター セットを宣言で、既定のパラメーターの設定、および入力オブジェクトを受け取ることができますを指定するコマンドレットを記述する方法を示します。

[Events01 サンプル](./events01-sample.md)によって生成されるイベントを登録するユーザーのためのコマンドレットを作成する方法を示します[System.IO.Filesystemwatcher](/dotnet/api/System.IO.FileSystemWatcher)します。 このコマンドレットを使用した、ユーザーは、特定のディレクトリの下のファイルが作成されるときに実行するアクションを登録することができますなど。 このサンプルはから派生した、 [Microsoft.PowerShell.Commands.Objecteventregistrationbase](/dotnet/api/Microsoft.PowerShell.Commands.ObjectEventRegistrationBase)基本クラス。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
