---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 05/06/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-member?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Member
ms.openlocfilehash: 290d19cb2bf04e22bf7855cb88467ed26ad42fe7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213963"
---
# <span data-ttu-id="65234-103">Get-Member</span><span class="sxs-lookup"><span data-stu-id="65234-103">Get-Member</span></span>

## <span data-ttu-id="65234-104">概要</span><span class="sxs-lookup"><span data-stu-id="65234-104">SYNOPSIS</span></span>
<span data-ttu-id="65234-105">オブジェクトのプロパティとメソッドを取得します。</span><span class="sxs-lookup"><span data-stu-id="65234-105">Gets the properties and methods of objects.</span></span>

## <span data-ttu-id="65234-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="65234-106">SYNTAX</span></span>

```
Get-Member [-InputObject <PSObject>] [[-Name] <String[]>] [-MemberType <PSMemberTypes>]
 [-View <PSMemberViewTypes>] [-Static] [-Force] [<CommonParameters>]
```

## <span data-ttu-id="65234-107">Description</span><span class="sxs-lookup"><span data-stu-id="65234-107">DESCRIPTION</span></span>

<span data-ttu-id="65234-108">`Get-Member`コマンドレットは、オブジェクトのメンバー (プロパティとメソッド) を取得します。</span><span class="sxs-lookup"><span data-stu-id="65234-108">The `Get-Member` cmdlet gets the members, the properties and methods, of objects.</span></span>

<span data-ttu-id="65234-109">オブジェクトを指定するには、 **InputObject** パラメーターを使用するか、にオブジェクトをパイプ処理 `Get-Member` します。</span><span class="sxs-lookup"><span data-stu-id="65234-109">To specify the object, use the **InputObject** parameter or pipe an object to `Get-Member`.</span></span> <span data-ttu-id="65234-110">静的メンバー (インスタンスではなく、クラスのメンバー) に関する情報を取得するには、 **static** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="65234-110">To get information about static members, the members of the class, not of the instance, use the **Static** parameter.</span></span> <span data-ttu-id="65234-111">**MemberType** **パラメーターなど、** 特定の種類のメンバーだけを取得するには、を使用します。</span><span class="sxs-lookup"><span data-stu-id="65234-111">To get only certain types of members, such as **NoteProperties** , use the **MemberType** parameter.</span></span>

## <span data-ttu-id="65234-112">例</span><span class="sxs-lookup"><span data-stu-id="65234-112">EXAMPLES</span></span>

### <span data-ttu-id="65234-113">例 1: プロセスオブジェクトのメンバーを取得する</span><span class="sxs-lookup"><span data-stu-id="65234-113">Example 1: Get the members of process objects</span></span>

<span data-ttu-id="65234-114">このコマンドは、コマンドレットによって生成されるサービスオブジェクトのプロパティとメソッドを表示し `Get-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="65234-114">This command displays the properties and methods of the service objects generated by the `Get-Service` cmdlet.</span></span>

<span data-ttu-id="65234-115">`Get-Member`コマンドの部分にはパラメーターがないため、パラメーターには既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="65234-115">Because the `Get-Member` part of the command does not have any parameters, it uses default values for the parameters.</span></span> <span data-ttu-id="65234-116">既定では、は `Get-Member` 静的または組み込みのメンバーを取得しません。</span><span class="sxs-lookup"><span data-stu-id="65234-116">By default, `Get-Member` does not get static or intrinsic members.</span></span>

```powershell
Get-Service | Get-Member
```

```Output
   TypeName: System.ServiceProcess.ServiceController

Name                      MemberType    Definition
----                      ----------    ----------
Name                      AliasProperty Name = ServiceName
RequiredServices          AliasProperty RequiredServices = ServicesDependedOn
Disposed                  Event         System.EventHandler Disposed(System.Object, System.EventArgs)
Close                     Method        void Close()
Continue                  Method        void Continue()
CreateObjRef              Method        System.Runtime.Remoting.ObjRef CreateObjRef(type requestedType)
Dispose                   Method        void Dispose(), void IDisposable.Dispose()
Equals                    Method        bool Equals(System.Object obj)
ExecuteCommand            Method        void ExecuteCommand(int command)
GetHashCode               Method        int GetHashCode()
GetLifetimeService        Method        System.Object GetLifetimeService()
GetType                   Method        type GetType()
InitializeLifetimeService Method        System.Object InitializeLifetimeService()
Pause                     Method        void Pause()
Refresh                   Method        void Refresh()
Start                     Method        void Start(), void Start(string[] args)
Stop                      Method        void Stop()
WaitForStatus             Method        void WaitForStatus(System.ServiceProcess.ServiceControllerSt...
CanPauseAndContinue       Property      bool CanPauseAndContinue {get;}
CanShutdown               Property      bool CanShutdown {get;}
CanStop                   Property      bool CanStop {get;}
Container                 Property      System.ComponentModel.IContainer Container {get;}
DependentServices         Property      System.ServiceProcess.ServiceController[] DependentServices {get;}
DisplayName               Property      string DisplayName {get;set;}
MachineName               Property      string MachineName {get;set;}
ServiceHandle             Property      System.Runtime.InteropServices.SafeHandle ServiceHandle {get;}
ServiceName               Property      string ServiceName {get;set;}
ServicesDependedOn        Property      System.ServiceProcess.ServiceController[] ServicesDependedOn {get;}
ServiceType               Property      System.ServiceProcess.ServiceType ServiceType {get;}
Site                      Property      System.ComponentModel.ISite Site {get;set;}
StartType                 Property      System.ServiceProcess.ServiceStartMode StartType {get;}
Status                    Property      System.ServiceProcess.ServiceControllerStatus Status {get;}
ToString                  ScriptMethod  System.Object ToString();
```

### <span data-ttu-id="65234-117">例 2: サービスオブジェクトのメンバーを取得する</span><span class="sxs-lookup"><span data-stu-id="65234-117">Example 2: Get members of service objects</span></span>

<span data-ttu-id="65234-118">この例では、コマンドレットによって取得されたサービスオブジェクトのすべてのメンバー (プロパティとメソッド) を取得し `Get-Service` ます。これには、 **psbase** 、 **PSObject** 、 **get_** および **set_** メソッドなどの組み込みメンバーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="65234-118">This example gets all of the members (properties and methods) of the service objects retrieved by the `Get-Service` cmdlet, including the intrinsic members, such as **PSBase** , **PSObject** , and the **get_** and **set_** methods.</span></span>

```powershell
Get-Service | Get-Member -Force
(Get-Service Schedule).PSBase
```

<span data-ttu-id="65234-119">この `Get-Member` コマンドは、 **Force** パラメーターを使用して、オブジェクトの組み込みメンバーとコンパイラによって生成されたメンバーを表示に追加します。</span><span class="sxs-lookup"><span data-stu-id="65234-119">The `Get-Member` command uses the **Force** parameter to add the intrinsic members and compiler-generated members of the objects to the display.</span></span> <span data-ttu-id="65234-120">これらのプロパティとメソッドは、オブジェクトのアダプター適用対象のメソッドを使用する場合と同じ方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="65234-120">You can use these properties and methods in the same way that you would use an adapted method of the object.</span></span> <span data-ttu-id="65234-121">2 番目のコマンドは、Schedule サービスの PSBase プロパティの値を表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="65234-121">The second command shows how to display the value of the PSBase property of the Schedule service.</span></span>

### <span data-ttu-id="65234-122">例 3: サービスオブジェクトの拡張メンバーを取得する</span><span class="sxs-lookup"><span data-stu-id="65234-122">Example 3: Get extended members of service objects</span></span>

<span data-ttu-id="65234-123">この例で `Types.ps1xml` は、ファイルまたはコマンドレットを使用して拡張されたサービスオブジェクトのメソッドとプロパティを取得し `Add-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="65234-123">This example gets the methods and properties of service objects that were extended by using a `Types.ps1xml` file or the `Add-Member` cmdlet.</span></span>

```powershell
Get-Service | Get-Member -View Extended
```

```Output
   TypeName: System.ServiceProcess.ServiceController

Name             MemberType    Definition
----             ----------    ----------
Name             AliasProperty Name = ServiceName
RequiredServices AliasProperty RequiredServices = ServicesDependedOn
ToString         ScriptMethod  System.Object ToString();
```

<span data-ttu-id="65234-124">この `Get-Member` コマンドは、 **View** パラメーターを使用して、サービスオブジェクトの拡張されたメンバーのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="65234-124">The `Get-Member` command uses the **View** parameter to get only the extended members of the service objects.</span></span> <span data-ttu-id="65234-125">この場合、拡張メンバーは、 **ServiceName** プロパティの alias プロパティである **Name** プロパティです。</span><span class="sxs-lookup"><span data-stu-id="65234-125">In this case, the extended member is the **Name** property, which is an alias property of the **ServiceName** property.</span></span>

### <span data-ttu-id="65234-126">例 4: イベントログオブジェクトのスクリプトプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="65234-126">Example 4: Get script properties of event log objects</span></span>

<span data-ttu-id="65234-127">この例では、イベントビューアーのシステムログにあるイベントログオブジェクトのスクリプトプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="65234-127">This example gets the script properties of event log objects in the System log in Event Viewer.</span></span>

```powershell
Get-WinEvent -LogName System -MaxEvents 1 | Get-Member -MemberType NoteProperty
```

```Output
   TypeName: System.Diagnostics.Eventing.Reader.EventLogRecord

Name    MemberType   Definition
----    ----------   ----------
Message NoteProperty string Message=The machine-default permission settings do not grant Local ...
```

<span data-ttu-id="65234-128">**MemberType** パラメーターは、 `NoteProperty` **MemberType** プロパティの値がであるオブジェクトのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="65234-128">The **MemberType** parameter gets only objects with a value of `NoteProperty` for their **MemberType** property.</span></span>

<span data-ttu-id="65234-129">このコマンドは、 **EventLogRecord** オブジェクトの **Message** プロパティを返します。</span><span class="sxs-lookup"><span data-stu-id="65234-129">The command returns the **Message** property of the **EventLogRecord** object.</span></span>

### <span data-ttu-id="65234-130">例 5: 指定したプロパティを使用してオブジェクトを取得する</span><span class="sxs-lookup"><span data-stu-id="65234-130">Example 5: Get objects with a specified property</span></span>

<span data-ttu-id="65234-131">この例では、コマンドレットの一覧から出力に **MachineName** プロパティを持つオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="65234-131">This example gets objects that have a **MachineName** property in the output from a list of cmdlets.</span></span>

<span data-ttu-id="65234-132">変数には、 `$list` 評価対象のコマンドレットの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="65234-132">The `$list` variable contains a list of cmdlets to be evaluated.</span></span> <span data-ttu-id="65234-133">**Foreach** ステートメントは各コマンドを呼び出し、結果をに送信し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="65234-133">The **foreach** statement invokes each command and sends the results to `Get-Member`.</span></span> <span data-ttu-id="65234-134">**Name** パラメーターを指定すると、の結果は `Get-Member` **MachineName** という名前のメンバーに制限されます。</span><span class="sxs-lookup"><span data-stu-id="65234-134">The **Name** parameter limits the results from `Get-Member` to members that have the name **MachineName** .</span></span>

```powershell
$list = "Get-Process", "Get-Service", "Get-Culture", "Get-PSDrive", "Get-ExecutionPolicy"
foreach ($cmdlet in $list) {& $cmdlet | Get-Member -Name MachineName}
```

```Output
   TypeName: System.Diagnostics.Process

Name        MemberType Definition
----        ---------- ----------
MachineName Property   string MachineName {get;}

   TypeName: System.ServiceProcess.ServiceController

Name        MemberType Definition
----        ---------- ----------
MachineName Property   string MachineName {get;set;}
```

<span data-ttu-id="65234-135">結果には、プロセスオブジェクトとサービスオブジェクトのみが **MachineName** プロパティを持つことが示されています。</span><span class="sxs-lookup"><span data-stu-id="65234-135">The results show that only process objects and service objects have a **MachineName** property.</span></span>

### <span data-ttu-id="65234-136">例 6: 配列のメンバーを取得する</span><span class="sxs-lookup"><span data-stu-id="65234-136">Example 6: Get members for an array</span></span>

<span data-ttu-id="65234-137">この例では、オブジェクトの配列のメンバーを検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="65234-137">This example demonstrates how to find the members of an array of objects.</span></span> <span data-ttu-id="65234-138">パイプを使用してオブジェクトの配列をに渡した場合 `Get-Member` 、コマンドレットは、配列内の一意のオブジェクト型ごとにメンバーリストを返します。</span><span class="sxs-lookup"><span data-stu-id="65234-138">When you pipe and array of objects to `Get-Member`, the cmdlet returns a member list for each unique object type in the array.</span></span>
<span data-ttu-id="65234-139">**InputObject** パラメーターを使用して配列を渡すと、配列は単一のオブジェクトとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="65234-139">If you pass the array using the **InputObject** parameter, the array is treated as a single object.</span></span>

```powershell
$array = @(1,'hello')
$array | Get-Member
```

```Output
   TypeName: System.Int32

Name        MemberType Definition
----        ---------- ----------
CompareTo   Method     int CompareTo(System.Object value), int CompareTo(int value), int ICompar...
Equals      Method     bool Equals(System.Object obj), bool Equals(int obj), bool IEquatable[int...
GetHashCode Method     int GetHashCode()
GetType     Method     type GetType()
GetTypeCode Method     System.TypeCode GetTypeCode(), System.TypeCode IConvertible.GetTypeCode()
ToBoolean   Method     bool IConvertible.ToBoolean(System.IFormatProvider provider)
ToByte      Method     byte IConvertible.ToByte(System.IFormatProvider provider)
...

   TypeName: System.String

Name                 MemberType            Definition
----                 ----------            ----------
Clone                Method                System.Object Clone(), System.Object ICloneable.Clone()
CompareTo            Method                int CompareTo(System.Object value), int CompareTo(str...
Contains             Method                bool Contains(string value), bool Contains(string val...
CopyTo               Method                void CopyTo(int sourceIndex, char[] destination, int ...
EndsWith             Method                bool EndsWith(string value), bool EndsWith(string val...
EnumerateRunes       Method                System.Text.StringRuneEnumerator EnumerateRunes()
Equals               Method                bool Equals(System.Object obj), bool Equals(string va...
GetEnumerator        Method                System.CharEnumerator GetEnumerator(), System.Collect...
GetHashCode          Method                int GetHashCode(), int GetHashCode(System.StringCompa...
...
```

```powershell
Get-Member -InputObject $array
```

```Output
   TypeName: System.Object[]

Name           MemberType            Definition
----           ----------            ----------
Add            Method                int IList.Add(System.Object value)
Address        Method                System.Object&, System.Private.CoreLib, Version=4.0.0.0, Cu...
Clear          Method                void IList.Clear()
Clone          Method                System.Object Clone(), System.Object ICloneable.Clone()
CompareTo      Method                int IStructuralComparable.CompareTo(System.Object other, Sy...
...
```

<span data-ttu-id="65234-140">変数には、 `$array` 配列がパイプ処理されるときに見られるように、 **Int32** オブジェクトと **string** オブジェクトが含まれてい `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="65234-140">The `$array` variable contains an **Int32** object and a **string** object, as seen when the array is piped to `Get-Member`.</span></span> <span data-ttu-id="65234-141">`$array` **InputObject** パラメーターを使用してを渡すと、 `Get-Member` **Object []** 型のメンバーが返されます。</span><span class="sxs-lookup"><span data-stu-id="65234-141">When `$array` is passed using the **InputObject** parameter `Get-Member` returns the members of the **Object[]** type.</span></span>

### <span data-ttu-id="65234-142">例 7: 設定できるオブジェクトのプロパティを決定する</span><span class="sxs-lookup"><span data-stu-id="65234-142">Example 7: Determine which object properties you can set</span></span>

<span data-ttu-id="65234-143">この例は、オブジェクトのどのプロパティを変更できるかを判断する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="65234-143">This example shows how to determine which properties of an object can be changed.</span></span>

```powershell
$File = Get-Item c:\test\textFile.txt
$File.PSObject.Properties | Where-Object isSettable | Select-Object -Property Name
```

```Output
Name
----
PSPath
PSParentPath
PSChildName
PSDrive
PSProvider
PSIsContainer
IsReadOnly
CreationTime
CreationTimeUtc
LastAccessTime
LastAccessTimeUtc
LastWriteTime
LastWriteTimeUtc
Attributes
```

## <span data-ttu-id="65234-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="65234-144">PARAMETERS</span></span>

### <span data-ttu-id="65234-145">-Force</span><span class="sxs-lookup"><span data-stu-id="65234-145">-Force</span></span>

<span data-ttu-id="65234-146">組み込みメンバーと、コンパイラによって生成された **get_** および **set_** メソッドを表示に追加します。</span><span class="sxs-lookup"><span data-stu-id="65234-146">Adds the intrinsic members and the compiler-generated **get_** and **set_** methods to the display.</span></span>
<span data-ttu-id="65234-147">**Force** パラメーターを使用した場合に追加されるプロパティを次に示します。</span><span class="sxs-lookup"><span data-stu-id="65234-147">The following list describes the properties that are added when you use the **Force** parameter:</span></span>

- <span data-ttu-id="65234-148">**Psbase** : 拡張機能または適合しない .net オブジェクトの元のプロパティ。</span><span class="sxs-lookup"><span data-stu-id="65234-148">**PSBase** : The original properties of the .NET object without extension or adaptation.</span></span> <span data-ttu-id="65234-149">これらは、オブジェクトクラスに対して定義されているプロパティです。</span><span class="sxs-lookup"><span data-stu-id="65234-149">These are the properties defined for the object class.</span></span>
- <span data-ttu-id="65234-150">**Psadapted** 。</span><span class="sxs-lookup"><span data-stu-id="65234-150">**PSAdapted** .</span></span> <span data-ttu-id="65234-151">PowerShell 拡張型システムで定義されているプロパティとメソッド。</span><span class="sxs-lookup"><span data-stu-id="65234-151">The properties and methods defined in the PowerShell extended type system.</span></span>
- <span data-ttu-id="65234-152">**PSExtended** 。</span><span class="sxs-lookup"><span data-stu-id="65234-152">**PSExtended** .</span></span> <span data-ttu-id="65234-153">`Types.ps1xml`ファイルまたはコマンドレットを使用して追加されたプロパティとメソッド `Add-Member` 。</span><span class="sxs-lookup"><span data-stu-id="65234-153">The properties and methods that were added in the `Types.ps1xml` files or by using the `Add-Member` cmdlet.</span></span>
- <span data-ttu-id="65234-154">**PSObject** 。</span><span class="sxs-lookup"><span data-stu-id="65234-154">**PSObject** .</span></span> <span data-ttu-id="65234-155">ベースオブジェクトを PowerShell **PSObject** オブジェクトに変換するアダプター。</span><span class="sxs-lookup"><span data-stu-id="65234-155">The adapter that converts the base object to a PowerShell **PSObject** object.</span></span>
- <span data-ttu-id="65234-156">**PSTypeNames** 。</span><span class="sxs-lookup"><span data-stu-id="65234-156">**PSTypeNames** .</span></span> <span data-ttu-id="65234-157">オブジェクト特定性の順に記述するオブジェクト型の一覧。</span><span class="sxs-lookup"><span data-stu-id="65234-157">A list of object types that describe the object, in order of specificity.</span></span> <span data-ttu-id="65234-158">オブジェクトの書式を設定するときに、powershell は `Format.ps1xml` powershell インストールディレクトリ () 内のファイル内の型を検索 `$PSHOME` します。</span><span class="sxs-lookup"><span data-stu-id="65234-158">When formatting the object, PowerShell searches for the types in the `Format.ps1xml` files in the PowerShell installation directory (`$PSHOME`).</span></span> <span data-ttu-id="65234-159">検出した最初の型の書式設定定義を使用します。</span><span class="sxs-lookup"><span data-stu-id="65234-159">It uses the formatting definition for the first type that it finds.</span></span>

<span data-ttu-id="65234-160">既定では、は、 `Get-Member` **ベース** と **適合** を除くすべてのビューでこれらのプロパティを取得しますが、表示しません。</span><span class="sxs-lookup"><span data-stu-id="65234-160">By default, `Get-Member` gets these properties in all views except **Base** and **Adapted** , but does not display them.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65234-161">-InputObject</span><span class="sxs-lookup"><span data-stu-id="65234-161">-InputObject</span></span>

<span data-ttu-id="65234-162">取得するメンバーを含んでいるオブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="65234-162">Specifies the object whose members are retrieved.</span></span>

<span data-ttu-id="65234-163">**InputObject** パラメーターの使用は、オブジェクトをにパイプする場合と同じではありません `Get-Member` 。</span><span class="sxs-lookup"><span data-stu-id="65234-163">Using the **InputObject** parameter is not the same as piping an object to `Get-Member`.</span></span> <span data-ttu-id="65234-164">相違点は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="65234-164">The differences are as follows:</span></span>

- <span data-ttu-id="65234-165">オブジェクトのコレクションをにパイプすると `Get-Member` 、は、 `Get-Member` 文字列の配列内の各文字列のプロパティなど、コレクション内の個々のオブジェクトのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="65234-165">When you pipe a collection of objects to `Get-Member`, `Get-Member` gets the members of the individual objects in the collection, such as the properties of each string in an array of strings.</span></span>
- <span data-ttu-id="65234-166">**InputObject** を使用してオブジェクトのコレクションを送信すると、は、 `Get-Member` 文字列の配列の配列のプロパティなど、コレクションのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="65234-166">When you use **InputObject** to submit a collection of objects, `Get-Member` gets the members of the collection, such as the properties of the array in an array of strings.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="65234-167">-MemberType</span><span class="sxs-lookup"><span data-stu-id="65234-167">-MemberType</span></span>

<span data-ttu-id="65234-168">このコマンドレットが取得するメンバーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="65234-168">Specifies the member type that this cmdlet gets.</span></span> <span data-ttu-id="65234-169">既定値は **[すべて]** です。</span><span class="sxs-lookup"><span data-stu-id="65234-169">The default is **All** .</span></span>

<span data-ttu-id="65234-170">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="65234-170">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="65234-171">AliasProperty</span><span class="sxs-lookup"><span data-stu-id="65234-171">AliasProperty</span></span>
- <span data-ttu-id="65234-172">CodeProperty</span><span class="sxs-lookup"><span data-stu-id="65234-172">CodeProperty</span></span>
- <span data-ttu-id="65234-173">プロパティ</span><span class="sxs-lookup"><span data-stu-id="65234-173">Property</span></span>
- <span data-ttu-id="65234-174">NoteProperty</span><span class="sxs-lookup"><span data-stu-id="65234-174">NoteProperty</span></span>
- <span data-ttu-id="65234-175">ScriptProperty</span><span class="sxs-lookup"><span data-stu-id="65234-175">ScriptProperty</span></span>
- <span data-ttu-id="65234-176">Properties</span><span class="sxs-lookup"><span data-stu-id="65234-176">Properties</span></span>
- <span data-ttu-id="65234-177">PropertySet</span><span class="sxs-lookup"><span data-stu-id="65234-177">PropertySet</span></span>
- <span data-ttu-id="65234-178">認証方法</span><span class="sxs-lookup"><span data-stu-id="65234-178">Method</span></span>
- <span data-ttu-id="65234-179">CodeMethod</span><span class="sxs-lookup"><span data-stu-id="65234-179">CodeMethod</span></span>
- <span data-ttu-id="65234-180">ScriptMethod</span><span class="sxs-lookup"><span data-stu-id="65234-180">ScriptMethod</span></span>
- <span data-ttu-id="65234-181">メソッド</span><span class="sxs-lookup"><span data-stu-id="65234-181">Methods</span></span>
- <span data-ttu-id="65234-182">ParameterizedProperty</span><span class="sxs-lookup"><span data-stu-id="65234-182">ParameterizedProperty</span></span>
- <span data-ttu-id="65234-183">セット</span><span class="sxs-lookup"><span data-stu-id="65234-183">MemberSet</span></span>
- <span data-ttu-id="65234-184">event</span><span class="sxs-lookup"><span data-stu-id="65234-184">Event</span></span>
- <span data-ttu-id="65234-185">動的</span><span class="sxs-lookup"><span data-stu-id="65234-185">Dynamic</span></span>
- <span data-ttu-id="65234-186">All</span><span class="sxs-lookup"><span data-stu-id="65234-186">All</span></span>

<span data-ttu-id="65234-187">これらの値の詳細については、「 [PSMemberTypes Enumeration](/dotnet/api/system.management.automation.psmembertypes)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65234-187">For information about these values, see [PSMemberTypes Enumeration](/dotnet/api/system.management.automation.psmembertypes).</span></span>

<span data-ttu-id="65234-188">すべてのオブジェクトにすべての型のメンバーがあるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="65234-188">Not all objects have every type of member.</span></span> <span data-ttu-id="65234-189">オブジェクトに含まれていないメンバーの種類を指定すると、PowerShell は null 値を返します。</span><span class="sxs-lookup"><span data-stu-id="65234-189">If you specify a member type that the object does not have, PowerShell returns a null value.</span></span>

<span data-ttu-id="65234-190">すべての拡張メンバーなど、関連する型のメンバーを取得するには、 **View** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="65234-190">To get related types of members, such as all extended members, use the **View** parameter.</span></span> <span data-ttu-id="65234-191">**MemberType** パラメーターを **Static** または **View** パラメーターと共に使用すると、は `Get-Member` 両方のセットに属するメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="65234-191">If you use the **MemberType** parameter with the **Static** or **View** parameters, `Get-Member` gets the members that belong to both sets.</span></span>

```yaml
Type: System.Management.Automation.PSMemberTypes
Parameter Sets: (All)
Aliases: Type
Accepted values: AliasProperty, CodeProperty, Property, NoteProperty, ScriptProperty, Properties, PropertySet, Method, CodeMethod, ScriptMethod, Methods, ParameterizedProperty, MemberSet, Event, Dynamic, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65234-192">-Name</span><span class="sxs-lookup"><span data-stu-id="65234-192">-Name</span></span>

<span data-ttu-id="65234-193">オブジェクトの 1 つまたは複数のプロパティまたはメソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="65234-193">Specifies the names of one or more properties or methods of the object.</span></span> <span data-ttu-id="65234-194">`Get-Member` 指定されたプロパティおよびメソッドのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="65234-194">`Get-Member` gets only the specified properties and methods.</span></span>

<span data-ttu-id="65234-195">**Name** パラメーターを **MemberType** 、 **View** 、または **Static** パラメーターと共に使用すると、 `Get-Member` すべてのパラメーターの条件を満たすメンバーのみが取得されます。</span><span class="sxs-lookup"><span data-stu-id="65234-195">If you use the **Name** parameter with the **MemberType** , **View** , or **Static** parameter, `Get-Member` gets only the members that satisfy the criteria of all parameters.</span></span>

<span data-ttu-id="65234-196">静的メンバーを名前で取得するには、 **static** パラメーターを **name** パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="65234-196">To get a static member by name, use the **Static** parameter with the **Name** parameter.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65234-197">-Static</span><span class="sxs-lookup"><span data-stu-id="65234-197">-Static</span></span>

<span data-ttu-id="65234-198">このコマンドレットがオブジェクトの静的プロパティおよびメソッドのみを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="65234-198">Indicates that this cmdlet gets only the static properties and methods of the object.</span></span> <span data-ttu-id="65234-199">静的プロパティおよびメソッドは、クラスの特定のインスタンスで定義されるのではなく、オブジェクトのクラスで定義されます。</span><span class="sxs-lookup"><span data-stu-id="65234-199">Static properties and methods are defined on the class of objects, not on any particular instance of the class.</span></span>

<span data-ttu-id="65234-200">**Static** パラメーターを **view** パラメーターと共に使用すると、 **view** パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="65234-200">If you use the **Static** parameter with the **View** parameter, the **View** parameter is ignored.</span></span>
<span data-ttu-id="65234-201">**Static** パラメーターを **MemberType** パラメーターと共に使用すると、 `Get-Member` 両方のセットに属しているメンバーのみが取得されます。</span><span class="sxs-lookup"><span data-stu-id="65234-201">If you use the **Static** parameter with the **MemberType** parameter, `Get-Member` gets only the members that belong to both sets.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65234-202">-ビュー</span><span class="sxs-lookup"><span data-stu-id="65234-202">-View</span></span>

<span data-ttu-id="65234-203">このコマンドレットが特定の型のプロパティとメソッドだけを取得することを指定します。</span><span class="sxs-lookup"><span data-stu-id="65234-203">Specifies that this cmdlet gets only particular types properties and methods.</span></span> <span data-ttu-id="65234-204">1 つまたは複数の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="65234-204">Specify one or more of the values.</span></span> <span data-ttu-id="65234-205">既定値は、[ **拡張** **] になっています** 。</span><span class="sxs-lookup"><span data-stu-id="65234-205">The default is **Adapted** , **Extended** .</span></span>

<span data-ttu-id="65234-206">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="65234-206">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="65234-207">底。</span><span class="sxs-lookup"><span data-stu-id="65234-207">Base.</span></span> <span data-ttu-id="65234-208">.NET オブジェクトの元のプロパティおよびメソッドのみを取得します (拡張子または適合なし)。</span><span class="sxs-lookup"><span data-stu-id="65234-208">Gets only the original properties and methods of the .NET object (without extension or adaptation).</span></span>
- <span data-ttu-id="65234-209">適用.</span><span class="sxs-lookup"><span data-stu-id="65234-209">Adapted.</span></span> <span data-ttu-id="65234-210">PowerShell 拡張型システムで定義されているプロパティとメソッドだけを取得します。</span><span class="sxs-lookup"><span data-stu-id="65234-210">Gets only the properties and methods defined in the PowerShell extended type system.</span></span>
- <span data-ttu-id="65234-211">長引い.</span><span class="sxs-lookup"><span data-stu-id="65234-211">Extended.</span></span> <span data-ttu-id="65234-212">`Types.ps1xml`ファイルまたはコマンドレットを使用して追加されたプロパティとメソッドだけを取得し `Add-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="65234-212">Gets only the properties and methods that were added in a `Types.ps1xml` files or by using the `Add-Member` cmdlet.</span></span>
- <span data-ttu-id="65234-213">すべて。</span><span class="sxs-lookup"><span data-stu-id="65234-213">All.</span></span> <span data-ttu-id="65234-214">Base、Adapted、および Extended ビューのメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="65234-214">Gets the members in the Base, Adapted, and Extended views.</span></span>

<span data-ttu-id="65234-215">**View** パラメーターは、メンバーの表示だけでなく、取得するメンバーを決定します。</span><span class="sxs-lookup"><span data-stu-id="65234-215">The **View** parameter determines the members retrieved, not just the display of those members.</span></span>

<span data-ttu-id="65234-216">スクリプトプロパティなど、特定のメンバーの種類を取得するには、 **MemberType** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="65234-216">To get particular member types, such as script properties, use the **MemberType** parameter.</span></span> <span data-ttu-id="65234-217">同じコマンドで **MemberType** パラメーターと **View** パラメーターを使用すると、 `Get-Member` 両方のセットに属するメンバーを取得します。</span><span class="sxs-lookup"><span data-stu-id="65234-217">If you use the **MemberType** and **View** parameters in the same command, `Get-Member` gets the members that belong to both sets.</span></span> <span data-ttu-id="65234-218">**Static** パラメーターと **view** パラメーターを同じコマンドで使用すると、 **view** パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="65234-218">If you use the **Static** and **View** parameters in the same command, the **View** parameter is ignored.</span></span>

```yaml
Type: System.Management.Automation.PSMemberViewTypes
Parameter Sets: (All)
Aliases:
Accepted values: Extended, Adapted, Base, All

Required: False
Position: Named
Default value: Adapted, Extended
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="65234-219">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="65234-219">CommonParameters</span></span>

<span data-ttu-id="65234-220">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="65234-220">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="65234-221">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65234-221">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="65234-222">入力</span><span class="sxs-lookup"><span data-stu-id="65234-222">INPUTS</span></span>

### <span data-ttu-id="65234-223">システム管理. PSObject</span><span class="sxs-lookup"><span data-stu-id="65234-223">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="65234-224">パイプを使用して任意のオブジェクトをにパイプすることができ `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="65234-224">You can pipe any object to `Get-Member`.</span></span>

## <span data-ttu-id="65234-225">出力</span><span class="sxs-lookup"><span data-stu-id="65234-225">OUTPUTS</span></span>

### <span data-ttu-id="65234-226">Microsoft. PowerShell. MemberDefinition</span><span class="sxs-lookup"><span data-stu-id="65234-226">Microsoft.PowerShell.Commands.MemberDefinition</span></span>

<span data-ttu-id="65234-227">`Get-Member` が取得する各プロパティまたはメソッドのオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="65234-227">`Get-Member` returns an object for each property or method that its gets.</span></span>

## <span data-ttu-id="65234-228">注</span><span class="sxs-lookup"><span data-stu-id="65234-228">NOTES</span></span>

<span data-ttu-id="65234-229">コレクションオブジェクトに関する情報を取得するには、 **InputObject** パラメーターを使用するか、オブジェクトの前にコンマを付加してを渡し `Get-Member` ます。</span><span class="sxs-lookup"><span data-stu-id="65234-229">You can get information about a collection object either by using the **InputObject** parameter or by piping the object, preceded by a comma, to `Get-Member`.</span></span>

<span data-ttu-id="65234-230">`$This`新しいプロパティとメソッドの値を定義するスクリプトブロックでは、自動変数を使用できます。</span><span class="sxs-lookup"><span data-stu-id="65234-230">You can use the `$This` automatic variable in script blocks that define the values of new properties and methods.</span></span> <span data-ttu-id="65234-231">変数は、 `$This` プロパティとメソッドを追加するオブジェクトのインスタンスを参照します。</span><span class="sxs-lookup"><span data-stu-id="65234-231">The `$This` variable refers to the instance of the object to which the properties and methods are being added.</span></span> <span data-ttu-id="65234-232">変数の詳細については `$This` 、「 [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65234-232">For more information about the `$This` variable, see [about_Automatic_Variables](../Microsoft.PowerShell.Core/About/about_Automatic_Variables.md).</span></span>

<span data-ttu-id="65234-233">などの型リテラルと _同様に、型を表す_ オブジェクトを渡すと、 `[int]` `Get-Member` 型に関する情報が返さ `[System.RuntimeType]` れます。</span><span class="sxs-lookup"><span data-stu-id="65234-233">If you pass an object representing a _type_ , like a type literal such as `[int]`, `Get-Member` return information about the `[System.RuntimeType]` type.</span></span> <span data-ttu-id="65234-234">ただし、 **static** パラメーターを使用すると、は、 `Get-Member` インスタンスによって表される特定の型の静的メンバーを返し `System.RuntimeType` ます。</span><span class="sxs-lookup"><span data-stu-id="65234-234">However, when you use the **Static** parameter, `Get-Member` returns the static members of the specific type represented by the `System.RuntimeType` instance.</span></span>

## <span data-ttu-id="65234-235">関連リンク</span><span class="sxs-lookup"><span data-stu-id="65234-235">RELATED LINKS</span></span>

[<span data-ttu-id="65234-236">Add-Member</span><span class="sxs-lookup"><span data-stu-id="65234-236">Add-Member</span></span>](Add-Member.md)