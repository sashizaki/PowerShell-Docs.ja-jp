---
description: レジストリ
Locale: en-US
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_registry_provider?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: レジストリ プロバイダー
ms.openlocfilehash: 2d57afc164885b4d207108a360215e63a5431632
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602596"
---
# <a name="registry-provider"></a><span data-ttu-id="5bbd0-103">レジストリプロバイダー</span><span class="sxs-lookup"><span data-stu-id="5bbd0-103">Registry provider</span></span>

## <a name="provider-name"></a><span data-ttu-id="5bbd0-104">プロバイダー名</span><span class="sxs-lookup"><span data-stu-id="5bbd0-104">Provider name</span></span>

<span data-ttu-id="5bbd0-105">レジストリ</span><span class="sxs-lookup"><span data-stu-id="5bbd0-105">Registry</span></span>

## <a name="drives"></a><span data-ttu-id="5bbd0-106">ドライブ</span><span class="sxs-lookup"><span data-stu-id="5bbd0-106">Drives</span></span>

<span data-ttu-id="5bbd0-107">`HKLM:`, `HKCU:`</span><span class="sxs-lookup"><span data-stu-id="5bbd0-107">`HKLM:`, `HKCU:`</span></span>

## <a name="capabilities"></a><span data-ttu-id="5bbd0-108">機能</span><span class="sxs-lookup"><span data-stu-id="5bbd0-108">Capabilities</span></span>

<span data-ttu-id="5bbd0-109">"**プロセス**"、" **usetransactions** "</span><span class="sxs-lookup"><span data-stu-id="5bbd0-109">**ShouldProcess**, **UseTransactions**</span></span>

## <a name="short-description"></a><span data-ttu-id="5bbd0-110">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="5bbd0-110">Short description</span></span>

<span data-ttu-id="5bbd0-111">PowerShell のレジストリキー、エントリ、および値へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-111">Provides access to the registry keys, entries, and values in PowerShell.</span></span>

## <a name="detailed-description"></a><span data-ttu-id="5bbd0-112">詳しい説明</span><span class="sxs-lookup"><span data-stu-id="5bbd0-112">Detailed description</span></span>

<span data-ttu-id="5bbd0-113">Powershell **レジストリ** プロバイダーを使用すると、powershell のレジストリキー、エントリ、および値を取得、追加、変更、消去、削除できます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-113">The PowerShell **Registry** provider lets you get, add, change, clear, and delete registry keys, entries, and values in PowerShell.</span></span>

<span data-ttu-id="5bbd0-114">**レジストリ** ドライブは、コンピューター上のレジストリキーとサブキーを含む階層型の名前空間です。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-114">The **Registry** drives are a hierarchical namespace containing the registry keys and subkeys on your computer.</span></span> <span data-ttu-id="5bbd0-115">レジストリ エントリと値はその階層の構成要素ではありません。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-115">Registry entries and values are not components of that hierarchy.</span></span> <span data-ttu-id="5bbd0-116">各キーのプロパティです。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-116">Instead, they are properties of each of the keys.</span></span>

<span data-ttu-id="5bbd0-117">**レジストリ** プロバイダーは、この記事で説明されている次のコマンドレットをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-117">The **Registry** provider supports the following cmdlets, which are covered in this article.</span></span>

- [<span data-ttu-id="5bbd0-118">Get-Location</span><span class="sxs-lookup"><span data-stu-id="5bbd0-118">Get-Location</span></span>](xref:Microsoft.PowerShell.Management.Get-Location)
- [<span data-ttu-id="5bbd0-119">Set-Location</span><span class="sxs-lookup"><span data-stu-id="5bbd0-119">Set-Location</span></span>](xref:Microsoft.PowerShell.Management.Set-Location)
- [<span data-ttu-id="5bbd0-120">Get-Item</span><span class="sxs-lookup"><span data-stu-id="5bbd0-120">Get-Item</span></span>](xref:Microsoft.PowerShell.Management.Get-Item)
- [<span data-ttu-id="5bbd0-121">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="5bbd0-121">Get-ChildItem</span></span>](xref:Microsoft.PowerShell.Management.Get-ChildItem)
- [<span data-ttu-id="5bbd0-122">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="5bbd0-122">Invoke-Item</span></span>](xref:Microsoft.PowerShell.Management.Invoke-Item)
- [<span data-ttu-id="5bbd0-123">Move-Item</span><span class="sxs-lookup"><span data-stu-id="5bbd0-123">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="5bbd0-124">New-Item</span><span class="sxs-lookup"><span data-stu-id="5bbd0-124">New-Item</span></span>](xref:Microsoft.PowerShell.Management.New-Item)
- [<span data-ttu-id="5bbd0-125">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="5bbd0-125">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="5bbd0-126">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5bbd0-126">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="5bbd0-127">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5bbd0-127">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)
- [<span data-ttu-id="5bbd0-128">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5bbd0-128">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)
- [<span data-ttu-id="5bbd0-129">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5bbd0-129">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="5bbd0-130">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="5bbd0-130">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="5bbd0-131">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="5bbd0-131">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="types-exposed-by-this-provider"></a><span data-ttu-id="5bbd0-132">このプロバイダーによって公開される型</span><span class="sxs-lookup"><span data-stu-id="5bbd0-132">Types exposed by this provider</span></span>

<span data-ttu-id="5bbd0-133">レジストリキーは、 [Microsoft の Win32](/dotnet/api/microsoft.win32.registrykey) クラスのインスタンスとして表されます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-133">Registry keys are represented as instances of the [Microsoft.Win32.RegistryKey](/dotnet/api/microsoft.win32.registrykey) class.</span></span> <span data-ttu-id="5bbd0-134">レジストリエントリは、 [Pscustomobject](/dotnet/api/system.management.automation.pscustomobject) クラスのインスタンスとして表されます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-134">Registry entries are represented as instances of the [PSCustomObject](/dotnet/api/system.management.automation.pscustomobject) class.</span></span>

## <a name="navigating-the-registry-drives"></a><span data-ttu-id="5bbd0-135">レジストリドライブの移動</span><span class="sxs-lookup"><span data-stu-id="5bbd0-135">Navigating the Registry drives</span></span>

<span data-ttu-id="5bbd0-136">**レジストリ** プロバイダーは、そのデータストアを2つの既定のドライブとして公開します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-136">The **Registry** provider exposes its data store as two default drives.</span></span> <span data-ttu-id="5bbd0-137">レジストリの場所 HKEY_LOCAL_MACHINE がドライブにマップされ、 `HKLM:` HKEY_CURRENT_USER がドライブにマップされ `HKCU:` ます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-137">The registry location HKEY_LOCAL_MACHINE is mapped to the `HKLM:` drive and HKEY_CURRENT_USER is mapped to the `HKCU:` drive.</span></span> <span data-ttu-id="5bbd0-138">レジストリを操作するには、 `HKLM:` 次のコマンドを使用して場所をドライブに変更します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-138">To work with the registry, you can change your location to the `HKLM:` drive using the following command.</span></span>

```powershell
Set-Location HKLM:
```

<span data-ttu-id="5bbd0-139">ファイル システム ドライブに戻るには、ドライブ名を入力します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-139">To return to a file system drive, type the drive name.</span></span> <span data-ttu-id="5bbd0-140">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-140">For example, type:</span></span>

```powershell
Set-Location C:
```

<span data-ttu-id="5bbd0-141">他の PowerShell ドライブから **レジストリ** プロバイダーを操作することもできます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-141">You can also work with the **Registry** provider from any other PowerShell drive.</span></span> <span data-ttu-id="5bbd0-142">別の場所からレジストリキーを参照するには、パスのドライブ名 (、) を使用し `HKLM:` `HKCU:` ます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-142">To reference a registry key from another location, use the drive name (`HKLM:`, `HKCU:`) in the path.</span></span> <span data-ttu-id="5bbd0-143">\\**レジストリ** ドライブのレベルを示すには、円記号 () またはスラッシュ (/) を使用します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-143">Use a backslash (\\) or a forward slash (/) to indicate a level of the **Registry** drive.</span></span>

```powershell
PS C:\> cd HKLM:\Software
```

> [!NOTE]
> <span data-ttu-id="5bbd0-144">PowerShell では、エイリアスを使用して、プロバイダーパスを操作するための使い慣れた方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-144">PowerShell uses aliases to allow you a familiar way to work with provider paths.</span></span> <span data-ttu-id="5bbd0-145">`dir`やなどのコマンド `ls` は、 [get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem)のエイリアスであり、 `cd` [Set Location](xref:Microsoft.PowerShell.Management.Set-Location)のエイリアスであり、 `pwd` [get location](xref:Microsoft.PowerShell.Management.Get-Location)のエイリアスです。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-145">Commands such as `dir` and `ls` are now aliases for [Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem), `cd` is an alias for [Set-Location](xref:Microsoft.PowerShell.Management.Set-Location), and `pwd` is an alias for [Get-Location](xref:Microsoft.PowerShell.Management.Get-Location).</span></span>

<span data-ttu-id="5bbd0-146">この最後の例は、 **レジストリ** プロバイダーの移動に使用できる別のパス構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-146">This last example shows another path syntax you can use to navigate the **Registry** provider.</span></span> <span data-ttu-id="5bbd0-147">この構文では、プロバイダー名に続けて2つのコロンが使用され `::` ます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-147">This syntax uses the provider name, followed by two colons `::`.</span></span> <span data-ttu-id="5bbd0-148">この構文では、マップされたドライブ名ではなく、完全な HIVE 名を使用でき `HKLM` ます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-148">This syntax allows you to use the full HIVE name, instead of the mapped drive name `HKLM`.</span></span>

```powershell
cd "Registry::HKEY_LOCAL_MACHINE\Software"
```

## <a name="displaying-the-contents-of-registry-keys"></a><span data-ttu-id="5bbd0-149">レジストリキーの内容を表示しています</span><span class="sxs-lookup"><span data-stu-id="5bbd0-149">Displaying the contents of registry keys</span></span>

<span data-ttu-id="5bbd0-150">レジストリは、キー、サブキー、およびエントリに分割されます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-150">The registry is divided into keys, subkeys, and entries.</span></span> <span data-ttu-id="5bbd0-151">レジストリ構造の詳細については、「 [レジストリの構造](/windows/desktop/sysinfo/structure-of-the-registry)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-151">For more information about registry structure, see [Structure of the Registry](/windows/desktop/sysinfo/structure-of-the-registry).</span></span>

<span data-ttu-id="5bbd0-152">**レジストリ** ドライブでは、各キーはコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-152">In a **Registry** drive, each key is a container.</span></span> <span data-ttu-id="5bbd0-153">キーには、任意の数のキーを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-153">A key can contain any number of keys.</span></span> <span data-ttu-id="5bbd0-154">親キーを持つレジストリキーは、サブキーと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-154">A registry key that has a parent key is called a subkey.</span></span> <span data-ttu-id="5bbd0-155">を使用し `Get-ChildItem` て、レジストリキーを表示したり `Set-Location` 、キーのパスに移動したりできます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-155">You can use `Get-ChildItem` to view registry keys and `Set-Location` to navigate to a key path.</span></span>

<span data-ttu-id="5bbd0-156">レジストリ値はレジストリキーの属性です。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-156">Registry values are attributes of a registry key.</span></span> <span data-ttu-id="5bbd0-157">**レジストリ** ドライブでは、**アイテムのプロパティ** と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-157">In the **Registry** drive, they are called **Item Properties**.</span></span> <span data-ttu-id="5bbd0-158">レジストリキーには、子キーと項目プロパティの両方を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-158">A registry key can have both children keys and item properties.</span></span>

<span data-ttu-id="5bbd0-159">この例では、との `Get-Item` 違い `Get-ChildItem` が示されています。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-159">In this example, the difference between `Get-Item` and `Get-ChildItem` is shown.</span></span> <span data-ttu-id="5bbd0-160">を `Get-Item` "スプーラ" レジストリキーに対して使用すると、そのプロパティを表示できます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-160">When you use `Get-Item` on the "Spooler" registry key, you can view its properties.</span></span>

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

<span data-ttu-id="5bbd0-161">各レジストリキーには、サブキーを含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-161">Each registry key can also have subkeys.</span></span> <span data-ttu-id="5bbd0-162">レジストリキーでを使用する場合 `Get-Item` 、サブキーは表示されません。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-162">When you use `Get-Item` on a registry key, the subkeys are not displayed.</span></span> <span data-ttu-id="5bbd0-163">`Get-ChildItem`コマンドレットにより、各サブキーのプロパティを含む "スプーラ" キーの子項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-163">The `Get-ChildItem` cmdlet will show you children items of the "Spooler" key, including each subkey's properties.</span></span> <span data-ttu-id="5bbd0-164">を使用する場合、[親キー] プロパティは表示されません `Get-ChildItem` 。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-164">The parent keys properties are not shown when using `Get-ChildItem`.</span></span>

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

<span data-ttu-id="5bbd0-165">`Get-Item`コマンドレットは、現在の場所でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-165">The `Get-Item` cmdlet can also be used on the current location.</span></span> <span data-ttu-id="5bbd0-166">次の例では、"スプーラ" レジストリキーに移動し、アイテムのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-166">The following example navigates to the "Spooler" registry key and gets the item properties.</span></span>
<span data-ttu-id="5bbd0-167">ドット `.` は、現在の場所を示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-167">The dot `.` is used to indicate the current location.</span></span>

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

<span data-ttu-id="5bbd0-168">このセクションで説明するコマンドレットの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-168">For more information on the cmdlets covered in this section, see the following articles.</span></span>

<span data-ttu-id="5bbd0-169">-[項目](xref:Microsoft.PowerShell.Management.Get-Item) 
- の取得[Get-childitem](xref:Microsoft.PowerShell.Management.Get-ChildItem)</span><span class="sxs-lookup"><span data-stu-id="5bbd0-169">-[Get-Item](xref:Microsoft.PowerShell.Management.Get-Item)
-[Get-ChildItem](xref:Microsoft.PowerShell.Management.Get-ChildItem)</span></span>

## <a name="viewing-registry-key-values"></a><span data-ttu-id="5bbd0-170">レジストリキー値の表示</span><span class="sxs-lookup"><span data-stu-id="5bbd0-170">Viewing registry key values</span></span>

<span data-ttu-id="5bbd0-171">レジストリキーの値は、各レジストリキーのプロパティとして格納されます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-171">Registry key values are stored as properties of each registry key.</span></span> <span data-ttu-id="5bbd0-172">`Get-ItemProperty`コマンドレットは、指定した名前を使用してレジストリキーのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-172">The `Get-ItemProperty` cmdlet views registry key properties using the name you specify.</span></span> <span data-ttu-id="5bbd0-173">結果として、指定したプロパティを含む **Pscustomobject** 生成されます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-173">The result is a **PSCustomObject** containing the properties you specify.</span></span>

<span data-ttu-id="5bbd0-174">次の例では、 `Get-ItemProperty` コマンドレットを使用してすべてのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-174">The Following example uses the `Get-ItemProperty` cmdlet to view all properties.</span></span> <span data-ttu-id="5bbd0-175">生成されたオブジェクトを変数に格納すると、目的のプロパティ値にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-175">Storing the resulting object in a variable allows you to access the desired property value.</span></span>

```powershell
$p = Get-ItemProperty -Path HKLM:\SYSTEM\CurrentControlSet\Services\Spooler
$p.DependOnService
```

```output
RPCSS
http
```

<span data-ttu-id="5bbd0-176">パラメーターの値を指定 `-Name` すると、指定したプロパティが選択され、 **Pscustomobject** 返されます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-176">Specifying a value for the `-Name` parameter selects the properties you specify and returns the **PSCustomObject**.</span></span>  <span data-ttu-id="5bbd0-177">次の例は、パラメーターを使用した場合の出力の違いを示して `-Name` います。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-177">The following example shows the difference in output when you use the `-Name` parameter.</span></span>

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

<span data-ttu-id="5bbd0-178">PowerShell 5.0 以降では、 `Get-ItemPropertyValue` コマンドレットは、指定したプロパティの値のみを返します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-178">Beginning in PowerShell 5.0, the `Get-ItemPropertyValue` cmdlet returns only the value of the property you specify.</span></span>

```powershell
Get-ItemPropertyValue -Path HKLM:\SOFTWARE\Microsoft\Wbem -Name BUILD
```

```output
17134.1
```

<span data-ttu-id="5bbd0-179">このセクションで使用するコマンドレットの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-179">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="5bbd0-180">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5bbd0-180">Get-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)
- [<span data-ttu-id="5bbd0-181">Get-ItemPropertyValue</span><span class="sxs-lookup"><span data-stu-id="5bbd0-181">Get-ItemPropertyValue</span></span>](xref:Microsoft.PowerShell.Management.Get-ItemProperty)

## <a name="changing-registry-key-values"></a><span data-ttu-id="5bbd0-182">レジストリキー値の変更</span><span class="sxs-lookup"><span data-stu-id="5bbd0-182">Changing registry key values</span></span>

<span data-ttu-id="5bbd0-183">`Set-ItemProperty`コマンドレットでは、レジストリキーの属性を設定します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-183">The `Set-ItemProperty` cmdlet will set attributes for registry keys.</span></span> <span data-ttu-id="5bbd0-184">次の例では、を使用して `Set-ItemProperty` 、スプーラサービスの開始の種類を手動に変更します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-184">The following example uses `Set-ItemProperty` to change the spooler service start type to manual.</span></span> <span data-ttu-id="5bbd0-185">この例では、コマンドレットを使用して、 **Starttype** を *Automatic* に戻し `Set-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-185">The example changes the **StartType** back to *Automatic* using the `Set-Service` cmdlet.</span></span>

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

<span data-ttu-id="5bbd0-186">各レジストリキーには *既定* 値があります。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-186">Each registry key has a *default* value.</span></span> <span data-ttu-id="5bbd0-187">レジストリキーの *既定* 値は、またはのいずれかを使用して変更でき `Set-Item` `Set-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-187">You can change the *default* value for a registry key with either `Set-Item` or `Set-ItemProperty`.</span></span>

```powershell
Set-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name "(default)" -Value "one"
Set-Item -Path HKLM:\SOFTWARE\Contoso -Value "two"
```

<span data-ttu-id="5bbd0-188">このセクションで使用するコマンドレットの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-188">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="5bbd0-189">Set-Item</span><span class="sxs-lookup"><span data-stu-id="5bbd0-189">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)
- [<span data-ttu-id="5bbd0-190">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5bbd0-190">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="creating-registry-keys-and-values"></a><span data-ttu-id="5bbd0-191">レジストリキーと値の作成</span><span class="sxs-lookup"><span data-stu-id="5bbd0-191">Creating registry keys and values</span></span>

<span data-ttu-id="5bbd0-192">コマンドレットにより、指定した `New-Item` 名前のレジストリキーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-192">The `New-Item` cmdlet will create registry keys with a name that you provide.</span></span>
<span data-ttu-id="5bbd0-193">関数を使用することもでき `mkdir` ます。この関数は、内部でコマンドレットを呼び出します `New-Item` 。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-193">You can also use the `mkdir` function, which calls the `New-Item` cmdlet internally.</span></span>

```
PS HKLM:\SOFTWARE\> mkdir ContosoCompany

    Hive: HKEY_LOCAL_MACHINE\SOFTWARE

Name                           Property
----                           --------
ContosoCompany
```

<span data-ttu-id="5bbd0-194">コマンドレットを使用して、指定した `New-ItemProperty` レジストリキーに値を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-194">You can use the `New-ItemProperty` cmdlet to create values in a registry key that you specify.</span></span> <span data-ttu-id="5bbd0-195">次の例では、ContosoCompany レジストリキーに新しい DWORD 値を作成します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-195">The following example creates a new DWORD value on the ContosoCompany registry key.</span></span>

```powershell
$path = "HKLM:\SOFTWARE\ContosoCompany"
New-ItemProperty -Path  -Name Test -Type DWORD -Value 1
```

> [!NOTE]
> <span data-ttu-id="5bbd0-196">その他の許可されている型の値については、この記事の「動的パラメーター」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-196">Review the dynamic parameters section in this article for other allowed type values.</span></span>

<span data-ttu-id="5bbd0-197">コマンドレットの使用方法の詳細については、「 [get-itemproperty](xref:Microsoft.PowerShell.Management.New-ItemProperty)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-197">For detailed cmdlet usage, see [New-ItemProperty](xref:Microsoft.PowerShell.Management.New-ItemProperty).</span></span>

## <a name="copying-registry-keys-and-values"></a><span data-ttu-id="5bbd0-198">レジストリキーと値のコピー</span><span class="sxs-lookup"><span data-stu-id="5bbd0-198">Copying registry keys and values</span></span>

<span data-ttu-id="5bbd0-199">**レジストリ** プロバイダーで、コマンドレットを使用して、 `Copy-Item` レジストリキーと値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-199">In the **Registry** provider, use the `Copy-Item` cmdlet copies registry keys and values.</span></span> <span data-ttu-id="5bbd0-200">コマンドレットを使用して、 `Copy-ItemProperty` レジストリ値のみをコピーします。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-200">Use the `Copy-ItemProperty` cmdlet to copy registry values only.</span></span>
<span data-ttu-id="5bbd0-201">次のコマンドは、"Contoso" レジストリキーとそのプロパティを、指定された場所 "HKLM:\ ソフトウェア \ Fabrikam" にコピーします。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-201">The following command copies the "Contoso" registry key, and its properties to the specified location "HKLM:\Software\Fabrikam".</span></span>

<span data-ttu-id="5bbd0-202">`Copy-Item` コピー先キーが存在しない場合は、作成します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-202">`Copy-Item` creates the destination key if it does not exist.</span></span> <span data-ttu-id="5bbd0-203">コピー先のキーが存在する場合は、コピー先のキーの `Copy-Item` 子項目 (サブキー) として、ソースキーの複製が作成されます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-203">If the destination key exists, `Copy-Item` creates a duplicate of the source key as a child item (subkey) of the destination key.</span></span>

```powershell
Copy-Item -Path  HKLM:\Software\Contoso -Destination HKLM:\Software\Fabrikam
```

<span data-ttu-id="5bbd0-204">次のコマンドは、コマンドレットを使用して、" `Copy-ItemProperty` Contoso" キーから "Fabrikam" キーに "Server" の値をコピーします。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-204">The following command uses the `Copy-ItemProperty` cmdlet to copy the "Server" value from the "Contoso" key to the "Fabrikam" key.</span></span>

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Copy-ItemProperty -Path $source -Destination $dest -Name Server
```

<span data-ttu-id="5bbd0-205">このセクションで使用するコマンドレットの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-205">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="5bbd0-206">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="5bbd0-206">Copy-Item</span></span>](xref:Microsoft.PowerShell.Management.Copy-Item)
- [<span data-ttu-id="5bbd0-207">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5bbd0-207">Copy-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Copy-ItemProperty)

## <a name="moving-registry-keys-and-values"></a><span data-ttu-id="5bbd0-208">レジストリキーと値の移動</span><span class="sxs-lookup"><span data-stu-id="5bbd0-208">Moving registry keys and values</span></span>

<span data-ttu-id="5bbd0-209">`Move-Item` `Move-ItemProperty` コマンドレットとコマンドレットは、対応する "Copy" のように動作します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-209">The `Move-Item` and `Move-ItemProperty` cmdlets behave like their "Copy" counterparts.</span></span> <span data-ttu-id="5bbd0-210">コピー先が存在する場合は、コピー `Move-Item` 先のキーの下にソースキーを移動します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-210">If the destination exists, `Move-Item` moves the source key underneath the destination key.</span></span> <span data-ttu-id="5bbd0-211">コピー先のキーが存在しない場合は、ソースキーが移行先のパスに移動されます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-211">If the destination key does not exist, the source key is moved to the destination path.</span></span>

<span data-ttu-id="5bbd0-212">次のコマンドを実行すると、"Contoso" キーがパス "HKLM:\ \ ソフトウェア \ Fabrikam" に移動します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-212">The following command moves the "Contoso" key to the path "HKLM:\SOFTWARE\Fabrikam".</span></span>

```powershell
Move-Item -Path HKLM:\SOFTWARE\Contoso -Destination HKLM:\SOFTWARE\Fabrikam
```

<span data-ttu-id="5bbd0-213">このコマンドは、すべてのプロパティを "HKLM:\ SOFTWARE\ContosoCompany" から "HKLM:\ Fabrikam" に移動します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-213">This command moves all of the properties from "HKLM:\SOFTWARE\ContosoCompany" to "HKLM:\SOFTWARE\Fabrikam".</span></span>

```powershell
$source = "HKLM:\SOFTWARE\Contoso"
$dest = "HKLM:\SOFTWARE\Fabrikam"
Move-ItemProperty -Path $source -Destination $dest -Name *
```

<span data-ttu-id="5bbd0-214">このセクションで使用するコマンドレットの詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-214">For more information on the cmdlets used in this section, see the following articles.</span></span>

- [<span data-ttu-id="5bbd0-215">Move-Item</span><span class="sxs-lookup"><span data-stu-id="5bbd0-215">Move-Item</span></span>](xref:Microsoft.PowerShell.Management.Move-Item)
- [<span data-ttu-id="5bbd0-216">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5bbd0-216">Move-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Move-ItemProperty)

## <a name="renaming-registry-keys-and-values"></a><span data-ttu-id="5bbd0-217">レジストリキーと値の名前を変更する</span><span class="sxs-lookup"><span data-stu-id="5bbd0-217">Renaming registry keys and values</span></span>

<span data-ttu-id="5bbd0-218">レジストリキーと値の名前は、ファイルやフォルダーと同じように変更できます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-218">You can rename registry keys and values just like you would files and folders.</span></span>
<span data-ttu-id="5bbd0-219">`Rename-Item` レジストリ値の名前を変更するときに、レジストリキーの名前を変更 `Rename-ItemProperty` します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-219">`Rename-Item` renames registry keys, while `Rename-ItemProperty` renames registry values.</span></span>

```powershell
$path = "HKLM:\SOFTWARE\Contoso"
Rename-ItemProperty -Path $path -Name ContosoTest -NewName FabrikamTest
Rename-Item -Path $path -NewName Fabrikam
```

## <a name="changing-security-descriptors"></a><span data-ttu-id="5bbd0-220">セキュリティ記述子の変更</span><span class="sxs-lookup"><span data-stu-id="5bbd0-220">Changing security descriptors</span></span>

<span data-ttu-id="5bbd0-221">およびコマンドレットを使用して、レジストリキーへのアクセスを制限することができ `Get-Acl` `Set-Acl` ます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-221">You can restrict access to registry keys using the `Get-Acl` and `Set-Acl` cmdlets.</span></span> <span data-ttu-id="5bbd0-222">次の例では、"HKLM:\ \ ソフトウェア \ Contoso" レジストリキーにフルコントロールを持つ新しいユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-222">The following example adds a new user with full control to the "HKLM:\SOFTWARE\Contoso" registry key.</span></span>

```powershell
$acl = Get-Acl -Path HKLM:\SOFTWARE\Contoso
$rule = New-Object System.Security.AccessControl.RegistryAccessRule `
("CONTOSO\jsmith", "FullControl", "Allow")
$acl.SetAccessRule($rule)
$acl | Set-Acl -Path HKLM:\SOFTWARE\Contoso
```

<span data-ttu-id="5bbd0-223">その他の例とコマンドレットの使用方法の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-223">For more examples and cmdlet usage details see the following articles.</span></span>

- [<span data-ttu-id="5bbd0-224">Get-Acl</span><span class="sxs-lookup"><span data-stu-id="5bbd0-224">Get-Acl</span></span>](xref:Microsoft.PowerShell.Security.Get-Acl)
- [<span data-ttu-id="5bbd0-225">Set-Acl</span><span class="sxs-lookup"><span data-stu-id="5bbd0-225">Set-Acl</span></span>](xref:Microsoft.PowerShell.Security.Set-Acl)

## <a name="removing-and-clearing-registry-keys-and-values"></a><span data-ttu-id="5bbd0-226">レジストリキーと値の削除と消去</span><span class="sxs-lookup"><span data-stu-id="5bbd0-226">Removing and clearing registry keys and values</span></span>

<span data-ttu-id="5bbd0-227">**削除項目** を使用して、含まれる項目を削除できますが、項目に他の項目が含まれている場合は、削除を確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-227">You can remove contained items by using **Remove-Item**, but you will be prompted to confirm the removal if the item contains anything else.</span></span> <span data-ttu-id="5bbd0-228">次の例では、キー "HKLM:\ \ ソフトウェア \ Contoso" を削除しようとしています。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-228">The following example attempts to delete a key "HKLM:\SOFTWARE\Contoso".</span></span>

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

<span data-ttu-id="5bbd0-229">メッセージを表示せずに含まれる項目を削除するには、パラメーターを指定し `-Recurse` ます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-229">To delete contained items without prompting, specify the `-Recurse` parameter.</span></span>

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso -Recurse
```

<span data-ttu-id="5bbd0-230">"Hklm:\ \ ソフトウェア \ contoso" 内のすべての項目を削除するが、"HKLM:\ $ $ contoso" 自体は削除しない場合は、末尾に円記号を付けた後にワイルドカードを使用し `\` ます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-230">If you wanted to remove all items within "HKLM:\SOFTWARE\Contoso" but not "HKLM:\SOFTWARE\Contoso" itself, use a trailing backslash `\` followed by a wildcard.</span></span>

```powershell
Remove-Item -Path HKLM:\SOFTWARE\Contoso\* -Recurse
```

<span data-ttu-id="5bbd0-231">このコマンドは、"HKLM:\ ContosoTest" レジストリキーから "" レジストリ値を削除します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-231">This command deletes the "ContosoTest" registry value from the "HKLM:\SOFTWARE\Contoso" registry key.</span></span>

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Contoso -Name ContosoTest
```

<span data-ttu-id="5bbd0-232">`Clear-Item` キーのすべてのレジストリ値をクリアします。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-232">`Clear-Item` clears all registry values for a key.</span></span> <span data-ttu-id="5bbd0-233">次の例では、"HKLM:\ \ ソフトウェア \ Contoso" レジストリキーからすべての値を削除します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-233">The following example clears all values from the "HKLM:\SOFTWARE\Contoso" registry key.</span></span> <span data-ttu-id="5bbd0-234">特定のプロパティのみをクリアするには、を使用し `Clear-ItemProperty` ます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-234">To clear only a specific property, use `Clear-ItemProperty`.</span></span>

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

<span data-ttu-id="5bbd0-235">その他の例とコマンドレットの使用方法の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-235">For more examples and cmdlet usage details see the following articles.</span></span>

- [<span data-ttu-id="5bbd0-236">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="5bbd0-236">Clear-Item</span></span>](xref:Microsoft.PowerShell.Management.Clear-Item)
- [<span data-ttu-id="5bbd0-237">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5bbd0-237">Clear-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Clear-ItemProperty)
- [<span data-ttu-id="5bbd0-238">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="5bbd0-238">Remove-Item</span></span>](xref:Microsoft.PowerShell.Management.Remove-Item)
- [<span data-ttu-id="5bbd0-239">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5bbd0-239">Remove-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Remove-ItemProperty)

## <a name="dynamic-parameters"></a><span data-ttu-id="5bbd0-240">動的パラメーター</span><span class="sxs-lookup"><span data-stu-id="5bbd0-240">Dynamic parameters</span></span>

<span data-ttu-id="5bbd0-241">動的パラメーターは、PowerShell プロバイダーによって追加されるコマンドレットパラメーターであり、プロバイダーに対応したドライブでコマンドレットが使用されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-241">Dynamic parameters are cmdlet parameters that are added by a PowerShell provider and are available only when the cmdlet is being used in the provider-enabled drive.</span></span>

### <a name="type-microsoftwin32registryvaluekind"></a><span data-ttu-id="5bbd0-242">「<>」と入力します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-242">Type <Microsoft.Win32.RegistryValueKind></span></span>

<span data-ttu-id="5bbd0-243">レジストリ値のデータ型を確立または変更します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-243">Establishes or changes the data type of a registry value.</span></span> <span data-ttu-id="5bbd0-244">既定値は `String` (REG_SZ) です。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-244">The default is `String` (REG_SZ).</span></span>

<span data-ttu-id="5bbd0-245">このパラメーターは [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty) コマンドレットの設計に基づき動作します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-245">This parameter works as designed on the [Set-ItemProperty](xref:Microsoft.PowerShell.Management.Set-ItemProperty) cmdlet.</span></span> <span data-ttu-id="5bbd0-246">レジストリ ドライブの [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item) コマンドレットでも利用できますが、効果はありません。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-246">It is also available on the [Set-Item](xref:Microsoft.PowerShell.Management.Set-Item) cmdlet in the registry drives, but it has no effect.</span></span>

|<span data-ttu-id="5bbd0-247">値</span><span class="sxs-lookup"><span data-stu-id="5bbd0-247">Value</span></span> | <span data-ttu-id="5bbd0-248">説明</span><span class="sxs-lookup"><span data-stu-id="5bbd0-248">Description</span></span> |
| ---- | ----------- |
| `String` | <span data-ttu-id="5bbd0-249">Null 終了文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-249">Specifies a null-terminated string.</span></span> <span data-ttu-id="5bbd0-250">REG_SZ と同じです。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-250">Equivalent to REG_SZ.</span></span> |
| `ExpandString` | <span data-ttu-id="5bbd0-251">展開されていない null で終わる文字列を指定します</span><span class="sxs-lookup"><span data-stu-id="5bbd0-251">Specifies a null-terminated string that contains unexpanded</span></span> |
|                | <span data-ttu-id="5bbd0-252">環境変数への参照</span><span class="sxs-lookup"><span data-stu-id="5bbd0-252">references to environment variables that are expanded when</span></span> |
|                | <span data-ttu-id="5bbd0-253">値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-253">the value is retrieved.</span></span> <span data-ttu-id="5bbd0-254">REG_EXPAND_SZ と同じです。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-254">Equivalent to REG_EXPAND_SZ.</span></span> |
| `Binary` | <span data-ttu-id="5bbd0-255">あらゆる形式のバイナリ データを指定します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-255">Specifies binary data in any form.</span></span> <span data-ttu-id="5bbd0-256">REG_BINARY と同じです。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-256">Equivalent to REG_BINARY.</span></span> |
| `DWord` | <span data-ttu-id="5bbd0-257">32 ビットのバイナリ数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-257">Specifies a 32-bit binary number.</span></span> <span data-ttu-id="5bbd0-258">REG_DWORD と同じです。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-258">Equivalent to REG_DWORD.</span></span> |
| `MultiString` | <span data-ttu-id="5bbd0-259">Null で終わる文字列の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-259">Specifies an array of null-terminated strings terminated by</span></span> |
|               | <span data-ttu-id="5bbd0-260">2つの null 文字。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-260">two null characters.</span></span> <span data-ttu-id="5bbd0-261">REG_MULTI_SZ と同じです。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-261">Equivalent to REG_MULTI_SZ.</span></span> |
| `QWord` | <span data-ttu-id="5bbd0-262">64ビットのバイナリ数値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-262">Specifies a 64-bit binary number.</span></span> <span data-ttu-id="5bbd0-263">REG_QWORD と同じです。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-263">Equivalent to REG_QWORD.</span></span> |
| `Unknown` | <span data-ttu-id="5bbd0-264">サポートされていないレジストリデータ型を示します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-264">Indicates an unsupported registry data type, such as</span></span> |
|           | <span data-ttu-id="5bbd0-265">REG_RESOURCE_LIST。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-265">REG_RESOURCE_LIST.</span></span> |

#### <a name="cmdlets-supported"></a><span data-ttu-id="5bbd0-266">サポートされているコマンドレット</span><span class="sxs-lookup"><span data-stu-id="5bbd0-266">Cmdlets supported</span></span>

- [<span data-ttu-id="5bbd0-267">Set-Item</span><span class="sxs-lookup"><span data-stu-id="5bbd0-267">Set-Item</span></span>](xref:Microsoft.PowerShell.Management.Set-Item)
- [<span data-ttu-id="5bbd0-268">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="5bbd0-268">Set-ItemProperty</span></span>](xref:Microsoft.PowerShell.Management.Set-ItemProperty)

## <a name="using-the-pipeline"></a><span data-ttu-id="5bbd0-269">パイプラインの使用</span><span class="sxs-lookup"><span data-stu-id="5bbd0-269">Using the pipeline</span></span>

<span data-ttu-id="5bbd0-270">プロバイダーのコマンドレットは、パイプラインの入力を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-270">Provider cmdlets accept pipeline input.</span></span> <span data-ttu-id="5bbd0-271">パイプラインを使用すると、1つのコマンドレットから別のプロバイダーのコマンドレットにプロバイダーデータを送信することにより、タスクを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-271">You can use the pipeline to simplify task by sending provider data from one cmdlet to another provider cmdlet.</span></span> <span data-ttu-id="5bbd0-272">プロバイダーコマンドレットでパイプラインを使用する方法の詳細については、この記事全体で説明されているコマンドレットリファレンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-272">To read more about how to use the pipeline with provider cmdlets, see the cmdlet references provided throughout this article.</span></span>

## <a name="getting-help"></a><span data-ttu-id="5bbd0-273">ヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="5bbd0-273">Getting help</span></span>

<span data-ttu-id="5bbd0-274">Windows PowerShell 3.0 より、プロバイダー コマンドレットのためにカスタマイズされたヘルプ トピックを取得できます。これはファイル システム ドライブでのプロバイダー コマンドレットの動作を説明します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-274">Beginning in Windows PowerShell 3.0, you can get customized help topics for provider cmdlets that explain how those cmdlets behave in a file system drive.</span></span>

<span data-ttu-id="5bbd0-275">ファイルシステムドライブ用にカスタマイズされたヘルプトピックを取得するに `Get-Help` は、ファイルシステムドライブでコマンドを実行するか、 **Path** パラメーターを使用してファイルシステムドライブを指定します。</span><span class="sxs-lookup"><span data-stu-id="5bbd0-275">To get the help topics that are customized for the file system drive, run a `Get-Help` command in a file system drive or use the **Path** parameter to specify a file system drive.</span></span>

```powershell
Get-Help Get-ChildItem
```

```powershell
Get-Help Get-ChildItem -Path HKLM:
```

## <a name="see-also"></a><span data-ttu-id="5bbd0-276">関連項目</span><span class="sxs-lookup"><span data-stu-id="5bbd0-276">See also</span></span>

 [<span data-ttu-id="5bbd0-277">about_Providers</span><span class="sxs-lookup"><span data-stu-id="5bbd0-277">about_Providers</span></span>](../About/about_Providers.md)

