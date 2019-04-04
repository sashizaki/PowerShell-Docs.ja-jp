---
title: パブリック リソース スキーマ |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e67298ee-a773-4402-8afb-d97ad0e030e5
caps.latest.revision: 4
ms.openlocfilehash: c7e20ff0f36e8cab2d414ff2e5924b3359ad9c60
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58057248"
---
# <a name="public-resource-schema"></a><span data-ttu-id="71a7a-102">パブリック リソース スキーマ</span><span class="sxs-lookup"><span data-stu-id="71a7a-102">Public Resource Schema</span></span>

<span data-ttu-id="71a7a-103">Management OData では、MOF を使用して、リソースとそのプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="71a7a-103">Management OData uses MOF to define resources and their properties.</span></span> <span data-ttu-id="71a7a-104">Management OData エンティティのプロパティは、基になるコマンドレットによって返されるマネージ型のプロパティに直接対応します。</span><span class="sxs-lookup"><span data-stu-id="71a7a-104">The properties of a Management OData entity correspond directly to the properties of the managed type returned by the underlying cmdlet.</span></span>

## <a name="defining-a-resource"></a><span data-ttu-id="71a7a-105">リソースを定義します。</span><span class="sxs-lookup"><span data-stu-id="71a7a-105">Defining a resource</span></span>

<span data-ttu-id="71a7a-106">各リソースは、Windows PowerShell コマンドレットによって返されるオブジェクトに対応します。</span><span class="sxs-lookup"><span data-stu-id="71a7a-106">Each resource corresponds to an object returned by a Windows PowerShell cmdlet.</span></span> <span data-ttu-id="71a7a-107">パブリック リソースの MOF ファイルでは、クラスを宣言することで、リソースを定義します。</span><span class="sxs-lookup"><span data-stu-id="71a7a-107">In the public resource MOF file, you define a resource by declaring a class.</span></span> <span data-ttu-id="71a7a-108">クラスは、オブジェクトのプロパティに対応するプロパティで構成されます。</span><span class="sxs-lookup"><span data-stu-id="71a7a-108">The class consists of properties that correspond to the properties of the object.</span></span> <span data-ttu-id="71a7a-109">たとえば、次の例で、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)クラスは、次の MOF で表されます。</span><span class="sxs-lookup"><span data-stu-id="71a7a-109">For example, in the following example, the [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process) class is represented by the following MOF.</span></span>

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

<span data-ttu-id="71a7a-110">各プロパティ名には、データ型が付きます。</span><span class="sxs-lookup"><span data-stu-id="71a7a-110">Each property name is preceded by a data type.</span></span> <span data-ttu-id="71a7a-111">この例では、データ型が .NET のフレームワークでのプリミティブの CLR データ型に対応していますが、プロパティは他のリソースまたは複合型は、どちらも後で説明への参照にもできます。</span><span class="sxs-lookup"><span data-stu-id="71a7a-111">The data types in this example correspond to primitive CLR data types in the .NET Frameworks, but properties can also be references to other resources or complex types, which are both described later.</span></span>

<span data-ttu-id="71a7a-112">`Key`修飾子は、リソースのインスタンスを一意に識別するプロパティを使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="71a7a-112">The `Key` qualifier indicates that a property is used to uniquely identify a resource instance.</span></span> <span data-ttu-id="71a7a-113">リソースは、1 つ以上のキーを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="71a7a-113">A resource can have more than one key.</span></span>

<span data-ttu-id="71a7a-114">`Required`修飾子は、プロパティが必要であることを示します。</span><span class="sxs-lookup"><span data-stu-id="71a7a-114">The `Required` qualifier indicates that the property is required.</span></span> <span data-ttu-id="71a7a-115">プロパティが付いた場合、`Key`修飾子が必要になることと見なされます、`Required`修飾子が必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="71a7a-115">If a property is labeled with the `Key` qualifier, it is considered to be required, and the `Required` qualifier is not necessary.</span></span>

### <a name="complex-data-types"></a><span data-ttu-id="71a7a-116">複合データ型</span><span class="sxs-lookup"><span data-stu-id="71a7a-116">Complex data types</span></span>

<span data-ttu-id="71a7a-117">エンティティのプロパティは、複雑なデータ型を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="71a7a-117">Properties of entities can have complex data types.</span></span> <span data-ttu-id="71a7a-118">複雑なデータ型は、C プログラミング言語で構造体のような他の種類で構成されている型です。</span><span class="sxs-lookup"><span data-stu-id="71a7a-118">Complex data types are types that are made up of other types, similar to structs in the C programming language.</span></span> <span data-ttu-id="71a7a-119">複合型がでクラスとして、MOF ファイルで宣言されている、`ComplexType`修飾子は、次の例に示すようにします。</span><span class="sxs-lookup"><span data-stu-id="71a7a-119">A complex type is declared in the MOF file as a class with the `ComplexType` qualifier, as in the following example.</span></span>

```csharp
[ComplexType]
class PswsTest_ProcessModule
{
    String ModuleName;
    String FileName;
};
```

<span data-ttu-id="71a7a-120">宣言としてエンティティ プロパティとして複合型を宣言する、`string`の種類を`EmbeddedInstance`複合型の名前を含む修飾子。</span><span class="sxs-lookup"><span data-stu-id="71a7a-120">To declare an entity property as a complex type, you declare it as a `string` type with the `EmbeddedInstance` qualifier, including the name of the complex type.</span></span> <span data-ttu-id="71a7a-121">次の例のプロパティの宣言を示しています、`PswsTest_ProcessModule`前の例で宣言された型。</span><span class="sxs-lookup"><span data-stu-id="71a7a-121">The following example shows the declaration of a property of the `PswsTest_ProcessModule` type declared in the previous example.</span></span>

```csharp
[Required, EmbeddedInstance("PswsTest_ProcessModule")] String Modules[];
```

### <a name="associating-entities"></a><span data-ttu-id="71a7a-122">エンティティの関連付け</span><span class="sxs-lookup"><span data-stu-id="71a7a-122">Associating entities</span></span>

<span data-ttu-id="71a7a-123">アソシエーションおよび関連クラスの修飾子を使用して、2 つのエンティティを関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="71a7a-123">You can associate two entities by using the Association and AssociationClass qualifiers.</span></span> <span data-ttu-id="71a7a-124">詳細については、[Management OData エンティティを関連付ける](./associating-management-odata-entities.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71a7a-124">For more information, see [Associating Management OData Entities](./associating-management-odata-entities.md).</span></span>

### <a name="derived-types"></a><span data-ttu-id="71a7a-125">派生型</span><span class="sxs-lookup"><span data-stu-id="71a7a-125">Derived types</span></span>

<span data-ttu-id="71a7a-126">別の型から型を派生させることができます。</span><span class="sxs-lookup"><span data-stu-id="71a7a-126">You can derive a type from another type.</span></span> <span data-ttu-id="71a7a-127">派生型では、そのプロパティを明示的に派生した派生元である型のプロパティのすべてを継承します。</span><span class="sxs-lookup"><span data-stu-id="71a7a-127">The derived type inherits all of the properties of the type from which it derives in addition to any properties explicitly derived.</span></span> <span data-ttu-id="71a7a-128">次の例では、型宣言し、その型から派生した 2 つの型の宣言を示します。</span><span class="sxs-lookup"><span data-stu-id="71a7a-128">The following example shows a type declaration and then a declaration of two types derived from that type.</span></span>

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