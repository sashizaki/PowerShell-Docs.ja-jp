---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC ファイル リソース
ms.openlocfilehash: 86a5dcd97b4163b3780038c815d3de5a523ce4bf
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34218945"
---
# <a name="dsc-file-resource"></a><span data-ttu-id="2b570-103">DSC ファイル リソース</span><span class="sxs-lookup"><span data-stu-id="2b570-103">DSC File Resource</span></span>

> <span data-ttu-id="2b570-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="2b570-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="2b570-105">Windows PowerShell Desired State Configuration (DSC) の File リソースは、ターゲット ノード上でファイルとフォルダーを管理するためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="2b570-105">The File resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage files and folders on the target node.</span></span>

><span data-ttu-id="2b570-106">**注:** **MatchSource** プロパティが **$false** (既定値) に送信される場合、最初に構成が適用されるとき、コピー対象のコンテンツがキャッシュされます。</span><span class="sxs-lookup"><span data-stu-id="2b570-106">**Note:** If the **MatchSource** property is set to **$false** (which is the default value), the contents to be copied are cached the first time the configuration is applied.</span></span>
><span data-ttu-id="2b570-107">構成の後続のアプリケーションは、**SourcePath** で指定された更新済みのファイルやフォルダーを確認しません。</span><span class="sxs-lookup"><span data-stu-id="2b570-107">Subsequent applications of the configuration will not check for updated files and/or folders in the path specified by **SourcePath**.</span></span> <span data-ttu-id="2b570-108">構成が適用されるたびに **SourcePath** のファイルまたはフォルダーの更新を確認する場合、**MatchSource** を **$true** に設定します。</span><span class="sxs-lookup"><span data-stu-id="2b570-108">If you want to check for updates to the files and/or folders in **SourcePath** every time the configuration is applied, set **MatchSource** to **$true**.</span></span>

## <a name="syntax"></a><span data-ttu-id="2b570-109">構文</span><span class="sxs-lookup"><span data-stu-id="2b570-109">Syntax</span></span>
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

## <a name="properties"></a><span data-ttu-id="2b570-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2b570-110">Properties</span></span>

|  <span data-ttu-id="2b570-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="2b570-111">Property</span></span>  |  <span data-ttu-id="2b570-112">説明</span><span class="sxs-lookup"><span data-stu-id="2b570-112">Description</span></span>   |
|---|---|
| <span data-ttu-id="2b570-113">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="2b570-113">DestinationPath</span></span>| <span data-ttu-id="2b570-114">ファイルまたはディレクトリの状態を保証する場所を示します。</span><span class="sxs-lookup"><span data-stu-id="2b570-114">Indicates the location where you want to ensure the state for a file or directory.</span></span>|
| <span data-ttu-id="2b570-115">属性</span><span class="sxs-lookup"><span data-stu-id="2b570-115">Attributes</span></span>| <span data-ttu-id="2b570-116">対象となるファイルまたはディレクトリの属性の望ましい状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b570-116">Specifies the desired state of the attributes for the targeted file or directory.</span></span>|
| <span data-ttu-id="2b570-117">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2b570-117">Checksum</span></span>| <span data-ttu-id="2b570-118">2 つのファイルが同じであるかどうかを決定するときに使用するチェックサム タイプを示します。</span><span class="sxs-lookup"><span data-stu-id="2b570-118">Indicates the checksum type to use when determining whether two files are the same.</span></span> <span data-ttu-id="2b570-119">__Checksum__ が指定されていない場合、ファイルまたはディレクトリ名のみが比較に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2b570-119">If __Checksum__ is not specified, only the file or directory name is used for comparison.</span></span> <span data-ttu-id="2b570-120">有効な値は、SHA-1、SHA-256、SHA-512、createdDate、modifiedDate です。</span><span class="sxs-lookup"><span data-stu-id="2b570-120">Valid values include: SHA-1, SHA-256, SHA-512, createdDate, modifiedDate.</span></span>|
| <span data-ttu-id="2b570-121">内容</span><span class="sxs-lookup"><span data-stu-id="2b570-121">Contents</span></span>| <span data-ttu-id="2b570-122">特定の文字列など、ファイルの内容を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b570-122">Specifies the contents of a file, such as a particular string.</span></span>|
| <span data-ttu-id="2b570-123">Credential</span><span class="sxs-lookup"><span data-stu-id="2b570-123">Credential</span></span>| <span data-ttu-id="2b570-124">ソース ファイルなどのリソースにアクセスする必要がある場合、このようなアクセスに必要な資格情報を示します。</span><span class="sxs-lookup"><span data-stu-id="2b570-124">Indicates the credentials that are required to access resources, such as source files, if such access is required.</span></span>|
| <span data-ttu-id="2b570-125">Ensure</span><span class="sxs-lookup"><span data-stu-id="2b570-125">Ensure</span></span>| <span data-ttu-id="2b570-126">ファイルまたはディレクトリが存在するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2b570-126">Indicates if the file or directory exists.</span></span> <span data-ttu-id="2b570-127">ファイルまたはディレクトリが存在しないことを保証するには、このプロパティを "Absent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="2b570-127">Set this property to "Absent" to ensure that the file or directory does not exist.</span></span> <span data-ttu-id="2b570-128">ファイルまたはディレクトリが存在することを保証するには、このプロパティを "Present" に設定します。</span><span class="sxs-lookup"><span data-stu-id="2b570-128">Set it to "Present" to ensure that the file or directory does exist.</span></span> <span data-ttu-id="2b570-129">既定は "Present" です。</span><span class="sxs-lookup"><span data-stu-id="2b570-129">The default is "Present".</span></span>|
| <span data-ttu-id="2b570-130">Force</span><span class="sxs-lookup"><span data-stu-id="2b570-130">Force</span></span>| <span data-ttu-id="2b570-131">特定のファイル操作 (ファイルの上書き、空でないディレクトリの削除など) によって、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="2b570-131">Certain file operations (such as overwriting a file or deleting a directory that is not empty) will result in an error.</span></span> <span data-ttu-id="2b570-132">Force プロパティを使用すると、このようなエラーが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="2b570-132">Using the Force property overrides such errors.</span></span> <span data-ttu-id="2b570-133">既定値は __$false__ です。</span><span class="sxs-lookup"><span data-stu-id="2b570-133">The default value is __$false__.</span></span>|
| <span data-ttu-id="2b570-134">Recurse</span><span class="sxs-lookup"><span data-stu-id="2b570-134">Recurse</span></span>| <span data-ttu-id="2b570-135">サブディレクトリが含まれるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2b570-135">Indicates if subdirectories are included.</span></span> <span data-ttu-id="2b570-136">サブディレクトリを含めるようにするには、このプロパティを __$true__ に設定します。</span><span class="sxs-lookup"><span data-stu-id="2b570-136">Set this property to __$true__ to indicate that you want subdirectories to be included.</span></span> <span data-ttu-id="2b570-137">既定値は __$false__ です。</span><span class="sxs-lookup"><span data-stu-id="2b570-137">The default is __$false__.</span></span> <span data-ttu-id="2b570-138">**注**: このプロパティは、Type プロパティが Directory に設定されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="2b570-138">**Note**: This property is only valid when the Type property is set to Directory.</span></span>|
| <span data-ttu-id="2b570-139">DependsOn</span><span class="sxs-lookup"><span data-stu-id="2b570-139">DependsOn</span></span> | <span data-ttu-id="2b570-140">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="2b570-140">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="2b570-141">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="2b570-141">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="2b570-142">SourcePath</span><span class="sxs-lookup"><span data-stu-id="2b570-142">SourcePath</span></span>| <span data-ttu-id="2b570-143">ファイルまたはフォルダー リソースのコピー元のパスを示します。</span><span class="sxs-lookup"><span data-stu-id="2b570-143">Indicates the path from which to copy the file or folder resource.</span></span>|
| <span data-ttu-id="2b570-144">種類</span><span class="sxs-lookup"><span data-stu-id="2b570-144">Type</span></span>| <span data-ttu-id="2b570-145">構成されているリソースがディレクトリまたはファイルのいずれであるかを示します。</span><span class="sxs-lookup"><span data-stu-id="2b570-145">Indicates if the resource being configured is a directory or a file.</span></span> <span data-ttu-id="2b570-146">リソースがディレクトリであることを示すには、このプロパティを "Directory" に設定します。</span><span class="sxs-lookup"><span data-stu-id="2b570-146">Set this property to "Directory" to indicate that the resource is a directory.</span></span> <span data-ttu-id="2b570-147">リソースがファイルであることを示すには、"File" に設定します。</span><span class="sxs-lookup"><span data-stu-id="2b570-147">Set it to "File" to indicate that the resource is a file.</span></span> <span data-ttu-id="2b570-148">既定値は "File" です。</span><span class="sxs-lookup"><span data-stu-id="2b570-148">The default value is “File”.</span></span>|
| <span data-ttu-id="2b570-149">MatchSource</span><span class="sxs-lookup"><span data-stu-id="2b570-149">MatchSource</span></span>| <span data-ttu-id="2b570-150">既定値の __$false__ に設定した場合、最初に構成が適用されるときにソース (たとえば、ファイル A、B、および C) 上のファイルが宛先に追加されます。</span><span class="sxs-lookup"><span data-stu-id="2b570-150">If set to the default value of __$false__, then any files on the source (say, files A, B, and C) will be added to the destination the first time the configuration is applied.</span></span> <span data-ttu-id="2b570-151">新しいファイル (D) がソースに追加された場合、構成が後で再適用された場合にも、このファイルは宛先に追加されません。</span><span class="sxs-lookup"><span data-stu-id="2b570-151">If a new file (D) is added to the source, it will not be added to the destination, even when the configuration is re-applied later.</span></span> <span data-ttu-id="2b570-152">値が __$true__ の場合、構成が適用されるたびに、後でソースで検出された新しいファイル (この例のファイル D など) が宛先に追加されます。</span><span class="sxs-lookup"><span data-stu-id="2b570-152">If the value is __$true__, then each time the configuration is applied, new files subsequently found on the source (such as file D in this example) are added to the destination.</span></span> <span data-ttu-id="2b570-153">既定値は **$false** です。</span><span class="sxs-lookup"><span data-stu-id="2b570-153">The default value is **$false**.</span></span>|

## <a name="example"></a><span data-ttu-id="2b570-154">例</span><span class="sxs-lookup"><span data-stu-id="2b570-154">Example</span></span>

<span data-ttu-id="2b570-155">次の例は、File リソースを使用して、("プル" サーバーなどの) ソース コンピューター上のパス `C:\Users\Public\Documents\DSCDemo\DemoSource` のディレクトリがターゲット ノードにも (すべてのサブディレクトリと共に) 存在することを保証する例を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b570-155">The following example shows how to use the File resource to ensure that a directory with the path `C:\Users\Public\Documents\DSCDemo\DemoSource` on a source computer (such as the “pull” server) is also present (along with all subdirectories) on the target node.</span></span> <span data-ttu-id="2b570-156">また、完了時に確認メッセージもログに書き込まれ、ログ記録操作の前にファイル チェック操作が実行されるようにするステートメントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b570-156">It also writes a confirmatory message to the log when complete and includes a statement to ensure that the file-checking operation runs prior to the logging operation.</span></span>

```powershell
Configuration FileResourceDemo
{
    Node "localhost"
    {
        File DirectoryCopy
        {
            Ensure = "Present"  # You can also set Ensure to "Absent"
            Type = "Directory" # Default is "File".
            Recurse = $true # Ensure presence of subdirectories, too
            SourcePath = "C:\Users\Public\Documents\DSCDemo\DemoSource"
            DestinationPath = "C:\Users\Public\Documents\DSCDemo\DemoDestination"
        }

        Log AfterDirectoryCopy
        {
            # The message below gets written to the Microsoft-Windows-Desired State Configuration/Analytic log
            Message = "Finished running the file resource with ID DirectoryCopy"
            DependsOn = "[File]DirectoryCopy" # This means run "DirectoryCopy" first.
        }
    }
}
```