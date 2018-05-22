---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Archive リソース
ms.openlocfilehash: 458b4f0f20dc96dab62e709183c25ff57d971aae
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="dsc-archive-resource"></a><span data-ttu-id="88a69-103">DSC Archive リソース</span><span class="sxs-lookup"><span data-stu-id="88a69-103">DSC Archive Resource</span></span>

> <span data-ttu-id="88a69-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="88a69-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="88a69-105">Windows PowerShell Desired State Configuration (DSC) の Archive リソースは、特定のパスでアーカイブ (.zip) ファイルをアンパックするメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="88a69-105">The Archive resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to unpack archive (.zip) files at a specific path.</span></span>

## <a name="syntax"></a><span data-ttu-id="88a69-106">構文</span><span class="sxs-lookup"><span data-stu-id="88a69-106">Syntax</span></span>
```MOF
Archive [string] #ResourceName
{
    Destination = [string]
    Path = [string]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ Force = [bool] ]
    [ Validate = [bool] ]
}
```

## <a name="properties"></a><span data-ttu-id="88a69-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="88a69-107">Properties</span></span>

|  <span data-ttu-id="88a69-108">プロパティ</span><span class="sxs-lookup"><span data-stu-id="88a69-108">Property</span></span>  |  <span data-ttu-id="88a69-109">説明</span><span class="sxs-lookup"><span data-stu-id="88a69-109">Description</span></span>   |
|---|---|
| <span data-ttu-id="88a69-110">Destination</span><span class="sxs-lookup"><span data-stu-id="88a69-110">Destination</span></span>| <span data-ttu-id="88a69-111">アーカイブ コンテンツが抽出されることを保証する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="88a69-111">Specifies the location where you want to ensure the archive contents are extracted.</span></span>|
| <span data-ttu-id="88a69-112">パス</span><span class="sxs-lookup"><span data-stu-id="88a69-112">Path</span></span>| <span data-ttu-id="88a69-113">アーカイブ ファイルのソース パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="88a69-113">Specifies the source path of the archive file.</span></span>|
| <span data-ttu-id="88a69-114">__チェックサム__</span><span class="sxs-lookup"><span data-stu-id="88a69-114">__Checksum__</span></span>| <span data-ttu-id="88a69-115">2 つのファイルが同じであるかどうかを決定するときに使用するタイプを定義します。</span><span class="sxs-lookup"><span data-stu-id="88a69-115">Defines the type to use when determining whether two files are the same.</span></span> <span data-ttu-id="88a69-116">__Checksum__ が指定されていない場合、ファイルまたはディレクトリ名のみが比較に使用されます。</span><span class="sxs-lookup"><span data-stu-id="88a69-116">If __Checksum__ is not specified, only the file or directory name is used for comparison.</span></span> <span data-ttu-id="88a69-117">有効な値は、SHA-1、SHA-256、SHA-512、createdDate、modifiedDate、none (既定) です。</span><span class="sxs-lookup"><span data-stu-id="88a69-117">Valid values include: SHA-1, SHA-256, SHA-512, createdDate, modifiedDate, none (default).</span></span> <span data-ttu-id="88a69-118">__Validate__ を指定せずに __Checksum__ を指定した場合、構成は失敗します。</span><span class="sxs-lookup"><span data-stu-id="88a69-118">If you specify __Checksum__ without __Validate__, the configuration will fail.</span></span>|
| <span data-ttu-id="88a69-119">Ensure</span><span class="sxs-lookup"><span data-stu-id="88a69-119">Ensure</span></span>| <span data-ttu-id="88a69-120">アーカイブのコンテンツが __Destination__ に存在するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="88a69-120">Determines whether to check if the content of the archive exists at the __Destination__.</span></span> <span data-ttu-id="88a69-121">コンテンツが存在することを保証するには、このプロパティを __Present__ に設定します。</span><span class="sxs-lookup"><span data-stu-id="88a69-121">Set this property to __Present__ to ensure the contents exist.</span></span> <span data-ttu-id="88a69-122">コンテンツが存在しないことを保証するには、__Absent__ に設定します。</span><span class="sxs-lookup"><span data-stu-id="88a69-122">Set it to __Absent__ to ensure they do not exist.</span></span> <span data-ttu-id="88a69-123">既定値は __Present__ です。</span><span class="sxs-lookup"><span data-stu-id="88a69-123">The default value is __Present__.</span></span>|
| <span data-ttu-id="88a69-124">DependsOn</span><span class="sxs-lookup"><span data-stu-id="88a69-124">DependsOn</span></span> | <span data-ttu-id="88a69-125">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="88a69-125">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="88a69-126">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="88a69-126">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="88a69-127">[検証]</span><span class="sxs-lookup"><span data-stu-id="88a69-127">Validate</span></span>| <span data-ttu-id="88a69-128">Checksum プロパティを使用して、アーカイブが署名と一致するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="88a69-128">Uses the Checksum property to determine if the archive matches the signature.</span></span> <span data-ttu-id="88a69-129">Validate を指定せずに Checksum を指定した場合、構成は失敗します。</span><span class="sxs-lookup"><span data-stu-id="88a69-129">If you specify Checksum without Validate, the configuration will fail.</span></span> <span data-ttu-id="88a69-130">Checksum を指定せずに Validate を指定した場合、SHA-256 チェックサムが既定で使用されます。</span><span class="sxs-lookup"><span data-stu-id="88a69-130">If you specify Validate without Checksum, a SHA-256 checksum is used by default.</span></span>|
| <span data-ttu-id="88a69-131">Force</span><span class="sxs-lookup"><span data-stu-id="88a69-131">Force</span></span>| <span data-ttu-id="88a69-132">特定のファイル操作 (ファイルの上書き、空でないディレクトリの削除など) によって、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="88a69-132">Certain file operations (such as overwriting a file or deleting a directory that is not empty) will result in an error.</span></span> <span data-ttu-id="88a69-133">Force プロパティを使用すると、このようなエラーが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="88a69-133">Using the Force property overrides such errors.</span></span> <span data-ttu-id="88a69-134">既定値は False です。</span><span class="sxs-lookup"><span data-stu-id="88a69-134">The default value is False.</span></span>|

## <a name="example"></a><span data-ttu-id="88a69-135">例</span><span class="sxs-lookup"><span data-stu-id="88a69-135">Example</span></span>

<span data-ttu-id="88a69-136">次の例は、Archive リソースを使用して、Test.zip というアーカイブ ファイルのコンテンツが指定した宛先に存在し、抽出されていることを保証する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="88a69-136">The following example shows how to use the Archive resource to ensure that the contents of an archive file called Test.zip exist and are extracted at a given destination.</span></span>

```
Archive ArchiveExample {
    Ensure = "Present"  # You can also set Ensure to "Absent"
    Path = "C:\Users\Public\Documents\Test.zip"
    Destination = "C:\Users\Public\Documents\ExtractionPath"
}
```