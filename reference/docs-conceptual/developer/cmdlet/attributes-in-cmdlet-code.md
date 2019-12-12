---
title: コマンドレットコードの属性 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aea8d293-c45b-41eb-8385-548f7c9b280b
caps.latest.revision: 10
ms.openlocfilehash: 14505c4f7cc8490418ca463e3b81902f29d4f90b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72370001"
---
# <a name="attributes-in-cmdlet-code"></a>コマンドレット コードの属性

Windows PowerShell によって提供される共通の機能を使用するために、コマンドレットコードで定義されているクラスとパブリックプロパティは属性で修飾されています。 たとえば、次のクラス定義では、コマンドレット属性を使用して、 **Get Proc**コマンドレットが実装されている Microsoft .NET Framework クラスを識別します。 (このコマンドレットは、このドキュメントの例として使用されており、Windows PowerShell によって提供される `Get-Process` コマンドレットに似ています)。

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

これらの属性は、実装がコマンドレットコードの実装とは別であるため、メタデータと見なされます。 Windows PowerShell ランタイムは、コマンドレットを実行すると、属性を認識し、各属性に対して適切なアクションを実行します。

これらの属性によって提供される独自のバージョンの機能を実装することもできますが、適切なコマンドレットの設計では、これらの共通機能を使用します。

コマンドレットで宣言できるさまざまな属性の詳細については、「[属性の型](./attribute-types.md)」を参照してください。

## <a name="see-also"></a>参照

[属性の型](./attribute-types.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
