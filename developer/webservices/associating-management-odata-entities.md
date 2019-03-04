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
# <a name="associating-management-odata-entities"></a>Management OData エンティティを関連付ける

2 つの異なる管理 OData エンティティ間のアソシエーションを作成すると便利です。 Management OData サービスでした管理カテゴリで構成されている製品のカタログは、エンティティが存在し、エンティティの定義など`Product`と`Category`します。 これら 2 つのエンティティを関連付けることによって、クライアントは、web サービスに 1 つの要求のカテゴリのすべての製品に関する情報を取得できます。

エンティティ間のアソシエーションを作成する方法を示すサンプルをダウンロードできます[関連付けサンプル](https://code.msdn.microsoft.com:443/windowsdesktop/Association-sample-0f0fa87e)します。

## <a name="creating-the-association-in-the-resource-schema-file"></a>リソースのスキーマ ファイルの関連付けを作成します。

次の MOF は、2 つのエンティティを定義します。 それらの間のアソシエーションを作成します。

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

`Category`クラスは、そのカテゴリに属する製品の名前の配列であるプロパティを定義します。

2 つのエンティティに関連付けるでクラスを定義する必要があります、`Association`サービスのリソースのスキーマ MOF ファイル内の属性。 クラスは、関連付けられている、という 2 つのエンティティを定義する必要があります`ends`アソシエーションの。 次の例では、カテゴリおよび製品エンティティ間のアソシエーションを定義するクラスの定義を示します。

```csharp
[Association]
class ProductCategory {
Category ref theCategory;
Product ref theProducts;
}
```

カテゴリのクラスの Products プロパティの宣言を変更することも必要があります。 使用する、`AssociationClass`プロパティがアソシエーションの一方の end であることを指定するキーワード。 プロパティは、文字列の配列ではなく、個別のエンティティへの参照としても定義する必要があります。 使用してこれを行う、`ref`キーワード。 次の例では、関連付けのプロパティ定義を示します。

```csharp
class Sample_Category {

[key] string CategoryName;

[AssociationClass("Sample_ProductCategory"),ToEnd("theProducts")]
Sample_Product ref AssociatedProducts[];
};
```

最後に、プロパティ定義を追加することによって、アソシエーションの他方の end を宣言する必要があります、`Product`クラス。 これは、配列または単一のエンティティに対する参照です。 各製品が 1 つだけのカテゴリに属する、仮定の定義であるようです。

```csharp
class Sample_Product {

[key] string ProductName;
[AssociationClass("Sample_ProductCategory"),ToEnd("theCategory")]
Sample_Category ref AssociatedCategory;
};
```

アソシエーションの 2 つの end を表すプロパティには、ナビゲーション プロパティが呼び出されます。

#### <a name="steps-for-associating-entities-in-the-resource-schema-file"></a>リソースのスキーマ ファイル内のエンティティに関連付けるための手順

- 使用して、クラスとの関連付けを定義、`Association`キーワード。

- アソシエーションの end を定義するには、関連付けられているエンティティのプロパティを修飾するために、関連クラスのキーワードを使用します。

## <a name="creating-the-association-in-the-resource-mapping-xml-file"></a>リソース マッピング XML ファイルで、関連付けの作成

リソース マッピング XML ファイル内のアソシエーションをマップするときに考慮すべき 3 つの異なる場合があります。

#### <a name="determining-how-to-associate-entities-in-the-resource-mapping-file"></a>リソースのマッピング ファイル内のエンティティに関連付ける方法を決定します。

- ナビゲーション プロパティが存在する場合、基になります。 .NET framework の型とプロパティが含まれている外部キーには、明示的なマッピングは必要ありません。

- 基になる .NET Framework 型にナビゲーション プロパティが存在しない場合は、関連付けられているインスタンスのキーの一覧を取得するコマンドレットを指定する必要があります。 追加することで、これを行う、`Association`下で入れ子になった要素、`CmdletImplementation`を定義する要素を次の要素、`cmdlets`の他の CRUD コマンド。

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

- ナビゲーション プロパティが、基になる .NET Framework の型に存在の外部キーではなくオブジェクトのインスタンスが含まれている場合、コマンドレットは (Windows PowerShell 関数またはスクリプトを記述する) を作成する必要があります、外部キーを取得します。 リソースのマッピング ファイルでそのコマンドレットを指定します。 たとえば、キーを取得するスクリプトは、次のようになります。

  ```
  Param(
      [string] $Key
      )

  (get-category $key).AssociatedProducts

  ```

  リソースのマッピング ファイル内の XML は次のようになります。

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

- 関連付けられているエンティティを取得するコマンドレットを指定するだけでなく、コマンドレットを追加し、参照をコレクションから削除を指定することもできます。 次の例では、追加 ProductToCategory と削除 ProductFromCategory コマンドレットが存在する (が定義することも、スクリプトまたは前の例のように関数で)。

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

## <a name="querying-associated-entities"></a>関連付けられているエンティティのクエリを実行します。

クライアントは、特定のクエリを作成して、エンティティに関連付けられているインスタンスの一覧を取得できます。

#### <a name="constructing-queries-for-associated-entities"></a>関連付けられているエンティティのクエリを作成します。

- クライアントは、関連付けられた製品を取得せず、カテゴリの詳細を要求できます。 たとえば、次の要求がの詳細を取得、`food`カテゴリ。

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')
  ```

  カテゴリの関連する製品を取得する (ただし、それ自体には、カテゴリ、クライアントの詳細がないが、要求でナビゲーション プロパティを指定します。

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/AssociatedProducts
  ```

- 製品の Url のみを取得する、`$links`要求の修飾子です。

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')/$links/AssociatedProducts
  ```

- クライアントを使用してカテゴリの詳細と、関連付けられている製品の両方を取得できます、`$expand`修飾子。

  ```
  http://localhost:7000/MODataSvc/sample.svc/Category('food')?$expand=AssociatedProducts
  ```

## <a name="see-also"></a>参照

[Management OData IIS 拡張機能の Web サービスを作成します。](./creating-a-management-odata-web-service.md)