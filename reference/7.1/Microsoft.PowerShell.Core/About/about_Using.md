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
# <a name="about-using"></a><span data-ttu-id="bb637-103">使用について</span><span class="sxs-lookup"><span data-stu-id="bb637-103">About Using</span></span>

## <a name="short-description"></a><span data-ttu-id="bb637-104">概要</span><span class="sxs-lookup"><span data-stu-id="bb637-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="bb637-105">セッションで使用される名前空間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb637-105">Allows you to indicate which namespaces are used in the session.</span></span>

## <a name="long-description"></a><span data-ttu-id="bb637-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="bb637-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="bb637-107">`using`ステートメントでは、セッションで使用する名前空間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb637-107">The `using` statement allows you to specify which namespaces are used in the session.</span></span> <span data-ttu-id="bb637-108">名前空間を追加すると、.NET のクラスおよびメンバーの使用が簡略化され、スクリプトモジュールとアセンブリからクラスをインポートできるようになります。</span><span class="sxs-lookup"><span data-stu-id="bb637-108">Adding namespaces simplifies usage of .NET classes and member and allows you to import classes from script modules and assemblies.</span></span>

<span data-ttu-id="bb637-109">ステートメントは、 `using` スクリプト内の他のステートメントの前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb637-109">The `using` statements must come before any other statements in a script.</span></span>

<span data-ttu-id="bb637-110">ステートメントは、 `using` `using:` 変数のスコープ修飾子と混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="bb637-110">The `using` statement should not be confused with the `using:` scope modifier for variables.</span></span> <span data-ttu-id="bb637-111">詳細については、「 [about_Remote_Variables](about_Remote_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb637-111">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="namespace-syntax"></a><span data-ttu-id="bb637-112">名前空間の構文</span><span class="sxs-lookup"><span data-stu-id="bb637-112">Namespace syntax</span></span>

<span data-ttu-id="bb637-113">型の解決に使用する .NET 名前空間を指定するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="bb637-113">To specify .NET namespaces from which to resolve types:</span></span>

```
using namespace <.NET-namespace>
```

<span data-ttu-id="bb637-114">名前空間を指定すると、短い名前を使用して型を簡単に参照できます。</span><span class="sxs-lookup"><span data-stu-id="bb637-114">Specifying a namespace makes it easier to reference types by their short names.</span></span>

## <a name="module-syntax"></a><span data-ttu-id="bb637-115">モジュールの構文</span><span class="sxs-lookup"><span data-stu-id="bb637-115">Module syntax</span></span>

<span data-ttu-id="bb637-116">PowerShell モジュールからクラスを読み込むには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="bb637-116">To load classes from a PowerShell module:</span></span>

```
using module <module-name>
```

<span data-ttu-id="bb637-117">の値には、 `<module-name>` モジュール名、モジュールの完全な指定、またはモジュールファイルへのパスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb637-117">The value of `<module-name>` can be a module name, a full module specification, or a path to a module file.</span></span>

<span data-ttu-id="bb637-118">`<module-name>`がパスの場合は、完全修飾パスまたは相対パスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="bb637-118">When `<module-name>` is a path, the path can be fully qualified or relative.</span></span> <span data-ttu-id="bb637-119">相対パスは、using ステートメントを含むスクリプトに対して相対的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="bb637-119">A relative path is resolved relative to the script that contains the using statement.</span></span>

<span data-ttu-id="bb637-120">`<module-name>`が名前またはモジュールの指定である場合、PowerShell は指定されたモジュールの **PSModulePath** を検索します。</span><span class="sxs-lookup"><span data-stu-id="bb637-120">When `<module-name>` is a name or module specification, PowerShell searches the **PSModulePath** for the specified module.</span></span>

<span data-ttu-id="bb637-121">モジュール仕様は、次のキーを持つハッシュテーブルです。</span><span class="sxs-lookup"><span data-stu-id="bb637-121">A module specification is a hash table that has the following keys.</span></span>

- <span data-ttu-id="bb637-122">`ModuleName` - **必須** モジュール名を指定します。</span><span class="sxs-lookup"><span data-stu-id="bb637-122">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="bb637-123">`GUID` - **省略可能** モジュールの GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="bb637-123">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="bb637-124">以下の3つのキーのいずれかを指定する **必要** もあります。</span><span class="sxs-lookup"><span data-stu-id="bb637-124">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="bb637-125">これらのキーを一緒に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bb637-125">These keys can't be used together.</span></span>
  - <span data-ttu-id="bb637-126">`ModuleVersion` -モジュールの許容される最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="bb637-126">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="bb637-127">`RequiredVersion` -モジュールの正確な必須バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="bb637-127">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="bb637-128">`MaximumVersion` -モジュールの許容される最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="bb637-128">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

## <a name="assembly-syntax"></a><span data-ttu-id="bb637-129">アセンブリ構文</span><span class="sxs-lookup"><span data-stu-id="bb637-129">Assembly syntax</span></span>

<span data-ttu-id="bb637-130">.NET アセンブリから型をプリロードするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="bb637-130">To preload types from a .NET assembly:</span></span>

```
using assembly <.NET-assembly-path>
```

<span data-ttu-id="bb637-131">アセンブリを読み込むと、解析時にそのアセンブリから .NET 型がスクリプトにプリロードされます。</span><span class="sxs-lookup"><span data-stu-id="bb637-131">Loading an assembly preloads .NET types from that assembly into a script at parse time.</span></span> <span data-ttu-id="bb637-132">これにより、プリロードされたアセンブリの型を使用する新しい PowerShell クラスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bb637-132">This allows you to create new PowerShell classes that use types from the preloaded assembly.</span></span>

<span data-ttu-id="bb637-133">新しい PowerShell クラスを作成しない場合は、 `Add-Type` 代わりにコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb637-133">If you are not creating new PowerShell classes, use the `Add-Type` cmdlet instead.</span></span> <span data-ttu-id="bb637-134">詳細については、「 [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb637-134">For more information, see [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span></span>

## <a name="examples"></a><span data-ttu-id="bb637-135">例</span><span class="sxs-lookup"><span data-stu-id="bb637-135">Examples</span></span>

### <a name="example-1---add-namespaces-for-typename-resolution"></a><span data-ttu-id="bb637-136">例 1-typename の解決のための名前空間を追加する</span><span class="sxs-lookup"><span data-stu-id="bb637-136">Example 1 - Add namespaces for typename resolution</span></span>

<span data-ttu-id="bb637-137">次のスクリプトは、"Hello World" 文字列の暗号化ハッシュを取得します。</span><span class="sxs-lookup"><span data-stu-id="bb637-137">The following script gets the cryptographic hash for the "Hello World" string.</span></span>

<span data-ttu-id="bb637-138">とでは、との間の参照が簡略化されていることに注意して `using namespace System.Text` `using namespace System.IO` `[UnicodeEncoding]` `System.Text` `[Stream]` `[MemoryStream]` `System.IO` ください。</span><span class="sxs-lookup"><span data-stu-id="bb637-138">Note how the `using namespace System.Text` and `using namespace System.IO` simplify the references to `[UnicodeEncoding]` in `System.Text` and `[Stream]` and to `[MemoryStream]` in `System.IO`.</span></span>

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

### <a name="example-2---load-classes-from-a-script-module"></a><span data-ttu-id="bb637-139">例 2-スクリプトモジュールからクラスを読み込む</span><span class="sxs-lookup"><span data-stu-id="bb637-139">Example 2 - Load classes from a script module</span></span>

<span data-ttu-id="bb637-140">この例では、次のクラスを定義する **Cardgames** という名前の PowerShell スクリプトモジュールを用意しています。</span><span class="sxs-lookup"><span data-stu-id="bb637-140">In this example, we have a PowerShell script module named **CardGames** that defines the following classes:</span></span>

- <span data-ttu-id="bb637-141">**CardGames。デッキ**</span><span class="sxs-lookup"><span data-stu-id="bb637-141">**CardGames.Deck**</span></span>
- <span data-ttu-id="bb637-142">**CardGames. カード**</span><span class="sxs-lookup"><span data-stu-id="bb637-142">**CardGames.Card**</span></span>

<span data-ttu-id="bb637-143">`Import-Module` また、ステートメントでは、モジュール `#requires` で定義されているモジュール関数、エイリアス、および変数のみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="bb637-143">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="bb637-144">クラスはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="bb637-144">Classes are not imported.</span></span> <span data-ttu-id="bb637-145">この `using module` コマンドは、モジュールをインポートし、クラス定義も読み込みます。</span><span class="sxs-lookup"><span data-stu-id="bb637-145">The `using module` command imports the module and also loads the class definitions.</span></span>

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a><span data-ttu-id="bb637-146">例 3-アセンブリからクラスを読み込む</span><span class="sxs-lookup"><span data-stu-id="bb637-146">Example 3 - Load classes from an assembly</span></span>

<span data-ttu-id="bb637-147">この例では、クラスを使用して新しい PowerShell クラスを作成できるように、アセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="bb637-147">This example loads an assembly so that its classes can be used to create new PowerShell classes.</span></span> <span data-ttu-id="bb637-148">次のスクリプトは、 **Directorycontext** クラスから派生した新しい PowerShell クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="bb637-148">The following script creates a new PowerShell class that is derived from **DirectoryContext** class.</span></span>

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
