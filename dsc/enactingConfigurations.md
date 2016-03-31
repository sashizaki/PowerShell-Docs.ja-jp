# 構成の適用

>適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

PowerShell Desired State Configuration (DSC) 構成を適用するには、プッシュ モードとプル モードの 2 つの方法があります。

## プッシュ モード
![プッシュ モード](images/Push.png "How push mode works")

プッシュ モードは、[Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) コマンドレットを呼び出してターゲット ノードに構成を適用するユーザー アクティビティを示します。

構成を作成し、コンパイルした後、プッシュ モードで適用するには、[Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) コマンドレットを呼び出し、コマンドレットの -Path パラメーターを構成 MOF が配置されているパスに設定します。 たとえば、構成 MOF が `C:\DSC\Configurations\localhost.mof` にある場合は、次のコマンドを使用してローカル コンピューターに適用します。
`Start-DscConfiguration -Path 'C:\DSC\Configurations'`

> __注__: 既定では、DSC はバックグラウンド ジョブとして構成を実行します。 構成を対話的に実行するには、__-Wait__ パラメーターを指定して [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) を呼び出します。

クラウド展開エンジンは、通常、より広範な展開ソリューション内でプル モードを活用します。  たとえば、Microsoft Azure は、仮想マシンの [DSC 拡張](https://azure.microsoft.com/en-us/documentation/articles/virtual-machines-extensions-features/)を提供します。  これにより、展開の一部として仮想マシン内で抽出され、実行されるアーカイブ ファイルに構成スクリプトと必要なすべての DSC モジュールを含めるためのオプションが提供されます。  

## プル モード
![プル モード](images/Pull.png "How pull mode works")
プル モードでは、プル クライアントはリモート プル サーバーから Desired State Configuration を取得するように構成されます。 同様に、プル サーバーは、DSC サービスをホストするようにセットアップされ、プル クライアントに必要な構成とリソースを使用してプロビジョニングされています。
それぞれのプル クライアントには、ノードの構成に対して定期的なコンプライアンス チェックを実行するタスクがスケジュールされています。 イベントが最初にトリガーされたとき、プル クライアント上のローカル構成マネージャー (LCM) によって構成の検証が行われます。 プル クライアントが期待どおりに構成されている場合は、何も起こりません。 期待どおりに構成されていない場合、LCM は指定された構成を取得するようプル サーバーに要求します。 プル サーバーにその構成が存在し、最初の検証チェックに合格した場合、構成はプル クライアントに送信され、LCM によって実行されます。

DSC プル サーバーをオンプレミスで展開する方法の詳細については、『DSC Pull Server Configuration and Planning Guide (DSC プル サーバー構成および計画ガイド)』を参照してください。

オンライン サービスを利用してプル サーバー機能をホストする場合は、「[Azure Automation DSC の概要](https://azure.microsoft.com/en-us/documentation/articles/automation-dsc-overview/)」を参照してください。

次のトピックでは、プル サーバーとクライアントをセットアップする方法について説明します。

- [Setting up a web pull server (Web プル サーバーのセットアップ)](pullServer.md)
- [Setting up an SMB pull server (SMB プル サーバーのセットアップ)](pullServerSMB.md)
- [Configuring a pull client (プル クライアントの構成)](pullClientConfigID.md)

<!--HONumber=Feb16_HO4-->


