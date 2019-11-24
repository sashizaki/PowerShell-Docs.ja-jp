---
title: パブリックリソーススキーマ |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e67298ee-a773-4402-8afb-d97ad0e030e5
caps.latest.revision: 4
ms.openlocfilehash: c7e20ff0f36e8cab2d414ff2e5924b3359ad9c60
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366271"
---
# <a name="public-resource-schema"></a><span data-ttu-id="e0999-102">パブリック リソース スキーマ</span><span class="sxs-lookup"><span data-stu-id="e0999-102">Public Resource Schema</span></span>

<span data-ttu-id="e0999-103">管理 OData は、MOF を使用してリソースとそのプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="e0999-103">Management OData uses MOF to define resources and their properties.</span></span> <span data-ttu-id="e0999-104">管理 OData エンティティのプロパティは、基になるコマンドレットによって返されるマネージ型のプロパティに直接対応します。</span><span class="sxs-lookup"><span data-stu-id="e0999-104">The properties of a Management OData entity correspond directly to the properties of the managed type returned by the underlying cmdlet.</span></span>

## <a name="defining-a-resource"></a><span data-ttu-id="e0999-105">リソースの定義</span><span class="sxs-lookup"><span data-stu-id="e0999-105">Defining a resource</span></span>

<span data-ttu-id="e0999-106">各リソースは、Windows PowerShell コマンドレットによって返されるオブジェクトに対応します。</span><span class="sxs-lookup"><span data-stu-id="e0999-106">Each resource corresponds to an object returned by a Windows PowerShell cmdlet.</span></span> <span data-ttu-id="e0999-107">パブリックリソース MOF ファイルでは、クラスを宣言することによってリソースを定義します。</span><span class="sxs-lookup"><span data-stu-id="e0999-107">In the public resource MOF file, you define a resource by declaring a class.</span></span> <span data-ttu-id="e0999-108">クラスは、オブジェクトのプロパティに対応するプロパティで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e0999-108">The class consists of properties that correspond to the properties of the object.</span></span> <span data-ttu-id="e0999-109">たとえば、次の例では、system.string[クラスは](/dotnet/api/System.Diagnostics.Process)次の MOF で表されています。</span><span class="sxs-lookup"><span data-stu-id="e0999-109">For example, in the following example, the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) class is represented by the following MOF.</span></span>

```csharp
class PswsTest_Process
{
    [Key] SInt32 Id;
    [Required] SInt32 BasePriority;
    [Required] SInt32 HandleCount;
    [Required] string MachineName;
    [Required] SInt32 MainWindowHandle;

    ...
};
```

<span data-ttu-id="e0999-110">各プロパティ名の前にはデータ型が付きます。</span><span class="sxs-lookup"><span data-stu-id="e0999-110">Each property name is preceded by a data type.</span></span> <span data-ttu-id="e0999-111">この例のデータ型は、.NET Framework のプリミティブな CLR データ型に対応していますが、プロパティは、後で説明する他のリソースや複合型への参照にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e0999-111">The data types in this example correspond to primitive CLR data types in the .NET Frameworks, but properties can also be references to other resources or complex types, which are both described later.</span></span>

<span data-ttu-id="e0999-112">`Key` 修飾子は、プロパティがリソースインスタンスを一意に識別するために使用されることを示します。</span><span class="sxs-lookup"><span data-stu-id="e0999-112">The `Key` qualifier indicates that a property is used to uniquely identify a resource instance.</span></span> <span data-ttu-id="e0999-113">1つのリソースに複数のキーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e0999-113">A resource can have more than one key.</span></span>

<span data-ttu-id="e0999-114">`Required` 修飾子は、プロパティが必須であることを示します。</span><span class="sxs-lookup"><span data-stu-id="e0999-114">The `Required` qualifier indicates that the property is required.</span></span> <span data-ttu-id="e0999-115">`Key` 修飾子を使用してプロパティにラベルが付けられている場合は、必須であると見なされ、`Required` 修飾子は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e0999-115">If a property is labeled with the `Key` qualifier, it is considered to be required, and the `Required` qualifier is not necessary.</span></span>

### <a name="complex-data-types"></a><span data-ttu-id="e0999-116">複合データ型</span><span class="sxs-lookup"><span data-stu-id="e0999-116">Complex data types</span></span>

<span data-ttu-id="e0999-117">エンティティのプロパティには、複合データ型を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e0999-117">Properties of entities can have complex data types.</span></span> <span data-ttu-id="e0999-118">複合データ型は、C プログラミング言語の構造体と同様に、他の型で構成される型です。</span><span class="sxs-lookup"><span data-stu-id="e0999-118">Complex data types are types that are made up of other types, similar to structs in the C programming language.</span></span> <span data-ttu-id="e0999-119">次の例に示すように、複合型は、MOF ファイルで `ComplexType` 修飾子を持つクラスとして宣言されます。</span><span class="sxs-lookup"><span data-stu-id="e0999-119">A complex type is declared in the MOF file as a class with the `ComplexType` qualifier, as in the following example.</span></span>

```csharp
[ComplexType]
class PswsTest_ProcessModule
{
    String ModuleName;
    String FileName;
};
```

<span data-ttu-id="e0999-120">複合型としてエンティティプロパティを宣言するには、複合型の名前を含む、`EmbeddedInstance` 修飾子を使用して `string` 型として宣言します。</span><span class="sxs-lookup"><span data-stu-id="e0999-120">To declare an entity property as a complex type, you declare it as a `string` type with the `EmbeddedInstance` qualifier, including the name of the complex type.</span></span> <span data-ttu-id="e0999-121">次の例は、前の例で宣言した `PswsTest_ProcessModule` 型のプロパティの宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="e0999-121">The following example shows the declaration of a property of the `PswsTest_ProcessModule` type declared in the previous example.</span></span>

```csharp
[Required, EmbeddedInstance("PswsTest_ProcessModule")] String Modules[];
```

### <a name="associating-entities"></a><span data-ttu-id="e0999-122">エンティティの関連付け</span><span class="sxs-lookup"><span data-stu-id="e0999-122">Associating entities</span></span>

<span data-ttu-id="e0999-123">アソシエーションと AssociationClass 修飾子を使用して、2つのエンティティを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="e0999-123">You can associate two entities by using the Association and AssociationClass qualifiers.</span></span> <span data-ttu-id="e0999-124">詳細については、「 [Management OData エンティティの関連付け](./associating-management-odata-entities.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0999-124">For more information, see [Associating Management OData Entities](./associating-management-odata-entities.md).</span></span>

### <a name="derived-types"></a><span data-ttu-id="e0999-125">派生型</span><span class="sxs-lookup"><span data-stu-id="e0999-125">Derived types</span></span>

<span data-ttu-id="e0999-126">別の型から型を派生させることができます。</span><span class="sxs-lookup"><span data-stu-id="e0999-126">You can derive a type from another type.</span></span> <span data-ttu-id="e0999-127">派生型は、明示的に派生したプロパティに加えて、派生元の型のすべてのプロパティを継承します。</span><span class="sxs-lookup"><span data-stu-id="e0999-127">The derived type inherits all of the properties of the type from which it derives in addition to any properties explicitly derived.</span></span> <span data-ttu-id="e0999-128">次の例は、型宣言と、その型から派生した2つの型の宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="e0999-128">The following example shows a type declaration and then a declaration of two types derived from that type.</span></span>

```csharp
Class Product {

    [Key] String ProductName;

};

Class DairyProduct : Product {

    Uint16 PercentFat;
};
Class POPProduct : Product {

    Boolean IsCarbonated;
};
```