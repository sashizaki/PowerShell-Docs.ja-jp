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
ms.openlocfilehash: 0c99f4bcfe5e2d34d31714dc85a53b5e8abe0925
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62066959"
---
# <a name="writing-a-windows-powershell-snap-in"></a>Windows PowerShell スナップインを記述する

この例では、アセンブリ内のすべてのコマンドレットと Windows PowerShell プロバイダーの登録に使用できる Windows PowerShell スナップインを記述する方法を示します。

この種類のスナップインでは、どのコマンドレットとプロバイダーを登録するを選択しません。 登録されているかを選択できるように、スナップインを作成するを参照してください。[カスタム Windows PowerShell スナップインの書き込み](./writing-a-custom-windows-powershell-snap-in.md)します。

### <a name="writing-a-windows-powershell-snap-in"></a>Windows PowerShell スナップインを記述する

1. RunInstallerAttribute 属性を追加します。

2. 派生するパブリック クラスを作成、 [System.Management.Automation.PSSnapIn](/dotnet/api/System.Management.Automation.PSSnapIn)クラス。

    この例では、クラス名は"GetProcPSSnapIn01"が。

3. (必須) スナップインの名前のパブリック プロパティを追加します。 スナップインの名前を付けるときは使用しないで、次の文字: # . , ( ) { } [ ] & - /\ $ ; : " ' \< > ; ? @ ` *

    この例で、スナップインの名前は"GetProcPSSnapIn01"です。

4. (必須) スナップインの仕入先のパブリック プロパティを追加します。

    この例では、仕入先は"Microsoft"です。

5. スナップインが (省略可能) の仕入先のリソースのパブリック プロパティを追加します。

    この例では、仕入先のリソースは、"GetProcPSSnapIn01、Microsoft"が。

6. (必須) スナップインの説明については、パブリック プロパティを追加します。

    この例で、説明は、「これは get-proc コマンドレットを登録する Windows PowerShell スナップインが」。

7. スナップインが (省略可能) の説明のリソースのパブリック プロパティを追加します。

    この例では、仕入先のリソースは「GetProcPSSnapIn01、これが get-proc コマンドレットを登録する Windows PowerShell スナップイン」。

## <a name="example"></a>例

この例では、Windows PowerShell シェルに Get-proc コマンドレットを登録するのに使用できる Windows PowerShell スナップインを記述する方法を示します。 のみ、GetProcPSSnapIn01 スナップイン クラスと、Get-proc コマンドレット クラスでこの例では、アセンブリの完全は含めること注意してください。

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

## <a name="see-also"></a>参照

[登録のコマンドレット、プロバイダー、およびアプリケーションをホストする方法](http://msdn.microsoft.com/en-us/a41e9054-29c8-40ab-bf2b-8ce4e7ec1c8c)

[Windows PowerShell シェル SDK](../windows-powershell-reference.md)
