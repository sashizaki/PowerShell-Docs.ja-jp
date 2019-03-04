---
title: Management OData エンティティの関連付け |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 947a3add-3593-400d-8144-8b44c8adbe5e
caps.latest.revision: 5
ms.openlocfilehash: 44b718e024eb98ac562edb50076287a31f5edc6b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860828"
---
# <a name="associating-management-odata-entities"></a><span data-ttu-id="eeaa1-102">Management OData エンティティを関連付ける</span><span class="sxs-lookup"><span data-stu-id="eeaa1-102">Associating Management OData Entities</span></span>

<span data-ttu-id="eeaa1-103">2 つの異なる管理 OData エンティティ間のアソシエーションを作成すると便利です。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-103">It is often useful to create an association between two different Management OData entities.</span></span> <span data-ttu-id="eeaa1-104">Management OData サービスでした管理カテゴリで構成されている製品のカタログは、エンティティが存在し、エンティティの定義など`Product`と`Category`します。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-104">For example, a Management OData service could have entities that manage a catalogue of products that are organized in categories, and define the entities `Product` and `Category`.</span></span> <span data-ttu-id="eeaa1-105">これら 2 つのエンティティを関連付けることによって、クライアントは、web サービスに 1 つの要求のカテゴリのすべての製品に関する情報を取得できます。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-105">By associating these two entities, a client can get information about all of the products in a category with a single request to the web service.</span></span>

<span data-ttu-id="eeaa1-106">エンティティ間のアソシエーションを作成する方法を示すサンプルをダウンロードできます[関連付けサンプル](https://code.msdn.microsoft.com:443/windowsdesktop/Association-sample-0f0fa87e)します。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-106">A sample that shows how to create associations between entities can be downloaded at [Association sample](https://code.msdn.microsoft.com:443/windowsdesktop/Association-sample-0f0fa87e).</span></span>

## <a name="creating-the-association-in-the-resource-schema-file"></a><span data-ttu-id="eeaa1-107">リソースのスキーマ ファイルの関連付けを作成します。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-107">Creating the Association in the resource schema file</span></span>

<span data-ttu-id="eeaa1-108">次の MOF は、2 つのエンティティを定義します。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-108">The following MOF defines two entities.</span></span> <span data-ttu-id="eeaa1-109">それらの間のアソシエーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-109">We will create an association between them.</span></span>

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

<span data-ttu-id="eeaa1-110">`Category`クラスは、そのカテゴリに属する製品の名前の配列であるプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-110">The `Category` class defines a property that is an array of the names of the products that belong to that category.</span></span>

<span data-ttu-id="eeaa1-111">2 つのエンティティに関連付けるでクラスを定義する必要があります、`Association`サービスのリソースのスキーマ MOF ファイル内の属性。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-111">To associate two entities, you must define a class with the `Association` attribute in the resource schema MOF file for the service.</span></span> <span data-ttu-id="eeaa1-112">クラスは、関連付けられている、という 2 つのエンティティを定義する必要があります`ends`アソシエーションの。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-112">The class must define the two entities to be associated, called `ends` of the association.</span></span> <span data-ttu-id="eeaa1-113">次の例では、カテゴリおよび製品エンティティ間のアソシエーションを定義するクラスの定義を示します。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-113">The following example shows a definition of a class that defines an association between the Category and Products entities.</span></span>

```csharp
[Association]
class ProductCategory {
Category ref theCategory;
Product ref theProducts;
}
```

<span data-ttu-id="eeaa1-114">カテゴリのクラスの Products プロパティの宣言を変更することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-114">You must also change the declaration of the Products property in the Category class.</span></span> <span data-ttu-id="eeaa1-115">使用する、`AssociationClass`プロパティがアソシエーションの一方の end であることを指定するキーワード。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-115">You use the `AssociationClass` keyword to specify that the property is one end of the association.</span></span> <span data-ttu-id="eeaa1-116">プロパティは、文字列の配列ではなく、個別のエンティティへの参照としても定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-116">The property must also be defined as a reference to a separate entity, rather than an array of strings.</span></span> <span data-ttu-id="eeaa1-117">使用してこれを行う、`ref`キーワード。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-117">You do this by using the `ref` keyword.</span></span> <span data-ttu-id="eeaa1-118">次の例では、関連付けのプロパティ定義を示します。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-118">The following example shows the property definition for the association.</span></span>

```csharp
class Sample_Category {

[key] string CategoryName;

[AssociationClass("Sample_ProductCategory"),ToEnd("theProducts")]
Sample_Product ref AssociatedProducts[];
};
```

<span data-ttu-id="eeaa1-119">最後に、プロパティ定義を追加することによって、アソシエーションの他方の end を宣言する必要があります、`Product`クラス。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-119">Finally, you must declare the other end of the association by adding a property definition to the `Product` class.</span></span> <span data-ttu-id="eeaa1-120">これは、配列または単一のエンティティに対する参照です。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-120">This is a reference to either an array or to a single entity.</span></span> <span data-ttu-id="eeaa1-121">各製品が 1 つだけのカテゴリに属する、仮定の定義であるようです。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-121">Assuming that each product belongs to only one category, the definition would be as follows.</span></span>

```csharp
class Sample_Product {

[key] string ProductName;
[AssociationClass("Sample_ProductCategory"),ToEnd("theCategory")]
Sample_Category ref AssociatedCategory;
};
```

<span data-ttu-id="eeaa1-122">アソシエーションの 2 つの end を表すプロパティには、ナビゲーション プロパティが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-122">The properties that represent the two ends of the association are called navigation properties.</span></span>

#### <a name="steps-for-associating-entities-in-the-resource-schema-file"></a><span data-ttu-id="eeaa1-123">リソースのスキーマ ファイル内のエンティティに関連付けるための手順</span><span class="sxs-lookup"><span data-stu-id="eeaa1-123">Steps for associating entities in the resource schema file</span></span>

- <span data-ttu-id="eeaa1-124">使用して、クラスとの関連付けを定義、`Association`キーワード。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-124">Define the association as a class by using the `Association` keyword.</span></span>

- <span data-ttu-id="eeaa1-125">アソシエーションの end を定義するには、関連付けられているエンティティのプロパティを修飾するために、関連クラスのキーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-125">Define the ends of the association by using the AssociationClass keyword to qualify properties of the associated entities.</span></span>

## <a name="creating-the-association-in-the-resource-mapping-xml-file"></a><span data-ttu-id="eeaa1-126">リソース マッピング XML ファイルで、関連付けの作成</span><span class="sxs-lookup"><span data-stu-id="eeaa1-126">Creating the association in the resource mapping XML file</span></span>

<span data-ttu-id="eeaa1-127">リソース マッピング XML ファイル内のアソシエーションをマップするときに考慮すべき 3 つの異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-127">There are three different cases to consider when mapping an association in the resource mapping XML file.</span></span>

#### <a name="determining-how-to-associate-entities-in-the-resource-mapping-file"></a><span data-ttu-id="eeaa1-128">リソースのマッピング ファイル内のエンティティに関連付ける方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-128">Determining how to associate entities in the resource mapping file</span></span>

- <span data-ttu-id="eeaa1-129">ナビゲーション プロパティが存在する場合、基になります。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-129">If the navigation property is present in the underlying.</span></span> <span data-ttu-id="eeaa1-130">.NET framework の型とプロパティが含まれている外部キーには、明示的なマッピングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-130">.NET Framework type, and that property contains foreign keys, no explicit mapping is necessary.</span></span>

- <span data-ttu-id="eeaa1-131">基になる .NET Framework 型にナビゲーション プロパティが存在しない場合は、関連付けられているインスタンスのキーの一覧を取得するコマンドレットを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-131">If the navigation property does not exist in the underlying .NET Framework type, you must specify a cmdlet that retrieves the list of keys of the associated instances.</span></span> <span data-ttu-id="eeaa1-132">追加することで、これを行う、`Association`下で入れ子になった要素、`CmdletImplementation`を定義する要素を次の要素、`cmdlets`の他の CRUD コマンド。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-132">You do this by adding an `Association` element nested under the `CmdletImplementation` element, following the elements that define the `cmdlets` for the other CRUD commands.</span></span>

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

- <span data-ttu-id="eeaa1-133">ナビゲーション プロパティが、基になる .NET Framework の型に存在の外部キーではなくオブジェクトのインスタンスが含まれている場合、コマンドレットは (Windows PowerShell 関数またはスクリプトを記述する) を作成する必要があります、外部キーを取得します。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-133">If the navigation property does exist in the underlying .NET Framework type, but it contains object instances instead of foreign keys, then you must create a cmdlet (by writing a Windows PowerShell function or script) to retrieve the foreign keys.</span></span> <span data-ttu-id="eeaa1-134">リソースのマッピング ファイルでそのコマンドレットを指定します。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-134">You then specify that cmdlet in the resource mapping file.</span></span> <span data-ttu-id="eeaa1-135">たとえば、キーを取得するスクリプトは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-135">For example, the script to retrieve the keys would look like the following.</span></span>

  ```
  Param(
      [string] $Key
      )

  (get-category $key).AssociatedProducts

  ```

  <span data-ttu-id="eeaa1-136">リソースのマッピング ファイル内の XML は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-136">And the XML in the resource mapping file would look like the following.</span></span>

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

- <span data-ttu-id="eeaa1-137">関連付けられているエンティティを取得するコマンドレットを指定するだけでなく、コマンドレットを追加し、参照をコレクションから削除を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-137">In addition to specifying a cmdlet to retrieve the associated entities, you can also specify cmdlets to add and remove references from the collection.</span></span> <span data-ttu-id="eeaa1-138">次の例では、追加 ProductToCategory と削除 ProductFromCategory コマンドレットが存在する (が定義することも、スクリプトまたは前の例のように関数で)。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-138">The following example assumes that the Add-ProductToCategory and Remove-ProductFromCategory cmdlets exist (they can also be defined in a script or function as in the previous example).</span></span>

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

## <a name="querying-associated-entities"></a><span data-ttu-id="eeaa1-139">関連付けられているエンティティのクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-139">Querying associated entities</span></span>

<span data-ttu-id="eeaa1-140">クライアントは、特定のクエリを作成して、エンティティに関連付けられているインスタンスの一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-140">The client can retrieve a list of the instances associated with an entity by creating specific queries.</span></span>

#### <a name="constructing-queries-for-associated-entities"></a><span data-ttu-id="eeaa1-141">関連付けられているエンティティのクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-141">Constructing queries for associated entities</span></span>

- <span data-ttu-id="eeaa1-142">クライアントは、関連付けられた製品を取得せず、カテゴリの詳細を要求できます。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-142">A client can request the details of a category without retrieving its associated products.</span></span> <span data-ttu-id="eeaa1-143">たとえば、次の要求がの詳細を取得、`food`カテゴリ。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-143">For example, the following request gets details of the `food` category.</span></span>

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')
  ```

  <span data-ttu-id="eeaa1-144">カテゴリの関連する製品を取得する (ただし、それ自体には、カテゴリ、クライアントの詳細がないが、要求でナビゲーション プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-144">To get the associated products of the category (but not details of the category itself, the client specifies the navigation property in the request.</span></span>

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/AssociatedProducts
  ```

- <span data-ttu-id="eeaa1-145">製品の Url のみを取得する、`$links`要求の修飾子です。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-145">To retrieve only URLs of the products, use the `$links` qualifier in the request.</span></span>

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/$links/AssociatedProducts
  ```

- <span data-ttu-id="eeaa1-146">クライアントを使用してカテゴリの詳細と、関連付けられている製品の両方を取得できます、`$expand`修飾子。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-146">The client can get both the category details and its associated products by using the `$expand` qualifier.</span></span>

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')?$expand=AssociatedProducts
  ```

## <a name="see-also"></a><span data-ttu-id="eeaa1-147">参照</span><span class="sxs-lookup"><span data-stu-id="eeaa1-147">See Also</span></span>

[<span data-ttu-id="eeaa1-148">Management OData IIS 拡張機能の Web サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="eeaa1-148">Creating a Management OData IIS Extension Web Service</span></span>](./creating-a-management-odata-web-service.md)