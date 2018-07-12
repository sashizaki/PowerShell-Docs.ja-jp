---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: Windows PowerShell SDK のインストール
ms.assetid: c3636b45-61aa-4720-85f0-58312c4fc8f9
ms.openlocfilehash: fa876bac0c1afac24f93d11dd2e7ecfb1165cf5f
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37893540"
---
# <a name="installing-the-windows-powershell-sdk"></a>Windows PowerShell SDK のインストール

以下のトピックでは、異なるバージョンの Windows に PowerShell SDK をインストールする方法について説明します。

## <a name="installing-windows-powershell-30-sdk-for-windows-8-and-windows-server-2012"></a>Windows 8 と Windows Server 2012 での Windows PowerShell 3.0 SDK のインストール

Windows PowerShell 3.0 は Windows 8 と Windows Server 2012 で自動的にインストールされます。
さらに、Windows 8 SDK の一部としての Windows PowerShell 3.0 の参照アセンブリもダウンロードおよびインストールできます。
これらのアセンブリでは、Windows PowerShell 3.0 のコマンドレット、プロバイダー、およびホスト プログラムを記述できます。
Windows 8 用 Windows SDK をインストールすると、Windows PowerShell アセンブリが自動的に参照アセンブリ フォルダー (`\Program Files (x86)\Reference Assemblies\Microsoft\WindowsPowerShell\3.0`) にインストールされます。
詳細については、[Windows 8 SDK ダウンロード サイト](https://developer.microsoft.com/en-us/windows/downloads/sdk-archive)を参照してください。
Windows PowerShell のサンプル コードもデベロッパー センターで入手できます。
詳細については、[デベロッパー センター サイト](https://code.msdn.microsoft.com:443/windowsdesktop/)のデスクトップ サンプル コード ページをご覧ください。

さらに、Windows PowerShell 3.0 には Windows PowerShell 2.0 SDK との下位互換性があり、これには多くのサンプルコードが含まれます。
Windows PowerShell 2.0 SDK をダウンロードする方法の詳細については、以下をご覧ください。
(2.0 のサンプル コードは Windows 8 および Windows PowerShell 3.0 と互換性がありますが、Windows PowerShell 2.0 を Windows 8 プラットフォームにインストールすることはできません)。

## <a name="installing-windows-powershell-30-sdk-for-windows-7-and-windows-server-2008-r2"></a>Windows 7 と Windows Server 2008 R2 での Windows PowerShell 3.0 SDK のインストール

Windows 7 と Windows Server 2008 R2 では、PowerShell 2.0 が自動的にインストールされます。
さらに、これらのシステムに PowerShell 3.0 をインストールできます。
(詳細については、「[Windows PowerShell のインストール](Installing-Windows-PowerShell.md)」をご覧ください。)
前述のように、Windows 7 および Windows Server 2008 R2 で Windows 8 SDK をインストールすることもできます。

## <a name="installing-windows-powershell-20-sdk-for-windows-7-vista-xp-server-2003-and-server-2008"></a>Windows 7、Vista、XP、Server 2003、Server 2008 での Windows PowerShell 2.0 SDK のインストール

Windows PowerShell 2.0 SDK は、コマンドレット、プロバイダー、アプリケーションのホストを記述するために必要な参照アセンブリを提供し、コードの記述を開始するときに開始点として使用できる C# サンプル コードを提供します。

この SDK をインストールするには、「[Windows PowerShell 2.0 SDK](http://www.microsoft.com/en-us/download/details.aspx?id=2560)」を参照してください。

## <a name="reference-assemblies"></a>参照アセンブリ

既定では、参照アセンブリは `c:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\V1.0` にインストールされます。

> [!NOTE] 
> Windows PowerShell 2.0 のアセンブリに対してコンパイルされるコードは、Windows PowerShell 1.0 のインストールに読み込むことができません。
> ただし、Windows PowerShell 1.0 のアセンブリに対してコンパイルされるコードは、Windows PowerShell 2.0 のインストールに読み込むことができます。

## <a name="samples"></a>サンプル

既定では、コード サンプルは `C:\Program Files\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\` にインストールされます。

次のセクションでは、各サンプル コードについて簡単に説明します。

## <a name="cmdlet-samples"></a>コマンドレット サンプル

### <a name="getprocesssample01"></a>GetProcessSample01

ローカル コンピューターのすべてのプロセスを取得する簡単なコマンドレットを記述する方法を示します。

### <a name="getprocesssample02"></a>GetProcessSample02

コマンドレットにパラメーターを追加する方法を示します。
このコマンドレットは 1 つまたは複数のプロセス名を取得し、それに一致するプロセスを返します。

### <a name="getprocesssample03"></a>GetProcessSample03

パイプラインからの入力を受け入れるパラメーターを追加する方法を示します。

### <a name="getprocesssample04"></a>GetProcessSample04

終了しないエラーの処理方法を示します。

### <a name="getprocesssample05"></a>GetProcessSample05

指定されたプロセスの一覧を表示する方法を示します。

### <a name="selectobject"></a>SelectObject

特定のオブジェクトのみを選択するフィルターの記述方法を示します。

### <a name="selectstring"></a>SelectString

指定されたパターンのファイルを検索する方法を示します。

### <a name="stopprocesssample01"></a>StopProcessSample01

*PassThru* パラメーターの実装方法と、[ShouldProcess](/dotnet/api/system.management.automation.cmdlet.shouldprocess) メソッドと [ShouldContinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue) メソッドを呼び出すことでユーザーにフィードバックを要求する方法を示します。
ユーザーはオブジェクトを返すようにコマンドレットに強制するとき、*PassThru* を指定します。

### <a name="stopprocesssample02"></a>StopProcessSample02

特定のプロセスの停止方法を示します。

### <a name="stopprocesssample03"></a>StopProcessSample03

パラメーターのエイリアスの宣言方法とワイルドカードのサポート方法を示します。

### <a name="stopprocesssample04"></a>StopProcessSample04

パラメーター セットの宣言方法、コマンドレットが入力として取得するオブジェクト、既定として使用するパラメーター セットの指定方法を示します。

## <a name="remoting-samples"></a>リモート処理のサンプル

### <a name="remoterunspace01"></a>RemoteRunspace01

リモート接続の確立に使用されるリモート実行空間の作成方法を示します。

### <a name="remoterunspacepool01"></a>RemoteRunspacePool01

リモート実行空間プールの構築方法とそのプールを使用して複数のコマンドを同時に実行する方法を示します。

### <a name="serialization01"></a>Serialization01

既存の .NET クラスを見て、そのクラスで選択されているパブリック プロパティからの情報がシリアル化/逆シリアル化全体で維持されていることを確認する方法を示します。

### <a name="serialization02"></a>Serialization02

既存の .NET クラスを見て、そのクラスのインスタンスからの情報がクラスのパブリック プロパティで利用できないとき、その情報がシリアル化/シリアル化解除全体で維持されていることを確認する方法を示します。

### <a name="serialization03"></a>Serialization03

既存の .NET クラスを見て、そのクラスのインスタンスと派生クラスのインスタンスがライブ .NET オブジェクトに逆シリアル化 (リハイドレート) されていることを確認する方法を示します。

## <a name="event-samples"></a>イベントのサンプル

### <a name="event01"></a>Event01

ObjectEventRegistrationBase から派生させることでイベント登録のコマンドレットを作成する方法を示します。

### <a name="event02"></a>Event02

リモート コンピューターで生成された Windows PowerShell イベントの通知を受信する方法を示します。
[Runspace](/dotnet/api/system.management.automation.runspaces.runspace) クラスで公開された PSEventReceived イベントを使用します。

## <a name="hosting-application-samples"></a>アプリケーションのホストのサンプル

### <a name="runspace01"></a>Runspace01

[PowerShell](/dotnet/api/system.management.automation.powershell) クラスを使用し、[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) コマンドレットを同期的に実行する方法を示します。
[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) コマンドレットは、ローカル コンピューターで実行されているプロセスごとに [Process](https://technet.microsoft.com/library/system.diagnostics.process.aspx) オブジェクトを返します。

### <a name="runspace02"></a>Runspace02

[PowerShell](/dotnet/api/system.management.automation.powershell) クラスを使用し、[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) コマンドレットと [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) コマンドレットを同期的に実行する方法を示します。
[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) コマンドレットは、ローカル コンピューターで実行されているプロセスごとに [Process](https://technet.microsoft.com/library/system.diagnostics.process.aspx) オブジェクトを返します。`Sort-Object` は、[Id](https://technet.microsoft.com/library/system.diagnostics.process.id.aspx) プロパティに基づいてオブジェクトを並べ替えます。
これらのコマンドの結果は、[DataGridView](https://technet.microsoft.com/library/system.windows.forms.datagridview.aspx) コントロールを利用して表示されます。

### <a name="runspace03"></a>Runspace03

[PowerShell](/dotnet/api/system.management.automation.powershell) クラスを使用してスクリプトを同期的に実行する方法と終了しないエラーを処理する方法を示します。
このスクリプトはプロセス名の一覧を受信し、これらのプロセスを取得します。
スクリプトの実行時に生成された終了しないエラーを含む、スクリプトの結果がコンソール ウィンドウに表示されます。

### <a name="runspace04"></a>Runspace04

[PowerShell](/dotnet/api/system.management.automation.powershell) クラスを使用してコマンドを実行する方法とコマンドの実行時にスローされた終了するエラーをキャッチする方法を示します。
2 つのコマンドが実行され、最後のコマンドには無効なパラメーターの引数が渡されます。
結果として、オブジェクトは返されず、終了するエラーがスローされます。

### <a name="runspace05"></a>Runspace05

実行空間が開いたとき、スナップショットのコマンドレットが利用できるように [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate) オブジェクトにスナップインを追加する方法を示します。
このスナップインにより、[PowerShell](/dotnet/api/system.management.automation.powershell) オブジェクトを使用して同期的に実行される Get-Proc コマンドレット ([GetProcessSample01 サンプル](https://technet.microsoft.com/library/ff602028.aspx)により定義) が与えられます。

### <a name="runspace06"></a>Runspace06

実行空間が開いたとき、モジュールが読み込まれるように [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate) オブジェクトにモジュールを追加する方法を示します。
このモジュールにより、[PowerShell](/dotnet/api/system.management.automation.powershell) オブジェクトを使用して同期的に実行される Get-Proc コマンドレット ([GetProcessSample02 サンプル](https://technet.microsoft.com/library/ff602027.aspx)により定義) が与えられます。

### <a name="runspace07"></a>Runspace07

実行空間を作成し、その実行空間を使用し、[PowerShell](/dotnet/api/system.management.automation.powershell) オブジェクトを使用して 2 つのコマンドレットを同期的に実行する方法を示します。

### <a name="runspace08"></a>Runspace08

[PowerShell](/dotnet/api/system.management.automation.powershell) オブジェクトのパイプラインにコマンドと引数を追加する方法とコマンドを同期的に実行する方法を示します。

### <a name="runspace09"></a>Runspace09

[PowerShell](/dotnet/api/system.management.automation.powershell) オブジェクトのパイプラインにスクリプトを追加する方法とそのスクリプトを非同期的に実行する方法を示します。
イベントはスクリプトの出力を処理するために使用されます。

### <a name="runspace10"></a>Runspace10

既定の最初のセッション状態を作成する方法、コマンドレットを [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate) に追加する方法、最初のセッション状態を使用する実行空間を作成する方法、[PowerShell](/dotnet/api/system.management.automation.powershell) オブジェクトを使用してコマンドを実行する方法を示します。

### <a name="runspace11"></a>Runspace11

[ProxyCommand](/dotnet/api/system.management.automation.proxycommand) クラスを使用し、既存のコマンドレットを呼び出すが、利用できるパラメーターのセットを制約するプロキシ コマンドを作成する方法を示します。
このプロキシ コマンドは、制約付き実行空間の作成に使用される最初のセッション状態に追加されます。
つまり、ユーザーはプロキシ コマンドを使用しないとコマンドレットの機能にアクセスできません。

### <a name="powershell01"></a>PowerShell01

[InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate) オブジェクトを使用し、制約のある実行空間を作成する方法を示します。

### <a name="powershell02"></a>PowerShell02

実行空間プールを使用し、複数のコマンドを同時に実行する方法を示します。

## <a name="host-samples"></a>ホストのサンプル

### <a name="host01"></a>Host01

カスタム ホストを使用するホスト アプリケーションを実装する方法を示します。
このサンプルでは、カスタム ホストを使用する実行空間が作成され、その後 [PowerShell](/dotnet/api/system.management.automation.powershell) API を使用して "exit" を呼び出すスクリプトが実行されます。
ホスト アプリケーションはスクリプトの出力を確認し、結果を印刷します。

### <a name="host02"></a>Host02

カスタム ホストの実装と共に Windows PowerShell ランタイムを使用するホスト アプリケーションを記述する方法を示します。
ホスト アプリケーションはホストのカルチャをドイツ語に設定し、[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) コマンドレットを実行して、pwrsh.exe を使用して確認できるものと同じ結果を表示し、最新のデータと時刻をドイツ語で印刷します。

### <a name="host03"></a>Host03

コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。

### <a name="host04"></a>Host04

コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。
このホスト アプリケーションでは、複数選択を指定するための確認メッセージを表示することもできます。

### <a name="host05"></a>Host05

コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。
このホスト アプリケーションでは、[Enter-PsSession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) コマンドレットと [Exit-PsSession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession) コマンドレットを使用してリモート コンピューターを呼び出すこともできます。

### <a name="host06"></a>Host06

コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。
さらに、このサンプルでは、トークナイザー API を使用して、ユーザーが入力したテキストの色を指定します。

## <a name="provider-samples"></a>プロバイダーのサンプル

### <a name="accessdbprovidersample01"></a>AccessDBProviderSample01

[CmdletProvider](/dotnet/api/system.management.automation.provider.cmdletprovider) クラスから直接派生するプロバイダー クラスの宣言方法を示します。
すべてを網羅しておく目的でここに含めておきます。

### <a name="accessdbprovidersample02"></a>AccessDBProviderSample02

`New-PSDrive` コマンドレットと `Remove-PSDrive` コマンドレットを呼び出すために [NewDrive](/dotnet/api/system.management.automation.provider.drivecmdletprovider.newdrive) メソッドと [RemoveDrive](/dotnet/api/system.management.automation.provider.drivecmdletprovider.removedrive) メソッドを上書きする方法を示します。
このサンプルのプロバイダー クラスは [DriveCmdletProvider](/dotnet/api/system.management.automation.provider.drivecmdletprovider) クラスから派生します。

### <a name="accessdbprovidersample03"></a>AccessDBProviderSample03

`Get-Item` コマンドレットと `Set-Item` コマンドレットを呼び出すために [GetItem](/dotnet/api/system.management.automation.provider.itemcmdletprovider.getitem) メソッドと [SetItem](/dotnet/api/system.management.automation.provider.itemcmdletprovider.setitem) メソッドを上書きする方法を示します。
このサンプルのプロバイダー クラスは [ItemCmdletProvider](/dotnet/api/system.management.automation.provider.itemcmdletprovider) クラスから派生します。

### <a name="accessdbprovidersample04"></a>AccessDBProviderSample04

`Copy-Item`、`Get-ChildItem`、`New-Item`、`Remove-Item` コマンドレットを呼び出すためにコンテナー メソッドを上書きする方法を示します。
これらのメソッドは、データ ストアにコンテナーであるアイテムが含まれる場合に実装する必要があります。
コンテナーは、共通の親項目の子項目のグループです。
このサンプルのプロバイダー クラスは [ItemCmdletProvider](/dotnet/api/system.management.automation.provider.itemcmdletprovider) クラスから派生します。

### <a name="accessdbprovidersample05"></a>AccessDBProviderSample05

`Move-Item` コマンドレットと `Join-Path` コマンドレットを呼び出すためにコンテナー メソッドを上書きする方法を示します。
これらのメソッドは、ユーザーがコンテナー内で項目を移動する必要があり、データ ストアに入れ子状態のコンテナーが含まれる場合に実装する必要があります。
このサンプルのプロバイダー クラスは [NavigationCmdletProvider](/dotnet/api/system.management.automation.provider.navigationcmdletprovider) クラスから派生します。

### <a name="accessdbprovidersample06"></a>AccessDBProviderSample06

`Clear-Content`、`Get-Content`、`Set-Content` コマンドレットを呼び出すためにコンテンツ メソッドを上書きする方法を示します。
これらのメソッドは、ユーザーがデータ ストア内の項目のコンテンツを管理する必要がある場合に実装する必要があります。
このサンプルのプロバイダー クラスは [NavigationCmdletProvider](/dotnet/api/system.management.automation.provider.navigationcmdletprovider) クラスから派生し、[IContentCmdletProvider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) インターフェイスを実装します。