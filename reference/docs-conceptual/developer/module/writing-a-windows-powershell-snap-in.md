---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell スナップインを記述する
description: Windows PowerShell スナップインを記述する
ms.openlocfilehash: f658c2fa1211bfb77d2e8edd3999ce7f92df13bb
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659455"
---
# <a name="writing-a-windows-powershell-snap-in"></a><span data-ttu-id="733fa-103">Windows PowerShell スナップインを記述する</span><span class="sxs-lookup"><span data-stu-id="733fa-103">Writing a Windows PowerShell Snap-in</span></span>

<span data-ttu-id="733fa-104">この例では、すべてのコマンドレットと Windows PowerShell プロバイダーをアセンブリに登録するために使用できる Windows PowerShell スナップインを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="733fa-104">This example shows how to write a Windows PowerShell snap-in that can be used to register all the cmdlets and Windows PowerShell providers in an assembly.</span></span>

<span data-ttu-id="733fa-105">この種類のスナップインでは、登録するコマンドレットとプロバイダーは選択しません。</span><span class="sxs-lookup"><span data-stu-id="733fa-105">With this type of snap-in, you do not select which cmdlets and providers you want to register.</span></span> <span data-ttu-id="733fa-106">登録内容を選択できるスナップインを作成するには、「 [カスタム Windows PowerShell スナップインの作成](./writing-a-custom-windows-powershell-snap-in.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="733fa-106">To write a snap-in that allows you to select what is registered, see [Writing a Custom Windows PowerShell Snap-in](./writing-a-custom-windows-powershell-snap-in.md).</span></span>

### <a name="writing-a-windows-powershell-snap-in"></a><span data-ttu-id="733fa-107">Windows PowerShell スナップインを記述する</span><span class="sxs-lookup"><span data-stu-id="733fa-107">Writing a Windows PowerShell Snap-in</span></span>

1. <span data-ttu-id="733fa-108">Runインストーラ属性属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="733fa-108">Add the RunInstallerAttribute attribute.</span></span>

2. <span data-ttu-id="733fa-109">[Add-pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn)クラスから派生するパブリッククラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="733fa-109">Create a public class that derives from the [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn) class.</span></span>

    <span data-ttu-id="733fa-110">この例では、クラス名は "GetProcPSSnapIn01" です。</span><span class="sxs-lookup"><span data-stu-id="733fa-110">In this example, the class name is "GetProcPSSnapIn01".</span></span>

3. <span data-ttu-id="733fa-111">スナップインの名前のパブリックプロパティを追加します (必須)。</span><span class="sxs-lookup"><span data-stu-id="733fa-111">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="733fa-112">スナップインに名前を付ける場合、 `#` 、、 `.` `,` 、、 `(` 、 `)` `{` `}` `[` `]` `&` `-` `/` `\` `$` `;` `:` `"` `'` `<` `>` `|` `?` `@` 、、、 `` ` `` 、、、、、、、、、、、、、、、、、、、、、、、、 `*`</span><span class="sxs-lookup"><span data-stu-id="733fa-112">When naming snap-ins, do not use any of the following characters: `#`, `.`, `,`, `(`, `)`, `{`, `}`, `[`, `]`, `&`, `-`, `/`, `\`, `$`, `;`, `:`, `"`, `'`, `<`, `>`, `|`, `?`, `@`, `` ` ``, `*`</span></span>

    <span data-ttu-id="733fa-113">この例では、スナップインの名前は "GetProcPSSnapIn01" です。</span><span class="sxs-lookup"><span data-stu-id="733fa-113">In this example, the name of the snap-in is "GetProcPSSnapIn01".</span></span>

4. <span data-ttu-id="733fa-114">スナップインのベンダのパブリックプロパティを追加します (必須)。</span><span class="sxs-lookup"><span data-stu-id="733fa-114">Add a public property for the vendor of the snap-in (required).</span></span>

    <span data-ttu-id="733fa-115">この例では、ベンダーは "Microsoft" です。</span><span class="sxs-lookup"><span data-stu-id="733fa-115">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="733fa-116">スナップインのベンダリソースのパブリックプロパティを追加します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="733fa-116">Add a public property for the vendor resource of the snap-in (optional).</span></span>

    <span data-ttu-id="733fa-117">この例では、vendor リソースは "GetProcPSSnapIn01, Microsoft" です。</span><span class="sxs-lookup"><span data-stu-id="733fa-117">In this example, the vendor resource is "GetProcPSSnapIn01,Microsoft".</span></span>

6. <span data-ttu-id="733fa-118">スナップインの説明のパブリックプロパティを追加します (必須)。</span><span class="sxs-lookup"><span data-stu-id="733fa-118">Add a public property for the description of the snap-in (required).</span></span>

    <span data-ttu-id="733fa-119">この例では、説明は "This は Windows PowerShell スナップインです。これは、get proc コマンドレットを登録する" です。</span><span class="sxs-lookup"><span data-stu-id="733fa-119">In this example, the description is "This is a Windows PowerShell snap-in that registers the  get-proc cmdlet".</span></span>

7. <span data-ttu-id="733fa-120">スナップインの説明リソースのパブリックプロパティを追加します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="733fa-120">Add a public property for the description resource of the snap-in (optional).</span></span>

    <span data-ttu-id="733fa-121">この例では、ベンダリソースは "GetProcPSSnapIn01, This は Windows PowerShell スナップインであり、これは get proc コマンドレットを登録する" です。</span><span class="sxs-lookup"><span data-stu-id="733fa-121">In this example, the vendor resource is "GetProcPSSnapIn01,This is a Windows PowerShell snap-in  that registers the get-proc cmdlet".</span></span>

## <a name="example"></a><span data-ttu-id="733fa-122">例</span><span class="sxs-lookup"><span data-stu-id="733fa-122">Example</span></span>

<span data-ttu-id="733fa-123">この例では、windows powershell シェルで Get-Proc コマンドレットを登録するために使用できる Windows PowerShell スナップインを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="733fa-123">This example shows how to write a Windows PowerShell snap-in that can be used to register the Get-Proc cmdlet in the Windows PowerShell shell.</span></span> <span data-ttu-id="733fa-124">この例では、完全なアセンブリには GetProcPSSnapIn01 スナップインクラスとコマンドレットクラスのみが含まれることに注意してください `Get-Proc` 。</span><span class="sxs-lookup"><span data-stu-id="733fa-124">Be aware that in this example, the complete assembly would contain only the GetProcPSSnapIn01 snap-in class and the `Get-Proc` cmdlet class.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="733fa-125">参照</span><span class="sxs-lookup"><span data-stu-id="733fa-125">See Also</span></span>

<span data-ttu-id="733fa-126">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="733fa-126">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="733fa-127">Windows PowerShell シェル SDK</span><span class="sxs-lookup"><span data-stu-id="733fa-127">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
