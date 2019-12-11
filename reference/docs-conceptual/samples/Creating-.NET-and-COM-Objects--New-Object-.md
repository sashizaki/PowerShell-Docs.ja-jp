---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: .NET オブジェクトと COM オブジェクトを作成する (New-Object)
ms.openlocfilehash: 6e98a159451bc7da4ba3b37eaeb813eb71590d2b
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71325165"
---
# <a name="creating-net-and-com-objects-new-object"></a><span data-ttu-id="ddb9f-103">.NET オブジェクトと COM オブジェクトを作成する (New-Object)</span><span class="sxs-lookup"><span data-stu-id="ddb9f-103">Creating .NET and COM Objects (New-Object)</span></span>

<span data-ttu-id="ddb9f-104">ソフトウェア コンポーネントの中には、さまざまなシステム管理タスクを実行できるようにする .NET Framework や COM インターフェイスを備えているものがあります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-104">There are software components with .NET Framework and COM interfaces that enable you to perform many system administration tasks.</span></span> <span data-ttu-id="ddb9f-105">これらのコンポーネントは Windows PowerShell から使用することもでき、コマンドレットだけではできないタスクも実行できます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-105">Windows PowerShell lets you use these components, so you are not limited to the tasks that can be performed by using cmdlets.</span></span> <span data-ttu-id="ddb9f-106">Windows PowerShell の初回リリースでは、コマンドレットの多くがリモート コンピューターに対応していません。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-106">Many of the cmdlets in the initial release of Windows PowerShell do not work against remote computers.</span></span> <span data-ttu-id="ddb9f-107">ここでは、イベント ログを管理する場合に、.NET Framework の **System.Diagnostics.EventLog** クラスを Windows PowerShell から直接使用して、この制限を回避する方法を紹介します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-107">We will demonstrate how to get around this limitation when managing event logs by using the .NET Framework **System.Diagnostics.EventLog** class directly from Windows PowerShell.</span></span>

## <a name="using-new-object-for-event-log-access"></a><span data-ttu-id="ddb9f-108">New-Object によるイベント ログへのアクセス</span><span class="sxs-lookup"><span data-stu-id="ddb9f-108">Using New-Object for Event Log Access</span></span>

<span data-ttu-id="ddb9f-109">.NET Framework のクラス ライブラリには、イベント ログの管理に使用する **System.Diagnostics.EventLog** というクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-109">The .NET Framework Class Library includes a class named **System.Diagnostics.EventLog** that can be used to manage event logs.</span></span> <span data-ttu-id="ddb9f-110">.NET Framework クラスの新しいインスタンスを作成するには、**New-Object** コマンドレットと **TypeName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-110">You can create a new instance of a .NET Framework class by using the **New-Object** cmdlet with the **TypeName** parameter.</span></span> <span data-ttu-id="ddb9f-111">たとえば、次のコマンドを実行すると、イベント ログの参照が作成されます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-111">For example, the following command creates an event log reference:</span></span>

```
PS> New-Object -TypeName System.Diagnostics.EventLog

  Max(K) Retain OverflowAction        Entries Name
  ------ ------ --------------        ------- ----
```

<span data-ttu-id="ddb9f-112">このコマンドによって EventLog クラスのインスタンスは作成されましたが、このインスタンスにはデータがまったく含まれていません。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-112">Although the command has created an instance of the EventLog class, the instance does not include any data.</span></span> <span data-ttu-id="ddb9f-113">これは、特定のイベント ログを指定しなかったためです。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-113">That is because we did not specify a particular event log.</span></span> <span data-ttu-id="ddb9f-114">実際のイベント ログを取得するにはどうすればよいのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-114">How do you get a real event log?</span></span>

### <a name="using-constructors-with-new-object"></a><span data-ttu-id="ddb9f-115">New-Object でのコンストラクターの使用</span><span class="sxs-lookup"><span data-stu-id="ddb9f-115">Using Constructors with New-Object</span></span>

<span data-ttu-id="ddb9f-116">特定のイベント ログを参照するには、ログの名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-116">To refer to a specific event log, you need to specify the name of the log.</span></span> <span data-ttu-id="ddb9f-117">**New-Object** には、**ArgumentList** というパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-117">**New-Object** has an **ArgumentList** parameter.</span></span> <span data-ttu-id="ddb9f-118">このパラメーターの値として渡した引数は、オブジェクトの特殊な初期化メソッドで使用されます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-118">The arguments you pass as values to this parameter are used by a special startup method of the object.</span></span> <span data-ttu-id="ddb9f-119">オブジェクトを構築 (construct) する目的で使用されることから、このメソッドは*コンストラクター*と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-119">The method is called a *constructor* because it is used to construct the object.</span></span> <span data-ttu-id="ddb9f-120">たとえば、Application ログの参照を取得するには、"Application" という文字列を引数として指定します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-120">For example, to get a reference to the Application log, you specify the string 'Application' as an argument:</span></span>

```
PS> New-Object -TypeName System.Diagnostics.EventLog -ArgumentList Application

Max(K) Retain OverflowAction        Entries Name
------ ------ --------------        ------- ----
16,384      7 OverwriteOlder          2,160 Application
```

> [!NOTE]
> <span data-ttu-id="ddb9f-121">.NET Framework の中核となるクラスの大半は System 名前空間に存在するため、指定された型名が見つからなかった場合、Windows PowerShell は、そのクラスを自動的に System 名前空間から検索しようと試みます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-121">Since most of the .NET Framework core classes are contained in the System namespace, Windows PowerShell will automatically attempt to find classes you specify in the System namespace if it cannot find a match for the typename you specify.</span></span> <span data-ttu-id="ddb9f-122">したがって、「System.Diagnostics.EventLog」の部分は「Diagnostics.EventLog」と指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-122">This means that you can specify Diagnostics.EventLog instead of System.Diagnostics.EventLog.</span></span>

### <a name="storing-objects-in-variables"></a><span data-ttu-id="ddb9f-123">オブジェクトの変数への保存</span><span class="sxs-lookup"><span data-stu-id="ddb9f-123">Storing Objects in Variables</span></span>

<span data-ttu-id="ddb9f-124">オブジェクトの参照を保存し、それを現在のシェルで使用できます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-124">You might want to store a reference to an object, so you can use it in the current shell.</span></span> <span data-ttu-id="ddb9f-125">Windows PowerShell では多くの作業をパイプラインを使って実行できるため、変数を使用する機会はあまり多くありません。しかし、場合によっては、オブジェクトの参照を変数に格納した方が、オブジェクトを効率よく操作できることがあります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-125">Although Windows PowerShell lets you do a lot of work with pipelines, lessening the need for variables, sometimes storing references to objects in variables makes it more convenient to manipulate those objects.</span></span>

<span data-ttu-id="ddb9f-126">Windows PowerShell では、変数 (つまり、オブジェクトに名前を付けたもの) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-126">Windows PowerShell lets you create variables that are essentially named objects.</span></span> <span data-ttu-id="ddb9f-127">正しい Windows PowerShell コマンドであれば、その出力を変数に格納できます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-127">The output from any valid Windows PowerShell command can be stored in a variable.</span></span> <span data-ttu-id="ddb9f-128">変数名の先頭には、常に $ が付きます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-128">Variable names always begin with $.</span></span> <span data-ttu-id="ddb9f-129">Application ログの参照を変数 $AppLog に格納するには、この変数名の後に等号を入力し、続けて、Application ログ オブジェクトの作成に使用するコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-129">If you want to store the Application log reference in a variable named $AppLog, type the name of the variable, followed by an equal sign and then type the command used to create the Application log object:</span></span>

```
PS> $AppLog = New-Object -TypeName System.Diagnostics.EventLog -ArgumentList Application
```

<span data-ttu-id="ddb9f-130">その後、「$AppLog」と入力すると、Application ログが格納されていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-130">If you then type $AppLog, you can see that it contains the Application log:</span></span>

```
PS> $AppLog

  Max(K) Retain OverflowAction        Entries Name
  ------ ------ --------------        ------- ----
  16,384      7 OverwriteOlder          2,160 Application
```

### <a name="accessing-a-remote-event-log-with-new-object"></a><span data-ttu-id="ddb9f-131">New-Object によるリモートのイベント ログへのアクセス</span><span class="sxs-lookup"><span data-stu-id="ddb9f-131">Accessing a Remote Event Log with New-Object</span></span>

<span data-ttu-id="ddb9f-132">前のセクションで使用したコマンドは、アクセス先としてローカル コンピューターを想定していました。ローカル コンピューターのイベント ログを取得するのであれば、**Get-EventLog** コマンドレットを使って行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-132">The commands used in the preceding section target the local computer; the **Get-EventLog** cmdlet can do that.</span></span> <span data-ttu-id="ddb9f-133">リモート コンピューターの Application ログにアクセスするには、引数として、ログの名前とコンピューター名 (または IP アドレス) の両方を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-133">To access the Application log on a remote computer, you must supply both the log name and a computer name (or IP address) as arguments.</span></span>

```
PS> $RemoteAppLog = New-Object -TypeName System.Diagnostics.EventLog Application,192.168.1.81
PS> $RemoteAppLog

  Max(K) Retain OverflowAction        Entries Name
  ------ ------ --------------        ------- ----
     512      7 OverwriteOlder            262 Application
```

<span data-ttu-id="ddb9f-134">これで、イベント ログの参照が $RemoteAppLog 変数に格納されました。以降、この変数を使って、具体的にどのようなタスクを実行できるのかを説明します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-134">Now that we have a reference to an event log stored in the $RemoteAppLog variable, what tasks can we perform on it?</span></span>

### <a name="clearing-an-event-log-with-object-methods"></a><span data-ttu-id="ddb9f-135">オブジェクトのメソッドを使用したイベント ログのクリア</span><span class="sxs-lookup"><span data-stu-id="ddb9f-135">Clearing an Event Log with Object Methods</span></span>

<span data-ttu-id="ddb9f-136">多くの場合、オブジェクトには、特定のタスクを実行するときに呼び出すことのできるメソッドが存在します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-136">Objects often have methods that can be called to perform tasks.</span></span> <span data-ttu-id="ddb9f-137">**Get-Member** を使用すると、オブジェクトに関連付けられているメソッドを表示できます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-137">You can use **Get-Member** to display the methods associated with an object.</span></span> <span data-ttu-id="ddb9f-138">次の例は、EventLog クラスのメソッドを表示するコマンドと、その出力の抜粋です。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-138">The following command and selected output show some the methods of the EventLog class:</span></span>

```
PS> $RemoteAppLog | Get-Member -MemberType Method

   TypeName: System.Diagnostics.EventLog

Name                      MemberType Definition
----                      ---------- ----------
...
Clear                     Method     System.Void Clear()
Close                     Method     System.Void Close()
...
GetType                   Method     System.Type GetType()
...
ModifyOverflowPolicy      Method     System.Void ModifyOverflowPolicy(Overfl...
RegisterDisplayName       Method     System.Void RegisterDisplayName(String ...
...
ToString                  Method     System.String ToString()
WriteEntry                Method     System.Void WriteEntry(String message),...
WriteEvent                Method     System.Void WriteEvent(EventInstance in...
```

<span data-ttu-id="ddb9f-139">イベント ログをクリアするには、**Clear()** メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-139">The **Clear()** method can be used to clear the event log.</span></span> <span data-ttu-id="ddb9f-140">メソッドを呼び出すときは、引数が不要な場合でも、メソッド名の後に丸かっこを必ず入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-140">When calling a method, you must always follow the method name by parentheses, even if the method does not require arguments.</span></span> <span data-ttu-id="ddb9f-141">Windows PowerShell は、丸かっこの有無により、それがメソッド名なのか、同名のプロパティ名なのかを判断します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-141">This lets Windows PowerShell distinguish between the method and a potential property with the same name.</span></span> <span data-ttu-id="ddb9f-142">**Clear** メソッドを呼び出すには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-142">Type the following to call the **Clear** method:</span></span>

```
PS> $RemoteAppLog.Clear()
```

<span data-ttu-id="ddb9f-143">ログを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-143">Type the following to display the log.</span></span> <span data-ttu-id="ddb9f-144">イベント ログがクリアされ、エントリ数が 262 から 0 に変わっていることが確認できます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-144">You will see that the event log was cleared, and now has 0 entries instead of 262:</span></span>

```
PS> $RemoteAppLog

  Max(K) Retain OverflowAction        Entries Name
  ------ ------ --------------        ------- ----
     512      7 OverwriteOlder              0 Application
```

## <a name="creating-com-objects-with-new-object"></a><span data-ttu-id="ddb9f-145">New-Object による COM オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="ddb9f-145">Creating COM Objects with New-Object</span></span>
<span data-ttu-id="ddb9f-146">コンポーネント オブジェクト モデル (COM) のコンポーネントを操作するには、**New-Object** を使用します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-146">You can use **New-Object** to work with Component Object Model (COM) components.</span></span> <span data-ttu-id="ddb9f-147">一口にコンポーネントと言っても、その種類は Windows Script Host (WSH) に含まれている各種ライブラリから、Internet Explorer のようなほとんどのシステムにインストールされている ActiveX アプリケーションまで多岐にわたります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-147">Components range from the various libraries included with Windows Script Host (WSH) to ActiveX applications such as Internet Explorer that are installed on most systems.</span></span>

<span data-ttu-id="ddb9f-148">**New-Object** では、.NET Framework ランタイム呼び出し可能ラッパーを使って COM オブジェクトを作成します。したがって、COM オブジェクトを呼び出す際には .NET Framework の場合と同じ制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-148">**New-Object** uses .NET Framework Runtime-Callable Wrappers to create COM objects, so it has the same limitations that .NET Framework does when calling COM objects.</span></span> <span data-ttu-id="ddb9f-149">COM オブジェクトを作成するには、使用する COM クラスのプログラム識別子 (*ProgId*) を **ComObject** パラメーターで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-149">To create a COM object, you need to specify the **ComObject** parameter with the Programmatic Identifier or *ProgId* of the COM class you want to use.</span></span> <span data-ttu-id="ddb9f-150">COM の使用上の制限や、システム上で利用できる ProgId の調査方法については、このマニュアルの範囲を超えているので詳しく説明しません。しかし、WSH などの環境に存在する、一般によく知られているようなオブジェクトについては、Windows PowerShell 内で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-150">A complete discussion of the limitations of COM use and determining what ProgIds are available on a system is beyond the scope of this user's guide, but most well-known objects from environments such as WSH can be used within Windows PowerShell.</span></span>

<span data-ttu-id="ddb9f-151">次の ProgID を指定することで、WSH オブジェクトを作成できます:**WScript.Shell**、**WScript.Network**、**Scripting.Dictionary**、および **Scripting.FileSystemObject**。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-151">You can create the WSH objects by specifying these progids: **WScript.Shell**, **WScript.Network**, **Scripting.Dictionary**, and **Scripting.FileSystemObject**.</span></span> <span data-ttu-id="ddb9f-152">これらのオブジェクトを作成するコマンドの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-152">The following commands create these objects:</span></span>

```powershell
New-Object -ComObject WScript.Shell
New-Object -ComObject WScript.Network
New-Object -ComObject Scripting.Dictionary
New-Object -ComObject Scripting.FileSystemObject
```

<span data-ttu-id="ddb9f-153">これらのクラスの機能は、その多くが、Windows PowerShell から他の方法を使ってアクセスすることもできます。ただし、ショートカットの作成など、一部のタスクについては、WSH のクラスを使用した方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-153">Although most of the functionality of these classes is made available in other ways in Windows PowerShell, a few tasks such as shortcut creation are still easier to do using the WSH classes.</span></span>

## <a name="creating-a-desktop-shortcut-with-wscriptshell"></a><span data-ttu-id="ddb9f-154">WScript.Shell によるデスクトップ ショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="ddb9f-154">Creating a Desktop Shortcut with WScript.Shell</span></span>

<span data-ttu-id="ddb9f-155">COM オブジェクトの使用が適しているタスクの 1 つに、ショートカットの作成があります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-155">One task that can be performed quickly with a COM object is creating a shortcut.</span></span> <span data-ttu-id="ddb9f-156">Windows PowerShell のホーム フォルダーに対するショートカットをデスクトップ上に作成するとします。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-156">Suppose you want to create a shortcut on your desktop that links to the home folder for Windows PowerShell.</span></span> <span data-ttu-id="ddb9f-157">まず必要なことは、**WScript.Shell** の参照を作成することです。ここでは、この参照を **$WshShell** という変数に格納することにします。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-157">You first need to create a reference to **WScript.Shell**, which we will store in a variable named **$WshShell**:</span></span>

```powershell
$WshShell = New-Object -ComObject WScript.Shell
```

<span data-ttu-id="ddb9f-158">Get-Member は COM オブジェクトに対応しているため、次のように入力することで、オブジェクトのメンバーを調査できます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-158">Get-Member works with COM objects, so you can explore the members of the object by typing:</span></span>

```
PS> $WshShell | Get-Member

   TypeName: System.__ComObject#{41904400-be18-11d3-a28b-00104bd35090}

Name                     MemberType            Definition
----                     ----------            ----------
AppActivate              Method                bool AppActivate (Variant, Va...
CreateShortcut           Method                IDispatch CreateShortcut (str...
...
```

<span data-ttu-id="ddb9f-159">**Get-Member** には、省略可能なパラメーター **InputObject** があります。**Get-Member** に対する入力をパイプで渡す代わりに、このパラメーターを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-159">**Get-Member** has an optional **InputObject** parameter you can use instead of piping to provide input to **Get-Member**.</span></span> <span data-ttu-id="ddb9f-160">**Get-Member -InputObject $WshShell** コマンドを使用しても表示される出力結果は同じです。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-160">You would get the same output as shown above if you instead used the command **Get-Member -InputObject $WshShell**.</span></span> <span data-ttu-id="ddb9f-161">**InputObject** を使用した場合、その引数は単一の項目として扱われます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-161">If you use **InputObject**, it treats its argument as a single item.</span></span> <span data-ttu-id="ddb9f-162">つまり、1 つの変数に複数のオブジェクトが格納されている場合、**Get-Member** では、それらはオブジェクトの配列として扱われます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-162">This means that if you have several objects in a variable, **Get-Member** treats them as an array of objects.</span></span> <span data-ttu-id="ddb9f-163">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-163">For example:</span></span>

```
PS> $a = 1,2,"three"
PS> Get-Member -InputObject $a
TypeName: System.Object[]
Name               MemberType    Definition
----               ----------    ----------
Count              AliasProperty Count = Length
...
```

<span data-ttu-id="ddb9f-164">**WScript.Shell CreateShortcut** メソッドは、作成するショートカット ファイルのパスのみを引数として受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-164">The **WScript.Shell CreateShortcut** method accepts a single argument, the path to the shortcut file to create.</span></span> <span data-ttu-id="ddb9f-165">デスクトップへのフル パスを入力することもできますが、より簡単な方法があります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-165">We could type in the full path to the desktop, but there is an easier way.</span></span> <span data-ttu-id="ddb9f-166">通常、デスクトップは、現在のユーザーのホーム フォルダーにある "デスクトップ" というフォルダー名で表されます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-166">The desktop is normally represented by a folder named Desktop inside the home folder of the current user.</span></span> <span data-ttu-id="ddb9f-167">Windows PowerShell には、このフォルダーへのパスを保持する **$Home** という変数が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-167">Windows PowerShell has a variable **$Home** that contains the path to this folder.</span></span> <span data-ttu-id="ddb9f-168">この変数を使ってホーム フォルダーのパスを指定し、続けて、デスクトップ フォルダーの名前と、作成するショートカットの名前を追加します。次にその例を示します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-168">We can specify the path to the home folder by using this variable, and then add the name of the Desktop folder and the name for the shortcut to create by typing:</span></span>

```powershell
$lnk = $WshShell.CreateShortcut("$Home\Desktop\PSHome.lnk")
```

<span data-ttu-id="ddb9f-169">変数名と思われる情報が二重引用符内に存在した場合、Windows PowerShell は、それを対応する値に置き換えようと試みます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-169">When you use something that looks like a variable name inside double-quotes, Windows PowerShell tries to substitute a matching value.</span></span> <span data-ttu-id="ddb9f-170">一重引用符を使用した場合、変数値の置き換えは行われません。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-170">If you use single-quotes, Windows PowerShell does not try to substitute the variable value.</span></span> <span data-ttu-id="ddb9f-171">たとえば、次のコマンドを入力してみてください。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-171">For example, try typing the following commands:</span></span>

```
PS> "$Home\Desktop\PSHome.lnk"
C:\Documents and Settings\aka\Desktop\PSHome.lnk
PS> '$Home\Desktop\PSHome.lnk'
$Home\Desktop\PSHome.lnk
```

<span data-ttu-id="ddb9f-172">**$lnk** という変数には、現在、新しいショートカットの参照が格納されています。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-172">We now have a variable named **$lnk** that contains a new shortcut reference.</span></span> <span data-ttu-id="ddb9f-173">メンバーを表示するには、この変数をパイプを使って **Get-Member** に渡します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-173">If you want to see its members, you can pipe it to **Get-Member**.</span></span> <span data-ttu-id="ddb9f-174">次のように、ショートカットを完成するために必要なメンバーが出力結果として表示されます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-174">The output below shows the members we need to use to finish creating our shortcut:</span></span>

```
PS> $lnk | Get-Member
TypeName: System.__ComObject#{f935dc23-1cf0-11d0-adb9-00c04fd58a0b}
Name             MemberType   Definition
----             ----------   ----------
...
Save             Method       void Save ()
...
TargetPath       Property     string TargetPath () {get} {set}
```

<span data-ttu-id="ddb9f-175">**TargetPath** (Windows PowerShell のアプリケーション フォルダー) を指定した後、**Save** メソッドを呼び出してショートカット **$lnk** を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-175">We need to specify the **TargetPath**, which is the application folder for Windows PowerShell, and then save the shortcut **$lnk** by calling the **Save** method.</span></span> <span data-ttu-id="ddb9f-176">Windows PowerShell のアプリケーション フォルダーのパスは変数 **$PSHome** に保存されているため、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-176">The Windows PowerShell application folder path is stored in the variable **$PSHome**, so we can do this by typing:</span></span>

```powershell
$lnk.TargetPath = $PSHome
$lnk.Save()
```

## <a name="using-internet-explorer-from-windows-powershell"></a><span data-ttu-id="ddb9f-177">Windows PowerShell からの Internet Explorer の使用</span><span class="sxs-lookup"><span data-stu-id="ddb9f-177">Using Internet Explorer from Windows PowerShell</span></span>

<span data-ttu-id="ddb9f-178">Microsoft Office ファミリのアプリケーションや Internet Explorer など、多くのアプリケーションは COM を使用して自動化できます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-178">Many applications (including the Microsoft Office family of applications and Internet Explorer) can be automated by using COM.</span></span> <span data-ttu-id="ddb9f-179">COM ベースのアプリケーション操作に関係する一般的なテクニックと問題点を、Internet Explorer を例に取り上げます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-179">Internet Explorer illustrates some of the typical techniques and issues involved in working with COM-based applications.</span></span>

<span data-ttu-id="ddb9f-180">Internet Explorer のインスタンスを作成するには、次のように、Internet Explorer の ProgId として **InternetExplorer.Application** を指定します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-180">You create an Internet Explorer instance by specifying the Internet Explorer ProgId, **InternetExplorer.Application**:</span></span>

```powershell
$ie = New-Object -ComObject InternetExplorer.Application
```

<span data-ttu-id="ddb9f-181">このコマンドでは、Internet Explorer は起動しますが、表示はされません。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-181">This command starts Internet Explorer, but does not make it visible.</span></span> <span data-ttu-id="ddb9f-182">「Get-Process」と入力すると、iexplore という名前のプロセスが実行されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-182">If you type Get-Process, you can see that a process named iexplore is running.</span></span> <span data-ttu-id="ddb9f-183">実際、Windows PowerShell を終了しても、このプロセスは実行されたままです。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-183">In fact, if you exit Windows PowerShell, the process will continue to run.</span></span> <span data-ttu-id="ddb9f-184">iexplore プロセスを終了するには、コンピューターを再起動するか、またはタスク マネージャーなどのツールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-184">You must reboot the computer or use a tool like Task Manager to end the iexplore process.</span></span>

> [!NOTE]
> <span data-ttu-id="ddb9f-185">独立したプロセスとして起動する COM オブジェクトは、一般に *ActiveX 実行可能ファイル*と呼ばれ、起動時にユーザー インターフェイス ウィンドウを表示するものと、表示しないものが存在します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-185">COM objects that start as separate processes, commonly called *ActiveX executables*, may or may not display a user interface window when they start up.</span></span> <span data-ttu-id="ddb9f-186">Internet Explorer のように、ウィンドウは作成されても、表示状態にはしない COM オブジェクトの場合、フォーカスが Windows デスクトップに移されることが多く、ユーザーが操作できるようにするためには、ウィンドウを表示状態にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-186">If they create a window but do not make it visible, like Internet Explorer, the focus will generally move to the Windows desktop and you must make the window visible to interact with it.</span></span>

<span data-ttu-id="ddb9f-187">**$ie | Get-Member** と入力すると、Internet Explorer のプロパティおよびメソッドを表示できます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-187">By typing **$ie | Get-Member**, you can view properties and methods for Internet Explorer.</span></span> <span data-ttu-id="ddb9f-188">Internet Explorer ウィンドウを表示するには、次のように、Visible プロパティを $true に設定します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-188">To see the Internet Explorer window, set the Visible property to $true by typing:</span></span>

```powershell
$ie.Visible = $true
```

<span data-ttu-id="ddb9f-189">次に、Navigate メソッドを使用すると、特定の Web アドレスに移動できます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-189">You can then navigate to a specific Web address by using the Navigate method:</span></span>

```powershell
$ie.Navigate("https://devblogs.microsoft.com/scripting/")
```

<span data-ttu-id="ddb9f-190">Internet Explorer オブジェクト モデルの他のメンバーを使用すると、この Web ページからテキストの内容を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-190">Using other members of the Internet Explorer object model, it is possible to retrieve text content from the Web page.</span></span> <span data-ttu-id="ddb9f-191">次のコマンドを実行すると、現在の Web ページの本文に含まれる HTML テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-191">The following command will display the HTML text in the body of the current Web page:</span></span>

```powershell
$ie.Document.Body.InnerText
```

<span data-ttu-id="ddb9f-192">Internet Explorer を PowerShell 内から終了するには、Quit() メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-192">To close Internet Explorer from within PowerShell, call its Quit() method:</span></span>

```powershell
$ie.Quit()
```

<span data-ttu-id="ddb9f-193">この場合、アプリケーションは強制的に終了されます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-193">This will force it to close.</span></span> <span data-ttu-id="ddb9f-194">一見すると、まだ COM オブジェクトが有効であるかのように見えますが、この時点で、$ie 変数には正しい参照が存在しません。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-194">The $ie variable no longer contains a valid reference even though it still appears to be a COM object.</span></span> <span data-ttu-id="ddb9f-195">使用を試みると、オートメーション エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-195">If you attempt to use it, you will get an automation error:</span></span>

```
PS> $ie | Get-Member
Get-Member : Exception retrieving the string representation for property "Appli
cation" : "The object invoked has disconnected from its clients. (Exception fro
m HRESULT: 0x80010108 (RPC_E_DISCONNECTED))"
At line:1 char:16
+ $ie | Get-Member <<<<
```

<span data-ttu-id="ddb9f-196">コマンド "$ie = $null" などのような形で残っている参照を削除することも、次のように入力して変数を完全に削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-196">You can either remove the remaining reference with a command like $ie = $null, or completely remove the variable by typing:</span></span>

```powershell
Remove-Variable ie
```

> [!NOTE]
> <span data-ttu-id="ddb9f-197">参照を削除したときに、ActiveX 実行可能ファイルを終了するか、実行を継続するかに関して、共通の標準は存在しません。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-197">There is no common standard for whether ActiveX executables exit or continue to run when you remove a reference to one.</span></span> <span data-ttu-id="ddb9f-198">アプリケーションが終了するかどうかは、アプリケーションが可視状態であるか、編集中のドキュメントが存在するか、Windows PowerShell がまだ実行されているかなど、さまざまな条件に依存します。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-198">Depending on circumstances such as whether the application is visible, whether an edited document is running in it, and even whether Windows PowerShell is still running, the application may or may not exit.</span></span> <span data-ttu-id="ddb9f-199">そのため、Windows PowerShell で使用する ActiveX 実行可能ファイルごとに、終了時の動作をテストしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-199">For this reason, you should test termination behavior for each ActiveX executable you want to use in Windows PowerShell.</span></span>

## <a name="getting-warnings-about-net-framework-wrapped-com-objects"></a><span data-ttu-id="ddb9f-200">.NET Framework によってラップされた COM オブジェクトの警告の取得</span><span class="sxs-lookup"><span data-stu-id="ddb9f-200">Getting Warnings About .NET Framework-Wrapped COM Objects</span></span>

<span data-ttu-id="ddb9f-201">COM オブジェクトに、.NET Framework *ランタイム呼び出し可能ラッパー* (RCW) が関連付けられていて、これが **New-Object** で使用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-201">In some cases, a COM object might have an associated .NET Framework *Runtime-Callable Wrapper* or RCW, and this will be used by **New-Object**.</span></span> <span data-ttu-id="ddb9f-202">RCW の動作は通常の COM オブジェクトの動作とは異なる場合があるため、**New-Object** には、RCW アクセスに関する警告を取得する **Strict** パラメーターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-202">Since the behavior of the RCW may be different from the behavior of the normal COM object, **New-Object** has a **Strict** parameter to warn you about RCW access.</span></span> <span data-ttu-id="ddb9f-203">**Strict** パラメーターを指定し、RCW を使用する COM オブジェクトを作成した場合、次のような警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-203">If you specify the **Strict** parameter and then create a COM object that uses an RCW, you get a warning message:</span></span>

```
PS> $xl = New-Object -ComObject Excel.Application -Strict
New-Object : The object written to the pipeline is an instance of the type "Mic
rosoft.Office.Interop.Excel.ApplicationClass" from the component's primary inte
rop assembly. If this type exposes different members than the IDispatch members
, scripts written to work with this object might not work if the primary intero
p assembly is not installed.
At line:1 char:17
+ $xl = New-Object  <<<< -ComObject Excel.Application -Strict
```

<span data-ttu-id="ddb9f-204">オブジェクトは作成されますが、標準の COM オブジェクトではないことを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ddb9f-204">Although the object is still created, you are warned that it is not a standard COM object.</span></span>
