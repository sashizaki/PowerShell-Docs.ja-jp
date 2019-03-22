---
ms.date: 06/12/2017
contributor: manikb
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: PowerShellGet のインストール
ms.openlocfilehash: 23a53a9117c9f6a7ad157b635cd7ff4b3b3444c5
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2019
ms.locfileid: "58054830"
---
# <a name="installing-powershellget"></a>PowerShellGet のインストール

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a>PowerShellGet は、以下のリリースではインボックス モジュールである

- [Windows 10](https://www.microsoft.com/windows) 以降
- [Windows Server 2016](/windows-server/windows-server) 以降
- [Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) 以降
- [PowerShell 6](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-powershellget-module-for-powershell-versions-30-and-40"></a>PowerShell バージョン 3.0 および 4.0 用の PowerShellGet モジュールの取得

- [PackageManagement MSI](https://www.microsoft.com/download/details.aspx?id=51451)

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

- `Update-Module` を使用して新しいバージョンを取得します。

  ```powershell
  Update-Module -Name PowerShellGet
  Exit
  ```

### <a name="for-systems-running-powershell-3-or-powershell-4-that-have-installed-the-packagemanagement-msihttpswwwmicrosoftcomdownloaddetailsaspxid51451"></a>[PackageManagement MSI](https://www.microsoft.com/download/details.aspx?id=51451) をインストールした PowerShell 3 または PowerShell 4 を実行しているシステムの場合

- 管理者特権で、PowerShell セッションから PowerShellGet のコマンドレットを使用して、ローカル ディレクトリにモジュールを保存します。

  ```powershell
  Save-Module PowerShellGet -Path C:\LocalFolder
  Exit
  ```

- PowerShellGet および PackageManagement モジュールが他のプロセスで確実に読み込まれていないようにします。
- `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` フォルダーと `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` フォルダーの内容を削除します。
- 管理者特権で PS コンソールを再度開いて、次のコマンドを実行します。

  ```powershell
  Copy-Item "C:\LocalFolder\PowerShellGet\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
  Copy-Item "C:\LocalFolder\PackageManagement\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
  ```
