---
description: PowerShell での完全パス名と相対パス名の形式について説明します。
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_path_syntax?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Path_Syntax
ms.openlocfilehash: 9a95865d67dc15bf79762987622b702b14faf6c6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604977"
---
# <a name="about-path-syntax"></a><span data-ttu-id="08f45-103">パスの構文について</span><span class="sxs-lookup"><span data-stu-id="08f45-103">About Path Syntax</span></span>

## <a name="short-description"></a><span data-ttu-id="08f45-104">概要</span><span class="sxs-lookup"><span data-stu-id="08f45-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="08f45-105">PowerShell での完全パス名と相対パス名の形式について説明します。</span><span class="sxs-lookup"><span data-stu-id="08f45-105">Describes the full and relative path name formats in  PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="08f45-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="08f45-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="08f45-107">PowerShell プロバイダーを介してアクセスできるデータストア内のすべての項目は、パス名によって一意に識別できます。</span><span class="sxs-lookup"><span data-stu-id="08f45-107">All items in a data store accessible through a PowerShell provider can be uniquely identified by their path names.</span></span> <span data-ttu-id="08f45-108">パス名は、項目名、項目が配置されているコンテナーとサブコンテナー、およびコンテナーへのアクセスに使用する PowerShell ドライブを組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="08f45-108">A path name is a combination of the item name, the container and subcontainers in which the item is located, and the PowerShell drive through which the containers are accessed.</span></span>

<span data-ttu-id="08f45-109">PowerShell では、パス名は、完全修飾と相対の2種類のいずれかに分割されます。</span><span class="sxs-lookup"><span data-stu-id="08f45-109">In PowerShell, path names are divided into one of two types: fully qualified and relative.</span></span> <span data-ttu-id="08f45-110">完全修飾パス名は、パスを構成するすべての要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="08f45-110">A fully qualified path name consists of all elements that make up a path.</span></span> <span data-ttu-id="08f45-111">次の構文は、完全修飾パス名の要素を示しています。</span><span class="sxs-lookup"><span data-stu-id="08f45-111">The following syntax shows the elements in a fully qualified path name:</span></span>

```powershell
[<provider>::]<drive>:[\<container>[\<subcontainer>...]]\<item>
```

<span data-ttu-id="08f45-112">プレースホルダーは、 \<provider\> データストアへのアクセスに使用する PowerShell プロバイダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="08f45-112">The \<provider\> placeholder refers to the PowerShell provider through which you access the data store.</span></span> <span data-ttu-id="08f45-113">たとえば、FileSystem プロバイダーを使用すると、コンピューター上のファイルとディレクトリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="08f45-113">For example, the FileSystem provider allows you to access the files and directories on your computer.</span></span> <span data-ttu-id="08f45-114">この構文の要素は省略可能であり、ドライブ名はすべてのプロバイダーで一意であるため、必要ありません。</span><span class="sxs-lookup"><span data-stu-id="08f45-114">This element of the syntax is optional and is never needed because the drive names are unique across all providers.</span></span>

<span data-ttu-id="08f45-115">プレースホルダーは、 \<drive\> 特定の powershell プロバイダーでサポートされている powershell ドライブを参照します。</span><span class="sxs-lookup"><span data-stu-id="08f45-115">The \<drive\> placeholder refers to the PowerShell drive that is supported by a particular PowerShell provider.</span></span> <span data-ttu-id="08f45-116">FileSystem プロバイダーの場合、PowerShell ドライブはシステム上に構成されている Windows ドライブにマップされます。</span><span class="sxs-lookup"><span data-stu-id="08f45-116">In the case of the FileSystem provider, the PowerShell drives map to the Windows drives that are configured on your system.</span></span> <span data-ttu-id="08f45-117">たとえば、システムに A: ドライブと C: ドライブが含まれている場合、FileSystem プロバイダーは PowerShell で同じドライブを作成します。</span><span class="sxs-lookup"><span data-stu-id="08f45-117">For example, if your system includes an A: drive and a C: drive, the FileSystem provider creates the same drives in PowerShell.</span></span>

<span data-ttu-id="08f45-118">ドライブを指定したら、その項目を含むコンテナーとサブコンテナーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08f45-118">After you have specified the drive, you must specify any containers and subcontainers that contain the item.</span></span> <span data-ttu-id="08f45-119">コンテナーは、データストアに存在する階層の順序で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08f45-119">The containers must be specified in the hierarchical order in which they exist in the data store.</span></span> <span data-ttu-id="08f45-120">つまり、親コンテナー、親コンテナー内の子コンテナーなどを使用して開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08f45-120">In other words, you must start with the parent container, then the child container in that parent container, and so on.</span></span> <span data-ttu-id="08f45-121">また、各コンテナーの前には円記号を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="08f45-121">In addition, each container must be preceded by a backslash.</span></span> <span data-ttu-id="08f45-122">(PowerShell では、他の PowerShells との互換性のためにスラッシュを使用できます)。</span><span class="sxs-lookup"><span data-stu-id="08f45-122">(Note that PowerShell allows you to use forward slashes for compatibility with other PowerShells.)</span></span>

<span data-ttu-id="08f45-123">コンテナーとサブコンテナーを指定した後、項目名の前に円記号を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="08f45-123">After the container and subcontainers have been specified, you must provide the item name, preceded by a backslash.</span></span> <span data-ttu-id="08f45-124">たとえば、C: Windows System32 ディレクトリ内の Shell.dll ファイルの完全修飾パス名は次のように \\ \\ なります。</span><span class="sxs-lookup"><span data-stu-id="08f45-124">For example, the fully qualified path name for the Shell.dll file in the C:\\Windows\\System32 directory is as follows:</span></span>

```powershell
C:\Windows\System32\Shell.dll
```

<span data-ttu-id="08f45-125">この場合、コンテナーへのアクセスに使用されるドライブは C: ドライブ、最上位のコンテナーは Windows、サブコンテナーは System32 (Windows コンテナー内にある)、項目は Shell.dll です。</span><span class="sxs-lookup"><span data-stu-id="08f45-125">In this case, the drive through which the containers are accessed is the C: drive, the top-level container is Windows, the subcontainer is System32 (located within the Windows container), and the item is Shell.dll.</span></span>

<span data-ttu-id="08f45-126">場合によっては、完全修飾パス名を指定する必要はなく、代わりに相対パス名を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="08f45-126">In some situations, you do not need to specify a fully qualified path name and can instead use a relative path name.</span></span> <span data-ttu-id="08f45-127">相対パス名は、現在の作業場所に基づいています。</span><span class="sxs-lookup"><span data-stu-id="08f45-127">A relative path name is based on the current working location.</span></span> <span data-ttu-id="08f45-128">PowerShell では、現在の作業場所に対する相対的な位置に基づいて項目を識別できます。</span><span class="sxs-lookup"><span data-stu-id="08f45-128">PowerShell allows you to identify an item based on its location relative to the current working location.</span></span> <span data-ttu-id="08f45-129">相対パス名は、特殊文字を使用して指定できます。</span><span class="sxs-lookup"><span data-stu-id="08f45-129">You can specify relative path names by using special characters.</span></span> <span data-ttu-id="08f45-130">次の表では、これらの各文字について説明し、相対パス名と完全修飾パス名の例を示します。</span><span class="sxs-lookup"><span data-stu-id="08f45-130">The following table describes each of these characters and provides examples of relative path names and fully qualified path names.</span></span> <span data-ttu-id="08f45-131">テーブルの例は、現在の作業ディレクトリが C:\ に設定されていることに基づいています。</span><span class="sxs-lookup"><span data-stu-id="08f45-131">The examples in the table are based on the current working directory being set to C:\Windows.</span></span>

|<span data-ttu-id="08f45-132">Symbol</span><span class="sxs-lookup"><span data-stu-id="08f45-132">Symbol</span></span>|<span data-ttu-id="08f45-133">説明</span><span class="sxs-lookup"><span data-stu-id="08f45-133">Description</span></span>               |<span data-ttu-id="08f45-134">相対パス</span><span class="sxs-lookup"><span data-stu-id="08f45-134">Relative path</span></span>    |<span data-ttu-id="08f45-135">完全なパス</span><span class="sxs-lookup"><span data-stu-id="08f45-135">Full path</span></span>          |
|------|--------------------------|-----------------|-------------------|
|<span data-ttu-id="08f45-136">.</span><span class="sxs-lookup"><span data-stu-id="08f45-136">.</span></span>     |<span data-ttu-id="08f45-137">現在の場所</span><span class="sxs-lookup"><span data-stu-id="08f45-137">Current location</span></span>          |<span data-ttu-id="08f45-138">.\\System</span><span class="sxs-lookup"><span data-stu-id="08f45-138">.\\System</span></span>        |<span data-ttu-id="08f45-139">c: \\ Windows \\ システム</span><span class="sxs-lookup"><span data-stu-id="08f45-139">c:\\Windows\\System</span></span>|
|<span data-ttu-id="08f45-140">..</span><span class="sxs-lookup"><span data-stu-id="08f45-140">..</span></span>    |<span data-ttu-id="08f45-141">現在の場所の親</span><span class="sxs-lookup"><span data-stu-id="08f45-141">Parent of current location</span></span>|<span data-ttu-id="08f45-142">..\\プログラムファイル</span><span class="sxs-lookup"><span data-stu-id="08f45-142">..\\Program Files</span></span>|<span data-ttu-id="08f45-143">c: \\ プログラムファイル</span><span class="sxs-lookup"><span data-stu-id="08f45-143">c:\\Program Files</span></span>  |
|\     |<span data-ttu-id="08f45-144">現在ののドライブルート</span><span class="sxs-lookup"><span data-stu-id="08f45-144">Drive root of current</span></span>     |<span data-ttu-id="08f45-145">\\プログラムファイル</span><span class="sxs-lookup"><span data-stu-id="08f45-145">\\Program Files</span></span>  |<span data-ttu-id="08f45-146">c: \\ プログラムファイル</span><span class="sxs-lookup"><span data-stu-id="08f45-146">c:\\Program Files</span></span>  |
|      |<span data-ttu-id="08f45-147">location</span><span class="sxs-lookup"><span data-stu-id="08f45-147">location</span></span>                  |                 |                   |
|<span data-ttu-id="08f45-148">存在</span><span class="sxs-lookup"><span data-stu-id="08f45-148">[none]</span></span>|<span data-ttu-id="08f45-149">特殊文字がありません</span><span class="sxs-lookup"><span data-stu-id="08f45-149">No special characters</span></span>     |<span data-ttu-id="08f45-150">System (システム)</span><span class="sxs-lookup"><span data-stu-id="08f45-150">System</span></span>           |<span data-ttu-id="08f45-151">c: \\ Windows \\ システム</span><span class="sxs-lookup"><span data-stu-id="08f45-151">c:\\Windows\\System</span></span>|

<span data-ttu-id="08f45-152">コマンドでパス名を使用する場合は、完全修飾パス名または相対パスを使用する場合と同じ方法で、その名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="08f45-152">When using a path name in a command, you enter that name in the same way whether you use a fully qualified path name or a relative one.</span></span> <span data-ttu-id="08f45-153">たとえば、現在の作業ディレクトリが C:\ windowsであるとします。</span><span class="sxs-lookup"><span data-stu-id="08f45-153">For example, suppose that your current working directory is C:\Windows.</span></span> <span data-ttu-id="08f45-154">次の Get-ChildItem コマンドは、C:\ の docs ディレクトリ内のすべての項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="08f45-154">The following Get-ChildItem command retrieves all items in the C:\Techdocs directory:</span></span>

```powershell
Get-ChildItem \techdocs
```

<span data-ttu-id="08f45-155">円記号は、現在の作業場所のドライブルートを使用する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="08f45-155">The backslash indicates that the drive root of the current working location should be used.</span></span> <span data-ttu-id="08f45-156">作業ディレクトリは C: Windows であるため、 \\ ドライブルートは c: ドライブです。</span><span class="sxs-lookup"><span data-stu-id="08f45-156">Because the working directory is C:\\Windows, the drive root is the C: drive.</span></span> <span data-ttu-id="08f45-157">テクニカル docs ディレクトリはルートから外れているため、円記号のみを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="08f45-157">Because the techdocs directory is located off the root, you need to specify only the backslash.</span></span>

<span data-ttu-id="08f45-158">次のコマンドを使用して、同じ結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="08f45-158">You can achieve the same results by using the following command:</span></span>

```powershell
Get-ChildItem c:\techdocs
```

<span data-ttu-id="08f45-159">完全修飾パス名と相対パス名のどちらを使用するかにかかわらず、パス名は項目を特定するだけでなく、項目が別のコンテナー内の別の項目と同じ名前を共有している場合でも項目を一意に識別できるため、重要です。</span><span class="sxs-lookup"><span data-stu-id="08f45-159">Regardless of whether you use a fully qualified path name or a relative path name, a path name is important not only because it locates an item but also because it uniquely identifies the item even if that item shares the same name as another item in a different container.</span></span>

<span data-ttu-id="08f45-160">たとえば、それぞれ Results.txt という名前の2つのファイルがあるとします。</span><span class="sxs-lookup"><span data-stu-id="08f45-160">For instance, suppose that you have two files that are each named Results.txt.</span></span>
<span data-ttu-id="08f45-161">最初のファイルは C: テクニカルドキュメント Jan という名前のディレクトリにあり、 \\ \\ 2 番目のファイルは c: テクニカルドキュメント Feb という名前のディレクトリにあり \\ \\ ます。最初のファイルのパス名 (C: \\ テクニカルドキュメント \\ Jan \\Results.txt) と2番目のファイルのパス名 (c: \\ テクニカルドキュメント \\ 2 月Results.txt) を使用すると、 \\ 2 つのファイルを明確に区別できます。</span><span class="sxs-lookup"><span data-stu-id="08f45-161">The first file is in a directory named C:\\Techdocs\\Jan, and the second file is in a directory named C:\\Techdocs\\Feb. The path name for the first file (C:\\Techdocs\\Jan\\Results.txt) and the path name for the second file (C:\\Techdocs\\Feb\\Results.txt) allow you to clearly distinguish between the two files.</span></span>

## <a name="see-also"></a><span data-ttu-id="08f45-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="08f45-162">SEE ALSO</span></span>

[<span data-ttu-id="08f45-163">about_Locations</span><span class="sxs-lookup"><span data-stu-id="08f45-163">about_Locations</span></span>](about_Locations.md)

