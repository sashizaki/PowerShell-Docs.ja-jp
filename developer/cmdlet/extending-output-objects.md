---
title: 出力オブジェクトの拡張 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a252e0ec-d456-42d7-bd49-d6b8bc57f388
caps.latest.revision: 11
ms.openlocfilehash: 9c9d50c880f843e21621e5735c800e3afb48b2ad
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068166"
---
# <a name="extending-output-objects"></a><span data-ttu-id="80828-102">出力オブジェクトを拡張する</span><span class="sxs-lookup"><span data-stu-id="80828-102">Extending Output Objects</span></span>

<span data-ttu-id="80828-103">型ファイル (.ps1xml) を使用して、コマンドレット、関数、およびスクリプトによって返される .NET Framework オブジェクトを拡張することができます。</span><span class="sxs-lookup"><span data-stu-id="80828-103">You can extend the .NET Framework objects that are returned by cmdlets, functions, and scripts by using types files (.ps1xml).</span></span> <span data-ttu-id="80828-104">型ファイルは XML ベースのファイルを既存のオブジェクトにプロパティとメソッドを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="80828-104">Types files are XML-based files that let you add properties and methods to existing objects.</span></span> <span data-ttu-id="80828-105">たとえば、Windows PowerShell は、Types.ps1xml ファイルをいくつかの既存の .NET Framework オブジェクトに要素を追加します。 を提供します。</span><span class="sxs-lookup"><span data-stu-id="80828-105">For example, Windows PowerShell provides the Types.ps1xml file, which adds elements to several existing .NET Framework objects.</span></span> <span data-ttu-id="80828-106">Types.ps1xml ファイルは、Windows PowerShell インストール ディレクトリにあります (`$pshome`)。</span><span class="sxs-lookup"><span data-stu-id="80828-106">The Types.ps1xml file is located in the Windows PowerShell installation directory (`$pshome`).</span></span> <span data-ttu-id="80828-107">さらにそれらのオブジェクトを拡張する、またはその他のオブジェクトを拡張する独自の種類ファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="80828-107">You can create your own types file to further extend those objects or to extend other objects.</span></span> <span data-ttu-id="80828-108">型ファイルを使用してオブジェクトを拡張すると、新しい要素を持つオブジェクトの任意のインスタンスが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="80828-108">When you extend an object by using a types file, any instance of the object is extended with the new elements.</span></span>

## <a name="extending-the-systemarray-object"></a><span data-ttu-id="80828-109">System.Array オブジェクトを拡張します。</span><span class="sxs-lookup"><span data-stu-id="80828-109">Extending the System.Array Object</span></span>

<span data-ttu-id="80828-110">次の例は、Windows PowerShell を拡張する方法を示しています、 [System.Array](/dotnet/api/System.Array) Types.ps1xml ファイル内のオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="80828-110">The following example shows how Windows PowerShell extends the [System.Array](/dotnet/api/System.Array) object in the Types.ps1xml file.</span></span> <span data-ttu-id="80828-111">既定では、 [System.Array](/dotnet/api/System.Array)オブジェクトが、`Length`配列内のオブジェクトの数を一覧表示するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="80828-111">By default, [System.Array](/dotnet/api/System.Array) objects have a `Length` property that lists the number of objects in the array.</span></span> <span data-ttu-id="80828-112">ただし、"length"という名前は、プロパティを明確に記載されていないため、Windows PowerShell が追加されます。、`Count`エイリアスのプロパティと同じ値を表示する、`Length`プロパティ。</span><span class="sxs-lookup"><span data-stu-id="80828-112">However, because the name "length" does not clearly describe the property, Windows PowerShell adds the `Count` alias property, which displays the same value as the `Length` property.</span></span> <span data-ttu-id="80828-113">次の XML を追加、`Count`プロパティを[System.Array](/dotnet/api/System.Array)型。</span><span class="sxs-lookup"><span data-stu-id="80828-113">The following XML adds the `Count` property to the [System.Array](/dotnet/api/System.Array) type.</span></span>

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

<span data-ttu-id="80828-114">この新しいエイリアス プロパティを表示するには、使用、 [Get-member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member)任意の配列でコマンドを次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="80828-114">To see this new alias property, use a [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) command on any array, as shown in the following example.</span></span>

```powershell
Get-Member -InputObject (1,2,3,4)
```

<span data-ttu-id="80828-115">このコマンドは、次の結果を返します。</span><span class="sxs-lookup"><span data-stu-id="80828-115">The command returns the following results.</span></span>
```output
Name           MemberType    Definition
----           ----------    ----------
Count          AliasProperty Count = Length
Address        Method        System.Object& Address(Int32 )
Clone          Method        System.Object Clone()
CopyTo         Method        System.Void CopyTo(Array array, Int32 index):
Equals         Method        System.Boolean Equals(Object obj)
Get            Method        System.Object Get(Int32 )
...
Length         Property      System.Int32 Length {get;}
```
<span data-ttu-id="80828-116">いずれかを使用することができます、`Count`プロパティまたは`Length`プロパティを配列内のオブジェクトの数を確認します。</span><span class="sxs-lookup"><span data-stu-id="80828-116">You can use either the `Count` property or the `Length` property to determine how many objects are in an array.</span></span> <span data-ttu-id="80828-117">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="80828-117">For example:</span></span>

```powershell
PS> (1, 2, 3, 4).Count
```

```output
4
```

```powershell
PS> (1, 2, 3, 4).Length
```

```output
4
```

## <a name="custom-types-files"></a><span data-ttu-id="80828-118">カスタム型は、ファイル</span><span class="sxs-lookup"><span data-stu-id="80828-118">Custom Types Files</span></span>

<span data-ttu-id="80828-119">カスタム型ファイルを作成するには、型の既存のファイルをコピーすることで開始します。</span><span class="sxs-lookup"><span data-stu-id="80828-119">To create a custom types file, start by copying an existing types file.</span></span> <span data-ttu-id="80828-120">新しいファイルでは、任意の名前を使用できますが、.ps1xml ファイル名拡張子があります。</span><span class="sxs-lookup"><span data-stu-id="80828-120">The new file can have any name, but it must have a .ps1xml file name extension.</span></span> <span data-ttu-id="80828-121">ファイルをコピーすると、Windows PowerShell にアクセスできる任意のディレクトリに新しいファイルを配置することができますが、Windows PowerShell のインストール ディレクトリにファイルを配置すると便利です (`$pshome`) またはインストール ディレクトリのサブディレクトリにします。</span><span class="sxs-lookup"><span data-stu-id="80828-121">When you copy the file, you can place the new file in any directory that is accessible to Windows PowerShell, but it is useful to place the files in the Windows PowerShell installation directory (`$pshome`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="80828-122">ファイルには、独自の拡張型を追加するには、拡張する各オブジェクトの型の要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="80828-122">To add your own extended types to the file, add a types element for each object that you want to extend.</span></span> <span data-ttu-id="80828-123">次のトピックでは、例を示します。</span><span class="sxs-lookup"><span data-stu-id="80828-123">The following topics provide examples.</span></span>

- <span data-ttu-id="80828-124">プロパティおよびプロパティ セットを追加する方法の詳細については、次を参照してください[拡張プロパティ。](./extending-properties-for-objects.md)</span><span class="sxs-lookup"><span data-stu-id="80828-124">For more information about adding properties and property sets, see [Extended Properties](./extending-properties-for-objects.md)</span></span>

- <span data-ttu-id="80828-125">メソッドを追加する方法の詳細については、次を参照してください。[拡張メソッド](./defining-default-methods-for-objects.md)します。</span><span class="sxs-lookup"><span data-stu-id="80828-125">For more information about adding methods, see [Extended Methods](./defining-default-methods-for-objects.md).</span></span>

- <span data-ttu-id="80828-126">メンバーのセットを追加する方法の詳細については、次を参照してください。[メンバーのセットを拡張](./defining-default-member-sets-for-objects.md)します。</span><span class="sxs-lookup"><span data-stu-id="80828-126">For more information about adding member sets, see [Extended Member Sets](./defining-default-member-sets-for-objects.md).</span></span>

<span data-ttu-id="80828-127">独自の拡張型を定義した後は、次のメソッドのいずれかを使用して、拡張オブジェクトを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="80828-127">After you define your own extended types, use one of the following methods to make your extended objects available:</span></span>

- <span data-ttu-id="80828-128">で、拡張された種類のファイルを現在のセッションに使用できるようにするには使用、 [Update-typedata](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData)コマンドレットに新しいファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="80828-128">To make your extended types file available to the current session, use the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) cmdlet to add the new file.</span></span> <span data-ttu-id="80828-129">他の型 (Types.ps1xml ファイルを含む) ファイルで定義されている型よりも優先する型を自分の場合、使用、`PrependData`のパラメーター、 [Update-typedata](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="80828-129">If you want your types to take precedence over the types that are defined in other types files (including the Types.ps1xml file), use the `PrependData` parameter of the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) cmdlet.</span></span>
- <span data-ttu-id="80828-130">で、拡張された種類のファイルを今後のすべてのセッションに使用できるように型ファイルをモジュールに追加する、現在のセッションをエクスポートまたは追加、 [Update-typedata](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData)コマンドを Windows PowerShell プロファイル。</span><span class="sxs-lookup"><span data-stu-id="80828-130">To make your extended types file available to all future sessions, add the types file to a module, export the current session, or add the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) command to your Windows PowerShell profile.</span></span>

## <a name="signing-types-files"></a><span data-ttu-id="80828-131">種類のファイルへの署名</span><span class="sxs-lookup"><span data-stu-id="80828-131">Signing Types Files</span></span>

<span data-ttu-id="80828-132">ファイルの種類は、XML は、スクリプト ブロックを含めることができますので、改ざんを防ぐためにデジタル署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="80828-132">Types files should be digitally signed to prevent tampering because the XML can include script blocks.</span></span> <span data-ttu-id="80828-133">デジタル署名を追加する方法の詳細については、次を参照してください[about_Signing。](/powershell/module/microsoft.powershell.core/about/about_signing)</span><span class="sxs-lookup"><span data-stu-id="80828-133">For more information about adding digital signatures, see [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)</span></span>

## <a name="see-also"></a><span data-ttu-id="80828-134">参照</span><span class="sxs-lookup"><span data-stu-id="80828-134">See Also</span></span>

[<span data-ttu-id="80828-135">オブジェクトの既定のプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="80828-135">Defining Default Properties for Objects</span></span>](./extending-properties-for-objects.md)

[<span data-ttu-id="80828-136">オブジェクトの既定のメソッドを定義します。</span><span class="sxs-lookup"><span data-stu-id="80828-136">Defining Default Methods for Objects</span></span>](./defining-default-methods-for-objects.md)

[<span data-ttu-id="80828-137">オブジェクトの既定のメンバーのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="80828-137">Defining Default Member Sets for Objects</span></span>](./defining-default-member-sets-for-objects.md)

[<span data-ttu-id="80828-138">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="80828-138">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
