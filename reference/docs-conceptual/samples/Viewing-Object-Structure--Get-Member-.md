---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: オブジェクトの構造を表示する (Get-member)
description: Get-Member は、PowerShell のオブジェクトの型と構造を表示できる強力なツールです。
ms.openlocfilehash: 3c294fe47294e2cf8daf125aac55661dd38cf9bb
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501220"
---
# <a name="viewing-object-structure-get-member"></a><span data-ttu-id="b1c15-104">オブジェクトの構造を表示する (Get-member)</span><span class="sxs-lookup"><span data-stu-id="b1c15-104">Viewing Object Structure (Get-Member)</span></span>

<span data-ttu-id="b1c15-105">オブジェクトは、Windows PowerShell において非常に中心的な役割を担っているため、任意のオブジェクトの種類で動作するよう設計されたネイティブ コマンドがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="b1c15-105">Because objects play such a central role in Windows PowerShell, there are several native commands designed to work with arbitrary object types.</span></span> <span data-ttu-id="b1c15-106">最も重要なコマンドは、 **Get-Member** コマンドです。</span><span class="sxs-lookup"><span data-stu-id="b1c15-106">The most important one is the **Get-Member** command.</span></span>

<span data-ttu-id="b1c15-107">コマンドで返されるオブジェクトを分析するための最も単純な手法は、パイプを使用してそのコマンドの出力を **Get-Member** コマンドレットに渡すことです。</span><span class="sxs-lookup"><span data-stu-id="b1c15-107">The simplest technique for analyzing the objects that a command returns is to pipe the output of that command to the **Get-Member** cmdlet.</span></span> <span data-ttu-id="b1c15-108">**Get-Member** コマンドレットでは、オブジェクトの種類の正式な名前とそのメンバーの完全な一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1c15-108">The **Get-Member** cmdlet shows you the formal name of the object type and a complete listing of its members.</span></span> <span data-ttu-id="b1c15-109">返される要素の数が非常に多いことがあります。</span><span class="sxs-lookup"><span data-stu-id="b1c15-109">The number of elements that are returned can sometimes be overwhelming.</span></span> <span data-ttu-id="b1c15-110">たとえば、プロセス オブジェクトには 100 を超えるメンバーが含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="b1c15-110">For example, a process object can have over 100 members.</span></span>

<span data-ttu-id="b1c15-111">プロセス オブジェクトのすべてのメンバーを表示して、出力をすべて確認できるようにページングするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b1c15-111">To see all the members of a Process object and page the output so you can view all of it, type:</span></span>

```powershell
Get-Process | Get-Member | Out-Host -Paging
```

<span data-ttu-id="b1c15-112">このコマンドの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b1c15-112">The output from this command will look something like this:</span></span>

```Output
TypeName: System.Diagnostics.Process

Name                           MemberType     Definition
----                           ----------     ----------
Handles                        AliasProperty  Handles = Handlecount
Name                           AliasProperty  Name = ProcessName
NPM                            AliasProperty  NPM = NonpagedSystemMemorySize
PM                             AliasProperty  PM = PagedMemorySize
VM                             AliasProperty  VM = VirtualMemorySize
WS                             AliasProperty  WS = WorkingSet
add_Disposed                   Method         System.Void add_Disposed(Event...
...
```

<span data-ttu-id="b1c15-113">表示する要素をフィルター処理することで、この長い情報の一覧をより使いやすくできます。</span><span class="sxs-lookup"><span data-stu-id="b1c15-113">We can make this long list of information more usable by filtering for elements we want to see.</span></span> <span data-ttu-id="b1c15-114">**Get-Member** コマンドを使用すると、プロパティであるメンバーのみを一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="b1c15-114">The **Get-Member** command lets you list only members that are properties.</span></span> <span data-ttu-id="b1c15-115">プロパティにはいくつかの形式があります。</span><span class="sxs-lookup"><span data-stu-id="b1c15-115">There are several forms of properties.</span></span> <span data-ttu-id="b1c15-116">**Get-Member MemberType** パラメーターを値 **Properties** に設定すると、コマンドレットはすべての種類のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="b1c15-116">The cmdlet displays properties of any type if we set the **Get-Member MemberType** parameter to the value **Properties** .</span></span> <span data-ttu-id="b1c15-117">結果の一覧はこれでもまだ非常に長いですが、より管理しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="b1c15-117">The resulting list is still very long, but a bit more manageable:</span></span>

```
PS> Get-Process | Get-Member -MemberType Properties

   TypeName: System.Diagnostics.Process

Name                       MemberType     Definition
----                       ----------     ----------
Handles                    AliasProperty  Handles = Handlecount
Name                       AliasProperty  Name = ProcessName
...
ExitCode                   Property       System.Int32 ExitCode {get;}
...
Handle                     Property       System.IntPtr Handle {get;}
...
CPU                        ScriptProperty System.Object CPU {get=$this.Total...
...
Path                       ScriptProperty System.Object Path {get=$this.Main...
...
```

> [!NOTE]
> <span data-ttu-id="b1c15-118">MemberType の指定できる値は、AliasProperty、CodeProperty、Property、NoteProperty、ScriptProperty、Properties、PropertySet、Method、CodeMethod、ScriptMethod、Methods、ParameterizedProperty、MemberSet、および All です。</span><span class="sxs-lookup"><span data-stu-id="b1c15-118">The allowed values of MemberType are AliasProperty, CodeProperty, Property, NoteProperty, ScriptProperty, Properties, PropertySet, Method, CodeMethod, ScriptMethod, Methods, ParameterizedProperty, MemberSet, and All.</span></span>

<span data-ttu-id="b1c15-119">プロセスには、60 を超えるプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="b1c15-119">There are over 60 properties for a process.</span></span> <span data-ttu-id="b1c15-120">Windows PowerShell では、既知のオブジェクトのほんの一部のプロパティしか表示されません。これは、すべてを表示すると管理が困難なほどの大量の情報が生成されるためです。</span><span class="sxs-lookup"><span data-stu-id="b1c15-120">The reason Windows PowerShell often shows only a handful of properties for any well-known object is that showing all of them would produce an unmanageable amount of information.</span></span>

> [!NOTE]
> <span data-ttu-id="b1c15-121">Windows PowerShell は、.format.ps1xml で終わる名前を持つ XML ファイルに保存されている情報を使用して、オブジェクトの種類を表示する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="b1c15-121">Windows PowerShell determines how to display an object type by using information stored in XML files that have names ending in .format.ps1xml.</span></span> <span data-ttu-id="b1c15-122">プロセス オブジェクトの書式設定データは、.NET System.Diagnostics.Process オブジェクトであり、DotNetTypes.format.ps1xml に保存されます。</span><span class="sxs-lookup"><span data-stu-id="b1c15-122">The formatting data for process objects, which are .NET System.Diagnostics.Process objects, is stored in DotNetTypes.format.ps1xml.</span></span>

<span data-ttu-id="b1c15-123">Windows PowerShell が既定で表示する以外のプロパティを確認する必要がある場合は、出力データを自分で書式設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1c15-123">If you need to look at properties other than those that Windows PowerShell displays by default, you will need to format the output data yourself.</span></span> <span data-ttu-id="b1c15-124">これは、書式設定コマンドレットを使用して行えます。</span><span class="sxs-lookup"><span data-stu-id="b1c15-124">This can be done by using the format cmdlets.</span></span>
