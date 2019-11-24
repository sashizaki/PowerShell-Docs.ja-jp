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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72370001"
---
# <a name="attributes-in-cmdlet-code"></a><span data-ttu-id="909d4-102">コマンドレット コードの属性</span><span class="sxs-lookup"><span data-stu-id="909d4-102">Attributes in Cmdlet Code</span></span>

<span data-ttu-id="909d4-103">Windows PowerShell によって提供される共通の機能を使用するために、コマンドレットコードで定義されているクラスとパブリックプロパティは属性で修飾されています。</span><span class="sxs-lookup"><span data-stu-id="909d4-103">To use the common functionality provided by Windows PowerShell, the classes and public properties defined in the cmdlet code are decorated with attributes.</span></span> <span data-ttu-id="909d4-104">たとえば、次のクラス定義では、コマンドレット属性を使用して、 **Get Proc**コマンドレットが実装されている Microsoft .NET Framework クラスを識別します。</span><span class="sxs-lookup"><span data-stu-id="909d4-104">For example, the following class definition uses the Cmdlet attribute to identify the Microsoft .NET Framework class in which the **Get-Proc** cmdlet is implemented.</span></span> <span data-ttu-id="909d4-105">(このコマンドレットは、このドキュメントの例として使用されており、Windows PowerShell によって提供される `Get-Process` コマンドレットに似ています)。</span><span class="sxs-lookup"><span data-stu-id="909d4-105">(This cmdlet is used as an example in this document, and is similar to the `Get-Process` cmdlet provided by Windows PowerShell.)</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

<span data-ttu-id="909d4-106">これらの属性は、実装がコマンドレットコードの実装とは別であるため、メタデータと見なされます。</span><span class="sxs-lookup"><span data-stu-id="909d4-106">These attributes are considered metadata because their implementation is separate from the implementation of the cmdlet code.</span></span> <span data-ttu-id="909d4-107">Windows PowerShell ランタイムは、コマンドレットを実行すると、属性を認識し、各属性に対して適切なアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="909d4-107">When the Windows PowerShell runtime runs the cmdlet, it recognizes the attributes and then performs the appropriate action for each attribute.</span></span>

<span data-ttu-id="909d4-108">これらの属性によって提供される独自のバージョンの機能を実装することもできますが、適切なコマンドレットの設計では、これらの共通機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="909d4-108">Although you might want to implement your own version of the functionality provided by these attributes, a good cmdlet design uses these common functionalities.</span></span>

<span data-ttu-id="909d4-109">コマンドレットで宣言できるさまざまな属性の詳細については、「[属性の型](./attribute-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="909d4-109">For more information about the different attributes that can be declared in your cmdlets, see [Attribute Types](./attribute-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="909d4-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="909d4-110">See Also</span></span>

[<span data-ttu-id="909d4-111">属性の型</span><span class="sxs-lookup"><span data-stu-id="909d4-111">Attribute Types</span></span>](./attribute-types.md)

[<span data-ttu-id="909d4-112">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="909d4-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
