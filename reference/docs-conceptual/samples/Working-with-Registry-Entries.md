---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: レジストリ エントリの操作
description: この記事では、PowerShell を使用してレジストリ エントリを処理する方法について説明します。
ms.openlocfilehash: 65f8b4ed7b2f9af26bfd22f34577a4bd52f35e70
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501458"
---
# <a name="working-with-registry-entries"></a><span data-ttu-id="49d44-104">レジストリ エントリの操作</span><span class="sxs-lookup"><span data-stu-id="49d44-104">Working with Registry Entries</span></span>

<span data-ttu-id="49d44-105">レジストリ エントリはキーのプロパティであり直接参照できないため、利用するときは少し異なる方法を取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="49d44-105">Because registry entries are properties of keys and, as such, cannot be directly browsed, we need to take a slightly different approach when working with them.</span></span>

## <a name="listing-registry-entries"></a><span data-ttu-id="49d44-106">レジストリ エントリの一覧表示</span><span class="sxs-lookup"><span data-stu-id="49d44-106">Listing Registry Entries</span></span>

<span data-ttu-id="49d44-107">レジストリ エントリを確認するには、多くのさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="49d44-107">There are many different ways to examine registry entries.</span></span> <span data-ttu-id="49d44-108">最も簡単な方法は、キーに関連付けられているプロパティの名前を取得することです。</span><span class="sxs-lookup"><span data-stu-id="49d44-108">The simplest way is to get the property names associated with a key.</span></span> <span data-ttu-id="49d44-109">たとえば、レジストリ キー `HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion` のエントリの名前を確認するには、`Get-Item` を使います。</span><span class="sxs-lookup"><span data-stu-id="49d44-109">For example, to see the names of the entries in the registry key `HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion`, use `Get-Item`.</span></span> <span data-ttu-id="49d44-110">レジストリ キーは、キーのレジストリ エントリの一覧であり、"Property"という汎用的な名前のプロパティを持っています。</span><span class="sxs-lookup"><span data-stu-id="49d44-110">Registry keys have a property with the generic name of "Property" that is a list of registry entries in the key.</span></span>
<span data-ttu-id="49d44-111">次のコマンドは、Property プロパティを選択し、一覧に表示されるように項目を拡張します。</span><span class="sxs-lookup"><span data-stu-id="49d44-111">The following command selects the Property property and expands the items so that they are displayed in a list:</span></span>

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

<span data-ttu-id="49d44-112">レジストリ エントリをさらに読みやすい形式で表示するには、`Get-ItemProperty` を使います。</span><span class="sxs-lookup"><span data-stu-id="49d44-112">To view the registry entries in a more readable form, use `Get-ItemProperty`:</span></span>

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

<span data-ttu-id="49d44-113">キーの Windows PowerShell 関連のプロパティには、 **PSPath** 、 **PSParentPath** 、 **PSChildName** 、および **PSProvider** のように、すべて先頭に "PS" が付きます。</span><span class="sxs-lookup"><span data-stu-id="49d44-113">The Windows PowerShell-related properties for the key are all prefixed with "PS", such as **PSPath** , **PSParentPath** , **PSChildName** , and **PSProvider** .</span></span>

<span data-ttu-id="49d44-114">現在の場所を参照するために、`*.*` 表記を使用できます。</span><span class="sxs-lookup"><span data-stu-id="49d44-114">You can use the `*.*` notation for referring to the current location.</span></span> <span data-ttu-id="49d44-115">`Set-Location` を使用して、まず **CurrentVersion** レジストリのコンテナーに変更します。</span><span class="sxs-lookup"><span data-stu-id="49d44-115">You can use `Set-Location` to change to the **CurrentVersion** registry container first:</span></span>

```powershell
Set-Location -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
```

<span data-ttu-id="49d44-116">または、`Set-Location` と共に組み込みの HKLM PSDrive を使用できます。</span><span class="sxs-lookup"><span data-stu-id="49d44-116">Alternatively, you can use the built-in HKLM PSDrive with `Set-Location`:</span></span>

```powershell
Set-Location -Path hklm:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

<span data-ttu-id="49d44-117">次に、現在の場所に対して `*.*` 表記を使用して、完全パスを指定することなくプロパティを一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="49d44-117">You can then use the `*.*` notation for the current location to list the properties without specifying a full path:</span></span>

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

<span data-ttu-id="49d44-118">パスの展開は、ファイル システム内の場合と同様に機能します。そのため、この場所から `Get-ItemProperty -Path ..\Help` を使って `HKLM:\SOFTWARE\Microsoft\Windows\Help` の **ItemProperty** の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="49d44-118">Path expansion works the same as it does within the file system, so from this location you can get the **ItemProperty** listing for `HKLM:\SOFTWARE\Microsoft\Windows\Help` by using `Get-ItemProperty -Path ..\Help`.</span></span>

## <a name="getting-a-single-registry-entry"></a><span data-ttu-id="49d44-119">1 つのレジストリ エントリの取得</span><span class="sxs-lookup"><span data-stu-id="49d44-119">Getting a Single Registry Entry</span></span>

<span data-ttu-id="49d44-120">レジストリ キーの特定のエントリを取得する場合は、いくつかの可能なアプローチのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="49d44-120">If you want to retrieve a specific entry in a registry key, you can use one of several possible approaches.</span></span> <span data-ttu-id="49d44-121">この例では、`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion` の **DevicePath** の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="49d44-121">This example finds the value of **DevicePath** in `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span></span>

<span data-ttu-id="49d44-122">`Get-ItemProperty` を使用する場合、 **Path** パラメーターを使用してキーの名前を指定し、 **Name** パラメーターを使用して **DevicePath** のエントリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="49d44-122">Using `Get-ItemProperty`, use the **Path** parameter to specify the name of the key, and the **Name** parameter to specify the name of the **DevicePath** entry.</span></span>

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

<span data-ttu-id="49d44-123">このコマンドは、標準の Windows PowerShell のプロパティと **DevicePath** プロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="49d44-123">This command returns the standard Windows PowerShell properties as well as the **DevicePath** property.</span></span>

> [!NOTE]
> <span data-ttu-id="49d44-124">`Get-ItemProperty` には **Filter** 、 **Include** 、 **Exclude** パラメーターが含まれていますが、これらはプロパティ名でフィルター処理するためには使えません。</span><span class="sxs-lookup"><span data-stu-id="49d44-124">Although `Get-ItemProperty` has **Filter** , **Include** , and **Exclude** parameters, they cannot be used to filter by property name.</span></span> <span data-ttu-id="49d44-125">これらのパラメーターはレジストリ キー (項目のパス) を参照するものであり、レジストリ エントリ (項目のプロパティ) を参照しているのではありません。</span><span class="sxs-lookup"><span data-stu-id="49d44-125">These parameters refer to registry keys, which are item paths and not registry entries, which are item properties.</span></span>

<span data-ttu-id="49d44-126">別のオプションとして、Reg.exe コマンド ライン ツールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="49d44-126">Another option is to use the Reg.exe command line tool.</span></span> <span data-ttu-id="49d44-127">reg.exe のヘルプを表示するには、コマンド プロンプトで `reg.exe /?` と入力します。</span><span class="sxs-lookup"><span data-stu-id="49d44-127">For help with reg.exe, type `reg.exe /?` at a command prompt.</span></span> <span data-ttu-id="49d44-128">DevicePath エントリを検索するには、次のコマンドに示すように reg.exe を使用します。</span><span class="sxs-lookup"><span data-stu-id="49d44-128">To find the DevicePath entry, use reg.exe as shown in the following command:</span></span>

```powershell
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion /v DevicePath
```

```Output
! REG.EXE VERSION 3.0

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
    DevicePath  REG_EXPAND_SZ   %SystemRoot%\inf
```

<span data-ttu-id="49d44-129">また、 **WshShell** COM オブジェクトを使っていくつかのレジストリ エントリを検索することもできますが、大きなバイナリ データや、"\\" のような文字を含むレジストリ エントリ名を使う場合、この方法は機能しません。</span><span class="sxs-lookup"><span data-stu-id="49d44-129">You can also use the **WshShell** COM object as well to find some registry entries, although this method does not work with large binary data or with registry entry names that include characters such as "\\").</span></span> <span data-ttu-id="49d44-130">プロパティ名を区切り記号 \\ と共に項目のパスに追加します。</span><span class="sxs-lookup"><span data-stu-id="49d44-130">Append the property name to the item path with a \\ separator:</span></span>

```powershell
(New-Object -ComObject WScript.Shell).RegRead("HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\DevicePath")
```

```Output
%SystemRoot%\inf
```

## <a name="setting-a-single-registry-entry"></a><span data-ttu-id="49d44-131">1 つのレジストリ エントリの設定</span><span class="sxs-lookup"><span data-stu-id="49d44-131">Setting a Single Registry Entry</span></span>

<span data-ttu-id="49d44-132">レジストリ キーの特定のエントリを変更する場合は、いくつかある可能なアプローチのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="49d44-132">If you want to change a specific entry in a registry key, you can use one of several possible approaches.</span></span> <span data-ttu-id="49d44-133">この例では、`HKEY_CURRENT_USER\Environment` 下の **Path** エントリを変更します。</span><span class="sxs-lookup"><span data-stu-id="49d44-133">This example modifies the **Path** entry under `HKEY_CURRENT_USER\Environment`.</span></span> <span data-ttu-id="49d44-134">**Path** エントリでは、実行可能ファイルを検索する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="49d44-134">The **Path** entry specifies where to find executable files.</span></span>

1. <span data-ttu-id="49d44-135">`Get-ItemProperty` を使って **Path** エントリの現在の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="49d44-135">Retrieve the current value of the **Path** entry using `Get-ItemProperty`.</span></span>
2. <span data-ttu-id="49d44-136">`;` で区切りながら新しい値を追加します。</span><span class="sxs-lookup"><span data-stu-id="49d44-136">Add the new value, separating it with a `;`.</span></span>
3. <span data-ttu-id="49d44-137">指定したキー、エントリ名、およびレジストリ エントリを変更する値と共に `Set-ItemProperty` を使います。</span><span class="sxs-lookup"><span data-stu-id="49d44-137">Use `Set-ItemProperty` with the specified key, entry name, and value to modify the registry entry.</span></span>

```powershell
$value = Get-ItemProperty -Path HKCU:\Environment -Name Path
$newpath = $value.Path += ";C:\src\bin\"
Set-ItemProperty -Path HKCU:\Environment -Name Path -Value $newpath
```

> [!NOTE]
> <span data-ttu-id="49d44-138">`Set-ItemProperty` には **Filter** 、 **Include** 、 **Exclude** パラメーターが含まれていますが、これらはプロパティ名でフィルター処理するためには使えません。</span><span class="sxs-lookup"><span data-stu-id="49d44-138">Although `Set-ItemProperty` has **Filter** , **Include** , and **Exclude** parameters, they cannot be used to filter by property name.</span></span> <span data-ttu-id="49d44-139">これらのパラメーターはレジストリ キー (項目のパス) を参照し、レジストリ エントリ (項目のプロパティ) を参照するのではありません。</span><span class="sxs-lookup"><span data-stu-id="49d44-139">These parameters refer to registry keys—which are item paths—and not registry entries—which are item properties.</span></span>

<span data-ttu-id="49d44-140">別のオプションとして、Reg.exe コマンド ライン ツールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="49d44-140">Another option is to use the Reg.exe command line tool.</span></span> <span data-ttu-id="49d44-141">reg.exe のヘルプを表示するには、コマンド プロンプトで「 **reg.exe /?** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="49d44-141">For help with reg.exe, type **reg.exe /?**</span></span>
<span data-ttu-id="49d44-142">at a command prompt.</span><span class="sxs-lookup"><span data-stu-id="49d44-142">at a command prompt.</span></span>

<span data-ttu-id="49d44-143">次の例では、上記の例で追加したパスを削除することで **Path** エントリを変更します。</span><span class="sxs-lookup"><span data-stu-id="49d44-143">The following example changes the **Path** entry by removing the path added in the example above.</span></span>
<span data-ttu-id="49d44-144">`reg query` から返された文字列を解析しなくて済むようにするため、`Get-ItemProperty` を引き続き使って現在の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="49d44-144">`Get-ItemProperty` is still used to retrieve the current value to avoid having to parse the string returned from `reg query`.</span></span> <span data-ttu-id="49d44-145">**Path** エントリに追加された最後のパスを取得するために、 **SubString** および **LastIndexOf** メソッドを使います。</span><span class="sxs-lookup"><span data-stu-id="49d44-145">The **SubString** and **LastIndexOf** methods are used to retrieve the last path added to the **Path** entry.</span></span>

```powershell
$value = Get-ItemProperty -Path HKCU:\Environment -Name Path
$newpath = $value.Path.SubString(0, $value.Path.LastIndexOf(';'))
reg add HKCU\Environment /v Path /d $newpath /f
```

```Output
The operation completed successfully.
```

## <a name="creating-new-registry-entries"></a><span data-ttu-id="49d44-146">新しいレジストリ エントリの作成</span><span class="sxs-lookup"><span data-stu-id="49d44-146">Creating New Registry Entries</span></span>

<span data-ttu-id="49d44-147">"PowerShellPath" という名前の新しいエントリを **CurrentVersion** キーに追加するには、キーのパス、エントリ名、エントリの値と共に `New-ItemProperty` を使用します。</span><span class="sxs-lookup"><span data-stu-id="49d44-147">To add a new entry named "PowerShellPath" to the **CurrentVersion** key, use `New-ItemProperty` with the path to the key, the entry name, and the value of the entry.</span></span> <span data-ttu-id="49d44-148">この例では、Windows PowerShell の変数 `$PSHome` の値を取得します。これには、Windows PowerShell のインストール ディレクトリへのパスが格納されます。</span><span class="sxs-lookup"><span data-stu-id="49d44-148">For this example, we will take the value of the Windows PowerShell variable `$PSHome`, which stores the path to the installation directory for Windows PowerShell.</span></span>

<span data-ttu-id="49d44-149">キーに新しいエントリを追加するには、次のコマンドを使用します。このコマンドは、新しいエントリに関する情報も返します。</span><span class="sxs-lookup"><span data-stu-id="49d44-149">You can add the new entry to the key by using the following command, and the command also returns information about the new entry:</span></span>

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

<span data-ttu-id="49d44-150">**PropertyType** は、次の表の **Microsoft.Win32.RegistryValueKind** 列挙体のメンバーの名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="49d44-150">The **PropertyType** must be the name of a **Microsoft.Win32.RegistryValueKind** enumeration member from the following table:</span></span>

|<span data-ttu-id="49d44-151">PropertyType の値</span><span class="sxs-lookup"><span data-stu-id="49d44-151">PropertyType Value</span></span>|<span data-ttu-id="49d44-152">説明</span><span class="sxs-lookup"><span data-stu-id="49d44-152">Meaning</span></span>|
|----------------------|-----------|
|<span data-ttu-id="49d44-153">Binary</span><span class="sxs-lookup"><span data-stu-id="49d44-153">Binary</span></span>|<span data-ttu-id="49d44-154">Binary Data</span><span class="sxs-lookup"><span data-stu-id="49d44-154">Binary data</span></span>|
|<span data-ttu-id="49d44-155">DWord</span><span class="sxs-lookup"><span data-stu-id="49d44-155">DWord</span></span>|<span data-ttu-id="49d44-156">有効な UInt32 である数字</span><span class="sxs-lookup"><span data-stu-id="49d44-156">A number that is a valid UInt32</span></span>|
|<span data-ttu-id="49d44-157">ExpandString</span><span class="sxs-lookup"><span data-stu-id="49d44-157">ExpandString</span></span>|<span data-ttu-id="49d44-158">動的に展開される環境変数を含むことができる文字列</span><span class="sxs-lookup"><span data-stu-id="49d44-158">A string that can contain environment variables that are dynamically expanded</span></span>|
|<span data-ttu-id="49d44-159">MultiString</span><span class="sxs-lookup"><span data-stu-id="49d44-159">MultiString</span></span>|<span data-ttu-id="49d44-160">複数行文字列</span><span class="sxs-lookup"><span data-stu-id="49d44-160">A multiline string</span></span>|
|<span data-ttu-id="49d44-161">String</span><span class="sxs-lookup"><span data-stu-id="49d44-161">String</span></span>|<span data-ttu-id="49d44-162">任意の文字列値</span><span class="sxs-lookup"><span data-stu-id="49d44-162">Any string value</span></span>|
|<span data-ttu-id="49d44-163">QWord</span><span class="sxs-lookup"><span data-stu-id="49d44-163">QWord</span></span>|<span data-ttu-id="49d44-164">8 バイトのバイナリ データ</span><span class="sxs-lookup"><span data-stu-id="49d44-164">8 bytes of binary data</span></span>|

> [!NOTE]
> <span data-ttu-id="49d44-165">**Path** パラメーターに値の配列を指定して、レジストリ エントリを複数の場所に追加できます。</span><span class="sxs-lookup"><span data-stu-id="49d44-165">You can add a registry entry to multiple locations by specifying an array of values for the **Path** parameter:</span></span>

```powershell
New-ItemProperty -Name PowerShellPath -PropertyType String -Value $PSHome `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion, HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

<span data-ttu-id="49d44-166">また、 **Force** パラメーターを任意の `New-ItemProperty` コマンドに追加して、既存のレジストリ エントリの値を上書きすることもできます。</span><span class="sxs-lookup"><span data-stu-id="49d44-166">You can also overwrite a pre-existing registry entry value by adding the **Force** parameter to any `New-ItemProperty` command.</span></span>

## <a name="renaming-registry-entries"></a><span data-ttu-id="49d44-167">レジストリ エントリの名前変更</span><span class="sxs-lookup"><span data-stu-id="49d44-167">Renaming Registry Entries</span></span>

<span data-ttu-id="49d44-168">**PowerShellPath** エントリの名前を "PSHome" に変更するには、`Rename-ItemProperty` を使用します。</span><span class="sxs-lookup"><span data-stu-id="49d44-168">To rename the **PowerShellPath** entry to "PSHome," use `Rename-ItemProperty`:</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -NewName PSHome
```

<span data-ttu-id="49d44-169">名前が変更された値を表示するには、 **PassThru** パラメーターをコマンドに追加します。</span><span class="sxs-lookup"><span data-stu-id="49d44-169">To display the renamed value, add the **PassThru** parameter to the command.</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -NewName PSHome -passthru
```

## <a name="deleting-registry-entries"></a><span data-ttu-id="49d44-170">レジストリ エントリの削除</span><span class="sxs-lookup"><span data-stu-id="49d44-170">Deleting Registry Entries</span></span>

<span data-ttu-id="49d44-171">PSHome と PowerShellPath の両方のレジストリ エントリを削除するには、`Remove-ItemProperty` を使用します。</span><span class="sxs-lookup"><span data-stu-id="49d44-171">To delete both the PSHome and PowerShellPath registry entries, use `Remove-ItemProperty`:</span></span>

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PSHome
Remove-ItemProperty -Path HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath
```
