---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 81ce13a082ad1d7a13ba5fd76a7595b55708f54e
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="register-a-powershell-repository"></a><span data-ttu-id="17c7a-102">PowerShell リポジトリの登録</span><span class="sxs-lookup"><span data-stu-id="17c7a-102">Register a PowerShell Repository</span></span>
<span data-ttu-id="17c7a-103">内部リポジトリに対して動作するように PowerShellGet を構成できます。</span><span class="sxs-lookup"><span data-stu-id="17c7a-103">You can configure PowerShellGet to operate against internal repositories.</span></span> <span data-ttu-id="17c7a-104">これは、次の追加コマンドレットを使用して行います。</span><span class="sxs-lookup"><span data-stu-id="17c7a-104">This is done by using the following additions:</span></span>
- <span data-ttu-id="17c7a-105">Register-PSRepository: 現在のユーザーのリポジトリを登録します。</span><span class="sxs-lookup"><span data-stu-id="17c7a-105">Register-PSRepository: Registers a repository for the current user.</span></span>
- <span data-ttu-id="17c7a-106">Unregister-PSRepository: 現在のユーザーの登録済みリポジトリを削除します。</span><span class="sxs-lookup"><span data-stu-id="17c7a-106">Unregister-PSRepository: Removes a registered repository for the current user.</span></span>
- <span data-ttu-id="17c7a-107">Set-PSRepository: 登録されたリポジトリの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="17c7a-107">Set-PSRepository: Set values for a registered repository.</span></span>
- <span data-ttu-id="17c7a-108">Get-PSRepository: 現在のユーザーのすべての登録済みリポジトリを取得します。</span><span class="sxs-lookup"><span data-stu-id="17c7a-108">Get-PSRepository: Get all registered repositories for the current user.</span></span>

<span data-ttu-id="17c7a-109">リポジトリを登録した後、Find-Module および Install-Module を使用して操作できます。</span><span class="sxs-lookup"><span data-stu-id="17c7a-109">After a repository is registered, you can use Find-Module and Install-Module to work with it.</span></span>

```powershell
\#Register a default repository
Register-PSRepository –Name DemoRepo –SourceLocation “https://www.myget.org/F/powershellgetdemo/api/v2” –PublishLocation “<https://www.myget.org/F/powershellgetdemo/api/v2>/package” –InstallationPolicy –Trusted

\#Get all of the registered repositories
Get-PSRepository
Name SourceLocation
---- --------------
PSGallery https://msconfiggallery.cloudapp...
DemoRepo https://www.myget.org/F/powershe...

\#Search only the new repository for modules
Find-Module -Repository DemoRepo
Repository Version Name
---------- ------- ----
DemoRepo 1.0.1 xActiveDirectory
DemoRepo 1.1.1 SomeModule

\#By default, PowerShellGet operates against all registered repositories when none is specified. In this example, the “SomeModule” module is installed from the DemoRepo.
Install-Module SomeModule

\#Removing a repository
Unregister-PSRepository DemoRepo
```

