---
title: エラー情報を表示する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76fcc0c1-9795-45d3-a564-40f822b657b5
caps.latest.revision: 8
ms.openlocfilehash: 4bc8666ee9053eb368402c8644558f4fe2dcc9ee
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858278"
---
# <a name="displaying-error-information"></a><span data-ttu-id="ec644-102">エラー情報を表示する</span><span class="sxs-lookup"><span data-stu-id="ec644-102">Displaying Error Information</span></span>

<span data-ttu-id="ec644-103">このトピックでは、ユーザーによるエラー情報の表示方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec644-103">This topic discusses the ways in which users can display error information.</span></span>

<span data-ttu-id="ec644-104">コマンドレットには、エラーが発生すると、エラー情報の表示は、既定では、ように、次のエラー出力。</span><span class="sxs-lookup"><span data-stu-id="ec644-104">When your cmdlet encounters an error, the presentation of the error information will, by default, resemble the following error output.</span></span>

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

<span data-ttu-id="ec644-105">ただし、ユーザーによって表示できますエラー カテゴリを設定して、`$ErrorView`変数を`"CategoryView"`します。</span><span class="sxs-lookup"><span data-stu-id="ec644-105">However, users can view errors by category by setting the `$ErrorView` variable to `"CategoryView"`.</span></span> <span data-ttu-id="ec644-106">カテゴリのビューには、エラーのフリー テキストによる説明ではなく、エラー レコードから特定の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec644-106">Category view displays specific information from the error record rather than a free-text description of the error.</span></span> <span data-ttu-id="ec644-107">このビューは、スキャンするエラーの長いリストがある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ec644-107">This view can be useful if you have a long list of errors to scan.</span></span> <span data-ttu-id="ec644-108">カテゴリ表示で、以前のエラー メッセージは、次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec644-108">In category view, the previous error message is displayed as follows.</span></span>

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

<span data-ttu-id="ec644-109">エラー カテゴリの詳細については、次を参照してください。 [Windows PowerShell のエラー レコード](./windows-powershell-error-records.md)します。</span><span class="sxs-lookup"><span data-stu-id="ec644-109">For more information about error categories, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ec644-110">参照</span><span class="sxs-lookup"><span data-stu-id="ec644-110">See Also</span></span>

[<span data-ttu-id="ec644-111">Windows PowerShell のエラー レコード</span><span class="sxs-lookup"><span data-stu-id="ec644-111">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="ec644-112">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="ec644-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
