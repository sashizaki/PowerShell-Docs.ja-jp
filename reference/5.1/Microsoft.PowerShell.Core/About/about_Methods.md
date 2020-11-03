---
description: メソッドを使用して PowerShell のオブジェクトに対してアクションを実行する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 04/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_methods?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Methods
ms.openlocfilehash: 7160b049cffffa35263fc75fd595997c98ca2e34
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222672"
---
# <a name="about-methods"></a><span data-ttu-id="42600-104">メソッドの概要</span><span class="sxs-lookup"><span data-stu-id="42600-104">About methods</span></span>

## <a name="short-description"></a><span data-ttu-id="42600-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="42600-105">Short description</span></span>
<span data-ttu-id="42600-106">メソッドを使用して PowerShell のオブジェクトに対してアクションを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42600-106">Describes how to use methods to perform actions on objects in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="42600-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="42600-107">Long description</span></span>

<span data-ttu-id="42600-108">PowerShell はオブジェクトを使用して、データストア内の項目またはコンピューターの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="42600-108">PowerShell uses objects to represent the items in data stores or the state of the computer.</span></span> <span data-ttu-id="42600-109">たとえば、FileInfo オブジェクトはファイルシステムドライブ内のファイルを表し、ProcessInfo オブジェクトはコンピューター上のプロセスを表します。</span><span class="sxs-lookup"><span data-stu-id="42600-109">For example, FileInfo objects represent the files in file system drives and ProcessInfo objects represent the processes on the computer.</span></span>

<span data-ttu-id="42600-110">オブジェクトには、オブジェクトに関するデータを格納するプロパティと、オブジェクトを変更するためのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="42600-110">Objects have properties, which store data about the object, and methods that let you change the object.</span></span>

<span data-ttu-id="42600-111">"メソッド" は、オブジェクトに対して実行できるアクションを指定する命令のセットです。</span><span class="sxs-lookup"><span data-stu-id="42600-111">A "method" is a set of instructions that specify an action you can perform on the object.</span></span> <span data-ttu-id="42600-112">たとえば、オブジェクトには、 `FileInfo` オブジェクトが表すファイルをコピーするメソッドが含まれてい `CopyTo` `FileInfo` ます。</span><span class="sxs-lookup"><span data-stu-id="42600-112">For example, the `FileInfo` object includes the `CopyTo` method that copies the file that the `FileInfo` object represents.</span></span>

<span data-ttu-id="42600-113">任意のオブジェクトのメソッドを取得するには、コマンドレットを使用し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="42600-113">To get the methods of any object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="42600-114">**MemberType** プロパティは、"Method" という値で使用します。</span><span class="sxs-lookup"><span data-stu-id="42600-114">Use its **MemberType** property with a value of "Method".</span></span> <span data-ttu-id="42600-115">次のコマンドは、プロセスオブジェクトのメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="42600-115">The following command gets the methods of process objects.</span></span>

```powershell
Get-Process | Get-Member -MemberType Method
```

```Output
TypeName: System.Diagnostics.Process

Name                      MemberType Definition
----                      ---------- ----------
BeginErrorReadLine        Method     System.Void BeginErrorReadLine()
BeginOutputReadLine       Method     System.Void BeginOutputReadLine()
...
Kill                      Method     System.Void Kill()
Refresh                   Method     System.Void Refresh()
Start                     Method     bool Start()
ToString                  Method     string ToString()
WaitForExit               Method     bool WaitForExit(int milliseconds), ...
WaitForInputIdle          Method     bool WaitForInputIdle(int millisecon...
```

<span data-ttu-id="42600-116">オブジェクトのメソッドを実行または "呼び出す" には、ドット (.)、メソッド名、および一連のかっこ "()" を入力します。</span><span class="sxs-lookup"><span data-stu-id="42600-116">To perform or "invoke" a method of an object, type a dot (.), the method name, and a set of parentheses "()".</span></span> <span data-ttu-id="42600-117">メソッドに引数がある場合は、引数の値をかっこ内に配置します。</span><span class="sxs-lookup"><span data-stu-id="42600-117">If the method has arguments, place the argument values inside the parentheses.</span></span> <span data-ttu-id="42600-118">引数がない場合でも、すべてのメソッド呼び出しにかっこが必要です。</span><span class="sxs-lookup"><span data-stu-id="42600-118">The parentheses are required for every method call, even when there are no arguments.</span></span> <span data-ttu-id="42600-119">メソッドが複数の引数を受け取る場合は、コンマで区切る必要があります。</span><span class="sxs-lookup"><span data-stu-id="42600-119">If the method takes multiple arguments, they should be separated by commas.</span></span>

<span data-ttu-id="42600-120">たとえば、次のコマンドは、プロセスの Kill メソッドを呼び出して、コンピューター上のメモ帳プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="42600-120">For example, the following command invokes the Kill method of processes to end the Notepad process on the computer.</span></span>

```powershell
$notepad = Get-Process notepad
$notepad.Kill()
```

<span data-ttu-id="42600-121">この例は、上記のステートメントを組み合わせることによって短縮できます。</span><span class="sxs-lookup"><span data-stu-id="42600-121">This example can be shortened by combining the above statements.</span></span>

```powershell
(Get-Process Notepad).Kill()
```

<span data-ttu-id="42600-122">コマンドは、 `Get-Process` Kill メソッドが呼び出される前に実行されるように、かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="42600-122">The `Get-Process` command is enclosed in parentheses to ensure that it runs before the Kill method is invoked.</span></span> <span data-ttu-id="42600-123">`Kill`次に、返されたオブジェクトに対してメソッドが呼び出され `Process` ます。</span><span class="sxs-lookup"><span data-stu-id="42600-123">The `Kill` method is then invoked on the returned `Process` object.</span></span>

<span data-ttu-id="42600-124">もう1つの便利な方法は、 `Replace` 文字列のメソッドです。</span><span class="sxs-lookup"><span data-stu-id="42600-124">Another very useful method is the `Replace` method of strings.</span></span> <span data-ttu-id="42600-125">`Replace`メソッドは、文字列内のテキストを置換します。</span><span class="sxs-lookup"><span data-stu-id="42600-125">The `Replace` method, replaces text within a string.</span></span> <span data-ttu-id="42600-126">次の例では、文字列の末尾の引用符の直後にドット (.) を配置できます。</span><span class="sxs-lookup"><span data-stu-id="42600-126">In the example below, the dot (.) can be placed immediately after the end quote of the string.</span></span>

```powershell
'this is rocket science'.Replace('rocket', 'rock')
```

```Output
this is rock science
```

<span data-ttu-id="42600-127">前の例で示したように、コマンド、変数内のオブジェクト、またはオブジェクト (引用符で囲まれた文字列など) を生成するすべてのオブジェクトに対して、メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="42600-127">As shown in the previous examples, you can invoke a method on an object that you get by using a command, an object in a variable, or anything that results in an object (like a string in quotes).</span></span>

<span data-ttu-id="42600-128">PowerShell 4.0 以降では、動的なメソッド名を使用したメソッド呼び出しがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="42600-128">Starting in PowerShell 4.0, method invocation by using dynamic method names is supported.</span></span>

### <a name="learning-about-methods"></a><span data-ttu-id="42600-129">メソッドについて学習する</span><span class="sxs-lookup"><span data-stu-id="42600-129">Learning about methods</span></span>

<span data-ttu-id="42600-130">オブジェクトのメソッドの定義を検索するには、MSDN でオブジェクトの種類のヘルプトピックにアクセスし、そのメソッドのページを探します。</span><span class="sxs-lookup"><span data-stu-id="42600-130">To find definitions of the methods of an object, go to help topic for the object type in MSDN and look for its methods page.</span></span> <span data-ttu-id="42600-131">たとえば、次のページでは、process オブジェクトのメソッドについて説明して[います。](/dotnet/api/system.diagnostics.process#methods)</span><span class="sxs-lookup"><span data-stu-id="42600-131">For example, the following page describes the methods of process objects [System.Diagnostics.Process](/dotnet/api/system.diagnostics.process#methods).</span></span>

<span data-ttu-id="42600-132">メソッドの引数を確認するには、メソッドの定義を確認します。これは、PowerShell コマンドレットの構文ダイアグラムに似ています。</span><span class="sxs-lookup"><span data-stu-id="42600-132">To determine the arguments of a method, review the method definition, which is like the syntax diagram of a PowerShell cmdlet.</span></span>

<span data-ttu-id="42600-133">メソッド定義には、PowerShell コマンドレットのパラメーターセットに似た1つ以上のメソッドシグネチャが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="42600-133">A method definition might have one or more method signatures, which are like the parameter sets of PowerShell cmdlets.</span></span> <span data-ttu-id="42600-134">シグネチャは、メソッドを呼び出すためのすべての有効な形式のコマンドを示しています。</span><span class="sxs-lookup"><span data-stu-id="42600-134">The signatures show all of the valid formats of commands to invoke the method.</span></span>

<span data-ttu-id="42600-135">たとえば、 `CopyTo` クラスのメソッドには、 `FileInfo` 次の2つのメソッドシグネチャが含まれています。</span><span class="sxs-lookup"><span data-stu-id="42600-135">For example, the `CopyTo` method of the `FileInfo` class contains the following two method signatures:</span></span>

```
    CopyTo(String destFileName)
    CopyTo(String destFileName, Boolean overwrite)
```

<span data-ttu-id="42600-136">最初のメソッドシグネチャは、コピー先のファイル名 (およびパス) を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="42600-136">The first method signature takes the destination file name (and a path).</span></span> <span data-ttu-id="42600-137">次の例では、最初のメソッドを使用して、 `CopyTo` `Final.txt` ファイルをディレクトリにコピーし `C:\Bin` ます。</span><span class="sxs-lookup"><span data-stu-id="42600-137">The following example uses the first `CopyTo` method to copy the `Final.txt` file to the `C:\Bin` directory.</span></span>

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt")
```

> [!NOTE]
> <span data-ttu-id="42600-138">PowerShell の _引数_ モードとは異なり、オブジェクトメソッドは、powershell が構築されている .net framework へのパススルーである _式_ モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="42600-138">Unlike PowerShell's _argument_ mode, object methods execute in _expression_ mode, which is a pass-through to the .NET framework that PowerShell is built on.</span></span> <span data-ttu-id="42600-139">_式_ モードでは、 **bareword** の引数 (引用符で囲まれていない文字列) は使用できません。</span><span class="sxs-lookup"><span data-stu-id="42600-139">In _expression_ mode **bareword** arguments (unquoted strings) are not allowed.</span></span> <span data-ttu-id="42600-140">パスをパラメーターとして使用する場合は、パスを引数として使用する場合に、この違いを確認できます。</span><span class="sxs-lookup"><span data-stu-id="42600-140">You can see this difference when using a the path as a parameter, versus the path as an argument.</span></span> <span data-ttu-id="42600-141">解析モードの詳細については、 [about_Parsing](about_Parsing.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42600-141">You can read more about parsing modes in [about_Parsing](about_Parsing.md)</span></span>

<span data-ttu-id="42600-142">2番目のメソッドシグネチャは、コピー先ファイル名と、コピー先ファイルが既に存在する場合に上書きするかどうかを決定するブール値を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="42600-142">The second method signature takes a destination file name and a Boolean value that determines whether the destination file should be overwritten, if it already exists.</span></span>

<span data-ttu-id="42600-143">次の例では、2番目のメソッドを使用して、 `CopyTo` `Final.txt` ファイルをディレクトリにコピーし、既存の `C:\Bin` ファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="42600-143">The following example uses the second `CopyTo` method to copy the `Final.txt` file to the `C:\Bin` directory, and to overwrite existing files.</span></span>

```powershell
(Get-ChildItem c:\final.txt).CopyTo("c:\bin\final.txt", $true)
```

### <a name="methods-of-scalar-objects-and-collections"></a><span data-ttu-id="42600-144">スカラーオブジェクトとコレクションのメソッド</span><span class="sxs-lookup"><span data-stu-id="42600-144">Methods of Scalar objects and Collections</span></span>

<span data-ttu-id="42600-145">特定の型の1つの ("スカラー") オブジェクトのメソッドは、多くの場合、同じ型のオブジェクトのコレクションのメソッドとは異なります。</span><span class="sxs-lookup"><span data-stu-id="42600-145">The methods of one ("scalar") object of a particular type are often different from the methods of a collection of objects of the same type.</span></span>

<span data-ttu-id="42600-146">たとえば、すべてのプロセスにメソッドがあり `Kill` ますが、プロセスのコレクションには Kill メソッドがありません。</span><span class="sxs-lookup"><span data-stu-id="42600-146">For example, every process has a `Kill` method, but a collection of processes does not have a Kill method.</span></span>

<span data-ttu-id="42600-147">PowerShell 3.0 以降、PowerShell は、スカラーオブジェクトとコレクションの異なるメソッドに起因するスクリプトエラーを防止しようとします。</span><span class="sxs-lookup"><span data-stu-id="42600-147">Beginning in PowerShell 3.0, PowerShell tries to prevent scripting errors that result from the differing methods of scalar objects and collections.</span></span>

<span data-ttu-id="42600-148">コレクションを送信するが、1つの ("スカラー") オブジェクトにのみ存在するメソッドを要求する場合、PowerShell はコレクション内のすべてのオブジェクトに対してメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="42600-148">If you submit a collection, but request a method that exists only on single ("scalar") objects, PowerShell invokes the method on every object in the collection.</span></span>

<span data-ttu-id="42600-149">メソッドが個別のオブジェクトとコレクションに存在する場合は、コレクションのメソッドだけが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="42600-149">If the method exists on the individual objects and on the collection, only the collection's method is invoked.</span></span>

<span data-ttu-id="42600-150">この機能は、スカラーオブジェクトおよびコレクションのプロパティにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="42600-150">This feature also works on properties of scalar objects and collections.</span></span> <span data-ttu-id="42600-151">詳細については、「 [about_Properties](about_Properties.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42600-151">For more information, see [about_Properties](about_Properties.md).</span></span>

### <a name="examples"></a><span data-ttu-id="42600-152">例</span><span class="sxs-lookup"><span data-stu-id="42600-152">Examples</span></span>

<span data-ttu-id="42600-153">次の例では、オブジェクトのコレクション内の個々のプロセスオブジェクトの **Kill** メソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="42600-153">The following example runs the **Kill** method of individual process objects in a collection of objects.</span></span>

<span data-ttu-id="42600-154">最初のコマンドは、メモ帳プロセスの3つのインスタンスを開始します。</span><span class="sxs-lookup"><span data-stu-id="42600-154">The first command starts three instances of the Notepad process.</span></span> <span data-ttu-id="42600-155">`Get-Process` メモ帳プロセスの3つのインスタンスをすべて取得し、変数に保存し `$p` ます。</span><span class="sxs-lookup"><span data-stu-id="42600-155">`Get-Process` gets all three instance of the Notepad process and saves them in the `$p` variable.</span></span>

```powershell
Notepad; Notepad; Notepad
$p = Get-Process Notepad
$p.Count
```

```Output
3
```

<span data-ttu-id="42600-156">次のコマンドは、変数内の3つのプロセスすべてで **Kill** メソッドを実行し `$p` ます。</span><span class="sxs-lookup"><span data-stu-id="42600-156">The next command runs the **Kill** method on all three processes in the `$p` variable.</span></span> <span data-ttu-id="42600-157">このコマンドは、プロセスのコレクションにメソッドがない場合でも機能 `Kill` します。</span><span class="sxs-lookup"><span data-stu-id="42600-157">This command works even though a collection of processes does not have a `Kill` method.</span></span>

```powershell
$p.Kill()
Get-Process Notepad
```

<span data-ttu-id="42600-158">コマンドは、 `Get-Process` メソッドが動作したことを確認し `Kill` ます。</span><span class="sxs-lookup"><span data-stu-id="42600-158">The `Get-Process` command confirms that the `Kill` method worked.</span></span>

```Output
Get-Process : Cannot find a process with the name "notepad". Verify the proc
ess name and call the cmdlet again.
At line:1 char:12
+ Get-Process <<<<  notepad
    + CategoryInfo          : ObjectNotFound: (notepad:String) [Get-Process]
, ProcessCommandException
    + FullyQualifiedErrorId : NoProcessFoundForGivenName,Microsoft.PowerShel
l.Commands.GetProcessCommand
```

<span data-ttu-id="42600-159">この例は機能的には、コマンドレットを使用して、 `Foreach-Object` コレクション内の各オブジェクトに対してメソッドを実行することと同じです。</span><span class="sxs-lookup"><span data-stu-id="42600-159">This example is functionally equivalent to using the `Foreach-Object` cmdlet to run the method on each object in the collection.</span></span>

```powershell
$p | ForEach-Object {$_.Kill()}
```

### <a name="foreach-and-where-methods"></a><span data-ttu-id="42600-160">ForEach および Where メソッド</span><span class="sxs-lookup"><span data-stu-id="42600-160">ForEach and Where methods</span></span>

<span data-ttu-id="42600-161">PowerShell 4.0 以降では、メソッド構文を使用したコレクションのフィルター処理がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="42600-161">Beginning in PowerShell 4.0, collection filtering by using a method syntax is supported.</span></span> <span data-ttu-id="42600-162">これにより、コレクションとを処理するときに、2つの新しいメソッドを使用できるように `ForEach` `Where` なります。</span><span class="sxs-lookup"><span data-stu-id="42600-162">This allows use of two new methods when dealing with collections `ForEach` and `Where`.</span></span>

<span data-ttu-id="42600-163">これらのメソッドの詳細については、「[about_arrays](about_arrays.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42600-163">You can read more about these methods in [about_arrays](about_arrays.md)</span></span>

### <a name="calling-a-specific-method-when-multiple-overloads-exist"></a><span data-ttu-id="42600-164">複数のオーバーロードが存在する場合の特定のメソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="42600-164">Calling a specific method when multiple overloads exist</span></span>

<span data-ttu-id="42600-165">.NET メソッドを呼び出すときは、次のシナリオを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="42600-165">Consider the following scenario when calling .NET methods.</span></span> <span data-ttu-id="42600-166">メソッドがオブジェクトを受け取り、より具体的な型を取得するインターフェイスを介してオーバーロードを持つ場合、PowerShell は、明示的にそのインターフェイスにキャストしない限り、オブジェクトを受け入れるメソッドを選択します。</span><span class="sxs-lookup"><span data-stu-id="42600-166">If a method takes an object but has an overload via an interface taking a more specific type, PowerShell chooses the method that accepts the object unless you explicitly cast it to that interface.</span></span>

```powershell
Add-Type -TypeDefinition @'

   // Interface
   public interface IFoo {
     string Bar(int p);
   }

   // Type that implements the interface
   public class Foo : IFoo {

   // Direct member method named 'Bar'
   public string Bar(object p) { return $"object: {p}"; }

   // *Explicit* implementation of IFoo's 'Bar' method().
   string IFoo.Bar(int p) {
       return $"int: {p}";
   }

}
'@
```

<span data-ttu-id="42600-167">この例では、 `object` **Bar** メソッドのより限定的なオーバーロードが選択されています。</span><span class="sxs-lookup"><span data-stu-id="42600-167">In this example the less specific `object` overload of the **Bar** method was chosen.</span></span>

```powershell
[Foo]::new().Bar(1)
```

```Output
object: 1
```

<span data-ttu-id="42600-168">この例では、メソッドをインターフェイス **IFoo** にキャストして、 **Bar** メソッドのより具体的なオーバーロードを選択します。</span><span class="sxs-lookup"><span data-stu-id="42600-168">In this example we cast the method to the interface **IFoo** to select the more specific overload of the **Bar** method.</span></span>

```powershell
([IFoo] [Foo]::new()).Bar(1)
```

```Output
int: 1
```

## <a name="see-also"></a><span data-ttu-id="42600-169">参照</span><span class="sxs-lookup"><span data-stu-id="42600-169">See Also</span></span>

[<span data-ttu-id="42600-170">about_Objects</span><span class="sxs-lookup"><span data-stu-id="42600-170">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="42600-171">about_Properties</span><span class="sxs-lookup"><span data-stu-id="42600-171">about_Properties</span></span>](about_Properties.md)

[<span data-ttu-id="42600-172">Get-Member</span><span class="sxs-lookup"><span data-stu-id="42600-172">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)
