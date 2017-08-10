---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell コア プロバイダー"
ms.assetid: 6e24bf6d-4c70-4edf-956a-1e8e4779ba10
ms.openlocfilehash: fdfdfee86884d3ac18a33ac424828faa96ecd8bd
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="windows-powershell-core-providers"></a><span data-ttu-id="1e825-103">Windows PowerShell コア プロバイダー</span><span class="sxs-lookup"><span data-stu-id="1e825-103">Windows PowerShell Core Providers</span></span>
<span data-ttu-id="1e825-104">このセクションには、**Microsoft.PowerShell.Core** モジュールの Windows PowerShell プロバイダーについて説明するヘルプ トピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1e825-104">This section contains help topics that describe the Windows PowerShell providers in the **Microsoft.PowerShell.Core** module.</span></span>

<span data-ttu-id="1e825-105">Windows PowerShell プロバイダーは .NET プログラムであり、特化されたデータ ストアのデータを Windows PowerShell で利用できるようにします。このデータを簡単に表示し、管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1e825-105">Windows PowerShell providers are .NET programs that make the data in a specialized data store available in Windows PowerShell so that you can easily view and manage it.</span></span> <span data-ttu-id="1e825-106">プロバイダーが公開するデータはファイル システム ドライブのようにドライブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e825-106">The data that a provider exposes appears in a drive, much like a file system drive.</span></span> <span data-ttu-id="1e825-107">詳細については、「[about_Providers [v4]](https://technet.microsoft.com/en-us/library/2d9b3f32-be78-49ad-a547-21231c803242)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e825-107">For more information, see [about_Providers [v4]](https://technet.microsoft.com/en-us/library/2d9b3f32-be78-49ad-a547-21231c803242).</span></span>

|<span data-ttu-id="1e825-108">プロバイダー</span><span class="sxs-lookup"><span data-stu-id="1e825-108">Provider</span></span>|<span data-ttu-id="1e825-109">説明</span><span class="sxs-lookup"><span data-stu-id="1e825-109">Description</span></span>|
|------------|---------------|
|[<span data-ttu-id="1e825-110">Alias プロバイダー [v3]</span><span class="sxs-lookup"><span data-stu-id="1e825-110">Alias Provider [v3]</span></span>](https://technet.microsoft.com/en-us/library/dce3f872-aeff-4eb2-8b38-876cd612fc29)|<span data-ttu-id="1e825-111">Windows PowerShell エイリアスとその値へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1e825-111">Provides access to the Windows PowerShell aliases and their values.</span></span>|
|[<span data-ttu-id="1e825-112">Environment プロバイダー [v3]</span><span class="sxs-lookup"><span data-stu-id="1e825-112">Environment Provider [v3]</span></span>](https://technet.microsoft.com/en-us/library/94fcd05d-e702-4706-9b7d-ad7e5fd0ec09)|<span data-ttu-id="1e825-113">Windows 環境変数へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1e825-113">Provides access to the Windows environment variables.</span></span>|
|[<span data-ttu-id="1e825-114">FileSystem プロバイダー [v3]</span><span class="sxs-lookup"><span data-stu-id="1e825-114">FileSystem Provider [v3]</span></span>](https://technet.microsoft.com/en-us/library/0e494537-dfdf-437a-8b27-c21e30aa1f9f)|<span data-ttu-id="1e825-115">ファイルとディレクトリへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1e825-115">Provides access to files and directories.</span></span>|
|[<span data-ttu-id="1e825-116">Function プロバイダー [v3]</span><span class="sxs-lookup"><span data-stu-id="1e825-116">Function Provider [v3]</span></span>](https://technet.microsoft.com/en-us/library/7dfc92f4-9a88-4399-978d-6d5d224b3e76)|<span data-ttu-id="1e825-117">Windows PowerShell で定義されている関数へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1e825-117">Provides access to the functions defined in Windows PowerShell.</span></span>|
|[<span data-ttu-id="1e825-118">Registry プロバイダー [v3]</span><span class="sxs-lookup"><span data-stu-id="1e825-118">Registry Provider [v3]</span></span>](https://technet.microsoft.com/en-us/library/d3c8013c-8caa-48d7-9feb-bfef0d95926e)|<span data-ttu-id="1e825-119">システム レジストリのキーと値へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1e825-119">Provides access to the system registry keys and values.</span></span>|
|[<span data-ttu-id="1e825-120">Variable プロバイダー [v3]</span><span class="sxs-lookup"><span data-stu-id="1e825-120">Variable Provider [v3]</span></span>](https://technet.microsoft.com/en-us/library/78dbcbbd-7946-4b9b-b75b-146f247f821c)|<span data-ttu-id="1e825-121">Windows PowerShell の変数とその値へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1e825-121">Provides access to Windows PowerShell variables and their values.</span></span>|

## <a name="see-also"></a><span data-ttu-id="1e825-122">参照</span><span class="sxs-lookup"><span data-stu-id="1e825-122">See Also</span></span>
- [<span data-ttu-id="1e825-123">Certificate プロバイダー [v3]</span><span class="sxs-lookup"><span data-stu-id="1e825-123">Certificate Provider [v3]</span></span>](https://technet.microsoft.com/en-us/library/3f743541-d0c6-4670-809a-b16fb01f7c4d)
- [<span data-ttu-id="1e825-124">WSMan プロバイダー [v3]</span><span class="sxs-lookup"><span data-stu-id="1e825-124">WSMan Provider [v3]</span></span>](https://technet.microsoft.com/en-us/library/4c3d8d36-4f7a-4211-996f-64110e4b2eb7)
- [<span data-ttu-id="1e825-125">about_Providers [v4]</span><span class="sxs-lookup"><span data-stu-id="1e825-125">about_Providers [v4]</span></span>](https://technet.microsoft.com/en-us/library/2d9b3f32-be78-49ad-a547-21231c803242)
- [<span data-ttu-id="1e825-126">Microsoft.PowerShell.Core モジュール</span><span class="sxs-lookup"><span data-stu-id="1e825-126">Microsoft.PowerShell.Core Module</span></span>](Microsoft.PowerShell.Core-Module.md)

