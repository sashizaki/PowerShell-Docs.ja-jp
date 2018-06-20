---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.topic: conceptual
title: 既知の問題または制限の書き込みのテンプレート例
ms.openlocfilehash: 453d4e40b906ebcab7314f04e138ded271338846
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34221937"
---
>注: わかりやすいタイトルと簡単な説明を提供します

## <a name="example-erroneous-executionpolicy-errors"></a>例: Erroneous ExecutionPolicy エラー ##
Windows 7 で PowerShell モジュールと DSC リソースを使用すると、ExecutionPolicy についてレポートされるエラーとなる場合があります。

### <a name="resolution"></a>解決方法

解決するには、管理者特権の PowerShell セッション (管理者として実行) で、次のコマンドを実行して **ExecutionPolicy** を **RemoteSigned** に設定します。

```powershell
Set-ExecutionPolicy RemoteSigned
```
