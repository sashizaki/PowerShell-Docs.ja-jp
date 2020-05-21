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
ms.openlocfilehash: 4849735bf412497f5590b109c67760b6a197cb2b
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561732"
---
# <a name="associating-management-odata-entities"></a>Management OData エンティティを関連付ける

多くの場合、2つの異なる管理 OData エンティティ間のアソシエーションを作成すると便利です。 たとえば、管理 OData サービスは、カテゴリで編成された製品のカタログを管理するエンティティを持つことができ、エンティティ `Product` とを定義し `Category` ます。 これら2つのエンティティを関連付けることにより、クライアントは、web サービスへの単一の要求を使用して、カテゴリ内のすべての製品に関する情報を取得できます。

エンティティ間の関連付けを作成する方法を示すサンプルは、[アソシエーションサンプル](https://code.msdn.microsoft.com:443/windowsdesktop/Association-sample-0f0fa87e)でダウンロードできます。

## <a name="creating-the-association-in-the-resource-schema-file"></a>リソーススキーマファイル内でのアソシエーションの作成

次の MOF は、2つのエンティティを定義します。 これらの間には、関連付けを作成します。

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

クラスは、 `Category` そのカテゴリに属する製品の名前の配列であるプロパティを定義します。

2つのエンティティを関連付けるには、 `Association` サービスのリソーススキーマ MOF ファイルで属性を使用してクラスを定義する必要があります。 クラスでは、アソシエーションのと呼ばれる、関連付ける2つのエンティティを定義する必要があり `ends` ます。 次の例は、カテゴリと製品のエンティティ間の関連付けを定義するクラスの定義を示しています。

```csharp
[Association]
class ProductCategory {
Category ref theCategory;
Product ref theProducts;
}
```

Category クラスの Products プロパティの宣言も変更する必要があります。 キーワードを使用して、 `AssociationClass` プロパティがアソシエーションの1つの end であることを指定します。 プロパティは、文字列の配列ではなく、別のエンティティへの参照としても定義する必要があります。 これを行うには、キーワードを使用し `ref` ます。 次の例は、アソシエーションのプロパティ定義を示しています。

```csharp
class Sample_Category {

[key] string CategoryName;

[AssociationClass("Sample_ProductCategory"),ToEnd("theProducts")]
Sample_Product ref AssociatedProducts[];
};
```

最後に、プロパティ定義をクラスに追加して、アソシエーションのもう一方の end を宣言する必要があり `Product` ます。 これは、配列または単一のエンティティへの参照です。 各製品が1つのカテゴリにのみ属していると仮定すると、定義は次のようになります。

```csharp
class Sample_Product {

[key] string ProductName;
[AssociationClass("Sample_ProductCategory"),ToEnd("theCategory")]
Sample_Category ref AssociatedCategory;
};
```

アソシエーションの2つの end を表すプロパティは、ナビゲーションプロパティと呼ばれます。

#### <a name="steps-for-associating-entities-in-the-resource-schema-file"></a>リソーススキーマファイル内のエンティティを関連付ける手順

- キーワードを使用して、アソシエーションをクラスとして定義し `Association` ます。

- アソシエーションの end を定義するには、AssociationClass キーワードを使用して、関連付けられているエンティティのプロパティを限定します。

## <a name="creating-the-association-in-the-resource-mapping-xml-file"></a>リソースマッピング XML ファイルでのアソシエーションの作成

リソースマッピング XML ファイル内のアソシエーションをマップする場合は、3つの異なるケースが考えられます。

#### <a name="determining-how-to-associate-entities-in-the-resource-mapping-file"></a>リソースマッピングファイル内のエンティティを関連付ける方法の決定

- ナビゲーションプロパティが基になるに存在する場合は。 .NET Framework 型、およびそのプロパティに外部キーが含まれているため、明示的なマッピングは必要ありません。

- ナビゲーションプロパティが基になる .NET Framework 型に存在しない場合は、関連付けられているインスタンスのキーの一覧を取得するコマンドレットを指定する必要があります。 これを行うには、 `Association` 要素の下に入れ子になった要素を追加し `CmdletImplementation` 、 `cmdlets` 他の CRUD コマンドのを定義する要素に従います。

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

- ナビゲーションプロパティが基になる .NET Framework 型に存在するが、外部キーではなくオブジェクトインスタンスが含まれている場合、外部キーを取得するには、Windows PowerShell の関数またはスクリプトを記述して、コマンドレットを作成する必要があります。 次に、そのコマンドレットをリソースマッピングファイルで指定します。 たとえば、キーを取得するスクリプトは、次のようになります。

  ```
  Param(
      [string] $Key
      )

  (get-category $key).AssociatedProducts

  ```

  また、リソースマッピングファイルの XML は次のようになります。

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

- 関連付けられているエンティティを取得するコマンドレットを指定するだけでなく、コマンドレットを指定してコレクションの参照を追加および削除することもできます。 次の例では、Add-ProductToCategory および Remove-Producttocategory コマンドレットが存在することを前提としています (前の例と同様に、スクリプトまたは関数でも定義できます)。

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

## <a name="querying-associated-entities"></a>関連エンティティのクエリ

クライアントは、特定のクエリを作成することによって、エンティティに関連付けられているインスタンスの一覧を取得できます。

#### <a name="constructing-queries-for-associated-entities"></a>関連付けられたエンティティに対するクエリの構築

- クライアントは、関連付けられている製品を取得せずに、カテゴリの詳細を要求できます。 たとえば、次の要求では、カテゴリの詳細が取得され `food` ます。

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')
  ```

  カテゴリの関連製品を取得する (ただし、カテゴリ自体の詳細は含まれません)、クライアントは要求のナビゲーションプロパティを指定します。

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/AssociatedProducts
  ```

- 製品の Url のみを取得するには、 `$links` 要求で修飾子を使用します。

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/$links/AssociatedProducts
  ```

- クライアントは、修飾子を使用して、カテゴリの詳細とそれに関連付けられている製品の両方を取得でき `$expand` ます。

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')?$expand=AssociatedProducts
  ```

## <a name="see-also"></a>参照

[Management OData IIS 拡張 Web サービスの作成](./creating-a-management-odata-web-service.md)
