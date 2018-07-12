---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC User リソース
ms.openlocfilehash: 04543351df19160a2da05ccea96e5d392d8c55bf
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37892527"
---
# <a name="dsc-user-resource"></a>DSC User リソース

適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

PowerShell Desired State Configuration (DSC) の **User** リソースは、ターゲット ノード上でローカル ユーザー アカウントを管理するためのメカニズムを備えています。

## <a name="syntax"></a>構文

```
User [string] #ResourceName
{
    UserName = [string]
    [ Description = [string] ]
    [ Disabled = [bool] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ FullName = [string] ]
    [ Password = [PSCredential] ]
    [ PasswordChangeNotAllowed = [bool] ]
    [ PasswordChangeRequired = [bool] ]
    [ PasswordNeverExpires = [bool] ]
    [ DependsOn = [string[]] ]
}
```

## <a name="properties"></a>プロパティ

|  プロパティ  |  説明   |
|---|---|
| UserName| 特定の状態を保証するアカウント名を示します。|
| 説明| ユーザー アカウントのために使用する説明を示します。|
| 無効| アカウントが有効になっているかどうかを示します。 このアカウントを無効にするには、このプロパティを `$true` に設定し、有効にするには `$false` に設定します。|
| Ensure| アカウントが存在するかどうかを示します。 このアカウントが存在することを保証するには、このプロパティを "Present" に設定し、アカウントが存在しないことを保証するには、"Absent" に設定します。|
| FullName| ユーザー アカウントのために使用する完全名の文字列を表します。|
| Password| このアカウントに使用するパスワードを示します。 |
| PasswordChangeNotAllowed| ユーザーがパスワードを変更できるかどうかを示します。 ユーザーがパスワードを変更できないようにするには、このプロパティを `$true` に設定し、ユーザーがパスワードを変更できるようにするには、`$false` に設定します。 既定値は `$false` です。|
| PasswordChangeRequired| ユーザーが次回ログオンしたときにパスワードを変更する必要があるかどうかを示します。 ユーザーがパスワードを変更する必要がある場合は、このプロパティを `$true` に設定します。 既定値は `$true` です。|
| PasswordNeverExpires| パスワードの有効期限が切れるかどうかを示します。 このアカウントのパスワードの有効期限が切れないようにするにはこのプロパティを `$true` に設定し、パスワードの有効期限が切れるようにする場合は `$false` を設定します。 既定値は `$false` です。|
| DependsOn | このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。|

## <a name="example"></a>例

```powershell
User UserExample
{
    Ensure = "Present"  # To ensure the user account does not exist, set Ensure to "Absent"
    UserName = "SomeName"
    Password = $passwordCred # This needs to be a credential object
    DependsOn = "[Group]GroupExample" # Configures GroupExample first
}
```