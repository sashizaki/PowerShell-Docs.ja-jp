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
# <a name="attributes-in-cmdlet-code"></a><span data-ttu-id="979f7-102">コマンドレット コードの属性</span><span class="sxs-lookup"><span data-stu-id="979f7-102">Attributes in Cmdlet Code</span></span>

<span data-ttu-id="979f7-103">Windows PowerShell によって提供される共通の機能を使用するために、コマンドレットコードで定義されているクラスとパブリックプロパティは属性で修飾されています。</span><span class="sxs-lookup"><span data-stu-id="979f7-103">To use the common functionality provided by Windows PowerShell, the classes and public properties defined in the cmdlet code are decorated with attributes.</span></span> <span data-ttu-id="979f7-104">たとえば、次のクラス定義では、コマンドレット属性を使用して、 **Get Proc**コマンドレットが実装されている Microsoft .NET Framework クラスを識別します。</span><span class="sxs-lookup"><span data-stu-id="979f7-104">For example, the following class definition uses the Cmdlet attribute to identify the Microsoft .NET Framework class in which the **Get-Proc** cmdlet is implemented.</span></span> <span data-ttu-id="979f7-105">(このコマンドレットは、このドキュメントの例として使用されており、 `Get-Process` Windows PowerShell によって提供されるコマンドレットに似ています)。</span><span class="sxs-lookup"><span data-stu-id="979f7-105">(This cmdlet is used as an example in this document, and is similar to the `Get-Process` cmdlet provided by Windows PowerShell.)</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "Proc")]
public class GetProcCommand : Cmdlet
```

<span data-ttu-id="979f7-106">これらの属性は、実装がコマンドレットコードの実装とは別であるため、メタデータと見なされます。</span><span class="sxs-lookup"><span data-stu-id="979f7-106">These attributes are considered metadata because their implementation is separate from the implementation of the cmdlet code.</span></span> <span data-ttu-id="979f7-107">Windows PowerShell ランタイムは、コマンドレットを実行すると、属性を認識し、各属性に対して適切なアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="979f7-107">When the Windows PowerShell runtime runs the cmdlet, it recognizes the attributes and then performs the appropriate action for each attribute.</span></span>

<span data-ttu-id="979f7-108">これらの属性によって提供される独自のバージョンの機能を実装することもできますが、適切なコマンドレットの設計では、これらの共通機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="979f7-108">Although you might want to implement your own version of the functionality provided by these attributes, a good cmdlet design uses these common functionalities.</span></span>

<span data-ttu-id="979f7-109">コマンドレットで宣言できるさまざまな属性の詳細については、「[属性の型](./attribute-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="979f7-109">For more information about the different attributes that can be declared in your cmdlets, see [Attribute Types](./attribute-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="979f7-110">参照</span><span class="sxs-lookup"><span data-stu-id="979f7-110">See Also</span></span>

[<span data-ttu-id="979f7-111">属性の種類</span><span class="sxs-lookup"><span data-stu-id="979f7-111">Attribute Types</span></span>](./attribute-types.md)

[<span data-ttu-id="979f7-112">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="979f7-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
