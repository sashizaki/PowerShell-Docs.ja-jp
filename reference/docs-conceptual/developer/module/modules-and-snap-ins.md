---
title: モジュールとスナップイン |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d342f91-23e0-467f-8de2-f9657d820693
caps.latest.revision: 6
ms.openlocfilehash: b3d8209ea7e3e8353e73ebce1531991ec9519c74
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "83811661"
---
# <a name="modules-and-snap-ins"></a><span data-ttu-id="2fafb-102">モジュールとスナップイン</span><span class="sxs-lookup"><span data-stu-id="2fafb-102">Modules and Snap-ins</span></span>

<span data-ttu-id="2fafb-103">コマンドレットは、(Windows PowerShell 2.0 によって導入された) モジュールまたはスナップインを使用してセッションに追加できます。コマンドレットをセッションに追加すると、ホストアプリケーションまたはコマンドラインで対話形式で実行できます。</span><span class="sxs-lookup"><span data-stu-id="2fafb-103">Cmdlets can be added to a session using modules (introduced by Windows PowerShell 2.0) or snap-ins. Once the cmdlet is added to the session it can be run programmatically by a host application or interactively at the command line.</span></span>

<span data-ttu-id="2fafb-104">次の理由により、セッションにコマンドレットを追加するための配信方法としてモジュールを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2fafb-104">We recommend that you use modules as the delivery method for adding cmdlets to a session for the following reasons:</span></span>

- <span data-ttu-id="2fafb-105">モジュールを使用すると、コマンドレットが定義されているアセンブリを読み込むことによってコマンドレットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="2fafb-105">Modules allow you to add cmdlets by loading the assembly where the cmdlet is defined.</span></span> <span data-ttu-id="2fafb-106">スナップインクラスを実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2fafb-106">There is no need to implement a snap-in class.</span></span>

- <span data-ttu-id="2fafb-107">モジュールを使用すると、変数、関数、スクリプト、型、書式設定ファイルなどの他のリソースを追加できます。</span><span class="sxs-lookup"><span data-stu-id="2fafb-107">Modules allow you to add other resources, such as variables, functions, scripts, types and formatting files, and more.</span></span>

- <span data-ttu-id="2fafb-108">スナップインは、セッションにコマンドレットとプロバイダーを追加するためにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="2fafb-108">Snap-ins can be used only to add cmdlets and providers to the session.</span></span>

## <a name="see-also"></a><span data-ttu-id="2fafb-109">参照</span><span class="sxs-lookup"><span data-stu-id="2fafb-109">See Also</span></span>

[<span data-ttu-id="2fafb-110">Windows PowerShell モジュールを記述する</span><span class="sxs-lookup"><span data-stu-id="2fafb-110">Writing a Windows PowerShell Module</span></span>](writing-a-windows-powershell-module.md)

[<span data-ttu-id="2fafb-111">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="2fafb-111">Writing a Windows PowerShell Cmdlet</span></span>](../cmdlet/cmdlet-overview.md)
