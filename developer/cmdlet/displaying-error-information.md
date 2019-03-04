---
title: エラー情報を表示する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76fcc0c1-9795-45d3-a564-40f822b657b5
caps.latest.revision: 8
ms.openlocfilehash: 4bc8666ee9053eb368402c8644558f4fe2dcc9ee
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858278"
---
# <a name="displaying-error-information"></a>エラー情報を表示する

このトピックでは、ユーザーによるエラー情報の表示方法について説明します。

コマンドレットには、エラーが発生すると、エラー情報の表示は、既定では、ように、次のエラー出力。

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

ただし、ユーザーによって表示できますエラー カテゴリを設定して、`$ErrorView`変数を`"CategoryView"`します。 カテゴリのビューには、エラーのフリー テキストによる説明ではなく、エラー レコードから特定の情報が表示されます。 このビューは、スキャンするエラーの長いリストがある場合に役立ちます。 カテゴリ表示で、以前のエラー メッセージは、次のように表示されます。

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

エラー カテゴリの詳細については、次を参照してください。 [Windows PowerShell のエラー レコード](./windows-powershell-error-records.md)します。

## <a name="see-also"></a>参照

[Windows PowerShell のエラー レコード](./windows-powershell-error-records.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
