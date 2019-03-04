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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860498"
---
# <a name="modules-and-snap-ins"></a><span data-ttu-id="cdabd-102">モジュールとスナップイン</span><span class="sxs-lookup"><span data-stu-id="cdabd-102">Modules and Snap-ins</span></span>

<span data-ttu-id="cdabd-103">コマンドレットは、(Windows PowerShell 2.0 で導入) のモジュールまたはスナップインを使用してセッションに追加できます。コマンドレットは、ホスト アプリケーションによって、またはコマンドラインで対話的にプログラムで実行することができます、セッションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="cdabd-103">Cmdlets can be added to a session using modules (introduced by Windows PowerShell 2.0) or snap-ins. Once the cmdlet is added to the session it can be run programmatically by a host application or interactively at the command line.</span></span>

<span data-ttu-id="cdabd-104">コマンドレットを次の理由でセッションに追加する配信方法としては、モジュールを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cdabd-104">We recommend that you use modules as the delivery method for adding cmdlets to a session for the following reasons:</span></span>

- <span data-ttu-id="cdabd-105">モジュールを使用すると、コマンドレットを追加するには、アセンブリの読み込み、コマンドレットが定義されています。</span><span class="sxs-lookup"><span data-stu-id="cdabd-105">Modules allow you to add cmdlets by loading the assembly where the cmdlet is defined.</span></span> <span data-ttu-id="cdabd-106">スナップイン クラスを実装する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cdabd-106">There is no need to implement a snap-in class.</span></span>

- <span data-ttu-id="cdabd-107">モジュールを使用して、変数、関数、スクリプト、型と書式設定ファイル、および詳細などの他のリソースを追加できます。</span><span class="sxs-lookup"><span data-stu-id="cdabd-107">Modules allow you to add other resources, such as variables, functions, scripts, types and formatting files, and more.</span></span>

- <span data-ttu-id="cdabd-108">スナップインは、コマンドレットとプロバイダーをセッションに追加する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="cdabd-108">Snap-ins can be used only to add cmdlets and providers to the session.</span></span>

## <a name="see-also"></a><span data-ttu-id="cdabd-109">参照</span><span class="sxs-lookup"><span data-stu-id="cdabd-109">See Also</span></span>

[<span data-ttu-id="cdabd-110">Windows PowerShell モジュールの記述</span><span class="sxs-lookup"><span data-stu-id="cdabd-110">Writing a Windows PowerShell Module</span></span>](../module/writing-a-windows-powershell-module.md)

[<span data-ttu-id="cdabd-111">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="cdabd-111">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
