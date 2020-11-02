---
ms.date: 07/29/2020
title: PowerShell 5.0 の新しい言語機能
description: PowerShell 5.0 では、他のオブジェクト指向プログラミング言語のように、形式的構文とセマンティクスを使って、クラスや他のユーザー定義型を定義する機能が追加されました。
ms.openlocfilehash: 31ff54ba6f2800a0680c1a2db3832ca97246973d
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663308"
---
# <a name="new-language-features-in-powershell-50"></a>PowerShell 5.0 の新しい言語機能

PowerShell 5.0 では、他のオブジェクト指向プログラミング言語のように、形式的構文とセマンティクスを使って、クラスや他のユーザー定義型を定義する機能が追加されました。 開発者や IT プロフェッショナルがより広範なユース ケースで PowerShell を採用できるようにし、PowerShell アーティファクト (DSC リソースなど) の開発を簡素化し、管理面の対応を促進することがその目標です。

PowerShell 5.0 では、PowerShell に次の新しい言語要素が導入されています。

### <a name="class-keyword"></a>class キーワード

`class` キーワードでは新しいクラスを定義します。 これは、真の .NET Framework 型です。 クラス メンバーはパブリックですが、モジュール スコープ内でのみパブリックです。 型名を文字列として参照することはできません (たとえば、`New-Object` は機能しません)。このリリースでは、クラスが定義されているスクリプトまたはモジュール ファイルの外で type リテラル (`[MyClass]` など) を使用することはできません。

```powershell
class MyClass
{
    ...
}
```

### <a name="enum-keyword-and-enumerations"></a>enum キーワードおよび列挙

区切り文字として改行文字を使用する `enum` キーワードのサポートが追加されました。 現時点では、列挙子自体に関して列挙子を定義することはできません。 ただし、次の例に示すように、別の列挙型に関して列挙型を初期化することはできます。 また、基本データ型を指定することはできません。基本データ型は常に `[int]` です。

```powershell
enum Color2
{
    Yellow = [Color]::Blue
}
```

列挙子の値は、解析時定数である必要があります。 呼び出されたコマンドの結果に、それを設定することはできません。

```powershell
enum MyEnum
{
    Enum1
    Enum2
    Enum3 = 42
    Enum4 = [int]::MaxValue
}
```

次の例に示すように、enum では算術演算がサポートされます。

```powershell
enum SomeEnum { Max = 42 }
enum OtherEnum { Max = [SomeEnum]::Max + 1 }
```

### <a name="import-dscresource"></a>Import-DscResource

`Import-DscResource` は真の動的キーワードです。 PowerShell では、 **DscResource** 属性を含むクラスを探して、指定されたモジュールのルート モジュールを解析します。

### <a name="implementingassembly"></a>ImplementingAssembly

新しいフィールド **ImplementingAssembly** が **ModuleInfo** に追加されました。 これは、スクリプトでクラスが定義されている場合はスクリプト モジュールに作成された動的アセンブリに設定されるか、またはバイナリ モジュールの読み込み済みアセンブリに設定されます。 **ModuleType** が **Manifest** の場合は設定されません。

**ImplementingAssembly** フィールドのリフレクションでは、モジュール内のリソースが検出されます。 これは、PowerShell または他の管理言語で記述されたリソースを検出できることを意味します。

## <a name="further-reading"></a>関連項目

- [about_Classes](/powershell/module/microsoft.powershell.core/about/about_classes)
- [about_Enum](/powershell/module/microsoft.powershell.core/about/about_enum)
- [about_Classes_and_DSC](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc)
