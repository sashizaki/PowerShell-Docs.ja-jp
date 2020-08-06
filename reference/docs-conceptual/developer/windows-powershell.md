---
title: Windows PowerShell SDK
ms.date: 09/13/2016
ms.openlocfilehash: 0501f511499bc5de35fad5d7798f0d16e2d3b36b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786664"
---
# <a name="windows-powershell"></a><span data-ttu-id="d09b7-102">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d09b7-102">Windows PowerShell</span></span>

<span data-ttu-id="d09b7-103">更新日: 2013 年7月8日</span><span class="sxs-lookup"><span data-stu-id="d09b7-103">Updated: July 8, 2013</span></span>

<span data-ttu-id="d09b7-104">Windows PowerShell® は、システム管理に重点を置いて設計されたタスクベースのコマンド ライン シェルおよびスクリプト言語です。</span><span class="sxs-lookup"><span data-stu-id="d09b7-104">Windows PowerShell® is a task-based command-line shell and scripting language designed especially for system administration.</span></span> <span data-ttu-id="d09b7-105">Windows PowerShell®は .NET Framework 上に構築されており、windows オペレーティングシステムと windows 上で実行されるアプリケーションの管理を IT プロフェッショナルとパワーユーザーが制御し、自動化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d09b7-105">Built on the .NET Framework, Windows PowerShell® helps IT professionals and power users control and automate the administration of the Windows operating system and applications that run on Windows.</span></span>

<span data-ttu-id="d09b7-106">ここで公開されているドキュメントは、主に、Windows PowerShell によって提供される Api に関する参照情報を必要とするコマンドレット、プロバイダー、およびホストアプリケーション開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="d09b7-106">The documents published here are written primarily for cmdlet, provider, and host application developers who require reference information about the APIs provided by Windows PowerShell.</span></span>
<span data-ttu-id="d09b7-107">ただし、システム管理者は、これらのドキュメントで提供されている情報を見つけられる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d09b7-107">However, system administrators might also find the information provided by these documents useful.</span></span>

<span data-ttu-id="d09b7-108">Windows PowerShell の使用を開始するために必要な基本的な情報については、「Windows PowerShell を使用したはじめに」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d09b7-108">For the basic information needed to start using Windows PowerShell, see Getting Started with Windows PowerShell .</span></span>

## <a name="windows-powershell-documents-on-msdn"></a><span data-ttu-id="d09b7-109">MSDN の Windows PowerShell ドキュメント</span><span class="sxs-lookup"><span data-stu-id="d09b7-109">Windows PowerShell Documents on MSDN</span></span>

- <span data-ttu-id="d09b7-110">[Windows POWERSHELL SDK のインストール](./installing-the-windows-powershell-sdk.md)Windows PowerShell SDK をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d09b7-110">[Installing the Windows PowerShell SDK](./installing-the-windows-powershell-sdk.md) Provides information about how to install the Windows PowerShell SDK.</span></span>

- <span data-ttu-id="d09b7-111">[Windows PowerShell モジュールの作成](./module/writing-a-windows-powershell-module.md)Windows PowerShell ソリューションをパッケージ化して配布する必要がある管理者、スクリプト開発者、およびコマンドレットの開発者向けの情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d09b7-111">[Writing a Windows PowerShell Module](./module/writing-a-windows-powershell-module.md) Provides information for administrators, script developers, and cmdlet developers who need to package and distribute their Windows PowerShell solutions.</span></span>

- <span data-ttu-id="d09b7-112">[Windows PowerShell コマンドレットの記述](./cmdlet/writing-a-windows-powershell-cmdlet.md)コマンドレットの設計と実装に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d09b7-112">[Writing a Windows PowerShell Cmdlet](./cmdlet/writing-a-windows-powershell-cmdlet.md) Provides information for designing and implementing cmdlets.</span></span>

- <span data-ttu-id="d09b7-113">[Windows PowerShell プロバイダーの作成](./provider/writing-a-windows-powershell-provider.md)Windows PowerShell プロバイダーの設計と実装に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d09b7-113">[Writing a Windows PowerShell Provider](./provider/writing-a-windows-powershell-provider.md) Provides information for designing and implementing Windows PowerShell providers.</span></span> <span data-ttu-id="d09b7-114">これは、Windows PowerShell プロバイダーの動作を理解するのに役立ちます。また、独自のプロバイダーの設計または作成を開始するために使用できるサンプルコードも用意されています。</span><span class="sxs-lookup"><span data-stu-id="d09b7-114">It will help you understand how Windows PowerShell providers work, and it provides sample code that you can use to start designing or writing your own providers.</span></span>

- <span data-ttu-id="d09b7-115">[Windows PowerShell ホストアプリケーションの作成](./hosting/writing-a-windows-powershell-host-application.md)ホストアプリケーションを設計しているプログラムマネージャーおよびそれらを実装する開発者が使用できる情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d09b7-115">[Writing a Windows PowerShell Host Application](./hosting/writing-a-windows-powershell-host-application.md) Provides information that can be used by program managers who are designing host applications and by developers who are implementing them.</span></span> <span data-ttu-id="d09b7-116">ホストアプリケーションでは、コマンドが実行される実行空間を定義し、ローカルまたはリモートコンピューターでセッションを開いて、アプリケーションのニーズに基づいて、同期的または非同期的にコマンドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="d09b7-116">The host application can, define the runspace where commands are run, open sessions on a local or remote computer, and invoke the commands either synchronously or asynchronously based on the needs of the application.</span></span>

- <span data-ttu-id="d09b7-117">[PowerShell フォーマットファイルの作成](./format/writing-a-powershell-formatting-file.md)コマンド (コマンドレット、関数、およびスクリプト) によって返されるオブジェクトの表示形式を制御する、書式設定ファイルの作成に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="d09b7-117">[Writing a PowerShell Formatting File](./format/writing-a-powershell-formatting-file.md) Provides information for the authoring of formatting files, which control the display format for the objects that are returned by commands (cmdlets, functions, and scripts).</span></span>

- <span data-ttu-id="d09b7-118">[Windows PowerShell リファレンス](./windows-powershell-reference.md)コマンドレット、プロバイダー、およびホストアプリケーションの作成に使用される Api のリファレンスコンテンツと、その他のサポート Api について説明します。</span><span class="sxs-lookup"><span data-stu-id="d09b7-118">[Windows PowerShell Reference](./windows-powershell-reference.md) Provides reference content for the APIs used in writing cmdlets, providers, and host applications, as well as other supporting APIs.</span></span>
