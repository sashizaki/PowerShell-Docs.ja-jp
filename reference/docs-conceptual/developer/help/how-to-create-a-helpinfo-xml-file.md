---
title: HelpInfo XML ファイルを作成する方法
ms.date: 09/13/2016
ms.openlocfilehash: e395746e51309477bbcbff51b4591de3f73ce0db
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893307"
---
# <a name="how-to-create-a-helpinfo-xml-file"></a><span data-ttu-id="23c4f-102">HelpInfo XML ファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="23c4f-102">How to Create a HelpInfo XML File</span></span>

<span data-ttu-id="23c4f-103">このセクションのこのトピックでは、PowerShell の更新可能なヘルプ機能について、"HelpInfo XML ファイル" と呼ばれるヘルプ情報ファイルを作成および設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="23c4f-103">This topics in this section explains how to create and populate a help information file, commonly known as a "HelpInfo XML file," for the PowerShell Updatable Help feature.</span></span>

## <a name="helpinfo-xml-file-overview"></a><span data-ttu-id="23c4f-104">HelpInfo XML ファイルの概要</span><span class="sxs-lookup"><span data-stu-id="23c4f-104">HelpInfo XML File Overview</span></span>

<span data-ttu-id="23c4f-105">HelpInfo XML ファイルは、モジュールの更新可能なヘルプに関する主要な情報源です。</span><span class="sxs-lookup"><span data-stu-id="23c4f-105">The HelpInfo XML file is the primary source of information about Updatable Help for the module.</span></span> <span data-ttu-id="23c4f-106">これには、モジュールのヘルプファイルの場所、サポートされている UI カルチャ、およびユーザーが最新のヘルプファイルを持っているかどうかを判断するために更新可能なヘルプが使用するバージョン番号が含まれます。</span><span class="sxs-lookup"><span data-stu-id="23c4f-106">It includes the location of the help files for the modules, the supported UI cultures, and the version numbers that Updatable Help uses to determine whether the user has the newest help files.</span></span>

<span data-ttu-id="23c4f-107">モジュールに複数の UI カルチャ用の複数のヘルプファイルが含まれている場合でも、各モジュールには HelpInfo XML ファイルが1つだけあります。</span><span class="sxs-lookup"><span data-stu-id="23c4f-107">Each module has just one HelpInfo XML file, even if the module includes multiple help files for multiple UI cultures.</span></span> <span data-ttu-id="23c4f-108">モジュールの作成者は、HelpInfo XML ファイルを作成し、モジュールマニフェストの**Helpinfouri**キーによって指定されたインターネット上の場所に配置します。</span><span class="sxs-lookup"><span data-stu-id="23c4f-108">The module author creates the HelpInfo XML file and places it in the internet location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="23c4f-109">モジュールのヘルプファイルが更新されてアップロードされると、モジュールの作成者は HelpInfo XML ファイルを更新し、元の HelpInfo XML ファイルを新しいバージョンに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="23c4f-109">When the module help files are updated and uploaded, the module author updates the HelpInfo XML file and replaces the original HelpInfo XML file with the new version.</span></span>

<span data-ttu-id="23c4f-110">HelpInfo XML ファイルは慎重に管理することが重要です。</span><span class="sxs-lookup"><span data-stu-id="23c4f-110">It is critical that the HelpInfo XML file is carefully maintained.</span></span> <span data-ttu-id="23c4f-111">新しいファイルをアップロードしても、バージョン番号の増分を忘れた場合は、更新可能なヘルプによってユーザーのコンピューターに新しいファイルがダウンロードされません。</span><span class="sxs-lookup"><span data-stu-id="23c4f-111">If you upload new files, but forget to increment the version numbers, Updatable Help will not download the new files to users' computers.</span></span> <span data-ttu-id="23c4f-112">新しい UI カルチャのヘルプファイルを追加しても、HelpInfo XML ファイルを更新したり、正しい場所に配置したりしないと、更新可能なヘルプで新しいファイルがダウンロードされません。</span><span class="sxs-lookup"><span data-stu-id="23c4f-112">if you add help files for a new UI culture, but don't update the HelpInfo XML file or place it in the correct location, Updatable Help will not download the new files.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="23c4f-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="23c4f-113">In this section</span></span>

<span data-ttu-id="23c4f-114">このセクションには、次のトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="23c4f-114">This section includes the following topics.</span></span>

- [<span data-ttu-id="23c4f-115">HelpInfo XML スキーマ</span><span class="sxs-lookup"><span data-stu-id="23c4f-115">HelpInfo XML Schema</span></span>](./helpinfo-xml-schema.md)

- [<span data-ttu-id="23c4f-116">HelpInfo XML サンプル ファイル</span><span class="sxs-lookup"><span data-stu-id="23c4f-116">HelpInfo XML Sample File</span></span>](./helpinfo-xml-sample-file.md)

- [<span data-ttu-id="23c4f-117">HelpInfo XML ファイルに名前を付ける方法</span><span class="sxs-lookup"><span data-stu-id="23c4f-117">How to Name a HelpInfo XML File</span></span>](./how-to-name-a-helpinfo-xml-file.md)

- [<span data-ttu-id="23c4f-118">HelpInfo XML バージョン番号を設定する方法</span><span class="sxs-lookup"><span data-stu-id="23c4f-118">How to Set HelpInfo XML Version Numbers</span></span>](./how-to-set-helpinfo-xml-version-numbers.md)

## <a name="see-also"></a><span data-ttu-id="23c4f-119">参照</span><span class="sxs-lookup"><span data-stu-id="23c4f-119">See Also</span></span>

[<span data-ttu-id="23c4f-120">更新可能なヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="23c4f-120">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)
