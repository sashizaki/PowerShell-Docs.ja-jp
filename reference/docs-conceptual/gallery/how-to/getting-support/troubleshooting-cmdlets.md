---
ms.date: 06/12/2017
contributor: manikb
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: コマンドレットのトラブルシューティング
ms.openlocfilehash: d87c680472c2588efbfe8b3c4d6f2dbee6883a0c
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72352112"
---
# <a name="troubleshooting-cmdlets"></a>コマンドレットのトラブルシューティング

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a>"警告: パッケージ 'パッケージ名' をダウンロードできませんでした" の問題を解決する方法

一部のマシン上で `Install-Module` または `Update-Module` が失敗する場合があることがレポートされています。 調査の結果、ネットワーク接続の問題であることが判明しました。 最近、パッケージのダウンロードが安定するように、NuGet プロバイダーを更新しました。 下の指示に従い、最新版の NuGet プロバイダーをインストールし、モジュールをインストールするか、更新できます。 以下、'Azure' モジュールをサンプルとして使用します。

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

### <a name="required-network-endpoints"></a>必要なネットワーク エンドポイント

Install および Update コマンドレットを使用する場合、PowerShell ギャラリーによって使用されるネットワーク エンドポイントに接続するためのインターネット アクセスが必要です。 お使いのネットワーク アクセス ポリシーで、次のエンドポイントへの接続が許可されていることを確認してください。

- oneget.org
- go.microsoft.com
- az818661.vo.msecnd.net
- www.powershellgallery.com
- devopsgallerystorage.blob.core.windows.net
