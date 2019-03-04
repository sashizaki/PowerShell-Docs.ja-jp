---
title: コマンドレット コード内の属性 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aea8d293-c45b-41eb-8385-548f7c9b280b
caps.latest.revision: 10
ms.openlocfilehash: 14505c4f7cc8490418ca463e3b81902f29d4f90b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853788"
---
# <a name="attributes-in-cmdlet-code"></a>コマンドレット コードの属性

Windows PowerShell によって提供される一般的な機能を使用するには、クラスとコマンドレットのコードで定義されたパブリック プロパティは、属性で装飾されます。 次のクラス定義はコマンドレットの属性を使用して、Microsoft .NET Framework クラスを識別するためになど、 **Get-proc**コマンドレットが実装されます。 (このコマンドレットは、このドキュメントで例として使用と似ています、`Get-Process`コマンドレットの Windows PowerShell によって提供されます)。

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

これらの属性は、その実装は、コマンドレット コードの実装から独立したため、メタデータと見なされます。 Windows PowerShell ランタイムがコマンドレットを実行すると、属性を認識し、属性ごとに、適切な操作を実行します。

ただしこれらの属性によって提供される機能の独自のバージョンを実装することが適切なコマンドレットのデザインは、これらの一般的な機能を使用します。

コマンドレットで宣言できるさまざまな属性の詳細については、次を参照してください。[属性の型](./attribute-types.md)します。

## <a name="see-also"></a>参照

[属性の型](./attribute-types.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
