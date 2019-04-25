---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: オブジェクトの一部を選択する (Select-Object)
ms.assetid: 72e64b1a-d351-4500-9da3-24d8a71d7a92
ms.openlocfilehash: 323c57ba4462e20d9713fb74732989584f5a993f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057898"
---
# <a name="selecting-parts-of-objects-select-object"></a>オブジェクトの一部を選択する (Select-Object)

**Select-Object** コマンドレットを使用して、Windows PowerShell のオブジェクトを新規作成、またはカスタマイズできます。それらのオブジェクトには、作成時に使用する元のオブジェクトから選択したプロパティを含めることができます。 次のコマンドを入力して、Win32_LogicalDisk WMI クラスの Name および FreeSpace プロパティのみを含む、新規オブジェクトを作成します。

```
PS> Get-WmiObject -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace

Name                                    FreeSpace
----                                    ---------
C:                                      50664845312
```

そのコマンドの発行後に、データの種類を表示することはできません。しかし、Select-Object の後に、結果を Get-Member にパイプする場合、次のように PSCustomObject という新しい種類のオブジェクトを作成することを指定できます。

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

Select-Object には、数多くの用途があります。 その 1 つはデータのレプリケーションで、その後変更することができます。 これで、前のセクションで取り上げた問題に対処できるようになりました。 新規作成したオブジェクトの FreeSpace の値を更新することができ、その出力にはわかりやすいラベルが含まれています。

```
Get-WmiObject -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace | ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1024.0/1024.0; $_}
Name                                                                  FreeSpace
----                                                                  ---------
C:                                                                48317.7265625
```