---
ms.date: 06/12/2017
contributor: manikb
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: PowerShellGet のインストール
ms.openlocfilehash: 35be7d02ea856ea39218f05d32b43c60fa1bd53e
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34219353"
---
# <a name="installing-powershellget"></a>PowerShellGet のインストール

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a>PowerShellGet は、以下のリリースではインボックス モジュールである

- [Windows 10](https://www.microsoft.com/windows/get-windows-10) 以降
- [Windows Server 2016](https://technet.microsoft.com/windows-server-docs/get-started/windows-server-2016) 以降
- [Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) 以降
- [PowerShell 6](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-powershellget-module-for-powershell-versions-30-and-40"></a>PowerShell バージョン 3.0 および 4.0 用の PowerShellGet モジュールの取得

- [PackageManagement MSI](http://go.microsoft.com/fwlink/?LinkID=746217&clcid=0x409)

## <a name="get-the-latest-version-from-powershell-gallery"></a>PowerShell ギャラリーからの最新バージョンの取得

- PowerShellGet を更新する前には、最新の Nuget プロバイダーをインストールする必要があります。 そのためには、PowerShell セッションで、管理者特権で次のコマンドを実行します。

```powershell
Install-PackageProvider Nuget –Force
Exit
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a>PowerShell 5.0 (またはそれ以降) のシステムには、最新の PowerShellGet をインストール可能

- Windows 10、Windows Server 2016、WMF 5.0 または 5.1 がインストールされたシステム、PowerShell 6 を使用するシステムでこれを実行するには、管理者特権で PowerShell セッションから、次のコマンドを実行します。

```powershell
Install-Module –Name PowerShellGet –Force
Exit
```

- 新しいバージョンを取得するには、Update-Module を使用します。

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-systems-running-powershell-3-or-powershell-4-that-have-installed-the-packagemanagement-msihttpgomicrosoftcomfwlinklinkid746217clcid0x409"></a>[PackageManagement MSI](http://go.microsoft.com/fwlink/?LinkID=746217&clcid=0x409) をインストールした PowerShell 3 または PowerShell 4 を実行しているシステムの場合

- 管理者特権で、PowerShell セッションから PowerShellGet のコマンドレットを使用して、ローカル ディレクトリにモジュールを保存します。

```powershell
Save-Module PowerShellGet -Path C:\LocalFolder
Exit
```

- PowerShellGet および PackageManagment モジュールが他のプロセスで読み込まれていないことを確認します。
- `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` フォルダーと `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` フォルダーの内容を削除します。
- 管理者特権で PS コンソールを再度開いて、次のコマンドを実行します。

```powershell
Copy-Item "C:\LocalFolder\PowerShellGet\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
Copy-Item "C:\LocalFolder\PackageManagement\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
```