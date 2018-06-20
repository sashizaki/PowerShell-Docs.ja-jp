---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: ce5afc2f90f78433b64bf5b41946fc7506c43504
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34219652"
---
# <a name="import-dscresource-keyword-supports--moduleversion-parameter"></a>-ModuleVersion パラメーターをサポートする Import-DscResource キーワード

DSC 構成を作成するときに使用できる、`Import-DscResource` dynamic キーワードに新しいパラメーターを追加しました。 構成の作成者は、どのモジュール バージョンから DSC リソースを読み込むかを正確に指定できます。 キーワードの新しい構文は次の通りです:

```powershell
Import-DscResource [-Name <ResourceName(s)>] [-ModuleName <ModuleName(s)>] [-ModuleVersion <ModuleVersion>]
```

* **Name**: インポートする 1 つまたは複数のリソースの名前。
* **ModuleName**: モジュール名、またはインポートする 1 つまたは複数のモジュールの ModuleSpecification オブジェクト。
* **ModuleVersion**: インポートするモジュールのバージョン。 ModuleName が使用される場合、1 つの名前で 1 つのモジュールのみを表す必要があります。

Windows PowerShell ISE では、IntelliSense と共に表示されます。

![](../images/Import-DscResource-Modversion.jpg)

**注**: `–ModuleVersion` パラメーターは `–ModuleName` パラメーターと組み合わせてのみ使用できます。 `–Name` パラメーターのみを使用したリソース名では、使用できません。

これまでは、DSC リソースを読み込むときに、モジュールのバージョンを指定する唯一の方法は、`–ModuleName @{ModuleName="UserConfigProvider";ModuleVersion="3.0"}` などのモジュール指定オブジェクトを使用する方法のみでした。
