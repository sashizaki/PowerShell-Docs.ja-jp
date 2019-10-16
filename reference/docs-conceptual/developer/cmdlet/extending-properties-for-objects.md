---
title: オブジェクトのプロパティの拡張 |Microsoft Docs
ms.custom: ''
ms.date: 08/21/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f33ff3e9-213c-44aa-92ab-09450e65c676
caps.latest.revision: 11
ms.openlocfilehash: 3b14007384cca0d0cfa35655aee437adf73b1ff0
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364451"
---
# <a name="extending-properties-for-objects"></a>オブジェクトのプロパティを拡張する

.NET Framework オブジェクトを拡張すると、エイリアスプロパティ、コードプロパティ、メモプロパティ、スクリプトプロパティ、およびプロパティセットをオブジェクトに追加できます。 以下のセクションでは、これらのプロパティを定義する XML について説明します。

> [!NOTE]
> 次のセクションの例は、PowerShell インストールディレクトリ (`$PSHOME`) の既定の `Types.ps1xml` 種類のファイルに含まれています。 詳細については、「 [types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)」を参照してください。

## <a name="alias-properties"></a>エイリアスのプロパティ

エイリアスプロパティは、既存のプロパティの新しい名前を定義します。

次の例では、 **Count**プロパティが[system.string 型に](/dotnet/api/System.Array)追加されています。 Alias[プロパティ](/dotnet/api/system.management.automation.psaliasproperty)要素は、拡張プロパティを別名プロパティとして定義します。 [Name](/dotnet/api/system.management.automation.psmemberinfo.name)要素は、新しい名前を指定します。 また、 [Referencedmembername](/dotnet/api/system.management.automation.psaliasproperty.referencedmembername)要素は、エイリアスによって参照される既存のプロパティを指定します。 @No__t-0 要素[を、メンバーセット要素の](/dotnet/api/system.management.automation.psmemberset)メンバーに追加することもできます。

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>Length</ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>
```

## <a name="code-properties"></a>コードのプロパティ

コードプロパティは、.NET Framework オブジェクトの静的プロパティを参照します。

次の例では、 **Mode**プロパティが[DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo)型に追加されています。 [Codeproperty](/dotnet/api/system.management.automation.pscodeproperty)要素は、拡張プロパティをコードプロパティとして定義します。 [Name](/dotnet/api/system.management.automation.psmemberinfo.name)要素は、拡張プロパティの名前を指定します。 また、 [Getcodereference 参照](/dotnet/api/system.management.automation.pscodeproperty.gettercodereference)要素は、拡張プロパティによって参照される静的メソッドを定義します。 @No__t-0 要素[を、メンバーセット要素の](/dotnet/api/system.management.automation.psmemberset)メンバーに追加することもできます。

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <CodeProperty>
      <Name>Mode</Name>
      <GetCodeReference>
        <TypeName>Microsoft.PowerShell.Commands.FileSystemProvider</TypeName>
        <MethodName>Mode</MethodName>
      </GetCodeReference>
    </CodeProperty>
  </Members>
</Type>
```

## <a name="note-properties"></a>メモのプロパティ

Note プロパティは、静的な値を持つプロパティを定義します。

次の例では、 **Status**プロパティの値が常に**Success**であるが、 [DirectoryInfo](/dotnet/api/System.IO.DirectoryInfo)型に追加されています。 Note[プロパティ要素は、拡張](/dotnet/api/system.management.automation.psnoteproperty)プロパティを note プロパティとして定義します。 [Name](/dotnet/api/system.management.automation.psmemberinfo.name)要素は、拡張プロパティの名前を指定します。 [Value](/dotnet/api/system.management.automation.psnoteproperty.value)要素は、拡張プロパティの静的な値を指定します。 @No__t-0 要素[は、メンバー](/dotnet/api/system.management.automation.psmemberset)メンバーに追加することもできます。

```xml
<Type>
  <Name>System.IO.DirectoryInfo</Name>
  <Members>
    <NoteProperty>
      <Name>Status</Name>
      <Value>Success</Value>
    </NoteProperty>
  </Members>
</Type>
```

## <a name="script-properties"></a>スクリプトのプロパティ

スクリプトプロパティは、スクリプトの出力を値として持つプロパティを定義します。

次の例では、 **VersionInfo**プロパティ[が、system.string 型に](/dotnet/api/System.IO.FileInfo)追加されます。 [Scriptproperty](/dotnet/api/system.management.automation.psscriptproperty)要素は、拡張プロパティをスクリプトプロパティとして定義します。 [Name](/dotnet/api/system.management.automation.psmemberinfo.name)要素は、拡張プロパティの名前を指定します。 また、 [Getscriptblock](/dotnet/api/system.management.automation.psscriptproperty.getterscript)要素は、プロパティ値を生成するスクリプトを指定します。 @No__t-0 要素[を、メンバーセット要素の](/dotnet/api/system.management.automation.psmemberset)メンバーに追加することもできます。

```xml
<Type>
  <Name>System.IO.FileInfo</Name>
  <Members>
    <ScriptProperty>
      <Name>VersionInfo</Name>
      <GetScriptBlock>
        [System.Diagnostics.FileVersionInfo]::GetVersionInfo($this.FullName)
      </GetScriptBlock>
    </ScriptProperty>
  </Members>
</Type>
```

## <a name="property-sets"></a>プロパティセット

プロパティセットは、セットの名前で参照できる拡張プロパティのグループを定義します。
たとえば、[表形式](/powershell/module/Microsoft.PowerShell.Utility/Format-Table)の 
**プロパティ**パラメーターには、表示する特定のプロパティセットを指定できます。 プロパティセットを指定すると、そのセットに属するプロパティだけが表示されます。

オブジェクトに対して定義できるプロパティセットの数に制限はありません。 ただし、オブジェクトの既定の表示プロパティを定義するために使用されるプロパティセットは、 **Psstandardmembers**メンバーセット内で指定する必要があります。 @No__t-0 の種類のファイルでは、既定のプロパティセット名に**Defaultdisplayproperty**、 **DefaultDisplayPropertySet**、および**DefaultKeyPropertySet**が含まれます。 **Psstandardmembers**メンバーセットに追加した追加のプロパティセットはすべて無視されます。

次の例では、 **DefaultDisplayPropertySet**プロパティセットが[Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)型の**psstandardmembers**メンバーセットに追加されます。 [PropertySet](/dotnet/api/system.management.automation.pspropertyset)要素は、プロパティのグループを定義します。 [Name](/dotnet/api/system.management.automation.psmemberinfo.name)要素は、プロパティセットの名前を指定します。 また、 [Referencedproperties](/dotnet/api/system.management.automation.pspropertyset.referencedpropertynames)要素は、セットのプロパティを指定します。 @No__t-0 要素を[Type](/dotnet/api/system.management.automation.pstypename)要素のメンバーに追加することもできます。

```xml
<Type>
  <Name>System.ServiceProcess.ServiceController</Name>
  <Members>
    <MemberSet>
      <Name>PSStandardMembers</Name>
      <Members>
        <PropertySet>
           <Name>DefaultDisplayPropertySet</Name>
           <ReferencedProperties>
            <Name>Status</Name
            <Name>Name</Name>
            <Name>DisplayName</Name>
          </ReferencedProperties>
        </PropertySet>
      </Members>
    </MemberSet>
  </Members>
</Type>
```

## <a name="see-also"></a>「

[型について types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)

[システムの管理](/dotnet/api/System.Management.Automation)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
