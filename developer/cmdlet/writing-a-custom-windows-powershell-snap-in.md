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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067027"
---
# <a name="writing-a-custom-windows-powershell-snap-in"></a>カスタム Windows PowerShell スナップインを記述する

この例では、特定のコマンドレットを登録する Windows PowerShell スナップインを記述する方法を示します。

この種類のスナップインでは、登録するどのコマンドレット、プロバイダー、型、または形式を指定します。 アセンブリ内のすべてのコマンドレットとプロバイダーを登録するスナップインを作成する方法の詳細については、次を参照してください。 [、Windows PowerShell スナップインの書き込み](./writing-a-windows-powershell-snap-in.md)します。

## <a name="to-write-a-windows-powershell-snap-in-that-registers-specific-cmdlets"></a>Windows PowerShell スナップインの記述には、特定のコマンドレットを登録します。

1. RunInstallerAttribute 属性を追加します。

2. 派生するパブリック クラスを作成、 [System.Management.Automation.Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)クラス。

   この例では、クラス名は"CustomPSSnapinTest"が。

3. (必須) スナップインの名前のパブリック プロパティを追加します。 スナップインの名前を付けるときは使用しないで、次の文字。 #40 です。 , ( ) { } [ ] & - /\ $ ; : " ' \< > &#124; ? @ ` *

   この例で、スナップインの名前は"CustomPSSnapInTest"です。

4. (必須) スナップインの仕入先のパブリック プロパティを追加します。

   この例では、仕入先は"Microsoft"です。

5. スナップインが (省略可能) の仕入先のリソースのパブリック プロパティを追加します。

   この例では、仕入先のリソースは、"CustomPSSnapInTest、Microsoft"が。

6. (必須) スナップインの説明については、パブリック プロパティを追加します。

   この例では、説明。"This is テスト HelloWorld とテスト CustomSnapinTest コマンドレットが含まれるカスタムの Windows PowerShell スナップイン"。

7. スナップインが (省略可能) の説明のリソースのパブリック プロパティを追加します。

   この例では、仕入先のリソースは「CustomPSSnapInTest、これが、テスト HelloWorld とテスト CustomSnapinTest コマンドレットを含むカスタムの Windows PowerShell スナップイン」。

8. カスタム スナップイン (省略可能) を使用して、属しているコマンドレットの指定、 [System.Management.Automation.Runspaces.Cmdletconfigurationentry](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry)クラス。 ここで追加情報には、コマンドレット、その .NET 型およびコマンドレットのヘルプ ファイル名 (コマンドレット ヘルプ ファイル名の形式は name.dll help.xml をする必要があります) の名前が含まれます。

   この例では、テスト HelloWorld と TestCustomSnapinTest コマンドレットを追加します。

9. カスタム スナップイン (省略可能) に属しているプロバイダーを指定します。

   この例では、すべてのプロバイダーは指定しません。

10. カスタム スナップイン (省略可能) に属する型を指定します。

    この例では、任意の型は指定しません。

11. カスタム スナップイン (省略可能) に属している形式を指定します。

    この例では、すべての形式は指定しません。

## <a name="example"></a>例

この例では、テスト HelloWorld とテスト CustomSnapinTest コマンドレットを登録するために使用できるカスタム Windows PowerShell スナップインを記述する方法を示します。 その他のコマンドレットとは、このスナップインで登録されていないプロバイダーでこの例では、アセンブリの完全でした格納ことに注意します。

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

スナップインの登録の詳細については、次を参照してください。[登録コマンドレット、プロバイダー、およびアプリケーションをホストする方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)で、 [Windows PowerShell プログラマー ガイド](../prog-guide/windows-powershell-programmer-s-guide.md)します。

## <a name="see-also"></a>参照

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Windows PowerShell シェル SDK](../windows-powershell-reference.md)
