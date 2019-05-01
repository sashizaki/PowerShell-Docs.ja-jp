---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 5ac9566979e1b761249f5cc7c62ed44047a2b9f6
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058014"
---
# <a name="register-a-powershell-repository"></a>PowerShell リポジトリの登録
内部リポジトリに対して動作するように PowerShellGet を構成できます。 これは、次の追加コマンドレットを使用して行います。
- Register-PSRepository:現在のユーザーのリポジトリを登録します。
- Unregister-PSRepository:現在のユーザーの登録済みリポジトリを削除します。
- Set-PSRepository:登録されたリポジトリの値を設定します。
- Get-PSRepository:現在のユーザーのすべての登録済みリポジトリを取得します。

リポジトリを登録した後、Find-Module および Install-Module を使用して操作できます。

```powershell
\#Register a default repository
Register-PSRepository –Name DemoRepo –SourceLocation “https://www.myget.org/F/powershellgetdemo/api/v2” –PublishLocation “<https://www.myget.org/F/powershellgetdemo/api/v2>/package” –InstallationPolicy –Trusted

\#Get all of the registered repositories
Get-PSRepository
Name SourceLocation
---- --------------
PSGallery https://msconfiggallery.cloudapp...
DemoRepo https://www.myget.org/F/powershe...

\#Search only the new repository for modules
Find-Module -Repository DemoRepo
Repository Version Name
---------- ------- ----
DemoRepo 1.0.1 xActiveDirectory
DemoRepo 1.1.1 SomeModule

\#By default, PowerShellGet operates against all registered repositories when none is specified. In this example, the “SomeModule” module is installed from the DemoRepo.
Install-Module SomeModule

\#Removing a repository
Unregister-PSRepository DemoRepo
```
