---
ms.date: 06/03/2019
keywords: PowerShell, コマンドレット
title: ソフトウェア インストールの操作
ms.openlocfilehash: 6d2111a332f0e8c1b545186d3d950e936aed1834
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "66830302"
---
# <a name="working-with-software-installations"></a>ソフトウェア インストールの操作

Windows インストーラーを使用するように設計されているアプリケーションは、WMI の **Win32_Product** クラスからアクセスできますが、今日使用されているすべてのアプリケーションが Windows インストーラーを使用しているわけではありません。
代替のセットアップ ルーチンが使われるアプリケーションは、通常 Windows インストーラーによって管理されません。
このようなアプリケーションを処理するための具体的な方法は、インストーラー ソフトウェアおよびアプリケーション開発者による決定によって異なります。 たとえば、コンピューター上のフォルダーにファイルをコピーすることでインストールするアプリケーションは、通常、ここで紹介している手法を使用して管理することはできません。 このようなファイルとフォルダーとしてのアプリケーションは、「[ファイルとフォルダーの操作](Working-with-Files-and-Folders.md)」で説明されている手法を使って管理できます。

> [!CAUTION]
> **Win32_Product** クラスはクエリ用に最適化されていません。 クエリでワイルドカード フィルターが使われると、インストールされているすべての製品を列挙するため WMI によって MSI のプロバイダーが使われ、その後フィルターを処理するために完全な一覧が順次解析されます。 これによってインストールされているパッケージの整合性チェックも開始され、インストールの検証および修復が行われます。 この検証は時間のかかるプロセスで、イベント ログにエラーが発生する可能性があります。 詳細については、[サポート技術情報の記事 974524](https://support.microsoft.com/help/974524) をご覧ください。

## <a name="listing-windows-installer-applications"></a>Windows インストーラー アプリケーションを一覧表示する

ローカルまたはリモート システムに Windows インストーラーを使用してインストールされているアプリケーションの一覧を表示するには、次の単純な WMI クエリを使用します。

```powershell
Get-CimInstance -Class Win32_Product |
  Where-Object Name -eq "Microsoft .NET Core Runtime - 2.1.2 (x64)"
```

```Output
Name               Caption                     Vendor                 Version      IdentifyingNumber
----               -------                     ------                 -------      -----------------
Microsoft .NET ... Microsoft .NET Core Runt... Microsoft Corporation  16.72.26629  {ACC73072-9AD5-416C-94B...
```

**Win32_Product** オブジェクトのすべてのプロパティを画面に表示するには、`Format-List` コマンドレットなど、書式設定のコマンドレットの **Properties** パラメーターに `*` (all) の値を指定して使用します。

```powershell
Get-CimInstance -Class Win32_Product |
  Where-Object Name -eq "Microsoft .NET Core Runtime - 2.1.2 (x64)" |
    Format-List -Property *
```

```Output
Name                  : Microsoft .NET Core Runtime - 2.1.2 (x64)
Version               : 16.72.26629
InstallState          : 5
Caption               : Microsoft .NET Core Runtime - 2.1.2 (x64)
Description           : Microsoft .NET Core Runtime - 2.1.2 (x64)
IdentifyingNumber     : {ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}
SKUNumber             :
Vendor                : Microsoft Corporation
AssignmentType        : 1
HelpLink              :
HelpTelephone         :
InstallDate           : 20180816
InstallDate2          :
InstallLocation       :
InstallSource         : C:\ProgramData\Package Cache\{ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}v16.72.26629\
Language              : 1033
LocalPackage          : C:\WINDOWS\Installer\414c96e.msi
PackageCache          : C:\WINDOWS\Installer\414c96e.msi
PackageCode           : {D20AC783-1EC5-4A58-9277-F452F5EB9AD9}
PackageName           : dotnet-runtime-2.1.2-win-x64.msi
ProductID             :
RegCompany            :
RegOwner              :
Transforms            :
URLInfoAbout          :
URLUpdateInfo         :
WordCount             : 0
PSComputerName        :
CimClass              : root/cimv2:Win32_Product
CimInstanceProperties : {Caption, Description, IdentifyingNumber, Name...}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

または、`Get-CimInstance` **Filter** パラメーターを使用して、Microsoft .NET Framework 2.0 のみを選択できます。 **Filter** パラメーターの値に対しては、Windows PowerShell の構文ではなく、WMI Query Language (WQL) の構文が使われます。 たとえば、次のように入力します。

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='Microsoft .NET Core Runtime - 2.1.2 (x64)'" |
  Format-List -Property *
```

関心のあるプロパティだけを一覧表示させるには、書式設定コマンドレットの **Property** パラメーターを使用して必要なプロパティを一覧表示させます。

```powershell
Get-CimInstance -Class Win32_Product  -Filter "Name='Microsoft .NET Core Runtime - 2.1.2 (x64)'" |
  Format-List -Property Name,InstallDate,InstallLocation,PackageCache,Vendor,Version,IdentifyingNumber
```

```Output
Name              : Microsoft .NET Core Runtime - 2.1.2 (x64)
InstallDate       : 20180816
InstallLocation   :
PackageCache      : C:\WINDOWS\Installer\414c96e.msi
Vendor            : Microsoft Corporation
Version           : 16.72.26629
IdentifyingNumber : {ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}
```

## <a name="listing-all-uninstallable-applications"></a>アンインストール可能なすべてのアプリケーションを一覧表示する

ほとんどの標準的なアプリケーションでは Windows にアンインストーラーが登録されるため、Windows レジストリでこれらを検索することで、ローカルで操作できます。 システム上のすべてのアプリケーションを検索する確実な方法はありません。 ただし、 **[プログラムの追加と削除]** に表示されるリストを備えているプログラムをすべて検索することは可能です。 **[プログラム追加と削除]** では、次のレジストリ キーによってこれらのアプリケーションが検索されます。

`HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion\Uninstall` の順にクリックします。

このキーを調べて、アプリケーションを検索することができます。 Uninstall キーを簡単に表示できるように、このレジストリの場所に PowerShell ドライブをマップできます。

```powershell
New-PSDrive -Name Uninstall -PSProvider Registry -Root HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall
```

```Output
Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
Uninstall  Registry      HKEY_LOCAL_MACHINE\SOFTWARE\Micr...
```
これで "Uninstall:" という名前のドライブができました。これを使うと、アプリケーションのインストールをすばやく便利に検索できます。 Uninstall のレジストリ キーの数をカウントすることによって、インストールされているアプリケーションの数がわかります。PowerShell ドライブ:

```
(Get-ChildItem -Path Uninstall:).Count
459
```

**Get-ChildItem** をはじめとするさまざまな方法を利用して、アプリケーションの一覧を詳細に検索できます。 アプリケーションの一覧を取得して、 **$UninstallableApplications** 変数に保存するには、次のコマンドを使用します。

```powershell
$UninstallableApplications = Get-ChildItem -Path Uninstall:
```

Uninstall の下のレジストリ キーにレジストリ エントリの値を表示するには、レジストリ キーの GetValue メソッドを使用します。 メソッドの値は、レジストリ エントリの名前です。

たとえば、Uninstall キーの下でアプリケーションの表示名を検索するには、次のコマンドを使用します。

```powershell
$UninstallableApplications | ForEach-Object -Process { $_.GetValue('DisplayName') }
```

これらの値が一意である保証はありません。 次の例では、インストールされている 2 つの項目が "Windows Media エンコーダー 9 シリーズ" として表示されます。

```powershell
$UninstallableApplications | Where-Object -FilterScript { $_.GetValue("DisplayName") -eq "Windows Media Encoder 9 Series"}
```

```Output
Name                           Property
----                           --------
{ACC73072-9AD5-416C-94BF-D82DD AuthorizedCDFPrefix :
CEA0F1B}                       Comments            :
                               Contact             :
                               DisplayVersion      : 16.72.26629
                               HelpLink            :
                               HelpTelephone       :
                               InstallDate         : 20180816
                               InstallLocation     :
                               InstallSource       : C:\ProgramData\Package
                               Cache\{ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}v16.72.26629\
                               ModifyPath          : MsiExec.exe /X{ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}
                               NoModify            : 1
                               Publisher           : Microsoft Corporation
                               Readme              :
                               Size                :
                               EstimatedSize       : 67156
                               SystemComponent     : 1
                               UninstallString     : MsiExec.exe /X{ACC73072-9AD5-416C-94BF-D82DDCEA0F1B}
                               URLInfoAbout        :
                               URLUpdateInfo       :
                               VersionMajor        : 16
                               VersionMinor        : 72
                               WindowsInstaller    : 1
                               Version             : 273180677
                               Language            : 1033
                               DisplayName         : Microsoft .NET Core Runtime - 2.1.2 (x64)
```

## <a name="installing-applications"></a>アプリケーションのインストール

**Win32_Product** クラスを使用して、リモートまたはローカルで、Windows インストーラー パッケージをインストールできます。

> [!NOTE]
> アプリケーションをインストールするには、[管理者として実行] オプションを指定して PowerShell を起動する必要があります。

リモートでインストールする場合、WMI のサブシステムによって PowerShell のパスが認識されないため、汎用名前付け規則 (UNC) のネットワーク パスを使って .msi パッケージへのパスを指定します。 たとえば、リモート コンピューター PC01 のネットワーク共有 `\\AppServ\dsp` にある NewPackage.msi パッケージをインストールするには、PowerShell プロンプトに次のコマンドを入力します。

```powershell
Invoke-CimMethod -ClassName Win32_Product -MethodName Install -Arguments @{PackageLocation='\\AppSrv\dsp\NewPackage.msi'}
```

Windows インストーラーのテクノロジが使われないアプリケーションには、展開を自動化するためのアプリケーション固有の方法がある場合があります。 そのアプリケーションのドキュメントをチェックするか、アプリケーション ベンダーのサポート システムをご確認ください。

## <a name="removing-applications"></a>アプリケーションの削除

PowerShell を使用した Windows インストーラー パッケージの削除は、パッケージのインストールとほとんど同じ方法で機能します。 名前に基づいてアンインストールするパッケージを選択する例を以下に示します。場合によっては、**IdentifyingNumber** を使用してフィルター処理した方が簡単になることがあります。

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='ILMerge'" | Invoke-CimMethod -MethodName Uninstall
```

他のアプリケーションの削除は、ローカルで実行する場合でも、それほど単純ではありません。 **UninstallString** プロパティを抽出することで、これらのアプリケーションに対するコマンド ラインのアンインストール文字列を検索できます。
このメソッドは、Windows インストーラー アプリケーションや Uninstall キーの下に表示される古いプログラムに対して機能します。

```powershell
Get-ChildItem -Path Uninstall: | ForEach-Object -Process { $_.GetValue('UninstallString') }
```

必要であれば、出力を表示名でフィルター処理できます。

```powershell
Get-ChildItem -Path Uninstall: |
    Where-Object -FilterScript { $_.GetValue('DisplayName') -like 'Win*'} |
        ForEach-Object -Process { $_.GetValue('UninstallString') }
```

ただし、これらの文字列は、変更なしでは PowerShell プロンプトから直接使用できない場合があります。

## <a name="upgrading-windows-installer-applications"></a>Windows インストーラー アプリケーションのアップグレード

アプリケーションをアップグレードするには、アプリケーションの名前、およびアプリケーションのアップグレード パッケージのパスを認識している必要があります。 その情報があれば、1 つの PowerShell コマンドを使用してアプリケーションをアップグレードできます。

```powershell
Get-CimInstance -Class Win32_Product -Filter "Name='OldAppName'" |
  Invoke-CimMethod -MethodName Upgrade -Arguments @{PackageLocation='\\AppSrv\dsp\OldAppUpgrade.msi'}
```
