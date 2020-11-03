---
description: セッションで使用される名前空間を指定できます。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/29/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: ff6b43c3af1deddb5cb1b4c2e2c86a2cc2cac5d4
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224944"
---
# <a name="about-using"></a><span data-ttu-id="c1786-104">使用について</span><span class="sxs-lookup"><span data-stu-id="c1786-104">About Using</span></span>

## <a name="short-description"></a><span data-ttu-id="c1786-105">概要</span><span class="sxs-lookup"><span data-stu-id="c1786-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="c1786-106">セッションで使用される名前空間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c1786-106">Allows you to indicate which namespaces are used in the session.</span></span>

## <a name="long-description"></a><span data-ttu-id="c1786-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="c1786-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="c1786-108">`using`ステートメントでは、セッションで使用する名前空間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="c1786-108">The `using` statement allows you to specify which namespaces are used in the session.</span></span> <span data-ttu-id="c1786-109">名前空間を追加すると、.NET のクラスおよびメンバーの使用が簡略化され、スクリプトモジュールとアセンブリからクラスをインポートできるようになります。</span><span class="sxs-lookup"><span data-stu-id="c1786-109">Adding namespaces simplifies usage of .NET classes and member and allows you to import classes from script modules and assemblies.</span></span>

<span data-ttu-id="c1786-110">ステートメントは、 `using` スクリプト内の他のステートメントの前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1786-110">The `using` statements must come before any other statements in a script.</span></span>

<span data-ttu-id="c1786-111">ステートメントは、 `using` `using:` 変数のスコープ修飾子と混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="c1786-111">The `using` statement should not be confused with the `using:` scope modifier for variables.</span></span> <span data-ttu-id="c1786-112">詳細については、「 [about_Remote_Variables](about_Remote_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1786-112">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="c1786-113">構文</span><span class="sxs-lookup"><span data-stu-id="c1786-113">Syntax</span></span>

<span data-ttu-id="c1786-114">型の解決に使用する .NET 名前空間を指定するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c1786-114">To specify .NET namespaces from which to resolve types:</span></span>

```
using namespace <.NET-namespace>
```

<span data-ttu-id="c1786-115">PowerShell モジュールからクラスを読み込むには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c1786-115">To load classes from a PowerShell module:</span></span>

```
using module <module-name>
```

<span data-ttu-id="c1786-116">.NET アセンブリから型をプリロードするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c1786-116">To preload types from a .NET assembly:</span></span>

```
using assembly <.NET-assembly-path>
using assembly <.NET-namespace>
```

<span data-ttu-id="c1786-117">名前空間を指定すると、短い名前を使用して型を簡単に参照できます。</span><span class="sxs-lookup"><span data-stu-id="c1786-117">Specifying a namespace makes it easier to reference types by their short names.</span></span>

<span data-ttu-id="c1786-118">アセンブリを読み込むと、解析時にそのアセンブリから .NET 型がスクリプトにプリロードされます。</span><span class="sxs-lookup"><span data-stu-id="c1786-118">Loading an assembly preloads .NET types from that assembly into a script at parse time.</span></span> <span data-ttu-id="c1786-119">これにより、プリロードされたアセンブリの型を使用する新しい PowerShell クラスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c1786-119">This allows you to create new PowerShell classes that use types from the preloaded assembly.</span></span>

<span data-ttu-id="c1786-120">Windows PowerShell 5.1 では、パス名または名前を指定してアセンブリを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="c1786-120">In Windows PowerShell 5.1 you can load the assembly by path name or by name.</span></span> <span data-ttu-id="c1786-121">名前を使用すると、PowerShell によって、.NET グローバルアセンブリキャッシュ (GAC) で、関連付けられているアセンブリが検索されます。</span><span class="sxs-lookup"><span data-stu-id="c1786-121">When you use the name, PowerShell searches the .NET Global Assembly Cache (GAC) for the associated assembly.</span></span>

<span data-ttu-id="c1786-122">新しい PowerShell クラスを作成しない場合は、 `Add-Type` 代わりにコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c1786-122">If you are not creating new PowerShell classes, use the `Add-Type` cmdlet instead.</span></span> <span data-ttu-id="c1786-123">詳細については、「 [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1786-123">For more information, see [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span></span>

## <a name="examples"></a><span data-ttu-id="c1786-124">例</span><span class="sxs-lookup"><span data-stu-id="c1786-124">Examples</span></span>

### <a name="example-1---add-namespaces-for-typename-resolution"></a><span data-ttu-id="c1786-125">例 1-typename の解決のための名前空間を追加する</span><span class="sxs-lookup"><span data-stu-id="c1786-125">Example 1 - Add namespaces for typename resolution</span></span>

<span data-ttu-id="c1786-126">次のスクリプトは、"Hello World" 文字列の暗号化ハッシュを取得します。</span><span class="sxs-lookup"><span data-stu-id="c1786-126">The following script gets the cryptographic hash for the "Hello World" string.</span></span>

<span data-ttu-id="c1786-127">とでは、との間の参照が簡略化されていることに注意して `using namespace System.Text` `using namespace System.IO` `[UnicodeEncoding]` `System.Text` `[Stream]` `[MemoryStream]` `System.IO` ください。</span><span class="sxs-lookup"><span data-stu-id="c1786-127">Note how the `using namespace System.Text` and `using namespace System.IO` simplify the references to `[UnicodeEncoding]` in `System.Text` and `[Stream]` and to `[MemoryStream]` in `System.IO`.</span></span>

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

### <a name="example-2---load-classes-from-a-script-module"></a><span data-ttu-id="c1786-128">例 2-スクリプトモジュールからクラスを読み込む</span><span class="sxs-lookup"><span data-stu-id="c1786-128">Example 2 - Load classes from a script module</span></span>

<span data-ttu-id="c1786-129">この例では、次のクラスを定義する **Cardgames** という名前の PowerShell スクリプトモジュールを用意しています。</span><span class="sxs-lookup"><span data-stu-id="c1786-129">In this example, we have a PowerShell script module named **CardGames** that defines the following classes:</span></span>

- <span data-ttu-id="c1786-130">**CardGames。デッキ**</span><span class="sxs-lookup"><span data-stu-id="c1786-130">**CardGames.Deck**</span></span>
- <span data-ttu-id="c1786-131">**CardGames. カード**</span><span class="sxs-lookup"><span data-stu-id="c1786-131">**CardGames.Card**</span></span>

<span data-ttu-id="c1786-132">`Import-Module` また、ステートメントでは、モジュール `#requires` で定義されているモジュール関数、エイリアス、および変数のみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="c1786-132">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="c1786-133">クラスはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="c1786-133">Classes are not imported.</span></span> <span data-ttu-id="c1786-134">この `using module` コマンドは、モジュールをインポートし、クラス定義も読み込みます。</span><span class="sxs-lookup"><span data-stu-id="c1786-134">The `using module` command imports the module and also loads the class definitions.</span></span>

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a><span data-ttu-id="c1786-135">例 3-アセンブリからクラスを読み込む</span><span class="sxs-lookup"><span data-stu-id="c1786-135">Example 3 - Load classes from an assembly</span></span>

<span data-ttu-id="c1786-136">この例では、クラスを使用して新しい PowerShell クラスを作成できるように、アセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="c1786-136">This example loads an assembly so that its classes can be used to create new PowerShell classes.</span></span> <span data-ttu-id="c1786-137">次のスクリプトは、 **Directorycontext** クラスから派生した新しい PowerShell クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c1786-137">The following script creates a new PowerShell class that is derived from **DirectoryContext** class.</span></span>

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
