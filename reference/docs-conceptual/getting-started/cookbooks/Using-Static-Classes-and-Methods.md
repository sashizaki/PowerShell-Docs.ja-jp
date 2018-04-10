---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: 静的なクラスとメソッドの使用
ms.assetid: 418ad766-afa6-4b8c-9a44-471889af7fd9
ms.openlocfilehash: 0f2b02c3a40365ad0335118b057a4e548c9f6535
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="using-static-classes-and-methods"></a><span data-ttu-id="64008-103">静的なクラスとメソッドの使用</span><span class="sxs-lookup"><span data-stu-id="64008-103">Using Static Classes and Methods</span></span>
<span data-ttu-id="64008-104">.NET Framework のクラスの中には、**New-Object** では作成できないものもあります。</span><span class="sxs-lookup"><span data-stu-id="64008-104">Not all .NET Framework classes can be created by using **New-Object**.</span></span> <span data-ttu-id="64008-105">たとえば、**New-Object** で **System.Environment** オブジェクトや **System.Math** オブジェクトを作成しようとすると、次のようなエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="64008-105">For example, if you try to create a **System.Environment** or a **System.Math** object with **New-Object**, you will get the following error messages:</span></span>

```
PS> New-Object System.Environment
New-Object : Constructor not found. Cannot find an appropriate constructor for
type System.Environment.
At line:1 char:11
+ New-Object  <<<< System.Environment

PS> New-Object System.Math
New-Object : Constructor not found. Cannot find an appropriate constructor for
type System.Math.
At line:1 char:11
+ New-Object  <<<< System.Math
```

<span data-ttu-id="64008-106">エラーが発生する理由は、これらのクラスからは、新しいオブジェクトを作成することができないためです。</span><span class="sxs-lookup"><span data-stu-id="64008-106">These errors occur because there is no way to create a new object from these classes.</span></span> <span data-ttu-id="64008-107">これらのクラスは、メソッドおよびプロパティが収められている参照用のライブラリであり、状態の変化を伴いません。</span><span class="sxs-lookup"><span data-stu-id="64008-107">These classes are reference libraries of methods and properties that do not change state.</span></span> <span data-ttu-id="64008-108">これらのメソッドやプロパティは、オブジェクトを作成しなくても使用できます。</span><span class="sxs-lookup"><span data-stu-id="64008-108">You don't need to create them, you simply use them.</span></span> <span data-ttu-id="64008-109">これらのクラスやメソッドは、作成、破棄、変更されないため、*静的クラス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="64008-109">Classes and methods such as these are called *static classes* because they are not created, destroyed, or changed.</span></span> <span data-ttu-id="64008-110">この点をわかりやすく説明するために、実際に静的クラスを使用する例を紹介します。</span><span class="sxs-lookup"><span data-stu-id="64008-110">To make this clear we will provide examples that use static classes.</span></span>

### <a name="getting-environment-data-with-systemenvironment"></a><span data-ttu-id="64008-111">System.Environment による環境データの取得</span><span class="sxs-lookup"><span data-stu-id="64008-111">Getting Environment Data with System.Environment</span></span>
<span data-ttu-id="64008-112">通常、Windows PowerShell でオブジェクトを操作するために最初に行うことは、Get-Member を使用して、そのオブジェクトに含まれているメンバーを調べることです。</span><span class="sxs-lookup"><span data-stu-id="64008-112">Usually, the first step in working with an object in Windows PowerShell is to use Get-Member to find out what members it contains.</span></span> <span data-ttu-id="64008-113">静的クラスの場合、実際のクラスがオブジェクトではないため、このプロセスが若干異なります。</span><span class="sxs-lookup"><span data-stu-id="64008-113">With static classes, the process is a little different because the actual class is not an object.</span></span>

#### <a name="referring-to-the-static-systemenvironment-class"></a><span data-ttu-id="64008-114">静的クラス System.Environment の参照</span><span class="sxs-lookup"><span data-stu-id="64008-114">Referring to the Static System.Environment Class</span></span>
<span data-ttu-id="64008-115">静的クラスを参照するには、そのクラス名を角かっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="64008-115">You can refer to a static class by surrounding the class name with square brackets.</span></span> <span data-ttu-id="64008-116">たとえば、**System.Environment** を参照するには、角かっこの内側に名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="64008-116">For example, you can refer to **System.Environment** by typing the name within brackets.</span></span> <span data-ttu-id="64008-117">これにより、型に関する一般的な情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="64008-117">Doing so displays some generic type information:</span></span>

```
PS> [System.Environment]

IsPublic IsSerial Name                                     BaseType
-------- -------- ----                                     --------
True     False    Environment                              System.Object
```

> [!NOTE]
> <span data-ttu-id="64008-118">既に説明したように、**New-Object** を使用するとき、</span><span class="sxs-lookup"><span data-stu-id="64008-118">As we mentioned previously, Windows PowerShell automatically prepends '**System.**'</span></span> <span data-ttu-id="64008-119">型名の前には ’**System.**’ が自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="64008-119">to type names when you use **New-Object**.</span></span> <span data-ttu-id="64008-120">角かっこで囲まれた型名を使用する場合も同様です。つまり、**\[System.Environment]** は、**\[Environment]** と指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="64008-120">The same thing happens when using a bracketed type name, so you can specify **\[System.Environment]** as **\[Environment]**.</span></span>

<span data-ttu-id="64008-121">**System.Environment** クラスには、現在のプロセス (Windows PowerShell 内で作業している場合は powershell.exe) の作業環境に関する一般情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="64008-121">The **System.Environment** class contains general information about the working environment for the current process, which is powershell.exe when working within Windows PowerShell.</span></span>

<span data-ttu-id="64008-122">「**\[System.Environment] | Get-Member**」と入力してこのクラスの詳細を表示しようとすると、オブジェクトの種類は、**System.Environment** ではなく、**System.RuntimeType** であると報告されます。</span><span class="sxs-lookup"><span data-stu-id="64008-122">If you try to view details of this class by typing **\[System.Environment] | Get-Member**, the object type is reported as being **System.RuntimeType** , not **System.Environment**:</span></span>

```
PS> [System.Environment] | Get-Member

   TypeName: System.RuntimeType
```

<span data-ttu-id="64008-123">Get-Member で静的メンバーを表示するには、**Static** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="64008-123">To view static members with Get-Member, specify the **Static** parameter:</span></span>

```
PS> [System.Environment] | Get-Member -Static

   TypeName: System.Environment

Name                       MemberType Definition
----                       ---------- ----------
Equals                     Method     static System.Boolean Equals(Object ob...
Exit                       Method     static System.Void Exit(Int32 exitCode)
...
CommandLine                Property   static System.String CommandLine {get;}
CurrentDirectory           Property   static System.String CurrentDirectory ...
ExitCode                   Property   static System.Int32 ExitCode {get;set;}
HasShutdownStarted         Property   static System.Boolean HasShutdownStart...
MachineName                Property   static System.String MachineName {get;}
NewLine                    Property   static System.String NewLine {get;}
OSVersion                  Property   static System.OperatingSystem OSVersio...
ProcessorCount             Property   static System.Int32 ProcessorCount {get;}
StackTrace                 Property   static System.String StackTrace {get;}
SystemDirectory            Property   static System.String SystemDirectory {...
TickCount                  Property   static System.Int32 TickCount {get;}
UserDomainName             Property   static System.String UserDomainName {g...
UserInteractive            Property   static System.Boolean UserInteractive ...
UserName                   Property   static System.String UserName {get;}
Version                    Property   static System.Version Version {get;}
WorkingSet                 Property   static System.Int64 WorkingSet {get;}
TickCount                               ExitCode
```

<span data-ttu-id="64008-124">これで、System.Environment から、必要なプロパティを選んで表示できます。</span><span class="sxs-lookup"><span data-stu-id="64008-124">We can now select properties to view from System.Environment.</span></span>

#### <a name="displaying-static-properties-of-systemenvironment"></a><span data-ttu-id="64008-125">System.Environment の静的プロパティの表示</span><span class="sxs-lookup"><span data-stu-id="64008-125">Displaying Static Properties of System.Environment</span></span>

<span data-ttu-id="64008-126">System.Environment の場合はプロパティも静的です。通常のプロパティとは異なる方法で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64008-126">The properties of System.Environment are also static, and must be specified in a different way than normal properties.</span></span> <span data-ttu-id="64008-127">操作の対象が静的メソッドまたは静的プロパティであることを Windows PowerShell に伝えるには **::** を使用します。</span><span class="sxs-lookup"><span data-stu-id="64008-127">We use **::** to indicate to Windows PowerShell that we want to work with a static method or property.</span></span> <span data-ttu-id="64008-128">Windows PowerShell の起動に使ったコマンドを表示するには、次のように入力して、**CommandLine** プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="64008-128">To see the command that was used to launch Windows PowerShell, we check the **CommandLine** property by typing:</span></span>

```
PS> [System.Environment]::Commandline
"C:\Program Files\Windows PowerShell\v1.0\powershell.exe"
```

<span data-ttu-id="64008-129">オペレーティング システムのバージョンを確認するには、次のように入力して、OSVersion プロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="64008-129">To check the operating system version, display the OSVersion property by typing:</span></span>

```
PS> [System.Environment]::OSVersion

           Platform ServicePack         Version             VersionString
           -------- -----------         -------             -------------
            Win32NT Service Pack 2      5.1.2600.131072     Microsoft Windows...
```

<span data-ttu-id="64008-130">コンピューターがシャットダウンの処理中であるかどうかを確認するには、**HasShutdownStarted** プロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="64008-130">We can check whether the computer is in the process of shutting down by displaying the **HasShutdownStarted** property:</span></span>

```
PS> [System.Environment]::HasShutdownStarted
False
```

### <a name="doing-math-with-systemmath"></a><span data-ttu-id="64008-131">System.Math による数学的演算の実行</span><span class="sxs-lookup"><span data-stu-id="64008-131">Doing Math with System.Math</span></span>

<span data-ttu-id="64008-132">System.Math 静的クラスは、数学的演算を行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="64008-132">The System.Math static class is useful for performing some mathematical operations.</span></span> <span data-ttu-id="64008-133">**System.Math** の重要なメンバーのほとんどはメソッドであり、**Get-Member** を使って表示できます。</span><span class="sxs-lookup"><span data-stu-id="64008-133">The important members of **System.Math** are mostly methods, which we can display by using **Get-Member**.</span></span>

> [!NOTE]
> <span data-ttu-id="64008-134">System.Math には同じ名前の複数のメソッドが存在しますが、これらはパラメーターの型が異なります。</span><span class="sxs-lookup"><span data-stu-id="64008-134">System.Math has several methods with the same name, but they are distinguished by the type of their parameters.</span></span>

<span data-ttu-id="64008-135">**System.Math** クラスのメソッドを一覧表示するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="64008-135">Type the following command to list the methods of the **System.Math** class.</span></span>

```
PS> [System.Math] | Get-Member -Static -MemberType Methods

   TypeName: System.Math

Name            MemberType Definition
----            ---------- ----------
Abs             Method     static System.Single Abs(Single value), static Sy...
Acos            Method     static System.Double Acos(Double d)
Asin            Method     static System.Double Asin(Double d)
Atan            Method     static System.Double Atan(Double d)
Atan2           Method     static System.Double Atan2(Double y, Double x)
BigMul          Method     static System.Int64 BigMul(Int32 a, Int32 b)
Ceiling         Method     static System.Double Ceiling(Double a), static Sy...
Cos             Method     static System.Double Cos(Double d)
Cosh            Method     static System.Double Cosh(Double value)
DivRem          Method     static System.Int32 DivRem(Int32 a, Int32 b, Int3...
Equals          Method     static System.Boolean Equals(Object objA, Object ...
Exp             Method     static System.Double Exp(Double d)
Floor           Method     static System.Double Floor(Double d), static Syst...
IEEERemainder   Method     static System.Double IEEERemainder(Double x, Doub...
Log             Method     static System.Double Log(Double d), static System...
Log10           Method     static System.Double Log10(Double d)
Max             Method     static System.SByte Max(SByte val1, SByte val2), ...
Min             Method     static System.SByte Min(SByte val1, SByte val2), ...
Pow             Method     static System.Double Pow(Double x, Double y)
ReferenceEquals Method     static System.Boolean ReferenceEquals(Object objA...
Round           Method     static System.Double Round(Double a), static Syst...
Sign            Method     static System.Int32 Sign(SByte value), static Sys...
Sin             Method     static System.Double Sin(Double a)
Sinh            Method     static System.Double Sinh(Double value)
Sqrt            Method     static System.Double Sqrt(Double d)
Tan             Method     static System.Double Tan(Double a)
Tanh            Method     static System.Double Tanh(Double value)
Truncate        Method     static System.Decimal Truncate(Decimal d), static...
```

<span data-ttu-id="64008-136">これにより、いくつかの数学的メソッドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="64008-136">This displays several mathematical methods.</span></span> <span data-ttu-id="64008-137">以下は、いくつかの一般的なメソッドを実行した結果を示すコマンドの一覧です。</span><span class="sxs-lookup"><span data-stu-id="64008-137">Here is a list of commands that demonstrate how some of the common methods work:</span></span>

```
PS> [System.Math]::Sqrt(9)
3
PS> [System.Math]::Pow(2,3)
8
PS> [System.Math]::Floor(3.3)
3
PS> [System.Math]::Floor(-3.3)
-4
PS> [System.Math]::Ceiling(3.3)
4
PS> [System.Math]::Ceiling(-3.3)
-3
PS> [System.Math]::Max(2,7)
7
PS> [System.Math]::Min(2,7)
2
PS> [System.Math]::Truncate(9.3)
9
PS> [System.Math]::Truncate(-9.3)
-9
```