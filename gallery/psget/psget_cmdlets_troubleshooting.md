---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: "ギャラリー, PowerShell, コマンドレット, PSGet"
title: psget_cmdlets_troubleshooting
ms.openlocfilehash: ccb39f44e8d11f1e2a912da0c4f18b700e836c91
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
## <a name="how-to-resolve-warning-package-your-package-name-failed-to-download-issue"></a>"警告: パッケージ 'パッケージ名' をダウンロードできませんでした" 問題を解決する方法




Install-Module または Update-Module が一部のコンピューターで時折失敗することが報告されています。
調査の結果、ネットワーク接続の問題であることが判明しました。
最近、パッケージのダウンロードが安定するように、NuGet プロバイダーを更新しました。
下の指示に従い、最新版の NuGet プロバイダーをインストールし、モジュールをインストールするか、更新できます。
以下、'Azure' モジュールをサンプルとして使用します。

```powershell
Install-PackageProvider NuGet -MinimumVersion 2.8.5.206 -Force
Launch new PowerShell Console
Update-Module Azure -Verbose
```

