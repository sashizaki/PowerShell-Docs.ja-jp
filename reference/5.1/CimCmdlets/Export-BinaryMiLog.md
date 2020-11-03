---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/export-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-BinaryMiLog
ms.openlocfilehash: cf03ad884121c6cf8cf65cdb791cbdc4e587c3b9
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212456"
---
# <span data-ttu-id="4cd4a-103">Export-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="4cd4a-103">Export-BinaryMiLog</span></span>

## <span data-ttu-id="4cd4a-104">概要</span><span class="sxs-lookup"><span data-stu-id="4cd4a-104">SYNOPSIS</span></span>
<span data-ttu-id="4cd4a-105">オブジェクトのバイナリエンコードされた表現を作成し、ファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="4cd4a-105">Creates a binary encoded representation of an object or objects and stores it in a file.</span></span>

## <span data-ttu-id="4cd4a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4cd4a-106">SYNTAX</span></span>

```
Export-BinaryMiLog [-InputObject <CimInstance>] [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="4cd4a-107">Description</span><span class="sxs-lookup"><span data-stu-id="4cd4a-107">DESCRIPTION</span></span>

<span data-ttu-id="4cd4a-108">`Export-BinaryMILog`コマンドレットでは、オブジェクトまたはオブジェクトのバイナリベースの表現を作成し、ファイルに格納します。</span><span class="sxs-lookup"><span data-stu-id="4cd4a-108">The `Export-BinaryMILog` cmdlet creates a binary-based representation of an object or objects and stores it in a file.</span></span> <span data-ttu-id="4cd4a-109">その後、コマンドレットを使用して、 `Import-BinaryMiLog` そのファイルの内容に基づいて保存されたオブジェクトを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="4cd4a-109">You can then use the `Import-BinaryMiLog` cmdlet to re-create the saved object based on the contents of that file.</span></span>

<span data-ttu-id="4cd4a-110">このコマンドレットはに似ていますが、では `Import-Clixml` 、結果と `Export-BinaryMILog` して得られるオブジェクトがバイナリエンコードファイルに格納される点が異なります。</span><span class="sxs-lookup"><span data-stu-id="4cd4a-110">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="4cd4a-111">例</span><span class="sxs-lookup"><span data-stu-id="4cd4a-111">EXAMPLES</span></span>

### <span data-ttu-id="4cd4a-112">例 1-CimInstances のバイナリ表現を作成する</span><span class="sxs-lookup"><span data-stu-id="4cd4a-112">Example 1 - Create a binary representation of CimInstances</span></span>

```powershell
Get-CimInstance Win32_Process | Export-BinaryMiLog -Path "Processes.bmil"
```

<span data-ttu-id="4cd4a-113">このコマンドは、Path パラメーターで指定されたバイナリ MI ログファイルに **CimInstances** をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="4cd4a-113">This command exports **CimInstances** to a binary MI log file specified by the Path parameter.</span></span> <span data-ttu-id="4cd4a-114">このファイルをインポートして **CimInstances** を再作成する方法については、Import-BinaryMiLog の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cd4a-114">See the example for Import-BinaryMiLog to see how to recreate the **CimInstances** by importing this file.</span></span>

## <span data-ttu-id="4cd4a-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4cd4a-115">PARAMETERS</span></span>

### <span data-ttu-id="4cd4a-116">-InputObject</span><span class="sxs-lookup"><span data-stu-id="4cd4a-116">-InputObject</span></span>

<span data-ttu-id="4cd4a-117">このコマンドレットへの入力を指定します。</span><span class="sxs-lookup"><span data-stu-id="4cd4a-117">Specifies the input to this cmdlet.</span></span> <span data-ttu-id="4cd4a-118">このパラメーターを使用するか、またはこのコマンドレットへの入力をパイプで渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="4cd4a-118">You can use this parameter, or you can pipe the input to this cmdlet.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4cd4a-119">-Path</span><span class="sxs-lookup"><span data-stu-id="4cd4a-119">-Path</span></span>

<span data-ttu-id="4cd4a-120">オブジェクトのバイナリ表現を格納するファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="4cd4a-120">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="4cd4a-121">**Path** パラメーターは、ワイルドカードと相対パスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4cd4a-121">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="4cd4a-122">このコマンドレットは、パスが複数のファイルに解決された場合にエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="4cd4a-122">This cmdlet generates an error if the path resolves to more than one file.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="4cd4a-123">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4cd4a-123">CommonParameters</span></span>

<span data-ttu-id="4cd4a-124">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4cd4a-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4cd4a-125">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4cd4a-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4cd4a-126">入力</span><span class="sxs-lookup"><span data-stu-id="4cd4a-126">INPUTS</span></span>

### <span data-ttu-id="4cd4a-127">Microsoft.Management.Infrastructure.CimInstance</span><span class="sxs-lookup"><span data-stu-id="4cd4a-127">Microsoft.Management.Infrastructure.CimInstance</span></span>

## <span data-ttu-id="4cd4a-128">出力</span><span class="sxs-lookup"><span data-stu-id="4cd4a-128">OUTPUTS</span></span>

### <span data-ttu-id="4cd4a-129">System.Object</span><span class="sxs-lookup"><span data-stu-id="4cd4a-129">System.Object</span></span>

## <span data-ttu-id="4cd4a-130">注</span><span class="sxs-lookup"><span data-stu-id="4cd4a-130">NOTES</span></span>

## <span data-ttu-id="4cd4a-131">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4cd4a-131">RELATED LINKS</span></span>

[<span data-ttu-id="4cd4a-132">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="4cd4a-132">Get-CimInstance</span></span>](get-ciminstance.md)

[<span data-ttu-id="4cd4a-133">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="4cd4a-133">Import-BinaryMiLog</span></span>](import-binarymilog.md)

[<span data-ttu-id="4cd4a-134">Import-Clixml</span><span class="sxs-lookup"><span data-stu-id="4cd4a-134">Import-Clixml</span></span>](../microsoft.powershell.utility/import-clixml.md)
