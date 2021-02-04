---
description: セッションで使用される名前空間を指定できます。
Locale: en-US
ms.date: 01/19/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_using?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Using
ms.openlocfilehash: 2ada269fd0ce6b34a5f7faccfddf47a799301eb9
ms.sourcegitcommit: 94d597c4fb38793bc49ca7610e2c9973b1e577c2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98619943"
---
# <a name="about-using"></a><span data-ttu-id="e97a3-103">使用について</span><span class="sxs-lookup"><span data-stu-id="e97a3-103">About Using</span></span>

## <a name="short-description"></a><span data-ttu-id="e97a3-104">概要</span><span class="sxs-lookup"><span data-stu-id="e97a3-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="e97a3-105">セッションで使用される名前空間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e97a3-105">Allows you to indicate which namespaces are used in the session.</span></span>

## <a name="long-description"></a><span data-ttu-id="e97a3-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="e97a3-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="e97a3-107">`using`ステートメントでは、セッションで使用する名前空間を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e97a3-107">The `using` statement allows you to specify which namespaces are used in the session.</span></span> <span data-ttu-id="e97a3-108">名前空間を追加すると、.NET のクラスおよびメンバーの使用が簡略化され、スクリプトモジュールとアセンブリからクラスをインポートできるようになります。</span><span class="sxs-lookup"><span data-stu-id="e97a3-108">Adding namespaces simplifies usage of .NET classes and member and allows you to import classes from script modules and assemblies.</span></span>

<span data-ttu-id="e97a3-109">ステートメントは、 `using` スクリプトまたはモジュール内の他のステートメントの前に記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e97a3-109">The `using` statements must come before any other statements in a script or module.</span></span> <span data-ttu-id="e97a3-110">パラメーターを含め、コメント解除されたステートメントの前には使用できません。</span><span class="sxs-lookup"><span data-stu-id="e97a3-110">No uncommented statement can precede it, including parameters.</span></span>

<span data-ttu-id="e97a3-111">ステートメントには、 `using` 変数を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="e97a3-111">The `using` statement must not contain any variables.</span></span>

<span data-ttu-id="e97a3-112">ステートメントは、 `using` `using:` 変数のスコープ修飾子と混同しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="e97a3-112">The `using` statement should not be confused with the `using:` scope modifier for variables.</span></span> <span data-ttu-id="e97a3-113">詳細については、「 [about_Remote_Variables](about_Remote_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e97a3-113">For more information, see [about_Remote_Variables](about_Remote_Variables.md).</span></span>

## <a name="namespace-syntax"></a><span data-ttu-id="e97a3-114">名前空間の構文</span><span class="sxs-lookup"><span data-stu-id="e97a3-114">Namespace syntax</span></span>

<span data-ttu-id="e97a3-115">型の解決に使用する .NET 名前空間を指定するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="e97a3-115">To specify .NET namespaces from which to resolve types:</span></span>

```
using namespace <.NET-namespace>
```

<span data-ttu-id="e97a3-116">名前空間を指定すると、短い名前を使用して型を簡単に参照できます。</span><span class="sxs-lookup"><span data-stu-id="e97a3-116">Specifying a namespace makes it easier to reference types by their short names.</span></span>

## <a name="module-syntax"></a><span data-ttu-id="e97a3-117">モジュールの構文</span><span class="sxs-lookup"><span data-stu-id="e97a3-117">Module syntax</span></span>

<span data-ttu-id="e97a3-118">PowerShell モジュールからクラスを読み込むには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="e97a3-118">To load classes from a PowerShell module:</span></span>

```
using module <module-name>
```

<span data-ttu-id="e97a3-119">の値には、 `<module-name>` モジュール名、モジュールの完全な指定、またはモジュールファイルへのパスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e97a3-119">The value of `<module-name>` can be a module name, a full module specification, or a path to a module file.</span></span>

<span data-ttu-id="e97a3-120">`<module-name>`がパスの場合は、完全修飾パスまたは相対パスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e97a3-120">When `<module-name>` is a path, the path can be fully qualified or relative.</span></span> <span data-ttu-id="e97a3-121">相対パスは、using ステートメントを含むスクリプトに対して相対的に解決されます。</span><span class="sxs-lookup"><span data-stu-id="e97a3-121">A relative path is resolved relative to the script that contains the using statement.</span></span>

> [!NOTE]
> <span data-ttu-id="e97a3-122">相対パスにスラッシュ () が含まれている場合 `/` 、PowerShell では、スクリプトの場所を基準とした相対パスではなく、現在の場所を基準とした相対パスが処理されます。</span><span class="sxs-lookup"><span data-stu-id="e97a3-122">When the relative path contains a forward slash (`/`), PowerShell treats the path as relative to the current location rather than relative to the script location.</span></span> <span data-ttu-id="e97a3-123">このバグは、PowerShell 7.1 で修正されています。</span><span class="sxs-lookup"><span data-stu-id="e97a3-123">This bug is fixed in PowerShell 7.1.</span></span>

<span data-ttu-id="e97a3-124">`<module-name>`が名前またはモジュールの指定である場合、PowerShell は指定されたモジュールの **PSModulePath** を検索します。</span><span class="sxs-lookup"><span data-stu-id="e97a3-124">When `<module-name>` is a name or module specification, PowerShell searches the **PSModulePath** for the specified module.</span></span>

<span data-ttu-id="e97a3-125">モジュール仕様は、次のキーを持つハッシュテーブルです。</span><span class="sxs-lookup"><span data-stu-id="e97a3-125">A module specification is a hash table that has the following keys.</span></span>

- <span data-ttu-id="e97a3-126">`ModuleName` - **必須** モジュール名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e97a3-126">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="e97a3-127">`GUID` - **省略可能** モジュールの GUID を指定します。</span><span class="sxs-lookup"><span data-stu-id="e97a3-127">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="e97a3-128">以下の3つのキーのいずれかを指定する **必要** もあります。</span><span class="sxs-lookup"><span data-stu-id="e97a3-128">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="e97a3-129">これらのキーを一緒に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e97a3-129">These keys can't be used together.</span></span>
  - <span data-ttu-id="e97a3-130">`ModuleVersion` -モジュールの許容される最小バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e97a3-130">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="e97a3-131">`RequiredVersion` -モジュールの正確な必須バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e97a3-131">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="e97a3-132">`MaximumVersion` -モジュールの許容される最大バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e97a3-132">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

<span data-ttu-id="e97a3-133">ステートメントは、 `using module` `ModuleToProcess` スクリプトモジュールまたはバイナリモジュールのルートモジュール () からクラスをインポートします。</span><span class="sxs-lookup"><span data-stu-id="e97a3-133">The `using module` statement imports classes from the root module (`ModuleToProcess`) of a script module or binary module.</span></span> <span data-ttu-id="e97a3-134">入れ子になったモジュールで定義されているクラスや、ドットソースのスクリプトで定義されているクラスをモジュールに常にインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e97a3-134">It does not consistently import classes defined in nested modules or classes defined in scripts that are dot-sourced into the module.</span></span> <span data-ttu-id="e97a3-135">モジュールの外部のユーザーが使用できるようにするクラスは、ルートモジュールで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e97a3-135">Classes that you want to be available to users outside of the module should be defined in the root module.</span></span>

<span data-ttu-id="e97a3-136">スクリプトモジュールの開発時には、コードに変更を加えた後、Force パラメーターを指定してを使用して新しいバージョンのモジュールを読み込むのが一般的です `Import-Module` 。 </span><span class="sxs-lookup"><span data-stu-id="e97a3-136">During development of a script module, it is common to make changes to the code then load the new version of the module using `Import-Module` with the **Force** parameter.</span></span> <span data-ttu-id="e97a3-137">これは、ルートモジュールの関数の変更に対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="e97a3-137">This works for changes to functions in the root module only.</span></span> <span data-ttu-id="e97a3-138">`Import-Module` では、入れ子になったモジュールは再読み込みされません。</span><span class="sxs-lookup"><span data-stu-id="e97a3-138">`Import-Module` does not reload any nested modules.</span></span> <span data-ttu-id="e97a3-139">また、更新されたクラスを読み込む方法はありません。</span><span class="sxs-lookup"><span data-stu-id="e97a3-139">Also, there is no way to load any updated classes.</span></span>

<span data-ttu-id="e97a3-140">最新バージョンを実行していることを確認するには、コマンドレットを使用してモジュールをアンロードする必要があり `Remove-Module` ます。</span><span class="sxs-lookup"><span data-stu-id="e97a3-140">To ensure that you are running the latest version, you must unload the module using the `Remove-Module` cmdlet.</span></span> <span data-ttu-id="e97a3-141">`Remove-Module` ルートモジュール、すべての入れ子になったモジュール、およびモジュールで定義されているすべてのクラスを削除します。</span><span class="sxs-lookup"><span data-stu-id="e97a3-141">`Remove-Module` removes the root module, all nested modules, and any classes defined in the modules.</span></span> <span data-ttu-id="e97a3-142">次に、およびステートメントを使用して、モジュールとクラスを再度読み込みます `Import-Module` `using module` 。</span><span class="sxs-lookup"><span data-stu-id="e97a3-142">Then you can reload the module and the classes using `Import-Module` and the `using module` statement.</span></span>

## <a name="assembly-syntax"></a><span data-ttu-id="e97a3-143">アセンブリ構文</span><span class="sxs-lookup"><span data-stu-id="e97a3-143">Assembly syntax</span></span>

<span data-ttu-id="e97a3-144">.NET アセンブリから型をプリロードするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="e97a3-144">To preload types from a .NET assembly:</span></span>

```
using assembly <.NET-assembly-path>
```

<span data-ttu-id="e97a3-145">アセンブリを読み込むと、解析時にそのアセンブリから .NET 型がスクリプトにプリロードされます。</span><span class="sxs-lookup"><span data-stu-id="e97a3-145">Loading an assembly preloads .NET types from that assembly into a script at parse time.</span></span> <span data-ttu-id="e97a3-146">これにより、プリロードされたアセンブリの型を使用する新しい PowerShell クラスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e97a3-146">This allows you to create new PowerShell classes that use types from the preloaded assembly.</span></span>

<span data-ttu-id="e97a3-147">新しい PowerShell クラスを作成しない場合は、 `Add-Type` 代わりにコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e97a3-147">If you are not creating new PowerShell classes, use the `Add-Type` cmdlet instead.</span></span> <span data-ttu-id="e97a3-148">詳細については、「 [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e97a3-148">For more information, see [Add-Type](xref:Microsoft.PowerShell.Utility.Add-Type).</span></span>

## <a name="examples"></a><span data-ttu-id="e97a3-149">使用例</span><span class="sxs-lookup"><span data-stu-id="e97a3-149">Examples</span></span>

### <a name="example-1---add-namespaces-for-typename-resolution"></a><span data-ttu-id="e97a3-150">例 1-typename の解決のための名前空間を追加する</span><span class="sxs-lookup"><span data-stu-id="e97a3-150">Example 1 - Add namespaces for typename resolution</span></span>

<span data-ttu-id="e97a3-151">次のスクリプトは、"Hello World" 文字列の暗号化ハッシュを取得します。</span><span class="sxs-lookup"><span data-stu-id="e97a3-151">The following script gets the cryptographic hash for the "Hello World" string.</span></span>

<span data-ttu-id="e97a3-152">とでは、との間の参照が簡略化されていることに注意して `using namespace System.Text` `using namespace System.IO` `[UnicodeEncoding]` `System.Text` `[Stream]` `[MemoryStream]` `System.IO` ください。</span><span class="sxs-lookup"><span data-stu-id="e97a3-152">Note how the `using namespace System.Text` and `using namespace System.IO` simplify the references to `[UnicodeEncoding]` in `System.Text` and `[Stream]` and to `[MemoryStream]` in `System.IO`.</span></span>

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

### <a name="example-2---load-classes-from-a-script-module"></a><span data-ttu-id="e97a3-153">例 2-スクリプトモジュールからクラスを読み込む</span><span class="sxs-lookup"><span data-stu-id="e97a3-153">Example 2 - Load classes from a script module</span></span>

<span data-ttu-id="e97a3-154">この例では、次のクラスを定義する **Cardgames** という名前の PowerShell スクリプトモジュールを用意しています。</span><span class="sxs-lookup"><span data-stu-id="e97a3-154">In this example, we have a PowerShell script module named **CardGames** that defines the following classes:</span></span>

- <span data-ttu-id="e97a3-155">**CardGames。デッキ**</span><span class="sxs-lookup"><span data-stu-id="e97a3-155">**CardGames.Deck**</span></span>
- <span data-ttu-id="e97a3-156">**CardGames. カード**</span><span class="sxs-lookup"><span data-stu-id="e97a3-156">**CardGames.Card**</span></span>

<span data-ttu-id="e97a3-157">`Import-Module` また、ステートメントでは、モジュール `#requires` で定義されているモジュール関数、エイリアス、および変数のみをインポートします。</span><span class="sxs-lookup"><span data-stu-id="e97a3-157">`Import-Module` and the `#requires` statement only import the module functions, aliases, and variables, as defined by the module.</span></span> <span data-ttu-id="e97a3-158">クラスはインポートされません。</span><span class="sxs-lookup"><span data-stu-id="e97a3-158">Classes are not imported.</span></span> <span data-ttu-id="e97a3-159">この `using module` コマンドは、モジュールをインポートし、クラス定義も読み込みます。</span><span class="sxs-lookup"><span data-stu-id="e97a3-159">The `using module` command imports the module and also loads the class definitions.</span></span>

```powershell
using module CardGames
using namespace CardGames

[Deck]$deck = [Deck]::new()
$deck.Shuffle()
[Card[]]$hand1 = $deck.Deal(5)
[Card[]]$hand2 = $deck.Deal(5)
[Card[]]$hand3 = $deck.Deal(5)
```

### <a name="example-3---load-classes-from-an-assembly"></a><span data-ttu-id="e97a3-160">例 3-アセンブリからクラスを読み込む</span><span class="sxs-lookup"><span data-stu-id="e97a3-160">Example 3 - Load classes from an assembly</span></span>

<span data-ttu-id="e97a3-161">この例では、クラスを使用して新しい PowerShell クラスを作成できるように、アセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="e97a3-161">This example loads an assembly so that its classes can be used to create new PowerShell classes.</span></span> <span data-ttu-id="e97a3-162">次のスクリプトは、 **Directorycontext** クラスから派生した新しい PowerShell クラスを作成します。</span><span class="sxs-lookup"><span data-stu-id="e97a3-162">The following script creates a new PowerShell class that is derived from **DirectoryContext** class.</span></span>

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
