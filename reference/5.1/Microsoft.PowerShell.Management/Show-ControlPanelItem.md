---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 04/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/show-controlpanelitem?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-ControlPanelItem
ms.openlocfilehash: 368e385d51437f9ac93b700c929b185dce30a644
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214403"
---
# <span data-ttu-id="de5d4-103">Show-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="de5d4-103">Show-ControlPanelItem</span></span>

## <span data-ttu-id="de5d4-104">概要</span><span class="sxs-lookup"><span data-stu-id="de5d4-104">SYNOPSIS</span></span>
<span data-ttu-id="de5d4-105">コントロール パネル項目を開きます。</span><span class="sxs-lookup"><span data-stu-id="de5d4-105">Opens control panel items.</span></span>

## <span data-ttu-id="de5d4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="de5d4-106">SYNTAX</span></span>

### <span data-ttu-id="de5d4-107">RegularName (既定値)</span><span class="sxs-lookup"><span data-stu-id="de5d4-107">RegularName (Default)</span></span>

```
Show-ControlPanelItem [-Name] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="de5d4-108">CanonicalName</span><span class="sxs-lookup"><span data-stu-id="de5d4-108">CanonicalName</span></span>

```
Show-ControlPanelItem -CanonicalName <String[]> [<CommonParameters>]
```

### <span data-ttu-id="de5d4-109">Get-controlpanelitem</span><span class="sxs-lookup"><span data-stu-id="de5d4-109">ControlPanelItem</span></span>

```
Show-ControlPanelItem [[-InputObject] <ControlPanelItem[]>] [<CommonParameters>]
```

## <span data-ttu-id="de5d4-110">Description</span><span class="sxs-lookup"><span data-stu-id="de5d4-110">DESCRIPTION</span></span>

<span data-ttu-id="de5d4-111">コマンドレットにより、 `Show-ControlPanelItem` ローカルコンピューター上のコントロールパネル項目が開きます。</span><span class="sxs-lookup"><span data-stu-id="de5d4-111">The `Show-ControlPanelItem` cmdlet opens control panel items on the local computer.</span></span> <span data-ttu-id="de5d4-112">これを使用すると、ユーザーインターフェイスを持たないシステムであっても、名前、カテゴリ、または説明でコントロールパネル項目を開くことができます。</span><span class="sxs-lookup"><span data-stu-id="de5d4-112">You can use it to open control panel items by name, category, or description, even on systems that do not have a user interface.</span></span> <span data-ttu-id="de5d4-113">パイプを使用して、コントロールパネルの項目をコマンドレットからに送ることができ `Get-ControlPanelItem` `Show-ControlPanelItem` ます。</span><span class="sxs-lookup"><span data-stu-id="de5d4-113">You can pipe control panel items from the `Get-ControlPanelItem` cmdlet to `Show-ControlPanelItem`.</span></span>

<span data-ttu-id="de5d4-114">`Show-ControlPanelItem` システムで開くことができるコントロールパネル項目だけを検索します。</span><span class="sxs-lookup"><span data-stu-id="de5d4-114">`Show-ControlPanelItem` searches only control panel items that can be opened on the system.</span></span> <span data-ttu-id="de5d4-115">**コントロールパネル** または **エクスプローラー** がインストールされていないコンピューターでは、は、 `Show-ControlPanelItem` これらのコンポーネントなしで開くことができるコントロールパネル項目だけを検索します。</span><span class="sxs-lookup"><span data-stu-id="de5d4-115">On computers that do not have **Control Panel** or **File Explorer** , `Show-ControlPanelItem` searches only control panel items that can open without these components.</span></span>

<span data-ttu-id="de5d4-116">このコマンドレットは、windows PowerShell 3.0 で導入され、Windows 8、Windows Server 2012、およびそれ以降のバージョンで動作します。</span><span class="sxs-lookup"><span data-stu-id="de5d4-116">This cmdlet was introduced in Windows PowerShell 3.0 and works on Windows 8, Windows Server 2012, and higher versions.</span></span>

## <span data-ttu-id="de5d4-117">例</span><span class="sxs-lookup"><span data-stu-id="de5d4-117">EXAMPLES</span></span>

### <span data-ttu-id="de5d4-118">例 1: コントロールパネル項目を表示する</span><span class="sxs-lookup"><span data-stu-id="de5d4-118">Example 1: Show a control panel item</span></span>

<span data-ttu-id="de5d4-119">この例では、[ **自動再生** ] コントロールパネル項目を起動します。</span><span class="sxs-lookup"><span data-stu-id="de5d4-119">This example launches the **AutoPlay** control panel item.</span></span>

```powershell
Show-ControlPanelItem -Name "AutoPlay"
```

### <span data-ttu-id="de5d4-120">例 2: パイプを使用してコントロールパネル項目をこのコマンドレットにする</span><span class="sxs-lookup"><span data-stu-id="de5d4-120">Example 2: Pipe a control panel item to this cmdlet</span></span>

<span data-ttu-id="de5d4-121">この例では、ローカルコンピューターの [ **Windows Defender ファイアウォール** ] コントロールパネル項目を開きます。</span><span class="sxs-lookup"><span data-stu-id="de5d4-121">This example opens the **Windows Defender Firewall** control panel item on the local computer.</span></span>
<span data-ttu-id="de5d4-122">Windows ファイアウォールのコントロールパネル項目の名前が、Windows のバージョンによって変更されました。</span><span class="sxs-lookup"><span data-stu-id="de5d4-122">The name of the Windows Firewall control panel item has changed over the versions of Windows.</span></span> <span data-ttu-id="de5d4-123">この例では、ワイルドカードパターンを使用して、コントロールパネル項目を検索します。</span><span class="sxs-lookup"><span data-stu-id="de5d4-123">This example uses a wildcard pattern to find the control panel item.</span></span>

```powershell
Get-ControlPanelItem -Name "*Firewall" | Show-ControlPanelItem
```

<span data-ttu-id="de5d4-124">`Get-ControlPanelItem` コントロールパネル項目を取得し、 `Show-ControlPanelItem` コマンドレットでそれを開きます。</span><span class="sxs-lookup"><span data-stu-id="de5d4-124">`Get-ControlPanelItem` gets the control panel item and the `Show-ControlPanelItem` cmdlet opens it.</span></span>

### <span data-ttu-id="de5d4-125">例 3: ファイル名を使用してコントロール パネル項目を開く</span><span class="sxs-lookup"><span data-stu-id="de5d4-125">Example 3: Use a file name to open a control panel item</span></span>

<span data-ttu-id="de5d4-126">この例では、[ **プログラムと機能** ] コントロールパネル項目をアプリケーション名を使用して開きます。</span><span class="sxs-lookup"><span data-stu-id="de5d4-126">This example opens the **Programs and Features** control panel item by using its application name.</span></span>

```powershell
appwiz.cpl
```

<span data-ttu-id="de5d4-127">このメソッドは、コマンドを使用する代わりに使用し `Show-ControlPanelItem` ます。</span><span class="sxs-lookup"><span data-stu-id="de5d4-127">This method is an alternative to using a `Show-ControlPanelItem` command.</span></span>

> [!NOTE]
> <span data-ttu-id="de5d4-128">PowerShell では、コントロールパネルファイルの .cpl ファイル拡張子を省略できます。これは、環境変数の値に含まれているためです `$env:PathExt` 。</span><span class="sxs-lookup"><span data-stu-id="de5d4-128">In PowerShell, you can omit the .cpl file extension for control panel files because it's included in the value of the `$env:PathExt` environment variable.</span></span>

## <span data-ttu-id="de5d4-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="de5d4-129">PARAMETERS</span></span>

### <span data-ttu-id="de5d4-130">-CanonicalName</span><span class="sxs-lookup"><span data-stu-id="de5d4-130">-CanonicalName</span></span>

<span data-ttu-id="de5d4-131">指定された正規名または名前パターンを使用して、コントロールパネル項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="de5d4-131">Specifies control panel items by using the specified canonical names or name patterns.</span></span> <span data-ttu-id="de5d4-132">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="de5d4-132">Wildcard characters are permitted.</span></span> <span data-ttu-id="de5d4-133">複数の名前を入力すると、このコマンドレットは、名前リストの項目が **or** 演算子で区切られた場合と同様に、任意の名前に一致するコントロールパネル項目を開きます。</span><span class="sxs-lookup"><span data-stu-id="de5d4-133">If you enter multiple names, this cmdlet opens control panel items that match any of the names, as if the items in the name list were separated by an **OR** operator.</span></span>

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

### <span data-ttu-id="de5d4-134">-InputObject</span><span class="sxs-lookup"><span data-stu-id="de5d4-134">-InputObject</span></span>

<span data-ttu-id="de5d4-135">コントロールパネル項目オブジェクトを送信することによって開くコントロールパネル項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="de5d4-135">Specifies control panel items to open by submitting control panel item objects.</span></span> <span data-ttu-id="de5d4-136">コントロールパネル項目オブジェクトが格納されている変数を入力するか、などのコントロールパネル項目オブジェクトを取得するコマンドまたは式を入力し `Get-ControlPanelItem` ます。</span><span class="sxs-lookup"><span data-stu-id="de5d4-136">Enter a variable that contains control panel item objects, or type a command or expression that gets control panel item objects, such as `Get-ControlPanelItem`.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ControlPanelItem[]
Parameter Sets: ControlPanelItem
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="de5d4-137">-Name</span><span class="sxs-lookup"><span data-stu-id="de5d4-137">-Name</span></span>

<span data-ttu-id="de5d4-138">コントロールパネル項目の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="de5d4-138">Specifies names of control panel items.</span></span> <span data-ttu-id="de5d4-139">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="de5d4-139">Wildcard characters are permitted.</span></span> <span data-ttu-id="de5d4-140">複数の名前を入力すると、このコマンドレットは、名前リストの項目が **or** 演算子で区切られた場合と同様に、任意の名前に一致するコントロールパネル項目を開きます。</span><span class="sxs-lookup"><span data-stu-id="de5d4-140">If you enter multiple names, this cmdlet opens control panel items that match any of the names, as if the items in the name list were separated by an **OR** operator.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RegularName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="de5d4-141">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="de5d4-141">CommonParameters</span></span>

<span data-ttu-id="de5d4-142">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="de5d4-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="de5d4-143">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de5d4-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="de5d4-144">入力</span><span class="sxs-lookup"><span data-stu-id="de5d4-144">INPUTS</span></span>

### <span data-ttu-id="de5d4-145">System.string、Microsoft. PowerShell. Controloffice</span><span class="sxs-lookup"><span data-stu-id="de5d4-145">System.String, Microsoft.PowerShell.Commands.ControlPanelItem</span></span>

<span data-ttu-id="de5d4-146">パイプを使用して、名前またはコントロールパネルの項目オブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="de5d4-146">You can pipe a name or control panel item object to this cmdlet.</span></span>

## <span data-ttu-id="de5d4-147">出力</span><span class="sxs-lookup"><span data-stu-id="de5d4-147">OUTPUTS</span></span>

### <span data-ttu-id="de5d4-148">なし</span><span class="sxs-lookup"><span data-stu-id="de5d4-148">None</span></span>

<span data-ttu-id="de5d4-149">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="de5d4-149">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="de5d4-150">注</span><span class="sxs-lookup"><span data-stu-id="de5d4-150">NOTES</span></span>

## <span data-ttu-id="de5d4-151">関連リンク</span><span class="sxs-lookup"><span data-stu-id="de5d4-151">RELATED LINKS</span></span>

[<span data-ttu-id="de5d4-152">Get-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="de5d4-152">Get-ControlPanelItem</span></span>](Get-ControlPanelItem.md)
