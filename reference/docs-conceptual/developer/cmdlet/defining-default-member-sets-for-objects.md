---
title: オブジェクトの既定のメンバーセットの定義 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 80e1f54890d3aac1702414699ead16fcf38271e1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774628"
---
# <a name="defining-default-member-sets-for-objects"></a>オブジェクトの既定のメンバー セットを定義する

PSStandardMembers メンバーセットは、オブジェクトの既定のプロパティセットを定義するために Windows PowerShell によって使用されます。 既定のプロパティセットは、プロパティセットで定義されているプロパティのみを表示するために、書式設定コマンドレットなどのコマンドで使用できます。 既定のプロパティセットには、DefaultDisplayProperty、DefaultDisplayPropertySet、および DefaultKeyPropertySet が含まれます。 Windows PowerShell は、PSStandardMembers メンバーセットに追加された他のすべてのメンバーセットとその他のプロパティセットを無視します。

## <a name="member-set-for-systemdiagnosticsprocess"></a>System. Diagnostics. プロセスのメンバーセット

次の例では、PSStandardMembers メンバーセットに[よって、DefaultDisplayPropertySet オブジェクトに](/dotnet/api/System.Diagnostics.Process)対して設定されたプロパティが定義されています。 このプロパティセットは、[フォーマットリスト](/powershell/module/Microsoft.PowerShell.Utility/Format-List)コマンドレットによって使用されます。

```xml
<Type>
  <Name>System.Diagnostics.Process</Name>
  <Members>
    <MemberSet>
     <Name>PSStandardMembers</Name>
     <Members>
       <PropertySet>
         <Name>DefaultDisplayPropertySet</Name>
         <ReferencedProperties>
           <Name>Id</Name>
           <Name>Handles</Name>
           <Name>CPU</Name>
           <Name>Name</Name>
         </ReferencedProperties>
      </PropertySet>
    </Members>
  </MemberSet>
```

次の出力は、[フォーマットリスト](/powershell/module/Microsoft.PowerShell.Utility/Format-List)コマンドレットによって返される既定のプロパティを示しています。 `Id`各プロセスオブジェクトに対して返されるのは、、、 `Handles` `CPU` 、およびの `Name` 各プロパティだけです。

```powershell
Get-Process | format-list
```

```output
Id      : 2036
Handles : 27
CPU     :
Name    : AEADISRV

Id      : 272
Handles : 38
CPU     :
Name    : agrsmsvc
...
```

## <a name="see-also"></a>参照

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
