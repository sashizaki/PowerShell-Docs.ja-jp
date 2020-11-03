---
external help file: Microsoft.PowerShell.Security.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Security
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.security/test-filecatalog?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-FileCatalog
ms.openlocfilehash: 01b349ab76ee1d661edd0d30ac23202555575485
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93211211"
---
# <span data-ttu-id="2352a-103">Test-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="2352a-103">Test-FileCatalog</span></span>

## <span data-ttu-id="2352a-104">概要</span><span class="sxs-lookup"><span data-stu-id="2352a-104">SYNOPSIS</span></span>
<span data-ttu-id="2352a-105">`Test-FileCatalog` 信頼性を検証するために、カタログファイル (.cat) に含まれるハッシュが実際のファイルのハッシュと一致するかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="2352a-105">`Test-FileCatalog` validates whether the hashes contained in a catalog file (.cat) matches the hashes of the actual files in order to validate their authenticity.</span></span>

<span data-ttu-id="2352a-106">このコマンドレットは、Windows でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2352a-106">This cmdlet is only supported on Windows.</span></span>

## <span data-ttu-id="2352a-107">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2352a-107">SYNTAX</span></span>

```
Test-FileCatalog [-Detailed] [-FilesToSkip <String[]>] [-CatalogFilePath] <String> [[-Path] <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="2352a-108">Description</span><span class="sxs-lookup"><span data-stu-id="2352a-108">DESCRIPTION</span></span>

<span data-ttu-id="2352a-109">`Test-FileCatalog` カタログファイル (.cat) のファイルハッシュとディスク上の実際のファイルのハッシュを比較することによって、ファイルの信頼性を検証します。</span><span class="sxs-lookup"><span data-stu-id="2352a-109">`Test-FileCatalog` validates the authenticity of files by comparing the file hashes of a catalog file (.cat) with the hashes of actual files on disk.</span></span>
<span data-ttu-id="2352a-110">不一致が検出されると、ValidationFailed としてステータスが返されます。</span><span class="sxs-lookup"><span data-stu-id="2352a-110">If it detects any mismatches, it returns the status as ValidationFailed.</span></span> <span data-ttu-id="2352a-111">-Detailed パラメーターを利用し、この情報をすべて取得できます。</span><span class="sxs-lookup"><span data-stu-id="2352a-111">Users can retrieve all this information by using the -Detailed parameter.</span></span>
<span data-ttu-id="2352a-112">また、カタログファイルでコマンドレットを呼び出した場合と同じ、署名プロパティにカタログの署名の状態が表示され `Get-AuthenticodeSignature` ます。</span><span class="sxs-lookup"><span data-stu-id="2352a-112">It also displays signing status of catalog in Signature property which is equivalent to calling `Get-AuthenticodeSignature` cmdlet on the catalog file.</span></span>
<span data-ttu-id="2352a-113">-FilesToSkip パラメーターを利用し、検証中にファイルをスキップすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2352a-113">Users can also skip any file during validation by using the -FilesToSkip parameter.</span></span>

<span data-ttu-id="2352a-114">このコマンドレットは、Windows でのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2352a-114">This cmdlet is only supported on Windows.</span></span>

## <span data-ttu-id="2352a-115">例</span><span class="sxs-lookup"><span data-stu-id="2352a-115">EXAMPLES</span></span>

### <span data-ttu-id="2352a-116">例 1: ファイルカタログを作成および検証する</span><span class="sxs-lookup"><span data-stu-id="2352a-116">Example 1: Create and validate a file catalog</span></span>

```powershell
New-FileCatalog -Path $PSHOME\Modules\Microsoft.PowerShell.Utility -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -CatalogVersion 2.0

Test-FileCatalog -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -Path "$PSHome\Modules\Microsoft.PowerShell.Utility\"
```

```Output
Valid
```

### <span data-ttu-id="2352a-117">例 2: 詳細な出力を使用してファイルカタログを検証する</span><span class="sxs-lookup"><span data-stu-id="2352a-117">Example 2: Validate a file catalog with detailed output</span></span>

```powershell
Test-FileCatalog -CatalogFilePath \temp\Microsoft.PowerShell.Utility.cat -Path "$PSHome\Modules\Microsoft.PowerShell.Utility\"
```

```Output
Status        : Valid
HashAlgorithm : SHA256
CatalogItems  : {[Microsoft.PowerShell.Utility.psd1,
                A7028BD54018AE519381CDF5BF91F3B0417BD9345478086089ACBFAD05C899FC], [Microsoft.PowerShell.Utility.psm1,
                1127E8151FB86BCB683F932E8F6538552F7195816ED351A28AE07A753B8F20DE]}
PathItems     : {[Microsoft.PowerShell.Utility.psd1,
                A7028BD54018AE519381CDF5BF91F3B0417BD9345478086089ACBFAD05C899FC], [Microsoft.PowerShell.Utility.psm1,
                1127E8151FB86BCB683F932E8F6538552F7195816ED351A28AE07A753B8F20DE]}
Signature     : System.Management.Automation.Signature
```

## <span data-ttu-id="2352a-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2352a-118">PARAMETERS</span></span>

### <span data-ttu-id="2352a-119">-CatalogFilePath</span><span class="sxs-lookup"><span data-stu-id="2352a-119">-CatalogFilePath</span></span>

<span data-ttu-id="2352a-120">検証に使用するハッシュを含むカタログファイル (.cat) へのパスです。</span><span class="sxs-lookup"><span data-stu-id="2352a-120">A path to a catalog file (.cat) that contains the hashes to be used for validation.</span></span>

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

### <span data-ttu-id="2352a-121">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2352a-121">-Confirm</span></span>

<span data-ttu-id="2352a-122">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2352a-122">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="2352a-123">-Detailed</span><span class="sxs-lookup"><span data-stu-id="2352a-123">-Detailed</span></span>

<span data-ttu-id="2352a-124">詳細な情報を返し `CatalogInformation` ます。これは、テストされたファイルを含むより詳細なオブジェクト、予想される/実際のハッシュ、およびカタログファイルが署名されている場合の Authenticode 署名です。</span><span class="sxs-lookup"><span data-stu-id="2352a-124">Returns more information a more detailed `CatalogInformation` object that contains the files tested, their expected/actual hashes, and an Authenticode signature of the catalog file if it's signed.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2352a-125">-FilesToSkip</span><span class="sxs-lookup"><span data-stu-id="2352a-125">-FilesToSkip</span></span>

<span data-ttu-id="2352a-126">検証の一部としてテストすべきではないパスの配列。</span><span class="sxs-lookup"><span data-stu-id="2352a-126">An array of paths that should not be tested as part of the validation.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2352a-127">-Path</span><span class="sxs-lookup"><span data-stu-id="2352a-127">-Path</span></span>

<span data-ttu-id="2352a-128">カタログファイルに対して検証する必要のあるフォルダーまたはファイルの配列。</span><span class="sxs-lookup"><span data-stu-id="2352a-128">A folder or array of files that should be validated against the catalog file.</span></span>

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

### <span data-ttu-id="2352a-129">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2352a-129">-WhatIf</span></span>

<span data-ttu-id="2352a-130">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="2352a-130">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="2352a-131">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2352a-131">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="2352a-132">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2352a-132">CommonParameters</span></span>

<span data-ttu-id="2352a-133">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="2352a-133">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="2352a-134">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2352a-134">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="2352a-135">入力</span><span class="sxs-lookup"><span data-stu-id="2352a-135">INPUTS</span></span>

### <span data-ttu-id="2352a-136">DirectoryInfo []、System.string []。</span><span class="sxs-lookup"><span data-stu-id="2352a-136">System.IO.DirectoryInfo[], System.String[]</span></span>

<span data-ttu-id="2352a-137">パイプラインは、 `DirectoryInfo` 検証する必要があるファイルへのパスを表す文字列またはオブジェクトの配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="2352a-137">The pipeline accepts an array of strings or `DirectoryInfo` objects that represent paths to the files that need to be validated.</span></span>

## <span data-ttu-id="2352a-138">出力</span><span class="sxs-lookup"><span data-stu-id="2352a-138">OUTPUTS</span></span>

### <span data-ttu-id="2352a-139">CatalogValidationStatus (システム管理)</span><span class="sxs-lookup"><span data-stu-id="2352a-139">System.Management.Automation.CatalogValidationStatus</span></span>

<span data-ttu-id="2352a-140">またはのいずれかの値を格納している既定の戻り値の型 `Valid` `ValidationFailed` 。</span><span class="sxs-lookup"><span data-stu-id="2352a-140">The default return type containing a value of either `Valid` or `ValidationFailed`.</span></span>

### <span data-ttu-id="2352a-141">システム管理. CatalogInformation</span><span class="sxs-lookup"><span data-stu-id="2352a-141">System.Management.Automation.CatalogInformation</span></span>

<span data-ttu-id="2352a-142">を使用するときに返されるより詳細なオブジェクト。これを使用すると、 `-Detailed` 検証に合格した特定のファイル、予想されるハッシュ、検出されたハッシュ、およびカタログで使用されるアルゴリズムを分析できます。</span><span class="sxs-lookup"><span data-stu-id="2352a-142">A more detailed object returned when using `-Detailed` which can be used to analyze specific files that may or may not have passed validation, which hashes were expected vs. found, and the algorithm used in the catalog.</span></span>

## <span data-ttu-id="2352a-143">注</span><span class="sxs-lookup"><span data-stu-id="2352a-143">NOTES</span></span>

## <span data-ttu-id="2352a-144">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2352a-144">RELATED LINKS</span></span>

[<span data-ttu-id="2352a-145">New-FileCatalog</span><span class="sxs-lookup"><span data-stu-id="2352a-145">New-FileCatalog</span></span>](New-FileCatalog.md)

[<span data-ttu-id="2352a-146">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="2352a-146">PowerShellGet</span></span>](/powershell/module/PowerShellGet)