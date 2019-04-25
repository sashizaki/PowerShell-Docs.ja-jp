---
title: PowerShell のファイルを書式設定の書き込み |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39acce45-5144-43ba-894d-a4ce782fa67d
caps.latest.revision: 13
ms.openlocfilehash: f89f0009972d5237d71cb8f0d1c53cd0ae614b67
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62083577"
---
# <a name="writing-a-powershell-formatting-file"></a><span data-ttu-id="ad697-102">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="ad697-102">Writing a PowerShell Formatting File</span></span>

<span data-ttu-id="ad697-103">コマンドレットまたはコマンド ラインにオブジェクトを出力する関数を作成するコマンドの開発者が、「PowerShell 書式設定ファイルへの書き込み」です。</span><span class="sxs-lookup"><span data-stu-id="ad697-103">"Writing a PowerShell Formatting File" is for command developers who are writing cmdlets or functions that output objects to the command line.</span></span> <span data-ttu-id="ad697-104">書式設定ファイルは、PowerShell でのコマンドラインでこれらのオブジェクトの表示方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="ad697-104">Formatting files define how PowerShell displays those objects at the command line.</span></span> <span data-ttu-id="ad697-105">このドキュメントでは、XML 要素のこれらのファイルとリファレンスのセクションで使用される XML の例については、これらのファイルを書き込むときに理解しておくべき概念の説明、ファイルの書式設定の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="ad697-105">This documentation provides an overview of formatting files, an explanation of the concepts that you should understand when writing these files, examples of XML used in these files, and a reference section for the XML elements.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ad697-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ad697-106">In This Section</span></span>

<span data-ttu-id="ad697-107">[ファイルの概要を書式設定](./formatting-file-overview.md)さまざまな種類の .NET オブジェクトで定義できる形式のビューのファイルで定義できる共通の機能を含む、書式設定ファイルの一般的なコンポーネントとどのようなフォーマット ファイルが説明し、XML の簡単な例は、テーブル ビューの定義に使用します。</span><span class="sxs-lookup"><span data-stu-id="ad697-107">[Formatting File Overview](./formatting-file-overview.md) Describes what a format file is and the general components of a formatting file, including common features that can be defined in the file, the different types of format views that can be defined for .NET objects, and a simplified example of the XML used to define a table view.</span></span>

<span data-ttu-id="ad697-108">[ファイルの概念を書式設定](./formatting-file-concepts.md)ファイルする場合、独自の書式設定の作成、定義できるビューの種類とそれらのビューの特別なコンポーネントなどを把握する必要がある情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ad697-108">[Formatting File Concepts](./formatting-file-concepts.md) Includes information that you might need to know when creating your own formatting files, such as the different types of views that you can define and special components of those views.</span></span>

<span data-ttu-id="ad697-109">[書式設定ファイルの例は](./examples-of-formatting-files.md)テーブル ビュー、リスト ビュー、およびワイド ビューの例と選択のセットを選択条件などの機能を定義する方法を示す例を含め、いくつかの書式設定ファイルの提供の XML の例とコモン コントロール。</span><span class="sxs-lookup"><span data-stu-id="ad697-109">[Examples of Formatting Files](./examples-of-formatting-files.md) Provides XML examples of several formatting files, including examples of a table view, a list view, and a wide view, as well as examples that show how to define features such as selection sets, selection conditions, and common controls.</span></span>

<span data-ttu-id="ad697-110">[XML のリファレンスを書式設定](./format-schema-xml-reference.md)書式設定ファイルで使用される XML 要素のリファレンス トピックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ad697-110">[Format XML Reference](./format-schema-xml-reference.md) Includes reference topics for the XML elements used in a formatting file.</span></span>
