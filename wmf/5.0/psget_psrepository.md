---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 9a9bdac652512640209c20e3deb20d7abc0142c6
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34219533"
---
# <a name="register-a-powershell-repository"></a>PowerShell リポジトリの登録
内部リポジトリに対して動作するように PowerShellGet を構成できます。 これは、次の追加コマンドレットを使用して行います。
- Register-PSRepository: 現在のユーザーのリポジトリを登録します。
- Unregister-PSRepository: 現在のユーザーの登録済みリポジトリを削除します。
- Set-PSRepository: 登録されたリポジトリの値を設定します。
- Get-PSRepository: 現在のユーザーのすべての登録済みリポジトリを取得します。

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
