---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: オブジェクトの一部を選択する (Select-Object)
ms.openlocfilehash: 4d4c89f0b5103e4701a3af3cd07fcd7c8f1c697f
ms.sourcegitcommit: a6f13c16a535acea279c0ddeca72f1f0d8a8ce4c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2019
ms.locfileid: "67030107"
---
# <a name="selecting-parts-of-objects-select-object"></a><span data-ttu-id="ecea8-103">オブジェクトの一部を選択する (Select-Object)</span><span class="sxs-lookup"><span data-stu-id="ecea8-103">Selecting Parts of Objects (Select-Object)</span></span>

<span data-ttu-id="ecea8-104">**Select-Object** コマンドレットを使用して、Windows PowerShell のオブジェクトを新規作成、またはカスタマイズできます。それらのオブジェクトには、作成時に使用する元のオブジェクトから選択したプロパティを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ecea8-104">You can use the **Select-Object** cmdlet to create new, custom Windows PowerShell objects that contain properties selected from the objects you use to create them.</span></span> <span data-ttu-id="ecea8-105">次のコマンドを入力して、Win32_LogicalDisk WMI クラスの Name および FreeSpace プロパティのみを含む、新規オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ecea8-105">Type the following command to create a new object that includes only the Name and FreeSpace properties of the Win32_LogicalDisk WMI class:</span></span>

```
PS> Get-WmiObject -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace

Name                                    FreeSpace
----                                    ---------
C:                                      50664845312
```

<span data-ttu-id="ecea8-106">そのコマンドの発行後に、データの種類を表示することはできません。しかし、Select-Object の後に、結果を Get-Member にパイプする場合、次のように PSCustomObject という新しい種類のオブジェクトを作成することを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ecea8-106">You cannot see the type of data after issuing that command, but if you pipe the result to Get-Member after the Select-Object, you can tell that you have a new type of object, a PSCustomObject:</span></span>

```
PS> Get-WmiObject -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace| Get-Member

   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       System.Boolean Equals(Object obj)
GetHashCode Method       System.Int32 GetHashCode()
GetType     Method       System.Type GetType()
ToString    Method       System.String ToString()
FreeSpace   NoteProperty  FreeSpace=...
Name        NoteProperty System.String Name=C:
```

<span data-ttu-id="ecea8-107">Select-Object には、数多くの用途があります。</span><span class="sxs-lookup"><span data-stu-id="ecea8-107">Select-Object has many uses.</span></span> <span data-ttu-id="ecea8-108">その 1 つはデータのレプリケーションで、その後変更することができます。</span><span class="sxs-lookup"><span data-stu-id="ecea8-108">One of them is replicating data that you can then modify.</span></span> <span data-ttu-id="ecea8-109">これで、前のセクションで取り上げた問題に対処できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ecea8-109">We can now handle the problem we ran across in the previous section.</span></span> <span data-ttu-id="ecea8-110">新規作成したオブジェクトの FreeSpace の値を更新することができ、その出力にはわかりやすいラベルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ecea8-110">We can update the value of FreeSpace in our newly-created objects and the output will include the descriptive label:</span></span>

```
Get-WmiObject -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace | ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1024.0/1024.0; $_}
Name                                                                  FreeSpace
----                                                                  ---------
C:                                                                48317.7265625
```
