---
title: オブジェクトの既定のメソッドの定義 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53fe744a-485f-4c21-9623-1cb546372211
caps.latest.revision: 9
ms.openlocfilehash: fa0f0371856d8723af7ec17a4306de209a481a18
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068217"
---
# <a name="defining-default-methods-for-objects"></a>オブジェクトの既定のメソッドを定義する

.NET Framework オブジェクトを拡張するときに、オブジェクトをコード メソッドおよびスクリプト メソッドを追加できます。 これらのメソッドを定義するために使用される XML は次のセクションで説明します。

> [!NOTE]
> セクションでは、次の例は、Windows PowerShell のインストール ディレクトリに Types.ps1xml 型ファイル (`$pshome`)。

## <a name="code-methods"></a>コード メソッド

コードのメソッドは、.NET Framework オブジェクトの静的メソッドを参照します。

次の例では、 **ConvertLargeIntegerToInt64**メソッドに追加されます、 [System.Xml.Xmlnode でしょうか。Displayproperty = Fullname](/dotnet/api/System.Xml.XmlNode)型。 [CodeMethod](http://msdn.microsoft.com/en-us/1ea9b031-bbcf-4e35-b497-bf30fa0b1b05)要素は、コードの方法として、拡張メソッドを定義します。 [名前](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873)要素は、拡張メソッドの名前を指定します。 また、 [CodeReference](http://msdn.microsoft.com/en-us/70017b85-18d2-4f55-8357-92f309d5618b)要素は、静的メソッドを指定します。 (追加することも、 [CodeMethod](http://msdn.microsoft.com/en-us/1ea9b031-bbcf-4e35-b497-bf30fa0b1b05)要素のメンバーに、[メンバー セット](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3)要素です)。

```xml
<Type>
  <Name>System.Xml.XmlNode</Name>
  <Members>
    <CodeMethod>
      <Name>ToString</Name>
      <CodeReference>
        <TypeName>Microsoft.PowerShell.ToStringCodemethods</TypeName>
        <MethodName>XmlNode</MethodName>
      </CodeReference>
    </CodeMethod>
  </Members>
</Type>
```

## <a name="script-methods"></a>スクリプト メソッド

スクリプト メソッドでは、値が、スクリプトの出力メソッドを定義します。 次の例では、 **ConvertToDateTime**メソッドに追加されます、 [System.Management.Managementobject でしょうか。Displayproperty = Fullname](/dotnet/api/System.Management.ManagementObject)型。 [ScriptMethod](http://msdn.microsoft.com/en-us/59f8160f-bc95-42f0-92e2-b16a616bc65c)要素は、スクリプト メソッドとして、拡張メソッドを定義します。 [名前](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873)要素は、拡張メソッドの名前を指定します。 また、[スクリプト](http://msdn.microsoft.com/en-us/1937ad1b-bb2b-4512-9864-01fc0767d46f)要素は、メソッドの値を生成するスクリプトを指定します。 (追加することも、 [ScriptMethod](http://msdn.microsoft.com/en-us/59f8160f-bc95-42f0-92e2-b16a616bc65c)要素のメンバーに、[メンバー セット](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3)要素です)。

```xml
<Type>
  <Name>System.Management.ManagementObject</Name>
  <Members>
    <ScriptMethod>
      <Name>ConvertToDateTime</Name>
      <Script>
        [System.Management.ManagementDateTimeConverter]::ToDateTime($args[0])
      </Script>
    </ScriptMethod>
  </Members>
</Type>
```

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)