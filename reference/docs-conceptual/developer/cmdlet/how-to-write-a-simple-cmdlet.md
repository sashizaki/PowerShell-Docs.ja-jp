---
title: '方法: 簡単なコマンドレットを記述する |Microsoft Docs'
ms.custom: ''
ms.date: 01/15/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 137543d8-0012-4cba-bcd6-98b25aac83bb
caps.latest.revision: 9
ms.openlocfilehash: 9bd72e8f97c194c98adb1049f5a966549113fd12
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83563885"
---
# <a name="how-to-write-a-cmdlet"></a>コマンドレットを記述する方法

この記事では、コマンドレットを記述する方法について説明します。 `Send-Greeting`コマンドレットは、入力として1つのユーザー名を受け取り、そのユーザーにあいさつを書き込みます。 このコマンドレットは多くの作業を実行しませんが、この例ではコマンドレットの主要なセクションを示しています。

## <a name="steps-to-write-a-cmdlet"></a>コマンドレットを記述する手順

1. クラスをコマンドレットとして宣言するには、**コマンドレット**の属性を使用します。 **コマンドレット**属性では、コマンドレット名の動詞と名詞を指定します。

   コマンドレット属性の詳細については、「**コマンドレット**[属性の宣言](cmdlet-attribute-declaration.md)」を参照してください。

2. クラスの名前を指定します。

3. コマンドレットが次のいずれかのクラスから派生するように指定します。

   * [System. Automation. コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet)
   * [PSCmdlet (システム管理)](/dotnet/api/System.Management.Automation.PSCmdlet)

4. コマンドレットのパラメーターを定義するには、 **Parameter**属性を使用します。 この場合、必須パラメーターが1つだけ指定されています。

   **Parameter**属性の詳細については、「 [parameterattribute 宣言](parameter-attribute-declaration.md)」を参照してください。

5. 入力を処理する入力処理メソッドをオーバーライドします。 この場合は、システムの管理....[コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)がオーバーライドされます。

6. あいさつ文を記述するには、 [WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)メソッドを使用します。
   あいさつは次の形式で表示されます。

   ```Output
   Hello <UserName>!
   ```

## <a name="example"></a>例

```csharp
using System.Management.Automation;  // Windows PowerShell assembly.

namespace SendGreeting
{
  // Declare the class as a cmdlet and specify the
  // appropriate verb and noun for the cmdlet name.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory=true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    // Override the ProcessRecord method to process
    // the supplied user name and write out a
    // greeting to the user by calling the WriteObject
    // method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "!");
    }
  }
}
```

## <a name="see-also"></a>関連項目

[System. Automation. コマンドレット](/dotnet/api/System.Management.Automation.Cmdlet)

[PSCmdlet (システム管理)](/dotnet/api/System.Management.Automation.PSCmdlet)

[システムの管理....................](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[WriteObject (システム管理)](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[属性の宣言](cmdlet-attribute-declaration.md)

[ParameterAttribute の宣言](parameter-attribute-declaration.md)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](writing-a-windows-powershell-cmdlet.md)
