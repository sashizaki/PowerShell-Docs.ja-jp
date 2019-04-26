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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068686"
---
# <a name="attributes-in-cmdlet-code"></a><span data-ttu-id="4d6b4-102">コマンドレット コードの属性</span><span class="sxs-lookup"><span data-stu-id="4d6b4-102">Attributes in Cmdlet Code</span></span>

<span data-ttu-id="4d6b4-103">Windows PowerShell によって提供される一般的な機能を使用するには、クラスとコマンドレットのコードで定義されたパブリック プロパティは、属性で装飾されます。</span><span class="sxs-lookup"><span data-stu-id="4d6b4-103">To use the common functionality provided by Windows PowerShell, the classes and public properties defined in the cmdlet code are decorated with attributes.</span></span> <span data-ttu-id="4d6b4-104">次のクラス定義はコマンドレットの属性を使用して、Microsoft .NET Framework クラスを識別するためになど、 **Get-proc**コマンドレットが実装されます。</span><span class="sxs-lookup"><span data-stu-id="4d6b4-104">For example, the following class definition uses the Cmdlet attribute to identify the Microsoft .NET Framework class in which the **Get-Proc** cmdlet is implemented.</span></span> <span data-ttu-id="4d6b4-105">(このコマンドレットは、このドキュメントで例として使用と似ています、`Get-Process`コマンドレットの Windows PowerShell によって提供されます)。</span><span class="sxs-lookup"><span data-stu-id="4d6b4-105">(This cmdlet is used as an example in this document, and is similar to the `Get-Process` cmdlet provided by Windows PowerShell.)</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

<span data-ttu-id="4d6b4-106">これらの属性は、その実装は、コマンドレット コードの実装から独立したため、メタデータと見なされます。</span><span class="sxs-lookup"><span data-stu-id="4d6b4-106">These attributes are considered metadata because their implementation is separate from the implementation of the cmdlet code.</span></span> <span data-ttu-id="4d6b4-107">Windows PowerShell ランタイムがコマンドレットを実行すると、属性を認識し、属性ごとに、適切な操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="4d6b4-107">When the Windows PowerShell runtime runs the cmdlet, it recognizes the attributes and then performs the appropriate action for each attribute.</span></span>

<span data-ttu-id="4d6b4-108">ただしこれらの属性によって提供される機能の独自のバージョンを実装することが適切なコマンドレットのデザインは、これらの一般的な機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="4d6b4-108">Although you might want to implement your own version of the functionality provided by these attributes, a good cmdlet design uses these common functionalities.</span></span>

<span data-ttu-id="4d6b4-109">コマンドレットで宣言できるさまざまな属性の詳細については、次を参照してください。[属性の型](./attribute-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d6b4-109">For more information about the different attributes that can be declared in your cmdlets, see [Attribute Types](./attribute-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4d6b4-110">参照</span><span class="sxs-lookup"><span data-stu-id="4d6b4-110">See Also</span></span>

[<span data-ttu-id="4d6b4-111">属性の型</span><span class="sxs-lookup"><span data-stu-id="4d6b4-111">Attribute Types</span></span>](./attribute-types.md)

[<span data-ttu-id="4d6b4-112">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="4d6b4-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
