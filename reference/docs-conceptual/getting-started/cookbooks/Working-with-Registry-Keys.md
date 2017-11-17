---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "レジストリ キーの操作"
ms.assetid: 91bfaecd-8684-48b4-ad86-065dfe6dc90a
ms.openlocfilehash: efb2c016afa2212c2907c0740ad26c4e4cddd3af
ms.sourcegitcommit: 74255f0b5f386a072458af058a15240140acb294
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2017
---
# <a name="working-with-registry-keys"></a><span data-ttu-id="58b1a-103">レジストリ キーの操作</span><span class="sxs-lookup"><span data-stu-id="58b1a-103">Working with Registry Keys</span></span>
<span data-ttu-id="58b1a-104">レジストリ キーは Windows PowerShell ドライブ上の項目であるため、それらの操作はファイルやフォルダーの操作によく似ています。</span><span class="sxs-lookup"><span data-stu-id="58b1a-104">Because registry keys are items on Windows PowerShell drives, working with them is very similar to working with files and folders.</span></span> <span data-ttu-id="58b1a-105">1 つの決定的な違いは、レジストリ ベースの Windows PowerShell ドライブ上のすべての項目は、ファイル システム ドライブ上のフォルダーと同じように、コンテナーであることです。</span><span class="sxs-lookup"><span data-stu-id="58b1a-105">One critical difference is that every item on a registry-based Windows PowerShell drive is a container, just like a folder on a file system drive.</span></span> <span data-ttu-id="58b1a-106">ただし、レジストリ エントリとそれに関連する値は、個別の項目ではなく、項目のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="58b1a-106">However, registry entries and their associated values are properties of the items, not distinct items.</span></span>

### <a name="listing-all-subkeys-of-a-registry-key"></a><span data-ttu-id="58b1a-107">レジストリ キーのすべてのサブキーを一覧表示</span><span class="sxs-lookup"><span data-stu-id="58b1a-107">Listing All Subkeys of a Registry Key</span></span>
<span data-ttu-id="58b1a-108">**Get-ChildItem** を使用することにより、レジストリ キーの直下にあるすべての項目を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="58b1a-108">You can show all items directly within a registry key by using **Get-ChildItem**.</span></span> <span data-ttu-id="58b1a-109">非表示の項目やシステム項目を表示するには、オプションの **Force** パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="58b1a-109">Add the optional **Force** parameter to display hidden or system items.</span></span> <span data-ttu-id="58b1a-110">たとえば、次のコマンドは、HKEY_CURRENT_USER レジストリ ハイブに対応する、Windows PowerShell ドライブ HKCU: の直下にある項目を表示します。</span><span class="sxs-lookup"><span data-stu-id="58b1a-110">For example, this command displays the items directly within Windows PowerShell drive HKCU:, which corresponds to the HKEY_CURRENT_USER registry hive:</span></span>

```
PS> Get-ChildItem -Path hkcu:\

   Hive: Microsoft.PowerShell.Core\Registry::HKEY_CURRENT_USER

SKC  VC Name                           Property
---  -- ----                           --------
  2   0 AppEvents                      {}
  7  33 Console                        {ColorTable00, ColorTable01, ColorTab...
 25   1 Control Panel                  {Opened}
  0   5 Environment                    {APR_ICONV_PATH, INCLUDE, LIB, TEMP...}
  1   7 Identities                     {Last Username, Last User ...
  4   0 Keyboard Layout                {}
...
```

<span data-ttu-id="58b1a-111">これらは、レジストリ エディター (Regedit.exe) 内の HKEY_CURRENT_USER の下に表示される最上位キーです。</span><span class="sxs-lookup"><span data-stu-id="58b1a-111">These are the top-level keys visible under HKEY_CURRENT_USER in the Registry Editor (Regedit.exe).</span></span>

<span data-ttu-id="58b1a-112">レジストリ プロバイダーの名前とその後に "**::**" を指定することにより、このレジストリ パスを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="58b1a-112">You can also specify this registry path by specifying the registry provider's name, followed by "**::**".</span></span> <span data-ttu-id="58b1a-113">レジストリ プロバイダーの完全名は **Microsoft.PowerShell.Core\\Registry** ですが、短縮して **Registry** だけにすることができます。</span><span class="sxs-lookup"><span data-stu-id="58b1a-113">The registry provider's full name is **Microsoft.PowerShell.Core\\Registry**, but this can be shortened to just **Registry**.</span></span> <span data-ttu-id="58b1a-114">次のいずれのコマンドを使用しても、HKCU の直下にある内容を一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="58b1a-114">Any of the following commands will list the contents directly under HKCU:</span></span>

```
Get-ChildItem -Path Registry::HKEY_CURRENT_USER
Get-ChildItem -Path Microsoft.PowerShell.Core\Registry::HKEY_CURRENT_USER
Get-ChildItem -Path Registry::HKCU
Get-ChildItem -Path Microsoft.PowerShell.Core\Registry::HKCU
Get-ChildItem HKCU:
```

<span data-ttu-id="58b1a-115">これらのコマンドは、Cmd.exe の **DIR** コマンドや UNIX シェルの **ls** を使用したときと同様に、直接含まれている項目のみ一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="58b1a-115">These commands list only the directly contained items, much like using Cmd.exe's **DIR** command or **ls** in a UNIX shell.</span></span> <span data-ttu-id="58b1a-116">内包されている項目を表示するには、**Recurse** パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58b1a-116">To show contained items, you need to specify the **Recurse** parameter.</span></span> <span data-ttu-id="58b1a-117">HKCU 内のすべてのレジストリ キーを一覧表示するには、次のコマンドを使用します (この操作は、非常に長い時間がかかることがあります)。</span><span class="sxs-lookup"><span data-stu-id="58b1a-117">To list all registry keys in HKCU, use the following command (This operation can take an extremely long time.):</span></span>

```
Get-ChildItem -Path hkcu:\ -Recurse
```

<span data-ttu-id="58b1a-118">**Get-ChildItem** は、**Path**、**Filter**、**Include**、**Exclude** の各パラメーターを使用して複雑なフィルター処理機能を実行できますが、これらのパラメーターは通常、名前にのみ基づいています。</span><span class="sxs-lookup"><span data-stu-id="58b1a-118">**Get-ChildItem** can perform complex filtering capabilities through its **Path**, **Filter**, **Include**, and **Exclude** parameters, but those parameters are typically based only on name.</span></span> <span data-ttu-id="58b1a-119">**Where-Object** コマンドレットを使用することにより、項目の他のプロパティに基づいた複雑なフィルター処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="58b1a-119">You can perform complex filtering based on other properties of items by using the **Where-Object**cmdlet.</span></span> <span data-ttu-id="58b1a-120">次のコマンドは、1 つのサブキーと 4 つの値を持つ、HKCU:\\Software 内のすべてのキーを検索します。</span><span class="sxs-lookup"><span data-stu-id="58b1a-120">The following command finds all keys within HKCU:\\Software that have no more than one subkey and also have exactly four values:</span></span>

```
Get-ChildItem -Path HKCU:\Software -Recurse | Where-Object -FilterScript {($_.SubKeyCount -le 1) -and ($_.ValueCount -eq 4) }
```

### <a name="copying-keys"></a><span data-ttu-id="58b1a-121">キーのコピー</span><span class="sxs-lookup"><span data-stu-id="58b1a-121">Copying Keys</span></span>
<span data-ttu-id="58b1a-122">コピーは **Copy-Item** を使用して行われます。</span><span class="sxs-lookup"><span data-stu-id="58b1a-122">Copying is done with **Copy-Item**.</span></span> <span data-ttu-id="58b1a-123">次のコマンドは、HKLM:\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion とそのすべてのプロパティを HKCU:\\ にコピーして、"CurrentVersion" という名前の新しいキーを作成します。</span><span class="sxs-lookup"><span data-stu-id="58b1a-123">The following command copies HKLM:\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion and all of its properties to HKCU:\\, creating a new key named "CurrentVersion":</span></span>

```
Copy-Item -Path 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion' -Destination hkcu:
```

<span data-ttu-id="58b1a-124">レジストリ エディター内、または **Get-ChildItem** を使用してこの新しいキーを調べると、格納されているサブキーのコピーが新しい場所に存在しないことがわかります。</span><span class="sxs-lookup"><span data-stu-id="58b1a-124">If you examine this new key in the registry editor or by using **Get-ChildItem**, you will notice that you do not have copies of the contained subkeys in the new location.</span></span> <span data-ttu-id="58b1a-125">コンテナーのすべての内容をコピーするために、**Recurse** パラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58b1a-125">In order to copy all of the contents of a container, you need to specify the **Recurse** parameter.</span></span> <span data-ttu-id="58b1a-126">上記のコピー コマンドを再帰的に実行するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="58b1a-126">To make the preceding copy command recursive, you would use this command:</span></span>

```
Copy-Item -Path 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion' -Destination hkcu: -Recurse
```

<span data-ttu-id="58b1a-127">ファイル システムのコピーは、使用可能な他の既存のツールを使用して行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="58b1a-127">You can still use other tools you already have available to perform filesystem copies.</span></span> <span data-ttu-id="58b1a-128">任意のレジストリ編集ツール (reg.exe、regini.exe、regedit.exe など) およびレジストリの編集をサポートする COM オブジェクト (WScript.Shell や WMI の StdRegProv クラスなど) を Windows PowerShell 内から使用できます。</span><span class="sxs-lookup"><span data-stu-id="58b1a-128">Any registry editing tools—including reg.exe, regini.exe, and regedit.exe—and COM objects that support registry editing (such as WScript.Shell and WMI's StdRegProv class) can be used from within Windows PowerShell.</span></span>

### <a name="creating-keys"></a><span data-ttu-id="58b1a-129">キーの作成</span><span class="sxs-lookup"><span data-stu-id="58b1a-129">Creating Keys</span></span>
<span data-ttu-id="58b1a-130">レジストリでのキーの新規作成は、ファイル システムに新しい項目を作成するよりも簡単です。</span><span class="sxs-lookup"><span data-stu-id="58b1a-130">Creating new keys in the registry is simpler than creating a new item in a file system.</span></span> <span data-ttu-id="58b1a-131">すべてのレジストリ キーはコンテナーであるため、項目の種類を指定する必要はなく、次に示すように、明示的なパスを指定するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="58b1a-131">Because all registry keys are containers, you do not need to specify the item type; you simply supply an explicit path, such as:</span></span>

```
New-Item -Path hkcu:\software_DeleteMe
```

<span data-ttu-id="58b1a-132">また、プロバイダーに基づくパスを使用して、キーを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="58b1a-132">You can also use a provider-based path to specify a key:</span></span>

```
New-Item -Path Registry::HKCU_DeleteMe
```

### <a name="deleting-keys"></a><span data-ttu-id="58b1a-133">キーの削除</span><span class="sxs-lookup"><span data-stu-id="58b1a-133">Deleting Keys</span></span>
<span data-ttu-id="58b1a-134">項目の削除は、基本的にすべてのプロバイダーで同じです。</span><span class="sxs-lookup"><span data-stu-id="58b1a-134">Deleting items is essentially the same for all providers.</span></span> <span data-ttu-id="58b1a-135">次のコマンドを実行すると、確認を求められずに項目が削除されます。</span><span class="sxs-lookup"><span data-stu-id="58b1a-135">The following commands will silently remove items:</span></span>

```
Remove-Item -Path hkcu:\Software_DeleteMe
Remove-Item -Path 'hkcu:\key with spaces in the name'
```

### <a name="removing-all-keys-under-a-specific-key"></a><span data-ttu-id="58b1a-136">特定のキーの下にあるすべてのキーの削除</span><span class="sxs-lookup"><span data-stu-id="58b1a-136">Removing All Keys Under a Specific Key</span></span>
<span data-ttu-id="58b1a-137">内包されている項目を削除するには、**Remove-Item** を使用します。ただし、その項目に他の何らかの項目が含まれている場合は、削除の確認を求められます。</span><span class="sxs-lookup"><span data-stu-id="58b1a-137">You can remove contained items by using **Remove-Item**, but you will be prompted to confirm the removal if the item contains anything else.</span></span> <span data-ttu-id="58b1a-138">たとえば、作成した HKCU:\\CurrentVersion サブキーを削除しようとしすると、次のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="58b1a-138">For example, if we attempt to delete the HKCU:\\CurrentVersion subkey we created, we see this:</span></span>

```
Remove-Item -Path hkcu:\CurrentVersion

Confirm
The item at HKCU:\CurrentVersion\AdminDebug has children and the -recurse
parameter was not specified. If you continue, all children will be removed with
 the item. Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):
```

<span data-ttu-id="58b1a-139">確認のメッセージを表示せずに、内包されている項目を削除するには、**-Recurse** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="58b1a-139">To delete contained items without prompting, specify the **-Recurse** parameter:</span></span>

```
Remove-Item -Path HKCU:\CurrentVersion -Recurse
```

<span data-ttu-id="58b1a-140">HKCU:\\CurrentVersion 内のすべての項目を削除するものの、HKCU:\\CurrentVersion そのものは削除しない場合は、代わりに次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="58b1a-140">If you wanted to remove all items within HKCU:\\CurrentVersion but not HKCU:\\CurrentVersion itself, you could instead use:</span></span>

```
Remove-Item -Path HKCU:\CurrentVersion\* -Recurse
```

