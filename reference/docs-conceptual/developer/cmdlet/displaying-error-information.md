---
title: エラー情報の表示 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76fcc0c1-9795-45d3-a564-40f822b657b5
caps.latest.revision: 8
ms.openlocfilehash: 4bc8666ee9053eb368402c8644558f4fe2dcc9ee
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369971"
---
# <a name="displaying-error-information"></a>エラー情報を表示する

このトピックでは、ユーザーがエラー情報を表示する方法について説明します。

コマンドレットでエラーが発生した場合、既定では、エラー情報の表示は次のようなエラー出力になります。

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

ただし、ユーザーは `$ErrorView` 変数を `"CategoryView"` に設定することにより、エラーをカテゴリ別に表示できます。 カテゴリビューでは、エラーの詳細な説明ではなく、エラーレコードからの特定の情報が表示されます。 このビューは、スキャンするエラーの一覧が長い場合に便利です。 カテゴリビューでは、前のエラーメッセージが次のように表示されます。

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

エラーカテゴリの詳細については、「 [Windows PowerShell エラーレコード](./windows-powershell-error-records.md)」を参照してください。

## <a name="see-also"></a>参照

[Windows PowerShell エラーレコード](./windows-powershell-error-records.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
