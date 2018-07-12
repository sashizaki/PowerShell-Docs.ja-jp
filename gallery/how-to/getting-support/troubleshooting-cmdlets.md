---
ms.date: 06/12/2017
contributor: manikb
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: コマンドレットのトラブルシューティング
ms.openlocfilehash: c0a1fbcafd8c4443dc9d628c54c4c525d9701861
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37892476"
---
# <a name="troubleshooting-cmdlets"></a>コマンドレットのトラブルシューティング

## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a>"警告: パッケージ 'パッケージ名' をダウンロードできませんでした" 問題を解決する方法

一部のマシン上で `Install-Module` または `Update-Module` が失敗する場合があることがレポートされています。
調査の結果、ネットワーク接続の問題であることが判明しました。
最近、パッケージのダウンロードが安定するように、NuGet プロバイダーを更新しました。
下の指示に従い、最新版の NuGet プロバイダーをインストールし、モジュールをインストールするか、更新できます。
以下、'Azure' モジュールをサンプルとして使用します。

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```