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
# <a name="defining-default-member-sets-for-objects"></a><span data-ttu-id="c4169-102">オブジェクトの既定のメンバー セットを定義する</span><span class="sxs-lookup"><span data-stu-id="c4169-102">Defining Default Member Sets for Objects</span></span>

<span data-ttu-id="c4169-103">Windows PowerShell は PSStandardMembers メンバーのセットを使用して、オブジェクトの既定のプロパティ セットを定義します。</span><span class="sxs-lookup"><span data-stu-id="c4169-103">The PSStandardMembers member set is used by Windows PowerShell to define the default property sets for an object.</span></span> <span data-ttu-id="c4169-104">既定のプロパティ セットは、プロパティ セットによって定義されているプロパティのみを表示する、書式設定コマンドレットなどのコマンドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="c4169-104">The default property sets can be used by commands such as the formatting cmdlets to display only those properties that are defined by the property set.</span></span> <span data-ttu-id="c4169-105">既定のプロパティ セットには、DefaultDisplayProperty、DefaultDisplayPropertySet、および DefaultKeyPropertySet が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c4169-105">The default property sets include DefaultDisplayProperty, DefaultDisplayPropertySet, and DefaultKeyPropertySet.</span></span> <span data-ttu-id="c4169-106">Windows PowerShell では、他のすべてのメンバー セットおよび PSStandardMembers メンバーのセットに追加されたその他のプロパティ セットは無視されます。</span><span class="sxs-lookup"><span data-stu-id="c4169-106">Windows PowerShell ignores all other member sets and any other property sets added to the PSStandardMembers member set.</span></span>

## <a name="member-set-for-systemdiagnosticsprocess"></a><span data-ttu-id="c4169-107">System.Diagnostics.Process のメンバーのセット</span><span class="sxs-lookup"><span data-stu-id="c4169-107">Member Set for System.Diagnostics.Process</span></span>

<span data-ttu-id="c4169-108">次の例では、PSStandardMembers メンバーのセットが DefaultDisplayPropertySet プロパティのセットを定義します。 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c4169-108">In the following example, the PSStandardMembers member set defines the DefaultDisplayPropertySet property set for [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects.</span></span> <span data-ttu-id="c4169-109">このプロパティのセットを使って、 [Format-list](/powershell/module/Microsoft.PowerShell.Utility/Format-List)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="c4169-109">This property set is used by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span>

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

<span data-ttu-id="c4169-110">次の出力がによって返される既定のプロパティを示しています、 [Format-list](/powershell/module/Microsoft.PowerShell.Utility/Format-List)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="c4169-110">The following output shows the default properties returned by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span> <span data-ttu-id="c4169-111">のみ、 `Id`、 `Handles`、 `CPU`、および`Name`各プロセス オブジェクトのプロパティが返されます。</span><span class="sxs-lookup"><span data-stu-id="c4169-111">Only the `Id`, `Handles`, `CPU`, and `Name` properties are returned for each process object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c4169-112">参照</span><span class="sxs-lookup"><span data-stu-id="c4169-112">See Also</span></span>

[<span data-ttu-id="c4169-113">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="c4169-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
