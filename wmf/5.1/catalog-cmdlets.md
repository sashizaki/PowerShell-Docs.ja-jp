---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: WMF, PowerShell, セットアップ
title: カタログ コマンドレット
ms.openlocfilehash: 7eaca09667af0eb5d719f23e987bb112e8514978
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="catalog-cmdlets"></a><span data-ttu-id="380f4-103">カタログ コマンドレット</span><span class="sxs-lookup"><span data-stu-id="380f4-103">Catalog Cmdlets</span></span>

<span data-ttu-id="380f4-104">[Microsoft.Powershell.Secuity](https://technet.microsoft.com/en-us/library/hh847877.aspx) モジュールに新しいコマンドレットが 2 つ追加されました。Windows カタログ ファイルを生成し、検証するコマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="380f4-104">We have added two new cmdlets in [Microsoft.Powershell.Secuity](https://technet.microsoft.com/en-us/library/hh847877.aspx) module to generate and validate windows catalog files.</span></span>

## <a name="new-filecatalog"></a><span data-ttu-id="380f4-105">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="380f4-105">New-FileCatalog</span></span>
--------------------------------

<span data-ttu-id="380f4-106">`New-FileCatalog` は、一連のフォルダーやファイルに対して Windows カタログ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="380f4-106">`New-FileCatalog` creates a windows catalog file for set of folders and files.</span></span> <span data-ttu-id="380f4-107">カタログ ファイルには、指定されたパスのすべてのファイルのハッシュが含まれています。</span><span class="sxs-lookup"><span data-stu-id="380f4-107">A catalog file contains hashes for all files in specified paths.</span></span> <span data-ttu-id="380f4-108">ユーザーは一連のフォルダーと共に、それらのフォルダーを表すカタログ ファイルを配信できます。</span><span class="sxs-lookup"><span data-stu-id="380f4-108">Users can distribute the set of folders along with corresponding the catalog file that represents those folders.</span></span> <span data-ttu-id="380f4-109">コンテンツの受信側は、カタログ ファイルを使用して、カタログが作成された後にフォルダーに変更が行われたかどうかを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="380f4-109">A catalog file can be used by the recipient of content to validate whether any changes were made to the folders after the catalog was created.</span></span>

```powershell
New-FileCatalog [-CatalogFilePath] <string> [[-Path] <string[]>] [-CatalogVersion <int>] [-WhatIf] [-Confirm] [<CommonParameters>]
```
<span data-ttu-id="380f4-110">カタログのバージョン 1 と 2 を作成できます。</span><span class="sxs-lookup"><span data-stu-id="380f4-110">We support creating catalog version 1 and 2.</span></span> <span data-ttu-id="380f4-111">バージョン 1 は SHA1 ハッシュ アルゴリズムを使用して、バージョン 2 は SHA256 ハッシュ アルゴリズムを使用してファイル ハッシュを作成します。</span><span class="sxs-lookup"><span data-stu-id="380f4-111">Version 1 uses SHA1 hashing algorithm to create file hashes and version 2 uses SHA256.</span></span> <span data-ttu-id="380f4-112">*Windows Server 2008 R2* と *Windows 7* はカタログ バージョン 2 に対応していません。</span><span class="sxs-lookup"><span data-stu-id="380f4-112">Catalog version 2 is not supported on *Windows Server 2008 R2* and *Windows 7*.</span></span> <span data-ttu-id="380f4-113">プラットフォームとして *Windows 8*、*Windows Server 2012* 以降を使用する場合、カタログ バージョン 2 が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="380f4-113">It is recommended to use catalog version 2 if using platforms *Windows 8*, *Windows Server 2012* and above.</span></span>

<span data-ttu-id="380f4-114">既存のモジュールでこのコマンドを使用するには、モジュール マニフェストの場所と一致するように CatalogFilePath および Path 変数を指定します。</span><span class="sxs-lookup"><span data-stu-id="380f4-114">To use this command on an existing module, specify the CatalogFilePath and Path variables to match the location of the module manifest.</span></span> <span data-ttu-id="380f4-115">下の例では、モジュール マニフェストは、C:\Program Files\Windows PowerShell\Modules\Pester にあります。</span><span class="sxs-lookup"><span data-stu-id="380f4-115">In the example below, the module manifest is in C:\Program Files\Windows PowerShell\Modules\Pester.</span></span>

![](../images/NewFileCatalog.jpg)

<span data-ttu-id="380f4-116">これはカタログ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="380f4-116">This creates the catalog file.</span></span>

![](../images/CatalogFile1.jpg)

![](../images/CatalogFile2.jpg)

<span data-ttu-id="380f4-117">カタログ ファイルの整合性を検証するために (上記の例では Pester.cat)、[Set-AuthenticodeSignature](https://technet.microsoft.com/library/hh849819.aspx) コマンドレットで署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="380f4-117">To verify the integrity of a catalog file (Pester.cat in above exmaple) it should be signed using the [Set-AuthenticodeSignature](https://technet.microsoft.com/library/hh849819.aspx) cmdlet.</span></span>


## <a name="test-filecatalog"></a><span data-ttu-id="380f4-118">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="380f4-118">Test-FileCatalog</span></span>
--------------------------------

<span data-ttu-id="380f4-119">`Test-FileCatalog` は、一連のフォルダーを表すカタログを検証します。</span><span class="sxs-lookup"><span data-stu-id="380f4-119">`Test-FileCatalog` validates the catalog representing a set of folders.</span></span>

```powershell
Test-FileCatalog [-CatalogFilePath] <string> [[-Path] <string[]>] [-Detailed] [-FilesToSkip <string[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

![](../images/TestFileCatalog.jpg)

<span data-ttu-id="380f4-120">このコマンドレットは、カタログ ファイル内で見つかったすべてのファイルとその相対パスのハッシュを、ディスクに保存されているものと比較します。</span><span class="sxs-lookup"><span data-stu-id="380f4-120">This cmdlet compares the hashes of all files and their relative paths found in the catalog file with ones saved to disk.</span></span> <span data-ttu-id="380f4-121">ファイル ハッシュとパスの間に不一致が検出された場合、`ValidationFailed` というステータスを返します。</span><span class="sxs-lookup"><span data-stu-id="380f4-121">If it detects any mismatch between file hashes and paths it returns a status of `ValidationFailed`.</span></span>
<span data-ttu-id="380f4-122">`Detailed` スイッチを利用し、この情報をすべて取得できます。</span><span class="sxs-lookup"><span data-stu-id="380f4-122">Users can retrieve all this information using the `Detailed` switch.</span></span> <span data-ttu-id="380f4-123">カタログの署名ステータスは、`Signature` フィールドとして表示されます。これは、カタログ ファイルで [Get-AuthenticodeSignature](https://technet.microsoft.com/en-us/library/hh849805.aspx) コマンドレットを呼び出すことと同じです。</span><span class="sxs-lookup"><span data-stu-id="380f4-123">The signing status of the catalog is displayed as the `Signature` field, which is same as calling the [Get-AuthenticodeSignature](https://technet.microsoft.com/en-us/library/hh849805.aspx) cmdlet on the catalog file.</span></span>
<span data-ttu-id="380f4-124">`FilesToSkip` パラメーターを利用し、検証中にファイルをスキップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="380f4-124">Users can also skip any file during validation by using the `FilesToSkip` parameter.</span></span>
