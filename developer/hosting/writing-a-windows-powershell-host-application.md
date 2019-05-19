---
title: Windows PowerShell ホスト アプリケーションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81aeafad-dbc3-4712-8bb9-e6a417be260f
caps.latest.revision: 15
ms.openlocfilehash: 1aaf936aa22af5c4a4b8c2fa4e6b3bbd2cff6d20
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855081"
---
# <a name="writing-a-windows-powershell-host-application"></a><span data-ttu-id="2d43a-102">Windows PowerShell ホスト アプリケーションを記述する</span><span class="sxs-lookup"><span data-stu-id="2d43a-102">Writing a Windows PowerShell Host Application</span></span>

<span data-ttu-id="2d43a-103">Windows PowerShell は、アプリケーションでホストできます。</span><span class="sxs-lookup"><span data-stu-id="2d43a-103">You can host Windows PowerShell in your application.</span></span> <span data-ttu-id="2d43a-104">ホスト アプリケーションは、コマンドが実行をローカルまたはリモート コンピューターでセッションを開いて、アプリケーションのニーズに応じて同期または非同期ベースのいずれかのコマンドを呼び出すには、実行空間を定義できます。</span><span class="sxs-lookup"><span data-stu-id="2d43a-104">The host application can define the runspace where commands are run, open sessions on a local or remote computer, and invoke the commands either synchronously or asynchronously based on the needs of the application.</span></span>

<span data-ttu-id="2d43a-105">次のトピックでは、Windows PowerShell をホストするアプリケーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-105">The following topics explain how to create an application that hosts Windows PowerShell.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2d43a-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2d43a-106">In This Section</span></span>

<span data-ttu-id="2d43a-107">[Windows PowerShell ホストのクイック スタート](./windows-powershell-host-quickstart.md)について説明し、コード サンプルを取得するホスト アプリケーションの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-107">[Windows PowerShell Host Quickstart](./windows-powershell-host-quickstart.md) Provides instructions and code samples to get you started creating host applications.</span></span>

<span data-ttu-id="2d43a-108">[実行空間を作成する](./creating-runspaces.md)ホスト アプリケーションでの Windows PowerShell コマンドを実行する実行空間を作成する方法を説明するトピックのセット。</span><span class="sxs-lookup"><span data-stu-id="2d43a-108">[Creating Runspaces](./creating-runspaces.md) A set of topics that explain how to create runspaces to run Windows PowerShell command in a host application.</span></span>

<span data-ttu-id="2d43a-109">[追加して、コマンドを起動](./adding-and-invoking-commands.md)を作成して、ホスト アプリケーションでのコマンド パイプラインの実行方法について説明します.</span><span class="sxs-lookup"><span data-stu-id="2d43a-109">[Adding and invoking commands](./adding-and-invoking-commands.md) Explains how to create and run a command pipeline in your host application..</span></span>

<span data-ttu-id="2d43a-110">[リモート実行空間を作成する](./creating-remote-runspaces.md)実行空間をリモート コンピューターに接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-110">[Creating remote runspaces](./creating-remote-runspaces.md) Explains how to connect a runspace to a remote computer.</span></span>

<span data-ttu-id="2d43a-111">[カスタム ユーザー インターフェイスを作成する](./creating-a-custom-user-interface.md)導入のカスタム ユーザー インターフェイスし、例へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="2d43a-111">[Creating a custom user interface](./creating-a-custom-user-interface.md) Introduces custom user interfaces and provides links to examples.</span></span>

<span data-ttu-id="2d43a-112">[ホスト アプリケーション サンプル](./host-application-samples.md)このセクションには、完全なホスト アプリケーションのサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d43a-112">[Host Application Samples](./host-application-samples.md) This section includes samples of complete host applications.</span></span>

## <a name="see-also"></a><span data-ttu-id="2d43a-113">参照</span><span class="sxs-lookup"><span data-stu-id="2d43a-113">See Also</span></span>

[<span data-ttu-id="2d43a-114">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d43a-114">Windows PowerShell</span></span>](http://msdn.microsoft.com/en-us/b41a2af3-aec1-402d-8e18-c2c26be461ff)
