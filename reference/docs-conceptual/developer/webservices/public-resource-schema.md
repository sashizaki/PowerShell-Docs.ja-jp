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
# <a name="public-resource-schema"></a>パブリック リソース スキーマ

管理 OData は、MOF を使用してリソースとそのプロパティを定義します。 管理 OData エンティティのプロパティは、基になるコマンドレットによって返されるマネージ型のプロパティに直接対応します。

## <a name="defining-a-resource"></a>リソースの定義

各リソースは、Windows PowerShell コマンドレットによって返されるオブジェクトに対応します。 パブリックリソース MOF ファイルでは、クラスを宣言することによってリソースを定義します。 クラスは、オブジェクトのプロパティに対応するプロパティで構成されます。 たとえば、次の例では、system.string[クラスは](/dotnet/api/System.Diagnostics.Process)次の MOF で表されています。

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

各プロパティ名の前にはデータ型が付きます。 この例のデータ型は、.NET Framework のプリミティブな CLR データ型に対応していますが、プロパティは、後で説明する他のリソースや複合型への参照にすることもできます。

@No__t-0 修飾子は、プロパティがリソースインスタンスを一意に識別するために使用されることを示します。 1つのリソースに複数のキーを含めることができます。

@No__t-0 修飾子は、プロパティが必須であることを示します。 プロパティに `Key` 修飾子が付いている場合、必須と見なされ、`Required` 修飾子は必要ありません。

### <a name="complex-data-types"></a>複合データ型

エンティティのプロパティには、複合データ型を含めることができます。 複合データ型は、C プログラミング言語の構造体と同様に、他の型で構成される型です。 次の例に示すように、複合型は、MOF ファイルで @no__t 0 修飾子を持つクラスとして宣言されます。

```csharp
[ComplexType]
class PswsTest_ProcessModule
{
    String ModuleName;
    String FileName;
};
```

エンティティプロパティを複合型として宣言するには、複合型の名前を含む、`EmbeddedInstance` 修飾子を持つ @no__t 0 型として宣言します。 次の例は、前の例で宣言した @no__t 0 型のプロパティの宣言を示しています。

```csharp
[Required, EmbeddedInstance("PswsTest_ProcessModule")] String Modules[];
```

### <a name="associating-entities"></a>エンティティの関連付け

アソシエーションと AssociationClass 修飾子を使用して、2つのエンティティを関連付けることができます。 詳細については、「 [Management OData エンティティの関連付け](./associating-management-odata-entities.md)」を参照してください。

### <a name="derived-types"></a>派生型

別の型から型を派生させることができます。 派生型は、明示的に派生したプロパティに加えて、派生元の型のすべてのプロパティを継承します。 次の例は、型宣言と、その型から派生した2つの型の宣言を示しています。

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