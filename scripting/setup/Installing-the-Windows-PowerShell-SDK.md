---
title:  Windows PowerShell SDK のインストール
ms.date:  2016-05-11
keywords:  powershell,cmdlet
description:  
ms.topic:  article
author:  jpjofre
manager:  dongill
ms.prod:  powershell
ms.assetid:  c3636b45-61aa-4720-85f0-58312c4fc8f9
---

# Windows PowerShell SDK のインストール
<?xml version="1.0" encoding="utf-8"?>
<developerConceptualDocument xmlns="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://ddue.schemas.microsoft.com/authoring/2003/5 http://dduestorage.blob.core.windows.net/ddueschema/developer.xsd">
  <introduction>
    <para>以下のトピックでは、異なるバージョンの Windows に PowerShell SDK をインストールする方法について説明します。</para>
  </introduction>
  <section>
    <title>Windows 8 および Windows Server 2012 用 Windows PowerShell 3.0 SDK のインストール</title>
    <content>
      <para>Windows PowerShell 3.0 は、Windows 8 および Windows Server 2012 で自動的にインストールされます。 さらに、Windows 8 SDK の一部としての Windows PowerShell 3.0 の参照アセンブリもダウンロードおよびインストールできます。 これらのアセンブリでは、Windows PowerShell 3.0 のコマンドレット、プロバイダー、およびホスト プログラムを記述できます。 Windows 8 用 Windows SDK をインストールすると、Windows PowerShell アセンブリが自動的に \Program Files (x86)\Reference Assemblies\Microsoft\WindowsPowerShell\3.0 にインストールされます。 詳細については、<externalLink><linkText>Windows 8 SDK のダウンロード サイト (</linkText><linkUri>http://msdn.microsoft.com/windows/hardware/hh852363.aspx</linkUri></externalLink>) をご覧ください。 Windows PowerShell のサンプル コードもデベロッパー センターで入手できます。 詳細については、「<externalLink><linkText>デベロッパー センター サイト」 (</linkText><linkUri>http://code.msdn.microsoft.com/windowsdesktop/</linkUri></externalLink>) のデスクトップ サンプル コード ページをご覧ください。 </para>
      <para>さらに、Windows PowerShell 3.0 には Windows PowerShell 2.0 SDK との下位互換性があり、これには多くのサンプルコードが含まれます。 Windows PowerShell 2.0 SDK をダウンロードする方法の詳細については、以下をご覧ください。 (2.0 のサンプル コードは Windows 8 および Windows PowerShell 3.0 と互換性がありますが、Windows PowerShell 2.0 を Windows 8 プラットフォームにインストールすることはできません)。 </para>
    </content>
  </section>
  <section>
    <title>Windows 7 および Windows Server 2008 R2 用 Windows PowerShell 3.0 SDK のインストール</title>
    <content>
      <para>Windows ７ および Windows Server 2008 R2 には、PowerShell 2.0 が自動的にインストールされています。 さらに、これらのシステムに PowerShell 3.0 をインストールできます。 詳細については、「<link xlink:href="6fbb0409-5a54-48ec-95e6-7f8b7d8c4969">Windows PowerShell のインストール</link>」をご覧ください。 前述のように、Windows 7 および Windows Server 2008 R2 で Windows 8 SDK をインストールすることもできます。</para>
    </content>
  </section>
  <section>
    <title>Windows 7、Vista、XP、Server 2003、および Server 2008 用 Windows PowerShell 2.0 SDK のインストール</title>
    <content>
      <para><token>mshshort</token> 2.0 SDK は、コマンドレット、プロバイダー、およびホスト アプリケーションを記述するために必要な参照アセンブリ、およびコードの記述を開始するときに開始点として使用できる C# サンプル コードを提供します。 </para>
      <para>この SDK をインストールするには、「<externalLink><linkText>Windows PowerShell 2.0 SDK」 (</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=184611</linkUri></externalLink>) をご覧ください。</para>
    </content>
    <sections>
      <section>
        <title>参照アセンブリ</title>
        <content>
          <para>参照アセンブリは、既定で次の場所にインストールされます: <codeInline>c:\Program \reference Assemblies\Microsoft\WindowsPowerShell\V1.0</codeInline></para>
          <alert class="note">
            <para>Windows PowerShell 1.0 のインストールには、Windows PowerShell 2.0 のアセンブリに対してコンパイルされるコードを読み込むことができません。 ただし、Windows PowerShell 1.0 のアセンブリに対してコンパイルされるコードは、Windows PowerShell 2.0 のインストールに読み込むことができます。</para>
          </alert>
        </content>
      </section>
      <section>
        <title>サンプル</title>
        <content>
          <para>サンプル コードは、既定で次の場所にインストールされます: <codeInline>C:\Program \microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\</codeInline></para>
          <para>以下のセクションでは、各サンプルの実行内容について簡単に説明します。</para>
        </content>
        <sections>
          <section>
            <title>コマンドレットのサンプル</title>
            <content>
              <definitionTable>
                <definedTerm>GetProcessSample01</definedTerm>
                <definition>
                  <para>ローカル コンピューター上のすべてのプロセスを取得する単純なコマンドレットを記述する方法を示します。</para>
                </definition>
                <definedTerm>GetProcessSample02</definedTerm>
                <definition>
                  <para>コマンドレットにパラメーターを追加する方法を示します。 このコマンドレットは、1 つまたは複数のプロセス名を取得し、一致するプロセスを返します。</para>
                </definition>
                <definedTerm>GetProcessSample03</definedTerm>
                <definition>
                  <para>パイプラインから入力を受け付けるパラメーターを追加する方法を示します。</para>
                </definition>
                <definedTerm>GetProcessSample04</definedTerm>
                <definition>
                  <para>終わらないエラーを処理する方法を示します。</para>
                </definition>
                <definedTerm>GetProcessSample05</definedTerm>
                <definition>
                  <para>指定されたプロセスの一覧を表示する方法を示します。</para>
                </definition>
                <definedTerm>SelectObject</definedTerm>
                <definition>
                  <para>特定のオブジェクトのみを選択するフィルターを作成する方法を示します。 </para>
                </definition>
                <definedTerm>SelectString</definedTerm>
                <definition>
                  <para>指定したパターンに対するファイルを検索する方法を示します。</para>
                </definition>
                <definedTerm>StopProcessSample01</definedTerm>
                <definition>
                  <para><parameterReference>PassThru</parameterReference>パラメーターを実装し、<codeEntityReference>Overload:System.Management.Automation.Cmdlet.ShouldProcess</codeEntityReference> および <codeEntityReference>Overload:System.Management.Automation.Cmdlet.ShouldContinue</codeEntityReference> メソッドの呼び出しによってユーザーからのフィードバックを要求する方法を示します。 ユーザーは、コマンドレットがオブジェクトを返すように強制するときに <parameterReference>PassThru</parameterReference> を指定します。</para>
                </definition>
                <definedTerm>StopProcessSample02</definedTerm>
                <definition>
                  <para>特定のプロセスを停止する方法を示します。</para>
                </definition>
                <definedTerm>StopProcessSample03</definedTerm>
                <definition>
                  <para>パラメーターのエイリアスを宣言する方法と、ワイルドカードをサポートする方法を示します。</para>
                </definition>
                <definedTerm>StopProcessSample04</definedTerm>
                <definition>
                  <para>パラメーター セットを宣言する方法、コマンドレットが入力として使用するオブジェクト、および使用する既定のパラメーター セットを指定する方法を示します。</para>
                </definition>
              </definitionTable>
            </content>
          </section>
          <section>
            <title>リモート処理のサンプル</title>
            <content>
              <definitionTable>
                <definedTerm>RemoteRunspace01</definedTerm>
                <definition>
                  <para>リモート接続を確立するために使用されるリモート実行空間を作成する方法を示します。</para>
                </definition>
                <definedTerm>RemoteRunspacePool01</definedTerm>
                <definition>
                  <para>リモートの実行空間プールを作成する方法と、このプールを使用して同時に複数のコマンドを実行する方法を示します。</para>
                </definition>
                <definedTerm>Serialization01</definedTerm>
                <definition>
                  <para>既存の .NET クラスを確認し、このクラスの選択されたパブリック プロパティからの情報がシリアル化または逆シリアル化全体で保持されているかどうかを確認する方法を示します。</para>
                </definition>
                <definedTerm>Serialization02</definedTerm>
                <definition>
                  <para>既存の .NET クラスを確認し、このクラスのインスタンスからの情報がクラスのパブリック プロパティで利用できない場合に、この情報がシリアル化または逆シリアル化全体で保持されているかどうかを確認する方法を示します。</para>
                </definition>
                <definedTerm>Serialization03</definedTerm>
                <definition>
                  <para>既存の .NET クラスを確認し、このクラスおよび派生クラスのインスタンスが有効な .NET オブジェクトに逆シリアル化 (復元) されていることを確認する方法を示します。</para>
                </definition>
              </definitionTable>
            </content>
          </section>
          <section>
            <title>イベント サンプル</title>
            <content>
              <definitionTable>
                <definedTerm>Event01</definedTerm>
                <definition>
                  <para>イベント登録用のコマンドレットを、ObjectEventRegistrationBase から派生させることによって作成する方法を示します。</para>
                </definition>
                <definedTerm>Event02</definedTerm>
                <definition>
                  <para>リモート コンピューターで生成される <token>mshshort</token> イベントの通知を受信する方法を示します。 <codeEntityReference>T:System.Management.Automation.Runspaces.Runspace</codeEntityReference> クラスを通じて公開される PSEventReceived イベントを使用します。</para>
                </definition>
              </definitionTable>
            </content>
          </section>
          <section>
            <title>ホスト アプリケーションのサンプル</title>
            <content>
              <definitionTable>
                <definedTerm>Runspace01</definedTerm>
                <definition>
                  <para><codeEntityReference>T:System.Management.Automation.PowerShell</codeEntityReference> クラスを使用して <externalLink><linkText>Get-Process</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=113324</linkUri></externalLink> コマンドレットを同期的に実行する方法を示します。 <externalLink><linkText>Get-Process</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=113324</linkUri></externalLink> コマンドレットは、ローカル コンピューターで実行されている各プロセスに対して <codeEntityReference>T:System.Diagnostics.Process</codeEntityReference> オブジェクトを返します。</para>
                </definition>
                <definedTerm>Runspace02</definedTerm>
                <definition>
                  <para><codeEntityReference>T:System.Management.Automation.PowerShell</codeEntityReference> クラスを使用して <externalLink><linkText>Get-Process</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=113324</linkUri></externalLink> コマンドレットと <externalLink><linkText>Sort-Object</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkID=113403</linkUri></externalLink> コマンドレットを同期的に実行する方法を示します。 <externalLink><linkText>Get-Process</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=113324</linkUri></externalLink> コマンドレットは、ローカル コンピューターで実行されている各プロセスに対して <codeEntityReference>T:System.Diagnostics.Process</codeEntityReference> オブジェクトを返し、Sort-Object は <codeEntityReference>P:System.Diagnostics.Process.Id</codeEntityReference> プロパティに基づいてオブジェクトを並べ替えます。 これらのコマンドの結果は、<codeEntityReference>T:System.Windows.Forms.DataGridView</codeEntityReference> コントロールを使用して表示されます。</para>
                </definition>
                <definedTerm>Runspace03</definedTerm>
                <definition>
                  <para><codeEntityReference>T:System.Management.Automation.PowerShell</codeEntityReference> クラスを使用してスクリプトを同期的に実行し、未終了エラーを処理する方法を示します。 このスクリプトはプロセス名の一覧を受信し、これらのプロセスを取得します。 スクリプトの実行時に生成された未終了エラーを含むスクリプトの結果は、コンソール ウィンドウに表示されます。</para>
                </definition>
                <definedTerm>Runspace04</definedTerm>
                <definition>
                  <para><codeEntityReference>T:System.Management.Automation.PowerShell</codeEntityReference> クラスを使用してコマンドを実行する方法、およびコマンドの実行時にスローされる終了エラーをキャッチする方法を示します。 2 つのコマンドが実行され、最後のコマンドには無効なパラメーターの引数が渡されます。 その結果、オブジェクトが返されず、終了エラーがスローされます。</para>
                </definition>
                <definedTerm>Runspace05</definedTerm>
                <definition>
                  <para><codeEntityReference>T:System.Management.Automation.Runspaces.InitialSessionState</codeEntityReference> オブジェクトにスナップインを追加して、実行空間が開かれたときにこのスナップインのコマンドレットを使用できるようにする方法を示します。 このスナップインでは、<codeEntityReference>T:System.Management.Automation.PowerShell</codeEntityReference> オブジェクトを使用して同期的に実行される (<legacyLink xlink:href="7b48bf80-cbf0-4cb1-8d5b-3b8d06196598">GetProcessSample01 サンプル</legacyLink>によって定義される) Get-Proc コマンドレットが提供されます。</para>
                </definition>
                <definedTerm>Runspace06</definedTerm>
                <definition>
                  <para><codeEntityReference>T:System.Management.Automation.Runspaces.InitialSessionState</codeEntityReference> オブジェクトにモジュールを追加し、実行空間が開かれたときにこのモジュールが読み込まれるようにする方法を示します。 このモジュールでは、<codeEntityReference>T:System.Management.Automation.PowerShell</codeEntityReference> オブジェクトを使って同期的に実行される (<legacyLink xlink:href="481f557d-3344-4d33-b2da-4736a0165181">GetProcessSample02 サンプル</legacyLink>によって定義される) Get-Proc コマンドレットが提供されます。</para>
                </definition>
                <definedTerm>Runspace07</definedTerm>
                <definition>
                  <para>実行空間を作成し、その実行空間を使用して、<codeEntityReference>T:System.Management.Automation.PowerShell</codeEntityReference> オブジェクトを使って 2 つのコマンドレットを同期的に実行する方法を示します。</para>
                </definition>
                <definedTerm>Runspace08</definedTerm>
                <definition>
                  <para><codeEntityReference>T:System.Management.Automation.PowerShell</codeEntityReference> オブジェクトのパイプラインにコマンドと引数を追加する方法、およびコマンドを同期的に実行する方法を示します。</para>
                </definition>
                <definedTerm>Runspace09</definedTerm>
                <definition>
                  <para> <codeEntityReference>T:System.Management.Automation.PowerShell</codeEntityReference> オブジェクトのパイプラインにスクリプトを追加する方法、およびスクリプトを非同期的に実行する方法を示します。 イベントは、スクリプトの出力の処理に使用されます。</para>
                </definition>
                <definedTerm>Runspace10</definedTerm>
                <definition>
                  <para>既定の最初のセッション状態を作成する方法、<codeEntityReference>T:System.Management.Automation.Runspaces.InitialSessionState</codeEntityReference> にコマンドレットを追加する方法、 最初のセッション状態を使用する実行空間を作成する方法、および <codeEntityReference>T:System.Management.Automation.PowerShell</codeEntityReference> オブジェクトを使用してコマンドを実行する方法を示します。</para>
                </definition>
                <definedTerm>Runspace11</definedTerm>
                <definition>
                  <para> <codeEntityReference>T:System.Management.Automation.ProxyCommand</codeEntityReference> クラスを使用して、既存のコマンドレットを呼び出し、使用可能なパラメーターのセットを制限するプロキシ コマンドを作成する方法を示します。 このプロキシ コマンドは、制約付き実行空間の作成に使用される最初のセッション状態に追加されます。 これは、ユーザーが、プロキシ コマンドを介してのみコマンドレットの機能にアクセスできることを意味します。</para>
                </definition>
                <definedTerm>PowerShell01</definedTerm>
                <definition>
                  <para> <codeEntityReference>T:System.Management.Automation.Runspaces.InitialSessionState</codeEntityReference> オブジェクトを使用して制約付き実行空間を作成する方法を示します。</para>
                </definition>
                <definedTerm>PowerShell02</definedTerm>
                <definition>
                  <para>実行空間プールを使用して、同時に複数のコマンドを実行する方法を示します。</para>
                </definition>
              </definitionTable>
            </content>
          </section>
          <section>
            <title>ホスト サンプル</title>
            <content>
              <definitionTable>
                <definedTerm>Host01</definedTerm>
                <definition>
                  <para>カスタム ホストを使用するホスト アプリケーションを実装する方法を示します。 このサンプルでは、カスタム ホストを使用する実行空間が作成され、その後 <codeEntityReference>T:System.Management.Automation.PowerShell</codeEntityReference> API を使用して "exit" を呼び出すスクリプトが実行されます。 ホスト アプリケーションはスクリプトの出力を確認し、結果を印刷します。</para>
                </definition>
                <definedTerm>Host02</definedTerm>
                <definition>
                  <para>カスタム ホストの実装で <token>mshshort</token> ランタイムを使用するホスト アプリケーションを書き込む方法を示します。 ホスト アプリケーションはホストのカルチャをドイツ語に設定し、<externalLink><linkText>Get-Process </linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=113324</linkUri></externalLink> コマンドレットを実行して、pwrsh.exe を使用して確認できるものと同じ結果を表示し、最新のデータと時刻をドイツ語で印刷します。</para>
                </definition>
                <definedTerm>Host03</definedTerm>
                <definition>
                  <para>コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</para>
                </definition>
                <definedTerm>Host04</definedTerm>
                <definition>
                  <para>コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。 このホスト アプリケーションでは、ユーザーが複数の選択肢を指定できるようにする確認メッセージの表示もサポートされます。</para>
                </definition>
                <definedTerm>Host05</definedTerm>
                <definition>
                  <para>コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。 このホスト アプリケーションでは、<externalLink><linkText>Enter-PsSession (</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=135210</linkUri></externalLink>) コマンドレットおよび <externalLink><linkText>Exit-PsSession (</linkText><linkUri>http://go.microsoft.com/fwlink/?LinkId=135212</linkUri></externalLink>) コマンドレットを使用したリモート コンピューターへの呼び出しもサポートされます。</para>
                </definition>
                <definedTerm>Host06</definedTerm>
                <definition>
                  <para>コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。 さらに、このサンプルでは、トークナイザー API を使用して、ユーザーが入力したテキストの色を指定します。</para>
                </definition>
              </definitionTable>
            </content>
          </section>
          <section>
            <title>プロバイダーのサンプル</title>
            <content>
              <definitionTable>
                <definedTerm>AccessDBProviderSample01</definedTerm>
                <definition>
                  <para><codeEntityReference>T:System.Management.Automation.Provider.CmdletProvider</codeEntityReference> クラスから直接派生するプロバイダー クラスを宣言する方法を示します。 これは、情報の完全性を目的としてここに記載されています。</para>
                </definition>
                <definedTerm>AccessDBProviderSample02</definedTerm>
                <definition>
                  <para> <codeEntityReference>M:System.Management.Automation.Provider.DriveCmdletProvider.NewDrive(System.Management.Automation.PSDriveInfo)</codeEntityReference> メソッドおよび <codeEntityReference>M:System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive(System.Management.Automation.PSDriveInfo)</codeEntityReference> メソッドを上書きして、New-PSDrive コマンドレットと Remove-PSDrive コマンドレットの呼び出しをサポートする方法を示します。 このサンプルのプロバイダー クラスは、<codeEntityReference>T:System.Management.Automation.Provider.DriveCmdletProvider</codeEntityReference> クラスから派生します。</para>
                </definition>
                <definedTerm>AccessDBProviderSample03</definedTerm>
                <definition>
                  <para><codeEntityReference>M:System.Management.Automation.Provider.ItemCmdletProvider.GetItem(System.String)</codeEntityReference> メソッドおよび <codeEntityReference>M:System.Management.Automation.Provider.ItemCmdletProvider.SetItem(System.String,System.Object)</codeEntityReference> メソッドを上書きして、Get-Item コマンドレットと Set-Item コマンドレットの呼び出しをサポートする方法を示します。 このサンプルのプロバイダー クラスは、<codeEntityReference>T:System.Management.Automation.Provider.ItemCmdletProvider</codeEntityReference> クラスから派生します。</para>
                </definition>
                <definedTerm>AccessDBProviderSample04</definedTerm>
                <definition>
                  <para>コンテナーのメソッドを上書きして、Copy-Item コマンドレット、Get-ChildItem コマンドレット、New-Item コマンドレット、および Remove-Item コマンドレットの呼び出しをサポートする方法を示します。 これらのメソッドは、データ ストアにコンテナーであるアイテムが含まれる場合に実装する必要があります。 コンテナーは、共通の親項目の子項目のグループです。 このサンプルのプロバイダー クラスは、<codeEntityReference>T:System.Management.Automation.Provider.ItemCmdletProvider</codeEntityReference> クラスから派生します。</para>
                </definition>
                <definedTerm>AccessDBProviderSample05</definedTerm>
                <definition>
                  <para>コンテナーのメソッドを上書きして、Move-Item コマンドレットと Join-Path コマンドレットの呼び出しをサポートする方法を示します。 これらのメソッドは、ユーザーがコンテナー内で項目を移動する必要があり、データ ストアに入れ子状態のコンテナーが含まれる場合に実装する必要があります。 このサンプルのプロバイダー クラスは、<codeEntityReference>T:System.Management.Automation.Provider.NavigationCmdletProvider</codeEntityReference> クラスから派生します。</para>
                </definition>
                <definedTerm>AccessDBProviderSample06</definedTerm>
                <definition>
                  <para>コンテンツのメソッドを上書きして、Clear-Content コマンドレット、Get-Content コマンドレット、および Set-Content コマンドレットの呼び出しをサポートする方法を示します。 これらのメソッドは、ユーザーがデータ ストア内の項目のコンテンツを管理する必要がある場合に実装する必要があります。 このサンプルのプロバイダー クラスは、<codeEntityReference>T:System.Management.Automation.Provider.NavigationCmdletProvider</codeEntityReference> クラスから派生し、<codeEntityReference>T:System.Management.Automation.Provider.IContentCmdletProvider</codeEntityReference> インターフェイスを実装します。</para>
                </definition>
              </definitionTable>
            </content>
          </section>
        </sections>
      </section>
    </sections>
  </section>
  <relatedTopics />
</developerConceptualDocument>



<!--HONumber=May16_HO4-->


