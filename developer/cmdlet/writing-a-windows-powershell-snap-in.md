---
title: Windows PowerShell スナップインの書き込み |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- snap-ins [PowerShell SDK], PSSnapin example
ms.assetid: 875024f4-e02b-4416-80b9-af5e5b50aad6
caps.latest.revision: 7
ms.openlocfilehash: ee8a6538fa6ad4d0f480f2dac46fe0f823a38be8
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853768"
---
# <a name="writing-a-windows-powershell-snap-in"></a><span data-ttu-id="23ff0-102">Windows PowerShell スナップインを記述する</span><span class="sxs-lookup"><span data-stu-id="23ff0-102">Writing a Windows PowerShell Snap-in</span></span>

<span data-ttu-id="23ff0-103">この例では、アセンブリ内のすべてのコマンドレットと Windows PowerShell プロバイダーの登録に使用できる Windows PowerShell スナップインを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="23ff0-103">This example shows how to write a Windows PowerShell snap-in that can be used to register all the cmdlets and Windows PowerShell providers in an assembly.</span></span>

<span data-ttu-id="23ff0-104">この種類のスナップインでは、どのコマンドレットとプロバイダーを登録するを選択しません。</span><span class="sxs-lookup"><span data-stu-id="23ff0-104">With this type of snap-in, you do not select which cmdlets and providers you want to register.</span></span> <span data-ttu-id="23ff0-105">登録されているかを選択できるように、スナップインを作成するを参照してください。[カスタム Windows PowerShell スナップインの書き込み](./writing-a-custom-windows-powershell-snap-in.md)します。</span><span class="sxs-lookup"><span data-stu-id="23ff0-105">To write a snap-in that allows you to select what is registered, see [Writing a Custom Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md).</span></span>

### <a name="writing-a-windows-powershell-snap-in"></a><span data-ttu-id="23ff0-106">Windows PowerShell スナップインを記述する</span><span class="sxs-lookup"><span data-stu-id="23ff0-106">Writing a Windows PowerShell Snap-in</span></span>

1. <span data-ttu-id="23ff0-107">RunInstallerAttribute 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="23ff0-107">Add the RunInstallerAttribute attribute.</span></span>

2. <span data-ttu-id="23ff0-108">派生するパブリック クラスを作成、 [System.Management.Automation.Pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn)クラス。</span><span class="sxs-lookup"><span data-stu-id="23ff0-108">Create a public class that derives from the [System.Management.Automation.Pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn) class.</span></span>

    <span data-ttu-id="23ff0-109">この例では、クラス名は"GetProcPSSnapIn01"が。</span><span class="sxs-lookup"><span data-stu-id="23ff0-109">In this example, the class name is "GetProcPSSnapIn01".</span></span>

3. <span data-ttu-id="23ff0-110">(必須) スナップインの名前のパブリック プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="23ff0-110">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="23ff0-111">スナップインの名前を付けるときは使用しないで、次の文字。 #40 です。</span><span class="sxs-lookup"><span data-stu-id="23ff0-111">When naming snap-ins, do not use any of the following characters: # .</span></span> <span data-ttu-id="23ff0-112">, ( ) { } [ ] & - /\ $ ; : " ' \< > ; ?</span><span class="sxs-lookup"><span data-stu-id="23ff0-112">, ( ) { } [ ] & - /\ $ ; : " ' \< > ; ?</span></span> <span data-ttu-id="23ff0-113">@ \` \*</span><span class="sxs-lookup"><span data-stu-id="23ff0-113">@ \` \*</span></span>

    <span data-ttu-id="23ff0-114">この例で、スナップインの名前は"GetProcPSSnapIn01"です。</span><span class="sxs-lookup"><span data-stu-id="23ff0-114">In this example, the name of the snap-in is "GetProcPSSnapIn01".</span></span>

4. <span data-ttu-id="23ff0-115">(必須) スナップインの仕入先のパブリック プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="23ff0-115">Add a public property for the vendor of the snap-in (required).</span></span>

    <span data-ttu-id="23ff0-116">この例では、仕入先は"Microsoft"です。</span><span class="sxs-lookup"><span data-stu-id="23ff0-116">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="23ff0-117">スナップインが (省略可能) の仕入先のリソースのパブリック プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="23ff0-117">Add a public property for the vendor resource of the snap-in (optional).</span></span>

    <span data-ttu-id="23ff0-118">この例では、仕入先のリソースは、"GetProcPSSnapIn01、Microsoft"が。</span><span class="sxs-lookup"><span data-stu-id="23ff0-118">In this example, the vendor resource is "GetProcPSSnapIn01,Microsoft".</span></span>

6. <span data-ttu-id="23ff0-119">(必須) スナップインの説明については、パブリック プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="23ff0-119">Add a public property for the description of the snap-in (required).</span></span>

    <span data-ttu-id="23ff0-120">この例で、説明は、「これは get-proc コマンドレットを登録する Windows PowerShell スナップインが」。</span><span class="sxs-lookup"><span data-stu-id="23ff0-120">In this example, the description is "This is a Windows PowerShell snap-in that registers the get-proc cmdlet".</span></span>

7. <span data-ttu-id="23ff0-121">スナップインが (省略可能) の説明のリソースのパブリック プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="23ff0-121">Add a public property for the description resource of the snap-in (optional).</span></span>

    <span data-ttu-id="23ff0-122">この例では、仕入先のリソースは「GetProcPSSnapIn01、これが get-proc コマンドレットを登録する Windows PowerShell スナップイン」。</span><span class="sxs-lookup"><span data-stu-id="23ff0-122">In this example, the vendor resource is "GetProcPSSnapIn01,This is a Windows PowerShell snap-in that registers the get-proc cmdlet".</span></span>

## <a name="example"></a><span data-ttu-id="23ff0-123">例</span><span class="sxs-lookup"><span data-stu-id="23ff0-123">Example</span></span>

<span data-ttu-id="23ff0-124">この例では、Windows PowerShell シェルに Get-proc コマンドレットを登録するのに使用できる Windows PowerShell スナップインを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="23ff0-124">This example shows how to write a Windows PowerShell snap-in that can be used to register the Get-Proc cmdlet in the Windows PowerShell shell.</span></span> <span data-ttu-id="23ff0-125">のみ、GetProcPSSnapIn01 スナップイン クラスと、Get-proc コマンドレット クラスでこの例では、アセンブリの完全は含めること注意してください。</span><span class="sxs-lookup"><span data-stu-id="23ff0-125">Be aware that in this example, the complete assembly would contain only the GetProcPSSnapIn01 snap-in class and the Get-Proc cmdlet class.</span></span>

```csharp
[RunInstaller(true)]
public class GetProcPSSnapIn01 : PSSnapIn
{
  /// <summary>
  /// Create an instance of the GetProcPSSnapIn01 class.
  /// </summary>
  public GetProcPSSnapIn01()
         : base()
  {
  }

  /// <summary>
  /// Specify the name of the PowerShell snap-in.
  /// </summary>
  public override string Name
  {
    get
    {
      return "GetProcPSSnapIn01";
    }
  }

  /// <summary>
  /// Specify the vendor for the PowerShell snap-in.
  /// </summary>
  public override string Vendor
  {
    get
    {
      return "Microsoft";
    }
  }

  /// <summary>
  /// Specify the localization resource information for the vendor.
  /// Use the format: resourceBaseName,VendorName.
  /// </summary>
  public override string VendorResource
  {
    get
    {
      return "GetProcPSSnapIn01,Microsoft";
    }
  }

  /// <summary>
  /// Specify a description of the PowerShell snap-in.
  /// </summary>
  public override string Description
  {
    get
    {
      return "This is a PowerShell snap-in that includes the get-proc cmdlet.";
    }
  }

  /// <summary>
  /// Specify the localization resource information for the description.
  /// Use the format: resourceBaseName,Description.
  /// </summary>
  public override string DescriptionResource
  {
    get
    {
      return "GetProcPSSnapIn01,This is a PowerShell snap-in that includes the get-proc cmdlet.";
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="23ff0-126">参照</span><span class="sxs-lookup"><span data-stu-id="23ff0-126">See Also</span></span>

[<span data-ttu-id="23ff0-127">登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法</span><span class="sxs-lookup"><span data-stu-id="23ff0-127">How to Register Cmdlets, Providers, and Host Applications</span></span>](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="23ff0-128">登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法</span><span class="sxs-lookup"><span data-stu-id="23ff0-128">How to Register Cmdlets, Providers, and Host Applications</span></span>](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="23ff0-129">Windows PowerShell シェル SDK</span><span class="sxs-lookup"><span data-stu-id="23ff0-129">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
