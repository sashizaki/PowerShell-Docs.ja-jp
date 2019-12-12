---
title: コマンドレットの出力 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1362f4cd-4e05-4ace-ade6-7128da8ad86c
caps.latest.revision: 10
ms.openlocfilehash: 4c6aacd49b0a87bca6806ba5f08a1b4d48a90959
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365941"
---
# <a name="cmdlet-output"></a><span data-ttu-id="5e9d8-102">コマンドレット出力</span><span class="sxs-lookup"><span data-stu-id="5e9d8-102">Cmdlet Output</span></span>

<span data-ttu-id="5e9d8-103">このセクションでは、コマンドレットの出力の種類と、コマンドレットがエラーメッセージやオブジェクトなどの出力を生成するために呼び出すことができるメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5e9d8-103">This section discusses the types of cmdlet output and the methods that cmdlets can call to generate output such as error messages and objects.</span></span> <span data-ttu-id="5e9d8-104">このセクションでは、コマンドレットによって返される .NET Framework 型と、それらのオブジェクトの表示方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="5e9d8-104">This section also describes how to define the .NET Framework types that are returned by your cmdlets and how those objects are displayed.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="5e9d8-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5e9d8-105">In This Section</span></span>

<span data-ttu-id="5e9d8-106">[コマンドレットの出力の種類](./types-of-cmdlet-output.md)コマンドレットによって生成される型と出力、およびコマンドレットが出力を生成するために呼び出すメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5e9d8-106">[Types of Cmdlet Output](./types-of-cmdlet-output.md) Describes the types and output that cmdlets can generate and the methods that cmdlets call to generate the output.</span></span>

<span data-ttu-id="5e9d8-107">[コマンドレットのエラー報告](./cmdlet-error-reporting.md)コマンドレットの出力のサブセットであるコマンドレットのエラーレポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5e9d8-107">[Cmdlet Error Reporting](./cmdlet-error-reporting.md) Discusses cmdlet error reporting, a subset of cmdlet output.</span></span>

<span data-ttu-id="5e9d8-108">[出力オブジェクトの拡張](./extending-output-objects.md)型ファイル (types.ps1xml) を使用して、コマンドレット、関数、およびスクリプトによって返される .NET Framework オブジェクトを拡張する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e9d8-108">[Extending Output Objects](./extending-output-objects.md) Discusses how to use the types files (.ps1xml) to extend the .NET Framework objects that are returned by cmdlets, functions, and scripts.</span></span>

<span data-ttu-id="5e9d8-109">[PowerShell のフォーマットファイル](../format/powershell-formatting-files.md)Windows PowerShell で .NET Framework オブジェクトの特定のセットの既定の表示を定義する、書式設定ファイル (types.ps1xml) ファイルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5e9d8-109">[PowerShell Formatting Files](../format/powershell-formatting-files.md) Describes the formatting files (.format.ps1xml) files that define the default display for a specific set of .NET Framework objects in Windows PowerShell.</span></span>

<span data-ttu-id="5e9d8-110">[カスタムの書式設定ファイル](./custom-formatting-files.md)独自のカスタム書式設定ファイルを作成して、既定の表示形式を上書きしたり、独自のコマンドによって返されるオブジェクトの表示を定義したりする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5e9d8-110">[Custom Formatting Files](./custom-formatting-files.md) Describes how to create your own custom formatting files to overwrite the default display formats or to define the display of objects returned by your own commands.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e9d8-111">参照</span><span class="sxs-lookup"><span data-stu-id="5e9d8-111">See Also</span></span>

[<span data-ttu-id="5e9d8-112">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="5e9d8-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
