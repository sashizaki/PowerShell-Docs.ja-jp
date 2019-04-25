---
title: HelpInfo XML ファイルを作成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3971ce1f-271c-4938-a9d3-47ff3aaf7219
caps.latest.revision: 9
ms.openlocfilehash: 7df9764fd573b75f285fec592448a550e481bea3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082415"
---
# <a name="how-to-create-a-helpinfo-xml-file"></a><span data-ttu-id="1ef5a-102">HelpInfo XML ファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="1ef5a-102">How to Create a HelpInfo XML File</span></span>

<span data-ttu-id="1ef5a-103">このセクションでは、このトピックでは、作成し、一般的"HelpInfo XML ファイルが、"Windows PowerShell の更新可能なヘルプ機能と呼ばれる、ヘルプ情報ファイルを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1ef5a-103">This topics in this section explains how to create and populate a help information file, commonly known as a "HelpInfo XML file," for the Windows PowerShell Updatable Help feature.</span></span>

## <a name="helpinfo-xml-file-overview"></a><span data-ttu-id="1ef5a-104">HelpInfo XML ファイルの概要</span><span class="sxs-lookup"><span data-stu-id="1ef5a-104">HelpInfo XML File Overview</span></span>

<span data-ttu-id="1ef5a-105">HelpInfo XML ファイルは、主要なモジュールの更新可能なヘルプについての情報源です。</span><span class="sxs-lookup"><span data-stu-id="1ef5a-105">The HelpInfo XML file is the primary source of information about Updatable Help for the module.</span></span> <span data-ttu-id="1ef5a-106">これには、モジュール、サポートされている UI カルチャ、および更新可能なヘルプを使用して、ユーザーが最新のヘルプ ファイルを持つかどうかを決定するバージョン番号のヘルプ ファイルの場所が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1ef5a-106">It includes the location of the help files for the modules, the supported UI cultures, and the version numbers that Updatable Help uses to determine whether the user has the newest help files.</span></span>

<span data-ttu-id="1ef5a-107">各モジュールは、モジュールには、複数の UI カルチャ用の複数のヘルプ ファイルが含まれています。 場合でも、1 つだけの HelpInfo XML ファイルを持っています。</span><span class="sxs-lookup"><span data-stu-id="1ef5a-107">Each module has just one HelpInfo XML file, even if the module includes multiple help files for multiple UI cultures.</span></span> <span data-ttu-id="1ef5a-108">モジュールの作成者が HelpInfo XML ファイルを作成しで指定されたインターネット上の場所に配置、 **HelpInfoUri**モジュール マニフェストでキー。</span><span class="sxs-lookup"><span data-stu-id="1ef5a-108">The module author creates the HelpInfo XML file and places it in the Internet location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="1ef5a-109">モジュールのヘルプ ファイルが更新され、アップロード、ときに、モジュールの作成者は HelpInfo XML ファイルを更新し、元の HelpInfo XML ファイルを新しいバージョンに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1ef5a-109">When the module help files are updated and uploaded, the module author updates the HelpInfo XML file and replaces the original HelpInfo XML file with the new version.</span></span>

<span data-ttu-id="1ef5a-110">HelpInfo XML ファイルを慎重に維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1ef5a-110">It is critical that the HelpInfo XML file is carefully maintained.</span></span> <span data-ttu-id="1ef5a-111">新しいファイルをアップロードする場合は、バージョン番号をインクリメントすることを忘れないで更新可能なヘルプ ユーザーのコンピューターの新しいファイルはダウンロードされません。</span><span class="sxs-lookup"><span data-stu-id="1ef5a-111">If you upload new files, but forget to increment the version numbers, Updatable Help will not download the new files to users' computers.</span></span> <span data-ttu-id="1ef5a-112">新しい UI カルチャのヘルプ ファイルの追加が HelpInfo XML ファイルを更新または適切な場所に配置場合、更新可能なヘルプと新しいファイルがダウンロードされません。</span><span class="sxs-lookup"><span data-stu-id="1ef5a-112">if you add help files for a new UI culture, but don't update the HelpInfo XML file or place it in the correct location, Updatable Help will not download the new files.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1ef5a-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1ef5a-113">In this section</span></span>

<span data-ttu-id="1ef5a-114">このセクションには、次のトピックがあります。</span><span class="sxs-lookup"><span data-stu-id="1ef5a-114">This section includes the following topics.</span></span>

- [<span data-ttu-id="1ef5a-115">HelpInfo XML スキーマ</span><span class="sxs-lookup"><span data-stu-id="1ef5a-115">HelpInfo XML Schema</span></span>](./helpinfo-xml-schema.md)

- [<span data-ttu-id="1ef5a-116">HelpInfo XML ファイルのサンプル</span><span class="sxs-lookup"><span data-stu-id="1ef5a-116">HelpInfo XML Sample File</span></span>](./helpinfo-xml-sample-file.md)

- [<span data-ttu-id="1ef5a-117">HelpInfo XML ファイル名を指定する方法</span><span class="sxs-lookup"><span data-stu-id="1ef5a-117">How to Name a HelpInfo XML File</span></span>](./how-to-name-a-helpinfo-xml-file.md)

- [<span data-ttu-id="1ef5a-118">HelpInfo XML バージョン番号を設定する方法</span><span class="sxs-lookup"><span data-stu-id="1ef5a-118">How to Set HelpInfo XML Version Numbers</span></span>](./how-to-set-helpinfo-xml-version-numbers.md)

## <a name="see-also"></a><span data-ttu-id="1ef5a-119">参照</span><span class="sxs-lookup"><span data-stu-id="1ef5a-119">See Also</span></span>

[<span data-ttu-id="1ef5a-120">更新可能なヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="1ef5a-120">Supporting Updatable Help</span></span>](./supporting-updatable-help.md)