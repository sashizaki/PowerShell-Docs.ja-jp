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
[!INCLUDE[wps_2](../Token/wps_2_md.md)] をインストールして起動したら、次のセットアップ オプションを実行することを検討してください。 これらのタスクは、いつでも実行できます。

-   **ヘルプ ファイルをインストールします。** [!INCLUDE[psversion3](../Token/psversion3_md.md)] に含まれているコマンドレットには、ヘルプ ファイルが付属していません。 ただし、[Update-Help](https://technet.microsoft.com/en-us/library/93e1d870-ace6-432b-8778-8920291d7545) コマンドレットを使うと、最新のヘルプ ファイルをダウンロードしてコンピューターにインストールできます。 ファイルをインストールしたら、[Get-Help](https://technet.microsoft.com/en-us/library/1f46eeb4-49d7-4bec-bb29-395d9b42f54a) コマンドレットを使ってコマンド ラインに表示します。 詳しくは、「[about_Updatable_Help](https://technet.microsoft.com/en-us/library/10bba75c-f4ac-4ca1-bbf3-8f34dd521ffe)」をご覧ください。

    ヘルプ ファイルをインストールしない場合でも、ヘルプ トピックをオンラインで読むことができます。 特定のコマンドレットのオンライン バージョンのヘルプ トピックを見つけるには、「`Get-Help <CmdletName> -Online`」と入力します。 TechNet ライブラリで [!INCLUDE[wps_2](../Token/wps_2_md.md)] のヘルプ トピックを読むには、[http://go.microsoft.com/fwlink/?LinkID=107116](http://go.microsoft.com/fwlink/?LinkID=107116) をご覧ください。

-   **スクリプトを実行します。** [!INCLUDE[mshshort](../Token/mshshort_md.md)] をセキュリティで保護するため、[!INCLUDE[mshshort](../Token/mshshort_md.md)] の既定の実行ポリシーは **Restricted** になっています。 このポリシーによると、コマンドレットは実行できますが、スクリプトは実行できません。 スクリプトを実行するには、[Set-ExecutionPolicy[PSITPro5_Security]](https://technet.microsoft.com/en-us/library/5690a0e1-495b-4e63-8280-65ead7bf01ab) コマンドレットを使って、実行ポリシーを **AllSigned** や **RemoteSigned** に変更します。 コンピューターの Administrators グループのメンバーだけが、このコマンドレットを実行できます。 詳しくは、「[about_Execution_Policies [v4]](https://technet.microsoft.com/en-us/library/347708dc-1515-4d74-978b-8334603472e6)」をご覧ください。

-   **リモート処理を有効にします。** システムは、他のコンピューターでリモート コマンドを実行できるように既に構成されています。 [!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)] と [!INCLUDE[win8_server_2](../Token/win8_server_2_md.md)] では、システムはリモート コマンドを受信できるようにも構成されています。つまり、他のコンピューターがローカル コンピューターでリモート コマンドを実行できるようになっています。 Windows の他のバージョンを実行しているコンピューターがリモート コマンドを受信できるようにするには、リモートから管理するコンピューター上で [Enable-PSRemoting](https://technet.microsoft.com/en-us/library/19437c28-33b8-4ac1-9113-8439cc8beffb) コマンドレットを実行します。 コンピューターの Administrators グループのメンバーだけが、このコマンドレットを実行できます。 詳しくは、「[about_Remote](https://technet.microsoft.com/en-us/library/9b4a5c87-9162-4adf-bdfe-fbc80b9b8970)」をご覧ください。

    注: [!INCLUDE[psversion2](../Token/psversion2_md.md)] を実行しているコンピューターでリモート処理が有効になっている場合は、[!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] をインストールした後も、リモート処理は引き続き有効のままです。 ただし、[!INCLUDE[lserver](../Token/lserver_md.md)] ([!INCLUDE[win7_server_secondref](../Token/win7_server_secondref_md.md)] ではない) 上では、[!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] をインストールした後でリモート処理を再度有効にする必要があります。

## 参照
[Windows PowerShell のインストール](../Topic/Installing-Windows-PowerShell.md)
[Windows PowerShell [ps] の開始](https://technet.microsoft.com/en-us/library/8ec8c2d7-8e7c-4722-a3d2-498fe5739a8e)



<!--HONumber=Apr16_HO2-->


