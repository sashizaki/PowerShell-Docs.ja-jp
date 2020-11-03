---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/remove-typedata?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-TypeData
ms.openlocfilehash: 23a5241aa2f4b18fc02c3ea1c1a5bb8fb467b430
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216288"
---
# <span data-ttu-id="c2329-103">Remove-TypeData</span><span class="sxs-lookup"><span data-stu-id="c2329-103">Remove-TypeData</span></span>

## <span data-ttu-id="c2329-104">構文</span><span class="sxs-lookup"><span data-stu-id="c2329-104">Synopsis</span></span>
<span data-ttu-id="c2329-105">現在のセッションから拡張型を削除します。</span><span class="sxs-lookup"><span data-stu-id="c2329-105">Deletes extended types from the current session.</span></span>

## <span data-ttu-id="c2329-106">構文</span><span class="sxs-lookup"><span data-stu-id="c2329-106">Syntax</span></span>

### <span data-ttu-id="c2329-107">RemoveTypeDataSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="c2329-107">RemoveTypeDataSet (Default)</span></span>

```
Remove-TypeData -TypeData <TypeData> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c2329-108">RemoveTypeSet</span><span class="sxs-lookup"><span data-stu-id="c2329-108">RemoveTypeSet</span></span>

```
Remove-TypeData [-TypeName] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c2329-109">RemoveFileSet 場合</span><span class="sxs-lookup"><span data-stu-id="c2329-109">RemoveFileSet</span></span>

```
Remove-TypeData -Path <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c2329-110">Description</span><span class="sxs-lookup"><span data-stu-id="c2329-110">DESCRIPTION</span></span>

<span data-ttu-id="c2329-111">コマンドレットでは、 `Remove-TypeData` 現在のセッションから拡張型データを削除します。</span><span class="sxs-lookup"><span data-stu-id="c2329-111">The `Remove-TypeData` cmdlet deletes extended type data from the current session.</span></span> <span data-ttu-id="c2329-112">このコマンドレットは、現在のセッションと、現在のセッションで作成されたセッションにのみ作用します。</span><span class="sxs-lookup"><span data-stu-id="c2329-112">This cmdlet affects only the current session and sessions that are created in the current session.</span></span>

<span data-ttu-id="c2329-113">コマンドとファイルを定義することで、PowerShell でオブジェクトにプロパティとメソッドを追加でき `Update-TypeData` `Types.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="c2329-113">You can add properties and methods to objects in PowerShell by defining them in `Update-TypeData` commands and `Types.ps1xml` files.</span></span> <span data-ttu-id="c2329-114">`Remove-TypeData` これらの拡張プロパティとメソッドを現在のセッションから削除します。</span><span class="sxs-lookup"><span data-stu-id="c2329-114">`Remove-TypeData` deletes those extended properties and methods from the current session.</span></span> <span data-ttu-id="c2329-115">`Remove-TypeData` ファイルを削除し `Types.ps1xml` たり、ファイルから拡張型定義を削除したりすることはありません `Types.ps1xml` 。</span><span class="sxs-lookup"><span data-stu-id="c2329-115">`Remove-TypeData` does not delete the `Types.ps1xml` files or delete any extended type definitions from the `Types.ps1xml` files.</span></span> <span data-ttu-id="c2329-116">ファイルの詳細について `Types.ps1xml` は、「 [about_Types.ps1xml](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2329-116">For more information about `Types.ps1xml` files, see [about_Types.ps1xml](../Microsoft.PowerShell.Core/about/about_Types.ps1xml.md).</span></span>

<span data-ttu-id="c2329-117">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="c2329-117">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="c2329-118">例</span><span class="sxs-lookup"><span data-stu-id="c2329-118">Examples</span></span>

### <span data-ttu-id="c2329-119">例 1: 指定された型の型データを削除する</span><span class="sxs-lookup"><span data-stu-id="c2329-119">Example 1: Remove type data for a specified type</span></span>

<span data-ttu-id="c2329-120">この例では、ファイルによっ **System.Array** て追加された型データ `Types.ps1xml` と、コマンドレットを使用してセッションに追加された動的な型データを含む、配列型のすべての型データをセッションから削除します。 `Update-TypeData`</span><span class="sxs-lookup"><span data-stu-id="c2329-120">This example deletes all type data for the **System.Array** type  from the session, including type data that was added by a `Types.ps1xml` file and dynamic type data that was added to the session by using the `Update-TypeData` cmdlet.</span></span>

```powershell
Remove-TypeData -TypeName System.Array
```

### <span data-ttu-id="c2329-121">例 2: セッションから拡張データ型を削除する</span><span class="sxs-lookup"><span data-stu-id="c2329-121">Example 2: Remove an extended data type from a session</span></span>

<span data-ttu-id="c2329-122">この例は、セッションから拡張型データを削除した場合の効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="c2329-122">This example shows the effect of removing extended type data from a session.</span></span> <span data-ttu-id="c2329-123">最初のは、system.string `Get-TypeData` 型の拡張 **System.DateTime** 型データを取得します。</span><span class="sxs-lookup"><span data-stu-id="c2329-123">The first `Get-TypeData` gets extended type data for the **System.DateTime** type.</span></span> <span data-ttu-id="c2329-124">出力には、PowerShell のすべての system.string オブジェクトに **datetime** プロパティが追加されていることが示されて **います。**</span><span class="sxs-lookup"><span data-stu-id="c2329-124">The output shows that a **DateTime** property has been added to all **System.DateTime** objects in PowerShell.</span></span> <span data-ttu-id="c2329-125">この `Get-Date` コマンドレットは **、system.string** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c2329-125">The `Get-Date` cmdlet returns a **System.DateTime** object.</span></span> <span data-ttu-id="c2329-126">このコマンドは、ドット表記を使用して、を返す **system.string オブジェクトの** **datetime** プロパティの値を取得し `Get-Date` ます。</span><span class="sxs-lookup"><span data-stu-id="c2329-126">The command uses dot notation to get the value of the **DateTime** property of the **System.DateTime** object that `Get-Date` returns.</span></span>

```powershell
Get-TypeData System.DateTime
(Get-Date).DateTime
Get-TypeData System.DateTime | Remove-TypeData
(Get-Date).DateTime
```

```Output
TypeName        Members
--------        -------
System.DateTime {[DateTime, System.Management.Automation.Runspaces.ScriptPropertyData]}

Friday, January 20, 2012 9:01:00 PM
```

<span data-ttu-id="c2329-127">次の `Get-TypeData` コマンドレットは、system.string 型のすべての **System.DateTime** 拡張型データを取得し、コマンドレットにパイプを使用して `Remove-TypeData` 拡張型データを削除します。</span><span class="sxs-lookup"><span data-stu-id="c2329-127">The next `Get-TypeData` cmdlet to get all extended type data for the **System.DateTime** type and pipes that to the `Remove-TypeData` cmdlet to delete the extended type data.</span></span> <span data-ttu-id="c2329-128">最後の `Get-Date` コマンドレットは、 **DateTime** 型の拡張型データを削除した場合の影響を示しています。</span><span class="sxs-lookup"><span data-stu-id="c2329-128">The last `Get-Date` cmdlet shows the effect of deleting the extended type data for the **System.DateTime** type.</span></span> <span data-ttu-id="c2329-129">System.string プロパティ **は存在しなく** なったため、その値を取得するコマンドは nothing を返します。</span><span class="sxs-lookup"><span data-stu-id="c2329-129">Because the **System.DateTime** property no longer exists, a command to get its value returns nothing.</span></span>

### <span data-ttu-id="c2329-130">例 3: モジュールの拡張型を削除する</span><span class="sxs-lookup"><span data-stu-id="c2329-130">Example 3: Remove extended types for modules</span></span>

<span data-ttu-id="c2329-131">この例では、モジュールオブジェクトのすべての拡張型データを削除します。</span><span class="sxs-lookup"><span data-stu-id="c2329-131">This example removes all extended type data for module objects.</span></span> <span data-ttu-id="c2329-132">パイプを使用してオブジェクトをにパイプすると `Remove-TypeData` 、は `Remove-TypeData` オブジェクトの種類の名前を取得し、その型のすべてのオブジェクトのすべての型データを削除します。</span><span class="sxs-lookup"><span data-stu-id="c2329-132">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the name of the object type and removes all type data for all objects of that type.</span></span>

```powershell
Get-Module | Remove-TypeData
```

### <span data-ttu-id="c2329-133">例 4: 指定したモジュールから拡張型を削除する</span><span class="sxs-lookup"><span data-stu-id="c2329-133">Example 4: Remove extended types from specified modules</span></span>

<span data-ttu-id="c2329-134">この例では、コマンドレットの **Path** パラメーターを使用して、 `Remove-TypeData` `Types.ps1xml` **Psscheduledjob** モジュールおよび **psworkflow** モジュールによって追加されたファイルで定義されている拡張型を削除します。</span><span class="sxs-lookup"><span data-stu-id="c2329-134">This example uses the **Path** parameter of the `Remove-TypeData` cmdlet to remove the extended types that are defined in the `Types.ps1xml` files that are added by the **PSScheduledJob** and **PSWorkflow** modules.</span></span> <span data-ttu-id="c2329-135">このコマンドは、コマンドレットを使用して追加された動的な型データには影響しません `Update-TypeData` 。</span><span class="sxs-lookup"><span data-stu-id="c2329-135">This command does not affect dynamic type data that is added by using the `Update-TypeData` cmdlet.</span></span> <span data-ttu-id="c2329-136">このコマンドは、モジュールが現在のセッションにインポートされている場合にのみ成功します。</span><span class="sxs-lookup"><span data-stu-id="c2329-136">The command succeeds only when the modules have been imported into the current session.</span></span>

```powershell
Remove-TypeData -Path "$PSHOME\Modules\PSScheduledJob", "$PSHOME\Modules\PSWorkflow\PSWorkflow.types.ps1xml"
```

<span data-ttu-id="c2329-137">モジュールの詳細については、「 [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2329-137">For more information about modules, see [about_Modules](../Microsoft.PowerShell.Core/About/about_Modules.md).</span></span>

### <span data-ttu-id="c2329-138">例 5: リモートセッションから拡張型を削除する</span><span class="sxs-lookup"><span data-stu-id="c2329-138">Example 5: Remove extended types from a remote session</span></span>

<span data-ttu-id="c2329-139">この例では、リモートセッションから拡張型を削除します。</span><span class="sxs-lookup"><span data-stu-id="c2329-139">This example removes extended types from a remote session.</span></span> <span data-ttu-id="c2329-140">このコマンドは、コマンドレットを使用して、 `Invoke-Command` 変数内のセッションのすべての CIM 型の拡張型データを削除し `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="c2329-140">The command uses the `Invoke-Command` cmdlet to remove extended type data for all CIM types in the sessions in the `$S` variable.</span></span>

```powershell
Invoke-Command -Session $S {Get-TypeData -TypeName *CIM* | Remove-TypeData}
```

## <span data-ttu-id="c2329-141">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c2329-141">Parameters</span></span>

### <span data-ttu-id="c2329-142">-Path</span><span class="sxs-lookup"><span data-stu-id="c2329-142">-Path</span></span>

<span data-ttu-id="c2329-143">このコマンドレットがセッション拡張型データから削除するファイルの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="c2329-143">Specifies an array of files that this cmdlet deletes from the session extended type data.</span></span> <span data-ttu-id="c2329-144">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="c2329-144">This parameter is required.</span></span>

<span data-ttu-id="c2329-145">1つ以上のファイルのパスとファイル名を入力し `Types.ps1xml` ます。</span><span class="sxs-lookup"><span data-stu-id="c2329-145">Enter the paths and file names of one or more `Types.ps1xml` files.</span></span> <span data-ttu-id="c2329-146">ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c2329-146">Wildcards are not supported.</span></span> <span data-ttu-id="c2329-147">パスを省略した場合、現在のディレクトリが既定の場所になります。</span><span class="sxs-lookup"><span data-stu-id="c2329-147">If you omit the path, the default location is the current directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: RemoveFileSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2329-148">-TypeData</span><span class="sxs-lookup"><span data-stu-id="c2329-148">-TypeData</span></span>

<span data-ttu-id="c2329-149">このコマンドレットがセッションから削除する型データを指定します。</span><span class="sxs-lookup"><span data-stu-id="c2329-149">Specifies the type data that this cmdlet deletes from the session.</span></span> <span data-ttu-id="c2329-150">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="c2329-150">This parameter is required.</span></span> <span data-ttu-id="c2329-151">**Typedata** オブジェクト (System.string **. typedata** ) を含む変数、またはコマンドなどの **typedata** オブジェクトを取得するコマンドを入力します `Get-TypeData` 。</span><span class="sxs-lookup"><span data-stu-id="c2329-151">Enter a variable that contains **TypeData** objects ( **System.Management.Automation.Runspaces.TypeData** ) or a command that gets **TypeData** objects, such as a `Get-TypeData` command.</span></span> <span data-ttu-id="c2329-152">パイプを使用して **Typedata** オブジェクトをにパイプすることもでき `Remove-TypeData` ます。</span><span class="sxs-lookup"><span data-stu-id="c2329-152">You can also pipe **TypeData** objects to `Remove-TypeData`.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.TypeData
Parameter Sets: RemoveTypeDataSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c2329-153">-TypeName</span><span class="sxs-lookup"><span data-stu-id="c2329-153">-TypeName</span></span>

<span data-ttu-id="c2329-154">このコマンドレットがすべての拡張型データを削除する型を指定します。</span><span class="sxs-lookup"><span data-stu-id="c2329-154">Specifies the types that this cmdlet deletes all extended type data for.</span></span> <span data-ttu-id="c2329-155">System 名前空間の型に対しては、短い名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="c2329-155">For types in the System namespace, enter the short name.</span></span> <span data-ttu-id="c2329-156">それ以外の場合は、完全な型名が必要です。</span><span class="sxs-lookup"><span data-stu-id="c2329-156">Otherwise, the full type name is required.</span></span> <span data-ttu-id="c2329-157">ワイルドカードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c2329-157">Wildcards are not supported.</span></span>

<span data-ttu-id="c2329-158">パイプを使用して型名をにすることができ `Remove-TypeData` ます。</span><span class="sxs-lookup"><span data-stu-id="c2329-158">You can pipe type names to `Remove-TypeData`.</span></span> <span data-ttu-id="c2329-159">パイプを使用してオブジェクトをにパイプすると `Remove-TypeData` 、は `Remove-TypeData` オブジェクトの型名を取得し、そのオブジェクト型のすべての型データを削除します。</span><span class="sxs-lookup"><span data-stu-id="c2329-159">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the type name of the object and removes all type data for the object type.</span></span>

```yaml
Type: System.String
Parameter Sets: RemoveTypeSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c2329-160">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c2329-160">-Confirm</span></span>

<span data-ttu-id="c2329-161">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c2329-161">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2329-162">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c2329-162">-WhatIf</span></span>

<span data-ttu-id="c2329-163">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="c2329-163">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="c2329-164">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c2329-164">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c2329-165">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c2329-165">CommonParameters</span></span>

<span data-ttu-id="c2329-166">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="c2329-166">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c2329-167">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2329-167">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c2329-168">入力</span><span class="sxs-lookup"><span data-stu-id="c2329-168">Inputs</span></span>

### <span data-ttu-id="c2329-169">システムの管理.... TypeData</span><span class="sxs-lookup"><span data-stu-id="c2329-169">System.Management.Automation.Runspaces.TypeData</span></span>

<span data-ttu-id="c2329-170">パイプを使用して、コマンドレットが返すような **Typedata** オブジェクトをにすることができ `Get-TypeData` `Remove-TypeData` ます。</span><span class="sxs-lookup"><span data-stu-id="c2329-170">You can pipe **TypeData** object, such as the ones that the `Get-TypeData` cmdlet returns, to `Remove-TypeData`.</span></span>

### <span data-ttu-id="c2329-171">System.String</span><span class="sxs-lookup"><span data-stu-id="c2329-171">System.String</span></span>

<span data-ttu-id="c2329-172">型名をにパイプすることができ `Remove-TypeData` ます。</span><span class="sxs-lookup"><span data-stu-id="c2329-172">You can pipe the type names to `Remove-TypeData`.</span></span> <span data-ttu-id="c2329-173">パイプを使用してオブジェクトをにパイプすると `Remove-TypeData` 、は `Remove-TypeData` オブジェクトの型名を取得し、そのオブジェクト型のすべての型データを削除します。</span><span class="sxs-lookup"><span data-stu-id="c2329-173">When you pipe an object to `Remove-TypeData`, `Remove-TypeData` gets the type name of the object and removes all type data for the object type.</span></span>

## <span data-ttu-id="c2329-174">出力</span><span class="sxs-lookup"><span data-stu-id="c2329-174">Outputs</span></span>

### <span data-ttu-id="c2329-175">なし</span><span class="sxs-lookup"><span data-stu-id="c2329-175">None</span></span>

<span data-ttu-id="c2329-176">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="c2329-176">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c2329-177">メモ</span><span class="sxs-lookup"><span data-stu-id="c2329-177">Notes</span></span>

<span data-ttu-id="c2329-178">`Remove-TypeData` では、現在のセッションの拡張型データのみを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c2329-178">`Remove-TypeData` can remove only the extended type data in the current session.</span></span> <span data-ttu-id="c2329-179">このコマンドレットは、モジュールに定義されている一方で現在のセッションにインポートされていない拡張型のように、コンピューター上に存在していて現在のセッションに追加されていない拡張型データは削除できません。</span><span class="sxs-lookup"><span data-stu-id="c2329-179">It cannot remove extended type data that is on the computer, but has not been added to the current session, such as extended types that are defined in modules that have not been imported into the current session.</span></span>

## <span data-ttu-id="c2329-180">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c2329-180">Related links</span></span>

[<span data-ttu-id="c2329-181">Get-TypeData</span><span class="sxs-lookup"><span data-stu-id="c2329-181">Get-TypeData</span></span>](Get-TypeData.md)

[<span data-ttu-id="c2329-182">Update-TypeData</span><span class="sxs-lookup"><span data-stu-id="c2329-182">Update-TypeData</span></span>](Update-TypeData.md)
