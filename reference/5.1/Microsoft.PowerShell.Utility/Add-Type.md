---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/26/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/add-type?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-Type
ms.openlocfilehash: af7cd937ccfc7c5f05fd0213764ed51a3ba9f2bb
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214160"
---
# <span data-ttu-id="21ed8-103">Add-Type</span><span class="sxs-lookup"><span data-stu-id="21ed8-103">Add-Type</span></span>

## <span data-ttu-id="21ed8-104">概要</span><span class="sxs-lookup"><span data-stu-id="21ed8-104">SYNOPSIS</span></span>
<span data-ttu-id="21ed8-105">PowerShell セッションに Microsoft .NET Framework クラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-105">Adds a Microsoft .NET Framework class to a PowerShell session.</span></span>

## <span data-ttu-id="21ed8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="21ed8-106">SYNTAX</span></span>

### <span data-ttu-id="21ed8-107">FromSource (既定値)</span><span class="sxs-lookup"><span data-stu-id="21ed8-107">FromSource (Default)</span></span>

```
Add-Type [-CodeDomProvider <CodeDomProvider>] [-CompilerParameters <CompilerParameters>]
 [-TypeDefinition] <String> [-Language <Language>] [-ReferencedAssemblies <String[]>]
 [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings]
 [<CommonParameters>]
```

### <span data-ttu-id="21ed8-108">FromMember</span><span class="sxs-lookup"><span data-stu-id="21ed8-108">FromMember</span></span>

```
Add-Type [-CodeDomProvider <CodeDomProvider>] [-CompilerParameters <CompilerParameters>]
 [-Name] <String> [-MemberDefinition] <String[]> [-Namespace <String>] [-UsingNamespace <String[]>]
 [-Language <Language>] [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>]
 [-OutputType <OutputAssemblyType>] [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### <span data-ttu-id="21ed8-109">FromPath</span><span class="sxs-lookup"><span data-stu-id="21ed8-109">FromPath</span></span>

```
Add-Type [-CompilerParameters <CompilerParameters>] [-Path] <String[]>
 [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>]
 [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### <span data-ttu-id="21ed8-110">FromLiteralPath</span><span class="sxs-lookup"><span data-stu-id="21ed8-110">FromLiteralPath</span></span>

```
Add-Type [-CompilerParameters <CompilerParameters>] -LiteralPath <String[]>
 [-ReferencedAssemblies <String[]>] [-OutputAssembly <String>] [-OutputType <OutputAssemblyType>]
 [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

### <span data-ttu-id="21ed8-111">FromAssemblyName</span><span class="sxs-lookup"><span data-stu-id="21ed8-111">FromAssemblyName</span></span>

```
Add-Type -AssemblyName <String[]> [-PassThru] [-IgnoreWarnings] [<CommonParameters>]
```

## <span data-ttu-id="21ed8-112">Description</span><span class="sxs-lookup"><span data-stu-id="21ed8-112">DESCRIPTION</span></span>

<span data-ttu-id="21ed8-113">`Add-Type`コマンドレットを使用すると、PowerShell セッションで Microsoft .NET Framework クラスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-113">The `Add-Type` cmdlet lets you define a Microsoft .NET Framework class in your PowerShell session.</span></span>
<span data-ttu-id="21ed8-114">次に、コマンドレットを使用してオブジェクトをインスタンス化 `New-Object` し、.NET Framework オブジェクトを使用する場合と同じようにオブジェクトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-114">You can then instantiate objects, by using the `New-Object` cmdlet, and use the objects just as you would use any .NET Framework object.</span></span> <span data-ttu-id="21ed8-115">`Add-Type`Powershell プロファイルにコマンドを追加すると、すべての powershell セッションでクラスが使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="21ed8-115">If you add an `Add-Type` command to your PowerShell profile, the class is available in all PowerShell sessions.</span></span>

<span data-ttu-id="21ed8-116">既存のアセンブリまたはソース コード ファイルを指定して型を指定することも、インラインで、または変数に保存されたソース コードを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-116">You can specify the type by specifying an existing assembly or source code files, or you can specify the source code inline or saved in a variable.</span></span> <span data-ttu-id="21ed8-117">メソッドだけを指定し、クラスを定義して生成することもでき `Add-Type` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-117">You can even specify only a method and `Add-Type` will define and generate the class.</span></span> <span data-ttu-id="21ed8-118">Windows では、この機能を使用して、PowerShell でアンマネージ関数に対するプラットフォーム呼び出し (P/Invoke) 呼び出しを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-118">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span> <span data-ttu-id="21ed8-119">ソースコードを指定すると、は `Add-Type` 指定されたソースコードをコンパイルし、新しい .NET Framework 型を含むメモリ内アセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-119">If you specify source code, `Add-Type` compiles the specified source code and generates an in-memory assembly that contains the new .NET Framework types.</span></span>

<span data-ttu-id="21ed8-120">のパラメーターを使用して、 `Add-Type` 代替言語とコンパイラを指定できます。 C# は、既定、コンパイラオプション、アセンブリの依存関係、クラスの名前空間、型の名前、および生成されたアセンブリです。</span><span class="sxs-lookup"><span data-stu-id="21ed8-120">You can use the parameters of `Add-Type` to specify an alternate language and compiler, C# is the default, compiler options, assembly dependencies, the class namespace, the names of the type, and the resulting assembly.</span></span>

## <span data-ttu-id="21ed8-121">例</span><span class="sxs-lookup"><span data-stu-id="21ed8-121">EXAMPLES</span></span>

### <span data-ttu-id="21ed8-122">例 1: セッションに .NET 型を追加する</span><span class="sxs-lookup"><span data-stu-id="21ed8-122">Example 1: Add a .NET type to a session</span></span>

<span data-ttu-id="21ed8-123">この例では、変数に格納されているソースコードを指定することによって、 **Basictest** クラスをセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-123">This example adds the **BasicTest** class to the session by specifying source code that is stored in a variable.</span></span> <span data-ttu-id="21ed8-124">**Basictest** クラスは、整数の追加、オブジェクトの作成、および整数の乗算を行うために使用されます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-124">The **BasicTest** class is used to add integers, create an object, and multiply integers.</span></span>

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

<span data-ttu-id="21ed8-125">変数は、 `$Source` クラスのソースコードを格納します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-125">The `$Source` variable stores the source code for the class.</span></span> <span data-ttu-id="21ed8-126">この型には、という静的メソッドと、と `Add` いう非静的メソッドがあり `Multiply` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-126">The type has a static method called `Add` and a non-static method called `Multiply`.</span></span>

<span data-ttu-id="21ed8-127">コマンドレットでは、 `Add-Type` クラスをセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-127">The `Add-Type` cmdlet adds the class to the session.</span></span> <span data-ttu-id="21ed8-128">インラインソースコードを使用しているため、このコマンドは **Typedefinition** パラメーターを使用して変数内のコードを指定し `$Source` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-128">Because it's using inline source code, the command uses the **TypeDefinition** parameter to specify the code in the `$Source` variable.</span></span>

<span data-ttu-id="21ed8-129">`Add` **Basictest** クラスの静的メソッドでは、2つのコロンの文字 () を使用して `::` 、クラスの静的メンバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-129">The `Add` static method of the **BasicTest** class uses the double-colon characters (`::`) to specify a static member of the class.</span></span> <span data-ttu-id="21ed8-130">整数が追加され、合計が表示されます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-130">The integers are added and the sum is displayed.</span></span>

<span data-ttu-id="21ed8-131">`New-Object`コマンドレットは、 **basictest** クラスのインスタンスをインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-131">The `New-Object` cmdlet instantiates an instance of the **BasicTest** class.</span></span> <span data-ttu-id="21ed8-132">このメソッドは、新しいオブジェクトを変数に保存し `$BasicTestObject` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-132">It saves the new object in the `$BasicTestObject` variable.</span></span>

<span data-ttu-id="21ed8-133">`$BasicTestObject` メソッドを使用 `Multiply` します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-133">`$BasicTestObject` uses the `Multiply` method.</span></span> <span data-ttu-id="21ed8-134">整数が乗算され、製品が表示されます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-134">The integers are multiplied and the product is displayed.</span></span>

### <span data-ttu-id="21ed8-135">例 2: 追加された型を確認する</span><span class="sxs-lookup"><span data-stu-id="21ed8-135">Example 2: Examine an added type</span></span>

<span data-ttu-id="21ed8-136">この例では、コマンドレットを使用して、 `Get-Member` `Add-Type` `New-Object` **例 1** で作成したコマンドレットとコマンドレットによって作成されたオブジェクトを確認します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-136">This example uses the `Get-Member` cmdlet to examine the objects that the `Add-Type` and `New-Object` cmdlets created in **Example 1** .</span></span>

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

<span data-ttu-id="21ed8-137">この `Get-Member` コマンドレットは、セッションに追加された **basictest** クラスの型とメンバーを取得し `Add-Type` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-137">The `Get-Member` cmdlet gets the type and members of the **BasicTest** class that `Add-Type` added to the session.</span></span> <span data-ttu-id="21ed8-138">`Get-Member`このコマンドは、 **system.runtimetype** オブジェクトであることを明らかにします。これは、 **system.object** クラスから派生したものです。</span><span class="sxs-lookup"><span data-stu-id="21ed8-138">The `Get-Member` command reveals that it's a **System.RuntimeType** object, which is derived from the **System.Object** class.</span></span>

<span data-ttu-id="21ed8-139">`Get-Member` **Static** パラメーターは、 **basictest** クラスの静的プロパティと静的メソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-139">The `Get-Member` **Static** parameter gets the static properties and methods of the **BasicTest** class.</span></span> <span data-ttu-id="21ed8-140">出力は、メソッドが含まれていることを示してい `Add` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-140">The output shows that the `Add` method is included.</span></span>

<span data-ttu-id="21ed8-141">この `Get-Member` コマンドレットは、変数に格納されているオブジェクトのメンバーを取得し `$BasicTestObject` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-141">The `Get-Member` cmdlet gets the members of the object stored in the `$BasicTestObject` variable.</span></span>
<span data-ttu-id="21ed8-142">`$BasicTestObject` は、 `New-Object` コマンドレットと **basictest** クラスを使用して作成されました。</span><span class="sxs-lookup"><span data-stu-id="21ed8-142">`$BasicTestObject` was created by using the `New-Object` cmdlet with the **BasicTest** class.</span></span> <span data-ttu-id="21ed8-143">出力には、変数の値 `$BasicTestObject` が **basictest** クラスのインスタンスであり、というメンバーが含まれていることがわかり `Multiply` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-143">The output reveals that the value of the `$BasicTestObject` variable is an instance of the **BasicTest** class and that it includes a member called `Multiply`.</span></span>

### <span data-ttu-id="21ed8-144">例 3: アセンブリから型を追加する</span><span class="sxs-lookup"><span data-stu-id="21ed8-144">Example 3: Add types from an assembly</span></span>

<span data-ttu-id="21ed8-145">この例では、アセンブリから現在のセッションにクラスを追加し `Accessibility.dll` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-145">This example adds the classes from the `Accessibility.dll` assembly to the current session.</span></span>

```powershell
$AccType = Add-Type -AssemblyName "accessib*" -PassThru
```

<span data-ttu-id="21ed8-146">変数は、 `$AccType` コマンドレットを使用して作成されたオブジェクトを格納し `Add-Type` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-146">The `$AccType` variable stores an object created with the `Add-Type` cmdlet.</span></span> <span data-ttu-id="21ed8-147">`Add-Type`**AssemblyName** パラメーターを使用して、アセンブリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-147">`Add-Type` uses the **AssemblyName** parameter to specify the name of the assembly.</span></span> <span data-ttu-id="21ed8-148">アスタリスク ( `*` ) のワイルドカード文字を使用すると、名前やスペルがわからない場合でも、正しいアセンブリを取得できます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-148">The asterisk (`*`) wildcard character allows you to get the correct assembly even when you aren't sure of the name or its spelling.</span></span> <span data-ttu-id="21ed8-149">**PassThru** パラメーターは、セッションに追加されるクラスを表すオブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-149">The **PassThru** parameter generates objects that represent the classes that are added to the session.</span></span>

### <span data-ttu-id="21ed8-150">例 4: ネイティブ Windows Api を呼び出す</span><span class="sxs-lookup"><span data-stu-id="21ed8-150">Example 4: Call native Windows APIs</span></span>

<span data-ttu-id="21ed8-151">この例では、PowerShell でネイティブ Windows Api を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-151">This example demonstrates how to call native Windows APIs in PowerShell.</span></span> <span data-ttu-id="21ed8-152">`Add-Type` は、プラットフォーム呼び出し (P/Invoke) メカニズムを使用して、PowerShell からの関数を呼び出し `User32.dll` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-152">`Add-Type` uses the Platform Invoke (P/Invoke) mechanism to call a function in `User32.dll` from PowerShell.</span></span> <span data-ttu-id="21ed8-153">この例は、Windows オペレーティングシステムを実行しているコンピューターでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-153">This example only works on computers running the Windows operating system.</span></span>

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

<span data-ttu-id="21ed8-154">変数は、 `$Signature` 関数の C# シグネチャを格納し `ShowWindowAsync` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-154">The `$Signature` variable stores the C# signature of the `ShowWindowAsync` function.</span></span> <span data-ttu-id="21ed8-155">結果として得られるメソッドが PowerShell セッションで確実に表示されるようにするには、 `public` 標準署名にキーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-155">To ensure that the resulting method will be visible in a PowerShell session, the `public` keyword was added to the standard signature.</span></span> <span data-ttu-id="21ed8-156">詳細については、「 [Showwindowasync 関数](/windows/win32/api/winuser/nf-winuser-showwindowasync)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21ed8-156">For more information, see [ShowWindowAsync function](/windows/win32/api/winuser/nf-winuser-showwindowasync).</span></span>

<span data-ttu-id="21ed8-157">この `$ShowWindowAsync` 変数は、PassThru パラメーターによって作成されたオブジェクトを格納し `Add-Type` **PassThru** ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-157">The `$ShowWindowAsync` variable stores the object created by the `Add-Type` **PassThru** parameter.</span></span>
<span data-ttu-id="21ed8-158">コマンドレットでは、 `Add-Type` `ShowWindowAsync` 静的メソッドとして PowerShell セッションに関数を追加します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-158">The `Add-Type` cmdlet adds the `ShowWindowAsync` function to the PowerShell session as a static method.</span></span> <span data-ttu-id="21ed8-159">このコマンドでは、 **memberdefinition** パラメーターを使用して、変数に保存されているメソッド定義を指定して `$Signature` います。</span><span class="sxs-lookup"><span data-stu-id="21ed8-159">The command uses the **MemberDefinition** parameter to specify the method definition saved in the `$Signature` variable.</span></span> <span data-ttu-id="21ed8-160">このコマンドは、 **Name** および **Namespace** 　パラメーターを使用して、クラスの名前と名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-160">The command uses the **Name** and **Namespace** parameters to specify a name and namespace for the class.</span></span> <span data-ttu-id="21ed8-161">**PassThru** パラメーターは、型を表すオブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-161">The **PassThru** parameter generates an object that represents the types.</span></span>

<span data-ttu-id="21ed8-162">`ShowWindowAsync`PowerShell コンソールを最小化して復元するためのコマンドでは、新しい静的メソッドが使用されます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-162">The new `ShowWindowAsync` static method is used in the commands to minimize and restore the PowerShell console.</span></span> <span data-ttu-id="21ed8-163">このメソッドは、ウィンドウハンドルと、ウィンドウの表示方法を指定する整数の2つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="21ed8-163">The method takes two parameters: the window handle, and an integer that specifies how the window is displayed.</span></span>

<span data-ttu-id="21ed8-164">PowerShell コンソールを最小化するには、 `ShowWindowAsync` `Get-Process` コマンドレットを自動変数と共に使用して、現在の powershell セッションをホストして `$PID` いるプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-164">To minimize the PowerShell console, `ShowWindowAsync` uses the `Get-Process` cmdlet with the `$PID` automatic variable to get the process that is hosting the current PowerShell session.</span></span> <span data-ttu-id="21ed8-165">次に、現在のプロセスの **MainWindowHandle** プロパティと、値を表すの値を使用し `2` `SW_MINIMIZE` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-165">Then it uses the **MainWindowHandle** property of the current process and a value of `2`, which represents the `SW_MINIMIZE` value.</span></span>

<span data-ttu-id="21ed8-166">ウィンドウを復元するために、は `ShowWindowAsync` 値を表すウィンドウ位置にの値を使用し `4` `SW_RESTORE` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-166">To restore the window, `ShowWindowAsync` uses a value of `4` for the window position, which represents the `SW_RESTORE` value.</span></span>

<span data-ttu-id="21ed8-167">ウィンドウを最大化するには、が表すの値を使用し `3` `SW_MAXIMIZE` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-167">To maximize the window, use the value of `3` that represents `SW_MAXIMIZE`.</span></span>

### <span data-ttu-id="21ed8-168">例 5: Visual Basic ファイルから型を追加する</span><span class="sxs-lookup"><span data-stu-id="21ed8-168">Example 5: Add a type from a Visual Basic file</span></span>

<span data-ttu-id="21ed8-169">この例では、コマンドレットを使用して、 `Add-Type` ファイルで定義されている **VBFromFile** クラスを `Hello.vb` 現在のセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-169">This example uses the `Add-Type` cmdlet to add the **VBFromFile** class that's defined in the `Hello.vb` file to the current session.</span></span> <span data-ttu-id="21ed8-170">ファイルのテキスト `Hello.vb` がコマンドの出力に表示されます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-170">The text of the `Hello.vb` file is shown in the command output.</span></span>

```powershell
Add-Type -Path "C:\PS-Test\Hello.vb"
[VBFromFile]::SayHello(", World")

# From Hello.vb

Public Class VBFromFile
  Public Shared Function SayHello(sourceName As String) As String
    Dim myValue As String = "Hello"
    return myValue + sourceName
  End Function
End Class
```

```Output
Hello, World
```

<span data-ttu-id="21ed8-171">`Add-Type`**Path** パラメーターを使用してソースファイルを指定し、 `Hello.vb` ファイルで定義されている型を追加します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-171">`Add-Type` uses the **Path** parameter to specify the source file, `Hello.vb`, and adds the type defined in the file.</span></span> <span data-ttu-id="21ed8-172">`SayHello`関数は、 **VBFromFile** クラスの静的メソッドとして呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-172">The `SayHello` function is called as a static method of the **VBFromFile** class.</span></span>

### <span data-ttu-id="21ed8-173">例 6: JScript.NET を使用してクラスを追加する</span><span class="sxs-lookup"><span data-stu-id="21ed8-173">Example 6: Add a class with JScript.NET</span></span>

<span data-ttu-id="21ed8-174">この例では、JScript.NET を使用して、PowerShell セッションに新しいクラス **Frectangle** を作成します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-174">This example uses JScript.NET to create a new class, **FRectangle** , in your PowerShell session.</span></span>

```powershell
Add-Type @'
 class FRectangle {
   var Length : double;
   var Height : double;
   function Perimeter() : double {
       return (Length + Height) * 2; }
   function Area() : double {
       return Length * Height;  } }
'@ -Language JScript

$rect = [FRectangle]::new()
$rect
```

```Output
Length Height
------ ------
     0      0
```

### <span data-ttu-id="21ed8-175">例 7: F # コンパイラを追加する</span><span class="sxs-lookup"><span data-stu-id="21ed8-175">Example 7: Add an F# compiler</span></span>

<span data-ttu-id="21ed8-176">この例では、コマンドレットを使用し `Add-Type` て、PowerShell セッションに F # コードコンパイラを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-176">This example shows how to use the `Add-Type` cmdlet to add an F# code compiler to your PowerShell session.</span></span> <span data-ttu-id="21ed8-177">PowerShell でこの例を実行するには、 `FSharp.Compiler.CodeDom.dll` F # 言語でインストールされたが必要です。</span><span class="sxs-lookup"><span data-stu-id="21ed8-177">To run this example in PowerShell, you must have the `FSharp.Compiler.CodeDom.dll` that is installed with the F# language.</span></span>

```powershell
Add-Type -Path "FSharp.Compiler.CodeDom.dll"
$Provider = New-Object Microsoft.FSharp.Compiler.CodeDom.FSharpCodeProvider
$FSharpCode = @"
let rec loop n =if n <= 0 then () else beginprint_endline (string_of_int n);loop (n-1)end
"@
$FSharpType = Add-Type -TypeDefinition $FSharpCode -CodeDomProvider $Provider -PassThru |
   Where-Object { $_.IsPublic }
$FSharpType::loop(4)
```

```Output
4
3
2
1
```

<span data-ttu-id="21ed8-178">`Add-Type`**Path** パラメーターを使用してアセンブリを指定し、アセンブリ内の型を取得します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-178">`Add-Type` uses the **Path** parameter to specify an assembly and gets the types in the assembly.</span></span>
<span data-ttu-id="21ed8-179">`New-Object` F # コードプロバイダーのインスタンスを作成し、その結果を変数に保存し `$Provider` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-179">`New-Object` creates an instance of the F# code provider and saves the result in the `$Provider` variable.</span></span> <span data-ttu-id="21ed8-180">変数は、 `$FSharpCode` **Loop** メソッドを定義する F # コードを保存します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-180">The `$FSharpCode` variable saves the F# code that defines the **Loop** method.</span></span>

<span data-ttu-id="21ed8-181">変数は、 `$FSharpType` `Add-Type` で定義されているパブリック型を保存するコマンドレットの結果を格納し `$FSharpCode` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-181">The the `$FSharpType` variable stores the results of the `Add-Type` cmdlet that saves the public types defined in `$FSharpCode`.</span></span> <span data-ttu-id="21ed8-182">**TypeDefinition** パラメーターは、型を定義するソース コードを指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-182">The **TypeDefinition** parameter specifies the source code that defines the types.</span></span> <span data-ttu-id="21ed8-183">**CodeDomProvider** パラメーターは、ソース コード コンパイラを指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-183">The **CodeDomProvider** parameter specifies the source code compiler.</span></span> <span data-ttu-id="21ed8-184">**PassThru** パラメーターは `Add-Type` 、型を表す **ランタイム** オブジェクトを返すように指示します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-184">The **PassThru** parameter directs `Add-Type` to return a **Runtime** object that represents the types.</span></span>
<span data-ttu-id="21ed8-185">オブジェクトは、パイプを使用してコマンドレットに送信され `Where-Object` ます。このコマンドレットは、パブリック型のみを返します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-185">The objects are sent down the pipeline to the `Where-Object` cmdlet, which returns only the public types.</span></span> <span data-ttu-id="21ed8-186">**Where-object** コマンドレットは、結果のパブリック型をサポートするために F # プロバイダーが非パブリック型を生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-186">The **Where-Object** cmdlet is used because the F# provider generates non-public types to support the resulting public type.</span></span>

<span data-ttu-id="21ed8-187">Loop メソッドは、変数に格納されている型の静的メソッドとして呼び出され `$FSharpType` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-187">The Loop method is called as a static method of the type stored in the `$FSharpType` variable.</span></span>

## <span data-ttu-id="21ed8-188">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="21ed8-188">PARAMETERS</span></span>

### <span data-ttu-id="21ed8-189">-AssemblyName</span><span class="sxs-lookup"><span data-stu-id="21ed8-189">-AssemblyName</span></span>

<span data-ttu-id="21ed8-190">型を含むアセンブリの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-190">Specifies the name of an assembly that includes the types.</span></span> <span data-ttu-id="21ed8-191">`Add-Type` 指定したアセンブリから型を取得します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-191">`Add-Type` takes the types from the specified assembly.</span></span> <span data-ttu-id="21ed8-192">このパラメーターは、アセンブリ名に基づいて型を作成する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="21ed8-192">This parameter is required when you're creating types based on an assembly name.</span></span>

<span data-ttu-id="21ed8-193">アセンブリの完全名または簡易名 (部分名とも呼ばれます) を入力します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-193">Enter the full or simple name, also known as the partial name, of an assembly.</span></span> <span data-ttu-id="21ed8-194">アセンブリ名ではワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-194">Wildcard characters are permitted in the assembly name.</span></span> <span data-ttu-id="21ed8-195">単純な名前または部分名を入力すると、は `Add-Type` それを完全な名前に解決し、完全な名前を使用してアセンブリを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-195">If you enter a simple or partial name, `Add-Type` resolves it to the full name, and then uses the full name to load the assembly.</span></span>

<span data-ttu-id="21ed8-196">このパラメーターは、パスまたはファイル名を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="21ed8-196">This parameter doesn't accept a path or a file name.</span></span> <span data-ttu-id="21ed8-197">アセンブリダイナミックリンクライブラリ (DLL) ファイルへのパスを入力するには、 **path** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-197">To enter the path to the assembly dynamic-link library (DLL) file, use the **Path** parameter.</span></span>

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

### <span data-ttu-id="21ed8-198">-CodeDomProvider</span><span class="sxs-lookup"><span data-stu-id="21ed8-198">-CodeDomProvider</span></span>

<span data-ttu-id="21ed8-199">コード ジェネレーターまたはコンパイラを指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-199">Specifies a code generator or compiler.</span></span> <span data-ttu-id="21ed8-200">`Add-Type` 指定されたコンパイラを使用して、ソースコードをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="21ed8-200">`Add-Type` uses the specified compiler to compile the source code.</span></span> <span data-ttu-id="21ed8-201">既定値は C# コンパイラです。</span><span class="sxs-lookup"><span data-stu-id="21ed8-201">The default is the C# compiler.</span></span> <span data-ttu-id="21ed8-202">**Language** パラメーターを使用して指定できない言語を使用している場合は、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-202">Use this parameter if you're using a language that can't be specified by using the **Language** parameter.</span></span> <span data-ttu-id="21ed8-203">指定する **CodeDomProvider** は、ソースコードからアセンブリを生成できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="21ed8-203">The **CodeDomProvider** that you specify must be able to generate assemblies from source code.</span></span>

```yaml
Type: System.CodeDom.Compiler.CodeDomProvider
Parameter Sets: FromSource, FromMember
Aliases: Provider

Required: False
Position: Named
Default value: C# compiler
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21ed8-204">-CompilerParameters</span><span class="sxs-lookup"><span data-stu-id="21ed8-204">-CompilerParameters</span></span>

<span data-ttu-id="21ed8-205">ソース コード コンパイラのオプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-205">Specifies the options for the source code compiler.</span></span> <span data-ttu-id="21ed8-206">これらのオプションは、リビジョンなしでコンパイラに送信されます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-206">These options are sent to the compiler without revision.</span></span>

<span data-ttu-id="21ed8-207">このパラメーターを使用すると、コンパイラに対して、実行可能ファイルの生成、リソースの埋め込み、オプションなどのコマンドラインオプションの設定を行うように指示でき `/unsafe` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-207">This parameter allows you to direct the compiler to generate an executable file, embed resources, or set command-line options, such as the `/unsafe` option.</span></span> <span data-ttu-id="21ed8-208">このパラメーターは、 **CompilerParameters** クラス **CompilerParameters** を実装します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-208">This parameter implements the **CompilerParameters** class, **System.CodeDom.Compiler.CompilerParameters** .</span></span>

<span data-ttu-id="21ed8-209">**CompilerParameters** パラメーターと **referencedassemblies** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="21ed8-209">You can't use the **CompilerParameters** and **ReferencedAssemblies** parameters in the same command.</span></span>

```yaml
Type: System.CodeDom.Compiler.CompilerParameters
Parameter Sets: FromSource, FromMember, FromPath, FromLiteralPath
Aliases: CP

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21ed8-210">-IgnoreWarnings</span><span class="sxs-lookup"><span data-stu-id="21ed8-210">-IgnoreWarnings</span></span>

<span data-ttu-id="21ed8-211">コンパイラの警告は無視します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-211">Ignores compiler warnings.</span></span> <span data-ttu-id="21ed8-212">`Add-Type`コンパイラの警告がエラーとして処理されないようにするには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-212">Use this parameter to prevent `Add-Type` from handling compiler warnings as errors.</span></span>

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

### <span data-ttu-id="21ed8-213">-言語</span><span class="sxs-lookup"><span data-stu-id="21ed8-213">-Language</span></span>

<span data-ttu-id="21ed8-214">ソース コードで使用される言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-214">Specifies the language that is used in the source code.</span></span> <span data-ttu-id="21ed8-215">コマンドレットでは、 `Add-Type` このパラメーターの値を使用して、適切な **CodeDomProvider** を選択します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-215">The `Add-Type` cmdlet uses the value of this parameter to select the appropriate **CodeDomProvider** .</span></span> <span data-ttu-id="21ed8-216">CSharp が既定値です。</span><span class="sxs-lookup"><span data-stu-id="21ed8-216">CSharp is the default value.</span></span> <span data-ttu-id="21ed8-217">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="21ed8-217">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="21ed8-218">CSharp</span><span class="sxs-lookup"><span data-stu-id="21ed8-218">CSharp</span></span>
- <span data-ttu-id="21ed8-219">CSharpVersion2</span><span class="sxs-lookup"><span data-stu-id="21ed8-219">CSharpVersion2</span></span>
- <span data-ttu-id="21ed8-220">CSharpVersion3</span><span class="sxs-lookup"><span data-stu-id="21ed8-220">CSharpVersion3</span></span>
- <span data-ttu-id="21ed8-221">JScript</span><span class="sxs-lookup"><span data-stu-id="21ed8-221">JScript</span></span>
- <span data-ttu-id="21ed8-222">VisualBasic</span><span class="sxs-lookup"><span data-stu-id="21ed8-222">VisualBasic</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.Language
Parameter Sets: FromSource, FromMember
Aliases:
Accepted values: CSharp, CSharpVersion2, CSharpVersion3, JScript, VisualBasic

Required: False
Position: Named
Default value: CSharp
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21ed8-223">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="21ed8-223">-LiteralPath</span></span>

<span data-ttu-id="21ed8-224">型を含むソース コード ファイルまたはアセンブリ DLL ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-224">Specifies the path to source code files or assembly DLL files that contain the types.</span></span> <span data-ttu-id="21ed8-225">**Path** と異なり、 **LiteralPath** パラメーターの値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-225">Unlike **Path** , the value of the **LiteralPath** parameter is used exactly as it's typed.</span></span> <span data-ttu-id="21ed8-226">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="21ed8-226">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="21ed8-227">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-227">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="21ed8-228">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="21ed8-228">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: FromLiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="21ed8-229">-MemberDefinition</span><span class="sxs-lookup"><span data-stu-id="21ed8-229">-MemberDefinition</span></span>

<span data-ttu-id="21ed8-230">クラスの新しいプロパティまたはメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-230">Specifies new properties or methods for the class.</span></span> <span data-ttu-id="21ed8-231">`Add-Type` プロパティまたはメソッドをサポートするために必要なテンプレートコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-231">`Add-Type` generates the template code that is required to support the properties or methods.</span></span>

<span data-ttu-id="21ed8-232">Windows では、この機能を使用して、PowerShell でアンマネージ関数に対するプラットフォーム呼び出し (P/Invoke) 呼び出しを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-232">On Windows, you can use this feature to make Platform Invoke (P/Invoke) calls to unmanaged functions in PowerShell.</span></span>

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

### <span data-ttu-id="21ed8-233">-Name</span><span class="sxs-lookup"><span data-stu-id="21ed8-233">-Name</span></span>

<span data-ttu-id="21ed8-234">作成するクラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-234">Specifies the name of the class to create.</span></span> <span data-ttu-id="21ed8-235">メンバー定義から型を生成する場合は、このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="21ed8-235">This parameter is required when generating a type from a member definition.</span></span>

<span data-ttu-id="21ed8-236">型名と名前空間はセッション内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="21ed8-236">The type name and namespace must be unique within a session.</span></span> <span data-ttu-id="21ed8-237">型をアンロードまたは変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="21ed8-237">You can't unload a type or change it.</span></span>
<span data-ttu-id="21ed8-238">型のコードを変更するには、名前を変更するか、新しい PowerShell セッションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21ed8-238">To change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="21ed8-239">それ以外の場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-239">Otherwise, the command fails.</span></span>

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

### <span data-ttu-id="21ed8-240">-Namespace</span><span class="sxs-lookup"><span data-stu-id="21ed8-240">-Namespace</span></span>

<span data-ttu-id="21ed8-241">型の名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-241">Specifies a namespace for the type.</span></span>

<span data-ttu-id="21ed8-242">このパラメーターがコマンドに含まれていない場合、型は、名前空間 " **Microsoft. PowerShell** ..." に作成されます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-242">If this parameter isn't included in the command, the type is created in the **Microsoft.PowerShell.Commands.AddType.AutoGeneratedTypes** namespace.</span></span> <span data-ttu-id="21ed8-243">パラメーターが、空の文字列値または値を持つコマンドに含まれている場合 `$Null` 、型はグローバル名前空間で生成されます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-243">If the parameter is included in the command with an empty string value or a value of `$Null`, the type is generated in the global namespace.</span></span>

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

### <span data-ttu-id="21ed8-244">-OutputAssembly</span><span class="sxs-lookup"><span data-stu-id="21ed8-244">-OutputAssembly</span></span>

<span data-ttu-id="21ed8-245">その場所に指定した名前のアセンブリ DLL ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-245">Generates a DLL file for the assembly with the specified name in the location.</span></span> <span data-ttu-id="21ed8-246">省略可能なパスとファイル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-246">Enter an optional path and file name.</span></span> <span data-ttu-id="21ed8-247">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-247">Wildcard characters are permitted.</span></span> <span data-ttu-id="21ed8-248">既定では、は `Add-Type` メモリ内にのみアセンブリを生成します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-248">By default, `Add-Type` generates the assembly only in memory.</span></span>

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

### <span data-ttu-id="21ed8-249">-OutputType</span><span class="sxs-lookup"><span data-stu-id="21ed8-249">-OutputType</span></span>

<span data-ttu-id="21ed8-250">出力アセンブリの出力の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-250">Specifies the output type of the output assembly.</span></span> <span data-ttu-id="21ed8-251">既定では、出力の種類は指定されていません。</span><span class="sxs-lookup"><span data-stu-id="21ed8-251">By default, no output type is specified.</span></span> <span data-ttu-id="21ed8-252">このパラメーターは、コマンドで出力アセンブリが指定されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="21ed8-252">This parameter is valid only when an output assembly is specified in the command.</span></span> <span data-ttu-id="21ed8-253">値の詳細については、「 [OutputAssemblyType Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21ed8-253">For more information about the values, see [OutputAssemblyType Enumeration](/dotnet/api/microsoft.powershell.commands.outputassemblytype).</span></span>

<span data-ttu-id="21ed8-254">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="21ed8-254">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="21ed8-255">ConsoleApplication</span><span class="sxs-lookup"><span data-stu-id="21ed8-255">ConsoleApplication</span></span>
- <span data-ttu-id="21ed8-256">ライブラリ</span><span class="sxs-lookup"><span data-stu-id="21ed8-256">Library</span></span>
- <span data-ttu-id="21ed8-257">構文は</span><span class="sxs-lookup"><span data-stu-id="21ed8-257">WindowsApplication</span></span>

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

### <span data-ttu-id="21ed8-258">-PassThru</span><span class="sxs-lookup"><span data-stu-id="21ed8-258">-PassThru</span></span>

<span data-ttu-id="21ed8-259">追加された型を表す **System.Runtime** 　オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-259">Returns a **System.Runtime** object that represents the types that were added.</span></span> <span data-ttu-id="21ed8-260">既定では、このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="21ed8-260">By default, this cmdlet doesn't generate any output.</span></span>

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

### <span data-ttu-id="21ed8-261">-Path</span><span class="sxs-lookup"><span data-stu-id="21ed8-261">-Path</span></span>

<span data-ttu-id="21ed8-262">型を含むソース コード ファイルまたはアセンブリ DLL ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-262">Specifies the path to source code files or assembly DLL files that contain the types.</span></span>

<span data-ttu-id="21ed8-263">ソースコードファイルを送信すると、は `Add-Type` ファイル内のコードをコンパイルし、その型のメモリ内アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-263">If you submit source code files, `Add-Type` compiles the code in the files and creates an in-memory assembly of the types.</span></span> <span data-ttu-id="21ed8-264">**Path** の値に指定されたファイル名拡張子によって、が使用するコンパイラが決まり `Add-Type` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-264">The file name extension specified in the value of **Path** determines the compiler that `Add-Type` uses.</span></span>

<span data-ttu-id="21ed8-265">アセンブリファイルを送信すると、は `Add-Type` アセンブリからの型を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="21ed8-265">If you submit an assembly file, `Add-Type` takes the types from the assembly.</span></span> <span data-ttu-id="21ed8-266">メモリ内アセンブリまたはグローバル アセンブリ キャッシュを指定するには、 **AssemblyName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-266">To specify an in-memory assembly or the global assembly cache, use the **AssemblyName** parameter.</span></span>

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

### <span data-ttu-id="21ed8-267">-ReferencedAssemblies</span><span class="sxs-lookup"><span data-stu-id="21ed8-267">-ReferencedAssemblies</span></span>

<span data-ttu-id="21ed8-268">型が依存しているアセンブリを指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-268">Specifies the assemblies upon which the type depends.</span></span> <span data-ttu-id="21ed8-269">既定では、は `Add-Type` およびを参照し `System.dll` `System.Management.Automation.dll` ます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-269">By default, `Add-Type` references `System.dll` and `System.Management.Automation.dll`.</span></span> <span data-ttu-id="21ed8-270">既定のアセンブリに加え、このパラメーターを使用して指定されたアセンブリも参照されます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-270">The assemblies that you specify by using this parameter are referenced in addition to the default assemblies.</span></span>

<span data-ttu-id="21ed8-271">**CompilerParameters** パラメーターと **referencedassemblies** パラメーターを同じコマンドで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="21ed8-271">You can't use the **CompilerParameters** and **ReferencedAssemblies** parameters in the same command.</span></span>

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

### <span data-ttu-id="21ed8-272">-TypeDefinition</span><span class="sxs-lookup"><span data-stu-id="21ed8-272">-TypeDefinition</span></span>

<span data-ttu-id="21ed8-273">型定義を含むソース コードを指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-273">Specifies the source code that contains the type definitions.</span></span> <span data-ttu-id="21ed8-274">文字列またはヒア文字列のソース コードを入力するか、ソース コードを含む変数を入力します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-274">Enter the source code in a string or here-string, or enter a variable that contains the source code.</span></span> <span data-ttu-id="21ed8-275">ここで説明する文字列の詳細については、「 [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21ed8-275">For more information about here-strings, see [about_Quoting_Rules](../Microsoft.PowerShell.Core/about/about_Quoting_Rules.md).</span></span>

<span data-ttu-id="21ed8-276">型定義に、名前空間宣言を含めます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-276">Include a namespace declaration in your type definition.</span></span> <span data-ttu-id="21ed8-277">名前空間の宣言を省略すると、型が別の型または別の型のショートカットと同名となり、意図しない上書きを引き起こす場合があります。</span><span class="sxs-lookup"><span data-stu-id="21ed8-277">If you omit the namespace declaration, your type might have the same name as another type or the shortcut for another type, causing an unintentional overwrite.</span></span> <span data-ttu-id="21ed8-278">たとえば、 **exception** という型を定義した場合、 **system.exception のショート** カットとして **例外** を使用するスクリプトは失敗します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-278">For example, if you define a type called **Exception** , scripts that use **Exception** as the shortcut for **System.Exception** will fail.</span></span>

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

### <span data-ttu-id="21ed8-279">-名前空間を介して</span><span class="sxs-lookup"><span data-stu-id="21ed8-279">-UsingNamespace</span></span>

<span data-ttu-id="21ed8-280">クラスに必要な他の名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-280">Specifies other namespaces that are required for the class.</span></span> <span data-ttu-id="21ed8-281">これは、C# のキーワードとよく似て `Using` います。</span><span class="sxs-lookup"><span data-stu-id="21ed8-281">This is much like the C# keyword, `Using`.</span></span>

<span data-ttu-id="21ed8-282">既定では、は `Add-Type` **System** 名前空間を参照します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-282">By default, `Add-Type` references the **System** namespace.</span></span> <span data-ttu-id="21ed8-283">**Memberdefinition** パラメーターが使用されている場合、は `Add-Type` 既定で **InteropServices** 名前空間も参照します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-283">When the **MemberDefinition** parameter is used, `Add-Type` also references the **System.Runtime.InteropServices** namespace by default.</span></span> <span data-ttu-id="21ed8-284">既定の名前空間に加え、 **UsingNamespace** パラメーターを使用して追加された名前空間も参照されます。</span><span class="sxs-lookup"><span data-stu-id="21ed8-284">The namespaces that you add by using the **UsingNamespace** parameter are referenced in addition to the default namespaces.</span></span>

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

### <span data-ttu-id="21ed8-285">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="21ed8-285">CommonParameters</span></span>

<span data-ttu-id="21ed8-286">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="21ed8-286">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="21ed8-287">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21ed8-287">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="21ed8-288">入力</span><span class="sxs-lookup"><span data-stu-id="21ed8-288">INPUTS</span></span>

### <span data-ttu-id="21ed8-289">なし</span><span class="sxs-lookup"><span data-stu-id="21ed8-289">None</span></span>

<span data-ttu-id="21ed8-290">オブジェクトをパイプラインからに送信することはできません `Add-Type` 。</span><span class="sxs-lookup"><span data-stu-id="21ed8-290">You can't send objects down the pipeline to `Add-Type`.</span></span>

## <span data-ttu-id="21ed8-291">出力</span><span class="sxs-lookup"><span data-stu-id="21ed8-291">OUTPUTS</span></span>

### <span data-ttu-id="21ed8-292">None または system.string</span><span class="sxs-lookup"><span data-stu-id="21ed8-292">None or System.Type</span></span>

<span data-ttu-id="21ed8-293">**PassThru** パラメーターを使用すると、 `Add-Type` 新しい型を表す system.string オブジェクトが返され **ます。**</span><span class="sxs-lookup"><span data-stu-id="21ed8-293">When you use the **PassThru** parameter, `Add-Type` returns a **System.Type** object that represents the new type.</span></span> <span data-ttu-id="21ed8-294">それ以外の場合、このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="21ed8-294">Otherwise, this cmdlet doesn't generate any output.</span></span>

## <span data-ttu-id="21ed8-295">注</span><span class="sxs-lookup"><span data-stu-id="21ed8-295">NOTES</span></span>

<span data-ttu-id="21ed8-296">追加した型は、現在のセッションのみに存在します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-296">The types that you add exist only in the current session.</span></span> <span data-ttu-id="21ed8-297">すべてのセッションで型を使用するには、それらを PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-297">To use the types in all sessions, add them to your PowerShell profile.</span></span> <span data-ttu-id="21ed8-298">プロファイルの詳細については、「 [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21ed8-298">For more information about the profile, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md).</span></span>

<span data-ttu-id="21ed8-299">型名と名前空間は、セッション内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="21ed8-299">Type names and namespaces must be unique within a session.</span></span> <span data-ttu-id="21ed8-300">型をアンロードまたは変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="21ed8-300">You can't unload a type or change it.</span></span> <span data-ttu-id="21ed8-301">型のコードを変更する必要がある場合は、名前を変更するか、新しい PowerShell セッションを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21ed8-301">If you need to change the code for a type, you must change the name or start a new PowerShell session.</span></span>
<span data-ttu-id="21ed8-302">それ以外の場合、コマンドは失敗します。</span><span class="sxs-lookup"><span data-stu-id="21ed8-302">Otherwise, the command fails.</span></span>

<span data-ttu-id="21ed8-303">IronPython や J# などの一部の言語の **CodeDomProvider** クラスでは、出力は生成されません。</span><span class="sxs-lookup"><span data-stu-id="21ed8-303">The **CodeDomProvider** class for some languages, such as IronPython and J#, doesn't generate output.</span></span> <span data-ttu-id="21ed8-304">そのため、これらの言語で記述された型をで使用することはできません `Add-Type` 。</span><span class="sxs-lookup"><span data-stu-id="21ed8-304">As a result, types written in these languages can't be used with `Add-Type`.</span></span>

<span data-ttu-id="21ed8-305">このコマンドレットは、Microsoft .NET Framework [CodeDomProvider クラス](/dotnet/api/system.codedom.compiler.codedomprovider)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="21ed8-305">This cmdlet is based on the Microsoft .NET Framework [CodeDomProvider Class](/dotnet/api/system.codedom.compiler.codedomprovider).</span></span>

## <span data-ttu-id="21ed8-306">関連リンク</span><span class="sxs-lookup"><span data-stu-id="21ed8-306">RELATED LINKS</span></span>

[<span data-ttu-id="21ed8-307">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="21ed8-307">about_Profiles</span></span>](../Microsoft.PowerShell.Core/About/about_profiles.md)

[<span data-ttu-id="21ed8-308">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="21ed8-308">about_Quoting_Rules</span></span>](../Microsoft.PowerShell.Core/About/about_Quoting_Rules.md)

[<span data-ttu-id="21ed8-309">Add-Member</span><span class="sxs-lookup"><span data-stu-id="21ed8-309">Add-Member</span></span>](Add-Member.md)

[<span data-ttu-id="21ed8-310">New-Object</span><span class="sxs-lookup"><span data-stu-id="21ed8-310">New-Object</span></span>](New-Object.md)

[<span data-ttu-id="21ed8-311">OutputAssemblyType</span><span class="sxs-lookup"><span data-stu-id="21ed8-311">OutputAssemblyType</span></span>](/dotnet/api/microsoft.powershell.commands.outputassemblytype)

[<span data-ttu-id="21ed8-312">プラットフォーム呼び出し (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="21ed8-312">Platform Invoke (P/Invoke)</span></span>](/dotnet/standard/native-interop/pinvoke)

[<span data-ttu-id="21ed8-313">Where-Object</span><span class="sxs-lookup"><span data-stu-id="21ed8-313">Where-Object</span></span>](../Microsoft.PowerShell.Core/Where-Object.md)
