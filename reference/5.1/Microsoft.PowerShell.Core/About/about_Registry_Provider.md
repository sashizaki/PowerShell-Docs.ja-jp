---
description: レジストリ
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_registry_provider?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: レジストリ プロバイダー
ms.openlocfilehash: a45513ca0ab4816793d52771ea1cfa56b239ecbf
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223320"
---
# <a name="registry-provider"></a><span data-ttu-id="4a1b6-104">レジストリプロバイダー</span><span class="sxs-lookup"><span data-stu-id="4a1b6-104">Registry provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="4a1b6-105">プロバイダー名</span><span class="sxs-lookup"><span data-stu-id="4a1b6-105">Provider name</span></span>

<span data-ttu-id="4a1b6-106">レジストリ</span><span class="sxs-lookup"><span data-stu-id="4a1b6-106">Registry</span></span>

## <a name="drives"></a><span data-ttu-id="4a1b6-107">ドライブ</span><span class="sxs-lookup"><span data-stu-id="4a1b6-107">Drives</span></span>

<span data-ttu-id="4a1b6-108">`HKLM:`, `HKCU:`</span><span class="sxs-lookup"><span data-stu-id="4a1b6-108">`HKLM:`, `HKCU:`</span></span>

## <a name="capabilities"></a><span data-ttu-id="4a1b6-109">機能</span><span class="sxs-lookup"><span data-stu-id="4a1b6-109">Capabilities</span></span>

<span data-ttu-id="4a1b6-110">" **プロセス** "、" **usetransactions** "</span><span class="sxs-lookup"><span data-stu-id="4a1b6-110">**ShouldProcess** , **UseTransactions**</span></span>

## <a name="short-description"></a><span data-ttu-id="4a1b6-111">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="4a1b6-111">Short description</span></span>

<span data-ttu-id="4a1b6-112">PowerShell のレジストリキー、エントリ、および値へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-112">Provides access to the registry keys, entries, and values in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="4a1b6-113">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="4a1b6-113">Detailed description</span></span>

<span data-ttu-id="4a1b6-114">Powershell **レジストリ** プロバイダーを使用すると、powershell のレジストリキー、エントリ、および値を取得、追加、変更、消去、削除できます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-114">The PowerShell **Registry** provider lets you get, add, change, clear, and delete registry keys, entries, and values in PowerShell.</span></span>

<span data-ttu-id="4a1b6-115">**レジストリ** ドライブは、コンピューター上のレジストリキーとサブキーを含む階層型の名前空間です。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-115">The **Registry** drives are a hierarchical namespace containing the registry keys and subkeys on your computer.</span></span> <span data-ttu-id="4a1b6-116">レジストリ エントリと値はその階層の構成要素ではありません。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-116">Registry entries and values are not components of that hierarchy.</span></span> <span data-ttu-id="4a1b6-117">各キーのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-117">Instead, they are properties of each of the keys.</span></span>

<span data-ttu-id="4a1b6-118">**レジストリ** プロバイダーは、この記事で説明されている次のコマンドレットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-118">The **Registry** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="4a1b6-119">Get-Location</span><span class="sxs-lookup"><span data-stu-id="4a1b6-119">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="4a1b6-120">Set-Location</span><span class="sxs-lookup"><span data-stu-id="4a1b6-120">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="4a1b6-121">Get-Item</span><span class="sxs-lookup"><span data-stu-id="4a1b6-121">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="4a1b6-122">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="4a1b6-122">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="4a1b6-123">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="4a1b6-123">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="4a1b6-124">Move-Item</span><span class="sxs-lookup"><span data-stu-id="4a1b6-124">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="4a1b6-125">New-Item</span><span class="sxs-lookup"><span data-stu-id="4a1b6-125">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="4a1b6-126">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="4a1b6-126">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="4a1b6-127">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4a1b6-127">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="4a1b6-128">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4a1b6-128">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="4a1b6-129">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4a1b6-129">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="4a1b6-130">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4a1b6-130">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="4a1b6-131">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="4a1b6-131">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="4a1b6-132">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="4a1b6-132">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="4a1b6-133">このプロバイダーによって公開される型</span><span class="sxs-lookup"><span data-stu-id="4a1b6-133">Types exposed by this provider</span></span>

<span data-ttu-id="4a1b6-134">レジストリキーは、 [Microsoft の Win32](/dotnet/api/microsoft.win32.registrykey) クラスのインスタンスとして表されます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-134">Registry keys are represented as instances of the [Microsoft.Win32.RegistryKey](/dotnet/api/microsoft.win32.registrykey) class.</span></span> <span data-ttu-id="4a1b6-135">レジストリエントリは、 [Pscustomobject](/dotnet/api/system.management.automation.pscustomobject) クラスのインスタンスとして表されます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-135">Registry entries are represented as instances of the [PSCustomObject](/dotnet/api/system.management.automation.pscustomobject) class.</span></span>

## <a name="navigating-the-registry-drives"></a><span data-ttu-id="4a1b6-136">レジストリドライブの移動</span><span class="sxs-lookup"><span data-stu-id="4a1b6-136">Navigating the Registry drives</span></span>

<span data-ttu-id="4a1b6-137">**レジストリ** プロバイダーは、そのデータストアを2つの既定のドライブとして公開します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-137">The **Registry** provider exposes its data store as two default drives.</span></span> <span data-ttu-id="4a1b6-138">レジストリの場所 HKEY_LOCAL_MACHINE がドライブにマップされ、 `HKLM:` HKEY_CURRENT_USER がドライブにマップされ `HKCU:` ます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-138">The registry location HKEY_LOCAL_MACHINE is mapped to the `HKLM:` drive and HKEY_CURRENT_USER is mapped to the `HKCU:` drive.</span></span> <span data-ttu-id="4a1b6-139">レジストリを操作するには、 `HKLM:` 次のコマンドを使用して場所をドライブに変更します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-139">To work with the registry, you can change your location to the `HKLM:` drive using the following command.</span></span>

```powershell
Set-Location HKLM:
```

<span data-ttu-id="4a1b6-140">ファイル システム ドライブに戻るには、ドライブ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-140">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="4a1b6-141">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-141">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="4a1b6-142">他の PowerShell ドライブから **レジストリ** プロバイダーを操作することもできます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-142">You can also work with the **Registry** provider from any other PowerShell drive.</span></span> <span data-ttu-id="4a1b6-143">別の場所からレジストリキーを参照するには、パスのドライブ名 (、) を使用し `HKLM:` `HKCU:` ます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-143">To reference a registry key from another location, use the drive name (`HKLM:`, `HKCU:`) in the path.</span></span> <span data-ttu-id="4a1b6-144">\\**レジストリ** ドライブのレベルを示すには、円記号 () またはスラッシュ (/) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-144">Use a backslash (\\) or a forward slash (/) to indicate a level of the **Registry** drive.</span></span>

```powershell
PS C:\> cd HKLM:\Software
```

> [!NOTE]
> <span data-ttu-id="4a1b6-145">PowerShell では、エイリアスを使用して、プロバイダーパスを操作するための使い慣れた方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-145">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="4a1b6-146">`dir`やなどのコマンド `ls` は、 [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem)のエイリアスであり、 `cd` [Set Location](xref:Microsoft.PowerShell.Management.Set-Location)のエイリアスであり、 `pwd` [get location](xref:Microsoft.PowerShell.Management.Get-Location)のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-146">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location), and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

<span data-ttu-id="4a1b6-147">この最後の例は、 **レジストリ** プロバイダーの移動に使用できる別のパス構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-147">This last example shows another path syntax you can use to navigate the **Registry** provider.</span></span> <span data-ttu-id="4a1b6-148">この構文では、プロバイダー名に続けて2つのコロンが使用され `::` ます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-148">This syntax uses the provider name, followed by two colons `::`.</span></span> <span data-ttu-id="4a1b6-149">この構文では、マップされたドライブ名ではなく、完全な HIVE 名を使用でき `HKLM` ます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-149">This syntax allows you to use the full HIVE name, instead of the mapped drive name `HKLM`.</span></span>

```powershell
cd "Registry::HKEY_LOCAL_MACHINE\Software"
```

## <a name="displaying-the-contents-of-registry-keys"></a><span data-ttu-id="4a1b6-150">レジストリキーの内容を表示しています</span><span class="sxs-lookup"><span data-stu-id="4a1b6-150">Displaying the contents of registry keys</span></span>

<span data-ttu-id="4a1b6-151">レジストリは、キー、サブキー、およびエントリに分割されます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-151">The registry is divided into keys, subkeys, and entries.</span></span> <span data-ttu-id="4a1b6-152">レジストリ構造の詳細については、「 [レジストリの構造](/windows/desktop/sysinfo/structure-of-the-registry)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-152">For more information about registry structure, see [Structure of the Registry](/windows/desktop/sysinfo/structure-of-the-registry).</span></span>

<span data-ttu-id="4a1b6-153">**レジストリ** ドライブでは、各キーはコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-153">In a **Registry** drive, each key is a container.</span></span> <span data-ttu-id="4a1b6-154">キーには、任意の数のキーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-154">A key can contain any number of keys.</span></span> <span data-ttu-id="4a1b6-155">親キーを持つレジストリキーは、サブキーと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-155">A registry key that has a parent key is called a subkey.</span></span> <span data-ttu-id="4a1b6-156">を使用し `Get-ChildItem` て、レジストリキーを表示したり `Set-Location` 、キーのパスに移動したりできます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-156">You can use `Get-ChildItem` to view registry keys and `Set-Location` to navigate to a key path.</span></span>

<span data-ttu-id="4a1b6-157">レジストリ値はレジストリキーの属性です。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-157">Registry values are attributes of a registry key.</span></span> <span data-ttu-id="4a1b6-158">**レジストリ** ドライブでは、 **アイテムのプロパティ** と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-158">In the **Registry** drive, they are called **Item Properties**.</span></span> <span data-ttu-id="4a1b6-159">レジストリキーには、子キーと項目プロパティの両方を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-159">A registry key can have both children keys and item properties.</span></span>

<span data-ttu-id="4a1b6-160">この例では、との `Get-Item` 違い `Get-ChildItem` が示されています。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-160">In this example, the difference between `Get-Item` and `Get-ChildItem` is shown.</span></span> <span data-ttu-id="4a1b6-161">を `Get-Item` "スプーラ" レジストリキーに対して使用すると、そのプロパティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-161">When you use `Get-Item` on the "Spooler" registry key, you can view its properties.</span></span>

```
PS C:\ > Get-Item -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler


    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services


Name        Property
----        --------
Spooler     DependOnService    : {RPCSS, http}
            Description        : @%systemroot%\system32\spoolsv.exe,-2
            DisplayName        : @%systemroot%\system32\spoolsv.exe,-1
            ErrorControl       : 1
            FailureActions     : {16, 14, 0, 0...}
            Group              : SpoolerGroup
            ImagePath          : C:\WINDOWS\System32\spoolsv.exe
            ObjectName         : LocalSystem
            RequiredPrivileges : {SeTcbPrivilege, SeImpersonatePrivilege, ...
            ServiceSidType     : 1
            Start              : 2
            Type               : 27
```

<span data-ttu-id="4a1b6-162">各レジストリキーには、サブキーを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-162">Each registry key can also have subkeys.</span></span> <span data-ttu-id="4a1b6-163">レジストリキーでを使用する場合 `Get-Item` 、サブキーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-163">When you use `Get-Item` on a registry key, the subkeys are not displayed.</span></span> <span data-ttu-id="4a1b6-164">`Get-ChildItem`コマンドレットにより、各サブキーのプロパティを含む "スプーラ" キーの子項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-164">The `Get-ChildItem` cmdlet will show you children items of the "Spooler" key, including each subkey's properties.</span></span> <span data-ttu-id="4a1b6-165">を使用する場合、[親キー] プロパティは表示されません `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-165">The parent keys properties are not shown when using `Get-ChildItem`.</span></span>

```
PS C:\> Get-ChildItem -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler


    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Spooler


Name             Property
----             --------
Performance      Close           : PerfClose
                 Collect         : PerfCollect
                 Collect Timeout : 2000
                 Library         : C:\Windows\System32\winspool.drv
                 Object List     : 1450
                 Open            : PerfOpen
                 Open Timeout    : 4000
Security         Security : {1, 0, 20, 128...}
```

<span data-ttu-id="4a1b6-166">`Get-Item`コマンドレットは、現在の場所でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-166">The `Get-Item` cmdlet can also be used on the current location.</span></span> <span data-ttu-id="4a1b6-167">次の例では、"スプーラ" レジストリキーに移動し、アイテムのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-167">The following example navigates to the "Spooler" registry key and gets the item properties.</span></span>
<span data-ttu-id="4a1b6-168">ドット `.` は、現在の場所を示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-168">The dot `.` is used to indicate the current location.</span></span>

```
PS C:\> cd HKLM:\System\CurrentControlSet\Services\Spooler
PS HKLM:\SYSTEM\CurrentControlSet\Services\Spooler> Get-Item .

    Hive: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services

Name             Property
----             --------
Spooler          DependOnService    : {RPCSS, http}
                 Description        : @%systemroot%\system32\spoolsv.exe,-2
...
```

<span data-ttu-id="4a1b6-169">このセクションで説明するコマンドレットの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-169">For more information on the cmdlets covered in this section, see the following articles.</span></span>

<span data-ttu-id="4a1b6-170">-[項目](xref:Microsoft.PowerShell.Management.Get-Item) 
- の取得[Get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem)</span><span class="sxs-lookup"><span data-stu-id="4a1b6-170">-[Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
-[Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)</span></span>

## <a name="viewing-registry-key-values"></a><span data-ttu-id="4a1b6-171">レジストリキー値の表示</span><span class="sxs-lookup"><span data-stu-id="4a1b6-171">Viewing registry key values</span></span>

<span data-ttu-id="4a1b6-172">レジストリキーの値は、各レジストリキーのプロパティとして格納されます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-172">Registry key values are stored as properties of each registry key.</span></span> <span data-ttu-id="4a1b6-173">`Get-ItemProperty`コマンドレットは、指定した名前を使用してレジストリキーのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-173">The `Get-ItemProperty` cmdlet views registry key properties using the name you specify.</span></span> <span data-ttu-id="4a1b6-174">結果として、指定したプロパティを含む **Pscustomobject** 生成されます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-174">The result is a **PSCustomObject** containing the properties you specify.</span></span>

<span data-ttu-id="4a1b6-175">次の例では、 `Get-ItemProperty` コマンドレットを使用してすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-175">The Following example uses the `Get-ItemProperty` cmdlet to view all properties.</span></span> <span data-ttu-id="4a1b6-176">生成されたオブジェクトを変数に格納すると、目的のプロパティ値にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-176">Storing the resulting object in a variable allows you to access the desired property value.</span></span>

```powershell
$p = Get-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler
$p.DependOnService
```

```output
RPCSS
http
```

<span data-ttu-id="4a1b6-177">パラメーターの値を指定 `-Name` すると、指定したプロパティが選択され、 **Pscustomobject** 返されます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-177">Specifying a value for the `-Name` parameter selects the properties you specify and returns the **PSCustomObject**.</span></span>  <span data-ttu-id="4a1b6-178">次の例は、パラメーターを使用した場合の出力の違いを示して `-Name` います。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-178">The following example shows the difference in output when you use the `-Name` parameter.</span></span>

```
PS C:\> Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Wbem

BUILD                      : 17134.1
Installation Directory     : C:\WINDOWS\system32\WBEM
MOF Self-Install Directory : C:\WINDOWS\system32\WBEM\MOF
PSPath                     : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wbem
PSParentPath               : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft
PSChildName                : Wbem
PSDrive                    : HKLM
PSProvider                 : Microsoft.PowerShell.Core\Registry

PS C:\> Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Wbem -Name BUILD

BUILD        : 17134.1
PSPath       : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wbem
PSParentPath : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft
PSChildName  : Wbem
PSDrive      : HKLM
PSProvider   : Microsoft.PowerShell.Core\Registry
```

<span data-ttu-id="4a1b6-179">PowerShell 5.0 以降では、 `Get-ItemPropertyValue` コマンドレットは、指定したプロパティの値のみを返します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-179">Beginning in PowerShell 5.0, the `Get-ItemPropertyValue` cmdlet returns only the value of the property you specify.</span></span>

```powershell
Get-ItemPropertyValue -Path HKLM:\SOFTWARE\Microsoft\Wbem -Name BUILD
```

```output
17134.1
```

<span data-ttu-id="4a1b6-180">このセクションで使用するコマンドレットの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-180">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="4a1b6-181">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4a1b6-181">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="4a1b6-182">Get-ItemPropertyValue</span><span class="sxs-lookup"><span data-stu-id="4a1b6-182">Get-ItemPropertyValue</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)

## <a name="changing-registry-key-values"></a><span data-ttu-id="4a1b6-183">レジストリキー値の変更</span><span class="sxs-lookup"><span data-stu-id="4a1b6-183">Changing registry key values</span></span>

<span data-ttu-id="4a1b6-184">`Set-ItemProperty`コマンドレットでは、レジストリキーの属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-184">The `Set-ItemProperty` cmdlet will set attributes for registry keys.</span></span> <span data-ttu-id="4a1b6-185">次の例では、を使用して `Set-ItemProperty` 、スプーラサービスの開始の種類を手動に変更します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-185">The following example uses `Set-ItemProperty` to change the spooler service start type to manual.</span></span> <span data-ttu-id="4a1b6-186">この例では、コマンドレットを使用して、 **Starttype** を *Automatic* に戻し `Set-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-186">The example changes the **StartType** back to *Automatic* using the `Set-Service` cmdlet.</span></span>

```
PS C:\> Get-Service spooler | Select-Object Name, StartMode

Name    StartType
----    ---------
spooler Automatic

PS C:\> $path = "HKLM:\SYSTEM\CurrentControlSet\Services\Spooler\"
PS C:\> Set-ItemProperty -Path $path -Name Start -Value 3
PS C:\> Get-Service spooler | Select-Object Name, StartMode

Name    StartType
----    ---------
spooler    Manual

PS C:\> Set-Service -Name Spooler -StartupType Automatic
```

<span data-ttu-id="4a1b6-187">各レジストリキーには *既定* 値があります。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-187">Each registry key has a *default* value.</span></span> <span data-ttu-id="4a1b6-188">レジストリキーの *既定* 値は、またはのいずれかを使用して変更でき `Set-Item` `Set-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-188">You can change the *default* value for a registry key with either `Set-Item` or `Set-ItemProperty`.</span></span>

```powershell
Set-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name "(default)" -Value "one"
Set-Item -Path HKLM:\SOFTWARE\Contoso -Value "two"
```

<span data-ttu-id="4a1b6-189">このセクションで使用するコマンドレットの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-189">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="4a1b6-190">Set-Item</span><span class="sxs-lookup"><span data-stu-id="4a1b6-190">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)
- [<span data-ttu-id="4a1b6-191">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4a1b6-191">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="creating-registry-keys-and-values"></a><span data-ttu-id="4a1b6-192">レジストリキーと値の作成</span><span class="sxs-lookup"><span data-stu-id="4a1b6-192">Creating registry keys and values</span></span>

<span data-ttu-id="4a1b6-193">コマンドレットにより、指定した `New-Item` 名前のレジストリキーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-193">The `New-Item` cmdlet will create registry keys with a name that you provide.</span></span>
<span data-ttu-id="4a1b6-194">関数を使用することもでき `mkdir` ます。この関数は、内部でコマンドレットを呼び出します `New-Item` 。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-194">You can also use the `mkdir` function, which calls the `New-Item` cmdlet internally.</span></span>

```
PS HKLM:\SOFTWARE\> mkdir ContosoCompany

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name                           Property
----                           --------
ContosoCompany
```

<span data-ttu-id="4a1b6-195">コマンドレットを使用して、指定した `New-ItemProperty` レジストリキーに値を作成できます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-195">You can use the `New-ItemProperty` cmdlet to create values in a registry key that you specify.</span></span> <span data-ttu-id="4a1b6-196">次の例では、ContosoCompany レジストリキーに新しい DWORD 値を作成します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-196">The following example creates a new DWORD value on the ContosoCompany registry key.</span></span>

```powershell
$path = "HKLM:\SOFTWARE\ContosoCompany"
New-ItemProperty -Path  -Name Test -Type DWORD -Value 1
```

> [!NOTE]
> <span data-ttu-id="4a1b6-197">その他の許可されている型の値については、この記事の「動的パラメーター」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-197">Review the dynamic parameters section in this article for other allowed type values.</span></span>

<span data-ttu-id="4a1b6-198">コマンドレットの使用方法の詳細については、「 [get-itemproperty](xref:Microsoft.PowerShell.Management.New-ItemProperty)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-198">For detailed cmdlet usage, see [New-ItemProperty](xref:Microsoft.PowerShell.Management.New-ItemProperty).</span></span>

## <a name="copying-registry-keys-and-values"></a><span data-ttu-id="4a1b6-199">レジストリキーと値のコピー</span><span class="sxs-lookup"><span data-stu-id="4a1b6-199">Copying registry keys and values</span></span>

<span data-ttu-id="4a1b6-200">**レジストリ** プロバイダーで、コマンドレットを使用して、 `Copy-Item` レジストリキーと値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-200">In the **Registry** provider, use the `Copy-Item` cmdlet copies registry keys and values.</span></span> <span data-ttu-id="4a1b6-201">コマンドレットを使用して、 `Copy-ItemProperty` レジストリ値のみをコピーします。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-201">Use the `Copy-ItemProperty` cmdlet to copy registry values only.</span></span>
<span data-ttu-id="4a1b6-202">次のコマンドは、"Contoso" レジストリキーとそのプロパティを、指定された場所 "HKLM:\ ソフトウェア \ Fabrikam" にコピーします。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-202">The following command copies the "Contoso" registry key, and its properties to the specified location "HKLM:\Software\Fabrikam".</span></span>

<span data-ttu-id="4a1b6-203">`Copy-Item` コピー先キーが存在しない場合は、作成します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-203">`Copy-Item` creates the destination key if it does not exist.</span></span> <span data-ttu-id="4a1b6-204">コピー先のキーが存在する場合は、コピー先のキーの `Copy-Item` 子項目 (サブキー) として、ソースキーの複製が作成されます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-204">If the destination key exists, `Copy-Item` creates a duplicate of the source key as a child item (subkey) of the destination key.</span></span>

```powershell
Copy-Item -Path  HKLM:\Software\Contoso -Destination HKLM:\Software\Fabrikam
```

<span data-ttu-id="4a1b6-205">次のコマンドは、コマンドレットを使用して、" `Copy-ItemProperty` Contoso" キーから "Fabrikam" キーに "Server" の値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-205">The following command uses the `Copy-ItemProperty` cmdlet to copy the "Server" value from the "Contoso" key to the "Fabrikam" key.</span></span>

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Copy-ItemProperty -Path $source -Destination $dest -Name Server
```

<span data-ttu-id="4a1b6-206">このセクションで使用するコマンドレットの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-206">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="4a1b6-207">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="4a1b6-207">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)
- [<span data-ttu-id="4a1b6-208">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4a1b6-208">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

## <a name="moving-registry-keys-and-values"></a><span data-ttu-id="4a1b6-209">レジストリキーと値の移動</span><span class="sxs-lookup"><span data-stu-id="4a1b6-209">Moving registry keys and values</span></span>

<span data-ttu-id="4a1b6-210">`Move-Item` `Move-ItemProperty` コマンドレットとコマンドレットは、対応する "Copy" のように動作します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-210">The `Move-Item` and `Move-ItemProperty` cmdlets behave like their "Copy" counterparts.</span></span> <span data-ttu-id="4a1b6-211">コピー先が存在する場合は、コピー `Move-Item` 先のキーの下にソースキーを移動します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-211">If the destination exists, `Move-Item` moves the source key underneath the destination key.</span></span> <span data-ttu-id="4a1b6-212">コピー先のキーが存在しない場合は、ソースキーが移行先のパスに移動されます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-212">If the destination key does not exist, the source key is moved to the destination path.</span></span>

<span data-ttu-id="4a1b6-213">次のコマンドを実行すると、"Contoso" キーがパス "HKLM:\ \ ソフトウェア \ Fabrikam" に移動します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-213">The following command moves the "Contoso" key to the path "HKLM:\SOFTWARE\Fabrikam".</span></span>

```powershell
Move-Item -Path HKLM:\SOFTWARE\Contoso -Destination HKLM:\SOFTWARE\Fabrikam
```

<span data-ttu-id="4a1b6-214">このコマンドは、すべてのプロパティを "HKLM:\ SOFTWARE\ContosoCompany" から "HKLM:\ Fabrikam" に移動します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-214">This command moves all of the properties from "HKLM:\SOFTWARE\ContosoCompany" to "HKLM:\SOFTWARE\Fabrikam".</span></span>

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Move-ItemProperty -Path $source -Destination $dest -Name *
```

<span data-ttu-id="4a1b6-215">このセクションで使用するコマンドレットの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-215">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="4a1b6-216">Move-Item</span><span class="sxs-lookup"><span data-stu-id="4a1b6-216">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="4a1b6-217">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4a1b6-217">Move-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Move-ItemProperty)

## <a name="renaming-registry-keys-and-values"></a><span data-ttu-id="4a1b6-218">レジストリキーと値の名前を変更する</span><span class="sxs-lookup"><span data-stu-id="4a1b6-218">Renaming registry keys and values</span></span>

<span data-ttu-id="4a1b6-219">レジストリキーと値の名前は、ファイルやフォルダーと同じように変更できます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-219">You can rename registry keys and values just like you would files and folders.</span></span>
<span data-ttu-id="4a1b6-220">`Rename-Item` レジストリ値の名前を変更するときに、レジストリキーの名前を変更 `Rename-ItemProperty` します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-220">`Rename-Item` renames registry keys, while `Rename-ItemProperty` renames registry values.</span></span>

```powershell
$path = "HKLM:\SOFTWARE\Contoso"
Rename-ItemProperty -Path $path -Name ContosoTest -NewName FabrikamTest
Rename-Item -Path $path -NewName Fabrikam
```

## <a name="changing-security-descriptors"></a><span data-ttu-id="4a1b6-221">セキュリティ記述子の変更</span><span class="sxs-lookup"><span data-stu-id="4a1b6-221">Changing security descriptors</span></span>

<span data-ttu-id="4a1b6-222">およびコマンドレットを使用して、レジストリキーへのアクセスを制限することができ `Get-Acl` `Set-Acl` ます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-222">You can restrict access to registry keys using the `Get-Acl` and `Set-Acl` cmdlets.</span></span> <span data-ttu-id="4a1b6-223">次の例では、"HKLM:\ \ ソフトウェア \ Contoso" レジストリキーにフルコントロールを持つ新しいユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-223">The following example adds a new user with full control to the "HKLM:\SOFTWARE\Contoso" registry key.</span></span>

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Contoso
$rule = New-Object System.Security.AccessControl.RegistryAccessRule `
("CONTOSO\jsmith", "FullControl", "Allow")
$acl.SetAccessRule($rule)
$acl | Set-Acl -Path HKLM:\SOFTWARE\Contoso
```

<span data-ttu-id="4a1b6-224">その他の例とコマンドレットの使用方法の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-224">For more examples and cmdlet usage details see the following articles.</span></span>

- [<span data-ttu-id="4a1b6-225">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="4a1b6-225">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="4a1b6-226">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="4a1b6-226">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="removing-and-clearing-registry-keys-and-values"></a><span data-ttu-id="4a1b6-227">レジストリキーと値の削除と消去</span><span class="sxs-lookup"><span data-stu-id="4a1b6-227">Removing and clearing registry keys and values</span></span>

<span data-ttu-id="4a1b6-228">**削除項目** を使用して、含まれる項目を削除できますが、項目に他の項目が含まれている場合は、削除を確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-228">You can remove contained items by using **Remove-Item** , but you will be prompted to confirm the removal if the item contains anything else.</span></span> <span data-ttu-id="4a1b6-229">次の例では、キー "HKLM:\ \ ソフトウェア \ Contoso" を削除しようとしています。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-229">The following example attempts to delete a key "HKLM:\SOFTWARE\Contoso".</span></span>

```
PS C:\> dir HKLM:\SOFTWARE\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Contoso

Name                           Property
----                           --------
ChildKey

PS C:\> Remove-Item -Path HKLM:\SOFTWARE\Contoso

Confirm
The item at HKLM:\SOFTWARE\Contoso has children and the -Recurse
parameter was not specified. If you continue, all children will be removed
with the item. Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help
(default is "Y"):
```

<span data-ttu-id="4a1b6-230">メッセージを表示せずに含まれる項目を削除するには、パラメーターを指定し `-Recurse` ます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-230">To delete contained items without prompting, specify the `-Recurse` parameter.</span></span>

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso -Recurse
```

<span data-ttu-id="4a1b6-231">"Hklm:\ \ ソフトウェア \ contoso" 内のすべての項目を削除するが、"HKLM:\ $ $ contoso" 自体は削除しない場合は、末尾に円記号を付けた後にワイルドカードを使用し `\` ます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-231">If you wanted to remove all items within "HKLM:\SOFTWARE\Contoso" but not "HKLM:\SOFTWARE\Contoso" itself, use a trailing backslash `\` followed by a wildcard.</span></span>

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso\* -Recurse
```

<span data-ttu-id="4a1b6-232">このコマンドは、"HKLM:\ ContosoTest" レジストリキーから "" レジストリ値を削除します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-232">This command deletes the "ContosoTest" registry value from the "HKLM:\SOFTWARE\Contoso" registry key.</span></span>

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name ContosoTest
```

<span data-ttu-id="4a1b6-233">`Clear-Item` キーのすべてのレジストリ値をクリアします。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-233">`Clear-Item` clears all registry values for a key.</span></span> <span data-ttu-id="4a1b6-234">次の例では、"HKLM:\ \ ソフトウェア \ Contoso" レジストリキーからすべての値を削除します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-234">The following example clears all values from the "HKLM:\SOFTWARE\Contoso" registry key.</span></span> <span data-ttu-id="4a1b6-235">特定のプロパティのみをクリアするには、を使用し `Clear-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-235">To clear only a specific property, use `Clear-ItemProperty`.</span></span>

```
PS HKLM:\SOFTWARE\> Get-Item .\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name           Property
----           --------
Contoso        Server     : {a, b, c}
               HereString : {This is text which contains
               newlines. It also contains "quoted" strings}
               (default)  : 1

PS HKLM:\SOFTWARE\> Clear-Item .\Contoso\
PS HKLM:\SOFTWARE\> Get-Item .\Contoso\

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name                           Property
----                           --------
Contoso
```

<span data-ttu-id="4a1b6-236">その他の例とコマンドレットの使用方法の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-236">For more examples and cmdlet usage details see the following articles.</span></span>

- [<span data-ttu-id="4a1b6-237">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="4a1b6-237">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="4a1b6-238">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4a1b6-238">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="4a1b6-239">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="4a1b6-239">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="4a1b6-240">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4a1b6-240">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)

## <a name="dynamic-parameters"></a><span data-ttu-id="4a1b6-241">動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="4a1b6-241">Dynamic parameters</span></span>

<span data-ttu-id="4a1b6-242">動的パラメーターは、PowerShell プロバイダーによって追加されるコマンドレットパラメーターであり、プロバイダーに対応したドライブでコマンドレットが使用されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-242">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="type-microsoftwin32registryvaluekind"></a><span data-ttu-id="4a1b6-243">「<>」と入力します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-243">Type <Microsoft.Win32.RegistryValueKind></span></span>

<span data-ttu-id="4a1b6-244">レジストリ値のデータ型を確立または変更します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-244">Establishes or changes the data type of a registry value.</span></span> <span data-ttu-id="4a1b6-245">既定値は `String` (REG_SZ) です。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-245">The default is `String` (REG_SZ).</span></span>

<span data-ttu-id="4a1b6-246">このパラメーターは [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty) コマンドレットの設計に基づき動作します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-246">This parameter works as designed on the [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty) cmdlet.</span></span> <span data-ttu-id="4a1b6-247">レジストリ ドライブの [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item) コマンドレットでも利用できますが、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-247">It is also available on the [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item) cmdlet in the registry drives, but it has no effect.</span></span>

|<span data-ttu-id="4a1b6-248">値</span><span class="sxs-lookup"><span data-stu-id="4a1b6-248">Value</span></span> | <span data-ttu-id="4a1b6-249">説明</span><span class="sxs-lookup"><span data-stu-id="4a1b6-249">Description</span></span> |
| ---- | ----------- |
| `String` | <span data-ttu-id="4a1b6-250">Null 終了文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-250">Specifies a null-terminated string.</span></span> <span data-ttu-id="4a1b6-251">REG_SZ と同じです。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-251">Equivalent to REG_SZ.</span></span> |
| `ExpandString` | <span data-ttu-id="4a1b6-252">展開されていない null で終わる文字列を指定します</span><span class="sxs-lookup"><span data-stu-id="4a1b6-252">Specifies a null-terminated string that contains unexpanded</span></span> |
|                | <span data-ttu-id="4a1b6-253">環境変数への参照</span><span class="sxs-lookup"><span data-stu-id="4a1b6-253">references to environment variables that are expanded when</span></span> |
|                | <span data-ttu-id="4a1b6-254">値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-254">the value is retrieved.</span></span> <span data-ttu-id="4a1b6-255">REG_EXPAND_SZ と同じです。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-255">Equivalent to REG_EXPAND_SZ.</span></span> |
| `Binary` | <span data-ttu-id="4a1b6-256">あらゆる形式のバイナリ データを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-256">Specifies binary data in any form.</span></span> <span data-ttu-id="4a1b6-257">REG_BINARY と同じです。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-257">Equivalent to REG_BINARY.</span></span> |
| `DWord` | <span data-ttu-id="4a1b6-258">32 ビットのバイナリ数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-258">Specifies a 32-bit binary number.</span></span> <span data-ttu-id="4a1b6-259">REG_DWORD と同じです。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-259">Equivalent to REG_DWORD.</span></span> |
| `MultiString` | <span data-ttu-id="4a1b6-260">Null で終わる文字列の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-260">Specifies an array of null-terminated strings terminated by</span></span> |
|               | <span data-ttu-id="4a1b6-261">2つの null 文字。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-261">two null characters.</span></span> <span data-ttu-id="4a1b6-262">REG_MULTI_SZ と同じです。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-262">Equivalent to REG_MULTI_SZ.</span></span> |
| `QWord` | <span data-ttu-id="4a1b6-263">64ビットのバイナリ数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-263">Specifies a 64-bit binary number.</span></span> <span data-ttu-id="4a1b6-264">REG_QWORD と同じです。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-264">Equivalent to REG_QWORD.</span></span> |
| `Unknown` | <span data-ttu-id="4a1b6-265">サポートされていないレジストリデータ型を示します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-265">Indicates an unsupported registry data type, such as</span></span> |
|           | <span data-ttu-id="4a1b6-266">REG_RESOURCE_LIST。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-266">REG_RESOURCE_LIST.</span></span> |

#### <a name="cmdlets-supported"></a><span data-ttu-id="4a1b6-267">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="4a1b6-267">Cmdlets supported</span></span>

- [<span data-ttu-id="4a1b6-268">Set-Item</span><span class="sxs-lookup"><span data-stu-id="4a1b6-268">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)
- [<span data-ttu-id="4a1b6-269">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="4a1b6-269">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="using-the-pipeline"></a><span data-ttu-id="4a1b6-270">パイプラインの使用</span><span class="sxs-lookup"><span data-stu-id="4a1b6-270">Using the pipeline</span></span>

<span data-ttu-id="4a1b6-271">プロバイダーのコマンドレットは、パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-271">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="4a1b6-272">パイプラインを使用すると、1つのコマンドレットから別のプロバイダーのコマンドレットにプロバイダーデータを送信することにより、タスクを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-272">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span> <span data-ttu-id="4a1b6-273">プロバイダーコマンドレットでパイプラインを使用する方法の詳細については、この記事全体で説明されているコマンドレットリファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-273">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="4a1b6-274">ヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="4a1b6-274">Getting help</span></span>

<span data-ttu-id="4a1b6-275">Windows PowerShell 3.0 より、プロバイダー コマンドレットのためにカスタマイズされたヘルプ トピックを取得できます。これはファイル システム ドライブでのプロバイダー コマンドレットの動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-275">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="4a1b6-276">ファイルシステムドライブ用にカスタマイズされたヘルプトピックを取得するに `Get-Help` は、ファイルシステムドライブでコマンドを実行するか、 **Path** パラメーターを使用してファイルシステムドライブを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a1b6-276">To get the help topics that are customized for the file system drive, run a `Get-Help` command in a file system drive or use the **Path** parameter to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path HKLM:
```

## <a name="see-also"></a><span data-ttu-id="4a1b6-277">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a1b6-277">See also</span></span>

 [<span data-ttu-id="4a1b6-278">about_Providers</span><span class="sxs-lookup"><span data-stu-id="4a1b6-278">about_Providers</span></span>](../About/about_Providers.md)
