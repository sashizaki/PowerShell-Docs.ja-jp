---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: Windows PowerShell のシステム要件
ms.assetid: 6d1d3c75-3be4-4fc9-8805-ca9b2c454d42
ms.openlocfilehash: 5e1fdb9cb4f10fd71c2d2daf693cb359fddcc5bc
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50002720"
---
# <a name="windows-powershell-system-requirements"></a>Windows PowerShell のシステム要件
このトピックでは、Windows PowerShell 3.0、Windows PowerShell 4.0、Windows PowerShell 5.0、および Windows PowerShell 5.1 のシステム要件の一覧や、Windows PowerShell Integrated Scripting Environment (ISE)、CIM コマンド、ワークフローなどの特殊な機能の一覧を示します。

Windows® 8.1 および Windows Server® 2012 R2 には、必要なプログラムがすべて付属しています。 このトピックは、以前のリリースの Windows のユーザー向けです。

## <a name="operating-system-requirements"></a>オペレーティング システムの要件
Windows PowerShell 5.1 は、次のバージョンの Windows で実行されます。

- Windows Server 2019 (既定でインストール済み)

- Windows Server 2016 (既定でインストール済み)

- Windows Server 2012 R2 では、[Windows Management Framework 5.1](https://aka.ms/wmf5download) をインストールして Windows PowerShell 5.1 を実行します

- Windows Server 2012 では、[Windows Management Framework 5.1](https://aka.ms/wmf5download) をインストールして Windows PowerShell 5.0 を実行します

- Windows Server 2008 R2 (Service Pack 1 適用済み) では、[Windows Management Framework 5.1](https://aka.ms/wmf5download) をインストールして Windows PowerShell 5.1 を実行します

- Windows 10 バージョン 1607 以降 - 既定でインストール済み

- Windows 10 バージョン 1507、1511 - [Windows Management Framework 5.1](https://aka.ms/wmf5download) をインストールして Windows PowerShell 5.1 を実行します

- Windows 8.1 では、[Windows Management Framework 5.1](https://aka.ms/wmf5download) をインストールして Windows PowerShell 5.1 を実行します

- Windows 7 (Service Pack 1 適用済み) では、[Windows Management Framework 5.1](https://aka.ms/wmf5download) をインストールして Windows PowerShell 5.1 を実行します

Windows PowerShell 5.0 (Windows PowerShell 5.1 が優先) は、次のバージョンの Windows で実行されます。

- Windows Server 2019 (上位バージョンが既定でインストール済み)

- Windows Server 2016 (上位バージョンが既定でインストール済み)

- Windows Server 2012 R2 では、[Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) をインストールして Windows PowerShell 5.0 を実行します

- Windows Server 2012 では、[Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) をインストールして Windows PowerShell 5.0 を実行します

- Windows Server 2008 R2 (Service Pack 1 適用済み) では、[Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) をインストールして Windows PowerShell 5.0 を実行します

- Windows 10 バージョン 1607 以降 - (上位バージョンが既定でインストール済み)

- Windows 10 バージョン 1507、1511 - 既定でインストール済み

- Windows 8.1 では、[Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) をインストールして Windows PowerShell 5.0 を実行します

- Windows 7 (Service Pack 1 適用済み) では、[Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) をインストールして Windows PowerShell 5.0 を実行します

Windows PowerShell 4.0 は、次のバージョンの Windows で実行できます。

- Windows 8.1 (既定でインストール済み)

- Windows Server 2012 R2 (既定でインストール済み)

- Windows® 7 (Service Pack 1 適用済み) では、[Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) をインストールして Windows PowerShell 4.0 を実行します

- Windows Server® 2008 R2 (Service Pack 1 適用済み) では、[Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) をインストールして Windows PowerShell 4.0 を実行します

Windows PowerShell 3.0 は、次のバージョンの Windows で実行できます。

- Windows 8 (既定でインストール済み)

- Windows Server 2012 (既定でインストール済み)

- Windows® 7 (Service Pack 1 適用済み) では、[Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) をインストールして Windows PowerShell 3.0 を実行します

- Windows Server® 2008 R2 (Service Pack 1 適用済み) では、[Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) をインストールして Windows PowerShell 3.0 を実行します

- Windows Server 2008 (Service Pack 2 適用済み) では、[Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) をインストールして Windows PowerShell 3.0 を実行します

## <a name="microsoft-net-framework-requirements"></a>Microsoft .NET Framework の要件
Windows PowerShell 5.1 には Microsoft .NET Framework 4.5 のフル インストールが必要です。 Windows 8.1 と Windows Server 2012 R2 には、既定で Microsoft .NET Framework 4.5 が付属しています。

Windows PowerShell 5.0 には Microsoft .NET Framework 4.5 のフル インストールが必要です。 Windows 8.1 と Windows Server 2012 R2 には、既定で Microsoft .NET Framework 4.5 が付属しています。

Windows PowerShell 4.0 には Microsoft .NET Framework 4.5 のフル インストールが必要です。 Windows 8.1 と Windows Server 2012 R2 には、既定で Microsoft .NET Framework 4.5 が付属しています。

Windows PowerShell 3.0 には Microsoft .NET Framework 4 のフル インストールが必要です。 Windows 8 と Windows Server 2012 には、既定で Microsoft .NET Framework 4.5 が含まれるため、この要件は満たされています。

Microsoft .NET Framework 4.5 (dotNetFx45_Full_setup.exe) をインストールするには、Microsoft ダウンロード センターの「[Microsoft .NET Framework 4.5](http://go.microsoft.com/fwlink/?LinkID=242919)」をご覧ください。

Microsoft .NET Framework 4 (dotNetFx40_Full_setup.exe) をフル インストールするには、Microsoft ダウンロード センターの「[Microsoft .NET Framework 4 (Web インストーラー)](http://go.microsoft.com/fwlink/?LinkID=212931)」をご覧ください。

## <a name="windows-management-framework-40"></a>Windows Management Framework 4.0
Windows PowerShell 5.0 には、Windows Server 2008 R2 SP1 と Windows 7 SP1 に Windows Management Framework 4.0 をプレインストールする必要があります。

## <a name="ws-management-30"></a>WS-Management 3.0
Windows PowerShell 3.0 と Windows PowerShell 4.0 は、WinRM サービスおよび WSMan プロトコルをサポートする WS-Management 3.0 を必要とします。 このプログラムは、Windows 8.1、Windows Server 2012 R2、Windows 8、Windows Server 2012、Windows Management Framework 4.0、Windows Management Framework 3.0 にも組み込まれています。

## <a name="windows-management-instrumentation-30"></a>Windows Management Instrumentation 3.0
Windows PowerShell 3.0 と Windows PowerShell 4.0 には、Windows Management Instrumentation 3.0 (WMI) が必要です。 このプログラムは、Windows 8.1、Windows Server 2012 R2、Windows 8、Windows Server 2012、Windows Management Framework 4.0、Windows Management Framework 3.0 にも組み込まれています。 このプログラムがコンピューターにインストールされていない場合、CIM コマンドなどの、WMI を必要とする機能は実行されません。

## <a name="common-language-runtime-40"></a>共通言語ランタイム 4.0
Windows PowerShell 3.0、Windows PowerShell 4.0、および Windows PowerShell 5.0 は、共通言語ランタイム (CLR) 4.0 に対してコンパイルされます。

## <a name="graphical-user-interface-requirements"></a>グラフィカル ユーザー インターフェイスの要件
Windows PowerShell はグラフィカル ユーザー インターフェイスを必要としないコンソール ベースのアプリケーションです。 そのため、画面 (モニター) もユーザー インターフェイスも持たない、Windows Server 2012 R2 または Windows Server 2012 の Server Core インストール オプションなどのコンピューターに適しています。

ただし、次のように一部グラフィカル ユーザー インターフェイスを必要とする項目もあります。 詳細については、各項目のヘルプ トピックをご覧ください。

- Windows PowerShell Integrated Scripting Environment (ISE)

- コマンドレット

    1.  [Out-GridView](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-gridview)

    2.  [Show-Command](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Show-Command)

    3.  [Show-ControlPanelItem](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Management/Show-ControlPanelItem)

    4.  [Show-EventLog](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Management/Show-EventLog)

- パラメーター

    1.  [Get-Help](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Get-Help) コマンドレットの **ShowWindow** パラメーター。

    2.  [Register-PSSessionConfiguration](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Register-PSSessionConfiguration) と [Set-PSSessionConfiguration](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Set-PSSessionConfiguration) コマンドレットの **ShowSecurityDescriptorUI** パラメーター。

## <a name="windows-powershell-engine-requirements"></a>Windows PowerShell Engine の要件
Windows PowerShell 4.0 は、Windows PowerShell 3.0 および Windows PowerShell 2.0 との下位互換性を保つように設計されています。 Windows PowerShell 2.0 と Windows PowerShell 3.0 用に記述されたコマンドレット、プロバイダー、スナップイン、モジュール、スクリプトは、未変更のまま Windows PowerShell 4.0 で実行できます。

ただし、Microsoft .NET Framework 4 でランタイムのアクティブ化ポリシーが変更されたため、Windows PowerShell 2.0 用に記述され、共通言語ランタイム (CLR) 2.0 でコンパイルされた Windows PowerShell ホスト プログラムは、変更を加えなければ Windows PowerShell 3.0 (CLR 4.0 でコンパイルされたもの) で実行できません。

Windows PowerShell 2.0 エンジンには最低でも Microsoft .NET Framework 2.0.50727 が必要です。 この要件は Microsoft .NET Framework 3.5 Service Pack 1 で満たされています。 Microsoft .NET Framework 4 以降のリリースの Microsoft .NET Framework では、この要件が満たされません。

Windows PowerShell 2.0 エンジンの追加とインストールや、必要なバージョンの Microsoft .NET Framework の追加とインストールについては、「[Windows PowerShell 2.0 エンジンのインストール](Installing-the-Windows-PowerShell-2.0-Engine.md)」をご覧ください。 Windows PowerShell 2.0 エンジンの開始に関する情報については、「[Windows PowerShell 2.0 エンジンの開始](Starting-the-Windows-PowerShell-2.0-Engine.md)」を参照してください。

## <a name="windows-preinstallation-environment"></a>Windows プレインストール環境
Windows PowerShell 2.0、Windows PowerShell 3.0、および Windows PowerShell 4.0 は、Windows プレインストール環境 (Windows PE) で実行できます。 ただし、次のコマンドレットはサポートされていません。

- [バックグラウンド インテリジェント転送サービス (BITS) のコマンドレット](http://go.microsoft.com/fwlink/?LinkId=257514)

- [Get-EventLog](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Management/Get-EventLog)

- [Get-WinEvent](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent)

- [Save-Help](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Save-Help)

- [Update-Help](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Update-Help)

また、**WinRM** サービスは Windows PE に存在しません。

## <a name="see-also"></a>参照
- [Windows PowerShell ファースト ステップ ガイド](../getting-started/Getting-Started-with-Windows-PowerShell.md)
- [Windows PowerShell のインストール](Installing-Windows-PowerShell.md)
- [Windows PowerShell の開始](Starting-Windows-PowerShell.md)
