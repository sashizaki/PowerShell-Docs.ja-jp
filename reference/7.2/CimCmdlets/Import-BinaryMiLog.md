---
external help file: Microsoft.Management.Infrastructure.CimCmdlets.dll-Help.xml
Locale: en-US
Module Name: CimCmdlets
ms.date: 02/20/2019
online version: https://docs.microsoft.com/powershell/module/cimcmdlets/import-binarymilog?WT.mc_id=ps-gethelp
schema: 2.0.0
title: Import-BinaryMiLog
ms.openlocfilehash: 646f3e0990ce451300a28ca0de58576c70c55a9b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603215"
---
# <span data-ttu-id="fbc7b-102">Import-BinaryMiLog</span><span class="sxs-lookup"><span data-stu-id="fbc7b-102">Import-BinaryMiLog</span></span>

## <span data-ttu-id="fbc7b-103">概要</span><span class="sxs-lookup"><span data-stu-id="fbc7b-103">SYNOPSIS</span></span>
<span data-ttu-id="fbc7b-104">エクスポートファイルの内容に基づいて、保存されたオブジェクトを再作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="fbc7b-104">Used to re-create the saved objects based on the contents of an export file.</span></span>

## <span data-ttu-id="fbc7b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fbc7b-105">SYNTAX</span></span>

```
Import-BinaryMiLog [-Path] <String> [<CommonParameters>]
```

## <span data-ttu-id="fbc7b-106">Description</span><span class="sxs-lookup"><span data-stu-id="fbc7b-106">DESCRIPTION</span></span>

<span data-ttu-id="fbc7b-107">このコマンドレットを使用して、によって作成されたエクスポートファイルの内容に基づいて、保存されたオブジェクトを再作成し `Export-BinaryMILog` ます。</span><span class="sxs-lookup"><span data-stu-id="fbc7b-107">Use this cmdlet to re-create saved objects based on the contents of an export file created by `Export-BinaryMILog`.</span></span> <span data-ttu-id="fbc7b-108">このコマンドレットはに似ていますが、では `Import-Clixml` 、結果と `Export-BinaryMILog` して得られるオブジェクトがバイナリエンコードファイルに格納される点が異なります。</span><span class="sxs-lookup"><span data-stu-id="fbc7b-108">This cmdlet is similar to `Import-Clixml`, except that `Export-BinaryMILog` stores the resulting object in a binary encoded file.</span></span>

## <span data-ttu-id="fbc7b-109">例</span><span class="sxs-lookup"><span data-stu-id="fbc7b-109">EXAMPLES</span></span>

### <span data-ttu-id="fbc7b-110">例 1-ファイルにエクスポートされたオブジェクトを復元する</span><span class="sxs-lookup"><span data-stu-id="fbc7b-110">Example 1 - Restore objects exported to a file</span></span>

```powershell
Import-BinaryMiLog -Path "Processes.bmil"
```

## <span data-ttu-id="fbc7b-111">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fbc7b-111">PARAMETERS</span></span>

### <span data-ttu-id="fbc7b-112">-Path</span><span class="sxs-lookup"><span data-stu-id="fbc7b-112">-Path</span></span>

<span data-ttu-id="fbc7b-113">オブジェクトのバイナリ表現を格納するファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc7b-113">Specifies the path of the file in which to store the binary representation of the object.</span></span> <span data-ttu-id="fbc7b-114">**Path** パラメーターは、ワイルドカードと相対パスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fbc7b-114">The **Path** parameter supports wildcards and relative paths.</span></span> <span data-ttu-id="fbc7b-115">このコマンドレットは、パスが複数のファイルに解決された場合にエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="fbc7b-115">This cmdlet generates an error if the path resolves to more than one file.</span></span>

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

### <span data-ttu-id="fbc7b-116">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fbc7b-116">CommonParameters</span></span>
<span data-ttu-id="fbc7b-117">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="fbc7b-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fbc7b-118">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbc7b-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="fbc7b-119">入力</span><span class="sxs-lookup"><span data-stu-id="fbc7b-119">INPUTS</span></span>

### <span data-ttu-id="fbc7b-120">なし</span><span class="sxs-lookup"><span data-stu-id="fbc7b-120">None</span></span>

## <span data-ttu-id="fbc7b-121">出力</span><span class="sxs-lookup"><span data-stu-id="fbc7b-121">OUTPUTS</span></span>

### <span data-ttu-id="fbc7b-122">System.Object</span><span class="sxs-lookup"><span data-stu-id="fbc7b-122">System.Object</span></span>

## <span data-ttu-id="fbc7b-123">注</span><span class="sxs-lookup"><span data-stu-id="fbc7b-123">NOTES</span></span>

## <span data-ttu-id="fbc7b-124">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fbc7b-124">RELATED LINKS</span></span>
