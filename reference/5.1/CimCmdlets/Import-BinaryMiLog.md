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
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212424"
---
# <span data-ttu-id="d016a-103">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="d016a-103">Import-BinaryMiLog</span></span>

## <span data-ttu-id="d016a-104">概要</span><span class="sxs-lookup"><span data-stu-id="d016a-104">SYNOPSIS</span></span>
<span data-ttu-id="d016a-105">エクスポートファイルの内容に基づいて、保存されたオブジェクトを再作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="d016a-105">Used to re-create the saved objects based on the contents of an export file.</span></span>

## <span data-ttu-id="d016a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d016a-106">SYNTAX</span></span>

```
Import-BinaryMiLog [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="d016a-107">Description</span><span class="sxs-lookup"><span data-stu-id="d016a-107">DESCRIPTION</span></span>

<span data-ttu-id="d016a-108">このコマンドレットを使用して、によって作成されたエクスポートファイルの内容に基づいて、保存されたオブジェクトを再作成し `Export-BinaryMILog` ます。</span><span class="sxs-lookup"><span data-stu-id="d016a-108">Use this cmdlet to re-create saved objects based on the contents of an export file created by `Export-BinaryMILog`.</span></span> <span data-ttu-id="d016a-109">このコマンドレットはに似ていますが、では `Import-Clixml` 、結果と `Export-BinaryMILog` して得られるオブジェクトがバイナリエンコードファイルに格納される点が異なります。</span><span class="sxs-lookup"><span data-stu-id="d016a-109">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="d016a-110">例</span><span class="sxs-lookup"><span data-stu-id="d016a-110">EXAMPLES</span></span>

### <span data-ttu-id="d016a-111">例 1-ファイルにエクスポートされたオブジェクトを復元する</span><span class="sxs-lookup"><span data-stu-id="d016a-111">Example 1 - Restore objects exported to a file</span></span>

```powershell
Import-BinaryMiLog -Path "Processes.bmil"
```

## <span data-ttu-id="d016a-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d016a-112">PARAMETERS</span></span>

### <span data-ttu-id="d016a-113">-Path</span><span class="sxs-lookup"><span data-stu-id="d016a-113">-Path</span></span>

<span data-ttu-id="d016a-114">オブジェクトのバイナリ表現を格納するファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d016a-114">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="d016a-115">**Path** パラメーターは、ワイルドカードと相対パスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d016a-115">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="d016a-116">このコマンドレットは、パスが複数のファイルに解決された場合にエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="d016a-116">This cmdlet generates an error if the path resolves to more than one file.</span></span>

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

### <span data-ttu-id="d016a-117">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d016a-117">CommonParameters</span></span>
<span data-ttu-id="d016a-118">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d016a-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d016a-119">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d016a-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d016a-120">入力</span><span class="sxs-lookup"><span data-stu-id="d016a-120">INPUTS</span></span>

### <span data-ttu-id="d016a-121">なし</span><span class="sxs-lookup"><span data-stu-id="d016a-121">None</span></span>

## <span data-ttu-id="d016a-122">出力</span><span class="sxs-lookup"><span data-stu-id="d016a-122">OUTPUTS</span></span>

### <span data-ttu-id="d016a-123">System.Object</span><span class="sxs-lookup"><span data-stu-id="d016a-123">System.Object</span></span>

## <span data-ttu-id="d016a-124">注</span><span class="sxs-lookup"><span data-stu-id="d016a-124">NOTES</span></span>

## <span data-ttu-id="d016a-125">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d016a-125">RELATED LINKS</span></span>