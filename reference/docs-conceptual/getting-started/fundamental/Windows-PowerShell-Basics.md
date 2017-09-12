---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell の基礎"
ms.assetid: 6b3cbbc8-060c-4877-b00b-7300dbbe4e28
ms.openlocfilehash: 7b5cdfce876aa7d5559fe772379829011b275a02
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2017
---
# <a name="windows-powershell-basics"></a><span data-ttu-id="7d30b-103">Windows PowerShell の基礎</span><span class="sxs-lookup"><span data-stu-id="7d30b-103">Windows PowerShell Basics</span></span>
<span data-ttu-id="7d30b-104">グラフィカル ユーザー インターフェイスでは、ほとんどのコンピューターのユーザーによく知られているいくつかの基本的な概念を使用します。</span><span class="sxs-lookup"><span data-stu-id="7d30b-104">Graphical user interfaces use some basic concepts that are well known to most computer users.</span></span> <span data-ttu-id="7d30b-105">ユーザーはタスクを実行する際、なじみのあるインターフェイスに依存します。</span><span class="sxs-lookup"><span data-stu-id="7d30b-105">Users rely on the familiarity of those interfaces to accomplish tasks.</span></span> <span data-ttu-id="7d30b-106">オペレーティング システムは閲覧可能な項目のグラフィック表示をユーザーに提示しますが、これには通常、特定の機能にアクセスするためのドロップダウン メニューと、コンテキスト特有の機能にアクセスするためのコンテキスト メニューが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d30b-106">Operating systems present users with a graphical representation of items that can be browsed, usually with drop-down menus for accessing specific functionality and context menus for accessing context-specific functionality.</span></span>

<span data-ttu-id="7d30b-107">Windows PowerShell などのコマンド ライン インターフェイス (CLI) にはユーザーを支援するメニューやグラフィカル システムがないため、情報を表示するための別のアプローチを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d30b-107">A command-line interface (CLI), such as Windows PowerShell, must use a different approach to expose information, because it does not have menus or graphical systems to help the user.</span></span> <span data-ttu-id="7d30b-108">コマンドを使用するには、その名前を把握しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d30b-108">You need to know command names before you can use them.</span></span> <span data-ttu-id="7d30b-109">GUI 環境の機能と等価の複雑なコマンドを入力することはできますが、一般的なコマンドとコマンド パラメーターをよく理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d30b-109">Although you can type complex commands that are equivalent to the features in a GUI environment, you must become familiar with commonly-used commands and command parameters.</span></span>

<span data-ttu-id="7d30b-110">ほとんどの CLI には、インターフェイスについてユーザーが学ぶのに役立つパターンがありません。</span><span class="sxs-lookup"><span data-stu-id="7d30b-110">Most CLIs do not have patterns that can help the user to learn the interface.</span></span> <span data-ttu-id="7d30b-111">CLI は最初のオペレーティング システム シェルだったため、多くのコマンド名とパラメーター名は任意に選ばれました。</span><span class="sxs-lookup"><span data-stu-id="7d30b-111">Because CLIs were the first operating system shells, many command names and parameter names were selected arbitrarily.</span></span> <span data-ttu-id="7d30b-112">一般に、明快さよりも簡潔さを旨としてコマンド名が選ばれました。</span><span class="sxs-lookup"><span data-stu-id="7d30b-112">Terse command names were generally chosen over clear ones.</span></span> <span data-ttu-id="7d30b-113">大部分の CLI にはヘルプ システムとコマンド設計標準が組み込まれていますが、一般に最初期のコマンドとの互換性を保つ設計になっているため、コマンド セットは今も数十年前の決定によって形作られているのが現状です。</span><span class="sxs-lookup"><span data-stu-id="7d30b-113">Although help systems and command design standards are integrated into most CLIs, they have been generally designed for compatibility with the earliest commands, so the command set is still shaped by decisions made decades ago.</span></span>

<span data-ttu-id="7d30b-114">Windows PowerShell の設計は、ユーザーが持つ CLI の歴史的知識を生かすものです。</span><span class="sxs-lookup"><span data-stu-id="7d30b-114">Windows PowerShell was designed to take advantage of a user's historic knowledge of CLIs.</span></span> <span data-ttu-id="7d30b-115">この章では、Windows PowerShell について素早く学習するために使用できる基本的なツールと概念を説明します。</span><span class="sxs-lookup"><span data-stu-id="7d30b-115">In this chapter, we will talk about some basic tools and concepts that you can use to learn Windows PowerShell quickly.</span></span> <span data-ttu-id="7d30b-116">具体的な内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7d30b-116">They include:</span></span>

- <span data-ttu-id="7d30b-117">Get-Command の使用</span><span class="sxs-lookup"><span data-stu-id="7d30b-117">Using Get-Command</span></span>

- <span data-ttu-id="7d30b-118">Cmd.exe および UNIX コマンドの使用</span><span class="sxs-lookup"><span data-stu-id="7d30b-118">Using Cmd.exe and UNIX commands</span></span>

- <span data-ttu-id="7d30b-119">外部コマンドの使用</span><span class="sxs-lookup"><span data-stu-id="7d30b-119">Using External Commands</span></span>

- <span data-ttu-id="7d30b-120">タブ補完の使用</span><span class="sxs-lookup"><span data-stu-id="7d30b-120">Using Tab-Completion</span></span>

- <span data-ttu-id="7d30b-121">Get-Help の使用</span><span class="sxs-lookup"><span data-stu-id="7d30b-121">Using Get-Help</span></span>

