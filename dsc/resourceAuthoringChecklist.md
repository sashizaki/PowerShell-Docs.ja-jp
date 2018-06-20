---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: リソース作成のチェックリスト
ms.openlocfilehash: 76d9fecca8618fcc178975465f45cda0d0e04064
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
ms.locfileid: "34189960"
---
# <a name="resource-authoring-checklist"></a><span data-ttu-id="ac25e-103">リソース作成のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="ac25e-103">Resource authoring checklist</span></span>
<span data-ttu-id="ac25e-104">このチェックリストは、新しい DSC リソースを作成するときのベスト プラクティスの一覧です。</span><span class="sxs-lookup"><span data-stu-id="ac25e-104">This checklist is a list of best practices when authoring a new DSC Resource.</span></span>
## <a name="resource-module-contains-psd1-file-and-schemamof-for-every-resource"></a><span data-ttu-id="ac25e-105">リソース モジュールにすべてのリソースの .psd1 ファイルと schema.mof が含まれている</span><span class="sxs-lookup"><span data-stu-id="ac25e-105">Resource module contains .psd1 file and schema.mof for every resource</span></span>
<span data-ttu-id="ac25e-106">リソースが正しい構造であり、必要なすべてのファイルが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-106">Check that your resource has correct structure and contains all required files.</span></span> <span data-ttu-id="ac25e-107">すべてのリソース モジュールには .psd1 ファイルが含まれている必要があり、すべて非複合リソースには .schema.mof ファイルが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-107">Every resource module should contain a .psd1 file and every non-composite resource should have schema.mof file.</span></span> <span data-ttu-id="ac25e-108">スキーマが含まれていないリソースは **Get-DscResource** によって一覧表示されず、ユーザーは ISE でこれらのモジュールに対してコードを記述するときに IntelliSense を使用できません。</span><span class="sxs-lookup"><span data-stu-id="ac25e-108">Resources that do not contain schema will not be listed by **Get-DscResource** and users will not be able to use the intellisense when writing code against those modules in ISE.</span></span>
<span data-ttu-id="ac25e-109">[xPSDesiredStateConfiguration リソース モジュール](https://github.com/PowerShell/xPSDesiredStateConfiguration)の一部である xRemoteFile リソースのディレクトリ構造は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-109">The directory structure for xRemoteFile resource, which is part of the [xPSDesiredStateConfiguration resource module](https://github.com/PowerShell/xPSDesiredStateConfiguration), looks as follows:</span></span>


```
xPSDesiredStateConfiguration
    DSCResources
        MSFT_xRemoteFile
            MSFT_xRemoteFile.psm1
            MSFT_xRemoteFile.schema.mof
    Examples
        xRemoteFile_DownloadFile.ps1
    ResourceDesignerScripts
        GenerateXRemoteFileSchema.ps1
    Tests
        ResourceDesignerTests.ps1
    xPSDesiredStateConfiguration.psd1
```

## <a name="resource-and-schema-are-correct"></a><span data-ttu-id="ac25e-110">リソースとスキーマが正しい ##</span><span class="sxs-lookup"><span data-stu-id="ac25e-110">Resource and schema are correct##</span></span>
<span data-ttu-id="ac25e-111">リソース スキーマ (\*.schema.mof) ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-111">Verify the resource schema (\*.schema.mof) file.</span></span> <span data-ttu-id="ac25e-112">[DSC リソース デザイナー](https://www.powershellgallery.com/packages/xDSCResourceDesigner/)をスキーマの開発と試験に利用できます。</span><span class="sxs-lookup"><span data-stu-id="ac25e-112">You can use the [DSC Resource Designer](https://www.powershellgallery.com/packages/xDSCResourceDesigner/) to help develop and test your schema.</span></span>
<span data-ttu-id="ac25e-113">次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-113">Make sure that:</span></span>
- <span data-ttu-id="ac25e-114">プロパティの型が正しい (たとえば、数値を受け入れるプロパティには文字列を使用せず、UInt32 またはその他の数値型を代わりに使用する必要があります)</span><span class="sxs-lookup"><span data-stu-id="ac25e-114">Property types are correct (e.g. don’t use String for properties which accept numeric values, you should use UInt32 or other numeric types instead)</span></span>
- <span data-ttu-id="ac25e-115">プロパティの属性が正しく指定されている ([key]、[required]、[write]、[read])</span><span class="sxs-lookup"><span data-stu-id="ac25e-115">Property attributes are specified correctly as: ([key], [required], [write], [read])</span></span>
- <span data-ttu-id="ac25e-116">スキーマ内の少なくとも 1 つのパラメーターが [key] としてマークされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-116">At least one parameter in the schema has to be marked as [key]</span></span>
- <span data-ttu-id="ac25e-117">[read] プロパティは [required]、[key]、[write] のいずれとも共存しません。</span><span class="sxs-lookup"><span data-stu-id="ac25e-117">[read] property does not coexist together with any of: [required], [key], [write]</span></span>
- <span data-ttu-id="ac25e-118">[read] 以外の複数の条件が指定されている場合、[key] が優先されます。</span><span class="sxs-lookup"><span data-stu-id="ac25e-118">If multiple qualifiers are specified except [read], then [key] takes precedence</span></span>
- <span data-ttu-id="ac25e-119">[write] と [required] が指定されている場合、[required] が優先されます。</span><span class="sxs-lookup"><span data-stu-id="ac25e-119">If [write] and [required] are specified, then [required] takes precedence</span></span>
- <span data-ttu-id="ac25e-120">ValueMap が適切な場所に指定されている</span><span class="sxs-lookup"><span data-stu-id="ac25e-120">ValueMap is specified where appropriate</span></span>

<span data-ttu-id="ac25e-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-121">Example:</span></span>
```
[Read, ValueMap{"Present", "Absent"}, Values{"Present", "Absent"}, Description("Says whether DestinationPath exists on the machine")] String Ensure;
```

- <span data-ttu-id="ac25e-122">フレンドリ名が指定され、DSC 名前付け規則に準拠している</span><span class="sxs-lookup"><span data-stu-id="ac25e-122">Friendly name is specified and confirms to DSC naming conventions</span></span>

<span data-ttu-id="ac25e-123">例: ```[ClassVersion("1.0.0.0"), FriendlyName("xRemoteFile")]```</span><span class="sxs-lookup"><span data-stu-id="ac25e-123">Example: ```[ClassVersion("1.0.0.0"), FriendlyName("xRemoteFile")]```</span></span>

- <span data-ttu-id="ac25e-124">すべてのフィールドにわかりやすい説明があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-124">Every field has meaningful description.</span></span> <span data-ttu-id="ac25e-125">PowerShell GitHub リポジトリには、[xRemoteFile の .schema.mof](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/dev/DSCResources/MSFT_xRemoteFile/MSFT_xRemoteFile.schema.mof) など、良い例があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-125">The PowerShell GitHub repository has good examples, such as [the .schema.mof for xRemoteFile](https://github.com/PowerShell/xPSDesiredStateConfiguration/blob/dev/DSCResources/MSFT_xRemoteFile/MSFT_xRemoteFile.schema.mof)</span></span>

<span data-ttu-id="ac25e-126">また、[DSC リソース デザイナー](https://www.powershellgallery.com/packages/xDSCResourceDesigner/)から **Test-xDscResource** および **Test-xDscSchema** コマンドレットを使用して、リソースとスキーマを自動的に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-126">Additionally, you should use **Test-xDscResource** and **Test-xDscSchema** cmdlets from [DSC Resource Designer](https://www.powershellgallery.com/packages/xDSCResourceDesigner/) to automatically verify the resource and schema:</span></span>
```
Test-xDscResource <Resource_folder>
Test-xDscSchema <Path_to_resource_schema_file>
```
<span data-ttu-id="ac25e-127">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-127">For example:</span></span>
```powershell
Test-xDscResource ..\DSCResources\MSFT_xRemoteFile
Test-xDscSchema ..\DSCResources\MSFT_xRemoteFile\MSFT_xRemoteFile.schema.mof
```

## <a name="resource-loads-without-errors"></a><span data-ttu-id="ac25e-128">リソースがエラーなしで読み込まれる</span><span class="sxs-lookup"><span data-stu-id="ac25e-128">Resource loads without errors</span></span> ##
<span data-ttu-id="ac25e-129">リソース モジュールを正常に読み込めるか確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-129">Check whether the resource module can be successfully loaded.</span></span>
<span data-ttu-id="ac25e-130">これは、手動で実行する (`Import-Module <resource_module> -force ` を実行してエラーが発生しないことを確認する) か、自動テストを作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="ac25e-130">This can be achieved manually, by running `Import-Module <resource_module> -force ` and confirming that no errors occurred, or by writing test automation.</span></span> <span data-ttu-id="ac25e-131">後者の場合は、テスト ケースで次の構造に従うことができます。</span><span class="sxs-lookup"><span data-stu-id="ac25e-131">In case of the latter, you can follow this structure in your test case:</span></span>
```powershell
$error = $null
Import-Module <resource_module> –force
If ($error.count –ne 0) {
    Throw “Module was not imported correctly. Errors returned: $error”
}
```
## <a name="resource-is-idempotent-in-the-positive-case"></a><span data-ttu-id="ac25e-132">正の場合、リソースはべき等である</span><span class="sxs-lookup"><span data-stu-id="ac25e-132">Resource is idempotent in the positive case</span></span>
<span data-ttu-id="ac25e-133">DSC リソースの基本的な特性の 1 つにべき等性があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-133">One of the fundamental characteristics of DSC resources is be idempotence.</span></span> <span data-ttu-id="ac25e-134">つまり、そのリソースを含む DSC 構成を複数回適用したとき、常に同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="ac25e-134">It means that applying a DSC configuration containing that resource multiple times will always achieve the same result.</span></span> <span data-ttu-id="ac25e-135">たとえば、次の File リソースを含む構成を作成するとします。</span><span class="sxs-lookup"><span data-stu-id="ac25e-135">For example, if we create a configuration which contains the following File resource:</span></span>
```powershell
File file {
    DestinationPath = "C:\test\test.txt"
    Contents = "Sample text"
}
```
<span data-ttu-id="ac25e-136">これを最初に適用した後、test.txt ファイルが C:\test フォルダーに出現します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-136">After applying it for the first time, file test.txt should appear in C:\test folder.</span></span> <span data-ttu-id="ac25e-137">ただし、同じ構成の後続の実行で、マシンの状態を変更しないでください (たとえば、test.txt ファイルのコピーを作成しないでください)。</span><span class="sxs-lookup"><span data-stu-id="ac25e-137">However, subsequent runs of the same configuration should not change the state of the machine (e.g. no copies of the test.txt file should be created).</span></span>
<span data-ttu-id="ac25e-138">リソースがべき等であることを確認するには、リソースを直接テストする場合は **Set-TargetResource** を繰り返し呼び出し、エンド ツー エンド テストを実行する場合は **Start-DscConfiguration** を複数回呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-138">To ensure a resource is idempotent you can repeatedly call **Set-TargetResource** when testing the resource directly, or call **Start-DscConfiguration** multiple times when doing end to end testing.</span></span> <span data-ttu-id="ac25e-139">実行するたびに結果が同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-139">The result should be the same after every run.</span></span>


## <a name="test-user-modification-scenario"></a><span data-ttu-id="ac25e-140">ユーザー変更シナリオのテスト</span><span class="sxs-lookup"><span data-stu-id="ac25e-140">Test user modification scenario</span></span> ##
<span data-ttu-id="ac25e-141">コンピューターの状態を変更し、DSC を再実行することで、**Set-TargetResource** と **Test-TargetResource** が適切に機能することを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ac25e-141">By changing the state of the machine and then rerunning DSC, you can verify that **Set-TargetResource** and **Test-TargetResource** function properly.</span></span> <span data-ttu-id="ac25e-142">実行する手順を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-142">Here are steps you should take:</span></span>
1.  <span data-ttu-id="ac25e-143">目的の状態でないリソースで開始します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-143">Start with the resource not in the desired state.</span></span>
2.  <span data-ttu-id="ac25e-144">リソースで構成を実行します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-144">Run configuration with your resource</span></span>
3.  <span data-ttu-id="ac25e-145">**Test-DscConfiguration** が true を返すことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-145">Verify **Test-DscConfiguration** returns True</span></span>
4.  <span data-ttu-id="ac25e-146">構成対象アイテムが目的の状態から抜けるように変更します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-146">Modify the configured item to be out of the desired state</span></span>
5.  <span data-ttu-id="ac25e-147">**Test-DscConfiguration** が false を返すことを確認します。Registry リソースを使用した具体的な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-147">Verify **Test-DscConfiguration** returns false Here’s a more concrete example using Registry resource:</span></span>
1.  <span data-ttu-id="ac25e-148">目的の状態でないレジストリ キーで開始します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-148">Start with registry key not in the desired state</span></span>
2.  <span data-ttu-id="ac25e-149">**Start-DscConfiguration** を構成で実行し、目的の状態にして正常終了することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-149">Run **Start-DscConfiguration** with a configuration to put it in the desired state and verify it passes.</span></span>
3.  <span data-ttu-id="ac25e-150">**Test-DscConfiguration** を実行し、true を返すことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-150">Run **Test-DscConfiguration** and verify it returns true</span></span>
4.  <span data-ttu-id="ac25e-151">キーの値を変更して、目的でない状態にします。</span><span class="sxs-lookup"><span data-stu-id="ac25e-151">Modify the value of the key so that it is not in the desired state</span></span>
5.  <span data-ttu-id="ac25e-152">**Test-DscConfiguration** を実行し、false を返すことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-152">Run **Test-DscConfiguration** and verify it returns false</span></span>
6.  <span data-ttu-id="ac25e-153">Get-DscConfiguration を使用して Get-TargetResource 機能が検証されている</span><span class="sxs-lookup"><span data-stu-id="ac25e-153">Get-TargetResource functionality was verified using Get-DscConfiguration</span></span>

<span data-ttu-id="ac25e-154">Get-TargetResource は、リソースの現在の状態の詳細を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-154">Get-TargetResource should return details of the current state of the resource.</span></span> <span data-ttu-id="ac25e-155">構成を適用した後に Get-DscConfiguration を呼び出し、出力がマシンの現在の状態を正しく反映していることを検証することによってテストします。</span><span class="sxs-lookup"><span data-stu-id="ac25e-155">Make sure to test it by calling Get-DscConfiguration after you apply the configuration and verifying that output correctly reflects the current state of the machine.</span></span> <span data-ttu-id="ac25e-156">この領域の問題は Start-DscConfiguration の呼び出し時には出現しないため、個別にテストすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="ac25e-156">It's important to test it separately, since any issues in this area won't appear when calling Start-DscConfiguration.</span></span>

## <a name="call-getsettest-targetresource-functions-directly"></a><span data-ttu-id="ac25e-157">**Get/Set/Test-TargetResource** 関数を直接呼び出す</span><span class="sxs-lookup"><span data-stu-id="ac25e-157">Call **Get/Set/Test-TargetResource** functions directly</span></span> ##

<span data-ttu-id="ac25e-158">リソースに実装されている **Get/Set/Test-TargetResource** 関数をテストするには、それらを直接呼び出し、期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-158">Make sure you test the **Get/Set/Test-TargetResource** functions implemented in your resource by calling them directly and verifying that they work as expected.</span></span>

## <a name="verify-end-to-end-using-start-dscconfiguration"></a><span data-ttu-id="ac25e-159">**Start-DscConfiguration** を使用してエンド ツー エンドで確認する</span><span class="sxs-lookup"><span data-stu-id="ac25e-159">Verify End to End using **Start-DscConfiguration**</span></span> ##

<span data-ttu-id="ac25e-160">直接呼び出すことによって **Get/Set/Test-TargetResource** 関数をテストすることは重要ですが、この方法ですべての問題が検出されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="ac25e-160">Testing **Get/Set/Test-TargetResource** functions by calling them directly is important, but not all issues will be discovered this way.</span></span> <span data-ttu-id="ac25e-161">テストにおいては、**Start-DscConfiguration** やプル サーバーの使用に関する部分を重視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-161">You should focus significant part of your testing on using **Start-DscConfiguration** or the pull server.</span></span> <span data-ttu-id="ac25e-162">これはユーザーが実際にリソースを使用する方法であり、この種類のテストの重要性を過小評価しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="ac25e-162">In fact, this is how users will use the resource, so don’t underestimate the significance of this type of tests.</span></span>
<span data-ttu-id="ac25e-163">可能性がある問題の種類:</span><span class="sxs-lookup"><span data-stu-id="ac25e-163">Possible types of issues:</span></span>
- <span data-ttu-id="ac25e-164">DSC エージェントはサービスとして実行されるため、資格情報またはセッションの動作が異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-164">Credential/Session may behave differently because the DSC agent runs as a service.</span></span>  <span data-ttu-id="ac25e-165">機能は必ずエンド ツー エンドでテストしてください。</span><span class="sxs-lookup"><span data-stu-id="ac25e-165">Be sure to test any features here end to end.</span></span>
- <span data-ttu-id="ac25e-166">**Start-DscConfiguration** によるエラー出力は、**Set-TargetResource** 関数を直接呼び出したときに表示されるものとは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-166">Errors output by **Start-DscConfiguration** may be different than those displayed when calling the **Set-TargetResource** function directly.</span></span>

## <a name="test-compatability-on-all-dsc-supported-platforms"></a><span data-ttu-id="ac25e-167">すべての DSC 対応プラットフォームで互換性を試験する</span><span class="sxs-lookup"><span data-stu-id="ac25e-167">Test compatability on all DSC supported platforms</span></span> ##
<span data-ttu-id="ac25e-168">リソースは、DSC がサポートされているすべてのプラットフォーム (Windows Server 2008 R2 以降) で動作する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-168">Resource should work on all DSC supported platforms (Windows Server 2008 R2 and newer).</span></span> <span data-ttu-id="ac25e-169">DSC の最新バージョンを取得するには、OS に最新の WMF (Windows Management Framework) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ac25e-169">Install the latest WMF (Windows Management Framework) on your OS to get the latest version of DSC.</span></span> <span data-ttu-id="ac25e-170">リソースがこれらのプラットフォームの一部で動作しないことが意図的である場合は、特定のエラー メッセージが返される必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-170">If your resource does not work on some of these platforms by design, a specific error message should be returned.</span></span> <span data-ttu-id="ac25e-171">また、リソースで、呼び出すコマンドレットが特定のマシン上に存在するかどうかがチェックされることも確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-171">Also, make sure your resource checks whether cmdlets you are calling are present on particular machine.</span></span> <span data-ttu-id="ac25e-172">Windows Server 2012 には、WMF がインストールされていても Windows Server 2008R2では使用できない多数の新しいコマンドレットが追加されています。</span><span class="sxs-lookup"><span data-stu-id="ac25e-172">Windows Server 2012 added a large number of new cmdlets that are not available on Windows Server 2008R2, even with WMF installed.</span></span>

## <a name="verify-on-windows-client-if-applicable"></a><span data-ttu-id="ac25e-173">(該当する場合) Windows クライアントで確認する</span><span class="sxs-lookup"><span data-stu-id="ac25e-173">Verify on Windows Client (if applicable)</span></span> ##
<span data-ttu-id="ac25e-174">非常に一般的なテスト不足の 1 つは、Windows のサーバー バージョンでのみリソースを検証することです。</span><span class="sxs-lookup"><span data-stu-id="ac25e-174">One very common test gap is verifying the resource only on server versions of Windows.</span></span> <span data-ttu-id="ac25e-175">多くのリソースはクライアント SKU でも動作するように設計されているため、その場合は、これらのプラットフォームでも必ずテストします。</span><span class="sxs-lookup"><span data-stu-id="ac25e-175">Many resources are also designed to work on Client SKUs, so if that’s true in your case, don’t forget to test it on those platforms as well.</span></span>
## <a name="get-dscresource-lists-the-resource"></a><span data-ttu-id="ac25e-176">Get-DscResource でリソースが一覧表示される</span><span class="sxs-lookup"><span data-stu-id="ac25e-176">Get-DSCResource lists the resource</span></span> ##
<span data-ttu-id="ac25e-177">モジュールを展開した後、Get-DscResource を呼び出すと、結果として他のリソースが一覧表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-177">After deploying the module, calling Get-DscResource should list your resource among others as a result.</span></span> <span data-ttu-id="ac25e-178">一覧にリソースが見つからない場合は、そのリソースの schema.mof ファイルが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-178">If you can’t find your resource in the list, make sure that schema.mof file for that resource exists.</span></span>
## <a name="resource-module-contains-examples"></a><span data-ttu-id="ac25e-179">リソース モジュールに例が含まれている</span><span class="sxs-lookup"><span data-stu-id="ac25e-179">Resource module contains examples</span></span> ##
<span data-ttu-id="ac25e-180">他のユーザーが使い方を理解できるように質の高いサンプルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-180">Creating quality examples which will help others understand how to use it.</span></span> <span data-ttu-id="ac25e-181">多くのユーザーはサンプル コードをドキュメントとして扱うため、特に、このことは重要です。</span><span class="sxs-lookup"><span data-stu-id="ac25e-181">This is crucial, especially since many users treat sample code as documentation.</span></span>
- <span data-ttu-id="ac25e-182">最初に、モジュールに含める例を決定する必要があります。少なくとも、リソースの最も重要なユース ケースを反映する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-182">First, you should determine the examples that will be included with the module – at minimum, you should cover most important use cases for your resource:</span></span>
- <span data-ttu-id="ac25e-183">エンド ツー エンドのシナリオで連携して動作する必要がある複数のリソースがモジュールに含まれる場合、基本的なエンド ツー エンドの例を最初に配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ac25e-183">If your module contains several resources that need to work together for an end-to-end scenario, the basic end-to-end example would ideally be first.</span></span>
- <span data-ttu-id="ac25e-184">最初の例は、非常に単純なもの - 小さい管理しやすいチャンク内のリソースを使い始める方法 (新しい VHD の作成など) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-184">The initial examples should be very simple -- how to get started with your resources in small manageable chunks (e.g. creating a new VHD)</span></span>
- <span data-ttu-id="ac25e-185">その後の例は、これらの例の上にビルドし (VHD からの VM の作成、VM の削除、VM の変更など)、高度な機能を示します (動的メモリがある VM の作成など)。</span><span class="sxs-lookup"><span data-stu-id="ac25e-185">Subsequent examples should build on those examples (e.g. creating a VM from a VHD, removing VM, modifying VM), and show advanced functionality (e.g. creating a VM with dynamic memory)</span></span>
- <span data-ttu-id="ac25e-186">構成の例はパラメーター化する必要があります (すべての値は構成にパラメーターとして渡す必要があり、ハードコードされた値は使用しません)。</span><span class="sxs-lookup"><span data-stu-id="ac25e-186">Example configurations should be parameterized (all values should be passed to the configuration as parameters and there should be no hardcoded values):</span></span>
```powershell
configuration Sample_xRemoteFile_DownloadFile
{
    param
    (
        [string[]] $nodeName = 'localhost',

        [parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String] $destinationPath,

        [parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String] $uri,

        [String] $userAgent,

        [Hashtable] $headers
    )

    Import-DscResource -Name MSFT_xRemoteFile -ModuleName xPSDesiredStateConfiguration

    Node $nodeName
    {
        xRemoteFile DownloadFile
        {
            DestinationPath = $destinationPath
            Uri = $uri
            UserAgent = $userAgent
            Headers = $headers
        }
    }
}
```
- <span data-ttu-id="ac25e-187">スクリプトの例の最後に、実際の値を使用して構成を呼び出す方法の例 (コメント アウト) を含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ac25e-187">It’s a good practice to include (commented out) example of how to call the configuration with the actual values at the end of the example script.</span></span>
<span data-ttu-id="ac25e-188">たとえば、上記の構成では、UserAgent を指定する最善の方法が次のとおりであることは必ずしも明白ではありません。</span><span class="sxs-lookup"><span data-stu-id="ac25e-188">For example, in the configuration above it isn't neccessarily obvious that the best way to specify UserAgent is:</span></span>

<span data-ttu-id="ac25e-189">`UserAgent = [Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer` その場合、その構成で意図する実行内容をコメントで明らかにできます。</span><span class="sxs-lookup"><span data-stu-id="ac25e-189">`UserAgent = [Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer` In which case a comment can clarify the intended execution of the configuration:</span></span>
```
<#
Sample use (parameter values need to be changed according to your scenario):

Sample_xRemoteFile_DownloadFile -destinationPath "$env:SystemDrive\fileName.jpg" -uri "http://www.contoso.com/image.jpg"

Sample_xRemoteFile_DownloadFile -destinationPath "$env:SystemDrive\fileName.jpg" -uri "http://www.contoso.com/image.jpg" `
-userAgent [Microsoft.PowerShell.Commands.PSUserAgent]::InternetExplorer -headers @{"Accept-Language" = "en-US"}
#>
```
- <span data-ttu-id="ac25e-190">各例で、実行内容を示す簡単な説明と、パラメーターの意味を記述します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-190">For each example, write a short description which explains what it does, and the meaning of the parameters.</span></span>
- <span data-ttu-id="ac25e-191">リソースのほとんどの重要なシナリオが例でカバーされていることを確認し、不足がない場合は、すべてが実行され、マシンを目的の状態にすることを検証します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-191">Make sure examples cover most the important scenarios for your resource and if there’s nothing missing, verify that they all execute and put machine in the desired state.</span></span>

## <a name="error-messages-are-easy-to-understand-and-help-users-solve-problems"></a><span data-ttu-id="ac25e-192">エラー メッセージは、わかりやすく、ユーザーが問題を解決するために役立つものである</span><span class="sxs-lookup"><span data-stu-id="ac25e-192">Error messages are easy to understand and help users solve problems</span></span> ##
<span data-ttu-id="ac25e-193">優れたエラー メッセージとは、次のようなものです。</span><span class="sxs-lookup"><span data-stu-id="ac25e-193">Good error messages should be:</span></span>
- <span data-ttu-id="ac25e-194">存在する: エラー メッセージに関する最大の問題は、存在しないことがよくあるということです。メッセージが必ず存在するようにします。</span><span class="sxs-lookup"><span data-stu-id="ac25e-194">There: The biggest problem with error messages is that they often don’t exist, so make sure they are there.</span></span>
- <span data-ttu-id="ac25e-195">わかりやすい: 人間が判読できる、明瞭なエラー コード。</span><span class="sxs-lookup"><span data-stu-id="ac25e-195">Easy to understand: Human readable, no obscure error codes</span></span>
- <span data-ttu-id="ac25e-196">正確である: 何が問題であるかを正確に説明します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-196">Precise: Describe what’s exactly the problem</span></span>
- <span data-ttu-id="ac25e-197">建設的である: 問題を解決する方法を助言します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-197">Constructive: Advice how to fix the issue</span></span>
- <span data-ttu-id="ac25e-198">礼儀正しい: ユーザーを非難したり、見下したりしません。エラーはリソース機能を直接実行したときに返されるものとは異なる可能性があるため、エンド ツー エンドのシナリオで (**Start-DscConfiguration** を使用して) エラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-198">Polite: Don’t blame user or make them feel bad Make sure you verify errors in End to End scenarios (using **Start-DscConfiguration**), because they may differ from those returned when running resource functions directly.</span></span>

## <a name="log-messages-are-easy-to-understand-and-informative-including-verbose-debug-and-etw-logs"></a><span data-ttu-id="ac25e-199">ログ メッセージは、わかりやすく、有益な情報が含まれている (-verbose、-debug、および ETW ログを含む)</span><span class="sxs-lookup"><span data-stu-id="ac25e-199">Log messages are easy to understand and informative (including –verbose, –debug and ETW logs)</span></span> ##
<span data-ttu-id="ac25e-200">リソースによって出力されるログがわかりやすく、ユーザーにとって価値のあるものであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-200">Ensure that logs outputted by the resource are easy to understand and provide value to the user.</span></span> <span data-ttu-id="ac25e-201">リソースは、ユーザーに役立つ可能性のあるすべての情報を出力する必要がありますが、常にログが多い方がよいとは限りません。</span><span class="sxs-lookup"><span data-stu-id="ac25e-201">Resources should output all information which might be helpful to the user, but more logs is not always better.</span></span> <span data-ttu-id="ac25e-202">冗長性および付加価値を提供しないデータを出力することは避ける必要があります。求めている情報を探して何百ものログ エントリを確認する必要がないようにします。</span><span class="sxs-lookup"><span data-stu-id="ac25e-202">You should avoid redundancy and outputting data which does not provide additional value – don’t make someone go through hundreds of log entries in order to find what they're looking for.</span></span> <span data-ttu-id="ac25e-203">もちろん、ログを出力しないことはこの問題に対する適切な解決策ではありません。</span><span class="sxs-lookup"><span data-stu-id="ac25e-203">Of course, no logs is not an acceptable solution for this problem either.</span></span>

<span data-ttu-id="ac25e-204">テストする場合は、詳細ログとデバッグ ログ (**Start-DscConfiguration** を -verbose および -debug スイッチを適切に指定して実行する)、および ETW ログも分析する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-204">When testing, you should also analyze verbose and debug logs (by running **Start-DscConfiguration** with –verbose and –debug switches appropriately), as well as ETW logs.</span></span> <span data-ttu-id="ac25e-205">DSC ETW ログを確認するには、イベント ビューアーに移動し、次のフォルダーを開きます。Applications and Services- Microsoft - Windows - Desired State Configuration。</span><span class="sxs-lookup"><span data-stu-id="ac25e-205">To see DSC ETW logs, go to Event Viewer and open the following folder: Applications and Services- Microsoft - Windows - Desired State Configuration.</span></span>  <span data-ttu-id="ac25e-206">既定では稼動チャネルがありますが、構成を実行する前に分析チャネルとデバッグ チャネルを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ac25e-206">By default there will be Operational channel, but make sure you enable Analytic and Debug channels before running the configuration.</span></span>
<span data-ttu-id="ac25e-207">分析/デバッグ チャネルを有効にするには、次のスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ac25e-207">To enable Analytic/Debug channels, you can execute script below:</span></span>
```powershell
$statusEnabled = $true
# Use "Analytic" to enable Analytic channel
$eventLogFullName = "Microsoft-Windows-Dsc/Debug"
$commandToExecute = "wevtutil set-log $eventLogFullName /e:$statusEnabled /q:$statusEnabled   "
$log = New-Object System.Diagnostics.Eventing.Reader.EventLogConfiguration $eventLogFullName
if($statusEnabled -eq $log.IsEnabled)
{
    Write-Host -Verbose "The channel event log is already enabled"
    return
}
Invoke-Expression $commandToExecute
```
## <a name="resource-implementation-does-not-contain-hardcoded-paths"></a><span data-ttu-id="ac25e-208">リソースの実装にハードコードされたパスが含まれていない</span><span class="sxs-lookup"><span data-stu-id="ac25e-208">Resource implementation does not contain hardcoded paths</span></span> ##
<span data-ttu-id="ac25e-209">リソースの実装にハードコードされたパスがないことを確認します (特に、それらが言語 (en-us) を想定する場合、または使用できるシステム変数がある場合)。</span><span class="sxs-lookup"><span data-stu-id="ac25e-209">Ensure there are no hardcoded paths in the resource implementation, particularly if they assume language (en-us), or when there are system variables that can be used.</span></span>
<span data-ttu-id="ac25e-210">リソースが特定のパスにアクセスする必要がある場合、パスは他のコンピューターでは異なる可能性があるため、パスをハードコーディングする代わりに環境変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-210">If your resource need to access specific paths, use environment variables instead of hardcoding the path, as it may differ on other machines.</span></span>

<span data-ttu-id="ac25e-211">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-211">Example:</span></span>

<span data-ttu-id="ac25e-212">次の代わりに、</span><span class="sxs-lookup"><span data-stu-id="ac25e-212">Instead of:</span></span>
```
$tempPath = "C:\Users\kkaczma\AppData\Local\Temp\MyResource"
$programFilesPath = "C:\Program Files (x86)"
 ```
<span data-ttu-id="ac25e-213">次のように記述できます。</span><span class="sxs-lookup"><span data-stu-id="ac25e-213">You can write:</span></span>
```
$tempPath = Join-Path $env:temp "MyResource"
$programFilesPath = ${env:ProgramFiles(x86)}
```
## <a name="resource-implementation-does-not-contain-user-information"></a><span data-ttu-id="ac25e-214">リソースの実装にユーザー情報が含まれていない</span><span class="sxs-lookup"><span data-stu-id="ac25e-214">Resource implementation does not contain user information</span></span> ##
<span data-ttu-id="ac25e-215">コード内に電子メール名、アカウント情報、または、ユーザーの名前がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-215">Make sure there are no email names, account information, or names of people in the code.</span></span>
## <a name="resource-was-tested-with-validinvalid-credentials"></a><span data-ttu-id="ac25e-216">リソースが有効/無効な資格情報を使用してテストされている</span><span class="sxs-lookup"><span data-stu-id="ac25e-216">Resource was tested with valid/invalid credentials</span></span> ##
<span data-ttu-id="ac25e-217">リソースが資格情報をパラメーターとして受け取る場合:</span><span class="sxs-lookup"><span data-stu-id="ac25e-217">If your resource takes a credential as parameter:</span></span>
- <span data-ttu-id="ac25e-218">ローカル システム (またはリモート リソースのコンピューター アカウント) にアクセスがない場合に、リソースが動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-218">Verify the resource works when Local System (or the computer account for remote resources) does not have access.</span></span>
- <span data-ttu-id="ac25e-219">Get、Set、および Test に指定された資格情報でリソースが動作することを検証します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-219">Verify the resource works with a credential specified for Get, Set and Test</span></span>
- <span data-ttu-id="ac25e-220">リソースが共有にアクセスする場合は、サポートする必要がある次のようなすべてのバリエーションをテストします。</span><span class="sxs-lookup"><span data-stu-id="ac25e-220">If your resource accesses shares, test all the variants you need to support, such as:</span></span>
  - <span data-ttu-id="ac25e-221">標準の Windows 共有。</span><span class="sxs-lookup"><span data-stu-id="ac25e-221">Standard windows shares.</span></span>
  - <span data-ttu-id="ac25e-222">DFS 共有。</span><span class="sxs-lookup"><span data-stu-id="ac25e-222">DFS shares.</span></span>
  - <span data-ttu-id="ac25e-223">SAMBA 共有 (Linux をサポートする場合)。</span><span class="sxs-lookup"><span data-stu-id="ac25e-223">SAMBA shares (if you want to support Linux.)</span></span>

## <a name="resource-does-not-require-interactive-input"></a><span data-ttu-id="ac25e-224">リソースには対話型の入力は不要です。</span><span class="sxs-lookup"><span data-stu-id="ac25e-224">Resource does not require interactive input</span></span> ##
<span data-ttu-id="ac25e-225">**Get/Set/Test-TargetResource** 関数は自動的に実行される必要があり、実行のいずれの段階でもユーザーの入力を待機することはできません (たとえば、これらの関数内で **Get-Credential** を使用することはできません)。</span><span class="sxs-lookup"><span data-stu-id="ac25e-225">**Get/Set/Test-TargetResource** functions should be executed automatically and must not wait for user’s input at any stage of execution (e.g. you should not use **Get-Credential** inside these functions).</span></span> <span data-ttu-id="ac25e-226">ユーザーの入力を提供する必要がある場合は、コンパイル フェーズ中にパラメーターとして構成に渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-226">If you need to provide user’s input, you should pass it to the configuration as parameter during the compilation phase.</span></span>
## <a name="resource-functionality-was-thoroughly-tested"></a><span data-ttu-id="ac25e-227">リソース機能が十分にテストされている</span><span class="sxs-lookup"><span data-stu-id="ac25e-227">Resource functionality was thoroughly tested</span></span> ##
<span data-ttu-id="ac25e-228">このチェックリストには、テストする必要がある重要な項目や見落とされがちな項目が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ac25e-228">This checklist contains items which are important to be tested and/or are often missed.</span></span> <span data-ttu-id="ac25e-229">一連のテスト (テストするリソースに固有であり、ここに記載されていない、主に機能のテスト) があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-229">There will be bunch of tests, mainly functional ones which will be specific to the resource you are testing and are not mentioned here.</span></span> <span data-ttu-id="ac25e-230">負のテスト ケースを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="ac25e-230">Don’t forget about negative test cases.</span></span>
## <a name="best-practice-resource-module-contains-tests-folder-with-resourcedesignertestsps1-script"></a><span data-ttu-id="ac25e-231">ベスト プラクティス: リソース モジュールに、ResourceDesignerTests.ps1 スクリプトを含む Test フォルダーが含まれている</span><span class="sxs-lookup"><span data-stu-id="ac25e-231">Best practice: Resource module contains Tests folder with ResourceDesignerTests.ps1 script</span></span> ##
<span data-ttu-id="ac25e-232">リソース モジュール内に "Test" フォルダーを作成し、ResourceDesignerTests.ps1 ファイルを作成し、指定したモジュール内のすべてのリソースに対して **Test-xDscResource** と **Test-xDscSchema** を使用してテストを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ac25e-232">It’s a good practice to create folder “Tests” inside resource module, create ResourceDesignerTests.ps1 file and add tests using **Test-xDscResource** and **Test-xDscSchema** for all resources in given module.</span></span>
<span data-ttu-id="ac25e-233">この方法で、指定したモジュールのすべてのリソースのスキーマをすばやく検証し、発行する前にサニティ チェックを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ac25e-233">This way you can quickly validate schemas of all resources from the given modules and do a sanity check before publishing.</span></span>
<span data-ttu-id="ac25e-234">xRemoteFile の場合、ResourceTests.ps1 は次のように単純になります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-234">For xRemoteFile, ResourceTests.ps1 could look as simple as:</span></span>
```powershell
Test-xDscResource ..\DSCResources\MSFT_xRemoteFile
Test-xDscSchema ..\DSCResources\MSFT_xRemoteFile\MSFT_xRemoteFile.schema.mof
```
##<a name="best-practice-resource-folder-contains-resource-designer-script-for-generating-schema"></a><span data-ttu-id="ac25e-235">ベスト プラクティス: リソース フォルダーにスキーマを生成するためのリソース デザイナー スクリプトが含まれている ##</span><span class="sxs-lookup"><span data-stu-id="ac25e-235">Best practice: Resource folder contains resource designer script for generating schema##</span></span>
<span data-ttu-id="ac25e-236">各リソースに、リソースの mof スキーマを生成する、リソース デザイナー スクリプトを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac25e-236">Each resource should contain a resource designer script which generates a mof schema of the resource.</span></span> <span data-ttu-id="ac25e-237">このファイルは、<ResourceName>\ResourceDesignerScripts に配置し、Generate<ResourceName>Schema.ps1 という名前を付ける必要があります。xRemoteFile リソースの場合、このファイルの名前は GenerateXRemoteFileSchema.ps1 となり、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ac25e-237">This file should be placed in <ResourceName>\ResourceDesignerScripts and be named Generate<ResourceName>Schema.ps1 For xRemoteFile resource this file would be called GenerateXRemoteFileSchema.ps1 and contain:</span></span>
```powershell
$DestinationPath = New-xDscResourceProperty -Name DestinationPath -Type String -Attribute Key -Description 'Path under which downloaded or copied file should be accessible after operation.'
$Uri = New-xDscResourceProperty -Name Uri -Type String -Attribute Required -Description 'Uri of a file which should be copied or downloaded. This parameter supports HTTP and HTTPS values.'
$Headers = New-xDscResourceProperty -Name Headers -Type Hashtable[] -Attribute Write -Description 'Headers of the web request.'
$UserAgent = New-xDscResourceProperty -Name UserAgent -Type String -Attribute Write -Description 'User agent for the web request.'
$Ensure = New-xDscResourceProperty -Name Ensure -Type String -Attribute Read -ValidateSet "Present", "Absent" -Description 'Says whether DestinationPath exists on the machine'
$Credential = New-xDscResourceProperty -Name Credential -Type PSCredential -Attribute Write -Description 'Specifies a user account that has permission to send the request.'
$CertificateThumbprint = New-xDscResourceProperty -Name CertificateThumbprint -Type String -Attribute Write -Description 'Digital public key certificate that is used to send the request.'

New-xDscResource -Name MSFT_xRemoteFile -Property @($DestinationPath, $Uri, $Headers, $UserAgent, $Ensure, $Credential, $CertificateThumbprint) -ModuleName xPSDesiredStateConfiguration2 -FriendlyName xRemoteFile
```
## <a name="best-practice-resource-supports--whatif"></a><span data-ttu-id="ac25e-238">ベスト プラクティス: リソースによる -whatif のサポート</span><span class="sxs-lookup"><span data-stu-id="ac25e-238">Best practice: Resource supports -whatif</span></span> ##
<span data-ttu-id="ac25e-239">リソースが "危険な" 操作を実行する場合は、-whatif 機能を実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ac25e-239">If your resource is performing “dangerous” operations, it’s a good practice to implement -whatif functionality.</span></span> <span data-ttu-id="ac25e-240">完了したら、whatif スイッチを使用しないでコマンドが実行された場合にどのようなことが発生するかについて、whatif 出力で正しく記述されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-240">After it’s done, make sure that whatif output correctly describes operations which would happen if command was executed without whatif switch.</span></span>
<span data-ttu-id="ac25e-241">また、-whatif スイッチが存在する場合は、その操作が実行されない (ノードの状態の変更は行われない) ことも確認します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-241">Also, verify that operations does not execute (no changes to the node’s state are made) when –whatif switch is present.</span></span>
<span data-ttu-id="ac25e-242">たとえば、File リソースをテストすると仮定します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-242">For example, let’s assume we are testing File resource.</span></span> <span data-ttu-id="ac25e-243">"test" の内容を持つファイル "test.txt" を作成する単純な構成を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ac25e-243">Below is simple configuration which creates file “test.txt” with contents “test”:</span></span>
```powershell
configuration config
{
    node localhost
    {
        File file
        {
            Contents="test"
            DestinationPath="C:\test\test.txt"
        }
    }
}
config
```
<span data-ttu-id="ac25e-244">-whatif スイッチを含む構成をコンパイルし、実行すると、構成を実行したときに発生することが出力に正確に示されます。</span><span class="sxs-lookup"><span data-stu-id="ac25e-244">If we compile and then execute the configuration with the –whatif switch, the output is telling us exactly what would happen when we run the configuration.</span></span> <span data-ttu-id="ac25e-245">ただし、構成自体は実行されていません (test.txt ファイルは作成されていません)。</span><span class="sxs-lookup"><span data-stu-id="ac25e-245">The configuration itself however was not executed (test.txt file was not created).</span></span>
```powershell
Start-DscConfiguration -path .\config -ComputerName localhost -wait -verbose -whatif
VERBOSE: Perform operation 'Invoke CimMethod' with following parameters, ''methodName' =
SendConfigurationApply,'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' =
root/Microsoft/Windows/DesiredStateConfiguration'.
VERBOSE: An LCM method call arrived from computer CHARLESX1 with user sid
S-1-5-21-397955417-626881126-188441444-5179871.
What if: [X]: LCM:  [ Start  Set      ]
What if: [X]: LCM:  [ Start  Resource ]  [[File]file]
What if: [X]: LCM:  [ Start  Test     ]  [[File]file]
What if: [X]:                            [[File]file] The system cannot find the file specified.
What if: [X]:                            [[File]file] The related file/directory is: C:\test\test.txt.
What if: [X]: LCM:  [ End    Test     ]  [[File]file]  in 0.0270 seconds.
What if: [X]: LCM:  [ Start  Set      ]  [[File]file]
What if: [X]:                            [[File]file] The system cannot find the file specified.
What if: [X]:                            [[File]file] The related file/directory is: C:\test\test.txt.
What if: [X]:                            [C:\test\test.txt] Creating and writing contents and setting attributes.
What if: [X]: LCM:  [ End    Set      ]  [[File]file]  in 0.0180 seconds.
What if: [X]: LCM:  [ End    Resource ]  [[File]file]
What if: [X]: LCM:  [ End    Set      ]
VERBOSE: [X]: LCM:  [ End    Set      ]    in  0.1050 seconds.
VERBOSE: Operation 'Invoke CimMethod' complete.
```

<span data-ttu-id="ac25e-246">この一覧ですべての内容を網羅しているわけではないですが、DSC リソースの設計、開発、テスト中に発生した多くの重要な問題を反映しています。</span><span class="sxs-lookup"><span data-stu-id="ac25e-246">This list is not exhaustive, but it covers many important issues which can be encountered while designing, developing and testing DSC resources.</span></span>