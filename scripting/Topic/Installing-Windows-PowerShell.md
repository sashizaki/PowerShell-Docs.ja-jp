---
title: Windows PowerShell のインストール
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6fbb0409-5a54-48ec-95e6-7f8b7d8c4969
---
# Windows PowerShell のインストール
[!INCLUDE[win8_client_1](../Token/win8_client_1_md.md)] と [!INCLUDE[win8_server_1](../Token/win8_server_1_md.md)] には [!INCLUDE[psversion3](../Token/psversion3_md.md)] とそのすべての前提条件が含まれます。 システムには、[!INCLUDE[psversion3](../Token/psversion3_md.md)] を使用できないホスト プログラムとの下位互換性のために [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンも含まれています。

このトピックでは、以前のシステムに [!INCLUDE[psversion3](../Token/psversion3_md.md)] をインストールし、必要な機能をインストールして有効にする方法を説明します。

このトピックには、次のセクションが含まれています。

-   [Windows 8 と Windows Server 2012 での Windows PowerShell のインストール](../Topic/Installing-Windows-PowerShell.md#BKMK_InstallingOnWindows8andWindowsServer2012)

-   [Windows 7 と Windows Server 2008 R2 での Windows PowerShell のインストール](../Topic/Installing-Windows-PowerShell.md#BKMK_InstallingOnWindows7andWindowsServer2008R2)

-   [Windows Server 2008 での Windows PowerShell のインストール](../Topic/Installing-Windows-PowerShell.md#BKMK_InstallingOnWindowsServer2008LH)

-   [Server Core での Windows PowerShell のインストール](../Topic/Installing-Windows-PowerShell.md#BKMK_InstallingOnServerCore)

-   [Windows PowerShell Web Access の展開](assetId:///639d0eff-98a3-4124-b52c-26921ebd98b0)

-   [Windows PowerShell 2.0 エンジンのインストール](../Topic/Installing-the-Windows-PowerShell-2.0-Engine.md)

## <a name="BKMK_InstallingOnWindows8andWindowsServer2012"></a>Windows 8 と Windows Server 2012 での Windows PowerShell のインストール
[!INCLUDE[psversion3](../Token/psversion3_md.md)] は最初からインストールと構成が済んでおり、使用準備が整った状態です。 [!INCLUDE[mshgraphicalhost](../Token/mshgraphicalhost_md.md)] はインストール済みの有効な状態です。 [!INCLUDE[mshshort](../Token/mshshort_md.md)] を開始する方法の詳細については、「[Windows 8 で Windows PowerShell を開始する](assetId:///d7be1668-8617-4890-ad90-dd9765fbd2c3)」と「[Windows Server 2012 で Windows PowerShell を開始する](assetId:///4fc0110a-cc0c-42a4-bbb5-3cc89a0fc968)」をご覧ください。

## <a name="BKMK_InstallingOnWindows7andWindowsServer2008R2"></a>Windows 7 と Windows Server 2008 R2 での Windows PowerShell のインストール
次に挙げる手順では、[!INCLUDE[win7_client_secondref](../Token/win7_client_secondref_md.md)] Service Pack 1 と [!INCLUDE[win7_server_secondref](../Token/win7_server_secondref_md.md)] Service Pack 1 を実行するコンピューターに [!INCLUDE[psversion3](../Token/psversion3_md.md)] をインストールする方法を説明します。 その下には、[!INCLUDE[win7_server_secondref](../Token/win7_server_secondref_md.md)] の Server Core インストール オプションを使用して実行するコンピューター用に、インストール手順が別に用意されています。

#### インストールの準備を行う

-   [!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] をインストールする前に、以前のバージョンの Windows Management Framework 3.0 をすべてアンインストールします。

#### [!INCLUDE[psversion3](../Token/psversion3_md.md)] をインストールするには

1.  Microsoft .NET Framework 4 (dotNetFx40_Full_setup.exe) を Microsoft ダウンロード センター ([http://go.microsoft.com/fwlink/?LinkID=212547](http://go.microsoft.com/fwlink/?LinkID=212547)) から完全インストールします。

    または、Microsoft .NET Framework 4.5 (dotNetFx45_Full_setup.exe) を Microsoft ダウンロード センター ([http://go.microsoft.com/fwlink/?LinkID=242919](http://go.microsoft.com/fwlink/?LinkID=242919)) からインストールします。

2.  [!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] を Microsoft ダウンロード センター ([http://go.microsoft.com/fwlink/?LinkID=240290](http://go.microsoft.com/fwlink/?LinkID=240290)) からインストールします。

[!INCLUDE[psversion3](../Token/psversion3_md.md)] を開始する方法の詳細については、「[以前のバージョンの Windows で Windows PowerShell を開始する](../Topic/Starting-Windows-PowerShell-on-Earlier-Versions-of-Windows.md)」をご覧ください。

## <a name="BKMK_InstallingOnServerCore"></a>Server Core での Windows PowerShell のインストール
次に挙げる手順では、[!INCLUDE[win7_server_secondref](../Token/win7_server_secondref_md.md)] Service Pack 1 の Server Core インストール オプションを実行するコンピューターに [!INCLUDE[psversion3](../Token/psversion3_md.md)] をインストールする方法を説明します。

手順の最初の操作では、展開イメージのサービスと管理 (DISM) コマンドを使用して、Server Core 対応 Microsoft [!INCLUDE[dnprdnlong](../Token/dnprdnlong_md.md)] と [!INCLUDE[psversion2](../Token/psversion2_md.md)] をインストールします。 これらのプログラムは、以降の操作でインストールする [!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] の前提条件です。

#### インストールの準備を行う

-   [!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] をインストールする前に、以前のバージョンの Windows Management Framework 3.0 をすべてアンインストールします。

#### [!INCLUDE[psversion3](../Token/psversion3_md.md)] をインストールするには

1.  Cmd.exe を起動します

2.  次の DISM コマンドを実行します。 これらのコマンドは、[!INCLUDE[dnprdnlong](../Token/dnprdnlong_md.md)] と [!INCLUDE[psversion2](../Token/psversion2_md.md)] をインストールします。

    ```
    dism /online /enable-feature:NetFx2-ServerCore
    dism /online /enable-feature:MicrosoftWindowsPowerShell
    dism /online /enable-feature:NetFx2-ServerCore-WOW64
    ```

3.  Server Core 対応 Microsoft [!INCLUDE[netfx40_short](../Token/netfx40_short_md.md)] を Microsoft ダウンロード センター ([http://go.microsoft.com/fwlink/?LinkID=248450](http://go.microsoft.com/fwlink/?LinkID=248450)) から完全インストールします。

4.  [!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] を Microsoft ダウンロード センター ([http://go.microsoft.com/fwlink/?LinkID=240290](http://go.microsoft.com/fwlink/?LinkID=240290)) からインストールします。

## <a name="BKMK_InstallingOnWindowsServer2008LH"></a>Windows Server 2008 での Windows PowerShell のインストール
次に挙げる手順では、[!INCLUDE[lserver](../Token/lserver_md.md)] Service Pack 2 を実行するコンピューターに [!INCLUDE[psversion3](../Token/psversion3_md.md)] をインストールする方法を説明します。

[!INCLUDE[lserver](../Token/lserver_md.md)] システムでは、Windows Management Framework ([!INCLUDE[psversion2](../Token/psversion2_md.md)]、KB 968930) が [!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] の前提条件です。 "認証の拡張保護" 機能を使用すると、コンピューターを認証転送攻撃から保護したり、リモート セッションの作成時に **UseSSL** パラメーターを使用したりできます。 [!INCLUDE[psversion3](../Token/psversion3_md.md)] と [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンをインストールするには、以下の手順に従います。

#### インストールの準備を行う

-   [!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] をインストールする前に、以前のバージョンの Windows Management Framework 3.0 をすべてアンインストールします。

#### [!INCLUDE[psversion3](../Token/psversion3_md.md)] をインストールするには

1.  Microsoft .NET Framework 3.5 Service Pack 1 を Microsoft ダウンロード センター ([http://go.microsoft.com/fwlink/?LinkID=242910](http://go.microsoft.com/fwlink/?LinkID=242910)) からインストールします。

2.  Windows Management Framework ([!INCLUDE[psversion2](../Token/psversion2_md.md)]、KB 968930) を Microsoft ダウンロード センター ([http://go.microsoft.com/fwlink/?LinkId=243035](http://go.microsoft.com/fwlink/?LinkId=243035)) からインストールします。

3.  Microsoft .NET Framework 4 (dotNetFx40_Full_setup.exe) を Microsoft ダウンロード センター ([http://go.microsoft.com/fwlink/?LinkID=212547](http://go.microsoft.com/fwlink/?LinkID=212547)) から完全インストールします。

    または、Microsoft .NET Framework 4.5 (dotNetFx45_Full_setup.exe) を Microsoft ダウンロード センター ([http://go.microsoft.com/fwlink/?LinkID=242919](http://go.microsoft.com/fwlink/?LinkID=242919)) からインストールします。

4.  "認証の拡張保護" (KB 968389) を [http://go.microsoft.com/fwlink/?LinkID=186398](http://go.microsoft.com/fwlink/?LinkID=186398) からインストールします。

5.  [!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] を Microsoft ダウンロード センター ([http://go.microsoft.com/fwlink/?LinkID=240290](http://go.microsoft.com/fwlink/?LinkID=240290)) からインストールします。

## 参照
[Windows PowerShell のシステム要件](../Topic/Windows-PowerShell-System-Requirements.md)
[Windows PowerShell [ps] を開始する](assetId:///8ec8c2d7-8e7c-4722-a3d2-498fe5739a8e)



<!--HONumber=Apr16_HO1-->


