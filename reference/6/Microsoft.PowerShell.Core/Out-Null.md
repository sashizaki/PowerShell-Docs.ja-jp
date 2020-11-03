---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-null?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Null
ms.openlocfilehash: a9d5c47eaf189e37f7f16b11cd48101f7b0e584d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216395"
---
# <span data-ttu-id="7ecd1-103">Out-Null</span><span class="sxs-lookup"><span data-stu-id="7ecd1-103">Out-Null</span></span>

## <span data-ttu-id="7ecd1-104">概要</span><span class="sxs-lookup"><span data-stu-id="7ecd1-104">SYNOPSIS</span></span>
<span data-ttu-id="7ecd1-105">パイプラインで送信するか、表示するのではなく、出力を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="7ecd1-105">Hides the output instead of sending it down the pipeline or displaying it.</span></span>

## <span data-ttu-id="7ecd1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7ecd1-106">SYNTAX</span></span>

```
Out-Null [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="7ecd1-107">Description</span><span class="sxs-lookup"><span data-stu-id="7ecd1-107">DESCRIPTION</span></span>

<span data-ttu-id="7ecd1-108">**Out null** コマンドレットは、出力を null に送信します。実際には、パイプラインから削除し、出力が画面に表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="7ecd1-108">The **Out-Null** cmdlet sends its output to NULL, in effect, removing it from the pipeline and preventing the output to be displayed at the screen.</span></span>

## <span data-ttu-id="7ecd1-109">例</span><span class="sxs-lookup"><span data-stu-id="7ecd1-109">EXAMPLES</span></span>

### <span data-ttu-id="7ecd1-110">例 1: 出力を削除する</span><span class="sxs-lookup"><span data-stu-id="7ecd1-110">Example 1: Delete output</span></span>

```powershell
Get-ChildItem | Out-Null
```

<span data-ttu-id="7ecd1-111">このコマンドは、現在の場所/ディレクトリ内の項目を取得しますが、その出力はパイプラインから渡されず、コマンドラインにも表示されません。</span><span class="sxs-lookup"><span data-stu-id="7ecd1-111">This command gets items in the current location/directory, but its output is not passed through the pipeline nor displayed at the command line.</span></span>
<span data-ttu-id="7ecd1-112">これは、不要な出力を隠す場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="7ecd1-112">This is useful for hiding output that you do not need.</span></span>

## <span data-ttu-id="7ecd1-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7ecd1-113">PARAMETERS</span></span>

### <span data-ttu-id="7ecd1-114">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7ecd1-114">-InputObject</span></span>

<span data-ttu-id="7ecd1-115">(パイプラインから削除された) NULL に送信するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="7ecd1-115">Specifies the object to be sent to NULL (removed from pipeline).</span></span>
<span data-ttu-id="7ecd1-116">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="7ecd1-116">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="7ecd1-117">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7ecd1-117">CommonParameters</span></span>

<span data-ttu-id="7ecd1-118">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7ecd1-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7ecd1-119">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ecd1-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7ecd1-120">入力</span><span class="sxs-lookup"><span data-stu-id="7ecd1-120">INPUTS</span></span>

### <span data-ttu-id="7ecd1-121">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="7ecd1-121">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="7ecd1-122">パイプを使用して任意のオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="7ecd1-122">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="7ecd1-123">出力</span><span class="sxs-lookup"><span data-stu-id="7ecd1-123">OUTPUTS</span></span>

### <span data-ttu-id="7ecd1-124">なし</span><span class="sxs-lookup"><span data-stu-id="7ecd1-124">None</span></span>

<span data-ttu-id="7ecd1-125">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="7ecd1-125">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="7ecd1-126">注</span><span class="sxs-lookup"><span data-stu-id="7ecd1-126">NOTES</span></span>

* <span data-ttu-id="7ecd1-127">**Out** 動詞 ( **out** コマンドレット) を含むコマンドレットには、名前またはファイルパスのパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="7ecd1-127">The cmdlets that contain the **Out** verb (the **Out** cmdlets) do not have parameters for names or file paths.</span></span> <span data-ttu-id="7ecd1-128">**Out** コマンドレットにデータを送信するには、パイプライン演算子 (|) を使用して、PowerShell コマンドの出力をコマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="7ecd1-128">To send data to an **Out** cmdlet, use a pipeline operator (|) to send the output of a PowerShell command to the cmdlet.</span></span> <span data-ttu-id="7ecd1-129">変数にデータを格納し、 *InputObject* パラメーターを使用してコマンドレットにデータを渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="7ecd1-129">You can also store data in a variable and use the *InputObject* parameter to pass the data to the cmdlet.</span></span> <span data-ttu-id="7ecd1-130">詳細については、例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ecd1-130">For more information, see the examples.</span></span>
* <span data-ttu-id="7ecd1-131">**Out-Null** は出力オブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="7ecd1-131">**Out-Null** does not return any output objects.</span></span> <span data-ttu-id="7ecd1-132">パイプを使用して **Out-Null** の出力を Get-Member コマンドレットに渡した場合、 **Get Member** はオブジェクトが指定されていないことを報告します。</span><span class="sxs-lookup"><span data-stu-id="7ecd1-132">If you pipe the output of **Out-Null** to the Get-Member cmdlet, **Get-Member** reports that no objects have been specified.</span></span>

## <span data-ttu-id="7ecd1-133">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7ecd1-133">RELATED LINKS</span></span>

[<span data-ttu-id="7ecd1-134">Out-Default</span><span class="sxs-lookup"><span data-stu-id="7ecd1-134">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="7ecd1-135">Out-Host</span><span class="sxs-lookup"><span data-stu-id="7ecd1-135">Out-Host</span></span>](Out-Host.md)
