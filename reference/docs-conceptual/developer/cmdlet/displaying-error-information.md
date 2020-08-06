---
title: エラー情報の表示 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e542110e9c35a74c5d4c112b0a831f7f8ad9242e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774577"
---
# <a name="displaying-error-information"></a>エラー情報を表示する

このトピックでは、ユーザーがエラー情報を表示する方法について説明します。

コマンドレットでエラーが発生した場合、既定では、エラー情報の表示は次のようなエラー出力になります。

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

ただし、ユーザーは変数をに設定することによって、エラーをカテゴリ別に表示でき `$ErrorView` `"CategoryView"` ます。 カテゴリビューでは、エラーの詳細な説明ではなく、エラーレコードからの特定の情報が表示されます。 このビューは、スキャンするエラーの一覧が長い場合に便利です。 カテゴリビューでは、前のエラーメッセージが次のように表示されます。

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

エラーカテゴリの詳細については、「 [Windows PowerShell エラーレコード](./windows-powershell-error-records.md)」を参照してください。

## <a name="see-also"></a>参照

[Windows PowerShell エラー レコード](./windows-powershell-error-records.md)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
