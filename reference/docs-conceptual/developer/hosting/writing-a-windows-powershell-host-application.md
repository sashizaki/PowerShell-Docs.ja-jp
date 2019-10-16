---
title: Windows PowerShell ホストアプリケーションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81aeafad-dbc3-4712-8bb9-e6a417be260f
caps.latest.revision: 15
ms.openlocfilehash: b44708b3bbcb974a6178323dff2302b7da121af6
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367281"
---
# <a name="writing-a-windows-powershell-host-application"></a><span data-ttu-id="175a3-102">Windows PowerShell ホスト アプリケーションを記述する</span><span class="sxs-lookup"><span data-stu-id="175a3-102">Writing a Windows PowerShell Host Application</span></span>

<span data-ttu-id="175a3-103">アプリケーションで Windows PowerShell をホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="175a3-103">You can host Windows PowerShell in your application.</span></span> <span data-ttu-id="175a3-104">ホストアプリケーションでは、コマンドが実行される実行空間を定義し、ローカルまたはリモートコンピューターでセッションを開いて、アプリケーションのニーズに基づいて、同期的または非同期的にコマンドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="175a3-104">The host application can define the runspace where commands are run, open sessions on a local or remote computer, and invoke the commands either synchronously or asynchronously based on the needs of the application.</span></span>

<span data-ttu-id="175a3-105">次のトピックでは、Windows PowerShell をホストするアプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="175a3-105">The following topics explain how to create an application that hosts Windows PowerShell.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="175a3-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="175a3-106">In This Section</span></span>

<span data-ttu-id="175a3-107">[Windows PowerShell ホストのクイックスタート](./windows-powershell-host-quickstart.md)ホストアプリケーションの作成を開始するための手順とコードサンプルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="175a3-107">[Windows PowerShell Host Quickstart](./windows-powershell-host-quickstart.md) Provides instructions and code samples to get you started creating host applications.</span></span>

<span data-ttu-id="175a3-108">実行[空間の作成](./creating-runspaces.md)ホストアプリケーションで Windows PowerShell コマンドを実行するための実行空間を作成する方法について説明する一連のトピックです。</span><span class="sxs-lookup"><span data-stu-id="175a3-108">[Creating Runspaces](./creating-runspaces.md) A set of topics that explain how to create runspaces to run Windows PowerShell command in a host application.</span></span>

<span data-ttu-id="175a3-109">[コマンドの追加と呼び出し](./adding-and-invoking-commands.md)ホストアプリケーションでコマンドパイプラインを作成して実行する方法について説明します。「」をご利用ください。</span><span class="sxs-lookup"><span data-stu-id="175a3-109">[Adding and invoking commands](./adding-and-invoking-commands.md) Explains how to create and run a command pipeline in your host application..</span></span>

<span data-ttu-id="175a3-110">[リモート実行空間の作成](./creating-remote-runspaces.md)実行空間をリモートコンピューターに接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="175a3-110">[Creating remote runspaces](./creating-remote-runspaces.md) Explains how to connect a runspace to a remote computer.</span></span>

<span data-ttu-id="175a3-111">[カスタムユーザーインターフェイスの作成](./creating-a-custom-user-interface.md)カスタムユーザーインターフェイスについて説明し、例へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="175a3-111">[Creating a custom user interface](./creating-a-custom-user-interface.md) Introduces custom user interfaces and provides links to examples.</span></span>

<span data-ttu-id="175a3-112">[ホストアプリケーションのサンプル](./host-application-samples.md)このセクションには、完全なホストアプリケーションのサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="175a3-112">[Host Application Samples](./host-application-samples.md) This section includes samples of complete host applications.</span></span>

## <a name="see-also"></a><span data-ttu-id="175a3-113">参照</span><span class="sxs-lookup"><span data-stu-id="175a3-113">See Also</span></span>

[<span data-ttu-id="175a3-114">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="175a3-114">Windows PowerShell</span></span>](https://msdn.microsoft.com/en-us/b41a2af3-aec1-402d-8e18-c2c26be461ff)
