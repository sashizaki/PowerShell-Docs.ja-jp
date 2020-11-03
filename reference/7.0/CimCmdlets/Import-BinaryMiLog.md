---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/import-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-BinaryMiLog
ms.openlocfilehash: ce5dd31170bc47edaa04ca3c31deab62dc4ec354
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224995"
---
# <span data-ttu-id="798fa-103">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="798fa-103">Import-BinaryMiLog</span></span>

## <span data-ttu-id="798fa-104">概要</span><span class="sxs-lookup"><span data-stu-id="798fa-104">SYNOPSIS</span></span>
<span data-ttu-id="798fa-105">エクスポートファイルの内容に基づいて、保存されたオブジェクトを再作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="798fa-105">Used to re-create the saved objects based on the contents of an export file.</span></span>

## <span data-ttu-id="798fa-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="798fa-106">SYNTAX</span></span>

```
Import-BinaryMiLog [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="798fa-107">Description</span><span class="sxs-lookup"><span data-stu-id="798fa-107">DESCRIPTION</span></span>

<span data-ttu-id="798fa-108">このコマンドレットを使用して、によって作成されたエクスポートファイルの内容に基づいて、保存されたオブジェクトを再作成し `Export-BinaryMILog` ます。</span><span class="sxs-lookup"><span data-stu-id="798fa-108">Use this cmdlet to re-create saved objects based on the contents of an export file created by `Export-BinaryMILog`.</span></span> <span data-ttu-id="798fa-109">このコマンドレットはに似ていますが、では `Import-Clixml` 、結果と `Export-BinaryMILog` して得られるオブジェクトがバイナリエンコードファイルに格納される点が異なります。</span><span class="sxs-lookup"><span data-stu-id="798fa-109">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="798fa-110">例</span><span class="sxs-lookup"><span data-stu-id="798fa-110">EXAMPLES</span></span>

### <span data-ttu-id="798fa-111">例 1-ファイルにエクスポートされたオブジェクトを復元する</span><span class="sxs-lookup"><span data-stu-id="798fa-111">Example 1 - Restore objects exported to a file</span></span>

```powershell
Import-BinaryMiLog -Path "Processes.bmil"
```

## <span data-ttu-id="798fa-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="798fa-112">PARAMETERS</span></span>

### <span data-ttu-id="798fa-113">-Path</span><span class="sxs-lookup"><span data-stu-id="798fa-113">-Path</span></span>

<span data-ttu-id="798fa-114">オブジェクトのバイナリ表現を格納するファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="798fa-114">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="798fa-115">**Path** パラメーターは、ワイルドカードと相対パスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="798fa-115">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="798fa-116">このコマンドレットは、パスが複数のファイルに解決された場合にエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="798fa-116">This cmdlet generates an error if the path resolves to more than one file.</span></span>

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

### <span data-ttu-id="798fa-117">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="798fa-117">CommonParameters</span></span>
<span data-ttu-id="798fa-118">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="798fa-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="798fa-119">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="798fa-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="798fa-120">入力</span><span class="sxs-lookup"><span data-stu-id="798fa-120">INPUTS</span></span>

### <span data-ttu-id="798fa-121">なし</span><span class="sxs-lookup"><span data-stu-id="798fa-121">None</span></span>

## <span data-ttu-id="798fa-122">出力</span><span class="sxs-lookup"><span data-stu-id="798fa-122">OUTPUTS</span></span>

### <span data-ttu-id="798fa-123">System.Object</span><span class="sxs-lookup"><span data-stu-id="798fa-123">System.Object</span></span>

## <span data-ttu-id="798fa-124">注</span><span class="sxs-lookup"><span data-stu-id="798fa-124">NOTES</span></span>

## <span data-ttu-id="798fa-125">関連リンク</span><span class="sxs-lookup"><span data-stu-id="798fa-125">RELATED LINKS</span></span>
