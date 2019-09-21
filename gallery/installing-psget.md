---
ms.date: 06/12/2017
contributor: manikb
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: PowerShellGet のインストール
ms.openlocfilehash: a0ef46a9ee4bbf668a58067256d098967bde48c5
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71143591"
---
# <a name="installing-powershellget"></a>PowerShellGet のインストール

## <a name="powershellget-is-an-in-box-module-in-the-following-releases"></a>PowerShellGet は、以下のリリースではインボックス モジュールである

- [Windows 10](https://www.microsoft.com/windows) 以降
- [Windows Server 2016](/windows-server/windows-server) 以降
- [Windows Management Framework (WMF) 5.0](https://www.microsoft.com/download/details.aspx?id=50395) 以降
- [PowerShell 6](https://github.com/PowerShell/PowerShell/releases)

## <a name="get-the-latest-version-from-powershell-gallery"></a>PowerShell ギャラリーからの最新バージョンの取得

**PowerShellGet** を更新する前には、最新の **NuGet** プロバイダーをインストールする必要があります。 管理者特権の PowerShell セッションから次のコマンドを実行します。

```powershell
Install-PackageProvider -Name NuGet -Force
Exit
```

### <a name="for-systems-with-powershell-50-or-newer-you-can-install-the-latest-powershellget"></a>PowerShell 5.0 (またはそれ以降) のシステムには、最新の PowerShellGet をインストール可能

Windows 10、Windows Server 2016、WMF 5.0 または 5.1 がインストールされたシステム、PowerShell 6 を使用するシステムに PowerShellGet をインストールするには、管理者特権の PowerShell セッションから次のコマンドを実行します。

```powershell
Install-Module -Name PowerShellGet -Force
Exit
```

`Update-Module` を使用して新しいバージョンを取得します。

```powershell
Update-Module -Name PowerShellGet
Exit
```

### <a name="for-systems-running-powershell-3-or-powershell-4-that-have-installed-the-packagemanagement-preview"></a>PackageManagement プレビューをインストールした PowerShell 3 または PowerShell 4 を実行しているシステムの場合

1. 管理者特権の PowerShell セッションから `Save-Module` を使用し、ローカル ディレクトリにモジュールを保存します。

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder
   Exit
   ```

1. **PowerShellGet** モジュールと **PackageManagement** モジュールが他のプロセスで確実に読み込まれていないようにします。
1. フォルダー: `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` と `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` のコンテンツを削除します。
1. 管理者特権で PowerShell コンソールを再度開き、次のコマンドを実行します。

   ```powershell
   Copy-Item "C:\LocalFolder\PowerShellGet\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
   Copy-Item "C:\LocalFolder\PackageManagement\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
   ```
