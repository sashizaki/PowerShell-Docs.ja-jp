---
title: 確認メッセージ |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a886a26d-7730-4586-aeac-fd3f0bc60b88
caps.latest.revision: 8
ms.openlocfilehash: 229725b5b9f1f0082592dcebe11564fd2f630ce1
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059475"
---
# <a name="confirmation-messages"></a>確認メッセージ

バリエーションに応じて表示できるさまざまな確認メッセージをここでは、 [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)呼び出されるメソッド。

> [!IMPORTANT]
> 確認を要求する方法を示すサンプル コードでは、次を参照してください。[要求の確認方法](./how-to-request-confirmations.md)します。

## <a name="specifying-the-resource"></a>リソースを指定します。

呼び出すことによって変更される直前にあるリソースを指定することができます、 [System.Management.Automation.Cmdlet.Shouldprocess%2A でしょうか。Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0)メソッド。 この場合を使用して、リソースを指定する、`target`メソッド、および操作のパラメーターは、Windows PowerShell によって追加されます。 次のメッセージ テキスト"MyResource"が対象のリソースで、操作が呼び出しを行うコマンドの名前とします。

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

ユーザーが選択した場合**はい**または**すべてはい**、確認を要求 (示すように、次の例) への呼び出し、 [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドを作成すると、これにより、2 番目の確認メッセージが表示されます。

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="specifying-the-operation-and-resource"></a>操作とリソースを指定します。

変更されようとしているリソースおよびコマンドが呼び出すことによって実行される操作を指定することができます、 [System.Management.Automation.Cmdlet.Shouldprocess%2A でしょうか。Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0)メソッド。 この場合を使用して、リソースを指定する、`target`パラメーターと、操作を使用して、`target`パラメーター。 次のメッセージ テキスト"MyResource"は対象のリソースと"myaction という名前"は、操作を実行します。

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

ユーザーが選択した場合**はい**または**すべてはい**前のメッセージへの呼び出しに、 [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドが行われる原因となる、2 番目の確認メッセージが表示されます。

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
