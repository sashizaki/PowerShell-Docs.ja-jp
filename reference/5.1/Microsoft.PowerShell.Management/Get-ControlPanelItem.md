---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 09/11/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ControlPanelItem
ms.openlocfilehash: 51bc04b4de901a611330266b6b0f58471f998432
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215475"
---
# <span data-ttu-id="e371b-103">Get-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="e371b-103">Get-ControlPanelItem</span></span>

## <span data-ttu-id="e371b-104">概要</span><span class="sxs-lookup"><span data-stu-id="e371b-104">SYNOPSIS</span></span>
<span data-ttu-id="e371b-105">コントロール パネル項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="e371b-105">Gets control panel items.</span></span>

## <span data-ttu-id="e371b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e371b-106">SYNTAX</span></span>

### <span data-ttu-id="e371b-107">RegularName (既定値)</span><span class="sxs-lookup"><span data-stu-id="e371b-107">RegularName (Default)</span></span>

```
Get-ControlPanelItem [[-Name] <String[]>] [-Category <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="e371b-108">CanonicalName</span><span class="sxs-lookup"><span data-stu-id="e371b-108">CanonicalName</span></span>

```
Get-ControlPanelItem -CanonicalName <String[]> [-Category <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="e371b-109">Description</span><span class="sxs-lookup"><span data-stu-id="e371b-109">DESCRIPTION</span></span>

<span data-ttu-id="e371b-110">`Get-ControlPanelItem`コマンドレットは、ローカルコンピューター上のコントロールパネル項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="e371b-110">The `Get-ControlPanelItem` cmdlet gets control panel items on the local computer.</span></span> <span data-ttu-id="e371b-111">ユーザー インターフェイスを持たないシステムであっても、名前、カテゴリ、または説明によってコントロール パネル項目を探すことができます。</span><span class="sxs-lookup"><span data-stu-id="e371b-111">You can use it to find control panel items by name, category, or description, even on systems that do not have a user interface.</span></span>

<span data-ttu-id="e371b-112">このコマンドレットは、システムで開くことができるコントロールパネル項目だけを取得します。</span><span class="sxs-lookup"><span data-stu-id="e371b-112">This cmdlet gets only the control panel items that can be opened on the system.</span></span> <span data-ttu-id="e371b-113">コントロールパネルまたはエクスプローラーがインストールされていないコンピューターでは、このコマンドレットは、これらのコンポーネントなしで開くことができるコントロールパネル項目だけを取得します。</span><span class="sxs-lookup"><span data-stu-id="e371b-113">On computers that do not have Control Panel or File Explorer, this cmdlet gets only control panel items that can open without these components.</span></span>

<span data-ttu-id="e371b-114">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e371b-114">This cmdlet was introduced in Windows PowerShell 3.0.</span></span> <span data-ttu-id="e371b-115">Windows 8 と Windows Server 2012 以降でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="e371b-115">It works only on Windows 8 and Windows Server 2012 and newer.</span></span>

## <span data-ttu-id="e371b-116">例</span><span class="sxs-lookup"><span data-stu-id="e371b-116">EXAMPLES</span></span>

### <span data-ttu-id="e371b-117">例 1: すべてのコントロール パネル項目を取得する</span><span class="sxs-lookup"><span data-stu-id="e371b-117">Example 1: Get all control panel items</span></span>

<span data-ttu-id="e371b-118">このコマンドは、ローカル コンピューター上のすべてのコントロール パネル項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="e371b-118">This command gets all control panel items on the local computer.</span></span>

```powershell
Get-ControlPanelItem
```

```Output
Name                          CanonicalName                 Category                      Description
----                          -------------                 --------                      -----------
Action Center                 Microsoft.ActionCenter        {System and Security}         Review recent messages and...
Administrative Tools          Microsoft.AdministrativeTools {System and Security}         Configure administrative s...
AutoPlay                      Microsoft.AutoPlay            {Hardware}                    Change default settings fo...
BitLocker Drive Encryption    Microsoft.BitLockerDriveEn... {System and Security}         Protect your computer usin...
Color Management              Microsoft.ColorManagement     {All Control Panel Items}     Change advanced color mana...
Credential Manager            Microsoft.CredentialManager   {User Accounts}               Manage your Windows Creden...
Date and Time                 Microsoft.DateAndTime         {Clock, Language, and Region} Set the date, time, and ti...
...
```

### <span data-ttu-id="e371b-119">例 2: コントロール パネル項目を名前で取得する</span><span class="sxs-lookup"><span data-stu-id="e371b-119">Example 2: Get control panel items by name</span></span>

<span data-ttu-id="e371b-120">この例では、名前にプログラムまたはアプリが含まれているコントロールパネル項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="e371b-120">This example gets control panel items that have Program or App in their names.</span></span>

```powershell
Get-ControlPanelItem -Name "*Program*", "*App*"
```

### <span data-ttu-id="e371b-121">例 3: コントロール パネル項目をカテゴリで取得する</span><span class="sxs-lookup"><span data-stu-id="e371b-121">Example 3: Get control panel items by category</span></span>

<span data-ttu-id="e371b-122">このコマンドは、名前にセキュリティが設定されているカテゴリのすべてのコントロールパネル項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="e371b-122">This command gets all control panel items in categories that have Security in their names.</span></span>

```powershell
Get-ControlPanelItem -Category "*Security*"
```

### <span data-ttu-id="e371b-123">例 4: コントロール パネル項目を開く</span><span class="sxs-lookup"><span data-stu-id="e371b-123">Example 4: Open a control panel item</span></span>

<span data-ttu-id="e371b-124">この例では、ローカルコンピューターの [Windows ファイアウォール] コントロールパネル項目を開きます。</span><span class="sxs-lookup"><span data-stu-id="e371b-124">This example opens the Windows Firewall control panel item on the local computer.</span></span>

```powershell
Get-ControlPanelItem -Name "Windows Firewall" | Show-ControlPanelItem
```

<span data-ttu-id="e371b-125">`Get-ControlPanelItem`コマンドレットでは、コントロールパネル項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="e371b-125">The `Get-ControlPanelItem` cmdlet gets the control panel item.</span></span> <span data-ttu-id="e371b-126">コマンドレットにより、 `Show-ControlPanelItem` ファイルが開きます。</span><span class="sxs-lookup"><span data-stu-id="e371b-126">The `Show-ControlPanelItem` cmdlet opens it.</span></span>

### <span data-ttu-id="e371b-127">例 5: リモート コンピューター上のコントロール パネル項目を取得する</span><span class="sxs-lookup"><span data-stu-id="e371b-127">Example 5: Get control panel items on a remote computer</span></span>

<span data-ttu-id="e371b-128">この例では、Server01 リモートコンピューター上のコントロールパネルの BitLocker ドライブ暗号化項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="e371b-128">This example gets the BitLocker Drive Encryption control panel item on the Server01 remote computer.</span></span>
<span data-ttu-id="e371b-129">コマンドレットは、 `Invoke-Command` `Get-ControlPanelItem` コマンドレットをリモートで実行します。</span><span class="sxs-lookup"><span data-stu-id="e371b-129">The `Invoke-Command` cmdlet runs the `Get-ControlPanelItem` cmdlet remotely.</span></span>

```powershell
Invoke-Command -ComputerName "Server01" {Get-ControlPanelItem -Name "BitLocker*" }
```

### <span data-ttu-id="e371b-130">例 6: コントロール パネル項目の説明を検索する</span><span class="sxs-lookup"><span data-stu-id="e371b-130">Example 6: Search the descriptions of control panel items</span></span>

<span data-ttu-id="e371b-131">この例では、[コントロールパネル] 項目の [ **説明** ] プロパティを検索して、name **デバイス** を含むものだけを取得します。</span><span class="sxs-lookup"><span data-stu-id="e371b-131">This example searches the **Description** property of the control panel items to get only those that contain the name **Device** .</span></span>

```powershell
Get-ControlPanelItem | Where-Object {$_.Description -like "*Device*"}
```

```Output
Name                    CanonicalName                 Category    Description
----                    -------------                 --------    -----------
AutoPlay                Microsoft.AutoPlay            {Hardware}  Change default settings fo...
Devices and Printers    Microsoft.DevicesAndPrinters  {Hardware}  View and manage devices, p...
Sound                   Microsoft.Sound               {Hardware}  Configure your audio devic...
```

<span data-ttu-id="e371b-132">コマンドレットでは、 `Get-ControlPanelItem` すべてのコントロールパネル項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="e371b-132">The `Get-ControlPanelItem` cmdlet gets all control panel items.</span></span> <span data-ttu-id="e371b-133">`Where-Object`コマンドレットは、 **Description** プロパティの値で項目をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="e371b-133">The `Where-Object` cmdlet filters the items by the value of the **Description** property.</span></span>

## <span data-ttu-id="e371b-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e371b-134">PARAMETERS</span></span>

### <span data-ttu-id="e371b-135">-CanonicalName</span><span class="sxs-lookup"><span data-stu-id="e371b-135">-CanonicalName</span></span>

<span data-ttu-id="e371b-136">コントロールパネルの項目を文字列配列として指定します。これらの項目は、このコマンドレットによって取得される正規名または名前パターンによって指定されます。</span><span class="sxs-lookup"><span data-stu-id="e371b-136">Specifies, as a string array, the control panel items by their canonical names or name patterns that this cmdlet gets.</span></span> <span data-ttu-id="e371b-137">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e371b-137">Wildcards are permitted.</span></span> <span data-ttu-id="e371b-138">複数の名前を入力すると、このコマンドレットは、名前リスト内の項目が "or" 演算子で区切られた場合と同様に、任意の名前に一致するコントロールパネル項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="e371b-138">If you enter multiple names, this cmdlet gets control panel items that match any of the names, as though the items in the name list were separated by an "or" operator.</span></span>

<span data-ttu-id="e371b-139">既定では、このコマンドレットは、システム内のすべてのコントロールパネル項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="e371b-139">By default, this cmdlet gets all control panel items in the system.</span></span>

```yaml
Type: System.String[]
Parameter Sets: CanonicalName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="e371b-140">-カテゴリ</span><span class="sxs-lookup"><span data-stu-id="e371b-140">-Category</span></span>

<span data-ttu-id="e371b-141">このコマンドレットが取得する指定されたカテゴリのコントロールパネル項目のカテゴリを文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="e371b-141">Specifies, as a string array, the categories of the control panel items in the specified categories that this cmdlet gets.</span></span> <span data-ttu-id="e371b-142">カテゴリ名または名前パターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="e371b-142">Enter a category name or name pattern.</span></span> <span data-ttu-id="e371b-143">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e371b-143">Wildcards are permitted.</span></span> <span data-ttu-id="e371b-144">複数の名前を入力すると、このコマンドレットは、名前リスト内の項目が "or" 演算子で区切られた場合と同様に、任意の名前に一致するコントロールパネル項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="e371b-144">If you enter multiple names, this cmdlet gets control panel items that match any of the names, as though the items in the name list were separated by an "or" operator.</span></span> <span data-ttu-id="e371b-145">既定では、このコマンドレットは、システム内のすべてのコントロールパネル項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="e371b-145">By default, this cmdlet gets all control panel items in the system.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="e371b-146">-Name</span><span class="sxs-lookup"><span data-stu-id="e371b-146">-Name</span></span>

<span data-ttu-id="e371b-147">このコマンドレットが取得するコントロールパネルの名前または名前パターンを文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="e371b-147">Specifies, as a string array, the names or name patterns of the control panel that this cmdlet gets.</span></span>
<span data-ttu-id="e371b-148">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e371b-148">Wildcards are permitted.</span></span> <span data-ttu-id="e371b-149">このコマンドレットには、パイプを使用して名前または名前パターンを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="e371b-149">You can also pipe a name or name pattern to this cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="e371b-150">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e371b-150">CommonParameters</span></span>

<span data-ttu-id="e371b-151">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e371b-151">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e371b-152">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e371b-152">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e371b-153">入力</span><span class="sxs-lookup"><span data-stu-id="e371b-153">INPUTS</span></span>

### <span data-ttu-id="e371b-154">System.String</span><span class="sxs-lookup"><span data-stu-id="e371b-154">System.String</span></span>

<span data-ttu-id="e371b-155">このコマンドレットには、名前または名前パターンをパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="e371b-155">You can pipe a name or name pattern to this cmdlet.</span></span>

## <span data-ttu-id="e371b-156">出力</span><span class="sxs-lookup"><span data-stu-id="e371b-156">OUTPUTS</span></span>

### <span data-ttu-id="e371b-157">Microsoft. PowerShell. Controlaccess Item</span><span class="sxs-lookup"><span data-stu-id="e371b-157">Microsoft.PowerShell.Commands.ControlPanelItem</span></span>

<span data-ttu-id="e371b-158">このコマンドレットは、ローカルコンピューター上のコントロールパネル項目を取得します。</span><span class="sxs-lookup"><span data-stu-id="e371b-158">This cmdlet gets control panel items on the local computer.</span></span>

## <span data-ttu-id="e371b-159">注</span><span class="sxs-lookup"><span data-stu-id="e371b-159">NOTES</span></span>

## <span data-ttu-id="e371b-160">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e371b-160">RELATED LINKS</span></span>

[<span data-ttu-id="e371b-161">Show-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="e371b-161">Show-ControlPanelItem</span></span>](Show-ControlPanelItem.md)
