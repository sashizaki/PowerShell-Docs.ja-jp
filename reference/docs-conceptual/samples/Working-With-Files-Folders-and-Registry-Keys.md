---
ms.date: 07/28/2020
keywords: powershell,コマンドレット
title: ファイル、フォルダー、レジストリ キーの操作
ms.openlocfilehash: 7ead5d0e82feb852845468fb3a012a0908a4ce75
ms.sourcegitcommit: 339e5fc8a4cc18b4ff6956fe5180343588e40e30
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87410191"
---
# <a name="working-with-files-folders-and-registry-keys"></a><span data-ttu-id="1fa83-103">ファイル、フォルダー、レジストリ キーの操作</span><span class="sxs-lookup"><span data-stu-id="1fa83-103">Working With Files, Folders and Registry Keys</span></span>

<span data-ttu-id="1fa83-104">Windows PowerShell は、名詞の **Item** を使用して Windows PowerShell ドライブで検出された項目を参照します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-104">Windows PowerShell uses the noun **Item** to refer to items found on a Windows PowerShell drive.</span></span>
<span data-ttu-id="1fa83-105">Windows PowerShell FileSystem プロバイダーを処理する場合、**Item** は、ファイル、フォルダー、または Windows PowerShell ドライブである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="1fa83-105">When dealing with the Windows PowerShell FileSystem provider, an **Item** might be a file, a folder, or the Windows PowerShell drive.</span></span> <span data-ttu-id="1fa83-106">これらの項目を一覧表示して操作することは、ほとんどの管理設定において重要で基本的なタスクであるため、これらのタスクについては詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-106">Listing and working with these items is a critical basic task in most administrative settings, so we want to discuss these tasks in detail.</span></span>

## <a name="enumerating-files-folders-and-registry-keys-get-childitem"></a><span data-ttu-id="1fa83-107">ファイル、フォルダー、およびレジストリ キーの列挙 (Get-ChildItem)</span><span class="sxs-lookup"><span data-stu-id="1fa83-107">Enumerating Files, Folders, and Registry Keys (Get-ChildItem)</span></span>

<span data-ttu-id="1fa83-108">特定の場所から項目のコレクションを取得することは一般的なタスクであるため、`Get-ChildItem` コマンドレットは、特にフォルダーなどのコンテナー内で見つかったすべての項目を返すよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="1fa83-108">Since getting a collection of items from a particular location is such a common task, the `Get-ChildItem` cmdlet is designed specifically to return all items found within a container such as a folder.</span></span>

<span data-ttu-id="1fa83-109">C:\\Windows フォルダー内に直接含まれるすべてのファイルとフォルダーを返す場合は、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-109">If you want to return all files and folders that are contained directly within the folder C:\\Windows, type:</span></span>

```
PS> Get-ChildItem -Path C:\Windows
    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2006-05-16   8:10 AM          0 0.log
-a---        2005-11-29   3:16 PM         97 acc1.txt
-a---        2005-10-23  11:21 PM       3848 actsetup.log
...
```

<span data-ttu-id="1fa83-110">一覧は、**Cmd.exe** で `dir` コマンドを入力したとき、または UNIX コマンド シェルで `ls` コマンドを入力したときに表示されるものと似ています。</span><span class="sxs-lookup"><span data-stu-id="1fa83-110">The listing looks similar to what you would see when you enter the `dir` command in **Cmd.exe**, or the `ls` command in a UNIX command shell.</span></span>

<span data-ttu-id="1fa83-111">`Get-ChildItem` コマンドレットのパラメーターを使用して、複雑な一覧表示を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1fa83-111">You can perform very complex listings by using parameters of the `Get-ChildItem` cmdlet.</span></span> <span data-ttu-id="1fa83-112">次に、いくつかのシナリオで見ていきます。</span><span class="sxs-lookup"><span data-stu-id="1fa83-112">We will look at a few scenarios next.</span></span> <span data-ttu-id="1fa83-113">`Get-ChildItem` コマンドレットの構文を確認するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-113">You can see the syntax the `Get-ChildItem` cmdlet by typing:</span></span>

```powershell
Get-Command -Name Get-ChildItem -Syntax
```

<span data-ttu-id="1fa83-114">これらのパラメーターは混在して利用でき、詳細にカスタマイズされた出力を取得するのに適しています。</span><span class="sxs-lookup"><span data-stu-id="1fa83-114">These parameters can be mixed and matched to get highly customized output.</span></span>

### <a name="listing-all-contained-items--recurse"></a><span data-ttu-id="1fa83-115">含まれるすべての項目の一覧表示 (-Recurse)</span><span class="sxs-lookup"><span data-stu-id="1fa83-115">Listing all Contained Items (-Recurse)</span></span>

<span data-ttu-id="1fa83-116">Windows フォルダー内の項目と、サブフォルダー内に含まれる項目の両方を表示するには、`Get-ChildItem` の **Recurse** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-116">To see both the items inside a Windows folder and any items that are contained within the subfolders, use the **Recurse** parameter of `Get-ChildItem`.</span></span> <span data-ttu-id="1fa83-117">一覧には、Windows フォルダー内のすべて、およびそのサブフォルダー内の項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fa83-117">The listing displays everything within the Windows folder and the items in its subfolders.</span></span> <span data-ttu-id="1fa83-118">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-118">For example:</span></span>

```
PS> Get-ChildItem -Path C:\WINDOWS -Recurse

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\WINDOWS
    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\WINDOWS\AppPatch
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM    1852416 AcGenral.dll
...
```

### <a name="filtering-items-by-name--name"></a><span data-ttu-id="1fa83-119">名前で項目をフィルター処理する (-名前)</span><span class="sxs-lookup"><span data-stu-id="1fa83-119">Filtering Items by Name (-Name)</span></span>

<span data-ttu-id="1fa83-120">項目の名前のみを表示するには、`Get-Childitem` の **Name** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-120">To display only the names of items, use the **Name** parameter of `Get-Childitem`:</span></span>

```
PS> Get-ChildItem -Path C:\WINDOWS -Name
addins
AppPatch
assembly
...
```

### <a name="forcibly-listing-hidden-items--force"></a><span data-ttu-id="1fa83-121">強制的に非表示のアイテムを一覧表示する (-Force)</span><span class="sxs-lookup"><span data-stu-id="1fa83-121">Forcibly Listing Hidden Items (-Force)</span></span>

<span data-ttu-id="1fa83-122">ファイル エクスプローラーまたは Cmd.exe で通常は非表示の項目は、`Get-ChildItem` コマンドの出力に表示されません。</span><span class="sxs-lookup"><span data-stu-id="1fa83-122">Items that are normally invisible in File Explorer or Cmd.exe are not displayed in the output of a `Get-ChildItem` command.</span></span> <span data-ttu-id="1fa83-123">非表示の項目を表示するには、`Get-ChildItem` の **Force** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-123">To display hidden items, use the **Force** parameter of `Get-ChildItem`.</span></span>
<span data-ttu-id="1fa83-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-124">For example:</span></span>

```powershell
Get-ChildItem -Path C:\Windows -Force
```

<span data-ttu-id="1fa83-125">このパラメーターが Force と呼ばれるのは、`Get-ChildItem` コマンドの通常の動作を強制的にオーバーライドできるためです。</span><span class="sxs-lookup"><span data-stu-id="1fa83-125">This parameter is named Force because you can forcibly override the normal behavior of the `Get-ChildItem` command.</span></span> <span data-ttu-id="1fa83-126">Force は、コマンドレットが通常は実行しないアクションを強制するために広く使用されるパラメーターですが、システムのセキュリティを侵害するアクションは実行しません。</span><span class="sxs-lookup"><span data-stu-id="1fa83-126">Force is a widely used parameter that forces an action that a cmdlet would not normally perform, although it will not perform any action that compromises the security of the system.</span></span>

### <a name="matching-item-names-with-wildcards"></a><span data-ttu-id="1fa83-127">ワイルドカードを使用した項目の名前のマッチング</span><span class="sxs-lookup"><span data-stu-id="1fa83-127">Matching Item Names with Wildcards</span></span>

<span data-ttu-id="1fa83-128">`Get-ChildItem` コマンドは、一覧表示する項目のパスでワイルドカードを受け付けます。</span><span class="sxs-lookup"><span data-stu-id="1fa83-128">The `Get-ChildItem` command accepts wildcards in the path of the items to list.</span></span>

<span data-ttu-id="1fa83-129">ワイルドカードのマッチングは Windows PowerShell のエンジンによって処理されるため、ワイルドカードを受け入れるすべてのコマンドレットは、同じ表記法を使用し、マッチングの動作も同じになります。</span><span class="sxs-lookup"><span data-stu-id="1fa83-129">Because wildcard matching is handled by the Windows PowerShell engine, all cmdlets that accepts wildcards use the same notation and have the same matching behavior.</span></span> <span data-ttu-id="1fa83-130">Windows PowerShell のワイルドカードの表記法は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1fa83-130">The Windows PowerShell wildcard notation includes:</span></span>

- <span data-ttu-id="1fa83-131">アスタリスク (`*`) は、任意の文字の 0 個以上の出現と照合します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-131">Asterisk (`*`) matches zero or more occurrences of any character.</span></span>

- <span data-ttu-id="1fa83-132">疑問符 (`?`) は、厳密に 1 つの文字と照合します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-132">Question mark (`?`) matches exactly one character.</span></span>

- <span data-ttu-id="1fa83-133">左角かっこ (`[`) 文字および右角かっこ (`]`) は、照合する文字のセットを囲みます。</span><span class="sxs-lookup"><span data-stu-id="1fa83-133">Left bracket (`[`) character and right bracket (`]`) character surround a set of characters to be matched.</span></span>

<span data-ttu-id="1fa83-134">ここでは、ワイルドカードを指定するとどのように機能するか、例を示します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-134">Here are some examples of how wildcard specification works.</span></span>

<span data-ttu-id="1fa83-135">Windows ディレクトリでサフィックス `.log` が使用され、基本名が正確に 5 文字であるすべてのファイルを検索するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-135">To find all files in the Windows directory with the suffix `.log` and exactly five characters in the base name, enter the following command:</span></span>

```
PS> Get-ChildItem -Path C:\Windows\?????.log

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
...
-a---        2006-05-11   6:31 PM     204276 ocgen.log
-a---        2006-05-11   6:31 PM      22365 ocmsn.log
...
-a---        2005-11-11   4:55 AM         64 setup.log
-a---        2005-12-15   2:24 PM      17719 VxSDM.log
...
```

<span data-ttu-id="1fa83-136">Windows ディレクトリで文字 `x` で始まるすべてのファイルを検索するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-136">To find all files that begin with the letter `x` in the Windows directory, type:</span></span>

```powershell
Get-ChildItem -Path C:\Windows\x*
```

<span data-ttu-id="1fa83-137">名前が "x" または "z" で始まるすべてのファイルを検索するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-137">To find all files whose names begin with "x" or "z", type:</span></span>

```powershell
Get-ChildItem -Path C:\Windows\[xz]*
```

<span data-ttu-id="1fa83-138">ワイルドカードの詳細については、「[about_Wildcards](/powershell/module/microsoft.powershell.core/about/about_wildcards)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fa83-138">For more information about wildcards, see [about_Wildcards](/powershell/module/microsoft.powershell.core/about/about_wildcards).</span></span>

### <a name="excluding-items--exclude"></a><span data-ttu-id="1fa83-139">項目の除外 (-Exclude)</span><span class="sxs-lookup"><span data-stu-id="1fa83-139">Excluding Items (-Exclude)</span></span>

<span data-ttu-id="1fa83-140">`Get-ChildItem` の **Exclude** パラメーターを使用して、特定の項目を除外できます。</span><span class="sxs-lookup"><span data-stu-id="1fa83-140">You can exclude specific items by using the **Exclude** parameter of `Get-ChildItem`.</span></span> <span data-ttu-id="1fa83-141">これにより、単一のステートメントで複雑なフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="1fa83-141">This lets you perform complex filtering in a single statement.</span></span>

<span data-ttu-id="1fa83-142">たとえば、**System32** フォルダーで Windows タイム サービスの DLL を検索しようとしていて、DLL の名前について覚えているのは、"W" で始まり "32" が含まれている、ということだけだとします。</span><span class="sxs-lookup"><span data-stu-id="1fa83-142">For example, suppose you are trying to find the Windows Time Service DLL in the **System32** folder, and all you can remember about the DLL name is that it begins with "W" and has "32" in it.</span></span>

<span data-ttu-id="1fa83-143">`w*32*.dll` のような式によって、条件を満たすすべての DLL が検索されますが、さらにファイルをフィルターで除外し、win32 ファイルを省略したい場合もあります。</span><span class="sxs-lookup"><span data-stu-id="1fa83-143">An expression like `w*32*.dll` will find all DLLs that satisfy the conditions, but you may want to further filter out the files and omit any win32 files.</span></span> <span data-ttu-id="1fa83-144">これらのファイルを省略するには、**Exclude** パラメーターにパターン `win*` を指定します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-144">You can omit these files by using the **Exclude** parameter with the pattern `win*`:</span></span>

```
PS> Get-ChildItem -Path C:\WINDOWS\System32\w*32*.dll -Exclude win*

    Directory: C:\WINDOWS\System32

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           3/18/2019  9:43 PM         495616 w32time.dll
-a---           3/18/2019  9:44 PM          35328 w32topl.dll
-a---           1/24/2020  5:44 PM         401920 Wldap32.dll
-a---          10/10/2019  5:40 PM         442704 ws2_32.dll
-a---           3/18/2019  9:44 PM          66048 wsnmp32.dll
-a---           3/18/2019  9:44 PM          18944 wsock32.dll
-a---           3/18/2019  9:44 PM          64792 wtsapi32.dll
```

### <a name="mixing-get-childitem-parameters"></a><span data-ttu-id="1fa83-145">Get-ChildItem パラメーターの混在</span><span class="sxs-lookup"><span data-stu-id="1fa83-145">Mixing Get-ChildItem Parameters</span></span>

<span data-ttu-id="1fa83-146">同じコマンドの中で、`Get-ChildItem` コマンドレットのパラメーターを複数使用できます。</span><span class="sxs-lookup"><span data-stu-id="1fa83-146">You can use several of the parameters of the `Get-ChildItem` cmdlet in the same command.</span></span> <span data-ttu-id="1fa83-147">パラメーターを混在させる前に、ワイルドカードのマッチングを理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="1fa83-147">Before you mix parameters, be sure that you understand wildcard matching.</span></span> <span data-ttu-id="1fa83-148">たとえば、次のコマンドは、結果を返しません。</span><span class="sxs-lookup"><span data-stu-id="1fa83-148">For example, the following command returns no results:</span></span>

```powershell
Get-ChildItem -Path C:\Windows\*.dll -Recurse -Exclude [a-y]*.dll
```

<span data-ttu-id="1fa83-149">Windows フォルダーに文字 "z" で始まる DLL が 2 つ存在しても、結果を返しません。</span><span class="sxs-lookup"><span data-stu-id="1fa83-149">There are no results, even though there are two DLLs that begin with the letter "z" in the Windows folder.</span></span>

<span data-ttu-id="1fa83-150">返される結果がないのは、パスの一部にワイルドカードを指定したためです。</span><span class="sxs-lookup"><span data-stu-id="1fa83-150">No results were returned because we specified the wildcard as part of the path.</span></span> <span data-ttu-id="1fa83-151">コマンドが再帰的でも、`Get-ChildItem` コマンドレットは、Windows フォルダー内にあり、名前が `.dll` で終わる項目に制限しています。</span><span class="sxs-lookup"><span data-stu-id="1fa83-151">Even though the command was recursive, the `Get-ChildItem` cmdlet restricted the items to those that are in the Windows folder with names ending with `.dll`.</span></span>

<span data-ttu-id="1fa83-152">名前が特殊なパターンに一致するファイルに対して再帰的な検索を指定するには、**Include** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="1fa83-152">To specify a recursive search for files whose names match a special pattern, use the **Include** parameter.</span></span>

```
PS> Get-ChildItem -Path C:\Windows -Include *.dll -Recurse -Exclude [a-y]*.dll

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows\System32\Setup

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM       8261 zoneoc.dll

    Directory: Microsoft.Windows PowerShell.Core\FileSystem::C:\Windows\System32

Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---        2004-08-04   8:00 AM     337920 zipfldr.dll
```
