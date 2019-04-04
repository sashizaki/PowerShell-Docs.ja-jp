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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861928"
---
# <a name="extending-output-objects"></a>出力オブジェクトを拡張する

型ファイル (.ps1xml) を使用して、コマンドレット、関数、およびスクリプトによって返される .NET Framework オブジェクトを拡張することができます。 型ファイルは XML ベースのファイルを既存のオブジェクトにプロパティとメソッドを追加することができます。 たとえば、Windows PowerShell は、Types.ps1xml ファイルをいくつかの既存の .NET Framework オブジェクトに要素を追加します。 を提供します。 Types.ps1xml ファイルは、Windows PowerShell インストール ディレクトリにあります (`$pshome`)。 さらにそれらのオブジェクトを拡張する、またはその他のオブジェクトを拡張する独自の種類ファイルを作成することができます。 型ファイルを使用してオブジェクトを拡張すると、新しい要素を持つオブジェクトの任意のインスタンスが拡張されます。

## <a name="extending-the-systemarray-object"></a>System.Array オブジェクトを拡張します。

次の例は、Windows PowerShell を拡張する方法を示しています、 [System.Array](/dotnet/api/System.Array) Types.ps1xml ファイル内のオブジェクト。 既定では、 [System.Array](/dotnet/api/System.Array)オブジェクトが、`Length`配列内のオブジェクトの数を一覧表示するプロパティ。 ただし、"length"という名前は、プロパティを明確に記載されていないため、Windows PowerShell が追加されます。、`Count`エイリアスのプロパティと同じ値を表示する、`Length`プロパティ。 次の XML を追加、`Count`プロパティを[System.Array](/dotnet/api/System.Array)型。

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

この新しいエイリアス プロパティを表示するには、使用、 [Get-member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member)任意の配列でコマンドを次の例に示すようにします。

```powershell
Get-Member -InputObject (1,2,3,4)
```

このコマンドは、次の結果を返します。
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
いずれかを使用することができます、`Count`プロパティまたは`Length`プロパティを配列内のオブジェクトの数を確認します。 たとえば、次のように入力します。

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

## <a name="custom-types-files"></a>カスタム型は、ファイル

カスタム型ファイルを作成するには、型の既存のファイルをコピーすることで開始します。 新しいファイルでは、任意の名前を使用できますが、.ps1xml ファイル名拡張子があります。 ファイルをコピーすると、Windows PowerShell にアクセスできる任意のディレクトリに新しいファイルを配置することができますが、Windows PowerShell のインストール ディレクトリにファイルを配置すると便利です (`$pshome`) またはインストール ディレクトリのサブディレクトリにします。

ファイルには、独自の拡張型を追加するには、拡張する各オブジェクトの型の要素を追加します。 次のトピックでは、例を示します。

- プロパティおよびプロパティ セットを追加する方法の詳細については、次を参照してください[拡張プロパティ。](./extending-properties-for-objects.md)

- メソッドを追加する方法の詳細については、[拡張メソッド](./defining-default-methods-for-objects.md)を参照してください。

- メンバーのセットを追加する方法の詳細については、[メンバーのセットを拡張](./defining-default-member-sets-for-objects.md)を参照してください。

独自の拡張型を定義した後は、次のメソッドのいずれかを使用して、拡張オブジェクトを使用できるようにします。

- で、拡張された種類のファイルを現在のセッションに使用できるようにするには使用、 [Update-typedata](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData)コマンドレットに新しいファイルを追加します。 他の型 (Types.ps1xml ファイルを含む) ファイルで定義されている型よりも優先する型を自分の場合、使用、`PrependData`のパラメーター、 [Update-typedata](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData)コマンドレット。
- で、拡張された種類のファイルを今後のすべてのセッションに使用できるように型ファイルをモジュールに追加する、現在のセッションをエクスポートまたは追加、 [Update-typedata](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData)コマンドを Windows PowerShell プロファイル。

## <a name="signing-types-files"></a>種類のファイルへの署名

ファイルの種類は、XML は、スクリプト ブロックを含めることができますので、改ざんを防ぐためにデジタル署名する必要があります。 デジタル署名を追加する方法の詳細については、次を参照してください[about_Signing。](/powershell/module/microsoft.powershell.core/about/about_signing)

## <a name="see-also"></a>参照

[オブジェクトの既定のプロパティを定義します。](./extending-properties-for-objects.md)

[オブジェクトの既定のメソッドを定義します。](./defining-default-methods-for-objects.md)

[オブジェクトの既定のメンバーのセットを定義します。](./defining-default-member-sets-for-objects.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
