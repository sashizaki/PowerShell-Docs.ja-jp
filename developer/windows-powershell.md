---
title: Windows PowerShell SDK
ms.date: 09/13/2016
ms.topic: article
ms.openlocfilehash: 7627ab336ddc40ab47c3017eed77c78bbdac4e7f
ms.sourcegitcommit: bc42c9166857147a1ecf9924b718d4a48eb901e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2019
ms.locfileid: "66470815"
---
# <a name="windows-powershell"></a><span data-ttu-id="f5608-102">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5608-102">Windows PowerShell</span></span>

<span data-ttu-id="f5608-103">更新:2013 年 7 月 8 日</span><span class="sxs-lookup"><span data-stu-id="f5608-103">Updated: July 8, 2013</span></span>

<span data-ttu-id="f5608-104">Windows PowerShell® は、システム管理に重点を置いて設計されたタスクベースのコマンド ライン シェルおよびスクリプト言語です。</span><span class="sxs-lookup"><span data-stu-id="f5608-104">Windows PowerShell® is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="f5608-105">.NET Framework 上に構築された Windows PowerShell® はにより、IT プロフェッショナルおよびパワー ユーザーを制御し、Windows オペレーティング システムおよび Windows で実行されるアプリケーションの管理を自動化します。</span><span class="sxs-lookup"><span data-stu-id="f5608-105">Built on the .NET Framework, Windows PowerShell® helps IT professionals and power users control and automate the administration of the Windows operating system and applications that run on Windows.</span></span>

<span data-ttu-id="f5608-106">ここで発行されるドキュメントは、コマンドレット、プロバイダー、および Windows PowerShell で提供される Api に関するリファレンス情報を必要とするホスト アプリケーションの開発者を主に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="f5608-106">The documents published here are written primarily for cmdlet, provider, and host application developers who require reference information about the APIs provided by Windows PowerShell.</span></span>
<span data-ttu-id="f5608-107">ただし、システム管理者は、便利なドキュメントはこれらによって提供される情報を検索も可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f5608-107">However, system administrators might also find the information provided by these documents useful.</span></span>

<span data-ttu-id="f5608-108">Windows PowerShell の使用を開始するための基本的な情報、Windows PowerShell の概要を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5608-108">For the basic information needed to start using Windows PowerShell, see Getting Started with Windows PowerShell .</span></span>

## <a name="windows-powershell-documents-on-msdn"></a><span data-ttu-id="f5608-109">MSDN の Windows PowerShell のドキュメント</span><span class="sxs-lookup"><span data-stu-id="f5608-109">Windows PowerShell Documents on MSDN</span></span>

- <span data-ttu-id="f5608-110">[Windows PowerShell SDK のインストール](./installing-the-windows-powershell-sdk.md)Windows PowerShell SDK をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f5608-110">[Installing the Windows PowerShell SDK](./installing-the-windows-powershell-sdk.md) Provides information about how to install the Windows PowerShell SDK.</span></span>

- <span data-ttu-id="f5608-111">[Windows PowerShell モジュールの記述](./module/writing-a-windows-powershell-module.md)管理者、スクリプトの開発者、およびパッケージ化して、Windows PowerShell のソリューションを配布する必要があるコマンドレットの開発者情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f5608-111">[Writing a Windows PowerShell Module](./module/writing-a-windows-powershell-module.md) Provides information for administrators, script developers, and cmdlet developers who need to package and distribute their Windows PowerShell solutions.</span></span>

- <span data-ttu-id="f5608-112">[Windows PowerShell コマンドレットの記述](./cmdlet/writing-a-windows-powershell-cmdlet.md)設計と実装のコマンドレットの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f5608-112">[Writing a Windows PowerShell Cmdlet](./cmdlet/writing-a-windows-powershell-cmdlet.md) Provides information for designing and implementing cmdlets.</span></span>

- <span data-ttu-id="f5608-113">[Windows PowerShell プロバイダーの記述](./provider/writing-a-windows-powershell-provider.md)設計と実装の Windows PowerShell プロバイダーの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f5608-113">[Writing a Windows PowerShell Provider](./provider/writing-a-windows-powershell-provider.md) Provides information for designing and implementing Windows PowerShell providers.</span></span> <span data-ttu-id="f5608-114">Windows PowerShell プロバイダーの連携方法を理解するのに役立ち、設計または独自のプロバイダーの書き込みを開始するために使用できるサンプル コードを提供します。</span><span class="sxs-lookup"><span data-stu-id="f5608-114">It will help you understand how Windows PowerShell providers work, and it provides sample code that you can use to start designing or writing your own providers.</span></span>

- <span data-ttu-id="f5608-115">[Windows PowerShell ホスト アプリケーションを記述して](./hosting/writing-a-windows-powershell-host-application.md)それらを実装している開発者とホスト アプリケーションを設計する場合に、プログラム マネージャーによって使用できる情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f5608-115">[Writing a Windows PowerShell Host Application](./hosting/writing-a-windows-powershell-host-application.md) Provides information that can be used by program managers who are designing host applications and by developers who are implementing them.</span></span> <span data-ttu-id="f5608-116">ホスト アプリケーションでは、コマンドが、ローカルまたはリモート コンピューターでセッションを開き、実行を実行空間を定義、アプリケーションのニーズに応じて同期または非同期ベースのいずれかのコマンドを呼び出すできます。</span><span class="sxs-lookup"><span data-stu-id="f5608-116">The host application can, define the runspace where commands are run, open sessions on a local or remote computer, and invoke the commands either synchronously or asynchronously based on the needs of the application.</span></span>

- <span data-ttu-id="f5608-117">[PowerShell の書式設定ファイルの書き込み](./format/writing-a-powershell-formatting-file.md)コマンド (コマンドレット、関数、およびスクリプト) によって返されるオブジェクトの表示形式を制御する、書式設定ファイルを作成するための情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="f5608-117">[Writing a PowerShell Formatting File](./format/writing-a-powershell-formatting-file.md) Provides information for the authoring of formatting files, which control the display format for the objects that are returned by commands (cmdlets, functions, and scripts).</span></span>

- <span data-ttu-id="f5608-118">[Windows PowerShell リファレンス](./windows-powershell-reference.md)コマンドレット、プロバイダー、およびアプリケーションのホストを作成するための Api とその他のサポートする Api のリファレンス コンテンツを提供します。</span><span class="sxs-lookup"><span data-stu-id="f5608-118">[Windows PowerShell Reference](./windows-powershell-reference.md) Provides reference content for the APIs used in writing cmdlets, providers, and host applications, as well as other supporting APIs.</span></span>
