---
description: セッションで使用される名前空間を指定できます。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/29/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: eaf983ad03676b4ac57a3b35bc44f72036da55b4
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222328"
---
# <a name="about-using"></a>使用について

## <a name="short-description"></a>概要
セッションで使用される名前空間を指定できます。

## <a name="long-description"></a>詳細説明

`using`ステートメントでは、セッションで使用する名前空間を指定できます。 名前空間を追加すると、.NET のクラスおよびメンバーの使用が簡略化され、スクリプトモジュールとアセンブリからクラスをインポートできるようになります。

ステートメントは、 `using` スクリプト内の他のステートメントの前に記述する必要があります。

ステートメントは、 `using` `using:` 変数のスコープ修飾子と混同しないようにしてください。 詳細については、「 [about_Remote_Variables](about_Remote_Variables.md)」を参照してください。

## <a name="syntax"></a>構文

型の解決に使用する .NET 名前空間を指定するには、次のようにします。

```
using namespace <.NET-namespace>
```

PowerShell モジュールからクラスを読み込むには、次のようにします。

```
using module <module-name>
```

.NET アセンブリから型をプリロードするには、次のようにします。

```
using assembly <.NET-assembly-path>
```

名前空間を指定すると、短い名前を使用して型を簡単に参照できます。

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

