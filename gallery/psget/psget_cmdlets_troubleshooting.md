---
description: 
manager: carolz
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "powershell,コマンドレット,ギャラリー"
ms.date: 2016-10-14
contributor: manikb
title: psget_cmdlets_troubleshooting
ms.technology: powershell
translationtype: Human Translation
ms.sourcegitcommit: e6c526d1074f61154d03b92b6bf6f599976f5936
ms.openlocfilehash: 740c72620e1a5a114716f924f859c57cad125614

---

## "警告: パッケージ 'パッケージ名' をダウンロードできませんでした" 問題を解決する方法




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




<!--HONumber=Oct16_HO2-->


