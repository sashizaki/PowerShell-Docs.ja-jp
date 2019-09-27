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
ms.openlocfilehash: 465ab9e8fa29716ce0f46ad0dcf01d0ddd615bcd
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71322933"
---
# <a name="writing-a-windows-powershell-snap-in"></a>Windows PowerShell スナップインを記述する

この例では、すべてのコマンドレットと Windows PowerShell プロバイダーをアセンブリに登録するために使用できる Windows PowerShell スナップインを記述する方法を示します。

この種類のスナップインでは、登録するコマンドレットとプロバイダーは選択しません。 登録内容を選択できるスナップインを作成するには、「[カスタム Windows PowerShell スナップインの作成](./writing-a-custom-windows-powershell-snap-in.md)」を参照してください。

### <a name="writing-a-windows-powershell-snap-in"></a>Windows PowerShell スナップインを記述する

1. Runインストーラ属性属性を追加します。

2. [Add-pssnapin](/dotnet/api/System.Management.Automation.PSSnapIn)クラスから派生するパブリッククラスを作成します。

    この例では、クラス名は "GetProcPSSnapIn01" です。

3. スナップインの名前のパブリックプロパティを追加します (必須)。 スナップインに名前を付けるときは、次の文字を使用しないでください。 #. , () {} [] &AMP;-/\ $;: "' \< >;? @ ` *

    この例では、スナップインの名前は "GetProcPSSnapIn01" です。

4. スナップインのベンダのパブリックプロパティを追加します (必須)。

    この例では、ベンダーは "Microsoft" です。

5. スナップインのベンダリソースのパブリックプロパティを追加します (省略可能)。

    この例では、vendor リソースは "GetProcPSSnapIn01, Microsoft" です。

6. スナップインの説明のパブリックプロパティを追加します (必須)。

    この例では、説明は "This は Windows PowerShell スナップインです。これは、get proc コマンドレットを登録する" です。

7. スナップインの説明リソースのパブリックプロパティを追加します (省略可能)。

    この例では、ベンダリソースは "GetProcPSSnapIn01, This は Windows PowerShell スナップインであり、これは get proc コマンドレットを登録する" です。

## <a name="example"></a>例

この例では、windows powershell シェルで Get Proc コマンドレットを登録するために使用できる Windows PowerShell スナップインを記述する方法を示します。 この例では、完全なアセンブリには GetProcPSSnapIn01 スナップインクラスと Get Proc cmdlet クラスのみが含まれることに注意してください。

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

## <a name="see-also"></a>関連項目

[コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](https://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Windows PowerShell Shell SDK](../windows-powershell-reference.md)
