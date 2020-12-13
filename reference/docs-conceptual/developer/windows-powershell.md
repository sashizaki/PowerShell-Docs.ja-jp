---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell SDK
description: Windows PowerShell SDK
ms.openlocfilehash: 751ccb02741db0ea63df1768dec4a19c5fa9ce92
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "94390203"
---
# <a name="windows-powershell"></a><span data-ttu-id="c8406-103">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c8406-103">Windows PowerShell</span></span>

<span data-ttu-id="c8406-104">更新日: 2013 年7月8日</span><span class="sxs-lookup"><span data-stu-id="c8406-104">Updated: July 8, 2013</span></span>

<span data-ttu-id="c8406-105">Windows PowerShell &reg; は、特にシステム管理用に設計された、タスクベースのコマンドラインシェルおよびスクリプト言語です。</span><span class="sxs-lookup"><span data-stu-id="c8406-105">Windows PowerShell&reg; is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="c8406-106">.NET Framework 上に構築された Windows PowerShell は、 &reg; IT 技術者およびパワーユーザーが windows オペレーティングシステムと windows 上で実行されるアプリケーションの管理を制御し、自動化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c8406-106">Built on the .NET Framework, Windows PowerShell&reg; helps IT professionals and power users control and automate the administration of the Windows operating system and applications that run on Windows.</span></span>

<span data-ttu-id="c8406-107">ここで公開されているドキュメントは、主に、Windows PowerShell によって提供される Api に関する参照情報を必要とするコマンドレット、プロバイダー、およびホストアプリケーション開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="c8406-107">The documents published here are written primarily for cmdlet, provider, and host application developers who require reference information about the APIs provided by Windows PowerShell.</span></span>
<span data-ttu-id="c8406-108">ただし、システム管理者は、これらのドキュメントで提供されている情報を見つけられる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="c8406-108">However, system administrators might also find the information provided by these documents useful.</span></span>

<span data-ttu-id="c8406-109">Windows PowerShell の使用を開始するために必要な基本的な情報については、「Windows PowerShell を使用したはじめに」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8406-109">For the basic information needed to start using Windows PowerShell, see Getting Started with Windows PowerShell .</span></span>

## <a name="windows-powershell-documents"></a><span data-ttu-id="c8406-110">Windows PowerShell ドキュメント</span><span class="sxs-lookup"><span data-stu-id="c8406-110">Windows PowerShell Documents</span></span>

- <span data-ttu-id="c8406-111">[Windows POWERSHELL SDK のインストール](./installing-the-windows-powershell-sdk.md) Windows PowerShell SDK をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8406-111">[Installing the Windows PowerShell SDK](./installing-the-windows-powershell-sdk.md) Provides information about how to install the Windows PowerShell SDK.</span></span>

- <span data-ttu-id="c8406-112">[Windows PowerShell モジュールの作成](./module/writing-a-windows-powershell-module.md) Windows PowerShell ソリューションをパッケージ化して配布する必要がある管理者、スクリプト開発者、およびコマンドレットの開発者向けの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c8406-112">[Writing a Windows PowerShell Module](./module/writing-a-windows-powershell-module.md) Provides information for administrators, script developers, and cmdlet developers who need to package and distribute their Windows PowerShell solutions.</span></span>

- <span data-ttu-id="c8406-113">[Windows PowerShell コマンドレットの記述](./cmdlet/writing-a-windows-powershell-cmdlet.md) コマンドレットの設計と実装に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c8406-113">[Writing a Windows PowerShell Cmdlet](./cmdlet/writing-a-windows-powershell-cmdlet.md) Provides information for designing and implementing cmdlets.</span></span>

- <span data-ttu-id="c8406-114">[Windows PowerShell プロバイダーの作成](./provider/writing-a-windows-powershell-provider.md) Windows PowerShell プロバイダーの設計と実装に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c8406-114">[Writing a Windows PowerShell Provider](./provider/writing-a-windows-powershell-provider.md) Provides information for designing and implementing Windows PowerShell providers.</span></span> <span data-ttu-id="c8406-115">これは、Windows PowerShell プロバイダーの動作を理解するのに役立ちます。また、独自のプロバイダーの設計または作成を開始するために使用できるサンプルコードも用意されています。</span><span class="sxs-lookup"><span data-stu-id="c8406-115">It will help you understand how Windows PowerShell providers work, and it provides sample code that you can use to start designing or writing your own providers.</span></span>

- <span data-ttu-id="c8406-116">[Windows PowerShell ホストアプリケーションの作成](./hosting/writing-a-windows-powershell-host-application.md) ホストアプリケーションを設計しているプログラムマネージャーおよびそれらを実装する開発者が使用できる情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c8406-116">[Writing a Windows PowerShell Host Application](./hosting/writing-a-windows-powershell-host-application.md) Provides information that can be used by program managers who are designing host applications and by developers who are implementing them.</span></span> <span data-ttu-id="c8406-117">ホストアプリケーションでは、コマンドが実行される実行空間を定義し、ローカルまたはリモートコンピューターでセッションを開いて、アプリケーションのニーズに基づいて、同期的または非同期的にコマンドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="c8406-117">The host application can, define the runspace where commands are run, open sessions on a local or remote computer, and invoke the commands either synchronously or asynchronously based on the needs of the application.</span></span>

- <span data-ttu-id="c8406-118">[PowerShell フォーマットファイルの作成](./format/writing-a-powershell-formatting-file.md) コマンド (コマンドレット、関数、およびスクリプト) によって返されるオブジェクトの表示形式を制御する、書式設定ファイルの作成に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c8406-118">[Writing a PowerShell Formatting File](./format/writing-a-powershell-formatting-file.md) Provides information for the authoring of formatting files, which control the display format for the objects that are returned by commands (cmdlets, functions, and scripts).</span></span>

- <span data-ttu-id="c8406-119">[Windows PowerShell リファレンス](./windows-powershell-reference.md) コマンドレット、プロバイダー、およびホストアプリケーションの作成に使用される Api のリファレンスコンテンツと、その他のサポート Api について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8406-119">[Windows PowerShell Reference](./windows-powershell-reference.md) Provides reference content for the APIs used in writing cmdlets, providers, and host applications, as well as other supporting APIs.</span></span>
