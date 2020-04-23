---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: レジストリ キーの操作
ms.openlocfilehash: 3feaf6d26db51a507434a6cec1f1095c9013efc8
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "75736847"
---
# <a name="working-with-registry-keys"></a>レジストリ キーの操作

レジストリ キーは PowerShell ドライブ上の項目であるため、それらの操作はファイルやフォルダーの操作によく似ています。 1 つの決定的な違いは、レジストリ ベースの PowerShell ドライブ上のすべての項目は、ファイル システム ドライブ上のフォルダーと同じように、コンテナーであることです。 ただし、レジストリ エントリとそれに関連する値は、個別の項目ではなく、項目のプロパティです。

## <a name="listing-all-subkeys-of-a-registry-key"></a>レジストリ キーのすべてのサブキーを一覧表示

`Get-ChildItem` を使用することにより、レジストリ キーの直下にあるすべての項目を表示することができます。 非表示の項目やシステム項目を表示するには、オプションの **Force** パラメーターを追加します。 たとえば、次のコマンドは、`HKCU:` レジストリ ハイブに対応する、PowerShell ドライブ `HKEY_CURRENT_USER` の直下にある項目を表示します。

```powershell
Get-ChildItem -Path HKCU:\ | Select-Object Name
```

```Output
   Hive: Microsoft.PowerShell.Core\Registry::HKEY_CURRENT_USER

Name
----
HKEY_CURRENT_USER\AppEvents
HKEY_CURRENT_USER\Console
HKEY_CURRENT_USER\Control Panel
HKEY_CURRENT_USER\DirectShow
HKEY_CURRENT_USER\dummy
HKEY_CURRENT_USER\Environment
HKEY_CURRENT_USER\EUDC
HKEY_CURRENT_USER\Keyboard Layout
HKEY_CURRENT_USER\MediaFoundation
HKEY_CURRENT_USER\Microsoft
HKEY_CURRENT_USER\Network
HKEY_CURRENT_USER\Printers
HKEY_CURRENT_USER\Software
HKEY_CURRENT_USER\System
HKEY_CURRENT_USER\Uninstall
HKEY_CURRENT_USER\WXP
HKEY_CURRENT_USER\Volatile Environment
```

これらは、レジストリ エディター (Regedit.exe) 内の `HKEY_CURRENT_USER` の下に表示される最上位キーです。

レジストリ プロバイダーの名前とその後に `::` を指定することにより、このレジストリ パスを指定することもできます。 レジストリ プロバイダーの完全名は `Microsoft.PowerShell.Core\Registry` ですが、短縮して `Registry` だけにすることができます。 次のいずれのコマンドを使用しても、`HKCU:` の直下にある内容を一覧表示できます。

```powershell
Get-ChildItem -Path Registry::HKEY_CURRENT_USER
Get-ChildItem -Path Microsoft.PowerShell.Core\Registry::HKEY_CURRENT_USER
Get-ChildItem -Path Registry::HKCU
Get-ChildItem -Path Microsoft.PowerShell.Core\Registry::HKCU
Get-ChildItem HKCU:
```

これらのコマンドは、`DIR`Cmd.exe**の** コマンドや UNIX シェルの `ls` を使用したときと同様に、直接含まれている項目のみ一覧表示します。 内包されている項目を表示するには、**Recurse** パラメーターを指定する必要があります。 `HKCU:` 内のすべてのレジストリ キーを一覧表示するには、次のコマンドを使用します。

```powershell
Get-ChildItem -Path HKCU:\ -Recurse
```

`Get-ChildItem` は、**Path**、**Filter**、**Include**、**Exclude** の各パラメーターを使用して複雑なフィルター処理機能を実行できますが、これらのパラメーターは通常、名前にのみ基づいています。 `Where-Object` コマンドレットを使用することにより、項目の他のプロパティに基づいた複雑なフィルター処理を実行できます。 次のコマンドは、1 つのサブキーと 4 つの値を持つ、`HKCU:\Software` 内のすべてのキーを検索します。

```powershell
Get-ChildItem -Path HKCU:\Software -Recurse |
  Where-Object {($_.SubKeyCount -le 1) -and ($_.ValueCount -eq 4) }
```

## <a name="copying-keys"></a>キーのコピー

コピーは `Copy-Item` を使用して行われます。 次の例では、`CurrentVersion` の `HKLM:\SOFTWARE\Microsoft\Windows\` サブキーとそのすべてのプロパティを、`HKCU:\` にコピーします。

```powershell
Copy-Item -Path 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion' -Destination HKCU:
```

レジストリ エディター内、または `Get-ChildItem` を使用してこの新しいキーを調べると、格納されているサブキーのコピーが新しい場所に存在しないことがわかります。 コンテナーのすべての内容をコピーするために、**Recurse** パラメーターを指定する必要があります。 上記のコピー コマンドを再帰的に実行するには、次のコマンドを使用します。

```powershell
Copy-Item -Path 'HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion' -Destination HKCU: -Recurse
```

ファイル システムのコピーは、使用可能な他の既存のツールを使用して行うこともできます。 任意のレジストリ編集ツール (**reg.exe**、**regini.exe**、**regedit.exe** など) およびレジストリの編集をサポートする COM オブジェクト (**WScript.Shell** や WMI の **StdRegProv** クラスなど) を Windows PowerShell 内から使用できます。

## <a name="creating-keys"></a>キーの作成

レジストリでのキーの新規作成は、ファイル システムに新しい項目を作成するよりも簡単です。 すべてのレジストリ キーはコンテナーであるため、項目の種類を指定する必要はなく、次に示すように、明示的なパスを指定するだけで済みます。

```powershell
New-Item -Path HKCU:\Software_DeleteMe
```

また、プロバイダーに基づくパスを使用して、キーを指定することもできます。

```powershell
New-Item -Path Registry::HKCU\Software_DeleteMe
```

## <a name="deleting-keys"></a>キーの削除

項目の削除は、基本的にすべてのプロバイダーで同じです。 次のコマンドを実行すると、確認を求められずに項目が削除されます。

```powershell
Remove-Item -Path HKCU:\Software_DeleteMe
Remove-Item -Path 'HKCU:\key with spaces in the name'
```

## <a name="removing-all-keys-under-a-specific-key"></a>特定のキーの下にあるすべてのキーの削除

内包されている項目を削除するには、`Remove-Item` を使用します。ただし、その項目に他の何らかの項目が含まれている場合は、削除の確認を求められます。 たとえば、作成した `HKCU:\CurrentVersion` サブキーを削除しようとしすると、次のメッセージが表示されます。

```powershell
Remove-Item -Path HKCU:\CurrentVersion
```

```Output
Confirm
The item at HKCU:\CurrentVersion\AdminDebug has children and the -recurse
parameter was not specified. If you continue, all children will be removed with
the item. Are you sure you want to continue?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
```

確認のメッセージを表示せずに、内包されている項目を削除するには、**Recurse** パラメーターを指定します。

```powershell
Remove-Item -Path HKCU:\CurrentVersion -Recurse
```

`HKCU:\CurrentVersion` 内のすべての項目を削除しますが、`HKCU:\CurrentVersion` そのものは削除しない場合は、代わりに次のように入力します。

```powershell
Remove-Item -Path HKCU:\CurrentVersion\* -Recurse
```
