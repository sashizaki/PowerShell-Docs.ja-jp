---
description: Windows Management Instrumentation (WMI) と Windows PowerShell の背景情報を提供します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi_cmdlets?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI_Cmdlets
ms.openlocfilehash: c2099c005cedf64e9621d66d6757419320c9b43e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223192"
---
# <a name="about-wmi-cmdlets"></a>WMI コマンドレットの概要

## <a name="short-description"></a>概要

Windows Management Instrumentation (WMI) と Windows PowerShell の背景情報を提供します。

## <a name="long-description"></a>詳細説明

このトピックでは、WMI テクノロジ、Windows PowerShell 用の WMI コマンドレット、WMI ベースのリモート処理、WMI アクセラレータ、および WMI のトラブルシューティングについて説明します。 このトピックでは、WMI に関する詳細情報へのリンクも示します。

### <a name="about-wmi"></a>WMI について

Windows Management Instrumentation (WMI) は、Web-Based Enterprise Management (WBEM) を Microsoft が実装したものです。WBEM とは、企業環境で管理情報にアクセスするための標準技術を確立する業界の取り組みの 1 つです。 WMI では、Common Information Model (CIM) 業界規格を使用して、システム、アプリケーション、ネットワーク、デバイスなどのマネージド コンポーネントを表現します。 CIM は、分散管理タスク フォース (DMTF) によって開発され、管理されています。 WMI を使用して、ローカルコンピューターとリモートコンピューターの両方を管理できます。 たとえば、WMI を使用して次の操作を行うことができます。

- リモートコンピューター上のプロセスを開始します。
- リモートでコンピューターを再起動します。
- ローカルコンピューターまたはリモートコンピューターにインストールされているアプリケーションの一覧を取得します。
- ローカルコンピューターまたはリモートコンピューター上の Windows イベントログに対してクエリを実行します。

### <a name="the-wmi-cmdlets-for-windows-powershell"></a>WINDOWS POWERSHELL 用の WMI コマンドレット

Windows PowerShell は、既定で Windows PowerShell で使用できる一連のコマンドレットを使用して WMI 機能を実装します。 これらのコマンドレットを使用して、ローカルコンピューターとリモートコンピューターを管理するために必要なエンドツーエンドのタスクを実行できます。

次の WMI コマンドレットが含まれています。

|コマンドレット           |説明                                   |
|-----------------|----------------------------------------------|
|Get-WmiObject    |WMI クラスまたは情報のインスタンスを取得します。  |
|                 |使用可能なクラスについて。                  |
|Invoke-WmiMethod |WMI メソッドを呼び出します。                            |
|Register-WmiEvent|WMI イベントをサブスクライブします。                    |
|Remove-WmiObject |WMI クラスおよびインスタンスを削除します。            |
|Set-WmiInstance  |WMI クラスのインスタンスを作成または変更します。 |

### <a name="sample-commands"></a>サンプルコマンド
次のコマンドは、ローカルコンピューターの BIOS 情報を表示します。

```powershell
C:\PS> get-wmiobject win32_bios | format-list *
```

次のコマンドは、3台のリモートコンピューターの WinRM サービスに関する情報を表示します。

```powershell
$wql = "select * from win32_service where name='WinRM'"
get-wmiobject -query $wql -computername server01, server01, server03
```

次のより複雑なコマンドは、プログラムのすべてのインスタンスを終了します。

```powershell
C:\PS> notepad.exe
C:\PS> $wql = "select * from win32_process where name='notepad.exe'"
C:\PS> $np = get-wmiobject -query $wql
C:\PS> $np | remove-wmiobject
```

### <a name="wmi-based-remoting"></a>WMI ベースのリモート処理

WMI を使用してローカルシステムを管理する機能は便利ですが、WMI を強力な管理ツールにするリモート処理機能です。 WMI は、Microsoft の分散コンポーネントオブジェクトモデル (DCOM) を使用して、システムへの接続と管理を行います。 場合によっては、DCOM 接続を許可するようにシステムを構成する必要があります。
ファイアウォールの設定とロックダウンされた DCOM のアクセス許可によって、システムをリモートで管理する WMI の機能がブロックされる場合があります。

### <a name="wmi-type-accelerators"></a>WMI の種類のアクセラレータ

Windows PowerShell には、WMI の種類のアクセラレータが含まれています。 これらの WMI 型アクセラレータ (ショートカット) を使用すると、非型のアクセラレータを使用する場合よりも、WMI オブジェクトに対するより直接的なアクセスが可能になります。

WMI では、次の種類のアクセラレータがサポートされています。

[WMISEARCHER]-WMI オブジェクトを検索するためのショートカットです。

[WMICLASS]-クラスの静的プロパティおよびメソッドにアクセスするためのショートカットです。

[WMI]-クラスの単一のインスタンスを取得するためのショートカット。

[WMISEARCHER] は、ManagementObjectSearcher の型アクセラレータです。 文字列コンストラクターを使用してサーチャーを作成することができます。これは、で GET () を実行することができます。

次に例を示します。

```powershell
PS> $s = [WmiSearcher]'Select * from Win32_Process where Handlecount > 1000'
PS> $s.Get() |sort handlecount |ft handlecount,__path,name -auto

count  __PATH                                              name
-----  ------                                              ----
1105   \\SERVER01\root\cimv2:Win32_Process.Handle="3724"   PowerShell...
1132   \\SERVER01\root\cimv2:Win32_Process.Handle="1388"   winlogon.exe
1495   \\SERVER01\root\cimv2:Win32_Process.Handle="2852"   iexplore.exe
1699   \\SERVER01\root\cimv2:Win32_Process.Handle="1204"   OUTLOOK.EXE
1719   \\SERVER01\root\cimv2:Win32_Process.Handle="1912"   iexplore.exe
2579   \\SERVER01\root\cimv2:Win32_Process.Handle="1768"   svchost.exe
```

[WMICLASS] は ManagementClass の型アクセラレータです。 これには、WMI クラスへのローカルまたは絶対 WMI パスを受け取り、そのクラスにバインドされたオブジェクトを返す文字列コンストラクターがあります。

次に例を示します。

```powershell
PS> $c = [WMICLASS]"root\cimv2:WIn32_Process"
PS> $c |fl *
Name             : Win32_Process
__GENUS          : 1
__CLASS          : Win32_Process
__SUPERCLASS     : CIM_Process
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Process
__PROPERTY_COUNT : 45
__DERIVATION     : {CIM_Process, CIM_LogicalElement,
                   CIM_ManagedSystemElement}
__SERVER         : SERVER01
__NAMESPACE      : ROOT\cimv2
__PATH           : \\SERVER01\ROOT\cimv2:Win32_Process
```

[WMI] は System.management.managementobject の型アクセラレータです。 これには、WMI インスタンスに対してローカルまたは絶対の WMI パスを取得し、そのインスタンスにバインドされたオブジェクトを返す文字列コンストラクターがあります。

次に例を示します。

```powershell
PS> $p = [WMI]'\\SERVER01\root\cimv2:Win32_Process.Handle="1204"'
PS> $p.Name
OUTLOOK.EXE
```

### <a name="wmi-troubleshooting"></a>WMI のトラブルシューティング

次の問題は、リモートコンピューターに接続しようとすると発生する可能性がある最も一般的な問題です。

問題 1: リモートコンピューターがオンラインではありません。

コンピューターがオフラインの場合は、WMI を使用してコンピューターに接続することはできません。
次のエラー メッセージを受け取ることがあります。

```
Remote server machine does not exist or is unavailable
```

このエラーメッセージが表示された場合は、コンピューターがオンラインになっていることを確認します。 リモートコンピューターに対して ping を実行します。

問題 2: リモートコンピューターに対するローカル管理者権限がありません。

WMI をリモートで使用するには、リモートコンピューターのローカル管理者権限を持っている必要があります。 そうしないと、そのコンピューターへのアクセスが拒否されます。

名前空間のセキュリティを確認するには:

1. [スタート] ボタンをクリックし、[マイコンピューター] を右クリックして、[管理] をクリックします。
2. [コンピューターの管理] で、[サービスとアプリケーション] を展開し、[WMI コントロール] を右クリックして、[プロパティ] をクリックします。
3. [WMI コントロールのプロパティ] ダイアログボックスで、[セキュリティ] タブをクリックします。

問題 3: ファイアウォールがリモートコンピューターへのアクセスをブロックしている。

WMI は、DCOM (Distributed COM) および RPC (リモートプロシージャコール) プロトコルを使用してネットワークをスキャンします。 既定では、多くのファイアウォールは、DCOM および RPC トラフィックをブロックします。 ファイアウォールでこれらのプロトコルがブロックされている場合、接続は失敗します。 たとえば、Microsoft Windows XP Service Pack 2 の Windows ファイアウォールは、すべての要請されていないネットワークトラフィック (DCOM および WMI を含む) を自動的にブロックするように構成されています。 既定の構成では、Windows ファイアウォールは着信 WMI 要求を拒否し、次のエラーメッセージが表示されます。

```
Remote server machine does not exist or is unavailable
```

## <a name="see-also"></a>関連項目

[WMI について](/windows/win32/wmisdk/about-wmi)

[WMI のトラブルシューティング](/windows/win32/wmisdk/wmi-troubleshooting)

[Get-WmiObject](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[Invoke-WmiMethod](xref:Microsoft.PowerShell.Management.Invoke-WmiMethod)

[Register-WmiEvent](xref:Microsoft.PowerShell.Management.Register-WmiEvent)

[Remove-WmiObject](xref:Microsoft.PowerShell.Management.Remove-WmiObject)

[Set-WmiInstance](xref:Microsoft.PowerShell.Management.Set-WmiInstance)
