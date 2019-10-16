---
title: コマンドレット動的パラメーター |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ae2196d-d6c8-4101-8805-4190d293af51
caps.latest.revision: 13
ms.openlocfilehash: 19d31f6b619dff23e7e35bb53d2397f4f41eb728
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369881"
---
# <a name="cmdlet-dynamic-parameters"></a>コマンドレット動的パラメーター

コマンドレットでは、他のパラメーターの引数が特定の値の場合など、特殊な条件下でユーザーが使用できるパラメーターを定義できます。 これらのパラメーターは、必要なときにのみ追加されるため、実行時に追加され、動的パラメーターと呼ばれます。 たとえば、特定のスイッチパラメーターが指定されている場合にのみ、いくつかのパラメーターを追加するコマンドレットを設計できます。

> [!NOTE]
> プロバイダーと PowerShell 関数では、動的パラメーターを定義することもできます。

## <a name="dynamic-parameters-in-powershell-cmdlets"></a>PowerShell コマンドレットの動的パラメーター

PowerShell では、プロバイダーコマンドレットのいくつかで動的パラメーターが使用されます。 たとえば、`Get-Item` および `Get-ChildItem` のコマンドレットは、 **Path**パラメーターに**証明書**プロバイダーのパスが指定されている場合に、実行時に**codesigningcert**パラメーターを追加します。 **Path**パラメーターに別のプロバイダーのパスが指定されている場合、 **Codesigningcert**パラメーターは使用できません。

次の例は、`Get-Item` が実行されたときに、実行時に**Codesigningcert**パラメーターがどのように追加されるかを示しています。

この例では、PowerShell ランタイムによってパラメーターが追加され、コマンドレットが正常に実行されました。

```powershell
Get-Item -Path cert:\CurrentUser -CodeSigningCert
```

```Output
Location   : CurrentUser
StoreNames : {SmartCardRoot, UserDS, AuthRoot, CA...}
```

この例では、**ファイルシステム**ドライブが指定され、エラーが返されます。 エラーメッセージは、 **Codesigningcert**パラメーターが見つからないことを示しています。

```powershell
Get-Item -Path C:\ -CodeSigningCert
```

```Output
Get-Item : A parameter cannot be found that matches parameter name 'codesigningcert'.
At line:1 char:37
+  get-item -path C:\ -codesigningcert <<<<
--------
    CategoryInfo          : InvalidArgument: (:) [Get-Item], ParameterBindingException
    FullyQualifiedErrorId : NamedParameterNotFound,Microsoft.PowerShell.Commands.GetItemCommand
```

## <a name="support-for-dynamic-parameters"></a>動的パラメーターのサポート

動的パラメーターをサポートするには、次の要素をコマンドレットコードに含める必要があります。

### <a name="interface"></a>インターフェイス

[IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters)のようになります。
このインターフェイスは、動的パラメーターを取得するメソッドを提供します。

たとえば、次のようになります。

`public class SendGreetingCommand : Cmdlet, IDynamicParameters`

### <a name="method"></a>認証方法

[IDynamicParameters](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)のようにしてください。
このメソッドは、動的パラメーター定義を含むオブジェクトを取得します。

たとえば、次のようになります。

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

### <a name="class"></a>［クラス］

追加する動的パラメーターを定義するクラス。 このクラスには、各パラメーターの**パラメーター**属性と、コマンドレットで必要とされるオプションの**エイリアス**および**検証**属性が含まれている必要があります。

たとえば、次のようになります。

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

動的パラメーターをサポートするコマンドレットの完全な例については、「[動的パラメーターを宣言する方法](./how-to-declare-dynamic-parameters.md)」を参照してください。

## <a name="see-also"></a>「

[IDynamicParameters (システム管理)](/dotnet/api/System.Management.Automation.IDynamicParameters)

[IDynamicParameters (システムの管理) パラメーター](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[動的パラメーターを宣言する方法](./how-to-declare-dynamic-parameters.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
