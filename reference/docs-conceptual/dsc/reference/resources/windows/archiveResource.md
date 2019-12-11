---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Archive リソース
ms.openlocfilehash: ddabe1a623783fe213b8059f47851184d5253fc5
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71954769"
---
# <a name="dsc-archive-resource"></a><span data-ttu-id="1e60b-103">DSC Archive リソース</span><span class="sxs-lookup"><span data-stu-id="1e60b-103">DSC Archive Resource</span></span>

> <span data-ttu-id="1e60b-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="1e60b-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="1e60b-105">Windows PowerShell Desired State Configuration (DSC) の Archive リソースは、特定のパスでアーカイブ (.zip) ファイルをアンパックするメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="1e60b-105">The Archive resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to unpack archive (.zip) files at a specific path.</span></span>

## <a name="syntax"></a><span data-ttu-id="1e60b-106">構文</span><span class="sxs-lookup"><span data-stu-id="1e60b-106">Syntax</span></span>

```Syntax
Archive [string] #ResourceName
{
    Destination = [string]
    Path = [string]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Force = [bool] ]
    [ Validate = [bool] ]
    [ Ensure = [string] { Absent | Present } ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="1e60b-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e60b-107">Properties</span></span>

|<span data-ttu-id="1e60b-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e60b-108">Property</span></span> |<span data-ttu-id="1e60b-109">説明</span><span class="sxs-lookup"><span data-stu-id="1e60b-109">Description</span></span> |
|---|---|
|<span data-ttu-id="1e60b-110">Destination</span><span class="sxs-lookup"><span data-stu-id="1e60b-110">Destination</span></span> |<span data-ttu-id="1e60b-111">アーカイブ コンテンツが抽出されることを保証する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="1e60b-111">Specifies the location where you want to ensure the archive contents are extracted.</span></span> |
|<span data-ttu-id="1e60b-112">パス</span><span class="sxs-lookup"><span data-stu-id="1e60b-112">Path</span></span> |<span data-ttu-id="1e60b-113">アーカイブ ファイルのソース パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e60b-113">Specifies the source path of the archive file.</span></span> |
|<span data-ttu-id="1e60b-114">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1e60b-114">Checksum</span></span> |<span data-ttu-id="1e60b-115">2 つのファイルが同じであるかどうかを決定するときに使用するタイプを定義します。</span><span class="sxs-lookup"><span data-stu-id="1e60b-115">Defines the type to use when determining whether two files are the same.</span></span> <span data-ttu-id="1e60b-116">**Checksum** が指定されていない場合、ファイルまたはディレクトリ名のみが比較に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1e60b-116">If **Checksum** is not specified, only the file or directory name is used for comparison.</span></span> <span data-ttu-id="1e60b-117">有効な値は、次のとおりです。**SHA-1**、**SHA-256**、**SHA-512**、**createdDate**、**modifiedDate**。</span><span class="sxs-lookup"><span data-stu-id="1e60b-117">Valid values include: **SHA-1**, **SHA-256**, **SHA-512**, **createdDate**, **modifiedDate**.</span></span> <span data-ttu-id="1e60b-118">**Validate** を指定せずに **Checksum** を指定した場合、構成は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1e60b-118">If you specify **Checksum** without **Validate**, the configuration will fail.</span></span> |
|<span data-ttu-id="1e60b-119">Force</span><span class="sxs-lookup"><span data-stu-id="1e60b-119">Force</span></span> |<span data-ttu-id="1e60b-120">特定のファイル操作 (ファイルの上書き、空でないディレクトリの削除など) によって、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1e60b-120">Certain file operations (such as overwriting a file or deleting a directory that is not empty) will result in an error.</span></span> <span data-ttu-id="1e60b-121">**Force** プロパティを使用すると、このようなエラーがオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="1e60b-121">Using the **Force** property overrides such errors.</span></span> <span data-ttu-id="1e60b-122">既定値は **False**です。</span><span class="sxs-lookup"><span data-stu-id="1e60b-122">The default value is **False**.</span></span> |
|<span data-ttu-id="1e60b-123">[検証]</span><span class="sxs-lookup"><span data-stu-id="1e60b-123">Validate</span></span>| <span data-ttu-id="1e60b-124">**Checksum** プロパティを使用して、アーカイブが署名と一致するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1e60b-124">Uses the **Checksum** property to determine if the archive matches the signature.</span></span> <span data-ttu-id="1e60b-125">**Validate** を指定せずに **Checksum** を指定した場合、構成は失敗します。</span><span class="sxs-lookup"><span data-stu-id="1e60b-125">If you specify **Checksum** without **Validate**, the configuration will fail.</span></span> <span data-ttu-id="1e60b-126">**Checksum** を指定せずに **Validate** を指定した場合、_SHA-256_ **チェックサム**が既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="1e60b-126">If you specify **Validate** without **Checksum**, a _SHA-256_ **Checksum** is used by default.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="1e60b-127">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e60b-127">Common properties</span></span>

|<span data-ttu-id="1e60b-128">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e60b-128">Property</span></span> |<span data-ttu-id="1e60b-129">説明</span><span class="sxs-lookup"><span data-stu-id="1e60b-129">Description</span></span> |
|---|---|
|<span data-ttu-id="1e60b-130">DependsOn</span><span class="sxs-lookup"><span data-stu-id="1e60b-130">DependsOn</span></span> |<span data-ttu-id="1e60b-131">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="1e60b-131">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="1e60b-132">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="1e60b-132">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="1e60b-133">Ensure</span><span class="sxs-lookup"><span data-stu-id="1e60b-133">Ensure</span></span> |<span data-ttu-id="1e60b-134">アーカイブのコンテンツが **Destination** に存在するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="1e60b-134">Determines whether to check if the content of the archive exists at the **Destination**.</span></span> <span data-ttu-id="1e60b-135">コンテンツが存在することを保証するには、このプロパティを **Present** に設定します。</span><span class="sxs-lookup"><span data-stu-id="1e60b-135">Set this property to **Present** to ensure the contents exist.</span></span> <span data-ttu-id="1e60b-136">コンテンツが存在しないことを保証するには、**Absent** に設定します。</span><span class="sxs-lookup"><span data-stu-id="1e60b-136">Set it to **Absent** to ensure they do not exist.</span></span> <span data-ttu-id="1e60b-137">既定値は **Present** です。</span><span class="sxs-lookup"><span data-stu-id="1e60b-137">The default value is **Present**.</span></span> |
|<span data-ttu-id="1e60b-138">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="1e60b-138">PsDscRunAsCredential</span></span> |<span data-ttu-id="1e60b-139">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="1e60b-139">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="1e60b-140">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="1e60b-140">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="1e60b-141">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e60b-141">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="1e60b-142">例</span><span class="sxs-lookup"><span data-stu-id="1e60b-142">Example</span></span>

<span data-ttu-id="1e60b-143">次の例は、Archive リソースを使用して、`Test.zip` というアーカイブ ファイルのコンテンツが指定した宛先に存在し、抽出されていることを保証する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1e60b-143">The following example shows how to use the Archive resource to ensure that the contents of an archive file called `Test.zip` exist and are extracted at a given destination.</span></span>

```powershell
Archive ArchiveExample {
    Ensure = "Present"
    Path = "C:\Users\Public\Documents\Test.zip"
    Destination = "C:\Users\Public\Documents\ExtractionPath"
}
```