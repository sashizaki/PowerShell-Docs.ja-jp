---
title: コマンドレットコードの属性 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1f92e329d304754d5596cef0c95dc597aca3a538
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774917"
---
# <a name="attributes-in-cmdlet-code"></a>コマンドレット コードの属性

Windows PowerShell によって提供される共通の機能を使用するために、コマンドレットコードで定義されているクラスとパブリックプロパティは属性で修飾されています。 たとえば、次のクラス定義では、コマンドレット属性を使用して、 **Get Proc**コマンドレットが実装されている Microsoft .NET Framework クラスを識別します。 (このコマンドレットは、このドキュメントの例として使用されており、 `Get-Process` Windows PowerShell によって提供されるコマンドレットに似ています)。

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

これらの属性は、実装がコマンドレットコードの実装とは別であるため、メタデータと見なされます。 Windows PowerShell ランタイムは、コマンドレットを実行すると、属性を認識し、各属性に対して適切なアクションを実行します。

これらの属性によって提供される独自のバージョンの機能を実装することもできますが、適切なコマンドレットの設計では、これらの共通機能を使用します。

コマンドレットで宣言できるさまざまな属性の詳細については、「[属性の型](./attribute-types.md)」を参照してください。

## <a name="see-also"></a>参照

[属性の種類](./attribute-types.md)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
