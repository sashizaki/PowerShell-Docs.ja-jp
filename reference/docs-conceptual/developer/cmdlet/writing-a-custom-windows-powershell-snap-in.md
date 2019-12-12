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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364251"
---
# <a name="writing-a-custom-windows-powershell-snap-in"></a>カスタム Windows PowerShell スナップインを記述する

この例では、特定のコマンドレットを登録する Windows PowerShell スナップインを作成する方法を示します。

この種類のスナップインでは、登録するコマンドレット、プロバイダー、種類、または形式を指定します。 アセンブリ内のすべてのコマンドレットとプロバイダーを登録するスナップインを作成する方法の詳細については、「 [Windows PowerShell スナップインの作成](./writing-a-windows-powershell-snap-in.md)」を参照してください。

## <a name="to-write-a-windows-powershell-snap-in-that-registers-specific-cmdlets"></a>特定のコマンドレットを登録する Windows PowerShell スナップインを作成するには

1. Runインストーラ属性属性を追加します。

2. [Custompssnapin](/dotnet/api/System.Management.Automation.CustomPSSnapIn)クラスから派生するパブリッククラスを作成します。

   この例では、クラス名は "CustomPSSnapinTest" です。

3. スナップインの名前のパブリックプロパティを追加します (必須)。 スナップインに名前を付けるときは、次の文字を使用しないでください。 #. , () {} [] &-/\ $;: "' \< > &#124;ですか? @ ` *

   この例では、スナップインの名前は "CustomPSSnapInTest" です。

4. スナップインのベンダのパブリックプロパティを追加します (必須)。

   この例では、ベンダーは "Microsoft" です。

5. スナップインのベンダリソースのパブリックプロパティを追加します (省略可能)。

   この例では、ベンダリソースは "CustomPSSnapInTest, Microsoft" です。

6. スナップインの説明のパブリックプロパティを追加します (必須)。

   この例での説明は次のとおりです。 "これは、テスト HelloWorld とテスト用のカスタム Windows PowerShell スナップインです。

7. スナップインの説明リソースのパブリックプロパティを追加します (省略可能)。

   この例では、仕入先リソースは "CustomPSSnapInTest です。これは、テスト HelloWorld とテスト用のカスタムの Windows PowerShell スナップインです。このスナップインには、テスト HelloWorld とテスト用のコマンドレットが含まれています。"

8. カスタムスナップインに属するコマンドレットを指定します (省略可能[)。このクラスを](/dotnet/api/System.Management.Automation.Runspaces.CmdletConfigurationEntry)使用してください。 ここで追加される情報には、コマンドレットの名前、.NET の種類、コマンドレットのヘルプファイル名が含まれています (コマンドレットヘルプファイル名の形式は dll-help)。

   この例では、テスト HelloWorld と TestCustomSnapinTest コマンドレットを追加します。

9. カスタムスナップインに属するプロバイダーを指定します (省略可能)。

   この例では、プロバイダーが指定されていません。

10. カスタムスナップインに属する種類を指定します (省略可能)。

    この例では、型は指定しません。

11. カスタムスナップインに属する形式を指定します (省略可能)。

    この例では、形式は指定されていません。

## <a name="example"></a>例

この例では、カスタム Windows PowerShell スナップインを記述して、テスト HelloWorld およびテスト用のコマンドレットの登録に使用できるようにする方法を示します。 この例では、完全なアセンブリに、このスナップインによって登録されない他のコマンドレットとプロバイダーが含まれている可能性があることに注意してください。

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

スナップインの登録の詳細については、「 [Windows PowerShell プログラマーズガイド](../prog-guide/windows-powershell-programmer-s-guide.md)」の「[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)」を参照してください。

## <a name="see-also"></a>参照

[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Windows PowerShell Shell SDK](../windows-powershell-reference.md)
