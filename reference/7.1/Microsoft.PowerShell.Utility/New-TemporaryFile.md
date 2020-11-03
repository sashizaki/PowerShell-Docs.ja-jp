---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/16/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-temporaryfile?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-TemporaryFile
ms.openlocfilehash: 406675d8bde1b6b9a28913c09d5374393705f93b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217384"
---
# <span data-ttu-id="1fd3d-103">New-TemporaryFile</span><span class="sxs-lookup"><span data-stu-id="1fd3d-103">New-TemporaryFile</span></span>

## <span data-ttu-id="1fd3d-104">概要</span><span class="sxs-lookup"><span data-stu-id="1fd3d-104">SYNOPSIS</span></span>
<span data-ttu-id="1fd3d-105">一時ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-105">Creates a temporary file.</span></span>

## <span data-ttu-id="1fd3d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1fd3d-106">SYNTAX</span></span>

```
New-TemporaryFile [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="1fd3d-107">Description</span><span class="sxs-lookup"><span data-stu-id="1fd3d-107">DESCRIPTION</span></span>

<span data-ttu-id="1fd3d-108">このコマンドレットは、スクリプトで使用できる一時ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-108">This cmdlet creates temporary files that you can use in scripts.</span></span>

<span data-ttu-id="1fd3d-109">コマンドレットでは、 `New-TemporaryFile` ファイル名拡張子を持つ空のファイルを作成し `.tmp` ます。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-109">The `New-TemporaryFile` cmdlet creates an empty file that has the `.tmp` file name extension.</span></span>
<span data-ttu-id="1fd3d-110">このコマンドレットは、ファイルに名前 `tmp<NNNN>.tmp` を `<NNNN>` 指定します。は、ランダムな16進数です。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-110">This cmdlet names the file `tmp<NNNN>.tmp`, where `<NNNN>` is a random hexadecimal number.</span></span>
<span data-ttu-id="1fd3d-111">コマンドレットにより、 **一時** フォルダーにファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-111">The cmdlet creates the file in your **TEMP** folder.</span></span>

<span data-ttu-id="1fd3d-112">このコマンドレットは、 [GetTempPath ()](/dotnet/api/system.io.path.gettemppath) メソッドを使用して、 **一時** フォルダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-112">This cmdlet uses the [Path.GetTempPath()](/dotnet/api/system.io.path.gettemppath) method to find your **TEMP** folder.</span></span> <span data-ttu-id="1fd3d-113">このメソッドは、次の順序で環境変数の存在を確認し、見つかった最初のパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-113">This method checks for the existence of environment variables in the following order and uses the first path found:</span></span>

- <span data-ttu-id="1fd3d-114">Windows プラットフォームの場合:</span><span class="sxs-lookup"><span data-stu-id="1fd3d-114">On Windows platforms:</span></span>

  1. <span data-ttu-id="1fd3d-115">TMP 環境変数によって指定されたパス。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-115">The path specified by the TMP environment variable.</span></span>
  1. <span data-ttu-id="1fd3d-116">TEMP 環境変数によって指定されたパス。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-116">The path specified by the TEMP environment variable.</span></span>
  1. <span data-ttu-id="1fd3d-117">USERPROFILE 環境変数によって指定されたパス。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-117">The path specified by the USERPROFILE environment variable.</span></span>
  1. <span data-ttu-id="1fd3d-118">Windows ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-118">The Windows directory.</span></span>

- <span data-ttu-id="1fd3d-119">Windows 以外のプラットフォームの場合: は、TMPDIR 環境変数で指定されたパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-119">On non-Windows platforms: Uses the path specified by the TMPDIR environment variable.</span></span>

## <span data-ttu-id="1fd3d-120">例</span><span class="sxs-lookup"><span data-stu-id="1fd3d-120">EXAMPLES</span></span>

### <span data-ttu-id="1fd3d-121">例 1: 一時ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="1fd3d-121">Example 1: Create a temporary file</span></span>

```powershell
$TempFile = New-TemporaryFile
```

<span data-ttu-id="1fd3d-122">このコマンドは、 `.tmp` 一時フォルダーにファイルを生成し、そのファイルへの参照を変数に格納し `$TempFile` ます。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-122">This command generates a `.tmp` file in your temporary folder, and then stores a reference to the file in the `$TempFile` variable.</span></span> <span data-ttu-id="1fd3d-123">このファイルは、後でスクリプト内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-123">You can use this file later in your script.</span></span>

## <span data-ttu-id="1fd3d-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1fd3d-124">PARAMETERS</span></span>

### <span data-ttu-id="1fd3d-125">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1fd3d-125">-Confirm</span></span>

<span data-ttu-id="1fd3d-126">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-126">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="1fd3d-127">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1fd3d-127">-WhatIf</span></span>

<span data-ttu-id="1fd3d-128">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-128">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="1fd3d-129">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-129">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="1fd3d-130">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1fd3d-130">CommonParameters</span></span>

<span data-ttu-id="1fd3d-131">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-131">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1fd3d-132">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-132">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="1fd3d-133">入力</span><span class="sxs-lookup"><span data-stu-id="1fd3d-133">INPUTS</span></span>

## <span data-ttu-id="1fd3d-134">出力</span><span class="sxs-lookup"><span data-stu-id="1fd3d-134">OUTPUTS</span></span>

### <span data-ttu-id="1fd3d-135">システム. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="1fd3d-135">System.IO.FileInfo</span></span>

<span data-ttu-id="1fd3d-136">このコマンドレットは、一時ファイルを表す **FileInfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="1fd3d-136">This cmdlet returns a **FileInfo** object that represents the temporary file.</span></span>

## <span data-ttu-id="1fd3d-137">注</span><span class="sxs-lookup"><span data-stu-id="1fd3d-137">NOTES</span></span>

## <span data-ttu-id="1fd3d-138">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1fd3d-138">RELATED LINKS</span></span>
