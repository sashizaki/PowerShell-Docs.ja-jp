---
title: Windows PowerShell SDK のインストール
ms.date: 09/13/2016
ms.topic: article
ms.openlocfilehash: da1b3dbb8a599aee2cdbab9115aedcab0b4c78c9
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367271"
---
# <a name="installing-the-windows-powershell-sdk"></a>Windows PowerShell SDK のインストール

適用対象: Windows PowerShell 2.0、Windows PowerShell 3.0

以下のトピックでは、異なるバージョンの Windows に PowerShell SDK をインストールする方法について説明します。

## <a name="installing-windows-powershell-30-sdk-for-windows-8-and-windows-server-2012"></a>Windows 8 と Windows Server 2012 での Windows PowerShell 3.0 SDK のインストール

Windows PowerShell 3.0 は Windows 8 と Windows Server 2012 で自動的にインストールされます。 さらに、Windows 8 SDK の一部としての Windows PowerShell 3.0 の参照アセンブリもダウンロードおよびインストールできます。 これらのアセンブリでは、Windows PowerShell 3.0 のコマンドレット、プロバイダー、およびホスト プログラムを記述できます。 Windows 8 用 Windows SDK をインストールすると、Windows PowerShell アセンブリが自動的に \Program Files (x86)\Reference Assemblies\Microsoft\WindowsPowerShell\3.0 にインストールされます。 詳細については、Windows 8 SDK のダウンロードサイトを参照してください。 Windows PowerShell のサンプル コードもデベロッパー センターで入手できます。
詳細については、デベロッパーセンターサイトのデスクトップコードサンプルページを参照してください。

さらに、Windows PowerShell 3.0 には Windows PowerShell 2.0 SDK との下位互換性があり、これには多くのサンプルコードが含まれます。 Windows PowerShell 2.0 SDK をダウンロードする方法の詳細については、以下をご覧ください。 (2.0 のサンプル コードは Windows 8 および Windows PowerShell 3.0 と互換性がありますが、Windows PowerShell 2.0 を Windows 8 プラットフォームにインストールすることはできません)。

## <a name="installing-windows-powershell-30-sdk-for-windows-7-and-windows-server-2008-r2"></a>Windows 7 と Windows Server 2008 R2 での Windows PowerShell 3.0 SDK のインストール

Windows 7 と Windows Server 2008 R2 では、PowerShell 2.0 が自動的にインストールされます。 さらに、これらのシステムに PowerShell 3.0 をインストールできます。 (詳細については、「Windows PowerShell のインストール」を参照してください)。 前述のように、Windows 7 および Windows Server 2008 R2 で Windows 8 SDK をインストールすることもできます。

## <a name="installing-windows-powershell-20-sdk-for-windows-7-vista-xp-server-2003-and-server-2008"></a>Windows 7、Vista、XP、Server 2003、Server 2008 での Windows PowerShell 2.0 SDK のインストール

Windows PowerShell 2.0 SDK は、コマンドレット、プロバイダー、アプリケーションのホストを記述するために必要な参照アセンブリを提供し、コードの記述を開始するときに開始点として使用できる C# サンプル コードを提供します。

この SDK をインストールするには、「Windows PowerShell 2.0 SDK」を参照してください。

### <a name="reference-assemblies"></a>参照アセンブリ

参照アセンブリは、既定では次の場所にインストールされます: c:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\V1.0.

> [!NOTE]
>
> Windows PowerShell 2.0 のアセンブリに対してコンパイルされるコードは、Windows PowerShell 1.0 のインストールに読み込むことができません。 ただし、Windows PowerShell 1.0 のアセンブリに対してコンパイルされるコードは、Windows PowerShell 2.0 のインストールに読み込むことができます。


### <a name="samples"></a>サンプル

既定では、コードサンプルは次の場所にインストールされます。 C:\Program are SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\. 次のセクションでは、各サンプル コードについて簡単に説明します。

#### <a name="cmdlet-samples"></a>コマンドレット サンプル

- GetProcessSample01-ローカルコンピューター上のすべてのプロセスを取得する簡単なコマンドレットを記述する方法を示します。
- GetProcessSample02-コマンドレットにパラメーターを追加する方法を示します。 このコマンドレットは 1 つまたは複数のプロセス名を取得し、それに一致するプロセスを返します。
- GetProcessSample03-パイプラインからの入力を受け入れるパラメーターを追加する方法を示します。
- GetProcessSample04-終了しないエラーを処理する方法を示します。
- GetProcessSample05-指定されたプロセスの一覧を表示する方法を示します。
- SelectObject-特定のオブジェクトのみを選択するフィルターを作成する方法を示します。
- SelectString-指定したパターンのファイルを検索する方法を示します。
- StopProcessSample01-PassThru パラメーターを実装する方法と、指定したメソッドの呼び出しによってユーザーフィードバックを要求する方法を示します。 コマンドレットがオブジェクトを返すように強制する場合は、PassThru パラメーターを指定します。
- StopProcessSample02-特定のプロセスを停止する方法を示します。
- StopProcessSample03-パラメーターのエイリアスを宣言する方法と、ワイルドカードをサポートする方法を示します。
- StopProcessSample04-パラメーターセットを宣言する方法、コマンドレットが入力として受け取るオブジェクト、および使用する既定のパラメーターセットを指定する方法を示します。

#### <a name="remoting-samples"></a>リモート処理のサンプル

- RemoteRunspace01-リモート接続を確立するために使用されるリモート実行空間を作成する方法を示します。
- RemoteRunspacePool01-リモートの実行空間プールを作成する方法と、このプールを使用して複数のコマンドを同時に実行する方法を示します。
- Serialization01-既存の .NET クラスを確認し、このクラスの選択されたパブリックプロパティからの情報がシリアル化と逆シリアル化の間で保持されることを確認する方法を示します。
- Serialization02-既存の .NET クラスを確認し、クラスのパブリックプロパティで情報を利用できない場合に、このクラスのインスタンスからの情報がシリアル化または逆シリアル化の間で保持されることを確認する方法を示します。
- Serialization03-既存の .NET クラスを確認し、このクラスと派生クラスのインスタンスがライブ .NET オブジェクトに逆シリアル化 (復元可能) されていることを確認する方法を示します。

#### <a name="event-samples"></a>イベントのサンプル

- Event01-ObjectEventRegistrationBase から派生することによって、イベント登録用のコマンドレットを作成する方法を示します。
- Event02-リモートコンピューターで生成された Windows PowerShell イベントの通知を受信する方法を示します。 実行空間クラスを通じて公開される PSEventReceived イベントを使用します。

#### <a name="hosting-application-samples"></a>アプリケーションのホストのサンプル

- Runspace01-PowerShell クラスを使用して `Get-Process` コマンドレットを同期的に実行する方法を示します。
@No__t-0 コマンドレットは、ローカルコンピューター上で実行されている各プロセスのプロセスオブジェクトを返します。
- Runspace02-PowerShell クラスを使用して、`Get-Process` および `Sort-Object` のコマンドレットを同期的に実行する方法を示します。 @No__t-0 コマンドレットは、ローカルコンピューター上で実行されている各プロセスのプロセスオブジェクトを返します。 @no__t は、Id プロパティに基づいてオブジェクトを並べ替えます。 これらのコマンドの結果は、DataGridView コントロールを使用して表示されます。
- Runspace03-PowerShell クラスを使用してスクリプトを同期的に実行する方法と、終了しないエラーを処理する方法を示します。 このスクリプトはプロセス名の一覧を受信し、これらのプロセスを取得します。 スクリプトの実行時に生成された終了しないエラーを含む、スクリプトの結果がコンソール ウィンドウに表示されます。
- Runspace04-PowerShell クラスを使用してコマンドを実行する方法と、コマンドの実行時にスローされる終了エラーをキャッチする方法を示します。 2 つのコマンドが実行され、最後のコマンドには無効なパラメーターの引数が渡されます。 結果として、オブジェクトは返されず、終了するエラーがスローされます。
- Runspace05-InitialSessionState オブジェクトにスナップインを追加して、実行空間を開いたときにスナップインのコマンドレットを使用できるようにする方法を示します。 スナップインには、PowerShell オブジェクトを使用して同期的に実行される Get Proc コマンドレット (GetProcessSample01 サンプルで定義) が用意されています。
- Runspace06-実行空間が開かれたときにモジュールが読み込まれるように、InitialSessionState オブジェクトにモジュールを追加する方法を示します。 モジュールには、PowerShell オブジェクトを使用して同期的に実行される GetProcessSample02 コマンドレット (サンプルで定義) が用意されています。
- Runspace07-実行空間を作成し、その実行空間を使用して、PowerShell オブジェクトを使用して2つのコマンドレットを同期的に実行する方法を示します。
- Runspace08-PowerShell オブジェクトのパイプラインにコマンドと引数を追加する方法と、コマンドを同期的に実行する方法を示します。
- Runspace09-PowerShell オブジェクトのパイプラインにスクリプトを追加する方法と、スクリプトを非同期で実行する方法を示します。 イベントはスクリプトの出力を処理するために使用されます。
- Runspace10-既定の初期セッション状態を作成する方法、コマンドレットを InitialSessionState に追加する方法、初期セッション状態を使用する実行空間を作成する方法、PowerShell オブジェクトを使用してコマンドを実行する方法について説明します。
- Runspace11-ProxyCommand クラスを使用して、既存のコマンドレットを呼び出すが、使用可能なパラメーターのセットを制限するプロキシコマンドを作成する方法を示します。 このプロキシ コマンドは、制約付き実行空間の作成に使用される最初のセッション状態に追加されます。 つまり、ユーザーはプロキシ コマンドを使用しないとコマンドレットの機能にアクセスできません。
- PowerShell01-InitialSessionState オブジェクトを使用して、制約付き実行空間を作成する方法を示します。
- PowerShell02-実行空間プールを使用して複数のコマンドを同時に実行する方法を示します。

#### <a name="host-samples"></a>ホストのサンプル

- Vmhost01-カスタムホストを使用するホストアプリケーションを実装する方法を示します。 このサンプルでは、カスタムホストを使用する実行空間が作成されます。その後、PowerShell API を使用して、"exit" を呼び出すスクリプトを実行します。 ホスト アプリケーションはスクリプトの出力を確認し、結果を印刷します。
- Host02-Windows PowerShell ランタイムをカスタムホスト実装と共に使用するホストアプリケーションを記述する方法を示します。 ホストアプリケーションは、ホストカルチャをドイツ語に設定し、@no__t コマンドレットを実行して、結果を表示します。これは pwrsh .exe を使用して表示されます。その後、現在のデータと時刻をドイツ語で印刷します。
- Host03-コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する、対話型のコンソールベースのホストアプリケーションを構築する方法を示します。
- Host04-コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する、対話型のコンソールベースのホストアプリケーションを構築する方法を示します。 このホスト アプリケーションでは、複数選択を指定するための確認メッセージを表示することもできます。
- Host05-コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する、対話型のコンソールベースのホストアプリケーションを構築する方法を示します。 このホストアプリケーションは、`Enter-PsSession` および `Exit-PsSession` のコマンドレットを使用して、リモートコンピューターへの呼び出しもサポートします。
- Host06-コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する、対話型のコンソールベースのホストアプリケーションを構築する方法を示します。 さらに、このサンプルでは、トークナイザー API を使用して、ユーザーが入力したテキストの色を指定します。

#### <a name="provider-samples"></a>プロバイダーのサンプル

- AccessDBProviderSample01-表示プロバイダークラスから直接派生するプロバイダークラスを宣言する方法を示します。 すべてを網羅しておく目的でここに含めておきます。

- AccessDBProviderSample02-NewDrive メソッドと RemoveDrive メソッドを上書きして、`New-PSDrive` および `Remove-PSDrive` コマンドレットの呼び出しをサポートする方法を示します。 このサンプルのプロバイダークラスは、DriveCmdletProvider クラスから派生します。

- AccessDBProviderSample03-`Get-Item` および `Set-Item` コマンドレットの呼び出しをサポートするように、GetItem メソッドと SetItem メソッドを上書きする方法を示します。 このサンプルのプロバイダークラスは、Itemのプロバイダークラスから派生します。

- AccessDBProviderSample04-`Copy-Item`、`Get-ChildItem`、`New-Item`、および `Remove-Item` コマンドレットの呼び出しをサポートするようにコンテナーメソッドを上書きする方法を示します。 これらのメソッドは、データ ストアにコンテナーであるアイテムが含まれる場合に実装する必要があります。 コンテナーは、共通の親項目の子項目のグループです。 このサンプルのプロバイダークラスは、Itemのプロバイダークラスから派生します。

- AccessDBProviderSample05-`Move-Item` および `Join-Path` コマンドレットの呼び出しをサポートするようにコンテナーメソッドを上書きする方法を示します。 これらのメソッドは、ユーザーがコンテナー内で項目を移動する必要があり、データ ストアに入れ子状態のコンテナーが含まれる場合に実装する必要があります。 このサンプルのプロバイダークラスは、Navigation、Provider クラスから派生します。

- AccessDBProviderSample06-`Clear-Content`、`Get-Content`、`Set-Content` の各コマンドレットの呼び出しをサポートするために、コンテンツメソッドを上書きする方法を示します。 これらのメソッドは、ユーザーがデータ ストア内の項目のコンテンツを管理する必要がある場合に実装する必要があります。 このサンプルのプロバイダークラスは NavigationIContentCmdletProvider Provider クラスから派生し、このクラスには、インターフェイスが実装されています。
