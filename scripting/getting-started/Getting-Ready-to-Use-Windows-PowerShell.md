---
title: Windows PowerShell を使用する準備を行う
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6dc7052d-cc5a-4220-950f-98f963a2b587
---
# Windows PowerShell を使用する準備を行う
Windows PowerShell をインストールして起動したら、次のセットアップ オプションを実行することを検討してください。 これらのタスクは、いつでも実行できます。

-   **ヘルプ ファイルをインストールします。** Windows PowerShell 3.0 に含まれているコマンドレットには、ヘルプ ファイルが付属していません。 ただし、[Update-Help](https://technet.microsoft.com/en-us/library/93e1d870-ace6-432b-8778-8920291d7545) コマンドレットを使うと、最新のヘルプ ファイルをダウンロードしてコンピューターにインストールできます。 ファイルをインストールしたら、[Get-Help](https://technet.microsoft.com/en-us/library/1f46eeb4-49d7-4bec-bb29-395d9b42f54a) コマンドレットを使ってコマンド ラインに表示します。 詳細については、[about_Updatable_Help](https://technet.microsoft.com/en-us/library/10bba75c-f4ac-4ca1-bbf3-8f34dd521ffe) に関するページを参照してください。.

    ヘルプ ファイルをインストールしない場合でも、ヘルプ トピックをオンラインで読むことができます。 特定のコマンドレットのオンライン バージョンのヘルプ トピックを見つけるには、「`Get-Help <CmdletName> -Online`」と入力します。 TechNet ライブラリで Windows PowerShell のヘルプ トピックを読むには、[http://go.microsoft.com/fwlink/?LinkID=107116](http://go.microsoft.com/fwlink/?LinkID=107116) をご覧ください。.

-   **スクリプトを実行します。** Windows PowerShell のセキュリティを維持するために、Windows PowerShell の既定の実行ポリシーは **制限あり** になっています。 このポリシーによると、コマンドレットは実行できますが、スクリプトは実行できません。 スクリプトを実行するには、[Set-ExecutionPolicy[PSITPro5_Security]](https://technet.microsoft.com/en-us/library/5690a0e1-495b-4e63-8280-65ead7bf01ab) コマンドレットを使って、実行ポリシーを **AllSigned** や **RemoteSigned** に変更します。 コンピューターの Administrators グループのメンバーだけが、このコマンドレットを実行できます。 詳細については、「[about_Execution_Policies [v4]](https://technet.microsoft.com/en-us/library/347708dc-1515-4d74-978b-8334603472e6)」を参照してください。.

-   **リモート処理を有効にします。** システムは、他のコンピューターでリモート コマンドを実行できるように既に構成されています。 Windows Server 2012 R2 と Windows Server 2012 では、システムはリモート コマンドを受信できるようにも構成されています。つまり、他のコンピューターがローカル コンピューターでリモート コマンドを実行できるようになっています。 Windows の他のバージョンを実行しているコンピューターがリモート コマンドを受信できるようにするには、リモートから管理するコンピューター上で [Enable-PSRemoting](https://technet.microsoft.com/en-us/library/19437c28-33b8-4ac1-9113-8439cc8beffb) コマンドレットを実行します。 コンピューターの Administrators グループのメンバーだけが、このコマンドレットを実行できます。 詳細については、「[about_Remote](https://technet.microsoft.com/en-us/library/9b4a5c87-9162-4adf-bdfe-fbc80b9b8970)」を参照してください。.

    注: Windows PowerShell 2.0 を実行しているコンピューターでリモート処理が有効になっている場合は、Windows Management Framework 3.0 をインストールした後も、リモート処理は引き続き有効のままです。 ただし、Windows Server 2008 (Windows Server 2008 R2 ではない) では、Windows Management Framework 3.0 をインストールした後に re\-enable のリモート処理が必要です。

## 参照
[Windows PowerShell のインストール](../setup/Installing-Windows-PowerShell.md)
[Windows PowerShell [ps] の開始](https://technet.microsoft.com/en-us/library/8ec8c2d7-8e7c-4722-a3d2-498fe5739a8e)



<!--HONumber=May16_HO2-->


