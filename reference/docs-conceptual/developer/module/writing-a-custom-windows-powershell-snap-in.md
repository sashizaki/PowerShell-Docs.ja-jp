---
ms.date: 09/13/2016
ms.topic: reference
title: カスタム Windows PowerShell スナップインを記述する
description: カスタム Windows PowerShell スナップインを記述する
ms.openlocfilehash: e79c0c3db583fa0add9287745e97958a71360592
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92659529"
---
# <a name="writing-a-custom-windows-powershell-snap-in"></a><span data-ttu-id="36b44-103">カスタム Windows PowerShell スナップインを記述する</span><span class="sxs-lookup"><span data-stu-id="36b44-103">Writing a Custom Windows PowerShell Snap-in</span></span>

<span data-ttu-id="36b44-104">この例では、特定のコマンドレットを登録する Windows PowerShell スナップインを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="36b44-104">This example shows how to write a Windows PowerShell snap-in that registers specific cmdlets.</span></span>

<span data-ttu-id="36b44-105">この種類のスナップインでは、登録するコマンドレット、プロバイダー、種類、または形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="36b44-105">With this type of snap-in, you specify which cmdlets, providers, types, or formats to register.</span></span> <span data-ttu-id="36b44-106">アセンブリ内のすべてのコマンドレットとプロバイダーを登録するスナップインを作成する方法の詳細については、「 [Windows PowerShell スナップインの作成](./writing-a-windows-powershell-snap-in.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36b44-106">For more information about how to write a snap-in that registers all the cmdlets and providers in an assembly, see [Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md).</span></span>

## <a name="to-write-a-windows-powershell-snap-in-that-registers-specific-cmdlets"></a><span data-ttu-id="36b44-107">特定のコマンドレットを登録する Windows PowerShell スナップインを作成するには</span><span class="sxs-lookup"><span data-stu-id="36b44-107">To write a Windows PowerShell Snap-in that registers specific cmdlets.</span></span>

1. <span data-ttu-id="36b44-108">Runインストーラ属性属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="36b44-108">Add the RunInstallerAttribute attribute.</span></span>
2. <span data-ttu-id="36b44-109">[Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)クラスから派生するパブリッククラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="36b44-109">Create a public class that derives from the [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) class.</span></span>

   <span data-ttu-id="36b44-110">この例では、クラス名は "CustomPSSnapinTest" です。</span><span class="sxs-lookup"><span data-stu-id="36b44-110">In this example, the class name is "CustomPSSnapinTest".</span></span>

3. <span data-ttu-id="36b44-111">スナップインの名前のパブリックプロパティを追加します (必須)。</span><span class="sxs-lookup"><span data-stu-id="36b44-111">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="36b44-112">スナップインに名前を付ける場合、 `#` 、、 `.` `,` 、、 `(` 、 `)` `{` `}` `[` `]` `&` `-` `/` `\` `$` `;` `:` `"` `'` `<` `>` `|` `?` `@` 、、、 `` ` `` 、、、、、、、、、、、、、、、、、、、、、、、、 `*`</span><span class="sxs-lookup"><span data-stu-id="36b44-112">When naming snap-ins, do not use any of the following characters: `#`, `.`, `,`, `(`, `)`, `{`, `}`, `[`, `]`, `&`, `-`, `/`, `\`, `$`, `;`, `:`, `"`, `'`, `<`, `>`, `|`, `?`, `@`, `` ` ``, `*`</span></span>

   <span data-ttu-id="36b44-113">この例では、スナップインの名前は "CustomPSSnapInTest" です。</span><span class="sxs-lookup"><span data-stu-id="36b44-113">In this example, the name of the snap-in is "CustomPSSnapInTest".</span></span>

4. <span data-ttu-id="36b44-114">スナップインのベンダのパブリックプロパティを追加します (必須)。</span><span class="sxs-lookup"><span data-stu-id="36b44-114">Add a public property for the vendor of the snap-in (required).</span></span>

   <span data-ttu-id="36b44-115">この例では、ベンダーは "Microsoft" です。</span><span class="sxs-lookup"><span data-stu-id="36b44-115">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="36b44-116">スナップインのベンダリソースのパブリックプロパティを追加します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="36b44-116">Add a public property for the vendor resource of the snap-in (optional).</span></span>

   <span data-ttu-id="36b44-117">この例では、ベンダリソースは "CustomPSSnapInTest, Microsoft" です。</span><span class="sxs-lookup"><span data-stu-id="36b44-117">In this example, the vendor resource is "CustomPSSnapInTest,Microsoft".</span></span>

6. <span data-ttu-id="36b44-118">スナップインの説明のパブリックプロパティを追加します (必須)。</span><span class="sxs-lookup"><span data-stu-id="36b44-118">Add a public property for the description of the snap-in (required).</span></span>

   <span data-ttu-id="36b44-119">この例での説明は次のとおりです。 "これは、 `Test-HelloWorld` コマンドレットとコマンドレットを含むカスタムの Windows PowerShell スナップインです `Test-CustomSnapinTest` 。"</span><span class="sxs-lookup"><span data-stu-id="36b44-119">In this example, the description is: "This is a custom Windows PowerShell snap-in that includes the `Test-HelloWorld` and `Test-CustomSnapinTest` cmdlets".</span></span>

7. <span data-ttu-id="36b44-120">スナップインの説明リソースのパブリックプロパティを追加します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="36b44-120">Add a public property for the description resource of the snap-in (optional).</span></span>

   <span data-ttu-id="36b44-121">この例では、ベンダリソースは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="36b44-121">In this example, the vendor resource is:</span></span>

   > <span data-ttu-id="36b44-122">CustomPSSnapInTest は、Test-HelloWorld と Test-CustomSnapinTest のコマンドレットを含むカスタムの Windows PowerShell スナップインです。</span><span class="sxs-lookup"><span data-stu-id="36b44-122">CustomPSSnapInTest, This is a custom Windows PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets".</span></span>

8. <span data-ttu-id="36b44-123">カスタムスナップインに属するコマンドレットを指定します (省略可能 [)。このクラスを](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) 使用してください。</span><span class="sxs-lookup"><span data-stu-id="36b44-123">Specify the cmdlets that belong to the custom snap-in (optional) using the [System.Management.Automation.Runspaces.Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) class.</span></span> <span data-ttu-id="36b44-124">ここで追加される情報には、コマンドレットの名前、.NET の種類、コマンドレットのヘルプファイル名 (コマンドレットヘルプファイル名の形式) が含まれてい `name.dll-help.xml` ます。</span><span class="sxs-lookup"><span data-stu-id="36b44-124">The information added here includes the name of the cmdlet, its .NET type, and the cmdlet Help file name (the format of the cmdlet Help file name should be `name.dll-help.xml`).</span></span>

   <span data-ttu-id="36b44-125">この例では、Test-HelloWorld と TestCustomSnapinTest コマンドレットを追加します。</span><span class="sxs-lookup"><span data-stu-id="36b44-125">This example adds the Test-HelloWorld and TestCustomSnapinTest cmdlets.</span></span>

9. <span data-ttu-id="36b44-126">カスタムスナップインに属するプロバイダーを指定します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="36b44-126">Specify the providers that belong to the custom snap-in (optional).</span></span>

   <span data-ttu-id="36b44-127">この例では、プロバイダーが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="36b44-127">This example does not specify any providers.</span></span>

10. <span data-ttu-id="36b44-128">カスタムスナップインに属する種類を指定します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="36b44-128">Specify the types that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="36b44-129">この例では、型は指定しません。</span><span class="sxs-lookup"><span data-stu-id="36b44-129">This example does not specify any types.</span></span>

11. <span data-ttu-id="36b44-130">カスタムスナップインに属する形式を指定します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="36b44-130">Specify the formats that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="36b44-131">この例では、形式は指定されていません。</span><span class="sxs-lookup"><span data-stu-id="36b44-131">This example does not specify any formats.</span></span>

## <a name="example"></a><span data-ttu-id="36b44-132">例</span><span class="sxs-lookup"><span data-stu-id="36b44-132">Example</span></span>

<span data-ttu-id="36b44-133">この例では、およびコマンドレットの登録に使用できるカスタム Windows PowerShell スナップインを記述する方法を示し `Test-HelloWorld` `Test-CustomSnapinTest` ます。</span><span class="sxs-lookup"><span data-stu-id="36b44-133">This example shows how to write a Custom Windows PowerShell snap-in that can be used to register the `Test-HelloWorld` and `Test-CustomSnapinTest` cmdlets.</span></span> <span data-ttu-id="36b44-134">この例では、完全なアセンブリに、このスナップインによって登録されない他のコマンドレットとプロバイダーが含まれている可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="36b44-134">Be aware that in this example, the complete assembly could contain other cmdlets and providers that would not be registered by this snap-in.</span></span>

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

<span data-ttu-id="36b44-135">スナップインの登録の詳細については、「 [Windows PowerShell プログラマーズガイド](../prog-guide/windows-powershell-programmer-s-guide.md)」の「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions/ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36b44-135">For more information about registering snap-ins, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85)) in the [Windows PowerShell Programmer's Guide](../prog-guide/windows-powershell-programmer-s-guide.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="36b44-136">参照</span><span class="sxs-lookup"><span data-stu-id="36b44-136">See Also</span></span>

<span data-ttu-id="36b44-137">[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions/ms714644(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="36b44-137">[How to Register Cmdlets, Providers, and Host Applications](/previous-versions/ms714644(v=vs.85))</span></span>

[<span data-ttu-id="36b44-138">Windows PowerShell シェル SDK</span><span class="sxs-lookup"><span data-stu-id="36b44-138">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
