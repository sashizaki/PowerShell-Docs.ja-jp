---
ms.date: 09/13/2016
ms.topic: reference
title: HelpInfo XML ファイルを作成する方法
description: HelpInfo XML ファイルを作成する方法
ms.openlocfilehash: d5a24306aa6488fdefad0b7b1ea9e2978a93a7b5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647716"
---
# <a name="how-to-create-a-helpinfo-xml-file"></a><span data-ttu-id="ab85f-103">HelpInfo XML ファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="ab85f-103">How to Create a HelpInfo XML File</span></span>

<span data-ttu-id="ab85f-104">このセクションのこのトピックでは、PowerShell の更新可能なヘルプ機能について、"HelpInfo XML ファイル" と呼ばれるヘルプ情報ファイルを作成および設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab85f-104">This topics in this section explains how to create and populate a help information file, commonly known as a "HelpInfo XML file," for the PowerShell Updatable Help feature.</span></span>

## <a name="helpinfo-xml-file-overview"></a><span data-ttu-id="ab85f-105">HelpInfo XML ファイルの概要</span><span class="sxs-lookup"><span data-stu-id="ab85f-105">HelpInfo XML File Overview</span></span>

<span data-ttu-id="ab85f-106">HelpInfo XML ファイルは、モジュールの更新可能なヘルプに関する主要な情報源です。</span><span class="sxs-lookup"><span data-stu-id="ab85f-106">The HelpInfo XML file is the primary source of information about Updatable Help for the module.</span></span> <span data-ttu-id="ab85f-107">これには、モジュールのヘルプファイルの場所、サポートされている UI カルチャ、およびユーザーが最新のヘルプファイルを持っているかどうかを判断するために更新可能なヘルプが使用するバージョン番号が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ab85f-107">It includes the location of the help files for the modules, the supported UI cultures, and the version numbers that Updatable Help uses to determine whether the user has the newest help files.</span></span>

<span data-ttu-id="ab85f-108">モジュールに複数の UI カルチャ用の複数のヘルプファイルが含まれている場合でも、各モジュールには HelpInfo XML ファイルが1つだけあります。</span><span class="sxs-lookup"><span data-stu-id="ab85f-108">Each module has just one HelpInfo XML file, even if the module includes multiple help files for multiple UI cultures.</span></span> <span data-ttu-id="ab85f-109">モジュールの作成者は、HelpInfo XML ファイルを作成し、モジュールマニフェストの **Helpinfouri** キーによって指定されたインターネット上の場所に配置します。</span><span class="sxs-lookup"><span data-stu-id="ab85f-109">The module author creates the HelpInfo XML file and places it in the internet location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="ab85f-110">モジュールのヘルプファイルが更新されてアップロードされると、モジュールの作成者は HelpInfo XML ファイルを更新し、元の HelpInfo XML ファイルを新しいバージョンに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ab85f-110">When the module help files are updated and uploaded, the module author updates the HelpInfo XML file and replaces the original HelpInfo XML file with the new version.</span></span>

<span data-ttu-id="ab85f-111">HelpInfo XML ファイルは慎重に管理することが重要です。</span><span class="sxs-lookup"><span data-stu-id="ab85f-111">It is critical that the HelpInfo XML file is carefully maintained.</span></span> <span data-ttu-id="ab85f-112">新しいファイルをアップロードしても、バージョン番号の増分を忘れた場合は、更新可能なヘルプによってユーザーのコンピューターに新しいファイルがダウンロードされません。</span><span class="sxs-lookup"><span data-stu-id="ab85f-112">If you upload new files, but forget to increment the version numbers, Updatable Help will not download the new files to users' computers.</span></span> <span data-ttu-id="ab85f-113">新しい UI カルチャのヘルプファイルを追加しても、HelpInfo XML ファイルを更新したり、正しい場所に配置したりしないと、更新可能なヘルプで新しいファイルがダウンロードされません。</span><span class="sxs-lookup"><span data-stu-id="ab85f-113">if you add help files for a new UI culture, but don't update the HelpInfo XML file or place it in the correct location, Updatable Help will not download the new files.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="ab85f-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ab85f-114">In this section</span></span>

<span data-ttu-id="ab85f-115">このセクションには、次のトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="ab85f-115">This section includes the following topics.</span></span>

- [<span data-ttu-id="ab85f-116">HelpInfo XML スキーマ</span><span class="sxs-lookup"><span data-stu-id="ab85f-116">HelpInfo XML Schema</span></span>](./helpinfo-xml-schema.md)

- [<span data-ttu-id="ab85f-117">HelpInfo XML サンプル ファイル</span><span class="sxs-lookup"><span data-stu-id="ab85f-117">HelpInfo XML Sample File</span></span>](./helpinfo-xml-sample-file.md)

- [<span data-ttu-id="ab85f-118">HelpInfo XML ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="ab85f-118">How to Name a HelpInfo XML File</span></span>](./how-to-name-a-helpinfo-xml-file.md)

- [<span data-ttu-id="ab85f-119">HelpInfo XML バージョン番号を設定する方法</span><span class="sxs-lookup"><span data-stu-id="ab85f-119">How to Set HelpInfo XML Version Numbers</span></span>](./how-to-set-helpinfo-xml-version-numbers.md)

## <a name="see-also"></a><span data-ttu-id="ab85f-120">参照</span><span class="sxs-lookup"><span data-stu-id="ab85f-120">See Also</span></span>

[<span data-ttu-id="ab85f-121">更新可能なヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="ab85f-121">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)
