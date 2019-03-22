---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.topic: conceptual
title: 既知の問題または制限の書き込みのテンプレート例
ms.openlocfilehash: 8c1004e16f78913174af2e519e451f6fd9f30ff7
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794495"
---
 >注: わかりやすいタイトルと簡単な説明を提供します

## <a name="example-erroneous-executionpolicy-errors"></a>次に例を示します。Erroneous ExecutionPolicy エラー
Windows 7 で PowerShell モジュールと DSC リソースを使用すると、ExecutionPolicy についてレポートされるエラーとなる場合があります。

### <a name="resolution"></a>解決方法

解決するには、管理者特権の PowerShell セッション (管理者として実行) で、次のコマンドを実行して **ExecutionPolicy** を **RemoteSigned** に設定します。

```powershell
Set-ExecutionPolicy RemoteSigned
```
