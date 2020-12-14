---
description: セッションで使用される名前空間を指定できます。
Locale: en-US
ms.date: 11/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: bbea815f93ba503fcce550dec28736630fec5a51
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "94890765"
---
# <a name="about-using"></a>使用について

## <a name="short-description"></a>概要
セッションで使用される名前空間を指定できます。

## <a name="long-description"></a>詳細説明

`using`ステートメントでは、セッションで使用する名前空間を指定できます。 名前空間を追加すると、.NET のクラスおよびメンバーの使用が簡略化され、スクリプトモジュールとアセンブリからクラスをインポートできるようになります。

ステートメントは、 `using` スクリプト内の他のステートメントの前に記述する必要があります。

ステートメントは、 `using` `using:` 変数のスコープ修飾子と混同しないようにしてください。 詳細については、「 [about_Remote_Variables](about_Remote_Variables.md)」を参照してください。

## <a name="namespace-syntax"></a>名前空間の構文

型の解決に使用する .NET 名前空間を指定するには、次のようにします。

```
using namespace <.NET-namespace>
```

名前空間を指定すると、短い名前を使用して型を簡単に参照できます。

## <a name="module-syntax"></a>モジュールの構文

PowerShell モジュールからクラスを読み込むには、次のようにします。

```
using module <module-name>
```

の値には、 `<module-name>` モジュール名、モジュールの完全な指定、またはモジュールファイルへのパスを指定できます。

`<module-name>`がパスの場合は、完全修飾パスまたは相対パスを指定できます。 相対パスは、using ステートメントを含むスクリプトに対して相対的に解決されます。

`<module-name>`が名前またはモジュールの指定である場合、PowerShell は指定されたモジュールの **PSModulePath** を検索します。

モジュール仕様は、次のキーを持つハッシュテーブルです。

- `ModuleName` - **必須** モジュール名を指定します。
- `GUID` - **省略可能** モジュールの GUID を指定します。
- 以下の3つのキーのいずれかを指定する **必要** もあります。 これらのキーを一緒に使用することはできません。
  - `ModuleVersion` -モジュールの許容される最小バージョンを指定します。
  - `RequiredVersion` -モジュールの正確な必須バージョンを指定します。
  - `MaximumVersion` -モジュールの許容される最大バージョンを指定します。

## <a name="assembly-syntax"></a>アセンブリ構文

.NET アセンブリから型をプリロードするには、次のようにします。

```
using assembly <.NET-assembly-path>
```

アセンブリを読み込むと、解析時にそのアセンブリから .NET 型がスクリプトにプリロードされます。 これにより、プリロードされたアセンブリの型を使用する新しい PowerShell クラスを作成できます。

新しい PowerShell クラスを作成しない場合は、 `Add-Type` 代わりにコマンドレットを使用します。 詳細については、「 [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type)」を参照してください。

## <a name="examples"></a>例

### <a name="example-1---add-namespaces-for-typename-resolution"></a>例 1-typename の解決のための名前空間を追加する

次のスクリプトは、"Hello World" 文字列の暗号化ハッシュを取得します。

とでは、との間の参照が簡略化されていることに注意して `using namespace System.Text` `using namespace System.IO` `[UnicodeEncoding]` `System.Text` `[Stream]` `[MemoryStream]` `System.IO` ください。

```powershell
using namespace System.Text
using namespace System.IO

[string]$string = "Hello World"
## Valid values are "SHA1", "SHA256", "SHA384", "SHA512", "MD5"
[string]$algorithm = "SHA256"

[byte[]]$stringbytes = [UnicodeEncoding]::Unicode.GetBytes($string)

[Stream]$memorystream = [MemoryStream]::new($stringbytes)
$hashfromstream = Get-FileHash -InputStream $memorystream `
  -Algorithm $algorithm
$hashfromstream.Hash.ToString()
```

### <a name="example-2---load-classes-from-a-script-module"></a>例 2-スクリプトモジュールからクラスを読み込む

この例では、次のクラスを定義する **Cardgames** という名前の PowerShell スクリプトモジュールを用意しています。

- **CardGames。デッキ**
- **CardGames. カード**

`Import-Module` また、ステートメントでは、モジュール `#requires` で定義されているモジュール関数、エイリアス、および変数のみをインポートします。 クラスはインポートされません。 この `using module` コマンドは、モジュールをインポートし、クラス定義も読み込みます。

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a>例 3-アセンブリからクラスを読み込む

この例では、クラスを使用して新しい PowerShell クラスを作成できるように、アセンブリを読み込みます。 次のスクリプトは、 **Directorycontext** クラスから派生した新しい PowerShell クラスを作成します。

```powershell
using assembly 'C:\Program Files\PowerShell\7\System.DirectoryServices.dll'
using namespace System.DirectoryServices.ActiveDirectory

class myDirectoryClass : System.DirectoryServices.ActiveDirectory.DirectoryContext
{

  [DirectoryContext]$domain

  myDirectoryClass([DirectoryContextType]$ctx) : base($ctx)
  {
    $this.domain = [DirectoryContext]::new([DirectoryContextType]$ctx)
  }

}

$myDomain = [myDirectoryClass]::new([DirectoryContextType]::Domain)
$myDomain
```

```Output
domain                                                    Name UserName ContextType
------                                                    ---- -------- -----------
System.DirectoryServices.ActiveDirectory.DirectoryContext                    Domain
```
