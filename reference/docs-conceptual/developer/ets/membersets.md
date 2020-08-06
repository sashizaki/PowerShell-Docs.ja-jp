---
title: 拡張型システムメンバーセット
ms.date: 07/09/2020
ms.topic: conceptual
ms.openlocfilehash: 11e1e7819efecc1f1d8164ef32fb97cda978e748
ms.sourcegitcommit: d26e2237397483c6333abcf4331bd82f2e72b4e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2020
ms.locfileid: "86217982"
---
# <a name="ets-member-sets"></a><span data-ttu-id="4e3ae-102">メンバーセットの取得</span><span class="sxs-lookup"><span data-stu-id="4e3ae-102">ETS member sets</span></span>

<span data-ttu-id="4e3ae-103">メンバーセットを使用すると、 **PSObject**オブジェクトのメンバーを2つのサブセットに分割して、サブセットのメンバーをサブセット名でまとめて参照できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-103">Member sets allow you to partition the members of the **PSObject** object into two subsets so that the members of the subsets can be referenced together by their subset name.</span></span> <span data-ttu-id="4e3ae-104">2種類のサブセットには、プロパティセットとメンバーセットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-104">The two types of subsets include property sets and member sets.</span></span> <span data-ttu-id="4e3ae-105">PowerShell がメンバーセットを使用する方法の例として、 **DefaultDisplayPropertySet**という名前の特定のプロパティセットがあります。これは、実行時に、指定された**PSObject**オブジェクトに対して表示するプロパティを決定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-105">For example of how PowerShell uses member sets, there is a specific property set named **DefaultDisplayPropertySet** that is used to determine, at runtime, which properties to display for a given **PSObject** object.</span></span>

## <a name="property-sets"></a><span data-ttu-id="4e3ae-106">プロパティ セット</span><span class="sxs-lookup"><span data-stu-id="4e3ae-106">Property Sets</span></span>

<span data-ttu-id="4e3ae-107">プロパティセットには、 **PSObject**型の任意の数のプロパティを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-107">Property sets can include any number of properties of an **PSObject** type.</span></span> <span data-ttu-id="4e3ae-108">一般に、プロパティセットは、(同じ型の) プロパティのコレクションが必要な場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-108">In general, a property set can be used whenever a collection of properties (of the same type) is needed.</span></span> <span data-ttu-id="4e3ae-109">プロパティセットは、 `PSPropertySet(System.String,System.Collections.Generic.IEnumerable{System.String})` プロパティセットの名前と参照されるプロパティの名前を指定してコンストラクターを呼び出すことによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-109">The property set is created by calling the `PSPropertySet(System.String,System.Collections.Generic.IEnumerable{System.String})` constructor with the name of the property set and the names of the referenced properties.</span></span> <span data-ttu-id="4e3ae-110">作成された**PSPropertySet**オブジェクトは、セット内のプロパティを指す別名として使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-110">The created **PSPropertySet** object can then be used as an alias that points to the properties in the set.</span></span> <span data-ttu-id="4e3ae-111">[PSPropertySet](/dotnet/api/system.management.automation.pspropertyset)クラスには、次のプロパティとメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-111">The [PSPropertySet](/dotnet/api/system.management.automation.pspropertyset) class has the following properties and methods.</span></span>

- <span data-ttu-id="4e3ae-112">**Isinstance**プロパティ: プロパティのソースを示す**ブール**値を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-112">**IsInstance** property: Gets a **Boolean** value that indicates the source of the property.</span></span>
- <span data-ttu-id="4e3ae-113">**MemberType** property: プロパティセット内のプロパティの型を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-113">**MemberType** property: Gets the type of properties in the property set.</span></span>
- <span data-ttu-id="4e3ae-114">**Name**プロパティ: プロパティセットの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-114">**Name** property: Gets the name of the property set.</span></span>
- <span data-ttu-id="4e3ae-115">**Referencedpropertynames**プロパティ: プロパティセット内のプロパティの名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-115">**ReferencedPropertyNames** property: Gets the names of the properties in the property set.</span></span>
- <span data-ttu-id="4e3ae-116">**TypeNameOfValue** property: このセットをプロパティセットとして定義する**PropertySet**列挙定数を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-116">**TypeNameOfValue** property: Gets a **PropertySet** enumeration constant that defines this set as a property set.</span></span>
- <span data-ttu-id="4e3ae-117">**Value**プロパティ: **PSPropertySet**オブジェクトを取得します。値の設定もできます。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-117">**Value** property: Gets or sets the **PSPropertySet** object.</span></span>
- <span data-ttu-id="4e3ae-118">`PSPropertySet.Copy`method: **PSPropertySet**オブジェクトの正確なコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-118">`PSPropertySet.Copy` method: Makes an exact copy of the **PSPropertySet** object.</span></span>
- <span data-ttu-id="4e3ae-119">`PSMemberSet.ToString`method: **PSPropertySet**オブジェクトを文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-119">`PSMemberSet.ToString` method: Converts the **PSPropertySet** object to a string.</span></span>

## <a name="member-sets"></a><span data-ttu-id="4e3ae-120">メンバーセット</span><span class="sxs-lookup"><span data-stu-id="4e3ae-120">Member Sets</span></span>

<span data-ttu-id="4e3ae-121">メンバーセットには、任意の型の任意の数の拡張メンバーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-121">Member sets can include any number of extended members of any type.</span></span> <span data-ttu-id="4e3ae-122">メンバーセットは、を呼び出すことによって作成されます。`PSMemberSet(System.String,System.Collections.Generic.IEnumerable{System.Management.Automation.PSMemberInfo})`</span><span class="sxs-lookup"><span data-stu-id="4e3ae-122">The member set is created by calling the `PSMemberSet(System.String,System.Collections.Generic.IEnumerable{System.Management.Automation.PSMemberInfo})`</span></span>
<span data-ttu-id="4e3ae-123">メンバーセットの名前と参照されるメンバーの名前を持つコンストラクター。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-123">constructor with the name of the member set and the names of the referenced members.</span></span> <span data-ttu-id="4e3ae-124">作成された**PSPropertySet**オブジェクトは、セット内のメンバーを指す別名として使用できます。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-124">The created **PSPropertySet** object can then be used as an alias that points to the members in the set.</span></span> <span data-ttu-id="4e3ae-125">[Psmemberset](/dotnet/api/system.management.automation.psmemberset)クラスには、次のプロパティとメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-125">The [PSMemberSet](/dotnet/api/system.management.automation.psmemberset) class has the following properties and methods.</span></span>

- <span data-ttu-id="4e3ae-126">**Isinstance**プロパティ: メンバーのソースを示す**ブール**値を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-126">**IsInstance** property: Gets a **Boolean** value that indicates the source of the member.</span></span>
- <span data-ttu-id="4e3ae-127">**Members**プロパティ: メンバーセットのすべてのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-127">**Members** property: Gets all the members of the member set.</span></span>
- <span data-ttu-id="4e3ae-128">**MemberType** property: このセットをメンバーセットとして定義**するメンバーセット列挙定数**を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-128">**MemberType** property: Gets a **MemberSet** enumeration constant that defines this set as a member set.</span></span>
- <span data-ttu-id="4e3ae-129">**メソッド**プロパティ: メンバーセットに含まれるメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-129">**Methods** property: Gets the methods included in the member set.</span></span>
- <span data-ttu-id="4e3ae-130">**Properties**プロパティ: メンバーセットに含まれるプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-130">**Properties** property: Gets the properties included in the member set.</span></span>
- <span data-ttu-id="4e3ae-131">**TypeNameOfValue** property: このセットをメンバーセットとして定義**するメンバーセット列挙定数**を取得します。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-131">**TypeNameOfValue** property: Gets a **MemberSet** enumeration constant that defines this set as a member set.</span></span>
- <span data-ttu-id="4e3ae-132">**Value**プロパティ: **psmemberset セット**オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-132">**Value** property: Gets the **PSMemberSet** object.</span></span>
- <span data-ttu-id="4e3ae-133">`PSMemberSet.Copy`method: **Psmemberset セット**オブジェクトの正確なコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-133">`PSMemberSet.Copy` method: Makes an exact copy of the **PSMemberSet** object.</span></span>
- <span data-ttu-id="4e3ae-134">`PSMemberSet.ToString`method: **Psmemberset セット**オブジェクトを文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="4e3ae-134">`PSMemberSet.ToString` method: Converts the **PSMemberSet** object to a string.</span></span>