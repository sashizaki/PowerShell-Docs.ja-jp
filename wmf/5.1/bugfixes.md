---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: WMF, PowerShell, セットアップ
title: WMF 5.1 のバグ修正
ms.openlocfilehash: 1e46d6d0419b3497450e6eaddbaa47456b004691
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="bug-fixes-in-wmf-51"></a><span data-ttu-id="008b3-103">WMF 5.1 のバグ修正</span><span class="sxs-lookup"><span data-stu-id="008b3-103">Bug Fixes in WMF 5.1#</span></span>

## <a name="bug-fixes"></a><span data-ttu-id="008b3-104">バグ修正</span><span class="sxs-lookup"><span data-stu-id="008b3-104">Bug fixes</span></span> ##

<span data-ttu-id="008b3-105">WMF 5.1 では、次の重要なバグが修正されました。</span><span class="sxs-lookup"><span data-stu-id="008b3-105">The following notable bugs are fixed in WMF 5.1:</span></span>

### <a name="module-auto-discovery-fully-honors-envpsmodulepath"></a><span data-ttu-id="008b3-106">モジュールの自動検出の完全な受け入れ `$env:PSModulePath`</span><span class="sxs-lookup"><span data-stu-id="008b3-106">Module auto-discovery fully honors `$env:PSModulePath`</span></span> ###

<span data-ttu-id="008b3-107">モジュールの自動検出 (コマンド呼び出し時に Import-Module を明示的に指定しないモジュールの自動的な読み込み) が、WMF 3 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="008b3-107">Module auto-discovery (loading modules automatically without an explicit Import-Module when calling a command) was introduced in WMF 3.</span></span>
<span data-ttu-id="008b3-108">導入時、PowerShell は `$env:PSModulePath` を使用する前に `$PSHome\Modules` のコマンドを確認していました。</span><span class="sxs-lookup"><span data-stu-id="008b3-108">When introduced, PowerShell checked for commands in `$PSHome\Modules` before using `$env:PSModulePath`.</span></span>

<span data-ttu-id="008b3-109">WMF 5.1 では、この動作が `$env:PSModulePath` を完全に受け入れるように変更されています。</span><span class="sxs-lookup"><span data-stu-id="008b3-109">WMF 5.1 changes this behavior to honor `$env:PSModulePath` completely.</span></span>
<span data-ttu-id="008b3-110">これにより、PowerShell によって提供されるコマンド (`Get-ChildItem` など) を定義するユーザー作成のモジュールを、自動的に読み込み、組み込みコマンドを正しくオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="008b3-110">This allows for a user-authored module that defines commands provided by PowerShell (e.g. `Get-ChildItem`) to be auto-loaded and correctly overriding the built-in command.</span></span>

### <a name="file-redirection-no-longer-hard-codes--encoding-unicode"></a><span data-ttu-id="008b3-111">ファイルのリダイレクトの非ハードコード化 `-Encoding Unicode`</span><span class="sxs-lookup"><span data-stu-id="008b3-111">File redirection no longer hard-codes `-Encoding Unicode`</span></span> ###

<span data-ttu-id="008b3-112">PowerShell のこれまでのすべてのバージョンでは、PowerShell が `-Encoding Unicode` を追加していたため、ファイル リダイレクト演算子 (`Get-ChildItem > out.txt` など) によって使用されるファイル エンコードを制御できませんでした。</span><span class="sxs-lookup"><span data-stu-id="008b3-112">In all previous versions of PowerShell, it was impossible to control the file encoding used by the file redirection operator, e.g. `Get-ChildItem > out.txt` because PowerShell added `-Encoding Unicode`.</span></span>

<span data-ttu-id="008b3-113">WMF 5.1 からは、`$PSDefaultParameterValues` を設定することによってリダイレクトのファイル エンコードを変更できます。</span><span class="sxs-lookup"><span data-stu-id="008b3-113">Starting with WMF 5.1, you can now change the file encoding of redirection by setting `$PSDefaultParameterValues`:</span></span>

```
$PSDefaultParameterValues["Out-File:Encoding"] = "Ascii"
```

### <a name="fixed-a-regression-in-accessing-members-of-systemreflectiontypeinfo"></a><span data-ttu-id="008b3-114">メンバーへのアクセスでのバグ再発の修正 `System.Reflection.TypeInfo`</span><span class="sxs-lookup"><span data-stu-id="008b3-114">Fixed a regression in accessing members of `System.Reflection.TypeInfo`</span></span> ###

<span data-ttu-id="008b3-115">WMF 5.0 で新しく発生したバグにより、`System.Reflection.RuntimeType` のメンバーにアクセスできませんでした (`[int].ImplementedInterfaces` など)。</span><span class="sxs-lookup"><span data-stu-id="008b3-115">A regression introduced in WMF 5.0 broke accessing members of `System.Reflection.RuntimeType`, e.g. `[int].ImplementedInterfaces`.</span></span>
<span data-ttu-id="008b3-116">WMF 5.1 ではこのバグが修正されています。</span><span class="sxs-lookup"><span data-stu-id="008b3-116">This bug has been fixed in WMF 5.1.</span></span>


### <a name="fixed-some-issues-with-com-objects"></a><span data-ttu-id="008b3-117">COM オブジェクトでのいくつかの問題の修正</span><span class="sxs-lookup"><span data-stu-id="008b3-117">Fixed some issues with COM objects</span></span> ###

<span data-ttu-id="008b3-118">WMF 5.0 では、COM オブジェクト上のメソッドを呼び出して COM オブジェクトのプロパティにアクセスする新しい COM バインダーが導入されました。</span><span class="sxs-lookup"><span data-stu-id="008b3-118">WMF 5.0 introduced a new COM binder for invoking methods on COM objects and accessing properties of COM objects.</span></span>
<span data-ttu-id="008b3-119">この新しいバインダーによりパフォーマンスが大幅に向上しましたが、バグもいくつか含まれていました。WMF 5.1 ではそれが修正されました。</span><span class="sxs-lookup"><span data-stu-id="008b3-119">This new binder improved performance significantly but also introduced some bugs which have been fixed in WMF 5.1.</span></span>

#### <a name="argument-conversions-were-not-always-performed-correctly"></a><span data-ttu-id="008b3-120">引数の変換が正常に実行されないことがあった</span><span class="sxs-lookup"><span data-stu-id="008b3-120">Argument conversions were not always performed correctly</span></span> ####

<span data-ttu-id="008b3-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="008b3-121">In the following example:</span></span>

```
$obj = New-Object -ComObject WScript.Shell
$obj.SendKeys([char]173)
```

<span data-ttu-id="008b3-122">SendKeys メソッドは string を受け取りますが、PowerShell は char を string に変換せず、変換を IDispatch::Invoke に延期していました。このメソッドは VariantChangeType を使用して変換を行います。この例では、結果として、期待される Volume.Mute キーではなくキー "1"、"7"、"3" が送られます。</span><span class="sxs-lookup"><span data-stu-id="008b3-122">The SendKeys method expects a string, but PowerShell did not convert the char to a string, deferring the conversion to IDispatch::Invoke, which uses VariantChangeType to do the conversion, which in this example resulted in sending the keys '1', '7', and '3' instead of the expected Volume.Mute key.</span></span>

#### <a name="enumerable-com-objects-not-always-handled-correctly"></a><span data-ttu-id="008b3-123">列挙可能な COM オブジェクトが正しく処理されないことがある</span><span class="sxs-lookup"><span data-stu-id="008b3-123">Enumerable COM objects not always handled correctly</span></span> ####

<span data-ttu-id="008b3-124">PowerShell は通常ほとんどの列挙可能なオブジェクトを列挙しますが、WMF 5.0 で発生したバグにより、IEnumerable を実装する COM オブジェクトの列挙が行われませんでした。</span><span class="sxs-lookup"><span data-stu-id="008b3-124">PowerShell normally enumerates most enumerable objects, but a regression introduced in WMF 5.0 prevented the enumeration of COM objects that implement IEnumerable.</span></span>  <span data-ttu-id="008b3-125">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="008b3-125">For example:</span></span>

```
function Get-COMDictionary
{
    $d = New-Object -ComObject Scripting.Dictionary
    $d.Add('a', 2)
    $d.Add('b', 2)
    return $d
}

$x = Get-COMDictionary
```

<span data-ttu-id="008b3-126">上の例では、WMF 5.0 が、キーと値のペアを列挙せずに、誤って Scripting.Dictionary をパイプラインに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="008b3-126">In the above example, WMF 5.0 incorrectly wrote the Scripting.Dictionary to the pipeline instead of enumerating the key/value pairs.</span></span>

<span data-ttu-id="008b3-127">この変更は、[Connect の問題 1752224](https://connect.microsoft.com/PowerShell/feedback/details/1752224) も解消します。</span><span class="sxs-lookup"><span data-stu-id="008b3-127">This change also addresses [issue 1752224 on Connect](https://connect.microsoft.com/PowerShell/feedback/details/1752224)</span></span>

### <a name="ordered-was-not-allowed-inside-classes"></a><span data-ttu-id="008b3-128">`[ordered]` がクラス内で許可されなかった</span><span class="sxs-lookup"><span data-stu-id="008b3-128">`[ordered]` was not allowed inside classes</span></span> ###

<span data-ttu-id="008b3-129">WMF 5.0 では、クラスで使用されるリテラル形を検証するクラスが導入されました。</span><span class="sxs-lookup"><span data-stu-id="008b3-129">WMF 5.0 introduced classes with validation of type literals used in classes.</span></span>
<span data-ttu-id="008b3-130">`[ordered]` はリテラル形のように見えますが、真の .Net 型ではありません。</span><span class="sxs-lookup"><span data-stu-id="008b3-130">`[ordered]` looks like a type literal but is not a true .NET type.</span></span>
<span data-ttu-id="008b3-131">WMF 5.0 は、クラスの内の `[ordered]` で誤ってエラーを報告しました。</span><span class="sxs-lookup"><span data-stu-id="008b3-131">WMF 5.0 incorrectly reported an error on `[ordered]` inside a class:</span></span>

```
class CThing
{
    [object] foo($i)
    {
        [ordered]@{ Thing = $i }
    }
}
```


### <a name="help-on-about-topics-with-multiple-versions-does-not-work"></a><span data-ttu-id="008b3-132">複数のバージョンがあるトピックについてのヘルプが機能しない</span><span class="sxs-lookup"><span data-stu-id="008b3-132">Help on About topics with multiple versions does not work</span></span> ###

<span data-ttu-id="008b3-133">WMF 5.1 より前では、複数のバージョンのモジュールがインストールされていて、そのすべてがヘルプ トピック (about_PSReadline など) を共有している場合、`help about_PSReadline` は複数のトピックを返し、実際のヘルプを表示する明確な方法はありませんでした。</span><span class="sxs-lookup"><span data-stu-id="008b3-133">Before WMF 5.1, if you had multiple versions of a module installed and they all shared a help topic, for example, about_PSReadline, `help about_PSReadline` would return multiple topics with no obvious way to view the real help.</span></span>

<span data-ttu-id="008b3-134">WMF 5.1 では、最新バージョンのトピックのヘルプを返すことでこれが解決されています。</span><span class="sxs-lookup"><span data-stu-id="008b3-134">WMF 5.1 fixes this by returning the help for the latest version of the topic.</span></span>

<span data-ttu-id="008b3-135">`Get-Help` では、必要なヘルプのバージョンを指定する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="008b3-135">`Get-Help` does not provide a way to specify which version you want help for.</span></span>
<span data-ttu-id="008b3-136">これを回避するには、モジュール ディレクトリに移動し、好みのエディターなどのツールで直接ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="008b3-136">To work around this, navigate to the modules directory and view the help directly with a tool like your favorite editor.</span></span>

### <a name="powershellexe-reading-from-stdin-stopped-working"></a><span data-ttu-id="008b3-137">STDIN からの powershell.exe の読み込みが停止する</span><span class="sxs-lookup"><span data-stu-id="008b3-137">powershell.exe reading from STDIN stopped working</span></span>

<span data-ttu-id="008b3-138">ネイティブ アプリから `powershell -command -` を使用して STDIN によるスクリプトで渡される PowerShell を実行していたが、コンソール ホストにほかの変更が加えられたため、これが壊れてしまいました。</span><span class="sxs-lookup"><span data-stu-id="008b3-138">Customers use `powershell -command -` from native apps to execute PowerShell passing in the script via STDIN unfortunately this was broken due to other changes it the console host.</span></span>

https://windowsserver.uservoice.com/forums/301869-powershell/suggestions/15854689-powershell-exe-command-is-broken-on-windows-10

### <a name="powershellexe-creates-spike-in-cpu-usage-on-startup"></a><span data-ttu-id="008b3-139">powershell.exe の起動時に CPU 使用率が急増する</span><span class="sxs-lookup"><span data-stu-id="008b3-139">powershell.exe creates spike in CPU usage on startup</span></span>

<span data-ttu-id="008b3-140">PowerShell は、ログインの遅延を回避するために WMI クエリを使用して、グループ ポリシーから起動したかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="008b3-140">PowerShell uses a WMI query to check if it was started via Group Policy to avoid causing delay in login.</span></span>
<span data-ttu-id="008b3-141">WMI クエリによって、最終的にシステムのすべてのプロセスに tzres.mui.dll が挿入されます。これは、WMI の Win32_Process クラスがローカルのタイムゾーン情報を取得しようとするためです。</span><span class="sxs-lookup"><span data-stu-id="008b3-141">The WMI query ends up injecting tzres.mui.dll into every process on the system since the WMI Win32_Process class attempts to retrieve local timezone information.</span></span>
<span data-ttu-id="008b3-142">結果的に、wmiprvse (WMI プロバイダーのホスト) で、大規模な CPU 使用率の急増が発生します。</span><span class="sxs-lookup"><span data-stu-id="008b3-142">This results in a large CPU spike in wmiprvse (the WMI provider host).</span></span>
<span data-ttu-id="008b3-143">修正プログラムでは、WMI を使用する代わりに、Win32 API 呼び出しを使用して同じ情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="008b3-143">Fix is to use Win32 API calls to get the same information instead of using WMI.</span></span>
