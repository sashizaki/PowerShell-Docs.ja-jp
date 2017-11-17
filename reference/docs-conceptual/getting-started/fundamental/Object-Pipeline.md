---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "オブジェクト パイプライン"
ms.assetid: 523d8ae4-d743-47a4-b79a-806130ca688a
ms.openlocfilehash: 3fa41cc744cf3ab66fc5ef186ead8eb919429a76
ms.sourcegitcommit: 74255f0b5f386a072458af058a15240140acb294
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2017
---
# <a name="object-pipeline"></a><span data-ttu-id="6af4f-103">オブジェクト パイプライン</span><span class="sxs-lookup"><span data-stu-id="6af4f-103">Object Pipeline</span></span>
<span data-ttu-id="6af4f-104">パイプラインは、複数の管を 1 つに継ぎ合わせた管路のような役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="6af4f-104">Pipelines act like a series of connected segments of pipe.</span></span> <span data-ttu-id="6af4f-105">パイプラインに沿って移動する項目は、個々の管を通過します。</span><span class="sxs-lookup"><span data-stu-id="6af4f-105">Items moving along the pipeline pass through each segment.</span></span> <span data-ttu-id="6af4f-106">Windows PowerShell でパイプラインを作成するには、パイプ演算子 (|) を使ってコマンドを接続します。</span><span class="sxs-lookup"><span data-stu-id="6af4f-106">To create a pipeline in Windows PowerShell, you connect commands together with the pipe operator "|".</span></span> <span data-ttu-id="6af4f-107">接続すると、各コマンドの出力が、次のコマンドの入力として使用されるようになります。</span><span class="sxs-lookup"><span data-stu-id="6af4f-107">The output of each command is used as input to the next command.</span></span>

<span data-ttu-id="6af4f-108">パイプラインは、コマンドライン インターフェイスで使用される最も重要な概念と言っても過言ではありません。</span><span class="sxs-lookup"><span data-stu-id="6af4f-108">Pipelines are arguably the most valuable concept used in command-line interfaces.</span></span> <span data-ttu-id="6af4f-109">パイプラインを適切に使用すると、複雑なコマンドを少ない手間で入力できるだけでなく、コマンドの処理の流れを容易に把握できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6af4f-109">Properly used, pipelines not only reduce the effort involved in entering complex commands, but also make it easier to see the flow of work in the commands.</span></span> <span data-ttu-id="6af4f-110">パイプラインが持つもう 1 つの特長として、パイプラインは各項目を個別に処理するため、パイプライン内の項目数 (0 個、1 個、または多数) に合わせて修正する必要がないという点があります。</span><span class="sxs-lookup"><span data-stu-id="6af4f-110">A related useful characteristic of pipelines is that because they operate on each item separately, you do not have to modify them based on whether you will have zero, one, or many items in the pipeline.</span></span> <span data-ttu-id="6af4f-111">さらに、パイプラインの各コマンド (パイプライン要素) は、通常、その出力をパイプライン内の次のコマンドに項目単位で渡します。</span><span class="sxs-lookup"><span data-stu-id="6af4f-111">Furthermore, each command in a pipeline (called a pipeline element) usually passes its output to the next command in the pipeline item-by-item.</span></span> <span data-ttu-id="6af4f-112">一般に、このことによって、複雑なコマンドによって生じるリソースの消費を抑え、出力を直ちに受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="6af4f-112">This usually reduces the resource demand of complex commands and allows you to begin getting the output immediately.</span></span>

<span data-ttu-id="6af4f-113">この章では、Windows PowerShell のパイプラインと、従来のシェルのパイプラインとの違いについて説明します。また、パイプラインの出力を制御したり、パイプラインの動作を表示したりするための基本的なツールをいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="6af4f-113">In this chapter, we will describe how the Windows PowerShell pipeline differs from the pipelines of most popular shells, and then demonstrate some basic tools that you can use to help control pipeline output and also to see how the pipeline operates.</span></span>

