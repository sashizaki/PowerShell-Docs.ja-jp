---
title: オブジェクトの既定のメンバーセットの定義 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77f94326-8ffe-4d40-bd2a-b79fb0b4a4e5
caps.latest.revision: 8
ms.openlocfilehash: 2d634e7638ec0e0117d65ca0b2d08e68f0068a03
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369781"
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

次の出力は、[フォーマットリスト](/powershell/module/Microsoft.PowerShell.Utility/Format-List)コマンドレットによって返される既定のプロパティを示しています。 各プロセスオブジェクトに対して返されるのは、`Id`、`Handles`、`CPU`、および `Name` プロパティだけです。

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
