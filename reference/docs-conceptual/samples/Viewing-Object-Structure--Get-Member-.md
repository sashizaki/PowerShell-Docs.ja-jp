---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: オブジェクトの構造を表示する (Get-member)
ms.assetid: a1819ed2-2ef3-453a-b2b0-f3589c550481
ms.openlocfilehash: cc93e45e4306b3d623c1d3d1096dd20c1afc59c8
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403197"
---
# <a name="viewing-object-structure-get-member"></a><span data-ttu-id="b57a0-103">オブジェクトの構造を表示する (Get-member)</span><span class="sxs-lookup"><span data-stu-id="b57a0-103">Viewing Object Structure (Get-Member)</span></span>

<span data-ttu-id="b57a0-104">オブジェクトは、Windows PowerShell において非常に中心的な役割を担っているため、任意のオブジェクトの種類で動作するよう設計されたネイティブ コマンドがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="b57a0-104">Because objects play such a central role in Windows PowerShell, there are several native commands designed to work with arbitrary object types.</span></span> <span data-ttu-id="b57a0-105">最も重要なコマンドは、**Get-Member** コマンドです。</span><span class="sxs-lookup"><span data-stu-id="b57a0-105">The most important one is the **Get-Member** command.</span></span>

<span data-ttu-id="b57a0-106">コマンドで返されるオブジェクトを分析するための最も単純な手法は、パイプを使用してそのコマンドの出力を **Get-Member** コマンドレットに渡すことです。</span><span class="sxs-lookup"><span data-stu-id="b57a0-106">The simplest technique for analyzing the objects that a command returns is to pipe the output of that command to the **Get-Member** cmdlet.</span></span> <span data-ttu-id="b57a0-107">**Get-Member** コマンドレットでは、オブジェクトの種類の正式な名前とそのメンバーの完全な一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b57a0-107">The **Get-Member** cmdlet shows you the formal name of the object type and a complete listing of its members.</span></span> <span data-ttu-id="b57a0-108">返される要素の数が非常に多いことがあります。</span><span class="sxs-lookup"><span data-stu-id="b57a0-108">The number of elements that are returned can sometimes be overwhelming.</span></span> <span data-ttu-id="b57a0-109">たとえば、プロセス オブジェクトには 100 を超えるメンバーが含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="b57a0-109">For example, a process object can have over 100 members.</span></span>

<span data-ttu-id="b57a0-110">プロセス オブジェクトのすべてのメンバーを表示して、出力をすべて確認できるようにページングするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b57a0-110">To see all the members of a Process object and page the output so you can view all of it, type:</span></span>

```powershell
Get-Process | Get-Member | Out-Host -Paging
```

<span data-ttu-id="b57a0-111">このコマンドの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b57a0-111">The output from this command will look something like this:</span></span>

```output
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

<span data-ttu-id="b57a0-112">表示する要素をフィルター処理することで、この長い情報の一覧をより使いやすくできます。</span><span class="sxs-lookup"><span data-stu-id="b57a0-112">We can make this long list of information more usable by filtering for elements we want to see.</span></span> <span data-ttu-id="b57a0-113">**Get-Member** コマンドを使用すると、プロパティであるメンバーのみを一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="b57a0-113">The **Get-Member** command lets you list only members that are properties.</span></span> <span data-ttu-id="b57a0-114">プロパティにはいくつかの形式があります。</span><span class="sxs-lookup"><span data-stu-id="b57a0-114">There are several forms of properties.</span></span> <span data-ttu-id="b57a0-115">**Get-Member MemberType** パラメーターを値 **Properties** に設定すると、コマンドレットはすべての種類のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="b57a0-115">The cmdlet displays properties of any type if we set the **Get-Member MemberType** parameter to the value **Properties**.</span></span> <span data-ttu-id="b57a0-116">結果の一覧はこれでもまだ非常に長いですが、より管理しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="b57a0-116">The resulting list is still very long, but a bit more manageable:</span></span>

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
> <span data-ttu-id="b57a0-117">MemberType の指定できる値は、AliasProperty、CodeProperty、Property、NoteProperty、ScriptProperty、Properties、PropertySet、Method、CodeMethod、ScriptMethod、Methods、ParameterizedProperty、MemberSet、および All です。</span><span class="sxs-lookup"><span data-stu-id="b57a0-117">The allowed values of MemberType are AliasProperty, CodeProperty, Property, NoteProperty, ScriptProperty, Properties, PropertySet, Method, CodeMethod, ScriptMethod, Methods, ParameterizedProperty, MemberSet, and All.</span></span>

<span data-ttu-id="b57a0-118">プロセスには、60 を超えるプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="b57a0-118">There are over 60 properties for a process.</span></span> <span data-ttu-id="b57a0-119">Windows PowerShell では、既知のオブジェクトのほんの一部のプロパティしか表示されません。これは、すべてを表示すると管理が困難なほどの大量の情報が生成されるためです。</span><span class="sxs-lookup"><span data-stu-id="b57a0-119">The reason Windows PowerShell often shows only a handful of properties for any well-known object is that showing all of them would produce an unmanageable amount of information.</span></span>

> [!NOTE]
> <span data-ttu-id="b57a0-120">Windows PowerShell は、.format.ps1xml で終わる名前を持つ XML ファイルに保存されている情報を使用して、オブジェクトの種類を表示する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="b57a0-120">Windows PowerShell determines how to display an object type by using information stored in XML files that have names ending in .format.ps1xml.</span></span> <span data-ttu-id="b57a0-121">プロセス オブジェクトの書式設定データは、.NET System.Diagnostics.Process オブジェクトであり、DotNetTypes.format.ps1xml に保存されます。</span><span class="sxs-lookup"><span data-stu-id="b57a0-121">The formatting data for process objects, which are .NET System.Diagnostics.Process objects, is stored in DotNetTypes.format.ps1xml.</span></span>

<span data-ttu-id="b57a0-122">Windows PowerShell が既定で表示する以外のプロパティを確認する必要がある場合は、出力データを自分で書式設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b57a0-122">If you need to look at properties other than those that Windows PowerShell displays by default, you will need to format the output data yourself.</span></span> <span data-ttu-id="b57a0-123">これは、書式設定コマンドレットを使用して行えます。</span><span class="sxs-lookup"><span data-stu-id="b57a0-123">This can be done by using the format cmdlets.</span></span>