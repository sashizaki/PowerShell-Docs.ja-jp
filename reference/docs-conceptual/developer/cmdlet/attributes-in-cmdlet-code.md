---
ms.date: 09/13/2016
ms.topic: reference
title: コマンドレット コードの属性
description: コマンドレット コードの属性
ms.openlocfilehash: 296bb8bcb06ef660e97dc792d1ecf596cc7c2930
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653653"
---
# <a name="attributes-in-cmdlet-code"></a><span data-ttu-id="a8eb4-103">コマンドレット コードの属性</span><span class="sxs-lookup"><span data-stu-id="a8eb4-103">Attributes in Cmdlet Code</span></span>

<span data-ttu-id="a8eb4-104">Windows PowerShell によって提供される共通の機能を使用するために、コマンドレットコードで定義されているクラスとパブリックプロパティは属性で修飾されています。</span><span class="sxs-lookup"><span data-stu-id="a8eb4-104">To use the common functionality provided by Windows PowerShell, the classes and public properties defined in the cmdlet code are decorated with attributes.</span></span> <span data-ttu-id="a8eb4-105">たとえば、次のクラス定義では、コマンドレット属性を使用して、 **Get Proc** コマンドレットが実装されている Microsoft .NET Framework クラスを識別します。</span><span class="sxs-lookup"><span data-stu-id="a8eb4-105">For example, the following class definition uses the Cmdlet attribute to identify the Microsoft .NET Framework class in which the **Get-Proc** cmdlet is implemented.</span></span> <span data-ttu-id="a8eb4-106">(このコマンドレットは、このドキュメントの例として使用されており、 `Get-Process` Windows PowerShell によって提供されるコマンドレットに似ています)。</span><span class="sxs-lookup"><span data-stu-id="a8eb4-106">(This cmdlet is used as an example in this document, and is similar to the `Get-Process` cmdlet provided by Windows PowerShell.)</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

<span data-ttu-id="a8eb4-107">これらの属性は、実装がコマンドレットコードの実装とは別であるため、メタデータと見なされます。</span><span class="sxs-lookup"><span data-stu-id="a8eb4-107">These attributes are considered metadata because their implementation is separate from the implementation of the cmdlet code.</span></span> <span data-ttu-id="a8eb4-108">Windows PowerShell ランタイムは、コマンドレットを実行すると、属性を認識し、各属性に対して適切なアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="a8eb4-108">When the Windows PowerShell runtime runs the cmdlet, it recognizes the attributes and then performs the appropriate action for each attribute.</span></span>

<span data-ttu-id="a8eb4-109">これらの属性によって提供される独自のバージョンの機能を実装することもできますが、適切なコマンドレットの設計では、これらの共通機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="a8eb4-109">Although you might want to implement your own version of the functionality provided by these attributes, a good cmdlet design uses these common functionalities.</span></span>

<span data-ttu-id="a8eb4-110">コマンドレットで宣言できるさまざまな属性の詳細については、「 [属性の型](./attribute-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8eb4-110">For more information about the different attributes that can be declared in your cmdlets, see [Attribute Types](./attribute-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a8eb4-111">参照</span><span class="sxs-lookup"><span data-stu-id="a8eb4-111">See Also</span></span>

[<span data-ttu-id="a8eb4-112">属性の種類</span><span class="sxs-lookup"><span data-stu-id="a8eb4-112">Attribute Types</span></span>](./attribute-types.md)

[<span data-ttu-id="a8eb4-113">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="a8eb4-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
