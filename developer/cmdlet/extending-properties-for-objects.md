---
title: オブジェクトのプロパティの拡張 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f33ff3e9-213c-44aa-92ab-09450e65c676
caps.latest.revision: 11
ms.openlocfilehash: dcab755f565cd176c85ef6b9c719bceae10301b4
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854528"
---
# <a name="extending-properties-for-objects"></a>オブジェクトのプロパティを拡張する

.NET Framework オブジェクトを拡張するときに追加できますエイリアス プロパティ、コードのプロパティ、ノート プロパティ、スクリプトのプロパティ、およびプロパティ セット オブジェクトにします。 これらのプロパティを定義するために使用される XML は次のセクションで説明します。

> [!NOTE]
> セクションでは、次の例は、Windows PowerShell のインストール ディレクトリで既定 Types.ps1xml 型ファイル (`$pshome`)。

## <a name="alias-properties"></a>エイリアスのプロパティ

エイリアスのプロパティでは、既存のプロパティの新しい名前を定義します。

次の例では、`Count`プロパティに追加されます、 [System.Array でしょうか。Displayproperty = Fullname](/dotnet/api/System.Array)型。 [AliasProperty](http://msdn.microsoft.com/en-us/b140038c-807a-4bb9-beca-332491cda1b1)要素は、エイリアス プロパティとして、拡張プロパティを定義します。 [名前](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873)要素を新しい名前を指定します。 また、 [ReferencedMemberName](http://msdn.microsoft.com/en-us/0c5db6cc-9033-4d48-88a7-76b962882f7a)要素は、別名で参照されている既存のプロパティを指定します。 (追加することも、 [AliasProperty](http://msdn.microsoft.com/en-us/d6647953-94ad-4b0b-af2e-4dda6952dee1)要素のメンバーに、[メンバー セット](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3)要素です)。

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

コードのプロパティは、.NET Framework オブジェクトの静的プロパティを参照します。

次の例では、`Node`プロパティに追加されます、 [System.IO.Directoryinfo でしょうか。Displayproperty = Fullname](/dotnet/api/System.IO.DirectoryInfo)型。 [CodeProperty](http://msdn.microsoft.com/en-us/59bc4d18-41eb-4c0d-8ad3-bbfa5dc488db)要素は、コードのプロパティとして、拡張プロパティを定義します。 [名前](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873)要素は、拡張プロパティの名前を指定します。 また、 [GetCodeReference](http://msdn.microsoft.com/en-us/62af34f5-cc22-42c0-9e0c-3bd0f5c1a4a0)要素は、拡張プロパティによって参照される静的メソッドを定義します。 (追加することも、 [CodeProperty](http://msdn.microsoft.com/en-us/59bc4d18-41eb-4c0d-8ad3-bbfa5dc488db)要素のメンバーに、[メンバー セット](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3)要素です)。

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

## <a name="note-properties"></a>ノート プロパティ

メモのプロパティでは、静的な値を持つプロパティを定義します。

次の例では、 `Status` (値は「成功」では常に) プロパティに追加されます、 [System.IO.Directoryinfo でしょうか。Displayproperty = Fullname](/dotnet/api/System.IO.DirectoryInfo)型。 [NoteProperty](http://msdn.microsoft.com/en-us/331e6c50-d703-43f0-89bc-ca9fb97800eb)要素拡張プロパティを定義します注プロパティとして、[名前](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873)要素は、拡張プロパティの名前を指定し、[値](http://msdn.microsoft.com/en-us/f3c77546-b98e-4c4e-bbe0-6dfd06696d1c)要素。拡張プロパティの静的な値を指定します。 (、 [NoteProperty](http://msdn.microsoft.com/en-us/331e6c50-d703-43f0-89bc-ca9fb97800eb)のメンバーに要素を追加することも、[メンバー セット](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3)要素です)。

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

スクリプト プロパティは、値が、スクリプトの出力のプロパティを定義します。

次の例では、`VersionInfo`プロパティに追加されます、 [System.IO.Fileinfo でしょうか。Displayproperty = Fullname](/dotnet/api/System.IO.FileInfo)型。 [ScriptProperty](http://msdn.microsoft.com/en-us/858a4247-676b-4cc9-9f3e-057109aad350)要素は、スクリプト プロパティとして、拡張プロパティを定義します。 [名前](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873)要素は、拡張プロパティの名前を指定します。 また、 [GetScriptBlock](http://msdn.microsoft.com/en-us/f3c77546-b98e-4c4e-bbe0-6dfd06696d1c)要素は、プロパティの値を生成するスクリプトを指定します。 (追加することも、 [ScriptProperty](http://msdn.microsoft.com/en-us/858a4247-676b-4cc9-9f3e-057109aad350)要素のメンバーに、[メンバー セット](http://msdn.microsoft.com/en-us/46a50fb5-e150-4c03-8584-e1b53e4d49e3)要素です)。

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

## <a name="property-sets"></a>プロパティ セット

プロパティ セットは、セットの名前で参照可能な拡張プロパティのグループを定義します。 たとえば、`Property`のパラメーター、 [Format-table](/powershell/module/Microsoft.PowerShell.Utility/Format-Table)コマンドレットは、特定のプロパティを表示する設定を指定できます。 プロパティのセットを指定すると、セットに属しているプロパティのみが表示されます。
プロパティ セットは、セットの名前で参照可能な拡張プロパティのグループを定義します。 たとえば、`Property`のパラメーター、 [Format-table](/powershell/module/Microsoft.PowerShell.Utility/Format-Table)コマンドレットは、特定のプロパティを表示する設定を指定できます。 プロパティのセットを指定すると、セットに属しているプロパティのみが表示されます。

オブジェクトに定義できるプロパティのセットの数に制限はありません。 ただし、PSStandardMembers メンバーのセット内でオブジェクトの既定の表示プロパティを定義するために使用するプロパティ セットを指定する必要があります。 DefaultDisplayProperty、DefaultDisplayPropertySet、および DefaultKeyPropertySet、Types.ps1xml の種類のファイルの既定のプロパティ セット名が含まれます。 PSStandardMembers メンバーのセットに追加するすべての追加のプロパティ セットは無視されます。

次の例では、DefaultDisplayPropertySet プロパティ セットは、PSStandardMembers メンバーのセットに追加、 [System.Serviceprocess.Servicecontroller でしょうか。Displayproperty = Fullname](/dotnet/api/System.ServiceProcess.ServiceController)型。 [PropertySet](http://msdn.microsoft.com/en-us/14cdc234-796e-4857-9b51-bdbaa1412188)要素は、プロパティのグループを定義します。 [名前](http://msdn.microsoft.com/en-us/b58e9d21-c8c9-49a5-909e-9c1cfc64f873)要素がプロパティ セットの名前を指定します。 また、 [ReferencedProperties](http://msdn.microsoft.com/en-us/5e620423-8679-4fbf-b6db-9f79288e4786)要素がセットのプロパティを指定します。 (追加することも、 [PropertySet](http://msdn.microsoft.com/en-us/14cdc234-796e-4857-9b51-bdbaa1412188)要素のメンバーに、[型](http://msdn.microsoft.com/en-us/e5dbd353-d6b2-40a1-92b6-6f1fea744ebe)要素です)。

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

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
