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
# <a name="defining-default-member-sets-for-objects"></a><span data-ttu-id="9c25b-102">オブジェクトの既定のメンバー セットを定義する</span><span class="sxs-lookup"><span data-stu-id="9c25b-102">Defining Default Member Sets for Objects</span></span>

<span data-ttu-id="9c25b-103">PSStandardMembers メンバーセットは、オブジェクトの既定のプロパティセットを定義するために Windows PowerShell によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="9c25b-103">The PSStandardMembers member set is used by Windows PowerShell to define the default property sets for an object.</span></span> <span data-ttu-id="9c25b-104">既定のプロパティセットは、プロパティセットで定義されているプロパティのみを表示するために、書式設定コマンドレットなどのコマンドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="9c25b-104">The default property sets can be used by commands such as the formatting cmdlets to display only those properties that are defined by the property set.</span></span> <span data-ttu-id="9c25b-105">既定のプロパティセットには、DefaultDisplayProperty、DefaultDisplayPropertySet、および DefaultKeyPropertySet が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9c25b-105">The default property sets include DefaultDisplayProperty, DefaultDisplayPropertySet, and DefaultKeyPropertySet.</span></span> <span data-ttu-id="9c25b-106">Windows PowerShell は、PSStandardMembers メンバーセットに追加された他のすべてのメンバーセットとその他のプロパティセットを無視します。</span><span class="sxs-lookup"><span data-stu-id="9c25b-106">Windows PowerShell ignores all other member sets and any other property sets added to the PSStandardMembers member set.</span></span>

## <a name="member-set-for-systemdiagnosticsprocess"></a><span data-ttu-id="9c25b-107">System. Diagnostics. プロセスのメンバーセット</span><span class="sxs-lookup"><span data-stu-id="9c25b-107">Member Set for System.Diagnostics.Process</span></span>

<span data-ttu-id="9c25b-108">次の例では、PSStandardMembers メンバーセットに[よって、DefaultDisplayPropertySet オブジェクトに](/dotnet/api/System.Diagnostics.Process)対して設定されたプロパティが定義されています。</span><span class="sxs-lookup"><span data-stu-id="9c25b-108">In the following example, the PSStandardMembers member set defines the DefaultDisplayPropertySet property set for [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) objects.</span></span> <span data-ttu-id="9c25b-109">このプロパティセットは、[フォーマットリスト](/powershell/module/Microsoft.PowerShell.Utility/Format-List)コマンドレットによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="9c25b-109">This property set is used by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span>

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

<span data-ttu-id="9c25b-110">次の出力は、[フォーマットリスト](/powershell/module/Microsoft.PowerShell.Utility/Format-List)コマンドレットによって返される既定のプロパティを示しています。</span><span class="sxs-lookup"><span data-stu-id="9c25b-110">The following output shows the default properties returned by the [Format-List](/powershell/module/Microsoft.PowerShell.Utility/Format-List) cmdlet.</span></span> <span data-ttu-id="9c25b-111">`Id`各プロセスオブジェクトに対して返されるのは、、、 `Handles` `CPU` 、およびの `Name` 各プロパティだけです。</span><span class="sxs-lookup"><span data-stu-id="9c25b-111">Only the `Id`, `Handles`, `CPU`, and `Name` properties are returned for each process object.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="9c25b-112">参照</span><span class="sxs-lookup"><span data-stu-id="9c25b-112">See Also</span></span>

[<span data-ttu-id="9c25b-113">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="9c25b-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
