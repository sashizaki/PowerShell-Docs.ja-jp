---
ms.date: 09/13/2016
ms.topic: reference
title: モジュールとスナップイン
description: モジュールとスナップイン
ms.openlocfilehash: de4ff1de9a29b78d7783fe7ed0265f5516db1fb4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92658682"
---
# <a name="modules-and-snap-ins"></a><span data-ttu-id="28fca-103">モジュールとスナップイン</span><span class="sxs-lookup"><span data-stu-id="28fca-103">Modules and Snap-ins</span></span>

<span data-ttu-id="28fca-104">コマンドレットは、(Windows PowerShell 2.0 によって導入された) モジュールまたはスナップインを使用してセッションに追加できます。コマンドレットをセッションに追加すると、ホストアプリケーションまたはコマンドラインで対話形式で実行できます。</span><span class="sxs-lookup"><span data-stu-id="28fca-104">Cmdlets can be added to a session using modules (introduced by Windows PowerShell 2.0) or snap-ins. Once the cmdlet is added to the session it can be run programmatically by a host application or interactively at the command line.</span></span>

<span data-ttu-id="28fca-105">次の理由により、セッションにコマンドレットを追加するための配信方法としてモジュールを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="28fca-105">We recommend that you use modules as the delivery method for adding cmdlets to a session for the following reasons:</span></span>

- <span data-ttu-id="28fca-106">モジュールを使用すると、コマンドレットが定義されているアセンブリを読み込むことによってコマンドレットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="28fca-106">Modules allow you to add cmdlets by loading the assembly where the cmdlet is defined.</span></span> <span data-ttu-id="28fca-107">スナップインクラスを実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="28fca-107">There is no need to implement a snap-in class.</span></span>

- <span data-ttu-id="28fca-108">モジュールを使用すると、変数、関数、スクリプト、型、書式設定ファイルなどの他のリソースを追加できます。</span><span class="sxs-lookup"><span data-stu-id="28fca-108">Modules allow you to add other resources, such as variables, functions, scripts, types and formatting files, and more.</span></span>

- <span data-ttu-id="28fca-109">スナップインは、セッションにコマンドレットとプロバイダーを追加するためにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="28fca-109">Snap-ins can be used only to add cmdlets and providers to the session.</span></span>

## <a name="see-also"></a><span data-ttu-id="28fca-110">参照</span><span class="sxs-lookup"><span data-stu-id="28fca-110">See Also</span></span>

[<span data-ttu-id="28fca-111">Windows PowerShell モジュールを記述する</span><span class="sxs-lookup"><span data-stu-id="28fca-111">Writing a Windows PowerShell Module</span></span>](writing-a-windows-powershell-module.md)

[<span data-ttu-id="28fca-112">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="28fca-112">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/cmdlet-overview.md)
