---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 04/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/out-default?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-Default
ms.openlocfilehash: 5e434b6af523da25b0128f6d8e85a196eaf09ff2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212851"
---
# <span data-ttu-id="7e4e0-103">Out-Default</span><span class="sxs-lookup"><span data-stu-id="7e4e0-103">Out-Default</span></span>

## <span data-ttu-id="7e4e0-104">概要</span><span class="sxs-lookup"><span data-stu-id="7e4e0-104">SYNOPSIS</span></span>
<span data-ttu-id="7e4e0-105">既定のフォーマッタおよび既定の出力コマンドレットに出力を送信します。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-105">Sends the output to the default formatter and to the default output cmdlet.</span></span>

## <span data-ttu-id="7e4e0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="7e4e0-106">SYNTAX</span></span>

```
Out-Default [-Transcript] [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="7e4e0-107">Description</span><span class="sxs-lookup"><span data-stu-id="7e4e0-107">DESCRIPTION</span></span>

<span data-ttu-id="7e4e0-108">PowerShell `Out-Default` は、すべてのパイプラインの末尾にを自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-108">PowerShell automatically adds `Out-Default` to the end of every pipeline.</span></span> <span data-ttu-id="7e4e0-109">`Out-Default` オブジェクトストリームを書式設定し、出力する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-109">`Out-Default` decides how to format and output the object stream.</span></span> <span data-ttu-id="7e4e0-110">オブジェクトストリームが文字列のストリームである場合は、 `Out-Default` これらのを直接パイプし `Out-Host` て、ホストによって提供される適切な api を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-110">If the object stream is a stream of strings, `Out-Default` pipes these directly to `Out-Host` which calls the appropriate APIs provided by the host.</span></span> <span data-ttu-id="7e4e0-111">オブジェクトストリームに文字列が含まれていない場合は、 `Out-Default` オブジェクトを調べて何を行うかを決定します。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-111">If the object stream does not contain strings, `Out-Default` inspects the object to determine what to do.</span></span>
<span data-ttu-id="7e4e0-112">まず、オブジェクトの種類を確認し、このオブジェクトの種類に対して登録済みの _ビュー_ があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-112">First it looks at the object type and determines whether there is a registered _view_ for this object type.</span></span>

<span data-ttu-id="7e4e0-113">PowerShell では、XML スキーマと、 `Update-FormatData` 任意のユーザーがオブジェクトの種類のビューを登録できるメカニズム (コマンドレット) が定義されています。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-113">PowerShell defines XML schema and a mechanism (the `Update-FormatData` cmdlet) where anyone can register views for an object type.</span></span> <span data-ttu-id="7e4e0-114">任意のオブジェクトの種類に対して、 **横** 、 **一覧** 、 **テーブル** 、または **カスタム** ビューを指定できます。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-114">You can specify **wide** , **list** , **table** , or **custom** views for any object type.</span></span> <span data-ttu-id="7e4e0-115">ビューでは、表示するプロパティと表示方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-115">The views specify which properties to display and how they should be displayed.</span></span> <span data-ttu-id="7e4e0-116">ビューが登録されている場合は、使用するフォーマッタを定義します。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-116">If a view is registered, it defines which formatter to use.</span></span> <span data-ttu-id="7e4e0-117">そのため、登録されたビューが **テーブル** ビューの場合、は `Out-Default` オブジェクトをにストリームし `Format-Table | Out-Host` ます。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-117">So if the registered view is a **table** view, `Out-Default` streams the objects to `Format-Table | Out-Host`.</span></span> <span data-ttu-id="7e4e0-118">`Format-Table` オブジェクトを (ビュー定義のデータによって駆動される) 書式設定レコードのストリームに変換し、その `Out-Host` 書式設定レコードをホストインターフェイスの呼び出しに変換します。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-118">`Format-Table` transforms the objects into a stream of Formatting records (driven by the data in the view definition) and `Out-Host` transforms the formatting records into calls on the Host interface.</span></span>

## <span data-ttu-id="7e4e0-119">例</span><span class="sxs-lookup"><span data-stu-id="7e4e0-119">EXAMPLES</span></span>

### <span data-ttu-id="7e4e0-120">例 1</span><span class="sxs-lookup"><span data-stu-id="7e4e0-120">Example 1</span></span>

<span data-ttu-id="7e4e0-121">このコマンドレットはエンドユーザーが直接実行することを意図していませんが、にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-121">While this cmdlet is not intended to be run directly by the end user, it can be.</span></span>

```powershell
Get-Process | Select-Object -First 5 | Out-Default
```

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     12     2.56       5.20       0.00    7376   0 aesm_service
     48    34.32      18.10      26.64    9320  13 AlertusDesktopAlert
     24    13.97      12.74       0.77   12656  13 ApplicationFrameHost
      8     1.79       4.41       0.00    8180   0 AppVShNotify
      9     1.99       5.07       0.19   19320  13 AppVShNotify
```

## <span data-ttu-id="7e4e0-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="7e4e0-122">PARAMETERS</span></span>

### <span data-ttu-id="7e4e0-123">-InputObject</span><span class="sxs-lookup"><span data-stu-id="7e4e0-123">-InputObject</span></span>

<span data-ttu-id="7e4e0-124">コマンドレットへの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-124">Accepts input to the cmdlet.</span></span>

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

### <span data-ttu-id="7e4e0-125">-トランスクリプト</span><span class="sxs-lookup"><span data-stu-id="7e4e0-125">-Transcript</span></span>

<span data-ttu-id="7e4e0-126">出力を PowerShell の議事録サービスに送信するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-126">Determines whether the output should be sent to PowerShell's transcription services.</span></span>

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

### <span data-ttu-id="7e4e0-127">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="7e4e0-127">CommonParameters</span></span>

<span data-ttu-id="7e4e0-128">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="7e4e0-129">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7e4e0-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="7e4e0-130">入力</span><span class="sxs-lookup"><span data-stu-id="7e4e0-130">INPUTS</span></span>

## <span data-ttu-id="7e4e0-131">出力</span><span class="sxs-lookup"><span data-stu-id="7e4e0-131">OUTPUTS</span></span>

## <span data-ttu-id="7e4e0-132">注</span><span class="sxs-lookup"><span data-stu-id="7e4e0-132">NOTES</span></span>

## <span data-ttu-id="7e4e0-133">関連リンク</span><span class="sxs-lookup"><span data-stu-id="7e4e0-133">RELATED LINKS</span></span>

[<span data-ttu-id="7e4e0-134">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="7e4e0-134">Format-Custom</span></span>](../Microsoft.PowerShell.Utility/Format-Custom.md)

[<span data-ttu-id="7e4e0-135">Format-List</span><span class="sxs-lookup"><span data-stu-id="7e4e0-135">Format-List</span></span>](../Microsoft.PowerShell.Utility/Format-List.md)

[<span data-ttu-id="7e4e0-136">Format-Table</span><span class="sxs-lookup"><span data-stu-id="7e4e0-136">Format-Table</span></span>](../Microsoft.PowerShell.Utility/Format-Table.md)

[<span data-ttu-id="7e4e0-137">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="7e4e0-137">Format-Wide</span></span>](../Microsoft.PowerShell.Utility/Format-Wide.md)

[<span data-ttu-id="7e4e0-138">about_Format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="7e4e0-138">about_Format.ps1xml</span></span>](About/about_Format.ps1xml.md)

[<span data-ttu-id="7e4e0-139">PowerShell の書式設定と出力が実際に動作するしくみ</span><span class="sxs-lookup"><span data-stu-id="7e4e0-139">How PowerShell Formatting and Outputting REALLY works</span></span>](https://devblogs.microsoft.com/powershell/how-powershell-formatting-and-outputting-really-works/)
