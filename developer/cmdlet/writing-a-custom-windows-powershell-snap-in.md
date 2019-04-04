---
title: カスタム Windows PowerShell スナップインの書き込み |Microsoft Docs
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
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57795591"
---
# <a name="writing-a-custom-windows-powershell-snap-in"></a><span data-ttu-id="17e09-102">カスタム Windows PowerShell スナップインを記述する</span><span class="sxs-lookup"><span data-stu-id="17e09-102">Writing a Custom Windows PowerShell Snap-in</span></span>

<span data-ttu-id="17e09-103">この例では、特定のコマンドレットを登録する Windows PowerShell スナップインを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="17e09-103">This example shows how to write a Windows PowerShell snap-in that registers specific cmdlets.</span></span>

<span data-ttu-id="17e09-104">この種類のスナップインでは、登録するどのコマンドレット、プロバイダー、型、または形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="17e09-104">With this type of snap-in, you specify which cmdlets, providers, types, or formats to register.</span></span> <span data-ttu-id="17e09-105">アセンブリ内のすべてのコマンドレットとプロバイダーを登録するスナップインを作成する方法の詳細については、[、Windows PowerShell スナップインの書き込み](./writing-a-windows-powershell-snap-in.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17e09-105">For more information about how to write a snap-in that registers all the cmdlets and providers in an assembly, see [Writing a Windows PowerShell Snap-in](./writing-a-windows-powershell-snap-in.md).</span></span>

## <a name="to-write-a-windows-powershell-snap-in-that-registers-specific-cmdlets"></a><span data-ttu-id="17e09-106">Windows PowerShell スナップインの記述には、特定のコマンドレットを登録します。</span><span class="sxs-lookup"><span data-stu-id="17e09-106">To write a Windows PowerShell Snap-in that registers specific cmdlets.</span></span>

1. <span data-ttu-id="17e09-107">RunInstallerAttribute 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="17e09-107">Add the RunInstallerAttribute attribute.</span></span>

2. <span data-ttu-id="17e09-108">派生するパブリック クラスを作成、 [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)クラス。</span><span class="sxs-lookup"><span data-stu-id="17e09-108">Create a public class that derives from the [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn) class.</span></span>

   <span data-ttu-id="17e09-109">この例では、クラス名は"CustomPSSnapinTest"が。</span><span class="sxs-lookup"><span data-stu-id="17e09-109">In this example, the class name is "CustomPSSnapinTest".</span></span>

3. <span data-ttu-id="17e09-110">(必須) スナップインの名前のパブリック プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="17e09-110">Add a public property for the name of the snap-in (required).</span></span> <span data-ttu-id="17e09-111">スナップインの名前を付けるときは使用しないで、次の文字。 #40 です。</span><span class="sxs-lookup"><span data-stu-id="17e09-111">When naming snap-ins, do not use any of the following characters: # .</span></span> <span data-ttu-id="17e09-112">, ( ) { } [ ] & - /\ $ ; : " ' \< > &#124; ?</span><span class="sxs-lookup"><span data-stu-id="17e09-112">, ( ) { } [ ] & - /\ $ ; : " ' \< > &#124; ?</span></span> <span data-ttu-id="17e09-113">@ \` \*</span><span class="sxs-lookup"><span data-stu-id="17e09-113">@ \` \*</span></span>

   <span data-ttu-id="17e09-114">この例で、スナップインの名前は"CustomPSSnapInTest"です。</span><span class="sxs-lookup"><span data-stu-id="17e09-114">In this example, the name of the snap-in is "CustomPSSnapInTest".</span></span>

4. <span data-ttu-id="17e09-115">(必須) スナップインの仕入先のパブリック プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="17e09-115">Add a public property for the vendor of the snap-in (required).</span></span>

   <span data-ttu-id="17e09-116">この例では、仕入先は"Microsoft"です。</span><span class="sxs-lookup"><span data-stu-id="17e09-116">In this example, the vendor is "Microsoft".</span></span>

5. <span data-ttu-id="17e09-117">スナップインが (省略可能) の仕入先のリソースのパブリック プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="17e09-117">Add a public property for the vendor resource of the snap-in (optional).</span></span>

   <span data-ttu-id="17e09-118">この例では、仕入先のリソースは、"CustomPSSnapInTest、Microsoft"が。</span><span class="sxs-lookup"><span data-stu-id="17e09-118">In this example, the vendor resource is "CustomPSSnapInTest,Microsoft".</span></span>

6. <span data-ttu-id="17e09-119">(必須) スナップインの説明については、パブリック プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="17e09-119">Add a public property for the description of the snap-in (required).</span></span>

   <span data-ttu-id="17e09-120">この例では、説明。"This is テスト HelloWorld とテスト CustomSnapinTest コマンドレットが含まれるカスタムの Windows PowerShell スナップイン"。</span><span class="sxs-lookup"><span data-stu-id="17e09-120">In this example, the description is: "This is a custom Windows PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets".</span></span>

7. <span data-ttu-id="17e09-121">スナップインが (省略可能) の説明のリソースのパブリック プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="17e09-121">Add a public property for the description resource of the snap-in (optional).</span></span>

   <span data-ttu-id="17e09-122">この例では、仕入先のリソースは「CustomPSSnapInTest、これが、テスト HelloWorld とテスト CustomSnapinTest コマンドレットを含むカスタムの Windows PowerShell スナップイン」。</span><span class="sxs-lookup"><span data-stu-id="17e09-122">In this example, the vendor resource is "CustomPSSnapInTest, This is a custom Windows PowerShell snap-in that includes the Test-HelloWorld and Test-CustomSnapinTest cmdlets".</span></span>

8. <span data-ttu-id="17e09-123">カスタム スナップイン (省略可能) を使用して、属しているコマンドレットの指定、 [System.Management.Automation.Runspaces.Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry)クラス。</span><span class="sxs-lookup"><span data-stu-id="17e09-123">Specify the cmdlets that belong to the custom snap-in (optional) using the [System.Management.Automation.Runspaces.Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry) class.</span></span> <span data-ttu-id="17e09-124">ここで追加情報には、コマンドレット、その .NET 型およびコマンドレットのヘルプ ファイル名 (コマンドレット ヘルプ ファイル名の形式は name.dll help.xml をする必要があります) の名前が含まれます。</span><span class="sxs-lookup"><span data-stu-id="17e09-124">The information added here includes the name of the cmdlet, its .NET type, and the cmdlet Help file name (the format of the cmdlet Help file name should be name.dll-help.xml).</span></span>

   <span data-ttu-id="17e09-125">この例では、テスト HelloWorld と TestCustomSnapinTest コマンドレットを追加します。</span><span class="sxs-lookup"><span data-stu-id="17e09-125">This example adds the Test-HelloWorld and TestCustomSnapinTest cmdlets.</span></span>

9. <span data-ttu-id="17e09-126">カスタム スナップイン (省略可能) に属しているプロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="17e09-126">Specify the providers that belong to the custom snap-in (optional).</span></span>

   <span data-ttu-id="17e09-127">この例では、すべてのプロバイダーは指定しません。</span><span class="sxs-lookup"><span data-stu-id="17e09-127">This example does not specify any providers.</span></span>

10. <span data-ttu-id="17e09-128">カスタム スナップイン (省略可能) に属する型を指定します。</span><span class="sxs-lookup"><span data-stu-id="17e09-128">Specify the types that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="17e09-129">この例では、任意の型は指定しません。</span><span class="sxs-lookup"><span data-stu-id="17e09-129">This example does not specify any types.</span></span>

11. <span data-ttu-id="17e09-130">カスタム スナップイン (省略可能) に属している形式を指定します。</span><span class="sxs-lookup"><span data-stu-id="17e09-130">Specify the formats that belong to the custom snap-in (optional).</span></span>

    <span data-ttu-id="17e09-131">この例では、すべての形式は指定しません。</span><span class="sxs-lookup"><span data-stu-id="17e09-131">This example does not specify any formats.</span></span>

## <a name="example"></a><span data-ttu-id="17e09-132">例</span><span class="sxs-lookup"><span data-stu-id="17e09-132">Example</span></span>

<span data-ttu-id="17e09-133">この例では、テスト HelloWorld とテスト CustomSnapinTest コマンドレットを登録するために使用できるカスタム Windows PowerShell スナップインを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="17e09-133">This example shows how to write a Custom Windows PowerShell snap-in that can be used to register the Test-HelloWorld and Test-CustomSnapinTest cmdlets.</span></span> <span data-ttu-id="17e09-134">その他のコマンドレットとは、このスナップインで登録されていないプロバイダーでこの例では、アセンブリの完全でした格納ことに注意します。</span><span class="sxs-lookup"><span data-stu-id="17e09-134">Be aware that in this example, the complete assembly could contain other cmdlets and providers that would not be registered by this snap-in.</span></span>

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

<span data-ttu-id="17e09-135">スナップインの登録の詳細については、[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)で、 [Windows PowerShell プログラマー ガイド](../prog-guide/windows-powershell-programmer-s-guide.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17e09-135">For more information about registering snap-ins, see [How to Register Cmdlets, Providers, and Host Applications](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c) in the [Windows PowerShell Programmer's Guide](../prog-guide/windows-powershell-programmer-s-guide.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="17e09-136">参照</span><span class="sxs-lookup"><span data-stu-id="17e09-136">See Also</span></span>

[<span data-ttu-id="17e09-137">登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法</span><span class="sxs-lookup"><span data-stu-id="17e09-137">How to Register Cmdlets, Providers, and Host Applications</span></span>](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[<span data-ttu-id="17e09-138">Windows PowerShell シェル SDK</span><span class="sxs-lookup"><span data-stu-id="17e09-138">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
