---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-type?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Type
ms.openlocfilehash: 9a51c97def7cddf45c391ed91ff67ad97fbedf77
ms.sourcegitcommit: e0f9fe6335be1e0f94bedaa0e8baec2acaeaa076
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "93219904"
---
# <span data-ttu-id="6a999-103">Add-Type</span><span class="sxs-lookup"><span data-stu-id="6a999-103">Add-Type</span></span>

## <span data-ttu-id="6a999-104">概要</span><span class="sxs-lookup"><span data-stu-id="6a999-104">SYNOPSIS</span></span>
<span data-ttu-id="6a999-105">PowerShell セッションに Microsoft .NET コアクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="6a999-105">Adds a Microsoft .NET Core class to a PowerShell session.</span></span>

## <span data-ttu-id="6a999-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6a999-106">SYNTAX</span></span>

### <span data-ttu-id="6a999-107">FromSource (既定値)</span><span class="sxs-lookup"><span data-stu-id="6a999-107">FromSource (Default)</span></span>

```
Add-Type [-TypeDefinition] <String> [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="6a999-108">FromMember</span><span class="sxs-lookup"><span data-stu-id="6a999-108">FromMember</span></span>

```
Add-Type [-Name] <String> [-MemberDefinition] <String[]> [-Namespace <String>]
 [-UsingNamespace <String[]>] [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [-CompilerOptions <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="6a999-109">FromPath</span><span class="sxs-lookup"><span data-stu-id="6a999-109">FromPath</span></span>

```
Add-Type [-Path] <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="6a999-110">FromLiteralPath</span><span class="sxs-lookup"><span data-stu-id="6a999-110">FromLiteralPath</span></span>

```
Add-Type -LiteralPath <String[]> [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [-CompilerOptions <String[]>]
 [<CommonParameters>]
```

### <span data-ttu-id="6a999-111">FromAssemblyName</span><span class="sxs-lookup"><span data-stu-id="6a999-111">FromAssemblyName</span></span>

```
Add-Type -AssemblyName <String[]> [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="6a999-112">Description</span><span class="sxs-lookup"><span data-stu-id="6a999-112">DESCRIPTION</span></span>

<span data-ttu-id="6a999-113">`Add-Type`コマンドレットを使用すると、PowerShell セッションで Microsoft .NET コアクラスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="6a999-113">The `Add-Type` cmdlet lets you define a Microsoft .NET Core class in your PowerShell session.</span></span> <span data-ttu-id="6a999-114">次に、コマンドレットを使用してオブジェクトをインスタンス化 `New-Object` し、.Net Core オブジェクトを使用する場合と同じようにオブジェクトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6a999-114">You can then instantiate objects, by using the `New-Object` cmdlet, and use the objects just as you would use any .NET Core object.</span></span> <span data-ttu-id="6a999-115">`Add-Type`Powershell プロファイルにコマンドを追加すると、すべての powershell セッションでクラスが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6a999-115">If you add an `Add-Type` command to your PowerShell profile, the class is available in all PowerShell sessions.</span></span>

<span data-ttu-id="6a999-116">既存のアセンブリまたはソース コード ファイルを指定して型を指定することも、インラインで、または変数に保存されたソース コードを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6a999-116">You can specify the type by specifying an existing assembly or source code files, or you can specify the source code inline or saved in a variable.</span></span> <span data-ttu-id="6a999-117">メソッドだけを指定し、クラスを定義して生成することもでき `Add-Type` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-117">You can even specify only a method and `Add-Type` defines and generates the class.</span></span> <span data-ttu-id="6a999-118">Windows では、この機能を使用して、PowerShell でアンマネージ関数に対するプラットフォーム呼び出し (P/Invoke) 呼び出しを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6a999-118">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span> <span data-ttu-id="6a999-119">ソースコードを指定すると、は `Add-Type` 指定されたソースコードをコンパイルし、新しい .Net Core 型を含むメモリ内アセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="6a999-119">If you specify source code, `Add-Type` compiles the specified source code and generates an in-memory assembly that contains the new .NET Core types.</span></span>

<span data-ttu-id="6a999-120">のパラメーターを使用して、 `Add-Type` 代替言語とコンパイラを指定できます。 C# は、既定、コンパイラオプション、アセンブリの依存関係、クラスの名前空間、型の名前、および生成されたアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="6a999-120">You can use the parameters of `Add-Type` to specify an alternate language and compiler, C# is the default, compiler options, assembly dependencies, the class namespace, the names of the type, and the resulting assembly.</span></span>

## <span data-ttu-id="6a999-121">例</span><span class="sxs-lookup"><span data-stu-id="6a999-121">EXAMPLES</span></span>

### <span data-ttu-id="6a999-122">例 1: セッションに .NET 型を追加する</span><span class="sxs-lookup"><span data-stu-id="6a999-122">Example 1: Add a .NET type to a session</span></span>

<span data-ttu-id="6a999-123">この例では、変数に格納されているソースコードを指定することによって、 **Basictest** クラスをセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="6a999-123">This example adds the **BasicTest** class to the session by specifying source code that is stored in a variable.</span></span> <span data-ttu-id="6a999-124">**Basictest** クラスは、整数の追加、オブジェクトの作成、および整数の乗算を行うために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6a999-124">The **BasicTest** class is used to add integers, create an object, and multiply integers.</span></span>

```powershell
$Source = @"
public class BasicTest
{
  public static int Add(int a, int b)
    {
        return (a + b);
    }
  public int Multiply(int a, int b)
    {
    return (a * b);
    }
}
"@

Add-Type -TypeDefinition $Source
[BasicTest]::Add(4, 3)
$BasicTestObject = New-Object BasicTest
$BasicTestObject.Multiply(5, 2)
```

<span data-ttu-id="6a999-125">変数は、 `$Source` クラスのソースコードを格納します。</span><span class="sxs-lookup"><span data-stu-id="6a999-125">The `$Source` variable stores the source code for the class.</span></span> <span data-ttu-id="6a999-126">この型には、という静的メソッドと、と `Add` いう非静的メソッドがあり `Multiply` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-126">The type has a static method called `Add` and a non-static method called `Multiply`.</span></span>

<span data-ttu-id="6a999-127">コマンドレットでは、 `Add-Type` クラスをセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="6a999-127">The `Add-Type` cmdlet adds the class to the session.</span></span> <span data-ttu-id="6a999-128">インラインソースコードを使用しているため、このコマンドは **Typedefinition** パラメーターを使用して変数内のコードを指定し `$Source` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-128">Because it's using inline source code, the command uses the **TypeDefinition** parameter to specify the code in the `$Source` variable.</span></span>

<span data-ttu-id="6a999-129">`Add` **Basictest** クラスの静的メソッドでは、2つのコロンの文字 () を使用して `::` 、クラスの静的メンバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a999-129">The `Add` static method of the **BasicTest** class uses the double-colon characters (`::`) to specify a static member of the class.</span></span> <span data-ttu-id="6a999-130">整数が追加され、合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a999-130">The integers are added and the sum is displayed.</span></span>

<span data-ttu-id="6a999-131">`New-Object`コマンドレットは、 **basictest** クラスのインスタンスをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="6a999-131">The `New-Object` cmdlet instantiates an instance of the **BasicTest** class.</span></span> <span data-ttu-id="6a999-132">このメソッドは、新しいオブジェクトを変数に保存し `$BasicTestObject` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-132">It saves the new object in the `$BasicTestObject` variable.</span></span>

<span data-ttu-id="6a999-133">`$BasicTestObject` メソッドを使用 `Multiply` します。</span><span class="sxs-lookup"><span data-stu-id="6a999-133">`$BasicTestObject` uses the `Multiply` method.</span></span> <span data-ttu-id="6a999-134">整数が乗算され、製品が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6a999-134">The integers are multiplied and the product is displayed.</span></span>

### <span data-ttu-id="6a999-135">例 2: 追加された型を確認する</span><span class="sxs-lookup"><span data-stu-id="6a999-135">Example 2: Examine an added type</span></span>

<span data-ttu-id="6a999-136">この例では、コマンドレットを使用して、 `Get-Member` `Add-Type` `New-Object` **例 1** で作成したコマンドレットとコマンドレットによって作成されたオブジェクトを確認します。</span><span class="sxs-lookup"><span data-stu-id="6a999-136">This example uses the `Get-Member` cmdlet to examine the objects that the `Add-Type` and `New-Object` cmdlets created in **Example 1**.</span></span>

```powershell
[BasicTest] | Get-Member
```

```Output
   TypeName: System.RuntimeType

Name                 MemberType Definition
----                 ---------- ----------
AsType               Method     type AsType()
Clone                Method     System.Object Clone(), System.Object ICloneable.Clone()
Equals               Method     bool Equals(System.Object obj), bool Equals(type o)
FindInterfaces       Method     type[] FindInterfaces(System.Reflection.TypeFilter filter...
...
```

```powershell
[BasicTest] | Get-Member -Static
```

```Output
  TypeName: BasicTest

Name            MemberType Definition
----            ---------- ----------
Add             Method     static int Add(int a, int b)
Equals          Method     static bool Equals(System.Object objA, System.Object objB)
new             Method     BasicTest new()
ReferenceEquals Method     static bool ReferenceEquals(System.Object objA, System.Object objB)
```

```powershell
$BasicTestObject | Get-Member
```

```Output
   TypeName: BasicTest

Name        MemberType Definition
----        ---------- ----------
Equals      Method     bool Equals(System.Object obj)
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
Multiply    Method     int Multiply(int a, int b)
ToString    Method     string ToString()
```

<span data-ttu-id="6a999-137">この `Get-Member` コマンドレットは、セッションに追加された **basictest** クラスの型とメンバーを取得し `Add-Type` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-137">The `Get-Member` cmdlet gets the type and members of the **BasicTest** class that `Add-Type` added to the session.</span></span> <span data-ttu-id="6a999-138">`Get-Member`このコマンドは、 **system.runtimetype** オブジェクトであることを明らかにします。これは、 **system.object** クラスから派生したものです。</span><span class="sxs-lookup"><span data-stu-id="6a999-138">The `Get-Member` command reveals that it's a **System.RuntimeType** object, which is derived from the **System.Object** class.</span></span>

<span data-ttu-id="6a999-139">`Get-Member` **Static** パラメーターは、 **basictest** クラスの静的プロパティと静的メソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a999-139">The `Get-Member` **Static** parameter gets the static properties and methods of the **BasicTest** class.</span></span> <span data-ttu-id="6a999-140">出力は、メソッドが含まれていることを示してい `Add` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-140">The output shows that the `Add` method is included.</span></span>

<span data-ttu-id="6a999-141">この `Get-Member` コマンドレットは、変数に格納されているオブジェクトのメンバーを取得し `$BasicTestObject` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-141">The `Get-Member` cmdlet gets the members of the object stored in the `$BasicTestObject` variable.</span></span>
<span data-ttu-id="6a999-142">`$BasicTestObject` は、 `New-Object` コマンドレットと **basictest** クラスを使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="6a999-142">`$BasicTestObject` was created by using the `New-Object` cmdlet with the **BasicTest** class.</span></span> <span data-ttu-id="6a999-143">出力には、変数の値 `$BasicTestObject` が **basictest** クラスのインスタンスであり、というメンバーが含まれていることがわかり `Multiply` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-143">The output reveals that the value of the `$BasicTestObject` variable is an instance of the **BasicTest** class and that it includes a member called `Multiply`.</span></span>

### <span data-ttu-id="6a999-144">例 3: アセンブリから型を追加する</span><span class="sxs-lookup"><span data-stu-id="6a999-144">Example 3: Add types from an assembly</span></span>

<span data-ttu-id="6a999-145">この例では、アセンブリから現在のセッションにクラスを追加し `NJsonSchema.dll` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-145">This example adds the classes from the `NJsonSchema.dll` assembly to the current session.</span></span>

```powershell
Set-Location -Path $PSHOME
$AccType = Add-Type -AssemblyName *jsonschema* -PassThru
```

<span data-ttu-id="6a999-146">`Set-Location`**Path** パラメーターを使用して変数を指定し `$PSHOME` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-146">`Set-Location` uses the **Path** parameter to specify the `$PSHOME` variable.</span></span> <span data-ttu-id="6a999-147">変数は、DLL ファイルが配置されている PowerShell インストールディレクトリを参照します。</span><span class="sxs-lookup"><span data-stu-id="6a999-147">The variable references the PowerShell installation directory where the DLL file is located.</span></span>

<span data-ttu-id="6a999-148">変数は、 `$AccType` コマンドレットを使用して作成されたオブジェクトを格納し `Add-Type` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-148">The `$AccType` variable stores an object created with the `Add-Type` cmdlet.</span></span> <span data-ttu-id="6a999-149">`Add-Type`**AssemblyName** パラメーターを使用して、アセンブリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a999-149">`Add-Type` uses the **AssemblyName** parameter to specify the name of the assembly.</span></span> <span data-ttu-id="6a999-150">アスタリスク ( `*` ) のワイルドカード文字を使用すると、名前やスペルがわからない場合でも、正しいアセンブリを取得できます。</span><span class="sxs-lookup"><span data-stu-id="6a999-150">The asterisk (`*`) wildcard character allows you to get the correct assembly even when you aren't sure of the name or its spelling.</span></span> <span data-ttu-id="6a999-151">**PassThru** パラメーターは、セッションに追加されるクラスを表すオブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="6a999-151">The **PassThru** parameter generates objects that represent the classes that are added to the session.</span></span>

### <span data-ttu-id="6a999-152">例 4: ネイティブ Windows Api を呼び出す</span><span class="sxs-lookup"><span data-stu-id="6a999-152">Example 4: Call native Windows APIs</span></span>

<span data-ttu-id="6a999-153">この例では、PowerShell でネイティブ Windows Api を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6a999-153">This example demonstrates how to call native Windows APIs in PowerShell.</span></span> <span data-ttu-id="6a999-154">`Add-Type` は、プラットフォーム呼び出し (P/Invoke) メカニズムを使用して、PowerShell からの関数を呼び出し `User32.dll` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-154">`Add-Type` uses the Platform Invoke (P/Invoke) mechanism to call a function in `User32.dll` from PowerShell.</span></span> <span data-ttu-id="6a999-155">この例は、Windows オペレーティングシステムを実行しているコンピューターでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="6a999-155">This example only works on computers running the Windows operating system.</span></span>

```powershell
$Signature = @"
[DllImport("user32.dll")]public static extern bool ShowWindowAsync(IntPtr hWnd, int nCmdShow);
"@

$ShowWindowAsync = Add-Type -MemberDefinition $Signature -Name "Win32ShowWindowAsync" -Namespace Win32Functions -PassThru

# Minimize the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $pid).MainWindowHandle, 2)

# Restore the PowerShell console

$ShowWindowAsync::ShowWindowAsync((Get-Process -Id $Pid).MainWindowHandle, 4)
```

<span data-ttu-id="6a999-156">変数は、 `$Signature` 関数の C# シグネチャを格納し `ShowWindowAsync` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-156">The `$Signature` variable stores the C# signature of the `ShowWindowAsync` function.</span></span> <span data-ttu-id="6a999-157">結果として得られるメソッドが PowerShell セッションで確実に表示されるようにするには、 `public` 標準署名にキーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="6a999-157">To ensure that the resulting method is visible in a PowerShell session, the `public` keyword was added to the standard signature.</span></span> <span data-ttu-id="6a999-158">詳細については、「 [Showwindowasync 関数](/windows/win32/api/winuser/nf-winuser-showwindowasync)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a999-158">For more information, see [ShowWindowAsync function](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span></span>

<span data-ttu-id="6a999-159">この `$ShowWindowAsync` 変数は、PassThru パラメーターによって作成されたオブジェクトを格納し `Add-Type` **PassThru** ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-159">The `$ShowWindowAsync` variable stores the object created by the `Add-Type` **PassThru** parameter.</span></span>
<span data-ttu-id="6a999-160">コマンドレットでは、 `Add-Type` `ShowWindowAsync` 静的メソッドとして PowerShell セッションに関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="6a999-160">The `Add-Type` cmdlet adds the `ShowWindowAsync` function to the PowerShell session as a static method.</span></span> <span data-ttu-id="6a999-161">このコマンドでは、 **memberdefinition** パラメーターを使用して、変数に保存されているメソッド定義を指定して `$Signature` います。</span><span class="sxs-lookup"><span data-stu-id="6a999-161">The command uses the **MemberDefinition** parameter to specify the method definition saved in the `$Signature` variable.</span></span> <span data-ttu-id="6a999-162">このコマンドは、 **Name** および **Namespace** 　パラメーターを使用して、クラスの名前と名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a999-162">The command uses the **Name** and **Namespace** parameters to specify a name and namespace for the class.</span></span> <span data-ttu-id="6a999-163">**PassThru** パラメーターは、型を表すオブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="6a999-163">The **PassThru** parameter generates an object that represents the types.</span></span>

<span data-ttu-id="6a999-164">`ShowWindowAsync`PowerShell コンソールを最小化して復元するためのコマンドでは、新しい静的メソッドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6a999-164">The new `ShowWindowAsync` static method is used in the commands to minimize and restore the PowerShell console.</span></span> <span data-ttu-id="6a999-165">このメソッドは、ウィンドウハンドルと、ウィンドウの表示方法を指定する整数の2つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6a999-165">The method takes two parameters: the window handle, and an integer that specifies how the window is displayed.</span></span>

<span data-ttu-id="6a999-166">PowerShell コンソールを最小化するには、 `ShowWindowAsync` `Get-Process` コマンドレットを自動変数と共に使用して、現在の powershell セッションをホストして `$PID` いるプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="6a999-166">To minimize the PowerShell console, `ShowWindowAsync` uses the `Get-Process` cmdlet with the `$PID` automatic variable to get the process that is hosting the current PowerShell session.</span></span> <span data-ttu-id="6a999-167">次に、現在のプロセスの **MainWindowHandle** プロパティと、値を表すの値を使用し `2` `SW_MINIMIZE` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-167">Then it uses the **MainWindowHandle** property of the current process and a value of `2`, which represents the `SW_MINIMIZE` value.</span></span>

<span data-ttu-id="6a999-168">ウィンドウを復元するために、は `ShowWindowAsync` 値を表すウィンドウ位置にの値を使用し `4` `SW_RESTORE` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-168">To restore the window, `ShowWindowAsync` uses a value of `4` for the window position, which represents the `SW_RESTORE` value.</span></span>

<span data-ttu-id="6a999-169">ウィンドウを最大化するには、が表すの値を使用し `3` `SW_MAXIMIZE` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-169">To maximize the window, use the value of `3` that represents `SW_MAXIMIZE`.</span></span>

## <span data-ttu-id="6a999-170">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6a999-170">PARAMETERS</span></span>

### <span data-ttu-id="6a999-171">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="6a999-171">-AssemblyName</span></span>

<span data-ttu-id="6a999-172">型を含むアセンブリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a999-172">Specifies the name of an assembly that includes the types.</span></span> <span data-ttu-id="6a999-173">`Add-Type` 指定したアセンブリから型を取得します。</span><span class="sxs-lookup"><span data-stu-id="6a999-173">`Add-Type` takes the types from the specified assembly.</span></span> <span data-ttu-id="6a999-174">このパラメーターは、アセンブリ名に基づいて型を作成する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="6a999-174">This parameter is required when you're creating types based on an assembly name.</span></span>

<span data-ttu-id="6a999-175">アセンブリの完全名または簡易名 (部分名とも呼ばれます) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6a999-175">Enter the full or simple name, also known as the partial name, of an assembly.</span></span> <span data-ttu-id="6a999-176">アセンブリ名ではワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6a999-176">Wildcard characters are permitted in the assembly name.</span></span> <span data-ttu-id="6a999-177">単純な名前または部分名を入力すると、は `Add-Type` それを完全な名前に解決し、完全な名前を使用してアセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="6a999-177">If you enter a simple or partial name, `Add-Type` resolves it to the full name, and then uses the full name to load the assembly.</span></span>

<span data-ttu-id="6a999-178">このパラメーターは、パスまたはファイル名を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="6a999-178">This parameter doesn't accept a path or a filename.</span></span> <span data-ttu-id="6a999-179">アセンブリダイナミックリンクライブラリ (DLL) ファイルへのパスを入力するには、 **path** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6a999-179">To enter the path to the assembly dynamic-link library (DLL) file, use the **Path** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromAssemblyName
Aliases: AN

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="6a999-180">-CompilerOptions</span><span class="sxs-lookup"><span data-stu-id="6a999-180">-CompilerOptions</span></span>

<span data-ttu-id="6a999-181">ソース コード コンパイラのオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a999-181">Specifies the options for the source code compiler.</span></span> <span data-ttu-id="6a999-182">これらのオプションは、リビジョンなしでコンパイラに送信されます。</span><span class="sxs-lookup"><span data-stu-id="6a999-182">These options are sent to the compiler without revision.</span></span>

<span data-ttu-id="6a999-183">このパラメーターを使用すると、コンパイラに対して、実行可能ファイルの生成、リソースの埋め込み、オプションなどのコマンドラインオプションの設定を行うように指示でき `/unsafe` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-183">This parameter allows you to direct the compiler to generate an executable file, embed resources, or set command-line options, such as the `/unsafe` option.</span></span>

<span data-ttu-id="6a999-184">**CompilerOptions** パラメーターと **referencedassemblies** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="6a999-184">You can't use the **CompilerOptions** and **ReferencedAssemblies** parameters in the same command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6a999-185">-IgnoreWarnings</span><span class="sxs-lookup"><span data-stu-id="6a999-185">-IgnoreWarnings</span></span>

<span data-ttu-id="6a999-186">コンパイラの警告は無視します。</span><span class="sxs-lookup"><span data-stu-id="6a999-186">Ignores compiler warnings.</span></span> <span data-ttu-id="6a999-187">`Add-Type`コンパイラの警告がエラーとして処理されないようにするには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6a999-187">Use this parameter to prevent `Add-Type` from handling compiler warnings as errors.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6a999-188">-言語</span><span class="sxs-lookup"><span data-stu-id="6a999-188">-Language</span></span>

<span data-ttu-id="6a999-189">ソース コードで使用される言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a999-189">Specifies the language that is used in the source code.</span></span> <span data-ttu-id="6a999-190">このパラメーターに指定できる値は **CSharp** です。</span><span class="sxs-lookup"><span data-stu-id="6a999-190">The acceptable value for this parameter is **CSharp**.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.Language
Parameter Sets: FromSource, FromMember
Aliases:
Accepted values: CSharp

Required: False
Position: Named
Default value: CSharp
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6a999-191">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="6a999-191">-LiteralPath</span></span>

<span data-ttu-id="6a999-192">型を含むソース コード ファイルまたはアセンブリ DLL ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a999-192">Specifies the path to source code files or assembly DLL files that contain the types.</span></span> <span data-ttu-id="6a999-193">**Path** と異なり、 **LiteralPath** パラメーターの値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6a999-193">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="6a999-194">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="6a999-194">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="6a999-195">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="6a999-195">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="6a999-196">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="6a999-196">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromLiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6a999-197">-MemberDefinition</span><span class="sxs-lookup"><span data-stu-id="6a999-197">-MemberDefinition</span></span>

<span data-ttu-id="6a999-198">クラスの新しいプロパティまたはメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a999-198">Specifies new properties or methods for the class.</span></span> <span data-ttu-id="6a999-199">`Add-Type` プロパティまたはメソッドをサポートするために必要なテンプレートコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="6a999-199">`Add-Type` generates the template code that is required to support the properties or methods.</span></span>

<span data-ttu-id="6a999-200">Windows では、この機能を使用して、PowerShell でアンマネージ関数に対するプラットフォーム呼び出し (P/Invoke) 呼び出しを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6a999-200">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6a999-201">-Name</span><span class="sxs-lookup"><span data-stu-id="6a999-201">-Name</span></span>

<span data-ttu-id="6a999-202">作成するクラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a999-202">Specifies the name of the class to create.</span></span> <span data-ttu-id="6a999-203">メンバー定義から型を生成する場合は、このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="6a999-203">This parameter is required when generating a type from a member definition.</span></span>

<span data-ttu-id="6a999-204">型名と名前空間はセッション内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a999-204">The type name and namespace must be unique within a session.</span></span> <span data-ttu-id="6a999-205">型をアンロードまたは変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6a999-205">You can't unload a type or change it.</span></span>
<span data-ttu-id="6a999-206">型のコードを変更するには、名前を変更するか、新しい PowerShell セッションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a999-206">To change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="6a999-207">それ以外の場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6a999-207">Otherwise, the command fails.</span></span>

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6a999-208">-Namespace</span><span class="sxs-lookup"><span data-stu-id="6a999-208">-Namespace</span></span>

<span data-ttu-id="6a999-209">型の名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a999-209">Specifies a namespace for the type.</span></span>

<span data-ttu-id="6a999-210">このパラメーターがコマンドに含まれていない場合、型は、名前空間 " **Microsoft. PowerShell** ..." に作成されます。</span><span class="sxs-lookup"><span data-stu-id="6a999-210">If this parameter isn't included in the command, the type is created in the **Microsoft.PowerShell.Commands.AddType.AutoGeneratedTypes** namespace.</span></span> <span data-ttu-id="6a999-211">パラメーターが、空の文字列値または値を持つコマンドに含まれている場合 `$Null` 、型はグローバル名前空間で生成されます。</span><span class="sxs-lookup"><span data-stu-id="6a999-211">If the parameter is included in the command with an empty string value or a value of `$Null`, the type is generated in the global namespace.</span></span>

```yaml
Type: System.String
Parameter Sets: FromMember
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6a999-212">-OutputAssembly</span><span class="sxs-lookup"><span data-stu-id="6a999-212">-OutputAssembly</span></span>

<span data-ttu-id="6a999-213">その場所に指定した名前のアセンブリ DLL ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="6a999-213">Generates a DLL file for the assembly with the specified name in the location.</span></span> <span data-ttu-id="6a999-214">省略可能なパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="6a999-214">Enter an optional path and filename.</span></span> <span data-ttu-id="6a999-215">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6a999-215">Wildcard characters are permitted.</span></span> <span data-ttu-id="6a999-216">既定では、は `Add-Type` メモリ内にのみアセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="6a999-216">By default, `Add-Type` generates the assembly only in memory.</span></span>

```yaml
Type: System.String
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="6a999-217">-OutputType</span><span class="sxs-lookup"><span data-stu-id="6a999-217">-OutputType</span></span>

<span data-ttu-id="6a999-218">出力アセンブリの出力の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a999-218">Specifies the output type of the output assembly.</span></span> <span data-ttu-id="6a999-219">既定では、出力の種類は指定されていません。</span><span class="sxs-lookup"><span data-stu-id="6a999-219">By default, no output type is specified.</span></span> <span data-ttu-id="6a999-220">このパラメーターは、コマンドで出力アセンブリが指定されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="6a999-220">This parameter is valid only when an output assembly is specified in the command.</span></span> <span data-ttu-id="6a999-221">値の詳細については、「 [OutputAssemblyType Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a999-221">For more information about the values, see [OutputAssemblyType Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span></span>

<span data-ttu-id="6a999-222">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6a999-222">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="6a999-223">ConsoleApplication</span><span class="sxs-lookup"><span data-stu-id="6a999-223">ConsoleApplication</span></span>
- <span data-ttu-id="6a999-224">ライブラリ</span><span class="sxs-lookup"><span data-stu-id="6a999-224">Library</span></span>
- <span data-ttu-id="6a999-225">構文は</span><span class="sxs-lookup"><span data-stu-id="6a999-225">WindowsApplication</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6a999-226">`ConsoleApplication`との `WindowsApplication` 値は動作する出力を生成しないため、使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6a999-226">The `ConsoleApplication` and `WindowsApplication` values don't produce working output and should not be used.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.OutputAssemblyType
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: OT
Accepted values: ConsoleApplication, Library, WindowsApplication

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6a999-227">-PassThru</span><span class="sxs-lookup"><span data-stu-id="6a999-227">-PassThru</span></span>

<span data-ttu-id="6a999-228">追加された型を表す **System.Runtime** 　オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="6a999-228">Returns a **System.Runtime** object that represents the types that were added.</span></span> <span data-ttu-id="6a999-229">既定では、このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="6a999-229">By default, this cmdlet doesn't generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6a999-230">-Path</span><span class="sxs-lookup"><span data-stu-id="6a999-230">-Path</span></span>

<span data-ttu-id="6a999-231">型を含むソース コード ファイルまたはアセンブリ DLL ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a999-231">Specifies the path to source code files or assembly DLL files that contain the types.</span></span>

<span data-ttu-id="6a999-232">ソースコードファイルを送信すると、は `Add-Type` ファイル内のコードをコンパイルし、その型のメモリ内アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="6a999-232">If you submit source code files, `Add-Type` compiles the code in the files and creates an in-memory assembly of the types.</span></span> <span data-ttu-id="6a999-233">**Path** の値に指定されたファイル拡張子によって、が使用するコンパイラが決まり `Add-Type` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-233">The file extension specified in the value of **Path** determines the compiler that `Add-Type` uses.</span></span>

<span data-ttu-id="6a999-234">アセンブリファイルを送信すると、は `Add-Type` アセンブリからの型を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="6a999-234">If you submit an assembly file, `Add-Type` takes the types from the assembly.</span></span> <span data-ttu-id="6a999-235">メモリ内アセンブリまたはグローバル アセンブリ キャッシュを指定するには、 **AssemblyName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="6a999-235">To specify an in-memory assembly or the global assembly cache, use the **AssemblyName** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromPath
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6a999-236">-ReferencedAssemblies</span><span class="sxs-lookup"><span data-stu-id="6a999-236">-ReferencedAssemblies</span></span>

<span data-ttu-id="6a999-237">型が依存しているアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a999-237">Specifies the assemblies upon which the type depends.</span></span> <span data-ttu-id="6a999-238">既定では、は `Add-Type` およびを参照し `System.dll` `System.Management.Automation.dll` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-238">By default, `Add-Type` references `System.dll` and `System.Management.Automation.dll`.</span></span> <span data-ttu-id="6a999-239">既定のアセンブリに加え、このパラメーターを使用して指定されたアセンブリも参照されます。</span><span class="sxs-lookup"><span data-stu-id="6a999-239">The assemblies that you specify by using this parameter are referenced in addition to the default assemblies.</span></span>

<span data-ttu-id="6a999-240">PowerShell 6 以降では、 **Referencedassemblies** に既定の .net アセンブリが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="6a999-240">Beginning in PowerShell 6, **ReferencedAssemblies** doesn't include the default .NET assemblies.</span></span> <span data-ttu-id="6a999-241">このパラメーターに渡された値には、それらへの特定の参照を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a999-241">You must include a specific reference to them in the value passed to this parameter.</span></span>

<span data-ttu-id="6a999-242">**CompilerOptions** パラメーターと **referencedassemblies** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="6a999-242">You can't use the **CompilerOptions** and **ReferencedAssemblies** parameters in the same command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: RA

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6a999-243">-TypeDefinition</span><span class="sxs-lookup"><span data-stu-id="6a999-243">-TypeDefinition</span></span>

<span data-ttu-id="6a999-244">型定義を含むソース コードを指定します。</span><span class="sxs-lookup"><span data-stu-id="6a999-244">Specifies the source code that contains the type definitions.</span></span> <span data-ttu-id="6a999-245">文字列またはヒア文字列のソース コードを入力するか、ソース コードを含む変数を入力します。</span><span class="sxs-lookup"><span data-stu-id="6a999-245">Enter the source code in a string or here-string, or enter a variable that contains the source code.</span></span> <span data-ttu-id="6a999-246">ここで説明する文字列の詳細については、「 [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a999-246">For more information about here-strings, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span></span>

<span data-ttu-id="6a999-247">型定義に、名前空間宣言を含めます。</span><span class="sxs-lookup"><span data-stu-id="6a999-247">Include a namespace declaration in your type definition.</span></span> <span data-ttu-id="6a999-248">名前空間の宣言を省略すると、型が別の型または別の型のショートカットと同名となり、意図しない上書きを引き起こす場合があります。</span><span class="sxs-lookup"><span data-stu-id="6a999-248">If you omit the namespace declaration, your type might have the same name as another type or the shortcut for another type, causing an unintentional overwrite.</span></span> <span data-ttu-id="6a999-249">たとえば、 **exception** という型を定義した場合、 **system.exception のショート** カットとして **例外** を使用するスクリプトは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6a999-249">For example, if you define a type called **Exception** , scripts that use **Exception** as the shortcut for **System.Exception** will fail.</span></span>

```yaml
Type: System.String
Parameter Sets: FromSource
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6a999-250">-名前空間を介して</span><span class="sxs-lookup"><span data-stu-id="6a999-250">-UsingNamespace</span></span>

<span data-ttu-id="6a999-251">クラスに必要な他の名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="6a999-251">Specifies other namespaces that are required for the class.</span></span> <span data-ttu-id="6a999-252">これは、C# のキーワードとよく似て `Using` います。</span><span class="sxs-lookup"><span data-stu-id="6a999-252">This is much like the C# keyword, `Using`.</span></span>

<span data-ttu-id="6a999-253">既定では、は `Add-Type` **System** 名前空間を参照します。</span><span class="sxs-lookup"><span data-stu-id="6a999-253">By default, `Add-Type` references the **System** namespace.</span></span> <span data-ttu-id="6a999-254">**Memberdefinition** パラメーターが使用されている場合、は `Add-Type` 既定で **InteropServices** 名前空間も参照します。</span><span class="sxs-lookup"><span data-stu-id="6a999-254">When the **MemberDefinition** parameter is used, `Add-Type` also references the **System.Runtime.InteropServices** namespace by default.</span></span> <span data-ttu-id="6a999-255">既定の名前空間に加え、 **UsingNamespace** パラメーターを使用して追加された名前空間も参照されます。</span><span class="sxs-lookup"><span data-stu-id="6a999-255">The namespaces that you add by using the **UsingNamespace** parameter are referenced in addition to the default namespaces.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromMember
Aliases: Using

Required: False
Position: Named
Default value: System namespace
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6a999-256">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6a999-256">CommonParameters</span></span>

<span data-ttu-id="6a999-257">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6a999-257">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6a999-258">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a999-258">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6a999-259">入力</span><span class="sxs-lookup"><span data-stu-id="6a999-259">INPUTS</span></span>

### <span data-ttu-id="6a999-260">なし</span><span class="sxs-lookup"><span data-stu-id="6a999-260">None</span></span>

<span data-ttu-id="6a999-261">オブジェクトをパイプラインからに送信することはできません `Add-Type` 。</span><span class="sxs-lookup"><span data-stu-id="6a999-261">You can't send objects down the pipeline to `Add-Type`.</span></span>

## <span data-ttu-id="6a999-262">出力</span><span class="sxs-lookup"><span data-stu-id="6a999-262">OUTPUTS</span></span>

### <span data-ttu-id="6a999-263">None または system.string</span><span class="sxs-lookup"><span data-stu-id="6a999-263">None or System.Type</span></span>

<span data-ttu-id="6a999-264">**PassThru** パラメーターを使用すると、 `Add-Type` 新しい型を表す system.string オブジェクトが返され **ます。**</span><span class="sxs-lookup"><span data-stu-id="6a999-264">When you use the **PassThru** parameter, `Add-Type` returns a **System.Type** object that represents the new type.</span></span> <span data-ttu-id="6a999-265">それ以外の場合、このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="6a999-265">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="6a999-266">注</span><span class="sxs-lookup"><span data-stu-id="6a999-266">NOTES</span></span>

<span data-ttu-id="6a999-267">追加した型は、現在のセッションのみに存在します。</span><span class="sxs-lookup"><span data-stu-id="6a999-267">The types that you add exist only in the current session.</span></span> <span data-ttu-id="6a999-268">すべてのセッションで型を使用するには、それらを PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="6a999-268">To use the types in all sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="6a999-269">プロファイルの詳細については、「 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a999-269">For more information about the profile, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="6a999-270">型名と名前空間は、セッション内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a999-270">Type names and namespaces must be unique within a session.</span></span> <span data-ttu-id="6a999-271">型をアンロードまたは変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="6a999-271">You can't unload a type or change it.</span></span> <span data-ttu-id="6a999-272">型のコードを変更する必要がある場合は、名前を変更するか、新しい PowerShell セッションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a999-272">If you need to change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="6a999-273">それ以外の場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="6a999-273">Otherwise, the command fails.</span></span>

<span data-ttu-id="6a999-274">Windows PowerShell (バージョン5.1 以降) では、 `Add-Type` まだ読み込まれていないものに対してを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a999-274">In Windows PowerShell (version 5.1 and below), you need to use `Add-Type` for anything that isn't already loaded.</span></span> <span data-ttu-id="6a999-275">最も一般的なことは、グローバルアセンブリキャッシュ (GAC) 内のアセンブリに当てはまります。</span><span class="sxs-lookup"><span data-stu-id="6a999-275">Most commonly, this applies to assemblies found in the Global Assembly Cache (GAC).</span></span>
<span data-ttu-id="6a999-276">PowerShell 6 以降では、GAC が存在しないため、PowerShell によって独自のアセンブリがにインストールされ `$PSHome` ます。</span><span class="sxs-lookup"><span data-stu-id="6a999-276">In PowerShell 6 and higher, there is no GAC, so PowerShell installs its own assemblies in `$PSHome`.</span></span>
<span data-ttu-id="6a999-277">これらのアセンブリは要求に応じて自動的に読み込まれるため、を使用して読み込む必要はありません `Add-Type` 。</span><span class="sxs-lookup"><span data-stu-id="6a999-277">These assemblies are automatically loaded on request, so there's no need to use `Add-Type` to load them.</span></span> <span data-ttu-id="6a999-278">ただし、を使用すると、 `Add-Type` スクリプトを任意のバージョンの PowerShell と暗黙的に互換性のあるものにすることができます。</span><span class="sxs-lookup"><span data-stu-id="6a999-278">However, using `Add-Type` is still permitted to allow scripts to be implicitly compatible with any version of PowerShell.</span></span>

<span data-ttu-id="6a999-279">GAC 内のアセンブリは、path ではなく、型名で読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="6a999-279">Assemblies in the GAC can be loaded by type name, rather than by path.</span></span> <span data-ttu-id="6a999-280">アセンブリを `Add-Type` 自動的に読み込むことができないため、任意のパスからアセンブリを読み込むにはが必要です。</span><span class="sxs-lookup"><span data-stu-id="6a999-280">Loading assemblies from an arbitrary path requires `Add-Type`, since those assemblies cannot not be loaded automatically.</span></span>

## <span data-ttu-id="6a999-281">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6a999-281">RELATED LINKS</span></span>

[<span data-ttu-id="6a999-282">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="6a999-282">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_profiles.md)

[<span data-ttu-id="6a999-283">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="6a999-283">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="6a999-284">Add-Member</span><span class="sxs-lookup"><span data-stu-id="6a999-284">Add-Member</span></span>](Add-Member.md)

[<span data-ttu-id="6a999-285">New-Object</span><span class="sxs-lookup"><span data-stu-id="6a999-285">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="6a999-286">OutputAssemblyType</span><span class="sxs-lookup"><span data-stu-id="6a999-286">OutputAssemblyType</span></span>](/dotnet/api/microsoft.powershell.commands.outputassemblytype)

[<span data-ttu-id="6a999-287">プラットフォーム呼び出し (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="6a999-287">Platform Invoke (P/Invoke)</span></span>](/dotnet/standard/native-interop/pinvoke)

[<span data-ttu-id="6a999-288">Where-Object</span><span class="sxs-lookup"><span data-stu-id="6a999-288">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
