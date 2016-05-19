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
このトピックでは、Windows PowerShell 3.0 と Windows PowerShell 4.0 のシステム要件、および Windows PowerShell Integrated Scripting Environment (ISE)、CIM コマンド、ワークフローなどの特殊な機能の一覧を示します。

WindowsÂ® 8.1 と Windows ServerÂ® 2012 R2 には、必要なプログラムがすべて付属しています。 このトピックは、以前のリリースの Windows のユーザー向けです。

## オペレーティング システムの要件
Windows PowerShell 4.0 は、次のバージョンの Windows で実行できます。

-   Windows 8.1 (既定でインストール済み)

-   Windows Server 2012 R2 (既定でインストール済み)

-   WindowsÂ® 7 (Service Pack 1 適用済み) では、[Windows Management Framework 4.0](http://go.microsoft.com/fwlink/?LinkId=293881) をインストールして Windows PowerShell 4.0 を実行します

-   Windows ServerÂ® 2008 R2 (Service Pack 1 適用済み) では、[Windows Management Framework 4.0](http://go.microsoft.com/fwlink/?LinkId=293881) をインストールして Windows PowerShell 4.0 を実行します

Windows PowerShell 3.0 は、次のバージョンの Windows で実行できます。

-   Windows 8 (既定でインストール済み)

-   Windows Server 2012 (既定でインストール済み)

-   WindowsÂ® 7 (Service Pack 1 適用済み) では、[Windows Management Framework 3.0](http://www.microsoft.com/download/details.aspx?id=34595) をインストールして Windows PowerShell 3.0 を実行します

-   Windows ServerÂ® 2008 R2 (Service Pack 1 適用済み) では、[Windows Management Framework 3.0](http://www.microsoft.com/download/details.aspx?id=34595) をインストールして Windows PowerShell 3.0 を実行します

-   Windows Server 2008 (Service Pack 2 適用済み) では、[Windows Management Framework 3.0](http://www.microsoft.com/download/details.aspx?id=34595) をインストールして Windows PowerShell 3.0 を実行します

## Microsoft .NET Framework の要件
Windows PowerShell 4.0 には Microsoft .NET Framework 4.5 のフル インストールが必要です。 Windows 8.1 と Windows Server 2012 R2 には、既定で Microsoft .NET Framework 4.5 が付属しています。

Windows PowerShell 3.0 には Microsoft .NET Framework 4 のフル インストールが必要です。 Windows 8 と Windows Server 2012 には、既定で Microsoft .NET Framework 4.5 が含まれるため、この要件は満たされています。

Microsoft .NET Framework 4.5 (dotNetFx45_Full_setup.exe) をインストールするには、Microsoft ダウンロード センターの「[Microsoft .NET Framework 4.5](http://go.microsoft.com/fwlink/?LinkID=242919)」をご覧ください。

Microsoft .NET Framework 4 (dotNetFx40_Full_setup.exe) をフル インストールするには、Microsoft ダウンロード センターの「[Microsoft .NET Framework 4 (Web インストーラー)](http://go.microsoft.com/fwlink/?LinkID=212931)」をご覧ください。

## WS-Management 3.0
Windows PowerShell 3.0 と Windows PowerShell 4.0 は、WinRM サービスおよび WSMan プロトコルをサポートする WS-Management 3.0 を必要とします。 このプログラムは、Windows 8.1、Windows Server 2012 R2、Windows 8、Windows Server 2012、Windows Management Framework 4.0、Windows Management Framework 3.0 にも組み込まれています。

## Windows Management Instrumentation 3.0
Windows PowerShell 3.0 と Windows PowerShell 4.0 には、Windows Management Instrumentation 3.0 (WMI) が必要です。 このプログラムは、Windows 8.1、Windows Server 2012 R2、Windows 8、Windows Server 2012、Windows Management Framework 4.0、Windows Management Framework 3.0 にも組み込まれています。 このプログラムがコンピューターにインストールされていない場合、CIM コマンドなどの、WMI を必要とする機能は実行されません。

## 共通言語ランタイム 4.0
Windows PowerShell 3.0 と Windows PowerShell 4.0 は、共通言語ランタイム (CLR) 4.0 に対してコンパイルされます。

## グラフィカル ユーザー インターフェイスの要件
Windows PowerShell はグラフィカル ユーザー インターフェイスを必要としないコンソール ベースのアプリケーションです。 そのため、画面 (モニター) もユーザー インターフェイスも持たない、Windows Server 2012 R2 または Windows Server 2012 の Server Core インストール オプションなどのコンピューターに適しています。

ただし、次のように一部グラフィカル ユーザー インターフェイスを必要とする項目もあります。 詳細については、各項目のヘルプ トピックをご覧ください。

-   Windows PowerShell Integrated Scripting Environment (ISE)

-   コマンドレット

    1.  [Out-GridView](https://technet.microsoft.com/en-us/library/70915a86-d753-464e-8349-cba02316154c)

    2.  [Show-Command](https://technet.microsoft.com/en-us/library/65bba50b-91a8-49d5-80a2-a30fc684ba41)

    3.  [Show-ControlPanelItem](https://technet.microsoft.com/en-us/library/0685d42c-37cc-498f-acf6-0ecfeb0cb162)

    4.  [Show-EventLog](https://technet.microsoft.com/en-us/library/a3b0f5ad-0438-42c7-915b-d1b4793a431c)

-   パラメーター

    1.  [Get-Help](https://technet.microsoft.com/en-us/library/1f46eeb4-49d7-4bec-bb29-395d9b42f54a) コマンドレットの **ShowWindow** パラメーター。

    2.  [Register-PSSessionConfiguration](https://technet.microsoft.com/en-us/library/e9152ae2-bd6d-4056-9bc7-dc1893aa29ea) と [Set-PSSessionConfiguration](https://technet.microsoft.com/en-us/library/b21fbad3-1759-4260-b206-dcb8431cd6ea) コマンドレットの **ShowSecurityDescriptorUi** パラメーター。

## Windows PowerShell Engine の要件
Windows PowerShell 4.0 は、Windows PowerShell 3.0 および Windows PowerShell 2.0 との下位互換性を保つように設計されています。 Windows PowerShell 2.0 と Windows PowerShell 3.0 用に記述されたコマンドレット、プロバイダー、スナップイン、モジュール、スクリプトは、未変更のまま Windows PowerShell 4.0 で実行できます。

ただし、Microsoft .NET Framework 4 でランタイムのアクティブ化ポリシーが変更されたため、Windows PowerShell 2.0 用に記述され、共通言語ランタイム (CLR) 2.0 でコンパイルされた Windows PowerShell ホスト プログラムは、変更を加えなければ Windows PowerShell 3.0 (CLR 4.0 でコンパイルされたもの) で実行できません。

Windows PowerShell 2.0 エンジンには最低でも Microsoft .NET Framework 2.0.50727 が必要です。 この要件は Microsoft .NET Framework 3.5 Service Pack 1 で満たされています。 Microsoft .NET Framework 4 以降のリリースの Microsoft .NET Framework では、この要件が満たされません。

Windows PowerShell 2.0 エンジンの追加とインストールや、必要なバージョンの Microsoft .NET Framework の追加とインストールについては、「[Windows PowerShell 2.0 エンジンのインストール](Installing-the-Windows-PowerShell-2.0-Engine.md)」をご覧ください。 Windows PowerShell 2.0 エンジンの開始に関する情報については、「[Windows PowerShell 2.0 エンジンの開始](Starting-the-Windows-PowerShell-2.0-Engine.md)」を参照してください。.

## Windows プレインストール環境
Windows PowerShell 2.0、Windows PowerShell 3.0、および Windows PowerShell 4.0 は、Windows プレインストール環境 (Windows PE) で実行できます。 ただし、次のコマンドレットはサポートされていません。

-   [バックグラウンド インテリジェント転送サービス (BITS) のコマンドレット](http://go.microsoft.com/fwlink/?LinkId=257514)

-   [Get-EventLog](https://technet.microsoft.com/en-us/library/b4985b11-82bf-487d-928d-becd96fc0419)

-   [Get-WinEvent[PSITPro5_Diagnostic]](https://technet.microsoft.com/en-us/library/5fe94870-ed6b-4ce2-9500-93846cc65c95)

-   [Save-Help](https://technet.microsoft.com/en-us/library/aed94f90-b73f-4e25-a25d-7c18d9f161fa)

-   [Update-Help](https://technet.microsoft.com/en-us/library/93e1d870-ace6-432b-8778-8920291d7545)

また、**WinRm** サービスは Windows PE に存在しません。

## 参照
[Windows PowerShell ファースト ステップ ガイド](../getting-started/Getting-Started-with-Windows-PowerShell.md)
[Windows PowerShell のインストール](Installing-Windows-PowerShell.md)
[Windows PowerShell [ps] の開始](https://technet.microsoft.com/en-us/library/8ec8c2d7-8e7c-4722-a3d2-498fe5739a8e)



<!--HONumber=May16_HO2-->


