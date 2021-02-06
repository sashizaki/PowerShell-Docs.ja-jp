---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-typedata?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TypeData
ms.openlocfilehash: db5dc586f2a165d83c25bdf2addaeb625f9e1ba0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601195"
---
# <span data-ttu-id="22577-102">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="22577-102">Get-TypeData</span></span>

## <span data-ttu-id="22577-103">構文</span><span class="sxs-lookup"><span data-stu-id="22577-103">Synopsis</span></span>
<span data-ttu-id="22577-104">現在のセッションで、拡張型データを取得します。</span><span class="sxs-lookup"><span data-stu-id="22577-104">Gets the extended type data in the current session.</span></span>

## <span data-ttu-id="22577-105">構文</span><span class="sxs-lookup"><span data-stu-id="22577-105">Syntax</span></span>

```
Get-TypeData [[-TypeName] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="22577-106">説明</span><span class="sxs-lookup"><span data-stu-id="22577-106">Description</span></span>

<span data-ttu-id="22577-107">`Get-TypeData`コマンドレットは、現在のセッションの拡張型データを取得します。</span><span class="sxs-lookup"><span data-stu-id="22577-107">The `Get-TypeData` cmdlet gets the extended type data in the current session.</span></span> <span data-ttu-id="22577-108">これには、ファイルによってセッションに追加された型データ `Types.ps1xml` と、コマンドレットのパラメーターを使用して追加された動的な型データが含まれ `Update-TypeData` ます。</span><span class="sxs-lookup"><span data-stu-id="22577-108">This includes type data that was added to the session by `Types.ps1xml` file and dynamic type data that was added by using the parameter of the `Update-TypeData` cmdlet.</span></span>

<span data-ttu-id="22577-109">が返す拡張型データを使用すると、 `Get-TypeData` セッションの型データを調べて、 `Update-TypeData` `Remove-TypeData` コマンドレットおよびコマンドレットに送信できます。</span><span class="sxs-lookup"><span data-stu-id="22577-109">You can use the extended type data that `Get-TypeData` returns to examine the type data in the session and send it to the `Update-TypeData` and `Remove-TypeData` cmdlets.</span></span>

<span data-ttu-id="22577-110">拡張型データは、PowerShell のオブジェクトにプロパティとメソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="22577-110">Extended type data adds properties and methods to objects in PowerShell.</span></span> <span data-ttu-id="22577-111">その追加されたプロパティとメソッドを、オブジェクトの型によって決定されるプロパティとメソッドを使用するのと同じ方法で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="22577-111">You can use the added properties and methods in the same ways that you would use the properties and methods that are defined in the object type.</span></span> <span data-ttu-id="22577-112">ただし、スクリプトを記述するときは、追加されたプロパティとメソッドがすべての PowerShell セッションに存在しない可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="22577-112">However, when writing scripts, be aware that the added properties and methods might not be present in every PowerShell session.</span></span>

<span data-ttu-id="22577-113">ファイルの詳細について `Types.ps1xml` は、「 [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22577-113">For more information about `Types.ps1xml` files, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md).</span></span> <span data-ttu-id="22577-114">コマンドレットによって追加される動的な型データの詳細については `Update-TypeData` 、「」を参照してください `Update-TypeData` 。</span><span class="sxs-lookup"><span data-stu-id="22577-114">For more information about dynamic type data that the `Update-TypeData` cmdlet adds, see `Update-TypeData`.</span></span>

<span data-ttu-id="22577-115">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="22577-115">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="22577-116">例</span><span class="sxs-lookup"><span data-stu-id="22577-116">Examples</span></span>

### <span data-ttu-id="22577-117">例 1: すべての拡張型データを取得する</span><span class="sxs-lookup"><span data-stu-id="22577-117">Example 1: Get all extended type data</span></span>

<span data-ttu-id="22577-118">この例では、現在のセッションのすべての拡張型データを取得します。</span><span class="sxs-lookup"><span data-stu-id="22577-118">This example gets all extended type data in the current session.</span></span>

 ```powershell
Get-TypeData
```

### <span data-ttu-id="22577-119">例 2: 名前を指定して型を取得する</span><span class="sxs-lookup"><span data-stu-id="22577-119">Example 2: Get types by name</span></span>

<span data-ttu-id="22577-120">この例では、イベントを含む名前を持つ、現在のセッションのすべての型を取得します。</span><span class="sxs-lookup"><span data-stu-id="22577-120">This example gets all types in the current session that have names that contain Eventing.</span></span>

 ```powershell
"*Eventing*" | Get-TypeData
```

```Output
TypeName                                                  Members
--------                                                  -------
System.Diagnostics.Eventing.Reader.EventLogConfiguration  {}System.Diagnostics.Eventing.Reader.EventLogRecord
                                                          {}System.Diagnostics.Eventing.Reader.ProviderMetadata
                                                          {[ProviderName, System.Management.Automation.Runspaces.AliasProper...
```

### <span data-ttu-id="22577-121">例 3: プロパティ値を作成するスクリプトブロックを取得する</span><span class="sxs-lookup"><span data-stu-id="22577-121">Example 3: Get the script block that creates a property value</span></span>

<span data-ttu-id="22577-122">この例では、 **EventLogEntry** オブジェクトの **EventID** プロパティの値を作成するスクリプトブロックを取得します。</span><span class="sxs-lookup"><span data-stu-id="22577-122">This example gets the script block that creates the value of the **EventID** property of **EventLogEntry** objects.</span></span>

 ```powershell
(Get-TypeData *EventLogEntry*).Members.EventID
```

```Output
GetScriptBlock                     SetScriptBlock     IsHidden Name
--------------                     --------------     -------- ----
$this.get_EventID() -band 0xFFFF                         False EventID
```

### <span data-ttu-id="22577-123">例 4: 指定したオブジェクトのプロパティを定義するスクリプトブロックを取得する</span><span class="sxs-lookup"><span data-stu-id="22577-123">Example 4: Get the script block that defines a property for a specified object</span></span>

<span data-ttu-id="22577-124">この例では、PowerShell の **system.string オブジェクトの** **datetime** プロパティを定義するスクリプトブロックを取得します。</span><span class="sxs-lookup"><span data-stu-id="22577-124">This example gets the script block that defines the **DateTime** property of **System.DateTime** objects in PowerShell.</span></span>

 ```powershell
(Get-TypeData -TypeName System.DateTime).Members["DateTime"].GetScriptBlock
if ((& { Set-StrictMode -Version 1; $this.DisplayHint }) -ieq  "Date") {
    "{0}" -f $this.ToLongDateString()
}
elseif ((& { Set-StrictMode -Version 1; $this.DisplayHint }) -ieq "Time") {
    "{0}" -f  $this.ToLongTimeString()
}
else {
    "{0} {1}" -f $this.ToLongDateString(), $this.ToLongTimeString()
}
```

<span data-ttu-id="22577-125">このコマンドは、コマンドレットを使用して、 `Get-TypeData` **DataTime** 型の拡張型データを取得します。</span><span class="sxs-lookup"><span data-stu-id="22577-125">The command uses the `Get-TypeData` cmdlet to get the extended type data for the **System.DataTime** type.</span></span> <span data-ttu-id="22577-126">コマンドは、**TypeData** オブジェクトの **Members** プロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="22577-126">The command gets the **Members** property of the **TypeData** object.</span></span>

<span data-ttu-id="22577-127">**Members** プロパティには、拡張型データで定義されているプロパティとメソッドのハッシュテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="22577-127">The **Members** property contains a hash table of properties and methods that are defined by extended type data.</span></span> <span data-ttu-id="22577-128">Members ハッシュ テーブルの各キーは、プロパティ名またはメソッド名であり、各値は、プロパティ値またはメソッド値の定義です。</span><span class="sxs-lookup"><span data-stu-id="22577-128">Each key in the Members hash table is a property or method name and each value is the definition of the property or method value.</span></span>

<span data-ttu-id="22577-129">このコマンドは、**メンバー** の **DateTime** キーと **getscriptblock** プロパティ値を取得します。</span><span class="sxs-lookup"><span data-stu-id="22577-129">The command gets the **DateTime** key in **Members** and its **GetScriptBlock** property value.</span></span>

<span data-ttu-id="22577-130">出力には、PowerShell のすべての system.string オブジェクトの **datetime** プロパティの値を作成するスクリプトブロックが示されて **います。**</span><span class="sxs-lookup"><span data-stu-id="22577-130">The output shows the script block that creates the value of the **DateTime** property of every **System.DateTime** object in PowerShell.</span></span>

## <span data-ttu-id="22577-131">パラメーター</span><span class="sxs-lookup"><span data-stu-id="22577-131">Parameters</span></span>

### <span data-ttu-id="22577-132">-TypeName</span><span class="sxs-lookup"><span data-stu-id="22577-132">-TypeName</span></span>

<span data-ttu-id="22577-133">指定された名前を持つ型に対してのみ、型データを配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="22577-133">Specifies type data as an array only for the types with the specified names.</span></span> <span data-ttu-id="22577-134">既定では、は、 `Get-TypeData` セッション内のすべての型を取得します。</span><span class="sxs-lookup"><span data-stu-id="22577-134">By default, `Get-TypeData` gets all types in the session.</span></span>

<span data-ttu-id="22577-135">型の名前または名前パターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="22577-135">Enter type names or a name patterns.</span></span> <span data-ttu-id="22577-136">System 名前空間の型であっても、フルネーム、またはワイルドカード文字を使用した名前パターンが必要です。</span><span class="sxs-lookup"><span data-stu-id="22577-136">Full names, or name patterns with wildcard characters are required, even for types in the System namespace.</span></span> <span data-ttu-id="22577-137">ワイルドカードがサポートされており、パラメーター名 **TypeName** は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="22577-137">Wildcards are supported and the parameter name **TypeName** is optional.</span></span> <span data-ttu-id="22577-138">パイプを使用して型名をにパイプすることもでき `Get-TypeData` ます。</span><span class="sxs-lookup"><span data-stu-id="22577-138">You can also pipe type names to `Get-TypeData`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="22577-139">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="22577-139">CommonParameters</span></span>

<span data-ttu-id="22577-140">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="22577-140">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="22577-141">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22577-141">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="22577-142">入力</span><span class="sxs-lookup"><span data-stu-id="22577-142">Inputs</span></span>

### <span data-ttu-id="22577-143">System.String</span><span class="sxs-lookup"><span data-stu-id="22577-143">System.String</span></span>

<span data-ttu-id="22577-144">パイプを使用して型名をにすることができ `Get-TypeData` ます。</span><span class="sxs-lookup"><span data-stu-id="22577-144">You can pipe type names to `Get-TypeData`.</span></span>

## <span data-ttu-id="22577-145">出力</span><span class="sxs-lookup"><span data-stu-id="22577-145">Outputs</span></span>

### <span data-ttu-id="22577-146">システムの管理.... TypeData</span><span class="sxs-lookup"><span data-stu-id="22577-146">System.Management.Automation.Runspaces.TypeData</span></span>

## <span data-ttu-id="22577-147">メモ</span><span class="sxs-lookup"><span data-stu-id="22577-147">Notes</span></span>

<span data-ttu-id="22577-148">`Get-TypeData` 現在のセッションの拡張型データのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="22577-148">`Get-TypeData` gets only the extended type data in the current session.</span></span> <span data-ttu-id="22577-149">このコマンドレットは、モジュールに定義されている一方で現在のセッションにインポートされていない拡張型のように、コンピューター上に存在していて現在のセッションに追加されていない拡張型データは取得しません。</span><span class="sxs-lookup"><span data-stu-id="22577-149">It does not get extended type data that is on the computer, but has not been added to the current session, such as extended types that are defined in modules that have not been imported into the current session.</span></span>

## <span data-ttu-id="22577-150">関連リンク</span><span class="sxs-lookup"><span data-stu-id="22577-150">Related links</span></span>

[<span data-ttu-id="22577-151">about_Types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="22577-151">about_Types.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Types.ps1xml.md)

[<span data-ttu-id="22577-152">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="22577-152">Remove-TypeData</span></span>](Remove-TypeData.md)

[<span data-ttu-id="22577-153">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="22577-153">Update-TypeData</span></span>](Update-TypeData.md)

