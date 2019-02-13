---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: レジストリ エントリの操作
ms.assetid: fd254570-27ac-4cc9-81d4-011afd29b7dc
ms.openlocfilehash: 8483b6f98739697b24a13055dfffbc7b5bacc2cc
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "55681541"
---
# <a name="working-with-registry-entries"></a><span data-ttu-id="88fc1-103">レジストリ エントリの操作</span><span class="sxs-lookup"><span data-stu-id="88fc1-103">Working with Registry Entries</span></span>

<span data-ttu-id="88fc1-104">レジストリ エントリはキーのプロパティであり直接参照できないため、利用するときは少し異なる方法を取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="88fc1-104">Because registry entries are properties of keys and, as such, cannot be directly browsed, we need to take a slightly different approach when working with them.</span></span>

### <a name="listing-registry-entries"></a><span data-ttu-id="88fc1-105">レジストリ エントリの一覧表示</span><span class="sxs-lookup"><span data-stu-id="88fc1-105">Listing Registry Entries</span></span>

<span data-ttu-id="88fc1-106">レジストリ エントリを確認するには、多くのさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="88fc1-106">There are many different ways to examine registry entries.</span></span> <span data-ttu-id="88fc1-107">最も簡単な方法は、キーに関連付けられているプロパティの名前を取得することです。</span><span class="sxs-lookup"><span data-stu-id="88fc1-107">The simplest way is to get the property names associated with a key.</span></span> <span data-ttu-id="88fc1-108">たとえば、レジストリ キー内のエントリの名前を表示する`HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion`を使用して、`Get-Item`します。</span><span class="sxs-lookup"><span data-stu-id="88fc1-108">For example, to see the names of the entries in the registry key `HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion`, use `Get-Item`.</span></span> <span data-ttu-id="88fc1-109">レジストリ キーは、キーのレジストリ エントリの一覧であり、"Property"という汎用的な名前のプロパティを持っています。</span><span class="sxs-lookup"><span data-stu-id="88fc1-109">Registry keys have a property with the generic name of "Property" that is a list of registry entries in the key.</span></span>
<span data-ttu-id="88fc1-110">次のコマンドは、Property プロパティを選択し、一覧に表示されるように項目を拡張します。</span><span class="sxs-lookup"><span data-stu-id="88fc1-110">The following command selects the Property property and expands the items so that they are displayed in a list:</span></span>

```powershell
Get-Item -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion |
  Select-Object -ExpandProperty Property
```

```Output
DevicePath
MediaPathUnexpanded
ProgramFilesDir
CommonFilesDir
ProductId
```

<span data-ttu-id="88fc1-111">読みやすい形式でレジストリ エントリを表示するには使用`Get-ItemProperty`:</span><span class="sxs-lookup"><span data-stu-id="88fc1-111">To view the registry entries in a more readable form, use `Get-ItemProperty`:</span></span>

```powershell
Get-ItemProperty -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
```

```Output
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

<span data-ttu-id="88fc1-112">キーの Windows PowerShell 関連のプロパティには、**PSPath**、**PSParentPath**、**PSChildName**、および **PSProvider** のように、すべて先頭に "PS" が付きます。</span><span class="sxs-lookup"><span data-stu-id="88fc1-112">The Windows PowerShell-related properties for the key are all prefixed with "PS", such as **PSPath**, **PSParentPath**, **PSChildName**, and **PSProvider**.</span></span>

<span data-ttu-id="88fc1-113">現在の場所を参照するには、"`*.*`." 表記法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="88fc1-113">You can use the `*.*` notation for referring to the current location.</span></span> <span data-ttu-id="88fc1-114">使用することができます`Set-Location`に変更する、 **CurrentVersion**レジストリのコンテナー最初。</span><span class="sxs-lookup"><span data-stu-id="88fc1-114">You can use `Set-Location` to change to the **CurrentVersion** registry container first:</span></span>

```powershell
Set-Location -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
```

<span data-ttu-id="88fc1-115">組み込みの HKLM PSDrive を使用する代わりに、 `Set-Location`:</span><span class="sxs-lookup"><span data-stu-id="88fc1-115">Alternatively, you can use the built-in HKLM PSDrive with `Set-Location`:</span></span>

```powershell
Set-Location -Path hklm:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

<span data-ttu-id="88fc1-116">現在の場所に対して "`*.*`." 表記法を使用して、完全パスを指定しないでプロパティの一覧を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="88fc1-116">You can then use the `*.*` notation for the current location to list the properties without specifying a full path:</span></span>

```powershell
Get-ItemProperty -Path .
```

```Output
...
DevicePath          : C:\WINDOWS\inf
MediaPathUnexpanded : C:\WINDOWS\Media
ProgramFilesDir     : C:\Program Files
...
```

<span data-ttu-id="88fc1-117">この場所から取得できるように、ファイル システム内と同じパスの展開動作、 **ItemProperty**の`HKLM:\SOFTWARE\Microsoft\Windows\Help`を使用して`Get-ItemProperty -Path ..\Help`します。</span><span class="sxs-lookup"><span data-stu-id="88fc1-117">Path expansion works the same as it does within the file system, so from this location you can get the **ItemProperty** listing for `HKLM:\SOFTWARE\Microsoft\Windows\Help` by using `Get-ItemProperty -Path ..\Help`.</span></span>

### <a name="getting-a-single-registry-entry"></a><span data-ttu-id="88fc1-118">1 つのレジストリ エントリの取得</span><span class="sxs-lookup"><span data-stu-id="88fc1-118">Getting a Single Registry Entry</span></span>

<span data-ttu-id="88fc1-119">レジストリ キーの特定のエントリを取得する場合は、いくつかの可能なアプローチのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="88fc1-119">If you want to retrieve a specific entry in a registry key, you can use one of several possible approaches.</span></span> <span data-ttu-id="88fc1-120">この例の値を検索する**DevicePath**で`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`します。</span><span class="sxs-lookup"><span data-stu-id="88fc1-120">This example finds the value of **DevicePath** in `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span></span>

<span data-ttu-id="88fc1-121">使用して`Get-ItemProperty`を使用して、**パス**、キーの名前を指定するパラメーター、および**名前**の名前を指定するパラメーター、 **DevicePath**エントリ。</span><span class="sxs-lookup"><span data-stu-id="88fc1-121">Using `Get-ItemProperty`, use the **Path** parameter to specify the name of the key, and the **Name** parameter to specify the name of the **DevicePath** entry.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\Software\Microsoft\Windows\CurrentVersion -Name DevicePath
```

```Output
PSPath       : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\
               Microsoft\Windows\CurrentVersion
PSParentPath : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\
               Microsoft\Windows
PSChildName  : CurrentVersion
PSDrive      : HKLM
PSProvider   : Microsoft.PowerShell.Core\Registry
DevicePath   : C:\WINDOWS\inf
```

<span data-ttu-id="88fc1-122">このコマンドは、標準の Windows PowerShell のプロパティと **DevicePath** プロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="88fc1-122">This command returns the standard Windows PowerShell properties as well as the **DevicePath** property.</span></span>

> [!NOTE]
> <span data-ttu-id="88fc1-123">`Get-ItemProperty`が**フィルター**、 **Include**、および**除外**パラメーター、プロパティ名でフィルター処理には使用できません。</span><span class="sxs-lookup"><span data-stu-id="88fc1-123">Although `Get-ItemProperty` has **Filter**, **Include**, and **Exclude** parameters, they cannot be used to filter by property name.</span></span> <span data-ttu-id="88fc1-124">これらのパラメーターは、項目のパスは、レジストリ エントリではないレジストリ キーを参照してください。</span><span class="sxs-lookup"><span data-stu-id="88fc1-124">These parameters refer to registry keys, which are item paths and not registry entries.</span></span> <span data-ttu-id="88fc1-125">項目のプロパティのレジストリ エントリ。</span><span class="sxs-lookup"><span data-stu-id="88fc1-125">Registry entries which are item properties.</span></span>

<span data-ttu-id="88fc1-126">別のオプションとして、Reg.exe コマンド ライン ツールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="88fc1-126">Another option is to use the Reg.exe command line tool.</span></span> <span data-ttu-id="88fc1-127">Reg.exe のヘルプを表示するには、入力`reg.exe /?`コマンド プロンプトでします。</span><span class="sxs-lookup"><span data-stu-id="88fc1-127">For help with reg.exe, type `reg.exe /?` at a command prompt.</span></span> <span data-ttu-id="88fc1-128">DevicePath エントリを検索するには、次のコマンドに示すように reg.exe を使用します。</span><span class="sxs-lookup"><span data-stu-id="88fc1-128">To find the DevicePath entry, use reg.exe as shown in the following command:</span></span>

```powershell
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion /v DevicePath
```

```Output
! REG.EXE VERSION 3.0

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
    DevicePath  REG_EXPAND_SZ   %SystemRoot%\inf
```

<span data-ttu-id="88fc1-129">また、**WshShell COM** オブジェクトを使用していくつかのレジストリ エントリを検索することもできますが、この方法は、大きなバイナリ データや、名前に "\\" を含むレジストリ エントリでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="88fc1-129">You can also use the **WshShell** COM object as well to find some registry entries, although this method does not work with large binary data or with registry entry names that include characters such as "\\").</span></span> <span data-ttu-id="88fc1-130">プロパティ名を区切り記号 \\ と共に項目のパスに追加します。</span><span class="sxs-lookup"><span data-stu-id="88fc1-130">Append the property name to the item path with a \\ separator:</span></span>

```powershell
(New-Object -ComObject WScript.Shell).RegRead("HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\DevicePath")
```

```Output
%SystemRoot%\inf
```

### <a name="setting-a-single-registry-entry"></a><span data-ttu-id="88fc1-131">1 つのレジストリ エントリの設定</span><span class="sxs-lookup"><span data-stu-id="88fc1-131">Setting a Single Registry Entry</span></span>

<span data-ttu-id="88fc1-132">レジストリ キーの特定のエントリを変更する場合は、いくつかの可能なアプローチのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="88fc1-132">If you want to change a specific entry in a registry key, you can use one of several possible approaches.</span></span> <span data-ttu-id="88fc1-133">この例の変更、**パス**エントリ`HKEY_CURRENT_USER\Environment`。</span><span class="sxs-lookup"><span data-stu-id="88fc1-133">This example modifies the **Path** entry under `HKEY_CURRENT_USER\Environment`.</span></span> <span data-ttu-id="88fc1-134">**パス**エントリは、実行可能ファイルを検索する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="88fc1-134">The **Path** entry specifies where to find executable files.</span></span>

1. <span data-ttu-id="88fc1-135">現在の値を取得、**パス**を使用してエントリ`Get-ItemProperty`します。</span><span class="sxs-lookup"><span data-stu-id="88fc1-135">Retrieve the current value of the **Path** entry using `Get-ItemProperty`.</span></span>
2. <span data-ttu-id="88fc1-136">分離することで、新しい値を追加、`;`します。</span><span class="sxs-lookup"><span data-stu-id="88fc1-136">Add the new value, separating it with a `;`.</span></span>
3. <span data-ttu-id="88fc1-137">使用`Set-ItemProperty`指定したキー、エントリ名、およびレジストリ エントリを変更する値。</span><span class="sxs-lookup"><span data-stu-id="88fc1-137">Use `Set-ItemProperty` with the specified key, entry name, and value to modify the registry entry.</span></span>

```powershell
$value = Get-ItemProperty -Path HKCU:\Environment -Name Path
$newpath = $value.Path += ";C:\src\bin\"
Set-ItemProperty -Path HKCU:\Environment -Name Path -Value $newpath
```

> [!NOTE]
> <span data-ttu-id="88fc1-138">`Set-ItemProperty`が**フィルター**、 **Include**、および**除外**パラメーター、プロパティ名でフィルター処理には使用できません。</span><span class="sxs-lookup"><span data-stu-id="88fc1-138">Although `Set-ItemProperty` has **Filter**, **Include**, and **Exclude** parameters, they cannot be used to filter by property name.</span></span> <span data-ttu-id="88fc1-139">これらのパラメーターはレジストリ キー (項目のパス) を参照し、レジストリ エントリ (項目のプロパティ) を参照するのではありません。</span><span class="sxs-lookup"><span data-stu-id="88fc1-139">These parameters refer to registry keys—which are item paths—and not registry entries—which are item properties.</span></span>

<span data-ttu-id="88fc1-140">別のオプションとして、Reg.exe コマンド ライン ツールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="88fc1-140">Another option is to use the Reg.exe command line tool.</span></span> <span data-ttu-id="88fc1-141">reg.exe のヘルプを表示するには、コマンド プロンプトで「**reg.exe /?**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="88fc1-141">For help with reg.exe, type **reg.exe /?**</span></span>
<span data-ttu-id="88fc1-142">at a command prompt.</span><span class="sxs-lookup"><span data-stu-id="88fc1-142">at a command prompt.</span></span>

<span data-ttu-id="88fc1-143">次の例の変更、**パス**上記の例で追加のパスを削除することで入力します。</span><span class="sxs-lookup"><span data-stu-id="88fc1-143">The following example changes the **Path** entry by removing the path added in the example above.</span></span>
<span data-ttu-id="88fc1-144">`Get-ItemProperty` 返された文字列を解析しなくてもすむように、現在の値を取得するために使用がまだ`reg query`します。</span><span class="sxs-lookup"><span data-stu-id="88fc1-144">`Get-ItemProperty` is still used to retrieve the current value to avoid having to parse the string returned from `reg query`.</span></span> <span data-ttu-id="88fc1-145">**SubString**と**LastIndexOf**に追加された最後のパスの取得に使用する方法、**パス**エントリ。</span><span class="sxs-lookup"><span data-stu-id="88fc1-145">The **SubString** and **LastIndexOf** methods are used to retrieve the last path added to the **Path** entry.</span></span>

```powershell
$value = Get-ItemProperty -Path HKCU:\Environment -Name Path
$newpath = $value.Path.SubString(0, $value.Path.LastIndexOf(';'))
reg add HKCU\Environment /v Path /d $newpath /f
```

```Output
The operation completed successfully.
```

### <a name="creating-new-registry-entries"></a><span data-ttu-id="88fc1-146">新しいレジストリ エントリの作成</span><span class="sxs-lookup"><span data-stu-id="88fc1-146">Creating New Registry Entries</span></span>

<span data-ttu-id="88fc1-147">"PowerShellPath"という名前の新しいエントリを追加する、 **CurrentVersion**キーを使用して`New-ItemProperty`キー、エントリ名、およびエントリの値へのパス。</span><span class="sxs-lookup"><span data-stu-id="88fc1-147">To add a new entry named "PowerShellPath" to the **CurrentVersion** key, use `New-ItemProperty` with the path to the key, the entry name, and the value of the entry.</span></span> <span data-ttu-id="88fc1-148">この例では、Windows PowerShell 変数の値を取得しましたが`$PSHome`、Windows PowerShell のインストール ディレクトリへのパスを格納します。</span><span class="sxs-lookup"><span data-stu-id="88fc1-148">For this example, we will take the value of the Windows PowerShell variable `$PSHome`, which stores the path to the installation directory for Windows PowerShell.</span></span>

<span data-ttu-id="88fc1-149">キーに新しいエントリを追加するには、次のコマンドを使用します。このコマンドは、新しいエントリに関する情報も返します。</span><span class="sxs-lookup"><span data-stu-id="88fc1-149">You can add the new entry to the key by using the following command, and the command also returns information about the new entry:</span></span>

```powershell
New-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -PropertyType String -Value $PSHome
```

```Output
PSPath         : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
PSParentPath   : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows
PSChildName    : CurrentVersion
PSDrive        : HKLM
PSProvider     : Microsoft.PowerShell.Core\Registry
PowerShellPath : C:\Program Files\Windows PowerShell\v1.0
```

<span data-ttu-id="88fc1-150">**PropertyType** は、次の表の **Microsoft.Win32.RegistryValueKind** 列挙体のメンバーの名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="88fc1-150">The **PropertyType** must be the name of a **Microsoft.Win32.RegistryValueKind** enumeration member from the following table:</span></span>

|<span data-ttu-id="88fc1-151">PropertyType の値</span><span class="sxs-lookup"><span data-stu-id="88fc1-151">PropertyType Value</span></span>|<span data-ttu-id="88fc1-152">意味</span><span class="sxs-lookup"><span data-stu-id="88fc1-152">Meaning</span></span>|
|----------------------|-----------|
|<span data-ttu-id="88fc1-153">Binary</span><span class="sxs-lookup"><span data-stu-id="88fc1-153">Binary</span></span>|<span data-ttu-id="88fc1-154">バイナリ データ</span><span class="sxs-lookup"><span data-stu-id="88fc1-154">Binary data</span></span>|
|<span data-ttu-id="88fc1-155">DWord</span><span class="sxs-lookup"><span data-stu-id="88fc1-155">DWord</span></span>|<span data-ttu-id="88fc1-156">有効な UInt32 である数字</span><span class="sxs-lookup"><span data-stu-id="88fc1-156">A number that is a valid UInt32</span></span>|
|<span data-ttu-id="88fc1-157">ExpandString</span><span class="sxs-lookup"><span data-stu-id="88fc1-157">ExpandString</span></span>|<span data-ttu-id="88fc1-158">動的に展開される環境変数を含むことができる文字列</span><span class="sxs-lookup"><span data-stu-id="88fc1-158">A string that can contain environment variables that are dynamically expanded</span></span>|
|<span data-ttu-id="88fc1-159">MultiString</span><span class="sxs-lookup"><span data-stu-id="88fc1-159">MultiString</span></span>|<span data-ttu-id="88fc1-160">複数行文字列</span><span class="sxs-lookup"><span data-stu-id="88fc1-160">A multiline string</span></span>|
|<span data-ttu-id="88fc1-161">String</span><span class="sxs-lookup"><span data-stu-id="88fc1-161">String</span></span>|<span data-ttu-id="88fc1-162">任意の文字列値</span><span class="sxs-lookup"><span data-stu-id="88fc1-162">Any string value</span></span>|
|<span data-ttu-id="88fc1-163">QWord</span><span class="sxs-lookup"><span data-stu-id="88fc1-163">QWord</span></span>|<span data-ttu-id="88fc1-164">8 バイトのバイナリ データ</span><span class="sxs-lookup"><span data-stu-id="88fc1-164">8 bytes of binary data</span></span>|

> [!NOTE]
> <span data-ttu-id="88fc1-165">**Path** パラメーターに値の配列を指定して、レジストリ エントリを複数の場所に追加できます。</span><span class="sxs-lookup"><span data-stu-id="88fc1-165">You can add a registry entry to multiple locations by specifying an array of values for the **Path** parameter:</span></span>

```powershell
New-ItemProperty -Name PowerShellPath -PropertyType String -Value $PSHome `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion, HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

<span data-ttu-id="88fc1-166">追加することで、既存のレジストリ エントリの値を上書きすることも、 **Force**パラメーターを`New-ItemProperty`コマンド。</span><span class="sxs-lookup"><span data-stu-id="88fc1-166">You can also overwrite a pre-existing registry entry value by adding the **Force** parameter to any `New-ItemProperty` command.</span></span>

### <a name="renaming-registry-entries"></a><span data-ttu-id="88fc1-167">レジストリ エントリの名前変更</span><span class="sxs-lookup"><span data-stu-id="88fc1-167">Renaming Registry Entries</span></span>

<span data-ttu-id="88fc1-168">名前を変更する、 **PowerShellPath**エントリを"PSHome"、" `Rename-ItemProperty`:</span><span class="sxs-lookup"><span data-stu-id="88fc1-168">To rename the **PowerShellPath** entry to "PSHome," use `Rename-ItemProperty`:</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -NewName PSHome
```

<span data-ttu-id="88fc1-169">名前が変更された値を表示するには、**PassThru** パラメーターをコマンドに追加します。</span><span class="sxs-lookup"><span data-stu-id="88fc1-169">To display the renamed value, add the **PassThru** parameter to the command.</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -NewName PSHome -passthru
```

### <a name="deleting-registry-entries"></a><span data-ttu-id="88fc1-170">レジストリ エントリの削除</span><span class="sxs-lookup"><span data-stu-id="88fc1-170">Deleting Registry Entries</span></span>

<span data-ttu-id="88fc1-171">PSHome と PowerShellPath の両方のレジストリ エントリを削除するには使用`Remove-ItemProperty`:</span><span class="sxs-lookup"><span data-stu-id="88fc1-171">To delete both the PSHome and PowerShellPath registry entries, use `Remove-ItemProperty`:</span></span>

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PSHome
Remove-ItemProperty -Path HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath
```
