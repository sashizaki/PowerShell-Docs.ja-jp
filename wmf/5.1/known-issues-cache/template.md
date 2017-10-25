---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
title: "既知の問題または制限の書き込みのテンプレート例"
ms.openlocfilehash: b93393b2c84e76a301e6406d1388e82e95a2959c
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
>注: わかりやすいタイトルと簡単な説明を提供します

## <a name="example-erroneous-executionpolicy-errors"></a>例: Erroneous ExecutionPolicy エラー ##
Windows 7 で PowerShell モジュールと DSC リソースを使用すると、ExecutionPolicy についてレポートされるエラーとなる場合があります。

### <a name="resolution"></a>解決方法

解決するには、管理者特権の PowerShell セッション (管理者として実行) で、次のコマンドを実行して **ExecutionPolicy** を **RemoteSigned** に設定します。

```powershell
Set-ExecutionPolicy RemoteSigned
```

