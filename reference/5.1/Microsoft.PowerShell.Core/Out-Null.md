---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-null?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Null
ms.openlocfilehash: 5a949629cdf0f0822866863822e82e70fc38d8c2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212843"
---
# <span data-ttu-id="82103-103">Out-Null</span><span class="sxs-lookup"><span data-stu-id="82103-103">Out-Null</span></span>

## <span data-ttu-id="82103-104">概要</span><span class="sxs-lookup"><span data-stu-id="82103-104">SYNOPSIS</span></span>
<span data-ttu-id="82103-105">パイプラインで送信するか、表示するのではなく、出力を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="82103-105">Hides the output instead of sending it down the pipeline or displaying it.</span></span>

## <span data-ttu-id="82103-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="82103-106">SYNTAX</span></span>

```
Out-Null [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="82103-107">Description</span><span class="sxs-lookup"><span data-stu-id="82103-107">DESCRIPTION</span></span>
<span data-ttu-id="82103-108">**Out null** コマンドレットは、出力を null に送信します。実際には、パイプラインから削除し、出力が画面に表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="82103-108">The **Out-Null** cmdlet sends its output to NULL, in effect, removing it from the pipeline and preventing the output to be displayed at the screen.</span></span> <span data-ttu-id="82103-109">これは、標準出力ストリームにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="82103-109">This only affects the standard output stream.</span></span>
<span data-ttu-id="82103-110">その他の出力ストリーム (エラーストリームなど) は影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="82103-110">Other output streams, like the Error stream are not affected.</span></span> <span data-ttu-id="82103-111">例外が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82103-111">Exceptions will be displayed.</span></span> <span data-ttu-id="82103-112">これにより、エラーが発生した場合にコマンドをテストしやすくなります。</span><span class="sxs-lookup"><span data-stu-id="82103-112">This makes it easier to test your command for any errors.</span></span>

## <span data-ttu-id="82103-113">例</span><span class="sxs-lookup"><span data-stu-id="82103-113">EXAMPLES</span></span>

### <span data-ttu-id="82103-114">例 1: 出力を削除する</span><span class="sxs-lookup"><span data-stu-id="82103-114">Example 1: Delete output</span></span>

```
PS C:\> Get-ChildItem | Out-Null
```

<span data-ttu-id="82103-115">このコマンドは、現在の場所/ディレクトリ内の項目を取得しますが、その出力はパイプラインから渡されず、コマンドラインにも表示されません。</span><span class="sxs-lookup"><span data-stu-id="82103-115">This command gets items in the current location/directory, but its output is not passed through the pipeline nor displayed at the command line.</span></span>
<span data-ttu-id="82103-116">これは、不要な出力を隠す場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="82103-116">This is useful for hiding output that you do not need.</span></span>

## <span data-ttu-id="82103-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="82103-117">PARAMETERS</span></span>

### <span data-ttu-id="82103-118">-InputObject</span><span class="sxs-lookup"><span data-stu-id="82103-118">-InputObject</span></span>
<span data-ttu-id="82103-119">(パイプラインから削除された) NULL に送信するオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="82103-119">Specifies the object to be sent to NULL (removed from pipeline).</span></span>
<span data-ttu-id="82103-120">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="82103-120">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="82103-121">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="82103-121">CommonParameters</span></span>
<span data-ttu-id="82103-122">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="82103-122">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="82103-123">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82103-123">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="82103-124">入力</span><span class="sxs-lookup"><span data-stu-id="82103-124">INPUTS</span></span>

### <span data-ttu-id="82103-125">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="82103-125">System.Management.Automation.PSObject</span></span>
<span data-ttu-id="82103-126">パイプを使用して任意のオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="82103-126">You can pipe any object to this cmdlet.</span></span>

## <span data-ttu-id="82103-127">出力</span><span class="sxs-lookup"><span data-stu-id="82103-127">OUTPUTS</span></span>

### <span data-ttu-id="82103-128">なし</span><span class="sxs-lookup"><span data-stu-id="82103-128">None</span></span>
<span data-ttu-id="82103-129">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="82103-129">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="82103-130">注</span><span class="sxs-lookup"><span data-stu-id="82103-130">NOTES</span></span>

* <span data-ttu-id="82103-131">**Out** 動詞 ( **out** コマンドレット) を含むコマンドレットには、名前またはファイルパスのパラメーターはありません。</span><span class="sxs-lookup"><span data-stu-id="82103-131">The cmdlets that contain the **Out** verb (the **Out** cmdlets) do not have parameters for names or file paths.</span></span> <span data-ttu-id="82103-132">**Out** コマンドレットにデータを送信するには、パイプライン演算子 (|) を使用して、Windows PowerShell コマンドの出力をコマンドレットに送信します。</span><span class="sxs-lookup"><span data-stu-id="82103-132">To send data to an **Out** cmdlet, use a pipeline operator (|) to send the output of a Windows PowerShell command to the cmdlet.</span></span> <span data-ttu-id="82103-133">変数にデータを格納し、 *InputObject* パラメーターを使用してコマンドレットにデータを渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="82103-133">You can also store data in a variable and use the *InputObject* parameter to pass the data to the cmdlet.</span></span> <span data-ttu-id="82103-134">詳細については、例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82103-134">For more information, see the examples.</span></span>
* <span data-ttu-id="82103-135">**Out-Null** は出力オブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="82103-135">**Out-Null** does not return any output objects.</span></span> <span data-ttu-id="82103-136">パイプを使用して **Out-Null** の出力を Get-Member コマンドレットに渡した場合、 **Get Member** はオブジェクトが指定されていないことを報告します。</span><span class="sxs-lookup"><span data-stu-id="82103-136">If you pipe the output of **Out-Null** to the Get-Member cmdlet, **Get-Member** reports that no objects have been specified.</span></span>

## <span data-ttu-id="82103-137">関連リンク</span><span class="sxs-lookup"><span data-stu-id="82103-137">RELATED LINKS</span></span>

[<span data-ttu-id="82103-138">Out-Default</span><span class="sxs-lookup"><span data-stu-id="82103-138">Out-Default</span></span>](Out-Default.md)

[<span data-ttu-id="82103-139">Out-Host</span><span class="sxs-lookup"><span data-stu-id="82103-139">Out-Host</span></span>](Out-Host.md)
