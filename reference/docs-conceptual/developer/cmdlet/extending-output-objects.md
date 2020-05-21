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
ms.openlocfilehash: 12a826363221b8a7ce06245c787a7bd0529e42f8
ms.sourcegitcommit: 17d798a041851382b406ed789097843faf37692d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83690907"
---
# <a name="extending-output-objects"></a><span data-ttu-id="d6038-102">出力オブジェクトを拡張する</span><span class="sxs-lookup"><span data-stu-id="d6038-102">Extending Output Objects</span></span>

<span data-ttu-id="d6038-103">型ファイル (types.ps1xml) を使用して、コマンドレット、関数、およびスクリプトによって返される .NET Framework オブジェクトを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="d6038-103">You can extend the .NET Framework objects that are returned by cmdlets, functions, and scripts by using types files (.ps1xml).</span></span> <span data-ttu-id="d6038-104">型ファイルは、既存のオブジェクトにプロパティとメソッドを追加できる XML ベースのファイルです。</span><span class="sxs-lookup"><span data-stu-id="d6038-104">Types files are XML-based files that let you add properties and methods to existing objects.</span></span> <span data-ttu-id="d6038-105">たとえば、Windows PowerShell は types.ps1xml ファイルを提供します。これにより、既存の複数の .NET Framework オブジェクトに要素が追加されます。</span><span class="sxs-lookup"><span data-stu-id="d6038-105">For example, Windows PowerShell provides the Types.ps1xml file, which adds elements to several existing .NET Framework objects.</span></span> <span data-ttu-id="d6038-106">Types.ps1xml ファイルは、Windows PowerShell インストールディレクトリ () にあります。 `$pshome`</span><span class="sxs-lookup"><span data-stu-id="d6038-106">The Types.ps1xml file is located in the Windows PowerShell installation directory (`$pshome`).</span></span> <span data-ttu-id="d6038-107">独自の型ファイルを作成して、それらのオブジェクトをさらに拡張したり、他のオブジェクトを拡張したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d6038-107">You can create your own types file to further extend those objects or to extend other objects.</span></span> <span data-ttu-id="d6038-108">型ファイルを使用してオブジェクトを拡張すると、そのオブジェクトのすべてのインスタンスが新しい要素で拡張されます。</span><span class="sxs-lookup"><span data-stu-id="d6038-108">When you extend an object by using a types file, any instance of the object is extended with the new elements.</span></span>

## <a name="extending-the-systemarray-object"></a><span data-ttu-id="d6038-109">System.string オブジェクトの拡張</span><span class="sxs-lookup"><span data-stu-id="d6038-109">Extending the System.Array Object</span></span>

<span data-ttu-id="d6038-110">次の例は、Windows PowerShell によっ[て types.ps1xml](/dotnet/api/System.Array)ファイル内の system.string オブジェクトがどのように拡張されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="d6038-110">The following example shows how Windows PowerShell extends the [System.Array](/dotnet/api/System.Array) object in the Types.ps1xml file.</span></span> <span data-ttu-id="d6038-111">既定では、 [system.string オブジェクトに](/dotnet/api/System.Array)は、 `Length` 配列内のオブジェクトの数を一覧表示するプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="d6038-111">By default, [System.Array](/dotnet/api/System.Array) objects have a `Length` property that lists the number of objects in the array.</span></span> <span data-ttu-id="d6038-112">ただし、名前 "length" はプロパティを明確に記述していないため、Windows PowerShell は `Count` alias プロパティを追加します。このプロパティには、プロパティと同じ値が表示され `Length` ます。</span><span class="sxs-lookup"><span data-stu-id="d6038-112">However, because the name "length" does not clearly describe the property, Windows PowerShell adds the `Count` alias property, which displays the same value as the `Length` property.</span></span> <span data-ttu-id="d6038-113">次の XML は、 `Count` プロパティを system.string 型に追加[します](/dotnet/api/System.Array)。</span><span class="sxs-lookup"><span data-stu-id="d6038-113">The following XML adds the `Count` property to the [System.Array](/dotnet/api/System.Array) type.</span></span>

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

<span data-ttu-id="d6038-114">この新しいエイリアスプロパティを表示するには、次の例に示すように、任意の配列で[Get メンバー](/powershell/module/Microsoft.PowerShell.Utility/Get-Member)コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d6038-114">To see this new alias property, use a [Get-Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) command on any array, as shown in the following example.</span></span>

```powershell
Get-Member -InputObject (1,2,3,4)
```

<span data-ttu-id="d6038-115">コマンドを実行すると、次の結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="d6038-115">The command returns the following results.</span></span>

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

<span data-ttu-id="d6038-116">プロパティまたはプロパティのいずれかを使用して、 `Count` `Length` 配列内のオブジェクトの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d6038-116">You can use either the `Count` property or the `Length` property to determine how many objects are in an array.</span></span> <span data-ttu-id="d6038-117">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d6038-117">For example:</span></span>

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

## <a name="custom-types-files"></a><span data-ttu-id="d6038-118">カスタム型ファイル</span><span class="sxs-lookup"><span data-stu-id="d6038-118">Custom Types Files</span></span>

<span data-ttu-id="d6038-119">カスタム型ファイルを作成するには、まず既存の型ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="d6038-119">To create a custom types file, start by copying an existing types file.</span></span> <span data-ttu-id="d6038-120">新しいファイルには任意の名前を付けることができますが、ファイル名の拡張子は types.ps1xml である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6038-120">The new file can have any name, but it must have a .ps1xml file name extension.</span></span> <span data-ttu-id="d6038-121">ファイルをコピーすると、Windows PowerShell にアクセスできる任意のディレクトリに新しいファイルを配置できますが、ファイルを Windows PowerShell インストールディレクトリ ( `$pshome` ) またはインストールディレクトリのサブディレクトリに配置すると便利です。</span><span class="sxs-lookup"><span data-stu-id="d6038-121">When you copy the file, you can place the new file in any directory that is accessible to Windows PowerShell, but it is useful to place the files in the Windows PowerShell installation directory (`$pshome`) or in a subdirectory of the installation directory.</span></span>

<span data-ttu-id="d6038-122">独自の拡張型をファイルに追加するには、拡張する各オブジェクトの types 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="d6038-122">To add your own extended types to the file, add a types element for each object that you want to extend.</span></span> <span data-ttu-id="d6038-123">次のトピックでは例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="d6038-123">The following topics provide examples.</span></span>

- <span data-ttu-id="d6038-124">プロパティとプロパティセットの追加の詳細については、「[拡張プロパティ](./extending-properties-for-objects.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6038-124">For more information about adding properties and property sets, see [Extended Properties](./extending-properties-for-objects.md)</span></span>

- <span data-ttu-id="d6038-125">メソッドの追加の詳細については、「[拡張メソッド](./defining-default-methods-for-objects.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6038-125">For more information about adding methods, see [Extended Methods](./defining-default-methods-for-objects.md).</span></span>

- <span data-ttu-id="d6038-126">メンバーセットの追加の詳細については、「[拡張メンバーセット](./defining-default-member-sets-for-objects.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6038-126">For more information about adding member sets, see [Extended Member Sets](./defining-default-member-sets-for-objects.md).</span></span>

<span data-ttu-id="d6038-127">独自の拡張型を定義したら、次のいずれかの方法を使用して拡張オブジェクトを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d6038-127">After you define your own extended types, use one of the following methods to make your extended objects available:</span></span>

- <span data-ttu-id="d6038-128">拡張型ファイルを現在のセッションで使用できるようにするには、[更新-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData)コマンドレットを使用して、新しいファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="d6038-128">To make your extended types file available to the current session, use the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) cmdlet to add the new file.</span></span> <span data-ttu-id="d6038-129">型を他の型のファイル (types.ps1xml ファイルを含む) で定義されている型よりも優先する場合は、 `PrependData` [更新-typedata](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData)コマンドレットのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d6038-129">If you want your types to take precedence over the types that are defined in other types files (including the Types.ps1xml file), use the `PrependData` parameter of the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) cmdlet.</span></span>
- <span data-ttu-id="d6038-130">拡張型ファイルを今後のすべてのセッションで使用できるようにするには、モジュールに型ファイルを追加するか、現在のセッションをエクスポートするか、または[更新-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData)コマンドを Windows PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="d6038-130">To make your extended types file available to all future sessions, add the types file to a module, export the current session, or add the [Update-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) command to your Windows PowerShell profile.</span></span>

## <a name="signing-types-files"></a><span data-ttu-id="d6038-131">署名の種類ファイル</span><span class="sxs-lookup"><span data-stu-id="d6038-131">Signing Types Files</span></span>

<span data-ttu-id="d6038-132">XML にはスクリプトブロックを含めることができるため、改ざんを防ぐために型ファイルをデジタル署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6038-132">Types files should be digitally signed to prevent tampering because the XML can include script blocks.</span></span> <span data-ttu-id="d6038-133">デジタル署名の追加の詳細については、「」を参照してください[about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)</span><span class="sxs-lookup"><span data-stu-id="d6038-133">For more information about adding digital signatures, see [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)</span></span>

## <a name="see-also"></a><span data-ttu-id="d6038-134">参照</span><span class="sxs-lookup"><span data-stu-id="d6038-134">See Also</span></span>

[<span data-ttu-id="d6038-135">オブジェクトの既定のプロパティの定義</span><span class="sxs-lookup"><span data-stu-id="d6038-135">Defining Default Properties for Objects</span></span>](./extending-properties-for-objects.md)

[<span data-ttu-id="d6038-136">オブジェクトの既定のメソッドを定義する</span><span class="sxs-lookup"><span data-stu-id="d6038-136">Defining Default Methods for Objects</span></span>](./defining-default-methods-for-objects.md)

[<span data-ttu-id="d6038-137">オブジェクトの既定のメンバー セットを定義する</span><span class="sxs-lookup"><span data-stu-id="d6038-137">Defining Default Member Sets for Objects</span></span>](./defining-default-member-sets-for-objects.md)

[<span data-ttu-id="d6038-138">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="d6038-138">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
