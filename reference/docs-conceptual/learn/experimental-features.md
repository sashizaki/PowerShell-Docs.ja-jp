---
ms.date: 04/28/2020
title: PowerShell の試験的機能の使用
description: 現在使用できる試験的機能とその使用方法を示します。
ms.openlocfilehash: 72a4309d6eeede4cd2ff7c38ce8e99ce3ace30eb
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809188"
---
# <a name="using-experimental-features-in-powershell"></a><span data-ttu-id="64589-103">PowerShell の試験的機能の使用</span><span class="sxs-lookup"><span data-stu-id="64589-103">Using Experimental Features in PowerShell</span></span>

<span data-ttu-id="64589-104">PowerShell の試験的機能のサポートは、試験的機能を PowerShell または PowerShell モジュールの既存の安定した機能と共存させるためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="64589-104">The Experimental Features support in PowerShell provides a mechanism for experimental features to coexist with existing stable features in PowerShell or PowerShell modules.</span></span>

<span data-ttu-id="64589-105">試験的機能は、設計が未完成です。</span><span class="sxs-lookup"><span data-stu-id="64589-105">An experimental feature is one where the design is not finalized.</span></span> <span data-ttu-id="64589-106">この機能は、ユーザーがテストしてフィードバックを提供するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="64589-106">The feature is available for users to test and provide feedback.</span></span> <span data-ttu-id="64589-107">試験的機能が完成すると、設計の変更が破壊的変更になります。</span><span class="sxs-lookup"><span data-stu-id="64589-107">Once an experimental feature is finalized, the design changes become breaking changes.</span></span>

> [!CAUTION]
> <span data-ttu-id="64589-108">試験的機能は、変更が破壊的になる可能性があるため、運用環境で使用することは想定されていません。</span><span class="sxs-lookup"><span data-stu-id="64589-108">Experimental features aren't intended to be used in production since the changes are allowed to be breaking.</span></span> <span data-ttu-id="64589-109">試験的機能は正式にはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="64589-109">Experimental features are not officially supported.</span></span> <span data-ttu-id="64589-110">しかし、フィードバックとバグ レポートは歓迎いたします。</span><span class="sxs-lookup"><span data-stu-id="64589-110">However, we appreciate any feedback and bug reports.</span></span> <span data-ttu-id="64589-111">[GitHub ソース リポジトリ](https://github.com/PowerShell/PowerShell/issues/new/choose)でイシューを送信できます。</span><span class="sxs-lookup"><span data-stu-id="64589-111">You can file issues in the [GitHub source repository](https://github.com/PowerShell/PowerShell/issues/new/choose).</span></span>

<span data-ttu-id="64589-112">これらの機能を有効または無効にする方法の詳細については、「[about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64589-112">For more information about enabling or disabling these features, see [about_Experimental_Features](/powershell/module/microsoft.powershell.core/about/about_experimental_features).</span></span>

## <a name="available-features"></a><span data-ttu-id="64589-113">利用可能な機能</span><span class="sxs-lookup"><span data-stu-id="64589-113">Available features</span></span>

<span data-ttu-id="64589-114">この記事では、使用可能な試験的機能と、その機能の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="64589-114">This article describes the experimental features that are available and how to use the feature.</span></span>

|                            <span data-ttu-id="64589-115">名前</span><span class="sxs-lookup"><span data-stu-id="64589-115">Name</span></span>                            |   <span data-ttu-id="64589-116">6.2</span><span class="sxs-lookup"><span data-stu-id="64589-116">6.2</span></span>   |   <span data-ttu-id="64589-117">7.0</span><span class="sxs-lookup"><span data-stu-id="64589-117">7.0</span></span>   | <span data-ttu-id="64589-118">7.1 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="64589-118">7.1 (preview)</span></span> |
| ---------------------------------------------------------- | :-----: | :-----: | :-----------: |
| <span data-ttu-id="64589-119">PSTempDrive (PS 7.0 以降のメインストリーム)</span><span class="sxs-lookup"><span data-stu-id="64589-119">PSTempDrive (mainstream in PS 7.0+)</span></span>                        | &check; |         |               |
| <span data-ttu-id="64589-120">PSUseAbbreviationExpansion (PS 7.0 以降のメインストリーム)</span><span class="sxs-lookup"><span data-stu-id="64589-120">PSUseAbbreviationExpansion (mainstream in PS 7.0+)</span></span>         | &check; |         |               |
| <span data-ttu-id="64589-121">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="64589-121">PSCommandNotFoundSuggestion</span></span>                                | &check; | &check; |    &check;    |
| <span data-ttu-id="64589-122">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="64589-122">PSImplicitRemotingBatching</span></span>                                 | &check; | &check; |    &check;    |
| <span data-ttu-id="64589-123">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="64589-123">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span> |         | &check; |    &check;    |
| <span data-ttu-id="64589-124">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="64589-124">PSDesiredStateConfiguration.InvokeDscResource</span></span>              |         | &check; |    &check;    |
| <span data-ttu-id="64589-125">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="64589-125">PSNullConditionalOperators</span></span>                                 |         | &check; |    &check;    |
| <span data-ttu-id="64589-126">PSUnixFileStat (Windows 以外)</span><span class="sxs-lookup"><span data-stu-id="64589-126">PSUnixFileStat (non-Windows only)</span></span>                          |         | &check; |    &check;    |
| <span data-ttu-id="64589-127">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="64589-127">PSNativePSPathResolution</span></span>                                   |         |         |    &check;    |
| <span data-ttu-id="64589-128">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="64589-128">PSCultureInvariantReplaceOperator</span></span>                          |         |         |    &check;    |

## <a name="microsoftpowershellutilitypsmanagebreakpointsinrunspace"></a><span data-ttu-id="64589-129">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span><span class="sxs-lookup"><span data-stu-id="64589-129">Microsoft.PowerShell.Utility.PSManageBreakpointsInRunspace</span></span>

<span data-ttu-id="64589-130">`Debug-Runspace` コマンドレットと `Debug-Job` コマンドレットの **BreakAll** パラメーターを有効にすると、デバッガーをアタッチするときに PowerShell を現在の場所ですぐに中断するかどうかをユーザーが決定できます。</span><span class="sxs-lookup"><span data-stu-id="64589-130">Enables the **BreakAll** parameter on the `Debug-Runspace` and `Debug-Job` cmdlets to allow users to decide if they want PowerShell to break immediately in the current location when they attach a debugger.</span></span>

## <a name="pscommandnotfoundsuggestion"></a><span data-ttu-id="64589-131">PSCommandNotFoundSuggestion</span><span class="sxs-lookup"><span data-stu-id="64589-131">PSCommandNotFoundSuggestion</span></span>

<span data-ttu-id="64589-132">**CommandNotFoundException** 後にあいまい一致検索に基づいて、可能性のあるコマンドを推奨します。</span><span class="sxs-lookup"><span data-stu-id="64589-132">Recommends potential commands based on fuzzy matching search after a **CommandNotFoundException**.</span></span>

```powershell
PS> get
```

```Output
get: The term 'get' is not recognized as the name of a cmdlet, function, script file, or operable
program. Check the spelling of the name, or if a path was included, verify that the path is correct
and try again.

Suggestion [4,General]: The most similar commands are: set, del, ft, gal, gbp, gc, gci, gcm, gdr,
gcs.
```

## <a name="pscultureinvariantreplaceoperator"></a><span data-ttu-id="64589-133">PSCultureInvariantReplaceOperator</span><span class="sxs-lookup"><span data-stu-id="64589-133">PSCultureInvariantReplaceOperator</span></span>

<span data-ttu-id="64589-134">`-replace` 演算子ステートメントの左側のオペランドが文字列でない場合、そのオペランドは文字列に変換されます。</span><span class="sxs-lookup"><span data-stu-id="64589-134">When the left-hand operand in a `-replace` operator statement is not a string, that operand is converted to a string.</span></span>

<span data-ttu-id="64589-135">この機能が無効になっている場合、`-replace` 演算子は、カルチャに依存した文字列変換を行います。</span><span class="sxs-lookup"><span data-stu-id="64589-135">When this feature is disabled, the `-replace` operator does a culture-sensitive string conversion.</span></span>
<span data-ttu-id="64589-136">たとえば、カルチャがフランス語 (fr) に設定されている場合、`1.2` の値は文字列 `1,2` に変換されます。</span><span class="sxs-lookup"><span data-stu-id="64589-136">For example, if your culture is set to French (fr), the value `1.2` is converted to the string `1,2`.</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
12
PS> [cultureinfo]::CurrentCulture = 'en'
PS> 1.2 -replace ','
1.2
```

<span data-ttu-id="64589-137">機能が有効になっている場合:</span><span class="sxs-lookup"><span data-stu-id="64589-137">With the feature enabled:</span></span>

```powershell
PS> [cultureinfo]::CurrentCulture = 'fr'
PS> 1.2 -replace ','
1.2
```

## <a name="psdesiredstateconfigurationinvokedscresource"></a><span data-ttu-id="64589-138">PSDesiredStateConfiguration.InvokeDscResource</span><span class="sxs-lookup"><span data-stu-id="64589-138">PSDesiredStateConfiguration.InvokeDscResource</span></span>

<span data-ttu-id="64589-139">Windows 以外のシステムで MOF へのコンパイルを有効にし、LCM を使用せずに `Invoke-DSCResource` を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="64589-139">Enables compilation to MOF on non-Windows systems and enables the use of `Invoke-DSCResource` without an LCM.</span></span>

## <a name="psimplicitremotingbatching"></a><span data-ttu-id="64589-140">PSImplicitRemotingBatching</span><span class="sxs-lookup"><span data-stu-id="64589-140">PSImplicitRemotingBatching</span></span>

<span data-ttu-id="64589-141">この機能は、シェルで入力されたコマンドを検査します。すべてのコマンドが、単純なパイプラインを形成する暗黙のリモート処理プロキシ コマンドである場合は、コマンドがまとめられ、1 つのリモート パイプラインとして呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="64589-141">This feature examines the command typed in the shell, and if all the commands are implicit remoting proxy commands that form a simple pipeline, then the commands are batched together and invoked as a single remote pipeline.</span></span>

<span data-ttu-id="64589-142">例:</span><span class="sxs-lookup"><span data-stu-id="64589-142">Example:</span></span>

```powershell
# Create remote session and import TestIMod module
$s = nsn -host remoteMachine
icm $s { ipmo 'C:\Users\user\Documents\WindowsPowerShell\Modules\TestIMod\TestIMod.psd1' }
Import-PSSession $s -mod testimod

$maxProcs = 1000
$filter = 'pwsh','powershell*','wmi*'

# Without batching, this pipeline takes approximately 12 seconds to run
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 12
Milliseconds      : 463

# But with the batching experimental feature enabled, it takes approximately 0.20 seconds
Measure-Command { Get-AllProcesses -MaxCount $maxProcs | Select-Custom $filter | Group-Stuff $filter }
Days              : 0
Hours             : 0
Minutes           : 0
Seconds           : 0
Milliseconds      : 209
```

<span data-ttu-id="64589-143">前述のように、バッチ処理機能を有効にすると、3 つの暗黙的なリモート処理プロキシ コマンド (`Get-AllProcesses`、`Select-Custom`、`Group-Stuff`) がすべてリモート セッションで実行され、パイプラインからの結果がクライアントに返される唯一のデータになります。</span><span class="sxs-lookup"><span data-stu-id="64589-143">As seen above, with the batching feature enabled, all three implicit remoting proxy commands, `Get-AllProcesses`, `Select-Custom`, `Group-Stuff`, run in the remote session and the result from the pipeline is the only data returned to the client.</span></span> <span data-ttu-id="64589-144">これにより、クライアントとリモート セッションの間で送受信されるデータの量が減少し、オブジェクトのシリアル化と逆シリアル化の量も少なくなります。</span><span class="sxs-lookup"><span data-stu-id="64589-144">This decreases the amount of data sent back and forth between client and remote session, and also reduces the amount of object serialization and de-serialization.</span></span>

## <a name="psnativepspathresolution"></a><span data-ttu-id="64589-145">PSNativePSPathResolution</span><span class="sxs-lookup"><span data-stu-id="64589-145">PSNativePSPathResolution</span></span>

<span data-ttu-id="64589-146">FileSystem プロバイダーを使用する PSDrive パスがネイティブ コマンドに渡されると、解決されたファイル パスがネイティブ コマンドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="64589-146">If a PSDrive path that uses the FileSystem provider is passed to a native command, the resolved file path is passed to the native command.</span></span> <span data-ttu-id="64589-147">これは、`code temp:/test.txt` のようなコマンドが期待どおりに動作することを意味します。</span><span class="sxs-lookup"><span data-stu-id="64589-147">This means a command like `code temp:/test.txt` now works as expected.</span></span>

<span data-ttu-id="64589-148">また、Windows の `~` で始まるパスは、完全なパスに解決され、ネイティブ コマンドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="64589-148">Also, on Windows, if the path starts with `~`, that is resolved to the full path and passed to the native command.</span></span> <span data-ttu-id="64589-149">どちらの場合も、パスは、関連するオペレーティング システムのディレクトリ区切り記号に正規化されます。</span><span class="sxs-lookup"><span data-stu-id="64589-149">In both cases, the path is normalized to the directory separators for the relevant operating system.</span></span>

- <span data-ttu-id="64589-150">パスが PSDrive または `~` (Windows) でない場合、パスの正規化は行われません</span><span class="sxs-lookup"><span data-stu-id="64589-150">If the path is not a PSDrive or `~` (on Windows), then path normalization doesn't occur</span></span>
- <span data-ttu-id="64589-151">パスが単一引用符で囲まれている場合、そのパスは解決されず、リテラルとして扱われます</span><span class="sxs-lookup"><span data-stu-id="64589-151">If the path is in single quotes, then it's not resolved and treated as literal</span></span>

## <a name="psnullconditionaloperators"></a><span data-ttu-id="64589-152">PSNullConditionalOperators</span><span class="sxs-lookup"><span data-stu-id="64589-152">PSNullConditionalOperators</span></span>

<span data-ttu-id="64589-153">Null 条件付きメンバー アクセス演算子 (`?.` および `?[]`) 用の新しい演算子が導入されています。</span><span class="sxs-lookup"><span data-stu-id="64589-153">Introduces new operators for Null conditional member access operators - `?.` and `?[]`.</span></span> <span data-ttu-id="64589-154">Null メンバー アクセス演算子は、スカラー型および配列型で使用できます。</span><span class="sxs-lookup"><span data-stu-id="64589-154">Null member access operators can used on scalar types and array types.</span></span> <span data-ttu-id="64589-155">変数が null でない場合は、アクセスされるメンバーの値を返します。</span><span class="sxs-lookup"><span data-stu-id="64589-155">Return the value of the accessed member if the variable is not null.</span></span> <span data-ttu-id="64589-156">変数の値が null の場合は、null を返します。</span><span class="sxs-lookup"><span data-stu-id="64589-156">If the value of the variable is null, then return null.</span></span>

```powershell
$x = $null
${x}?.propname
${x?}?.propname

${x}?[0]
${x?}?[0]

${x}?.MyMethod()
```

<span data-ttu-id="64589-157">プロパティ `propname` にアクセスし、`$x` が null でない場合にのみ値が返されます。</span><span class="sxs-lookup"><span data-stu-id="64589-157">The property `propname` is accessed and it's value is returned only if `$x` is not null.</span></span> <span data-ttu-id="64589-158">同様に、インデクサーは `$x` が null でない場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="64589-158">Similarly, the indexer is used only if `$x` is not null.</span></span> <span data-ttu-id="64589-159">`$x` が null の場合、null が返されます。</span><span class="sxs-lookup"><span data-stu-id="64589-159">If `$x` is null, then null is returned.</span></span>

<span data-ttu-id="64589-160">`?.` 演算子と `?[]` 演算子はメンバー アクセス演算子であり、変数名と演算子の間にスペースを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="64589-160">The `?.` and `?[]` operators are member access operators and do not allow a space in between the variable name and the operator.</span></span>

<span data-ttu-id="64589-161">PowerShell では変数名の一部として `?` が許可されるため、変数名と演算子の間にスペースを使用せずに演算子を使用する場合はあいまいさを解消する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64589-161">Since PowerShell allows `?` as part of the variable name, disambiguation is required when the operators are used without a space between the variable name and the operator.</span></span> <span data-ttu-id="64589-162">あいまいさを解消するには、変数が `${x?}?.propertyName` や `${y}?[0]` などの変数名を囲む `{}` を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64589-162">To disambiguate, the variables must use `{}` around the variable name like: `${x?}?.propertyName` or `${y}?[0]`.</span></span>

## <a name="pstempdrive"></a><span data-ttu-id="64589-163">PSTempDrive</span><span class="sxs-lookup"><span data-stu-id="64589-163">PSTempDrive</span></span>

<span data-ttu-id="64589-164">ユーザーの一時ディレクトリ パスにマップされた `TEMP:` PSDrive を作成します。</span><span class="sxs-lookup"><span data-stu-id="64589-164">Creates the `TEMP:` PSDrive mapped to user's temporary directory path.</span></span>

> [!NOTE]
> <span data-ttu-id="64589-165">この機能は試験段階から移行され、PowerShell 7 以降のメインストリーム機能になりました。</span><span class="sxs-lookup"><span data-stu-id="64589-165">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>

## <a name="psunixfilestat"></a><span data-ttu-id="64589-166">PSUnixFileStat</span><span class="sxs-lookup"><span data-stu-id="64589-166">PSUnixFileStat</span></span>

<span data-ttu-id="64589-167">この機能では、Unix の **stat** API のデータをファイル システム プロバイダーの出力に含めて、より Unix に近いファイル リストを容易に作成できる新しい動作が提供されます。</span><span class="sxs-lookup"><span data-stu-id="64589-167">This feature provides new behavior to include data from the Unix **stat** API in the output of the file system provider to facilitate a more Unix-like file listing.</span></span> <span data-ttu-id="64589-168">これにより、基になる Unix 型システムの `stat(2)` API の共通式を含む **UnixStat** という名前のファイル システム プロバイダーに新しいメモ プロパティが追加されます。</span><span class="sxs-lookup"><span data-stu-id="64589-168">It adds a new note property in the filesystem provider named **UnixStat** that includes a common expression of the `stat(2)` API from the underlying Unix type system.</span></span>

<span data-ttu-id="64589-169">`Get-ChildItem` からの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="64589-169">The output from `Get-ChildItem` should look something like this:</span></span>

```powershell
PS> dir | select -first 4 -skip 5


    Directory: /Users/jimtru/src/github/forks/JamesWTruher/PowerShell-1

UnixMode   User      Group           LastWriteTime        Size Name
--------   ----      -----           -------------        ---- ----
drwxr-xr-x jimtru    staff        10/23/2019 13:16         416 test
drwxr-xr-x jimtru    staff         11/8/2019 10:37         896 tools
-rw-r--r-- jimtru    staff         11/8/2019 10:37      112858 build.psm1
-rw-r--r-- jimtru    staff         11/8/2019 10:37      201297 CHANGELOG.md
```

## <a name="psuseabbreviationexpansion"></a><span data-ttu-id="64589-170">PSUseAbbreviationExpansion</span><span class="sxs-lookup"><span data-stu-id="64589-170">PSUseAbbreviationExpansion</span></span>

<span data-ttu-id="64589-171">この機能により、省略されたコマンドレットと関数のタブ補完が可能になります。</span><span class="sxs-lookup"><span data-stu-id="64589-171">This feature enables tab-completion of abbreviated cmdlets and functions:</span></span>

<span data-ttu-id="64589-172">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="64589-172">For example:</span></span>

- <span data-ttu-id="64589-173">`i-psdf<tab>` は `Import-PowerShellDataFile` を返します。</span><span class="sxs-lookup"><span data-stu-id="64589-173">`i-psdf<tab>` returns `Import-PowerShellDataFile`.</span></span>
- <span data-ttu-id="64589-174">`u-akvmssdr<tab>` は `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval` を返します。</span><span class="sxs-lookup"><span data-stu-id="64589-174">`u-akvmssdr<tab>` returns `Undo-AzKeyVaultManagedStorageSasDefinitionRemoval`</span></span>

<span data-ttu-id="64589-175">これは、タブ補完 (対話型使用) に対してのみ機能するため、`i-psdf` はスクリプト内で有効なコマンドレット名ではありません。</span><span class="sxs-lookup"><span data-stu-id="64589-175">This only works for tab completion (interactive use), so `i-psdf` is not a valid cmdlet name in a script.</span></span>

> [!NOTE]
> <span data-ttu-id="64589-176">この機能は試験段階から移行され、PowerShell 7 以降のメインストリーム機能になりました。</span><span class="sxs-lookup"><span data-stu-id="64589-176">This feature has moved out of the experimental phase and is a mainstream feature in PowerShell 7 and higher.</span></span>
