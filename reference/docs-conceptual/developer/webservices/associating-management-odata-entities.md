---
title: 管理 OData エンティティの関連付け |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 947a3add-3593-400d-8144-8b44c8adbe5e
caps.latest.revision: 5
ms.openlocfilehash: 44b718e024eb98ac562edb50076287a31f5edc6b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72359811"
---
# <a name="associating-management-odata-entities"></a><span data-ttu-id="a032b-102">Management OData エンティティを関連付ける</span><span class="sxs-lookup"><span data-stu-id="a032b-102">Associating Management OData Entities</span></span>

<span data-ttu-id="a032b-103">多くの場合、2つの異なる管理 OData エンティティ間のアソシエーションを作成すると便利です。</span><span class="sxs-lookup"><span data-stu-id="a032b-103">It is often useful to create an association between two different Management OData entities.</span></span> <span data-ttu-id="a032b-104">たとえば、管理 OData サービスは、カテゴリ内に編成された製品のカタログを管理するエンティティを持つことができ、エンティティ `Product` と `Category`を定義します。</span><span class="sxs-lookup"><span data-stu-id="a032b-104">For example, a Management OData service could have entities that manage a catalogue of products that are organized in categories, and define the entities `Product` and `Category`.</span></span> <span data-ttu-id="a032b-105">これら2つのエンティティを関連付けることにより、クライアントは、web サービスへの単一の要求を使用して、カテゴリ内のすべての製品に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="a032b-105">By associating these two entities, a client can get information about all of the products in a category with a single request to the web service.</span></span>

<span data-ttu-id="a032b-106">エンティティ間の関連付けを作成する方法を示すサンプルは、[アソシエーションサンプル](https://code.msdn.microsoft.com:443/windowsdesktop/Association-sample-0f0fa87e)でダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="a032b-106">A sample that shows how to create associations between entities can be downloaded at [Association sample](https://code.msdn.microsoft.com:443/windowsdesktop/Association-sample-0f0fa87e).</span></span>

## <a name="creating-the-association-in-the-resource-schema-file"></a><span data-ttu-id="a032b-107">リソーススキーマファイル内でのアソシエーションの作成</span><span class="sxs-lookup"><span data-stu-id="a032b-107">Creating the Association in the resource schema file</span></span>

<span data-ttu-id="a032b-108">次の MOF は、2つのエンティティを定義します。</span><span class="sxs-lookup"><span data-stu-id="a032b-108">The following MOF defines two entities.</span></span> <span data-ttu-id="a032b-109">これらの間には、関連付けを作成します。</span><span class="sxs-lookup"><span data-stu-id="a032b-109">We will create an association between them.</span></span>

```csharp
class Product {

[key] string ProductName;

// other fields ...
};

class Category {

[key] string CategoryName;

string Products[];

// other fields
}
```

<span data-ttu-id="a032b-110">`Category` クラスは、そのカテゴリに属する製品の名前の配列であるプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="a032b-110">The `Category` class defines a property that is an array of the names of the products that belong to that category.</span></span>

<span data-ttu-id="a032b-111">2つのエンティティを関連付けるには、サービスのリソーススキーマ MOF ファイルで `Association` 属性を持つクラスを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a032b-111">To associate two entities, you must define a class with the `Association` attribute in the resource schema MOF file for the service.</span></span> <span data-ttu-id="a032b-112">クラスでは、関連付けの `ends` と呼ばれる、関連付ける2つのエンティティを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a032b-112">The class must define the two entities to be associated, called `ends` of the association.</span></span> <span data-ttu-id="a032b-113">次の例は、カテゴリと製品のエンティティ間の関連付けを定義するクラスの定義を示しています。</span><span class="sxs-lookup"><span data-stu-id="a032b-113">The following example shows a definition of a class that defines an association between the Category and Products entities.</span></span>

```csharp
[Association]
class ProductCategory {
Category ref theCategory;
Product ref theProducts;
}
```

<span data-ttu-id="a032b-114">Category クラスの Products プロパティの宣言も変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a032b-114">You must also change the declaration of the Products property in the Category class.</span></span> <span data-ttu-id="a032b-115">`AssociationClass` キーワードを使用して、プロパティがアソシエーションの1つの end であることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a032b-115">You use the `AssociationClass` keyword to specify that the property is one end of the association.</span></span> <span data-ttu-id="a032b-116">プロパティは、文字列の配列ではなく、別のエンティティへの参照としても定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a032b-116">The property must also be defined as a reference to a separate entity, rather than an array of strings.</span></span> <span data-ttu-id="a032b-117">これを行うには、`ref` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="a032b-117">You do this by using the `ref` keyword.</span></span> <span data-ttu-id="a032b-118">次の例は、アソシエーションのプロパティ定義を示しています。</span><span class="sxs-lookup"><span data-stu-id="a032b-118">The following example shows the property definition for the association.</span></span>

```csharp
class Sample_Category {

[key] string CategoryName;

[AssociationClass("Sample_ProductCategory"),ToEnd("theProducts")]
Sample_Product ref AssociatedProducts[];
};
```

<span data-ttu-id="a032b-119">最後に、プロパティ定義を `Product` クラスに追加して、アソシエーションのもう一方の end を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a032b-119">Finally, you must declare the other end of the association by adding a property definition to the `Product` class.</span></span> <span data-ttu-id="a032b-120">これは、配列または単一のエンティティへの参照です。</span><span class="sxs-lookup"><span data-stu-id="a032b-120">This is a reference to either an array or to a single entity.</span></span> <span data-ttu-id="a032b-121">各製品が1つのカテゴリにのみ属していると仮定すると、定義は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a032b-121">Assuming that each product belongs to only one category, the definition would be as follows.</span></span>

```csharp
class Sample_Product {

[key] string ProductName;
[AssociationClass("Sample_ProductCategory"),ToEnd("theCategory")]
Sample_Category ref AssociatedCategory;
};
```

<span data-ttu-id="a032b-122">アソシエーションの2つの end を表すプロパティは、ナビゲーションプロパティと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a032b-122">The properties that represent the two ends of the association are called navigation properties.</span></span>

#### <a name="steps-for-associating-entities-in-the-resource-schema-file"></a><span data-ttu-id="a032b-123">リソーススキーマファイル内のエンティティを関連付ける手順</span><span class="sxs-lookup"><span data-stu-id="a032b-123">Steps for associating entities in the resource schema file</span></span>

- <span data-ttu-id="a032b-124">`Association` キーワードを使用して、アソシエーションをクラスとして定義します。</span><span class="sxs-lookup"><span data-stu-id="a032b-124">Define the association as a class by using the `Association` keyword.</span></span>

- <span data-ttu-id="a032b-125">アソシエーションの end を定義するには、AssociationClass キーワードを使用して、関連付けられているエンティティのプロパティを限定します。</span><span class="sxs-lookup"><span data-stu-id="a032b-125">Define the ends of the association by using the AssociationClass keyword to qualify properties of the associated entities.</span></span>

## <a name="creating-the-association-in-the-resource-mapping-xml-file"></a><span data-ttu-id="a032b-126">リソースマッピング XML ファイルでのアソシエーションの作成</span><span class="sxs-lookup"><span data-stu-id="a032b-126">Creating the association in the resource mapping XML file</span></span>

<span data-ttu-id="a032b-127">リソースマッピング XML ファイル内のアソシエーションをマップする場合は、3つの異なるケースが考えられます。</span><span class="sxs-lookup"><span data-stu-id="a032b-127">There are three different cases to consider when mapping an association in the resource mapping XML file.</span></span>

#### <a name="determining-how-to-associate-entities-in-the-resource-mapping-file"></a><span data-ttu-id="a032b-128">リソースマッピングファイル内のエンティティを関連付ける方法の決定</span><span class="sxs-lookup"><span data-stu-id="a032b-128">Determining how to associate entities in the resource mapping file</span></span>

- <span data-ttu-id="a032b-129">ナビゲーションプロパティが基になるに存在する場合は。</span><span class="sxs-lookup"><span data-stu-id="a032b-129">If the navigation property is present in the underlying.</span></span> <span data-ttu-id="a032b-130">.NET Framework 型、およびそのプロパティに外部キーが含まれているため、明示的なマッピングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="a032b-130">.NET Framework type, and that property contains foreign keys, no explicit mapping is necessary.</span></span>

- <span data-ttu-id="a032b-131">ナビゲーションプロパティが基になる .NET Framework 型に存在しない場合は、関連付けられているインスタンスのキーの一覧を取得するコマンドレットを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a032b-131">If the navigation property does not exist in the underlying .NET Framework type, you must specify a cmdlet that retrieves the list of keys of the associated instances.</span></span> <span data-ttu-id="a032b-132">これを行うには、他の CRUD コマンドの `cmdlets` を定義する要素に従って、`CmdletImplementation` 要素の下に入れ子になっている `Association` 要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="a032b-132">You do this by adding an `Association` element nested under the `CmdletImplementation` element, following the elements that define the `cmdlets` for the other CRUD commands.</span></span>

  ```xml
  Class Name=" Category">
     <CmdletImplementation>
        <Query> ... </Query>
        <Associations>
           <Field>
              <Name>AssociatedProducts</Name>
              <GetReference>
                 <Cmdlet>Get-ProductsInCategory</Cmdlet>
                 <ParameterForThisObject>Category</ParameterForThisObject>
              </GetReference>
           </Field>
        </Associations>
     </CmdletImplementation>
  </Class>
  ```

- <span data-ttu-id="a032b-133">ナビゲーションプロパティが基になる .NET Framework 型に存在するが、外部キーではなくオブジェクトインスタンスが含まれている場合、外部キーを取得するには、Windows PowerShell の関数またはスクリプトを記述して、コマンドレットを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a032b-133">If the navigation property does exist in the underlying .NET Framework type, but it contains object instances instead of foreign keys, then you must create a cmdlet (by writing a Windows PowerShell function or script) to retrieve the foreign keys.</span></span> <span data-ttu-id="a032b-134">次に、そのコマンドレットをリソースマッピングファイルで指定します。</span><span class="sxs-lookup"><span data-stu-id="a032b-134">You then specify that cmdlet in the resource mapping file.</span></span> <span data-ttu-id="a032b-135">たとえば、キーを取得するスクリプトは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a032b-135">For example, the script to retrieve the keys would look like the following.</span></span>

  ```
  Param(
      [string] $Key
      )

  (get-category $key).AssociatedProducts

  ```

  <span data-ttu-id="a032b-136">また、リソースマッピングファイルの XML は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="a032b-136">And the XML in the resource mapping file would look like the following.</span></span>

  ```xml
  Class Name=" Category">
     <CmdletImplementation>
        <Query> ... </Query>
        <Associations>
           <Field>
              <Name>AssociatedProducts</Name>
              <GetReference>
                 <Cmdlet>Get-ProductsInCategory.ps1</Cmdlet>
                 <ParameterForThisObject>Category</ParameterForThisObject>
              </GetReference>
           </Field>
        </Associations>
     </CmdletImplementation>
  </Class>
  ```

- <span data-ttu-id="a032b-137">関連付けられているエンティティを取得するコマンドレットを指定するだけでなく、コマンドレットを指定してコレクションの参照を追加および削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="a032b-137">In addition to specifying a cmdlet to retrieve the associated entities, you can also specify cmdlets to add and remove references from the collection.</span></span> <span data-ttu-id="a032b-138">次の例では、Add-ProductToCategory および Remove-Producttocategory コマンドレットが存在することを前提としています (前の例と同様に、スクリプトまたは関数でも定義できます)。</span><span class="sxs-lookup"><span data-stu-id="a032b-138">The following example assumes that the Add-ProductToCategory and Remove-ProductFromCategory cmdlets exist (they can also be defined in a script or function as in the previous example).</span></span>

  ```xml
  Class Name="Sample.Category">
     <CmdletImplementation>
        <Query> ... </Query>
        <Associations>
           <Field>
              <Name>AssociatedProducts</Name>
              <GetReference>
  ...
              </GetReference>
        <AddReference>
     <CmdletName>"Add-ProductToCategory"</>
     <ParameterForThisObject>"Product"</>
     <ParameterForReferredObject>"Category"</>
        </AddReference>
        <RemoveReference>
     <CmdletName="Remove-ProductFromCategory"/>
     <ParameterForThisObject >"Product"</>
     <ParameterForReferredObject >"Category"</>
        </RemoveReference>
           </Field>
        </Associations>
     </CmdletImplementation>
  </Class>
  ```

## <a name="querying-associated-entities"></a><span data-ttu-id="a032b-139">関連エンティティのクエリ</span><span class="sxs-lookup"><span data-stu-id="a032b-139">Querying associated entities</span></span>

<span data-ttu-id="a032b-140">クライアントは、特定のクエリを作成することによって、エンティティに関連付けられているインスタンスの一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="a032b-140">The client can retrieve a list of the instances associated with an entity by creating specific queries.</span></span>

#### <a name="constructing-queries-for-associated-entities"></a><span data-ttu-id="a032b-141">関連付けられたエンティティに対するクエリの構築</span><span class="sxs-lookup"><span data-stu-id="a032b-141">Constructing queries for associated entities</span></span>

- <span data-ttu-id="a032b-142">クライアントは、関連付けられている製品を取得せずに、カテゴリの詳細を要求できます。</span><span class="sxs-lookup"><span data-stu-id="a032b-142">A client can request the details of a category without retrieving its associated products.</span></span> <span data-ttu-id="a032b-143">たとえば、次の要求では、`food` カテゴリの詳細が取得されます。</span><span class="sxs-lookup"><span data-stu-id="a032b-143">For example, the following request gets details of the `food` category.</span></span>

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')
  ```

  <span data-ttu-id="a032b-144">カテゴリの関連製品を取得する (ただし、カテゴリ自体の詳細は含まれません)、クライアントは要求のナビゲーションプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="a032b-144">To get the associated products of the category (but not details of the category itself, the client specifies the navigation property in the request.</span></span>

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/AssociatedProducts
  ```

- <span data-ttu-id="a032b-145">製品の Url のみを取得するには、要求で `$links` 修飾子を使用します。</span><span class="sxs-lookup"><span data-stu-id="a032b-145">To retrieve only URLs of the products, use the `$links` qualifier in the request.</span></span>

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/$links/AssociatedProducts
  ```

- <span data-ttu-id="a032b-146">クライアントは、`$expand` の修飾子を使用して、カテゴリの詳細とそれに関連付けられている製品の両方を取得できます。</span><span class="sxs-lookup"><span data-stu-id="a032b-146">The client can get both the category details and its associated products by using the `$expand` qualifier.</span></span>

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')?$expand=AssociatedProducts
  ```

## <a name="see-also"></a><span data-ttu-id="a032b-147">参照</span><span class="sxs-lookup"><span data-stu-id="a032b-147">See Also</span></span>

[<span data-ttu-id="a032b-148">Management OData IIS 拡張 Web サービスの作成</span><span class="sxs-lookup"><span data-stu-id="a032b-148">Creating a Management OData IIS Extension Web Service</span></span>](./creating-a-management-odata-web-service.md)