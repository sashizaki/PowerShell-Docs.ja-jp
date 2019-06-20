---
title: Windows PowerShell コマンドレットの記述 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a82aba91-71af-447d-b9ef-b6b6ac7d9de4
caps.latest.revision: 19
ms.openlocfilehash: 743efcf23174a9521925c5c19dd670979bc0c523
ms.sourcegitcommit: 13f24786ed39ca1c07eff2b73a1974c366e31cb8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2019
ms.locfileid: "67263820"
---
# <a name="writing-a-windows-powershell-cmdlet"></a><span data-ttu-id="3c9e6-102">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="3c9e6-102">Writing a Windows PowerShell Cmdlet</span></span>

<span data-ttu-id="3c9e6-103">プログラム マネージャーのコマンドレットを設計する場合に、コマンドレットのコードを実装している開発者は、「Windows PowerShell コマンドレットの記述」。</span><span class="sxs-lookup"><span data-stu-id="3c9e6-103">"Writing a Windows PowerShell Cmdlet" is for program managers who are designing cmdlets and for developers who are implementing cmdlet code.</span></span> <span data-ttu-id="3c9e6-104">コマンドレットの動作を理解するのに役立ちます、コマンドレットの記述を開始するために使用できるサンプル コードを提供およびコマンドレットのコードの背後にある基礎を学習するために使用できるチュートリアルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3c9e6-104">It will help you understand how cmdlets work, it provides sample code that you can use to start writing cmdlets, and it includes tutorials that you can use to learn the fundamentals behind the cmdlet code.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3c9e6-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3c9e6-105">In This Section</span></span>

<span data-ttu-id="3c9e6-106">[コマンドレットの概要](./cmdlet-overview.md)このトピックではどのようなコマンドレットは、の概要といくつかの重要な用語の把握する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c9e6-106">[Cmdlet Overview](./cmdlet-overview.md) This topic provides an overview of what a cmdlet is and of some important terms you need to know.</span></span>

<span data-ttu-id="3c9e6-107">[Windows PowerShell コマンドレットの概念](./windows-powershell-cmdlet-concepts.md)このセクションでは、コマンドレットの概要とそのしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3c9e6-107">[Windows PowerShell Cmdlet Concepts](./windows-powershell-cmdlet-concepts.md) This section describes what cmdlets are and how they work.</span></span>

<span data-ttu-id="3c9e6-108">[コマンドレット コードの例を](./examples-of-cmdlet-code.md)このセクションには、独自のコマンドレットの記述を開始するために使用できるコード例にはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c9e6-108">[Examples of Cmdlet Code](./examples-of-cmdlet-code.md) This section contains example code that you can use to start writing your own cmdlets.</span></span>

<span data-ttu-id="3c9e6-109">[コマンドレットの出力の書式設定ファイルの書き込み](../format/writing-a-powershell-formatting-file.md)このセクションでは、書式設定ファイルを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="3c9e6-109">[Writing Formatting Files for Cmdlet Output](../format/writing-a-powershell-formatting-file.md) This section describe how to create formatting files.</span></span> <span data-ttu-id="3c9e6-110">書式設定ファイルは、コマンドラインで、PowerShell がオブジェクトを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="3c9e6-110">Formatting files define how PowerShell displays objects at the command line.</span></span>

<span data-ttu-id="3c9e6-111">[コマンドレットの記述に関するチュートリアル](./tutorials-for-writing-cmdlets.md)このセクションには、コマンドレット コードの基礎を学習するために使用できるチュートリアルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c9e6-111">[Tutorials for Writing Cmdlets](./tutorials-for-writing-cmdlets.md) This section contains tutorials that you can use to learn about the fundamentals behind the cmdlet code.</span></span>

<span data-ttu-id="3c9e6-112">[コマンドレット サンプル](./cmdlet-samples.md)ここには、完全なコマンドレットのサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c9e6-112">[Cmdlet Samples](./cmdlet-samples.md) This section contains samples of complete cmdlets.</span></span>

## <a name="reference"></a><span data-ttu-id="3c9e6-113">参照先</span><span class="sxs-lookup"><span data-stu-id="3c9e6-113">Reference</span></span>

[<span data-ttu-id="3c9e6-114">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="3c9e6-114">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
