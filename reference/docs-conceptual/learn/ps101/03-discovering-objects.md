---
title: オブジェクト、プロパティ、およびメソッドの検出
description: オブジェクト、プロパティ、およびメソッドを理解して使用するうえで開発者である必要はありません。
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 5ab972755afeba0d94bf6c2debaf84ec84cd9244
ms.sourcegitcommit: 0d958eac5bde5ccf5ee2c1bac4f009a63bf71368
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2020
ms.locfileid: "84438073"
---
# <a name="chapter-3---discovering-objects-properties-and-methods"></a><span data-ttu-id="a3399-103">第 3 章 - オブジェクト、プロパティ、およびメソッドの検出</span><span class="sxs-lookup"><span data-stu-id="a3399-103">Chapter 3 - Discovering objects, properties, and methods</span></span>

<span data-ttu-id="a3399-104">私が初めて出会ったコンピューターは Commodore 64 でしたが、自分の初めての現代的なコンピューターは、1 MB のメモリ、40 MB のハード ドライブ、および 1 基の 5-1/4 インチ フロッピー ディスク ドライブと CGA モニターを備え、Microsoft DOS 3.3 で動作する 286 12 MHz IBM 互換機でした。</span><span class="sxs-lookup"><span data-stu-id="a3399-104">My first introduction to computers was a Commodore 64, but my first modern computer was a 286 12-Mhz IBM clone with 1 megabyte of memory, a 40-megabyte hard drive, and one 5-1/4 inch floppy disk drive with a CGA monitor running Microsoft DOS 3.3.</span></span>

<span data-ttu-id="a3399-105">多くの IT 担当者は、私と同様にコマンド ラインに慣れていますが、オブジェクト、プロパティ、およびメソッドの話題になると思考停止状態に陥り、"私は開発者ではない" と口にします。</span><span class="sxs-lookup"><span data-stu-id="a3399-105">Many IT Pros, like myself, are no stranger to the command line, but when the subject of objects, properties, and methods comes up, they get the deer in the headlights look and say, "I'm not a developer."</span></span> <span data-ttu-id="a3399-106">でも聞いてください。</span><span class="sxs-lookup"><span data-stu-id="a3399-106">Guess what?</span></span> <span data-ttu-id="a3399-107">PowerShell をうまく使ううえで開発者である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a3399-107">You don't have to be a developer to be successful with PowerShell.</span></span> <span data-ttu-id="a3399-108">用語にとらわれないでください。</span><span class="sxs-lookup"><span data-stu-id="a3399-108">Don't get bogged down in the terminology.</span></span> <span data-ttu-id="a3399-109">最初からすべてを理解するのは難しいかもしれませんが、少し実践的な経験を積めばいずれピンとくる瞬間がやってきます。</span><span class="sxs-lookup"><span data-stu-id="a3399-109">Not everything may make sense initially, but after a little hands-on experience you'll start to have those "light bulb" moments.</span></span> <span data-ttu-id="a3399-110">"なるほど。</span><span class="sxs-lookup"><span data-stu-id="a3399-110">"Aha!</span></span> <span data-ttu-id="a3399-111">あの本に書かれていたのはそういうことか。"</span><span class="sxs-lookup"><span data-stu-id="a3399-111">So that's what the book was talking about."</span></span>

<span data-ttu-id="a3399-112">お使いのコンピューターで例を試して、実際に体験してみてください。</span><span class="sxs-lookup"><span data-stu-id="a3399-112">Be sure to try the examples on your computer to gain some of that hands-on experience.</span></span>

## <a name="requirements"></a><span data-ttu-id="a3399-113">必要条件</span><span class="sxs-lookup"><span data-stu-id="a3399-113">Requirements</span></span>

<span data-ttu-id="a3399-114">この章で紹介する例の中には、Active Directory PowerShell モジュールを必要とするものがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="a3399-114">The Active Directory PowerShell module is required by some of the examples shown in this chapter.</span></span>
<span data-ttu-id="a3399-115">このモジュールは、Windows 用リモート サーバー管理ツール (RSAT) の一部です。</span><span class="sxs-lookup"><span data-stu-id="a3399-115">The module is part of the Remote Server Administration Tools (RSAT) for Windows.</span></span> <span data-ttu-id="a3399-116">Windows の 1809 (またはそれ以上) のビルドでは、RSAT ツールは Windows の機能としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a3399-116">For the 1809 (or higher) build of Windows, the RSAT tools are installed as a Windows feature.</span></span>

- <span data-ttu-id="a3399-117">RSAT ツールのインストールについては、「[Windows 管理モジュール][]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3399-117">For information about installing the RSAT tools, see [Windows Management modules][].</span></span>
- <span data-ttu-id="a3399-118">Windows の以前のバージョンについては、[Windows 用 RSAT][] に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3399-118">For older versions of Windows, see [RSAT for Windows][].</span></span>

## <a name="get-member"></a><span data-ttu-id="a3399-119">Get-Member</span><span class="sxs-lookup"><span data-stu-id="a3399-119">Get-Member</span></span>

<span data-ttu-id="a3399-120">`Get-Member` は、コマンドで使用できるオブジェクト、プロパティ、およびメソッドを調べるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a3399-120">`Get-Member` helps you discover what objects, properties, and methods are available for commands.</span></span>
<span data-ttu-id="a3399-121">オブジェクトベースの出力を生成するすべてのコマンドを、`Get-Member` にパイプ処理することができます。</span><span class="sxs-lookup"><span data-stu-id="a3399-121">Any command that produces object-based output can be piped to `Get-Member`.</span></span> <span data-ttu-id="a3399-122">プロパティは、項目に関する特性です。</span><span class="sxs-lookup"><span data-stu-id="a3399-122">A property is a characteristic about an item.</span></span> <span data-ttu-id="a3399-123">運転免許証には目の色と呼ばれるプロパティがあり、そのプロパティの最も一般的な値は青と茶色です。</span><span class="sxs-lookup"><span data-stu-id="a3399-123">Your drivers license has a property called eye color and the most common values for that property are blue and brown.</span></span> <span data-ttu-id="a3399-124">メソッドは、項目に対して実行できるアクションです。</span><span class="sxs-lookup"><span data-stu-id="a3399-124">A method is an action that can be taken on an item.</span></span> <span data-ttu-id="a3399-125">運転免許証の例をそのまま使用した場合、米国の車両管理局では運転免許証を取り消すことができることから、"取り消し" がメソッドの 1 つになります。</span><span class="sxs-lookup"><span data-stu-id="a3399-125">In staying with the drivers license example, one of the methods is "Revoke" because the department of motor vehicles can revoke your drivers license.</span></span>

### <a name="properties"></a><span data-ttu-id="a3399-126">Properties</span><span class="sxs-lookup"><span data-stu-id="a3399-126">Properties</span></span>

<span data-ttu-id="a3399-127">次の例では、コンピューターで実行されている Windows タイム サービスに関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="a3399-127">In the following example, I'll retrieve information about the Windows Time service running on my computer.</span></span>

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

<span data-ttu-id="a3399-128">前の結果のセットに示されているように、**Status**、**Name**、および **DisplayName** はプロパティの例です。</span><span class="sxs-lookup"><span data-stu-id="a3399-128">**Status**, **Name**, and **DisplayName** are examples of properties as shown in the previous set of results.</span></span> <span data-ttu-id="a3399-129">**Status** プロパティの値は `Running`、**Name** プロパティの値は `w32time`、**DisplayName** の値は `Windows Time` です。</span><span class="sxs-lookup"><span data-stu-id="a3399-129">The value for the **Status** property is `Running`, the value for the **Name** property is `w32time`, and the value for **DisplayName** is `Windows Time`.</span></span>

<span data-ttu-id="a3399-130">次に、同じコマンドを `Get-Member` にパイプ処理します。</span><span class="sxs-lookup"><span data-stu-id="a3399-130">Now I'll pipe that same command to `Get-Member`:</span></span>

```powershell
Get-Service -Name w32time | Get-Member
```

```Output
   TypeName: System.ServiceProcess.ServiceController

Name                      MemberType    Definition
----                      ----------    ----------
Name                      AliasProperty Name = ServiceName
RequiredServices          AliasProperty RequiredServices = ServicesDependedOn
Disposed                  Event         System.EventHandler Disposed(System.Object, Sy...
Close                     Method        void Close()
Continue                  Method        void Continue()
CreateObjRef              Method        System.Runtime.Remoting.ObjRef CreateObjRef(ty...
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
WaitForStatus             Method        void WaitForStatus(System.ServiceProcess.Servi...
CanPauseAndContinue       Property      bool CanPauseAndContinue {get;}
CanShutdown               Property      bool CanShutdown {get;}
CanStop                   Property      bool CanStop {get;}
Container                 Property      System.ComponentModel.IContainer Container {get;}
DependentServices         Property      System.ServiceProcess.ServiceController[] Depe...
DisplayName               Property      string DisplayName {get;set;}
MachineName               Property      string MachineName {get;set;}
ServiceHandle             Property      System.Runtime.InteropServices.SafeHandle Serv...
ServiceName               Property      string ServiceName {get;set;}
ServicesDependedOn        Property      System.ServiceProcess.ServiceController[] Serv...
ServiceType               Property      System.ServiceProcess.ServiceType ServiceType ...
Site                      Property      System.ComponentModel.ISite Site {get;set;}
StartType                 Property      System.ServiceProcess.ServiceStartMode StartTy...
Status                    Property      System.ServiceProcess.ServiceControllerStatus ...
ToString                  ScriptMethod  System.Object ToString();
```

<span data-ttu-id="a3399-131">前の例における結果の最初の行には、非常に重要な情報が 1 つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3399-131">The first line of the results in the previous example contains one piece of very important information.</span></span> <span data-ttu-id="a3399-132">**TypeName** は、返されたオブジェクトの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="a3399-132">**TypeName** tells you what type of object was returned.</span></span> <span data-ttu-id="a3399-133">この例では、**System.ServiceProcess.ServiceController** オブジェクトが返されました。</span><span class="sxs-lookup"><span data-stu-id="a3399-133">In this example, a **System.ServiceProcess.ServiceController** object was returned.</span></span> <span data-ttu-id="a3399-134">これは、最後のピリオドの直後にある **TypeName** の部分に省略されることがよくあります (この例では **ServiceController**)。</span><span class="sxs-lookup"><span data-stu-id="a3399-134">This is often abbreviated as the portion of the **TypeName** just after the last period; **ServiceController** in this example.</span></span>

<span data-ttu-id="a3399-135">コマンドによって生成されるオブジェクトの種類がわかれば、この情報を使用して、その種類のオブジェクトを入力として受け取るコマンドを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="a3399-135">Once you know what type of object a command produces, you can use this information to find commands that accept that type of object as input.</span></span>

```powershell
Get-Command -ParameterType ServiceController
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Get-Service                                        3.1.0.0    Microsof...
Cmdlet          Restart-Service                                    3.1.0.0    Microsof...
Cmdlet          Resume-Service                                     3.1.0.0    Microsof...
Cmdlet          Set-Service                                        3.1.0.0    Microsof...
Cmdlet          Start-Service                                      3.1.0.0    Microsof...
Cmdlet          Stop-Service                                       3.1.0.0    Microsof...
Cmdlet          Suspend-Service                                    3.1.0.0    Microsof...
```

<span data-ttu-id="a3399-136">これらのすべてのコマンドには、パイプライン、パラメーター入力、またはその両方で **ServiceController** というオブジェクトの種類を受け取るパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="a3399-136">All of those commands have a parameter that accepts a **ServiceController** object type by pipeline, parameter input, or both.</span></span>

<span data-ttu-id="a3399-137">既定で表示されるよりも多くのプロパティがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a3399-137">Notice that there are more properties than are displayed by default.</span></span> <span data-ttu-id="a3399-138">これらの追加のプロパティは既定では表示されませんが、コマンドを `Select-Object` コマンドレットにパイプ処理し、**Property** パラメーターを使用することにより、パイプラインから選択できます。</span><span class="sxs-lookup"><span data-stu-id="a3399-138">Although these additional properties aren't displayed by default, they can be selected from the pipeline by piping the command to the `Select-Object` cmdlet and using the **Property** parameter.</span></span> <span data-ttu-id="a3399-139">次の例では、`Get-Service` の結果を `Select-Object` にパイプ処理し、**Property** パラメーターの値として `*` ワイルドカード文字を指定することにより、すべてのプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3399-139">The following example selects all of the properties by piping the results of `Get-Service` to `Select-Object` and specifying the `*` wildcard character as the value for the **Property** parameter.</span></span>

```powershell
Get-Service -Name w32time | Select-Object -Property *
```

```Output
Name                : w32time
RequiredServices    : {}
CanPauseAndContinue : False
CanShutdown         : True
CanStop             : True
DisplayName         : Windows Time
DependentServices   : {}
MachineName         : .
ServiceName         : w32time
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :
```

<span data-ttu-id="a3399-140">特定のプロパティは、**Property** パラメーターの値のコンマ区切りリストを使用して選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="a3399-140">Specific properties can also be selected using a comma-separated list for the value of the **Property** parameter.</span></span>

```powershell
Get-Service -Name w32time | Select-Object -Property Status, Name, DisplayName, ServiceType
```

```Output
 Status Name    DisplayName        ServiceType
 ------ ----    -----------        -----------
Running w32time Windows Time Win32ShareProcess
```

<span data-ttu-id="a3399-141">既定では、4 つのプロパティがテーブルで返され、5 つ目以降のプロパティはリストで返されます。</span><span class="sxs-lookup"><span data-stu-id="a3399-141">By default, four properties are returned in a table and five or more are returned in a list.</span></span> <span data-ttu-id="a3399-142">一部のコマンドでは、カスタム書式設定を使用して、テーブルに既定で表示されるプロパティの数を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="a3399-142">Some commands use custom formatting to override how many properties are displayed by default in a table.</span></span>
<span data-ttu-id="a3399-143">これらの既定値を手動で上書きするために使用できる `Format-*` コマンドレットがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="a3399-143">There are several `Format-*` cmdlets that can be used to manually override these defaults.</span></span> <span data-ttu-id="a3399-144">最も一般的なものは `Format-Table` と `Format-List` で、どちらも次の章で扱います。</span><span class="sxs-lookup"><span data-stu-id="a3399-144">The most common ones are `Format-Table` and `Format-List`, both of which will be covered in an upcoming chapter.</span></span>

<span data-ttu-id="a3399-145">ワイルドカード文字は、`Select-Object` でプロパティ名を指定するときに使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a3399-145">Wildcard characters can be used when specifying the property names with `Select-Object`.</span></span>

```powershell
Get-Service -Name w32time | Select-Object -Property Status, DisplayName, Can*
```

```powershell
Status              : Running
DisplayName         : Windows Time
CanPauseAndContinue : False
CanShutdown         : True
CanStop             : True
```

<span data-ttu-id="a3399-146">前の例では、`Can*` が **Property** パラメーターの値の 1 つとして使用され、`Can` で始まるすべてのプロパティが返されました。</span><span class="sxs-lookup"><span data-stu-id="a3399-146">In the previous example, `Can*` was used as one of the values for the **Property** parameter to return all the properties that start with `Can`.</span></span> <span data-ttu-id="a3399-147">これらには、**CanPauseAndContinue**、**CanShutdown**、および **CanStop** が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a3399-147">These include **CanPauseAndContinue**, **CanShutdown**, and **CanStop**.</span></span>

### <a name="methods"></a><span data-ttu-id="a3399-148">メソッド</span><span class="sxs-lookup"><span data-stu-id="a3399-148">Methods</span></span>

<span data-ttu-id="a3399-149">メソッドは、実行できるアクションです。</span><span class="sxs-lookup"><span data-stu-id="a3399-149">Methods are an action that can be taken.</span></span> <span data-ttu-id="a3399-150">`Get-Service` のメソッドのみを表示するには、**MemberType** パラメーターを使用して `Get-Member` の結果を絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="a3399-150">Use the **MemberType** parameter to narrow down the results of `Get-Member` to only show the methods for `Get-Service`.</span></span>

```powershell
Get-Service -Name w32time | Get-Member -MemberType Method
```

```Output
   TypeName: System.ServiceProcess.ServiceController

Name                      MemberType Definition
----                      ---------- ----------
Close                     Method     void Close()
Continue                  Method     void Continue()
CreateObjRef              Method     System.Runtime.Remoting.ObjRef CreateObjRef(type ...
Dispose                   Method     void Dispose(), void IDisposable.Dispose()
Equals                    Method     bool Equals(System.Object obj)
ExecuteCommand            Method     void ExecuteCommand(int command)
GetHashCode               Method     int GetHashCode()
GetLifetimeService        Method     System.Object GetLifetimeService()
GetType                   Method     type GetType()
InitializeLifetimeService Method     System.Object InitializeLifetimeService()
Pause                     Method     void Pause()
Refresh                   Method     void Refresh()
Start                     Method     void Start(), void Start(string[] args)
Stop                      Method     void Stop()
WaitForStatus             Method     void WaitForStatus(System.ServiceProcess.ServiceC...
```

<span data-ttu-id="a3399-151">ご覧のとおり、多くのメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="a3399-151">As you can see, there are many methods.</span></span> <span data-ttu-id="a3399-152">**Stop** メソッドを使用すると、Windows サービスを停止できます。</span><span class="sxs-lookup"><span data-stu-id="a3399-152">The **Stop** method can be used to stop a Windows service.</span></span>

```powershell
(Get-Service -Name w32time).Stop()
```

<span data-ttu-id="a3399-153">ここで、Windows タイム サービスが実際に停止していることを確認してみましょう。</span><span class="sxs-lookup"><span data-stu-id="a3399-153">Now to verify the Windows time service has indeed been stopped.</span></span>

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  w32time            Windows Time
```

<span data-ttu-id="a3399-154">私自身はメソッドを使用することはあまりありませんが、知っておくべきことがあります。</span><span class="sxs-lookup"><span data-stu-id="a3399-154">I rarely find myself using methods, but they're something you need to be aware of.</span></span> <span data-ttu-id="a3399-155">その項目を変更するための対応するコマンドがない `Get-*` コマンドに遭遇することがあります。</span><span class="sxs-lookup"><span data-stu-id="a3399-155">There are times that you'll come across a `Get-*` command without a corresponding command to modify that item.</span></span>
<span data-ttu-id="a3399-156">多くの場合、メソッドを使用して、それを変更するアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a3399-156">Often, a method can be used to perform an action that modifies it.</span></span> <span data-ttu-id="a3399-157">SqlServer PowerShell モジュールの `Get-SqlAgentJob` コマンドレットは、この良い例です。</span><span class="sxs-lookup"><span data-stu-id="a3399-157">The `Get-SqlAgentJob` cmdlet in the SqlServer PowerShell module is a good example of this.</span></span> <span data-ttu-id="a3399-158">このモジュールは、[SQL Server Management Studio (SMSS)][SMSS] の一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a3399-158">The module installs as part of [SQL Server Management Studio (SMSS)][SMSS].</span></span> <span data-ttu-id="a3399-159">対応する `Set-*` コマンドレットはありませんが、メソッドを使用して同じタスクを完了できます。</span><span class="sxs-lookup"><span data-stu-id="a3399-159">No corresponding `Set-*` cmdlet exists, but a method can be used to complete the same task.</span></span>

<span data-ttu-id="a3399-160">メソッドに注意するもう 1 つの理由は、`Get-*` コマンドでは破壊的な変更が実行されることはないと多くの初心者が思い込んでいることにあります。</span><span class="sxs-lookup"><span data-stu-id="a3399-160">Another reason to be aware of methods is that many beginners assume destructive changes can't be made with `Get-*` commands.</span></span> <span data-ttu-id="a3399-161">しかし、実際には、不適切な使用によって深刻な問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a3399-161">But they indeed can cause serious problems if used inappropriately.</span></span>

<span data-ttu-id="a3399-162">より良いオプションは、コマンドレットがある場合はそれを使用してアクションを実行することです。</span><span class="sxs-lookup"><span data-stu-id="a3399-162">A better option is to use a cmdlet to perform the action if one exists.</span></span> <span data-ttu-id="a3399-163">Windows タイム サービスを開始します。ただし、今回は、サービスを開始するためにコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3399-163">Go ahead and start the Windows Time service, except this time use the cmdlet for starting services.</span></span>

```powershell
Get-Service -Name w32time | Start-Service -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

<span data-ttu-id="a3399-164">既定では、`Start-Service` は、`Get-Service` の開始メソッドと同じように結果を返しません。</span><span class="sxs-lookup"><span data-stu-id="a3399-164">By default, `Start-Service` doesn't return any results just like the start method of `Get-Service`.</span></span>
<span data-ttu-id="a3399-165">ただし、コマンドレットを使用する利点の 1 つは、メソッドでは使用できない追加機能がコマンドレットによく用意されていることです。</span><span class="sxs-lookup"><span data-stu-id="a3399-165">But one of the benefits of using a cmdlet is that many times the cmdlet offers additional functionality that isn't available with a method.</span></span> <span data-ttu-id="a3399-166">前の例では、**PassThru** パラメーターが使用されています。</span><span class="sxs-lookup"><span data-stu-id="a3399-166">In the previous example, the **PassThru** parameter was used.</span></span> <span data-ttu-id="a3399-167">これにより、通常は出力を生成しないコマンドレットで出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a3399-167">This causes a cmdlet that doesn't normally produce output, to produce output.</span></span>

<span data-ttu-id="a3399-168">コマンドレットの出力に関する思い込みに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a3399-168">Be careful with assumptions about the output of a cmdlet.</span></span> <span data-ttu-id="a3399-169">思い込みにとらわれるとどうなるかは皆さんご存じのとおりです。</span><span class="sxs-lookup"><span data-stu-id="a3399-169">We all know what happens when you assume things.</span></span> <span data-ttu-id="a3399-170">そこで、Windows 10 ラボ環境コンピューターで実行されている PowerShell プロセスに関する情報を取得してみます。</span><span class="sxs-lookup"><span data-stu-id="a3399-170">I'll retrieve information about the PowerShell process running on my Windows 10 lab environment computer.</span></span>

```powershell
Get-Process -Name PowerShell
```

```Output
Handles  NPM(K)    PM(K)      WS(K)     CPU(s)     Id  SI ProcessName
-------  ------    -----      -----     ------     --  -- -----------
    922      48   107984     140552       2.84   9020   1 powershell

```

<span data-ttu-id="a3399-171">次に、同じコマンドを Get-Member にパイプ処理します。</span><span class="sxs-lookup"><span data-stu-id="a3399-171">Now I'll pipe that same command to Get-Member:</span></span>

```powershell
Get-Process -Name PowerShell | Get-Member
```

```Output
   TypeName: System.Diagnostics.Process

Name                       MemberType     Definition
----                       ----------     ----------
Handles                    AliasProperty  Handles = Handlecount
Name                       AliasProperty  Name = ProcessName
NPM                        AliasProperty  NPM = NonpagedSystemMemorySize64
PM                         AliasProperty  PM = PagedMemorySize64
SI                         AliasProperty  SI = SessionId
VM                         AliasProperty  VM = VirtualMemorySize64
WS                         AliasProperty  WS = WorkingSet64
Disposed                   Event          System.EventHandler Disposed(System.Object, ...
ErrorDataReceived          Event          System.Diagnostics.DataReceivedEventHandler ...
Exited                     Event          System.EventHandler Exited(System.Object, Sy...
OutputDataReceived         Event          System.Diagnostics.DataReceivedEventHandler ...
BeginErrorReadLine         Method         void BeginErrorReadLine()
BeginOutputReadLine        Method         void BeginOutputReadLine()
CancelErrorRead            Method         void CancelErrorRead()
CancelOutputRead           Method         void CancelOutputRead()
Close                      Method         void Close()
CloseMainWindow            Method         bool CloseMainWindow()
CreateObjRef               Method         System.Runtime.Remoting.ObjRef CreateObjRef(...
Dispose                    Method         void Dispose(), void IDisposable.Dispose()
Equals                     Method         bool Equals(System.Object obj)
GetHashCode                Method         int GetHashCode()
GetLifetimeService         Method         System.Object GetLifetimeService()
GetType                    Method         type GetType()
InitializeLifetimeService  Method         System.Object InitializeLifetimeService()
Kill                       Method         void Kill()
Refresh                    Method         void Refresh()
Start                      Method         bool Start()
ToString                   Method         string ToString()
WaitForExit                Method         bool WaitForExit(int milliseconds), void Wai...
WaitForInputIdle           Method         bool WaitForInputIdle(int milliseconds), boo...
__NounName                 NoteProperty   string __NounName=Process
BasePriority               Property       int BasePriority {get;}
Container                  Property       System.ComponentModel.IContainer Container {...
EnableRaisingEvents        Property       bool EnableRaisingEvents {get;set;}
ExitCode                   Property       int ExitCode {get;}
ExitTime                   Property       datetime ExitTime {get;}
Handle                     Property       System.IntPtr Handle {get;}
HandleCount                Property       int HandleCount {get;}
HasExited                  Property       bool HasExited {get;}
Id                         Property       int Id {get;}
MachineName                Property       string MachineName {get;}
MainModule                 Property       System.Diagnostics.ProcessModule MainModule ...
MainWindowHandle           Property       System.IntPtr MainWindowHandle {get;}
MainWindowTitle            Property       string MainWindowTitle {get;}
MaxWorkingSet              Property       System.IntPtr MaxWorkingSet {get;set;}
MinWorkingSet              Property       System.IntPtr MinWorkingSet {get;set;}
Modules                    Property       System.Diagnostics.ProcessModuleCollection M...
NonpagedSystemMemorySize   Property       int NonpagedSystemMemorySize {get;}
NonpagedSystemMemorySize64 Property       long NonpagedSystemMemorySize64 {get;}
PagedMemorySize            Property       int PagedMemorySize {get;}
PagedMemorySize64          Property       long PagedMemorySize64 {get;}
PagedSystemMemorySize      Property       int PagedSystemMemorySize {get;}
PagedSystemMemorySize64    Property       long PagedSystemMemorySize64 {get;}
PeakPagedMemorySize        Property       int PeakPagedMemorySize {get;}
PeakPagedMemorySize64      Property       long PeakPagedMemorySize64 {get;}
PeakVirtualMemorySize      Property       int PeakVirtualMemorySize {get;}
PeakVirtualMemorySize64    Property       long PeakVirtualMemorySize64 {get;}
PeakWorkingSet             Property       int PeakWorkingSet {get;}
PeakWorkingSet64           Property       long PeakWorkingSet64 {get;}
PriorityBoostEnabled       Property       bool PriorityBoostEnabled {get;set;}
PriorityClass              Property       System.Diagnostics.ProcessPriorityClass Prio...
PrivateMemorySize          Property       int PrivateMemorySize {get;}
PrivateMemorySize64        Property       long PrivateMemorySize64 {get;}
PrivilegedProcessorTime    Property       timespan PrivilegedProcessorTime {get;}
ProcessName                Property       string ProcessName {get;}
ProcessorAffinity          Property       System.IntPtr ProcessorAffinity {get;set;}
Responding                 Property       bool Responding {get;}
SafeHandle                 Property       Microsoft.Win32.SafeHandles.SafeProcessHandl...
SessionId                  Property       int SessionId {get;}
Site                       Property       System.ComponentModel.ISite Site {get;set;}
StandardError              Property       System.IO.StreamReader StandardError {get;}
StandardInput              Property       System.IO.StreamWriter StandardInput {get;}
StandardOutput             Property       System.IO.StreamReader StandardOutput {get;}
StartInfo                  Property       System.Diagnostics.ProcessStartInfo StartInf...
StartTime                  Property       datetime StartTime {get;}
SynchronizingObject        Property       System.ComponentModel.ISynchronizeInvoke Syn...
Threads                    Property       System.Diagnostics.ProcessThreadCollection T...
TotalProcessorTime         Property       timespan TotalProcessorTime {get;}
UserProcessorTime          Property       timespan UserProcessorTime {get;}
VirtualMemorySize          Property       int VirtualMemorySize {get;}
VirtualMemorySize64        Property       long VirtualMemorySize64 {get;}
WorkingSet                 Property       int WorkingSet {get;}
WorkingSet64               Property       long WorkingSet64 {get;}
PSConfiguration            PropertySet    PSConfiguration {Name, Id, PriorityClass, Fi...
PSResources                PropertySet    PSResources {Name, Id, Handlecount, WorkingS...
Company                    ScriptProperty System.Object Company {get=$this.Mainmodule....
CPU                        ScriptProperty System.Object CPU {get=$this.TotalProcessorT...
Description                ScriptProperty System.Object Description {get=$this.Mainmod...
FileVersion                ScriptProperty System.Object FileVersion {get=$this.Mainmod...
Path                       ScriptProperty System.Object Path {get=$this.Mainmodule.Fil...
Product                    ScriptProperty System.Object Product {get=$this.Mainmodule....
ProductVersion             ScriptProperty System.Object ProductVersion {get=$this.Main...
```

<span data-ttu-id="a3399-172">既定で表示されるよりも多くのプロパティがあることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a3399-172">Notice that there are more properties listed than are displayed by default.</span></span> <span data-ttu-id="a3399-173">表示される既定のプロパティの多くは、`Get-Member` の結果を表示するときにプロパティとして表示されません。</span><span class="sxs-lookup"><span data-stu-id="a3399-173">A number of the default properties displayed don't show up as properties when viewing the results of `Get-Member`.</span></span> <span data-ttu-id="a3399-174">これは、表示される値の多く (`NPM(K)`、`PM(K)`、`WS(K)`、`CPU(s)` など) が計算プロパティであるためです。</span><span class="sxs-lookup"><span data-stu-id="a3399-174">This is because many of the displayed values, such as `NPM(K)`, `PM(K)`, `WS(K)`, and `CPU(s)`, are calculated properties.</span></span> <span data-ttu-id="a3399-175">実際のプロパティ名を調べるには、コマンドを `Get-Member` にパイプ処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3399-175">To determine the actual property names, the command must be piped to `Get-Member`.</span></span>

<span data-ttu-id="a3399-176">コマンドが出力を生成しない場合は、`Get-Member` にパイプ処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="a3399-176">If a command does not produce output, it can't be piped to `Get-Member`.</span></span> <span data-ttu-id="a3399-177">`Start-Service` は既定で出力を生成しないため、`Get-Member` にパイプ処理しようとするとエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a3399-177">Since `Start-Service` doesn't produce any output by default, it generates an error when you try to pipe it to `Get-Member`.</span></span>

```powershell
Start-Service -Name w32time | Get-Member
```

```Output
Get-Member : You must specify an object for the Get-Member cmdlet.
At line:1 char:31
+ Start-Service -Name w32time | Get-Member
+
    + CategoryInfo          : CloseError: (:) [Get-Member], InvalidOperationException
    + FullyQualifiedErrorId : NoObjectInGetMember,Microsoft.PowerShell.Commands.GetMembe
   rCommand
```

<span data-ttu-id="a3399-178">**PassThru** パラメーターを `Start-Service` コマンドレットと共に指定して出力を生成すると、エラーが発生することなく `Get-Member` にパイプ処理することができます。</span><span class="sxs-lookup"><span data-stu-id="a3399-178">The **PassThru** parameter can be specified with the `Start-Service` cmdlet make it produce output, which is then piped to `Get-Member` without error.</span></span>

```powershell
Start-Service -Name w32time -PassThru | Get-Member
```

```Output
   TypeName: System.ServiceProcess.ServiceController

Name                      MemberType    Definition
----                      ----------    ----------
Name                      AliasProperty Name = ServiceName
RequiredServices          AliasProperty RequiredServices = ServicesDependedOn
Disposed                  Event         System.EventHandler Disposed(System.Object, Sy...
Close                     Method        void Close()
Continue                  Method        void Continue()
CreateObjRef              Method        System.Runtime.Remoting.ObjRef CreateObjRef(ty...
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
WaitForStatus             Method        void WaitForStatus(System.ServiceProcess.Servi...
CanPauseAndContinue       Property      bool CanPauseAndContinue {get;}
CanShutdown               Property      bool CanShutdown {get;}
CanStop                   Property      bool CanStop {get;}
Container                 Property      System.ComponentModel.IContainer Container {get;}
DependentServices         Property      System.ServiceProcess.ServiceController[] Depe...
DisplayName               Property      string DisplayName {get;set;}
MachineName               Property      string MachineName {get;set;}
ServiceHandle             Property      System.Runtime.InteropServices.SafeHandle Serv...
ServiceName               Property      string ServiceName {get;set;}
ServicesDependedOn        Property      System.ServiceProcess.ServiceController[] Serv...
ServiceType               Property      System.ServiceProcess.ServiceType ServiceType ...
Site                      Property      System.ComponentModel.ISite Site {get;set;}
StartType                 Property      System.ServiceProcess.ServiceStartMode StartTy...
Status                    Property      System.ServiceProcess.ServiceControllerStatus ...
ToString                  ScriptMethod  System.Object ToString();
```

<span data-ttu-id="a3399-179">`Get-Member` にパイプ処理するには、コマンドがオブジェクトベースの出力を生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3399-179">To be piped to `Get-Member`, a command must produce object-based output.</span></span>

```powershell
Get-Service -Name w32time | Out-Host | Get-Member
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time

Get-Member : You must specify an object for the Get-Member cmdlet.
At line:1 char:40
+ Get-Service -Name w32time | Out-Host | Get-Member
+
    + CategoryInfo          : CloseError: (:) [Get-Member], InvalidOperationException
    + FullyQualifiedErrorId : NoObjectInGetMember,Microsoft.PowerShell.Commands.GetMemberCommand
```

<span data-ttu-id="a3399-180">`Out-Host` は PowerShell ホストに直接書き込みますが、パイプライン用のオブジェクトベースの出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="a3399-180">`Out-Host` writes directly to the PowerShell host, but it doesn't produce object-based output for the pipeline.</span></span> <span data-ttu-id="a3399-181">そのため、`Get-Member` にパイプ処理することはできません。</span><span class="sxs-lookup"><span data-stu-id="a3399-181">So it can't be piped to `Get-Member`.</span></span>

## <a name="active-directory"></a><span data-ttu-id="a3399-182">Active Directory</span><span class="sxs-lookup"><span data-stu-id="a3399-182">Active Directory</span></span>

> [!NOTE]
> <span data-ttu-id="a3399-183">このセクションを完了するには、この章の「要件」セクションに記載されているリモート サーバー管理ツールが必要です。</span><span class="sxs-lookup"><span data-stu-id="a3399-183">The Remote Server Administration Tools listed in the requirements section of this chapter are required to complete this section.</span></span> <span data-ttu-id="a3399-184">また、このドキュメントの概要で説明したように、Windows 10 ラボ環境コンピューターは、ラボ環境ドメインのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3399-184">Also, as mentioned in the introduction to this book, your Windows 10 lab environment computer must be a member of the lab environment domain.</span></span>

<span data-ttu-id="a3399-185">`Get-Command` を **Module** パラメーターと共に使用して、リモート サーバー管理ツールのインストール時に ActiveDirectory PowerShell モジュールの一部として追加されたコマンドを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3399-185">Use `Get-Command` with the **Module** parameter to determine what commands were added as part of the ActiveDirectory PowerShell module when the remote server administration tools were installed.</span></span>

```powershell
Get-Command -Module ActiveDirectory
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Add-ADCentralAccessPolicyMember                    1.0.0.0    ActiveDi...
Cmdlet          Add-ADComputerServiceAccount                       1.0.0.0    ActiveDi...
Cmdlet          Add-ADDomainControllerPasswordReplicationPolicy    1.0.0.0    ActiveDi...
Cmdlet          Add-ADFineGrainedPasswordPolicySubject             1.0.0.0    ActiveDi...
Cmdlet          Add-ADGroupMember                                  1.0.0.0    ActiveDi...
Cmdlet          Add-ADPrincipalGroupMembership                     1.0.0.0    ActiveDi...
Cmdlet          Add-ADResourcePropertyListMember                   1.0.0.0    ActiveDi...
Cmdlet          Clear-ADAccountExpiration                          1.0.0.0    ActiveDi...
Cmdlet          Clear-ADClaimTransformLink                         1.0.0.0    ActiveDi...
Cmdlet          Disable-ADAccount                                  1.0.0.0    ActiveDi...
...
```

<span data-ttu-id="a3399-186">合計 147 個のコマンドが ActiveDirectory PowerShell モジュールの一部として追加されました。</span><span class="sxs-lookup"><span data-stu-id="a3399-186">A total of 147 commands were added as part of the ActiveDirectory PowerShell module.</span></span> <span data-ttu-id="a3399-187">これらのコマンドの一部では、既定で、使用可能なプロパティの一部のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="a3399-187">Some commands of these commands only return a portion of the available properties by default.</span></span>

<span data-ttu-id="a3399-188">このモジュールのコマンドの名前に関して何か違う点に気が付きましたか。</span><span class="sxs-lookup"><span data-stu-id="a3399-188">Did you notice anything different about the names of the commands in this module?</span></span> <span data-ttu-id="a3399-189">コマンドの名詞部分には AD プレフィックスがあります。</span><span class="sxs-lookup"><span data-stu-id="a3399-189">The noun portion of the commands has an AD prefix.</span></span> <span data-ttu-id="a3399-190">これは、ほとんどのモジュールのコマンドによく見られます。</span><span class="sxs-lookup"><span data-stu-id="a3399-190">This is common to see on the commands of most modules.</span></span> <span data-ttu-id="a3399-191">プレフィックスは、名前の競合を防ぐために設計されています。</span><span class="sxs-lookup"><span data-stu-id="a3399-191">The prefix is designed to help prevent naming conflicts.</span></span>

```powershell
Get-ADUser -Identity mike | Get-Member
```

```Output
   TypeName: Microsoft.ActiveDirectory.Management.ADUser

Name              MemberType            Definition
----              ----------            ----------
Contains          Method                bool Contains(string propertyName)
Equals            Method                bool Equals(System.Object obj)
GetEnumerator     Method                System.Collections.IDictionaryEnumerator GetEn...
GetHashCode       Method                int GetHashCode()
GetType           Method                type GetType()
ToString          Method                string ToString()
Item              ParameterizedProperty Microsoft.ActiveDirectory.Management.ADPropert...
DistinguishedName Property              System.String DistinguishedName {get;set;}
Enabled           Property              System.Boolean Enabled {get;set;}
GivenName         Property              System.String GivenName {get;set;}
Name              Property              System.String Name {get;}
ObjectClass       Property              System.String ObjectClass {get;set;}
ObjectGUID        Property              System.Nullable`1[[System.Guid, mscorlib, Vers...
SamAccountName    Property              System.String SamAccountName {get;set;}
SID               Property              System.Security.Principal.SecurityIdentifier S...
Surname           Property              System.String Surname {get;set;}
UserPrincipalName Property              System.String UserPrincipalName {get;set;}
```

<span data-ttu-id="a3399-192">Active Directory に漠然と慣れているだけの場合でも、ユーザー アカウントにはこの例に示されているよりも多くのプロパティがあることに気付いていることでしょう。</span><span class="sxs-lookup"><span data-stu-id="a3399-192">Even if you're only vaguely familiar with Active Directory, you're probably aware that a user account has more properties than are shown in this example.</span></span>

<span data-ttu-id="a3399-193">`Get-ADUser` コマンドレットには **Properties** パラメーターがあります。これを使用すると、返される追加の (既定以外の) プロパティを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a3399-193">The `Get-ADUser` cmdlet has a **Properties** parameter that is used to specify the additional (non-default) properties you want to return.</span></span> <span data-ttu-id="a3399-194">`*` ワイルドカード文字を指定すると、そのすべてが返されます。</span><span class="sxs-lookup"><span data-stu-id="a3399-194">Specifying the `*` wildcard character returns all of them.</span></span>

```powershell
Get-ADUser -Identity mike -Properties * | Get-Member
```

```Output
   TypeName: Microsoft.ActiveDirectory.Management.ADUser

Name                                 MemberType            Definition
----                                 ----------            ----------
Contains                             Method                bool Contains(string proper...
Equals                               Method                bool Equals(System.Object obj)
GetEnumerator                        Method                System.Collections.IDiction...
GetHashCode                          Method                int GetHashCode()
GetType                              Method                type GetType()
ToString                             Method                string ToString()
Item                                 ParameterizedProperty Microsoft.ActiveDirectory.M...
AccountExpirationDate                Property              System.DateTime AccountExpi...
accountExpires                       Property              System.Int64 accountExpires...
AccountLockoutTime                   Property              System.DateTime AccountLock...
AccountNotDelegated                  Property              System.Boolean AccountNotDe...
AllowReversiblePasswordEncryption    Property              System.Boolean AllowReversi...
AuthenticationPolicy                 Property              Microsoft.ActiveDirectory.M...
AuthenticationPolicySilo             Property              Microsoft.ActiveDirectory.M...
BadLogonCount                        Property              System.Int32 BadLogonCount ...
badPasswordTime                      Property              System.Int64 badPasswordTim...
badPwdCount                          Property              System.Int32 badPwdCount {g...
CannotChangePassword                 Property              System.Boolean CannotChange...
CanonicalName                        Property              System.String CanonicalName...
Certificates                         Property              Microsoft.ActiveDirectory.M...
City                                 Property              System.String City {get;set;}
CN                                   Property              System.String CN {get;}
codePage                             Property              System.Int32 codePage {get;...
Company                              Property              System.String Company {get;...
CompoundIdentitySupported            Property              Microsoft.ActiveDirectory.M...
Country                              Property              System.String Country {get;...
countryCode                          Property              System.Int32 countryCode {g...
Created                              Property              System.DateTime Created {get;}
createTimeStamp                      Property              System.DateTime createTimeS...
Deleted                              Property              System.Boolean Deleted {get;}
Department                           Property              System.String Department {g...
Description                          Property              System.String Description {...
DisplayName                          Property              System.String DisplayName {...
DistinguishedName                    Property              System.String Distinguished...
Division                             Property              System.String Division {get...
DoesNotRequirePreAuth                Property              System.Boolean DoesNotRequi...
dSCorePropagationData                Property              Microsoft.ActiveDirectory.M...
EmailAddress                         Property              System.String EmailAddress ...
EmployeeID                           Property              System.String EmployeeID {g...
EmployeeNumber                       Property              System.String EmployeeNumbe...
Enabled                              Property              System.Boolean Enabled {get...
Fax                                  Property              System.String Fax {get;set;}
GivenName                            Property              System.String GivenName {ge...
HomeDirectory                        Property              System.String HomeDirectory...
HomedirRequired                      Property              System.Boolean HomedirRequi...
HomeDrive                            Property              System.String HomeDrive {ge...
HomePage                             Property              System.String HomePage {get...
HomePhone                            Property              System.String HomePhone {ge...
Initials                             Property              System.String Initials {get...
instanceType                         Property              System.Int32 instanceType {...
isDeleted                            Property              System.Boolean isDeleted {g...
KerberosEncryptionType               Property              Microsoft.ActiveDirectory.M...
LastBadPasswordAttempt               Property              System.DateTime LastBadPass...
LastKnownParent                      Property              System.String LastKnownPare...
lastLogoff                           Property              System.Int64 lastLogoff {ge...
lastLogon                            Property              System.Int64 lastLogon {get...
LastLogonDate                        Property              System.DateTime LastLogonDa...
lastLogonTimestamp                   Property              System.Int64 lastLogonTimes...
LockedOut                            Property              System.Boolean LockedOut {g...
logonCount                           Property              System.Int32 logonCount {ge...
LogonWorkstations                    Property              System.String LogonWorkstat...
Manager                              Property              System.String Manager {get;...
MemberOf                             Property              Microsoft.ActiveDirectory.M...
MNSLogonAccount                      Property              System.Boolean MNSLogonAcco...
MobilePhone                          Property              System.String MobilePhone {...
Modified                             Property              System.DateTime Modified {g...
modifyTimeStamp                      Property              System.DateTime modifyTimeS...
msDS-User-Account-Control-Computed   Property              System.Int32 msDS-User-Acco...
Name                                 Property              System.String Name {get;}
nTSecurityDescriptor                 Property              System.DirectoryServices.Ac...
ObjectCategory                       Property              System.String ObjectCategor...
ObjectClass                          Property              System.String ObjectClass {...
ObjectGUID                           Property              System.Nullable`1[[System.G...
objectSid                            Property              System.Security.Principal.S...
Office                               Property              System.String Office {get;s...
OfficePhone                          Property              System.String OfficePhone {...
Organization                         Property              System.String Organization ...
OtherName                            Property              System.String OtherName {ge...
PasswordExpired                      Property              System.Boolean PasswordExpi...
PasswordLastSet                      Property              System.DateTime PasswordLas...
PasswordNeverExpires                 Property              System.Boolean PasswordNeve...
PasswordNotRequired                  Property              System.Boolean PasswordNotR...
POBox                                Property              System.String POBox {get;set;}
PostalCode                           Property              System.String PostalCode {g...
PrimaryGroup                         Property              System.String PrimaryGroup ...
primaryGroupID                       Property              System.Int32 primaryGroupID...
PrincipalsAllowedToDelegateToAccount Property              Microsoft.ActiveDirectory.M...
ProfilePath                          Property              System.String ProfilePath {...
ProtectedFromAccidentalDeletion      Property              System.Boolean ProtectedFro...
pwdAnswer                            Property              System.String pwdAnswer {ge...
pwdLastSet                           Property              System.Int64 pwdLastSet {ge...
pwdQuestion                          Property              System.String pwdQuestion {...
SamAccountName                       Property              System.String SamAccountNam...
sAMAccountType                       Property              System.Int32 sAMAccountType...
ScriptPath                           Property              System.String ScriptPath {g...
sDRightsEffective                    Property              System.Int32 sDRightsEffect...
ServicePrincipalNames                Property              Microsoft.ActiveDirectory.M...
SID                                  Property              System.Security.Principal.S...
SIDHistory                           Property              Microsoft.ActiveDirectory.M...
SmartcardLogonRequired               Property              System.Boolean SmartcardLog...
sn                                   Property              System.String sn {get;set;}
State                                Property              System.String State {get;set;}
StreetAddress                        Property              System.String StreetAddress...
Surname                              Property              System.String Surname {get;...
Title                                Property              System.String Title {get;set;}
TrustedForDelegation                 Property              System.Boolean TrustedForDe...
TrustedToAuthForDelegation           Property              System.Boolean TrustedToAut...
UseDESKeyOnly                        Property              System.Boolean UseDESKeyOnl...
userAccountControl                   Property              System.Int32 userAccountCon...
userCertificate                      Property              Microsoft.ActiveDirectory.M...
UserPrincipalName                    Property              System.String UserPrincipal...
uSNChanged                           Property              System.Int64 uSNChanged {get;}
uSNCreated                           Property              System.Int64 uSNCreated {get;}
whenChanged                          Property              System.DateTime whenChanged...
whenCreated                          Property              System.DateTime whenCreated...
```

<span data-ttu-id="a3399-195">これで、それらしく見えるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a3399-195">Now that looks more like it.</span></span>

<span data-ttu-id="a3399-196">Active Directory ユーザー アカウントのプロパティが既定で制限される理由を考えてみてください。</span><span class="sxs-lookup"><span data-stu-id="a3399-196">Can you think of a reason why the properties of an Active Directory user account would be so limited by default?</span></span> <span data-ttu-id="a3399-197">運用版の Active Directory 環境で、すべてのユーザー アカウントについてすべてのプロパティを返した場合を想像してください。</span><span class="sxs-lookup"><span data-stu-id="a3399-197">Imagine if you returned every property for every user account in your production Active Directory environment.</span></span> <span data-ttu-id="a3399-198">ドメイン コントローラー自体だけでなく、ネットワークにも発生する可能性があるパフォーマンスの低下を考えてみてください。</span><span class="sxs-lookup"><span data-stu-id="a3399-198">Think of the performance degradation that you could cause, not only to the domain controllers themselves, but also to your network.</span></span> <span data-ttu-id="a3399-199">とにかく実際にすべてのプロパティが必要になるかどうかは疑問です。</span><span class="sxs-lookup"><span data-stu-id="a3399-199">It's doubtful that you'll actually need every property anyway.</span></span> <span data-ttu-id="a3399-200">存在するプロパティを調べる場合、単一のユーザー アカウントについてすべてのプロパティを返すことはまったく問題ありません。</span><span class="sxs-lookup"><span data-stu-id="a3399-200">Returning all of the properties for a single user account is perfectly acceptable when you're trying to determine what properties exist.</span></span>

<span data-ttu-id="a3399-201">プロトタイプを作成するときにコマンドを何度も実行することは珍しくありません。</span><span class="sxs-lookup"><span data-stu-id="a3399-201">It's not uncommon to run a command many times when prototyping it.</span></span> <span data-ttu-id="a3399-202">大きなクエリを実行する場合は、クエリを 1 回実行し、その結果を変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="a3399-202">If you're going to perform some huge query, query it once and store the results in a variable.</span></span> <span data-ttu-id="a3399-203">次に、面倒なクエリを繰り返し使用する代わりに、変数の内容を操作します。</span><span class="sxs-lookup"><span data-stu-id="a3399-203">Then work with the contents of the variable instead of repeatedly using some expensive query.</span></span>

```powershell
$Users = Get-ADUser -Identity mike -Properties *
```

<span data-ttu-id="a3399-204">前のコマンドを何度も実行する代わりに、`$Users` 変数の内容を使用します。</span><span class="sxs-lookup"><span data-stu-id="a3399-204">Use the contents of the `$Users` variable instead of running the previous command numerous times.</span></span>
<span data-ttu-id="a3399-205">Active Directory 内でそのユーザーに変更を加えても変数の内容は更新されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a3399-205">Keep in mind that the contents of the variable aren't updated when changes are made to that user in Active Directory.</span></span>

<span data-ttu-id="a3399-206">`$Users` 変数を `Get-Member` にパイプ処理すると、使用可能なプロパティを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="a3399-206">You could pipe the `$Users` variable to `Get-Member` to discover the available properties.</span></span>

```powershell
$Users | Get-Member
```

<span data-ttu-id="a3399-207">次に、`$Users` を `Select-Object` にパイプ処理して個々のプロパティを選択します。Active Directory に対して何度もクエリを実行する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a3399-207">Then select the individual properties by piping `$Users` to `Select-Object`, all without ever having to query Active Directory more than one time.</span></span>

```powershell
$Users | Select-Object -Property Name, LastLogonDate, LastBadPasswordAttempt
```

<span data-ttu-id="a3399-208">Active Directory に対して複数回クエリを実行する場合は、**Properties** パラメーターを使用して、任意の既定以外のプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="a3399-208">If you are going to query Active Directory more than once, use the **Properties** parameter to specify any non-default properties you want.</span></span>

```powershell
Get-ADUser -Identity mike -Properties LastLogonDate, LastBadPasswordAttempt
```

```Output
DistinguishedName      : CN=Mike F. Robbins,OU=Sales,DC=mikefrobbins,DC=com
Enabled                : True
GivenName              : Mike
LastBadPasswordAttempt : 2/4/2017 10:46:15 AM
LastLogonDate          : 2/18/2017 12:45:14 AM
Name                   : Mike F. Robbins
ObjectClass            : user
ObjectGUID             : a82a8c58-1332-4a57-a6e2-68e0c750ea56
SamAccountName         : mike
SID                    : S-1-5-21-2989741381-570885089-3319121794-1108
Surname                : Robbins
UserPrincipalName      : miker@mikefrobbins.com
```

## <a name="summary"></a><span data-ttu-id="a3399-209">まとめ</span><span class="sxs-lookup"><span data-stu-id="a3399-209">Summary</span></span>

<span data-ttu-id="a3399-210">この章では、コマンドによって生成されるオブジェクトの種類を調べる方法、コマンドで使用できるプロパティとメソッドを調べる方法、および既定で返されるプロパティを制限するコマンドを操作する方法を学習しました。</span><span class="sxs-lookup"><span data-stu-id="a3399-210">In this chapter, you've learned how to determine what type of object a command produces, how to determine what properties and methods are available for a command, and how to work with commands that limit the properties that are returned by default.</span></span>

## <a name="review"></a><span data-ttu-id="a3399-211">確認</span><span class="sxs-lookup"><span data-stu-id="a3399-211">Review</span></span>

1. <span data-ttu-id="a3399-212">`Get-Process` コマンドレットではどのような種類のオブジェクトが生成されますか。</span><span class="sxs-lookup"><span data-stu-id="a3399-212">What type of object does the `Get-Process` cmdlet produce?</span></span>
1. <span data-ttu-id="a3399-213">コマンドの使用可能なプロパティを調べるにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="a3399-213">How do you determine what the available properties are for a command?</span></span>
1. <span data-ttu-id="a3399-214">何かを取得するためのコマンドが存在する一方で、それを設定するためのコマンドがない場合、何を確認する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="a3399-214">If a command exists for getting something but not for setting the same thing, what should you check for?</span></span>
1. <span data-ttu-id="a3399-215">既定で出力を生成しない特定のコマンドで出力を生成するにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="a3399-215">How can certain commands that don't produce output by default be made to produce output?</span></span>
1. <span data-ttu-id="a3399-216">大量の出力を生成するコマンドの結果を処理する場合は、どのようなことを検討する必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="a3399-216">If you're going to be working with the results of a command that produces an enormous amount of output, what should you consider doing?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="a3399-217">推奨トピック</span><span class="sxs-lookup"><span data-stu-id="a3399-217">Recommended Reading</span></span>

- <span data-ttu-id="a3399-218">[Get-Member][]</span><span class="sxs-lookup"><span data-stu-id="a3399-218">[Get-Member][]</span></span>
- <span data-ttu-id="a3399-219">[オブジェクトの構造を表示する (Get-member)][]</span><span class="sxs-lookup"><span data-stu-id="a3399-219">[Viewing Object Structure (Get-Member)][]</span></span>
- <span data-ttu-id="a3399-220">[about_Objects][]</span><span class="sxs-lookup"><span data-stu-id="a3399-220">[about_Objects][]</span></span>
- <span data-ttu-id="a3399-221">[about_Properties][]</span><span class="sxs-lookup"><span data-stu-id="a3399-221">[about_Properties][]</span></span>
- <span data-ttu-id="a3399-222">[about_Methods][]</span><span class="sxs-lookup"><span data-stu-id="a3399-222">[about_Methods][]</span></span>
- <span data-ttu-id="a3399-223">[何かを開始または停止する PowerShell コマンドレットがない場合、Get コマンドレットのメソッドを確認することを忘れないでください][use-methods]</span><span class="sxs-lookup"><span data-stu-id="a3399-223">[No PowerShell Cmdlet to Start or Stop Something? Don’t Forget to Check for Methods on the Get Cmdlets][use-methods]</span></span>

<!-- link references -->
[Windows 用 RSAT]: https://support.microsoft.com/help/2693643
[RSAT for Windows]: https://support.microsoft.com/help/2693643
[Windows 管理モジュール]: /powershell/scripting/whats-new/module-compatibility#windows-management-modules
[Windows Management modules]: /powershell/scripting/whats-new/module-compatibility#windows-management-modules
[Get-Member]: /powershell/module/microsoft.powershell.utility/get-member
[オブジェクトの構造を表示する (Get-member)]: /powershell/scripting/samples/viewing-object-structure--get-member-
[Viewing Object Structure (Get-Member)]: /powershell/scripting/samples/viewing-object-structure--get-member-
[about_Objects]: /powershell/module/microsoft.powershell.core/about/about_objects
[about_Properties]: /powershell/module/microsoft.powershell.core/about/about_properties
[about_Methods]: /powershell/module/microsoft.powershell.core/about/about_methods
[use-methods]: https://mikefrobbins.com/2016/12/15/no-powershell-cmdlet-to-start-or-stop-something-dont-forget-to-check-for-methods-on-the-get-cmdlets/
[SMSS]: /sql/ssms/download-sql-server-management-studio-ssms
