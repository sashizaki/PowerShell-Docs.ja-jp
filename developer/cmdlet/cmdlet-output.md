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
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068557"
---
# <a name="cmdlet-output"></a><span data-ttu-id="29529-102">コマンドレット出力</span><span class="sxs-lookup"><span data-stu-id="29529-102">Cmdlet Output</span></span>

<span data-ttu-id="29529-103">このセクションでは、コマンドレットの出力とエラー メッセージやオブジェクトなどの出力を生成するコマンドレットを呼び出すことができるメソッドの種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="29529-103">This section discusses the types of cmdlet output and the methods that cmdlets can call to generate output such as error messages and objects.</span></span> <span data-ttu-id="29529-104">このセクションでは、コマンドレットによって返される .NET Framework の型を定義する方法とそれらのオブジェクトを表示する方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="29529-104">This section also describes how to define the .NET Framework types that are returned by your cmdlets and how those objects are displayed.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="29529-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="29529-105">In This Section</span></span>

<span data-ttu-id="29529-106">[コマンドレットの出力の種類](./types-of-cmdlet-output.md)型とコマンドレットを生成できる出力と出力を生成するコマンドレットを呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="29529-106">[Types of Cmdlet Output](./types-of-cmdlet-output.md) Describes the types and output that cmdlets can generate and the methods that cmdlets call to generate the output.</span></span>

<span data-ttu-id="29529-107">[コマンドレットのエラー報告](./cmdlet-error-reporting.md)コマンドレット エラーの報告、コマンドレットの出力のサブセットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="29529-107">[Cmdlet Error Reporting](./cmdlet-error-reporting.md) Discusses cmdlet error reporting, a subset of cmdlet output.</span></span>

<span data-ttu-id="29529-108">[出力オブジェクトの拡張](./extending-output-objects.md)によってコマンドレット、関数、およびスクリプトの種類のファイル (.ps1xml) を使用して、返される .NET Framework のオブジェクトを拡張する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="29529-108">[Extending Output Objects](./extending-output-objects.md) Discusses how to use the types files (.ps1xml) to extend the .NET Framework objects that are returned by cmdlets, functions, and scripts.</span></span>

<span data-ttu-id="29529-109">[PowerShell の書式設定ファイル](../format/powershell-formatting-files.md)書式設定ファイルについて説明します (. format.ps1xml) Windows PowerShell での .NET Framework オブジェクトの特定セットの既定値を定義するファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="29529-109">[PowerShell Formatting Files](../format/powershell-formatting-files.md) Describes the formatting files (.format.ps1xml) files that define the default display for a specific set of .NET Framework objects in Windows PowerShell.</span></span>

<span data-ttu-id="29529-110">[カスタムの書式設定ファイル](./custom-formatting-files.md)独自のカスタム書式設定を作成する既定値を上書きするファイルの表示形式または独自のコマンドによって返されるオブジェクトの表示を定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="29529-110">[Custom Formatting Files](./custom-formatting-files.md) Describes how to create your own custom formatting files to overwrite the default display formats or to define the display of objects returned by your own commands.</span></span>

## <a name="see-also"></a><span data-ttu-id="29529-111">参照</span><span class="sxs-lookup"><span data-stu-id="29529-111">See Also</span></span>

[<span data-ttu-id="29529-112">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="29529-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
