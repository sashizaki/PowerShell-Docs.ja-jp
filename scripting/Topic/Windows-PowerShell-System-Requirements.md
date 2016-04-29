---
title: Windows PowerShell のシステム要件
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6d1d3c75-3be4-4fc9-8805-ca9b2c454d42
---
# Windows PowerShell のシステム要件
このトピックでは、[!INCLUDE[psversion3](../Token/psversion3_md.md)]、[!INCLUDE[psversion4](../Token/psversion4_md.md)]、特別な機能 ([!INCLUDE[mshgraphicalhost](../Token/mshgraphicalhost_md.md)]、CIM コマンド、ワークフローなど) のシステム要件を一覧表示します。

[!INCLUDE[winblue_client_1](../Token/winblue_client_1_md.md)] と [!INCLUDE[winblue_server_1](../Token/winblue_server_1_md.md)] には必要なすべてのプログラムが含まれています。 このトピックは、以前のリリースの Windows のユーザー向けです。

## オペレーティング システムの要件
[!INCLUDE[psversion4](../Token/psversion4_md.md)] は、次のバージョンの Windows で実行できます。

-   [!INCLUDE[winblue_client_2](../Token/winblue_client_2_md.md)] (既定でインストールされています)

-   [!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)] (既定でインストールされています)

-   [!INCLUDE[win7_client_firstref](../Token/win7_client_firstref_md.md)] (Service Pack 1 適用済み) では、[Windows Management Framework 4.0](http://go.microsoft.com/fwlink/?LinkId=293881) をインストールして [!INCLUDE[psversion4](../Token/psversion4_md.md)] を実行します

-   [!INCLUDE[win7_server_firstref](../Token/win7_server_firstref_md.md)] (Service Pack 1 適用済み) では、[Windows Management Framework 4.0](http://go.microsoft.com/fwlink/?LinkId=293881) をインストールして [!INCLUDE[psversion4](../Token/psversion4_md.md)] を実行します

[!INCLUDE[psversion3](../Token/psversion3_md.md)] は、次のバージョンの Windows で実行できます。

-   [!INCLUDE[win8_client_2](../Token/win8_client_2_md.md)] (既定でインストールされています)

-   [!INCLUDE[win8_server_2](../Token/win8_server_2_md.md)] (既定でインストールされています)

-   [!INCLUDE[win7_client_firstref](../Token/win7_client_firstref_md.md)] (Service Pack 1 適用済み) では、[Windows Management Framework 3.0](http://www.microsoft.com/download/details.aspx?id=34595) をインストールして [!INCLUDE[psversion3](../Token/psversion3_md.md)] を実行します

-   [!INCLUDE[win7_server_firstref](../Token/win7_server_firstref_md.md)] (Service Pack 1 適用済み) では、[Windows Management Framework 3.0](http://www.microsoft.com/download/details.aspx?id=34595) をインストールして [!INCLUDE[psversion3](../Token/psversion3_md.md)] を実行します

-   [!INCLUDE[lserver](../Token/lserver_md.md)] (Service Pack 2 適用済み) では、[Windows Management Framework 3.0](http://www.microsoft.com/download/details.aspx?id=34595) をインストールして [!INCLUDE[psversion3](../Token/psversion3_md.md)] を実行します

## Microsoft .NET Framework の要件
[!INCLUDE[psversion4](../Token/psversion4_md.md)] には Microsoft .NET Framework 4.5 のフル インストールが必要です。 [!INCLUDE[winblue_client_2](../Token/winblue_client_2_md.md)] および [!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)] には既定で Microsoft .NET Framework 4.5 が含まれます。

[!INCLUDE[psversion3](../Token/psversion3_md.md)] には Microsoft .NET Framework 4 のフル インストールが必要です。 [!INCLUDE[win8_client_2](../Token/win8_client_2_md.md)] および [!INCLUDE[win8_server_2](../Token/win8_server_2_md.md)] には既定で Microsoft .NET Framework 4.5 が含まれるため、この要件は満たされています。

Microsoft .NET Framework 4.5 (dotNetFx45_Full_setup.exe) をインストールするには、Microsoft ダウンロード センターの「[Microsoft .NET Framework 4.5](http://go.microsoft.com/fwlink/?LinkID=242919)」をご覧ください。

Microsoft .NET Framework 4 (dotNetFx40_Full_setup.exe) をフル インストールするには、Microsoft ダウンロード センターの「[Microsoft .NET Framework 4 (Web インストーラー)](http://go.microsoft.com/fwlink/?LinkID=212931)」をご覧ください。

## WS-Management 3.0
[!INCLUDE[psversion3](../Token/psversion3_md.md)] および [!INCLUDE[psversion4](../Token/psversion4_md.md)] は、WinRM サービスおよび WSMan プロトコルをサポートする WS-Management 3.0 を必要とします。 このプログラムは [!INCLUDE[winblue_client_2](../Token/winblue_client_2_md.md)]、[!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)]、[!INCLUDE[win8_client_2](../Token/win8_client_2_md.md)]、[!INCLUDE[win8_server_2](../Token/win8_server_2_md.md)]、Windows Management Framework 4.0、[!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] に含まれています。

## Windows Management Instrumentation 3.0
[!INCLUDE[psversion3](../Token/psversion3_md.md)] および [!INCLUDE[psversion4](../Token/psversion4_md.md)] には Windows Management Instrumentation 3.0 (WMI) が必要です。 このプログラムは [!INCLUDE[winblue_client_2](../Token/winblue_client_2_md.md)]、[!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)]、[!INCLUDE[win8_client_2](../Token/win8_client_2_md.md)]、[!INCLUDE[win8_server_2](../Token/win8_server_2_md.md)]、Windows Management Framework 4.0、[!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] に含まれています。 このプログラムがコンピューターにインストールされていない場合、CIM コマンドなどの、WMI を必要とする機能は実行されません。

## 共通言語ランタイム 4.0
[!INCLUDE[psversion3](../Token/psversion3_md.md)] および [!INCLUDE[psversion4](../Token/psversion4_md.md)] は共通言語ランタイム (CLR) 4.0 に対してコンパイルされます。

## グラフィカル ユーザー インターフェイスの要件
[!INCLUDE[wps_2](../Token/wps_2_md.md)] はグラフィカル ユーザー インターフェイスを必要としないコンソール ベースのアプリケーションです。 そのため、画面 (モニター) もユーザー インターフェイスも持たない、[!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)] または [!INCLUDE[win8_server_2](../Token/win8_server_2_md.md)] の Server Core インストール オプションなどのコンピューターに適しています。

ただし、次のように一部グラフィカル ユーザー インターフェイスを必要とする項目もあります。 詳細については、各項目のヘルプ トピックをご覧ください。

-   [!INCLUDE[mshgraphicalhost](../Token/mshgraphicalhost_md.md)]

-   コマンドレット

    1.  [Out-GridView](assetId:///70915a86-d753-464e-8349-cba02316154c)

    2.  [Show-Command](assetId:///65bba50b-91a8-49d5-80a2-a30fc684ba41)

    3.  [Show-ControlPanelItem](assetId:///0685d42c-37cc-498f-acf6-0ecfeb0cb162)

    4.  [Show-EventLog](assetId:///a3b0f5ad-0438-42c7-915b-d1b4793a431c)

-   パラメーター

    1.  [Get-Help](assetId:///1f46eeb4-49d7-4bec-bb29-395d9b42f54a) コマンドレットの **ShowWindow** パラメーター。

    2.  [Register-PSSessionConfiguration](assetId:///e9152ae2-bd6d-4056-9bc7-dc1893aa29ea) と [Set-PSSessionConfiguration](assetId:///b21fbad3-1759-4260-b206-dcb8431cd6ea) コマンドレットの **ShowSecurityDescriptorUi** パラメーター。

## Windows PowerShell Engine の要件
[!INCLUDE[psversion4](../Token/psversion4_md.md)] は [!INCLUDE[psversion3](../Token/psversion3_md.md)] および [!INCLUDE[psversion2](../Token/psversion2_md.md)] との下位互換性を保つように設計されています。 [!INCLUDE[psversion2](../Token/psversion2_md.md)] と [!INCLUDE[psversion3](../Token/psversion3_md.md)] のために記述されたコマンドレット、プロバイダー、スナップイン、モジュール、スクリプトは [!INCLUDE[psversion4](../Token/psversion4_md.md)] でそのまま実行されます。

ただし、Microsoft .NET Framework 4 のランタイムのアクティブ化ポリシーの変更のため、[!INCLUDE[psversion2](../Token/psversion2_md.md)] 用に作成され共通言語ランタイム (CLR) 2.0 でコンパイルされた [!INCLUDE[wps_2](../Token/wps_2_md.md)] ホスト プログラムは、変更を加えなければ [!INCLUDE[psversion3](../Token/psversion3_md.md)] (CLR 4.0 でコンパイル) で実行できません。

[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンには最低でも Microsoft .NET Framework 2.0.50727 が必要です。 この要件は Microsoft .NET Framework 3.5 Service Pack 1 で満たされています。 Microsoft .NET Framework 4 以降のリリースの Microsoft .NET Framework では、この要件が満たされません。

[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンの追加とインストールや、必要なバージョンの Microsoft .NET Framework の追加とインストールについては、「[Windows PowerShell 2.0 エンジンのインストール](../Topic/Installing-the-Windows-PowerShell-2.0-Engine.md)」をご覧ください。 [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンの開始に関する情報については、「[Windows PowerShell 2.0 エンジンの開始](../Topic/Starting-the-Windows-PowerShell-2.0-Engine.md)」をご覧ください。

## Windows プレインストール環境
[!INCLUDE[psversion2](../Token/psversion2_md.md)]、[!INCLUDE[psversion3](../Token/psversion3_md.md)]、[!INCLUDE[psversion4](../Token/psversion4_md.md)] は Windows プレインストール環境 (Windows PE) で実行できます。 ただし、次のコマンドレットはサポートされていません。

-   [バックグラウンド インテリジェント転送サービス (BITS) のコマンドレット](http://go.microsoft.com/fwlink/?LinkId=257514)

-   [Get-EventLog](assetId:///b4985b11-82bf-487d-928d-becd96fc0419)

-   [Get-WinEvent[PSITPro5_Diagnostic]](assetId:///5fe94870-ed6b-4ce2-9500-93846cc65c95)

-   [Save-Help](assetId:///aed94f90-b73f-4e25-a25d-7c18d9f161fa)

-   [Update-Help](assetId:///93e1d870-ace6-432b-8778-8920291d7545)

また、**WinRm** サービスは Windows PE に存在しません。

## 参照
[Windows PowerShell ファースト ステップ ガイド](../Topic/Getting-Started-with-Windows-PowerShell.md)
[Windows PowerShell のインストール](../Topic/Installing-Windows-PowerShell.md)
[Windows PowerShell [ps] を開始する](assetId:///8ec8c2d7-8e7c-4722-a3d2-498fe5739a8e)



<!--HONumber=Apr16_HO1-->


