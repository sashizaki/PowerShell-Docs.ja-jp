---
ms.date: 09/13/2016
ms.topic: reference
title: コマンドレット出力
description: コマンドレット出力
ms.openlocfilehash: 37606e57d9dff3ed9fa25b2b99eb07efa0147127
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653256"
---
# <a name="cmdlet-output"></a><span data-ttu-id="134e3-103">コマンドレット出力</span><span class="sxs-lookup"><span data-stu-id="134e3-103">Cmdlet Output</span></span>

<span data-ttu-id="134e3-104">このセクションでは、コマンドレットの出力の種類と、コマンドレットがエラーメッセージやオブジェクトなどの出力を生成するために呼び出すことができるメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="134e3-104">This section discusses the types of cmdlet output and the methods that cmdlets can call to generate output such as error messages and objects.</span></span> <span data-ttu-id="134e3-105">このセクションでは、コマンドレットによって返される .NET Framework 型と、それらのオブジェクトの表示方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="134e3-105">This section also describes how to define the .NET Framework types that are returned by your cmdlets and how those objects are displayed.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="134e3-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="134e3-106">In This Section</span></span>

<span data-ttu-id="134e3-107">[コマンドレットの出力の種類](./types-of-cmdlet-output.md) コマンドレットによって生成される型と出力、およびコマンドレットが出力を生成するために呼び出すメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="134e3-107">[Types of Cmdlet Output](./types-of-cmdlet-output.md) Describes the types and output that cmdlets can generate and the methods that cmdlets call to generate the output.</span></span>

<span data-ttu-id="134e3-108">[コマンドレットのエラー報告](./cmdlet-error-reporting.md) コマンドレットの出力のサブセットであるコマンドレットのエラーレポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="134e3-108">[Cmdlet Error Reporting](./cmdlet-error-reporting.md) Discusses cmdlet error reporting, a subset of cmdlet output.</span></span>

<span data-ttu-id="134e3-109">[出力オブジェクトの拡張](./extending-output-objects.md) 型ファイル (types.ps1xml) を使用して、コマンドレット、関数、およびスクリプトによって返される .NET Framework オブジェクトを拡張する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="134e3-109">[Extending Output Objects](./extending-output-objects.md) Discusses how to use the types files (.ps1xml) to extend the .NET Framework objects that are returned by cmdlets, functions, and scripts.</span></span>

<span data-ttu-id="134e3-110">[PowerShell のフォーマットファイル](../format/powershell-formatting-files.md) Windows PowerShell の特定の .NET Framework オブジェクトのセットに対する既定の表示を定義するフォーマットファイル (.format.ps1xml) ファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="134e3-110">[PowerShell Formatting Files](../format/powershell-formatting-files.md) Describes the formatting files (.format.ps1xml) files that define the default display for a specific set of .NET Framework objects in Windows PowerShell.</span></span>

<span data-ttu-id="134e3-111">[カスタムの書式設定ファイル](./custom-formatting-files.md) 独自のカスタム書式設定ファイルを作成して、既定の表示形式を上書きしたり、独自のコマンドによって返されるオブジェクトの表示を定義したりする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="134e3-111">[Custom Formatting Files](./custom-formatting-files.md) Describes how to create your own custom formatting files to overwrite the default display formats or to define the display of objects returned by your own commands.</span></span>

## <a name="see-also"></a><span data-ttu-id="134e3-112">参照</span><span class="sxs-lookup"><span data-stu-id="134e3-112">See Also</span></span>

[<span data-ttu-id="134e3-113">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="134e3-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
