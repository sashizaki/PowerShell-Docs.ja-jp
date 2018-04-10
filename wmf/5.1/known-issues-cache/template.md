---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
title: 既知の問題または制限の書き込みのテンプレート例
ms.openlocfilehash: cecf31127aaa1942471877a2056230ab592bd095
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
>注: わかりやすいタイトルと簡単な説明を提供します

## <a name="example-erroneous-executionpolicy-errors"></a>例: Erroneous ExecutionPolicy エラー ##
Windows 7 で PowerShell モジュールと DSC リソースを使用すると、ExecutionPolicy についてレポートされるエラーとなる場合があります。

### <a name="resolution"></a>解決方法

解決するには、管理者特権の PowerShell セッション (管理者として実行) で、次のコマンドを実行して **ExecutionPolicy** を **RemoteSigned** に設定します。

```powershell
Set-ExecutionPolicy RemoteSigned
```