---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "Linux 用 DSC の nxArchive リソース"
ms.openlocfilehash: e91ef5bcf4bdf413844c23d1d3bd823a535b536f
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="dsc-for-linux-nxarchive-resource"></a><span data-ttu-id="62f5b-103">Linux 用 DSC の nxArchive リソース</span><span class="sxs-lookup"><span data-stu-id="62f5b-103">DSC for Linux nxArchive Resource</span></span>

<span data-ttu-id="62f5b-104">PowerShell Desired State Configuration (DSC) の **nxArchive** リソースは、Linux ノード上の特定のパスでアーカイブ (.tar、.zip) ファイルをアンパックするメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="62f5b-104">The **nxArchive** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to unpack archive (.tar, .zip) files at a specific path on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="62f5b-105">構文</span><span class="sxs-lookup"><span data-stu-id="62f5b-105">Syntax</span></span>

```
nxArchive <string> #ResourceName
{
    SourcePath = <string>
    DestinationPath = <string>
    [ Checksum = <string> { ctime | mtime | md5 }  ]
    [ Force = <bool> ]
    [ DependsOn = <string[]> ]
    [ Ensure = <string> { Absent | Present }  ]
}
```

## <a name="properties"></a><span data-ttu-id="62f5b-106">プロパティ</span><span class="sxs-lookup"><span data-stu-id="62f5b-106">Properties</span></span>

|  <span data-ttu-id="62f5b-107">プロパティ</span><span class="sxs-lookup"><span data-stu-id="62f5b-107">Property</span></span> |  <span data-ttu-id="62f5b-108">説明</span><span class="sxs-lookup"><span data-stu-id="62f5b-108">Description</span></span> | 
|---|---|
| <span data-ttu-id="62f5b-109">SourcePath</span><span class="sxs-lookup"><span data-stu-id="62f5b-109">SourcePath</span></span>| <span data-ttu-id="62f5b-110">アーカイブ ファイルのソース パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="62f5b-110">Specifies the source path of the archive file.</span></span> <span data-ttu-id="62f5b-111">これは .tar、.zip、または .tar.gz ファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="62f5b-111">This should be a .tar, .zip, or .tar.gz file.</span></span> | 
| <span data-ttu-id="62f5b-112">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="62f5b-112">DestinationPath</span></span>| <span data-ttu-id="62f5b-113">アーカイブ コンテンツが抽出されることを保証する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="62f5b-113">Specifies the location where you want to ensure the archive contents are extracted.</span></span>| 
| <span data-ttu-id="62f5b-114">チェックサム</span><span class="sxs-lookup"><span data-stu-id="62f5b-114">Checksum</span></span>| <span data-ttu-id="62f5b-115">ソース アーカイブが更新されたかどうかを確認するときに使用するタイプを定義します。</span><span class="sxs-lookup"><span data-stu-id="62f5b-115">Defines the type to use when determining whether the source archive has been updated.</span></span> <span data-ttu-id="62f5b-116">値は、"ctime"、"mtime"、または "md5" です。</span><span class="sxs-lookup"><span data-stu-id="62f5b-116">Values are: "ctime", "mtime", or "md5".</span></span> <span data-ttu-id="62f5b-117">既定値は "md5" です。</span><span class="sxs-lookup"><span data-stu-id="62f5b-117">The default value is "md5".</span></span>| 
| <span data-ttu-id="62f5b-118">Force</span><span class="sxs-lookup"><span data-stu-id="62f5b-118">Force</span></span>| <span data-ttu-id="62f5b-119">特定のファイル操作 (ファイルの上書き、空でないディレクトリの削除など) によって、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="62f5b-119">Certain file operations (such as overwriting a file or deleting a directory that is not empty) will result in an error.</span></span> <span data-ttu-id="62f5b-120">**Force** プロパティを使用すると、このようなエラーが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="62f5b-120">Using the **Force** property overrides such errors.</span></span> <span data-ttu-id="62f5b-121">既定値は **$false** です。</span><span class="sxs-lookup"><span data-stu-id="62f5b-121">The default value is **$false**.</span></span>| 
| <span data-ttu-id="62f5b-122">DependsOn</span><span class="sxs-lookup"><span data-stu-id="62f5b-122">DependsOn</span></span> | <span data-ttu-id="62f5b-123">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="62f5b-123">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="62f5b-124">たとえば、最初に実行するリソース構成スクリプト ブロックの **ID** が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="62f5b-124">For example, if the **ID** of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>| 
| <span data-ttu-id="62f5b-125">Ensure</span><span class="sxs-lookup"><span data-stu-id="62f5b-125">Ensure</span></span>| <span data-ttu-id="62f5b-126">アーカイブのコンテンツが **Destination** に存在するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="62f5b-126">Determines whether to check if the content of the archive exists at the **Destination**.</span></span> <span data-ttu-id="62f5b-127">コンテンツが存在することを保証するには、このプロパティを "Present" に設定します。</span><span class="sxs-lookup"><span data-stu-id="62f5b-127">Set this property to "Present" to ensure the contents exist.</span></span> <span data-ttu-id="62f5b-128">コンテンツが存在しないことを保証するには、"Absent" に設定します。</span><span class="sxs-lookup"><span data-stu-id="62f5b-128">Set it to "Absent" to ensure they do not exist.</span></span> <span data-ttu-id="62f5b-129">既定値は "Present" です。</span><span class="sxs-lookup"><span data-stu-id="62f5b-129">The default value is "Present".</span></span>| 

## <a name="example"></a><span data-ttu-id="62f5b-130">例</span><span class="sxs-lookup"><span data-stu-id="62f5b-130">Example</span></span>

<span data-ttu-id="62f5b-131">次の例は、**nxArchive** リソースを使用して、`website.tar` というアーカイブ ファイルのコンテンツが指定した宛先に存在し、抽出されていることを保証する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="62f5b-131">The following example shows how to use the **nxArchive** resource to ensure that the contents of an archive file called `website.tar` exist and are extracted at a given destination.</span></span>

```
Import-DSCResource -Module nx 

nxFile SyncArchiveFromWeb
{
   Ensure = "Present"
   SourcePath = “http://release.contoso.com/releases/website.tar”
   DestinationPath = "/usr/release/staging/website.tar"
   Type = "File"
   Checksum = “mtime”
}

nxArchive SyncWebDir
{
   SourcePath = “/usr/release/staging/website.tar”
   DestinationPath = “/usr/local/apache2/htdocs/”
   Force = $false
   DependsOn = "[nxFile]SyncArchiveFromWeb"
} 
```

