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
 ><span data-ttu-id="e508c-103">注: わかりやすいタイトルと簡単な説明を提供します</span><span class="sxs-lookup"><span data-stu-id="e508c-103">Note: provide a proposed descriptive title and a brief description</span></span>

## <a name="example-erroneous-executionpolicy-errors"></a><span data-ttu-id="e508c-104">次に例を示します。Erroneous ExecutionPolicy エラー</span><span class="sxs-lookup"><span data-stu-id="e508c-104">Example: Erroneous ExecutionPolicy errors</span></span>
<span data-ttu-id="e508c-105">Windows 7 で PowerShell モジュールと DSC リソースを使用すると、ExecutionPolicy についてレポートされるエラーとなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e508c-105">On Windows 7, the use of PowerShell modules and DSC resources may result in errors reported about ExecutionPolicy.</span></span>

### <a name="resolution"></a><span data-ttu-id="e508c-106">解決方法</span><span class="sxs-lookup"><span data-stu-id="e508c-106">Resolution</span></span>

<span data-ttu-id="e508c-107">解決するには、管理者特権の PowerShell セッション (管理者として実行) で、次のコマンドを実行して **ExecutionPolicy** を **RemoteSigned** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e508c-107">To resolve, set the **ExecutionPolicy** to **RemoteSigned** by running the following command in an elevated PowerShell session (Run as Administrator):</span></span>

```powershell
Set-ExecutionPolicy RemoteSigned
```
