---
ms.date: 12/01/2020
title: コマンドレットのトラブルシューティング
description: この記事では、PowerShell ギャラリーを使用してエラーのトラブルシューティングを行うための情報と手順を示します
ms.openlocfilehash: 980da8ea7b8a09513f33a9939d512c437b755d8d
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913320"
---
# <a name="troubleshooting-cmdlets"></a>コマンドレットのトラブルシューティング

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a>"警告: パッケージ 'パッケージ名' をダウンロードできませんでした" の問題を解決する方法

一部のマシン上で `Install-Module` または `Update-Module` が失敗する場合があることがレポートされています。 調査の結果、ネットワーク接続の問題であることが判明しました。 最近、パッケージのダウンロードが安定するように、NuGet プロバイダーを更新しました。 下の指示に従い、最新版の NuGet プロバイダーをインストールし、モジュールをインストールするか、更新できます。 以下、'Azure' モジュールをサンプルとして使用します。

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

## <a name="required-network-endpoints"></a>必要なネットワーク エンドポイント

Install および Update コマンドレットを使用する場合、PowerShell ギャラリーによって使用されるネットワーク エンドポイントに接続するためのインターネット アクセスが必要です。 お使いのネットワーク アクセス ポリシーで、次のエンドポイントへの接続が許可されていることを確認してください。

- `psg-prod-eastus.azureedge.net` - CDN ホスト名
- `az818661.vo.msecnd.net` - CDN ホスト名
- `devopsgallerystorage.blob.core.windows.net` - ストレージ アカウントのホスト名
- `*.powershellgallery.com` - Web サイト
- `go.microsoft.com` - リダイレクト サービス

> [!NOTE]
> PowerShell ギャラリー サービスが停止すると、PowerShell ギャラリーとやりとりするコマンドレットが予期しないエラーで失敗することがあります。 PowerShell ギャラリーの現在の状態を確認するには、GitHub の [PowerShell Gallery Status](https://github.com/PowerShell/PowerShellGallery/blob/master/psgallery_status.md) ページを参照してください。
