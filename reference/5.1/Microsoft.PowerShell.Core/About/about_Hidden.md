---
description: 既定の Get-Member 結果からクラスメンバーを非表示にする Hidden キーワードについて説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/04/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_hidden?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Hidden
ms.openlocfilehash: 641ebdc942186db90a23f4c784a0f1b3c295cae9
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224968"
---
# <a name="about_hidden"></a><span data-ttu-id="f04b5-104">about_Hidden</span><span class="sxs-lookup"><span data-stu-id="f04b5-104">about_Hidden</span></span>

## <a name="short-description"></a><span data-ttu-id="f04b5-105">概要</span><span class="sxs-lookup"><span data-stu-id="f04b5-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="f04b5-106">既定の Get-Member 結果からクラスメンバーを非表示にする Hidden キーワードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f04b5-106">Describes the Hidden keyword, which hides class members from default Get-Member results.</span></span>

## <a name="long-description"></a><span data-ttu-id="f04b5-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="f04b5-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="f04b5-108">スクリプトで Hidden キーワードを使用すると、既定でクラスのメンバーが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="f04b5-108">When you use the Hidden keyword in a script, you hide the members of a class by default.</span></span> <span data-ttu-id="f04b5-109">Hidden キーワードを使用すると、プロパティ、メソッド (コンストラクター、イベント、エイリアスプロパティ、およびその他のメンバーの種類 (静的メンバーを含む)、Get-Member コマンドレットの既定の結果、IntelliSense とタブ補完の結果から、非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f04b5-109">The Hidden keyword can hide properties, methods (including constructors, events, alias properties, and other member types, including static members, from the default results of the Get-Member cmdlet, and from IntelliSense and tab completion results.</span></span> <span data-ttu-id="f04b5-110">Hidden キーワードを使用して非表示にしたメンバーを表示するには、Get-Member コマンドに-Force パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="f04b5-110">To display members that you have hidden with the Hidden keyword, add the -Force parameter to a Get-Member command.</span></span>

<span data-ttu-id="f04b5-111">非表示のメンバーは、非表示のメンバーを定義するクラスで完了が発生しない限り、タブ補完や IntelliSense を使用して表示されることはありません。</span><span class="sxs-lookup"><span data-stu-id="f04b5-111">Hidden members are not displayed by using tab completion or IntelliSense, unless the completion occurs in the class that defines the hidden member.</span></span>

<span data-ttu-id="f04b5-112">新しい属性 System.management.automation.hiddenattribute が追加され、C \# コードが PowerShell 内で同じセマンティクスを持つことができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f04b5-112">A new attribute, System.Management.Automation.HiddenAttribute, has been added, so that C\# code can have the same semantics within PowerShell.</span></span>

<span data-ttu-id="f04b5-113">Hidden キーワードは、クラス内のプロパティとメソッドを作成する場合に便利です。このクラスは、クラスの他のユーザーに対しては必ずしも必要ではなく、すぐに編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="f04b5-113">The Hidden keyword is useful for creating properties and methods within a class that you do not necessarily want other users of the class to see, or readily be able to edit.</span></span>

<span data-ttu-id="f04b5-114">Hidden キーワードは、クラスのメンバーを表示または変更する方法には影響しません。</span><span class="sxs-lookup"><span data-stu-id="f04b5-114">The Hidden keyword has no effect on how you can view or make changes to members of a class.</span></span> <span data-ttu-id="f04b5-115">PowerShell のすべての言語キーワードと同様に、Hidden では大文字と小文字が区別されず、非表示のメンバーもパブリックになります。</span><span class="sxs-lookup"><span data-stu-id="f04b5-115">Like all language keywords in PowerShell, Hidden is not case-sensitive, and hidden members are still public.</span></span>

<span data-ttu-id="f04b5-116">Hidden はカスタムクラスと共に PowerShell 5.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="f04b5-116">Hidden, along with custom classes, was introduced in PowerShell 5.0.</span></span>

## <a name="example"></a><span data-ttu-id="f04b5-117">例</span><span class="sxs-lookup"><span data-stu-id="f04b5-117">EXAMPLE</span></span>

<span data-ttu-id="f04b5-118">次の例では、クラス定義で Hidden キーワードを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f04b5-118">The following example shows how to use the Hidden keyword in a class definition.</span></span> <span data-ttu-id="f04b5-119">Car クラスメソッドドライブには、表示または変更する必要のないプロパティがあります (車のクラスでそのドライブが呼び出された回数、クラスのユーザーにとって重要ではないメトリック)。たとえば、車を購入するときに、車が撮影されたドライブの数について販売者に依頼することはできません。</span><span class="sxs-lookup"><span data-stu-id="f04b5-119">The Car class method, Drive, has a property, rides, that does not need to be viewed or changed (it merely tallies the number of times that Drive is called on the Car class, a metric that is not important to users of the class; consider, for example, that when you are buying a car, you do not ask the seller on how many drives the car has been taken.</span></span>

<span data-ttu-id="f04b5-120">クラスのユーザーがこのプロパティを変更する必要はほとんどないため、Hidden キーワードを使用して、Get-Member およびオートコンプリートの結果からプロパティを非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="f04b5-120">Because there is little need for users of the class to change this property, we can hide the property from Get-Member and automatic completion results by using the Hidden keyword.</span></span>

<span data-ttu-id="f04b5-121">Hidden キーワードを、プロパティとそのデータ型と同じステートメント行に入力して追加します。</span><span class="sxs-lookup"><span data-stu-id="f04b5-121">Add the Hidden keyword by entering it on the same statement line as the property and its data type.</span></span> <span data-ttu-id="f04b5-122">キーワードは、この行の任意の順序で指定できますが、Hidden キーワードを使用してステートメントを開始すると、隠ぺいされたすべてのメンバーを後で簡単に識別できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f04b5-122">Although the keyword can be in any order on this line, starting the statement with the Hidden keyword makes it easier for you later to identify all members that you have hidden.</span></span>

```powershell
class Car
{
   # Properties
   [String] $Color
   [String] $ModelYear
   [int] $Distance

   # Method
   [int] Drive ([int]$miles)
   {
      $this.Distance += $miles
      $this.rides++
      return $this.Distance
   }

   # Hidden property of the Drive method
    hidden [int] $rides = 0
}
```

<span data-ttu-id="f04b5-123">次に、Car クラスの新しいインスタンスを作成し、変数 testcar に保存し \$ ます。</span><span class="sxs-lookup"><span data-stu-id="f04b5-123">Now, create a new instance of the Car class, and save it in a variable, \$TestCar.</span></span>

```powershell
$TestCar = [Car]::new()
```

<span data-ttu-id="f04b5-124">新しいインスタンスを作成したら、パイプを使用して $TestCar 変数の内容を取得します。</span><span class="sxs-lookup"><span data-stu-id="f04b5-124">After you create the new instance, pipe the contents of the $TestCar variable to Get-Member.</span></span> <span data-ttu-id="f04b5-125">Get-Member コマンドの結果に示されているメンバーの中に、このプロパティが含まれていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="f04b5-125">Observe that the rides property is not among the members listed in the Get-Member command results.</span></span>

```output
PS C:\Windows\system32> $TestCar | Get-Member

   TypeName: Car

Name        MemberType Definition
----        ---------- ----------
Drive       Method     int Drive(int miles)
Equals      Method     bool Equals(System.Object obj)
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
ToString    Method     string ToString()
Color       Property   string Color {get;set;}
Distance    Property   int Distance {get;set;}
ModelYear   Property   string ModelYear {get;set;}

```

<span data-ttu-id="f04b5-126">ここで Get-Member をもう一度実行してみてください。今回は、-Force パラメーターを追加してください。</span><span class="sxs-lookup"><span data-stu-id="f04b5-126">Now, try running Get-Member again, but this time, add the -Force parameter.</span></span>
<span data-ttu-id="f04b5-127">結果には、既定で非表示になっている他のメンバーのように、非表示の [実行] プロパティが含まれていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f04b5-127">Note that the results contain the hidden rides property, among other members that are hidden by default.</span></span>

```output
PS C:\Windows\system32> $TestCar | Get-Member -Force

   TypeName: Car

Name          MemberType   Definition
----          ----------   ----------
pstypenames   CodeProperty System.Collections.ObjectModel.Collection`1
psadapted     MemberSet    psadapted {Color, ModelYear, Distance,
psbase        MemberSet    psbase {Color, ModelYear, Distance,...
psextended    MemberSet    psextended {}
psobject      MemberSet    psobject {BaseObject, Members,...
Drive         Method       int Drive(int miles)
Equals        Method       bool Equals(System.Object obj)
GetHashCode   Method       int GetHashCode()
GetType       Method       type GetType()
get_Color     Method       string get_Color()
get_Distance  Method       int get_Distance()
get_ModelYear Method       string get_ModelYear()
get_rides     Method       int get_rides()
set_Color     Method       void set_Color(string )
set_Distance  Method       void set_Distance(int )
set_ModelYear Method       void set_ModelYear(string )
set_rides     Method       void set_rides(int )
ToString      Method       string ToString()
Color         Property     string Color {get;set;}
Distance      Property     int Distance {get;set;}
ModelYear     Property     string ModelYear {get;set;}
rides         Property     int rides {get;set;}

```

## <a name="see-also"></a><span data-ttu-id="f04b5-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="f04b5-128">SEE ALSO</span></span>

[<span data-ttu-id="f04b5-129">about_Classes</span><span class="sxs-lookup"><span data-stu-id="f04b5-129">about_Classes</span></span>](about_Classes.md)

[<span data-ttu-id="f04b5-130">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="f04b5-130">about_Language_Keywords</span></span>](about_Language_Keywords.md)

[<span data-ttu-id="f04b5-131">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="f04b5-131">about_Wildcards</span></span>](about_Wildcards.md)

[<span data-ttu-id="f04b5-132">Get-Member</span><span class="sxs-lookup"><span data-stu-id="f04b5-132">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)
