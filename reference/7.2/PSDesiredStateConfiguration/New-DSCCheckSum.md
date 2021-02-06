---
external help file: PSDesiredStateConfiguration-help.xml
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/new-dscchecksum?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-DscChecksum
ms.openlocfilehash: 8b8d0c545cdb36b6184a0670a52a5a30aa33a465
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600097"
---
# <span data-ttu-id="e4db1-102">New-DscChecksum</span><span class="sxs-lookup"><span data-stu-id="e4db1-102">New-DscChecksum</span></span>

## <span data-ttu-id="e4db1-103">概要</span><span class="sxs-lookup"><span data-stu-id="e4db1-103">SYNOPSIS</span></span>
<span data-ttu-id="e4db1-104">DSC ドキュメントと DSC リソースのチェックサムファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4db1-104">Creates checksum files for DSC documents and DSC resources.</span></span>

## <span data-ttu-id="e4db1-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e4db1-105">SYNTAX</span></span>

```
New-DscChecksum [-Path] <String[]> [[-OutPath] <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e4db1-106">Description</span><span class="sxs-lookup"><span data-stu-id="e4db1-106">DESCRIPTION</span></span>

<span data-ttu-id="e4db1-107">**新しい-dscchecksum** コマンドレットは、PowerShell Desired State CONFIGURATION (DSC) ドキュメントと圧縮された dsc リソースのチェックサムファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="e4db1-107">The **New-DSCCheckSum** cmdlet generates checksum files for PowerShell Desired State Configuration (DSC) documents and compressed DSC resources.</span></span>
<span data-ttu-id="e4db1-108">このコマンドレットは、プルモードで使用される構成およびリソースごとにチェックサムファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="e4db1-108">This cmdlet generates a checksum file for each configuration and resource to be used in pull mode.</span></span>
<span data-ttu-id="e4db1-109">DSC サービスでは、チェックサムを使用して、ターゲットノードに正しい構成とリソースが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="e4db1-109">The DSC service uses the checksums to make sure that the correct configuration and resources exist on the target node.</span></span>
<span data-ttu-id="e4db1-110">チェックサムを、関連付けられている DSC ドキュメントと、DSC サービスストアの圧縮された DSC リソースと一緒に配置します。</span><span class="sxs-lookup"><span data-stu-id="e4db1-110">Place the checksums together with the associated DSC documents and compressed DSC resources in the DSC service store.</span></span>

## <span data-ttu-id="e4db1-111">例</span><span class="sxs-lookup"><span data-stu-id="e4db1-111">EXAMPLES</span></span>

### <span data-ttu-id="e4db1-112">例 1: 特定のパスにあるすべての構成のチェックサムファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="e4db1-112">Example 1: Create checksum files for all configurations in a specific path</span></span>

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="e4db1-113">以下のコマンドは、パス C:\DSC\Configurations にあるすべての構成のチェックサム ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4db1-113">This command creates checksum files for all configurations in the path C:\DSC\Configurations.</span></span>
<span data-ttu-id="e4db1-114">既に存在するチェックサムファイルはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="e4db1-114">Any checksum files that already exist are skipped.</span></span>

### <span data-ttu-id="e4db1-115">例 2: 特定のパスのすべての構成のチェックサムファイルを作成し、既存のチェックサムファイルを上書きする</span><span class="sxs-lookup"><span data-stu-id="e4db1-115">Example 2: Create checksum files for all configurations in a specific path and overwrite the existing checksum files</span></span>

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\" -Force
```

<span data-ttu-id="e4db1-116">以下のコマンドは、パス C:\DSC\Configurations にあるすべての構成の新しいチェックサム ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4db1-116">This command creates new checksum files for all configurations in the path C:\DSC\Configurations.</span></span>
<span data-ttu-id="e4db1-117">*Force* パラメーターを指定すると、既に存在するチェックサムファイルが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="e4db1-117">Specifying the *Force* parameter causes the command to overwrite any checksum files that already exist.</span></span>

## <span data-ttu-id="e4db1-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e4db1-118">PARAMETERS</span></span>

### <span data-ttu-id="e4db1-119">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e4db1-119">-Confirm</span></span>

<span data-ttu-id="e4db1-120">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4db1-120">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="e4db1-121">-Force</span><span class="sxs-lookup"><span data-stu-id="e4db1-121">-Force</span></span>

<span data-ttu-id="e4db1-122">指定した出力ファイルが既に存在する場合はコマンドレットによってそのファイルが上書きされることを示します。</span><span class="sxs-lookup"><span data-stu-id="e4db1-122">Indicates that the cmdlet overwrites the specified output file if it already exists.</span></span>

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

### <span data-ttu-id="e4db1-123">-OutPath</span><span class="sxs-lookup"><span data-stu-id="e4db1-123">-OutPath</span></span>

<span data-ttu-id="e4db1-124">出力チェックサム ファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4db1-124">Specifies the path and file name of the output checksum file.</span></span>

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

### <span data-ttu-id="e4db1-125">-Path</span><span class="sxs-lookup"><span data-stu-id="e4db1-125">-Path</span></span>

<span data-ttu-id="e4db1-126">入力ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e4db1-126">Specifies the path of the input file.</span></span>

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

### <span data-ttu-id="e4db1-127">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e4db1-127">-WhatIf</span></span>

<span data-ttu-id="e4db1-128">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="e4db1-128">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="e4db1-129">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e4db1-129">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="e4db1-130">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e4db1-130">CommonParameters</span></span>

<span data-ttu-id="e4db1-131">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e4db1-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e4db1-132">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4db1-132">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e4db1-133">入力</span><span class="sxs-lookup"><span data-stu-id="e4db1-133">INPUTS</span></span>

### <span data-ttu-id="e4db1-134">なし</span><span class="sxs-lookup"><span data-stu-id="e4db1-134">None</span></span>

## <span data-ttu-id="e4db1-135">出力</span><span class="sxs-lookup"><span data-stu-id="e4db1-135">OUTPUTS</span></span>

### <span data-ttu-id="e4db1-136">System.Object</span><span class="sxs-lookup"><span data-stu-id="e4db1-136">System.Object</span></span>

## <span data-ttu-id="e4db1-137">注</span><span class="sxs-lookup"><span data-stu-id="e4db1-137">NOTES</span></span>

## <span data-ttu-id="e4db1-138">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e4db1-138">RELATED LINKS</span></span>

[<span data-ttu-id="e4db1-139">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="e4db1-139">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

