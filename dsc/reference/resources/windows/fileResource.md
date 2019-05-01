---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC ファイル リソース
ms.openlocfilehash: b5bc2c305b8cfccbd044274811df631264a24279
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077332"
---
# <a name="dsc-file-resource"></a><span data-ttu-id="56ace-103">DSC ファイル リソース</span><span class="sxs-lookup"><span data-stu-id="56ace-103">DSC File Resource</span></span>

> <span data-ttu-id="56ace-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="56ace-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="56ace-105">Windows PowerShell Desired State Configuration (DSC) の File リソースは、ターゲット ノード上でファイルとフォルダーを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="56ace-105">The File resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage files and folders on the target node.</span></span> <span data-ttu-id="56ace-106">**DestinationPath** と **SourcePath** は両方ともターゲット ノードからアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="56ace-106">The **DestinationPath** and **SourcePath** must both be accessible by the target Node.</span></span>

## <a name="syntax"></a><span data-ttu-id="56ace-107">構文</span><span class="sxs-lookup"><span data-stu-id="56ace-107">Syntax</span></span>

```
File [string] #ResourceName
{
    DestinationPath = [string]
    [ Attributes = [string[]] { Archive | Hidden | ReadOnly | System }]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Contents = [string] ]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present } ]
    [ Force = [bool] ]
    [ Recurse = [bool] ]
    [ DependsOn = [string[]] ]
    [ SourcePath = [string] ]
    [ Type = [string] { Directory | File } ]
    [ MatchSource = [bool] ]
}
```

## <a name="properties"></a><span data-ttu-id="56ace-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="56ace-108">Properties</span></span>

|<span data-ttu-id="56ace-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="56ace-109">Property</span></span>       |<span data-ttu-id="56ace-110">説明</span><span class="sxs-lookup"><span data-stu-id="56ace-110">Description</span></span>                                                                   |<span data-ttu-id="56ace-111">必須</span><span class="sxs-lookup"><span data-stu-id="56ace-111">Required</span></span>|<span data-ttu-id="56ace-112">既定</span><span class="sxs-lookup"><span data-stu-id="56ace-112">Default</span></span>|
|---------------|------------------------------------------------------------------------------|--------|-------|
|<span data-ttu-id="56ace-113">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="56ace-113">DestinationPath</span></span>|<span data-ttu-id="56ace-114">確保するターゲット ノード上の場所は `Present` または `Absent` です。</span><span class="sxs-lookup"><span data-stu-id="56ace-114">The location, on the target node, you want to ensure is `Present` or `Absent`.</span></span>|<span data-ttu-id="56ace-115">可</span><span class="sxs-lookup"><span data-stu-id="56ace-115">Yes</span></span>|<span data-ttu-id="56ace-116">いいえ</span><span class="sxs-lookup"><span data-stu-id="56ace-116">No</span></span>|
|<span data-ttu-id="56ace-117">属性</span><span class="sxs-lookup"><span data-stu-id="56ace-117">Attributes</span></span>     |<span data-ttu-id="56ace-118">対象となるファイルまたはディレクトリの属性の望ましい状態。</span><span class="sxs-lookup"><span data-stu-id="56ace-118">The desired state of the attributes for the targeted file or directory.</span></span> <span data-ttu-id="56ace-119">有効な値は、**Archive**、**Hidden**、**ReadOnly**、**System** です。</span><span class="sxs-lookup"><span data-stu-id="56ace-119">Valid values are **Archive**, **Hidden**, **ReadOnly**, and **System**.</span></span>|<span data-ttu-id="56ace-120">いいえ</span><span class="sxs-lookup"><span data-stu-id="56ace-120">No</span></span>|<span data-ttu-id="56ace-121">None</span><span class="sxs-lookup"><span data-stu-id="56ace-121">None</span></span>|
|<span data-ttu-id="56ace-122">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56ace-122">Checksum</span></span>      |<span data-ttu-id="56ace-123">2 つのファイルが同じであるかどうかを決定するときに使用するチェックサム タイプ。</span><span class="sxs-lookup"><span data-stu-id="56ace-123">The checksum type to use when determining whether two files are the same.</span></span> <span data-ttu-id="56ace-124">有効な値は、次のとおりです。SHA-1、SHA-256、SHA-512、createdDate、modifiedDate。</span><span class="sxs-lookup"><span data-stu-id="56ace-124">Valid values include: SHA-1, SHA-256, SHA-512, createdDate, modifiedDate.</span></span>|<span data-ttu-id="56ace-125">いいえ</span><span class="sxs-lookup"><span data-stu-id="56ace-125">No</span></span>|<span data-ttu-id="56ace-126">ファイルまたはディレクトリの名前のみが比較されます。</span><span class="sxs-lookup"><span data-stu-id="56ace-126">Only the file or directory name is compared.</span></span>|
|<span data-ttu-id="56ace-127">内容</span><span class="sxs-lookup"><span data-stu-id="56ace-127">Contents</span></span>       |<span data-ttu-id="56ace-128">`File` 型に使用した場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="56ace-128">Only valid when used with `File` type.</span></span> <span data-ttu-id="56ace-129">確認 (Ensure) するコンテンツがターゲット ファイルの `Present` または `Absent` であることを示します。</span><span class="sxs-lookup"><span data-stu-id="56ace-129">Indicates the contents to Ensure are `Present` or `Absent` from the targeted file.</span></span> |<span data-ttu-id="56ace-130">いいえ</span><span class="sxs-lookup"><span data-stu-id="56ace-130">No</span></span>|<span data-ttu-id="56ace-131">None</span><span class="sxs-lookup"><span data-stu-id="56ace-131">None</span></span>|
|<span data-ttu-id="56ace-132">Credential</span><span class="sxs-lookup"><span data-stu-id="56ace-132">Credential</span></span>     |<span data-ttu-id="56ace-133">ソース ファイルなどのリソースにアクセスするために必要な資格情報。</span><span class="sxs-lookup"><span data-stu-id="56ace-133">The credentials that are required to access resources, such as source files.</span></span>|<span data-ttu-id="56ace-134">いいえ</span><span class="sxs-lookup"><span data-stu-id="56ace-134">No</span></span>|<span data-ttu-id="56ace-135">ターゲット ノードのコンピューター アカウント。</span><span class="sxs-lookup"><span data-stu-id="56ace-135">The target node's Computer Account.</span></span> <span data-ttu-id="56ace-136">("*注を参照*")</span><span class="sxs-lookup"><span data-stu-id="56ace-136">(*see note*)</span></span>|
|<span data-ttu-id="56ace-137">Ensure</span><span class="sxs-lookup"><span data-stu-id="56ace-137">Ensure</span></span>         |<span data-ttu-id="56ace-138">対象となるファイルまたはディレクトリの望ましい状態。</span><span class="sxs-lookup"><span data-stu-id="56ace-138">The desired state of the target file or directory.</span></span> |<span data-ttu-id="56ace-139">いいえ</span><span class="sxs-lookup"><span data-stu-id="56ace-139">No</span></span>|<span data-ttu-id="56ace-140">**Present**</span><span class="sxs-lookup"><span data-stu-id="56ace-140">**Present**</span></span>|
|<span data-ttu-id="56ace-141">Force</span><span class="sxs-lookup"><span data-stu-id="56ace-141">Force</span></span>          |<span data-ttu-id="56ace-142">結果としてエラーになるアクセス操作 (ファイルの上書き、空でないディレクトリの削除など) をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="56ace-142">Overrides access operations that would result in an error (such as overwriting a file or deleting a directory that is not empty).</span></span>|<span data-ttu-id="56ace-143">いいえ</span><span class="sxs-lookup"><span data-stu-id="56ace-143">No</span></span>|`$false`|
|<span data-ttu-id="56ace-144">Recurse</span><span class="sxs-lookup"><span data-stu-id="56ace-144">Recurse</span></span>        |<span data-ttu-id="56ace-145">`Directory` 型に使用した場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="56ace-145">Only valid when used with `Directory` type.</span></span> <span data-ttu-id="56ace-146">すべてのサブディレクトリに対して状態操作を再帰的に実行します。</span><span class="sxs-lookup"><span data-stu-id="56ace-146">Performs the state operation recursively to all subdirectories.</span></span>|<span data-ttu-id="56ace-147">いいえ</span><span class="sxs-lookup"><span data-stu-id="56ace-147">No</span></span>|`$false`|
|<span data-ttu-id="56ace-148">DependsOn</span><span class="sxs-lookup"><span data-stu-id="56ace-148">DependsOn</span></span>      |<span data-ttu-id="56ace-149">指定したリソースに依存関係を設定します。</span><span class="sxs-lookup"><span data-stu-id="56ace-149">Sets a dependency on specified resource(s).</span></span> <span data-ttu-id="56ace-150">このリソースは、依存リソースが正常に実行された後にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="56ace-150">This resource will only execute after successful execution of any dependent resources.</span></span> <span data-ttu-id="56ace-151">構文 `"[ResourceType]ResourceName"` を使用して依存リソースを指定できます。</span><span class="sxs-lookup"><span data-stu-id="56ace-151">You can specify dependent resources using the syntax `"[ResourceType]ResourceName"`.</span></span> <span data-ttu-id="56ace-152">「[about_DependsOn](../../../configurations/resource-depends-on.md)」を参照してください</span><span class="sxs-lookup"><span data-stu-id="56ace-152">See [about_DependsOn](../../../configurations/resource-depends-on.md)</span></span>|<span data-ttu-id="56ace-153">いいえ</span><span class="sxs-lookup"><span data-stu-id="56ace-153">No</span></span>|<span data-ttu-id="56ace-154">None</span><span class="sxs-lookup"><span data-stu-id="56ace-154">None</span></span>|
|<span data-ttu-id="56ace-155">SourcePath</span><span class="sxs-lookup"><span data-stu-id="56ace-155">SourcePath</span></span>     |<span data-ttu-id="56ace-156">ファイルまたはフォルダー リソースのコピー元のパス。</span><span class="sxs-lookup"><span data-stu-id="56ace-156">The path from which to copy the file or folder resource.</span></span>|<span data-ttu-id="56ace-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="56ace-157">No</span></span>|<span data-ttu-id="56ace-158">None</span><span class="sxs-lookup"><span data-stu-id="56ace-158">None</span></span>|
|<span data-ttu-id="56ace-159">種類</span><span class="sxs-lookup"><span data-stu-id="56ace-159">Type</span></span>           |<span data-ttu-id="56ace-160">構成されるリソースの種類。</span><span class="sxs-lookup"><span data-stu-id="56ace-160">The type of resource being configured.</span></span> <span data-ttu-id="56ace-161">有効な値は `Directory` と `File` です。</span><span class="sxs-lookup"><span data-stu-id="56ace-161">Valid values are `Directory` and `File`.</span></span>|<span data-ttu-id="56ace-162">いいえ</span><span class="sxs-lookup"><span data-stu-id="56ace-162">No</span></span>|`File`|
|<span data-ttu-id="56ace-163">MatchSource</span><span class="sxs-lookup"><span data-stu-id="56ace-163">MatchSource</span></span>    |<span data-ttu-id="56ace-164">最初のコピー後にソース ディレクトリに追加された新しいファイルをリソースで監視するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="56ace-164">Determines if the resource should monitor for new files added to the source directory after the initial copy.</span></span> <span data-ttu-id="56ace-165">`$true` の値は、最初のコピー後、すべての新しいソース ファイルが指定した場所にコピーされることを示します。</span><span class="sxs-lookup"><span data-stu-id="56ace-165">A value of `$true` indicates that, after the initial copy, any new source files should be copied to the destination.</span></span> <span data-ttu-id="56ace-166">`$False` に設定した場合、リソースではソース ディレクトリの内容がキャッシュされ、最初のコピー後に追加されたファイルはすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="56ace-166">If set to `$False`, the resource caches the contents of the source directory and ignores any files added after the initial copy.</span></span>|<span data-ttu-id="56ace-167">いいえ</span><span class="sxs-lookup"><span data-stu-id="56ace-167">No</span></span>|`$false`|

> [!WARNING]
> <span data-ttu-id="56ace-168">`Credential` または `PSRunAsCredential` (PS V.5) の値を指定しない場合、リソースはターゲット ノードのコンピューター アカウントを使用して `SourcePath` にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="56ace-168">If you do not specify a value for `Credential` or `PSRunAsCredential` (PS V.5), the resource will use the computer account of the target node to access the `SourcePath`.</span></span>  <span data-ttu-id="56ace-169">`SourcePath` が UNC 共有の場合、"アクセスが拒否されました" エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="56ace-169">When the `SourcePath` is a UNC share, this could result in an "Access Denied" error.</span></span> <span data-ttu-id="56ace-170">アクセス許可が適切に設定されていることを確認するか、`Credential` または `PSRunAsCredential` プロパティを使用して、使用するアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="56ace-170">Please ensure your permissions are set accordingly, or use the `Credential` or `PSRunAsCredential` properties to specify the account that should be used.</span></span>

## <a name="present-vs-absent"></a><span data-ttu-id="56ace-171">Present とAbsent</span><span class="sxs-lookup"><span data-stu-id="56ace-171">Present vs. Absent</span></span>

<span data-ttu-id="56ace-172">各 DSC リソースでは、`Ensure` プロパティに指定した値に基づいて異なる操作が実行されます。</span><span class="sxs-lookup"><span data-stu-id="56ace-172">Each DSC resource performs different operations based on the value you specify for the `Ensure` property.</span></span> <span data-ttu-id="56ace-173">上記のプロパティに指定した値によって、実行される状態操作が決まります。</span><span class="sxs-lookup"><span data-stu-id="56ace-173">The values you specify for the above properties determines the state operation performed.</span></span>

### <a name="existence"></a><span data-ttu-id="56ace-174">存在</span><span class="sxs-lookup"><span data-stu-id="56ace-174">Existence</span></span>

<span data-ttu-id="56ace-175">`DestinationPath` のみを指定した場合、リソースではパスが存在すること (`Present`) または存在しないこと (`Absent`) が確認されます。</span><span class="sxs-lookup"><span data-stu-id="56ace-175">When you only specify a `DestinationPath`, the resource ensures that the path exists (`Present`) or does not exist (`Absent`).</span></span>

### <a name="copy-operations"></a><span data-ttu-id="56ace-176">コピー操作</span><span class="sxs-lookup"><span data-stu-id="56ace-176">Copy Operations</span></span>

<span data-ttu-id="56ace-177">`Type` の値が **Directory** の `SourcePath` と `DestinationPath` を指定すると、リソースではソース ディレクトリが対象パスにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="56ace-177">When you specify a `SourcePath` and a `DestinationPath` with a `Type` value of **Directory**, the resource copies source directory to the destination path.</span></span> <span data-ttu-id="56ace-178">プロパティ `Recurse`、`Force`、および `MatchSource` で実行されるコピー操作の種類が変更され、`Credential` ではソース ディレクトリへのアクセスに使用するアカウントが決まります。</span><span class="sxs-lookup"><span data-stu-id="56ace-178">The properties `Recurse`, `Force`, and `MatchSource` change the type of copy operation performed, while `Credential` determines which account to use to access the source directory.</span></span>

### <a name="limitations"></a><span data-ttu-id="56ace-179">制限事項</span><span class="sxs-lookup"><span data-stu-id="56ace-179">Limitations</span></span>

<span data-ttu-id="56ace-180">`Attributes` プロパティに `DestinationPath` と一緒に `ReadOnly` の値を指定した場合、`Ensure = "Present"` によって指定したパスが作成され、`Contents` によってファイルの内容が設定されます。</span><span class="sxs-lookup"><span data-stu-id="56ace-180">If you specified a value of `ReadOnly` for the `Attributes` property alongside a `DestinationPath`, `Ensure = "Present"` would create the path specified, while `Contents` would set the contents of the file.</span></span>  <span data-ttu-id="56ace-181">`Absent` 状態操作では `Attributes` プロパティが完全に無視され、指定したパスにあるすべてのファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="56ace-181">An `Absent` state operation would ignore the `Attributes` property entirely, and remove any file at the specified path.</span></span>

## <a name="example"></a><span data-ttu-id="56ace-182">例</span><span class="sxs-lookup"><span data-stu-id="56ace-182">Example</span></span>

<span data-ttu-id="56ace-183">次の例では、ファイル リソースを使用して、ディレクトリとそのサブディレクトリをプル サーバーからターゲット ノードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="56ace-183">The following example copies a directory and its subdirectories from a pull server to a target node using the File Resource.</span></span> <span data-ttu-id="56ace-184">操作が成功すると、Log リソースで確認メッセージがイベント ログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="56ace-184">If the operation succeeds, the Log resource writes a confirmation message to the event log.</span></span>

<span data-ttu-id="56ace-185">ソース ディレクトリは、プル サーバーから共有されている UNC パス (`\\PullServer\DemoSource`) です。</span><span class="sxs-lookup"><span data-stu-id="56ace-185">The source directory is a UNC path (`\\PullServer\DemoSource`) shared from the Pull Server.</span></span> <span data-ttu-id="56ace-186">`Recurse` プロパティを使用すると、すべてのサブディレクトリも確実にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="56ace-186">The `Recurse` property ensures that all subdirectories are copied as well.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="56ace-187">ターゲット ノード上の LCM は、既定でローカル システム アカウントのコンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="56ace-187">The LCM on the target Node executes in the context of the local system account by default.</span></span> <span data-ttu-id="56ace-188">**SourcePath** へのアクセスを許可するには、ターゲット ノードのコンピューター アカウントに適切なアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="56ace-188">To grant access to the **SourcePath**, give the target Node's computer account appropriate permissions.</span></span> <span data-ttu-id="56ace-189">**Credential** と **PSDSCRunAsCredential** (v5) のいずれでも、LCM が **SourcePath** にアクセスするために使用するコンテキストが変更されます。</span><span class="sxs-lookup"><span data-stu-id="56ace-189">The **Credential** and **PSDSCRunAsCredential** (v5) both change the context the LCM uses to access the **SourcePath**.</span></span> <span data-ttu-id="56ace-190">それでも **SourcePath** へのアクセスに使用されるアカウントへのアクセスを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56ace-190">You still need to grant access to the account that will be used to access the **SourcePath**.</span></span>

```powershell
Configuration FileResourceDemo
{
    Node "localhost"
    {
        File DirectoryCopy
        {
            Ensure = "Present" # Ensure the directory is Present on the target node.
            Type = "Directory" # The default is File.
            Recurse = $true # Recursively copy all subdirectories.
            SourcePath = "\\PullServer\DemoSource"
            DestinationPath = "C:\Users\Public\Documents\DSCDemo\DemoDestination"
        }

        Log AfterDirectoryCopy
        {
            # The message below gets written to the Microsoft-Windows-Desired State Configuration/Analytic log
            Message = "Finished running the file resource with ID DirectoryCopy"
            DependsOn = "[File]DirectoryCopy" # Depends on successful execution of the File resource.
        }
    }
}
```

<span data-ttu-id="56ace-191">DSC で**資格情報**を使用する方法の詳細については、[実行ユーザー](../../../configurations/runAsUser.md)または[データの資格情報の構成](../../../configurations/configDataCredentials.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56ace-191">For more on using **Credentials** in DSC see [Run As User](../../../configurations/runAsUser.md) or [Config Data Credentials](../../../configurations/configDataCredentials.md).</span></span>
