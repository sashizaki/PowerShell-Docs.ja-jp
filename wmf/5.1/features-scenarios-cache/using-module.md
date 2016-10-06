---
title: "'using module' の FullyQuilifiedModuleName"
author: jaimeo
contributor: vors
translationtype: Human Translation
ms.sourcegitcommit: e39aa2e5cbda0c83e24e21c4459d957d8baaff25
ms.openlocfilehash: e09cfe0994ac523fd10658955731a93b6c176c88

---

'using module' の FullyQuilifiedModuleName
=========================

`using module` は PowerShell の他のモジュール関連構造と同様に動作します。

WMF 5.0 の問題
----------

* `using module` でモジュール バージョンを指定する方法がありません。
* システムに複数のバージョンのモジュールが存在する場合、エラーになります。

WMF 5.1
----------

* `ModuleSpecification` [ハッシュ テーブル](https://msdn.microsoft.com/en-us/library/jj136290(v=vs.85).aspx)を使用できます。 このハッシュテーブルの形式は次と同じです `Get-Module -FullyQualifiedName`

**次に例を示します。** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`

* モジュールに複数のバージョンが存在する場合、PowerShell は `Import-Module` と**同じ解決ロジック**を使用し、エラーを返しません。

* これで `using module` が `Import-Module` と `Import-DscResource` に合わせて調整されます。



<!--HONumber=Aug16_HO3-->


