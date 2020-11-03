---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-object?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Object
ms.openlocfilehash: 3246d33174f39bf52dfa68b2dbe1e7b76a320b61
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216576"
---
# <span data-ttu-id="89ca2-103">New-Object</span><span class="sxs-lookup"><span data-stu-id="89ca2-103">New-Object</span></span>

## <span data-ttu-id="89ca2-104">概要</span><span class="sxs-lookup"><span data-stu-id="89ca2-104">SYNOPSIS</span></span>
<span data-ttu-id="89ca2-105">Microsoft .NET Framework または COM オブジェクトのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-105">Creates an instance of a Microsoft .NET Framework or COM object.</span></span>

## <span data-ttu-id="89ca2-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="89ca2-106">SYNTAX</span></span>

### <span data-ttu-id="89ca2-107">Net (既定値)</span><span class="sxs-lookup"><span data-stu-id="89ca2-107">Net (Default)</span></span>

```
New-Object [-TypeName] <String> [[-ArgumentList] <Object[]>] [-Property <IDictionary>] [<CommonParameters>]
```

### <span data-ttu-id="89ca2-108">Com</span><span class="sxs-lookup"><span data-stu-id="89ca2-108">Com</span></span>

```
New-Object [-ComObject] <String> [-Strict] [-Property <IDictionary>] [<CommonParameters>]
```

## <span data-ttu-id="89ca2-109">Description</span><span class="sxs-lookup"><span data-stu-id="89ca2-109">DESCRIPTION</span></span>

<span data-ttu-id="89ca2-110">`New-Object`コマンドレットでは、.NET Framework または COM オブジェクトのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-110">The `New-Object` cmdlet creates an instance of a .NET Framework or COM object.</span></span>

<span data-ttu-id="89ca2-111">.NET Framework クラスの型または COM オブジェクトの ProgID のどちらかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="89ca2-111">You can specify either the type of a .NET Framework class or a ProgID of a COM object.</span></span> <span data-ttu-id="89ca2-112">既定では、.NET Framework クラスの完全修飾名を入力すると、そのクラスのインスタンスへの参照が返されます。</span><span class="sxs-lookup"><span data-stu-id="89ca2-112">By default, you type the fully qualified name of a .NET Framework class and the cmdlet returns a reference to an instance of that class.</span></span> <span data-ttu-id="89ca2-113">COM オブジェクトのインスタンスを作成するには、 **ComObject** パラメーターを使用して、オブジェクトの ProgID を値として指定します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-113">To create an instance of a COM object, use the **ComObject** parameter and specify the ProgID of the object as its value.</span></span>

## <span data-ttu-id="89ca2-114">例</span><span class="sxs-lookup"><span data-stu-id="89ca2-114">EXAMPLES</span></span>

### <span data-ttu-id="89ca2-115">例 1: system.object オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="89ca2-115">Example 1: Create a System.Version object</span></span>

<span data-ttu-id="89ca2-116">この例では、コンストラクターとして "1.2.3.4" 文字列を使用して **system.string オブジェクトを** 作成します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-116">This example creates a **System.Version** object using the "1.2.3.4" string as the constructor.</span></span>

```powershell
New-Object -TypeName System.Version -ArgumentList "1.2.3.4"
```

```Output
Major  Minor  Build  Revision
-----  -----  -----  --------
1      2      3      4
```

### <span data-ttu-id="89ca2-117">例 2: Internet Explorer COM オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="89ca2-117">Example 2: Create an Internet Explorer COM object</span></span>

<span data-ttu-id="89ca2-118">この例では、Internet Explorer アプリケーションを表す COM オブジェクトのインスタンスを2つ作成します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-118">This example creates two instances of the COM object that represents the Internet Explorer application.</span></span> <span data-ttu-id="89ca2-119">最初のインスタンスは、 **プロパティ** パラメーターハッシュテーブルを使用して **Navigate2** メソッドを呼び出し、オブジェクトの **visible** プロパティをに設定して、 `$True` アプリケーションが表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="89ca2-119">The first instance uses the **Property** parameter hash table to call the **Navigate2** method and set the **Visible** property of the object to `$True` to make the application visible.</span></span>
<span data-ttu-id="89ca2-120">2番目のインスタンスは、個々のコマンドで同じ結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-120">The second instance gets the same results with individual commands.</span></span>

```powershell
$IE1 = New-Object -COMObject InternetExplorer.Application -Property @{Navigate2="www.microsoft.com"; Visible = $True}

# The following command gets the same results as the example above.
$IE2 = New-Object -COMObject InternetExplorer.Application`
$IE2.Navigate2("www.microsoft.com")`
$IE2.Visible = $True`
```

### <span data-ttu-id="89ca2-121">例 3: Strict パラメーターを使用して、終了しないエラーを生成する</span><span class="sxs-lookup"><span data-stu-id="89ca2-121">Example 3: Use the Strict parameter to generate a non-terminating error</span></span>

<span data-ttu-id="89ca2-122">この例では、 **厳密** なパラメーターを追加すると、 `New-Object` COM オブジェクトが相互運用機能アセンブリを使用しているときに、コマンドレットが終了しないエラーを生成することを示しています。</span><span class="sxs-lookup"><span data-stu-id="89ca2-122">This example demonstrates that adding the **Strict** parameter causes the `New-Object` cmdlet to generate a non-terminating error when the COM object uses an interop assembly.</span></span>

```powershell
$A = New-Object -COMObject Word.Application -Strict -Property @{Visible = $True}
```

```Output
New-Object : The object written to the pipeline is an instance of the type
"Microsoft.Office.Interop.Word.ApplicationClass" from the component's primary interop assembly. If
this type exposes different members than the IDispatch members, scripts written to work with this
object might not work if the primary interop assembly is not installed.

At line:1 char:14
+ $A = New-Object  <<<< -COM Word.Application -Strict; $a.visible=$true
```

### <span data-ttu-id="89ca2-123">例 4: Windows デスクトップを管理するための COM オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="89ca2-123">Example 4: Create a COM object to manage Windows desktop</span></span>

<span data-ttu-id="89ca2-124">この例では、COM オブジェクトを作成および使用して Windows デスクトップを管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-124">This example shows how to create and use a COM object to manage your Windows desktop.</span></span>

<span data-ttu-id="89ca2-125">最初のコマンドは、コマンドレットの **ComObject** パラメーターを使用して、 `New-Object` **アプリケーション** PROGID を使用して COM オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-125">The first command uses the **ComObject** parameter of the `New-Object` cmdlet to create a COM object with the **Shell.Application** ProgID.</span></span> <span data-ttu-id="89ca2-126">結果として得られるオブジェクトは変数に格納され `$ObjShell` ます。</span><span class="sxs-lookup"><span data-stu-id="89ca2-126">It stores the resulting object in the `$ObjShell` variable.</span></span> <span data-ttu-id="89ca2-127">2番目のコマンドは、変数をコマンドレットにパイプして、 `$ObjShell` `Get-Member` COM オブジェクトのプロパティとメソッドを表示します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-127">The second command pipes the `$ObjShell` variable to the `Get-Member` cmdlet, which displays the properties and methods of the COM object.</span></span> <span data-ttu-id="89ca2-128">これらのメソッドの中には、 **ToggleDesktop** メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="89ca2-128">Among the methods is the **ToggleDesktop** method.</span></span> <span data-ttu-id="89ca2-129">3 番目のコマンドは、オブジェクトの **ToggleDesktop** メソッドを呼び出して、デスクトップ上の開いているウィンドウを最小化します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-129">The third command calls the **ToggleDesktop** method of the object to minimize the open windows on your desktop.</span></span>

```powershell
$Objshell = New-Object -COMObject "Shell.Application"
$objshell | Get-Member
$objshell.ToggleDesktop()
```

```Output
   TypeName: System.__ComObject#{866738b9-6cf2-4de8-8767-f794ebe74f4e}

Name                 MemberType Definition
----                 ---------- ----------
AddToRecent          Method     void AddToRecent (Variant, string)
BrowseForFolder      Method     Folder BrowseForFolder (int, string, int, Variant)
CanStartStopService  Method     Variant CanStartStopService (string)
CascadeWindows       Method     void CascadeWindows ()
ControlPanelItem     Method     void ControlPanelItem (string)
EjectPC              Method     void EjectPC ()
Explore              Method     void Explore (Variant)
ExplorerPolicy       Method     Variant ExplorerPolicy (string)
FileRun              Method     void FileRun ()
FindComputer         Method     void FindComputer ()
FindFiles            Method     void FindFiles ()
FindPrinter          Method     void FindPrinter (string, string, string)
GetSetting           Method     bool GetSetting (int)
GetSystemInformation Method     Variant GetSystemInformation (string)
Help                 Method     void Help ()
IsRestricted         Method     int IsRestricted (string, string)
IsServiceRunning     Method     Variant IsServiceRunning (string)
MinimizeAll          Method     void MinimizeAll ()
NameSpace            Method     Folder NameSpace (Variant)
Open                 Method     void Open (Variant)
RefreshMenu          Method     void RefreshMenu ()
ServiceStart         Method     Variant ServiceStart (string, Variant)
ServiceStop          Method     Variant ServiceStop (string, Variant)
SetTime              Method     void SetTime ()
ShellExecute         Method     void ShellExecute (string, Variant, Variant, Variant, Variant)
ShowBrowserBar       Method     Variant ShowBrowserBar (string, Variant)
ShutdownWindows      Method     void ShutdownWindows ()
Suspend              Method     void Suspend ()
TileHorizontally     Method     void TileHorizontally ()
TileVertically       Method     void TileVertically ()
ToggleDesktop        Method     void ToggleDesktop ()
TrayProperties       Method     void TrayProperties ()
UndoMinimizeALL      Method     void UndoMinimizeALL ()
Windows              Method     IDispatch Windows ()
WindowsSecurity      Method     void WindowsSecurity ()
WindowSwitcher       Method     void WindowSwitcher ()
Application          Property   IDispatch Application () {get}
Parent               Property   IDispatch Parent () {get}
```

### <span data-ttu-id="89ca2-130">例 5: 複数の引数をコンストラクターに渡す</span><span class="sxs-lookup"><span data-stu-id="89ca2-130">Example 5: Pass multiple arguments to a constructor</span></span>

<span data-ttu-id="89ca2-131">この例では、複数のパラメーターを受け取るコンストラクターを使用してオブジェクトを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-131">This example shows how to create an object with a constructor that takes multiple parameters.</span></span> <span data-ttu-id="89ca2-132">**ArgumentList** parameter を使用する場合、パラメーターは配列に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89ca2-132">The parameters must be put in an array when using **ArgumentList** parameter.</span></span>

```powershell
$array = @('One', 'Two', 'Three')
$parameters = @{
    TypeName = 'System.Collections.Generic.HashSet[string]'
    ArgumentList = ([string[]]$array, [System.StringComparer]::OrdinalIgnoreCase)
}
$set = New-Object @parameters
```

<span data-ttu-id="89ca2-133">PowerShell は、配列の各メンバーをコンストラクターのパラメーターにバインドします。</span><span class="sxs-lookup"><span data-stu-id="89ca2-133">PowerShell binds each member of the array to a parameter of the constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="89ca2-134">この例では、読みやすくするためにパラメータースプラッティングを使用します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-134">This example uses parameter splatting for readability.</span></span> <span data-ttu-id="89ca2-135">詳細については、「 [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89ca2-135">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

### <span data-ttu-id="89ca2-136">例 6: 1 つのパラメーターとして配列を受け取るコンストラクターを呼び出す</span><span class="sxs-lookup"><span data-stu-id="89ca2-136">Example 6: Calling a constructor that takes an array as a single parameter</span></span>

<span data-ttu-id="89ca2-137">この例では、配列またはコレクションであるパラメーターを受け取るコンストラクターを使用してオブジェクトを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-137">This example shows how to create an object with a constructor that takes a parameter that is an array or collection.</span></span> <span data-ttu-id="89ca2-138">配列パラメーターは、別の配列内にラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89ca2-138">The array parameter must be put in wrapped inside another array.</span></span>

```powershell
$array = @('One', 'Two', 'Three')
# This command throws an exception.
$set = New-Object -TypeName 'System.Collections.Generic.HashSet[string]' -ArgumentList $array
# This command succeeds.
$set = New-Object -TypeName 'System.Collections.Generic.HashSet[string]' -ArgumentList (,[string[]]$array)
$set
```

```Output
New-Object : Cannot find an overload for "HashSet`1" and the argument count: "3".
At line:1 char:8
+ $set = New-Object -TypeName 'System.Collections.Generic.HashSet[strin ...
+        ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidOperation: (:) [New-Object], MethodException
+ FullyQualifiedErrorId : ConstructorInvokedThrowException,Microsoft.PowerShell.Commands.NewObjectCommand

One
Two
Three
```

<span data-ttu-id="89ca2-139">この例で最初にオブジェクトを作成しようとすると失敗します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-139">The first attempt to create the object in this example fails.</span></span> <span data-ttu-id="89ca2-140">PowerShell は、の3つのメンバーをコンストラクターのパラメーターにバインドしようとしまし `$array` たが、コンストラクターは3つのパラメーターを受け取りません。</span><span class="sxs-lookup"><span data-stu-id="89ca2-140">PowerShell attempted to bind the three members of `$array` to parameters of the constructor but the constructor does not take three parameter.</span></span> <span data-ttu-id="89ca2-141">`$array`別の配列をラップすると、PowerShell がの3つのメンバーを `$array` コンストラクターのパラメーターにバインドできなくなります。</span><span class="sxs-lookup"><span data-stu-id="89ca2-141">Wrapping `$array` in another array prevents PowerShell from attempting to bind the three members of `$array` to parameters of the constructor.</span></span>

## <span data-ttu-id="89ca2-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="89ca2-142">PARAMETERS</span></span>

### <span data-ttu-id="89ca2-143">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="89ca2-143">-ArgumentList</span></span>

<span data-ttu-id="89ca2-144">.NET Framework クラスのコンストラクターに渡す引数の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-144">Specifies an array of arguments to pass to the constructor of the .NET Framework class.</span></span> <span data-ttu-id="89ca2-145">コンストラクターが配列である1つのパラメーターを受け取る場合は、そのパラメーターを別の配列内にラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89ca2-145">If the constructor takes a single parameter that is an array, you must wrap that parameter inside another array.</span></span> <span data-ttu-id="89ca2-146">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-146">For example:</span></span>

`$cert = New-Object System.Security.Cryptography.X509Certificates.X509Certificate -ArgumentList (,$bytes)`

<span data-ttu-id="89ca2-147">**ArgumentList** の動作の詳細については、「 [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89ca2-147">For more information about the behavior of **ArgumentList** , see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md#splatting-with-arrays).</span></span>

<span data-ttu-id="89ca2-148">**ArgumentList** のエイリアスは、 **Args** です。</span><span class="sxs-lookup"><span data-stu-id="89ca2-148">The alias for **ArgumentList** is **Args** .</span></span>

```yaml
Type: System.Object[]
Parameter Sets: Net
Aliases: Args

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89ca2-149">-ComObject</span><span class="sxs-lookup"><span data-stu-id="89ca2-149">-ComObject</span></span>

<span data-ttu-id="89ca2-150">COM オブジェクトのプログラム識別子 (ProgID) を指定します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-150">Specifies the programmatic identifier (ProgID) of the COM object.</span></span>

```yaml
Type: System.String
Parameter Sets: Com
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89ca2-151">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="89ca2-151">-Property</span></span>

<span data-ttu-id="89ca2-152">プロパティ値を設定し、新しいオブジェクトのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-152">Sets property values and invokes methods of the new object.</span></span>

<span data-ttu-id="89ca2-153">プロパティまたはメソッドの名前をキー、プロパティの値またはメソッドの引数を値とするハッシュ テーブルを入力します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-153">Enter a hash table in which the keys are the names of properties or methods and the values are property values or method arguments.</span></span> <span data-ttu-id="89ca2-154">`New-Object` オブジェクトを作成し、各プロパティ値を設定し、ハッシュテーブルに出現する順序で各メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-154">`New-Object` creates the object and sets each property value and invokes each method in the order that they appear in the hash table.</span></span>

<span data-ttu-id="89ca2-155">新しいオブジェクトが **PSObject** クラスから派生していて、オブジェクトに存在しないプロパティを指定した場合、は、 `New-Object` 指定されたプロパティを "メモ" プロパティとしてオブジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-155">If the new object is derived from the **PSObject** class, and you specify a property that does not exist on the object, `New-Object` adds the specified property to the object as a NoteProperty.</span></span> <span data-ttu-id="89ca2-156">オブジェクトが **PSObject** でない場合、コマンドは終了しないエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-156">If the object is not a **PSObject** , the command generates a non-terminating error.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89ca2-157">-Strict</span><span class="sxs-lookup"><span data-stu-id="89ca2-157">-Strict</span></span>

<span data-ttu-id="89ca2-158">作成しようとした COM オブジェクトが相互運用機能アセンブリを使用するときに、コマンドレットが終了しないエラーを生成することを示します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-158">Indicates that the cmdlet generates a non-terminating error when a COM object that you attempt to create uses an interop assembly.</span></span> <span data-ttu-id="89ca2-159">この機能は、実際の COM オブジェクトと、COM 呼び出し可能ラッパーを含む .NET Framework オブジェクトとを識別します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-159">This feature distinguishes actual COM objects from .NET Framework objects with COM-callable wrappers.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Com
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89ca2-160">-TypeName</span><span class="sxs-lookup"><span data-stu-id="89ca2-160">-TypeName</span></span>

<span data-ttu-id="89ca2-161">.NET Framework クラスの完全修飾名を指定します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-161">Specifies the fully qualified name of the .NET Framework class.</span></span> <span data-ttu-id="89ca2-162">**TypeName** パラメーターと **ComObject** パラメーターの両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="89ca2-162">You cannot specify both the **TypeName** parameter and the **ComObject** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: Net
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="89ca2-163">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="89ca2-163">CommonParameters</span></span>

<span data-ttu-id="89ca2-164">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="89ca2-164">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="89ca2-165">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89ca2-165">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="89ca2-166">入力</span><span class="sxs-lookup"><span data-stu-id="89ca2-166">INPUTS</span></span>

### <span data-ttu-id="89ca2-167">なし</span><span class="sxs-lookup"><span data-stu-id="89ca2-167">None</span></span>

<span data-ttu-id="89ca2-168">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="89ca2-168">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="89ca2-169">出力</span><span class="sxs-lookup"><span data-stu-id="89ca2-169">OUTPUTS</span></span>

### <span data-ttu-id="89ca2-170">Object</span><span class="sxs-lookup"><span data-stu-id="89ca2-170">Object</span></span>

<span data-ttu-id="89ca2-171">`New-Object` 作成されたオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-171">`New-Object` returns the object that is created.</span></span>

## <span data-ttu-id="89ca2-172">注</span><span class="sxs-lookup"><span data-stu-id="89ca2-172">NOTES</span></span>

- <span data-ttu-id="89ca2-173">`New-Object` VBScript の CreateObject 関数の中で最もよく使用される機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="89ca2-173">`New-Object` provides the most commonly-used functionality of the VBScript CreateObject function.</span></span> <span data-ttu-id="89ca2-174">VBScript のようなステートメントは、 `Set objShell = CreateObject("Shell.Application")` PowerShell でに変換でき `$objShell = New-Object -COMObject "Shell.Application"` ます。</span><span class="sxs-lookup"><span data-stu-id="89ca2-174">A statement like `Set objShell = CreateObject("Shell.Application")` in VBScript can be translated to `$objShell = New-Object -COMObject "Shell.Application"` in PowerShell.</span></span>
- <span data-ttu-id="89ca2-175">`New-Object` では、Windows スクリプトホスト環境で使用できる機能が拡張されており、コマンドラインやスクリプト内から .NET Framework オブジェクトを簡単に操作できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="89ca2-175">`New-Object` expands upon the functionality available in the Windows Script Host environment by making it easy to work with .NET Framework objects from the command line and within scripts.</span></span>

## <span data-ttu-id="89ca2-176">関連リンク</span><span class="sxs-lookup"><span data-stu-id="89ca2-176">RELATED LINKS</span></span>

[<span data-ttu-id="89ca2-177">about_Object_Creation</span><span class="sxs-lookup"><span data-stu-id="89ca2-177">about_Object_Creation</span></span>](../Microsoft.PowerShell.Core/About/about_Object_Creation.md)

[<span data-ttu-id="89ca2-178">Compare-Object</span><span class="sxs-lookup"><span data-stu-id="89ca2-178">Compare-Object</span></span>](Compare-Object.md)

[<span data-ttu-id="89ca2-179">Group-Object</span><span class="sxs-lookup"><span data-stu-id="89ca2-179">Group-Object</span></span>](Group-Object.md)

[<span data-ttu-id="89ca2-180">Measure-Object</span><span class="sxs-lookup"><span data-stu-id="89ca2-180">Measure-Object</span></span>](Measure-Object.md)

[<span data-ttu-id="89ca2-181">Select-Object</span><span class="sxs-lookup"><span data-stu-id="89ca2-181">Select-Object</span></span>](Select-Object.md)

[<span data-ttu-id="89ca2-182">Sort-Object</span><span class="sxs-lookup"><span data-stu-id="89ca2-182">Sort-Object</span></span>](Sort-Object.md)

[<span data-ttu-id="89ca2-183">Tee-Object</span><span class="sxs-lookup"><span data-stu-id="89ca2-183">Tee-Object</span></span>](Tee-Object.md)
