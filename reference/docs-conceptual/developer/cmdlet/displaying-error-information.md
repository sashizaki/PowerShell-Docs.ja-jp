---
ms.date: 09/13/2016
ms.topic: reference
title: エラー情報を表示する
description: エラー情報を表示する
ms.openlocfilehash: 37a3adb91d0e616a5c7f27bcab866f8da139f969
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653051"
---
# <a name="displaying-error-information"></a><span data-ttu-id="6c893-103">エラー情報を表示する</span><span class="sxs-lookup"><span data-stu-id="6c893-103">Displaying Error Information</span></span>

<span data-ttu-id="6c893-104">このトピックでは、ユーザーがエラー情報を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6c893-104">This topic discusses the ways in which users can display error information.</span></span>

<span data-ttu-id="6c893-105">コマンドレットでエラーが発生した場合、既定では、エラー情報の表示は次のようなエラー出力になります。</span><span class="sxs-lookup"><span data-stu-id="6c893-105">When your cmdlet encounters an error, the presentation of the error information will, by default, resemble the following error output.</span></span>

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

<span data-ttu-id="6c893-106">ただし、ユーザーは変数をに設定することによって、エラーをカテゴリ別に表示でき `$ErrorView` `"CategoryView"` ます。</span><span class="sxs-lookup"><span data-stu-id="6c893-106">However, users can view errors by category by setting the `$ErrorView` variable to `"CategoryView"`.</span></span> <span data-ttu-id="6c893-107">カテゴリビューでは、エラーの詳細な説明ではなく、エラーレコードからの特定の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c893-107">Category view displays specific information from the error record rather than a free-text description of the error.</span></span> <span data-ttu-id="6c893-108">このビューは、スキャンするエラーの一覧が長い場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="6c893-108">This view can be useful if you have a long list of errors to scan.</span></span> <span data-ttu-id="6c893-109">カテゴリビューでは、前のエラーメッセージが次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c893-109">In category view, the previous error message is displayed as follows.</span></span>

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

<span data-ttu-id="6c893-110">エラーカテゴリの詳細については、「 [Windows PowerShell エラーレコード](./windows-powershell-error-records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c893-110">For more information about error categories, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6c893-111">参照</span><span class="sxs-lookup"><span data-stu-id="6c893-111">See Also</span></span>

[<span data-ttu-id="6c893-112">Windows PowerShell エラー レコード</span><span class="sxs-lookup"><span data-stu-id="6c893-112">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="6c893-113">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="6c893-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
