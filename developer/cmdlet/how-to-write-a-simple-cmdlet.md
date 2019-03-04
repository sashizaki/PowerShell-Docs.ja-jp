---
title: 単純なコマンドレットを記述する方法 |Microsoft Docs
ms.custom: ''
ms.date: 01/15/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 137543d8-0012-4cba-bcd6-98b25aac83bb
caps.latest.revision: 9
ms.openlocfilehash: 8271512d06047f3ff5e45f81d971ffe2c1f6afd7
ms.sourcegitcommit: ce46e5098786e19d521b4bf948ff62d2b90bc53e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2019
ms.locfileid: "57251457"
---
# <a name="how-to-write-a-cmdlet"></a>コマンドレットを記述する方法

この記事では、コマンドレットを記述する方法を示します。 `Send-Greeting`コマンドレットは入力として 1 人のユーザー名を受け取りし、そのユーザーにあいさつ文を書き込みます。 コマンドレットは、多くの作業を実行しない、コマンドレットの主要なセクションでは、この例を示しています。

## <a name="steps-to-write-a-cmdlet"></a>コマンドレットを記述する手順について

1. コマンドレットとクラスを宣言するには、使用、**コマンドレット**属性。 **コマンドレット**属性は、動詞と名詞コマンドレット名を指定します。

   詳細については、**コマンドレット**属性は、「 [CmdletAttribute 宣言](cmdlet-attribute-declaration.md)します。

2. クラスの名前を指定します。

3. コマンドレットが、次のクラスのいずれかから派生したことを指定します。

   * [System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)
   * [System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)

4. コマンドレットのパラメーターを定義するには、使用、**パラメーター**属性。 この場合、パラメーターが指定された 1 つだけが必要です。

   詳細については、**パラメーター**属性は、「 [ParameterAttribute 宣言](parameter-attribute-declaration.md)します。

5. 入力の処理、入力を処理するメソッドをオーバーライドします。 ここで、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)メソッドをオーバーライドします。

6. 応答メッセージを書き込むメソッドを使用して[System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)します。
   応答メッセージは、次の形式で表示されます。

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

[System.Management.Automation.Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet)

[System.Management.Automation.PSCmdlet](/dotnet/api/System.Management.Automation.PSCmdlet)

[System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System.Management.Automation.Cmdlet.WriteObject](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject)

[CmdletAttribute 宣言](cmdlet-attribute-declaration.md)

[ParameterAttribute 宣言](parameter-attribute-declaration.md)

[Windows PowerShell コマンドレットの記述](writing-a-windows-powershell-cmdlet.md)