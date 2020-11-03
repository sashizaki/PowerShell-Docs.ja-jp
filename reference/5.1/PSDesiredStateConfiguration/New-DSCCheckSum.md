---
external help file: PSDesiredStateConfiguration-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/new-dscchecksum?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-DscChecksum
ms.openlocfilehash: cd784c5adac3aeeabc8e4cf9f5f4b0b67e9a000c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215307"
---
# <span data-ttu-id="fba31-103">New-DscChecksum</span><span class="sxs-lookup"><span data-stu-id="fba31-103">New-DscChecksum</span></span>

## <span data-ttu-id="fba31-104">概要</span><span class="sxs-lookup"><span data-stu-id="fba31-104">SYNOPSIS</span></span>
<span data-ttu-id="fba31-105">DSC ドキュメントと DSC リソースのチェックサムファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fba31-105">Creates checksum files for DSC documents and DSC resources.</span></span>

## <span data-ttu-id="fba31-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fba31-106">SYNTAX</span></span>

```
New-DscChecksum [-Path] <String[]> [[-OutPath] <String>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="fba31-107">Description</span><span class="sxs-lookup"><span data-stu-id="fba31-107">DESCRIPTION</span></span>
<span data-ttu-id="fba31-108">**新しい-dscchecksum** コマンドレットは、Windows PowerShell Desired State CONFIGURATION (DSC) ドキュメントと圧縮された dsc リソースのチェックサムファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="fba31-108">The **New-DSCCheckSum** cmdlet generates checksum files for Windows PowerShell Desired State Configuration (DSC) documents and compressed DSC resources.</span></span>
<span data-ttu-id="fba31-109">このコマンドレットは、プルモードで使用される構成およびリソースごとにチェックサムファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="fba31-109">This cmdlet generates a checksum file for each configuration and resource to be used in pull mode.</span></span>
<span data-ttu-id="fba31-110">DSC サービスでは、チェックサムを使用して、ターゲットノードに正しい構成とリソースが存在することを確認します。</span><span class="sxs-lookup"><span data-stu-id="fba31-110">The DSC service uses the checksums to make sure that the correct configuration and resources exist on the target node.</span></span>
<span data-ttu-id="fba31-111">チェックサムを、関連付けられている DSC ドキュメントと、DSC サービスストアの圧縮された DSC リソースと一緒に配置します。</span><span class="sxs-lookup"><span data-stu-id="fba31-111">Place the checksums together with the associated DSC documents and compressed DSC resources in the DSC service store.</span></span>

## <span data-ttu-id="fba31-112">例</span><span class="sxs-lookup"><span data-stu-id="fba31-112">EXAMPLES</span></span>

### <span data-ttu-id="fba31-113">例 1: 特定のパスにあるすべての構成のチェックサムファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="fba31-113">Example 1: Create checksum files for all configurations in a specific path</span></span>

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="fba31-114">以下のコマンドは、パス C:\DSC\Configurations にあるすべての構成のチェックサム ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fba31-114">This command creates checksum files for all configurations in the path C:\DSC\Configurations.</span></span>
<span data-ttu-id="fba31-115">既に存在するチェックサムファイルはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="fba31-115">Any checksum files that already exist are skipped.</span></span>

### <span data-ttu-id="fba31-116">例 2: 特定のパスのすべての構成のチェックサムファイルを作成し、既存のチェックサムファイルを上書きする</span><span class="sxs-lookup"><span data-stu-id="fba31-116">Example 2: Create checksum files for all configurations in a specific path and overwrite the existing checksum files</span></span>

```
PS C:\> New-DscCheckSum -Path "C:\DSC\Configurations\" -Force
```

<span data-ttu-id="fba31-117">以下のコマンドは、パス C:\DSC\Configurations にあるすべての構成の新しいチェックサム ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fba31-117">This command creates new checksum files for all configurations in the path C:\DSC\Configurations.</span></span>
<span data-ttu-id="fba31-118">*Force* パラメーターを指定すると、既に存在するチェックサムファイルが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="fba31-118">Specifying the *Force* parameter causes the command to overwrite any checksum files that already exist.</span></span>

## <span data-ttu-id="fba31-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fba31-119">PARAMETERS</span></span>

### <span data-ttu-id="fba31-120">-Force</span><span class="sxs-lookup"><span data-stu-id="fba31-120">-Force</span></span>
<span data-ttu-id="fba31-121">指定した出力ファイルが既に存在する場合はコマンドレットによってそのファイルが上書きされることを示します。</span><span class="sxs-lookup"><span data-stu-id="fba31-121">Indicates that the cmdlet overwrites the specified output file if it already exists.</span></span>

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

### <span data-ttu-id="fba31-122">-OutPath</span><span class="sxs-lookup"><span data-stu-id="fba31-122">-OutPath</span></span>
<span data-ttu-id="fba31-123">出力チェックサム ファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="fba31-123">Specifies the path and file name of the output checksum file.</span></span>

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

### <span data-ttu-id="fba31-124">-Path</span><span class="sxs-lookup"><span data-stu-id="fba31-124">-Path</span></span>
<span data-ttu-id="fba31-125">入力ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="fba31-125">Specifies the path of the input file.</span></span>

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

### <span data-ttu-id="fba31-126">-Confirm</span><span class="sxs-lookup"><span data-stu-id="fba31-126">-Confirm</span></span>
<span data-ttu-id="fba31-127">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fba31-127">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="fba31-128">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="fba31-128">-WhatIf</span></span>
<span data-ttu-id="fba31-129">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="fba31-129">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="fba31-130">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="fba31-130">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="fba31-131">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fba31-131">CommonParameters</span></span>
<span data-ttu-id="fba31-132">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="fba31-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fba31-133">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fba31-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fba31-134">入力</span><span class="sxs-lookup"><span data-stu-id="fba31-134">INPUTS</span></span>

## <span data-ttu-id="fba31-135">出力</span><span class="sxs-lookup"><span data-stu-id="fba31-135">OUTPUTS</span></span>

## <span data-ttu-id="fba31-136">注</span><span class="sxs-lookup"><span data-stu-id="fba31-136">NOTES</span></span>

## <span data-ttu-id="fba31-137">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fba31-137">RELATED LINKS</span></span>

[<span data-ttu-id="fba31-138">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="fba31-138">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)
