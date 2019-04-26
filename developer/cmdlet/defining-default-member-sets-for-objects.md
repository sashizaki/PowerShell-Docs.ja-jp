---
title: 既定のメンバーがオブジェクトの設定を定義する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77f94326-8ffe-4d40-bd2a-b79fb0b4a4e5
caps.latest.revision: 8
ms.openlocfilehash: 2d634e7638ec0e0117d65ca0b2d08e68f0068a03
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068251"
---
# <a name="defining-default-member-sets-for-objects"></a>オブジェクトの既定のメンバー セットを定義する

Windows PowerShell は PSStandardMembers メンバーのセットを使用して、オブジェクトの既定のプロパティ セットを定義します。 既定のプロパティ セットは、プロパティ セットによって定義されているプロパティのみを表示する、書式設定コマンドレットなどのコマンドで使用できます。 既定のプロパティ セットには、DefaultDisplayProperty、DefaultDisplayPropertySet、および DefaultKeyPropertySet が含まれます。 Windows PowerShell では、他のすべてのメンバー セットおよび PSStandardMembers メンバーのセットに追加されたその他のプロパティ セットは無視されます。

## <a name="member-set-for-systemdiagnosticsprocess"></a>System.Diagnostics.Process のメンバーのセット

次の例では、PSStandardMembers メンバーのセットが DefaultDisplayPropertySet プロパティのセットを定義します。 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。 このプロパティのセットを使って、 [Format-list](/powershell/module/Microsoft.PowerShell.Utility/Format-List)コマンドレット。

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

次の出力がによって返される既定のプロパティを示しています、 [Format-list](/powershell/module/Microsoft.PowerShell.Utility/Format-List)コマンドレット。 のみ、 `Id`、 `Handles`、 `CPU`、および`Name`各プロセス オブジェクトのプロパティが返されます。

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

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
