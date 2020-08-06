---
title: Windows PowerShell のフォーマットファイル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 54fae12163f8d439c2acc24df17ed140a556cba0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783502"
---
# <a name="windows-powershell-formatting-files"></a>Windows PowerShell 書式設定ファイル

Windows PowerShell には、インストールディレクトリ () に格納されているいくつかの書式設定ファイル (.format.ps1xml) が用意されて `$pshome` います。 これらの各ファイルは、.NET オブジェクトの特定のセットの既定の表示を定義します。 これらのファイルは変更しないでください。 ただし、独自のカスタム書式設定ファイルを作成するためのリファレンスとして使用することもできます。

`Certificate.Format.ps1xml`X.509 証明書や証明書ストアなど、証明書ストア内のオブジェクトの表示を定義します。

`DotNetTypes.Format.ps1xml`CultureInfo、FileVersionInfo、EventLogEntry オブジェクトなど、その他の .NET オブジェクトの表示を定義します。

`FileSystem.Format.ps1xml`ファイルやディレクトリオブジェクトなどのファイルシステムオブジェクトの表示を定義します。

`Help.Format.ps1xml`詳細、完全、パラメーター、例のビューなど、 [get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help)コマンドレットで使用するさまざまなビューを定義します。

`PowerShellCore.Format.ps1xml`[Get Member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member)および[get-help](/powershell/module/Microsoft.PowerShell.Core/Get-History)コマンドレットによって返されるオブジェクトなど、Windows PowerShell のコアコマンドレットによって生成されるオブジェクトの表示を定義します。

`PowerShellTrace.Format.ps1xml`Trace[コマンド](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command)レットによって生成されるトレースオブジェクトなど、トレースオブジェクトの表示を定義します。

`Registry.Format.ps1xml`キーオブジェクトやエントリオブジェクトなど、レジストリオブジェクトの表示を定義します。

## <a name="see-also"></a>参照

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](../cmdlet/writing-a-windows-powershell-cmdlet.md)
