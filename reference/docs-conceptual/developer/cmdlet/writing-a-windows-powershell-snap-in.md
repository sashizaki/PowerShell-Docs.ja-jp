---
title: Windows PowerShell スナップインを作成する |Microsoft Docs
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
ms.openlocfilehash: d12a66e354a23041fffb0f8fa286c849849ec2b0
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870474"
---
# <a name="writing-a-windows-powershell-snap-in"></a><span data-ttu-id="7c78c-102">Windows PowerShell スナップインを記述する</span><span class="sxs-lookup"><span data-stu-id="7c78c-102">Writing a Windows PowerShell Snap-in</span></span>

<span data-ttu-id="7c78c-103">この例では、すべてのコマンドレットと Windows PowerShell プロバイダーをアセンブリに登録するために使用できる Windows PowerShell スナップインを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7c78c-103">This example shows how to write a Windows PowerShell snap-in that can be used to register all the cmdlets and Windows PowerShell providers in an assembly.</span></span>

<span data-ttu-id="7c78c-104">この種類のスナップインでは、登録するコマンドレットとプロバイダーは選択しません。</span><span class="sxs-lookup"><span data-stu-id="7c78c-104">With this type of snap-in, you do not select which cmdlets and providers you want to register.</span></span> <span data-ttu-id="7c78c-105">登録内容を選択できるスナップインを作成するには、「[カスタム Windows PowerShell スナップインの作成](./writing-a-custom-windows-powershell-snap-in.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c78c-105">To write a snap-in that allows you to select what is registered, see [Writing a Custom Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md).</span></span>

### <a name="writing-a-windows-powershell-snap-in"></a><span data-ttu-id="7c78c-106">Windows PowerShell スナップインを記述する</span><span class="sxs-lookup"><span data-stu-id="7c78c-106">Writing a Windows PowerShell Snap-in</span></span>

1. <span data-ttu-id="7c78c-107">Runインストーラ属性属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="7c78c-107">Add the RunInstallerAttribute attribute.</span></span>

2. <span data-ttu-id="7c78c-108">[Add-pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn)クラスから派生するパブリッククラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="7c78c-108">Create a public class that derives from the [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) class.</span></span>

    <span data-ttu-id="7c78c-109">この例では、クラス名は "GetProcPSSnapIn01" です。</span><span class="sxs-lookup"><span data-stu-id="7c78c-109">In this example, the class name is "GetProcPSSnapIn01".</span></span>

3. <span data-ttu-id="7c78c-110">スナップインの名前のパブリックプロパティを追加します (必須)。</span><span class="sxs-lookup"><span data-stu-id="7c78c-110">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="7c78c-111">スナップインに名前を付けるときは、`#`、`.`、`,`、`(`、`)`、`{`、`}`、`[`、`]`、`&`、`-`、`/`、`\`、`$`、`;`、`:`、`"`、`'`、`<`、`>`、`|`のいずれの文字も使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="7c78c-111">When naming snap-ins, do not use any of the following characters: `#`, `.`, `,`, `(`, `)`, `{`, `}`, `[`, `]`, `&`, `-`, `/`, `\`, `$`, `;`, `:`, `"`, `'`, `<`, `>`, `|`, `?`, `@`, `` ` ``, `*`</span></span>

    <span data-ttu-id="7c78c-112">この例では、スナップインの名前は "GetProcPSSnapIn01" です。</span><span class="sxs-lookup"><span data-stu-id="7c78c-112">In this example, the name of the snap-in is "GetProcPSSnapIn01".</span></span>

4. <span data-ttu-id="7c78c-113">スナップインのベンダのパブリックプロパティを追加します (必須)。</span><span class="sxs-lookup"><span data-stu-id="7c78c-113">Add a public property for the vendor of the snap-in (required).</span></span>

    <span data-ttu-id="7c78c-114">この例では、ベンダーは "Microsoft" です。</span><span class="sxs-lookup"><span data-stu-id="7c78c-114">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="7c78c-115">スナップインのベンダリソースのパブリックプロパティを追加します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="7c78c-115">Add a public property for the vendor resource of the snap-in (optional).</span></span>

    <span data-ttu-id="7c78c-116">この例では、vendor リソースは "GetProcPSSnapIn01, Microsoft" です。</span><span class="sxs-lookup"><span data-stu-id="7c78c-116">In this example, the vendor resource is "GetProcPSSnapIn01,Microsoft".</span></span>

6. <span data-ttu-id="7c78c-117">スナップインの説明のパブリックプロパティを追加します (必須)。</span><span class="sxs-lookup"><span data-stu-id="7c78c-117">Add a public property for the description of the snap-in (required).</span></span>

    <span data-ttu-id="7c78c-118">この例では、説明は "This は Windows PowerShell スナップインです。これは、get proc コマンドレットを登録する" です。</span><span class="sxs-lookup"><span data-stu-id="7c78c-118">In this example, the description is "This is a Windows PowerShell snap-in that registers the  get-proc cmdlet".</span></span>

7. <span data-ttu-id="7c78c-119">スナップインの説明リソースのパブリックプロパティを追加します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="7c78c-119">Add a public property for the description resource of the snap-in (optional).</span></span>

    <span data-ttu-id="7c78c-120">この例では、ベンダリソースは "GetProcPSSnapIn01, This は Windows PowerShell スナップインであり、これは get proc コマンドレットを登録する" です。</span><span class="sxs-lookup"><span data-stu-id="7c78c-120">In this example, the vendor resource is "GetProcPSSnapIn01,This is a Windows PowerShell snap-in  that registers the get-proc cmdlet".</span></span>

## <a name="example"></a><span data-ttu-id="7c78c-121">例</span><span class="sxs-lookup"><span data-stu-id="7c78c-121">Example</span></span>

<span data-ttu-id="7c78c-122">この例では、windows powershell シェルで Get Proc コマンドレットを登録するために使用できる Windows PowerShell スナップインを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7c78c-122">This example shows how to write a Windows PowerShell snap-in that can be used to register the Get-Proc cmdlet in the Windows PowerShell shell.</span></span> <span data-ttu-id="7c78c-123">この例では、完全なアセンブリには GetProcPSSnapIn01 スナップインクラスと `Get-Proc` コマンドレットクラスのみが含まれることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7c78c-123">Be aware that in this example, the complete assembly would contain only the GetProcPSSnapIn01 snap-in class and the `Get-Proc` cmdlet class.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="7c78c-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c78c-124">See Also</span></span>

<span data-ttu-id="7c78c-125">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="7c78c-125">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="7c78c-126">Windows PowerShell Shell SDK</span><span class="sxs-lookup"><span data-stu-id="7c78c-126">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
