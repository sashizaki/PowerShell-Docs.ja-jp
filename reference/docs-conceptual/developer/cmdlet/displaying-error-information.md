---
title: エラー情報の表示 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e542110e9c35a74c5d4c112b0a831f7f8ad9242e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774577"
---
# <a name="displaying-error-information"></a><span data-ttu-id="e9208-102">エラー情報を表示する</span><span class="sxs-lookup"><span data-stu-id="e9208-102">Displaying Error Information</span></span>

<span data-ttu-id="e9208-103">このトピックでは、ユーザーがエラー情報を表示する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9208-103">This topic discusses the ways in which users can display error information.</span></span>

<span data-ttu-id="e9208-104">コマンドレットでエラーが発生した場合、既定では、エラー情報の表示は次のようなエラー出力になります。</span><span class="sxs-lookup"><span data-stu-id="e9208-104">When your cmdlet encounters an error, the presentation of the error information will, by default, resemble the following error output.</span></span>

```powershell
$ stop-service lanmanworkstation
You do not have sufficient permissions to stop the service Workstation.
```

<span data-ttu-id="e9208-105">ただし、ユーザーは変数をに設定することによって、エラーをカテゴリ別に表示でき `$ErrorView` `"CategoryView"` ます。</span><span class="sxs-lookup"><span data-stu-id="e9208-105">However, users can view errors by category by setting the `$ErrorView` variable to `"CategoryView"`.</span></span> <span data-ttu-id="e9208-106">カテゴリビューでは、エラーの詳細な説明ではなく、エラーレコードからの特定の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9208-106">Category view displays specific information from the error record rather than a free-text description of the error.</span></span> <span data-ttu-id="e9208-107">このビューは、スキャンするエラーの一覧が長い場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="e9208-107">This view can be useful if you have a long list of errors to scan.</span></span> <span data-ttu-id="e9208-108">カテゴリビューでは、前のエラーメッセージが次のように表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9208-108">In category view, the previous error message is displayed as follows.</span></span>

```powershell
$ $ErrorView = "CategoryView"
$ stop-service lanmanworkstation
CloseError: (System.ServiceProcess.ServiceController:ServiceController) [stop-service], ServiceCommandException
```

<span data-ttu-id="e9208-109">エラーカテゴリの詳細については、「 [Windows PowerShell エラーレコード](./windows-powershell-error-records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9208-109">For more information about error categories, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e9208-110">参照</span><span class="sxs-lookup"><span data-stu-id="e9208-110">See Also</span></span>

[<span data-ttu-id="e9208-111">Windows PowerShell エラー レコード</span><span class="sxs-lookup"><span data-stu-id="e9208-111">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="e9208-112">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="e9208-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
