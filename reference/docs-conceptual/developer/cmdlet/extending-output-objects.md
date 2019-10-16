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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369721"
---
# <a name="extending-output-objects"></a>出力オブジェクトを拡張する

型ファイル (types.ps1xml) を使用して、コマンドレット、関数、およびスクリプトによって返される .NET Framework オブジェクトを拡張できます。 型ファイルは、既存のオブジェクトにプロパティとメソッドを追加できる XML ベースのファイルです。 たとえば、Windows PowerShell は types.ps1xml ファイルを提供します。これにより、既存の複数の .NET Framework オブジェクトに要素が追加されます。 Types.ps1xml ファイルは、Windows PowerShell インストールディレクトリ (`$pshome`) にあります。 独自の型ファイルを作成して、それらのオブジェクトをさらに拡張したり、他のオブジェクトを拡張したりすることができます。 型ファイルを使用してオブジェクトを拡張すると、そのオブジェクトのすべてのインスタンスが新しい要素で拡張されます。

## <a name="extending-the-systemarray-object"></a>System.string オブジェクトの拡張

次の例は、Windows PowerShell によっ[て types.ps1xml](/dotnet/api/System.Array)ファイル内の system.string オブジェクトがどのように拡張されるかを示しています。 既定では、 [array オブジェクトに](/dotnet/api/System.Array)は、配列内のオブジェクトの数を一覧表示する @no__t 1 つのプロパティがあります。 ただし、名前 "length" によってプロパティが明確に記述されていないため、Windows PowerShell は `Count` エイリアスプロパティを追加します。このプロパティには、`Length` プロパティと同じ値が表示されます。 次の XML は、`Count` プロパティを system.string[型に追加します。](/dotnet/api/System.Array)

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

この新しいエイリアスプロパティを表示するには、次の例に示すように、任意の配列で[Get メンバー](/powershell/module/Microsoft.PowerShell.Utility/Get-Member)コマンドを使用します。

```powershell
Get-Member -InputObject (1,2,3,4)
```

コマンドを実行すると、次の結果が返されます。
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
@No__t-0 プロパティまたは `Length` プロパティを使用して、配列内のオブジェクトの数を確認できます。 たとえば、次のようになります。

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

## <a name="custom-types-files"></a>カスタム型ファイル

カスタム型ファイルを作成するには、まず既存の型ファイルをコピーします。 新しいファイルには任意の名前を付けることができますが、ファイル名の拡張子は types.ps1xml である必要があります。 ファイルをコピーすると、Windows PowerShell にアクセスできる任意のディレクトリに新しいファイルを配置できますが、ファイルを Windows PowerShell インストールディレクトリ (`$pshome`) またはインストールディレクトリのサブディレクトリに配置すると便利です。

独自の拡張型をファイルに追加するには、拡張する各オブジェクトの types 要素を追加します。 次のトピックでは例を紹介します。

- プロパティとプロパティセットの追加の詳細については、「[拡張プロパティ](./extending-properties-for-objects.md)」を参照してください。

- メソッドの追加の詳細については、「[拡張メソッド](./defining-default-methods-for-objects.md)」を参照してください。

- メンバーセットの追加の詳細については、「[拡張メンバーセット](./defining-default-member-sets-for-objects.md)」を参照してください。

独自の拡張型を定義したら、次のいずれかの方法を使用して拡張オブジェクトを使用できるようにします。

- 拡張型ファイルを現在のセッションで使用できるようにするには、[更新-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData)コマンドレットを使用して、新しいファイルを追加します。 型を他の型のファイル (types.ps1xml ファイルを含む) で定義されている型よりも優先する場合は、[更新プログラムの TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData)コマンドレットの `PrependData` パラメーターを使用します。
- 拡張型ファイルを今後のすべてのセッションで使用できるようにするには、モジュールに型ファイルを追加するか、現在のセッションをエクスポートするか、または[更新-TypeData](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData)コマンドを Windows PowerShell プロファイルに追加します。

## <a name="signing-types-files"></a>署名の種類ファイル

XML にはスクリプトブロックを含めることができるため、改ざんを防ぐために型ファイルをデジタル署名する必要があります。 デジタル署名の追加の詳細については、「 [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing) 」を参照してください。

## <a name="see-also"></a>参照

[オブジェクトの既定のプロパティの定義](./extending-properties-for-objects.md)

[オブジェクトの既定のメソッドの定義](./defining-default-methods-for-objects.md)

[オブジェクトの既定のメンバーセットの定義](./defining-default-member-sets-for-objects.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
