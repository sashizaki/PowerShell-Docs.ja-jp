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
ms.openlocfilehash: 157cd64e286392f3fd770e1e34542682b1e63625
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365371"
---
# <a name="modules-and-snap-ins"></a><span data-ttu-id="05fc5-102">モジュールとスナップイン</span><span class="sxs-lookup"><span data-stu-id="05fc5-102">Modules and Snap-ins</span></span>

<span data-ttu-id="05fc5-103">コマンドレットは、(Windows PowerShell 2.0 によって導入された) モジュールまたはスナップインを使用してセッションに追加できます。コマンドレットをセッションに追加すると、ホストアプリケーションまたはコマンドラインで対話形式で実行できます。</span><span class="sxs-lookup"><span data-stu-id="05fc5-103">Cmdlets can be added to a session using modules (introduced by Windows PowerShell 2.0) or snap-ins. Once the cmdlet is added to the session it can be run programmatically by a host application or interactively at the command line.</span></span>

<span data-ttu-id="05fc5-104">次の理由により、セッションにコマンドレットを追加するための配信方法としてモジュールを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="05fc5-104">We recommend that you use modules as the delivery method for adding cmdlets to a session for the following reasons:</span></span>

- <span data-ttu-id="05fc5-105">モジュールを使用すると、コマンドレットが定義されているアセンブリを読み込むことによってコマンドレットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="05fc5-105">Modules allow you to add cmdlets by loading the assembly where the cmdlet is defined.</span></span> <span data-ttu-id="05fc5-106">スナップインクラスを実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="05fc5-106">There is no need to implement a snap-in class.</span></span>

- <span data-ttu-id="05fc5-107">モジュールを使用すると、変数、関数、スクリプト、型、書式設定ファイルなどの他のリソースを追加できます。</span><span class="sxs-lookup"><span data-stu-id="05fc5-107">Modules allow you to add other resources, such as variables, functions, scripts, types and formatting files, and more.</span></span>

- <span data-ttu-id="05fc5-108">スナップインは、セッションにコマンドレットとプロバイダーを追加するためにのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="05fc5-108">Snap-ins can be used only to add cmdlets and providers to the session.</span></span>

## <a name="see-also"></a><span data-ttu-id="05fc5-109">参照</span><span class="sxs-lookup"><span data-stu-id="05fc5-109">See Also</span></span>

[<span data-ttu-id="05fc5-110">Windows PowerShell モジュールの作成</span><span class="sxs-lookup"><span data-stu-id="05fc5-110">Writing a Windows PowerShell Module</span></span>](../module/writing-a-windows-powershell-module.md)

[<span data-ttu-id="05fc5-111">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="05fc5-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
