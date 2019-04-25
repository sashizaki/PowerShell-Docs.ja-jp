---
title: Windows PowerShell の書式設定ファイル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d4c8f84-ebd2-4405-bb10-cfc5400d4ad6
caps.latest.revision: 6
ms.openlocfilehash: 49344d32dfcef36a904772b4a7237646a63cb12a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62065380"
---
# <a name="windows-powershell-formatting-files"></a>Windows PowerShell 書式設定ファイル

Windows PowerShell には、いくつかの書式設定ファイルが用意されています (. format.ps1xml) のインストール ディレクトリ内にある (`$pshome`)。 これらの各ファイルには、特定の一連の .NET オブジェクトの既定の表示を定義します。 これらのファイルを変更しない必要があります。 ただし、独自のカスタム書式設定ファイルを作成するための参照としてそれらを使用することができます。

Certificate.Format.ps1xml は、x.509 証明書などの証明書ストアと証明書ストア内のオブジェクトの表示を定義します。

DotNetTypes.Format.ps1xml は、CultureInfo、FileVersionInfo、および EventLogEntry オブジェクトなどの他の .NET オブジェクトの表示を定義します。

FileSystem.Format.ps1xml は、ファイルとディレクトリのオブジェクトなどのファイル システム オブジェクトの表示を定義します。

使用されるさまざまなビューを Help.Format.ps1xml 定義、 [Get-help](/powershell/module/Microsoft.PowerShell.Core/Get-Help)フル、パラメーター、および例の詳細なビューなどのコマンドレット。

PowerShellCore.Format.ps1xml 定義によって返されるオブジェクトなどの Windows PowerShell コア コマンドレットによって生成されたオブジェクトの表示、 [Get-member](/powershell/module/Microsoft.PowerShell.Utility/Get-Member)と[Get-history](/powershell/module/Microsoft.PowerShell.Core/Get-History)コマンドレット。

PowerShellTrace.Format.ps1xml 定義のトレース オブジェクトによって生成されるものなどの表示、 [Trace-command](/powershell/module/Microsoft.PowerShell.Utility/Trace-Command)コマンドレット。

Registry.Format.ps1xml では、レジストリ オブジェクト キーとエントリのオブジェクトなどの表示を定義します。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](../cmdlet/writing-a-windows-powershell-cmdlet.md)
