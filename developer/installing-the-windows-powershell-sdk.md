---
title: Windows PowerShell SDK のインストール
ms.date: 09/13/2016
ms.topic: article
ms.openlocfilehash: da1b3dbb8a599aee2cdbab9115aedcab0b4c78c9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082483"
---
# <a name="installing-the-windows-powershell-sdk"></a>Windows PowerShell SDK のインストール

適用先:Windows PowerShell 2.0、Windows PowerShell 3.0

以下のトピックでは、異なるバージョンの Windows に PowerShell SDK をインストールする方法について説明します。

## <a name="installing-windows-powershell-30-sdk-for-windows-8-and-windows-server-2012"></a>Windows 8 と Windows Server 2012 での Windows PowerShell 3.0 SDK のインストール

Windows PowerShell 3.0 は Windows 8 と Windows Server 2012 で自動的にインストールされます。 さらに、Windows 8 SDK の一部としての Windows PowerShell 3.0 の参照アセンブリもダウンロードおよびインストールできます。 これらのアセンブリでは、Windows PowerShell 3.0 のコマンドレット、プロバイダー、およびホスト プログラムを記述できます。 Windows 8 用 Windows SDK をインストールすると、Windows PowerShell アセンブリが自動的に \Program Files (x86)\Reference Assemblies\Microsoft\WindowsPowerShell\3.0 にインストールされます。 詳細については、サイトのダウンロード Windows 8 SDK を参照してください。 Windows PowerShell のサンプル コードもデベロッパー センターで入手できます。
詳細については、デベロッパー センターのサイトでデスクトップのコード サンプルのページを参照してください。

さらに、Windows PowerShell 3.0 には Windows PowerShell 2.0 SDK との下位互換性があり、これには多くのサンプルコードが含まれます。 Windows PowerShell 2.0 SDK をダウンロードする方法の詳細については、以下をご覧ください。 (2.0 のサンプル コードは Windows 8 および Windows PowerShell 3.0 と互換性がありますが、Windows PowerShell 2.0 を Windows 8 プラットフォームにインストールすることはできません)。

## <a name="installing-windows-powershell-30-sdk-for-windows-7-and-windows-server-2008-r2"></a>Windows 7 と Windows Server 2008 R2 での Windows PowerShell 3.0 SDK のインストール

Windows 7 と Windows Server 2008 R2 では、PowerShell 2.0 が自動的にインストールされます。 さらに、これらのシステムに PowerShell 3.0 をインストールできます。 (詳細については、参照 Windows PowerShell をインストールします。)。 前述のように、Windows 7 および Windows Server 2008 R2 で Windows 8 SDK をインストールすることもできます。

## <a name="installing-windows-powershell-20-sdk-for-windows-7-vista-xp-server-2003-and-server-2008"></a>Windows 7、Vista、XP、Server 2003、Server 2008 での Windows PowerShell 2.0 SDK のインストール

Windows PowerShell 2.0 SDK は、コマンドレット、プロバイダー、アプリケーションのホストを記述するために必要な参照アセンブリを提供し、コードの記述を開始するときに開始点として使用できる C# サンプル コードを提供します。

この SDK をインストールするには、Windows PowerShell 2.0 SDK を参照してください。

### <a name="reference-assemblies"></a>参照アセンブリ

参照アセンブリは、既定では、次の場所にインストールされます: c:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\V1.0 します。

> [!NOTE]
>
> Windows PowerShell 2.0 のアセンブリに対してコンパイルされるコードは、Windows PowerShell 1.0 のインストールに読み込むことができません。 ただし、Windows PowerShell 1.0 のアセンブリに対してコンパイルされるコードは、Windows PowerShell 2.0 のインストールに読み込むことができます。


### <a name="samples"></a>サンプル

コード サンプルは、既定では、次の場所にインストールされます。C:\Program Files\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\. 次のセクションでは、各サンプル コードについて簡単に説明します。

#### <a name="cmdlet-samples"></a>コマンドレット サンプル

- GetProcessSample01 - は、ローカル コンピューターのすべてのプロセスを取得する単純なコマンドレットを記述する方法を示します。
- GetProcessSample02 - は、コマンドレットにパラメーターを追加する方法を示します。 このコマンドレットは 1 つまたは複数のプロセス名を取得し、それに一致するプロセスを返します。
- GetProcessSample03 - は、パイプラインから入力を受け入れるパラメーターを追加する方法を示します。
- GetProcessSample04 - は、終了しないエラーを処理する方法を示します。
- GetProcessSample05 - は、指定されたプロセスの一覧を表示する方法を示します。
- SelectObject - は、特定のオブジェクトのみを選択するフィルターを記述する方法を示します。
- SelectString - は、指定されたパターンのファイルを検索する方法を示します。
- StopProcessSample01 -、PassThru パラメーターを実装する方法と、ShouldProcess と ShouldContinue メソッドを呼び出してユーザーからのフィードバックを要求する方法を示しています。 ユーザーが、オブジェクトを取得するコマンドレットを強制するときに、PassThru パラメーターを指定します。
- StopProcessSample02 - は、特定のプロセスを停止する方法を示します。
- StopProcessSample03 - は、パラメーターのエイリアスを宣言する方法と、ワイルドカードをサポートする方法を示します。
- StopProcessSample04 - パラメーターのセットを宣言する方法を示しています、コマンドレットは、入力、および既定のパラメーターを使用する設定を指定する方法として受け取るオブジェクト。

#### <a name="remoting-samples"></a>リモート処理のサンプル

- RemoteRunspace01 - は、リモート接続を確立するために使用されるリモート実行空間を作成する方法を示します。
- RemoteRunspacePool01 - は、このプールを使用して、同時に複数のコマンドを実行する方法とリモートの実行空間プールを作成する方法を示しています。
- Serialization01 - は、既存の .NET クラスを見て、このクラスの選択したパブリック プロパティからの情報をシリアル化/逆シリアル化の間で保持するかどうかを確認する方法を示します。
- Serialization02 - は、既存の .NET クラスを確認し、情報が、クラスのパブリック プロパティで利用できないときにこのクラスのインスタンスからの情報をシリアル化/逆シリアル化の間で保持するかどうかを確認する方法を示します。
- Serialization03 - は、既存の .NET クラスを見て、こと、このクラスの派生クラスのインスタンスが (リハイド レート) ライブ .NET オブジェクトに逆シリアル化することを確認する方法を示します。

#### <a name="event-samples"></a>イベントのサンプル

- Event01 - は、ObjectEventRegistrationBase から派生することによって、イベント登録のためのコマンドレットを作成する方法を示します。
- Event02 の表示方法をリモート コンピューターで生成される Windows PowerShell イベントの通知を受信する方法を示しています。 実行空間のクラスを通じて公開される PSEventReceived イベントを使用します。

#### <a name="hosting-application-samples"></a>アプリケーションのホストのサンプル

- Runspace01 - PowerShell クラスを使用して実行する方法を示しています、`Get-Process`コマンドレット同期的にします。
`Get-Process`コマンドレットは、ローカル コンピューターで実行されている各プロセスのプロセス オブジェクトを返します。
- Runspace02 - PowerShell クラスを使用して実行する方法を示しています、`Get-Process`と`Sort-Object`コマンドレット同期的にします。 `Get-Process`コマンドレットは、ローカル コンピューターで実行されている各プロセスのプロセス オブジェクトを返します、`Sort-Object`それぞれの Id プロパティに基づいてオブジェクトを並べ替えます。 DataGridView コントロールを使用して、これらのコマンドの結果が表示されます。
- Runspace03 - は、未終了エラーを処理する方法と PowerShell クラスを使用して同期的に、スクリプトを実行する方法を示しています。 このスクリプトはプロセス名の一覧を受信し、これらのプロセスを取得します。 スクリプトの実行時に生成された終了しないエラーを含む、スクリプトの結果がコンソール ウィンドウに表示されます。
- Runspace04 - は、PowerShell クラスを使用して、コマンドを実行する方法とをキャッチする方法を示しています。 コマンドの実行時にスローされたエラーを終了しています。 2 つのコマンドが実行され、最後のコマンドには無効なパラメーターの引数が渡されます。 結果として、オブジェクトは返されず、終了するエラーがスローされます。
- Runspace05 - は、実行空間が開いたときに、スナップインのコマンドレットを使用できるように、InitialSessionState オブジェクトにスナップインを追加する方法を示します。 スナップインでは、PowerShell オブジェクトを使用して同期的に実行される Get-proc コマンドレット (GetProcessSample01 サンプルで定義) を提供します。
- Runspace06 - は、実行空間が開かれたときに、モジュールが読み込まれるように InitialSessionState オブジェクトにモジュールを追加する方法を示します。 モジュールは、PowerShell オブジェクトを使用して同期的に実行される Get-proc コマンドレット (GetProcessSample02 サンプルで定義) を提供します。
- Runspace07 - は、実行空間を作成し、その実行空間を使用して、2 つのコマンドレットを PowerShell オブジェクトを使用して同期的に実行する方法を示します。
- Runspace08 - は、PowerShell オブジェクトのパイプラインにコマンドと引数を追加する方法と、コマンドを同期的に実行する方法を示します。
- Runspace09 - は、スクリプトを PowerShell オブジェクトのパイプラインに追加する方法と、スクリプトを非同期的に実行する方法を示します。 イベントはスクリプトの出力を処理するために使用されます。
- Runspace10 - は、既定の最初のセッション状態を作成する方法、InitialSessionState にコマンドレットを追加する方法、最初のセッションの状態を使用する実行空間を作成する方法、および PowerShell オブジェクトを使用して、コマンドを実行する方法を示しています。
- Runspace11 - ProxyCommand クラスを使用して、既存のコマンドレットを呼び出しますが、使用可能なパラメーターのセットを制限するプロキシ コマンドを作成する方法を示します。 このプロキシ コマンドは、制約付き実行空間の作成に使用される最初のセッション状態に追加されます。 つまり、ユーザーはプロキシ コマンドを使用しないとコマンドレットの機能にアクセスできません。
- PowerShell01 - は、InitialSessionState オブジェクトを使用して制約付き実行空間を作成する方法を示します。
- PowerShell02 - は、同時に複数のコマンドを実行する実行空間プールを使用する方法を示します。

#### <a name="host-samples"></a>ホストのサンプル

- Host01 というは、カスタム ホストを使用するホスト アプリケーションを実装する方法を示します。 カスタムのホストを使用する実行空間を作成するこのサンプルで、"exit"を呼び出すスクリプトを実行する PowerShell API を使用し、 ホスト アプリケーションはスクリプトの出力を確認し、結果を印刷します。
- Host02 - は、カスタム ホストの実装と共に Windows PowerShell ランタイムを使用するホスト アプリケーションを記述する方法を示します。 ホスト アプリケーションは、ドイツ語、実行するホストのカルチャを設定、`Get-Process`コマンドレットと同じ結果が表示されますが見る pwrsh.exe、および現在のデータと時刻を出力をドイツ語を使用しています。
- Host03 - は、コマンドラインからコマンドを読み取ってや、コマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。
- Host04 - は、コマンドラインからコマンドを読み取ってや、コマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。 このホスト アプリケーションでは、複数選択を指定するための確認メッセージを表示することもできます。
- Host05 - は、コマンドラインからコマンドを読み取ってや、コマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。 このホスト アプリケーションを使用してリモート コンピューターへの呼び出しをサポートすることも、`Enter-PsSession`と`Exit-PsSession`コマンドレット。
- Host06 - は、コマンドラインからコマンドを読み取ってや、コマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。 さらに、このサンプルでは、トークナイザー API を使用して、ユーザーが入力したテキストの色を指定します。

#### <a name="provider-samples"></a>プロバイダーのサンプル

- -AccessDBProviderSample01 CmdletProvider クラスから直接派生するプロバイダー クラスを宣言する方法を示します。 すべてを網羅しておく目的でここに含めておきます。

- AccessDBProviderSample02 の呼び出しをサポートする NewDrive と RemoveDrive メソッドを上書きする方法を示しています、`New-PSDrive`と`Remove-PSDrive`コマンドレット。 このサンプルのプロバイダー クラスは、DriveCmdletProvider クラスから派生します。

- AccessDBProviderSample03 の呼び出しをサポートする SetItem、GetItem、およびメソッドを上書きする方法を示しています、`Get-Item`と`Set-Item`コマンドレット。 このサンプルのプロバイダー クラスは、ItemCmdletProvider クラスから派生します。

- AccessDBProviderSample04 の呼び出しをサポートするコンテナーのメソッドを上書きする方法を示しています、 `Copy-Item`、 `Get-ChildItem`、 `New-Item`、および`Remove-Item`コマンドレット。 これらのメソッドは、データ ストアにコンテナーであるアイテムが含まれる場合に実装する必要があります。 コンテナーは、共通の親項目の子項目のグループです。 このサンプルのプロバイダー クラスは、ItemCmdletProvider クラスから派生します。

- AccessDBProviderSample05 の呼び出しをサポートするコンテナーのメソッドを上書きする方法を示しています、`Move-Item`と`Join-Path`コマンドレット。 これらのメソッドは、ユーザーがコンテナー内で項目を移動する必要があり、データ ストアに入れ子状態のコンテナーが含まれる場合に実装する必要があります。 このサンプルのプロバイダー クラスは、NavigationCmdletProvider クラスから派生します。

- AccessDBProviderSample06 の呼び出しをサポートするコンテンツのメソッドを上書きする方法を示しています、 `Clear-Content`、 `Get-Content`、および`Set-Content`コマンドレット。 これらのメソッドは、ユーザーがデータ ストア内の項目のコンテンツを管理する必要がある場合に実装する必要があります。 このサンプルのプロバイダー クラスは、NavigationCmdletProvider クラスから派生し、IContentCmdletProvider インターフェイスを実装します。
