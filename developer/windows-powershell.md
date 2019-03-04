---
title: Windows PowerShell SDK
ms.date: 09/13/2016
ms.topic: article
ms.openlocfilehash: 600d43874d9eda04d556a0ece198026dde9174c3
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855358"
---
# <a name="windows-powershell"></a><span data-ttu-id="24e2b-102">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="24e2b-102">Windows PowerShell</span></span>

<span data-ttu-id="24e2b-103">更新:2013 年 7 月 8 日</span><span class="sxs-lookup"><span data-stu-id="24e2b-103">Updated: July 8, 2013</span></span>

<span data-ttu-id="24e2b-104">Windows PowerShell® は、システム管理に重点を置いて設計されたタスクベースのコマンド ライン シェルおよびスクリプト言語です。</span><span class="sxs-lookup"><span data-stu-id="24e2b-104">Windows PowerShell® is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="24e2b-105">.NET Framework 上に構築された Windows PowerShell® はにより、IT プロフェッショナルおよびパワー ユーザーを制御し、Windows オペレーティング システムおよび Windows で実行されるアプリケーションの管理を自動化します。</span><span class="sxs-lookup"><span data-stu-id="24e2b-105">Built on the .NET Framework, Windows PowerShell® helps IT professionals and power users control and automate the administration of the Windows operating system and applications that run on Windows.</span></span>

<span data-ttu-id="24e2b-106">ここで発行されるドキュメントは、コマンドレット、プロバイダー、および Windows PowerShell で提供される Api に関するリファレンス情報を必要とするホスト アプリケーションの開発者を主に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="24e2b-106">The documents published here are written primarily for cmdlet, provider, and host application developers who require reference information about the APIs provided by Windows PowerShell.</span></span>
<span data-ttu-id="24e2b-107">ただし、システム管理者は、便利なドキュメントはこれらによって提供される情報を検索も可能性があります。</span><span class="sxs-lookup"><span data-stu-id="24e2b-107">However, system administrators might also find the information provided by these documents useful.</span></span>

<span data-ttu-id="24e2b-108">Windows PowerShell の使用を開始するための基本的な情報、Windows PowerShell の概要を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24e2b-108">For the basic information needed to start using Windows PowerShell, see Getting Started with Windows PowerShell .</span></span>

## <a name="windows-powershell-documents-on-msdn"></a><span data-ttu-id="24e2b-109">MSDN の Windows PowerShell のドキュメント</span><span class="sxs-lookup"><span data-stu-id="24e2b-109">Windows PowerShell Documents on MSDN</span></span>

- <span data-ttu-id="24e2b-110">[Windows PowerShell SDK のインストール](https://msdn.microsoft.com/en-us/library/ff458115.aspx)Windows PowerShell SDK をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="24e2b-110">[Installing the Windows PowerShell SDK](https://msdn.microsoft.com/en-us/library/ff458115.aspx) Provides information about how to install the Windows PowerShell SDK.</span></span>

- <span data-ttu-id="24e2b-111">[Windows PowerShell モジュールの記述](./module/writing-a-windows-powershell-module.md)管理者、スクリプトの開発者、およびパッケージ化して、Windows PowerShell のソリューションを配布する必要があるコマンドレットの開発者情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="24e2b-111">[Writing a Windows PowerShell Module](./module/writing-a-windows-powershell-module.md) Provides information for administrators, script developers, and cmdlet developers who need to package and distribute their Windows PowerShell solutions.</span></span>

- <span data-ttu-id="24e2b-112">[Windows PowerShell コマンドレットの記述](./cmdlet/writing-a-windows-powershell-cmdlet.md)設計と実装のコマンドレットの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="24e2b-112">[Writing a Windows PowerShell Cmdlet](./cmdlet/writing-a-windows-powershell-cmdlet.md) Provides information for designing and implementing cmdlets.</span></span>

- <span data-ttu-id="24e2b-113">[Windows PowerShell プロバイダーの記述](./provider/writing-a-windows-powershell-provider.md)設計と実装の Windows PowerShell プロバイダーの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="24e2b-113">[Writing a Windows PowerShell Provider](./provider/writing-a-windows-powershell-provider.md) Provides information for designing and implementing Windows PowerShell providers.</span></span> <span data-ttu-id="24e2b-114">Windows PowerShell プロバイダーの連携方法を理解するのに役立ち、設計または独自のプロバイダーの書き込みを開始するために使用できるサンプル コードを提供します。</span><span class="sxs-lookup"><span data-stu-id="24e2b-114">It will help you understand how Windows PowerShell providers work, and it provides sample code that you can use to start designing or writing your own providers.</span></span>

- <span data-ttu-id="24e2b-115">[Windows PowerShell ホスト アプリケーションを記述して](./hosting/writing-a-windows-powershell-host-application.md)それらを実装している開発者とホスト アプリケーションを設計する場合に、プログラム マネージャーによって使用できる情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="24e2b-115">[Writing a Windows PowerShell Host Application](./hosting/writing-a-windows-powershell-host-application.md) Provides information that can be used by program managers who are designing host applications and by developers who are implementing them.</span></span> <span data-ttu-id="24e2b-116">ホスト アプリケーションでは、コマンドが、ローカルまたはリモート コンピューターでセッションを開き、実行を実行空間を定義、アプリケーションのニーズに応じて同期または非同期ベースのいずれかのコマンドを呼び出すできます。</span><span class="sxs-lookup"><span data-stu-id="24e2b-116">The host application can, define the runspace where commands are run, open sessions on a local or remote computer, and invoke the commands either synchronously or asynchronously based on the needs of the application.</span></span>

- <span data-ttu-id="24e2b-117">[PowerShell の書式設定ファイルの書き込み](./format/writing-a-powershell-formatting-file.md)コマンド (コマンドレット、関数、およびスクリプト) によって返されるオブジェクトの表示形式を制御する、書式設定ファイルを作成するための情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="24e2b-117">[Writing a PowerShell Formatting File](./format/writing-a-powershell-formatting-file.md) Provides information for the authoring of formatting files, which control the display format for the objects that are returned by commands (cmdlets, functions, and scripts).</span></span>

- <span data-ttu-id="24e2b-118">[Windows PowerShell リファレンス](./windows-powershell-reference.md)コマンドレット、プロバイダー、およびアプリケーションのホストを作成するための Api とその他のサポートする Api のリファレンス コンテンツを提供します。</span><span class="sxs-lookup"><span data-stu-id="24e2b-118">[Windows PowerShell Reference](./windows-powershell-reference.md) Provides reference content for the APIs used in writing cmdlets, providers, and host applications, as well as other supporting APIs.</span></span>
