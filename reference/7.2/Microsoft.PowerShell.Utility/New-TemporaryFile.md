---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-temporaryfile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TemporaryFile
ms.openlocfilehash: 1c66cd3b1cc2fccc58cd75c367b41c445deb1e72
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599300"
---
# <span data-ttu-id="cb44e-102">New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="cb44e-102">New-TemporaryFile</span></span>

## <span data-ttu-id="cb44e-103">概要</span><span class="sxs-lookup"><span data-stu-id="cb44e-103">SYNOPSIS</span></span>
<span data-ttu-id="cb44e-104">一時ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb44e-104">Creates a temporary file.</span></span>

## <span data-ttu-id="cb44e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cb44e-105">SYNTAX</span></span>

```
New-TemporaryFile [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cb44e-106">Description</span><span class="sxs-lookup"><span data-stu-id="cb44e-106">DESCRIPTION</span></span>

<span data-ttu-id="cb44e-107">このコマンドレットは、スクリプトで使用できる一時ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb44e-107">This cmdlet creates temporary files that you can use in scripts.</span></span>

<span data-ttu-id="cb44e-108">コマンドレットでは、 `New-TemporaryFile` ファイル名拡張子を持つ空のファイルを作成し `.tmp` ます。</span><span class="sxs-lookup"><span data-stu-id="cb44e-108">The `New-TemporaryFile` cmdlet creates an empty file that has the `.tmp` file name extension.</span></span>
<span data-ttu-id="cb44e-109">このコマンドレットは、ファイルに名前 `tmp<NNNN>.tmp` を `<NNNN>` 指定します。は、ランダムな16進数です。</span><span class="sxs-lookup"><span data-stu-id="cb44e-109">This cmdlet names the file `tmp<NNNN>.tmp`, where `<NNNN>` is a random hexadecimal number.</span></span>
<span data-ttu-id="cb44e-110">コマンドレットにより、 **一時** フォルダーにファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cb44e-110">The cmdlet creates the file in your **TEMP** folder.</span></span>

<span data-ttu-id="cb44e-111">このコマンドレットは、 [GetTempPath ()](/dotnet/api/system.io.path.gettemppath) メソッドを使用して、 **一時** フォルダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="cb44e-111">This cmdlet uses the [Path.GetTempPath()](/dotnet/api/system.io.path.gettemppath) method to find your **TEMP** folder.</span></span> <span data-ttu-id="cb44e-112">このメソッドは、次の順序で環境変数の存在を確認し、見つかった最初のパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb44e-112">This method checks for the existence of environment variables in the following order and uses the first path found:</span></span>

- <span data-ttu-id="cb44e-113">Windows プラットフォームの場合:</span><span class="sxs-lookup"><span data-stu-id="cb44e-113">On Windows platforms:</span></span>

  1. <span data-ttu-id="cb44e-114">TMP 環境変数によって指定されたパス。</span><span class="sxs-lookup"><span data-stu-id="cb44e-114">The path specified by the TMP environment variable.</span></span>
  1. <span data-ttu-id="cb44e-115">TEMP 環境変数によって指定されたパス。</span><span class="sxs-lookup"><span data-stu-id="cb44e-115">The path specified by the TEMP environment variable.</span></span>
  1. <span data-ttu-id="cb44e-116">USERPROFILE 環境変数によって指定されたパス。</span><span class="sxs-lookup"><span data-stu-id="cb44e-116">The path specified by the USERPROFILE environment variable.</span></span>
  1. <span data-ttu-id="cb44e-117">Windows ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="cb44e-117">The Windows directory.</span></span>

- <span data-ttu-id="cb44e-118">Windows 以外のプラットフォームの場合: は、TMPDIR 環境変数で指定されたパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="cb44e-118">On non-Windows platforms: Uses the path specified by the TMPDIR environment variable.</span></span>

## <span data-ttu-id="cb44e-119">例</span><span class="sxs-lookup"><span data-stu-id="cb44e-119">EXAMPLES</span></span>

### <span data-ttu-id="cb44e-120">例 1: 一時ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="cb44e-120">Example 1: Create a temporary file</span></span>

```powershell
$TempFile = New-TemporaryFile
```

<span data-ttu-id="cb44e-121">このコマンドは、 `.tmp` 一時フォルダーにファイルを生成し、そのファイルへの参照を変数に格納し `$TempFile` ます。</span><span class="sxs-lookup"><span data-stu-id="cb44e-121">This command generates a `.tmp` file in your temporary folder, and then stores a reference to the file in the `$TempFile` variable.</span></span> <span data-ttu-id="cb44e-122">このファイルは、後でスクリプト内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="cb44e-122">You can use this file later in your script.</span></span>

## <span data-ttu-id="cb44e-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cb44e-123">PARAMETERS</span></span>

### <span data-ttu-id="cb44e-124">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cb44e-124">-Confirm</span></span>

<span data-ttu-id="cb44e-125">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb44e-125">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="cb44e-126">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cb44e-126">-WhatIf</span></span>

<span data-ttu-id="cb44e-127">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="cb44e-127">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="cb44e-128">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="cb44e-128">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="cb44e-129">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="cb44e-129">CommonParameters</span></span>

<span data-ttu-id="cb44e-130">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="cb44e-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cb44e-131">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cb44e-131">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="cb44e-132">入力</span><span class="sxs-lookup"><span data-stu-id="cb44e-132">INPUTS</span></span>

## <span data-ttu-id="cb44e-133">出力</span><span class="sxs-lookup"><span data-stu-id="cb44e-133">OUTPUTS</span></span>

### <span data-ttu-id="cb44e-134">システム. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="cb44e-134">System.IO.FileInfo</span></span>

<span data-ttu-id="cb44e-135">このコマンドレットは、一時ファイルを表す **FileInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="cb44e-135">This cmdlet returns a **FileInfo** object that represents the temporary file.</span></span>

## <span data-ttu-id="cb44e-136">注</span><span class="sxs-lookup"><span data-stu-id="cb44e-136">NOTES</span></span>

## <span data-ttu-id="cb44e-137">関連リンク</span><span class="sxs-lookup"><span data-stu-id="cb44e-137">RELATED LINKS</span></span>

