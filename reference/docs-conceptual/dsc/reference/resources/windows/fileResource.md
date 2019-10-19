---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC ファイル リソース
ms.openlocfilehash: 4c6945d4cdcbc64ac6d52db563823efe8fd0247e
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954679"
---
# <a name="dsc-file-resource"></a><span data-ttu-id="ef562-103">DSC ファイル リソース</span><span class="sxs-lookup"><span data-stu-id="ef562-103">DSC File Resource</span></span>

> <span data-ttu-id="ef562-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="ef562-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="ef562-105">Windows PowerShell Desired State Configuration (DSC) の **File** リソースは、ターゲット ノード上でファイルとフォルダーを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="ef562-105">The **File** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage files and folders on the target node.</span></span> <span data-ttu-id="ef562-106">**DestinationPath** と **SourcePath** は両方ともターゲット ノードからアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef562-106">**DestinationPath** and **SourcePath** must both be accessible by the target Node.</span></span>

## <a name="syntax"></a><span data-ttu-id="ef562-107">構文</span><span class="sxs-lookup"><span data-stu-id="ef562-107">Syntax</span></span>

```Syntax
File [string] #ResourceName
{
    DestinationPath = [string]
    [ Attributes = [string[]] { Archive | Hidden | ReadOnly | System }]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Contents = [string] ]
    [ Credential = [PSCredential] ]
    [ Force = [bool] ]
    [ Recurse = [bool] ]
    [ SourcePath = [string] ]
    [ Type = [string] { Directory | File } ]
    [ MatchSource = [bool] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="ef562-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ef562-108">Properties</span></span>

|<span data-ttu-id="ef562-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ef562-109">Property</span></span> |<span data-ttu-id="ef562-110">説明</span><span class="sxs-lookup"><span data-stu-id="ef562-110">Description</span></span> |
|---|---|
|<span data-ttu-id="ef562-111">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="ef562-111">DestinationPath</span></span> |<span data-ttu-id="ef562-112">**Ensure** で **Present** または **Absent** であることを保証するターゲット ノード上の場所。</span><span class="sxs-lookup"><span data-stu-id="ef562-112">The location, on the target node, you want to ensure is **Present** or **Absent** with **Ensure**.</span></span> |
|<span data-ttu-id="ef562-113">属性</span><span class="sxs-lookup"><span data-stu-id="ef562-113">Attributes</span></span> |<span data-ttu-id="ef562-114">対象となるファイルまたはディレクトリの属性の望ましい状態。</span><span class="sxs-lookup"><span data-stu-id="ef562-114">The desired state of the attributes for the targeted file or directory.</span></span> <span data-ttu-id="ef562-115">有効な値は、_Archive_、_Hidden_、_ReadOnly_、_System_ です。</span><span class="sxs-lookup"><span data-stu-id="ef562-115">Valid values are _Archive_, _Hidden_, _ReadOnly_, and _System_.</span></span> |
|<span data-ttu-id="ef562-116">チェックサム</span><span class="sxs-lookup"><span data-stu-id="ef562-116">Checksum</span></span> |<span data-ttu-id="ef562-117">2 つのファイルが同じであるかどうかを決定するときに使用するチェックサム タイプ。</span><span class="sxs-lookup"><span data-stu-id="ef562-117">The checksum type to use when determining whether two files are the same.</span></span> <span data-ttu-id="ef562-118">有効な値は、次のとおりです。**SHA-1**、**SHA-256**、**SHA-512**、**createdDate**、**modifiedDate**。</span><span class="sxs-lookup"><span data-stu-id="ef562-118">Valid values include: **SHA-1**, **SHA-256**, **SHA-512**, **createdDate**, **modifiedDate**.</span></span> |
|<span data-ttu-id="ef562-119">内容</span><span class="sxs-lookup"><span data-stu-id="ef562-119">Contents</span></span> |<span data-ttu-id="ef562-120">**File** **型**に使用した場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="ef562-120">Only valid when used with **Type** **File**.</span></span> <span data-ttu-id="ef562-121">**Ensure** (保証) するコンテンツがターゲット ファイルで **Present** または **Absent** であることを示します。</span><span class="sxs-lookup"><span data-stu-id="ef562-121">Indicates the contents to **Ensure** are **Present** or **Absent** from the targeted file.</span></span> |
|<span data-ttu-id="ef562-122">Credential</span><span class="sxs-lookup"><span data-stu-id="ef562-122">Credential</span></span> |<span data-ttu-id="ef562-123">ソース ファイルなどのリソースにアクセスするために必要な資格情報。</span><span class="sxs-lookup"><span data-stu-id="ef562-123">The credentials that are required to access resources, such as source files.</span></span> |
|<span data-ttu-id="ef562-124">Force</span><span class="sxs-lookup"><span data-stu-id="ef562-124">Force</span></span> |<span data-ttu-id="ef562-125">結果としてエラーになるアクセス操作 (ファイルの上書き、空でないディレクトリの削除など) をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="ef562-125">Overrides access operations that would result in an error (such as overwriting a file or deleting a directory that is not empty).</span></span> <span data-ttu-id="ef562-126">既定値は `$false` です。</span><span class="sxs-lookup"><span data-stu-id="ef562-126">Default value is `$false`.</span></span> |
|<span data-ttu-id="ef562-127">Recurse</span><span class="sxs-lookup"><span data-stu-id="ef562-127">Recurse</span></span> |<span data-ttu-id="ef562-128">**Directory** **型**に使用した場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="ef562-128">Only valid when used with **Type** **Directory**.</span></span> <span data-ttu-id="ef562-129">すべてのサブディレクトリに対して状態操作を再帰的に実行します。</span><span class="sxs-lookup"><span data-stu-id="ef562-129">Performs the state operation recursively to all subdirectories.</span></span> <span data-ttu-id="ef562-130">既定値は `$false` です。</span><span class="sxs-lookup"><span data-stu-id="ef562-130">Default value is `$false`.</span></span> |
|<span data-ttu-id="ef562-131">SourcePath</span><span class="sxs-lookup"><span data-stu-id="ef562-131">SourcePath</span></span> |<span data-ttu-id="ef562-132">ファイルまたはフォルダー リソースのコピー元のパス。</span><span class="sxs-lookup"><span data-stu-id="ef562-132">The path from which to copy the file or folder resource.</span></span> |
|<span data-ttu-id="ef562-133">種類</span><span class="sxs-lookup"><span data-stu-id="ef562-133">Type</span></span> |<span data-ttu-id="ef562-134">構成されるリソースの種類。</span><span class="sxs-lookup"><span data-stu-id="ef562-134">The type of resource being configured.</span></span> <span data-ttu-id="ef562-135">有効な値は **Directory** と **File** です。</span><span class="sxs-lookup"><span data-stu-id="ef562-135">Valid values are **Directory** and **File**.</span></span> <span data-ttu-id="ef562-136">既定値は **File** です。</span><span class="sxs-lookup"><span data-stu-id="ef562-136">Default value is **File**.</span></span> |
|<span data-ttu-id="ef562-137">MatchSource</span><span class="sxs-lookup"><span data-stu-id="ef562-137">MatchSource</span></span> |<span data-ttu-id="ef562-138">最初のコピー後にソース ディレクトリに追加された新しいファイルをリソースで監視するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="ef562-138">Determines if the resource should monitor for new files added to the source directory after the initial copy.</span></span> <span data-ttu-id="ef562-139">`$true` の値は、最初のコピー後、すべての新しいソース ファイルが指定した場所にコピーされることを示します。</span><span class="sxs-lookup"><span data-stu-id="ef562-139">A value of `$true` indicates that, after the initial copy, any new source files should be copied to the destination.</span></span> <span data-ttu-id="ef562-140">`$false` に設定した場合、リソースではソース ディレクトリの内容がキャッシュされ、最初のコピー後に追加されたファイルはすべて無視されます。</span><span class="sxs-lookup"><span data-stu-id="ef562-140">If set to `$false`, the resource caches the contents of the source directory and ignores any files added after the initial copy.</span></span> <span data-ttu-id="ef562-141">既定値は `$false` です。</span><span class="sxs-lookup"><span data-stu-id="ef562-141">Default value is `$false`.</span></span> |

> [!WARNING]
> <span data-ttu-id="ef562-142">**Credential** または **PSRunAsCredential** の値を指定しない場合、リソースはターゲット ノードのコンピューター アカウントを使用して **SourcePath** にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ef562-142">If you do not specify a value for **Credential** or **PSRunAsCredential**, the resource will use the computer account of the target node to access the **SourcePath**.</span></span> <span data-ttu-id="ef562-143">**SourcePath** が UNC 共有の場合、"アクセスが拒否されました" エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ef562-143">When the **SourcePath** is a UNC share, this could result in an "Access Denied" error.</span></span> <span data-ttu-id="ef562-144">アクセス許可が適切に設定されていることを保証するか、**Credential** または **PSRunAsCredential** プロパティを使用して、使用するアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="ef562-144">Please ensure your permissions are set accordingly, or use the **Credential** or **PSRunAsCredential** properties to specify the account that should be used.</span></span>

## <a name="common-properties"></a><span data-ttu-id="ef562-145">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="ef562-145">Common properties</span></span>

|<span data-ttu-id="ef562-146">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ef562-146">Property</span></span> |<span data-ttu-id="ef562-147">説明</span><span class="sxs-lookup"><span data-stu-id="ef562-147">Description</span></span> |
|---|---|
|<span data-ttu-id="ef562-148">DependsOn</span><span class="sxs-lookup"><span data-stu-id="ef562-148">DependsOn</span></span> |<span data-ttu-id="ef562-149">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="ef562-149">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="ef562-150">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="ef562-150">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="ef562-151">Ensure</span><span class="sxs-lookup"><span data-stu-id="ef562-151">Ensure</span></span> |<span data-ttu-id="ef562-152">**Destination** にファイルと **Contents** が存在するか、しないかを判断します。</span><span class="sxs-lookup"><span data-stu-id="ef562-152">Determines whether the file and **Contents** at the **Destination** should exist or not.</span></span> <span data-ttu-id="ef562-153">ファイルが存在することを保証するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="ef562-153">Set this property to **Present** to ensure the file exists.</span></span> <span data-ttu-id="ef562-154">コンテンツが存在しないことを保証するには、**Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="ef562-154">Set it to **Absent** to ensure they do not exist.</span></span> <span data-ttu-id="ef562-155">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="ef562-155">The default value is **Present**.</span></span> |
|<span data-ttu-id="ef562-156">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="ef562-156">PsDscRunAsCredential</span></span> |<span data-ttu-id="ef562-157">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="ef562-157">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="ef562-158">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="ef562-158">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="ef562-159">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef562-159">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

### <a name="additional-information"></a><span data-ttu-id="ef562-160">追加情報</span><span class="sxs-lookup"><span data-stu-id="ef562-160">Additional information</span></span>

- <span data-ttu-id="ef562-161">**DestinationPath** のみを指定した場合、リソースではパスが存在すること (**Present**) または存在しないこと (**Absent**) が保証されます。</span><span class="sxs-lookup"><span data-stu-id="ef562-161">When you only specify a **DestinationPath**, the resource ensures that the path exists if **Present** or does not exist if **Absent**.</span></span>
- <span data-ttu-id="ef562-162">**Type** の値が **Directory** の **SourcePath** と **DestinationPath** を指定すると、リソースではソース ディレクトリがコピー先のパスにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="ef562-162">When you specify a **SourcePath** and a **DestinationPath** with a **Type** value of **Directory**, the resource copies source directory to the destination path.</span></span> <span data-ttu-id="ef562-163">プロパティ **Recurse**、**Force**、**MatchSource** で実行されるコピー操作の種類が変更され、**Credential** ではソース ディレクトリへのアクセスに使用するアカウントが決まります。</span><span class="sxs-lookup"><span data-stu-id="ef562-163">The properties **Recurse**, **Force**, and **MatchSource** change the type of copy operation performed, while **Credential** determines which account to use to access the source directory.</span></span>
- <span data-ttu-id="ef562-164">**Attributes** プロパティの **ReadOnly** 値を **DestinationPath** と共に指定した場合、**Present** で指定のパスが作成され、**Contents** でファイルのコンテンツが設定されることを **Ensure** (保証) してください。</span><span class="sxs-lookup"><span data-stu-id="ef562-164">If you specified a value of **ReadOnly** for the **Attributes** property alongside a **DestinationPath**, **Ensure** **Present** would create the path specified, while **Contents** would set the contents of the file.</span></span> <span data-ttu-id="ef562-165">また、**Absent** 設定で **Attributes** プロパティ全体が無視され、指定のパスであらゆるファイルが削除されることを確認 (**Ensure**) してください。</span><span class="sxs-lookup"><span data-stu-id="ef562-165">An **Ensure** **Absent** setting would ignore the **Attributes** property entirely, and remove any file at the specified path.</span></span>

## <a name="example"></a><span data-ttu-id="ef562-166">例</span><span class="sxs-lookup"><span data-stu-id="ef562-166">Example</span></span>

<span data-ttu-id="ef562-167">次の例では、ファイル リソースを使用して、ディレクトリとそのサブディレクトリをプル サーバーからターゲット ノードにコピーします。</span><span class="sxs-lookup"><span data-stu-id="ef562-167">The following example copies a directory and its subdirectories from a pull server to a target node using the File Resource.</span></span> <span data-ttu-id="ef562-168">操作が成功すると、Log リソースで確認メッセージがイベント ログに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="ef562-168">If the operation succeeds, the Log resource writes a confirmation message to the event log.</span></span>

<span data-ttu-id="ef562-169">ソース ディレクトリは、プル サーバーから共有されている UNC パス (`\\PullServer\DemoSource`) です。</span><span class="sxs-lookup"><span data-stu-id="ef562-169">The source directory is a UNC path (`\\PullServer\DemoSource`) shared from the Pull Server.</span></span> <span data-ttu-id="ef562-170">**Recurse** プロパティを使用すると、すべてのサブディレクトリも確実にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="ef562-170">The **Recurse** property ensures that all subdirectories are copied as well.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef562-171">ターゲット ノード上の LCM は、既定でローカル システム アカウントのコンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="ef562-171">The LCM on the target Node executes in the context of the local system account by default.</span></span> <span data-ttu-id="ef562-172">**SourcePath** へのアクセスを許可するには、ターゲット ノードのコンピューター アカウントに適切なアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="ef562-172">To grant access to the **SourcePath**, give the target Node's computer account appropriate permissions.</span></span> <span data-ttu-id="ef562-173">**Credential** と **PSDSCRunAsCredential** のいずれでも、LCM が **SourcePath** にアクセスするために使用するコンテキストが変更されます。</span><span class="sxs-lookup"><span data-stu-id="ef562-173">The **Credential** and **PSDSCRunAsCredential** both change the context the LCM uses to access the **SourcePath**.</span></span> <span data-ttu-id="ef562-174">それでも **SourcePath** へのアクセスに使用されるアカウントへのアクセスを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef562-174">You still need to grant access to the account that will be used to access the **SourcePath**.</span></span>

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

<span data-ttu-id="ef562-175">DSC で**資格情報**を使用する方法の詳細については、[実行ユーザー](../../../configurations/runAsUser.md)または[データの資格情報の構成](../../../configurations/configDataCredentials.md)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ef562-175">For more on using **Credentials** in DSC see [Run As User](../../../configurations/runAsUser.md) or [Config Data Credentials](../../../configurations/configDataCredentials.md).</span></span>