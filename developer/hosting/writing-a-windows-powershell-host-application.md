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
ms.openlocfilehash: 2039e181becd1b39fc3d6cf0cdbcf0c20e9fc206
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863178"
---
# <a name="writing-a-windows-powershell-host-application"></a><span data-ttu-id="d33b3-102">Windows PowerShell ホスト アプリケーションを記述する</span><span class="sxs-lookup"><span data-stu-id="d33b3-102">Writing a Windows PowerShell Host Application</span></span>

<span data-ttu-id="d33b3-103">Windows PowerShell は、アプリケーションでホストできます。</span><span class="sxs-lookup"><span data-stu-id="d33b3-103">You can host Windows PowerShell in your application.</span></span> <span data-ttu-id="d33b3-104">ホスト アプリケーションは、コマンドが実行をローカルまたはリモート コンピューターでセッションを開いて、アプリケーションのニーズに応じて同期または非同期ベースのいずれかのコマンドを呼び出すには、実行空間を定義できます。</span><span class="sxs-lookup"><span data-stu-id="d33b3-104">The host application can define the runspace where commands are run, open sessions on a local or remote computer, and invoke the commands either synchronously or asynchronously based on the needs of the application.</span></span>

<span data-ttu-id="d33b3-105">次のトピックをホストするアプリケーションを作成する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="d33b3-105">The following topics explain how to create an application that hosts</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d33b3-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d33b3-106">In This Section</span></span>

<span data-ttu-id="d33b3-107">[Windows PowerShell ホストのクイック スタート](./windows-powershell-host-quickstart.md)について説明し、コード サンプルを取得するホスト アプリケーションの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="d33b3-107">[Windows PowerShell Host Quickstart](./windows-powershell-host-quickstart.md) Provides instructions and code samples to get you started creating host applications.</span></span>

<span data-ttu-id="d33b3-108">[実行空間を作成する](./creating-runspaces.md)ホスト アプリケーションでの Windows PowerShell コマンドを実行する実行空間を作成する方法を説明するトピックのセット。</span><span class="sxs-lookup"><span data-stu-id="d33b3-108">[Creating Runspaces](./creating-runspaces.md) A set of topics that explain how to create runspaces to run Windows PowerShell command in a host application.</span></span>

<span data-ttu-id="d33b3-109">[追加して、コマンドを起動](./adding-and-invoking-commands.md)を作成して、ホスト アプリケーションでのコマンド パイプラインの実行方法について説明します.</span><span class="sxs-lookup"><span data-stu-id="d33b3-109">[Adding and invoking commands](./adding-and-invoking-commands.md) Explains how to create and run a command pipeline in your host application..</span></span>

<span data-ttu-id="d33b3-110">[リモート実行空間を作成する](./creating-remote-runspaces.md)Expains、実行空間をリモート コンピューターに接続する方法。</span><span class="sxs-lookup"><span data-stu-id="d33b3-110">[Creating remote runspaces](./creating-remote-runspaces.md) Expains how to connect a runspace to a remote computer.</span></span>

<span data-ttu-id="d33b3-111">[カスタム ユーザー インターフェイスを作成する](./creating-a-custom-user-interface.md)導入のカスタム ユーザー インターフェイスし、例へのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="d33b3-111">[Creating a custom user interface](./creating-a-custom-user-interface.md) Introduces custom user interfaces and provides links to examples.</span></span>

<span data-ttu-id="d33b3-112">[ホスト アプリケーション サンプル](./host-application-samples.md)このセクションには、完全なホスト アプリケーションのサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d33b3-112">[Host Application Samples](./host-application-samples.md) This section includes samples of complete host applications.</span></span>

## <a name="see-also"></a><span data-ttu-id="d33b3-113">参照</span><span class="sxs-lookup"><span data-stu-id="d33b3-113">See Also</span></span>

[<span data-ttu-id="d33b3-114">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d33b3-114">Windows PowerShell</span></span>](http://msdn.microsoft.com/en-us/b41a2af3-aec1-402d-8e18-c2c26be461ff)