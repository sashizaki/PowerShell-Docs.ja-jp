---
description: PowerShell で作業場所から項目にアクセスする方法について説明します。
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_locations?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Locations
ms.openlocfilehash: 4876abe3c651ad2279b85355f2e5e029203b6d4e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600973"
---
# <a name="about_locations"></a><span data-ttu-id="6ef68-103">about_Locations</span><span class="sxs-lookup"><span data-stu-id="6ef68-103">about_Locations</span></span>

## <a name="short-description"></a><span data-ttu-id="6ef68-104">概要</span><span class="sxs-lookup"><span data-stu-id="6ef68-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="6ef68-105">PowerShell で作業場所から項目にアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ef68-105">Describes how to access items from the working location in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="6ef68-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="6ef68-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="6ef68-107">現在の作業場所は、コマンドが指す既定の場所です。</span><span class="sxs-lookup"><span data-stu-id="6ef68-107">The current working location is the default location to which commands point.</span></span>
<span data-ttu-id="6ef68-108">つまり、これは、コマンドの影響を受ける項目または場所への明示的なパスを指定していない場合に PowerShell が使用する場所です。</span><span class="sxs-lookup"><span data-stu-id="6ef68-108">In other words, this is the location that PowerShell uses if you do not supply an explicit path to the item or location that is affected by the command.</span></span> <span data-ttu-id="6ef68-109">ほとんどの場合、現在の作業場所は、PowerShell FileSystem プロバイダーを介してアクセスされるドライブで、場合によってはそのドライブ上のディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="6ef68-109">In most cases, the current working location is a drive accessed through the PowerShell FileSystem provider and, in some cases, a directory on that drive.</span></span>
<span data-ttu-id="6ef68-110">たとえば、現在の作業場所を次の場所に設定できます。</span><span class="sxs-lookup"><span data-stu-id="6ef68-110">For example, you might set your current working location to the following location:</span></span>

```powershell
C:\Program Files\Windows PowerShell
```

<span data-ttu-id="6ef68-111">その結果、別のパスが明示的に指定されていない限り、すべてのコマンドがこの場所から処理されます。</span><span class="sxs-lookup"><span data-stu-id="6ef68-111">As a result, all commands are processed from this location unless another path is explicitly provided.</span></span>

<span data-ttu-id="6ef68-112">PowerShell は、ドライブが現在のドライブではない場合でも、各ドライブの現在の作業場所を保持します。</span><span class="sxs-lookup"><span data-stu-id="6ef68-112">PowerShell maintains the current working location for each drive even when the drive is not the current drive.</span></span> <span data-ttu-id="6ef68-113">これにより、別の場所のドライブのみを参照して、現在の作業場所から項目にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="6ef68-113">This allows you to access items from the current working location by referring only to the drive of another location.</span></span>
<span data-ttu-id="6ef68-114">たとえば、現在の作業場所が C: Windows であるとし \\ ます。</span><span class="sxs-lookup"><span data-stu-id="6ef68-114">For example, suppose that your current working location is C:\\Windows.</span></span> <span data-ttu-id="6ef68-115">ここで、次のコマンドを使用して、現在の作業場所を HKLM: ドライブに変更したとします。</span><span class="sxs-lookup"><span data-stu-id="6ef68-115">Now, suppose you use the following command to change your current working location to the HKLM: drive:</span></span>

```powershell
Set-Location HKLM:
```

<span data-ttu-id="6ef68-116">現在の場所はレジストリドライブになっていますが、 \\ 次の例に示すように、c: ドライブを使用するだけで c: Windows ディレクトリ内の項目にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6ef68-116">Although your current location is now the registry drive, you can still access items in the C:\\Windows directory simply by using the C: drive, as shown in the following example:</span></span>

```powershell
Get-ChildItem C:
```

<span data-ttu-id="6ef68-117">PowerShell は、そのドライブの現在の作業場所が Windows ディレクトリであることを記憶しているので、そのディレクトリから項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="6ef68-117">PowerShell remembers that your current working location for that drive is the Windows directory, so it retrieves items from that directory.</span></span> <span data-ttu-id="6ef68-118">次のコマンドを実行した場合、結果は同じになります。</span><span class="sxs-lookup"><span data-stu-id="6ef68-118">The results would be the same if you ran the following command:</span></span>

```powershell
Get-ChildItem C:\Windows
```

<span data-ttu-id="6ef68-119">PowerShell では、Get-Location コマンドを使用して現在の作業場所を特定できます。また、Set-Location コマンドを使用して、現在の作業場所を設定できます。</span><span class="sxs-lookup"><span data-stu-id="6ef68-119">In PowerShell, you can use the Get-Location command to determine the current working location, and you can use the Set-Location command to set the current working location.</span></span> <span data-ttu-id="6ef68-120">たとえば、次のコマンドは、現在の作業場所を C: ドライブの Windows ディレクトリに設定します。</span><span class="sxs-lookup"><span data-stu-id="6ef68-120">For example, the following command sets the current working location to the Windows directory of the C: drive:</span></span>

```powershell
Set-Location c:\windows
```

<span data-ttu-id="6ef68-121">現在の作業場所を設定した後も、次の例に示すように、コマンドにドライブ名 (コロンの後にコロンを付ける) を含めるだけで、他のドライブから項目にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6ef68-121">After you set the current working location, you can still access items from other drives simply by including the drive name (followed by a colon) in the command, as shown in the following example:</span></span>

```powershell
Get-ChildItem HKLM:\software
```

<span data-ttu-id="6ef68-122">この例のコマンドは、レジストリの HKEY ローカルコンピューターハイブのソフトウェアコンテナー内の項目の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="6ef68-122">The example command retrieves a list of items in the Software container of the HKEY Local Machine hive in the registry.</span></span>

<span data-ttu-id="6ef68-123">PowerShell では、特殊文字を使用して、現在の作業場所とその親の場所を表すこともできます。</span><span class="sxs-lookup"><span data-stu-id="6ef68-123">PowerShell also allows you to use special characters to represent the current working location and its parent location.</span></span> <span data-ttu-id="6ef68-124">現在の作業場所を表すには、1つのピリオドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ef68-124">To represent the current working location, use a single period.</span></span> <span data-ttu-id="6ef68-125">現在の作業場所の親を表すには、2つの期間を使用します。</span><span class="sxs-lookup"><span data-stu-id="6ef68-125">To represent the parent of the current working location, use two periods.</span></span> <span data-ttu-id="6ef68-126">たとえば、次の例では、現在の作業場所のシステムサブディレクトリを指定しています。</span><span class="sxs-lookup"><span data-stu-id="6ef68-126">For example, the following specifies the System subdirectory in the current working location:</span></span>

```powershell
Get-ChildItem .\system
```

<span data-ttu-id="6ef68-127">現在の作業場所が C: windows の場合 \\ 、このコマンドは c: windows システム内のすべての項目の一覧を返し \\ \\ ます。</span><span class="sxs-lookup"><span data-stu-id="6ef68-127">If the current working location is C:\\Windows, this command returns a list of all the items in C:\\Windows\\System.</span></span> <span data-ttu-id="6ef68-128">ただし、2つの期間を使用する場合は、次の例に示すように、現在の作業ディレクトリの親ディレクトリが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ef68-128">However, if you use two periods, the parent directory of the current working directory is used, as shown in the following example:</span></span>

```powershell
Get-ChildItem ..\"program files"
```

<span data-ttu-id="6ef68-129">この場合、PowerShell は2つの期間を C: ドライブとして扱います。そのため、コマンドは C: Program Files ディレクトリ内のすべての項目を取得し \\ ます。</span><span class="sxs-lookup"><span data-stu-id="6ef68-129">In this case, PowerShell treats the two periods as the C: drive, so the command retrieves all the items in the C:\\Program Files directory.</span></span>

<span data-ttu-id="6ef68-130">スラッシュで始まるパスは、現在のドライブのルートからのパスを識別します。</span><span class="sxs-lookup"><span data-stu-id="6ef68-130">A path beginning with a slash identifies a path from the root of the current drive.</span></span> <span data-ttu-id="6ef68-131">たとえば、現在の作業場所が C: \\ Program Files PowerShell の場合、 \\ ドライブのルートは c になります。したがって、次のコマンドでは、C: Windows ディレクトリ内のすべての項目が一覧表示され \\ ます。</span><span class="sxs-lookup"><span data-stu-id="6ef68-131">For example, if your current working location is C:\\Program Files\\PowerShell, the root of your drive is C. Therefore, the following command lists all items in the C:\\Windows directory:</span></span>

```powershell
Get-ChildItem \windows
```

<span data-ttu-id="6ef68-132">コンテナーまたは項目の名前を指定するときに、ドライブ名、スラッシュ、ピリオドで始まるパスを指定しなかった場合、コンテナーまたは項目は現在の作業場所に配置されていると見なされます。</span><span class="sxs-lookup"><span data-stu-id="6ef68-132">If you do not specify a path beginning with a drive name, slash, or period when supplying the name of a container or item, the container or item is assumed to be located in the current working location.</span></span> <span data-ttu-id="6ef68-133">たとえば、現在の作業場所が C: windows の場合、 \\ 次のコマンドは c: windows システムディレクトリ内のすべての項目を返し \\ \\ ます。</span><span class="sxs-lookup"><span data-stu-id="6ef68-133">For example, if your current working location is C:\\Windows, the following command returns all the items in the C:\\Windows\\System directory:</span></span>

```powershell
Get-ChildItem system
```

<span data-ttu-id="6ef68-134">ディレクトリ名ではなくファイル名を指定すると、PowerShell によってそのファイルの詳細が返されます (ファイルが現在の作業場所にあることを前提としています)。</span><span class="sxs-lookup"><span data-stu-id="6ef68-134">If you specify a file name rather than a directory name, PowerShell returns details about that file (assuming that file is located in the current working location).</span></span>

## <a name="see-also"></a><span data-ttu-id="6ef68-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ef68-135">SEE ALSO</span></span>

[<span data-ttu-id="6ef68-136">Set-Location</span><span class="sxs-lookup"><span data-stu-id="6ef68-136">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)

[<span data-ttu-id="6ef68-137">about_Providers</span><span class="sxs-lookup"><span data-stu-id="6ef68-137">about_Providers</span></span>](about_Providers.md)

[<span data-ttu-id="6ef68-138">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="6ef68-138">about_Path_Syntax</span></span>](about_Path_Syntax.md)

