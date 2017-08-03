---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: WinRMSecurity
ms.openlocfilehash: a6adf61517708661e31a7387df5141f3c4f2c020
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="powershell-remoting-security-considerations"></a>PowerShell リモート処理のセキュリティに関する考慮事項

PowerShell リモート処理は、Windows システムの管理に推奨されている方法です。 Windows Server 2012 R2 では、PowerShell リモート処理が既定で有効になっています。 このドキュメントでは、PowerShell リモート処理を使用する場合のセキュリティ上の問題、推奨事項、およびベスト プラクティスを取り上げています。

## <a name="what-is-powershell-remoting"></a>PowerShell リモート処理とは

PowerShell リモート処理は、[Windows リモート管理 (WinRM)](https://msdn.microsoft.com/en-us/library/windows/desktop/aa384426.aspx) を使用しています。これは、ユーザーがリモート コンピューター上で PowerShell コマンドを実行できるように、Microsoft によって [Web Services for Management (WS-Management)](http://www.dmtf.org/sites/default/files/standards/documents/DSP0226_1.2.0.pdf) プロトコルが実装されたものです。 PowerShell リモート処理の使用方法の詳細については、「[リモート コマンドの実行](https://technet.microsoft.com/en-us/library/dd819505.aspx)」を参照してください。

PowerShell リモート処理は、コマンドレットの **ComputerName** パラメーターを使用してリモート コンピューターでコマンドを実行することとは異なります。この場合は、基盤となるプロトコルとしてリモート プロシージャ コール (RPC) が使用されています。

##  <a name="powershell-remoting-default-settings"></a>PowerShell リモート処理の既定の設定

PowerShell リモート処理 (および WinRM) は、次のポートをリッスンします。

- HTTP: 5985
- HTTPS: 5986

既定では、PowerShell リモート処理で許可されている接続は、Administrators グループのメンバーからのもののみです。 セッションはユーザーのコンテキストで開始されるため、PowerShell リモート処理を介して接続されている間は、個々のユーザーとグループに適用されているオペレーティング システムのアクセス制御がすべて、そのセッションに引き続き適用されます。

プライベート ネットワークの場合、PowerShell リモート処理の既定の Windows ファイアウォール規則はすべての接続を受け入れます。 パブリック ネットワークの場合、既定の Windows ファイアウォール規則で許可されるのは、同じサブネット内からの PowerShell リモート処理接続のみです。 パブリック ネットワーク上のすべての接続に対して PowerShell リモート処理を可能にするには、その規則を明示的に変更する必要があります。

>**警告:** パブリック ネットワークのファイアウォール規則は、悪意のある外部接続からコンピューターを保護することを目的としています。 この規則を削除する際は注意してください。

## <a name="process-isolation"></a>プロセスの分離

PowerShell リモート処理では、コンピューター間の通信に [Windows リモート管理 (WinRM)](https://msdn.microsoft.com/en-us/library/windows/desktop/aa384426) を使用します。 WinRM は Network Service アカウントでサービスとして実行されており、ユーザー アカウントとして実行される分離プロセスを生成して、PowerShell インスタンスをホストします。 1 ユーザーとして実行されている PowerShell のインスタンスは、別のユーザーとして PowerShell のインスタンスを実行しているプロセスにアクセスすることはできません。

## <a name="event-logs-generated-by-powershell-remoting"></a>PowerShell リモート処理によって生成されたイベント ログ

FireEye は、PowerShell リモート処理セッションによって生成されたイベント ログやその他のセキュリティ証拠をまとめたものを提供しています。これは、概要をまとめられています。これについては、  
[Investigating PowerShell Attacks (PowerShell 攻撃の調査)」を参照してください](https://www.fireeye.com/content/dam/fireeye-www/global/en/solutions/pdfs/wp-lazanciyan-investigating-powershell-attacks.pdf)。

## <a name="encryption-and-transport-protocols"></a>暗号化とトランスポート プロトコル

PowerShell リモート処理の接続のセキュリティについては、初期認証と進行中の通信という 2 つの観点から考慮することをお勧めします。 

使用されているトランスポート プロトコル (HTTP または HTTPS) に関係なく、PowerShell リモート処理では、常にすべての通信が、初期認証後に、セッションごとの AES 256 対称キーを使用して暗号化されます。
    
### <a name="initial-authentication"></a>初期認証

認証では、サーバーに対するクライアントの ID と、理想的にはクライアントに対するサーバーを確認します。
    
クライアントがコンピューター名 (server01 や server01.contoso.com など) を使用してドメイン サーバーに接続する場合、既定の認証プロトコルは [Kerberos](https://msdn.microsoft.com/en-us/library/windows/desktop/aa378747.aspx) です。
Kerberos では、再利用可能な資格情報を送信しなくても、ユーザー ID とサーバー ID の両方が保証されます。

クライアントが IP アドレスを使用してドメイン サーバーに接続する場合、またはワークグループ サーバーに接続する場合は、Kerberos 認証を使用できません。 その場合は、PowerShell リモート処理は [NTLM 認証プロトコル](https://msdn.microsoft.com/en-us/library/windows/desktop/aa378749.aspx)を利用します。 NTLM 認証プロトコルでは、委任可能な資格情報を送信しなくてもユーザー ID が保証されます。 NTLM プロトコルは、ユーザー ID を証明するために、クライアントとサーバーの両方でユーザーのパスワードからセッション キーを計算することを要求します。パスワード自体は交換しません。 サーバーは、通常ユーザーのパスワードを知らないため、ドメイン コントローラーと通信します。ドメイン コントローラーがユーザーのパスワードを知っていて、サーバー用にセッション キーを計算します。 
      
一方、NTLM プロトコルでは、サーバー ID が保証されません。 ドメインに参加しているコンピューターのコンピューター アカウントにアクセスできる攻撃者は、認証に NTLM を使用するプロトコルと同様にドメイン コントローラーを呼び出して NTLM セッション キーを計算することで、サーバーになりすます場合があります。

NTLM ベースの認証は既定では無効になっていますが、ターゲット サーバーで SSL を構成するか、クライアントで WinRM TrustedHosts 設定を構成することで許可できます。
    
#### <a name="using-ssl-certificates-to-validate-server-identity-during-ntlm-based-connections"></a>NTLM ベースの接続時に SSL 証明書を使用してサーバー ID を検証する

NTLM 認証プロトコルではターゲット サーバーの ID を保証できないため (パスワードを認識しているだけのため)、PowerShell リモート処理に SSL を使用するようターゲット サーバーを構成できます。 SSL 証明書をターゲット サーバーに割り当てると (クライアントも信頼している証明機関によって発行されている場合)、ユーザー ID とサーバー ID の両方が保証される NTLM ベースの認証が可能になります。
    
#### <a name="ignoring-ntlm-based-server-identity-errors"></a>NTLM ベースのサーバー ID を無視する
      
SSL 証明書を NTLM 接続用のサーバーに展開できない場合は、そのサーバーを WinRM の **TrustedHosts** 一覧に追加することで ID エラーの発生を抑制できます。 ホスト自体の信頼性を示すために、サーバー名を TrustedHosts の一覧に追加することは考えないでください。NTLM 認証プロトコルでは、実際に接続しているホストが、必ずしも意図して接続しているホストであるとは限りません。
代わりに、TrustedHosts の設定を、サーバーの ID を確認できないことが原因で生成されたエラーを抑制するホストの一覧と考える必要があります。
    
    
### <a name="ongoing-communication"></a>進行中の通信

初期認証が完了すると、[PowerShell リモート処理プロトコル](https://msdn.microsoft.com/en-us/library/dd357801.aspx)によって、進行中の通信はすべて、セッションごとの AES 256 対称キーを使用して暗号化されます。  


## <a name="making-the-second-hop"></a>次ホップの実行

PowerShell リモート処理では、既定で、認証に Kerberos (使用可能な場合) または NTLM が使用されます。 このどちらのプロトコルも、資格情報を送信することなく、リモート コンピューターに対して認証を行います。
これは認証方法としては最も安全ですが、リモート コンピューターにユーザーの資格情報がないため、このリモート コンピューターは、ユーザーに代わって他のコンピューターおよびサービスにアクセスすることはできません。 これは "次ホップの問題" と呼ばれます。

この問題を回避する方法はいくつかあります。 これらの方法およびその長所と短所については、「[PowerShell リモート処理での次ホップの実行](PS-remoting-second-hop.md)」をご覧ください。










