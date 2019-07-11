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
ms.openlocfilehash: af554cde5e888f2a008028010332caa473151622
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67733984"
---
# <a name="defining-default-methods-for-objects"></a>オブジェクトの既定のメソッドを定義する

.NET Framework オブジェクトを拡張するときに、オブジェクトをコード メソッドおよびスクリプト メソッドを追加できます。 これらのメソッドを定義するために使用される XML は次のセクションで説明します。

> [!NOTE]
> セクションでは、次の例は、Windows PowerShell のインストール ディレクトリに Types.ps1xml 型ファイル (`$pshome`)。

## <a name="code-methods"></a>コード メソッド

コードのメソッドは、.NET Framework オブジェクトの静的メソッドを参照します。

次の例では、 **ConvertLargeIntegerToInt64**メソッドに追加されます、 [System.Xml.Xmlnode でしょうか。Displayproperty = Fullname](/dotnet/api/System.Xml.XmlNode)型。 [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod)要素は、コードの方法として、拡張メソッドを定義します。 [名前](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name)要素は、拡張メソッドの名前を指定します。 また、 [CodeReference](/dotnet/api/system.management.automation.pscodemethod.codereference?view=pscore-6.2.0#System_Management_Automation_PSCodeMethod_CodeReference)要素は、静的メソッドを指定します。 (追加することも、 [PSCodeMethod](/dotnet/api/system.management.automation.pscodemethod)要素のメンバーに、 [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0)要素です)。

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

スクリプト メソッドでは、値が、スクリプトの出力メソッドを定義します。 次の例では、 **ConvertToDateTime**メソッドに追加されます、 [System.Management.Managementobject でしょうか。Displayproperty = Fullname](/dotnet/api/System.Management.ManagementObject)型。 [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0)要素は、スクリプト メソッドとして、拡張メソッドを定義します。 [名前](/dotnet/api/system.management.automation.psmemberinfo.name?view=pscore-6.2.0#System_Management_Automation_PSMemberInfo_Name)要素は、拡張メソッドの名前を指定します。 また、[スクリプト](/dotnet/api/system.management.automation.psscriptmethod.script?view=pscore-6.2.0#System_Management_Automation_PSScriptMethod_Script)要素は、メソッドの値を生成するスクリプトを指定します。 (追加することも、 [PSScriptMethod](/dotnet/api/system.management.automation.psscriptmethod?view=pscore-6.2.0)要素のメンバーに、 [PSMemberSets](/dotnet/api/system.management.automation.psmemberset?view=pscore-6.2.0)要素です)。

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

## <a name="see-also"></a>関連項目

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
