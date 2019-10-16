---
title: カスタム Windows PowerShell スナップインを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- snap-ins [PowerShell SDK], custom PSSnapin example
- cmdlets [PowerShell SDK], specified in snap-ins
ms.assetid: 55c8b5cb-8ee2-4080-afc4-3f09c9f20128
caps.latest.revision: 6
ms.openlocfilehash: 4d50ef4dcd75d5c0ba802fbcfe2d7d1d7c954707
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364251"
---
# <a name="writing-a-custom-windows-powershell-snap-in"></a><span data-ttu-id="f78e6-102">カスタム Windows PowerShell スナップインを記述する</span><span class="sxs-lookup"><span data-stu-id="f78e6-102">Writing a Custom Windows PowerShell Snap-in</span></span>

<span data-ttu-id="f78e6-103">この例では、特定のコマンドレットを登録する Windows PowerShell スナップインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f78e6-103">This example shows how to write a Windows PowerShell snap-in that registers specific cmdlets.</span></span>

<span data-ttu-id="f78e6-104">この種類のスナップインでは、登録するコマンドレット、プロバイダー、種類、または形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="f78e6-104">With this type of snap-in, you specify which cmdlets, providers, types, or formats to register.</span></span> <span data-ttu-id="f78e6-105">アセンブリ内のすべてのコマンドレットとプロバイダーを登録するスナップインを作成する方法の詳細については、「 [Windows PowerShell スナップインの作成](./writing-a-windows-powershell-snap-in.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f78e6-105">For more information about how to write a snap-in that registers all the cmdlets and providers in an assembly, see [Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md).</span></span>

## <a name="to-write-a-windows-powershell-snap-in-that-registers-specific-cmdlets"></a><span data-ttu-id="f78e6-106">特定のコマンドレットを登録する Windows PowerShell スナップインを作成するには</span><span class="sxs-lookup"><span data-stu-id="f78e6-106">To write a Windows PowerShell Snap-in that registers specific cmdlets.</span></span>

1. <span data-ttu-id="f78e6-107">Runインストーラ属性属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="f78e6-107">Add the RunInstallerAttribute attribute.</span></span>

2. <span data-ttu-id="f78e6-108">[Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)クラスから派生するパブリッククラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f78e6-108">Create a public class that derives from the [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) class.</span></span>

   <span data-ttu-id="f78e6-109">この例では、クラス名は "CustomPSSnapinTest" です。</span><span class="sxs-lookup"><span data-stu-id="f78e6-109">In this example, the class name is "CustomPSSnapinTest".</span></span>

3. <span data-ttu-id="f78e6-110">スナップインの名前のパブリックプロパティを追加します (必須)。</span><span class="sxs-lookup"><span data-stu-id="f78e6-110">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="f78e6-111">スナップインに名前を付けるときは、次の文字を使用しないでください。 #.</span><span class="sxs-lookup"><span data-stu-id="f78e6-111">When naming snap-ins, do not use any of the following characters: # .</span></span> <span data-ttu-id="f78e6-112">, () {} [] &-/\ $;: "' \< > &#124; ?</span><span class="sxs-lookup"><span data-stu-id="f78e6-112">, ( ) { } [ ] & - /\ $ ; : " ' \< > &#124; ?</span></span> <span data-ttu-id="f78e6-113">@ \` \*</span><span class="sxs-lookup"><span data-stu-id="f78e6-113">@ \` \*</span></span>

   <span data-ttu-id="f78e6-114">この例では、スナップインの名前は "CustomPSSnapInTest" です。</span><span class="sxs-lookup"><span data-stu-id="f78e6-114">In this example, the name of the snap-in is "CustomPSSnapInTest".</span></span>

4. <span data-ttu-id="f78e6-115">スナップインのベンダのパブリックプロパティを追加します (必須)。</span><span class="sxs-lookup"><span data-stu-id="f78e6-115">Add a public property for the vendor of the snap-in (required).</span></span>

   <span data-ttu-id="f78e6-116">この例では、ベンダーは "Microsoft" です。</span><span class="sxs-lookup"><span data-stu-id="f78e6-116">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="f78e6-117">スナップインのベンダリソースのパブリックプロパティを追加します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="f78e6-117">Add a public property for the vendor resource of the snap-in (optional).</span></span>

   <span data-ttu-id="f78e6-118">この例では、ベンダリソースは "CustomPSSnapInTest, Microsoft" です。</span><span class="sxs-lookup"><span data-stu-id="f78e6-118">In this example, the vendor resource is "CustomPSSnapInTest,Microsoft".</span></span>

6. <span data-ttu-id="f78e6-119">スナップインの説明のパブリックプロパティを追加します (必須)。</span><span class="sxs-lookup"><span data-stu-id="f78e6-119">Add a public property for the description of the snap-in (required).</span></span>

   <span data-ttu-id="f78e6-120">この例での説明は次のとおりです。 "これは、テスト HelloWorld とテスト用のカスタム Windows PowerShell スナップインです。</span><span class="sxs-lookup"><span data-stu-id="f78e6-120">In this example, the description is: "This is a custom Windows PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets".</span></span>

7. <span data-ttu-id="f78e6-121">スナップインの説明リソースのパブリックプロパティを追加します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="f78e6-121">Add a public property for the description resource of the snap-in (optional).</span></span>

   <span data-ttu-id="f78e6-122">この例では、仕入先リソースは "CustomPSSnapInTest です。これは、テスト HelloWorld とテスト用のカスタムの Windows PowerShell スナップインです。このスナップインには、テスト HelloWorld とテスト用のコマンドレットが含まれています。"</span><span class="sxs-lookup"><span data-stu-id="f78e6-122">In this example, the vendor resource is "CustomPSSnapInTest, This is a custom Windows PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets".</span></span>

8. <span data-ttu-id="f78e6-123">カスタムスナップインに属するコマンドレットを指定します (省略可能[)。このクラスを](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry)使用してください。</span><span class="sxs-lookup"><span data-stu-id="f78e6-123">Specify the cmdlets that belong to the custom snap-in (optional) using the [System.Management.Automation.Runspaces.Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) class.</span></span> <span data-ttu-id="f78e6-124">ここで追加される情報には、コマンドレットの名前、.NET の種類、コマンドレットのヘルプファイル名が含まれています (コマンドレットヘルプファイル名の形式は dll-help)。</span><span class="sxs-lookup"><span data-stu-id="f78e6-124">The information added here includes the name of the cmdlet, its .NET type, and the cmdlet Help file name (the format of the cmdlet Help file name should be name.dll-help.xml).</span></span>

   <span data-ttu-id="f78e6-125">この例では、テスト HelloWorld と TestCustomSnapinTest コマンドレットを追加します。</span><span class="sxs-lookup"><span data-stu-id="f78e6-125">This example adds the Test-HelloWorld and TestCustomSnapinTest cmdlets.</span></span>

9. <span data-ttu-id="f78e6-126">カスタムスナップインに属するプロバイダーを指定します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="f78e6-126">Specify the providers that belong to the custom snap-in (optional).</span></span>

   <span data-ttu-id="f78e6-127">この例では、プロバイダーが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="f78e6-127">This example does not specify any providers.</span></span>

10. <span data-ttu-id="f78e6-128">カスタムスナップインに属する種類を指定します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="f78e6-128">Specify the types that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="f78e6-129">この例では、型は指定しません。</span><span class="sxs-lookup"><span data-stu-id="f78e6-129">This example does not specify any types.</span></span>

11. <span data-ttu-id="f78e6-130">カスタムスナップインに属する形式を指定します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="f78e6-130">Specify the formats that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="f78e6-131">この例では、形式は指定されていません。</span><span class="sxs-lookup"><span data-stu-id="f78e6-131">This example does not specify any formats.</span></span>

## <a name="example"></a><span data-ttu-id="f78e6-132">例</span><span class="sxs-lookup"><span data-stu-id="f78e6-132">Example</span></span>

<span data-ttu-id="f78e6-133">この例では、カスタム Windows PowerShell スナップインを記述して、テスト HelloWorld およびテスト用のコマンドレットの登録に使用できるようにする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f78e6-133">This example shows how to write a Custom Windows PowerShell snap-in that can be used to register the Test-HelloWorld and Test-CustomSnapinTest cmdlets.</span></span> <span data-ttu-id="f78e6-134">この例では、完全なアセンブリに、このスナップインによって登録されない他のコマンドレットとプロバイダーが含まれている可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f78e6-134">Be aware that in this example, the complete assembly could contain other cmdlets and providers that would not be registered by this snap-in.</span></span>

```csharp
[RunInstaller(true)]
public class CustomPSSnapinTest : CustomPSSnapIn
{
  /// <summary>
  /// Creates an instance of CustomPSSnapInTest class.
  /// </summary>
  public CustomPSSnapinTest()
          : base()
  {
  }

  /// <summary>
  /// Specify the name of the custom PowerShell snap-in.
  /// </summary>
  public override string Name
  {
    get
    {
      return "CustomPSSnapInTest";
    }
  }

  /// <summary>
  /// Specify the vendor for the custom PowerShell snap-in.
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
  /// Use the format: resourceBaseName,resourceName.
  /// </summary>
  public override string VendorResource
  {
    get
    {
        return "CustomPSSnapInTest,Microsoft";
    }
  }

  /// <summary>
  /// Specify a description of the custom PowerShell snap-in.
  /// </summary>
  public override string Description
  {
    get
    {
      return "This is a custom PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets.";
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
        return "CustomPSSnapInTest,This is a custom PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets.";
    }
  }

  /// <summary>
  /// Specify the cmdlets that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<CmdletConfigurationEntry> _cmdlets;
  public override Collection<CmdletConfigurationEntry> Cmdlets
  {
    get
    {
      if (_cmdlets == null)
      {
        _cmdlets = new Collection<CmdletConfigurationEntry>();
        _cmdlets.Add(new CmdletConfigurationEntry("test-customsnapintest", typeof(TestCustomSnapinTest), "TestCmdletHelp.dll-help.xml"));
        _cmdlets.Add(new CmdletConfigurationEntry("test-helloworld", typeof(TestHelloWorld), "HelloWorldHelp.dll-help.xml"));
      }

      return _cmdlets;
    }
  }

  /// <summary>
  /// Specify the providers that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<ProviderConfigurationEntry> _providers;
  public override Collection<ProviderConfigurationEntry> Providers
  {
    get
    {
      if (_providers == null)
      {
        _providers = new Collection<ProviderConfigurationEntry>();
      }

      return _providers;
    }
  }

  /// <summary>
  /// Specify the types that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<TypeConfigurationEntry> _types;
  public override Collection<TypeConfigurationEntry> Types
  {
    get
    {
      if (_types == null)
      {
        _types = new Collection<TypeConfigurationEntry>();
      }

      return _types;
    }
  }

  /// <summary>
  /// Specify the formats that belong to this custom PowerShell snap-in.
  /// </summary>
  private Collection<FormatConfigurationEntry> _formats;
  public override Collection<FormatConfigurationEntry> Formats
  {
    get
    {
      if (_formats == null)
      {
        _formats = new Collection<FormatConfigurationEntry>();
      }

      return _formats;
    }
  }
}
```

<span data-ttu-id="f78e6-135">スナップインの登録の詳細については、「 [Windows PowerShell プログラマーズガイド](../prog-guide/windows-powershell-programmer-s-guide.md)」の「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f78e6-135">For more information about registering snap-ins, see [How to Register Cmdlets, Providers, and Host Applications](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c) in the [Windows PowerShell Programmer's Guide](../prog-guide/windows-powershell-programmer-s-guide.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f78e6-136">参照</span><span class="sxs-lookup"><span data-stu-id="f78e6-136">See Also</span></span>

[<span data-ttu-id="f78e6-137">コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法</span><span class="sxs-lookup"><span data-stu-id="f78e6-137">How to Register Cmdlets, Providers, and Host Applications</span></span>](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="f78e6-138">Windows PowerShell Shell SDK</span><span class="sxs-lookup"><span data-stu-id="f78e6-138">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
