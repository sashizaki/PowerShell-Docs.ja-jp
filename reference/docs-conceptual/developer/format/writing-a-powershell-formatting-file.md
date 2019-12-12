---
title: PowerShell 形式のフォーマットファイルを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 39acce45-5144-43ba-894d-a4ce782fa67d
caps.latest.revision: 13
ms.openlocfilehash: f89f0009972d5237d71cb8f0d1c53cd0ae614b67
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72361411"
---
# <a name="writing-a-powershell-formatting-file"></a><span data-ttu-id="93553-102">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="93553-102">Writing a PowerShell Formatting File</span></span>

<span data-ttu-id="93553-103">「PowerShell フォーマットファイルの作成」は、コマンドレットを記述するコマンド開発者、またはオブジェクトをコマンドラインに出力する関数です。</span><span class="sxs-lookup"><span data-stu-id="93553-103">"Writing a PowerShell Formatting File" is for command developers who are writing cmdlets or functions that output objects to the command line.</span></span> <span data-ttu-id="93553-104">ファイルのフォーマットでは、PowerShell がコマンドラインでそれらのオブジェクトを表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="93553-104">Formatting files define how PowerShell displays those objects at the command line.</span></span> <span data-ttu-id="93553-105">このドキュメントでは、フォーマットファイルの概要、これらのファイルを記述するときに理解しておく必要がある概念の説明、これらのファイルで使用される XML の例、および XML 要素のリファレンスセクションを示します。</span><span class="sxs-lookup"><span data-stu-id="93553-105">This documentation provides an overview of formatting files, an explanation of the concepts that you should understand when writing these files, examples of XML used in these files, and a reference section for the XML elements.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="93553-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="93553-106">In This Section</span></span>

<span data-ttu-id="93553-107">[フォーマットファイルの概要](./formatting-file-overview.md)フォーマットファイルの概要と、フォーマットファイルの一般的なコンポーネントについて説明します。これには、ファイルで定義できる共通機能、.NET オブジェクトに対して定義できるさまざまな種類のフォーマットビュー、テーブルビューの定義に使用される XML の簡略化された例などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="93553-107">[Formatting File Overview](./formatting-file-overview.md) Describes what a format file is and the general components of a formatting file, including common features that can be defined in the file, the different types of format views that can be defined for .NET objects, and a simplified example of the XML used to define a table view.</span></span>

<span data-ttu-id="93553-108">[フォーマットファイルの概念](./formatting-file-concepts.md)独自のフォーマットファイルを作成する場合に必要な情報が含まれています。たとえば、定義可能なさまざまな種類のビューや、それらのビューの特殊なコンポーネントなどです。</span><span class="sxs-lookup"><span data-stu-id="93553-108">[Formatting File Concepts](./formatting-file-concepts.md) Includes information that you might need to know when creating your own formatting files, such as the different types of views that you can define and special components of those views.</span></span>

<span data-ttu-id="93553-109">[フォーマットファイルの例](./examples-of-formatting-files.md)いくつかの書式設定ファイルの XML の例を示します。たとえば、テーブルビュー、リストビュー、ワイドビューの例に加えて、選択セット、選択条件、一般的なコントロールなどの機能を定義する方法を示す例もあります。</span><span class="sxs-lookup"><span data-stu-id="93553-109">[Examples of Formatting Files](./examples-of-formatting-files.md) Provides XML examples of several formatting files, including examples of a table view, a list view, and a wide view, as well as examples that show how to define features such as selection sets, selection conditions, and common controls.</span></span>

<span data-ttu-id="93553-110">[フォーマット XML リファレンス](./format-schema-xml-reference.md)書式設定ファイルで使用される XML 要素のリファレンストピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="93553-110">[Format XML Reference](./format-schema-xml-reference.md) Includes reference topics for the XML elements used in a formatting file.</span></span>
