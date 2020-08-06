---
title: 確認メッセージ |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 8f8192f6ed96b1eeb22e3b28ce1366eee8e7c16a
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782193"
---
# <a name="confirmation-messages"></a>確認メッセージ

次に示すのは、[システム](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)の種類によって異なる確認メッセージが表示されます。このメソッドは、呼び出さ[れるメソッドの](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)種類によって異なります。

> [!IMPORTANT]
> 確認を要求する方法を示すサンプルコードについては、「確認[を要求する方法](./how-to-request-confirmations.md)」を参照してください。

## <a name="specifying-the-resource"></a>リソースの指定

変更しようとしているリソースを指定するには、このコマンドレットを呼び出してください[。Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0)メソッド。 この場合、メソッドのパラメーターを使用してリソースを指定する `target` と、操作は Windows PowerShell によって追加されます。 次のメッセージでは、"MyResource" というテキストが使用されるリソースであり、操作は呼び出しを行うコマンドの名前です。

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

次の例に示すように、ユーザーが確認要求に対して **[はい]** または **[はい] を**選択した場合は、" [System](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) ..............................................

```output
Confirm
Are you sure you want to perform this action?
Performing operation "Test-RequestConfirmationTemplate1" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): y

Confirm
Continue with this operation?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):
```

## <a name="specifying-the-operation-and-resource"></a>操作とリソースの指定

変更しようとしているリソースと、コマンドが実行される操作を指定するには、そのリソースを使用します。この場合、 [% 2a を呼び出します。Displayproperty = Fullname](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess?view=powershellsdk-1.1.0)メソッド。 この場合、パラメーターを使用してリソースを指定し、パラメーターを使用して `target` 操作を `target` 行います。 次のメッセージでは、"MyResource" というテキストが動作しているリソースであり、"Myresource" は実行される操作です。

```output
Confirm
Are you sure you want to perform this action?
Performing operation "MyAction" on Target "MyResource".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

ユーザーが前のメッセージに対して **[はい]** または **[はい] を**選択した場合は、" [System](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) ................................................

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

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
