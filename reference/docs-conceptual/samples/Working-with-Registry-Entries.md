---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: レジストリ エントリの操作
ms.assetid: fd254570-27ac-4cc9-81d4-011afd29b7dc
ms.openlocfilehash: bffdf80931fc4dc570b584623487077dc5d449dc
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403118"
---
# <a name="working-with-registry-entries"></a><span data-ttu-id="e75fa-103">レジストリ エントリの操作</span><span class="sxs-lookup"><span data-stu-id="e75fa-103">Working with Registry Entries</span></span>

<span data-ttu-id="e75fa-104">レジストリ エントリはキーのプロパティであり直接参照できないため、利用するときは少し異なる方法を取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="e75fa-104">Because registry entries are properties of keys and, as such, cannot be directly browsed, we need to take a slightly different approach when working with them.</span></span>

### <a name="listing-registry-entries"></a><span data-ttu-id="e75fa-105">レジストリ エントリの一覧表示</span><span class="sxs-lookup"><span data-stu-id="e75fa-105">Listing Registry Entries</span></span>

<span data-ttu-id="e75fa-106">レジストリ エントリを確認するには、多くのさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="e75fa-106">There are many different ways to examine registry entries.</span></span> <span data-ttu-id="e75fa-107">最も簡単な方法は、キーに関連付けられているプロパティの名前を取得することです。</span><span class="sxs-lookup"><span data-stu-id="e75fa-107">The simplest way is to get the property names associated with a key.</span></span> <span data-ttu-id="e75fa-108">たとえば、レジストリ キー **HKEY_LOCAL_MACHINE\\Software\\Microsoft\\Windows\\CurrentVersion** のエントリの名前を表示するには、**Get-Item** を使用します。</span><span class="sxs-lookup"><span data-stu-id="e75fa-108">For example, to see the names of the entries in the registry key **HKEY_LOCAL_MACHINE\\Software\\Microsoft\\Windows\\CurrentVersion**, use **Get-Item**.</span></span> <span data-ttu-id="e75fa-109">レジストリ キーは、キーのレジストリ エントリの一覧であり、"Property"という汎用的な名前のプロパティを持っています。</span><span class="sxs-lookup"><span data-stu-id="e75fa-109">Registry keys have a property with the generic name of "Property" that is a list of registry entries in the key.</span></span> <span data-ttu-id="e75fa-110">次のコマンドは、Property プロパティを選択し、一覧に表示されるように項目を拡張します。</span><span class="sxs-lookup"><span data-stu-id="e75fa-110">The following command selects the Property property and expands the items so that they are displayed in a list:</span></span>

```
PS> Get-Item -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion | Select-Object -ExpandProperty Property
DevicePath
MediaPathUnexpanded
ProgramFilesDir
CommonFilesDir
ProductId
```

<span data-ttu-id="e75fa-111">レジストリ エントリをさらに読みやすい形式で表示するには、**Get-ItemProperty** を使用します。</span><span class="sxs-lookup"><span data-stu-id="e75fa-111">To view the registry entries in a more readable form, use **Get-ItemProperty**:</span></span>

```
PS> Get-ItemProperty -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion

PSPath              : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SO
                      FTWARE\Microsoft\Windows\CurrentVersion
PSParentPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SO
                      FTWARE\Microsoft\Windows
PSChildName         : CurrentVersion
PSDrive             : HKLM
PSProvider          : Microsoft.PowerShell.Core\Registry
DevicePath          : C:\WINDOWS\inf
MediaPathUnexpanded : C:\WINDOWS\Media
ProgramFilesDir     : C:\Program Files
CommonFilesDir      : C:\Program Files\Common Files
ProductId           : 76487-338-1167776-22465
WallPaperDir        : C:\WINDOWS\Web\Wallpaper
MediaPath           : C:\WINDOWS\Media
ProgramFilesPath    : C:\Program Files
PF_AccessoriesName  : Accessories
(default)           :
```

<span data-ttu-id="e75fa-112">キーの Windows PowerShell 関連のプロパティには、**PSPath**、**PSParentPath**、**PSChildName**、および **PSProvider** のように、すべて先頭に "PS" が付きます。</span><span class="sxs-lookup"><span data-stu-id="e75fa-112">The Windows PowerShell-related properties for the key are all prefixed with "PS", such as **PSPath**, **PSParentPath**, **PSChildName**, and **PSProvider**.</span></span>

<span data-ttu-id="e75fa-113">現在の場所を参照するには、"**.**" 表記法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e75fa-113">You can use the "**.**" notation for referring to the current location.</span></span> <span data-ttu-id="e75fa-114">**Set-Location** を使用して、まず **CurrentVersion** レジストリのコンテナーに移動します。</span><span class="sxs-lookup"><span data-stu-id="e75fa-114">You can use **Set-Location** to change to the **CurrentVersion** registry container first:</span></span>

```powershell
Set-Location -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
```

<span data-ttu-id="e75fa-115">または、**Set-Location** を指定して組み込みの HKLM PSDrive を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e75fa-115">Alternatively, you can use the built-in HKLM PSDrive with **Set-Location**:</span></span>

```powershell
Set-Location -Path hklm:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

<span data-ttu-id="e75fa-116">現在の場所に対して "**.**" 表記法を使用して、完全パスを指定しないでプロパティの一覧を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="e75fa-116">You can then use the "**.**" notation for the current location to list the properties without specifying a full path:</span></span>

```
PS> Get-ItemProperty -Path .
...
DevicePath          : C:\WINDOWS\inf
MediaPathUnexpanded : C:\WINDOWS\Media
ProgramFilesDir     : C:\Program Files
...
```

<span data-ttu-id="e75fa-117">パスの展開は、ファイル システム内と同様に機能するので、この場所からは、**GetItemProperty Path ..\\Help** を使用して **HKLM:\\SOFTWARE\\Microsoft\\Windows\\Help** の **ItemProperty** の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="e75fa-117">Path expansion works the same as it does within the file system, so from this location you can get the **ItemProperty** listing for **HKLM:\\SOFTWARE\\Microsoft\\Windows\\Help** by using **Get-ItemProperty -Path ..\\Help**.</span></span>

### <a name="getting-a-single-registry-entry"></a><span data-ttu-id="e75fa-118">1 つのレジストリ エントリの取得</span><span class="sxs-lookup"><span data-stu-id="e75fa-118">Getting a Single Registry Entry</span></span>

<span data-ttu-id="e75fa-119">レジストリ キーの特定のエントリを取得する場合は、いくつかの可能なアプローチのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e75fa-119">If you want to retrieve a specific entry in a registry key, you can use one of several possible approaches.</span></span> <span data-ttu-id="e75fa-120">この例では、**HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion** の **DevicePath** の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="e75fa-120">This example finds the value of **DevicePath** in **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion**.</span></span>

<span data-ttu-id="e75fa-121">**Get-ItemProperty** を使用する場合に、**Path** パラメーターを使用してキーの名前を指定し、**Name** パラメーターを使用して **DevicePath** のエントリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e75fa-121">Using **Get-ItemProperty**, use the **Path** parameter to specify the name of the key, and the **Name** parameter to specify the name of the **DevicePath** entry.</span></span>

```
PS> Get-ItemProperty -Path HKLM:\Software\Microsoft\Windows\CurrentVersion -Name DevicePath

PSPath       : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\
               Microsoft\Windows\CurrentVersion
PSParentPath : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\
               Microsoft\Windows
PSChildName  : CurrentVersion
PSDrive      : HKLM
PSProvider   : Microsoft.PowerShell.Core\Registry
DevicePath   : C:\WINDOWS\inf
```

<span data-ttu-id="e75fa-122">このコマンドは、標準の Windows PowerShell のプロパティと **DevicePath** プロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="e75fa-122">This command returns the standard Windows PowerShell properties as well as the **DevicePath** property.</span></span>

> [!NOTE]
> <span data-ttu-id="e75fa-123">**Get-ItemProperty** に **Filter**、**Include**、**Exclude** の各パラメーターがあっても、プロパティ名によるフィルター処理に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e75fa-123">Although **Get-ItemProperty** has **Filter**, **Include**, and **Exclude** parameters, they cannot be used to filter by property name.</span></span> <span data-ttu-id="e75fa-124">これらのパラメーターはレジストリ キー (項目のパス) を参照し、レジストリ エントリ (項目のプロパティ) を参照するのではありません。</span><span class="sxs-lookup"><span data-stu-id="e75fa-124">These parameters refer to registry keys—which are item paths—and not registry entries—which are item properties.</span></span>

<span data-ttu-id="e75fa-125">別のオプションとして、Reg.exe コマンド ライン ツールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e75fa-125">Another option is to use the Reg.exe command line tool.</span></span> <span data-ttu-id="e75fa-126">reg.exe のヘルプを表示するには、コマンド プロンプトで「**reg.exe /?**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e75fa-126">For help with reg.exe, type **reg.exe /?**</span></span> <span data-ttu-id="e75fa-127">at a command prompt.</span><span class="sxs-lookup"><span data-stu-id="e75fa-127">at a command prompt.</span></span> <span data-ttu-id="e75fa-128">DevicePath エントリを検索するには、次のコマンドに示すように reg.exe を使用します。</span><span class="sxs-lookup"><span data-stu-id="e75fa-128">To find the DevicePath entry, use reg.exe as shown in the following command:</span></span>

```
PS> reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion /v DevicePath

! REG.EXE VERSION 3.0

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
    DevicePath  REG_EXPAND_SZ   %SystemRoot%\inf
```

<span data-ttu-id="e75fa-129">また、**WshShell COM** オブジェクトを使用していくつかのレジストリ エントリを検索することもできますが、この方法は、大きなバイナリ データや、名前に "\\" を含むレジストリ エントリでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="e75fa-129">You can also use the **WshShell COM** object as well to find some registry entries, although this method does not work with large binary data or with registry entry names that include characters such as "\\").</span></span> <span data-ttu-id="e75fa-130">プロパティ名を区切り記号 \\ と共に項目のパスに追加します。</span><span class="sxs-lookup"><span data-stu-id="e75fa-130">Append the property name to the item path with a \\ separator:</span></span>

```
PS> (New-Object -ComObject WScript.Shell).RegRead("HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\DevicePath")
%SystemRoot%\inf
```

### <a name="creating-new-registry-entries"></a><span data-ttu-id="e75fa-131">新しいレジストリ エントリの作成</span><span class="sxs-lookup"><span data-stu-id="e75fa-131">Creating New Registry Entries</span></span>

<span data-ttu-id="e75fa-132">"PowerShellPath" という名前の新しいエントリを **CurrentVersion** キーに追加するには、キーのパス、エントリ名、エントリの値を指定して **New-ItemProperty** を使用します。</span><span class="sxs-lookup"><span data-stu-id="e75fa-132">To add a new entry named "PowerShellPath" to the **CurrentVersion** key, use **New-ItemProperty** with the path to the key, the entry name, and the value of the entry.</span></span> <span data-ttu-id="e75fa-133">この例では、Windows PowerShell の変数 **$PSHome** の値を取得します。これは、Windows PowerShell のインストール ディレクトリへのパスを保存します。</span><span class="sxs-lookup"><span data-stu-id="e75fa-133">For this example, we will take the value of the Windows PowerShell variable **$PSHome**, which stores the path to the installation directory for Windows PowerShell.</span></span>

<span data-ttu-id="e75fa-134">キーに新しいエントリを追加するには、次のコマンドを使用します。このコマンドは、新しいエントリに関する情報も返します。</span><span class="sxs-lookup"><span data-stu-id="e75fa-134">You can add the new entry to the key by using the following command, and the command also returns information about the new entry:</span></span>

```
PS> New-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -PropertyType String -Value $PSHome

PSPath         : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWAR
                 E\Microsoft\Windows\CurrentVersion
PSParentPath   : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWAR
                 E\Microsoft\Windows
PSChildName    : CurrentVersion
PSDrive        : HKLM
PSProvider     : Microsoft.PowerShell.Core\Registry
PowerShellPath : C:\Program Files\Windows PowerShell\v1.0
```

<span data-ttu-id="e75fa-135">**PropertyType** は、次の表の **Microsoft.Win32.RegistryValueKind** 列挙体のメンバーの名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e75fa-135">The **PropertyType** must be the name of a **Microsoft.Win32.RegistryValueKind** enumeration member from the following table:</span></span>

|<span data-ttu-id="e75fa-136">PropertyType の値</span><span class="sxs-lookup"><span data-stu-id="e75fa-136">PropertyType Value</span></span>|<span data-ttu-id="e75fa-137">意味</span><span class="sxs-lookup"><span data-stu-id="e75fa-137">Meaning</span></span>|
|----------------------|-----------|
|<span data-ttu-id="e75fa-138">Binary</span><span class="sxs-lookup"><span data-stu-id="e75fa-138">Binary</span></span>|<span data-ttu-id="e75fa-139">バイナリ データ</span><span class="sxs-lookup"><span data-stu-id="e75fa-139">Binary data</span></span>|
|<span data-ttu-id="e75fa-140">DWord</span><span class="sxs-lookup"><span data-stu-id="e75fa-140">DWord</span></span>|<span data-ttu-id="e75fa-141">有効な UInt32 である数字</span><span class="sxs-lookup"><span data-stu-id="e75fa-141">A number that is a valid UInt32</span></span>|
|<span data-ttu-id="e75fa-142">ExpandString</span><span class="sxs-lookup"><span data-stu-id="e75fa-142">ExpandString</span></span>|<span data-ttu-id="e75fa-143">動的に展開される環境変数を含むことができる文字列</span><span class="sxs-lookup"><span data-stu-id="e75fa-143">A string that can contain environment variables that are dynamically expanded</span></span>|
|<span data-ttu-id="e75fa-144">MultiString</span><span class="sxs-lookup"><span data-stu-id="e75fa-144">MultiString</span></span>|<span data-ttu-id="e75fa-145">複数行文字列</span><span class="sxs-lookup"><span data-stu-id="e75fa-145">A multiline string</span></span>|
|<span data-ttu-id="e75fa-146">String</span><span class="sxs-lookup"><span data-stu-id="e75fa-146">String</span></span>|<span data-ttu-id="e75fa-147">任意の文字列値</span><span class="sxs-lookup"><span data-stu-id="e75fa-147">Any string value</span></span>|
|<span data-ttu-id="e75fa-148">QWord</span><span class="sxs-lookup"><span data-stu-id="e75fa-148">QWord</span></span>|<span data-ttu-id="e75fa-149">8 バイトのバイナリ データ</span><span class="sxs-lookup"><span data-stu-id="e75fa-149">8 bytes of binary data</span></span>|

> [!NOTE]
> <span data-ttu-id="e75fa-150">**Path** パラメーターに値の配列を指定して、レジストリ エントリを複数の場所に追加できます。</span><span class="sxs-lookup"><span data-stu-id="e75fa-150">You can add a registry entry to multiple locations by specifying an array of values for the **Path** parameter:</span></span>

```powershell
New-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion, HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -PropertyType String -Value $PSHome
```

<span data-ttu-id="e75fa-151">また、**Force** パラメーターを **New-ItemProperty** コマンドに追加して、既存のレジストリ エントリの値を上書きすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e75fa-151">You can also overwrite a pre-existing registry entry value by adding the **Force** parameter to any **New-ItemProperty** command.</span></span>

### <a name="renaming-registry-entries"></a><span data-ttu-id="e75fa-152">レジストリ エントリの名前変更</span><span class="sxs-lookup"><span data-stu-id="e75fa-152">Renaming Registry Entries</span></span>

<span data-ttu-id="e75fa-153">**PowerShellPath** エントリの名前を "PSHome" に変更するには、**Rename-ItemProperty** を使用します。</span><span class="sxs-lookup"><span data-stu-id="e75fa-153">To rename the **PowerShellPath** entry to "PSHome," use **Rename-ItemProperty**:</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -NewName PSHome
```

<span data-ttu-id="e75fa-154">名前が変更された値を表示するには、**PassThru** パラメーターをコマンドに追加します。</span><span class="sxs-lookup"><span data-stu-id="e75fa-154">To display the renamed value, add the **PassThru** parameter to the command.</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -NewName PSHome -passthru
```

### <a name="deleting-registry-entries"></a><span data-ttu-id="e75fa-155">レジストリ エントリの削除</span><span class="sxs-lookup"><span data-stu-id="e75fa-155">Deleting Registry Entries</span></span>

<span data-ttu-id="e75fa-156">PSHome と PowerShellPath の両方のレジストリ エントリを削除するには、**Remove-ItemProperty** を使用します。</span><span class="sxs-lookup"><span data-stu-id="e75fa-156">To delete both the PSHome and PowerShellPath registry entries, use **Remove-ItemProperty**:</span></span>

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PSHome
Remove-ItemProperty -Path HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath
```