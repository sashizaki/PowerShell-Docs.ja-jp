---
title: コマンドレットの動的パラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ae2196d-d6c8-4101-8805-4190d293af51
caps.latest.revision: 13
ms.openlocfilehash: 2fc73b6ef5a862fafb7a3c8fe3da19ac71bafc05
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068540"
---
# <a name="cmdlet-dynamic-parameters"></a>コマンドレットの動的パラメーター

コマンドレットは、特定の値を別のパラメーターの引数の場合などの特殊な条件下でユーザーに使用できるパラメーターを定義できます。 これらのパラメーターは、実行時に追加されと呼ばれます*動的パラメーター*のために必要な場合にのみ追加されます。 たとえば、特定のスイッチ パラメーターを指定する場合にのみ、いくつかのパラメーターを追加するコマンドレットをデザインできます。

> [!NOTE]
> プロバイダーと Windows PowerShell 関数では、動的パラメーターも定義できます。

## <a name="dynamic-parameters-in-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットで動的パラメーター

Windows PowerShell は、そのプロバイダーのコマンドレットのいくつかの動的パラメーターを使用します。 たとえば、`Get-Item`と`Get-ChildItem`コマンドレットを追加、`CodeSigningCert`時にパラメーターと、`Path`コマンドレットのパラメーターは、証明書プロバイダー パスを指定します。 場合、`Path`コマンドレットのパラメーターは、別のプロバイダーのパスを指定します、`CodeSigningCert`パラメーターは使用できません。

次の例に示す方法、`CodeSigningCert`時にパラメーターが追加されるときに、`Get-Item`コマンドレットを実行します。

最初の例では、Windows PowerShell ランタイムには、パラメーターが追加と、コマンドレットは成功します。

```powershell
Get-Item -Path cert:\CurrentUser -codesigningcert
```

```output
Location   : CurrentUser
StoreNames : {SmartCardRoot, UserDS, AuthRoot, CA...}
```

2 番目の例では、ファイル システム ドライブを指定し、エラーが返されます。 エラー メッセージが示す、`CodeSigningCert`パラメーターが見つかりません。

```powershell
Get-Item -Path C:\ -codesigningcert
```

```output
Get-Item : A parameter cannot be found that matches parameter name 'codesigningcert'.
At line:1 char:37
+  get-item -path C:\ -codesigningcert <<<<
--------
    CategoryInfo          : InvalidArgument: (:) [Get-Item], ParameterBindingException
    FullyQualifiedErrorId : NamedParameterNotFound,Microsoft.PowerShell.Commands.GetItemCommand
```

## <a name="support-for-dynamic-parameters"></a>動的パラメーターのサポート

動的パラメーターをサポートするには、コマンドレットのコードは、次の要素を含める必要があります。

[System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters)このインターフェイスは、動的パラメーターを取得するメソッドを提供します。

次に例を示します。

`public class SendGreetingCommand : Cmdlet, IDynamicParameters`

[System.Management.Automation.Idynamicparameters.Getdynamicparameters*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)このメソッドは、動的パラメーターの定義を含むオブジェクトを取得します。

次に例を示します。

```csharp
 public object GetDynamicParameters()
 {
   if (employee)
   {
     context= new SendGreetingCommandDynamicParameters();
     return context;
   }
   return null;
}
private SendGreetingCommandDynamicParameters context;
```

動的パラメーター クラスこのクラスは、追加するパラメーターを定義します。 このクラスは、各パラメーターと、コマンドレットで必要なオプションのエイリアスと検証属性のパラメーターの属性を含める必要があります。

次に例を示します。

```csharp
public class SendGreetingCommandDynamicParameters
{
  [Parameter]
  [ValidateSet ("Marketing", "Sales", "Development")]
  public string Department
  {
    get { return department; }
    set { department = value; }
  }
  private string department;
}
```

動的パラメーターをサポートするコマンドレットの完全な例を参照してください。[動的パラメーターを宣言する方法](./how-to-declare-dynamic-parameters.md)します。

## <a name="see-also"></a>参照

[System.Management.Automation.Idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters)

[System.Management.Automation.Idynamicparameters.Getdynamicparameters*](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[動的パラメーターを宣言する方法](./how-to-declare-dynamic-parameters.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
