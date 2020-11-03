---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/new-dscchecksum?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-DscChecksum
ms.openlocfilehash: 2a66f906025f7a25609080e0b8da7f01755cd2fa
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210080"
---
# <span data-ttu-id="121f3-103">New-DscChecksum</span><span class="sxs-lookup"><span data-stu-id="121f3-103">New-DscChecksum</span></span>

## <span data-ttu-id="121f3-104">概要</span><span class="sxs-lookup"><span data-stu-id="121f3-104">SYNOPSIS</span></span>
<span data-ttu-id="121f3-105">DSC ドキュメントと DSC リソースのチェックサムファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="121f3-105">Creates checksum files for DSC documents and DSC resources.</span></span>

## <span data-ttu-id="121f3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="121f3-106">SYNTAX</span></span>

```
New-DscChecksum [-Path] <String[]> [[-OutPath] <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="121f3-107">Description</span><span class="sxs-lookup"><span data-stu-id="121f3-107">DESCRIPTION</span></span>

<span data-ttu-id="121f3-108">**新しい-dscchecksum** コマンドレットは、PowerShell Desired State CONFIGURATION (DSC) ドキュメントと圧縮された dsc リソースのチェックサムファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="121f3-108">The **New-DSCCheckSum** cmdlet generates checksum files for PowerShell Desired State Configuration (DSC) documents and compressed DSC resources.</span></span>
<span data-ttu-id="121f3-109">このコマンドレットは、プルモードで使用される構成およびリソースごとにチェックサムファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="121f3-109">This cmdlet generates a checksum file for each configuration and resource to be used in pull mode.</span></span>
<span data-ttu-id="121f3-110">DSC サービスでは、チェックサムを使用して、ターゲットノードに正しい構成とリソースが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="121f3-110">The DSC service uses the checksums to make sure that the correct configuration and resources exist on the target node.</span></span>
<span data-ttu-id="121f3-111">チェックサムを、関連付けられている DSC ドキュメントと、DSC サービスストアの圧縮された DSC リソースと一緒に配置します。</span><span class="sxs-lookup"><span data-stu-id="121f3-111">Place the checksums together with the associated DSC documents and compressed DSC resources in the DSC service store.</span></span>

## <span data-ttu-id="121f3-112">例</span><span class="sxs-lookup"><span data-stu-id="121f3-112">EXAMPLES</span></span>

### <span data-ttu-id="121f3-113">例 1: 特定のパスにあるすべての構成のチェックサムファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="121f3-113">Example 1: Create checksum files for all configurations in a specific path</span></span>

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="121f3-114">以下のコマンドは、パス C:\DSC\Configurations にあるすべての構成のチェックサム ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="121f3-114">This command creates checksum files for all configurations in the path C:\DSC\Configurations.</span></span>
<span data-ttu-id="121f3-115">既に存在するチェックサムファイルはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="121f3-115">Any checksum files that already exist are skipped.</span></span>

### <span data-ttu-id="121f3-116">例 2: 特定のパスのすべての構成のチェックサムファイルを作成し、既存のチェックサムファイルを上書きする</span><span class="sxs-lookup"><span data-stu-id="121f3-116">Example 2: Create checksum files for all configurations in a specific path and overwrite the existing checksum files</span></span>

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\" -Force
```

<span data-ttu-id="121f3-117">以下のコマンドは、パス C:\DSC\Configurations にあるすべての構成の新しいチェックサム ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="121f3-117">This command creates new checksum files for all configurations in the path C:\DSC\Configurations.</span></span>
<span data-ttu-id="121f3-118">*Force* パラメーターを指定すると、既に存在するチェックサムファイルが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="121f3-118">Specifying the *Force* parameter causes the command to overwrite any checksum files that already exist.</span></span>

## <span data-ttu-id="121f3-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="121f3-119">PARAMETERS</span></span>

### <span data-ttu-id="121f3-120">-Confirm</span><span class="sxs-lookup"><span data-stu-id="121f3-120">-Confirm</span></span>

<span data-ttu-id="121f3-121">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="121f3-121">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="121f3-122">-Force</span><span class="sxs-lookup"><span data-stu-id="121f3-122">-Force</span></span>

<span data-ttu-id="121f3-123">指定した出力ファイルが既に存在する場合はコマンドレットによってそのファイルが上書きされることを示します。</span><span class="sxs-lookup"><span data-stu-id="121f3-123">Indicates that the cmdlet overwrites the specified output file if it already exists.</span></span>

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

### <span data-ttu-id="121f3-124">-OutPath</span><span class="sxs-lookup"><span data-stu-id="121f3-124">-OutPath</span></span>

<span data-ttu-id="121f3-125">出力チェックサム ファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="121f3-125">Specifies the path and file name of the output checksum file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="121f3-126">-Path</span><span class="sxs-lookup"><span data-stu-id="121f3-126">-Path</span></span>

<span data-ttu-id="121f3-127">入力ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="121f3-127">Specifies the path of the input file.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: ConfigurationPath

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="121f3-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="121f3-128">-WhatIf</span></span>

<span data-ttu-id="121f3-129">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="121f3-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="121f3-130">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="121f3-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="121f3-131">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="121f3-131">CommonParameters</span></span>

<span data-ttu-id="121f3-132">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="121f3-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="121f3-133">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="121f3-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="121f3-134">入力</span><span class="sxs-lookup"><span data-stu-id="121f3-134">INPUTS</span></span>

### <span data-ttu-id="121f3-135">なし</span><span class="sxs-lookup"><span data-stu-id="121f3-135">None</span></span>

## <span data-ttu-id="121f3-136">出力</span><span class="sxs-lookup"><span data-stu-id="121f3-136">OUTPUTS</span></span>

### <span data-ttu-id="121f3-137">System.Object</span><span class="sxs-lookup"><span data-stu-id="121f3-137">System.Object</span></span>

## <span data-ttu-id="121f3-138">注</span><span class="sxs-lookup"><span data-stu-id="121f3-138">NOTES</span></span>

## <span data-ttu-id="121f3-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="121f3-139">RELATED LINKS</span></span>

[<span data-ttu-id="121f3-140">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="121f3-140">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)
