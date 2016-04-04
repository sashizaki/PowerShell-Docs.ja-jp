# DSC Web プル サーバーのセットアップ

> 適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

DSC Web プル サーバーは、OData インターフェイスを使用してターゲット ノードからの要求に応じて DSC 構成ファイルをそのターゲット ノードで使用できるようにする、IIS 内の Web サービスです。

プル サーバーを使用するための要件:

* 次のものを実行するサーバー。
  - WMF/PowerShell 4.0 以降
  - IIS サーバー ロール
  - DSC サービス
* 理想としては、証明書を生成する何らかの手段。これは、ターゲット ノードのローカル構成マネージャー (LCM) に渡された資格情報をセキュリティ保護するためのものです。

IIS サーバー ロールと DSC サービスを追加するには、サーバー マネージャーで役割と機能の追加ウィザードを使用するか、または PowerShell を使用します。 どちらの手順も、このトピックに含まれているサンプル スクリプトが自動的に処理します。

## XWebService リソースの使用
Web プル サーバーをセットアップする最も簡単な方法は、xPSDesiredStateConfiguration モジュールに含まれる xWebService リソースを使用することです。 次の手順では、Web サービスをセットアップする構成でリソースを使用する方法について説明します。

1. [Install-Module](https://technet.microsoft.com/en-us/library/dn807162.aspx) コマンドレットを呼び出して、**xPSDesiredStateConfiguration** モジュールをインストールします。 **注**: **Install-Module** は、PowerShell 5.0 に含まれている **PowerShellGet** モジュールに含まれています。 「[PackageManagement PowerShell Modules Preview (PackageManagement PowerShell モジュールのプレビュー)](https://www.microsoft.com/en-us/download/details.aspx?id=49186)」で PowerShell 3.0 と 4.0 の **PowerShellGet** モジュールをダウンロードできます。 
1. `CERT:\LocalMachine\MY\` ストアにサブジェクトを `"CN=PSDSCPullServerCert"` にして自己署名証明書を作成します。 これを行うには、`New-SelfSignedCertificate  -CertStoreLocation 'CERT:\LocalMachine\MY' -DnsName "PSDSCPullServerCert"` コマンドを使用します。
1. PowerShell ISE で、次の構成スクリプトを起動 (F5) します (このスクリプトは、**xPSDesiredStateConfiguration** モジュールの Example フォルダーに Sample_xDscWebService.ps1 として存在します)。 このスクリプトは、プル サーバーおよびコンプライアンス サーバーをセットアップします。
  
```powershell
configuration Sample_xDscWebService 
6 { 
7     param  
8     ( 
9         [string[]]$NodeName = 'localhost', 
10 
 
11         [ValidateNotNullOrEmpty()] 
12         [string] $certificateThumbPrint 
13     ) 
14 
 
15     Import-DSCResource -ModuleName xPSDesiredStateConfiguration 
16 
 
17     Node $NodeName 
18     { 
19         WindowsFeature DSCServiceFeature 
20         { 
21             Ensure = "Present" 
22             Name   = "DSC-Service"             
23         } 
24 
 
25         xDscWebService PSDSCPullServer 
26         { 
27             Ensure                  = "Present" 
28             EndpointName            = "PSDSCPullServer" 
29             Port                    = 8080 
30             PhysicalPath            = "$env:SystemDrive\inetpub\PSDSCPullServer" 
31             CertificateThumbPrint   = $certificateThumbPrint          
32             ModulePath              = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Modules" 
33             ConfigurationPath       = "$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration"             
34             State                   = "Started" 
35             DependsOn               = "[WindowsFeature]DSCServiceFeature"                         
36         } 
```

1. 構成を実行して、作成した自己署名証明書の拇印を **certificateThumbPrint** パラメーターとして渡します。

```powershell
PS:\>$myCert = Get-ChildItem CERT:\LocalMachine\My | Where-Object {$_.Subject -eq 'CN=PSDSCPullServerCert'}
PS:\>Sample_xDSCService -certificateThumbprint $myCert.Thumbprint 
```

## 登録キー
サーバーにクライアント ノードを登録できるようにして、構成 ID の代わりに構成名を使用できるようにするには、`RegistrationKeys.txt` という名前のファイルに、登録キー (サーバーとクライアント ノードの両方に認識される GUID) を配置する必要があります。 既定では、この例で作成されるプル サーバーでは、そのファイルが `C:\Program Files\WindowsPowerShell\DscService` にあることを想定します。 登録キーから成る 1 行のみのテキスト ファイルを作成して、そのフォルダーに保存します。
> **注**: 登録キーは、PowerShell 4.0 ではサポートされていません。 

## 構成とリソースの配置
プル サーバーのセットアップが完了した後、`$env:PROGRAMFILES\WindowsPowerShell` の下に "DscService" という名前の新しいフォルダーがあります。 そのフォルダーには、"Modules" および "Configuration" という 2 つのフォルダーがあります。 "Modules" フォルダーには、ノードがこのサーバーからプルする構成に必要となるすべてのリソースを配置します。 "Configuration" フォルダーには、ノードによってプルされる構成の構成 MOF ファイルを配置します。 MOF ファイルの名前は、プル クライアントの種類によって異なります。 次のトピックでは、プル クライアントのセットアップについて詳しく説明します。

* [構成 ID を使用した DSC プル クライアントのセットアップ](pullClientConfigID.md)
* [構成名を使用した DSC プル クライアントのセットアップ](pullClientConfigNames.md)
* [部分構成](partialConfigs.md)

## MOF チェックサムの作成
ターゲット ノード上の LCM が構成を検証できるように、構成 MOF ファイルはチェックサム ファイルと組み合わせて使用する必要があります。 チェックサムを作成するには、[New-DSCCheckSum](https://technet.microsoft.com/en-us/library/dn521622.aspx) コマンドレットを呼び出します。 このコマンドレットは、構成 MOF が存在するフォルダーが指定された **Path** パラメーターを受け取ります。 このコマンドレットは、`ConfigurationMOFName.mof.checksum` という名前でチェックサム ファイルを作成します。ここで、`ConfigurationMOFName` は構成 MOF ファイルの名前です。 指定のフォルダーに複数の構成 MOF ファイルがある場合は、そのフォルダー内の構成ごとにチェックサムが作成されます。

チェックサム ファイルは、構成 MOF ファイルと同じディレクトリ (既定では `$env:PROGRAMFILES\WindowsPowerShell\DscService\Configuration`) に存在し、拡張子として `.checksum` が付けられた同じ名前である必要があります。

>**注**: 何らかの方法で構成 MOF ファイルを変更した場合は、チェックサム ファイルも作成し直す必要があります。

## 関連項目
* [Windows PowerShell Desired State Configuration の概要](overview.md)
* [構成の適用](enactingConfigurations.md)
* [How to retrieve node information from DSC pull server (DSC プル サーバーからノード情報を取得する方法)](retrieveNodeInfo.md)


<!--HONumber=Mar16_HO1-->


