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
ms.openlocfilehash: a9204ca7b28fc5792ef9bd18f6b0b24964de7386
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859548"
---
# <a name="public-resource-schema"></a>パブリック リソース スキーマ

Management OData では、MOF を使用して、リソースとそのプロパティを定義します。 Management OData エンティティのプロパティは、基になるコマンドレットによって返されるマネージ型のプロパティに直接対応します。

## <a name="defining-a-resource"></a>リソースを定義します。

各リソースは、Windows PowerShell コマンドレットによって返されるオブジェクトに対応します。 Publc リソースの MOF ファイルでは、クラスを宣言することで、リソースを定義します。 クラスは、オブジェクトのプロパティに対応するプロパティで構成されます。 たとえば、次の例で、 [System.Diagnostics.Process](/dotnet/api/System.Diagnostics.Process)クラスは、次の MOF で表されます。

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

各プロパティ名には、データ型が付きます。 この例では、データ型が .NET のフレームワークでのプリミティブの CLR データ型に対応していますが、プロパティは他のリソースまたは複合型は、どちらも後で説明への参照にもできます。

`Key`修飾子は、リソースのインスタンスを一意に識別するプロパティを使用することを示します。 リソースは、1 つ以上のキーを持つことができます。

`Required`修飾子は、プロパティが必要であることを示します。 プロパティが付いた場合、`Key`修飾子が必要になることと見なされます、`Required`修飾子が必要ではありません。

### <a name="complex-data-types"></a>複合データ型

エンティティのプロパティは、複雑なデータ型を持つことができます。 複雑なデータ型は、C プログラミング言語で構造体のような他の種類で構成されている型です。 複合型がでクラスとして、MOF ファイルで宣言されている、`ComplexType`修飾子は、次の例に示すようにします。

```csharp
[ComplexType]
class PswsTest_ProcessModule
{
    String ModuleName;
    String FileName;
};
```

宣言としてエンティティ プロパティとして複合型を宣言する、`string`の種類を`EmbeddedInstance`複合型の名前を含む修飾子。 次の例 hshows プロパティの宣言の`PswsTest_ProcessModule`前の例で宣言された型。

```csharp
[Required, EmbeddedInstance("PswsTest_ProcessModule")] String Modules[];
```

### <a name="associating-entities"></a>エンティティの関連付け

アソシエーションおよび AssocationClass の修飾子を使用して、2 つのエンティティを関連付けることができます。 詳細については、次を参照してください。 [Management OData エンティティを関連付ける](./associating-management-odata-entities.md)します。

### <a name="derived-types"></a>派生型

別の型から型を派生させることができます。 派生型では、そのプロパティを明示的に派生した派生元である型のプロパティのすべてを継承します。 次の例では、型宣言し、その型から派生した 2 つの型の宣言を示します。

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