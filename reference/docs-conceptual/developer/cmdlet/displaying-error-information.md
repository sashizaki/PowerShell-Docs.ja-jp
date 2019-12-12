---
title: エラー情報の表示 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76fcc0c1-9795-45d3-a564-40f822b657b5
caps.latest.revision: 8
ms.openlocfilehash: 4bc8666ee9053eb368402c8644558f4fe2dcc9ee
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369971"
---
# <a name="displaying-error-information"></a><span data-ttu-id="920a8-102">エラー情報を表示する</span><span class="sxs-lookup"><span data-stu-id="920a8-102">Displaying Error Information</span></span>

<span data-ttu-id="920a8-103">このトピックでは、ユーザーがエラー情報を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="920a8-103">This topic discusses the ways in which users can display error information.</span></span>

<span data-ttu-id="920a8-104">コマンドレットでエラーが発生した場合、既定では、エラー情報の表示は次のようなエラー出力になります。</span><span class="sxs-lookup"><span data-stu-id="920a8-104">When your cmdlet encounters an error, the presentation of the error information will, by default, resemble the following error output.</span></span>

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

<span data-ttu-id="920a8-105">ただし、ユーザーは `$ErrorView` 変数を `"CategoryView"`に設定することによって、エラーをカテゴリ別に表示できます。</span><span class="sxs-lookup"><span data-stu-id="920a8-105">However, users can view errors by category by setting the `$ErrorView` variable to `"CategoryView"`.</span></span> <span data-ttu-id="920a8-106">カテゴリビューでは、エラーの詳細な説明ではなく、エラーレコードからの特定の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="920a8-106">Category view displays specific information from the error record rather than a free-text description of the error.</span></span> <span data-ttu-id="920a8-107">このビューは、スキャンするエラーの一覧が長い場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="920a8-107">This view can be useful if you have a long list of errors to scan.</span></span> <span data-ttu-id="920a8-108">カテゴリビューでは、前のエラーメッセージが次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="920a8-108">In category view, the previous error message is displayed as follows.</span></span>

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

<span data-ttu-id="920a8-109">エラーカテゴリの詳細については、「 [Windows PowerShell エラーレコード](./windows-powershell-error-records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="920a8-109">For more information about error categories, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="920a8-110">参照</span><span class="sxs-lookup"><span data-stu-id="920a8-110">See Also</span></span>

[<span data-ttu-id="920a8-111">Windows PowerShell エラーレコード</span><span class="sxs-lookup"><span data-stu-id="920a8-111">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="920a8-112">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="920a8-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
