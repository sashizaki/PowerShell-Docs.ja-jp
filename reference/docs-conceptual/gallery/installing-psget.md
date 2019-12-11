---
ms.date: 09/19/2019
contributor: manikb
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: PowerShellGet のインストール
ms.openlocfilehash: 69dc851c54089b47fb19e5b32990d579d26effb9
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71328203"
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

### <a name="for-computers-running-powershell-30-or-powershell-40"></a>PowerShell 3.0 または PowerShell 4.0 を実行しているコンピューターの場合

この指示は、**PackageManagement Preview** をインストールしているか、いかなるバージョンの **PowerShellGet** もインストールしていないコンピューターに適用されます。

`Save-Module` コマンドレットは、両方の指示セットで使用されます。 `Save-Module` では、モジュールと、登録リポジトリからの依存関係があれば、それがダウンロードされ、保存されます。 モジュールの最新版はローカル コンピューターの指定のパスに保存されますが、インストールはされません。 詳細については、「[Save-Module](/powershell/module/PowershellGet/Save-Module)」を参照してください。

#### <a name="computers-with-the-packagemanagement-preview-installed"></a>PackageManagement Preview がインストールされているコンピューター

1. PowerShell セッションから `Save-Module` を使用し、ローカル ディレクトリにモジュールを保存します。

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. **PowerShellGet** モジュールと **PackageManagement** モジュールが他のプロセスで確実に読み込まれていないようにします。
1. フォルダー: `$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\` と `$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\` のコンテンツを削除します。
1. 管理者特権で PowerShell コンソールを再度開き、次のコマンドを実行します。

   ```powershell
   Copy-Item "C:\LocalFolder\PowerShellGet\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PowerShellGet\" -Recurse -Force
   Copy-Item "C:\LocalFolder\PackageManagement\*" "$env:ProgramFiles\WindowsPowerShell\Modules\PackageManagement\" -Recurse -Force
   ```

#### <a name="computers-without-powershellget"></a>PowerShellGet のないコンピューター

いかなるバージョンの **PowerShellGet** もインストールされていないコンピューターの場合、モジュールをインストールするには、**PowerShellGet** がインストールされているコンピューターが必要になります。

1. **PowerShellGet** がインストールされているコンピューターから、`Save-Module` を使用して **PowerShellGet** の最新版をダウンロードします。 2 つのフォルダーがダウンロードされます。**PowerShellGet** と **PackageManagement** です。 各フォルダーには、バージョン番号付きのサブフォルダーが含まれています。

   ```powershell
   Save-Module -Name PowerShellGet -Path C:\LocalFolder -Repository PSGallery
   ```

1. **PowerShellGet** がインストールされていないコンピューターに **PowerShellGet** フォルダーと **PackageManagement** フォルダーをコピーします。

   宛先ディレクトリは `$env:ProgramFiles\WindowsPowerShell\Modules` です。
