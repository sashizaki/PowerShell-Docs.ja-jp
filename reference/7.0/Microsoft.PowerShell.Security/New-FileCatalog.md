---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/new-filecatalog?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-FileCatalog
ms.openlocfilehash: aef0f6e63be07f0568927f8e65df675ff4f9eba7
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210179"
---
# <span data-ttu-id="53eff-103">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="53eff-103">New-FileCatalog</span></span>

## <span data-ttu-id="53eff-104">概要</span><span class="sxs-lookup"><span data-stu-id="53eff-104">SYNOPSIS</span></span>
<span data-ttu-id="53eff-105">`New-FileCatalog` ファイルの信頼性を検証するために使用できるファイルハッシュのカタログファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="53eff-105">`New-FileCatalog` creates a catalog file of file hashes that can be used to validate the authenticity of a file.</span></span>

## <span data-ttu-id="53eff-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="53eff-106">SYNTAX</span></span>

```
New-FileCatalog [-CatalogVersion <Int32>] [-CatalogFilePath] <String> [[-Path] <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="53eff-107">Description</span><span class="sxs-lookup"><span data-stu-id="53eff-107">DESCRIPTION</span></span>

<span data-ttu-id="53eff-108">`New-FileCatalog` 一連のフォルダーとファイルに対して [Windows カタログファイル](/windows-hardware/drivers/install/catalog-files) を作成します。</span><span class="sxs-lookup"><span data-stu-id="53eff-108">`New-FileCatalog` creates a [Windows catalog file](/windows-hardware/drivers/install/catalog-files) for a set of folders and files.</span></span>
<span data-ttu-id="53eff-109">このカタログファイルには、指定されたパス内のすべてのファイルのハッシュが含まれています。</span><span class="sxs-lookup"><span data-stu-id="53eff-109">This catalog file contains hashes for all files in the provided paths.</span></span>
<span data-ttu-id="53eff-110">その後、ユーザーは、カタログの作成時以降にフォルダーに変更が加えられたかどうかをユーザーが検証できるように、カタログをファイルと共に配布できます。</span><span class="sxs-lookup"><span data-stu-id="53eff-110">Users can then distribute the catalog with their files so that users can validate whether any changes have been made to the folders since catalog creation time.</span></span>

<span data-ttu-id="53eff-111">カタログ バージョン 1 と 2 がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="53eff-111">Catalog versions 1 and 2 are supported.</span></span> <span data-ttu-id="53eff-112">バージョン1は、(非推奨) SHA1 ハッシュアルゴリズムを使用してファイルハッシュを作成し、バージョン2は SHA256 を使用します。</span><span class="sxs-lookup"><span data-stu-id="53eff-112">Version 1 uses the (deprecated) SHA1 hashing algorithm to create file hashes, and version 2 uses SHA256.</span></span>
<span data-ttu-id="53eff-113">Windows Server 2008 R2 と Windows 7 はカタログ バージョン 2 に対応していません。</span><span class="sxs-lookup"><span data-stu-id="53eff-113">Catalog version 2 is not supported on Windows Server 2008 R2 or Windows 7.</span></span>
<span data-ttu-id="53eff-114">カタログ バージョン 2 は Windows 8、Windows Server 2012 以降のオペレーティング システムで利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53eff-114">You should use catalog version 2 on Windows 8, Windows Server 2012, and later operating systems.</span></span>

## <span data-ttu-id="53eff-115">例</span><span class="sxs-lookup"><span data-stu-id="53eff-115">EXAMPLES</span></span>

### <span data-ttu-id="53eff-116">例 1: のファイルカタログを作成する `Microsoft.PowerShell.Utility`</span><span class="sxs-lookup"><span data-stu-id="53eff-116">Example 1: Create a file catalog for `Microsoft.PowerShell.Utility`</span></span>

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0
```

```Output
Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----         11/2/2018 11:58 AM            950 Microsoft.PowerShell.Utility.cat
```

## <span data-ttu-id="53eff-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="53eff-117">PARAMETERS</span></span>

### <span data-ttu-id="53eff-118">-CatalogFilePath</span><span class="sxs-lookup"><span data-stu-id="53eff-118">-CatalogFilePath</span></span>

<span data-ttu-id="53eff-119">カタログファイル (.cat) を配置するファイルまたはフォルダーへのパス。</span><span class="sxs-lookup"><span data-stu-id="53eff-119">A path to a file or folder where the catalog file (.cat) should be placed.</span></span>
<span data-ttu-id="53eff-120">フォルダーパスを指定した場合は、既定のファイル名が `catalog.cat` 使用されます。</span><span class="sxs-lookup"><span data-stu-id="53eff-120">If a folder path is specified, the default filename `catalog.cat` will be used.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="53eff-121">-CatalogVersion</span><span class="sxs-lookup"><span data-stu-id="53eff-121">-CatalogVersion</span></span>

<span data-ttu-id="53eff-122">`1.0`は `2.0` 、カタログのバージョンを指定するために、またはを有効な値として受け入れます。</span><span class="sxs-lookup"><span data-stu-id="53eff-122">Accepts `1.0` or `2.0` as possible values for specifying the catalog version.</span></span>
<span data-ttu-id="53eff-123">`1.0` 可能な限り回避する必要があります。セキュリティで保護されていない SHA-1 ハッシュアルゴリズムが使用されるのに `2.0` 対し、は SECURE sha-256 アルゴリズムを使用し `1.0` ますが、は Windows 7 および Server 2008r2 で唯一サポートされているアルゴリズムです。</span><span class="sxs-lookup"><span data-stu-id="53eff-123">`1.0` should be used avoided whenever possible, as it uses the insecure SHA-1 hash algorithm, while `2.0` uses the secure SHA-256 algorithm However, `1.0` is the only supported algorithm on Windows 7 and Server 2008R2.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53eff-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="53eff-124">-Confirm</span></span>

<span data-ttu-id="53eff-125">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="53eff-125">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53eff-126">-Path</span><span class="sxs-lookup"><span data-stu-id="53eff-126">-Path</span></span>

<span data-ttu-id="53eff-127">カタログファイルに含める必要があるファイルまたはフォルダーへのパスまたはパスの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="53eff-127">Accepts a path or array of paths to files or folders that should be included in the catalog file.</span></span>
<span data-ttu-id="53eff-128">フォルダーが指定されている場合は、フォルダー内のすべてのファイルも含められます。</span><span class="sxs-lookup"><span data-stu-id="53eff-128">If a folder is specified, all the files in the folder will be included as well.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="53eff-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="53eff-129">-WhatIf</span></span>

<span data-ttu-id="53eff-130">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="53eff-130">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="53eff-131">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="53eff-131">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="53eff-132">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="53eff-132">CommonParameters</span></span>

<span data-ttu-id="53eff-133">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="53eff-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="53eff-134">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53eff-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="53eff-135">入力</span><span class="sxs-lookup"><span data-stu-id="53eff-135">INPUTS</span></span>

### <span data-ttu-id="53eff-136">System.String</span><span class="sxs-lookup"><span data-stu-id="53eff-136">System.String</span></span>

<span data-ttu-id="53eff-137">パイプラインは、カタログファイル名として使用される文字列を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="53eff-137">The pipeline takes a string that is used as the catalog filename.</span></span>

## <span data-ttu-id="53eff-138">出力</span><span class="sxs-lookup"><span data-stu-id="53eff-138">OUTPUTS</span></span>

### <span data-ttu-id="53eff-139">システム. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="53eff-139">System.IO.FileInfo</span></span>

## <span data-ttu-id="53eff-140">注</span><span class="sxs-lookup"><span data-stu-id="53eff-140">NOTES</span></span>

## <span data-ttu-id="53eff-141">関連リンク</span><span class="sxs-lookup"><span data-stu-id="53eff-141">RELATED LINKS</span></span>

[<span data-ttu-id="53eff-142">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="53eff-142">Test-FileCatalog</span></span>](Test-FileCatalog.md)

[<span data-ttu-id="53eff-143">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="53eff-143">PowerShellGet</span></span>](/powerShell/module/powershellget)