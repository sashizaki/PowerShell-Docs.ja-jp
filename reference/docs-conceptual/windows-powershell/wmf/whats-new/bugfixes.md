---
ms.date: 06/12/2017
title: WMF 5.1 のバグ修正
description: この記事では、WMF 5.1 のリリースで修正されたバグの一覧を示します。
ms.openlocfilehash: 2673860852ecd6e0b6582f6f69076f8c463eeccc
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92660773"
---
# <a name="bug-fixes-in-wmf-51"></a><span data-ttu-id="8c978-103">WMF 5.1 のバグ修正</span><span class="sxs-lookup"><span data-stu-id="8c978-103">Bug Fixes in WMF 5.1</span></span>

## <a name="bug-fixes"></a><span data-ttu-id="8c978-104">バグの修正</span><span class="sxs-lookup"><span data-stu-id="8c978-104">Bug fixes</span></span>

<span data-ttu-id="8c978-105">WMF 5.1 では、次の重要なバグが修正されました。</span><span class="sxs-lookup"><span data-stu-id="8c978-105">The following notable bugs are fixed in WMF 5.1:</span></span>

### <a name="module-auto-discovery-fully-honors-psmodulepath"></a><span data-ttu-id="8c978-106">モジュールの自動検出で PSModulePath が完全に受け入れられる</span><span class="sxs-lookup"><span data-stu-id="8c978-106">Module auto-discovery fully honors PSModulePath</span></span>

<span data-ttu-id="8c978-107">モジュールの自動検出 (コマンド呼び出し時に Import-Module を明示的に指定しないモジュールの自動的な読み込み) が、WMF 3 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="8c978-107">Module auto-discovery (loading modules automatically without an explicit Import-Module when calling a command) was introduced in WMF 3.</span></span> <span data-ttu-id="8c978-108">導入時、PowerShell は `$env:PSModulePath` を使用する前に `$PSHome\Modules` のコマンドを確認していました。</span><span class="sxs-lookup"><span data-stu-id="8c978-108">When introduced, PowerShell checked for commands in `$PSHome\Modules` before using `$env:PSModulePath`.</span></span>

<span data-ttu-id="8c978-109">WMF 5.1 では、この動作が `$env:PSModulePath` を完全に受け入れるように変更されています。</span><span class="sxs-lookup"><span data-stu-id="8c978-109">WMF 5.1 changes this behavior to honor `$env:PSModulePath` completely.</span></span> <span data-ttu-id="8c978-110">これにより、PowerShell によって提供されるコマンド (`Get-ChildItem` など) を定義するユーザー作成のモジュールを、自動的に読み込み、組み込みコマンドを正しくオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="8c978-110">This allows for a user-authored module that defines commands provided by PowerShell (e.g. `Get-ChildItem`) to be auto-loaded and correctly overriding the built-in command.</span></span>

### <a name="file-redirection-no-longer-hard-codes--encoding-unicode"></a><span data-ttu-id="8c978-111">ファイルのリダイレクトで -Encoding Unicode がハードコーディングされなくなった</span><span class="sxs-lookup"><span data-stu-id="8c978-111">File redirection no longer hard-codes -Encoding Unicode</span></span>

<span data-ttu-id="8c978-112">PowerShell のこれまでのすべてのバージョンでは、ファイル リダイレクト演算子によって使用されるファイル エンコードを制御できませんでした。</span><span class="sxs-lookup"><span data-stu-id="8c978-112">In all previous versions of PowerShell, it was impossible to control the file encoding used by the file redirection operator.</span></span>

<span data-ttu-id="8c978-113">WMF 5.1 からは、`$PSDefaultParameterValues` を設定することによってリダイレクトのファイル エンコードを変更できます。</span><span class="sxs-lookup"><span data-stu-id="8c978-113">Starting with WMF 5.1, you can now change the file encoding of redirection by setting `$PSDefaultParameterValues`:</span></span>

```powershell
$PSDefaultParameterValues["Out-File:Encoding"] = "Ascii"
```

### <a name="fixed-a-regression-in-accessing-members-of-systemreflectiontypeinfo"></a><span data-ttu-id="8c978-114">System.Reflection.TypeInfo のメンバーへのアクセスでのバグ再発の修正</span><span class="sxs-lookup"><span data-stu-id="8c978-114">Fixed a regression in accessing members of System.Reflection.TypeInfo</span></span>

<span data-ttu-id="8c978-115">WMF 5.0 で新しく発生したバグにより、`System.Reflection.RuntimeType` のメンバーにアクセスできませんでした (`[int].ImplementedInterfaces` など)。</span><span class="sxs-lookup"><span data-stu-id="8c978-115">A regression introduced in WMF 5.0 broke accessing members of `System.Reflection.RuntimeType`, for example, `[int].ImplementedInterfaces`.</span></span> <span data-ttu-id="8c978-116">WMF 5.1 ではこのバグが修正されています。</span><span class="sxs-lookup"><span data-stu-id="8c978-116">This bug has been fixed in WMF 5.1.</span></span>

### <a name="fixed-some-issues-with-com-objects"></a><span data-ttu-id="8c978-117">COM オブジェクトでのいくつかの問題の修正</span><span class="sxs-lookup"><span data-stu-id="8c978-117">Fixed some issues with COM objects</span></span>

<span data-ttu-id="8c978-118">WMF 5.0 では、COM オブジェクト上のメソッドを呼び出して COM オブジェクトのプロパティにアクセスする新しい COM バインダーが導入されました。</span><span class="sxs-lookup"><span data-stu-id="8c978-118">WMF 5.0 introduced a new COM binder for invoking methods on COM objects and accessing properties of COM objects.</span></span> <span data-ttu-id="8c978-119">この新しいバインダーによりパフォーマンスが大幅に向上しましたが、バグもいくつか含まれていました。WMF 5.1 ではそれが修正されました。</span><span class="sxs-lookup"><span data-stu-id="8c978-119">This new binder improved performance significantly but also introduced some bugs which have been fixed in WMF 5.1.</span></span>

#### <a name="argument-conversions-were-not-always-performed-correctly"></a><span data-ttu-id="8c978-120">引数の変換が正常に実行されないことがあった</span><span class="sxs-lookup"><span data-stu-id="8c978-120">Argument conversions were not always performed correctly</span></span>

<span data-ttu-id="8c978-121">次の例では</span><span class="sxs-lookup"><span data-stu-id="8c978-121">In the following example:</span></span>

```powershell
$obj = New-Object -ComObject WScript.Shell
$obj.SendKeys([char]173)
```

<span data-ttu-id="8c978-122">**SendKeys** メソッドは string を受け取りますが、PowerShell では char が string に変換されず、変換は **IDispatch::Invoke** に延期されていました。このメソッドでは、 **VariantChangeType** を使って変換が行われます。</span><span class="sxs-lookup"><span data-stu-id="8c978-122">The **SendKeys** method expects a string, but PowerShell did not convert the char to a string, deferring the conversion to **IDispatch::Invoke** , which uses **VariantChangeType** to do the conversion.</span></span> <span data-ttu-id="8c978-123">この例では、結果として、期待される **Volume.Mute** キーではなくキー "1"、"7"、"3" が送られます。</span><span class="sxs-lookup"><span data-stu-id="8c978-123">In this example, this resulted in sending the keys '1', '7', and '3' instead of the expected **Volume.Mute** key.</span></span>

#### <a name="enumerable-com-objects-not-always-handled-correctly"></a><span data-ttu-id="8c978-124">列挙可能な COM オブジェクトが正しく処理されないことがある</span><span class="sxs-lookup"><span data-stu-id="8c978-124">Enumerable COM objects not always handled correctly</span></span>

<span data-ttu-id="8c978-125">PowerShell は通常ほとんどの列挙可能なオブジェクトを列挙しますが、WMF 5.0 で発生したバグにより、IEnumerable を実装する COM オブジェクトの列挙が行われませんでした。</span><span class="sxs-lookup"><span data-stu-id="8c978-125">PowerShell normally enumerates most enumerable objects, but a regression introduced in WMF 5.0 prevented the enumeration of COM objects that implement IEnumerable.</span></span> <span data-ttu-id="8c978-126">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="8c978-126">For example:</span></span>

```powershell
function Get-COMDictionary
{
    $d = New-Object -ComObject Scripting.Dictionary
    $d.Add('a', 2)
    $d.Add('b', 2)
    return $d
}

$x = Get-COMDictionary
```

<span data-ttu-id="8c978-127">上の例の WMF 5.0 では、キーと値のペアは列挙されず、誤って **Scripting.Dictionary** がパイプラインに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="8c978-127">In the above example, WMF 5.0 incorrectly wrote the **Scripting.Dictionary** to the pipeline instead of enumerating the key/value pairs.</span></span>

### <a name="ordered-was-not-allowed-inside-classes"></a><span data-ttu-id="8c978-128">[ordered] がクラス内で許可されなかった</span><span class="sxs-lookup"><span data-stu-id="8c978-128">[ordered] was not allowed inside classes</span></span>

<span data-ttu-id="8c978-129">WMF 5.0 では、クラスで使用されるリテラル形を検証するクラスが導入されました。</span><span class="sxs-lookup"><span data-stu-id="8c978-129">WMF 5.0 introduced classes with validation of type literals used in classes.</span></span> <span data-ttu-id="8c978-130">`[ordered]` はリテラル形のように見えますが、真の .Net 型ではありません。</span><span class="sxs-lookup"><span data-stu-id="8c978-130">`[ordered]` looks like a type literal but is not a true .NET type.</span></span> <span data-ttu-id="8c978-131">WMF 5.0 は、クラスの内の `[ordered]` で誤ってエラーを報告しました。</span><span class="sxs-lookup"><span data-stu-id="8c978-131">WMF 5.0 incorrectly reported an error on `[ordered]` inside a class:</span></span>

```powershell
class CThing
{
    [object] foo($i)
    {
        [ordered]@{ Thing = $i }
    }
}
```

### <a name="help-on-about-topics-with-multiple-versions-does-not-work"></a><span data-ttu-id="8c978-132">複数のバージョンがあるトピックについてのヘルプが機能しない</span><span class="sxs-lookup"><span data-stu-id="8c978-132">Help on About topics with multiple versions does not work</span></span>

<span data-ttu-id="8c978-133">WMF 5.1 より前では、複数のバージョンのモジュールがインストールされていて、そのすべてがヘルプ トピック (about_PSReadline など) を共有している場合、`help about_PSReadline` は複数のトピックを返し、実際のヘルプを表示する明確な方法はありませんでした。</span><span class="sxs-lookup"><span data-stu-id="8c978-133">Before WMF 5.1, if you had multiple versions of a module installed and they all shared a help topic, for example, about_PSReadline, `help about_PSReadline` would return multiple topics with no obvious way to view the real help.</span></span>

<span data-ttu-id="8c978-134">WMF 5.1 では、最新バージョンのトピックのヘルプを返すことでこれが解決されています。</span><span class="sxs-lookup"><span data-stu-id="8c978-134">WMF 5.1 fixes this by returning the help for the latest version of the topic.</span></span>

<span data-ttu-id="8c978-135">`Get-Help` では、必要なヘルプのバージョンを指定する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="8c978-135">`Get-Help` does not provide a way to specify which version you want help for.</span></span> <span data-ttu-id="8c978-136">これを回避するには、モジュール ディレクトリに移動し、好みのエディターなどのツールで直接ヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="8c978-136">To work around this, navigate to the modules directory and view the help directly with a tool like your favorite editor.</span></span>

### <a name="powershellexe-reading-from-stdin-stopped-working"></a><span data-ttu-id="8c978-137">STDIN からの powershell.exe の読み込みが停止する</span><span class="sxs-lookup"><span data-stu-id="8c978-137">powershell.exe reading from STDIN stopped working</span></span>

<span data-ttu-id="8c978-138">お客様はネイティブ アプリから `powershell -command -` を使って PowerShell を実行し、STDIN でスクリプトに渡していましたが、コンソール ホストでの他の変更によってこれが壊れていました。</span><span class="sxs-lookup"><span data-stu-id="8c978-138">Customers use `powershell -command -` from native apps to execute PowerShell passing in the script via STDIN unfortunately this was broken by other changes in the console host.</span></span>

<span data-ttu-id="8c978-139">これは、Windows 10 Anniversary Update のバージョン 5.1 で修正されます。</span><span class="sxs-lookup"><span data-stu-id="8c978-139">This is fixed for version 5.1 in the Windows 10 Anniversary Update.</span></span>

### <a name="powershellexe-creates-spike-in-cpu-usage-on-startup"></a><span data-ttu-id="8c978-140">powershell.exe の起動時に CPU 使用率が急増する</span><span class="sxs-lookup"><span data-stu-id="8c978-140">powershell.exe creates spike in CPU usage on startup</span></span>

<span data-ttu-id="8c978-141">PowerShell は、ログインの遅延を回避するために WMI クエリを使用して、グループ ポリシーから起動したかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8c978-141">PowerShell uses a WMI query to check if it was started via Group Policy to avoid causing delay in login.</span></span> <span data-ttu-id="8c978-142">WMI の **Win32_Process** クラスはローカル タイムゾーンの情報を取得しようとするため、WMI クエリによって、最終的にシステムのすべてのプロセスに tzres.mui.dll が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="8c978-142">The WMI query ends up injecting tzres.mui.dll into every process on the system since the WMI **Win32_Process** class attempts to retrieve local timezone information.</span></span> <span data-ttu-id="8c978-143">結果として、 **wmiprvse** (WMI プロバイダーのホスト) で大きな CPU 使用率の急増が発生します。</span><span class="sxs-lookup"><span data-stu-id="8c978-143">This results in a large CPU spike in **wmiprvse** (the WMI provider host).</span></span> <span data-ttu-id="8c978-144">修正プログラムでは、WMI を使用する代わりに、Win32 API 呼び出しを使用して同じ情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="8c978-144">Fix is to use Win32 API calls to get the same information instead of using WMI.</span></span>
